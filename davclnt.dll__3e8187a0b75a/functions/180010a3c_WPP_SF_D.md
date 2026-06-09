# WPP_SF_D

- ea: `0x180010a3c`
- end: `0x180010a7a`
- name: `WPP_SF_D`
- size: `62`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, int)`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001600`
- `0x180002970`
- `0x180003b90`
- `0x180007ad0`
- `0x18000ceb0`
- `0x18000e494`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180010a6f`
- `ntdll!EtwTraceMessage` at `0x180010a6f`

## pseudocode

```c
__int64 __fastcall WPP_SF_D(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, a2, &v5);
}

```

## disassembly

```asm
0x180010a3c  mov     r11, rsp
0x180010a3f  mov     [r11+20h], r9d
0x180010a43  sub     rsp, 48h
0x180010a47  mov     qword ptr [r11-18h], 0
0x180010a4f  lea     rax, [r11+20h]
0x180010a53  movzx   r9d, dx
0x180010a57  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180010a5e  mov     qword ptr [r11-20h], 4
0x180010a66  mov     edx, 2Bh ; '+'
0x180010a6b  mov     [r11-28h], rax
0x180010a6f  call    cs:__imp_EtwTraceMessage
0x180010a75  add     rsp, 48h
0x180010a79  retn
```
