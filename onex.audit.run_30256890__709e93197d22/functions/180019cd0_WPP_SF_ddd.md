# WPP_SF_ddd

- ea: `0x180019cd0`
- end: `0x180019d21`
- name: `WPP_SF_ddd`
- size: `81`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002a30`
- `0x1800065a0`
- `0x1800074a0`
- `0x18000a550`
- `0x180013560`
- `0x1800198a0`
- `0x18001e290`
- `0x180026194`
- `0x180026b04`
- `0x18002a76c`
- `0x18002b968`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180019d16`
- `ntdll!EtwTraceMessage` at `0x180019d16`

## pseudocode

```c
__int64 __fastcall WPP_SF_ddd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+88h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5);
}

```

## disassembly

```asm
0x180019cd0  mov     r11, rsp
0x180019cd3  mov     [r11+20h], r9d
0x180019cd7  sub     rsp, 68h
0x180019cdb  mov     qword ptr [r11-18h], 0
0x180019ce3  lea     rax, [r11+30h]
0x180019ce7  mov     r9d, 4
0x180019ced  mov     [r11-20h], r9
0x180019cf1  mov     [r11-28h], rax
0x180019cf5  lea     rax, [r11+28h]
0x180019cf9  mov     [r11-30h], r9
0x180019cfd  mov     [r11-38h], rax
0x180019d01  lea     rax, [r11+20h]
0x180019d05  mov     [r11-40h], r9
0x180019d09  movzx   r9d, dx
0x180019d0d  mov     edx, 2Bh ; '+'
0x180019d12  mov     [r11-48h], rax
0x180019d16  call    cs:__imp_EtwTraceMessage
0x180019d1c  add     rsp, 68h
0x180019d20  retn
```
