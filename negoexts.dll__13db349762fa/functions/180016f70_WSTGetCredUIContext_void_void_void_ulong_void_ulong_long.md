# WSTGetCredUIContext(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x180016f70`
- end: `0x180017b58`
- name: `?WSTGetCredUIContext@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `3048`
- prototype: `__int64 __fastcall(void **, unsigned __int64, void **, unsigned int, void **, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800027e4`
- `0x1800028a0`
- `0x1800058a4`
- `0x180008544`
- `0x180008c58`
- `0x18000ba90`
- `0x18000ca08`
- `0x18000ec28`
- `0x18000ff54`
- `0x18000ffa4`
- `0x1800157d8`
- `0x180016f70`
- `0x18001a390`
- `0x18001d138`
- `0x18001ece2`
- `0x18001ecee`
- `0x18001ed20`
- `0x18001edb0`
- `0x180020010`

## import_xrefs

- `ntdll!NtClose` at `0x180017a04`
- `ntdll!NtClose` at `0x180017a04`

## string_xrefs

- `0x18001715a`: `onecore\ds\security\protocols\negoexts\miscapi.cxx`

## pseudocode

```c
__int64 __fastcall WSTGetCredUIContext(
        void **a1,
        unsigned __int64 a2,
        void **a3,
        unsigned int a4,
        void **a5,
        unsigned int *a6,
        int *a7)
{
  unsigned __int64 v8; // rsi
  unsigned int *v9; // r15
  unsigned int *v10; // r13
  unsigned int *v11; // r14
  int v12; // ebx
  struct _LUID *v13; // r14
  unsigned __int64 v14; // r12
  void *v15; // rcx
  struct _WST_CONTEXT *v16; // rax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 *v20; // rsi
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int *v26; // rbx
  int v27; // ecx
  char *v28; // r13
  char *i; // r14
  struct _WST_SSP_PACKAGE *v30; // r10
  unsigned int *v31; // rax
  int v32; // eax
  unsigned int **v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  unsigned int *v36; // rax
  unsigned int **v37; // rcx
  unsigned __int64 v38; // rcx
  unsigned __int64 v39; // rcx
  void *v40; // rsp
  void *v41; // rsp
  unsigned int *v42; // rax
  size_t v43; // rsi
  __int64 v44; // rcx
  unsigned __int64 v45; // rcx
  void *v46; // rsp
  void *v47; // rsp
  unsigned int *v48; // rax
  __int64 v49; // rcx
  unsigned int *v50; // r9
  void **v51; // r14
  _WORD *v52; // rcx
  unsigned __int64 v53; // r14
  __int64 v54; // rcx
  unsigned __int64 v55; // rcx
  void *v56; // rsp
  void *v57; // rsp
  unsigned int *v58; // rax
  struct _WST_CONTEXT *v59; // r13
  void ***j; // rsi
  void **v61; // rax
  void **v62; // r14
  unsigned int v64; // [rsp+40h] [rbp+0h] BYREF
  void *Src; // [rsp+48h] [rbp+8h]
  void *v66[2]; // [rsp+50h] [rbp+10h] BYREF
  unsigned int *v67; // [rsp+60h] [rbp+20h]
  struct _WST_SSP_PACKAGE *v68; // [rsp+68h] [rbp+28h]
  int v69; // [rsp+70h] [rbp+30h]
  void *v70; // [rsp+78h] [rbp+38h] BYREF
  unsigned int *v71; // [rsp+80h] [rbp+40h]
  int v72; // [rsp+88h] [rbp+48h]
  unsigned int *v73; // [rsp+90h] [rbp+50h]
  HANDLE Handle; // [rsp+98h] [rbp+58h] BYREF
  struct _WST_CONTEXT *v75; // [rsp+A0h] [rbp+60h]
  __int128 v76; // [rsp+A8h] [rbp+68h]
  __int64 v77; // [rsp+B8h] [rbp+78h]
  struct _LUID v78[2]; // [rsp+C0h] [rbp+80h] BYREF
  __int128 v79; // [rsp+D0h] [rbp+90h]
  __int128 v80; // [rsp+E0h] [rbp+A0h]
  struct _WST_CONTEXT *v81; // [rsp+F0h] [rbp+B0h]
  struct _WST_SSP_PACKAGE *v82; // [rsp+100h] [rbp+C0h]
  __int128 v83; // [rsp+118h] [rbp+D8h] BYREF
  __int64 v84; // [rsp+128h] [rbp+E8h]

  v8 = a2;
  *(_OWORD *)&v78[0].LowPart = 0;
  v79 = 0;
  v75 = 0;
  v70 = 0;
  v9 = 0;
  v68 = 0;
  *(_OWORD *)v66 = 0;
  v10 = 0;
  v67 = 0;
  v11 = 0;
  Src = 0;
  Handle = 0;
  v80 = SEC_WINNT_AUTH_DATA_TYPE_CSP_DATA;
  v76 = SEC_WINNT_AUTH_DATA_TYPE_PASSWORD;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids);
  v66[1] = v66;
  v66[0] = v66;
  if ( a4 < 0x28 || *(_DWORD *)v8 != 2 || *(_WORD *)(v8 + 4) < 0x28u )
  {
    v12 = -1073741811;
    goto LABEL_149;
  }
  v12 = ((__int64 (__fastcall *)(struct _LUID *, unsigned __int64, void **))basessp::WSTGlobalLsaFunctions->GetClientInfo)(
          v78,
          a2,
          a3);
  if ( v12 >= 0 )
  {
    v13 = (struct _LUID *)(v8 + 32);
    a2 = *(unsigned int *)(v8 + 36);
    if ( *(_QWORD *)(v8 + 32) && *(_QWORD *)(v8 + 32) != *(_QWORD *)v78 )
    {
      if ( v78[0].LowPart != 999 || v78[0].HighPart )
      {
        v12 = -1073741727;
        goto LABEL_14;
      }
      v83 = 0;
      v84 = 0;
      if ( !((unsigned __int8 (__fastcall *)(__int128 *))basessp::WSTGlobalLsaFunctions->GetCallInfo)(&v83) )
      {
        v12 = -1073741595;
LABEL_14:
        v11 = 0;
        goto LABEL_149;
      }
      if ( (BYTE8(v83) & 0x40) != 0 )
      {
        v12 = -1073741637;
        goto LABEL_14;
      }
      v78[0] = *v13;
      v12 = ((__int64 (__fastcall *)(unsigned __int64, HANDLE *))basessp::WSTGlobalLsaFunctions->OpenTokenByLogonId)(
              v8 + 32,
              &Handle);
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_DDDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            (unsigned int)&WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids,
            v12,
            *(_DWORD *)(v8 + 36),
            v13->LowPart,
            (__int64)"onecore\\ds\\security\\protocols\\negoexts\\miscapi.cxx",
            90);
        goto LABEL_14;
      }
    }
    v14 = 8;
    v77 = 8;
    v15 = *(void **)(v8 + 8);
    if ( !v15 )
    {
      a2 = (unsigned __int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids);
      goto LABEL_128;
    }
    v16 = WSTLocateAndReferenceContextByPointer(v15, v78);
    a3 = (void **)v16;
    v75 = v16;
    v81 = v16;
    if ( !v16 )
    {
      v12 = -1073740755;
      a2 = (unsigned __int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids,
          *(_QWORD *)(v8 + 8));
      goto LABEL_14;
    }
    if ( !*((_DWORD *)v16 + 39) )
    {
      v12 = -1073741811;
      v17 = WPP_GLOBAL_Control;
      a2 = (unsigned __int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v18 = 21;
      goto LABEL_31;
    }
    v19 = *((_QWORD *)v16 + 3);
    if ( v78[0].LowPart != *(_DWORD *)(v19 + 40) || v78[0].HighPart != *(_DWORD *)(v19 + 44) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids);
      v12 = -1073741816;
      v11 = 0;
      goto LABEL_149;
    }
    v20 = (__int64 *)(v8 + 16);
    a2 = SEC_WINNT_AUTH_DATA_TYPE_CSP_DATA;
    v21 = *v20 - SEC_WINNT_AUTH_DATA_TYPE_CSP_DATA;
    if ( *v20 == (_QWORD)SEC_WINNT_AUTH_DATA_TYPE_CSP_DATA )
    {
      v22 = v20[1];
      *((_QWORD *)&v80 + 1) = _mm_srli_si128((__m128i)SEC_WINNT_AUTH_DATA_TYPE_CSP_DATA, 8).m128i_u64[0];
      v21 = v22 - *((_QWORD *)&v80 + 1);
    }
    if ( v21 )
    {
      v23 = *v20;
      *(_QWORD *)&v76 = SEC_WINNT_AUTH_DATA_TYPE_PASSWORD;
      v24 = v23 - SEC_WINNT_AUTH_DATA_TYPE_PASSWORD;
      if ( !v24 )
      {
        v25 = v20[1];
        *((_QWORD *)&v76 + 1) = _mm_srli_si128((__m128i)SEC_WINNT_AUTH_DATA_TYPE_PASSWORD, 8).m128i_u64[0];
        v24 = v25 - *((_QWORD *)&v76 + 1);
      }
      if ( v24 )
      {
        v26 = 0;
        v73 = 0;
        v27 = 0;
        v64 = 0;
        v69 = 0;
        *(_QWORD *)&v80 = v20;
        v28 = (char *)v16 + 56;
        *(_QWORD *)&v76 = (char *)v16 + 56;
        for ( i = (char *)*((_QWORD *)v16 + 7); ; i = *(char **)i )
        {
          v71 = (unsigned int *)i;
          if ( i == v28 )
            goto LABEL_76;
          if ( v68 )
            WSTDereferencePackage(v68);
          v30 = WSTLocatePackageByAuthScheme((struct _GUID *)(i + 24));
          v68 = v30;
          v82 = v30;
          if ( !v30 )
            goto LABEL_56;
          if ( !v26 )
          {
            v31 = (unsigned int *)basessp::BaseSSP::WSTAllocate(WSTGlobalBaseSSP, 0x20u);
            v26 = v31;
            if ( !v31 )
              goto LABEL_47;
            v73 = v31;
            *((_QWORD *)v31 + 1) = v31;
            *(_QWORD *)v31 = v31;
            v30 = v68;
          }
          v32 = (*((__int64 (__fastcall **)(__int64, __int64 *, unsigned int *, unsigned int *))v30 + 36))(
                  *((_QWORD *)i + 5),
                  v20,
                  v26 + 4,
                  v26 + 6);
          v72 = v32;
          a2 = (unsigned __int64)&WPP_GLOBAL_Control;
          if ( v32 < 0 )
            break;
          v33 = (unsigned int **)v66[1];
          if ( *(void ***)v66[1] != v66 )
            goto LABEL_175;
          v27 = v64 + 1;
          v64 = v27;
          v69 = v27;
          a2 = (unsigned __int64)v66;
          *(_QWORD *)v26 = v66;
          *((_QWORD *)v26 + 1) = v33;
          *v33 = v26;
          v66[1] = v26;
          v14 += v26[4] + 8LL;
          v77 = v14;
          v26 = 0;
          v73 = 0;
LABEL_57:
          ;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids,
            (unsigned int)v32,
            *((_DWORD *)v68 + 6));
LABEL_56:
        v27 = v64;
        goto LABEL_57;
      }
    }
    v34 = *v20 - SEC_WINNT_AUTH_DATA_TYPE_CSP_DATA;
    if ( *v20 == (_QWORD)SEC_WINNT_AUTH_DATA_TYPE_CSP_DATA )
      v34 = v20[1] - *((_QWORD *)&v80 + 1);
    if ( !v34 && (*((_BYTE *)a3 + 260) & 1) != 0 )
    {
      v12 = -1073740755;
      v17 = WPP_GLOBAL_Control;
      a2 = (unsigned __int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v18 = 23;
      goto LABEL_31;
    }
    v35 = *v20 - v76;
    if ( *v20 == (_QWORD)v76 )
      v35 = v20[1] - *((_QWORD *)&v76 + 1);
    if ( !v35 && (*((_BYTE *)a3 + 260) & 3) == 3 )
    {
      v12 = -1073740755;
      v17 = WPP_GLOBAL_Control;
      a2 = (unsigned __int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v18 = 24;
LABEL_31:
        WPP_SF_(v17[2], v18, &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids);
        goto LABEL_14;
      }
LABEL_48:
      v11 = (unsigned int *)Src;
      goto LABEL_149;
    }
    v36 = (unsigned int *)basessp::BaseSSP::WSTAllocate(WSTGlobalBaseSSP, 0x20u);
    if ( !v36 )
    {
      v12 = -1073741801;
      goto LABEL_14;
    }
    *((_QWORD *)v36 + 1) = v36;
    *(_QWORD *)v36 = v36;
    v37 = (unsigned int **)v66[1];
    if ( *(void ***)v66[1] != v66 )
LABEL_175:
      __fastfail(3u);
    a2 = 1;
    v64 = 1;
    a3 = v66;
    *(_QWORD *)v36 = v66;
    *((_QWORD *)v36 + 1) = v37;
    *v37 = v36;
    v66[1] = v36;
    v14 = v36[4] + 16LL;
    v26 = 0;
    v27 = 1;
LABEL_76:
    if ( !v27 )
    {
      v12 = -1073740755;
      a2 = (unsigned __int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids);
      goto LABEL_48;
    }
    if ( v26 )
      WSTFree(v26);
    if ( v14 > 0xFFFF0000 )
    {
LABEL_83:
      v12 = -1073741637;
      goto LABEL_48;
    }
    v10 = 0;
    v67 = 0;
    if ( (_DWORD)v14
      && (unsigned int)v14 <= (unsigned __int64)g_ulMaxStackAllocSize
      && (unsigned __int64)(unsigned int)v14 + g_ulAdditionalProbeSize + 8 >= (unsigned int)v14 )
    {
      if ( (unsigned int)VerifyStackAvailable() )
      {
        v38 = (unsigned int)v14 + 23LL;
        if ( v38 <= (unsigned __int64)(unsigned int)v14 + 8 )
          v38 = 0xFFFFFFFFFFFFFF0LL;
        v39 = v38 & 0xFFFFFFFFFFFFFFF0uLL;
        v40 = alloca(v39);
        v41 = alloca(v39);
        v10 = &v64;
        v67 = &v64;
      }
      if ( !v10 )
      {
LABEL_94:
        if ( (unsigned __int64)(unsigned int)v14 + 8 >= (unsigned int)v14 )
        {
          v42 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
          v10 = v42;
          v67 = v42;
          if ( v42 )
          {
            *v42 = 1885431112;
            v10 = v42 + 2;
            v67 = v42 + 2;
          }
        }
        if ( !v10 )
          goto LABEL_47;
LABEL_98:
        memset_0(v10, 0, (unsigned int)v14);
        a2 = v64;
        v43 = 8LL * v64;
        v11 = 0;
        Src = 0;
        if ( v43 && v43 <= g_ulMaxStackAllocSize && v43 + g_ulAdditionalProbeSize + 8 >= v43 )
        {
          if ( (unsigned int)VerifyStackAvailable() )
          {
            v44 = v43 + 23;
            if ( v43 + 23 <= v43 + 8 )
              v44 = 0xFFFFFFFFFFFFFF0LL;
            v45 = v44 & 0xFFFFFFFFFFFFFFF0uLL;
            v46 = alloca(v45);
            v47 = alloca(v45);
            v11 = &v64;
            Src = &v64;
          }
          if ( !v11 )
            goto LABEL_108;
          *v11 = 1801679955;
          v11 += 2;
          Src = v11;
        }
        if ( v11 )
        {
LABEL_113:
          v49 = v64;
          if ( v64 >= 0xFFFF )
          {
            v12 = -1073741637;
            goto LABEL_149;
          }
          *((_WORD *)v10 + 2) = v64;
          *v10 = 8;
          v50 = &v10[2 * v49 + 2];
          v51 = (void **)v66[0];
          while ( 1 )
          {
            v71 = v50;
            if ( v51 == v66 || !(_DWORD)v49 )
              break;
            if ( *((_DWORD *)v51 + 4) >= 0xFFFFu )
              goto LABEL_83;
            v52 = Src;
            *(_DWORD *)Src = (_DWORD)v50 - (_DWORD)v10;
            v52[2] = *((_WORD *)v51 + 8);
            memcpy_0(v50, v51[3], *((unsigned int *)v51 + 4));
            v50 = (unsigned int *)((char *)v71 + *((unsigned int *)v51 + 4));
            v51 = (void **)*v51;
            LODWORD(v49) = v64;
          }
          memcpy_0(v10 + 2, Src, v43);
LABEL_128:
          v53 = (unsigned int)(unsigned __int16)v14 + 24;
          v9 = 0;
          if ( v53 <= g_ulMaxStackAllocSize && v53 + g_ulAdditionalProbeSize + 8 >= v53 )
          {
            if ( (unsigned int)VerifyStackAvailable() )
            {
              v54 = v53 + 23;
              if ( v53 + 23 <= v53 + 8 )
                v54 = 0xFFFFFFFFFFFFFF0LL;
              v55 = v54 & 0xFFFFFFFFFFFFFFF0uLL;
              v56 = alloca(v55);
              v57 = alloca(v55);
              v9 = &v64;
            }
            if ( !v9 )
            {
LABEL_137:
              if ( v53 + 8 >= v53 )
              {
                v58 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
                v9 = v58;
                if ( v58 )
                {
                  *v58 = 1885431112;
                  v9 = v58 + 2;
                }
              }
              if ( v9 )
                goto LABEL_141;
LABEL_47:
              v12 = -1073741801;
              goto LABEL_48;
            }
            *v9 = 1801679955;
            v9 += 2;
          }
          if ( v9 )
          {
LABEL_141:
            memset_0(v9, 0, (unsigned int)v53);
            *v9 = 2;
            *((_WORD *)v9 + 2) = 24;
            v9[2] = v14;
            v9[3] = 24;
            *((_QWORD *)v9 + 2) = 0;
            if ( v10 )
              memcpy_0(v9 + 6, v10, (unsigned __int16)v14);
            v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, void **))basessp::WSTGlobalLsaFunctions->AllocateClientBuffer)(
                    0,
                    (unsigned int)v53,
                    &v70);
            if ( v12 >= 0 )
            {
              if ( !Handle
                || (v12 = ((__int64 (__fastcall *)(HANDLE, unsigned int *))basessp::WSTGlobalLsaFunctions->DuplicateHandle)(
                            Handle,
                            v9 + 4),
                    v12 >= 0) )
              {
                v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, void *, unsigned int *))basessp::WSTGlobalLsaFunctions->CopyToClientBuffer)(
                        0,
                        (unsigned int)v53,
                        v70,
                        v9);
                if ( v12 >= 0 )
                {
                  *a5 = v70;
                  v70 = 0;
                  *a6 = v53;
                }
              }
            }
            goto LABEL_48;
          }
          goto LABEL_137;
        }
