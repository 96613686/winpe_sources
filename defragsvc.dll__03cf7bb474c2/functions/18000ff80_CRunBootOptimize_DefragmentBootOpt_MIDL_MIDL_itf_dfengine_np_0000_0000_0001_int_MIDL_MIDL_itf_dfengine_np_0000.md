# CRunBootOptimize::_DefragmentBootOpt(__MIDL___MIDL_itf_dfengine_np_0000_0000_0001,int,__MIDL___MIDL_itf_dfengine_np_0000_0000_0001,int,IVolume *,IFreeSpaceManager *)

- ea: `0x18000ff80`
- end: `0x180010b4e`
- name: `?_DefragmentBootOpt@CRunBootOptimize@@AEAAJU__MIDL___MIDL_itf_dfengine_np_0000_0000_0001@@H0HPEAUIVolume@@PEAUIFreeSpaceManager@@@Z`
- size: `3022`
- prototype: `__int64 __fastcall(CDefragOperation *, __int128 *, int, __int128 *, int, struct IVolume *, struct IFreeSpaceManager *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e4e0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18000c644`
- `0x18000ff80`
- `0x180010b54`
- `0x180010bc0`
- `0x180031a5c`
- `0x180038b40`
- `0x180038c3c`
- `0x18004bc88`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001064b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001064b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800108e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010ab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800108e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010ab1`

## string_xrefs

- `0x1800108be`: `Error retrieving file path`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRunBootOptimize::_DefragmentBootOpt(
        CDefragOperation *a1,
        __int128 *a2,
        int a3,
        __int128 *a4,
        int a5,
        struct IVolume *a6,
        struct IFreeSpaceManager *a7)
{
  CDefragOperation *v7; // r12
  struct IVolume *v8; // rbx
  struct IFreeSpaceManager *v9; // rdi
  __int16 v11; // ax
  int v12; // esi
  struct IFileOperation *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 (__fastcall *v18)(struct IVolume *, __int64, __int64 *); // rsi
  __int64 v19; // rcx
  __int64 (__fastcall *v20)(struct IVolume *, __int64, __int64 *); // rsi
  __int64 v21; // rcx
  __int64 (__fastcall *v22)(struct IVolume *, _QWORD, __int64 *); // rsi
  __int64 v23; // rcx
  unsigned int *v24; // r15
  __int64 (__fastcall *v25)(struct IVolume *, _QWORD, struct IFileOperation *, struct IFileOperation **); // rax
  bool v26; // sf
  char *v27; // r13
  __int64 v28; // r8
  unsigned int v29; // r12d
  __int64 (__fastcall *v30)(struct IVolume *, _QWORD, struct IFileOperation *, struct IFileOperation **); // rax
  int v31; // ecx
  int v32; // r12d
  unsigned int *v33; // rax
  __int64 v34; // r8
  int v35; // eax
  BOOL v36; // eax
  int v37; // eax
  const wchar_t *v38; // r9
  __int16 v39; // ax
  void *v40; // rcx
  void *v41; // rcx
  CSxGlobalTracer *v42; // rcx
  __int64 v43; // [rsp+48h] [rbp-C0h] BYREF
  struct IFileOperation *v44; // [rsp+50h] [rbp-B8h] BYREF
  int v45; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v46; // [rsp+5Ch] [rbp-ACh] BYREF
  int v47; // [rsp+60h] [rbp-A8h] BYREF
  __int16 v48; // [rsp+64h] [rbp-A4h]
  __int16 v49; // [rsp+66h] [rbp-A2h]
  __int64 v50; // [rsp+98h] [rbp-70h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v52; // [rsp+A8h] [rbp-60h]
  int v53; // [rsp+ACh] [rbp-5Ch]
  unsigned int v54; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v55; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v56; // [rsp+C0h] [rbp-48h] BYREF
  int v57; // [rsp+C8h] [rbp-40h] BYREF
  int v58; // [rsp+CCh] [rbp-3Ch] BYREF
  unsigned int v59; // [rsp+D0h] [rbp-38h]
  LPVOID pv; // [rsp+D8h] [rbp-30h] BYREF
  int v61; // [rsp+E0h] [rbp-28h] BYREF
  int v62; // [rsp+E4h] [rbp-24h] BYREF
  int v63[4]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v64; // [rsp+F8h] [rbp-10h] BYREF
  struct IVolume *v65; // [rsp+108h] [rbp+0h]
  struct IFreeSpaceManager *v66; // [rsp+110h] [rbp+8h]
  int v71; // [rsp+190h] [rbp+88h]

  v7 = a1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v47, "CRunBootOptimize::_DefragmentBootOpt", 371, 1);
  v8 = 0;
  v65 = 0;
  v9 = 0;
  v66 = 0;
  v50 = 0;
  v51 = 0;
  v56 = 0;
  v44 = 0;
  LODWORD(v43) = 0;
  v58 = 0;
  v46 = 0;
  v55 = 0;
  v45 = 0;
  v63[0] = 0;
  v57 = 0;
  v62 = 0;
  v61 = 0;
  pv = 0;
  v11 = 404;
  if ( !a6 || (v48 = 404, v11 = 405, !a7) )
  {
    v12 = -2147024809;
LABEL_4:
    v47 = v12;
LABEL_5:
    v49 = v11;
    goto LABEL_8;
  }
  v47 = 0;
  v48 = 405;
  (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)a6 + 8LL))(a6);
  v8 = a6;
  v65 = a6;
  (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)a7 + 8LL))(a7);
  v9 = a7;
  v66 = a7;
  v18 = *(__int64 (__fastcall **)(struct IVolume *, __int64, __int64 *))(*(_QWORD *)a6 + 104LL);
  v19 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v12 = v18(a6, 2, &v50);
  v47 = v12;
  v11 = 411;
  if ( v12 < 0 )
    goto LABEL_5;
  v48 = 411;
  v20 = *(__int64 (__fastcall **)(struct IVolume *, __int64, __int64 *))(*(_QWORD *)a6 + 104LL);
  v21 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v12 = v20(a6, 1, &v51);
  v47 = v12;
  v11 = 412;
  if ( v12 < 0 )
    goto LABEL_5;
  v48 = 412;
  v22 = *(__int64 (__fastcall **)(struct IVolume *, _QWORD, __int64 *))(*(_QWORD *)a6 + 104LL);
  v23 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v12 = v22(a6, 0, &v56);
  v47 = v12;
  v11 = 413;
  if ( v12 < 0 )
    goto LABEL_5;
  v48 = 413;
  v12 = (*(__int64 (__fastcall **)(struct IVolume *, int *, int *, int *, int *))(*(_QWORD *)a6 + 192LL))(
          a6,
          &v57,
          v63,
          &v62,
          &v61);
  v47 = v12;
  v11 = 416;
  if ( v12 < 0 )
    goto LABEL_5;
  v48 = 416;
  v11 = 417;
  if ( !v57 )
  {
    v12 = -1996488672;
    goto LABEL_4;
  }
  v47 = 0;
  v48 = 417;
  v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v50 + 64LL))(v50, &v58);
  v47 = v12;
  v11 = 425;
  if ( v12 < 0 )
    goto LABEL_5;
  v48 = 425;
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v50 + 48LL))(v50, &v46);
  v47 = v12;
  v11 = 429;
  if ( v12 < 0 )
    goto LABEL_5;
  v24 = 0;
  v59 = 0;
  v71 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  while ( 1 )
  {
    v48 = v11;
    if ( v12 == 1 )
      break;
    v25 = *(__int64 (__fastcall **)(struct IVolume *, _QWORD, struct IFileOperation *, struct IFileOperation **))(*(_QWORD *)a6 + 56LL);
    if ( v44 )
    {
      v12 = v25(a6, v46, v44, 0);
      v47 = v12;
      v26 = v12 < 0;
      v11 = 434;
    }
    else
    {
      v12 = v25(a6, v46, 0, &v44);
      v47 = v12;
      v26 = v12 < 0;
      v11 = 438;
    }
    if ( v26 )
      goto LABEL_7;
    v48 = v11;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      v37 = ((__int64 (__fastcall *)(struct IFileOperation *, struct IVolume *, LPVOID *))v44->lpVtbl[1].Unadvise)(
              v44,
              a6,
              &pv);
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      {
        v38 = L"Error retrieving file path";
        if ( !v37 )
          v38 = (const wchar_t *)pv;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids, v38);
      }
      CoTaskMemFree(pv);
      pv = 0;
    }
    LODWORD(v43) = 0;
    v45 = 0;
    v12 = ((__int64 (__fastcall *)(struct IFileOperation *, __int64, int *))v44->lpVtbl->SetProperties)(v44, 128, &v45);
    v47 = v12;
    v11 = 456;
    if ( v12 < 0 )
      goto LABEL_7;
    v48 = 456;
    v27 = (char *)v7 + 56;
    v12 = ((__int64 (__fastcall *)(struct IFileOperation *, _QWORD, unsigned __int64 *))v44->lpVtbl->SetOperationFlags)(
            v44,
            *((_QWORD *)v7 + 24),
            &v55);
    v47 = v12;
    v11 = 457;
    if ( v12 < 0 )
      goto LABEL_7;
    v48 = 457;
    if ( v45 )
    {
      if ( v55 > 2 )
        goto LABEL_44;
    }
    else if ( v55 > 1 )
    {
LABEL_44:
      v29 = 1;
LABEL_59:
      v31 = v43;
      goto LABEL_60;
    }
    if ( a3 )
    {
      v64 = *a2;
      v12 = ((__int64 (__fastcall *)(struct IFileOperation *, __int128 *, __int64 *))v44->lpVtbl->DeleteItems)(
              v44,
              &v64,
              &v43);
      v47 = v12;
      v11 = 473;
      if ( v12 < 0 )
        goto LABEL_7;
      v48 = 473;
    }
    v29 = 0;
    v31 = v43;
    if ( !(_DWORD)v43 && a5 )
    {
      v64 = *a4;
      v12 = ((__int64 (__fastcall *)(struct IFileOperation *, __int128 *, __int64 *))v44->lpVtbl->DeleteItems)(
              v44,
              &v64,
              &v43);
      v47 = v12;
      v11 = 477;
      if ( v12 < 0 )
        goto LABEL_7;
      v48 = 477;
      goto LABEL_59;
    }
LABEL_60:
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      v36 = !v29 && !v31;
      WPP_SF_llll(*((_QWORD *)WPP_GLOBAL_Control + 2), WPP_GLOBAL_Control, v28, v29, v31, v45, v36);
      v31 = v43;
    }
    if ( v29 || v31 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v51 + 32LL))(v51, v46);
      v47 = v12;
      v11 = 490;
      if ( v12 < 0 )
        goto LABEL_7;
      v48 = 490;
      v12 = CDefragOperation::_Defragment(a1, 1, v44, a6, a7, 0);
      if ( v12 == -1996488682 )
      {
        v32 = 1;
        goto LABEL_71;
      }
      v47 = v12;
      v11 = 503;
      if ( v12 < 0 )
        goto LABEL_7;
      v32 = 0;
      v48 = 503;
      if ( v12 == 150995204 )
      {
LABEL_77:
        v12 = ((__int64 (__fastcall *)(struct IFileOperation *, _QWORD, unsigned __int64 *))v44->lpVtbl->SetOperationFlags)(
                v44,
                *((_QWORD *)a1 + 23),
                &v55);
        v47 = v12;
        v11 = 528;
        if ( v12 < 0 )
          goto LABEL_7;
        v48 = 528;
        v45 = 0;
        v12 = ((__int64 (__fastcall *)(struct IFileOperation *, __int64, int *))v44->lpVtbl->SetProperties)(
                v44,
                128,
                &v45);
        v47 = v12;
        v11 = 531;
        if ( v12 < 0 )
          goto LABEL_7;
        v48 = 531;
        if ( v45 )
        {
          if ( v55 <= 2 )
            goto LABEL_84;
LABEL_81:
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v51 + 24LL))(v51, v46);
          v47 = v12;
          v11 = 538;
          if ( v12 < 0 )
            goto LABEL_7;
          ++v71;
          v48 = 538;
        }
        else
        {
          if ( v55 > 1 )
            goto LABEL_81;
LABEL_84:
          ++v52;
        }
        v35 = 0;
        LODWORD(v43) = 0;
        if ( a3 )
        {
          v64 = *a2;
          v12 = ((__int64 (__fastcall *)(struct IFileOperation *, __int128 *, __int64 *))v44->lpVtbl->DeleteItems)(
                  v44,
                  &v64,
                  &v43);
          v47 = v12;
          v11 = 549;
          if ( v12 < 0 )
            goto LABEL_7;
          v48 = 549;
          v35 = v43;
          if ( (_DWORD)v43 )
            goto LABEL_92;
        }
        if ( !a5 )
          goto LABEL_89;
        v64 = *a4;
        v12 = ((__int64 (__fastcall *)(struct IFileOperation *, __int128 *, __int64 *))v44->lpVtbl->DeleteItems)(
                v44,
                &v64,
                &v43);
        v47 = v12;
        v11 = 553;
        if ( v12 < 0 )
          goto LABEL_7;
        v48 = 553;
        v35 = v43;
        if ( (_DWORD)v43 )
LABEL_92:
          ++v53;
        else
LABEL_89:
          ++v54;
      }
      else
      {
LABEL_71:
        v12 = ((__int64 (__fastcall *)(struct IFileOperation *, struct IVolume *, struct IFreeSpaceManager *, char *))v44->lpVtbl->RenameItems)(
                v44,
                a6,
                a7,
                v27);
        v47 = v12;
        v11 = 510;
        if ( v12 < 0 )
          goto LABEL_7;
        v48 = 510;
        if ( v12 != 1 && !v32 )
          goto LABEL_77;
        v33 = (unsigned int *)CoTaskMemAlloc(0x10u);
        if ( !v33 )
        {
          v12 = -2147024882;
          v47 = -2147024882;
          v11 = 520;
LABEL_7:
          v49 = v11;
          if ( v24 )
          {
            do
            {
LABEL_127:
              v41 = v24;
              v24 = (unsigned int *)*((_QWORD *)v24 + 1);
              CoTaskMemFree(v41);
            }
            while ( v24 );
            v12 = v47;
          }
          goto LABEL_8;
        }
        v47 = 0;
        v48 = 520;
        *((_QWORD *)v33 + 1) = v24;
        *v33 = v46;
        v24 = v33;
        v35 = v43;
      }
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      {
        WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), &WPP_GLOBAL_Control, v34, v35 == 0);
      }
    }
    v7 = a1;
    v12 = (*(__int64 (__fastcall **)(CDefragOperation *))(*(_QWORD *)a1 + 32LL))(a1);
    v47 = v12;
    v11 = 571;
    if ( v12 < 0 )
      goto LABEL_7;
    v48 = 571;
    if ( v59 < 0x64 && !v58 )
    {
      v12 = CDefragOperation::_SetPercentComplete(a1, 0x64u);
      v47 = v12;
      v11 = 589;
      if ( v12 < 0 )
        goto LABEL_7;
      v48 = 589;
      v59 = 100;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v50 + 56LL))(v50, &v46);
    v47 = v12;
    v11 = 593;
    if ( v12 < 0 )
      goto LABEL_7;
  }
  while ( v24 )
  {
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids);
    }
    v30 = *(__int64 (__fastcall **)(struct IVolume *, _QWORD, struct IFileOperation *, struct IFileOperation **))(*(_QWORD *)a6 + 56LL);
    if ( v44 )
    {
      v47 = v30(a6, *v24, v44, 0);
      if ( v47 < 0 )
      {
        v49 = 604;
        goto LABEL_127;
      }
      v48 = 604;
    }
    else
    {
      v47 = v30(a6, *v24, 0, &v44);
      if ( v47 < 0 )
      {
        v49 = 608;
        goto LABEL_127;
      }
      v48 = 608;
    }
    v47 = ((__int64 (__fastcall *)(struct IFileOperation *, struct IVolume *))v44->lpVtbl->DeleteItem)(v44, a6);
    v39 = 612;
    if ( v47 < 0 )
      goto LABEL_125;
    v48 = 612;
    v47 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v51 + 32LL))(v51, *v24);
    v39 = 615;
    if ( v47 < 0 )
      goto LABEL_125;
    v48 = 615;
    v47 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v50 + 32LL))(v50, *v24);
    v39 = 616;
    if ( v47 < 0
      || (v48 = 616,
          v47 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v56 + 32LL))(v56, *v24),
          v39 = 617,
          v47 < 0)
      || (v48 = 617,
          v47 = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD))(*(_QWORD *)a6 + 152LL))(a6, *v24),
          v39 = 620,
          v47 < 0) )
    {
LABEL_125:
      v49 = v39;
      goto LABEL_127;
    }
    v40 = v24;
    v48 = 620;
    v24 = (unsigned int *)*((_QWORD *)v24 + 1);
    CoTaskMemFree(v40);
  }
  v42 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids, v52, v71);
      v42 = WPP_GLOBAL_Control;
    }
    if ( v42 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x40000) != 0 )
      WPP_SF_dd(*((_QWORD *)v42 + 2), 29, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids, v54, v53);
  }
  v12 = 0;
  v47 = 0;
LABEL_8:
  v13 = v44;
  if ( v44 )
  {
    v44 = 0;
    ((void (__fastcall *)(struct IFileOperation *))v13->lpVtbl->Release)(v13);
  }
  v14 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( v9 )
    (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v8 )
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v8 + 16LL))(v8);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v47);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000ff80  mov     rax, rsp
0x18000ff83  mov     [rax+20h], r9
0x18000ff87  mov     [rax+18h], r8d
0x18000ff8b  mov     [rax+10h], rdx
0x18000ff8f  mov     [rax+8], rcx
0x18000ff93  push    rbp
0x18000ff94  push    rbx
0x18000ff95  push    rsi
0x18000ff96  push    rdi
0x18000ff97  push    r12
0x18000ff99  push    r13
0x18000ff9b  push    r14
0x18000ff9d  push    r15
0x18000ff9f  lea     rbp, [rax-58h]
0x18000ffa3  sub     rsp, 118h
0x18000ffaa  mov     r12, rcx
0x18000ffad  mov     r9d, 1; unsigned __int16
0x18000ffb3  mov     r8d, 173h; unsigned __int16
0x18000ffb9  lea     rdx, aCrunbootoptimi; "CRunBootOptimize::_DefragmentBootOpt"
0x18000ffc0  lea     rcx, [rsp+150h+var_F8]; this
0x18000ffc5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000ffca  nop
0x18000ffcb  xor     r13d, r13d
0x18000ffce  mov     ebx, r13d
0x18000ffd1  mov     [rbp+50h+var_50], rbx
0x18000ffd5  mov     edi, r13d
0x18000ffd8  mov     [rbp+50h+var_48], r13
0x18000ffdc  mov     [rbp+50h+var_C0], r13
0x18000ffe0  mov     [rbp+50h+var_B8], r13
0x18000ffe4  mov     [rbp+50h+var_98], r13
0x18000ffe8  mov     [rsp+150h+var_108], r13
0x18000ffed  mov     dword ptr [rsp+150h+var_110], r13d
0x18000fff2  mov     [rbp+50h+var_8C], r13d
0x18000fff6  mov     dword ptr [rsp+150h+var_FC], r13d
0x18000fffb  mov     [rbp+50h+var_A0], r13
0x18000ffff  mov     [rsp+150h+var_100], r13d
0x180010004  mov     [rbp+50h+var_70], r13d
0x180010008  mov     [rbp+50h+var_90], r13d
0x18001000c  mov     [rbp+50h+var_74], r13d
0x180010010  mov     [rbp+50h+var_78], r13d
0x180010014  mov     [rbp+50h+pv], r13
0x180010018  mov     r14, [rbp+50h+arg_28]
0x18001001f  mov     eax, 194h
0x180010024  test    r14, r14
0x180010027  jz      short loc_180010043
0x180010029  mov     [rsp+150h+var_F4], ax
0x18001002e  mov     rsi, [rbp+50h+arg_30]
0x180010035  mov     eax, 195h
0x18001003a  test    rsi, rsi
0x18001003d  jnz     loc_180010123
0x180010043  mov     esi, 80070057h
0x180010048  mov     [rsp+150h+var_F8], esi
0x18001004c  mov     [rsp+150h+var_F2], ax
0x180010051  jmp     short loc_18001006F
0x180010053  mov     esi, 8007000Eh
0x180010058  mov     [rsp+150h+var_F8], esi
0x18001005c  mov     eax, 208h
0x180010061  mov     [rsp+150h+var_F2], ax
0x180010066  test    r15, r15
0x180010069  jnz     loc_180010AAA
0x18001006f  mov     rcx, [rsp+150h+var_108]
0x180010074  test    rcx, rcx
0x180010077  jz      short loc_18001008B
0x180010079  mov     [rsp+150h+var_108], r13
0x18001007e  mov     rax, [rcx]
0x180010081  mov     rax, [rax+10h]
0x180010085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001008a  nop
0x18001008b  mov     rcx, [rbp+50h+var_98]
0x18001008f  test    rcx, rcx
0x180010092  jz      short loc_1800100A5
0x180010094  mov     [rbp+50h+var_98], r13
0x180010098  mov     rax, [rcx]
0x18001009b  mov     rax, [rax+10h]
0x18001009f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100a4  nop
0x1800100a5  mov     rcx, [rbp+50h+var_B8]
0x1800100a9  test    rcx, rcx
0x1800100ac  jz      short loc_1800100BF
0x1800100ae  mov     [rbp+50h+var_B8], r13
0x1800100b2  mov     rax, [rcx]
0x1800100b5  mov     rax, [rax+10h]
0x1800100b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100be  nop
0x1800100bf  mov     rcx, [rbp+50h+var_C0]
0x1800100c3  test    rcx, rcx
0x1800100c6  jz      short loc_1800100D9
0x1800100c8  mov     [rbp+50h+var_C0], r13
0x1800100cc  mov     rax, [rcx]
0x1800100cf  mov     rax, [rax+10h]
0x1800100d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100d8  nop
0x1800100d9  test    rdi, rdi
0x1800100dc  jz      short loc_1800100EE
0x1800100de  mov     rax, [rdi]
0x1800100e1  mov     rcx, rdi
0x1800100e4  mov     rax, [rax+10h]
0x1800100e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100ed  nop
0x1800100ee  test    rbx, rbx
0x1800100f1  jz      short loc_180010103
0x1800100f3  mov     rcx, [rbx]
0x1800100f6  mov     rax, [rcx+10h]
0x1800100fa  mov     rcx, rbx
0x1800100fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010102  nop
0x180010103  lea     rcx, [rsp+150h+var_F8]; this
0x180010108  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001010d  mov     eax, esi
0x18001010f  add     rsp, 118h
0x180010116  pop     r15
0x180010118  pop     r14
0x18001011a  pop     r13
0x18001011c  pop     r12
0x18001011e  pop     rdi
0x18001011f  pop     rsi
0x180010120  pop     rbx
0x180010121  pop     rbp
0x180010122  retn
0x180010123  mov     [rsp+150h+var_F8], r13d
0x180010128  mov     [rsp+150h+var_F4], ax
0x18001012d  mov     rax, [r14]
0x180010130  mov     rcx, r14
0x180010133  mov     rax, [rax+8]
0x180010137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001013c  nop
0x18001013d  mov     rbx, r14
0x180010140  mov     [rbp+50h+var_50], rbx
0x180010144  mov     rax, [rsi]
0x180010147  mov     rcx, rsi
0x18001014a  mov     rax, [rax+8]
0x18001014e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010153  nop
0x180010154  mov     rdi, rsi
0x180010157  mov     [rbp+50h+var_48], rsi
0x18001015b  mov     rax, [r14]
0x18001015e  mov     rsi, [rax+68h]
0x180010162  mov     rcx, [rbp+50h+var_C0]
0x180010166  test    rcx, rcx
0x180010169  jz      short loc_18001017C
0x18001016b  mov     [rbp+50h+var_C0], r13
0x18001016f  mov     rdx, [rcx]
0x180010172  mov     rax, [rdx+10h]
0x180010176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001017b  nop
0x18001017c  lea     r8, [rbp+50h+var_C0]
0x180010180  mov     edx, 2
0x180010185  mov     rcx, r14
0x180010188  mov     rax, rsi
0x18001018b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010190  mov     esi, eax
0x180010192  mov     [rsp+150h+var_F8], eax
0x180010196  test    eax, eax
0x180010198  mov     eax, 19Bh
0x18001019d  js      loc_18001004C
0x1800101a3  mov     [rsp+150h+var_F4], ax
0x1800101a8  mov     rax, [r14]
0x1800101ab  mov     rsi, [rax+68h]
0x1800101af  mov     rcx, [rbp+50h+var_B8]
0x1800101b3  test    rcx, rcx
0x1800101b6  jz      short loc_1800101C9
0x1800101b8  mov     [rbp+50h+var_B8], r13
0x1800101bc  mov     rdx, [rcx]
0x1800101bf  mov     rax, [rdx+10h]
0x1800101c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101c8  nop
0x1800101c9  lea     r8, [rbp+50h+var_B8]
0x1800101cd  mov     edx, 1
0x1800101d2  mov     rcx, r14
0x1800101d5  mov     rax, rsi
0x1800101d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101dd  mov     esi, eax
0x1800101df  mov     [rsp+150h+var_F8], eax
0x1800101e3  test    eax, eax
0x1800101e5  mov     eax, 19Ch
0x1800101ea  js      loc_18001004C
0x1800101f0  mov     [rsp+150h+var_F4], ax
0x1800101f5  mov     rax, [r14]
0x1800101f8  mov     rsi, [rax+68h]
0x1800101fc  mov     rcx, [rbp+50h+var_98]
0x180010200  test    rcx, rcx
0x180010203  jz      short loc_180010216
0x180010205  mov     [rbp+50h+var_98], r13
0x180010209  mov     rdx, [rcx]
0x18001020c  mov     rax, [rdx+10h]
0x180010210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010215  nop
0x180010216  lea     r8, [rbp+50h+var_98]
0x18001021a  xor     edx, edx
0x18001021c  mov     rcx, r14
0x18001021f  mov     rax, rsi
0x180010222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010227  mov     esi, eax
0x180010229  mov     [rsp+150h+var_F8], eax
0x18001022d  test    eax, eax
0x18001022f  mov     eax, 19Dh
0x180010234  js      loc_18001004C
0x18001023a  mov     [rsp+150h+var_F4], ax
0x18001023f  mov     rax, [r14]
0x180010242  lea     rcx, [rbp+50h+var_78]
0x180010246  mov     [rsp+150h+var_130], rcx
0x18001024b  lea     r9, [rbp+50h+var_74]
0x18001024f  lea     r8, [rbp+50h+var_70]
0x180010253  lea     rdx, [rbp+50h+var_90]
0x180010257  mov     rcx, r14
0x18001025a  mov     rax, [rax+0C0h]
0x180010261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010266  mov     esi, eax
0x180010268  mov     [rsp+150h+var_F8], eax
0x18001026c  test    eax, eax
0x18001026e  mov     eax, 1A0h
0x180010273  js      loc_18001004C
0x180010279  mov     [rsp+150h+var_F4], ax
0x18001027e  mov     eax, 1A1h
0x180010283  cmp     [rbp+50h+var_90], r13d
0x180010287  jz      loc_180010986
0x18001028d  mov     [rsp+150h+var_F8], r13d
0x180010292  mov     [rsp+150h+var_F4], ax
0x180010297  mov     rcx, [rbp+50h+var_C0]
0x18001029b  mov     rax, [rcx]
0x18001029e  lea     rdx, [rbp+50h+var_8C]
0x1800102a2  mov     rax, [rax+40h]
0x1800102a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102ab  mov     esi, eax
0x1800102ad  mov     [rsp+150h+var_F8], eax
0x1800102b1  test    eax, eax
0x1800102b3  mov     eax, 1A9h
0x1800102b8  js      loc_18001004C
0x1800102be  mov     [rsp+150h+var_F4], ax
0x1800102c3  mov     rcx, [rbp+50h+var_C0]
0x1800102c7  mov     rax, [rcx]
0x1800102ca  lea     rdx, [rsp+150h+var_FC]
0x1800102cf  mov     rax, [rax+30h]
0x1800102d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102d8  mov     esi, eax
0x1800102da  mov     [rsp+150h+var_F8], eax
0x1800102de  test    eax, eax
0x1800102e0  mov     eax, 1ADh
0x1800102e5  js      loc_18001004C
0x1800102eb  mov     r15, r13
0x1800102ee  mov     [rbp+50h+var_88], r13d
0x1800102f2  mov     dword ptr [rbp+50h+arg_28], r13d
0x1800102f9  mov     [rbp+50h+var_B0], r13d
0x1800102fd  mov     [rbp+50h+var_AC], r13d
0x180010301  mov     [rbp+50h+var_A8], r13d
0x180010305  mov     [rsp+150h+var_F4], ax
0x18001030a  cmp     esi, 1
0x18001030d  jz      loc_1800103FB
0x180010313  mov     rax, [r14]
0x180010316  mov     rax, [rax+38h]
0x18001031a  mov     r8, [rsp+150h+var_108]
0x18001031f  test    r8, r8
0x180010322  jz      loc_180010477
0x180010328  xor     r9d, r9d
0x18001032b  mov     edx, dword ptr [rsp+150h+var_FC]
0x18001032f  mov     rcx, r14
0x180010332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010337  mov     esi, eax
0x180010339  mov     [rsp+150h+var_F8], eax
0x18001033d  test    eax, eax
0x18001033f  mov     eax, 1B2h
0x180010344  js      loc_180010061
0x18001034a  mov     [rsp+150h+var_F4], ax
0x18001034f  mov     rax, cs:WPP_GLOBAL_Control
0x180010356  mov     esi, 40000h
0x18001035b  test    [rax+1Ch], esi
0x18001035e  jnz     loc_18001088B
0x180010364  mov     dword ptr [rsp+150h+var_110], r13d
0x180010369  mov     [rsp+150h+var_100], r13d
0x18001036e  mov     rcx, [rsp+150h+var_108]
0x180010373  mov     rax, [rcx]
0x180010376  lea     r8, [rsp+150h+var_100]
0x18001037b  mov     edx, 80h
0x180010380  mov     rax, [rax+40h]
0x180010384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010389  mov     esi, eax
0x18001038b  mov     [rsp+150h+var_F8], eax
0x18001038f  test    eax, eax
0x180010391  mov     eax, 1C8h
0x180010396  js      loc_180010061
0x18001039c  mov     [rsp+150h+var_F4], ax
0x1800103a1  mov     rcx, [rsp+150h+var_108]
0x1800103a6  lea     r13, [r12+38h]
0x1800103ab  mov     rax, [rcx]
0x1800103ae  lea     r8, [rbp+50h+var_A0]
0x1800103b2  mov     rdx, [r13+88h]
0x1800103b9  mov     rax, [rax+28h]
0x1800103bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103c2  mov     esi, eax
0x1800103c4  mov     [rsp+150h+var_F8], eax
0x1800103c8  test    eax, eax
0x1800103ca  mov     eax, 1C9h
0x1800103cf  js      loc_180010990
0x1800103d5  mov     [rsp+150h+var_F4], ax
0x1800103da  cmp     [rsp+150h+var_100], 0
0x1800103df  jz      loc_18001049D
0x1800103e5  cmp     [rbp+50h+var_A0], 2
0x1800103ea  jbe     loc_1800104A8
0x1800103f0  mov     r12d, 1
0x1800103f6  jmp     loc_180010507
  ... truncated ...
```
