# DecompressBegin

- ea: `0x180006c1c`
- end: `0x180006d0e`
- name: `DecompressBegin`
- size: `242`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005e00`
- `0x180006b68`

## callees

- `0x180006c1c`
- `0x180006e8c`
- `0x18000707c`

## pseudocode

```c
__int64 __fastcall DecompressBegin(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        int a13,
        int a14)
{
  __int64 result; // rax
  int v17; // ecx
  unsigned __int16 v18; // ax
  int v19; // [rsp+48h] [rbp-30h]
  int v20; // [rsp+50h] [rbp-28h]
  int v21; // [rsp+58h] [rbp-20h]

  result = DecompressQuery(a1, a2, a3, a4, a5, a6, a7, a8, a9, v19, v20, v21, a13, a14);
  if ( !(_DWORD)result )
  {
    *(_QWORD *)(a1 + 8) = *(_QWORD *)(a1 + 16);
    if ( !*(_DWORD *)(a9 + 20) )
    {
      v17 = *(_DWORD *)(a9 + 8);
      v18 = -(__int16)v17;
      if ( v17 >= 0 )
        v18 = *(_DWORD *)(a9 + 8);
      *(_DWORD *)(a9 + 20) = v18
                           * (((*(_DWORD *)(a9 + 4) * (unsigned int)*(unsigned __int16 *)(a9 + 14) + 31) >> 3) & 0xFFFC);
    }
    if ( *(_WORD *)(a3 + 14) != 16
      || *(_WORD *)(a9 + 14) != 8
      || lpDitherTable
      || (lpDitherTable = (LPCVOID)Dither16InitScale()) != 0 )
    {
      *(_DWORD *)(a1 + 32) = 1;
      return 0;
    }
    else
    {
      return 4294967293LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006c1c  mov     [rsp+arg_0], rbx
0x180006c21  mov     [rsp+arg_8], rsi
0x180006c26  push    rdi
0x180006c27  sub     rsp, 70h
0x180006c2b  mov     eax, [rsp+78h+arg_68]
0x180006c32  mov     rsi, r8
0x180006c35  mov     rdi, [rsp+78h+arg_40]
0x180006c3d  mov     rbx, rcx
0x180006c40  mov     [rsp+78h+var_10], eax
0x180006c44  mov     eax, [rsp+78h+arg_60]
0x180006c4b  mov     [rsp+78h+var_18], eax
0x180006c4f  mov     eax, [rsp+78h+arg_38]
0x180006c56  mov     [rsp+78h+var_38], rdi
0x180006c5b  mov     [rsp+78h+var_40], eax
0x180006c5f  mov     eax, [rsp+78h+arg_30]
0x180006c66  mov     [rsp+78h+var_48], eax
0x180006c6a  mov     eax, [rsp+78h+arg_28]
0x180006c71  mov     [rsp+78h+var_50], eax
0x180006c75  mov     eax, [rsp+78h+arg_20]
0x180006c7c  mov     [rsp+78h+var_58], eax
0x180006c80  call    DecompressQuery
0x180006c85  test    eax, eax
0x180006c87  jnz     short loc_180006CFC
0x180006c89  mov     rax, [rbx+10h]
0x180006c8d  mov     [rbx+8], rax
0x180006c91  cmp     dword ptr [rdi+14h], 0
0x180006c95  jnz     short loc_180006CC3
0x180006c97  mov     ecx, [rdi+8]
0x180006c9a  movzx   eax, cx
0x180006c9d  movzx   edx, word ptr [rdi+0Eh]
0x180006ca1  neg     ax
0x180006ca4  imul    edx, [rdi+4]
0x180006ca8  add     edx, 1Fh
0x180006cab  shr     edx, 3
0x180006cae  and     edx, 0FFFCh
0x180006cb4  test    ecx, ecx
0x180006cb6  cmovns  ax, cx
0x180006cba  movzx   eax, ax
0x180006cbd  imul    edx, eax
0x180006cc0  mov     [rdi+14h], edx
0x180006cc3  cmp     word ptr [rsi+0Eh], 10h
0x180006cc8  jnz     short loc_180006CF3
0x180006cca  cmp     word ptr [rdi+0Eh], 8
0x180006ccf  jnz     short loc_180006CF3
0x180006cd1  cmp     cs:lpDitherTable, 0
0x180006cd9  jnz     short loc_180006CF3
0x180006cdb  call    Dither16InitScale
0x180006ce0  mov     cs:lpDitherTable, rax
0x180006ce7  test    rax, rax
0x180006cea  jnz     short loc_180006CF3
0x180006cec  mov     eax, 0FFFFFFFDh
0x180006cf1  jmp     short loc_180006CFC
0x180006cf3  mov     dword ptr [rbx+20h], 1
0x180006cfa  xor     eax, eax
0x180006cfc  lea     r11, [rsp+78h+var_8]
0x180006d01  mov     rbx, [r11+10h]
0x180006d05  mov     rsi, [r11+18h]
0x180006d09  mov     rsp, r11
0x180006d0c  pop     rdi
0x180006d0d  retn
```
