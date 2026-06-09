# WPP_SF_Dlld

- ea: `0x14001ba28`
- end: `0x14001ba99`
- name: `WPP_SF_Dlld`
- size: `113`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140006fd0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x14001ba8b`
- `ntdll!EtwTraceMessage` at `0x14001ba8b`

## pseudocode

```c
__int64 __fastcall WPP_SF_Dlld(__int64 a1)
{
  return EtwTraceMessage(a1, 43, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
}

```

## disassembly

```asm
0x14001ba28  mov     r11, rsp
0x14001ba2b  mov     [r11+20h], r9d
0x14001ba2f  sub     rsp, 88h
0x14001ba36  mov     qword ptr [r11-28h], 0
0x14001ba3e  lea     rax, [r11-18h]
0x14001ba42  mov     r9d, 1Ch
0x14001ba48  mov     [rsp+88h+var_18], 0
0x14001ba50  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14001ba57  lea     edx, [r9-18h]
0x14001ba5b  mov     [r11-30h], rdx
0x14001ba5f  mov     [r11-38h], rax
0x14001ba63  lea     rax, [r11+30h]
0x14001ba67  mov     [r11-40h], rdx
0x14001ba6b  mov     [r11-48h], rax
0x14001ba6f  lea     rax, [r11+28h]
0x14001ba73  mov     [r11-50h], rdx
0x14001ba77  mov     [r11-58h], rax
0x14001ba7b  lea     rax, [r11+20h]
0x14001ba7f  mov     [r11-60h], rdx
0x14001ba83  lea     edx, [r9+0Fh]
0x14001ba87  mov     [r11-68h], rax
0x14001ba8b  call    cs:__imp_EtwTraceMessage
0x14001ba91  add     rsp, 88h
0x14001ba98  retn
```
