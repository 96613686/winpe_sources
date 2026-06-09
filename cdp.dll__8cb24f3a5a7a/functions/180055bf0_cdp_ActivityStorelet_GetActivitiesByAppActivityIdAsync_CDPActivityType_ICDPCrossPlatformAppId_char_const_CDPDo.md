# cdp::ActivityStorelet::GetActivitiesByAppActivityIdAsync(CDPActivityType,ICDPCrossPlatformAppId *,char const *,CDPDownloadOptionFlags,ICDPActivitiesByAppActivityIdCallback *,char const *)

- ea: `0x180055bf0`
- end: `0x1800563ff`
- name: `?GetActivitiesByAppActivityIdAsync@ActivityStorelet@cdp@@UEAAJW4CDPActivityType@@PEAVICDPCrossPlatformAppId@@PEBDW4CDPDownloadOptionFlags@@PEAVICDPActivitiesByAppActivityIdCallback@@2@Z`
- size: `2063`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18000d350`
- `0x1800110f8`
- `0x180013da0`
- `0x18001ce80`
- `0x180030190`
- `0x180051938`
- `0x1800519dc`
- `0x180053e18`
- `0x180055518`
- `0x180055540`
- `0x1800557dc`
- `0x180055bf0`
- `0x180056b50`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800b5940`
- `0x18012d5cc`
- `0x180143248`
- `0x180199618`
- `0x1801f6fb0`
- `0x1801fc5a4`
- `0x1801fc5e8`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005611f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056201`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056293`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005611f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056201`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056293`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056325`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800561a9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800561a9`
- `msvcp_win!_Mtx_unlock` at `0x180055ecb`
- `msvcp_win!_Mtx_unlock` at `0x180055ecb`

## string_xrefs

