# ConvertNV11toIYUVorYV12(tagRECT const &,ParameterBase const *,int)

- ea: `0x180096c50`
- end: `0x180096e60`
- name: `?ConvertNV11toIYUVorYV12@@YAJAEBUtagRECT@@PEBUParameterBase@@H@Z`
- size: `528`
- prototype: `__int64 __fastcall(const struct tagRECT *, const struct ParameterBase *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180096c40`
- `0x180097080`

## callees

- `0x180096c50`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x180096d25`
- `MFPlat!MFCopyImage` at `0x180096d25`

## pseudocode

```c
__int64 __fastcall ConvertNV11toIYUVorYV12(const struct tagRECT *a1, const struct ParameterBase *a2, int a3)
{
  LONG v3; // edi
  LONG v4; // r12d
  int v5; // r14d
  __int64 v6; // rbx
  signed int v7; // r15d
  signed int v8; // r13d
  signed int v9; // esi
  __int64 v10; // rbp
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  int v14; // r15d
  int v15; // r8d
  int v16; // ebx
  int v17; // r9d
  int v18; // eax
  __int64 v19; // r10
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 v22; // rsi
  __int64 v23; // r13
  int v24; // eax
  __int64 v25; // r12
  __int64 v26; // r14
  int v27; // r11d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // edx
  __int64 v32; // [rsp+30h] [rbp-58h]
  signed int v33; // [rsp+90h] [rbp+8h]
  int v34; // [rsp+90h] [rbp+8h]
  __int64 v35; // [rsp+98h] [rbp+10h]
  __int64 v36; // [rsp+98h] [rbp+10h]
  int v37; // [rsp+A0h] [rbp+18h]
  __int64 v38; // [rsp+A8h] [rbp+20h]

  v3 = *((_DWORD *)a2 + 2);
  v4 = *((_DWORD *)a2 + 6);
  v5 = *((_DWORD *)a2 + 3);
  v6 = *(_QWORD *)a2;
  v7 = a1->left & 0xFFFFFFFC;
  v8 = a1->right & 0xFFFFFFFC;
  v9 = a1->top & 0xFFFFFFFE;
  v35 = *((_QWORD *)a2 + 2);
  v33 = a1->bottom & 0xFFFFFFFE;
  v10 = v3 / 2;
  v11 = *(_QWORD *)a2 + v3 * v5;
  v12 = v11;
  v13 = v11 + (int)v10 * (v5 / 2);
  if ( !a3 )
  {
    v12 = v11 + (int)v10 * (v5 / 2);
    v13 = v6 + v3 * v5;
  }
  v38 = v13;
  v32 = v12;
  if ( !MFCopyImage(
          (BYTE *)(v6 + v7 + (__int64)(v3 * v9)),
          v3,
          (const BYTE *)(v35 + v7 + (__int64)(v4 * v9)),
          v4,
          v8 - v7,
          v33 - v9) )
  {
    v14 = v7 / 4;
    v15 = v8 / 4;
    v37 = v8 / 4;
    v16 = v9 / 2;
    v17 = v33 / 2;
    v34 = v17;
    v18 = v4 / 2;
    v19 = v9 * (v4 / 2) + v35 + v4 * v5;
    v20 = (int)v10 * (v9 / 2);
    v21 = v20 + v38;
    v22 = v20 + v32;
    if ( v16 < v17 )
    {
      v23 = v18;
      v24 = 2 * v18;
      v25 = v24;
      v36 = v24;
      do
      {
        v26 = v19 + v23;
        v27 = v14;
        if ( v14 < v15 )
        {
          do
          {
            v28 = 2 * v27++;
            v29 = (*(unsigned __int8 *)(v28 + v19 + 1) + 1 + (unsigned int)*(unsigned __int8 *)(v28 + v26 + 1)) >> 1;
            v30 = (*(unsigned __int8 *)(v28 + v26) + (unsigned int)*(unsigned __int8 *)(v28 + v19) + 1) >> 1;
            *(_BYTE *)(v28 + v21) = v30;
            *(_BYTE *)(v28 + v21 + 1) = v30;
            *(_BYTE *)(v28 + v22) = v29;
            *(_BYTE *)(v28 + v22 + 1) = v29;
          }
          while ( v27 < v37 );
          v25 = v36;
          v15 = v37;
          v17 = v34;
        }
        v19 += v25;
        v21 += v10;
        v22 += v10;
        ++v16;
      }
      while ( v16 < v17 );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180096c50  push    rbx
0x180096c52  push    rbp
0x180096c53  push    rsi
0x180096c54  push    rdi
0x180096c55  push    r12
0x180096c57  push    r13
0x180096c59  push    r14
0x180096c5b  push    r15
0x180096c5d  sub     rsp, 48h
0x180096c61  mov     rax, [rdx+10h]
0x180096c65  mov     r9d, 2
0x180096c6b  mov     edi, [rdx+8]
0x180096c6e  mov     r12d, [rdx+18h]
0x180096c72  mov     r14d, [rdx+0Ch]
0x180096c76  mov     rbx, [rdx]
0x180096c79  mov     r15d, [rcx]
0x180096c7c  mov     r13d, [rcx+8]
0x180096c80  and     r15d, 0FFFFFFFCh
0x180096c84  mov     esi, [rcx+4]
0x180096c87  and     r13d, 0FFFFFFFCh
0x180096c8b  mov     r10d, [rcx+0Ch]
0x180096c8f  and     esi, 0FFFFFFFEh
0x180096c92  mov     [rsp+88h+arg_8], rax
0x180096c9a  and     r10d, 0FFFFFFFEh
0x180096c9e  mov     eax, edi
0x180096ca0  mov     [rsp+88h+arg_0], r10d
0x180096ca8  cdq
0x180096ca9  mov     r11d, r10d
0x180096cac  idiv    r9d
0x180096caf  mov     r10d, r13d
0x180096cb2  movsxd  rbp, eax
0x180096cb5  mov     eax, r14d
0x180096cb8  imul    eax, edi
0x180096cbb  movsxd  rcx, eax
0x180096cbe  mov     eax, r14d
0x180096cc1  cdq
0x180096cc2  add     rcx, rbx
0x180096cc5  idiv    r9d
0x180096cc8  mov     rdx, rcx
0x180096ccb  movsxd  r9, r15d
0x180096cce  imul    eax, ebp
0x180096cd1  cdqe
0x180096cd3  add     rax, rcx
0x180096cd6  test    r8d, r8d
0x180096cd9  cmovz   rdx, rax
0x180096cdd  cmovz   rax, rcx
0x180096ce1  mov     [rsp+88h+arg_18], rax
0x180096ce9  sub     r11d, esi
0x180096cec  mov     eax, esi
0x180096cee  mov     [rsp+88h+var_58], rdx
0x180096cf3  imul    eax, r12d
0x180096cf7  sub     r10d, r15d
0x180096cfa  mov     [rsp+88h+dwLines], r11d; dwLines
0x180096cff  mov     edx, edi; lDestStride
0x180096d01  mov     [rsp+88h+dwWidthInBytes], r10d; dwWidthInBytes
0x180096d06  movsxd  r8, eax
0x180096d09  mov     eax, esi
0x180096d0b  add     r8, r9
0x180096d0e  imul    eax, edi
0x180096d11  add     r8, [rsp+88h+arg_8]; pSrc
0x180096d19  movsxd  rcx, eax
0x180096d1c  add     rcx, r9
0x180096d1f  mov     r9d, r12d; lSrcStride
0x180096d22  add     rcx, rbx; pDest
0x180096d25  call    cs:__imp_MFCopyImage
0x180096d2b  test    eax, eax
0x180096d2d  jnz     loc_180096E4D
0x180096d33  mov     rdi, [rsp+88h+arg_18]
0x180096d3b  mov     ecx, 4
0x180096d40  mov     eax, r15d
0x180096d43  imul    r14d, r12d
0x180096d47  cdq
0x180096d48  idiv    ecx
0x180096d4a  movsxd  r10, r14d
0x180096d4d  mov     r15d, eax
0x180096d50  mov     eax, r13d
0x180096d53  cdq
0x180096d54  idiv    ecx
0x180096d56  mov     ecx, 2
0x180096d5b  mov     r8d, eax
0x180096d5e  mov     [rsp+88h+arg_10], eax
0x180096d65  mov     eax, esi
0x180096d67  cdq
0x180096d68  idiv    ecx
0x180096d6a  mov     ebx, eax
0x180096d6c  mov     eax, [rsp+88h+arg_0]
0x180096d73  cdq
0x180096d74  idiv    ecx
0x180096d76  mov     r9d, eax
0x180096d79  mov     [rsp+88h+arg_0], eax
0x180096d80  mov     eax, r12d
0x180096d83  cdq
0x180096d84  idiv    ecx
0x180096d86  mov     ecx, eax
0x180096d88  imul    ecx, esi
0x180096d8b  mov     rsi, [rsp+88h+var_58]
0x180096d90  movsxd  rdx, ecx
0x180096d93  mov     rcx, [rsp+88h+arg_8]
0x180096d9b  add     rcx, rdx
0x180096d9e  add     r10, rcx
0x180096da1  mov     ecx, ebx
0x180096da3  imul    ecx, ebp
0x180096da6  movsxd  rdx, ecx
0x180096da9  add     rdi, rdx
0x180096dac  add     rsi, rdx
0x180096daf  cmp     ebx, r9d
0x180096db2  jge     loc_180096E4D
0x180096db8  movsxd  r13, eax
0x180096dbb  add     eax, eax
0x180096dbd  movsxd  r12, eax
0x180096dc0  mov     [rsp+88h+arg_8], r12
0x180096dc8  lea     r14, [r10+r13]
0x180096dcc  mov     r11d, r15d
0x180096dcf  cmp     r15d, r8d
0x180096dd2  jge     short loc_180096E39
0x180096dd4  mov     r12d, [rsp+88h+arg_10]
0x180096ddc  lea     eax, [r11+r11]
0x180096de0  inc     r11d
0x180096de3  movsxd  r9, eax
0x180096de6  movzx   ecx, byte ptr [r9+r10+1]
0x180096dec  movzx   r8d, byte ptr [r9+r14+1]
0x180096df2  inc     ecx
0x180096df4  movzx   edx, byte ptr [r9+r10]
0x180096df9  add     r8d, ecx
0x180096dfc  movzx   ecx, byte ptr [r9+r14]
0x180096e01  inc     edx
0x180096e03  shr     r8d, 1
0x180096e06  add     edx, ecx
0x180096e08  shr     edx, 1
0x180096e0a  mov     [r9+rdi], dl
0x180096e0e  mov     [r9+rdi+1], dl
0x180096e13  mov     [r9+rsi], r8b
0x180096e17  mov     [r9+rsi+1], r8b
0x180096e1c  cmp     r11d, r12d
0x180096e1f  jl      short loc_180096DDC
0x180096e21  mov     r12, [rsp+88h+arg_8]
0x180096e29  mov     r8d, [rsp+88h+arg_10]
0x180096e31  mov     r9d, [rsp+88h+arg_0]
0x180096e39  add     r10, r12
0x180096e3c  add     rdi, rbp
0x180096e3f  add     rsi, rbp
0x180096e42  inc     ebx
0x180096e44  cmp     ebx, r9d
0x180096e47  jl      loc_180096DC8
0x180096e4d  xor     eax, eax
0x180096e4f  add     rsp, 48h
0x180096e53  pop     r15
0x180096e55  pop     r14
0x180096e57  pop     r13
0x180096e59  pop     r12
0x180096e5b  pop     rdi
0x180096e5c  pop     rsi
0x180096e5d  pop     rbp
0x180096e5e  pop     rbx
0x180096e5f  retn
```
