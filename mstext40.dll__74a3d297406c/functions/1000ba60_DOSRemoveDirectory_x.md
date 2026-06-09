# DOSRemoveDirectory(x)

- ea: `0x1000ba60`
- end: `0x1000ba83`
- name: `_DOSRemoveDirectory@4`
- size: `35`
- prototype: `int __stdcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1000d2b0`

## callees

- `0x1000ba60`
- `0x1002b360`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000ba73`
- `KERNEL32!GetLastError` at `0x1000ba73`

## pseudocode

```c
int __stdcall DOSRemoveDirectory(LPCWSTR lpPathName)
{
  if ( JetRemoveDirectoryW(lpPathName) )
    return 0;
  else
    return -(unsigned __int16)GetLastError();
}

```

## disassembly

```asm
0x1000ba60  push    [esp+lpPathName]; lpPathName
0x1000ba64  call    _JetRemoveDirectoryW@4; JetRemoveDirectoryW(x)
0x1000ba69  cmp     eax, 1
0x1000ba6c  jnz     short loc_1000BA73
0x1000ba6e  xor     eax, eax
0x1000ba70  retn    4
0x1000ba73  call    ds:__imp__GetLastError@0; GetLastError()
0x1000ba79  and     eax, 0FFFFh
0x1000ba7e  neg     eax
0x1000ba80  retn    4
```
