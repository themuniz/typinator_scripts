#!/usr/bin/env python3
"""
text_case.py
Manipulate the case of text on the clipboard.
"""

__author__ = "José Muñiz"
__version__ = 1
__license__ = "MIT"
__script__ = "text_case"

from logzero import logger, loglevel, logging
import sys
import subprocess


def main(transform_type='title'):
    """ Main entry point of the app """
    text = subprocess.run(['pbpaste'], encoding='utf-8', capture_output=True)
    logger.debug(f"Ran subprocess. Output: {text}")

    logger.debug(f"Transform type: {transform_type}") 
    if transform_type == 'upper':
        action = text.stdout.upper()
    elif transform_type == 'lower':
        action = text.stdout.lower()
    elif transform_type == 'title':
        action = text.stdout.title()

    logger.debug(f"Transformed text: {action}")

    sys.stdout.write(f'{action}')


if __name__ == "__main__":
    loglevel(logging.INFO)
    if len(sys.argv) > 1:
        logger.debug(f"Started with: {sys.argv}")
        main(transform_type=sys.argv[1])
    else:
        logger.debug(f"Started with {sys.argv}")
        main()
