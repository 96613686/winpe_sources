# CcpCheckOption

- ea: `0x180024b08`
- end: `0x180024f8f`
- name: `CcpCheckOption`
- size: `1159`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025070`
- `0x1800254c0`

## callees

- `0x180024b08`
- `0x180032454`
- `0x180033010`

## string_xrefs

- `0x180024bd7`: `Nak - Compression disabled`

## pseudocode

```c
__int64 __fastcall CcpCheckOption(_DWORD *a1, __int64 a2, _BYTE *a3, _DWORD *a4, int a5)
{
  unsigned __int8 v5; // al
  unsigned int v7; // r15d
  char v11; // al
  int v12; // r8d
  __int64 v13; // rdx
  int v14; // ebp
  int v15; // r9d
  int v16; // ebp
  int v17; // r12d
  const wchar_t *v18; // r8
  int v19; // eax
  const wchar_t *v20; // r8
  int v21; // r8d
  int v22; // eax
  bool v23; // zf
  int v24; // r8d
  int v25; // eax
  int v27; // eax
  __int64 v28; // rcx
  __int128 v29; // xmm1
  int v30; // eax
  _OWORD *v31; // rdx
  __int64 v32; // r8

  v5 = a3[1];
  v7 = 0;
  *a4 = 2;
  if ( !*a3 )
  {
    if ( v5 >= 6u )
    {
      if ( a1[5] || a1[4] || *(_BYTE *)(a2 + 68) )
        goto LABEL_94;
      *(_BYTE *)(a2 + 440) = 0;
LABEL_102:
      v28 = *(unsigned __int16 *)(a2 + 70);
      v29 = *(_OWORD *)(a2 + 88);
      v30 = *(_DWORD *)(a2 + 104);
      *(_WORD *)(a2 + 442) = v28;
      v31 = (_OWORD *)(a2 + 72);
      *(_OWORD *)(a2 + 444) = *v31;
      *(_OWORD *)(a2 + 460) = v29;
      *(_DWORD *)(a2 + 476) = v30;
      v32 = (unsigned __int8)a3[1];
      if ( v32 != v28 + 2 || memcmp_0(a3 + 2, v31, v32 - 2) )
        *a4 = 3;
      return v7;
    }
    return 722;
  }
  if ( *a3 != 18 )
  {
    if ( v5 >= 2u )
    {
      if ( a1[5] )
        goto LABEL_94;
      if ( a1[4] )
        goto LABEL_94;
      v11 = *(_BYTE *)(a2 + 68);
      if ( *a3 != v11 )
        goto LABEL_94;
      *(_BYTE *)(a2 + 440) = v11;
      goto LABEL_102;
    }
    return 722;
  }
  if ( v5 != 6 )
    return 722;
  v12 = (unsigned __int8)a3[5]
      + ((unsigned __int8)a3[2] << 24)
      + ((unsigned __int8)a3[4] << 8)
      + ((unsigned __int8)a3[3] << 16);
  *(_DWORD *)(a2 + 432) = v12;
  if ( a1[5] && (v12 & 1) != 0 )
  {
    v12 &= ~1u;
    *(_DWORD *)(a2 + 432) = v12;
    v13 = xmmword_18004C7A0;
    if ( (_QWORD)xmmword_18004C7A0 )
    {
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, _BYTE *))gRasccpTemplateFunc)(
        gRasccpEtwContext,
        xmmword_18004C7A0,
        L"Nak - Compression disabled",
        a3);
      v12 = *(_DWORD *)(a2 + 432);
      v13 = xmmword_18004C7A0;
    }
    *a4 = 3;
  }
  else
  {
    v13 = xmmword_18004C7A0;
  }
  v14 = *(_DWORD *)(a2 + 60);
  if ( (v14 & 0x1000000) == 0 && (v12 & 0x1000000) != 0 )
  {
    v12 &= ~0x1000000u;
    *a4 = 3;
    *(_DWORD *)(a2 + 432) = v12;
  }
  v15 = g_dwAllowPPTPWeakCrypto;
  if ( g_dwAllowPPTPWeakCrypto )
    v16 = v14 & 0xF0;
  else
    v16 = v14 & 0x40;
  if ( g_dwAllowPPTPWeakCrypto )
    v17 = v12 & 0xF0;
  else
    v17 = v12 & 0x40;
  if ( (v12 & 0x40) != 0 )
  {
    if ( (v16 & 0x40) != 0 )
    {
      if ( (v12 & 0xB0) == 0 )
        goto LABEL_32;
      *(_DWORD *)(a2 + 432) = v12 & 0xFFFFFF4F;
      if ( !v13 )
        goto LABEL_31;
      v18 = L"Nak - Accepting 128 bit";
    }
    else
    {
      *(_DWORD *)(a2 + 432) = v12 & 0xFFFFFFBF;
      if ( !v13 )
      {
LABEL_31:
        *a4 = 3;
        goto LABEL_32;
      }
      v18 = L"Nak - 128 bit not supported";
    }
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(gRasccpEtwContext, v13, v18);
    v15 = g_dwAllowPPTPWeakCrypto;
    v13 = xmmword_18004C7A0;
    goto LABEL_31;
  }
