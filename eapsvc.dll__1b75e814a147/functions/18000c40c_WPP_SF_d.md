# WPP_SF_d

- ea: `0x18000c40c`
- end: `0x18000c443`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, int)`
- caller_count: `19`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000d858`
- `0x18000f2c8`
- `0x18000f77c`
- `0x180010520`
- `0x18001064c`
- `0x180011698`
- `0x180011cb0`
- `0x1800122b8`
- `0x180012968`
- `0x180012b30`
- `0x180012cf8`
- `0x1800133a8`
- `0x180013578`
- `0x180013ba0`
- `0x1800142dc`
- `0x1800148c4`
- `0x1800153f9`
- `0x1800158ac`
- `0x180015ee1`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000c438`
- `ntdll!EtwTraceMessage` at `0x18000c438`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5);
}

```

## disassembly

```asm
0x18000c40c  mov     r11, rsp
0x18000c40f  mov     [r11+20h], r9d
0x18000c413  sub     rsp, 48h
0x18000c417  mov     qword ptr [r11-18h], 0
0x18000c41f  lea     rax, [r11+20h]
0x18000c423  movzx   r9d, dx
0x18000c427  mov     edx, 2Bh ; '+'
0x18000c42c  mov     qword ptr [r11-20h], 4
0x18000c434  mov     [r11-28h], rax
0x18000c438  call    cs:__imp_EtwTraceMessage
0x18000c43e  add     rsp, 48h
0x18000c442  retn
```
