# WPP_SF_Dd

- ea: `0x180009a6c`
- end: `0x180009ab8`
- name: `WPP_SF_Dd`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180007fc0`
- `0x1800097e8`
- `0x180009878`
- `0x180009908`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180009aad`
- `ntdll!EtwTraceMessage` at `0x180009aad`

## pseudocode

```c
__int64 __fastcall WPP_SF_Dd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, WPP_445ce22454fb3e51184a727f087831f0_Traceguids, a2, &v5);
}

```

## disassembly

```asm
0x180009a6c  mov     r11, rsp
0x180009a6f  mov     [r11+20h], r9d
0x180009a73  sub     rsp, 58h
0x180009a77  mov     qword ptr [r11-18h], 0
0x180009a7f  lea     rax, [r11+28h]
0x180009a83  mov     r8d, 4
0x180009a89  movzx   r9d, dx
0x180009a8d  mov     [r11-20h], r8
0x180009a91  mov     edx, 2Bh ; '+'
0x180009a96  mov     [r11-28h], rax
0x180009a9a  lea     rax, [r11+20h]
0x180009a9e  mov     [r11-30h], r8
0x180009aa2  lea     r8, WPP_445ce22454fb3e51184a727f087831f0_Traceguids
0x180009aa9  mov     [r11-38h], rax
0x180009aad  call    cs:__imp_EtwTraceMessage
0x180009ab3  add     rsp, 58h
0x180009ab7  retn
```
