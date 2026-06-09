# CcpCheckOption

- ea: `0x1800258b0`
- end: `0x180025d38`
- name: `CcpCheckOption`
- size: `1160`
- prototype: `__int64 __fastcall(_DWORD *, __int64, _BYTE *, _DWORD *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025e10`
- `0x180026270`

## callees

- `0x1800258b0`
- `0x180033a74`
- `0x180034010`

## string_xrefs

- `0x18002597f`: `Nak - Compression disabled`

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
    v13 = xmmword_18004D7A0;
    if ( (_QWORD)xmmword_18004D7A0 )
    {
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, _BYTE *))gRasccpTemplateFunc)(
        gRasccpEtwContext,
        xmmword_18004D7A0,
        L"Nak - Compression disabled",
        a3);
      v12 = *(_DWORD *)(a2 + 432);
      v13 = xmmword_18004D7A0;
    }
    *a4 = 3;
  }
  else
  {
    v13 = xmmword_18004D7A0;
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
    v13 = xmmword_18004D7A0;
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
      if ( *((_QWORD *)&xmmword_18004D7A0 + 1) )
      {
        v20 = L"Nak - Accepting 40 bit";
        v13 = *((_QWORD *)&xmmword_18004D7A0 + 1);
LABEL_45:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasccpTemplateFunc)(gRasccpEtwContext, v13, v20);
        v15 = g_dwAllowPPTPWeakCrypto;
        v13 = xmmword_18004D7A0;
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
      v13 = xmmword_18004D7A0;
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
      v13 = xmmword_18004D7A0;
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
0x1800258b0  push    rbx
0x1800258b2  push    rbp
0x1800258b3  push    rsi
0x1800258b4  push    rdi
0x1800258b5  push    r12
0x1800258b7  push    r14
0x1800258b9  push    r15
0x1800258bb  sub     rsp, 20h
0x1800258bf  mov     al, [r8+1]
0x1800258c3  mov     rdi, r9
0x1800258c6  xor     r15d, r15d
0x1800258c9  mov     r9, r8
0x1800258cc  mov     rbx, rdx
0x1800258cf  mov     r14, rcx
0x1800258d2  mov     dword ptr [rdi], 2
0x1800258d8  cmp     [r8], r15b
0x1800258db  jz      loc_180025CB9
0x1800258e1  cmp     byte ptr [r8], 12h
0x1800258e5  jz      short loc_18002591A
0x1800258e7  cmp     al, 2
0x1800258e9  jb      loc_180025CBD
0x1800258ef  cmp     [rcx+14h], r15d
0x1800258f3  jnz     loc_180025CA0
0x1800258f9  cmp     [rcx+10h], r15d
0x1800258fd  jnz     loc_180025CA0
0x180025903  mov     al, [rdx+44h]
0x180025906  cmp     [r8], al
0x180025909  jnz     loc_180025CA0
0x18002590f  mov     [rdx+1B8h], al
0x180025915  jmp     loc_180025CDE
0x18002591a  cmp     al, 6
0x18002591c  jnz     loc_180025CBD
0x180025922  movzx   r8d, byte ptr [r8+3]
0x180025927  mov     esi, 3
0x18002592c  movzx   eax, byte ptr [r9+4]
0x180025931  shl     eax, 8
0x180025934  shl     r8d, 10h
0x180025938  add     r8d, eax
0x18002593b  movzx   eax, byte ptr [r9+2]
0x180025940  shl     eax, 18h
0x180025943  add     r8d, eax
0x180025946  movzx   eax, byte ptr [r9+5]
0x18002594b  add     r8d, eax
0x18002594e  mov     [rdx+1B0h], r8d
0x180025955  cmp     [rcx+14h], r15d
0x180025959  jz      short loc_1800259A4
0x18002595b  test    r8b, 1
0x18002595f  jz      short loc_1800259A4
0x180025961  and     r8d, 0FFFFFFFEh
0x180025965  mov     [rdx+1B0h], r8d
0x18002596c  mov     rdx, qword ptr cs:xmmword_18004D7A0
0x180025973  test    rdx, rdx
0x180025976  jz      short loc_1800259A0
0x180025978  mov     rcx, cs:gRasccpEtwContext
0x18002597f  lea     r8, aNakCompression; "Nak - Compression disabled"
0x180025986  mov     rax, cs:gRasccpTemplateFunc
0x18002598d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025992  mov     r8d, [rbx+1B0h]
0x180025999  mov     rdx, qword ptr cs:xmmword_18004D7A0
0x1800259a0  mov     [rdi], esi
0x1800259a2  jmp     short loc_1800259AB
0x1800259a4  mov     rdx, qword ptr cs:xmmword_18004D7A0
0x1800259ab  mov     ebp, [rbx+3Ch]
0x1800259ae  bt      ebp, 18h
0x1800259b2  setnb   cl
0x1800259b5  bt      r8d, 18h
0x1800259ba  setb    al
0x1800259bd  test    al, cl
0x1800259bf  jz      short loc_1800259CF
0x1800259c1  btr     r8d, 18h
0x1800259c6  mov     [rdi], esi
0x1800259c8  mov     [rbx+1B0h], r8d
0x1800259cf  mov     r9d, cs:g_dwAllowPPTPWeakCrypto
0x1800259d6  mov     ecx, 0F0h
0x1800259db  test    r9d, r9d
0x1800259de  jz      short loc_1800259E4
0x1800259e0  and     ebp, ecx
0x1800259e2  jmp     short loc_1800259E7
0x1800259e4  and     ebp, 40h
0x1800259e7  mov     eax, r8d
0x1800259ea  and     eax, 40h
0x1800259ed  test    r9d, r9d
0x1800259f0  jz      short loc_1800259FA
0x1800259f2  mov     r12d, r8d
0x1800259f5  and     r12d, ecx
0x1800259f8  jmp     short loc_1800259FD
0x1800259fa  mov     r12d, eax
0x1800259fd  test    eax, eax
0x1800259ff  jz      short loc_180025A63
0x180025a01  test    bpl, 40h
0x180025a05  jz      short loc_180025A29
0x180025a07  test    r8b, 0B0h
0x180025a0b  jz      short loc_180025A63
0x180025a0d  and     r8d, 0FFFFFF4Fh
0x180025a14  mov     [rbx+1B0h], r8d
0x180025a1b  test    rdx, rdx
0x180025a1e  jz      short loc_180025A61
0x180025a20  lea     r8, aNakAccepting12; "Nak - Accepting 128 bit"
0x180025a27  jmp     short loc_180025A40
0x180025a29  and     r8d, 0FFFFFFBFh
0x180025a2d  mov     [rbx+1B0h], r8d
0x180025a34  test    rdx, rdx
0x180025a37  jz      short loc_180025A61
0x180025a39  lea     r8, aNak128BitNotSu; "Nak - 128 bit not supported"
0x180025a40  mov     rcx, cs:gRasccpEtwContext
0x180025a47  mov     rax, cs:gRasccpTemplateFunc
0x180025a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a53  mov     r9d, cs:g_dwAllowPPTPWeakCrypto
0x180025a5a  mov     rdx, qword ptr cs:xmmword_18004D7A0
0x180025a61  mov     [rdi], esi
0x180025a63  mov     eax, [rbx+1B0h]
0x180025a69  test    al, al
0x180025a6b  jns     short loc_180025A87
0x180025a6d  test    bpl, bpl
0x180025a70  jns     short loc_180025A7B
0x180025a72  test    al, 30h
0x180025a74  jz      short loc_180025A87
0x180025a76  and     eax, 0FFFFFFCFh
0x180025a79  jmp     short loc_180025A7F
0x180025a7b  btr     eax, 7
0x180025a7f  mov     [rdi], esi
0x180025a81  mov     [rbx+1B0h], eax
0x180025a87  test    al, 20h
0x180025a89  jz      short loc_180025AEE
0x180025a8b  test    bpl, 20h
0x180025a8f  jz      short loc_180025AB6
0x180025a91  test    al, 10h
0x180025a93  jz      short loc_180025AEE
0x180025a95  and     eax, 0FFFFFFEFh
0x180025a98  mov     [rbx+1B0h], eax
0x180025a9e  mov     rax, qword ptr cs:xmmword_18004D7A0+8
0x180025aa5  test    rax, rax
0x180025aa8  jz      short loc_180025AEC
0x180025aaa  lea     r8, aNakAccepting40; "Nak - Accepting 40 bit"
0x180025ab1  mov     rdx, rax
0x180025ab4  jmp     short loc_180025ACB
0x180025ab6  and     eax, 0FFFFFFDFh
0x180025ab9  mov     [rbx+1B0h], eax
0x180025abf  test    rdx, rdx
0x180025ac2  jz      short loc_180025AEC
0x180025ac4  lea     r8, aNak40BitNotSup; "Nak - 40 bit not supported"
0x180025acb  mov     rcx, cs:gRasccpEtwContext
0x180025ad2  mov     rax, cs:gRasccpTemplateFunc
0x180025ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ade  mov     r9d, cs:g_dwAllowPPTPWeakCrypto
0x180025ae5  mov     rdx, qword ptr cs:xmmword_18004D7A0
0x180025aec  mov     [rdi], esi
0x180025aee  mov     r8d, [rbx+1B0h]
0x180025af5  test    r8b, 10h
0x180025af9  setnz   cl
0x180025afc  test    bpl, 10h
0x180025b00  setz    al
0x180025b03  test    al, cl
0x180025b05  jz      short loc_180025B41
0x180025b07  and     r8d, 0FFFFFFEFh
0x180025b0b  mov     [rbx+1B0h], r8d
0x180025b12  test    rdx, rdx
0x180025b15  jz      short loc_180025B3F
0x180025b17  mov     rcx, cs:gRasccpEtwContext
0x180025b1e  lea     r8, aNakLegacy40Bit; "Nak - legacy 40 bit not supported"
0x180025b25  mov     rax, cs:gRasccpTemplateFunc
0x180025b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b31  mov     rdx, qword ptr cs:xmmword_18004D7A0
0x180025b38  mov     r9d, cs:g_dwAllowPPTPWeakCrypto
0x180025b3f  mov     [rdi], esi
0x180025b41  mov     eax, [rbx+1B0h]
0x180025b47  test    r9d, r9d
0x180025b4a  jz      short loc_180025B50
0x180025b4c  test    al, 0F0h
0x180025b4e  jmp     short loc_180025B52
0x180025b50  test    al, 40h
0x180025b52  jnz     loc_180025C17
0x180025b58  mov     r8d, [r14+10h]
0x180025b5c  mov     ecx, eax
0x180025b5e  test    r8d, r8d
0x180025b61  jnz     short loc_180025B6C
0x180025b63  test    r12d, r12d
0x180025b66  jz      loc_180025C17
0x180025b6c  test    ebp, ebp
0x180025b6e  jz      loc_180025C17
0x180025b74  cmp     [rsp+58h+arg_20], r15d
0x180025b7c  jz      short loc_180025BFC
0x180025b7e  mov     eax, [r14+18h]
0x180025b82  mov     ecx, 20h ; ' '
0x180025b87  mov     [r14+1Ch], eax
0x180025b8b  lea     r10d, [rcx+60h]
0x180025b8f  test    eax, eax
0x180025b91  jnz     short loc_180025BA2
0x180025b93  mov     dword ptr [r14+18h], 40h ; '@'
0x180025b9b  mov     eax, 40h ; '@'
0x180025ba0  jmp     short loc_180025BEA
0x180025ba2  cmp     eax, 40h ; '@'
0x180025ba5  jnz     short loc_180025BB5
0x180025ba7  test    r9d, r9d
0x180025baa  jz      short loc_180025BDF
0x180025bac  mov     [r14+18h], r10d
0x180025bb0  mov     eax, r10d
0x180025bb3  jmp     short loc_180025BEA
0x180025bb5  cmp     eax, r10d
0x180025bb8  jnz     short loc_180025BC7
0x180025bba  test    r9d, r9d
0x180025bbd  jz      short loc_180025BDF
0x180025bbf  mov     [r14+18h], ecx
0x180025bc3  mov     eax, ecx
0x180025bc5  jmp     short loc_180025BEA
0x180025bc7  cmp     eax, ecx
0x180025bc9  jnz     short loc_180025BDF
0x180025bcb  test    r9d, r9d
0x180025bce  jz      short loc_180025BDF
0x180025bd0  mov     dword ptr [r14+18h], 10h
0x180025bd8  mov     eax, 10h
0x180025bdd  jmp     short loc_180025BEA
0x180025bdf  mov     [r14+18h], r15d
0x180025be3  test    r8d, r8d
0x180025be6  jz      short loc_180025BF4
0x180025be8  xor     eax, eax
0x180025bea  test    ebp, eax
0x180025bec  jz      short loc_180025B8F
0x180025bee  or      [rbx+1B0h], eax
0x180025bf4  mov     eax, [rbx+1B0h]
0x180025bfa  jmp     short loc_180025C15
0x180025bfc  test    r8d, r8d
0x180025bff  jz      short loc_180025C0B
0x180025c01  mov     eax, 2E6h
0x180025c06  jmp     loc_180025CA9
0x180025c0b  mov     eax, ecx
0x180025c0d  or      eax, ebp
0x180025c0f  mov     [rbx+1B0h], eax
0x180025c15  mov     [rdi], esi
0x180025c17  test    eax, 0FEFFFF0Eh
0x180025c1c  jz      short loc_180025C64
0x180025c1e  test    r9d, r9d
0x180025c21  jz      short loc_180025C2A
0x180025c23  and     eax, 10000F1h
0x180025c28  jmp     short loc_180025C2F
0x180025c2a  and     eax, 1000041h
0x180025c2f  mov     [rbx+1B0h], eax
0x180025c35  test    rdx, rdx
0x180025c38  jz      short loc_180025C62
0x180025c3a  mov     rcx, cs:gRasccpEtwContext
0x180025c41  lea     r8, aNakUnknownBits; "Nak - unknown bits"
0x180025c48  mov     rax, cs:gRasccpTemplateFunc
0x180025c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c54  mov     rdx, qword ptr cs:xmmword_18004D7A0
0x180025c5b  mov     r9d, cs:g_dwAllowPPTPWeakCrypto
0x180025c62  mov     [rdi], esi
0x180025c64  cmp     [rdi], esi
0x180025c66  jnz     short loc_180025CA6
0x180025c68  test    r9d, r9d
0x180025c6b  jz      short loc_180025C78
0x180025c6d  test    byte ptr [rbx+1B0h], 0F1h
0x180025c74  jz      short loc_180025C81
0x180025c76  jmp     short loc_180025CA6
0x180025c78  test    byte ptr [rbx+1B0h], 41h
0x180025c7f  jnz     short loc_180025CA6
0x180025c81  test    rdx, rdx
0x180025c84  jz      short loc_180025CA0
0x180025c86  mov     rcx, cs:gRasccpEtwContext
0x180025c8d  lea     r8, aRejNoBitsSuppo; "Rej - No bits supported"
0x180025c94  mov     rax, cs:gRasccpTemplateFunc
0x180025c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ca0  mov     dword ptr [rdi], 4
0x180025ca6  mov     eax, r15d
0x180025ca9  add     rsp, 20h
0x180025cad  pop     r15
0x180025caf  pop     r14
0x180025cb1  pop     r12
0x180025cb3  pop     rdi
0x180025cb4  pop     rsi
0x180025cb5  pop     rbp
0x180025cb6  pop     rbx
0x180025cb7  retn
0x180025cb9  cmp     al, 6
0x180025cbb  jnb     short loc_180025CC5
0x180025cbd  mov     r15d, 2D2h
0x180025cc3  jmp     short loc_180025CA6
0x180025cc5  cmp     [rcx+14h], r15d
0x180025cc9  jnz     short loc_180025CA0
0x180025ccb  cmp     [rcx+10h], r15d
0x180025ccf  jnz     short loc_180025CA0
0x180025cd1  cmp     [rdx+44h], r15b
0x180025cd5  jnz     short loc_180025CA0
0x180025cd7  mov     [rdx+1B8h], r15b
0x180025cde  movzx   ecx, word ptr [rdx+46h]
0x180025ce2  movups  xmm1, xmmword ptr [rdx+58h]
0x180025ce6  mov     eax, [rdx+68h]
0x180025ce9  mov     [rdx+1BAh], cx
0x180025cf0  add     rdx, 48h ; 'H'; Buf2
0x180025cf4  add     rcx, 2
0x180025cf8  movups  xmm0, xmmword ptr [rdx]
0x180025cfb  movups  xmmword ptr [rbx+1BCh], xmm0
0x180025d02  movups  xmmword ptr [rbx+1CCh], xmm1
0x180025d09  mov     [rbx+1DCh], eax
0x180025d0f  movzx   r8d, byte ptr [r8+1]
0x180025d14  cmp     r8, rcx
0x180025d17  jz      short loc_180025D21
0x180025d19  mov     dword ptr [rdi], 3
0x180025d1f  jmp     short loc_180025CA6
0x180025d21  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180025d25  lea     rcx, [r9+2]; Buf1
  ... truncated ...
```
