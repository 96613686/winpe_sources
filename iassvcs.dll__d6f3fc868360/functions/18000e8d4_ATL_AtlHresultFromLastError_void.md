# ATL::AtlHresultFromLastError(void)

- ea: `0x18000e8d4`
- end: `0x18000e8ef`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `signed int(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e910`
- `0x1800110a8`
- `0x18001217c`
- `0x18001249c`

## callees

- `0x18000e8d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e8d8`
- `KERNEL32!GetLastError` at `0x18000e8d8`

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
0x18000e8d4  sub     rsp, 28h
0x18000e8d8  call    cs:__imp_GetLastError
0x18000e8de  test    eax, eax
0x18000e8e0  jle     short loc_18000E8EA
0x18000e8e2  movzx   eax, ax
0x18000e8e5  or      eax, 80070000h
0x18000e8ea  add     rsp, 28h
0x18000e8ee  retn
```
