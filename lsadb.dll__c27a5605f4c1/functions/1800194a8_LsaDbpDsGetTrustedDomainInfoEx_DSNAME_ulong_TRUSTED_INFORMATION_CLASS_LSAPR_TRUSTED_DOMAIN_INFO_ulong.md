# LsaDbpDsGetTrustedDomainInfoEx(_DSNAME *,ulong,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO *,ulong *)

- ea: `0x1800194a8`
- end: `0x180019c5c`
- name: `?LsaDbpDsGetTrustedDomainInfoEx@@YAJPEAU_DSNAME@@KW4_TRUSTED_INFORMATION_CLASS@@PEAT_LSAPR_TRUSTED_DOMAIN_INFO@@PEAK@Z`
- size: `1972`
- prototype: `__int64 __usercall@<rax>(struct _DSNAME *@<rcx>, unsigned int@<edx>, enum _TRUSTED_INFORMATION_CLASS@<r8d>, union _LSAPR_TRUSTED_DOMAIN_INFO *@<r9>, unsigned int *)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800136d4`
- `0x180014a40`
- `0x180017a88`
- `0x180018938`
- `0x180019110`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fee8`
- `0x180011f90`
- `0x180018fa4`
- `0x1800194a8`
- `0x18001a110`
- `0x18003ad30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800197ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019850`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800198db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001990a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800197ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019850`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800198db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001990a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019bdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019be7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019bf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019bfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019bdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019be7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019bf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019bfb`
- `ntdll!RtlLengthSid` at `0x180019a7b`
- `ntdll!RtlLengthSid` at `0x180019af9`
- `ntdll!RtlLengthSid` at `0x180019ba8`
- `ntdll!RtlLengthSid` at `0x180019a7b`
- `ntdll!RtlLengthSid` at `0x180019af9`
- `ntdll!RtlLengthSid` at `0x180019ba8`

## pseudocode

```c
__int64 __fastcall LsaDbpDsGetTrustedDomainInfoEx(
        struct _DSNAME *a1,
        unsigned int a2,
        enum _TRUSTED_INFORMATION_CLASS a3,
        union _LSAPR_TRUSTED_DOMAIN_INFO *a4,
        unsigned int *a5)
{
  void *v6; // r14
  void *v7; // r15
  __int128 v11; // xmm6
  __int128 v12; // xmm7
  int v13; // ebx
  unsigned int v14; // esi
  int v15; // r13d
  unsigned __int8 *v16; // r8
  unsigned int v17; // r9d
  __int64 v18; // rsi
  __int64 v19; // r13
  __int64 v20; // rsi
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned __int16 epi16; // dx
  __int64 v27; // rax
  HLOCAL v28; // rax
  const void **v29; // rdx
  size_t v30; // r8
  __int64 v31; // rax
  unsigned __int8 *v32; // rcx
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // r8d
  unsigned __int16 v37; // cx
  int v38; // esi
  int v39; // r12d
  int v40; // r12d
  int v41; // r12d
  int v42; // r12d
  ULONG v43; // edx
  int v44; // esi
  unsigned __int16 v46; // [rsp+38h] [rbp-D0h]
  unsigned __int16 v47; // [rsp+3Ah] [rbp-CEh]
  unsigned int v48; // [rsp+3Ch] [rbp-CCh]
  unsigned __int8 *v49; // [rsp+40h] [rbp-C8h]
  unsigned int v50; // [rsp+48h] [rbp-C0h]
  int v51; // [rsp+4Ch] [rbp-BCh]
  int v52; // [rsp+50h] [rbp-B8h]
  int v53; // [rsp+54h] [rbp-B4h]
  int v54; // [rsp+58h] [rbp-B0h]
  int v55; // [rsp+5Ch] [rbp-ACh]
  unsigned int v56; // [rsp+60h] [rbp-A8h]
  unsigned int v57[4]; // [rsp+68h] [rbp-A0h]
  HLOCAL hMem_8[2]; // [rsp+78h] [rbp-90h]
  unsigned __int8 *v59[2]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v60; // [rsp+98h] [rbp-70h] BYREF
  unsigned int *v61; // [rsp+A8h] [rbp-60h]
  _DWORD v62[4]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v63; // [rsp+C8h] [rbp-40h]
  int v64; // [rsp+D0h] [rbp-38h]
  int v65; // [rsp+D8h] [rbp-30h]
  __int64 v66; // [rsp+E0h] [rbp-28h]
  int v67; // [rsp+E8h] [rbp-20h]
  int v68; // [rsp+F0h] [rbp-18h]
  __int64 v69; // [rsp+F8h] [rbp-10h]
  int v70; // [rsp+100h] [rbp-8h]
  int v71; // [rsp+108h] [rbp+0h]
  __int64 v72; // [rsp+110h] [rbp+8h]
  int v73; // [rsp+118h] [rbp+10h]
  int v74; // [rsp+120h] [rbp+18h]
  __int64 v75; // [rsp+128h] [rbp+20h]
  int v76; // [rsp+130h] [rbp+28h]
  int v77; // [rsp+138h] [rbp+30h]
  __int64 v78; // [rsp+140h] [rbp+38h]
  int v79; // [rsp+148h] [rbp+40h]
  int v80; // [rsp+150h] [rbp+48h]
  __int64 v81; // [rsp+158h] [rbp+50h]
  int v82; // [rsp+160h] [rbp+58h]
  int v83; // [rsp+168h] [rbp+60h]
  __int64 v84; // [rsp+170h] [rbp+68h]

  v61 = a5;
  v62[0] = 0;
  v6 = 0;
  v62[2] = 0;
  v7 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  *(_OWORD *)v59 = 0;
  v60 = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids);
  v11 = 0;
  v12 = 0;
  *(_OWORD *)hMem_8 = 0;
  *(_OWORD *)v57 = 0;
  switch ( a3 )
  {
    case TrustedDomainInformationBasic:
      v62[0] = 590335;
      v64 = 589945;
      goto LABEL_14;
    case TrustedDomainInformationEx:
      v62[0] = 589957;
      v14 = 6;
      v64 = 590335;
      v67 = 589945;
      v70 = 589956;
      v73 = 589960;
      v76 = 590294;
      break;
    case TrustedDomainAuthInformation:
      v62[0] = 589953;
      v64 = 589959;
LABEL_14:
      v14 = 2;
      break;
    case TrustedDomainFullInformation:
      v62[0] = 589957;
      v14 = 7;
      v64 = 590335;
      v67 = 589945;
      v70 = 589956;
      v73 = 589960;
      v76 = 590294;
      v79 = 589958;
      break;
    case TrustedDomainFullInformation2Internal:
      v62[0] = 589957;
      v14 = 8;
      v64 = 590335;
      v67 = 589945;
      v70 = 589956;
      v73 = 589960;
      v76 = 590294;
      v79 = 589958;
      v82 = 591526;
      break;
    default:
      v13 = -1073741811;
LABEL_83:
      LocalFree(v7);
      LocalFree(*(HLOCAL *)&v57[2]);
      LocalFree(hMem_8[1]);
      LocalFree(v6);
      goto LABEL_84;
  }
  LODWORD(v59[0]) = v14;
  v59[1] = (unsigned __int8 *)v62;
  v13 = LsaDbpDsReadByDsName(a1, a2, (struct _ATTRBLOCKSIMPLE *)v59, (struct _ATTRBLOCKSIMPLE *)&v60);
  if ( v13 < 0 )
  {
    if ( v13 == -1073741275 && (a2 & 0x10000000) == 0 )
      v13 = -1073741772;
    goto LABEL_83;
  }
  v15 = v60;
  v16 = 0;
  v17 = 0;
  v51 = 0;
  v54 = 0;
  v52 = 0;
  v53 = 0;
  v49 = 0;
  v59[0] = 0;
  v48 = 0;
  v56 = 0;
  v50 = 0;
  if ( v14 != (_DWORD)v60 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids, v14, v60);
    v16 = 0;
    v17 = 0;
  }
  v18 = 0;
  v55 = 0;
  if ( v15 )
  {
    v19 = *((_QWORD *)&v60 + 1);
    v47 = 0;
    v46 = 0;
    while ( 1 )
    {
      if ( v13 < 0 )
        goto LABEL_83;
      v20 = 3 * v18;
      v21 = *(_DWORD *)(v19 + 8 * v20);
      if ( v21 <= 0x90087 )
        break;
      v33 = v21 - 589960;
      if ( !v33 )
      {
        v52 = **(_DWORD **)(*(_QWORD *)(v19 + 8 * v20 + 16) + 8LL);
        goto LABEL_51;
      }
      v34 = v33 - 334;
      if ( !v34 )
      {
        v53 = **(_DWORD **)(*(_QWORD *)(v19 + 8 * v20 + 16) + 8LL);
        goto LABEL_51;
      }
      v35 = v34 - 41;
      if ( v35 )
      {
        if ( v35 != 1191 )
        {
LABEL_43:
          v13 = -1073741811;
          goto LABEL_51;
        }
        v36 = **(_DWORD **)(v19 + 8 * v20 + 16);
        v50 = v36;
        if ( v36 )
        {
          v28 = LocalAlloc(0x40u, v36);
          v7 = v28;
          if ( v28 )
          {
            v29 = *(const void ***)(v19 + 8 * v20 + 16);
            v30 = v50;
            goto LABEL_37;
          }
LABEL_31:
          v13 = -1073741670;
        }
LABEL_51:
        epi16 = v47;
        goto LABEL_52;
      }
      hMem_8[1] = LocalAlloc(0x40u, **(unsigned int **)(v19 + 8 * v20 + 16) + 2LL);
      if ( !hMem_8[1] )
        goto LABEL_31;
      memset_0(hMem_8[1], 0, **(unsigned int **)(v19 + 8 * v20 + 16) + 2LL);
      memcpy_0(
        hMem_8[1],
        *(const void **)(*(_QWORD *)(v19 + 8 * v20 + 16) + 8LL),
        **(unsigned int **)(v19 + 8 * v20 + 16));
      epi16 = v47;
      v16 = v49;
      v17 = v48;
      LOWORD(hMem_8[0]) = **(_WORD **)(v19 + 8 * v20 + 16);
      v37 = LOWORD(hMem_8[0]) + 2;
      v46 = LOWORD(hMem_8[0]) + 2;
      WORD1(hMem_8[0]) = LOWORD(hMem_8[0]) + 2;
LABEL_54:
      v18 = (unsigned int)(v55 + 1);
      v55 = v18;
      if ( (unsigned int)v18 >= (unsigned int)v60 )
      {
        v12 = *(_OWORD *)v57;
        v11 = *(_OWORD *)hMem_8;
        goto LABEL_57;
      }
    }
    if ( v21 == 589959 )
    {
      v31 = *(_QWORD *)(v19 + 8 * v20 + 16);
      v32 = *(unsigned __int8 **)(v31 + 8);
      LODWORD(v31) = *(_DWORD *)v31;
      v59[0] = v32;
      v56 = v31;
      goto LABEL_51;
    }
    v22 = v21 - 589945;
    if ( !v22 )
    {
      v28 = LocalAlloc(0x40u, **(unsigned int **)(v19 + 8 * v20 + 16));
      v6 = v28;
      if ( v28 )
      {
        v29 = *(const void ***)(v19 + 8 * v20 + 16);
        v30 = *(unsigned int *)v29;
LABEL_37:
        memcpy_0(v28, v29[1], v30);
        goto LABEL_51;
      }
      goto LABEL_31;
    }
    v23 = v22 - 8;
    if ( v23 )
    {
      v24 = v23 - 3;
      if ( !v24 )
      {
        v54 = **(_DWORD **)(*(_QWORD *)(v19 + 8 * v20 + 16) + 8LL);
        goto LABEL_51;
      }
      v25 = v24 - 1;
      if ( v25 )
      {
        if ( v25 != 1 )
          goto LABEL_43;
        v51 = **(_DWORD **)(*(_QWORD *)(v19 + 8 * v20 + 16) + 8LL);
        goto LABEL_51;
      }
      *(_QWORD *)&v57[2] = LocalAlloc(0x40u, **(unsigned int **)(v19 + 8 * v20 + 16) + 2LL);
      if ( !*(_QWORD *)&v57[2] )
        goto LABEL_31;
      memset_0(*(void **)&v57[2], 0, **(unsigned int **)(v19 + 8 * v20 + 16) + 2LL);
      memcpy_0(
        *(void **)&v57[2],
        *(const void **)(*(_QWORD *)(v19 + 8 * v20 + 16) + 8LL),
        **(unsigned int **)(v19 + 8 * v20 + 16));
      LOWORD(v57[0]) = **(_WORD **)(v19 + 8 * v20 + 16);
      epi16 = LOWORD(v57[0]) + 2;
      v47 = LOWORD(v57[0]) + 2;
      HIWORD(v57[0]) = LOWORD(v57[0]) + 2;
LABEL_52:
      v17 = v48;
      v16 = v49;
    }
    else
    {
      v27 = *(_QWORD *)(v19 + 8 * v20 + 16);
      epi16 = v47;
      v16 = *(unsigned __int8 **)(v27 + 8);
      v17 = *(_DWORD *)v27;
      v49 = v16;
      v48 = *(_DWORD *)v27;
    }
    v37 = v46;
    goto LABEL_54;
  }
  *(_QWORD *)&v57[2] = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  epi16 = _mm_extract_epi16((__m128i)0LL, 1);
  v37 = epi16;
  hMem_8[1] = *(HLOCAL *)&v57[2];
  v47 = epi16;
  v46 = epi16;
