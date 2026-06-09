# ATL::AtlHresultFromLastError(void)

- ea: `0x140002bd8`
- end: `0x140002bf3`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004128`
- `0x140004f48`
- `0x140005384`

## callees

- `0x140002bd8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140002bdc`
- `KERNEL32!GetLastError` at `0x140002bdc`

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
0x140002bd8  sub     rsp, 28h
0x140002bdc  call    cs:__imp_GetLastError
0x140002be2  test    eax, eax
0x140002be4  jle     short loc_140002BEE
0x140002be6  movzx   eax, ax
0x140002be9  or      eax, 80070000h
0x140002bee  add     rsp, 28h
0x140002bf2  retn
```