- `0x180056150`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18005622c`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800562be`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180056350`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall cdp::ActivityStorelet::GetActivitiesByAppActivityIdAsync(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned __int64 a4,
        unsigned __int16 a5,
        __int64 a6,
        __int64 a7)
{
  unsigned __int64 v7; // rdi
  unsigned int v9; // esi
  int v11; // ecx
  int v12; // eax
  unsigned int v13; // ebx
  std::_Mutex_base *v14; // rbx
  signed __int32 v15; // r15d
  __int64 v16; // r14
  _DWORD *v17; // rsi
  __int64 v18; // rdi
  unsigned __int64 i; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // r15
  __int64 v24; // rdx
  float v25; // xmm0_4
  __int64 v26; // rcx
  float v27; // xmm1_4
  _QWORD *v28; // rcx
  __int64 *v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rdi
  _QWORD *v32; // r8
  __int64 v33; // rbx
  __int64 v34; // rcx
  __int64 v35; // r9
  int v36; // ebx
  void **v37; // r10
  int v38; // eax
  unsigned int v39; // ebx
  int v40; // eax
  unsigned int v41; // ebx
  __int64 v42; // rcx
  int v43; // ecx
  const struct std::nothrow_t *v44; // rdx
  void *v45; // rcx
  unsigned int v47; // ebx
  __int64 v48; // rax
  int v49; // ecx
  __int64 v50; // r9
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rax
  __int64 v54; // rax
  int v55; // ecx
  __int64 v56; // r9
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // rax
  int v60; // ecx
  __int64 v61; // r9
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rax
  int v65; // ecx
  __int64 v66; // r9
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // rax
  int v70; // [rsp+50h] [rbp-1C8h] BYREF
  char v71; // [rsp+58h] [rbp-1C0h] BYREF
  int v72; // [rsp+60h] [rbp-1B8h] BYREF
  int v73; // [rsp+64h] [rbp-1B4h] BYREF
  unsigned __int64 CurrentThreadId; // [rsp+68h] [rbp-1B0h] BYREF
  __int128 v75; // [rsp+70h] [rbp-1A8h] BYREF
  __int64 v76; // [rsp+80h] [rbp-198h] BYREF
  void *v77; // [rsp+88h] [rbp-190h] BYREF
  __int128 **v78; // [rsp+90h] [rbp-188h] BYREF
  __int64 v79; // [rsp+98h] [rbp-180h] BYREF
  char *v80; // [rsp+A0h] [rbp-178h]
  char v81; // [rsp+A8h] [rbp-170h]
  const char *v82; // [rsp+B0h] [rbp-168h] BYREF
  int v83; // [rsp+B8h] [rbp-160h] BYREF
  __int128 *v84; // [rsp+C0h] [rbp-158h] BYREF
  __int128 v85; // [rsp+C8h] [rbp-150h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+D8h] [rbp-140h] BYREF
  _BYTE v87[56]; // [rsp+110h] [rbp-108h] BYREF
  _BYTE v88[56]; // [rsp+148h] [rbp-D0h] BYREF
  _BYTE v89[56]; // [rsp+180h] [rbp-98h] BYREF
  void *v90[3]; // [rsp+1B8h] [rbp-60h] BYREF
  unsigned __int64 v91; // [rsp+1D0h] [rbp-48h]

  v7 = a4;
  CurrentThreadId = a4;
  v9 = a2;
  v70 = a2;
  cdp::TryCreateOrExtendCorrelationVector(v90, a7);
  if ( !v7 )
  {
    v72 = 864;
    goto LABEL_46;
  }
  if ( !a3 )
  {
    v72 = 865;
LABEL_46:
    v73 = -2147024809;
    Log<long &,char const (&)[36],int>(
      v11,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v73,
      (unsigned int)".\\activitystorelet.cpp",
      (__int64)&v72);
    v47 = v73;
LABEL_47:
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v90);
    return v47;
  }
  v72 = 0;
  cdp::ActivityStorelet::EnsureActivitiesByAppActivityIdRetrieverIsSetup((cdp::ActivityStorelet *)a1);
  v85 = 0;
  v12 = ComCrossPlatformAppIdFromCDPCrossPlatformAppId(a3, &v85);
  v13 = v12;
  if ( v12 < 0 )
  {
    v82 = ".\\activitystorelet.cpp";
    v83 = 873;
    v70 = v12;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v49,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v70,
      (unsigned int)&v82,
      (__int64)&v83,
      (__int64)&CurrentThreadId);
    v50 = cdp::ExceptionStackFromSourceLocationInfo(&v79, &v82);
    v53 = cdp::ErrorCodeToString(v13, v51, v52, v50);
    ConnectedDevices::Exception::Exception(pExceptionObject, v13, v53);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v84 = &v85;
  v78 = &v84;
  v14 = (std::_Mutex_base *)(*(_QWORD *)(a1 + 112) + 704LL);
  v82 = (const char *)v14;
  std::_Mutex_base::lock(v14);
  v15 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 304), 1u);
  v73 = v15;
  if ( a6 )
  {
    v16 = *(_QWORD *)(a1 + 112) + 448LL;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 8LL))(a6);
    v75 = 0;
    v79 = a6;
    v80 = &v71;
    v81 = 1;
    v17 = operator new(0x18u);
    v17[2] = 1;
    v17[3] = 1;
    *(_QWORD *)v17 = &std::_Ref_count_resource<ICDPActivitiesByAppActivityIdCallback *,cdp::detail::iunknown_deleter<ICDPActivitiesByAppActivityIdCallback>>::`vftable';
    *((_QWORD *)v17 + 2) = a6;
    *(_QWORD *)&v75 = a6;
    *((_QWORD *)&v75 + 1) = v17;
    v18 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 4; ++i )
      v18 = 0x100000001B3LL * (*((unsigned __int8 *)&v73 + i) ^ (unsigned __int64)v18);
    v20 = *(_QWORD *)(v16 + 48) & v18;
    v21 = *(_QWORD *)(v16 + 24);
    v22 = *(_QWORD *)(v21 + 16 * v20 + 8);
    v77 = *(void **)(v16 + 8);
    if ( (void *)v22 != v77 )
    {
      while ( v15 != *(_DWORD *)(v22 + 16) )
      {
        if ( v22 == *(_QWORD *)(v21 + 16 * v20) )
        {
          v77 = (void *)v22;
          goto LABEL_12;
        }
        v22 = *(_QWORD *)(v22 + 8);
      }
      goto LABEL_23;
    }
