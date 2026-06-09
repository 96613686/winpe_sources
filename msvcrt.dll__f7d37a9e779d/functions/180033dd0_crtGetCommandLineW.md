# __crtGetCommandLineW

- ea: `0x180033dd0`
- end: `0x180033dd7`
- name: `__crtGetCommandLineW`
- size: `7`
- prototype: `LPWSTR __stdcall()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007a24`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180033dd0`

## pseudocode

```c
// attributes: thunk
LPWSTR __stdcall _crtGetCommandLineW()
{
  return GetCommandLineW();
}

```

## disassembly

```asm
0x180033dd0  jmp     cs:__imp_GetCommandLineW
```
