# DOSMakeDirectory(x)

- ea: `0x1000b980`
- end: `0x1000b9a5`
- name: `_DOSMakeDirectory@4`
- size: `37`
- prototype: `int __stdcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1000d130`

## callees

- `0x1000b980`
- `0x1002a850`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000b995`
- `KERNEL32!GetLastError` at `0x1000b995`

## pseudocode

```c
int __stdcall DOSMakeDirectory(LPCWSTR lpPathName)
{
  if ( JetCreateDirectoryW(lpPathName, 0) )
    return 0;
  else
    return -(unsigned __int16)GetLastError();
}

```

## disassembly

```asm
0x1000b980  push    0; lpSecurityAttributes
0x1000b982  push    [esp+4+lpPathName]; lpPathName
0x1000b986  call    _JetCreateDirectoryW@8; JetCreateDirectoryW(x,x)
0x1000b98b  cmp     eax, 1
0x1000b98e  jnz     short loc_1000B995
0x1000b990  xor     eax, eax
0x1000b992  retn    4
0x1000b995  call    ds:__imp__GetLastError@0; GetLastError()
0x1000b99b  and     eax, 0FFFFh
0x1000b9a0  neg     eax
0x1000b9a2  retn    4
```