LABEL_12:
    if ( *(_QWORD *)(v16 + 16) == 0x666666666666666LL )
      std::_Xlength_error("unordered_map/set too long");
    v79 = v16 + 8;
    v80 = 0;
    v23 = std::_Allocate<16,std::_Default_allocate_traits>(40);
    v80 = (char *)v23;
    *(_DWORD *)(v23 + 16) = v73;
    *(_QWORD *)(v23 + 24) = a6;
    *(_QWORD *)(v23 + 32) = v17;
    v75 = 0;
    v24 = *(_QWORD *)(v16 + 16) + 1LL;
    if ( v24 < 0 )
      v25 = (float)(v24 & 1 | (unsigned int)((unsigned __int64)v24 >> 1))
          + (float)(v24 & 1 | (unsigned int)((unsigned __int64)v24 >> 1));
    else
      v25 = (float)(int)v24;
    v26 = *(_QWORD *)(v16 + 56);
    if ( v26 < 0 )
    {
      v48 = *(_QWORD *)(v16 + 56) & 1LL | ((unsigned __int64)v26 >> 1);
      v27 = (float)(int)v48 + (float)(int)v48;
    }
    else
    {
      v27 = (float)(int)v26;
    }
    if ( (float)(v25 / v27) > *(float *)v16 )
    {
      v54 = std::_Hash<std::_Umap_traits<unsigned int,cdp::AssetJobCallbackInfo,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,cdp::AssetJobCallbackInfo>>,0>>::_Desired_grow_bucket_count(v16);
      std::_Hash<std::_Umap_traits<unsigned int,std::pair<cdp::ActivityFilter,std::shared_ptr<ICDPActivityStoreCallback>>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::pair<cdp::ActivityFilter,std::shared_ptr<ICDPActivityStoreCallback>>>>,0>>::_Forced_rehash(
        v16,
        v54);
      v28 = *(_QWORD **)std::_Hash<std::_Umap_traits<unsigned int,cdp::AssetJobCallbackInfo,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,cdp::AssetJobCallbackInfo>>,0>>::_Find_last<unsigned int>(
                          v16,
                          &v79,
                          v23 + 16,
                          v18);
    }
    else
    {
      v28 = v77;
    }
    v29 = (__int64 *)v28[1];
    ++*(_QWORD *)(v16 + 16);
    *(_QWORD *)v23 = v28;
    *(_QWORD *)(v23 + 8) = v29;
    *v29 = v23;
    v28[1] = v23;
    v30 = *(_QWORD *)(v16 + 24);
    v31 = 2 * (*(_QWORD *)(v16 + 48) & v18);
    v32 = *(_QWORD **)(v30 + 8 * v31);
    if ( v32 == *(_QWORD **)(v16 + 8) )
    {
      *(_QWORD *)(v30 + 8 * v31) = v23;
    }
    else
    {
      if ( v32 == v28 )
      {
        *(_QWORD *)(v30 + 8 * v31) = v23;
        goto LABEL_22;
      }
      if ( *(__int64 **)(v30 + 8 * v31 + 8) != v29 )
        goto LABEL_22;
    }
    *(_QWORD *)(v30 + 8 * v31 + 8) = v23;
LABEL_22:
    v17 = (_DWORD *)*((_QWORD *)&v75 + 1);
    v15 = v73;
