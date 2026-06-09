# Pku2uVerifyApReply(_PKU2U_CONTEXT *,uchar *,ulong)

- ea: `0x18000f100`
- end: `0x18000fb94`
- name: `?Pku2uVerifyApReply@@YAJPEAU_PKU2U_CONTEXT@@PEAEK@Z`
- size: `2708`
- prototype: `__int64 __fastcall(struct _PKU2U_CONTEXT *, unsigned __int8 *, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b990`
- `0x18001cc90`

## callees

- `0x180007dc8`
- `0x18000f100`
- `0x180015190`
- `0x180016a10`
- `0x180017940`
- `0x18001a1d0`
- `0x180023cb8`
- `0x180023ce0`
- `0x180023d9c`
- `0x18002b454`
- `0x18002b744`
- `0x180031d8c`
- `0x180031e4c`
- `0x180044f80`
- `0x180046010`

## import_xrefs

- `MSASN1!ASN1_CreateDecoder` at `0x18000f2c6`
- `MSASN1!ASN1_CreateDecoder` at `0x18000f64a`
- `MSASN1!ASN1_CreateDecoder` at `0x18000f2c6`
- `MSASN1!ASN1_CreateDecoder` at `0x18000f64a`
- `MSASN1!ASN1_CloseDecoder` at `0x18000f458`
- `MSASN1!ASN1_CloseDecoder` at `0x18000f7b3`
- `MSASN1!ASN1_CloseDecoder` at `0x18000f458`
- `MSASN1!ASN1_CloseDecoder` at `0x18000f7b3`
- `MSASN1!ASN1_CreateModule` at `0x18000f29e`
- `MSASN1!ASN1_CreateModule` at `0x18000f622`
- `MSASN1!ASN1_CreateModule` at `0x18000f29e`
- `MSASN1!ASN1_CreateModule` at `0x18000f622`
- `MSASN1!ASN1_Decode` at `0x18000f367`
- `MSASN1!ASN1_Decode` at `0x18000f6e0`
- `MSASN1!ASN1_Decode` at `0x18000f367`
- `MSASN1!ASN1_Decode` at `0x18000f6e0`
- `cryptdll!CDLocateCSystem` at `0x18000f507`
- `cryptdll!CDLocateCSystem` at `0x18000f507`

## string_xrefs