LABEL_108:
        if ( v43 + 8 >= v43 )
        {
          v48 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
          v11 = v48;
          Src = v48;
          if ( v48 )
          {
            *v48 = 1885431112;
            v11 = v48 + 2;
            Src = v48 + 2;
          }
        }
        if ( !v11 )
        {
          v12 = -1073741801;
          goto LABEL_149;
        }
        goto LABEL_113;
      }
      *v10 = 1801679955;
      v10 += 2;
      v67 = v10;
    }
    if ( v10 )
      goto LABEL_98;
    goto LABEL_94;
  }
LABEL_149:
  if ( Handle )
    NtClose(Handle);
  v59 = v75;
  if ( v75 )
    WSTDereferenceContext(v75);
  if ( v67 && *(v67 - 2) == 1885431112 )
    ((void (__fastcall *)(unsigned int *, unsigned __int64, void **))g_pfnFree)(v67 - 2, a2, a3);
  if ( v11 && *(v11 - 2) == 1885431112 )
    ((void (__fastcall *)(unsigned int *, unsigned __int64, void **))g_pfnFree)(v11 - 2, a2, a3);
  if ( v9 && *(v9 - 2) == 1885431112 )
    ((void (__fastcall *)(unsigned int *, unsigned __int64, void **))g_pfnFree)(v9 - 2, a2, a3);
  if ( v68 )
    WSTDereferencePackage(v68);
  for ( j = (void ***)v66[0]; j != (void ***)v66; j = (void ***)*v62 )
  {
    v61 = *j;
    if ( (*j)[1] != j )
      goto LABEL_175;
    v62 = j[1];
    if ( *v62 != j )
      goto LABEL_175;
    *v62 = v61;
    v61[1] = v62;
    WSTFree(j[3]);
    WSTFree(j);
  }
  if ( v70 )
    ((void (__fastcall *)(_QWORD, void *, void **))basessp::WSTGlobalLsaFunctions->FreeClientBuffer)(0, v70, a3);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_Dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids,
      (unsigned int)v12,
      v59);
  *a7 = v12;
  return 0;
}

