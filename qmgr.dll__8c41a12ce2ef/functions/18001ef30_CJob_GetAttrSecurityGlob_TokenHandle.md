# CJob::GetAttrSecurityGlob(TokenHandle)

- ea: `0x18001ef30`
- end: `0x18001fa06`
- name: `?GetAttrSecurityGlob@CJob@@MEAAPEAUTRANSFER_GLOB@1@VTokenHandle@@@Z`
- size: `2774`
- prototype: `_QWORD *__fastcall(__int64, TokenHandle *)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800065ac`
- `0x180006640`
- `0x180014310`
- `0x18001c8fc`
- `0x18001dac0`
- `0x18001dad4`
- `0x18001df10`
- `0x18001ef30`
- `0x18001fa0c`
- `0x18001fa58`
- `0x18001fab8`
- `0x180020894`
- `0x1800213d8`
- `0x180035c04`
- `0x180066a40`
- `0x1800720e0`
- `0x18008df60`
- `0x18008e2ec`
- `0x18008ea2c`
- `0x1800961b8`
- `0x180099740`
- `0x18009d024`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800b8a5c`
- `0x1800cc400`
- `0x1800f4f2c`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001f31c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001f465`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001f80f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001f31c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001f465`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001f80f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001f57e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001f57e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001f71f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001f71f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
_QWORD *__fastcall CJob::GetAttrSecurityGlob(__int64 a1, TokenHandle *a2)
{
  __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  EVENT_LOG *v6; // rcx
  _QWORD *result; // rax
  CJob::TRANSFER_GLOB *v8; // rax
  void *v9; // r11
  __int64 v10; // rcx
  char v11; // r15
  int v12; // r12d
  int v13; // r14d
  bool v14; // di
  int v15; // esi
  TokenHandle *v16; // r12
  const IID *v17; // rdi
  struct IAbstractFile *DownloadReader; // rbx
  CAttrSecurityTransfer *v19; // rax
  CAttrSecurityTransfer *v20; // rdx
  CJob *v21; // rbx
  _QWORD *v22; // rsi
  __int128 *v23; // rcx
  __int64 v24; // rcx
  const unsigned __int16 *FriendlyBITSJobName; // rax
  __int64 v26; // r8
  __int64 v27; // rcx
  _OWORD *v28; // rdi
  const unsigned __int16 *v29; // r13
  __int128 *v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r8
  bool v33; // dl
  int v34; // eax
  __int64 v35; // rdx
  __int128 v36; // xmm0
  __int128 *v37; // rcx
  __int128 *v38; // rcx
  const unsigned __int16 *v39; // rax
  __int64 v40; // r8
  HRESULT v41; // ecx
  __int64 v42; // r8
  CJob *v43; // rax
  __int128 *v44; // rax
  __int64 *v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rdx
  ComError *v48; // rax
  unsigned int v49; // edx
  char v50; // [rsp+58h] [rbp-3F0h]
  int v51; // [rsp+88h] [rbp-3C0h]
  LPVOID Context; // [rsp+A0h] [rbp-3A8h] BYREF
  CJob::TRANSFER_GLOB *v53; // [rsp+A8h] [rbp-3A0h] BYREF
  CJob *PdcClientRegistrationHandle; // [rsp+B0h] [rbp-398h] BYREF
  void *v55; // [rsp+B8h] [rbp-390h] BYREF
  TokenHandle *v56; // [rsp+C0h] [rbp-388h] BYREF
  __int128 *v57; // [rsp+C8h] [rbp-380h] BYREF
  unsigned __int64 v58; // [rsp+D0h] [rbp-378h] BYREF
  __int64 v59; // [rsp+D8h] [rbp-370h]
  __int64 v60; // [rsp+E0h] [rbp-368h]
  __int64 v61; // [rsp+E8h] [rbp-360h] BYREF
  void *v62; // [rsp+F0h] [rbp-358h] BYREF
  CAttrSecurityTransfer *v63; // [rsp+F8h] [rbp-350h]
  struct IAbstractFile *v64; // [rsp+100h] [rbp-348h]
  CJob::TRANSFER_GLOB *v65; // [rsp+108h] [rbp-340h]
  TokenHandle *v66; // [rsp+110h] [rbp-338h]
  const ComError *v67; // [rsp+118h] [rbp-330h] BYREF
  void **pExceptionObject; // [rsp+120h] [rbp-328h] BYREF
  __int128 v69; // [rsp+128h] [rbp-320h]
  int v70; // [rsp+138h] [rbp-310h]
  int v71; // [rsp+13Ch] [rbp-30Ch]
  int v72; // [rsp+140h] [rbp-308h]
  void **v73; // [rsp+180h] [rbp-2C8h] BYREF
  __int128 v74; // [rsp+188h] [rbp-2C0h]
  int v75; // [rsp+198h] [rbp-2B0h]
  int v76; // [rsp+19Ch] [rbp-2ACh]
  int v77; // [rsp+1A0h] [rbp-2A8h]
  void **v78; // [rsp+1E0h] [rbp-268h] BYREF
  __int128 v79; // [rsp+1E8h] [rbp-260h]
  int v80; // [rsp+1F8h] [rbp-250h]
  int v81; // [rsp+1FCh] [rbp-24Ch]
  int v82; // [rsp+200h] [rbp-248h]
  void **v83; // [rsp+240h] [rbp-208h] BYREF
  __int128 v84; // [rsp+248h] [rbp-200h]
  HRESULT v85; // [rsp+258h] [rbp-1F0h]
  int v86; // [rsp+25Ch] [rbp-1ECh]
  int v87; // [rsp+260h] [rbp-1E8h]
  void **v88; // [rsp+2A0h] [rbp-1A8h] BYREF
  __int128 v89; // [rsp+2A8h] [rbp-1A0h]
  int v90; // [rsp+2B8h] [rbp-190h]
  int v91; // [rsp+2BCh] [rbp-18Ch]
  int v92; // [rsp+2C0h] [rbp-188h]
  void **v93; // [rsp+300h] [rbp-148h] BYREF
  __int128 v94; // [rsp+308h] [rbp-140h]
  int v95; // [rsp+318h] [rbp-130h]
  int v96; // [rsp+31Ch] [rbp-12Ch]
  int v97; // [rsp+320h] [rbp-128h]
  __int64 v98; // [rsp+360h] [rbp-E8h] BYREF
  __int128 v99; // [rsp+3B8h] [rbp-90h] BYREF
  __int64 v100; // [rsp+3C8h] [rbp-80h]
  unsigned __int64 v101; // [rsp+3D0h] [rbp-78h]
  __int128 v102; // [rsp+3D8h] [rbp-70h] BYREF
  __int64 v103; // [rsp+3E8h] [rbp-60h]
  unsigned __int64 v104; // [rsp+3F0h] [rbp-58h]
  __int128 v105; // [rsp+3F8h] [rbp-50h] BYREF
  __int64 v106; // [rsp+408h] [rbp-40h]
  unsigned __int64 v107; // [rsp+410h] [rbp-38h]

  try
  {
    v56 = a2;
    PdcClientRegistrationHandle = (CJob *)a1;
    v66 = a2;
    v65 = 0;
    v64 = 0;
    v63 = 0;
    v4 = *(_QWORD *)(a1 + 848);
    v5 = *(unsigned int *)(a1 + 844);
    if ( v5 >= (*(_QWORD *)(a1 + 856) - v4) >> 3 )
    {
      v94 = 0;
      v93 = &ComError::`vftable';
      v95 = -2147023537;
      v96 = 4425;
      v97 = 1;
      throw (ComError *)&v93;
    }
    if ( !*(_DWORD *)(a1 + 1232) || **(_QWORD **)(a1 + 1240) )
    {
      URLParser::CanonicalizeURL(&v55, *(_QWORD *)(*(_QWORD *)(v4 + 8 * v5) + 8LL) + 12LL, 0);
      v8 = (CJob::TRANSFER_GLOB *)operator new(0x58u);
      v53 = v8;
      if ( v8 )
      {
        v9 = (void *)CJob::TRANSFER_GLOB::TRANSFER_GLOB(v8);
        Context = v9;
      }
      else
      {
        v9 = 0;
        Context = 0;
      }
      v65 = (CJob::TRANSFER_GLOB *)v9;
      v10 = a1 & -(__int64)(*(_BYTE *)(a1 + 1504) != 0);
      v11 = *(_BYTE *)(a1 + 744);
      v12 = *(_DWORD *)(a1 + 1208);
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 1288) + 8LL));
      v61 = *(_QWORD *)(a1 + 1288);
      v13 = *(_DWORD *)(a1 + 1276);
      v14 = *(_DWORD *)(a1 + 656) != 0;
      v15 = *(_DWORD *)(a1 + 1232);
      v58 = *(_QWORD *)(a1 + 712);
      v59 = *(_QWORD *)(a1 + 720);
      _InterlockedIncrement((volatile signed __int32 *)v59);
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 696) + 8LL));
      v62 = *(void **)(a1 + 696);
      v57 = (__int128 *)(a1 + 676);
      v51 = v12;
      v50 = v14;
      v16 = v56;
      v17 = (const IID *)(a1 + 676);
      DownloadReader = (struct IAbstractFile *)GetDownloadReader(
                                                 (unsigned __int8 *)v55 + 12,
                                                 a1 + 676,
                                                 &v62,
                                                 (void **)&v58,
                                                 a1 + 913,
                                                 (__int64)v9 + 56,
                                                 a1 + 1008,
                                                 (CCredentialsContainer *)(a1 + 1032),
                                                 (__int64)v56,
                                                 a1 + 1240,
                                                 v15,
                                                 v50,
                                                 v13,
                                                 &v61,
                                                 0,
                                                 a1 + 1072,
                                                 a1 + 1064,
                                                 v51,
                                                 v11,
                                                 (v10 + 616) & -(__int64)(v10 != 0));
      v64 = DownloadReader;
      v19 = (CAttrSecurityTransfer *)operator new(0x168u);
      v53 = v19;
      if ( v19 )
        v20 = CAttrSecurityTransfer::CAttrSecurityTransfer(v19, DownloadReader);
      else
        v20 = 0;
      v63 = v20;
      v21 = PdcClientRegistrationHandle;
      v22 = Context;
      *(_QWORD *)Context = PdcClientRegistrationHandle;
      v22[1] = *(_QWORD *)(*((_QWORD *)v21 + 106) + 8LL * *((unsigned int *)v21 + 211));
      v22[2] =  CJob::`vcall'{312,{flat}};
      *((_DWORD *)v22 + 6) = 0;
      *((_DWORD *)v22 + 7) = HIDWORD(v59);
      v22[4] = v20;
      if ( CJob::IsPdcNetworkActivationRequested(v21) )
      {
        Context = 0;
        if ( !InitOnceExecuteOnce(&g_pdcManager, LazyGlobal<PdcManager>::LazyGlobalInitializer, 0, &Context) )
        {
          v69 = 0;
          pExceptionObject = &ComError::`vftable';
          v70 = -2147024882;
          v71 = 51;
          v72 = 1;
          throw (ComError *)&pExceptionObject;
        }
        if ( PdcManager::IsPdcFeatureAvailable((PdcManager *)Context) )
        {
          v105 = 0;
          v107 = 0;
          std::wstring::_Construct_empty(&v105);
          v106 = 0;
          v23 = &v105;
          if ( v107 > 7 )
            v23 = (__int128 *)v105;
          *(_WORD *)v23 = 0;
          v24 = *((_QWORD *)v21 + 92);
          if ( v24 )
          {
            AppPackageInfo::GetAppUserModelId(v24, &v105);
          }
          else
          {
            FriendlyBITSJobName = CTelemetry::GetFriendlyBITSJobName((LPCWCH)(*((_QWORD *)v21 + 87) + 12LL));
            v26 = -1;
            do
              ++v26;
            while ( FriendlyBITSJobName[v26] );
            std::wstring::_Assign<unsigned short>(&v105, FriendlyBITSJobName);
          }
          v28 = operator new(0xA0u);
          v53 = (CJob::TRANSFER_GLOB *)v28;
          if ( v28 )
          {
            Context = 0;
            if ( !InitOnceExecuteOnce(&g_pdcManager, LazyGlobal<PdcManager>::LazyGlobalInitializer, 0, &Context) )
            {
              v74 = 0;
              v73 = &ComError::`vftable';
              v75 = -2147024882;
              v76 = 51;
              v77 = 1;
              throw (ComError *)&v73;
            }
            PdcClientRegistrationHandle = (CJob *)PdcManager::GetPdcClientRegistrationHandle((PdcManager *)Context);
            v29 = CTelemetry::JobTypeAsString((enum BG_JOB_TYPE)*((_DWORD *)v21 + 166));
            v30 = &v105;
            if ( v107 > 7 )
              v30 = (__int128 *)v105;
            *v28 = *(_OWORD *)((char *)v21 + 676);
            v28[1] = 0;
            *((_QWORD *)v28 + 4) = 0;
            *((_QWORD *)v28 + 5) = 0;
            v31 = -1;
            do
              ++v31;
            while ( *((_WORD *)v30 + v31) );
            std::wstring::_Construct<1,unsigned short const *>(v28 + 1, v30);
            v28[3] = 0;
            *((_QWORD *)v28 + 8) = 0;
            *((_QWORD *)v28 + 9) = 0;
            v32 = -1;
            do
              ++v32;
            while ( v29[v32] );
            std::wstring::_Construct<1,unsigned short const *>(v28 + 3, v29);
            *((_QWORD *)v28 + 10) = PdcClientRegistrationHandle;
            CCritSec2::CCritSec2((CCritSec2 *)((char *)v28 + 88), v33);
            *((_QWORD *)v28 + 17) = 0;
            *((_DWORD *)v28 + 36) = 0;
            *((_QWORD *)v28 + 19) = GetTickCount64();
            v34 = ScopedPdcActivationHolder::PdcActivateNetwork((ScopedPdcActivationHolder *)v28);
            v27 = (unsigned int)v34;
            if ( v34 < 0 )
            {
              v79 = 0;
              v78 = &ComError::`vftable';
              v80 = v34;
              v81 = 218;
              v82 = 1;
              throw (ComError *)&v78;
            }
          }
          else
          {
            v28 = 0;
          }
          v35 = v22[9];
          v22[9] = v28;
          if ( v35 )
            std::default_delete<ScopedPdcActivationHolder>::operator()(v27);
          if ( v107 > 7 )
            std::_Deallocate<16>(v105, 2 * v107 + 2);
          v17 = (const IID *)((char *)v21 + 676);
        }
      }
      v36 = 0;
      v99 = 0;
      v101 = 0;
      *(double *)&v36 = std::wstring::_Construct_empty(&v99);
      v102 = v36;
      v104 = 0;
      std::wstring::_Construct_empty(&v102);
      v100 = 0;
      v37 = &v99;
      if ( v101 > 7 )
        v37 = (__int128 *)v99;
      *(_WORD *)v37 = 0;
      v103 = 0;
      v38 = &v102;
      if ( v104 > 7 )
        v38 = (__int128 *)v102;
      *(_WORD *)v38 = 0;
      if ( CJob::IsOwnedByAppPackage(v21) )
      {
        AppPackageInfo::GetAppUserModelId(*((_QWORD *)v21 + 92), &v99);
      }
      else
      {
        v39 = CTelemetry::GetFriendlyBITSJobName((LPCWCH)(*((_QWORD *)v21 + 87) + 12LL));
        v40 = -1;
        do
          ++v40;
        while ( v39[v40] );
        std::wstring::_Assign<unsigned short>(&v99, v39);
      }
      Context = 0;
      v41 = StringFromCLSID(v17, (LPOLESTR *)&Context);
      if ( v41 < 0 )
      {
        v84 = 0;
        v83 = &ComError::`vftable';
        v85 = v41;
        v86 = 807;
        v87 = 1;
        throw (ComError *)&v83;
      }
      v42 = -1;
      do
        ++v42;
      while ( *((_WORD *)Context + v42) );
      std::wstring::_Assign<unsigned short>(&v102, Context);
      if ( Context )
        CoTaskMemFree(Context);
      v43 = (CJob *)&v102;
      if ( v104 > 7 )
        v43 = (CJob *)v102;
      PdcClientRegistrationHandle = v43;
      v44 = &v99;
      if ( v101 > 7 )
        v44 = (__int128 *)v99;
      v57 = v44;
      Context = 0;
      if ( !InitOnceExecuteOnce(&g_SmePolicyTracker, LazyGlobal<SmePolicyTracker>::LazyGlobalInitializer, 0, &Context) )
      {
        v89 = 0;
        v88 = &ComError::`vftable';
        v90 = -2147024882;
        v91 = 51;
        v92 = 1;
        throw (ComError *)&v88;
      }
      v56 = (TokenHandle *)Context;
      v45 = (__int64 *)std::make_unique<ScopedSmeTaskHolder,SmePolicyTracker *,SmePolicyID &,unsigned short const *,unsigned short const *,0>(
                         (unsigned int)&v53,
                         (unsigned int)&v56,
                         (int)v21 + 1472,
                         (unsigned int)&v57,
                         (__int64)&PdcClientRegistrationHandle);
      v46 = *v45;
      *v45 = 0;
      v47 = v22[10];
      v22[10] = v46;
      if ( v47 )
        std::default_delete<ScopedSmeTaskHolder>::operator()();
      if ( v53 )
        std::default_delete<ScopedSmeTaskHolder>::operator()();
      if ( v104 > 7 )
        std::_Deallocate<16>(v102, 2 * v104 + 2);
      v103 = 0;
      v104 = 7;
      LOWORD(v102) = 0;
      if ( v101 > 7 )
        std::_Deallocate<16>(v99, 2 * v101 + 2);
      v100 = 0;
      v101 = 7;
      LOWORD(v99) = 0;
      if ( v55 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v55 + 2, 0xFFFFFFFF) == 1 )
          operator delete(v55, 0x10u);
        v55 = 0;
      }
      TokenHandle::Decrement(v16);
      result = v22;
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      v58 = 0x8020005600000004uLL;
      v60 = 0;
      v59 = 0x200000001LL;
      if ( v6 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
        WPP_SF_llDDS(
          *((_QWORD *)v6 + 2),
          (unsigned int)&word_18011AC70,
          -2145386410,
          4,
          1,
          86,
          2,
          (__int64)&word_18011AC70);
      (*(void (__fastcall **)(__int64, unsigned __int64 *, __int64))(*(_QWORD *)a1 + 456LL))(a1, &v58, -1);
      TokenHandle::Decrement(a2);
      result = 0;
    }
  }
  catch ( const ComError *v67 )
  {
    v48 = ComError::ComError((ComError *)&v98, v67);
    LogException(v48);
    operator delete(v63, 8u);
    if ( v64 )
      (*(void (__fastcall **)(struct IAbstractFile *, __int64))(*(_QWORD *)v64 + 32LL))(v64, 1);
    if ( v65 )
      CJob::TRANSFER_GLOB::`scalar deleting destructor'(v65, v49);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18001ef30  mov     r11, rsp
0x18001ef33  mov     [r11+18h], rbx
0x18001ef37  mov     [r11+20h], rsi
0x18001ef3b  push    rdi
0x18001ef3c  push    r12
0x18001ef3e  push    r13
0x18001ef40  push    r14
0x18001ef42  push    r15
0x18001ef44  sub     rsp, 420h
0x18001ef4b  mov     rax, cs:__security_cookie
0x18001ef52  xor     rax, rsp
0x18001ef55  mov     [rsp+448h+var_30], rax
0x18001ef5d  mov     rdi, rdx
0x18001ef60  mov     [r11-388h], rdx
0x18001ef67  mov     rbx, rcx
0x18001ef6a  mov     [rsp+448h+var_398], rcx
0x18001ef72  mov     [r11-338h], rdx
0x18001ef79  xor     esi, esi
0x18001ef7b  mov     [rsp+448h+var_340], rsi
0x18001ef83  mov     [rsp+448h+var_348], rsi
0x18001ef8b  mov     [rsp+448h+var_350], rsi
0x18001ef93  mov     rcx, [rcx+350h]
0x18001ef9a  mov     edx, [rbx+34Ch]
0x18001efa0  mov     rax, [rbx+358h]
0x18001efa7  sub     rax, rcx
0x18001efaa  sar     rax, 3
0x18001efae  cmp     rdx, rax
0x18001efb1  jnb     loc_18001F989
0x18001efb7  cmp     [rbx+4D0h], esi
0x18001efbd  jz      loc_18001F09E
0x18001efc3  mov     rax, [rbx+4D8h]
0x18001efca  cmp     [rax], rsi
0x18001efcd  jnz     loc_18001F09E
0x18001efd3  lea     r14, WPP_GLOBAL_Control
0x18001efda  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efe1  cmp     rcx, r14
0x18001efe4  jz      short loc_18001F006
0x18001efe6  test    byte ptr [rcx+1Ch], 2
0x18001efea  jz      short loc_18001F006
0x18001efec  lea     edx, [rsi+76h]
0x18001efef  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18001eff6  mov     rcx, [rcx+10h]
0x18001effa  call    WPP_SF_
0x18001efff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f006  mov     r9d, 4
0x18001f00c  mov     dword ptr [rsp+448h+var_378], r9d
0x18001f014  mov     [rsp+448h+var_368], rsi
0x18001f01c  mov     dword ptr [rsp+448h+var_370+4], 2
0x18001f027  lea     eax, [r9-3]
0x18001f02b  mov     dword ptr [rsp+448h+var_370], eax
0x18001f032  mov     r8d, 80200056h
0x18001f038  mov     dword ptr [rsp+448h+var_378+4], r8d
0x18001f040  cmp     rcx, r14
0x18001f043  jz      short loc_18001F070
0x18001f045  test    [rcx+1Ch], al
0x18001f048  jz      short loc_18001F070
0x18001f04a  lea     rdx, word_18011AC70
0x18001f051  mov     [rsp+448h+var_410], rdx
0x18001f056  mov     dword ptr [rsp+448h+var_418], 2
0x18001f05e  mov     dword ptr [rsp+448h+var_420], r8d
0x18001f063  mov     dword ptr [rsp+448h+var_428], eax
0x18001f067  mov     rcx, [rcx+10h]
0x18001f06b  call    WPP_SF_llDDS
0x18001f070  mov     rax, [rbx]
0x18001f073  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f077  lea     rdx, [rsp+448h+var_378]
0x18001f07f  mov     rcx, rbx
0x18001f082  mov     rax, [rax+1C8h]
0x18001f089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f08e  nop
0x18001f08f  mov     rcx, rdi; this
0x18001f092  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18001f097  xor     eax, eax
0x18001f099  jmp     loc_18001F9D9
0x18001f09e  mov     rax, [rcx+rdx*8]
0x18001f0a2  mov     rdx, [rax+8]
0x18001f0a6  add     rdx, 0Ch
0x18001f0aa  xor     r8d, r8d
0x18001f0ad  lea     rcx, [rsp+448h+var_390]
0x18001f0b5  call    ?CanonicalizeURL@URLParser@@SA?AV?$GenericStringHandle@G@@PEBGPEAV2@@Z; URLParser::CanonicalizeURL(ushort const *,GenericStringHandle<ushort> *)
0x18001f0ba  nop
0x18001f0bb  mov     ecx, 58h ; 'X'; dwBytes
0x18001f0c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f0c5  mov     [rsp+448h+var_3A0], rax
0x18001f0cd  test    rax, rax
0x18001f0d0  jz      short loc_18001F0E7
0x18001f0d2  mov     rcx, rax; this
0x18001f0d5  call    ??0TRANSFER_GLOB@CJob@@QEAA@XZ; CJob::TRANSFER_GLOB::TRANSFER_GLOB(void)
0x18001f0da  mov     r11, rax
0x18001f0dd  mov     [rsp+448h+Context], rax
0x18001f0e5  jmp     short loc_18001F0F2
0x18001f0e7  mov     r11, rsi
0x18001f0ea  mov     [rsp+448h+Context], rsi
0x18001f0f2  mov     [rsp+448h+var_340], r11
0x18001f0fa  mov     al, [rbx+5E0h]
0x18001f100  neg     al
0x18001f102  sbb     rcx, rcx
0x18001f105  and     rcx, rbx
0x18001f108  lea     rax, [rcx+268h]
0x18001f10f  neg     rcx
0x18001f112  sbb     r13, r13
0x18001f115  and     r13, rax
0x18001f118  mov     r15b, [rbx+2E8h]
0x18001f11f  mov     r12d, [rbx+4B8h]
0x18001f126  mov     rax, [rbx+508h]
0x18001f12d  lock inc dword ptr [rax+8]
0x18001f131  mov     rax, [rbx+508h]
0x18001f138  mov     [rsp+448h+var_360], rax
0x18001f140  mov     r14d, [rbx+4FCh]
0x18001f147  cmp     [rbx+290h], esi
0x18001f14d  setnz   dil
0x18001f151  mov     esi, [rbx+4D0h]
0x18001f157  mov     rax, [rbx+2C8h]
0x18001f15e  mov     [rsp+448h+var_378], rax
0x18001f166  mov     rax, [rbx+2D0h]
0x18001f16d  mov     [rsp+448h+var_370], rax
0x18001f175  lock inc dword ptr [rax]
0x18001f178  mov     rax, [rbx+2B8h]
0x18001f17f  lock inc dword ptr [rax+8]
0x18001f183  mov     rax, [rbx+2B8h]
0x18001f18a  mov     [rsp+448h+var_358], rax
0x18001f192  lea     rax, [rbx+2A4h]
0x18001f199  mov     [rsp+448h+var_380], rax
0x18001f1a1  lea     rax, [rbx+428h]
0x18001f1a8  lea     rdx, [rbx+430h]
0x18001f1af  lea     r8, [rbx+4D8h]
0x18001f1b6  lea     r9, [rbx+408h]
0x18001f1bd  lea     r10, [rbx+3F0h]
0x18001f1c4  add     r11, 38h ; '8'
0x18001f1c8  add     rbx, 391h
0x18001f1cf  mov     rcx, [rsp+448h+var_390]
0x18001f1d7  add     rcx, 0Ch
0x18001f1db  mov     [rsp+448h+var_3B0], r13
0x18001f1e3  mov     [rsp+448h+var_3B8], r15b
0x18001f1eb  mov     [rsp+448h+var_3C0], r12d
0x18001f1f3  mov     [rsp+448h+var_3C8], rax
0x18001f1fb  mov     [rsp+448h+var_3D0], rdx
0x18001f200  xor     r13d, r13d
0x18001f203  mov     [rsp+448h+var_3D8], r13
0x18001f208  lea     rax, [rsp+448h+var_360]
0x18001f210  mov     [rsp+448h+var_3E0], rax
0x18001f215  mov     [rsp+448h+var_3E8], r14d
0x18001f21a  mov     [rsp+448h+var_3F0], dil
0x18001f21f  mov     [rsp+448h+var_3F8], esi
0x18001f223  mov     [rsp+448h+var_400], r8
0x18001f228  mov     r12, [rsp+448h+var_388]
0x18001f230  mov     [rsp+448h+var_408], r12
0x18001f235  mov     [rsp+448h+var_410], r9
0x18001f23a  mov     [rsp+448h+var_418], r10
0x18001f23f  mov     [rsp+448h+var_420], r11
0x18001f244  mov     [rsp+448h+var_428], rbx
0x18001f249  lea     r9, [rsp+448h+var_378]
0x18001f251  lea     r8, [rsp+448h+var_358]
0x18001f259  mov     rdi, [rsp+448h+var_380]
0x18001f261  mov     rdx, rdi
0x18001f264  call    ?GetDownloadReader@@YAPEAVIAbstractFile@@PEBGAEBU_GUID@@V?$GenericStringHandle@G@@VSidHandle@@PEA_N1PEBUPROXY_SETTINGS@@PEBVCCredentialsContainer@@AEBVTokenHandle@@7K_NK2PEAVCNetworkMonitor@@PEAVCClientCertificate@@PEBVCCustomHeaders@@K8PEAUIServerCertificateValidator@@@Z; GetDownloadReader(ushort const *,_GUID const &,GenericStringHandle<ushort>,SidHandle,bool *,_GUID const &,PROXY_SETTINGS const *,CCredentialsContainer const *,TokenHandle const &,TokenHandle const &,ulong,bool,ulong,GenericStringHandle<ushort>,CNetworkMonitor *,CClientCertificate *,CCustomHeaders const *,ulong,bool,IServerCertificateValidator *)
0x18001f269  mov     rbx, rax
0x18001f26c  mov     [rsp+448h+var_348], rax
0x18001f274  mov     ecx, 168h; dwBytes
0x18001f279  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f27e  mov     [rsp+448h+var_3A0], rax
0x18001f286  test    rax, rax
0x18001f289  jz      short loc_18001F29B
0x18001f28b  mov     rdx, rbx; struct IAbstractFile *
0x18001f28e  mov     rcx, rax; this
0x18001f291  call    ??0CAttrSecurityTransfer@@QEAA@PEAVIAbstractFile@@@Z; CAttrSecurityTransfer::CAttrSecurityTransfer(IAbstractFile *)
0x18001f296  mov     rdx, rax
0x18001f299  jmp     short loc_18001F29E
0x18001f29b  mov     rdx, r13
0x18001f29e  mov     [rsp+448h+var_350], rdx
0x18001f2a6  mov     rbx, [rsp+448h+var_398]
0x18001f2ae  mov     rsi, [rsp+448h+Context]
0x18001f2b6  mov     [rsi], rbx
0x18001f2b9  mov     ecx, [rbx+34Ch]
0x18001f2bf  mov     rax, [rbx+350h]
0x18001f2c6  mov     rcx, [rax+rcx*8]
0x18001f2ca  mov     [rsi+8], rcx
0x18001f2ce  lea     rax, ??_9CJob@@$BBDI@AA; [thunk]: CJob::`vcall'{312,{flat}}
0x18001f2d5  mov     [rsi+10h], rax
0x18001f2d9  mov     [rsi+18h], r13d
0x18001f2dd  mov     eax, dword ptr [rsp+448h+var_370+4]
0x18001f2e4  mov     [rsi+1Ch], eax
0x18001f2e7  mov     [rsi+20h], rdx
0x18001f2eb  mov     rcx, rbx; this
0x18001f2ee  call    ?IsPdcNetworkActivationRequested@CJob@@QEAA_NXZ; CJob::IsPdcNetworkActivationRequested(void)
0x18001f2f3  test    al, al
0x18001f2f5  jz      loc_18001F6D1
0x18001f2fb  mov     [rsp+448h+Context], r13
0x18001f303  lea     r9, [rsp+448h+Context]; Context
0x18001f30b  xor     r8d, r8d; Parameter
0x18001f30e  lea     rdx, ?LazyGlobalInitializer@?$LazyGlobal@VPdcManager@@@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001f315  lea     rcx, ?g_pdcManager@@3V?$LazyGlobal@VPdcManager@@@@A; InitOnce
0x18001f31c  call    cs:__imp_InitOnceExecuteOnce
0x18001f322  test    eax, eax
0x18001f324  jnz     short loc_18001F375
0x18001f326  xorps   xmm0, xmm0
0x18001f329  movups  [rsp+448h+var_320], xmm0
0x18001f331  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18001f338  mov     [rsp+448h+pExceptionObject], rax
0x18001f340  mov     [rsp+448h+var_310], 8007000Eh
0x18001f34b  mov     [rsp+448h+var_30C], 33h ; '3'
0x18001f356  mov     [rsp+448h+var_308], 1
0x18001f361  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001f368  lea     rcx, [rsp+448h+pExceptionObject]; pExceptionObject
0x18001f370  call    _CxxThrowException_0
0x18001f375  mov     rcx, [rsp+448h+Context]; this
0x18001f37d  call    ?IsPdcFeatureAvailable@PdcManager@@QEAA_NXZ; PdcManager::IsPdcFeatureAvailable(void)
0x18001f382  test    al, al
0x18001f384  jz      loc_18001F6D1
0x18001f38a  xorps   xmm0, xmm0
0x18001f38d  movups  [rsp+448h+var_50], xmm0
0x18001f395  mov     [rsp+448h+var_38], r13
0x18001f39d  lea     rcx, [rsp+448h+var_50]
0x18001f3a5  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18001f3aa  nop
0x18001f3ab  mov     [rsp+448h+var_40], r13
0x18001f3b3  lea     rcx, [rsp+448h+var_50]
0x18001f3bb  mov     r14d, 7
0x18001f3c1  cmp     [rsp+448h+var_38], r14
0x18001f3c9  cmova   rcx, qword ptr [rsp+448h+var_50]
0x18001f3d2  mov     [rcx], r13w
0x18001f3d6  mov     rcx, [rbx+2E0h]
0x18001f3dd  test    rcx, rcx
0x18001f3e0  jz      short loc_18001F3F5
0x18001f3e2  lea     rdx, [rsp+448h+var_50]
0x18001f3ea  call    ?GetAppUserModelId@AppPackageInfo@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppPackageInfo::GetAppUserModelId(std::wstring &)
0x18001f3ef  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001f3f3  jmp     short loc_18001F426
0x18001f3f5  mov     rcx, [rbx+2B8h]
0x18001f3fc  add     rcx, 0Ch; lpString1
0x18001f400  call    ?GetFriendlyBITSJobName@CTelemetry@@SAPEBGPEBG@Z; CTelemetry::GetFriendlyBITSJobName(ushort const *)
0x18001f405  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001f409  mov     r8, r15
0x18001f40c  inc     r8
0x18001f40f  cmp     [rax+r8*2], r13w
0x18001f414  jnz     short loc_18001F40C
0x18001f416  mov     rdx, rax
0x18001f419  lea     rcx, [rsp+448h+var_50]
0x18001f421  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001f426  mov     ecx, 0A0h; dwBytes
0x18001f42b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f430  mov     rdi, rax
0x18001f433  mov     [rsp+448h+var_3A0], rax
0x18001f43b  test    rax, rax
0x18001f43e  jz      loc_18001F5E7
0x18001f444  mov     [rsp+448h+Context], r13
0x18001f44c  lea     r9, [rsp+448h+Context]; Context
0x18001f454  xor     r8d, r8d; Parameter
0x18001f457  lea     rdx, ?LazyGlobalInitializer@?$LazyGlobal@VPdcManager@@@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001f45e  lea     rcx, ?g_pdcManager@@3V?$LazyGlobal@VPdcManager@@@@A; InitOnce
0x18001f465  call    cs:__imp_InitOnceExecuteOnce
0x18001f46b  test    eax, eax
0x18001f46d  jnz     short loc_18001F4BE
0x18001f46f  xorps   xmm0, xmm0
0x18001f472  movups  [rsp+448h+var_2C0], xmm0
0x18001f47a  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18001f481  mov     [rsp+448h+var_2C8], rax
0x18001f489  mov     [rsp+448h+var_2B0], 8007000Eh
0x18001f494  mov     [rsp+448h+var_2AC], 33h ; '3'
0x18001f49f  mov     [rsp+448h+var_2A8], 1
0x18001f4aa  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001f4b1  lea     rcx, [rsp+448h+var_2C8]; pExceptionObject
0x18001f4b9  call    _CxxThrowException_0
0x18001f4be  mov     rcx, [rsp+448h+Context]; this
0x18001f4c6  call    ?GetPdcClientRegistrationHandle@PdcManager@@QEAAPEAXXZ; PdcManager::GetPdcClientRegistrationHandle(void)
0x18001f4cb  mov     [rsp+448h+var_398], rax
0x18001f4d3  mov     ecx, [rbx+298h]; enum BG_JOB_TYPE
0x18001f4d9  call    ?JobTypeAsString@CTelemetry@@SAPEBGW4BG_JOB_TYPE@@@Z; CTelemetry::JobTypeAsString(BG_JOB_TYPE)
0x18001f4de  mov     r13, rax
0x18001f4e1  lea     rdx, [rsp+448h+var_50]
0x18001f4e9  cmp     [rsp+448h+var_38], r14
0x18001f4f1  cmova   rdx, qword ptr [rsp+448h+var_50]
0x18001f4fa  movups  xmm0, xmmword ptr [rbx+2A4h]
0x18001f501  movdqu  xmmword ptr [rdi], xmm0
0x18001f505  lea     rcx, [rdi+10h]
0x18001f509  xorps   xmm1, xmm1
0x18001f50c  movups  xmmword ptr [rcx], xmm1
0x18001f50f  xor     eax, eax
0x18001f511  mov     [rcx+10h], rax
0x18001f515  mov     [rcx+18h], rax
0x18001f519  mov     r8, r15
0x18001f51c  inc     r8
0x18001f51f  cmp     [rdx+r8*2], ax
0x18001f524  jnz     short loc_18001F51C
0x18001f526  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001f52b  nop
0x18001f52c  lea     rcx, [rdi+30h]
0x18001f530  xorps   xmm0, xmm0
0x18001f533  movups  xmmword ptr [rcx], xmm0
0x18001f536  xor     eax, eax
0x18001f538  mov     [rcx+10h], rax
0x18001f53c  mov     [rcx+18h], rax
0x18001f540  mov     r8, r15
0x18001f543  inc     r8
0x18001f546  cmp     [r13+r8*2+0], ax
0x18001f54c  jnz     short loc_18001F543
0x18001f54e  mov     rdx, r13
0x18001f551  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001f556  nop
0x18001f557  mov     rax, [rsp+448h+var_398]
  ... truncated ...
```