- `0x18000f4a7`: `onecore\ds\security\protocols\pku2u\tick.cxx`
- `0x18000f9f7`: `onecore\ds\security\protocols\pku2u\tick.cxx`
- `0x18000fa3a`: `onecore\ds\security\protocols\pku2u\tick.cxx`
- `0x18000fa8c`: `onecore\ds\security\protocols\pku2u\tick.cxx`
- `0x18000fb12`: `onecore\ds\security\protocols\pku2u\tick.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uVerifyApReply(struct _PKU2U_CONTEXT *a1, unsigned __int8 *a2, int a3)
{
  int v4; // r8d
  int v5; // r9d
  int v6; // ebx
  unsigned __int8 *v7; // rdx
  unsigned __int8 v8; // r9
  int i; // ecx
  int v10; // eax
  int v11; // ebx
  int v12; // ebx
  __int64 v13; // rdi
  int v14; // ebx
  unsigned __int8 *v15; // r15
  __int64 Module; // rax
  unsigned int v17; // eax
  PVOID *v18; // r10
  int v19; // edi
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // r12d
  unsigned int v23; // edi
  __int64 v24; // rcx
  _DWORD *v25; // rbx
  bool v26; // zf
  char *v27; // rdi
  __int64 v28; // rcx
  char *v29; // r15
  __int64 v30; // r14
  __int64 v31; // rdx
  int v32; // ebx
  int v33; // r14d
  __int64 v34; // rdi
  __int64 v35; // rax
  unsigned int v36; // eax
  PVOID *v37; // r10
  int v38; // ebx
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // r8
  unsigned int v42; // edi
  __int64 v43; // r9
  _OWORD *v44; // rdi
  int v45; // eax
  char v46; // dl
  unsigned int v47; // r8d
  __int64 v48; // rax
  __int64 v49; // xmm1_8
  struct KERB_ENCRYPTION_KEY *v50; // rdx
  int v51; // eax
  int v52; // ecx
  int v53; // eax
  unsigned __int8 *v55; // [rsp+20h] [rbp-50h]
  __int64 v56; // [rsp+50h] [rbp-20h] BYREF
  __int64 v57; // [rsp+58h] [rbp-18h] BYREF
  __int64 v58; // [rsp+60h] [rbp-10h] BYREF
  union _LARGE_INTEGER Time; // [rsp+68h] [rbp-8h] BYREF
  void *v60; // [rsp+B8h] [rbp+48h] BYREF
  void *v61; // [rsp+C8h] [rbp+58h] BYREF

  v4 = a3 - 1;
  v61 = 0;
  v60 = 0;
  Time.QuadPart = 0;
  if ( v4 < 0 || *a2 != 96 || v4 < 1 )
    return 280;
  v5 = a2[1];
  v6 = v4 - 1;
  v7 = a2 + 2;
  if ( (v5 & 0x80u) == 0 )
  {
    i = v5;
  }
  else
  {
    v8 = v5 & 0x7F;
    if ( v8 + 1 > v6 || v8 > 4u )
      return 280;
    for ( i = 0; v8; --v8 )
    {
      v10 = *v7;
      --v6;
      ++v7;
      i = v10 + (i << 8);
    }
  }
  if ( i > v6 )
    return 280;
  if ( i < 0 )
    return 280;
  if ( i != v6 )
    return 280;
  v11 = v6 - 1;
  if ( v11 < 0 )
    return 280;
  if ( *v7 != 6 )
    return 280;
  v12 = v11 - 1;
  if ( v12 < 0 )
    return 280;
  v13 = v7[1];
  v14 = v12 - v13;
  if ( v14 < 0 )
    return 280;
  if ( (_DWORD)v13 != (_DWORD)pku2u_global_oids )
    return 280;
  v15 = v7 + 2;
  if ( memcmp_0(v7 + 2, Src, v7[1]) || v14 - 2 < 0 || v15[v13] != 2 || v15[v13 + 1] )
    return 280;
  v56 = 0;
  if ( v14 == 2 || !&v15[v13 + 2] )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    v19 = 60;
    goto LABEL_157;
  }
  if ( fKRB5ModuleStarted )
  {
    Module = PKU2UMSG_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               49,
               off_180047350,
               off_1800471C0,
               off_180047030,
               qword_180049F80,
               846556016);
    PKU2UMSG_Module = Module;
  }
  v17 = ASN1_CreateDecoder(Module, &v56, 0, 0, 0);
  if ( v17 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v17);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
      {
        WPP_SF_d(v18[2], 80, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, 60);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    v19 = 60;
LABEL_157:
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 )
      WPP_SF_sd(
        (unsigned int)v18[2],
        37,
        (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
        209);
    v52 = v19;
    goto LABEL_161;
  }
  v55 = &v15[v13 + 2];
  v19 = 0;
  v61 = 0;
  v20 = ASN1_Decode(v56, &v61, 36, 8, v55, v14 - 2);
  v21 = v20;
  if ( v20 >= 0 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    v22 = 60;
  }
  else
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)v20);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    v22 = 60;
    if ( v21 == -1009 || v21 == -1002 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 4) != 0 )
      {
        WPP_SF_d(v18[2], 82, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, 36);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      v19 = -2147483647;
    }
    else
    {
      if ( v21 != -1011 && v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
      {
        WPP_SF_d(v18[2], 83, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v21);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      v19 = 60;
    }
    v61 = 0;
  }
  if ( v56 )
  {
    ASN1_CloseDecoder();
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v19 )
    goto LABEL_157;
  if ( *(_QWORD *)v61 != 0xF00000005LL )
  {
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
    {
      WPP_SF_ddsd(
        (unsigned int)v18[2],
        38,
        (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        *(_DWORD *)v61,
        *((_DWORD *)v61 + 1),
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
        218);
      v23 = -1073741715;
      goto LABEL_163;
    }
    goto LABEL_62;
  }
  if ( *((_DWORD *)a1 + 14) && !*((_QWORD *)a1 + 22) )
  {
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
      WPP_SF_sd(
        (unsigned int)v18[2],
        39,
        (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
        225);
    goto LABEL_62;
  }
  v24 = *((_QWORD *)a1 + 22);
  v25 = v61;
  v26 = v24 == 0;
  v27 = (char *)(v24 + 56);
  v28 = *((unsigned int *)v61 + 3);
  v29 = (char *)v61 + 24;
  v30 = *((_QWORD *)v61 + 4);
  if ( v26 )
    v27 = (char *)a1 + 248;
  v56 = 0;
  v57 = 0;
  if ( (int)CDLocateCSystem(v28, &v56) < 0 )
  {
    v22 = 14;
    goto LABEL_144;
  }
  v31 = *((unsigned int *)v27 + 2);
  if ( *(_DWORD *)(v56 + 12) != (_DWORD)v31 )
    goto LABEL_143;
  if ( !v25[6]
    || !*((_QWORD *)v25 + 4)
    || (*(int (__fastcall **)(_QWORD, __int64, __int64, __int64 *))(v56 + 40))(*((_QWORD *)v27 + 2), v31, 12, &v57) < 0 )
  {
    goto LABEL_144;
  }
  v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, char *))(v56 + 56))(
          v57,
          *((_QWORD *)v25 + 4),
          (unsigned int)v25[6],
          v30,
          v29);
  (*(void (__fastcall **)(__int64 *))(v56 + 64))(&v57);
  if ( v32 < 0 )
  {
LABEL_143:
    v22 = 41;
LABEL_144:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        v22,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
        244);
    v53 = -1073741670;
    if ( v22 != 60 )
      v53 = -1073741715;
    goto LABEL_162;
  }
  v58 = 0;
  v33 = *((_DWORD *)v61 + 6);
  if ( !v33 || (v34 = *((_QWORD *)v61 + 4)) == 0 )
  {
    v37 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_138;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids);
LABEL_137:
    v37 = (PVOID *)WPP_GLOBAL_Control;
LABEL_138:
    v38 = 60;
LABEL_139:
    if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 )
      WPP_SF_sd(
        (unsigned int)v37[2],
        41,
        (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
        12);
    v52 = v38;
    goto LABEL_161;
  }
  if ( fKRB5ModuleStarted )
  {
    v35 = PKU2UMSG_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    v35 = ASN1_CreateModule(
            0x10000,
            1024,
            4096,
            49,
            off_180047350,
            off_1800471C0,
            off_180047030,
            qword_180049F80,
            846556016);
    PKU2UMSG_Module = v35;
  }
  v36 = ASN1_CreateDecoder(v35, &v58, 0, 0, 0);
  if ( v36 )
  {
    v37 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_138;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v36);
      v37 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v37 == &WPP_GLOBAL_Control || (*((_BYTE *)v37 + 28) & 1) == 0 )
      goto LABEL_138;
    WPP_SF_d(v37[2], 80, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, 60);
    goto LABEL_137;
  }
  v38 = 0;
  v60 = 0;
  v39 = ASN1_Decode(v58, &v60, 37, 8, v34, v33);
  v42 = v39;
  if ( v39 >= 0 )
  {
    v37 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v37 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)v39);
      v37 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v42 == -1009 || v42 == -1002 )
    {
      if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 4) != 0 )
      {
        WPP_SF_d(v37[2], 82, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, 37);
        v37 = (PVOID *)WPP_GLOBAL_Control;
      }
      v38 = -2147483647;
    }
    else
    {
      if ( v42 != -1011 && v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 )
      {
        WPP_SF_d(v37[2], 83, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v42);
        v37 = (PVOID *)WPP_GLOBAL_Control;
      }
      v38 = 60;
    }
    v60 = 0;
  }
  if ( v58 )
  {
    ASN1_CloseDecoder();
    v37 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v38 )
    goto LABEL_139;
  if ( (*((_BYTE *)a1 + 40) & 2) != 0 )
  {
    KerbConvertGeneralizedTimeToLargeInt(
      &Time,
      (struct tagASN1generalizedtime_t *)((char *)v60 + 2),
      *((_DWORD *)v60 + 4));
    if ( *((_QWORD *)a1 + 35) != Time.QuadPart )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids);
      v23 = -1073741117;
      goto LABEL_163;
    }
    v37 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (*(_BYTE *)v60 & 0x40) == 0 )
  {
    *((_QWORD *)a1 + 37) = 0;
    goto LABEL_121;
  }
  if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 4) != 0 )
    WPP_SF_DDD(v37[2], v40, v41, *((unsigned int *)v60 + 12), *((_DWORD *)a1 + 72), *((_DWORD *)a1 + 74));
  v26 = (*((_BYTE *)a1 + 40) & 4) == 0;
  v43 = *((unsigned int *)v60 + 12);
  *((_QWORD *)a1 + 37) = v43;
  if ( v26 || v43 == *((_QWORD *)a1 + 36) )
  {
LABEL_121:
    if ( *(char *)v60 < 0 )
    {
      if ( (*((_BYTE *)a1 + 40) & 4) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids);
          v23 = -1073741715;
          goto LABEL_163;
        }
        goto LABEL_62;
      }
      v44 = (_OWORD *)((char *)a1 + 224);
      if ( *((_DWORD *)a1 + 56) != *((_DWORD *)v60 + 6) )
        goto LABEL_171;
      v45 = *((_DWORD *)a1 + 58);
      if ( v45 != *((_DWORD *)v60 + 8) )
        goto LABEL_171;
      v46 = 0;
      v47 = 0;
      if ( v45 )
      {
        do
        {
          v48 = v47++;
          v46 |= *(_BYTE *)(*((_QWORD *)a1 + 30) + v48) ^ *(_BYTE *)(*((_QWORD *)v60 + 5) + v48);
        }
        while ( v47 < *((_DWORD *)a1 + 58) );
        if ( v46 )
        {
LABEL_171:
          *((_DWORD *)a1 + 10) |= 0x400u;
          KerbFreeKey((struct _PKU2U_CONTEXT *)((char *)a1 + 200));
          v49 = *((_QWORD *)a1 + 30);
          v50 = (struct KERB_ENCRYPTION_KEY *)((char *)v60 + 24);
          *(_OWORD *)((char *)a1 + 200) = *v44;
          *((_QWORD *)a1 + 27) = v49;
          *v44 = 0;
          *((_QWORD *)a1 + 30) = 0;
          v51 = KerbDuplicateKey((struct _PKU2U_CONTEXT *)((char *)a1 + 224), v50);
          if ( v51 )
          {
            v52 = v51;
LABEL_161:
            v53 = KerbMapKerbError(v52);
LABEL_162:
            v23 = v53;
            goto LABEL_163;
          }
        }
      }
    }
    v23 = 0;
    goto LABEL_163;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_ii(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v23 = -1073741715;
    goto LABEL_163;
  }
LABEL_62:
  v23 = -1073741715;
LABEL_163:
  if ( v61 )
    KerbFreeData(0x24u, v61);
  if ( v60 )
    KerbFreeData(0x25u, v60);
  return v23;
}

```

