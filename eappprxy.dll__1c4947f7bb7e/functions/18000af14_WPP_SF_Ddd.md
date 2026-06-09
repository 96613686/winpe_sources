# WPP_SF_Ddd

- ea: `0x18000af14`
- end: `0x18000af73`
- name: `WPP_SF_Ddd`
- size: `95`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800075c0`
- `0x180008850`
- `0x180009230`
- `0x1800096e0`
- `0x180009e10`
- `0x18000a1b0`
- `0x18000a550`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000af61`
- `ntdll!EtwTraceMessage` at `0x18000af61`

## pseudocode

```c
__int64 __fastcall WPP_SF_Ddd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+88h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, WPP_e9255469090b376a053f3594056fdc10_Traceguids, a2, &v5);
}

```

## disassembly

```asm
0x18000af14  mov     r11, rsp
0x18000af17  mov     [r11+20h], r9d
0x18000af1b  sub     rsp, 68h
0x18000af1f  mov     qword ptr [r11-18h], 0
0x18000af27  lea     rax, [r11+30h]
0x18000af2b  mov     r8d, 4
0x18000af31  movzx   r9d, dx
0x18000af35  mov     [r11-20h], r8
0x18000af39  mov     edx, 2Bh ; '+'
0x18000af3e  mov     [r11-28h], rax
0x18000af42  lea     rax, [r11+28h]
0x18000af46  mov     [r11-30h], r8
0x18000af4a  mov     [r11-38h], rax
0x18000af4e  lea     rax, [r11+20h]
0x18000af52  mov     [r11-40h], r8
0x18000af56  lea     r8, WPP_e9255469090b376a053f3594056fdc10_Traceguids
0x18000af5d  mov     [r11-48h], rax
0x18000af61  call    cs:__imp_EtwTraceMessage
0x18000af68  nop     dword ptr [rax+rax+00h]
0x18000af6d  add     rsp, 68h
0x18000af71  retn
```