LABEL_23:
    if ( v17 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
    v9 = v70;
    v7 = CurrentThreadId;
  }
  _Mtx_unlock(v14);
  v76 = 0;
  v33 = *(_QWORD *)(a1 + 112);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v76);
  v34 = 0;
  v76 = 0;
  v35 = *(_QWORD *)(v33 + 784);
  if ( v35 )
  {
    v36 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(*(_QWORD *)v35 + 24LL))(
            *(_QWORD *)(v33 + 784),
            &GUID_ac566344_eadd_4f1a_a84a_7ed279176ba9,
            &v76);
    v34 = v76;
  }
  else
  {
    v36 = 0;
  }
  if ( v36 < 0 )
  {
    *(_QWORD *)&v75 = ".\\activitystorelet.cpp";
    DWORD2(v75) = 891;
    v70 = v36;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v55,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v70,
      (unsigned int)&v75,
      (__int64)&v75 + 8,
      (__int64)&CurrentThreadId);
    v56 = cdp::ExceptionStackFromSourceLocationInfo(&v79, &v75);
    v59 = cdp::ErrorCodeToString((unsigned int)v36, v57, v58, v56);
    ConnectedDevices::Exception::Exception(v87, (unsigned int)v36, v59);
    throw (ConnectedDevices::Exception *)v87;
  }
  v37 = v90;
  if ( v91 > 0xF )
    v37 = (void **)v90[0];
  v38 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, unsigned __int64, _DWORD, __int64, signed __int32, void **))(*(_QWORD *)v34 + 288LL))(
          v34,
          v9,
          &v85,
          v7,
          a5,
          *(_QWORD *)(a1 + 240) + 40LL,
          v15,
          v37);
  v39 = v38;
  if ( v38 < 0 )
  {
    *(_QWORD *)&v75 = ".\\activitystorelet.cpp";
    DWORD2(v75) = 894;
    v70 = v38;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v60,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v70,
      (unsigned int)&v75,
      (__int64)&v75 + 8,
      (__int64)&CurrentThreadId);
    v61 = cdp::ExceptionStackFromSourceLocationInfo(&v79, &v75);
    v64 = cdp::ErrorCodeToString(v39, v62, v63, v61);
    ConnectedDevices::Exception::Exception(v88, v39, v64);
    throw (ConnectedDevices::Exception *)v88;
  }
  v40 = shared::CallbackNotificationRetriever::EnsureListening(*(shared::CallbackNotificationRetriever **)(a1 + 240));
  v41 = v40;
  if ( v40 < 0 )
  {
    *(_QWORD *)&v75 = ".\\activitystorelet.cpp";
    DWORD2(v75) = 895;
    v70 = v40;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v65,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v70,
      (unsigned int)&v75,
      (__int64)&v75 + 8,
      (__int64)&CurrentThreadId);
    v66 = cdp::ExceptionStackFromSourceLocationInfo(&v79, &v75);
    v69 = cdp::ErrorCodeToString(v41, v67, v68, v66);
    ConnectedDevices::Exception::Exception(v89, v41, v69);
    throw (ConnectedDevices::Exception *)v89;
  }
  v42 = v76;
  if ( v76 )
  {
    v76 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  ScopeWarden__lambda_f4400cf655c87da3399b0b180c1dba21___::_ScopeWarden__lambda_f4400cf655c87da3399b0b180c1dba21___(&v78);
  if ( v72 < 0 )
  {
    v70 = 898;
    Log<long &,char const (&)[36],int>(
      v43,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v72,
      (unsigned int)".\\activitystorelet.cpp",
      (__int64)&v70);
    v47 = v72;
    goto LABEL_47;
  }
  if ( v91 > 0xF )
  {
    v44 = (const struct std::nothrow_t *)(v91 + 1);
    CurrentThreadId = v91 + 1;
    v45 = v90[0];
    v77 = v90[0];
    if ( v91 + 1 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v77, &CurrentThreadId);
      v44 = (const struct std::nothrow_t *)CurrentThreadId;
      v45 = v77;
    }
    operator delete(v45, v44);
  }
  return 0;
}

