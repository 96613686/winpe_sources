# WPP_SF_d

- ea: `0x18000ade4`
- end: `0x18000ae22`
- name: `WPP_SF_d`
- size: `62`
- prototype: ``
- caller_count: `16`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006d20`
- `0x180007d40`
- `0x1800080c0`
- `0x180008850`
- `0x180009230`
- `0x1800096e0`
- `0x180009b90`
- `0x18000b8bc`
- `0x18000bac0`
- `0x18000bef4`
- `0x18000c204`
- `0x18000c280`
- `0x18000c500`
- `0x18000cae8`
- `0x18000d384`
- `0x18000e149`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000ae10`
- `ntdll!EtwTraceMessage` at `0x18000ae10`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x18000ade4  mov     r11, rsp
0x18000ade7  mov     [r11+20h], r9d
0x18000adeb  sub     rsp, 48h
0x18000adef  mov     qword ptr [r11-18h], 0
0x18000adf7  lea     rax, [r11+20h]
0x18000adfb  movzx   r9d, dx
0x18000adff  mov     edx, 2Bh ; '+'
0x18000ae04  mov     qword ptr [r11-20h], 4
0x18000ae0c  mov     [r11-28h], rax
0x18000ae10  call    cs:__imp_EtwTraceMessage
0x18000ae17  nop     dword ptr [rax+rax+00h]
0x18000ae1c  add     rsp, 48h
0x18000ae20  retn
```
