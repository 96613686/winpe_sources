# LoadMUILibraryW

- ea: `0x181089fd8`
- end: `0x18108a49d`
- name: `LoadMUILibraryW`
- size: `1221`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18067de04`
- `0x18084c508`
- `0x1810098f0`

## callees

- `0x1804e4c1c`
- `0x181089828`
- `0x1810898b0`
- `0x1810899d8`
- `0x181089b0c`
- `0x181089ba0`
- `0x181089d38`
- `0x181089fd8`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18108a046`
- `KERNEL32!LoadLibraryExW` at `0x18108a44d`
- `KERNEL32!LoadLibraryExW` at `0x18108a046`
- `KERNEL32!LoadLibraryExW` at `0x18108a44d`
- `KERNEL32!GetUserDefaultUILanguage` at `0x18108a101`
- `KERNEL32!GetUserDefaultUILanguage` at `0x18108a101`
- `KERNEL32!FreeLibrary` at `0x18108a2dc`
- `KERNEL32!FreeLibrary` at `0x18108a429`
- `KERNEL32!FreeLibrary` at `0x18108a464`
- `KERNEL32!FreeLibrary` at `0x18108a2dc`
- `KERNEL32!FreeLibrary` at `0x18108a429`
- `KERNEL32!FreeLibrary` at `0x18108a464`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18108a0db`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18108a0db`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18108a08f`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18108a08f`
- `KERNELBASE!GetSystemDefaultUILanguage` at `0x18108a1c5`
- `KERNELBASE!GetSystemDefaultUILanguage` at `0x18108a1c5`

## pseudocode

```c

```
