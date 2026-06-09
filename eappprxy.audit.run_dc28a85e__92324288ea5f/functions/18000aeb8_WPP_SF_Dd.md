# WPP_SF_Dd

- ea: `0x18000aeb8`
- end: `0x18000af0b`
- name: `WPP_SF_Dd`
- size: `83`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006100`
- `0x180006d20`
- `0x1800075c0`
- `0x180008cf0`
- `0x180009e10`
- `0x18000a1b0`
- `0x18000a550`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000aef9`
- `ntdll!EtwTraceMessage` at `0x18000aef9`

## pseudocode

```c
__int64 __fastcall WPP_SF_Dd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, WPP_e9255469090b376a053f3594056fdc10_Traceguids, a2, &v5);
}

```

## disassembly

```asm
0x18000aeb8  mov     r11, rsp
0x18000aebb  mov     [r11+20h], r9d
0x18000aebf  sub     rsp, 58h
0x18000aec3  mov     qword ptr [r11-18h], 0
0x18000aecb  lea     rax, [r11+28h]
0x18000aecf  mov     r8d, 4
0x18000aed5  movzx   r9d, dx
0x18000aed9  mov     [r11-20h], r8
0x18000aedd  mov     edx, 2Bh ; '+'
0x18000aee2  mov     [r11-28h], rax
0x18000aee6  lea     rax, [r11+20h]
0x18000aeea  mov     [r11-30h], r8
0x18000aeee  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x18000aef5  mov     [r11-38h], rax
0x18000aef9  call    cs:__imp_EtwTraceMessage
0x18000af00  nop     dword ptr [rax+rax+00h]
0x18000af05  add     rsp, 58h
0x18000af09  retn
```
