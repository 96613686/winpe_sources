# ATL::AtlHresultFromLastError(void)

- ea: `0x18000383c`
- end: `0x18000385e`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `34`
- prototype: `signed int(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000387c`
- `0x180004cf0`
- `0x18000596c`

## callees

- `0x18000383c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003840`
- `KERNEL32!GetLastError` at `0x180003840`

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
0x18000383c  sub     rsp, 28h
0x180003840  call    cs:__imp_GetLastError
0x180003847  nop     dword ptr [rax+rax+00h]
0x18000384c  test    eax, eax
0x18000384e  jle     short loc_180003858
0x180003850  movzx   eax, ax
0x180003853  or      eax, 80070000h
0x180003858  add     rsp, 28h
0x18000385c  retn
```