## disassembly

```asm
0x18000f100  push    rbp
0x18000f102  push    rbx
0x18000f103  push    rsi
0x18000f104  push    rdi
0x18000f105  push    r12
0x18000f107  push    r14
0x18000f109  push    r15
0x18000f10b  mov     rbp, rsp
0x18000f10e  sub     rsp, 70h
0x18000f112  xor     r12d, r12d
0x18000f115  mov     rsi, rcx
0x18000f118  sub     r8d, 1
0x18000f11c  mov     [rbp+arg_18], r12
0x18000f120  mov     [rbp+arg_8], r12
0x18000f124  mov     qword ptr [rbp+Time], r12
0x18000f128  js      loc_18000FB80
0x18000f12e  cmp     byte ptr [rdx], 60h ; '`'
0x18000f131  jnz     loc_18000FB80
0x18000f137  cmp     r8d, 1
0x18000f13b  jl      loc_18000FB80
0x18000f141  movzx   r9d, byte ptr [rdx+1]
0x18000f146  lea     ebx, [r8-1]
0x18000f14a  add     rdx, 2
0x18000f14e  test    r9b, r9b
0x18000f151  jns     short loc_18000F18C
0x18000f153  and     r9b, 7Fh
0x18000f157  movzx   eax, r9b
0x18000f15b  inc     eax
0x18000f15d  cmp     eax, ebx
0x18000f15f  jg      loc_18000FB80
0x18000f165  cmp     r9b, 4
0x18000f169  ja      loc_18000FB80
0x18000f16f  mov     ecx, r12d
0x18000f172  test    r9b, r9b
0x18000f175  jz      short loc_18000F18F
0x18000f177  movzx   eax, byte ptr [rdx]
0x18000f17a  dec     ebx
0x18000f17c  shl     ecx, 8
0x18000f17f  inc     rdx
0x18000f182  add     ecx, eax
0x18000f184  add     r9b, 0FFh
0x18000f188  jnz     short loc_18000F177
0x18000f18a  jmp     short loc_18000F18F
0x18000f18c  mov     ecx, r9d
0x18000f18f  cmp     ecx, ebx
0x18000f191  jg      loc_18000FB80
0x18000f197  test    ecx, ecx
0x18000f199  js      loc_18000FB80
0x18000f19f  cmp     ecx, ebx
0x18000f1a1  jnz     loc_18000FB80
0x18000f1a7  sub     ebx, 1
0x18000f1aa  js      loc_18000FB80
0x18000f1b0  cmp     byte ptr [rdx], 6
0x18000f1b3  jnz     loc_18000FB80
0x18000f1b9  sub     ebx, 1
0x18000f1bc  js      loc_18000FB80
0x18000f1c2  movzx   edi, byte ptr [rdx+1]
0x18000f1c6  sub     ebx, edi
0x18000f1c8  js      loc_18000FB80
0x18000f1ce  cmp     edi, cs:?pku2u_global_oids@@3PAUgss_OID_desc_struct@@A; gss_OID_desc_struct near * pku2u_global_oids
0x18000f1d4  jnz     loc_18000FB80
0x18000f1da  lea     r15, [rdx+2]
0x18000f1de  movsxd  r8, edi; Size
0x18000f1e1  mov     rdx, cs:Src; Buf2
0x18000f1e8  mov     rcx, r15; Buf1
0x18000f1eb  call    memcmp_0
0x18000f1f0  test    eax, eax
0x18000f1f2  jnz     loc_18000FB80
0x18000f1f8  lea     r14d, [rbx-2]
0x18000f1fc  test    r14d, r14d
0x18000f1ff  js      loc_18000FB80
0x18000f205  cmp     byte ptr [rdi+r15], 2
0x18000f20a  jnz     loc_18000FB80
0x18000f210  cmp     [rdi+r15+1], r12b
0x18000f215  jnz     loc_18000FB80
0x18000f21b  mov     [rsp+70h+arg_0], r13
0x18000f223  mov     [rbp+var_20], r12
0x18000f227  test    r14d, r14d
0x18000f22a  jz      loc_18000FAC7
0x18000f230  lea     rbx, [r15+2]
0x18000f234  add     rbx, rdi
0x18000f237  jz      loc_18000FAC7
0x18000f23d  cmp     cs:?fKRB5ModuleStarted@@3HA, r12d; int fKRB5ModuleStarted
0x18000f244  lea     rax, qword_180049F80
0x18000f24b  lea     rcx, off_180047030
0x18000f252  lea     rdx, off_1800471C0
0x18000f259  lea     r8, off_180047350
0x18000f260  jnz     short loc_18000F2AD
0x18000f262  mov     [rsp+70h+var_30], 32756B70h
0x18000f26a  mov     r9d, 31h ; '1'
0x18000f270  mov     [rsp+70h+var_38], rax
0x18000f275  mov     [rsp+70h+var_40], rcx
0x18000f27a  mov     ecx, 10000h
0x18000f27f  mov     [rsp+70h+var_48], rdx
0x18000f284  mov     edx, 400h
0x18000f289  mov     [rsp+70h+var_50], r8
0x18000f28e  mov     r8d, 1000h
0x18000f294  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x18000f29e  call    cs:__imp_ASN1_CreateModule
0x18000f2a4  mov     cs:PKU2UMSG_Module, rax
0x18000f2ab  jmp     short loc_18000F2B4
0x18000f2ad  mov     rax, cs:PKU2UMSG_Module
0x18000f2b4  xor     r9d, r9d
0x18000f2b7  mov     [rsp+70h+var_50], r12
0x18000f2bc  xor     r8d, r8d
0x18000f2bf  lea     rdx, [rbp+var_20]
0x18000f2c3  mov     rcx, rax
0x18000f2c6  call    cs:__imp_ASN1_CreateDecoder
0x18000f2cc  test    eax, eax
0x18000f2ce  jz      short loc_18000F342
0x18000f2d0  mov     r10, cs:WPP_GLOBAL_Control
0x18000f2d7  lea     r13, WPP_GLOBAL_Control
0x18000f2de  mov     r12d, 3Ch ; '<'
0x18000f2e4  cmp     r10, r13
0x18000f2e7  jz      short loc_18000F33A
0x18000f2e9  test    byte ptr [r10+1Ch], 1
0x18000f2ee  jz      short loc_18000F30F
0x18000f2f0  mov     rcx, [r10+10h]
0x18000f2f4  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000f2fb  mov     edx, 4Dh ; 'M'
0x18000f300  mov     r9d, eax
0x18000f303  call    WPP_SF_d
0x18000f308  mov     r10, cs:WPP_GLOBAL_Control
0x18000f30f  cmp     r10, r13
0x18000f312  jz      short loc_18000F33A
0x18000f314  test    byte ptr [r10+1Ch], 1
0x18000f319  jz      short loc_18000F33A
0x18000f31b  mov     rcx, [r10+10h]
0x18000f31f  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000f326  mov     edx, 50h ; 'P'
0x18000f32b  mov     r9d, r12d
0x18000f32e  call    WPP_SF_d
0x18000f333  mov     r10, cs:WPP_GLOBAL_Control
0x18000f33a  mov     edi, r12d
0x18000f33d  jmp     loc_18000FB02
0x18000f342  mov     rcx, [rbp+var_20]
0x18000f346  lea     rdx, [rbp+arg_18]
0x18000f34a  mov     dword ptr [rsp+70h+var_48], r14d
0x18000f34f  mov     r9d, 8
0x18000f355  mov     r8d, 24h ; '$'
0x18000f35b  mov     [rsp+70h+var_50], rbx
0x18000f360  mov     edi, r12d
0x18000f363  mov     [rbp+arg_18], r12
0x18000f367  call    cs:__imp_ASN1_Decode
0x18000f36d  mov     ebx, eax
0x18000f36f  test    eax, eax
0x18000f371  jns     loc_18000F43B
0x18000f377  mov     r10, cs:WPP_GLOBAL_Control
0x18000f37e  lea     r13, WPP_GLOBAL_Control
0x18000f385  cmp     r10, r13
0x18000f388  jz      short loc_18000F3B0
0x18000f38a  test    byte ptr [r10+1Ch], 4
0x18000f38f  jz      short loc_18000F3B0
0x18000f391  mov     rcx, [r10+10h]
0x18000f395  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000f39c  mov     edx, 51h ; 'Q'
0x18000f3a1  mov     r9d, eax
0x18000f3a4  call    WPP_SF_d
0x18000f3a9  mov     r10, cs:WPP_GLOBAL_Control
0x18000f3b0  mov     r12d, 3Ch ; '<'
0x18000f3b6  cmp     ebx, 0FFFFFC0Fh
0x18000f3bc  jz      short loc_18000F3FE
0x18000f3be  cmp     ebx, 0FFFFFC16h
0x18000f3c4  jz      short loc_18000F3FE
0x18000f3c6  cmp     ebx, 0FFFFFC0Dh
0x18000f3cc  jz      short loc_18000F3F9
0x18000f3ce  cmp     r10, r13
0x18000f3d1  jz      short loc_18000F3F9
0x18000f3d3  test    byte ptr [r10+1Ch], 1
0x18000f3d8  jz      short loc_18000F3F9
0x18000f3da  mov     rcx, [r10+10h]
0x18000f3de  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000f3e5  mov     edx, 53h ; 'S'
0x18000f3ea  mov     r9d, ebx
0x18000f3ed  call    WPP_SF_d
0x18000f3f2  mov     r10, cs:WPP_GLOBAL_Control
0x18000f3f9  mov     edi, r12d
0x18000f3fc  jmp     short loc_18000F431
0x18000f3fe  cmp     r10, r13
0x18000f401  jz      short loc_18000F42C
0x18000f403  test    byte ptr [r10+1Ch], 4
0x18000f408  jz      short loc_18000F42C
0x18000f40a  mov     rcx, [r10+10h]
0x18000f40e  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000f415  mov     edx, 52h ; 'R'
0x18000f41a  mov     r9d, 24h ; '$'
0x18000f420  call    WPP_SF_d
0x18000f425  mov     r10, cs:WPP_GLOBAL_Control
0x18000f42c  mov     edi, 80000001h
0x18000f431  mov     [rbp+arg_18], 0
0x18000f439  jmp     short loc_18000F44F
0x18000f43b  mov     r10, cs:WPP_GLOBAL_Control
0x18000f442  lea     r13, WPP_GLOBAL_Control
0x18000f449  mov     r12d, 3Ch ; '<'
0x18000f44f  mov     rcx, [rbp+var_20]
0x18000f453  test    rcx, rcx
0x18000f456  jz      short loc_18000F465
0x18000f458  call    cs:__imp_ASN1_CloseDecoder
0x18000f45e  mov     r10, cs:WPP_GLOBAL_Control
0x18000f465  test    edi, edi
0x18000f467  jnz     loc_18000FB02
0x18000f46d  mov     rbx, [rbp+arg_18]
0x18000f471  mov     r9d, [rbx]
0x18000f474  cmp     r9d, 5
0x18000f478  jnz     loc_18000FA78
0x18000f47e  cmp     dword ptr [rbx+4], 0Fh
0x18000f482  jnz     loc_18000FA78
0x18000f488  cmp     [rsi+38h], edi
0x18000f48b  jz      short loc_18000F4D1
0x18000f48d  cmp     qword ptr [rsi+0B0h], 0
0x18000f495  jnz     short loc_18000F4D1
0x18000f497  cmp     r10, r13
0x18000f49a  jz      short loc_18000F4C7
0x18000f49c  test    byte ptr [r10+1Ch], 1
0x18000f4a1  jz      short loc_18000F4C7
0x18000f4a3  mov     rcx, [r10+10h]
0x18000f4a7  lea     r9, aOnecoreDsSecur_10; "onecore\\ds\\security\\protocols\\pku2u"...
0x18000f4ae  mov     edx, 27h ; '''
0x18000f4b3  mov     dword ptr [rsp+70h+var_50], 8E1h
0x18000f4bb  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000f4c2  call    WPP_SF_sd
0x18000f4c7  mov     edi, 0C000006Dh
0x18000f4cc  jmp     loc_18000FB3B
0x18000f4d1  mov     rcx, [rsi+0B0h]
0x18000f4d8  lea     rax, [rsi+0F8h]
0x18000f4df  mov     rbx, [rbp+arg_18]
0x18000f4e3  lea     rdx, [rbp+var_20]
0x18000f4e7  test    rcx, rcx
0x18000f4ea  lea     rdi, [rcx+38h]
0x18000f4ee  mov     ecx, [rbx+0Ch]
0x18000f4f1  lea     r15, [rbx+18h]
0x18000f4f5  mov     r14, [rbx+20h]
0x18000f4f9  cmovz   rdi, rax
0x18000f4fd  xor     eax, eax
0x18000f4ff  mov     [rbp+var_20], rax
0x18000f503  mov     [rbp+var_18], rax
0x18000f507  call    cs:__imp_CDLocateCSystem
0x18000f50d  test    eax, eax
0x18000f50f  jns     short loc_18000F51C
0x18000f511  mov     r12d, 0Eh
0x18000f517  jmp     loc_18000FA24
0x18000f51c  mov     rax, [rbp+var_20]
0x18000f520  mov     edx, [rdi+8]
0x18000f523  cmp     [rax+0Ch], edx
0x18000f526  jnz     loc_18000FA1E
0x18000f52c  cmp     dword ptr [rbx+18h], 0
0x18000f530  jz      loc_18000FA24
0x18000f536  cmp     qword ptr [rbx+20h], 0
0x18000f53b  jz      loc_18000FA24
0x18000f541  mov     rcx, [rdi+10h]
0x18000f545  lea     r9, [rbp+var_18]
0x18000f549  mov     rax, [rax+28h]
0x18000f54d  mov     r8d, 0Ch
0x18000f553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f558  test    eax, eax
0x18000f55a  js      loc_18000FA24
0x18000f560  mov     rax, [rbp+var_20]
0x18000f564  mov     r9, r14
0x18000f567  mov     r8d, [rbx+18h]
0x18000f56b  mov     rdx, [rbx+20h]
0x18000f56f  mov     rcx, [rbp+var_18]
0x18000f573  mov     rax, [rax+38h]
0x18000f577  mov     [rsp+70h+var_50], r15
0x18000f57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f581  mov     rcx, [rbp+var_20]
0x18000f585  mov     ebx, eax
0x18000f587  mov     rax, [rcx+40h]
0x18000f58b  lea     rcx, [rbp+var_18]
0x18000f58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f594  test    ebx, ebx
0x18000f596  js      loc_18000FA1E
0x18000f59c  mov     rbx, [rbp+arg_18]
0x18000f5a0  xor     r15d, r15d
0x18000f5a3  mov     [rbp+var_10], r15
0x18000f5a7  mov     r14d, [rbx+18h]
0x18000f5ab  test    r14d, r14d
0x18000f5ae  jz      loc_18000F9B5
0x18000f5b4  mov     rdi, [rbx+20h]
0x18000f5b8  test    rdi, rdi
0x18000f5bb  jz      loc_18000F9B5
0x18000f5c1  cmp     cs:?fKRB5ModuleStarted@@3HA, r15d; int fKRB5ModuleStarted
0x18000f5c8  jnz     short loc_18000F631
0x18000f5ca  mov     [rsp+70h+var_30], 32756B70h
0x18000f5d2  lea     rax, qword_180049F80
0x18000f5d9  mov     [rsp+70h+var_38], rax
0x18000f5de  mov     edx, 400h
0x18000f5e3  lea     rax, off_180047030
0x18000f5ea  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x18000f5f4  mov     [rsp+70h+var_40], rax
0x18000f5f9  mov     ecx, 10000h
0x18000f5fe  lea     rax, off_1800471C0
0x18000f605  mov     r9d, 31h ; '1'
0x18000f60b  mov     [rsp+70h+var_48], rax
0x18000f610  mov     r8d, 1000h
0x18000f616  lea     rax, off_180047350
0x18000f61d  mov     [rsp+70h+var_50], rax
0x18000f622  call    cs:__imp_ASN1_CreateModule
0x18000f628  mov     cs:PKU2UMSG_Module, rax
0x18000f62f  jmp     short loc_18000F638
0x18000f631  mov     rax, cs:PKU2UMSG_Module
  ... truncated ...
```