```

## disassembly

```asm
0x180016f70  push    rbp
0x180016f72  push    rbx
0x180016f73  push    rsi
0x180016f74  push    rdi
0x180016f75  push    r12
0x180016f77  push    r13
0x180016f79  push    r14
0x180016f7b  push    r15
0x180016f7d  sub     rsp, 168h
0x180016f84  lea     rbp, [rsp+40h]
0x180016f89  movaps  [rbp+160h+var_50], xmm6
0x180016f90  movaps  [rbp+160h+var_60], xmm7
0x180016f97  mov     rax, cs:__security_cookie
0x180016f9e  xor     rax, rbp
0x180016fa1  mov     [rbp+160h+var_70], rax
0x180016fa8  mov     ebx, r9d
0x180016fab  mov     rsi, rdx
0x180016fae  xorps   xmm0, xmm0
0x180016fb1  movups  xmmword ptr [rbp+160h+var_E0.LowPart], xmm0
0x180016fb8  movups  [rbp+160h+var_D0], xmm0
0x180016fbf  xor     edi, edi
0x180016fc1  mov     [rbp+160h+var_100], rdi
0x180016fc5  mov     [rbp+160h+var_128], rdi
0x180016fc9  mov     r15d, edi
0x180016fcc  mov     [rbp+160h+var_138], rdi
0x180016fd0  movups  xmmword ptr [rbp+160h+var_150], xmm0
0x180016fd4  mov     r13d, edi
0x180016fd7  mov     [rbp+160h+var_140], rdi
0x180016fdb  mov     r14d, edi
0x180016fde  mov     [rbp+160h+Src], rdi
0x180016fe2  mov     [rbp+160h+Handle], rdi
0x180016fe6  movups  xmm6, cs:SEC_WINNT_AUTH_DATA_TYPE_CSP_DATA
0x180016fed  movups  [rbp+160h+var_C0], xmm6
0x180016ff4  movups  xmm7, cs:SEC_WINNT_AUTH_DATA_TYPE_PASSWORD
0x180016ffb  movups  [rbp+160h+var_F8], xmm7
0x180016fff  lea     r12, WPP_GLOBAL_Control
0x180017006  mov     rcx, cs:WPP_GLOBAL_Control
0x18001700d  cmp     rcx, r12
0x180017010  jz      short loc_18001702B
0x180017012  test    byte ptr [rcx+1Ch], 8
0x180017016  jz      short loc_18001702B
0x180017018  lea     edx, [rdi+12h]
0x18001701b  lea     r8, WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids
0x180017022  mov     rcx, [rcx+10h]
0x180017026  call    WPP_SF_
0x18001702b  lea     rax, [rbp+160h+var_150]
0x18001702f  mov     [rbp+160h+var_150+8], rax
0x180017033  lea     rax, [rbp+160h+var_150]
0x180017037  mov     [rbp+160h+var_150], rax
0x18001703b  mov     eax, 28h ; '('
0x180017040  cmp     ebx, eax
0x180017042  jb      loc_1800179EF
0x180017048  cmp     dword ptr [rsi], 2
0x18001704b  jnz     loc_1800179EF
0x180017051  cmp     [rsi+4], ax
0x180017055  jb      loc_1800179EF
0x18001705b  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x180017062  lea     rcx, [rbp+160h+var_E0]
0x180017069  mov     rax, [rax+80h]
0x180017070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017075  mov     ebx, eax
0x180017077  test    eax, eax
0x180017079  js      loc_1800179F4
0x18001707f  lea     r14, [rsi+20h]
0x180017083  mov     ecx, [r14]
0x180017086  mov     edx, [rsi+24h]
0x180017089  mov     eax, edx
0x18001708b  or      eax, ecx
0x18001708d  jz      loc_180017196
0x180017093  cmp     ecx, [rbp+160h+var_E0.LowPart]
0x180017099  jnz     short loc_1800170A7
0x18001709b  cmp     edx, [rbp+160h+var_E0.HighPart]
0x1800170a1  jz      loc_180017196
0x1800170a7  cmp     [rbp+160h+var_E0.LowPart], 3E7h
0x1800170b1  jnz     loc_18001718C
0x1800170b7  cmp     [rbp+160h+var_E0.HighPart], edi
0x1800170bd  jnz     loc_18001718C
0x1800170c3  xorps   xmm0, xmm0
0x1800170c6  xor     eax, eax
0x1800170c8  movups  [rbp+160h+var_88], xmm0
0x1800170cf  mov     [rbp+160h+var_78], rax
0x1800170d6  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x1800170dd  lea     rcx, [rbp+160h+var_88]
0x1800170e4  mov     rax, [rax+0C0h]
0x1800170eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170f0  test    al, al
0x1800170f2  jnz     short loc_180017101
0x1800170f4  mov     ebx, 0C00000E5h
0x1800170f9  mov     r14, rdi
0x1800170fc  jmp     loc_1800179F4
0x180017101  test    byte ptr [rbp+160h+var_88+8], 40h
0x180017108  jz      short loc_180017111
0x18001710a  mov     ebx, 0C00000BBh
0x18001710f  jmp     short loc_1800170F9
0x180017111  mov     rax, [r14]
0x180017114  mov     qword ptr [rbp+160h+var_E0.LowPart], rax
0x18001711b  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x180017122  lea     rdx, [rbp+160h+Handle]
0x180017126  mov     rcx, r14
0x180017129  mov     rax, [rax+170h]
0x180017130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017135  mov     ebx, eax
0x180017137  test    eax, eax
0x180017139  jns     short loc_180017196
0x18001713b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017142  cmp     rcx, r12
0x180017145  jz      short loc_1800170F9
0x180017147  test    byte ptr [rcx+1Ch], 1
0x18001714b  jz      short loc_1800170F9
0x18001714d  mov     edx, 13h
0x180017152  mov     [rsp+1A0h+var_168], 25Ah
0x18001715a  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\protocols\\negoe"...
0x180017161  mov     [rsp+1A0h+var_170], rax
0x180017166  mov     eax, [r14]
0x180017169  mov     [rsp+1A0h+var_178], eax
0x18001716d  mov     eax, [rsi+24h]
0x180017170  mov     dword ptr [rsp+1A0h+var_180], eax
0x180017174  mov     r9d, ebx
0x180017177  lea     r8, WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids
0x18001717e  mov     rcx, [rcx+10h]
0x180017182  call    WPP_SF_DDDsd
0x180017187  jmp     loc_1800170F9
0x18001718c  mov     ebx, 0C0000061h
0x180017191  jmp     loc_1800170F9
0x180017196  mov     r12d, 8
0x18001719c  mov     [rbp+160h+var_E8], r12
0x1800171a0  mov     rcx, [rsi+8]; void *
0x1800171a4  test    rcx, rcx
0x1800171a7  jz      loc_18001784B
0x1800171ad  lea     rdx, [rbp+160h+var_E0]; struct _LUID *
0x1800171b4  call    ?WSTLocateAndReferenceContextByPointer@@YAPEAU_WST_CONTEXT@@PEAXPEAU_LUID@@@Z; WSTLocateAndReferenceContextByPointer(void *,_LUID *)
0x1800171b9  mov     r8, rax
0x1800171bc  mov     [rbp+160h+var_100], rax
0x1800171c0  mov     [rbp+160h+var_B0], rax
0x1800171c7  test    rax, rax
0x1800171ca  jnz     short loc_18001720E
0x1800171cc  mov     ebx, 0C000042Dh
0x1800171d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171d8  lea     rdx, WPP_GLOBAL_Control
0x1800171df  cmp     rcx, rdx
0x1800171e2  jz      loc_1800170F9
0x1800171e8  test    byte ptr [rcx+1Ch], 4
0x1800171ec  jz      loc_1800170F9
0x1800171f2  lea     edx, [rax+14h]
0x1800171f5  mov     r9, [rsi+8]
0x1800171f9  lea     r8, WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids
0x180017200  mov     rcx, [rcx+10h]
0x180017204  call    WPP_SF_q
0x180017209  jmp     loc_1800170F9
0x18001720e  cmp     [rax+9Ch], edi
0x180017214  jnz     short loc_180017256
0x180017216  mov     ebx, 0C000000Dh
0x18001721b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017222  lea     rdx, WPP_GLOBAL_Control
0x180017229  cmp     rcx, rdx
0x18001722c  jz      loc_1800170F9
0x180017232  test    byte ptr [rcx+1Ch], 1
0x180017236  jz      loc_1800170F9
0x18001723c  mov     edx, 15h
0x180017241  lea     r8, WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids
0x180017248  mov     rcx, [rcx+10h]
0x18001724c  call    WPP_SF_
0x180017251  jmp     loc_1800170F9
0x180017256  mov     rcx, [rax+18h]
0x18001725a  mov     rax, qword ptr [rbp+160h+var_E0.LowPart]
0x180017261  cmp     eax, [rcx+28h]
0x180017264  jnz     loc_180017810
0x18001726a  mov     eax, [rbp+160h+var_E0.HighPart]
0x180017270  cmp     eax, [rcx+2Ch]
0x180017273  jnz     loc_180017810
0x180017279  add     rsi, 10h
0x18001727d  mov     rcx, [rsi]
0x180017280  movq    rdx, xmm6
0x180017285  sub     rcx, rdx
0x180017288  jnz     short loc_1800172A2
0x18001728a  mov     rcx, [rsi+8]
0x18001728e  psrldq  xmm6, 8
0x180017293  movq    rax, xmm6
0x180017298  mov     qword ptr [rbp+160h+var_C0+8], rax
0x18001729f  sub     rcx, rax
0x1800172a2  test    rcx, rcx
0x1800172a5  jz      loc_180017474
0x1800172ab  mov     rcx, [rsi]
0x1800172ae  movq    rax, xmm7
0x1800172b3  mov     qword ptr [rbp+160h+var_F8], rax
0x1800172b7  sub     rcx, rax
0x1800172ba  jnz     short loc_1800172D1
0x1800172bc  mov     rcx, [rsi+8]
0x1800172c0  psrldq  xmm7, 8
0x1800172c5  movq    rax, xmm7
0x1800172ca  mov     qword ptr [rbp+160h+var_F8+8], rax
0x1800172ce  sub     rcx, rax
0x1800172d1  test    rcx, rcx
0x1800172d4  jz      loc_180017474
0x1800172da  mov     rbx, rdi
0x1800172dd  mov     [rbp+160h+var_110], rbx
0x1800172e1  mov     ecx, edi
0x1800172e3  mov     [rbp+160h+var_160], ecx
0x1800172e6  mov     [rbp+160h+var_130], ecx
0x1800172e9  mov     qword ptr [rbp+160h+var_C0], rsi
0x1800172f0  lea     r13, [r8+38h]
0x1800172f4  mov     qword ptr [rbp+160h+var_F8], r13
0x1800172f8  mov     r14, [r13+0]
0x1800172fc  mov     [rbp+160h+var_120], r14
0x180017300  cmp     r14, r13
0x180017303  jz      loc_180017577
0x180017309  mov     rax, [rbp+160h+var_138]
0x18001730d  test    rax, rax
0x180017310  jz      short loc_18001731A
0x180017312  mov     rcx, rax; struct _WST_SSP_PACKAGE *
0x180017315  call    ?WSTDereferencePackage@@YAXPEAU_WST_SSP_PACKAGE@@@Z; WSTDereferencePackage(_WST_SSP_PACKAGE *)
0x18001731a  lea     rcx, [r14+18h]; struct _GUID *
0x18001731e  call    ?WSTLocatePackageByAuthScheme@@YAPEAU_WST_SSP_PACKAGE@@PEAU_GUID@@@Z; WSTLocatePackageByAuthScheme(_GUID *)
0x180017323  mov     r10, rax
0x180017326  mov     [rbp+160h+var_138], rax
0x18001732a  mov     [rbp+160h+var_A0], rax
0x180017331  test    rax, rax
0x180017334  jz      loc_180017469
0x18001733a  test    rbx, rbx
0x18001733d  jnz     short loc_180017373
0x18001733f  lea     edx, [rbx+20h]; unsigned __int64
0x180017342  mov     rcx, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180017349  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18001734e  mov     rbx, rax
0x180017351  test    rax, rax
0x180017354  jnz     short loc_180017364
0x180017356  mov     ebx, 0C0000017h
0x18001735b  mov     r14, [rbp+160h+Src]
0x18001735f  jmp     loc_1800179F4
0x180017364  mov     [rbp+160h+var_110], rax
0x180017368  mov     [rax+8], rax
0x18001736c  mov     [rax], rax
0x18001736f  mov     r10, [rbp+160h+var_138]
0x180017373  lea     r9, [rbx+18h]
0x180017377  lea     r8, [rbx+10h]
0x18001737b  mov     rdx, rsi
0x18001737e  mov     rcx, [r14+28h]
0x180017382  mov     rax, [r10+120h]
0x180017389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001738e  mov     r9d, eax
0x180017391  mov     [rbp+160h+var_118], eax
0x180017394  mov     ecx, [rbp+160h+var_160]
0x180017397  lea     rdx, WPP_GLOBAL_Control
0x18001739e  mov     r10, [rbp+160h+var_138]
0x1800173a2  jmp     short loc_1800173F3
0x1800173a4  mov     r9d, eax
0x1800173a7  mov     [rbp+160h+var_118], eax
0x1800173aa  xor     edi, edi
0x1800173ac  lea     rdx, WPP_GLOBAL_Control
0x1800173b3  mov     rax, [rbp+160h+var_B0]
0x1800173ba  mov     [rbp+160h+var_100], rax
0x1800173be  mov     r15d, edi
0x1800173c1  mov     r10, [rbp+160h+var_A0]
0x1800173c8  mov     [rbp+160h+var_138], r10
0x1800173cc  mov     rbx, [rbp+160h+var_110]
0x1800173d0  mov     ecx, [rbp+160h+var_130]
0x1800173d3  mov     [rbp+160h+var_160], ecx
0x1800173d6  mov     r12, [rbp+160h+var_E8]
0x1800173da  mov     eax, edi
0x1800173dc  mov     [rbp+160h+var_140], rax
0x1800173e0  mov     [rbp+160h+Src], rax
0x1800173e4  mov     rsi, qword ptr [rbp+160h+var_C0]
0x1800173eb  mov     r14, [rbp+160h+var_120]
0x1800173ef  mov     r13, qword ptr [rbp+160h+var_F8]
0x1800173f3  test    r9d, r9d
0x1800173f6  js      short loc_18001743A
0x1800173f8  mov     rax, [rbp+160h+var_150+8]
0x1800173fc  lea     rdx, [rbp+160h+var_150]
0x180017400  cmp     [rax], rdx
0x180017403  jnz     loc_180017B51
0x180017409  inc     ecx
0x18001740b  mov     [rbp+160h+var_160], ecx
0x18001740e  mov     [rbp+160h+var_130], ecx
0x180017411  lea     rdx, [rbp+160h+var_150]
0x180017415  mov     [rbx], rdx
0x180017418  mov     [rbx+8], rax
0x18001741c  mov     [rax], rbx
0x18001741f  mov     [rbp+160h+var_150+8], rbx
0x180017423  mov     eax, [rbx+10h]
0x180017426  add     r12, 8
0x18001742a  add     r12, rax
0x18001742d  mov     [rbp+160h+var_E8], r12
0x180017431  mov     rbx, rdi
0x180017434  mov     [rbp+160h+var_110], rbx
0x180017438  jmp     short loc_18001746C
0x18001743a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017441  cmp     rcx, rdx
0x180017444  jz      short loc_180017469
0x180017446  test    byte ptr [rcx+1Ch], 2
0x18001744a  jz      short loc_180017469
0x18001744c  mov     edx, 19h
0x180017451  mov     eax, [r10+18h]
0x180017455  mov     dword ptr [rsp+1A0h+var_180], eax
0x180017459  lea     r8, WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids
0x180017460  mov     rcx, [rcx+10h]
0x180017464  call    WPP_SF_Dd
0x180017469  mov     ecx, [rbp+160h+var_160]
0x18001746c  mov     r14, [r14]
0x18001746f  jmp     loc_1800172FC
0x180017474  mov     rax, [rsi]
  ... truncated ...
```
