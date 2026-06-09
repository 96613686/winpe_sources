# WPP_SF_q

- ea: `0x180012df0`
- end: `0x180012e29`
- name: `WPP_SF_q`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001bd0`
- `0x180003d50`
- `0x180007aa0`
- `0x18000c400`

## callees

- `0x180003e70`

## pseudocode

```c
ULONG WPP_SF_q(_QWORD a1, USHORT a2, _QWORD a3, ...)
{
  va_list va; // [rsp+58h] [rbp+20h] BYREF

  va_start(va, a3);
  return FastWppTraceMessage(1028, a2, (ULONGLONG)WPP_e15037783097355a5233924022d92169_Traceguids, va, 8, 0);
}

```

## disassembly

```asm
0x180012df0  mov     [rsp+arg_18], r9
0x180012df5  sub     rsp, 38h
0x180012df9  mov     ecx, 404h
0x180012dfe  mov     [rsp+38h+var_10], 0
0x180012e07  lea     r9, [rsp+38h+arg_18]
0x180012e0c  movzx   edx, dx
0x180012e0f  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180012e16  mov     [rsp+38h+var_18], 8
0x180012e1f  call    FastWppTraceMessage
0x180012e24  add     rsp, 38h
0x180012e28  retn
```
