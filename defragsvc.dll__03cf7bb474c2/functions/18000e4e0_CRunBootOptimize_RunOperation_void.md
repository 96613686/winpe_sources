# CRunBootOptimize::RunOperation(void)

- ea: `0x18000e4e0`
- end: `0x18000f31f`
- name: `?RunOperation@CRunBootOptimize@@UEAAJXZ`
- size: `3647`
- prototype: `__int64 __fastcall(CRunBootOptimize *__hidden this)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18000c644`
- `0x18000c794`
- `0x18000c848`
- `0x18000e168`
- `0x18000e4e0`
- `0x18000f328`
- `0x18000fcac`
- `0x18000fe24`
- `0x18000ff80`
- `0x180010c20`
- `0x180011ac4`
- `0x1800140bc`
- `0x18001913c`
- `0x18001f22c`
- `0x18001ff18`
- `0x1800298ec`
- `0x18002dd8c`
- `0x18002f114`
- `0x180038c3c`
- `0x180046494`
- `0x18004b73c`
- `0x1800546e8`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e638`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e638`

## string_xrefs

- `0x18000f224`: `Missing Registry Entries`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall CRunBootOptimize::RunOperation(CRunBootOptimize *this)
{
  unsigned int v2; // r15d
  int v3; // esi
  struct IVolume *v4; // rbx
  __int16 v5; // ax
  struct IVolume *v6; // rcx
  CRunBootOptimize *v7; // rcx
  wchar_t *v8; // rdx
  char v9; // bl
  unsigned int BootOptSettings; // eax
  int v11; // ebx
  CSxGlobalTracer *v12; // rcx
  unsigned __int16 *v13; // rbx
  struct IRunnableThread *v14; // rcx
  struct IRunnableThread *v15; // rcx
  char *v16; // r14
  struct IFreeSpaceManager *v17; // rcx
  unsigned int v18; // eax
  unsigned __int64 v19; // r12
  struct IVolume *v20; // rbx
  __int64 (__fastcall *v21)(struct IVolume *, __int64, __int64 *); // rsi
  __int64 v22; // rcx
  unsigned __int64 v23; // r13
  CSxGlobalTracer *v24; // rcx
  int v25; // esi
  __int64 v26; // rdx
  struct IRunnableThread *v27; // rcx
  struct IRunnableThread *v28; // rcx
  int v29; // r14d
  unsigned __int64 v30; // rbx
  __int64 v31; // rbx
  struct IRunnableThread *v32; // rcx
  struct IRunnableThread *v33; // rcx
  __int64 v34; // rdx
  unsigned __int64 v35; // rbx
  __int64 v36; // rcx
  __int64 v37; // r9
  CSxGlobalTracer *v38; // r10
  struct IRunnableThread *v39; // rcx
  wchar_t *v40; // r8
  unsigned int v41; // ebx
  struct IFreeSpaceManager *v42; // rcx
  __int64 v43; // rcx
  struct IVolume *v44; // rcx
  struct IRunnableThread *v45; // rcx
  struct __MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *v47; // [rsp+20h] [rbp-E0h]
  struct IRunnableThread *v48; // [rsp+40h] [rbp-C0h] BYREF
  int BootOptProgress; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v50; // [rsp+4Ch] [rbp-B4h]
  __int16 v51; // [rsp+4Eh] [rbp-B2h]
  struct IFreeSpaceManager *v52; // [rsp+80h] [rbp-80h] BYREF
  struct IVolume *v53; // [rsp+88h] [rbp-78h] BYREF
  int v54; // [rsp+90h] [rbp-70h] BYREF
  __int64 v55; // [rsp+98h] [rbp-68h] BYREF
  int v56; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v57; // [rsp+A4h] [rbp-5Ch] BYREF
  int v58; // [rsp+A8h] [rbp-58h]
  LPVOID pv[2]; // [rsp+B0h] [rbp-50h] BYREF
  const unsigned __int16 *v60; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v61; // [rsp+C8h] [rbp-38h]
  __int64 v62; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v63; // [rsp+D8h] [rbp-28h]
  __int128 v64; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v65; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v66; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v67; // [rsp+100h] [rbp+0h] BYREF
  __int64 v68; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v69[2]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v70[2]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v71; // [rsp+130h] [rbp+30h] BYREF
  __int128 v72; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v73[2]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v74[4]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v75; // [rsp+180h] [rbp+80h] BYREF

  v2 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&BootOptProgress, "CRunBootOptimize::RunOperation", 660, 1);
  v48 = 0;
  v53 = 0;
  v55 = 0;
  v74[2] = 0;
  v52 = 0;
  v75 = 0;
  v54 = 0;
  v57 = 0;
  v62 = 0;
  v68 = 0;
  v56 = 0;
  v67 = 0;
  v3 = 0;
  v58 = 0;
  pv[0] = 0;
  v66 = 0;
  v65 = 0;
  v4 = (struct IVolume *)*((_QWORD *)this + 93);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4 + 8LL))(*((_QWORD *)this + 93));
    v6 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    v53 = v4;
  }
  else
  {
    BootOptProgress = CDefragOperation::_CreateVolumeForFileSystem(this, &v53);
    v5 = 704;
    if ( BootOptProgress < 0 )
      goto LABEL_9;
    v50 = 704;
    v3 = 1;
    v58 = 1;
    v4 = v53;
  }
  if ( v4 )
  {
    if ( v3 )
    {
      BootOptProgress = (*(__int64 (__fastcall **)(struct IVolume *, char *))(*(_QWORD *)v4 + 48LL))(
                          v4,
                          (char *)this + 56);
      v5 = 723;
      if ( BootOptProgress < 0 )
        goto LABEL_9;
      v50 = 723;
    }
    if ( *((_DWORD *)this + 204) )
    {
      v60 = &qword_18006F470;
      v61 = 0;
      v75 = 0u;
      CBsString::Set((CBsString *)&v60, *((const unsigned __int16 **)this + 101));
      CBsString::Detach((CBsString *)&v60, (unsigned __int16 **)pv);
      v9 = 7;
      CBsString::_Release((LPVOID *)&v60);
    }
    else
    {
      v9 = 0;
    }
    BootOptSettings = CDefragOperation::_GetBootOptSettings(
                        this,
                        v9,
                        (struct __MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *)&v75,
                        &v56,
                        &v67,
                        &v66,
                        &v65,
                        (unsigned __int16 **)pv);
    v11 = BootOptSettings;
    if ( v56 )
    {
      BootOptProgress = CDefragOperation::_SetPercentComplete(this, 0);
      v5 = 792;
      if ( BootOptProgress >= 0 )
      {
        v50 = 792;
        *((_QWORD *)this + 95) = 0;
        *((_QWORD *)this + 96) = 0;
        *((_QWORD *)this + 97) = 0;
        *((_QWORD *)this + 98) = 0;
        *((_QWORD *)this + 99) = 0;
        *((_QWORD *)this + 100) = 0;
        if ( v3 )
        {
          BootOptProgress = CDefragOperation::_SetPhase(this, 1u);
          v5 = 807;
          if ( BootOptProgress < 0 )
            goto LABEL_9;
          v50 = 807;
          v13 = (unsigned __int16 *)pv[0];
          v14 = v48;
          if ( v48 )
          {
            v48 = 0;
            (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v14 + 16LL))(v14);
          }
          BootOptProgress = CRunAnalysis::CreateInstance(
                              1,
                              1,
                              v53,
                              &v48,
                              (struct __MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *)&v75,
                              &v66,
                              &v65,
                              v13);
          v5 = 817;
          if ( BootOptProgress < 0 )
            goto LABEL_9;
          v50 = 817;
          BootOptProgress = (*(__int64 (__fastcall **)(struct IRunnableThread *, _QWORD))(*(_QWORD *)v48 + 24LL))(
                              v48,
                              *((_QWORD *)this + 5));
          v5 = 820;
          if ( BootOptProgress < 0 )
            goto LABEL_9;
          v50 = 820;
          v15 = v48;
          if ( v48 )
          {
            v48 = 0;
            (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v15 + 16LL))(v15);
          }
        }
        v16 = (char *)this + 56;
        BootOptProgress = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(
                            *((_QWORD *)this + 6),
                            (char *)this + 56);
        v5 = 827;
        if ( BootOptProgress >= 0 )
        {
          v50 = 827;
          *((_QWORD *)this + 24) = 0;
          v17 = v52;
          if ( v52 )
          {
            v52 = 0;
            (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v17 + 16LL))(v17);
          }
          BootOptProgress = CFreeSpaceManager::CreateInstance(
                              *((unsigned __int16 **)this + 87),
                              *((_QWORD *)this + 18),
                              &v52);
          v5 = 836;
          if ( BootOptProgress >= 0 )
          {
            v50 = 836;
            v60 = (const unsigned __int16 *)*((_QWORD *)this + 22);
            v61 = *((_QWORD *)this + 21);
            BootOptProgress = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, const unsigned __int16 **))(*(_QWORD *)v52 + 48LL))(
                                v52,
                                &v60);
            v5 = 841;
            if ( BootOptProgress >= 0 )
            {
              v50 = 841;
              v18 = *((_DWORD *)this + 38);
              if ( v18 )
                v19 = v67 / v18;
              else
                v19 = 0;
              v20 = v53;
              v21 = *(__int64 (__fastcall **)(struct IVolume *, __int64, __int64 *))(*(_QWORD *)v53 + 104LL);
              v22 = v55;
              if ( v55 )
              {
                v55 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
              }
              BootOptProgress = v21(v20, 2, &v55);
              v5 = 855;
              if ( BootOptProgress >= 0 )
              {
                v50 = 855;
                BootOptProgress = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v55 + 64LL))(
                                    v55,
                                    &v57);
                v5 = 857;
                if ( BootOptProgress >= 0 )
                {
                  v60 = 0;
                  v63 = 0;
                  v23 = 0;
                  v50 = 857;
                  v24 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      32,
                      WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids,
                      v57);
                    v24 = WPP_GLOBAL_Control;
                  }
                  v25 = 0;
                  while ( 1 )
                  {
                    if ( v24 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v24 + 7) & 0x400000) != 0 )
                      WPP_SF_d(*((_QWORD *)v24 + 2), 33, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids, v2);
                    BootOptProgress = CDefragOperation::_SetPass(this, v2);
                    v5 = 867;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 867;
                    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
                    {
                      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids);
                    }
                    BootOptProgress = CDefragOperation::_SetPhase(this, 6u);
                    v5 = 874;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 874;
                    v27 = v48;
                    if ( v48 )
                    {
                      v48 = 0;
                      (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v27 + 16LL))(v27);
                    }
                    v64 = v75;
                    BootOptProgress = CRunEvict::CreateInstance(&v64, v26, v53, &v48, v47);
                    v5 = 879;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 879;
                    BootOptProgress = (*(__int64 (__fastcall **)(struct IRunnableThread *, _QWORD))(*(_QWORD *)v48 + 24LL))(
                                        v48,
                                        *((_QWORD *)this + 5));
                    v5 = 882;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 882;
                    v28 = v48;
                    if ( v48 )
                    {
                      v48 = 0;
                      (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v28 + 16LL))(v28);
                    }
                    BootOptProgress = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(
                                        *((_QWORD *)this + 6),
                                        v16);
                    v5 = 888;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 888;
                    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
                    {
                      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids);
                    }
                    BootOptProgress = CDefragOperation::_SetPhase(this, 3u);
                    v5 = 896;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 896;
                    v29 = 0;
                    if ( (_QWORD)v75 )
                    {
                      v60 = (const unsigned __int16 *)(v75 - 1);
                      v69[0] = 0;
                      v69[1] = v75 - 1;
                      BootOptProgress = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, _QWORD *))(*(_QWORD *)v52 + 48LL))(
                                          v52,
                                          v69);
                      v5 = 908;
                      if ( BootOptProgress < 0 )
                        break;
                      v29 = 1;
                      v50 = 908;
                    }
                    v30 = *((_QWORD *)this + 18) - 1LL;
                    if ( *((_QWORD *)&v75 + 1) < v30 )
                    {
                      v63 = *((_QWORD *)&v75 + 1) + 1LL;
                      v70[0] = *((_QWORD *)&v75 + 1) + 1LL;
                      v70[1] = v30;
                      BootOptProgress = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, _QWORD *))(*(_QWORD *)v52 + 48LL))(
                                          v52,
                                          v70);
                      v5 = 916;
                      if ( BootOptProgress < 0 )
                        break;
                      v23 = v30;
                      v25 = 1;
                      v50 = 916;
                    }
                    BootOptProgress = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v52 + 24LL))(v52);
                    v5 = 919;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 919;
                    v31 = v63;
                    *(_QWORD *)&v71 = v63;
                    *((_QWORD *)&v71 + 1) = v23;
                    *(_QWORD *)&v72 = 0;
                    *((_QWORD *)&v72 + 1) = v60;
                    BootOptProgress = CRunBootOptimize::_DefragmentBootOpt(this, &v72, v29, &v71, v25, v53, v52);
                    v25 = 0;
                    v5 = 929;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 929;
                    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
                    {
                      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids);
                    }
                    BootOptProgress = CDefragOperation::_SetPhase(this, 2u);
                    v5 = 939;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 939;
                    v32 = v48;
                    if ( v48 )
                    {
                      v48 = 0;
                      (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v32 + 16LL))(v32);
                    }
                    v64 = v75;
                    BootOptProgress = CRunConsolidate::CreateInstance(&v64, 1, v53, &v48);
                    v5 = 944;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 944;
                    BootOptProgress = (*(__int64 (__fastcall **)(struct IRunnableThread *, _QWORD))(*(_QWORD *)v48 + 24LL))(
                                        v48,
                                        *((_QWORD *)this + 5));
                    v5 = 947;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 947;
                    v33 = v48;
                    if ( v48 )
                    {
                      v48 = 0;
                      (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v33 + 16LL))(v33);
                    }
                    v16 = (char *)this + 56;
                    BootOptProgress = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(
                                        *((_QWORD *)this + 6),
                                        (char *)this + 56);
                    v5 = 952;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 952;
                    v64 = v75;
                    BootOptProgress = CRunBootOptimize::_GetBootOptProgress(this, v2, &v64, v53, v52, &v62, &v68, &v54);
                    v5 = 965;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 965;
                    if ( !v54 && v62 )
                    {
                      v34 = ((unsigned __int64)(110 * v62) * (unsigned __int128)0x47AE147AE147AE15uLL) >> 64;
                      v35 = (v34 + ((unsigned __int64)(110 * v62 - v34) >> 1)) >> 6;
                      v37 = *((_QWORD *)&v75 + 1);
                      v36 = v75;
                      if ( *((_QWORD *)&v75 + 1) + v35 - (unsigned __int64)v75 <= v19 )
                      {
                        v38 = WPP_GLOBAL_Control;
                      }
                      else
                      {
                        v38 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
                        {
                          WPP_SF_i(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            37,
                            WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids,
                            v35);
                          v37 = *((_QWORD *)&v75 + 1);
                          v36 = v75;
                          v38 = WPP_GLOBAL_Control;
                        }
                        v35 = v19 + v36 - v37;
                      }
                      if ( v35 + v37 - v36 > 50LL * *((_QWORD *)this + 18) / 0x64uLL )
                      {
                        if ( v38 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v38 + 7) & 0x400000) != 0 )
                          WPP_SF_(*((_QWORD *)v38 + 2), 39, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids);
                        BootOptProgress = -1996488679;
                        v5 = 996;
                        break;
                      }
                      if ( v38 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v38 + 7) & 0x400000) != 0 )
                      {
                        v47 = (struct __MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *)v35;
                        WPP_SF_II(*((_QWORD *)v38 + 2), 38, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids);
                        v37 = *((_QWORD *)&v75 + 1);
                      }
                      *((_QWORD *)&v75 + 1) = v35 + v37;
                      v31 = v63;
                    }
                    v73[0] = 0;
                    v73[1] = v60;
                    BootOptProgress = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, _QWORD *))(*(_QWORD *)v52 + 56LL))(
                                        v52,
                                        v73);
                    v5 = 1001;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 1001;
                    v74[0] = v31;
                    v74[1] = v23;
                    BootOptProgress = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, _QWORD *))(*(_QWORD *)v52 + 56LL))(
                                        v52,
                                        v74);
                    v5 = 1002;
                    if ( BootOptProgress < 0 )
                      break;
                    v50 = 1002;
                    v24 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        40,
                        WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids,
                        v2);
                      v24 = WPP_GLOBAL_Control;
                    }
                    if ( v54 )
                    {
                      *((_QWORD *)&v75 + 1) = v68 + 1;
                      if ( v24 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v24 + 7) & 0x40000) != 0 )
                        WPP_SF_II(*((_QWORD *)v24 + 2), 41, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids);
                      v64 = v75;
                      BootOptProgress = CDefragOperation::_SetBootOptZone(v24, &v64);
                      v5 = 1019;
                      if ( BootOptProgress >= 0 )
                      {
                        v50 = 1019;
                        BootOptProgress = CDefragOperation::_SetPercentComplete(this, 0x64u);
                        v5 = 1021;
                        if ( BootOptProgress >= 0 )
                        {
                          v50 = 1021;
                          v39 = v48;
                          if ( v48 )
                          {
                            v48 = 0;
                            (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v39 + 16LL))(v39);
                          }
                          goto LABEL_10;
                        }
                      }
                      break;
                    }
                    ++v2;
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids,
          BootOptSettings);
        v12 = WPP_GLOBAL_Control;
      }
      BootOptProgress = v11;
      v5 = 778;
      if ( v11 >= 0 )
      {
        v50 = 778;
        if ( v12 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x2000000) != 0 )
          WPP_SF_d(*((_QWORD *)v12 + 2), 31, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids, (unsigned int)v11);
        BootOptProgress = -1996488680;
        v5 = 789;
      }
    }
  }
  else
  {
    BootOptProgress = -2147467259;
    v5 = 716;
  }
