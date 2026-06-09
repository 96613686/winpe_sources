# DecompressGetFormat

- ea: `0x180006d14`
- end: `0x180006dd0`
- name: `DecompressGetFormat`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005e00`

## callees

- `0x180006d14`
- `0x180007020`
- `0x180007c95`

## pseudocode

```c
__int64 __fastcall DecompressGetFormat(__int64 a1, _DWORD *a2, __int64 a3)
{
  __int64 result; // rax
  unsigned __int64 v6; // rcx
  unsigned int v7; // edx
  signed int v8; // ecx
  unsigned int v9; // r8d
  int v10; // edx
  int v11; // eax
  unsigned int v12; // ecx

  result = DecompressQueryFmt(a1, (__int64)a2);
  if ( !(_DWORD)result )
  {
    v6 = 4LL * (unsigned int)a2[8];
    if ( v6 > 0xFFFFFFFF )
      return 4294967294LL;
    v7 = v6 + *a2;
    if ( v7 < (unsigned int)v6 || v7 > 0x7FFFFFFF )
      return 4294967294LL;
    if ( !a3 )
      return v7;
    if ( v7 > 0x428 )
    {
      return 4294967294LL;
    }
    else
    {
      memmove_0((void *)a3, a2, v7);
      v8 = a2[2] & 0xFFFFFFFC;
      v9 = a2[1] & 0xFFFFFFFC;
      *(_DWORD *)(a3 + 8) = v8;
      *(_DWORD *)(a3 + 4) = v9;
      v10 = *((unsigned __int16 *)a2 + 7);
      v11 = -v8;
      *(_WORD *)(a3 + 14) = v10;
      if ( v8 > 0 )
        LOWORD(v11) = v8;
      *(_WORD *)(a3 + 12) = 1;
      *(_DWORD *)(a3 + 16) = 0;
      v12 = (((v9 * v10 + 31) >> 3) & 0xFFFC) * (unsigned __int16)v11;
      result = 0;
      *(_DWORD *)(a3 + 20) = v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006d14  mov     [rsp+arg_0], rbx
0x180006d19  push    rdi
0x180006d1a  sub     rsp, 20h
0x180006d1e  mov     rdi, r8
0x180006d21  mov     rbx, rdx
0x180006d24  call    DecompressQueryFmt
0x180006d29  test    eax, eax
0x180006d2b  jnz     loc_180006DC5
0x180006d31  mov     ecx, [rbx+20h]
0x180006d34  mov     eax, 0FFFFFFFFh
0x180006d39  shl     rcx, 2
0x180006d3d  cmp     rcx, rax
0x180006d40  ja      short loc_180006DC0
0x180006d42  mov     edx, [rbx]
0x180006d44  add     edx, ecx
0x180006d46  cmp     edx, ecx
0x180006d48  jb      short loc_180006DC0
0x180006d4a  cmp     edx, 7FFFFFFFh
0x180006d50  ja      short loc_180006DC0
0x180006d52  test    rdi, rdi
0x180006d55  jnz     short loc_180006D5B
0x180006d57  mov     eax, edx
0x180006d59  jmp     short loc_180006DC5
0x180006d5b  cmp     edx, 428h
0x180006d61  ja      short loc_180006DC0
0x180006d63  mov     r8d, edx; Size
0x180006d66  mov     rcx, rdi; void *
0x180006d69  mov     rdx, rbx; Src
0x180006d6c  call    memmove_0
0x180006d71  mov     ecx, [rbx+8]
0x180006d74  mov     r8d, [rbx+4]
0x180006d78  and     ecx, 0FFFFFFFCh
0x180006d7b  and     r8d, 0FFFFFFFCh
0x180006d7f  mov     [rdi+8], ecx
0x180006d82  mov     eax, ecx
0x180006d84  mov     [rdi+4], r8d
0x180006d88  movzx   edx, word ptr [rbx+0Eh]
0x180006d8c  neg     eax
0x180006d8e  mov     [rdi+0Eh], dx
0x180006d92  cmovs   eax, ecx
0x180006d95  mov     word ptr [rdi+0Ch], 1
0x180006d9b  movzx   ecx, ax
0x180006d9e  mov     eax, edx
0x180006da0  imul    eax, r8d
0x180006da4  mov     dword ptr [rdi+10h], 0
0x180006dab  add     eax, 1Fh
0x180006dae  shr     eax, 3
0x180006db1  and     eax, 0FFFCh
0x180006db6  imul    ecx, eax
0x180006db9  xor     eax, eax
0x180006dbb  mov     [rdi+14h], ecx
0x180006dbe  jmp     short loc_180006DC5
0x180006dc0  mov     eax, 0FFFFFFFEh
0x180006dc5  mov     rbx, [rsp+28h+arg_0]
0x180006dca  add     rsp, 20h
0x180006dce  pop     rdi
0x180006dcf  retn
```
