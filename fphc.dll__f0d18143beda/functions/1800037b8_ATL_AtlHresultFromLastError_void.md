# ATL::AtlHresultFromLastError(void)

- ea: `0x1800037b8`
- end: `0x1800037d3`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800037f4`
- `0x180004a88`
- `0x180005620`

## callees

- `0x1800037b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037bc`

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
0x1800037b8  sub     rsp, 28h
0x1800037bc  call    cs:__imp_GetLastError
0x1800037c2  test    eax, eax
0x1800037c4  jle     short loc_1800037CE
0x1800037c6  movzx   eax, ax
0x1800037c9  or      eax, 80070000h
0x1800037ce  add     rsp, 28h
0x1800037d2  retn
```
