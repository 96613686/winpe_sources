# PcpTraceUpdateFlowEvent

- ea: `0x14000c164`
- end: `0x14000c212`
- name: `PcpTraceUpdateFlowEvent`
- size: `174`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000c460`
- `0x14000c5c0`
- `0x140020d30`
- `0x140020ec4`

## callees

- `0x14000c164`
- `0x1400116ec`

## pseudocode

```c
void PcpTraceUpdateFlowEvent(__int64 a1, int a2, int a3, __int64 a4, ...)
{
  int v4; // [rsp+B8h] [rbp+10h] BYREF
  int v5; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v6; // [rsp+D0h] [rbp+28h] BYREF
  va_list va; // [rsp+D0h] [rbp+28h]
  __int64 v8; // [rsp+D8h] [rbp+30h] BYREF
  va_list va1; // [rsp+D8h] [rbp+30h]
  __int64 v10; // [rsp+E0h] [rbp+38h] BYREF
  va_list va2; // [rsp+E0h] [rbp+38h]
  __int64 v12; // [rsp+E8h] [rbp+40h]
  va_list va3; // [rsp+F0h] [rbp+48h] BYREF

  va_start(va3, a4);
  va_start(va2, a4);
  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v8 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v10 = va_arg(va3, _QWORD);
  v12 = va_arg(va3, _QWORD);
  v5 = a3;
  v4 = a2;
  if ( PcgEventTraceEnabled )
    PcpEtwWriteFlowEvent(
      (const EVENT_DESCRIPTOR *)QOS_EVENT_PACER_UPDATE_FLOW,
      a1,
      8u,
      &v4,
      4,
      &v5,
      4,
      a4,
      32,
      va,
      2,
      va1,
      2,
      va2,
      4,
      v12,
      v10,
      va3,
      4);
}

```

## disassembly

```asm
0x14000c164  mov     r11, rsp
0x14000c167  mov     [r11+18h], r8d
0x14000c16b  mov     [rsp+arg_8], edx
0x14000c16f  sub     rsp, 0A8h
0x14000c176  mov     eax, cs:PcgEventTraceEnabled
0x14000c17c  test    eax, eax
0x14000c17e  jz      loc_14000C209
0x14000c184  mov     r10d, 8
0x14000c18a  lea     rax, [r11+48h]
0x14000c18e  lea     r8d, [r10-4]
0x14000c192  mov     [r11-18h], r8
0x14000c196  lea     edx, [r10-6]
0x14000c19a  mov     [r11-20h], rax
0x14000c19e  mov     eax, [r11+38h]
0x14000c1a2  mov     [r11-28h], eax
0x14000c1a6  mov     rax, [rsp+0A8h+arg_38]
0x14000c1ae  mov     [r11-30h], rax
0x14000c1b2  lea     rax, [r11+38h]
0x14000c1b6  mov     [r11-38h], r8
0x14000c1ba  mov     [r11-40h], rax
0x14000c1be  lea     rax, [r11+30h]
0x14000c1c2  mov     [r11-48h], rdx
0x14000c1c6  mov     [r11-50h], rax
0x14000c1ca  lea     rax, [r11+28h]
0x14000c1ce  mov     [r11-58h], rdx
0x14000c1d2  mov     rdx, rcx
0x14000c1d5  mov     [r11-60h], rax
0x14000c1d9  lea     rcx, QOS_EVENT_PACER_UPDATE_FLOW
0x14000c1e0  mov     qword ptr [r11-68h], 20h ; ' '
0x14000c1e8  lea     rax, [r11+18h]
0x14000c1ec  mov     [r11-70h], r9
0x14000c1f0  lea     r9, [r11+10h]
0x14000c1f4  mov     [r11-78h], r8
0x14000c1f8  mov     [r11-80h], rax
0x14000c1fc  mov     [rsp+0A8h+var_88], r8
0x14000c201  mov     r8d, r10d
0x14000c204  call    PcpEtwWriteFlowEvent
0x14000c209  add     rsp, 0A8h
0x14000c210  retn
```