LABEL_32:
  v19 = *(_DWORD *)(a2 + 432);
  if ( (v19 & 0x80u) == 0 )
    goto LABEL_38;
  if ( (v16 & 0x80u) == 0 )
  {
    v19 &= ~0x80u;
  }
  else
  {
    if ( (v19 & 0x30) == 0 )
      goto LABEL_38;
    v19 &= 0xFFFFFFCF;
  }
  *a4 = 3;
  *(_DWORD *)(a2 + 432) = v19;
LABEL_38:
  if ( (v19 & 0x20) != 0 )
  {
    if ( (v16 & 0x20) == 0 )
    {
      *(_DWORD *)(a2 + 432) = v19 & 0xFFFFFFDF;
      if ( v13 )
      {
        v20 = L"Nak - 40 bit not supported";
        goto LABEL_45;
      }
LABEL_46:
      *a4 = 3;
      goto LABEL_47;
    }
    if ( (v19 & 0x10) != 0 )
    {
      *(_DWORD *)(a2 + 432) = v19 & 0xFFFFFFEF;
      if ( *((_QWORD *)&xmmword_18004C7A0 + 1) )
      {
        v20 = L"Nak - Accepting 40 bit";
        v13 = *((_QWORD *)&xmmword_18004C7A0 + 1);
LABEL_45:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(gRasccpEtwContext, v13, v20);
        v15 = g_dwAllowPPTPWeakCrypto;
        v13 = xmmword_18004C7A0;
        goto LABEL_46;
      }
      goto LABEL_46;
    }
  }
LABEL_47:
  v21 = *(_DWORD *)(a2 + 432);
  if ( (v21 & 0x10) != 0 && (v16 & 0x10) == 0 )
  {
    *(_DWORD *)(a2 + 432) = v21 & 0xFFFFFFEF;
    if ( v13 )
    {
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
        gRasccpEtwContext,
        v13,
        L"Nak - legacy 40 bit not supported");
      v13 = xmmword_18004C7A0;
      v15 = g_dwAllowPPTPWeakCrypto;
    }
    *a4 = 3;
  }
  v22 = *(_DWORD *)(a2 + 432);
  if ( v15 )
    v23 = (v22 & 0xF0) == 0;
  else
    v23 = (v22 & 0x40) == 0;
  if ( !v23 )
    goto LABEL_80;
  v24 = a1[4];
  if ( !v24 && !v17 )
    goto LABEL_80;
  if ( !v16 )
    goto LABEL_80;
  if ( !a5 )
  {
    if ( !v24 )
    {
      v22 |= v16;
      *(_DWORD *)(a2 + 432) |= v16;
      goto LABEL_79;
    }
    return 742;
  }
  v25 = a1[6];
  a1[7] = v25;
  do
  {
    switch ( v25 )
    {
      case 0:
        a1[6] = 64;
        v25 = 64;
        continue;
      case 64:
        if ( v15 )
        {
          a1[6] = 128;
          v25 = 128;
          continue;
        }
        break;
      case 128:
        if ( v15 )
        {
          a1[6] = 32;
          v25 = 32;
          continue;
        }
        break;
      default:
        if ( v25 == 32 && v15 )
        {
          a1[6] = 16;
          v25 = 16;
          continue;
        }
        break;
    }
    a1[6] = 0;
    if ( !v24 )
      goto LABEL_75;
    v25 = 0;
  }
  while ( (v25 & v16) == 0 );
  *(_DWORD *)(a2 + 432) |= v25;
