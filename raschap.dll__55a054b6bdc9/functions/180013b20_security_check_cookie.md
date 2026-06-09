# __security_check_cookie

- ea: `0x180013b20`
- end: `0x180013b3e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `64`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001520`
- `0x180002530`
- `0x180003530`
- `0x180003c10`
- `0x1800047a0`
- `0x180007060`
- `0x180007370`
- `0x1800084c0`
- `0x180008938`
- `0x180008cf0`
- `0x180009dc0`
- `0x18000b1a0`
- `0x18000b9b4`
- `0x18000cd68`
- `0x18000e634`
- `0x18000ead0`
- `0x1800105a8`
- `0x180011414`
- `0x180012bdc`
- `0x18001419c`
- `0x180014bd8`
- `0x18001538c`
- `0x180015780`
- `0x180015998`
- `0x180015db0`
- `0x180016280`
- `0x180016674`
- `0x180016b04`
- `0x180017fd8`
- `0x180018b50`
- `0x180018c8c`
- `0x180019034`
- `0x1800192e0`
- `0x180019c3c`
- `0x18001a1dc`
- `0x18001ab6c`
- `0x18001b3ec`
- `0x18001b878`
- `0x18001b9c8`
- `0x18001be60`
- `0x18001c300`
- `0x18001c570`
- `0x18001ca0c`
- `0x18001d330`
- `0x18001de54`
- `0x18001e9dc`
- `0x18001ead0`
- `0x18001f3d8`
- `0x18001f540`
- `0x18001f904`

## callees

- `0x180013b20`
- `0x180013bb0`

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
0x180013b20  cmp     rcx, cs:__security_cookie
0x180013b27  jnz     short ReportFailure
0x180013b29  rol     rcx, 10h
0x180013b2d  test    cx, 0FFFFh
0x180013b32  jnz     short RestoreRcx
0x180013b34  retn
0x180013b35  ror     rcx, 10h; StackCookie
0x180013b39  jmp     __report_gsfailure
```