```

## disassembly

```asm
0x180055bf0  mov     r11, rsp
0x180055bf3  push    rbx
0x180055bf4  push    rsi
0x180055bf5  push    rdi
0x180055bf6  push    r12
0x180055bf8  push    r13
0x180055bfa  push    r14
0x180055bfc  push    r15
0x180055bfe  sub     rsp, 1E0h
0x180055c05  mov     rax, cs:__security_cookie
0x180055c0c  xor     rax, rsp
0x180055c0f  mov     [rsp+218h+var_40], rax
0x180055c17  mov     rdi, r9
0x180055c1a  mov     [rsp+218h+var_1B0], r9
0x180055c1f  mov     rbx, r8
0x180055c22  mov     esi, edx
0x180055c24  mov     [rsp+218h+var_1C8], edx
0x180055c28  mov     r13, rcx
0x180055c2b  mov     r12, [rsp+218h+arg_28]
0x180055c33  mov     rdx, [rsp+218h+arg_30]
0x180055c3b  lea     rcx, [r11-60h]
0x180055c3f  call    ?TryCreateOrExtendCorrelationVector@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; cdp::TryCreateOrExtendCorrelationVector(char const *)
0x180055c44  nop
0x180055c45  test    rdi, rdi
0x180055c48  jz      loc_1800560F4
0x180055c4e  test    rbx, rbx
0x180055c51  jz      loc_180056073
0x180055c57  mov     [rsp+218h+var_1B8], 0
0x180055c5f  mov     rcx, r13; this
0x180055c62  call    ?EnsureActivitiesByAppActivityIdRetrieverIsSetup@ActivityStorelet@cdp@@AEAAXXZ; cdp::ActivityStorelet::EnsureActivitiesByAppActivityIdRetrieverIsSetup(void)
0x180055c67  xorps   xmm0, xmm0
0x180055c6a  movups  [rsp+218h+var_150], xmm0
0x180055c72  lea     rdx, [rsp+218h+var_150]
0x180055c7a  mov     rcx, rbx
0x180055c7d  call    ComCrossPlatformAppIdFromCDPCrossPlatformAppId
0x180055c82  mov     ebx, eax
0x180055c84  test    eax, eax
0x180055c86  js      loc_180056101
0x180055c8c  lea     rax, [rsp+218h+var_150]
0x180055c94  mov     [rsp+218h+var_158], rax
0x180055c9c  lea     rax, [rsp+218h+var_158]
0x180055ca4  mov     [rsp+218h+var_188], rax
0x180055cac  mov     rbx, [r13+70h]
0x180055cb0  add     rbx, 2C0h
0x180055cb7  mov     [rsp+218h+var_168], rbx
0x180055cbf  mov     rcx, rbx; this
0x180055cc2  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180055cc7  nop
0x180055cc8  mov     r15d, 1
0x180055cce  lock xadd [r13+130h], r15d
0x180055cd7  mov     [rsp+218h+var_1B4], r15d
0x180055cdc  test    r12, r12
0x180055cdf  jz      loc_180055EC8
0x180055ce5  mov     r14, [r13+70h]
0x180055ce9  add     r14, 1C0h
0x180055cf0  mov     rax, [r12]
0x180055cf4  mov     rcx, r12
0x180055cf7  mov     rax, [rax+8]
0x180055cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d00  xorps   xmm0, xmm0
0x180055d03  movdqu  [rsp+218h+var_1A8], xmm0
0x180055d09  mov     al, [rsp+218h+var_1C0]
0x180055d0d  mov     [rsp+218h+var_1C0], al
0x180055d11  mov     [rsp+218h+var_180], r12
0x180055d19  lea     rax, [rsp+218h+var_1C0]
0x180055d1e  mov     [rsp+218h+var_178], rax
0x180055d26  mov     [rsp+218h+var_170], 1
0x180055d2e  mov     ecx, 18h; Size
0x180055d33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180055d38  mov     rsi, rax
0x180055d3b  mov     dword ptr [rax+8], 1
0x180055d42  mov     dword ptr [rax+0Ch], 1
0x180055d49  lea     rax, ??_7?$_Ref_count_resource@PEAVICDPActivitiesByAppActivityIdCallback@@U?$iunknown_deleter@VICDPActivitiesByAppActivityIdCallback@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPActivitiesByAppActivityIdCallback *,cdp::detail::iunknown_deleter<ICDPActivitiesByAppActivityIdCallback>>::`vftable'
0x180055d50  mov     [rsi], rax
0x180055d53  mov     [rsi+10h], r12
0x180055d57  mov     qword ptr [rsp+218h+var_1A8], r12
0x180055d5c  mov     qword ptr [rsp+218h+var_1A8+8], rsi
0x180055d61  mov     rdi, 0CBF29CE484222325h
0x180055d6b  xor     ecx, ecx
0x180055d6d  movzx   eax, byte ptr [rsp+rcx+218h+var_1B4]
0x180055d72  xor     rdi, rax
0x180055d75  mov     rdx, 100000001B3h
0x180055d7f  imul    rdi, rdx
0x180055d83  inc     rcx
0x180055d86  cmp     rcx, 4
0x180055d8a  jb      short loc_180055D6D
0x180055d8c  mov     rdx, rdi
0x180055d8f  and     rdx, [r14+30h]
0x180055d93  mov     r8, [r14+18h]
0x180055d97  mov     rax, rdx
0x180055d9a  add     rax, rax
0x180055d9d  mov     rcx, [r8+rax*8+8]
0x180055da2  lea     r9, [r14+8]
0x180055da6  mov     rax, [r9]
0x180055da9  mov     [rsp+218h+var_190], rax
0x180055db1  cmp     rcx, rax
0x180055db4  jz      short loc_180055DDA
0x180055db6  add     rdx, rdx
0x180055db9  mov     rax, [r8+rdx*8]
0x180055dbd  cmp     r15d, [rcx+10h]
0x180055dc1  jz      loc_180055EB2
0x180055dc7  cmp     rcx, rax
0x180055dca  jz      short loc_180055DD2
0x180055dcc  mov     rcx, [rcx+8]
0x180055dd0  jmp     short loc_180055DBD
0x180055dd2  mov     [rsp+218h+var_190], rcx
0x180055dda  mov     rax, 666666666666666h
0x180055de4  cmp     [r14+10h], rax
0x180055de8  jz      loc_1800561A2
0x180055dee  mov     [rsp+218h+var_180], r9
0x180055df6  mov     [rsp+218h+var_178], 0
0x180055e02  mov     ecx, 28h ; '('
0x180055e07  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180055e0c  mov     r15, rax
0x180055e0f  mov     [rsp+218h+var_178], rax
0x180055e17  mov     ecx, [rsp+218h+var_1B4]
0x180055e1b  mov     [rax+10h], ecx
0x180055e1e  mov     [rax+18h], r12
0x180055e22  mov     [rax+20h], rsi
0x180055e26  xorps   xmm0, xmm0
0x180055e29  movdqu  [rsp+218h+var_1A8], xmm0
0x180055e2f  mov     rdx, [r14+10h]
0x180055e33  add     rdx, 1
0x180055e37  xorps   xmm0, xmm0
0x180055e3a  js      loc_1800560BD
0x180055e40  cvtsi2ss xmm0, rdx
0x180055e45  mov     rcx, [r14+38h]
0x180055e49  xorps   xmm1, xmm1
0x180055e4c  test    rcx, rcx
0x180055e4f  js      loc_1800560DA
0x180055e55  cvtsi2ss xmm1, rcx
0x180055e5a  divss   xmm0, xmm1
0x180055e5e  comiss  xmm0, dword ptr [r14]
0x180055e62  ja      loc_1800561B0
0x180055e68  mov     rcx, [rsp+218h+var_190]
0x180055e70  mov     rdx, [rcx+8]
0x180055e74  inc     qword ptr [r14+10h]
0x180055e78  mov     [r15], rcx
0x180055e7b  mov     [r15+8], rdx
0x180055e7f  mov     [rdx], r15
0x180055e82  mov     [rcx+8], r15
0x180055e86  mov     rax, [r14+18h]
0x180055e8a  and     rdi, [r14+30h]
0x180055e8e  add     rdi, rdi
0x180055e91  mov     r8, [rax+rdi*8]
0x180055e95  cmp     r8, [r14+8]
0x180055e99  jnz     loc_180056055
0x180055e9f  mov     [rax+rdi*8], r15
0x180055ea3  mov     [rax+rdi*8+8], r15
0x180055ea8  mov     rsi, qword ptr [rsp+218h+var_1A8+8]
0x180055ead  mov     r15d, [rsp+218h+var_1B4]
0x180055eb2  test    rsi, rsi
0x180055eb5  jz      short loc_180055EBF
0x180055eb7  mov     rcx, rsi; this
0x180055eba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180055ebf  mov     esi, [rsp+218h+var_1C8]
0x180055ec3  mov     rdi, [rsp+218h+var_1B0]
0x180055ec8  mov     rcx, rbx; _Mtx_t
0x180055ecb  call    cs:__imp__Mtx_unlock
0x180055ed1  mov     [rsp+218h+var_198], 0
0x180055edd  mov     rbx, [r13+70h]
0x180055ee1  lea     rcx, [rsp+218h+var_198]
0x180055ee9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180055eee  nop
0x180055eef  xor     ecx, ecx
0x180055ef1  mov     [rsp+218h+var_198], rcx
0x180055ef9  mov     r9, [rbx+310h]
0x180055f00  test    r9, r9
0x180055f03  jz      loc_1800561E2
0x180055f09  mov     rax, [r9]
0x180055f0c  lea     r8, [rsp+218h+var_198]
0x180055f14  lea     rdx, _GUID_ac566344_eadd_4f1a_a84a_7ed279176ba9
0x180055f1b  mov     rcx, r9
0x180055f1e  mov     rax, [rax+18h]
0x180055f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f27  mov     ebx, eax
0x180055f29  mov     rcx, [rsp+218h+var_198]
0x180055f31  test    ebx, ebx
0x180055f33  js      loc_1800561E9
0x180055f39  mov     rax, [rcx]
0x180055f3c  mov     r11, [rax+120h]
0x180055f43  lea     r10, [rsp+218h+var_60]
0x180055f4b  cmp     [rsp+218h+var_48], 0Fh
0x180055f54  cmova   r10, [rsp+218h+var_60]
0x180055f5d  mov     r8, [r13+0F0h]
0x180055f64  add     r8, 28h ; '('
0x180055f68  movzx   eax, [rsp+218h+arg_20]
0x180055f70  mov     [rsp+218h+var_1E0], r10
0x180055f75  mov     [rsp+218h+var_1E8], r15d
0x180055f7a  mov     [rsp+218h+var_1F0], r8
0x180055f7f  mov     dword ptr [rsp+218h+var_1F8], eax
0x180055f83  mov     r9, rdi
0x180055f86  lea     r8, [rsp+218h+var_150]
0x180055f8e  mov     edx, esi
0x180055f90  mov     rax, r11
0x180055f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f98  mov     ebx, eax
0x180055f9a  test    eax, eax
0x180055f9c  js      loc_18005627B
0x180055fa2  mov     rcx, [r13+0F0h]; this
0x180055fa9  call    ?EnsureListening@CallbackNotificationRetriever@shared@@QEAAJXZ; shared::CallbackNotificationRetriever::EnsureListening(void)
0x180055fae  mov     ebx, eax
0x180055fb0  test    eax, eax
0x180055fb2  js      loc_18005630D
0x180055fb8  mov     rcx, [rsp+218h+var_198]
0x180055fc0  test    rcx, rcx
0x180055fc3  jz      short loc_180055FDE
0x180055fc5  mov     [rsp+218h+var_198], 0
0x180055fd1  mov     rax, [rcx]
0x180055fd4  mov     rax, [rax+10h]
0x180055fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fdd  nop
0x180055fde  lea     rcx, [rsp+218h+var_188]
0x180055fe6  call    ScopeWarden__lambda_f4400cf655c87da3399b0b180c1dba21______ScopeWarden__lambda_f4400cf655c87da3399b0b180c1dba21___
0x180055feb  nop
0x180055fec  mov     eax, [rsp+218h+var_1B8]
0x180055ff0  test    eax, eax
0x180055ff2  js      loc_1800563A4
0x180055ff8  mov     rdx, [rsp+218h+var_48]
0x180056000  cmp     rdx, 0Fh
0x180056004  jbe     short loc_180056030
0x180056006  inc     rdx; struct std::nothrow_t *
0x180056009  mov     [rsp+218h+var_1B0], rdx
0x18005600e  mov     rcx, [rsp+218h+var_60]; void *
0x180056016  mov     [rsp+218h+var_190], rcx
0x18005601e  cmp     rdx, 1000h
0x180056025  jnb     loc_1800563DB
0x18005602b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180056030  xor     eax, eax
0x180056032  mov     rcx, [rsp+218h+var_40]
0x18005603a  xor     rcx, rsp; StackCookie
0x18005603d  call    __security_check_cookie
0x180056042  add     rsp, 1E0h
0x180056049  pop     r15
0x18005604b  pop     r14
0x18005604d  pop     r13
0x18005604f  pop     r12
0x180056051  pop     rdi
0x180056052  pop     rsi
0x180056053  pop     rbx
0x180056054  retn
0x180056055  cmp     r8, rcx
0x180056058  jnz     short loc_180056063
0x18005605a  mov     [rax+rdi*8], r15
0x18005605e  jmp     loc_180055EA8
0x180056063  cmp     [rax+rdi*8+8], rdx
0x180056068  jnz     loc_180055EA8
0x18005606e  jmp     loc_180055EA3
0x180056073  mov     [rsp+218h+var_1B8], 361h
0x18005607b  mov     [rsp+218h+var_1B4], 80070057h
0x180056083  lea     rax, [rsp+218h+var_1B8]
0x180056088  mov     [rsp+218h+var_1F8], rax
0x18005608d  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180056094  lea     r8, [rsp+218h+var_1B4]
0x180056099  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800560a0  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800560a5  mov     ebx, [rsp+218h+var_1B4]
0x1800560a9  lea     rcx, [rsp+218h+var_60]; void *
0x1800560b1  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800560b6  mov     eax, ebx
0x1800560b8  jmp     loc_180056032
0x1800560bd  mov     rcx, rdx
0x1800560c0  shr     rcx, 1
0x1800560c3  mov     rax, rdx
0x1800560c6  and     eax, 1
0x1800560c9  or      rcx, rax
0x1800560cc  cvtsi2ss xmm0, rcx
0x1800560d1  addss   xmm0, xmm0
0x1800560d5  jmp     loc_180055E45
0x1800560da  mov     rax, rcx
0x1800560dd  shr     rax, 1
0x1800560e0  and     ecx, 1
0x1800560e3  or      rax, rcx
0x1800560e6  cvtsi2ss xmm1, rax
0x1800560eb  addss   xmm1, xmm1
0x1800560ef  jmp     loc_180055E5A
0x1800560f4  mov     [rsp+218h+var_1B8], 360h
0x1800560fc  jmp     loc_18005607B
0x180056101  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180056108  mov     [rsp+218h+var_168], r9
0x180056110  mov     [rsp+218h+var_160], 369h
0x18005611b  mov     [rsp+218h+var_1C8], ebx
0x18005611f  call    cs:__imp_GetCurrentThreadId
0x180056125  mov     eax, eax
0x180056127  mov     [rsp+218h+var_1B0], rax
0x18005612c  lea     rax, [rsp+218h+var_1B0]
0x180056131  mov     [rsp+218h+var_1F0], rax
0x180056136  lea     rax, [rsp+218h+var_160]
0x18005613e  mov     [rsp+218h+var_1F8], rax
0x180056143  lea     r9, [rsp+218h+var_168]
0x18005614b  lea     r8, [rsp+218h+var_1C8]
0x180056150  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180056157  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18005615c  lea     rdx, [rsp+218h+var_168]
0x180056164  lea     rcx, [rsp+218h+var_180]
0x18005616c  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180056171  mov     r9, rax
0x180056174  mov     ecx, ebx
0x180056176  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18005617b  mov     r8, rax
  ... truncated ...
```
