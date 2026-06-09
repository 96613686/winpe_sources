# ConvertToRGB

- ea: `0x180003e04`
- end: `0x180003ec0`
- name: `ConvertToRGB`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003548`

## callees

- `0x180002d80`
- `0x1800031d4`
- `0x1800033a4`
- `0x180003e04`

## pseudocode

```c
__int64 __fastcall ConvertToRGB(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  __int64 result; // rax

  result = a5;
  switch ( *(_WORD *)(a5 + 14) )
  {
    case 8:
      return ycClut8(
               *(unsigned __int16 *)(a1 + 6),
               *(unsigned __int16 *)(a1 + 4),
               (unsigned __int8 *)(a2 + *(unsigned int *)(a1 + 12)),
               (unsigned __int8 *)(a2 + *(unsigned int *)(a1 + 16)),
               (unsigned __int8 *)(a2 + *(unsigned int *)(a1 + 20)),
               a3,
               a4);
    case 0x10:
      return ycRgb16(
               *(unsigned __int16 *)(a1 + 6),
               *(unsigned __int16 *)(a1 + 4),
               (int)a2 + *(_DWORD *)(a1 + 12),
               (int)a2 + *(_DWORD *)(a1 + 20),
               a2 + *(unsigned int *)(a1 + 16),
               a3);
    case 0x18:
      return ycRgb24(
               *(unsigned __int16 *)(a1 + 6),
               *(unsigned __int16 *)(a1 + 4),
               (int)a2 + *(_DWORD *)(a1 + 12),
               (int)a2 + *(_DWORD *)(a1 + 20),
               a2 + *(unsigned int *)(a1 + 16),
               a3,
               a4);
  }
  return result;
}

```

## disassembly

```asm
0x180003e04  sub     rsp, 48h
0x180003e08  mov     rax, [rsp+48h+arg_20]
0x180003e0d  mov     r11d, r9d
0x180003e10  mov     r10, r8
0x180003e13  cmp     word ptr [rax+0Eh], 8
0x180003e18  jz      short loc_180003E8B
0x180003e1a  cmp     word ptr [rax+0Eh], 10h
0x180003e1f  jz      short loc_180003E5E
0x180003e21  cmp     word ptr [rax+0Eh], 18h
0x180003e26  jnz     loc_180003EBB
0x180003e2c  mov     eax, [rcx+10h]
0x180003e2f  mov     r9d, [rcx+14h]
0x180003e33  add     rax, rdx
0x180003e36  mov     r8d, [rcx+0Ch]
0x180003e3a  add     r9, rdx
0x180003e3d  mov     [rsp+48h+var_18], r11d
0x180003e42  add     r8, rdx
0x180003e45  movzx   edx, word ptr [rcx+4]
0x180003e49  movzx   ecx, word ptr [rcx+6]
0x180003e4d  mov     [rsp+48h+var_20], r10
0x180003e52  mov     [rsp+48h+var_28], rax
0x180003e57  call    ycRgb24
0x180003e5c  jmp     short loc_180003EBB
0x180003e5e  mov     eax, [rcx+10h]
0x180003e61  mov     r9d, [rcx+14h]
0x180003e65  add     rax, rdx
0x180003e68  mov     r8d, [rcx+0Ch]
0x180003e6c  add     r9, rdx
0x180003e6f  add     r8, rdx
0x180003e72  mov     [rsp+48h+var_20], r10
0x180003e77  movzx   edx, word ptr [rcx+4]
0x180003e7b  movzx   ecx, word ptr [rcx+6]
0x180003e7f  mov     [rsp+48h+var_28], rax
0x180003e84  call    ycRgb16
0x180003e89  jmp     short loc_180003EBB
0x180003e8b  mov     eax, [rcx+14h]
0x180003e8e  mov     r9d, [rcx+10h]
0x180003e92  add     rax, rdx
0x180003e95  mov     r8d, [rcx+0Ch]
0x180003e99  add     r9, rdx
0x180003e9c  mov     [rsp+48h+var_18], r11d
0x180003ea1  add     r8, rdx
0x180003ea4  movzx   edx, word ptr [rcx+4]
0x180003ea8  movzx   ecx, word ptr [rcx+6]
0x180003eac  mov     [rsp+48h+var_20], r10
0x180003eb1  mov     [rsp+48h+var_28], rax
0x180003eb6  call    ycClut8
0x180003ebb  add     rsp, 48h
0x180003ebf  retn
```
