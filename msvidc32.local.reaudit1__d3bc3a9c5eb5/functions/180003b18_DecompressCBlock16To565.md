# DecompressCBlock16To565

- ea: `0x180003b18`
- end: `0x180003f2a`
- name: `DecompressCBlock16To565`
- size: `1042`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800055f0`

## callees

- `0x180003b18`

## pseudocode

```c
__int16 *__fastcall DecompressCBlock16To565(int *a1, __int16 *a2, unsigned int *a3, int a4, int *a5)
{
  __int16 *v5; // r10
  __int64 v6; // r14
  unsigned int v9; // r9d
  int v10; // r8d
  unsigned int v11; // r9d
  int v12; // r9d
  int v13; // ecx
  unsigned __int16 v14; // si
  __int16 v15; // ax
  unsigned int v16; // edx
  __int16 *v17; // rdi
  _WORD *v18; // r10
  __int16 v19; // di
  int v20; // esi
  int v21; // r9d
  unsigned __int16 v22; // bp
  __int16 v23; // cx
  _WORD *v24; // rdi
  unsigned int v25; // edx
  __int16 v26; // dx
  unsigned int v27; // eax
  int v28; // r13d
  int v29; // r15d
  char v30; // dl
  char v31; // al
  int v32; // ecx
  int v33; // eax
  unsigned int v34; // edx
  unsigned __int16 v35; // di
  __int16 v36; // cx
  _WORD *v37; // r9
  __int16 v38; // ax
  __int16 v39; // r9
  int v40; // esi
  int v41; // edi
  unsigned __int16 v42; // r15
  __int16 v43; // cx
  unsigned int v44; // edx
  __int16 v45; // ax
  __int16 v46; // dx
  unsigned int v47; // eax
  int v48; // r12d
  int v49; // ecx
  int v50; // ebx
  char v51; // dl
  char v52; // al
  int v53; // ecx
  int v54; // eax
  __int16 *v55; // rdx
  unsigned int v56; // r9d
  __int16 v57; // dx
  int v58; // r9d
  int v59; // edi
  int v60; // ebx
  char v61; // dl
  char v62; // al
  _WORD *v64; // [rsp+68h] [rbp+10h]

  v5 = a2;
  v6 = a4;
  if ( *a5 > 0 )
  {
    --*a5;
    return v5;
  }
  v9 = *a3;
  if ( *a3 <= 1 )
  {
    LOWORD(v10) = 0;
LABEL_12:
    v14 = 0;
    goto LABEL_42;
  }
  v10 = (unsigned __int16)*a2;
  v11 = v9 - 2;
  v5 = a2 + 1;
  *a3 = v11;
  if ( (v10 & 0x8000u) != 0 )
  {
    if ( (v10 & 0xFFFFFC00) == 0x8400 )
    {
      *a5 = (v10 & 0x3FF) - 1;
    }
    else
    {
      v12 = 4;
      v13 = v10 & 0x1F
          | (unsigned __int16)(2 * (v10 & 0xFFE0))
          | ((v10 & 0x1F | (unsigned __int16)(2 * (v10 & 0xFFE0))) << 16);
      do
      {
        *a1 = v13;
        a1[1] = v13;
        a1 = (int *)((char *)a1 + v6);
        --v12;
      }
      while ( v12 );
    }
    return v5;
  }
  if ( v11 <= 1 )
    goto LABEL_12;
  v15 = *v5;
  if ( *v5 >= 0 )
  {
    v55 = a2 + 2;
    v56 = v11 - 2;
    *a3 = v56;
    v14 = v15 & 0x1F | (2 * (v15 & 0xFFE0));
    if ( v56 > 1 )
    {
      v5 += 2;
      *a3 = v56 - 2;
      v57 = *v55;
LABEL_44:
      v58 = 4;
      v59 = v57 & 0x1F
          | (unsigned __int16)(2 * (v57 & 0xFFE0))
          | ((v57 & 0x1F | (unsigned __int16)(2 * (v57 & 0xFFE0))) << 16);
      v60 = v59 ^ (v14 | (v14 << 16));
      do
      {
        v61 = v10;
        v62 = v10;
        LOWORD(v10) = (unsigned __int16)v10 >> 4;
        *a1 = v59 ^ v60 & *((_DWORD *)Bits2Bytes + (v62 & 3));
        a1[1] = v59 ^ v60 & *((_DWORD *)Bits2Bytes + (v61 & 0xC));
        a1 = (int *)((char *)a1 + v6);
        --v58;
      }
      while ( v58 );
      return v5;
    }
    ++v5;
LABEL_42:
    v57 = 0;
    goto LABEL_44;
  }
  v16 = v11 - 2;
  *a3 = v11 - 2;
  v17 = v5 + 1;
  v64 = v5 + 1;
  v18 = v5 + 1;
  if ( v11 - 2 > 1 )
  {
    v19 = *v17;
    ++v18;
    v16 = v11 - 4;
    v64 = v18;
    *a3 = v11 - 4;
  }
  else
  {
    v19 = 0;
  }
  v20 = v19 & 0x1F
      | (unsigned __int16)(2 * (v19 & 0xFFE0))
      | ((v19 & 0x1F | (unsigned __int16)(2 * (v19 & 0xFFE0))) << 16);
  v21 = v20
      ^ (v15 & 0x1F
       | (unsigned __int16)(2 * (v15 & 0xFFE0))
       | ((v15 & 0x1F | (unsigned __int16)(2 * (v15 & 0xFFE0))) << 16));
  if ( v16 > 1 )
  {
    v23 = *v18;
    v24 = v18 + 1;
    v25 = v16 - 2;
    *a3 = v25;
    v22 = (2 * (v23 & 0xFFE0)) | v23 & 0x1F;
    if ( v25 > 1 )
    {
      v27 = v25 - 2;
      v26 = *v24;
      v18 += 2;
      *a3 = v27;
      v64 = v24 + 1;
      goto LABEL_23;
    }
    ++v18;
    v64 = v24;
  }
  else
  {
    v22 = 0;
  }
  v26 = 0;
LABEL_23:
  v28 = 2;
  v29 = v26 & 0x1F
      | (unsigned __int16)(2 * (v26 & 0xFFE0))
      | ((v26 & 0x1F | (unsigned __int16)(2 * (v26 & 0xFFE0))) << 16);
  do
  {
    v30 = v10;
    v31 = v10;
    LOWORD(v10) = (unsigned __int16)v10 >> 4;
    v32 = v20 ^ v21 & *((_DWORD *)Bits2Bytes + (v31 & 3));
    v33 = v29 ^ (v29 ^ (v22 | (v22 << 16))) & *((_DWORD *)Bits2Bytes + (v30 & 0xC));
    *a1 = v32;
    a1[1] = v33;
    a1 = (int *)((char *)a1 + v6);
    --v28;
  }
  while ( v28 );
  v34 = *a3;
  if ( *a3 <= 1 )
  {
    v35 = 0;
LABEL_29:
    v39 = 0;
    goto LABEL_31;
  }
  v36 = *v18;
  v37 = v18 + 1;
  v34 -= 2;
  v38 = *v18 & 0xFFE0;
  *a3 = v34;
  v35 = v36 & 0x1F | (2 * v38);
  if ( v34 <= 1 )
  {
    ++v18;
    v64 = v37;
    goto LABEL_29;
  }
  v18 += 2;
  v34 -= 2;
  v39 = *v37;
  v64 = v18;
  *a3 = v34;
LABEL_31:
  v40 = v39 & 0x1F
      | (unsigned __int16)(2 * (v39 & 0xFFE0))
      | ((v39 & 0x1F | (unsigned __int16)(2 * (v39 & 0xFFE0))) << 16);
  v41 = v40 ^ (v35 | (v35 << 16));
  if ( v34 <= 1 )
  {
    v42 = 0;
LABEL_35:
    v46 = 0;
    goto LABEL_37;
  }
  v43 = *v18;
  v44 = v34 - 2;
  v45 = *v18 & 0xFFE0;
  *a3 = v44;
  v42 = v43 & 0x1F | (2 * v45);
  if ( v44 <= 1 )
  {
    v64 = v18 + 1;
    goto LABEL_35;
  }
  v47 = v44 - 2;
  v46 = v18[1];
  *a3 = v47;
  v64 = v18 + 2;
LABEL_37:
  v48 = 2;
  v49 = v46 & 0x1F | (unsigned __int16)(2 * (v46 & 0xFFE0));
  v50 = v49 | (v49 << 16);
  do
  {
    v51 = v10;
    v52 = v10;
    LOWORD(v10) = (unsigned __int16)v10 >> 4;
    v53 = v40 ^ v41 & *((_DWORD *)Bits2Bytes + (v52 & 3));
    v54 = v50 ^ (v50 ^ (v42 | (v42 << 16))) & *((_DWORD *)Bits2Bytes + (v51 & 0xC));
    *a1 = v53;
    a1[1] = v54;
    a1 = (int *)((char *)a1 + v6);
    --v48;
  }
  while ( v48 );
  return v64;
}

