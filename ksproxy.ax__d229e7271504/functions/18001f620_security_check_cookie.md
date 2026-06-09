# __security_check_cookie

- ea: `0x18001f620`
- end: `0x18001f63e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `85`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001038`
- `0x180007eb0`
- `0x180008208`
- `0x180008464`
- `0x180008690`
- `0x18000aaac`
- `0x18000d4b0`
- `0x18000d88c`
- `0x18000dd00`
- `0x18000f7e0`
- `0x180011840`
- `0x180011c20`
- `0x180012610`
- `0x180013d70`
- `0x180014a30`
- `0x1800157e8`
- `0x180015a90`
- `0x1800165a0`
- `0x180016a28`
- `0x180018adc`
- `0x1800191e0`
- `0x180019424`
- `0x1800196f0`
- `0x18001a840`
- `0x18001a950`
- `0x18001c5c4`
- `0x18001cf28`
- `0x18001de40`
- `0x18001e804`
- `0x180020428`
- `0x1800206cc`
- `0x180021340`
- `0x180021658`
- `0x180021fa0`
- `0x1800233a0`
- `0x180024140`
- `0x180024900`
- `0x180024d10`
- `0x180025480`
- `0x1800262d0`
- `0x180026de0`
- `0x180027350`
- `0x180027b00`
- `0x1800280d0`
- `0x180029ad0`
- `0x180029ee0`
- `0x18002a5f0`
- `0x18002cac4`
- `0x18002ecf0`
- `0x18002f6d8`

## callees

- `0x18001f620`
- `0x18001fbd0`

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
0x18001f620  cmp     rcx, cs:__security_cookie
0x18001f627  jnz     short ReportFailure
0x18001f629  rol     rcx, 10h
0x18001f62d  test    cx, 0FFFFh
0x18001f632  jnz     short RestoreRcx
0x18001f634  retn
0x18001f635  ror     rcx, 10h; StackCookie
0x18001f639  jmp     __report_gsfailure
```
