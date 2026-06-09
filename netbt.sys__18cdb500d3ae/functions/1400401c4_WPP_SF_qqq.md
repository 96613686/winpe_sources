# WPP_SF_qqq

- ea: `0x1400401c4`
- end: `0x14004020e`
- name: `WPP_SF_qqq`
- size: `74`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1400176f0`
- `0x1400178f0`
- `0x140021610`
- `0x14002410c`
- `0x140024cc0`
- `0x14002d608`
- `0x14002def0`
- `0x140048ac0`
- `0x14004bb10`
- `0x14004ce30`
- `0x14004d120`

## callees

- `0x140030bc8`

## pseudocode

```c
void WPP_SF_qqq(__int16 a1, USHORT a2, ULONGLONG a3, ...)
{
  __int64 v3; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  __int64 v5; // [rsp+80h] [rbp+28h] BYREF
  va_list va1; // [rsp+80h] [rbp+28h]
  va_list va2; // [rsp+88h] [rbp+30h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v3 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v5 = va_arg(va2, _QWORD);
  FastWppTraceMessage(a1, a2, a3, va, 8, va1, 8, va2, 8, 0);
}

```

## disassembly

```asm
0x1400401c4  mov     r11, rsp
0x1400401c7  mov     [r11+20h], r9
0x1400401cb  sub     rsp, 58h
0x1400401cf  mov     qword ptr [r11-10h], 0
0x1400401d7  lea     rax, [r11+30h]
0x1400401db  mov     r9d, 8
0x1400401e1  movzx   edx, dx
0x1400401e4  mov     [r11-18h], r9
0x1400401e8  mov     [r11-20h], rax
0x1400401ec  lea     rax, [r11+28h]
0x1400401f0  mov     [r11-28h], r9
0x1400401f4  mov     [r11-30h], rax
0x1400401f8  mov     [r11-38h], r9
0x1400401fc  lea     r9, [r11+20h]
0x140040200  movzx   ecx, cx
0x140040203  call    FastWppTraceMessage
0x140040208  add     rsp, 58h
0x14004020c  retn
```
