# UnCompactSubset1Font

- ea: `0x18000c874`
- end: `0x18000d100`
- name: `UnCompactSubset1Font`
- size: `2188`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009544`

## callees

- `0x18000c350`
- `0x18000c588`
- `0x18000c708`
- `0x18000c874`
- `0x18000d108`
- `0x18000f264`
- `0x18000f294`
- `0x180011538`
- `0x180011574`
- `0x18001986c`
- `0x180019a40`
- `0x180019c00`
- `0x18001a060`
- `0x18001a138`
- `0x18001a3bc`
- `0x18001a808`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall UnCompactSubset1Font(__int64 a1, __int64 a2, __int16 a3, __int64 a4, __int16 a5, int *a6)
{
  int v6; // r13d
  __int64 v8; // r15
  __int16 v9; // bx
  __int64 v10; // r8
  __int64 result; // rax
  int Generic; // eax
  int v13; // esi
  unsigned int v14; // r12d
  __int64 v15; // rdi
  unsigned int v16; // ebx
  unsigned __int16 i; // si
  unsigned __int16 v18; // r15
  unsigned __int16 v19; // bx
  __int64 v20; // rcx
  __int16 v21; // si
  _DWORD *v22; // rsi
  unsigned __int16 v23; // ax
  int *v24; // r15
  int v25; // r13d
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rsi
  __int64 v30; // rsi
  int *v31; // r13
  int v32; // esi
  int v33; // ecx
  unsigned __int16 v34; // si
  int v35; // r15d
  size_t Size; // [rsp+20h] [rbp-E0h]
  _WORD v37[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v38[2]; // [rsp+54h] [rbp-ACh] BYREF
  int v39; // [rsp+58h] [rbp-A8h] BYREF
  int v40; // [rsp+5Ch] [rbp-A4h] BYREF
  int v41; // [rsp+60h] [rbp-A0h]
  __int16 v42; // [rsp+64h] [rbp-9Ch]
  __int16 v43[2]; // [rsp+68h] [rbp-98h] BYREF
  __int16 v44; // [rsp+6Ch] [rbp-94h]
  __int16 v45[2]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v46; // [rsp+74h] [rbp-8Ch]
  int v47; // [rsp+78h] [rbp-88h]
  __int64 v48; // [rsp+80h] [rbp-80h]
  __int64 v49; // [rsp+88h] [rbp-78h]
  int v50[2]; // [rsp+90h] [rbp-70h]
  int *v51; // [rsp+98h] [rbp-68h]
  __int64 v52; // [rsp+A0h] [rbp-60h] BYREF
  int v53; // [rsp+A8h] [rbp-58h]
  __int128 v54; // [rsp+B0h] [rbp-50h] BYREF
  int v55; // [rsp+C0h] [rbp-40h]
  _OWORD v56[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v57; // [rsp+E8h] [rbp-18h]
  _OWORD v58[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v59; // [rsp+110h] [rbp+10h]
  _OWORD v60[2]; // [rsp+118h] [rbp+18h] BYREF
  int v61; // [rsp+138h] [rbp+38h]
  _OWORD v62[2]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v63[3]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v64; // [rsp+190h] [rbp+90h]

  v51 = a6;
  v46 = a3;
  v6 = 0;
  v48 = a4;
  *(_QWORD *)v50 = a1;
  v52 = 0;
  v53 = 0;
  v8 = a1;
  v38[0] = 0;
  v37[0] = 0;
  v9 = 0;
  memset(v58, 0, sizeof(v58));
  v59 = 0;
  v61 = 0;
  memset(v60, 0, sizeof(v60));
  v64 = 0;
  v55 = 0;
  memset(v62, 0, sizeof(v62));
  v57 = 0;
  memset(v63, 0, sizeof(v63));
  v54 = 0;
  memset(v56, 0, sizeof(v56));
  if ( !(unsigned int)GetGeneric(a1, v56, 1) )
    return 1033;
  LOWORD(v10) = 2;
  v43[0] = HIWORD(v57);
  Generic = GetGeneric(v8, v56, v10);
  v13 = *(_DWORD *)(v8 + 12);
  if ( Generic )
    v9 = HIWORD(v57);
  v45[0] = v9;
  result = ReadGeneric(v8, (unsigned int)&v52, 12, (unsigned int)&OFFSET_TABLE_CONTROL, v13, (__int64)v38);
  if ( !(_WORD)result )
  {
    v14 = WORD2(v52);
    v15 = Mem_Alloc(16LL * WORD2(v52));
    if ( !v15 )
      return 1005;
    v16 = v13 + v38[0];
    for ( i = 0; i < (unsigned __int16)v14; v16 += v38[0] )
    {
      v18 = ReadGeneric(v8, (unsigned int)v15 + 16 * i, 16, (unsigned int)&DIRECTORY_CONTROL, v16, (__int64)v38);
      if ( v18 )
      {
        Mem_Free(v15);
        return v18;
      }
      ++i;
      LODWORD(v8) = v50[0];
    }
    SortByOffset(v15, (unsigned __int16)v14);
    v39 = v16;
    v19 = ZeroLongWordAlign(a2, v16, &v39);
    if ( v19 )
      goto LABEL_73;
    v47 = 0;
    v42 = -1;
    LOWORD(v20) = 0;
    v44 = -1;
    v21 = 0;
    v41 = 0;
    if ( !(_WORD)v14 )
    {
LABEL_67:
      v31 = v51;
      *v51 = v39;
      v32 = *(_DWORD *)(a2 + 12);
      v19 = WriteGeneric(a2, (unsigned int)&v52, 12, (unsigned int)&OFFSET_TABLE_CONTROL, v32, (__int64)v37);
      if ( !v19 )
      {
        SortByTag(v15, (unsigned __int16)v14);
        v33 = v32 + v37[0];
        if ( (_WORD)v14 )
        {
          v34 = 0;
          v35 = v33;
          while ( 1 )
          {
            v19 = WriteGeneric(
                    a2,
                    (unsigned int)v15 + 16 * v34,
                    16,
                    (unsigned int)&DIRECTORY_CONTROL,
                    v33,
                    (__int64)v37);
            if ( v19 )
              break;
            ++v34;
            v33 = v35 + v37[0];
            v35 = v33;
            if ( v34 >= (unsigned __int16)v14 )
              goto LABEL_72;
          }
        }
        else
        {
LABEL_72:
          SetFileChecksum(a2, (unsigned int)*v31);
        }
      }
      goto LABEL_73;
    }
    while ( 1 )
    {
      v40 = 0;
      if ( !v21 )
        break;
      v6 = 0;
      v28 = (unsigned __int16)v20;
      v21 = 0;
      v47 = 0;
LABEL_59:
      v19 = CalcChecksum(
              a2,
              *(unsigned int *)(16 * v28 + v15 + 8),
              *(unsigned int *)(16 * v28 + v15 + 12),
              16 * v28 + v15 + 4);
      if ( v19 )
        goto LABEL_73;
      WORD1(v20) = HIWORD(v41);
      LODWORD(v8) = v50[0];
      LOWORD(v20) = v41 + 1;
      v41 = v20;
      if ( (unsigned __int16)v20 >= (unsigned __int16)v14 )
      {
        if ( v42 == -1
          || (HIWORD(v59) = v43[0],
              v29 = 16LL * v42,
              (v19 = WriteGeneric(
                       a2,
                       (unsigned int)v58,
                       36,
                       (unsigned int)HHEA_CONTROL,
                       *(_DWORD *)(v29 + v15 + 8),
                       (__int64)v37)) == 0)
          && (v19 = CalcChecksum(a2, *(unsigned int *)(v29 + v15 + 8), *(unsigned int *)(v29 + v15 + 12), v15 + v29 + 4)) == 0 )
        {
          if ( v44 == -1 )
            goto LABEL_67;
          HIWORD(v61) = v45[0];
          v30 = 16LL * v44;
          v19 = WriteGeneric(
                  a2,
                  (unsigned int)v60,
                  36,
                  (unsigned int)VHEA_CONTROL,
                  *(_DWORD *)(v30 + v15 + 8),
                  (__int64)v37);
          if ( !v19 )
          {
            v19 = CalcChecksum(a2, *(unsigned int *)(v30 + v15 + 8), *(unsigned int *)(v30 + v15 + 12), v15 + v30 + 4);
            if ( !v19 )
              goto LABEL_67;
          }
        }
LABEL_73:
        Mem_Free(v15);
        return v19;
      }
    }
    if ( !v46 )
      goto LABEL_47;
    v49 = (unsigned __int16)v20;
    v22 = (_DWORD *)(v15 + 16LL * (unsigned __int16)v20);
    if ( *v22 > 0x686D7478u )
    {
      if ( *v22 == 1819239265 )
      {
        v23 = UnCompactLOCA(v8, a2, v22[2], v39, a5, v46, v48, (__int64)&v40);
        goto LABEL_43;
      }
      if ( *v22 != 1835104368 )
      {
        if ( *v22 == 1986553185 )
        {
          v19 = ReadGeneric(v8, (unsigned int)v60, 36, (unsigned int)VHEA_CONTROL, v22[2], (__int64)v38);
          if ( v19 )
            goto LABEL_73;
          LOWORD(v20) = v41;
          v44 = v41;
          goto LABEL_47;
        }
        if ( *v22 != 1986884728 )
          goto LABEL_47;
        v23 = UnCompactXmtx(v8, a2, v22[2], v39, a5, v46, v48, (__int64)v45, (__int64)&v40);
        goto LABEL_43;
      }
      v19 = ReadGeneric(v8, (unsigned int)v62, 32, (unsigned int)MAXP_CONTROL, v22[2], (__int64)v38);
      if ( v19 )
        goto LABEL_73;
      WORD2(v62[0]) = a5;
      v23 = WriteGeneric(a2, (unsigned int)v62, 32, (unsigned int)MAXP_CONTROL, v39, (__int64)v37);
    }
    else
    {
      if ( *v22 == 1752003704 )
      {
        v23 = UnCompactXmtx(v8, a2, v22[2], v39, a5, v46, v48, (__int64)v43, (__int64)&v40);
        goto LABEL_43;
      }
      if ( *v22 == 1280594760 )
      {
        v23 = UnCompactLTSH(v8, a2, v22[2], v39, a5, v46, v48, (__int64)&v40);
        goto LABEL_43;
      }
      if ( *v22 != 1685353574 )
      {
        if ( *v22 != 1751412088 )
        {
          if ( *v22 != 1751474532 )
          {
            if ( *v22 == 1751672161 )
            {
              v19 = ReadGeneric(v8, (unsigned int)v58, 36, (unsigned int)HHEA_CONTROL, v22[2], (__int64)v38);
              if ( v19 )
                goto LABEL_73;
              LOWORD(v20) = v41;
              v42 = v41;
            }
            goto LABEL_47;
          }
          v19 = ReadGeneric(v8, (unsigned int)v63, 54, (unsigned int)HEAD_CONTROL, v22[2], (__int64)v38);
          if ( v19 )
            goto LABEL_73;
          DWORD2(v63[0]) = 0;
          v23 = WriteGeneric(a2, (unsigned int)v63, 54, (unsigned int)HEAD_CONTROL, v39, (__int64)v37);
          goto LABEL_27;
        }
        v23 = UnCompactHDMX(v8, a2, v22[2], v39, a5, v46, v48, (__int64)&v40);
LABEL_43:
        v6 = v40;
        goto LABEL_44;
      }
      v19 = ReadGeneric(v8, (unsigned int)&v54, 18, (unsigned int)&DTTF_HEADER_CONTROL, v22[2], (__int64)v38);
      if ( v19 )
        goto LABEL_73;
      LOWORD(v55) = 0;
      WORD6(v54) = 3;
      v23 = WriteGeneric(a2, (unsigned int)&v54, 18, (unsigned int)&DTTF_HEADER_CONTROL, v39, (__int64)v37);
    }
LABEL_27:
    v6 = v37[0];
LABEL_44:
    v19 = v23;
    if ( v23 )
      goto LABEL_73;
    if ( v6 )
    {
      v20 = v49;
      goto LABEL_51;
    }
    LOWORD(v20) = v41;
LABEL_47:
    v20 = (unsigned __int16)v20;
    v49 = (unsigned __int16)v20;
    v22 = (_DWORD *)(v15 + 16LL * (unsigned __int16)v20);
    v24 = v22 + 3;
    if ( v22[3] )
    {
      v25 = v39;
      LODWORD(Size) = v22[3];
      v19 = CopyBlockOver(a2, v50[0], v39, v22[2], Size);
      if ( v19 )
        goto LABEL_73;
      goto LABEL_52;
    }
LABEL_51:
    v24 = v22 + 3;
    v49 = v20;
    v22[3] = v6;
    v25 = v39;
LABEL_52:
    if ( (unsigned int)(unsigned __int16)v41 + 1 < v14 )
    {
      v26 = 2 * ((unsigned __int16)v41 + 1LL);
      if ( v22[2] == *(_DWORD *)(v15 + 16 * ((unsigned __int16)v41 + 1LL) + 8) )
      {
        v27 = *v24;
        if ( *v24 )
        {
          LOWORD(v47) = 1;
          *(_DWORD *)(v15 + 16 * ((unsigned __int16)v41 + 1LL) + 8) = v25;
          *(_DWORD *)(v15 + 8 * v26 + 12) = v27;
        }
      }
    }
    v22[2] = v25;
    v39 = *v24 + v25;
    v6 = 0;
    v19 = ZeroLongWordAlign(a2, (unsigned int)v39, &v39);
    if ( v19 )
      goto LABEL_73;
    v28 = v49;
    v21 = v47;
    goto LABEL_59;
  }
  return result;
}

```

