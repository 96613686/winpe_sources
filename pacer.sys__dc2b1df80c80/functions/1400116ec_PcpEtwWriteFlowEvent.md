# PcpEtwWriteFlowEvent

- ea: `0x1400116ec`
- end: `0x14001174f`
- name: `PcpEtwWriteFlowEvent`
- size: `99`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000aca4`
- `0x14000adf8`
- `0x14000c164`
- `0x14000f970`
- `0x14000fa40`
- `0x14000fb90`

## callees

- `0x14001155c`
- `0x140013110`

## pseudocode

```c
void PcpEtwWriteFlowEvent(const EVENT_DESCRIPTOR *a1, __int64 a2, unsigned __int16 a3, ...)
{
  GUID v3; // [rsp+30h] [rbp-28h] BYREF
  va_list va; // [rsp+78h] [rbp+20h] BYREF

  va_start(va, a3);
  *(_QWORD *)v3.Data4 = *((_QWORD *)&QOS_FLOW_PROVIDER_GUID + 1);
  *(_QWORD *)&v3.Data1 = a2;
  PcpEtwWriteEvent(a1, &v3, 0, a3, (__int64 *)va);
}

```

## disassembly

```asm
0x1400116ec  mov     r11, rsp
0x1400116ef  mov     [r11+18h], r8w
0x1400116f4  mov     [r11+20h], r9
0x1400116f8  sub     rsp, 58h
0x1400116fc  mov     rax, cs:__security_cookie
0x140011703  xor     rax, rsp
0x140011706  mov     [rsp+58h+var_18], rax
0x14001170b  movups  xmm0, cs:QOS_FLOW_PROVIDER_GUID
0x140011712  mov     qword ptr [r11-28h], 0
0x14001171a  lea     rax, [r11+20h]
0x14001171e  movzx   r9d, r8w
0x140011722  mov     [r11-38h], rax
0x140011726  movdqu  [rsp+58h+var_28], xmm0
0x14001172c  mov     [r11-28h], rdx
0x140011730  xor     r8d, r8d; RelatedActivityId
0x140011733  lea     rdx, [r11-28h]; ActivityId
0x140011737  call    PcpEtwWriteEvent
0x14001173c  mov     rcx, [rsp+58h+var_18]
0x140011741  xor     rcx, rsp; StackCookie
0x140011744  call    __security_check_cookie
0x140011749  add     rsp, 58h
0x14001174d  retn
```
