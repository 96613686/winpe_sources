# ATL::AtlHresultFromLastError(void)

- ea: `0x180003114`
- end: `0x18000312f`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003150`
- `0x180004d18`
- `0x180005b1c`
- `0x180005e3c`

## callees

- `0x180003114`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003118`
- `KERNEL32!GetLastError` at `0x180003118`

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
0x180003114  sub     rsp, 28h
0x180003118  call    cs:__imp_GetLastError
0x18000311e  test    eax, eax
0x180003120  jle     short loc_18000312A
0x180003122  movzx   eax, ax
0x180003125  or      eax, 80070000h
0x18000312a  add     rsp, 28h
0x18000312e  retn
```
