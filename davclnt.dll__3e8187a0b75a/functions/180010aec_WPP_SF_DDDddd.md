# WPP_SF_DDDddd

- ea: `0x180010aec`
- end: `0x180010b6f`
- name: `WPP_SF_DDDddd`
- size: `131`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001600`
- `0x180002970`
- `0x180006c50`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180010b61`
- `ntdll!EtwTraceMessage` at `0x180010b61`

## pseudocode

```c
__int64 __fastcall WPP_SF_DDDddd(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v5; // [rsp+B8h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, 240, &v5);
}

```

## disassembly

```asm
0x180010aec  mov     r11, rsp
0x180010aef  mov     [r11+20h], r9d
0x180010af3  sub     rsp, 98h
0x180010afa  mov     qword ptr [r11-18h], 0
0x180010b02  lea     rax, [r11+48h]
0x180010b06  mov     edx, 4
0x180010b0b  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180010b12  mov     [r11-20h], rdx
0x180010b16  mov     r9d, 0F0h
0x180010b1c  mov     [r11-28h], rax
0x180010b20  lea     rax, [r11+40h]
0x180010b24  mov     [r11-30h], rdx
0x180010b28  mov     [r11-38h], rax
0x180010b2c  lea     rax, [r11+38h]
0x180010b30  mov     [r11-40h], rdx
0x180010b34  mov     [r11-48h], rax
0x180010b38  lea     rax, [r11+30h]
0x180010b3c  mov     [r11-50h], rdx
0x180010b40  mov     [r11-58h], rax
0x180010b44  lea     rax, [r11+28h]
0x180010b48  mov     [r11-60h], rdx
0x180010b4c  mov     [r11-68h], rax
0x180010b50  lea     rax, [r11+20h]
0x180010b54  mov     [r11-70h], rdx
0x180010b58  mov     edx, 2Bh ; '+'
0x180010b5d  mov     [r11-78h], rax
0x180010b61  call    cs:__imp_EtwTraceMessage
0x180010b67  add     rsp, 98h
0x180010b6e  retn
```