LABEL_57:
  if ( v13 < 0 )
    goto LABEL_83;
  v38 = 0;
  v39 = a3 - 5;
  if ( !v39 )
  {
    *((_QWORD *)a4 + 2) = v6;
    *(_OWORD *)a4 = v11;
    if ( v6 )
      v38 = v37 + 8 + RtlLengthSid(v6);
    else
      v38 = v37 + 8;
    goto LABEL_78;
  }
  v40 = v39 - 1;
  if ( !v40 )
    goto LABEL_68;
  v41 = v40 - 1;
  if ( v41 )
  {
    v42 = v41 - 1;
    if ( v42 )
    {
      if ( v42 == 4 )
      {
        memset_0(a4, 0, 0x78u);
        *((_DWORD *)a4 + 11) = v52;
        *((_DWORD *)a4 + 12) = v53;
        *((_DWORD *)a4 + 10) = v54;
        *((_DWORD *)a4 + 16) = v51;
        *((_QWORD *)a4 + 4) = v6;
        *((_QWORD *)a4 + 7) = v7;
        *((_DWORD *)a4 + 13) = v50;
        *(_OWORD *)a4 = v12;
        *((_OWORD *)a4 + 1) = v11;
        if ( v6 )
          v43 = RtlLengthSid(v6);
        else
          v43 = 0;
        v38 = v43 + v46 + v47 + v50 + 24;
      }
      goto LABEL_78;
    }
    memset_0(a4, 0, 0x70u);
    v38 = 4;
    v37 = v46;
    epi16 = v47;
    *((_DWORD *)a4 + 14) = v51;
LABEL_68:
    *((_QWORD *)a4 + 5) = 0;
    *((_QWORD *)a4 + 6) = 0;
    *((_QWORD *)a4 + 4) = v6;
    *(_OWORD *)a4 = v12;
    *((_OWORD *)a4 + 1) = v11;
    if ( v6 )
      v44 = epi16 + v38 + v37 + 8 + RtlLengthSid(v6);
    else
      v44 = epi16 + v38 + v37 + 8;
    v38 = v44 + 12;
    *((_DWORD *)a4 + 11) = v52;
    *((_DWORD *)a4 + 12) = v53;
    *((_DWORD *)a4 + 10) = v54;
    goto LABEL_78;
  }
  *(_OWORD *)a4 = 0;
  *((_OWORD *)a4 + 1) = 0;
  *((_OWORD *)a4 + 2) = 0;
  v13 = LsaDbpDsUnmarshalAuthInfoHalf(0, 0, 0, v16, v17, a4);
  if ( v13 < 0 )
    goto LABEL_83;
  v13 = LsaDbpDsUnmarshalAuthInfoHalf(
          0,
          0,
          0,
          v59[0],
          v56,
          (struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)(((unsigned __int64)a4 + 24) & -(__int64)(a4 != 0)));
  if ( v13 < 0 )
  {
    LsaDbpDsFreeUnmarshalAuthInfoHalf(a4);
    goto LABEL_83;
  }
