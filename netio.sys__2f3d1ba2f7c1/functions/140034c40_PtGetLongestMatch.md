# PtGetLongestMatch

- ea: `0x140034c40`
- end: `0x140034d61`
- name: `PtGetLongestMatch`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140034c40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140034c7e`
- `ntoskrnl!RtlCompareMemory` at `0x140034cd5`
- `ntoskrnl!RtlCompareMemory` at `0x140034c7e`
- `ntoskrnl!RtlCompareMemory` at `0x140034cd5`

## pseudocode

```c
__int64 __fastcall PtGetLongestMatch(__int64 **a1, unsigned __int8 *a2, _QWORD *a3)
{
  __int64 *v3; // rsi
  __int64 *v4; // r14
  SIZE_T v8; // rbx
  SIZE_T v9; // rax
  int v10; // eax
  unsigned __int16 v11; // si
  SIZE_T v12; // rbx
  SIZE_T v13; // rax
  int v14; // r8d
  int v15; // eax
  __int64 v16; // rax
  __int64 result; // rax
  int v18; // esi

  v3 = *a1;
  v4 = 0;
  if ( !*a1 )
    goto LABEL_11;
  do
  {
    if ( a2 )
    {
      v8 = *((unsigned int *)a1 + 2);
      v9 = RtlCompareMemory(a2, (char *)v3 + 44, v8);
      if ( v9 == v8 )
      {
        v10 = 0;
      }
      else
      {
        v10 = a2[v9] - *((unsigned __int8 *)v3 + v9 + 44);
        if ( v10 < 0 )
          goto LABEL_5;
      }
      v4 = v3;
    }
    else
    {
      v10 = -1;
    }
LABEL_5:
    v3 = *(__int64 **)((char *)v3 + (((__int64)v10 >> 63) & 0xFFFFFFFFFFFFFFF0uLL) + 32);
  }
  while ( v3 );
  if ( !v4 )
  {
LABEL_11:
    v16 = 0;
    goto LABEL_12;
  }
  while ( 1 )
  {
    v11 = *((_WORD *)v4 + 21);
    v12 = (unsigned __int64)v11 >> 3;
    v13 = RtlCompareMemory((char *)v4 + 44, a2, v12);
    if ( v13 < v12 )
    {
      v14 = *((unsigned __int8 *)v4 + v13 + 44);
      v15 = a2[v13];
      goto LABEL_9;
    }
    v18 = v11 & 7;
    if ( !v18 )
      break;
    v14 = *((unsigned __int8 *)v4 + v12 + 44) >> (8 - v18);
    v15 = a2[v12] >> (8 - v18);
LABEL_9:
    if ( v14 == v15 )
      break;
    v4 = (__int64 *)*v4;
    if ( !v4 )
      goto LABEL_11;
  }
  v16 = v4[3];
LABEL_12:
  *a3 = v16;
  result = 0;
  if ( !v4 )
    return 3221226098LL;
  return result;
}

```

## disassembly

```asm
0x140034c40  push    rbx
0x140034c42  push    rbp
0x140034c43  push    rsi
0x140034c44  push    rdi
0x140034c45  push    r12
0x140034c47  push    r14
0x140034c49  push    r15
0x140034c4b  sub     rsp, 20h
0x140034c4f  mov     rsi, [rcx]
0x140034c52  xor     r14d, r14d
0x140034c55  mov     r12, r8
0x140034c58  mov     rdi, rdx
0x140034c5b  mov     r15, rcx
0x140034c5e  test    rsi, rsi
0x140034c61  jz      loc_140034D00
0x140034c67  test    rdi, rdi
0x140034c6a  jz      loc_140034D57
0x140034c70  mov     ebx, [r15+8]
0x140034c74  lea     rdx, [rsi+2Ch]; Source2
0x140034c78  mov     r8d, ebx; Length
0x140034c7b  mov     rcx, rdi; Source1
0x140034c7e  call    cs:__imp_RtlCompareMemory
0x140034c85  nop     dword ptr [rax+rax+00h]
0x140034c8a  cmp     rax, rbx
0x140034c8d  jz      loc_140034D23
0x140034c93  movzx   ecx, byte ptr [rax+rsi+2Ch]
0x140034c98  movzx   eax, byte ptr [rax+rdi]
0x140034c9c  sub     eax, ecx
0x140034c9e  jns     loc_140034D25
0x140034ca4  cdqe
0x140034ca6  sar     rax, 3Fh
0x140034caa  and     rax, 0FFFFFFFFFFFFFFF0h
0x140034cae  mov     rax, [rax+rsi+20h]
0x140034cb3  mov     rsi, rax
0x140034cb6  test    rax, rax
0x140034cb9  jnz     short loc_140034C67
0x140034cbb  test    r14, r14
0x140034cbe  jz      short loc_140034D00
0x140034cc0  movzx   esi, word ptr [r14+2Ah]
0x140034cc5  lea     rcx, [r14+2Ch]; Source1
0x140034cc9  mov     ebx, esi
0x140034ccb  mov     rdx, rdi; Source2
0x140034cce  shr     rbx, 3
0x140034cd2  mov     r8, rbx; Length
0x140034cd5  call    cs:__imp_RtlCompareMemory
0x140034cdc  nop     dword ptr [rax+rax+00h]
0x140034ce1  cmp     rax, rbx
0x140034ce4  jnb     short loc_140034D2D
0x140034ce6  movzx   r8d, byte ptr [rax+r14+2Ch]
0x140034cec  movzx   eax, byte ptr [rax+rdi]
0x140034cf0  sub     r8d, eax
0x140034cf3  test    r8d, r8d
0x140034cf6  jz      short loc_140034D51
0x140034cf8  mov     r14, [r14]
0x140034cfb  test    r14, r14
0x140034cfe  jnz     short loc_140034CC0
0x140034d00  xor     eax, eax
0x140034d02  mov     [r12], rax
0x140034d06  mov     ecx, 0C0000272h
0x140034d0b  xor     eax, eax
0x140034d0d  test    r14, r14
0x140034d10  cmovz   eax, ecx
0x140034d13  add     rsp, 20h
0x140034d17  pop     r15
0x140034d19  pop     r14
0x140034d1b  pop     r12
0x140034d1d  pop     rdi
0x140034d1e  pop     rsi
0x140034d1f  pop     rbp
0x140034d20  pop     rbx
0x140034d21  retn
0x140034d23  xor     eax, eax
0x140034d25  mov     r14, rsi
0x140034d28  jmp     loc_140034CA4
0x140034d2d  and     esi, 7
0x140034d30  jz      short loc_140034D51
0x140034d32  movzx   r8d, byte ptr [rbx+r14+2Ch]
0x140034d38  mov     eax, 8
0x140034d3d  sub     al, sil
0x140034d40  movzx   edx, al
0x140034d43  movzx   eax, byte ptr [rbx+rdi]
0x140034d47  movzx   ecx, dl
0x140034d4a  shr     r8d, cl
0x140034d4d  shr     eax, cl
0x140034d4f  jmp     short loc_140034CF0
0x140034d51  mov     rax, [r14+18h]
0x140034d55  jmp     short loc_140034D02
0x140034d57  mov     eax, 0FFFFFFFFh
0x140034d5c  jmp     loc_140034CA4
```