LABEL_9:
  v51 = v5;
LABEL_10:
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  if ( BootOptProgress < 0 )
  {
    switch ( BootOptProgress )
    {
      case -1996488681:
      case -1996488680:
        v40 = L"Missing Registry Entries";
        break;
      case -1996488679:
        v40 = L"Insufficient free space";
        break;
      case -1996488660:
        v40 = L"Operation not supported";
        break;
      default:
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids,
            (unsigned int)BootOptProgress);
        }
        v8 = L"No";
        goto LABEL_135;
    }
    v8 = L"No";
    goto LABEL_136;
  }
  v8 = (wchar_t *)L"Yes";
LABEL_135:
  v40 = (wchar_t *)&qword_18006F6A8;
LABEL_136:
  CRunBootOptimize::_SaveErrorInRegistry(v7, (BYTE *)v8, (BYTE *)v40);
  if ( v58 )
    Log_DF_OPTIMIZE_RESULT(
      (struct CSxFunctionTracer *)&BootOptProgress,
      0x426u,
      *((const unsigned __int16 **)this + 89),
      0x325u,
      BootOptProgress,
      0);
  v41 = BootOptProgress;
  v42 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v42 + 16LL))(v42);
  }
  v43 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v45 + 16LL))(v45);
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&BootOptProgress);
  return v41;
}

