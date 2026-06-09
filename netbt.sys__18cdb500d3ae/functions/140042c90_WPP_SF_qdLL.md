# WPP_SF_qdLL

- ea: `0x140042c90`
- end: `0x140042cf6`
- name: `WPP_SF_qdLL`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14001aa0c`

## callees

- `0x140030bc8`

## pseudocode

```c
void WPP_SF_qdLL(__int64 a1, __int64 a2, __int64 a3, ...)
{
  __int64 v3; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  __int64 v5; // [rsp+90h] [rbp+28h] BYREF
  va_list va1; // [rsp+90h] [rbp+28h]
  __int64 v7; // [rsp+98h] [rbp+30h] BYREF
  va_list va2; // [rsp+98h] [rbp+30h]
  va_list va3; // [rsp+A0h] [rbp+38h] BYREF

  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v3 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v5 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v7 = va_arg(va3, _QWORD);
  FastWppTraceMessage(
    1048,
    0x1Au,
    (ULONGLONG)WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids,
    va,
    8,
    va1,
    4,
    va2,
    4,
    va3,
    4,
    0);
}

```

## disassembly

```asm
0x140042c90  mov     r11, rsp
0x140042c93  mov     [r11+20h], r9
0x140042c97  sub     rsp, 68h
0x140042c9b  mov     qword ptr [r11-10h], 0
0x140042ca3  lea     rax, [r11+38h]
0x140042ca7  mov     edx, 1Ah
0x140042cac  lea     r9, [r11+20h]
0x140042cb0  mov     r10d, 418h
0x140042cb6  lea     r8, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids
0x140042cbd  lea     ecx, [rdx-16h]
0x140042cc0  mov     [r11-18h], rcx
0x140042cc4  mov     [r11-20h], rax
0x140042cc8  lea     rax, [r11+30h]
0x140042ccc  mov     [r11-28h], rcx
0x140042cd0  mov     [r11-30h], rax
0x140042cd4  lea     rax, [r11+28h]
0x140042cd8  mov     [r11-38h], rcx
0x140042cdc  mov     ecx, r10d
0x140042cdf  mov     [r11-40h], rax
0x140042ce3  mov     qword ptr [r11-48h], 8
0x140042ceb  call    FastWppTraceMessage
0x140042cf0  add     rsp, 68h
0x140042cf4  retn
```
