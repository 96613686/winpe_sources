# WPP_SF_dll

- ea: `0x1800344a4`
- end: `0x1800344fa`
- name: `WPP_SF_dll`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d6ac`

## callees

- `0x180017a20`

## pseudocode

```c
ULONG WPP_SF_dll(__int64 a1, __int64 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF
  __int64 v6; // [rsp+80h] [rbp+28h] BYREF
  va_list va; // [rsp+80h] [rbp+28h]
  va_list va1; // [rsp+88h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  v5 = a4;
  return FastWppTraceMessage(
           1028,
           0x49u,
           (ULONGLONG)WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids,
           &v5,
           4,
           va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x1800344a4  mov     r11, rsp
0x1800344a7  mov     [r11+20h], r9d
0x1800344ab  sub     rsp, 58h
0x1800344af  mov     qword ptr [r11-10h], 0
0x1800344b7  lea     rax, [r11+30h]
0x1800344bb  mov     edx, 49h ; 'I'
0x1800344c0  lea     r9, [r11+20h]
0x1800344c4  mov     r10d, 404h
0x1800344ca  lea     r8, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids
0x1800344d1  lea     ecx, [rdx-45h]
0x1800344d4  mov     [r11-18h], rcx
0x1800344d8  mov     [r11-20h], rax
0x1800344dc  lea     rax, [r11+28h]
0x1800344e0  mov     [r11-28h], rcx
0x1800344e4  mov     [r11-30h], rax
0x1800344e8  mov     [r11-38h], rcx
0x1800344ec  mov     ecx, r10d
0x1800344ef  call    FastWppTraceMessage
0x1800344f4  add     rsp, 58h
0x1800344f8  retn
```