## disassembly

```asm
0x18000c874  mov     [rsp-8+arg_10], rbx
0x18000c879  push    rbp
0x18000c87a  push    rsi
0x18000c87b  push    rdi
0x18000c87c  push    r12
0x18000c87e  push    r13
0x18000c880  push    r14
0x18000c882  push    r15
0x18000c884  lea     rbp, [rsp-0A0h]
0x18000c88c  sub     rsp, 1A0h
0x18000c893  mov     rax, cs:__security_cookie
0x18000c89a  xor     rax, rsp
0x18000c89d  mov     [rbp+0D0h+var_38], rax
0x18000c8a4  mov     rax, [rbp+0D0h+arg_28]
0x18000c8ab  xorps   xmm1, xmm1
0x18000c8ae  xorps   xmm0, xmm0
0x18000c8b1  mov     [rbp+0D0h+var_138], rax
0x18000c8b5  xor     eax, eax
0x18000c8b7  mov     [rsp+1D0h+var_15C], r8w
0x18000c8bd  xor     r13d, r13d
0x18000c8c0  mov     [rbp+0D0h+var_150], r9
0x18000c8c4  mov     r14, rdx
0x18000c8c7  mov     qword ptr [rbp+0D0h+var_140], rcx
0x18000c8cb  lea     rdx, [rbp+0D0h+var_108]
0x18000c8cf  mov     [rbp+0D0h+var_130], rax
0x18000c8d3  lea     r8d, [rax+1]
0x18000c8d7  mov     [rbp+0D0h+var_128], eax
0x18000c8da  mov     r15, rcx
0x18000c8dd  mov     [rsp+1D0h+var_17C], r13w
0x18000c8e3  mov     [rsp+1D0h+var_180], r13w
0x18000c8e9  mov     ebx, r13d
0x18000c8ec  movups  [rbp+0D0h+var_E0], xmm0
0x18000c8f0  mov     [rbp+0D0h+var_C0], eax
0x18000c8f3  movups  [rbp+0D0h+var_D0], xmm0
0x18000c8f7  mov     [rbp+0D0h+var_98], eax
0x18000c8fa  movups  [rbp+0D0h+var_B8], xmm1
0x18000c8fe  mov     [rbp+0D0h+var_40], rax
0x18000c905  movups  [rbp+0D0h+var_A8], xmm1
0x18000c909  mov     [rbp+0D0h+var_110], eax
0x18000c90c  movups  [rbp+0D0h+var_90], xmm0
0x18000c910  mov     [rbp+0D0h+var_E8], eax
0x18000c913  movups  [rbp+0D0h+var_80], xmm0
0x18000c917  movups  [rbp+0D0h+var_70], xmm1
0x18000c91b  movups  [rbp+0D0h+var_60], xmm1
0x18000c91f  movups  [rbp+0D0h+var_50], xmm1
0x18000c926  movups  [rbp+0D0h+var_120], xmm0
0x18000c92a  movups  [rbp+0D0h+var_108], xmm1
0x18000c92e  movups  [rbp+0D0h+var_F8], xmm1
0x18000c932  call    GetGeneric
0x18000c937  test    eax, eax
0x18000c939  jnz     short loc_18000C945
0x18000c93b  mov     eax, 409h
0x18000c940  jmp     loc_18000D0D6
0x18000c945  movzx   eax, word ptr [rbp+0D0h+var_E8+2]
0x18000c949  lea     rdx, [rbp+0D0h+var_108]
0x18000c94d  mov     r8w, 2
0x18000c952  mov     [rsp+1D0h+var_168], ax
0x18000c957  mov     rcx, r15
0x18000c95a  call    GetGeneric
0x18000c95f  mov     esi, [r15+0Ch]
0x18000c963  lea     r9, OFFSET_TABLE_CONTROL
0x18000c96a  test    eax, eax
0x18000c96c  lea     rdx, [rbp+0D0h+var_130]
0x18000c970  lea     rax, [rsp+1D0h+var_17C]
0x18000c975  mov     r8d, 0Ch
0x18000c97b  cmovnz  bx, word ptr [rbp+0D0h+var_E8+2]
0x18000c980  mov     rcx, r15
0x18000c983  mov     [rsp+1D0h+var_1A8], rax
0x18000c988  mov     [rsp+1D0h+var_160], bx
0x18000c98d  mov     dword ptr [rsp+1D0h+Size], esi
0x18000c991  call    ReadGeneric
0x18000c996  test    ax, ax
0x18000c999  jnz     loc_18000D0D6
0x18000c99f  movzx   r12d, word ptr [rbp+0D0h+var_130+4]
0x18000c9a4  mov     ecx, r12d
0x18000c9a7  shl     rcx, 4; Size
0x18000c9ab  call    Mem_Alloc
0x18000c9b0  mov     rdi, rax
0x18000c9b3  test    rax, rax
0x18000c9b6  jnz     short loc_18000C9C2
0x18000c9b8  mov     eax, 3EDh
0x18000c9bd  jmp     loc_18000D0D6
0x18000c9c2  movzx   ebx, [rsp+1D0h+var_17C]
0x18000c9c7  add     ebx, esi
0x18000c9c9  mov     esi, r13d
0x18000c9cc  cmp     r13w, r12w
0x18000c9d0  jnb     short loc_18000CA20
0x18000c9d2  lea     rax, [rsp+1D0h+var_17C]
0x18000c9d7  movzx   edx, si
0x18000c9da  shl     rdx, 4
0x18000c9de  lea     r9, DIRECTORY_CONTROL
0x18000c9e5  mov     [rsp+1D0h+var_1A8], rax
0x18000c9ea  add     rdx, rdi
0x18000c9ed  mov     r8d, 10h
0x18000c9f3  mov     dword ptr [rsp+1D0h+Size], ebx
0x18000c9f7  mov     rcx, r15
0x18000c9fa  call    ReadGeneric
0x18000c9ff  movzx   r15d, ax
0x18000ca03  test    ax, ax
0x18000ca06  jnz     loc_18000CB29
0x18000ca0c  movzx   eax, [rsp+1D0h+var_17C]
0x18000ca11  inc     si
0x18000ca14  mov     r15, qword ptr [rbp+0D0h+var_140]
0x18000ca18  add     ebx, eax
0x18000ca1a  cmp     si, r12w
0x18000ca1e  jb      short loc_18000C9D2
0x18000ca20  movzx   edx, r12w
0x18000ca24  mov     rcx, rdi
0x18000ca27  call    SortByOffset
0x18000ca2c  lea     r8, [rsp+1D0h+var_178]
0x18000ca31  mov     [rsp+1D0h+var_178], ebx
0x18000ca35  mov     edx, ebx
0x18000ca37  mov     rcx, r14
0x18000ca3a  call    ZeroLongWordAlign
0x18000ca3f  movzx   ebx, ax
0x18000ca42  test    ax, ax
0x18000ca45  jnz     loc_18000D0CB
0x18000ca4b  or      eax, 0FFFFFFFFh
0x18000ca4e  mov     [rsp+1D0h+var_158], r13d
0x18000ca53  mov     [rsp+1D0h+var_16C], ax
0x18000ca58  mov     ecx, r13d
0x18000ca5b  mov     [rsp+1D0h+var_164], ax
0x18000ca60  mov     esi, r13d
0x18000ca63  mov     [rsp+1D0h+var_170], ecx
0x18000ca67  cmp     r13w, r12w
0x18000ca6b  jnb     loc_18000D015
0x18000ca71  mov     [rsp+1D0h+var_174], r13d
0x18000ca76  test    si, si
0x18000ca79  jnz     loc_18000CED9
0x18000ca7f  movzx   edx, [rsp+1D0h+var_15C]
0x18000ca84  test    dx, dx
0x18000ca87  jz      loc_18000CE13
0x18000ca8d  movzx   eax, cx
0x18000ca90  mov     [rbp+0D0h+var_148], rax
0x18000ca94  add     rax, rax
0x18000ca97  lea     rsi, [rdi+rax*8]
0x18000ca9b  cmp     dword ptr [rsi], 686D7478h
0x18000caa1  ja      loc_18000CCD9
0x18000caa7  jz      loc_18000CC92
0x18000caad  cmp     dword ptr [rsi], 4C545348h
0x18000cab3  jz      loc_18000CC55
0x18000cab9  cmp     dword ptr [rsi], 64747466h
0x18000cabf  jz      loc_18000CBE8
0x18000cac5  cmp     dword ptr [rsi], 68646D78h
0x18000cacb  jz      loc_18000CBAB
0x18000cad1  cmp     dword ptr [rsi], 68656164h
0x18000cad7  jz      short loc_18000CB3A
0x18000cad9  cmp     dword ptr [rsi], 68686561h
0x18000cadf  jnz     loc_18000CE13
0x18000cae5  lea     rax, [rsp+1D0h+var_17C]
0x18000caea  mov     r8d, 24h ; '$'
0x18000caf0  mov     [rsp+1D0h+var_1A8], rax
0x18000caf5  lea     r9, HHEA_CONTROL
0x18000cafc  mov     eax, [rsi+8]
0x18000caff  lea     rdx, [rbp+0D0h+var_E0]
0x18000cb03  mov     rcx, r15
0x18000cb06  mov     dword ptr [rsp+1D0h+Size], eax
0x18000cb0a  call    ReadGeneric
0x18000cb0f  movzx   ebx, ax
0x18000cb12  test    ax, ax
0x18000cb15  jnz     loc_18000D0CB
0x18000cb1b  mov     ecx, [rsp+1D0h+var_170]
0x18000cb1f  mov     [rsp+1D0h+var_16C], cx
0x18000cb24  jmp     loc_18000CE13
0x18000cb29  mov     rcx, rdi
0x18000cb2c  call    Mem_Free
0x18000cb31  movzx   eax, r15w
0x18000cb35  jmp     loc_18000D0D6
0x18000cb3a  lea     rax, [rsp+1D0h+var_17C]
0x18000cb3f  mov     r8d, 36h ; '6'
0x18000cb45  mov     [rsp+1D0h+var_1A8], rax
0x18000cb4a  lea     r9, HEAD_CONTROL
0x18000cb51  mov     eax, [rsi+8]
0x18000cb54  lea     rdx, [rbp+0D0h+var_70]
0x18000cb58  mov     rcx, r15
0x18000cb5b  mov     dword ptr [rsp+1D0h+Size], eax
0x18000cb5f  call    ReadGeneric
0x18000cb64  movzx   ebx, ax
0x18000cb67  xor     eax, eax
0x18000cb69  test    bx, bx
0x18000cb6c  jnz     loc_18000D0CB
0x18000cb72  mov     r9d, [rsp+1D0h+var_178]
0x18000cb77  lea     r8d, [rax+36h]
0x18000cb7b  mov     dword ptr [rbp+0D0h+var_70+8], eax
0x18000cb7e  lea     rdx, [rbp+0D0h+var_70]
0x18000cb82  lea     rax, [rsp+1D0h+var_180]
0x18000cb87  mov     [rsp+1D0h+var_1A8], rax
0x18000cb8c  mov     dword ptr [rsp+1D0h+Size], r9d
0x18000cb91  lea     r9, HEAD_CONTROL
0x18000cb98  mov     rcx, r14
0x18000cb9b  call    WriteGeneric
0x18000cba0  movzx   r13d, [rsp+1D0h+var_180]
0x18000cba6  jmp     loc_18000CDFE
0x18000cbab  mov     r9d, [rsp+1D0h+var_178]
0x18000cbb0  lea     rax, [rsp+1D0h+var_174]
0x18000cbb5  mov     r8d, [rsi+8]
0x18000cbb9  mov     rcx, r15
0x18000cbbc  mov     [rsp+1D0h+var_198], rax
0x18000cbc1  mov     rax, [rbp+0D0h+var_150]
0x18000cbc5  mov     [rsp+1D0h+var_1A0], rax
0x18000cbca  movzx   eax, [rbp+0D0h+arg_20]
0x18000cbd1  mov     word ptr [rsp+1D0h+var_1A8], dx
0x18000cbd6  mov     rdx, r14
0x18000cbd9  mov     word ptr [rsp+1D0h+Size], ax
0x18000cbde  call    UnCompactHDMX
0x18000cbe3  jmp     loc_18000CDF9
0x18000cbe8  lea     rax, [rsp+1D0h+var_17C]
0x18000cbed  mov     r8d, 12h
0x18000cbf3  mov     [rsp+1D0h+var_1A8], rax
0x18000cbf8  lea     r9, DTTF_HEADER_CONTROL
0x18000cbff  mov     eax, [rsi+8]
0x18000cc02  lea     rdx, [rbp+0D0h+var_120]
0x18000cc06  mov     rcx, r15
0x18000cc09  mov     dword ptr [rsp+1D0h+Size], eax
0x18000cc0d  call    ReadGeneric
0x18000cc12  movzx   ebx, ax
0x18000cc15  xor     eax, eax
0x18000cc17  test    bx, bx
0x18000cc1a  jnz     loc_18000D0CB
0x18000cc20  mov     r9d, [rsp+1D0h+var_178]
0x18000cc25  lea     rdx, [rbp+0D0h+var_120]
0x18000cc29  mov     word ptr [rbp+0D0h+var_110], ax
0x18000cc2d  mov     eax, 3
0x18000cc32  mov     word ptr [rbp+0D0h+var_120+0Ch], ax
0x18000cc36  lea     r8d, [rax+0Fh]
0x18000cc3a  lea     rax, [rsp+1D0h+var_180]
0x18000cc3f  mov     [rsp+1D0h+var_1A8], rax
0x18000cc44  mov     dword ptr [rsp+1D0h+Size], r9d
0x18000cc49  lea     r9, DTTF_HEADER_CONTROL
0x18000cc50  jmp     loc_18000CB98
0x18000cc55  mov     r9d, [rsp+1D0h+var_178]
0x18000cc5a  lea     rax, [rsp+1D0h+var_174]
0x18000cc5f  mov     r8d, [rsi+8]
0x18000cc63  mov     rcx, r15
0x18000cc66  mov     [rsp+1D0h+var_198], rax
0x18000cc6b  mov     rax, [rbp+0D0h+var_150]
0x18000cc6f  mov     [rsp+1D0h+var_1A0], rax
0x18000cc74  movzx   eax, [rbp+0D0h+arg_20]
0x18000cc7b  mov     word ptr [rsp+1D0h+var_1A8], dx
0x18000cc80  mov     rdx, r14
0x18000cc83  mov     word ptr [rsp+1D0h+Size], ax
0x18000cc88  call    UnCompactLTSH
0x18000cc8d  jmp     loc_18000CDF9
0x18000cc92  lea     rax, [rsp+1D0h+var_174]
0x18000cc97  mov     [rsp+1D0h+var_190], rax
0x18000cc9c  lea     rax, [rsp+1D0h+var_168]
0x18000cca1  mov     r9d, [rsp+1D0h+var_178]
0x18000cca6  mov     rcx, r15
0x18000cca9  mov     r8d, [rsi+8]
0x18000ccad  mov     [rsp+1D0h+var_198], rax
0x18000ccb2  mov     rax, [rbp+0D0h+var_150]
0x18000ccb6  mov     [rsp+1D0h+var_1A0], rax
0x18000ccbb  movzx   eax, [rbp+0D0h+arg_20]
0x18000ccc2  mov     word ptr [rsp+1D0h+var_1A8], dx
0x18000ccc7  mov     rdx, r14
0x18000ccca  mov     word ptr [rsp+1D0h+Size], ax
0x18000cccf  call    UnCompactXmtx
0x18000ccd4  jmp     loc_18000CDF9
0x18000ccd9  cmp     dword ptr [rsi], 6C6F6361h
0x18000ccdf  jz      loc_18000CDC1
0x18000cce5  cmp     dword ptr [rsi], 6D617870h
0x18000cceb  jz      short loc_18000CD56
0x18000cced  cmp     dword ptr [rsi], 76686561h
0x18000ccf3  jz      short loc_18000CD12
0x18000ccf5  cmp     dword ptr [rsi], 766D7478h
0x18000ccfb  jnz     loc_18000CE13
0x18000cd01  lea     rax, [rsp+1D0h+var_174]
0x18000cd06  mov     [rsp+1D0h+var_190], rax
0x18000cd0b  lea     rax, [rsp+1D0h+var_160]
0x18000cd10  jmp     short loc_18000CCA1
0x18000cd12  lea     rax, [rsp+1D0h+var_17C]
0x18000cd17  mov     r8d, 24h ; '$'
0x18000cd1d  mov     [rsp+1D0h+var_1A8], rax
0x18000cd22  lea     r9, VHEA_CONTROL
0x18000cd29  mov     eax, [rsi+8]
0x18000cd2c  lea     rdx, [rbp+0D0h+var_B8]
0x18000cd30  mov     rcx, r15
0x18000cd33  mov     dword ptr [rsp+1D0h+Size], eax
0x18000cd37  call    ReadGeneric
0x18000cd3c  movzx   ebx, ax
0x18000cd3f  test    ax, ax
0x18000cd42  jnz     loc_18000D0CB
0x18000cd48  mov     ecx, [rsp+1D0h+var_170]
0x18000cd4c  mov     [rsp+1D0h+var_164], cx
0x18000cd51  jmp     loc_18000CE13
0x18000cd56  lea     rax, [rsp+1D0h+var_17C]
0x18000cd5b  mov     r8d, 20h ; ' '
0x18000cd61  mov     [rsp+1D0h+var_1A8], rax
0x18000cd66  lea     r9, MAXP_CONTROL
0x18000cd6d  mov     eax, [rsi+8]
0x18000cd70  lea     rdx, [rbp+0D0h+var_90]
0x18000cd74  mov     rcx, r15
0x18000cd77  mov     dword ptr [rsp+1D0h+Size], eax
0x18000cd7b  call    ReadGeneric
0x18000cd80  movzx   ebx, ax
0x18000cd83  test    ax, ax
0x18000cd86  jnz     loc_18000D0CB
0x18000cd8c  movzx   eax, [rbp+0D0h+arg_20]
0x18000cd93  lea     rdx, [rbp+0D0h+var_90]
0x18000cd97  mov     r9d, [rsp+1D0h+var_178]
  ... truncated ...
```
