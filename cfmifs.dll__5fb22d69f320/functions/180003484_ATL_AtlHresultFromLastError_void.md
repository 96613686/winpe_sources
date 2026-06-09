# ATL::AtlHresultFromLastError(void)

- ea: `0x180003484`
- end: `0x18000349f`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004818`
- `0x18000547c`
- `0x18000579c`

## callees

- `0x180003484`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003488`

## pseudocode

```c
signed int ATL::AtlHresultFromLastError(void)
{
  signed int result; // eax

  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180003484  sub     rsp, 28h
0x180003488  call    cs:__imp_GetLastError
0x18000348e  test    eax, eax
0x180003490  jle     short loc_18000349A
0x180003492  movzx   eax, ax
0x180003495  or      eax, 80070000h
0x18000349a  add     rsp, 28h
0x18000349e  retn
```
