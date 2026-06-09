# DOSFindLocalDirectory(x,x)

- ea: `0x1000b790`
- end: `0x1000b7a0`
- name: `_DOSFindLocalDirectory@8`
- size: `16`
- prototype: `int __stdcall(LPWSTR lpBuffer, DWORD nBufferLength)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1000d130`
- `0x10011d90`

## callees

- `0x1002aed0`

## pseudocode

```c
DWORD __stdcall DOSFindLocalDirectory(LPWSTR lpBuffer, DWORD nBufferLength)
{
  return JetGetTempPathW(nBufferLength, lpBuffer);
}

```

## disassembly

```asm
0x1000b790  push    [esp+lpBuffer]; lpBuffer
0x1000b794  push    [esp+4+nBufferLength]; nBufferLength
0x1000b798  call    _JetGetTempPathW@8; JetGetTempPathW(x,x)
0x1000b79d  retn    8
```