```

## disassembly

```asm
0x18000e4e0  push    rbp
0x18000e4e2  push    rbx
0x18000e4e3  push    rsi
0x18000e4e4  push    rdi
0x18000e4e5  push    r12
0x18000e4e7  push    r13
0x18000e4e9  push    r14
0x18000e4eb  push    r15
0x18000e4ed  lea     rbp, [rsp-0A8h]
0x18000e4f5  sub     rsp, 1A8h
0x18000e4fc  mov     rax, cs:__security_cookie
0x18000e503  xor     rax, rsp
0x18000e506  mov     [rbp+0E0h+var_50], rax
0x18000e50d  mov     rdi, rcx
0x18000e510  mov     r15d, 1
0x18000e516  mov     r9d, r15d; unsigned __int16
0x18000e519  mov     r8d, 294h; unsigned __int16
0x18000e51f  lea     rdx, aCrunbootoptimi_4; "CRunBootOptimize::RunOperation"
0x18000e526  lea     rcx, [rsp+1E0h+var_198]; this
0x18000e52b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e530  nop
0x18000e531  mov     [rsp+1E0h+var_1A0], 0
0x18000e53a  mov     [rbp+0E0h+var_158], 0
0x18000e542  mov     [rbp+0E0h+var_148], 0
0x18000e54a  mov     [rbp+0E0h+var_70], 0
0x18000e552  mov     [rbp+0E0h+var_160], 0
0x18000e55a  xorps   xmm0, xmm0
0x18000e55d  movups  [rbp+0E0h+var_60], xmm0
0x18000e564  mov     [rbp+0E0h+var_150], 0
0x18000e56b  mov     [rbp+0E0h+var_13C], 0
0x18000e572  mov     [rbp+0E0h+var_110], 0
0x18000e57a  mov     [rbp+0E0h+var_D8], 0
0x18000e582  mov     [rbp+0E0h+var_140], 0
0x18000e589  mov     [rbp+0E0h+var_E0], 0
0x18000e591  xor     esi, esi
0x18000e593  mov     [rbp+0E0h+var_138], esi
0x18000e596  mov     [rbp+0E0h+pv], rsi
0x18000e59a  mov     [rbp+0E0h+var_E8], rsi
0x18000e59e  mov     [rbp+0E0h+var_F0], rsi
0x18000e5a2  mov     rbx, [rdi+2E8h]
0x18000e5a9  lea     r14, WPP_GLOBAL_Control
0x18000e5b0  test    rbx, rbx
0x18000e5b3  jnz     short loc_18000E5E0
0x18000e5b5  lea     rdx, [rbp+0E0h+var_158]; struct IVolume **
0x18000e5b9  mov     rcx, rdi; this
0x18000e5bc  call    ?_CreateVolumeForFileSystem@CDefragOperation@@IEAAJPEAPEAUIVolume@@@Z; CDefragOperation::_CreateVolumeForFileSystem(IVolume * *)
0x18000e5c1  mov     [rsp+1E0h+var_198], eax
0x18000e5c5  test    eax, eax
0x18000e5c7  mov     eax, 2C0h
0x18000e5cc  js      short loc_18000E628
0x18000e5ce  mov     [rsp+1E0h+var_194], ax
0x18000e5d3  mov     esi, r15d
0x18000e5d6  mov     [rbp+0E0h+var_138], r15d
0x18000e5da  mov     rbx, [rbp+0E0h+var_158]
0x18000e5de  jmp     short loc_18000E612
0x18000e5e0  mov     rax, [rbx]
0x18000e5e3  mov     rcx, rbx
0x18000e5e6  mov     rax, [rax+8]
0x18000e5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5ef  nop
0x18000e5f0  mov     rcx, [rbp+0E0h+var_158]
0x18000e5f4  test    rcx, rcx
0x18000e5f7  jz      short loc_18000E60E
0x18000e5f9  mov     [rbp+0E0h+var_158], 0
0x18000e601  mov     rax, [rcx]
0x18000e604  mov     rax, [rax+10h]
0x18000e608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e60d  nop
0x18000e60e  mov     [rbp+0E0h+var_158], rbx
0x18000e612  test    rbx, rbx
0x18000e615  jnz     loc_18000E6BE
0x18000e61b  mov     [rsp+1E0h+var_198], 80004005h
0x18000e623  mov     eax, 2CCh
0x18000e628  lea     rbx, WPP_GLOBAL_Control
0x18000e62f  mov     [rsp+1E0h+var_192], ax
0x18000e634  mov     rcx, [rbp+0E0h+pv]; pv
0x18000e638  call    cs:__imp_CoTaskMemFree
0x18000e63e  mov     [rbp+0E0h+pv], 0
0x18000e646  mov     r9d, [rsp+1E0h+var_198]
0x18000e64b  test    r9d, r9d
0x18000e64e  jns     loc_18000F22D
0x18000e654  cmp     r9d, 89000017h
0x18000e65b  jz      loc_18000F224
0x18000e661  cmp     r9d, 89000018h
0x18000e668  jz      loc_18000F224
0x18000e66e  cmp     r9d, 89000019h
0x18000e675  jz      loc_18000F21B
0x18000e67b  cmp     r9d, 8900002Ch
0x18000e682  jz      loc_18000F20B
0x18000e688  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e68f  cmp     rcx, rbx
0x18000e692  jz      short loc_18000E6B2
0x18000e694  test    dword ptr [rcx+1Ch], 2000000h
0x18000e69b  jz      short loc_18000E6B2
0x18000e69d  mov     edx, 2Ah ; '*'
0x18000e6a2  lea     r8, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids
0x18000e6a9  mov     rcx, [rcx+10h]
0x18000e6ad  call    WPP_SF_d
0x18000e6b2  lea     rdx, aNo; "No"
0x18000e6b9  jmp     loc_18000F234
0x18000e6be  test    esi, esi
0x18000e6c0  jz      short loc_18000E6EB
0x18000e6c2  mov     rax, [rbx]
0x18000e6c5  lea     rdx, [rdi+38h]
0x18000e6c9  mov     rcx, rbx
0x18000e6cc  mov     rax, [rax+30h]
0x18000e6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6d5  mov     [rsp+1E0h+var_198], eax
0x18000e6d9  test    eax, eax
0x18000e6db  mov     eax, 2D3h
0x18000e6e0  js      loc_18000E628
0x18000e6e6  mov     [rsp+1E0h+var_194], ax
0x18000e6eb  cmp     dword ptr [rdi+330h], 0
0x18000e6f2  jnz     short loc_18000E6F8
0x18000e6f4  xor     ebx, ebx
0x18000e6f6  jmp     short loc_18000E74C
0x18000e6f8  lea     rax, qword_18006F470
0x18000e6ff  mov     [rbp+0E0h+var_120], rax
0x18000e703  mov     [rbp+0E0h+var_118], 0
0x18000e70b  mov     qword ptr [rbp+0E0h+var_60], 0
0x18000e716  mov     qword ptr [rbp+0E0h+var_60+8], 0
0x18000e721  mov     rdx, [rdi+328h]; unsigned __int16 *
0x18000e728  lea     rcx, [rbp+0E0h+var_120]; this
0x18000e72c  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000e731  lea     rdx, [rbp+0E0h+pv]; unsigned __int16 **
0x18000e735  lea     rcx, [rbp+0E0h+var_120]; this
0x18000e739  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x18000e73e  mov     ebx, 7
0x18000e743  lea     rcx, [rbp+0E0h+var_120]; this
0x18000e747  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000e74c  lea     rax, [rbp+0E0h+pv]
0x18000e750  mov     [rsp+1E0h+var_1A8], rax; unsigned __int16 **
0x18000e755  lea     rax, [rbp+0E0h+var_F0]
0x18000e759  mov     [rsp+1E0h+var_1B0], rax; unsigned __int64 *
0x18000e75e  lea     rax, [rbp+0E0h+var_E8]
0x18000e762  mov     [rsp+1E0h+var_1B8], rax; unsigned __int64 *
0x18000e767  lea     rax, [rbp+0E0h+var_E0]
0x18000e76b  mov     [rsp+1E0h+var_1C0], rax; unsigned __int64 *
0x18000e770  lea     r9, [rbp+0E0h+var_140]; int *
0x18000e774  lea     r8, [rbp+0E0h+var_60]; struct __MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *
0x18000e77b  mov     edx, ebx; unsigned int
0x18000e77d  mov     rcx, rdi; this
0x18000e780  call    ?_GetBootOptSettings@CDefragOperation@@IEAAJKPEAU__MIDL___MIDL_itf_dfengine_np_0000_0000_0001@@PEAHPEA_K22PEAPEAG@Z; CDefragOperation::_GetBootOptSettings(ulong,__MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *,int *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,ushort * *)
0x18000e785  mov     ebx, eax
0x18000e787  cmp     [rbp+0E0h+var_140], 0
0x18000e78b  jnz     loc_18000E813
0x18000e791  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e798  cmp     rcx, r14
0x18000e79b  jz      short loc_18000E7C5
0x18000e79d  test    dword ptr [rcx+1Ch], 2000000h
0x18000e7a4  jz      short loc_18000E7C5
0x18000e7a6  mov     edx, 1Eh
0x18000e7ab  mov     r9d, eax
0x18000e7ae  lea     r8, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids
0x18000e7b5  mov     rcx, [rcx+10h]
0x18000e7b9  call    WPP_SF_d
0x18000e7be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7c5  mov     [rsp+1E0h+var_198], ebx
0x18000e7c9  mov     eax, 30Ah
0x18000e7ce  test    ebx, ebx
0x18000e7d0  js      loc_18000E628
0x18000e7d6  mov     [rsp+1E0h+var_194], ax
0x18000e7db  cmp     rcx, r14
0x18000e7de  jz      short loc_18000E801
0x18000e7e0  test    dword ptr [rcx+1Ch], 2000000h
0x18000e7e7  jz      short loc_18000E801
0x18000e7e9  mov     edx, 1Fh
0x18000e7ee  mov     r9d, ebx
0x18000e7f1  lea     r8, WPP_bda4ed9a6e9b3fa61e4a6c3accce40e8_Traceguids
0x18000e7f8  mov     rcx, [rcx+10h]
0x18000e7fc  call    WPP_SF_d
0x18000e801  mov     [rsp+1E0h+var_198], 89000018h
0x18000e809  mov     eax, 315h
0x18000e80e  jmp     loc_18000E628
0x18000e813  xor     edx, edx; unsigned int
0x18000e815  mov     rcx, rdi; this
0x18000e818  call    ?_SetPercentComplete@CDefragOperation@@IEAAJK@Z; CDefragOperation::_SetPercentComplete(ulong)
0x18000e81d  mov     [rsp+1E0h+var_198], eax
0x18000e821  test    eax, eax
0x18000e823  mov     eax, 318h
0x18000e828  js      loc_18000E628
0x18000e82e  mov     [rsp+1E0h+var_194], ax
0x18000e833  mov     qword ptr [rdi+2F8h], 0
0x18000e83e  mov     qword ptr [rdi+300h], 0
0x18000e849  mov     qword ptr [rdi+308h], 0
0x18000e854  mov     qword ptr [rdi+310h], 0
0x18000e85f  mov     qword ptr [rdi+318h], 0
0x18000e86a  mov     qword ptr [rdi+320h], 0
0x18000e875  test    esi, esi
0x18000e877  jz      loc_18000E95A
0x18000e87d  mov     edx, r15d
0x18000e880  mov     rcx, rdi
0x18000e883  call    ?_SetPhase@CDefragOperation@@IEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0001@@@Z; CDefragOperation::_SetPhase(__MIDL___MIDL_itf_dfengine_0000_0000_0001)
0x18000e888  mov     [rsp+1E0h+var_198], eax
0x18000e88c  test    eax, eax
0x18000e88e  mov     eax, 327h
0x18000e893  js      loc_18000E628
0x18000e899  mov     [rsp+1E0h+var_194], ax
0x18000e89e  mov     rbx, [rbp+0E0h+pv]
0x18000e8a2  mov     rcx, [rsp+1E0h+var_1A0]
0x18000e8a7  test    rcx, rcx
0x18000e8aa  jz      short loc_18000E8C2
0x18000e8ac  mov     [rsp+1E0h+var_1A0], 0
0x18000e8b5  mov     rax, [rcx]
0x18000e8b8  mov     rax, [rax+10h]
0x18000e8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8c1  nop
0x18000e8c2  mov     [rsp+1E0h+var_1A8], rbx; unsigned __int16 *
0x18000e8c7  lea     rax, [rbp+0E0h+var_F0]
0x18000e8cb  mov     [rsp+1E0h+var_1B0], rax; unsigned __int64 *
0x18000e8d0  lea     rax, [rbp+0E0h+var_E8]
0x18000e8d4  mov     [rsp+1E0h+var_1B8], rax; unsigned __int64 *
0x18000e8d9  lea     rax, [rbp+0E0h+var_60]
0x18000e8e0  mov     [rsp+1E0h+var_1C0], rax; struct __MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *
0x18000e8e5  lea     r9, [rsp+1E0h+var_1A0]; struct IRunnableThread **
0x18000e8ea  mov     r8, [rbp+0E0h+var_158]; struct IVolume *
0x18000e8ee  mov     edx, r15d; int
0x18000e8f1  mov     ecx, r15d; int
0x18000e8f4  call    ?CreateInstance@CRunAnalysis@@SAJHHPEAUIVolume@@PEAPEAUIRunnableThread@@PEAU__MIDL___MIDL_itf_dfengine_np_0000_0000_0001@@PEA_K3PEAG@Z; CRunAnalysis::CreateInstance(int,int,IVolume *,IRunnableThread * *,__MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *,unsigned __int64 *,unsigned __int64 *,ushort *)
0x18000e8f9  mov     [rsp+1E0h+var_198], eax
0x18000e8fd  test    eax, eax
0x18000e8ff  mov     eax, 331h
0x18000e904  js      loc_18000E628
0x18000e90a  mov     [rsp+1E0h+var_194], ax
0x18000e90f  mov     rcx, [rsp+1E0h+var_1A0]
0x18000e914  mov     rax, [rcx]
0x18000e917  mov     rdx, [rdi+28h]
0x18000e91b  mov     rax, [rax+18h]
0x18000e91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e924  mov     [rsp+1E0h+var_198], eax
0x18000e928  test    eax, eax
0x18000e92a  mov     eax, 334h
0x18000e92f  js      loc_18000E628
0x18000e935  mov     [rsp+1E0h+var_194], ax
0x18000e93a  mov     rcx, [rsp+1E0h+var_1A0]
0x18000e93f  test    rcx, rcx
0x18000e942  jz      short loc_18000E95A
0x18000e944  mov     [rsp+1E0h+var_1A0], 0
0x18000e94d  mov     rax, [rcx]
0x18000e950  mov     rax, [rax+10h]
0x18000e954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e959  nop
0x18000e95a  mov     rcx, [rdi+30h]
0x18000e95e  lea     r14, [rdi+38h]
0x18000e962  mov     rax, [rcx]
0x18000e965  mov     rdx, r14
0x18000e968  mov     rax, [rax+18h]
0x18000e96c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e971  mov     [rsp+1E0h+var_198], eax
0x18000e975  test    eax, eax
0x18000e977  mov     eax, 33Bh
0x18000e97c  js      loc_18000E628
0x18000e982  mov     [rsp+1E0h+var_194], ax
0x18000e987  mov     qword ptr [rdi+0C0h], 0
0x18000e992  mov     rcx, [rbp+0E0h+var_160]
0x18000e996  test    rcx, rcx
0x18000e999  jz      short loc_18000E9B0
0x18000e99b  mov     [rbp+0E0h+var_160], 0
0x18000e9a3  mov     rax, [rcx]
0x18000e9a6  mov     rax, [rax+10h]
0x18000e9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9af  nop
0x18000e9b0  lea     r8, [rbp+0E0h+var_160]; struct IFreeSpaceManager **
0x18000e9b4  mov     rdx, [rdi+90h]; unsigned __int64
0x18000e9bb  mov     rcx, [rdi+2B8h]; unsigned __int16 *
0x18000e9c2  call    ?CreateInstance@CFreeSpaceManager@@SAJPEAG_KPEAPEAUIFreeSpaceManager@@@Z; CFreeSpaceManager::CreateInstance(ushort *,unsigned __int64,IFreeSpaceManager * *)
0x18000e9c7  mov     [rsp+1E0h+var_198], eax
0x18000e9cb  test    eax, eax
0x18000e9cd  mov     eax, 344h
0x18000e9d2  js      loc_18000E628
0x18000e9d8  mov     [rsp+1E0h+var_194], ax
0x18000e9dd  mov     rcx, [rbp+0E0h+var_160]
0x18000e9e1  mov     rax, [rdi+0B0h]
0x18000e9e8  mov     [rbp+0E0h+var_120], rax
0x18000e9ec  mov     rax, [rdi+0A8h]
0x18000e9f3  mov     [rbp+0E0h+var_118], rax
0x18000e9f7  mov     rax, [rcx]
0x18000e9fa  lea     rdx, [rbp+0E0h+var_120]
0x18000e9fe  mov     rax, [rax+30h]
0x18000ea02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea07  mov     [rsp+1E0h+var_198], eax
0x18000ea0b  test    eax, eax
0x18000ea0d  mov     eax, 349h
0x18000ea12  js      loc_18000E628
0x18000ea18  mov     [rsp+1E0h+var_194], ax
0x18000ea1d  mov     eax, [rdi+98h]
0x18000ea23  test    eax, eax
0x18000ea25  jz      short loc_18000EA37
0x18000ea27  mov     ecx, eax
0x18000ea29  xor     edx, edx
0x18000ea2b  mov     rax, [rbp+0E0h+var_E0]
0x18000ea2f  div     rcx
0x18000ea32  mov     r12, rax
0x18000ea35  jmp     short loc_18000EA3A
0x18000ea37  xor     r12d, r12d
0x18000ea3a  mov     rbx, [rbp+0E0h+var_158]
0x18000ea3e  mov     rax, [rbx]
0x18000ea41  mov     rsi, [rax+68h]
0x18000ea45  mov     rcx, [rbp+0E0h+var_148]
0x18000ea49  test    rcx, rcx
  ... truncated ...
```