LABEL_75:
  v22 = *(_DWORD *)(a2 + 432);
LABEL_79:
  *a4 = 3;
LABEL_80:
  if ( (v22 & 0xFEFFFF0E) != 0 )
  {
    if ( v15 )
      v27 = v22 & 0x10000F1;
    else
      v27 = v22 & 0x1000041;
    *(_DWORD *)(a2 + 432) = v27;
    if ( v13 )
    {
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
        gRasccpEtwContext,
        v13,
        L"Nak - unknown bits");
      v13 = xmmword_18004C7A0;
      v15 = g_dwAllowPPTPWeakCrypto;
    }
    *a4 = 3;
  }
  if ( *a4 == 3 )
  {
    if ( v15 )
    {
      if ( (*(_BYTE *)(a2 + 432) & 0xF1) != 0 )
        return v7;
    }
    else if ( (*(_BYTE *)(a2 + 432) & 0x41) != 0 )
    {
      return v7;
    }
    if ( v13 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(
        gRasccpEtwContext,
        v13,
        L"Rej - No bits supported");
LABEL_94:
    *a4 = 4;
  }
  return v7;
}

```

## disassembly

```asm
0x180024b08  push    rbx
0x180024b0a  push    rbp
0x180024b0b  push    rsi
0x180024b0c  push    rdi
0x180024b0d  push    r12
0x180024b0f  push    r14
0x180024b11  push    r15
0x180024b13  sub     rsp, 20h
0x180024b17  mov     al, [r8+1]
0x180024b1b  mov     rdi, r9
0x180024b1e  xor     r15d, r15d
0x180024b21  mov     r9, r8
0x180024b24  mov     rbx, rdx
0x180024b27  mov     r14, rcx
0x180024b2a  mov     dword ptr [rdi], 2
0x180024b30  cmp     [r8], r15b
0x180024b33  jz      loc_180024F10
0x180024b39  cmp     byte ptr [r8], 12h
0x180024b3d  jz      short loc_180024B72
0x180024b3f  cmp     al, 2
0x180024b41  jb      loc_180024F14
0x180024b47  cmp     [rcx+14h], r15d
0x180024b4b  jnz     loc_180024EF8
0x180024b51  cmp     [rcx+10h], r15d
0x180024b55  jnz     loc_180024EF8
0x180024b5b  mov     al, [rdx+44h]
0x180024b5e  cmp     [r8], al
0x180024b61  jnz     loc_180024EF8
0x180024b67  mov     [rdx+1B8h], al
0x180024b6d  jmp     loc_180024F35
0x180024b72  cmp     al, 6
0x180024b74  jnz     loc_180024F14
0x180024b7a  movzx   r8d, byte ptr [r8+3]
0x180024b7f  mov     esi, 3
0x180024b84  movzx   eax, byte ptr [r9+4]
0x180024b89  shl     eax, 8
0x180024b8c  shl     r8d, 10h
0x180024b90  add     r8d, eax
0x180024b93  movzx   eax, byte ptr [r9+2]
0x180024b98  shl     eax, 18h
0x180024b9b  add     r8d, eax
0x180024b9e  movzx   eax, byte ptr [r9+5]
0x180024ba3  add     r8d, eax
0x180024ba6  mov     [rdx+1B0h], r8d
0x180024bad  cmp     [rcx+14h], r15d
0x180024bb1  jz      short loc_180024BFC
0x180024bb3  test    r8b, 1
0x180024bb7  jz      short loc_180024BFC
0x180024bb9  and     r8d, 0FFFFFFFEh
0x180024bbd  mov     [rdx+1B0h], r8d
0x180024bc4  mov     rdx, qword ptr cs:xmmword_18004C7A0
0x180024bcb  test    rdx, rdx
0x180024bce  jz      short loc_180024BF8
0x180024bd0  mov     rcx, cs:gRasccpEtwContext
0x180024bd7  lea     r8, aNakCompression; "Nak - Compression disabled"
0x180024bde  mov     rax, cs:gRasccpTemplateFunc
0x180024be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bea  mov     r8d, [rbx+1B0h]
0x180024bf1  mov     rdx, qword ptr cs:xmmword_18004C7A0
0x180024bf8  mov     [rdi], esi
0x180024bfa  jmp     short loc_180024C03
0x180024bfc  mov     rdx, qword ptr cs:xmmword_18004C7A0
0x180024c03  mov     ebp, [rbx+3Ch]
0x180024c06  bt      ebp, 18h
0x180024c0a  setnb   cl
0x180024c0d  bt      r8d, 18h
0x180024c12  setb    al
0x180024c15  test    al, cl
0x180024c17  jz      short loc_180024C27
0x180024c19  btr     r8d, 18h
0x180024c1e  mov     [rdi], esi
0x180024c20  mov     [rbx+1B0h], r8d
0x180024c27  mov     r9d, cs:g_dwAllowPPTPWeakCrypto
0x180024c2e  mov     ecx, 0F0h
0x180024c33  test    r9d, r9d
0x180024c36  jz      short loc_180024C3C
0x180024c38  and     ebp, ecx
0x180024c3a  jmp     short loc_180024C3F
0x180024c3c  and     ebp, 40h
0x180024c3f  mov     eax, r8d
0x180024c42  and     eax, 40h
0x180024c45  test    r9d, r9d
0x180024c48  jz      short loc_180024C52
0x180024c4a  mov     r12d, r8d
0x180024c4d  and     r12d, ecx
0x180024c50  jmp     short loc_180024C55
0x180024c52  mov     r12d, eax
0x180024c55  test    eax, eax
0x180024c57  jz      short loc_180024CBB
0x180024c59  test    bpl, 40h
0x180024c5d  jz      short loc_180024C81
0x180024c5f  test    r8b, 0B0h
0x180024c63  jz      short loc_180024CBB
0x180024c65  and     r8d, 0FFFFFF4Fh
0x180024c6c  mov     [rbx+1B0h], r8d
0x180024c73  test    rdx, rdx
0x180024c76  jz      short loc_180024CB9
0x180024c78  lea     r8, aNakAccepting12; "Nak - Accepting 128 bit"
0x180024c7f  jmp     short loc_180024C98
0x180024c81  and     r8d, 0FFFFFFBFh
0x180024c85  mov     [rbx+1B0h], r8d
0x180024c8c  test    rdx, rdx
0x180024c8f  jz      short loc_180024CB9
0x180024c91  lea     r8, aNak128BitNotSu; "Nak - 128 bit not supported"
0x180024c98  mov     rcx, cs:gRasccpEtwContext
0x180024c9f  mov     rax, cs:gRasccpTemplateFunc
0x180024ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cab  mov     r9d, cs:g_dwAllowPPTPWeakCrypto
0x180024cb2  mov     rdx, qword ptr cs:xmmword_18004C7A0
0x180024cb9  mov     [rdi], esi
0x180024cbb  mov     eax, [rbx+1B0h]
0x180024cc1  test    al, al
0x180024cc3  jns     short loc_180024CDF
0x180024cc5  test    bpl, bpl
0x180024cc8  jns     short loc_180024CD3
0x180024cca  test    al, 30h
0x180024ccc  jz      short loc_180024CDF
0x180024cce  and     eax, 0FFFFFFCFh
0x180024cd1  jmp     short loc_180024CD7
0x180024cd3  btr     eax, 7
0x180024cd7  mov     [rdi], esi
0x180024cd9  mov     [rbx+1B0h], eax
0x180024cdf  test    al, 20h
0x180024ce1  jz      short loc_180024D46
0x180024ce3  test    bpl, 20h
0x180024ce7  jz      short loc_180024D0E
0x180024ce9  test    al, 10h
0x180024ceb  jz      short loc_180024D46
0x180024ced  and     eax, 0FFFFFFEFh
0x180024cf0  mov     [rbx+1B0h], eax
0x180024cf6  mov     rax, qword ptr cs:xmmword_18004C7A0+8
0x180024cfd  test    rax, rax
0x180024d00  jz      short loc_180024D44
0x180024d02  lea     r8, aNakAccepting40; "Nak - Accepting 40 bit"
0x180024d09  mov     rdx, rax
0x180024d0c  jmp     short loc_180024D23
0x180024d0e  and     eax, 0FFFFFFDFh
0x180024d11  mov     [rbx+1B0h], eax
0x180024d17  test    rdx, rdx
0x180024d1a  jz      short loc_180024D44
0x180024d1c  lea     r8, aNak40BitNotSup; "Nak - 40 bit not supported"
0x180024d23  mov     rcx, cs:gRasccpEtwContext
0x180024d2a  mov     rax, cs:gRasccpTemplateFunc
0x180024d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d36  mov     r9d, cs:g_dwAllowPPTPWeakCrypto
0x180024d3d  mov     rdx, qword ptr cs:xmmword_18004C7A0
0x180024d44  mov     [rdi], esi
0x180024d46  mov     r8d, [rbx+1B0h]
0x180024d4d  test    r8b, 10h
0x180024d51  setnz   cl
0x180024d54  test    bpl, 10h
0x180024d58  setz    al
0x180024d5b  test    al, cl
0x180024d5d  jz      short loc_180024D99
0x180024d5f  and     r8d, 0FFFFFFEFh
0x180024d63  mov     [rbx+1B0h], r8d
0x180024d6a  test    rdx, rdx
0x180024d6d  jz      short loc_180024D97
0x180024d6f  mov     rcx, cs:gRasccpEtwContext
0x180024d76  lea     r8, aNakLegacy40Bit; "Nak - legacy 40 bit not supported"
0x180024d7d  mov     rax, cs:gRasccpTemplateFunc
0x180024d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d89  mov     rdx, qword ptr cs:xmmword_18004C7A0
0x180024d90  mov     r9d, cs:g_dwAllowPPTPWeakCrypto
0x180024d97  mov     [rdi], esi
0x180024d99  mov     eax, [rbx+1B0h]
0x180024d9f  test    r9d, r9d
0x180024da2  jz      short loc_180024DA8
0x180024da4  test    al, 0F0h
0x180024da6  jmp     short loc_180024DAA
0x180024da8  test    al, 40h
0x180024daa  jnz     loc_180024E6F
0x180024db0  mov     r8d, [r14+10h]
0x180024db4  mov     ecx, eax
0x180024db6  test    r8d, r8d
0x180024db9  jnz     short loc_180024DC4
0x180024dbb  test    r12d, r12d
0x180024dbe  jz      loc_180024E6F
0x180024dc4  test    ebp, ebp
0x180024dc6  jz      loc_180024E6F
0x180024dcc  cmp     [rsp+58h+arg_20], r15d
0x180024dd4  jz      short loc_180024E54
0x180024dd6  mov     eax, [r14+18h]
0x180024dda  mov     ecx, 20h ; ' '
0x180024ddf  mov     [r14+1Ch], eax
0x180024de3  lea     r10d, [rcx+60h]
0x180024de7  test    eax, eax
0x180024de9  jnz     short loc_180024DFA
0x180024deb  mov     dword ptr [r14+18h], 40h ; '@'
0x180024df3  mov     eax, 40h ; '@'
0x180024df8  jmp     short loc_180024E42
0x180024dfa  cmp     eax, 40h ; '@'
0x180024dfd  jnz     short loc_180024E0D
0x180024dff  test    r9d, r9d
0x180024e02  jz      short loc_180024E37
0x180024e04  mov     [r14+18h], r10d
0x180024e08  mov     eax, r10d
0x180024e0b  jmp     short loc_180024E42
0x180024e0d  cmp     eax, r10d
0x180024e10  jnz     short loc_180024E1F
0x180024e12  test    r9d, r9d
0x180024e15  jz      short loc_180024E37
0x180024e17  mov     [r14+18h], ecx
0x180024e1b  mov     eax, ecx
0x180024e1d  jmp     short loc_180024E42
0x180024e1f  cmp     eax, ecx
0x180024e21  jnz     short loc_180024E37
0x180024e23  test    r9d, r9d
0x180024e26  jz      short loc_180024E37
0x180024e28  mov     dword ptr [r14+18h], 10h
0x180024e30  mov     eax, 10h
0x180024e35  jmp     short loc_180024E42
0x180024e37  mov     [r14+18h], r15d
0x180024e3b  test    r8d, r8d
0x180024e3e  jz      short loc_180024E4C
0x180024e40  xor     eax, eax
0x180024e42  test    ebp, eax
0x180024e44  jz      short loc_180024DE7
0x180024e46  or      [rbx+1B0h], eax
0x180024e4c  mov     eax, [rbx+1B0h]
0x180024e52  jmp     short loc_180024E6D
0x180024e54  test    r8d, r8d
0x180024e57  jz      short loc_180024E63
0x180024e59  mov     eax, 2E6h
0x180024e5e  jmp     loc_180024F01
0x180024e63  mov     eax, ecx
0x180024e65  or      eax, ebp
0x180024e67  mov     [rbx+1B0h], eax
0x180024e6d  mov     [rdi], esi
0x180024e6f  test    eax, 0FEFFFF0Eh
0x180024e74  jz      short loc_180024EBC
0x180024e76  test    r9d, r9d
0x180024e79  jz      short loc_180024E82
0x180024e7b  and     eax, 10000F1h
0x180024e80  jmp     short loc_180024E87
0x180024e82  and     eax, 1000041h
0x180024e87  mov     [rbx+1B0h], eax
0x180024e8d  test    rdx, rdx
0x180024e90  jz      short loc_180024EBA
0x180024e92  mov     rcx, cs:gRasccpEtwContext
0x180024e99  lea     r8, aNakUnknownBits; "Nak - unknown bits"
0x180024ea0  mov     rax, cs:gRasccpTemplateFunc
0x180024ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024eac  mov     rdx, qword ptr cs:xmmword_18004C7A0
0x180024eb3  mov     r9d, cs:g_dwAllowPPTPWeakCrypto
0x180024eba  mov     [rdi], esi
0x180024ebc  cmp     [rdi], esi
0x180024ebe  jnz     short loc_180024EFE
0x180024ec0  test    r9d, r9d
0x180024ec3  jz      short loc_180024ED0
0x180024ec5  test    byte ptr [rbx+1B0h], 0F1h
0x180024ecc  jz      short loc_180024ED9
0x180024ece  jmp     short loc_180024EFE
0x180024ed0  test    byte ptr [rbx+1B0h], 41h
0x180024ed7  jnz     short loc_180024EFE
0x180024ed9  test    rdx, rdx
0x180024edc  jz      short loc_180024EF8
0x180024ede  mov     rcx, cs:gRasccpEtwContext
0x180024ee5  lea     r8, aRejNoBitsSuppo; "Rej - No bits supported"
0x180024eec  mov     rax, cs:gRasccpTemplateFunc
0x180024ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ef8  mov     dword ptr [rdi], 4
0x180024efe  mov     eax, r15d
0x180024f01  add     rsp, 20h
0x180024f05  pop     r15
0x180024f07  pop     r14
0x180024f09  pop     r12
0x180024f0b  pop     rdi
0x180024f0c  pop     rsi
0x180024f0d  pop     rbp
0x180024f0e  pop     rbx
0x180024f0f  retn
0x180024f10  cmp     al, 6
0x180024f12  jnb     short loc_180024F1C
0x180024f14  mov     r15d, 2D2h
0x180024f1a  jmp     short loc_180024EFE
0x180024f1c  cmp     [rcx+14h], r15d
0x180024f20  jnz     short loc_180024EF8
0x180024f22  cmp     [rcx+10h], r15d
0x180024f26  jnz     short loc_180024EF8
0x180024f28  cmp     [rdx+44h], r15b
0x180024f2c  jnz     short loc_180024EF8
0x180024f2e  mov     [rdx+1B8h], r15b
0x180024f35  movzx   ecx, word ptr [rdx+46h]
0x180024f39  movups  xmm1, xmmword ptr [rdx+58h]
0x180024f3d  mov     eax, [rdx+68h]
0x180024f40  mov     [rdx+1BAh], cx
0x180024f47  add     rdx, 48h ; 'H'; Buf2
0x180024f4b  add     rcx, 2
0x180024f4f  movups  xmm0, xmmword ptr [rdx]
0x180024f52  movups  xmmword ptr [rbx+1BCh], xmm0
0x180024f59  movups  xmmword ptr [rbx+1CCh], xmm1
0x180024f60  mov     [rbx+1DCh], eax
0x180024f66  movzx   r8d, byte ptr [r8+1]
0x180024f6b  cmp     r8, rcx
0x180024f6e  jz      short loc_180024F78
0x180024f70  mov     dword ptr [rdi], 3
0x180024f76  jmp     short loc_180024EFE
0x180024f78  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180024f7c  lea     rcx, [r9+2]; Buf1
  ... truncated ...
```
