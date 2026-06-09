# __security_check_cookie

- ea: `0x180001560`
- end: `0x18000157e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `61`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002340`
- `0x180002450`
- `0x180002ec4`
- `0x180003944`
- `0x1800039e8`
- `0x180003a8c`
- `0x180003b58`
- `0x180003c24`
- `0x180003cf0`
- `0x180003d94`
- `0x180003e60`
- `0x180003f04`
- `0x18000501c`
- `0x1800052b4`
- `0x180005cc8`
- `0x180006520`
- `0x180006740`
- `0x180006970`
- `0x180006c60`
- `0x180007060`
- `0x180007500`
- `0x180007cc0`
- `0x1800080f0`
- `0x180008330`
- `0x18000861c`
- `0x1800086c0`
- `0x180008764`
- `0x180008808`
- `0x1800088ac`
- `0x180008988`
- `0x180008a2c`
- `0x180008b10`
- `0x180008bb4`
- `0x180008c58`
- `0x180008d3c`
- `0x180008f30`
- `0x18000935c`
- `0x1800099c0`
- `0x18000a300`
- `0x18000ad70`
- `0x18000b5f0`
- `0x18000b970`
- `0x18000bbe0`
- `0x18000bf60`
- `0x18000c2a0`
- `0x18000c3a0`
- `0x18000c4a0`
- `0x18000cca0`
- `0x18000d5f0`
- `0x18000d780`

## callees

- `0x180001560`
- `0x180001af0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180001560  cmp     rcx, cs:__security_cookie
0x180001567  jnz     short ReportFailure
0x180001569  rol     rcx, 10h
0x18000156d  test    cx, 0FFFFh
0x180001572  jnz     short RestoreRcx
0x180001574  retn
0x180001575  ror     rcx, 10h; StackCookie
0x180001579  jmp     __report_gsfailure
```
