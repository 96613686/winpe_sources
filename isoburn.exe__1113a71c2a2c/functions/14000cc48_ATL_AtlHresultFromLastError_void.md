# ATL::AtlHresultFromLastError(void)

- ea: `0x14000cc48`
- end: `0x14000cc63`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d708`
- `0x14000e20c`
- `0x14000e534`

## callees

- `0x14000cc48`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000cc4c`
- `KERNEL32!GetLastError` at `0x14000cc4c`

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
0x14000cc48  sub     rsp, 28h
0x14000cc4c  call    cs:__imp_GetLastError
0x14000cc52  test    eax, eax
0x14000cc54  jle     short loc_14000CC5E
0x14000cc56  movzx   eax, ax
0x14000cc59  or      eax, 80070000h
0x14000cc5e  add     rsp, 28h
0x14000cc62  retn
```
