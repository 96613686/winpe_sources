# WPP_SF_qDD

- ea: `0x180008a90`
- end: `0x180008aec`
- name: `WPP_SF_qDD`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001020`
- `0x180002080`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180008ae1`
- `ntdll!EtwTraceMessage` at `0x180008ae1`

## pseudocode

```c
__int64 WPP_SF_qDD(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  va_list va1; // [rsp+90h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  return EtwTraceMessage(a1, 43, WPP_bca2592d8fb93cecad2a84d86cc1e48c_Traceguids, a2, (__int64 *)va, 8, va1);
}

```

## disassembly

```asm
0x180008a90  mov     r11, rsp
0x180008a93  mov     [r11+20h], r9
0x180008a97  sub     rsp, 68h
0x180008a9b  mov     qword ptr [r11-18h], 0
0x180008aa3  lea     rax, [r11+30h]
0x180008aa7  mov     r8d, 4
0x180008aad  movzx   r9d, dx
0x180008ab1  mov     [r11-20h], r8
0x180008ab5  mov     edx, 2Bh ; '+'
0x180008aba  mov     [r11-28h], rax
0x180008abe  lea     rax, [r11+28h]
0x180008ac2  mov     [r11-30h], r8
0x180008ac6  lea     r8, WPP_bca2592d8fb93cecad2a84d86cc1e48c_Traceguids
0x180008acd  mov     [r11-38h], rax
0x180008ad1  lea     rax, [r11+20h]
0x180008ad5  mov     qword ptr [r11-40h], 8
0x180008add  mov     [r11-48h], rax
0x180008ae1  call    cs:__imp_EtwTraceMessage
0x180008ae7  add     rsp, 68h
0x180008aeb  retn
```