```

## disassembly

```asm
0x180003b18  push    rbx
0x180003b1a  push    rbp
0x180003b1b  push    rsi
0x180003b1c  push    rdi
0x180003b1d  push    r12
0x180003b1f  push    r13
0x180003b21  push    r14
0x180003b23  push    r15
0x180003b25  sub     rsp, 18h
0x180003b29  mov     r10, rdx
0x180003b2c  movsxd  r14, r9d
0x180003b2f  mov     rdx, [rsp+58h+arg_20]
0x180003b37  xor     r15d, r15d
0x180003b3a  mov     rbx, r8
0x180003b3d  mov     r11, rcx
0x180003b40  mov     eax, [rdx]
0x180003b42  test    eax, eax
0x180003b44  jle     short loc_180003B4F
0x180003b46  dec     eax
0x180003b48  mov     [rdx], eax
0x180003b4a  jmp     loc_180003F16
0x180003b4f  mov     r9d, [r8]
0x180003b52  mov     ebp, 1Fh
0x180003b57  mov     esi, 0FFE0h
0x180003b5c  lea     r13d, [rbp-1Eh]
0x180003b60  cmp     r9d, r13d
0x180003b63  ja      short loc_180003B6A
0x180003b65  mov     r8d, r15d
0x180003b68  jmp     short loc_180003BDD
0x180003b6a  movzx   r8d, word ptr [r10]
0x180003b6e  add     r9d, 0FFFFFFFEh
0x180003b72  add     r10, 2
0x180003b76  mov     [rbx], r9d
0x180003b79  test    r8w, r8w
0x180003b7d  jns     short loc_180003BD8
0x180003b7f  mov     eax, r8d
0x180003b82  mov     ecx, r8d
0x180003b85  and     eax, 0FFFFFC00h
0x180003b8a  cmp     eax, 8400h
0x180003b8f  jnz     short loc_180003BA1
0x180003b91  and     ecx, 3FFh
0x180003b97  sub     ecx, r13d
0x180003b9a  mov     [rdx], ecx
0x180003b9c  jmp     loc_180003F16
0x180003ba1  and     ecx, ebp
0x180003ba3  and     r8w, si
0x180003ba7  add     r8w, r8w
0x180003bab  mov     r9d, 4
0x180003bb1  movzx   eax, r8w
0x180003bb5  or      eax, ecx
0x180003bb7  mov     ecx, eax
0x180003bb9  shl     ecx, 10h
0x180003bbc  or      ecx, eax
0x180003bbe  mov     rax, r14
0x180003bc1  or      ebp, 0FFFFFFFFh
0x180003bc4  mov     [r11], ecx
0x180003bc7  mov     [r11+4], ecx
0x180003bcb  add     r11, rax
0x180003bce  add     r9d, ebp
0x180003bd1  jnz     short loc_180003BC4
0x180003bd3  jmp     loc_180003F16
0x180003bd8  cmp     r9d, r13d
0x180003bdb  ja      short loc_180003BE5
0x180003bdd  mov     esi, r15d
0x180003be0  jmp     loc_180003E96
0x180003be5  movzx   eax, word ptr [r10]
0x180003be9  test    ax, ax
0x180003bec  jns     loc_180003E74
0x180003bf2  lea     edx, [r9-2]
0x180003bf6  mov     r12d, 2
0x180003bfc  movzx   r9d, ax
0x180003c00  mov     [rbx], edx
0x180003c02  and     r9w, si
0x180003c06  mov     [rsp+58h+var_58], r12
0x180003c0a  add     r9w, r9w
0x180003c0e  lea     rdi, [r10+2]
0x180003c12  and     ax, bp
0x180003c15  mov     [rsp+58h+arg_8], rdi
0x180003c1a  or      r9w, ax
0x180003c1e  mov     r10, rdi
0x180003c21  cmp     edx, r13d
0x180003c24  ja      short loc_180003C2B
0x180003c26  mov     edi, r15d
0x180003c29  jmp     short loc_180003C3B
0x180003c2b  movzx   edi, word ptr [rdi]
0x180003c2e  add     r10, r12
0x180003c31  add     edx, 0FFFFFFFEh
0x180003c34  mov     [rsp+58h+arg_8], r10
0x180003c39  mov     [rbx], edx
0x180003c3b  movzx   eax, di
0x180003c3e  and     ax, si
0x180003c41  add     ax, ax
0x180003c44  movzx   ecx, ax
0x180003c47  movzx   eax, di
0x180003c4a  and     eax, ebp
0x180003c4c  or      ecx, eax
0x180003c4e  movzx   eax, r9w
0x180003c52  mov     r9d, eax
0x180003c55  mov     esi, ecx
0x180003c57  shl     r9d, 10h
0x180003c5b  shl     esi, 10h
0x180003c5e  or      r9d, eax
0x180003c61  or      esi, ecx
0x180003c63  xor     r9d, esi
0x180003c66  cmp     edx, r13d
0x180003c69  ja      short loc_180003C70
0x180003c6b  mov     ebp, r15d
0x180003c6e  jmp     short loc_180003CA0
0x180003c70  movzx   ecx, word ptr [r10]
0x180003c74  lea     rdi, [r10+2]
0x180003c78  and     bp, cx
0x180003c7b  add     edx, 0FFFFFFFEh
0x180003c7e  movzx   eax, cx
0x180003c81  mov     [rbx], edx
0x180003c83  mov     r10d, 0FFE0h
0x180003c89  and     ax, r10w
0x180003c8d  add     ax, ax
0x180003c90  or      bp, ax
0x180003c93  cmp     edx, r13d
0x180003c96  ja      short loc_180003CA5
0x180003c98  mov     r10, rdi
0x180003c9b  mov     [rsp+58h+arg_8], rdi
0x180003ca0  mov     edx, r15d
0x180003ca3  jmp     short loc_180003CB6
0x180003ca5  lea     eax, [rdx-2]
0x180003ca8  movzx   edx, word ptr [rdi]
0x180003cab  lea     r10, [rdi+2]
0x180003caf  mov     [rbx], eax
0x180003cb1  mov     [rsp+58h+arg_8], r10
0x180003cb6  movzx   eax, dx
0x180003cb9  mov     [rsp+58h+arg_20], r14
0x180003cc1  mov     ecx, 0FFE0h
0x180003cc6  lea     r14, Bits2Bytes
0x180003ccd  and     ax, cx
0x180003cd0  mov     r13d, r12d
0x180003cd3  mov     r12, [rsp+58h+arg_20]
0x180003cdb  add     ax, ax
0x180003cde  movzx   ecx, ax
0x180003ce1  movzx   eax, dx
0x180003ce4  and     eax, 1Fh
0x180003ce7  or      ecx, eax
0x180003ce9  movzx   eax, bp
0x180003cec  mov     edi, eax
0x180003cee  mov     r15d, ecx
0x180003cf1  shl     edi, 10h
0x180003cf4  shl     r15d, 10h
0x180003cf8  or      edi, eax
0x180003cfa  or      r15d, ecx
0x180003cfd  xor     edi, r15d
0x180003d00  or      ebp, 0FFFFFFFFh
0x180003d03  movzx   edx, r8w
0x180003d07  mov     eax, edx
0x180003d09  shr     r8w, 4
0x180003d0e  and     eax, 3
0x180003d11  and     edx, 0Ch
0x180003d14  mov     ecx, [r14+rax*4]
0x180003d18  mov     eax, [r14+rdx*4]
0x180003d1c  and     ecx, r9d
0x180003d1f  and     eax, edi
0x180003d21  xor     ecx, esi
0x180003d23  xor     eax, r15d
0x180003d26  mov     [r11], ecx
0x180003d29  mov     [r11+4], eax
0x180003d2d  add     r11, r12
0x180003d30  add     r13d, ebp
0x180003d33  jnz     short loc_180003D03
0x180003d35  mov     edx, [rbx]
0x180003d37  lea     r12d, [r13+1Fh]
0x180003d3b  mov     r13d, 0FFE0h
0x180003d41  cmp     edx, 1
0x180003d44  ja      short loc_180003D4A
0x180003d46  xor     edi, edi
0x180003d48  jmp     short loc_180003D75
0x180003d4a  movzx   ecx, word ptr [r10]
0x180003d4e  lea     r9, [r10+2]
0x180003d52  movzx   eax, cx
0x180003d55  add     edx, 0FFFFFFFEh
0x180003d58  and     ax, r13w
0x180003d5c  mov     [rbx], edx
0x180003d5e  and     cx, r12w
0x180003d62  lea     edi, [rax+rax]
0x180003d65  or      di, cx
0x180003d68  cmp     edx, 1
0x180003d6b  ja      short loc_180003D7A
0x180003d6d  mov     r10, r9
0x180003d70  mov     [rsp+58h+arg_8], r9
0x180003d75  xor     r9d, r9d
0x180003d78  jmp     short loc_180003D8C
0x180003d7a  lea     r10, [r9+2]
0x180003d7e  add     edx, 0FFFFFFFEh
0x180003d81  movzx   r9d, word ptr [r9]
0x180003d85  mov     [rsp+58h+arg_8], r10
0x180003d8a  mov     [rbx], edx
0x180003d8c  movzx   eax, r9w
0x180003d90  and     ax, r13w
0x180003d94  add     ax, ax
0x180003d97  movzx   ecx, ax
0x180003d9a  movzx   eax, r9w
0x180003d9e  and     eax, r12d
0x180003da1  or      ecx, eax
0x180003da3  movzx   eax, di
0x180003da6  mov     edi, eax
0x180003da8  mov     esi, ecx
0x180003daa  shl     edi, 10h
0x180003dad  shl     esi, 10h
0x180003db0  or      edi, eax
0x180003db2  or      esi, ecx
0x180003db4  xor     edi, esi
0x180003db6  cmp     edx, 1
0x180003db9  ja      short loc_180003DC0
0x180003dbb  xor     r15d, r15d
0x180003dbe  jmp     short loc_180003DEA
0x180003dc0  movzx   ecx, word ptr [r10]
0x180003dc4  lea     r9, [r10+2]
0x180003dc8  movzx   eax, cx
0x180003dcb  add     edx, 0FFFFFFFEh
0x180003dce  and     ax, r13w
0x180003dd2  mov     [rbx], edx
0x180003dd4  and     cx, r12w
0x180003dd8  lea     r15d, [rax+rax]
0x180003ddc  or      r15w, cx
0x180003de0  cmp     edx, 1
0x180003de3  ja      short loc_180003DEE
0x180003de5  mov     [rsp+58h+arg_8], r9
0x180003dea  xor     edx, edx
0x180003dec  jmp     short loc_180003E00
0x180003dee  lea     eax, [rdx-2]
0x180003df1  movzx   edx, word ptr [r9]
0x180003df5  lea     r10, [r9+2]
0x180003df9  mov     [rbx], eax
0x180003dfb  mov     [rsp+58h+arg_8], r10
0x180003e00  mov     r10, [rsp+58h+arg_20]
0x180003e08  movzx   eax, dx
0x180003e0b  and     ax, r13w
0x180003e0f  add     ax, ax
0x180003e12  movzx   ecx, ax
0x180003e15  movzx   eax, dx
0x180003e18  and     eax, r12d
0x180003e1b  mov     r12, [rsp+58h+var_58]
0x180003e1f  or      ecx, eax
0x180003e21  movzx   eax, r15w
0x180003e25  mov     r9d, eax
0x180003e28  mov     ebx, ecx
0x180003e2a  shl     r9d, 10h
0x180003e2e  shl     ebx, 10h
0x180003e31  or      r9d, eax
0x180003e34  or      ebx, ecx
0x180003e36  xor     r9d, ebx
0x180003e39  movzx   edx, r8w
0x180003e3d  mov     eax, edx
0x180003e3f  shr     r8w, 4
0x180003e44  and     eax, 3
0x180003e47  and     edx, 0Ch
0x180003e4a  mov     ecx, [r14+rax*4]
0x180003e4e  mov     eax, [r14+rdx*4]
0x180003e52  and     ecx, edi
0x180003e54  and     eax, r9d
0x180003e57  xor     ecx, esi
0x180003e59  xor     eax, ebx
0x180003e5b  mov     [r11], ecx
0x180003e5e  mov     [r11+4], eax
0x180003e62  add     r11, r10
0x180003e65  add     r12d, ebp
0x180003e68  jnz     short loc_180003E39
0x180003e6a  mov     r10, [rsp+58h+arg_8]
0x180003e6f  jmp     loc_180003F16
0x180003e74  movzx   ecx, ax
0x180003e77  lea     rdx, [r10+2]
0x180003e7b  and     ax, si
0x180003e7e  and     cx, bp
0x180003e81  add     r9d, 0FFFFFFFEh
0x180003e85  mov     [rbx], r9d
0x180003e88  lea     esi, [rax+rax]
0x180003e8b  or      si, cx
0x180003e8e  cmp     r9d, r13d
0x180003e91  ja      short loc_180003E9B
0x180003e93  mov     r10, rdx
0x180003e96  mov     edx, r15d
0x180003e99  jmp     short loc_180003EA8
0x180003e9b  lea     eax, [r9-2]
0x180003e9f  lea     r10, [rdx+2]
0x180003ea3  mov     [rbx], eax
0x180003ea5  movzx   edx, word ptr [rdx]
0x180003ea8  movzx   eax, dx
0x180003eab  mov     ecx, 0FFE0h
0x180003eb0  and     ax, cx
0x180003eb3  mov     r9d, 4
0x180003eb9  add     ax, ax
0x180003ebc  movzx   ecx, ax
0x180003ebf  movzx   eax, dx
0x180003ec2  and     eax, ebp
0x180003ec4  or      ecx, eax
0x180003ec6  movzx   eax, si
0x180003ec9  mov     ebx, eax
0x180003ecb  mov     edi, ecx
0x180003ecd  shl     ebx, 10h
0x180003ed0  mov     rsi, r14
0x180003ed3  shl     edi, 10h
0x180003ed6  lea     r14, Bits2Bytes
0x180003edd  or      ebx, eax
  ... truncated ...
```