LABEL_78:
  if ( v61 )
    *v61 = v38;
LABEL_84:
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids,
      (unsigned int)v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800194a8  mov     rax, rsp
0x1800194ab  mov     [rax+18h], rbx
0x1800194af  push    rbp
0x1800194b0  push    rsi
0x1800194b1  push    rdi
0x1800194b2  push    r12
0x1800194b4  push    r13
0x1800194b6  push    r14
0x1800194b8  push    r15
0x1800194ba  lea     rbp, [rax-0D8h]
0x1800194c1  sub     rsp, 1A0h
0x1800194c8  movaps  xmmword ptr [rax-48h], xmm6
0x1800194cc  movaps  xmmword ptr [rax-58h], xmm7
0x1800194d0  mov     rax, cs:__security_cookie
0x1800194d7  xor     rax, rsp
0x1800194da  mov     [rbp+0D0h+var_60], rax
0x1800194de  mov     rax, [rbp+0D0h+arg_20]
0x1800194e5  xorps   xmm0, xmm0
0x1800194e8  mov     [rbp+0D0h+var_130], rax
0x1800194ec  xorps   xmm1, xmm1
0x1800194ef  xor     eax, eax
0x1800194f1  mov     rdi, r9
0x1800194f4  mov     [rbp+0D0h+var_120], eax
0x1800194f7  mov     r14d, eax
0x1800194fa  mov     [rbp+0D0h+var_118], eax
0x1800194fd  mov     r15d, eax
0x180019500  mov     [rbp+0D0h+var_110], rax
0x180019504  mov     r12d, r8d
0x180019507  mov     [rbp+0D0h+var_108], eax
0x18001950a  mov     r13d, edx
0x18001950d  mov     [rbp+0D0h+var_100], eax
0x180019510  mov     rbx, rcx
0x180019513  mov     [rbp+0D0h+var_F8], rax
0x180019517  mov     [rbp+0D0h+var_F0], eax
0x18001951a  mov     [rbp+0D0h+var_E8], eax
0x18001951d  mov     [rbp+0D0h+var_E0], rax
0x180019521  mov     [rbp+0D0h+var_D8], eax
0x180019524  mov     [rbp+0D0h+var_D0], eax
0x180019527  mov     [rbp+0D0h+var_C8], rax
0x18001952b  mov     [rbp+0D0h+var_C0], eax
0x18001952e  mov     [rbp+0D0h+var_B8], eax
0x180019531  mov     [rbp+0D0h+var_B0], rax
0x180019535  mov     [rbp+0D0h+var_A8], eax
0x180019538  mov     [rbp+0D0h+var_A0], eax
0x18001953b  mov     [rbp+0D0h+var_98], rax
0x18001953f  mov     [rbp+0D0h+var_90], eax
0x180019542  mov     [rbp+0D0h+var_88], eax
0x180019545  mov     [rbp+0D0h+var_80], rax
0x180019549  mov     [rbp+0D0h+var_78], eax
0x18001954c  mov     [rbp+0D0h+var_70], eax
0x18001954f  mov     [rbp+0D0h+var_68], rax
0x180019553  movups  xmmword ptr [rbp+0D0h+var_150], xmm0
0x180019557  movups  [rbp+0D0h+var_140], xmm1
0x18001955b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019562  test    dword ptr [rcx+1Ch], 100h
0x180019569  jz      short loc_18001957E
0x18001956b  mov     rcx, [rcx+10h]
0x18001956f  lea     edx, [rax+10h]
0x180019572  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180019579  call    WPP_SF_
0x18001957e  mov     eax, 90079h
0x180019583  mov     ecx, r12d
0x180019586  xorps   xmm6, xmm6
0x180019589  xorps   xmm7, xmm7
0x18001958c  mov     edx, 2
0x180019591  movups  xmmword ptr [rsp+1D0h+hMem+8], xmm6
0x180019596  lea     r8d, [rax+0Fh]
0x18001959a  movups  xmmword ptr [rsp+1D0h+var_178+8], xmm7
0x18001959f  sub     ecx, 5
0x1800195a2  jz      loc_18001966D
0x1800195a8  sub     ecx, 1
0x1800195ab  jz      loc_180019643
0x1800195b1  sub     ecx, 1
0x1800195b4  jz      short loc_180019633
0x1800195b6  sub     ecx, 1
0x1800195b9  jz      short loc_180019602
0x1800195bb  cmp     ecx, 4
0x1800195be  jz      short loc_1800195CA
0x1800195c0  mov     ebx, 0C000000Dh
0x1800195c5  jmp     loc_180019BD9
0x1800195ca  mov     [rbp+0D0h+var_120], 90085h
0x1800195d1  mov     esi, 8
0x1800195d6  mov     [rbp+0D0h+var_108], 901FFh
0x1800195dd  mov     [rbp+0D0h+var_F0], eax
0x1800195e0  mov     [rbp+0D0h+var_D8], 90084h
0x1800195e7  mov     [rbp+0D0h+var_C0], r8d
0x1800195eb  mov     [rbp+0D0h+var_A8], 901D6h
0x1800195f2  mov     [rbp+0D0h+var_90], 90086h
0x1800195f9  mov     [rbp+0D0h+var_78], 906A6h
0x180019600  jmp     short loc_180019679
0x180019602  mov     [rbp+0D0h+var_120], 90085h
0x180019609  mov     esi, 7
0x18001960e  mov     [rbp+0D0h+var_108], 901FFh
0x180019615  mov     [rbp+0D0h+var_F0], eax
0x180019618  mov     [rbp+0D0h+var_D8], 90084h
0x18001961f  mov     [rbp+0D0h+var_C0], r8d
0x180019623  mov     [rbp+0D0h+var_A8], 901D6h
0x18001962a  mov     [rbp+0D0h+var_90], 90086h
0x180019631  jmp     short loc_180019679
0x180019633  mov     [rbp+0D0h+var_120], 90081h
0x18001963a  mov     [rbp+0D0h+var_108], 90087h
0x180019641  jmp     short loc_180019677
0x180019643  mov     [rbp+0D0h+var_120], 90085h
0x18001964a  mov     esi, 6
0x18001964f  mov     [rbp+0D0h+var_108], 901FFh
0x180019656  mov     [rbp+0D0h+var_F0], eax
0x180019659  mov     [rbp+0D0h+var_D8], 90084h
0x180019660  mov     [rbp+0D0h+var_C0], r8d
0x180019664  mov     [rbp+0D0h+var_A8], 901D6h
0x18001966b  jmp     short loc_180019679
0x18001966d  mov     [rbp+0D0h+var_120], 901FFh
0x180019674  mov     [rbp+0D0h+var_108], eax
0x180019677  mov     esi, edx
0x180019679  lea     rax, [rbp+0D0h+var_120]
0x18001967d  mov     dword ptr [rbp+0D0h+var_150], esi
0x180019680  lea     r9, [rbp+0D0h+var_140]; struct _ATTRBLOCKSIMPLE *
0x180019684  mov     [rbp+0D0h+var_150+8], rax
0x180019688  lea     r8, [rbp+0D0h+var_150]; struct _ATTRBLOCKSIMPLE *
0x18001968c  mov     edx, r13d; unsigned int
0x18001968f  mov     rcx, rbx; struct _DSNAME *
0x180019692  call    ?LsaDbpDsReadByDsName@@YAJPEAU_DSNAME@@KPEAU_ATTRBLOCKSIMPLE@@1@Z; LsaDbpDsReadByDsName(_DSNAME *,ulong,_ATTRBLOCKSIMPLE *,_ATTRBLOCKSIMPLE *)
0x180019697  mov     ebx, eax
0x180019699  test    eax, eax
0x18001969b  js      loc_180019BC4
0x1800196a1  mov     r13d, dword ptr [rbp+0D0h+var_140]
0x1800196a5  xor     r8d, r8d
0x1800196a8  xor     r9d, r9d
0x1800196ab  mov     [rsp+1D0h+var_18C], r14d
0x1800196b0  mov     [rsp+1D0h+var_180], r14d
0x1800196b5  mov     [rsp+1D0h+var_188], r14d
0x1800196ba  mov     [rsp+1D0h+var_184], r14d
0x1800196bf  mov     [rsp+1D0h+var_198], r8
0x1800196c4  mov     [rbp+0D0h+var_150], r8
0x1800196c8  mov     [rsp+1D0h+var_1A0+4], r9d
0x1800196cd  mov     [rsp+1D0h+var_178], r8d
0x1800196d2  mov     [rsp+1D0h+var_190], r8d
0x1800196d7  cmp     esi, r13d
0x1800196da  jz      short loc_18001970E
0x1800196dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196e3  test    dword ptr [rcx+1Ch], 100h
0x1800196ea  jz      short loc_18001970E
0x1800196ec  mov     rcx, [rcx+10h]
0x1800196f0  lea     edx, [r8+11h]
0x1800196f4  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x1800196fb  mov     [rsp+1D0h+var_1B0], r13d
0x180019700  mov     r9d, esi
0x180019703  call    WPP_SF_dd
0x180019708  mov     r8, r14
0x18001970b  mov     r9d, r8d
0x18001970e  xor     esi, esi
0x180019710  mov     [rsp+1D0h+var_17C], esi
0x180019714  test    r13d, r13d
0x180019717  jz      loc_1800199C9
0x18001971d  movzx   ecx, word ptr [rsp+1D0h+var_178+0Ah]
0x180019722  movzx   eax, word ptr [rsp+1D0h+hMem+0Ah]
0x180019727  mov     r13, qword ptr [rbp+0D0h+var_140+8]
0x18001972b  mov     word ptr [rsp+1D0h+var_1A0+2], cx
0x180019730  mov     word ptr [rsp+1D0h+var_1A0], ax
0x180019735  mov     r9d, 40h ; '@'
0x18001973b  test    ebx, ebx
0x18001973d  js      loc_180019BD9
0x180019743  lea     rsi, [rsi+rsi*2]
0x180019747  mov     ecx, 90087h
0x18001974c  mov     eax, [r13+rsi*8+0]
0x180019751  cmp     eax, ecx
0x180019753  ja      loc_180019893
0x180019759  jz      loc_18001987B
0x18001975f  sub     eax, 90079h
0x180019764  jz      loc_180019846
0x18001976a  sub     eax, 8
0x18001976d  jz      loc_180019826
0x180019773  sub     eax, 3
0x180019776  jz      loc_180019812
0x18001977c  sub     eax, 1
0x18001977f  jz      short loc_18001979E
0x180019781  cmp     eax, 1
0x180019784  jnz     loc_1800198B5
0x18001978a  mov     rax, [r13+rsi*8+10h]
0x18001978f  mov     rcx, [rax+8]
0x180019793  mov     eax, [rcx]
0x180019795  mov     [rsp+1D0h+var_18C], eax
0x180019799  jmp     loc_180019996
0x18001979e  mov     rax, [r13+rsi*8+10h]
0x1800197a3  mov     ecx, r9d; uFlags
0x1800197a6  mov     edx, [rax]
0x1800197a8  add     rdx, 2; uBytes
0x1800197ac  call    cs:__imp_LocalAlloc
0x1800197b2  mov     [rsp+1D0h+hMem], rax
0x1800197b7  mov     rcx, rax; void *
0x1800197ba  test    rax, rax
0x1800197bd  jnz     short loc_1800197C9
0x1800197bf  mov     ebx, 0C000009Ah
0x1800197c4  jmp     loc_180019996
0x1800197c9  mov     rax, [r13+rsi*8+10h]
0x1800197ce  xor     edx, edx; Val
0x1800197d0  mov     r8d, [rax]
0x1800197d3  add     r8, 2; Size
0x1800197d7  call    memset_0
0x1800197dc  mov     rdx, [r13+rsi*8+10h]
0x1800197e1  mov     rcx, [rsp+1D0h+hMem]; void *
0x1800197e6  mov     r8d, [rdx]; Size
0x1800197e9  mov     rdx, [rdx+8]; Src
0x1800197ed  call    memcpy_0
0x1800197f2  mov     rax, [r13+rsi*8+10h]
0x1800197f7  movzx   edx, word ptr [rax]
0x1800197fa  mov     word ptr [rsp+1D0h+var_178+8], dx
0x1800197ff  add     dx, 2
0x180019803  mov     word ptr [rsp+1D0h+var_1A0+2], dx
0x180019808  mov     word ptr [rsp+1D0h+var_178+0Ah], dx
0x18001980d  jmp     loc_18001999B
0x180019812  mov     rax, [r13+rsi*8+10h]
0x180019817  mov     rcx, [rax+8]
0x18001981b  mov     eax, [rcx]
0x18001981d  mov     [rsp+1D0h+var_180], eax
0x180019821  jmp     loc_180019996
0x180019826  mov     rax, [r13+rsi*8+10h]
0x18001982b  movzx   edx, word ptr [rsp+1D0h+var_1A0+2]
0x180019830  mov     r8, [rax+8]
0x180019834  mov     r9d, [rax]
0x180019837  mov     [rsp+1D0h+var_198], r8
0x18001983c  mov     [rsp+1D0h+var_1A0+4], r9d
0x180019841  jmp     loc_1800199A5
0x180019846  mov     rax, [r13+rsi*8+10h]
0x18001984b  mov     ecx, r9d; uFlags
0x18001984e  mov     edx, [rax]; uBytes
0x180019850  call    cs:__imp_LocalAlloc
0x180019856  mov     r14, rax
0x180019859  test    rax, rax
0x18001985c  jz      loc_1800197BF
0x180019862  mov     rdx, [r13+rsi*8+10h]
0x180019867  mov     r8d, [rdx]; Size
0x18001986a  mov     rdx, [rdx+8]; Src
0x18001986e  mov     rcx, rax; void *
0x180019871  call    memcpy_0
0x180019876  jmp     loc_180019996
0x18001987b  mov     rax, [r13+rsi*8+10h]
0x180019880  mov     rcx, [rax+8]
0x180019884  mov     eax, [rax]
0x180019886  mov     [rbp+0D0h+var_150], rcx
0x18001988a  mov     [rsp+1D0h+var_178], eax
0x18001988e  jmp     loc_180019996
0x180019893  sub     eax, 90088h
0x180019898  jz      loc_180019987
0x18001989e  sub     eax, 14Eh
0x1800198a3  jz      loc_180019976
0x1800198a9  sub     eax, 29h ; ')'
0x1800198ac  jz      short loc_1800198FC
0x1800198ae  cmp     eax, 4A7h
0x1800198b3  jz      short loc_1800198BF
0x1800198b5  mov     ebx, 0C000000Dh
0x1800198ba  jmp     loc_180019996
0x1800198bf  mov     rax, [r13+rsi*8+10h]
0x1800198c4  mov     r8d, [rax]
0x1800198c7  mov     [rsp+1D0h+var_190], r8d
0x1800198cc  test    r8d, r8d
0x1800198cf  jz      loc_180019996
0x1800198d5  mov     edx, r8d; uBytes
0x1800198d8  mov     ecx, r9d; uFlags
0x1800198db  call    cs:__imp_LocalAlloc
0x1800198e1  mov     r15, rax
0x1800198e4  test    rax, rax
0x1800198e7  jz      loc_1800197BF
0x1800198ed  mov     rdx, [r13+rsi*8+10h]
0x1800198f2  mov     r8d, [rsp+1D0h+var_190]
0x1800198f7  jmp     loc_18001986A
0x1800198fc  mov     rax, [r13+rsi*8+10h]
0x180019901  mov     ecx, r9d; uFlags
0x180019904  mov     edx, [rax]
0x180019906  add     rdx, 2; uBytes
0x18001990a  call    cs:__imp_LocalAlloc
0x180019910  mov     [rsp+1D0h+var_158], rax
0x180019915  mov     rcx, rax; void *
0x180019918  test    rax, rax
0x18001991b  jz      loc_1800197BF
0x180019921  mov     rax, [r13+rsi*8+10h]
0x180019926  xor     edx, edx; Val
0x180019928  mov     r8d, [rax]
0x18001992b  add     r8, 2; Size
0x18001992f  call    memset_0
0x180019934  mov     rdx, [r13+rsi*8+10h]
0x180019939  mov     rcx, [rsp+1D0h+var_158]; void *
0x18001993e  mov     r8d, [rdx]; Size
0x180019941  mov     rdx, [rdx+8]; Src
0x180019945  call    memcpy_0
0x18001994a  mov     rax, [r13+rsi*8+10h]
0x18001994f  movzx   edx, word ptr [rsp+1D0h+var_1A0+2]
0x180019954  mov     r8, [rsp+1D0h+var_198]
0x180019959  mov     r9d, [rsp+1D0h+var_1A0+4]
0x18001995e  movzx   ecx, word ptr [rax]
0x180019961  mov     word ptr [rsp+1D0h+hMem+8], cx
0x180019966  add     cx, 2
0x18001996a  mov     word ptr [rsp+1D0h+var_1A0], cx
0x18001996f  mov     word ptr [rsp+1D0h+hMem+0Ah], cx
0x180019974  jmp     short loc_1800199AA
0x180019976  mov     rax, [r13+rsi*8+10h]
0x18001997b  mov     rcx, [rax+8]
0x18001997f  mov     eax, [rcx]
0x180019981  mov     [rsp+1D0h+var_184], eax
0x180019985  jmp     short loc_180019996
0x180019987  mov     rax, [r13+rsi*8+10h]
  ... truncated ...
```
