# wil::ProfileDataStore::Unmarshal<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(winrt::Windows::Internal::Storage::Cloud::CloudStoreData const &,wil::ProfileDataStoreLoadOptions)

- ea: `0x1800402c8`
- end: `0x1800408dd`
- name: `??$Unmarshal@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$shared_ptr@V?$ProfileDataItem@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@AEBUCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@W4ProfileDataStoreLoadOptions@1@@Z`
- size: `1557`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `broker_com_uri`

## callers

- `0x180028e00`
- `0x18002b230`

## callees

- `0x180003080`
- `0x180003568`
- `0x180003c97`
- `0x180003cdf`
- `0x1800060a4`
- `0x18000c95c`
- `0x18000ce74`
- `0x18000cfcc`
- `0x18000f7d0`
- `0x18000f7fc`
- `0x18001361c`
- `0x18001ae30`
- `0x18001cbd0`
- `0x1800402c8`
- `0x180040bac`
- `0x180043f84`
- `0x180048150`
- `0x180048220`
- `0x1800484c0`
- `0x180048598`
- `0x18004a6e8`
- `0x18004a788`
- `0x18004b060`
- `0x18004be50`
- `0x18004bf74`
- `0x18004ce0c`
- `0x18004d81c`
- `0x1800504c8`
- `0x180061010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004052e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180040607`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180040895`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800408a4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004052e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180040607`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180040895`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800408a4`

## pseudocode

```c
_QWORD *__fastcall wil::ProfileDataStore::Unmarshal<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(
        _QWORD *a1,
        __int64 (__fastcall ****a2)(_QWORD, __int64 *, _QWORD **),
        char a3)
{
  int v5; // esi
  int v6; // eax
  int v7; // eax
  int v8; // ebx
  __int64 (__fastcall ***v9)(_QWORD, __int64 *, _QWORD **); // rcx
  _QWORD *v10; // rbx
  int v11; // eax
  int v12; // ebx
  _QWORD *v13; // rax
  _QWORD *v14; // rcx
  LPVOID *v15; // rax
  LPVOID v16; // r15
  __int64 v17; // rax
  const WCHAR *v18; // rsi
  const WCHAR *v19; // r13
  void *v20; // r15
  int v21; // eax
  HANDLE ProcessHeap; // rax
  __int64 v23; // rax
  const WCHAR *v24; // r12
  void *v25; // r15
  int v26; // eax
  HANDLE v27; // rax
  __int64 v28; // rax
  const WCHAR *v29; // rax
  __int64 v30; // r8
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // r8
  int v34; // ebx
  __int64 v35; // rax
  _QWORD *v36; // rsi
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v42; // r8
  void *v43; // rbx
  int v44; // eax
  HANDLE v45; // rax
  void *v46; // rbx
  int v47; // edi
  HANDLE v48; // rax
  unsigned int v50; // eax
  int v51; // [rsp+20h] [rbp-E0h]
  char v52; // [rsp+80h] [rbp-80h] BYREF
  char v53; // [rsp+81h] [rbp-7Fh]
  char v54; // [rsp+82h] [rbp-7Eh] BYREF
  bool v55; // [rsp+83h] [rbp-7Dh] BYREF
  int v56; // [rsp+84h] [rbp-7Ch] BYREF
  _QWORD *v57; // [rsp+88h] [rbp-78h] BYREF
  __int64 v58; // [rsp+90h] [rbp-70h] BYREF
  int v59; // [rsp+98h] [rbp-68h] BYREF
  int v60; // [rsp+9Ch] [rbp-64h] BYREF
  LPVOID v61; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v62; // [rsp+A8h] [rbp-58h] BYREF
  int v63; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v64; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD *v65; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID v67; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v68; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD *v69; // [rsp+E0h] [rbp-20h]
  __int128 v70; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v71; // [rsp+F8h] [rbp-8h]
  __int64 v72; // [rsp+100h] [rbp+0h]
  __int64 v73; // [rsp+110h] [rbp+10h] BYREF
  const WCHAR *v74; // [rsp+118h] [rbp+18h] BYREF
  __int64 v75; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v76; // [rsp+128h] [rbp+28h]
  __int128 *v77; // [rsp+130h] [rbp+30h]
  __int128 v78; // [rsp+138h] [rbp+38h] BYREF
  __int64 v79; // [rsp+148h] [rbp+48h]
  __int64 v80; // [rsp+150h] [rbp+50h]
  __int128 v81; // [rsp+158h] [rbp+58h] BYREF
  __int64 v82; // [rsp+168h] [rbp+68h]
  __int64 v83; // [rsp+170h] [rbp+70h]
  __int128 v84; // [rsp+178h] [rbp+78h] BYREF
  __int64 v85; // [rsp+188h] [rbp+88h]
  __int64 v86; // [rsp+190h] [rbp+90h]
  __int128 v87; // [rsp+198h] [rbp+98h] BYREF
  __int64 v88; // [rsp+1A8h] [rbp+A8h]
  _BYTE v89[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v90[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v91[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v76 = a1;
  v69 = a1;
  v5 = 0;
  v65 = 0;
  v52 = 1;
  v54 = 0;
  v59 = *(_DWORD *)winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::ResultCode(
                     a2,
                     &v60);
  v73 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::RetryAfter(a2);
  v6 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::DataDescriptionLanguage(a2);
  if ( v6 )
  {
    if ( v6 != 1 )
    {
      v50 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x286,
        (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
        (const char *)v50,
        v51);
    }
    v7 = 1;
  }
  else
  {
    v7 = 0;
  }
  v56 = v7;
  v63 = v7;
  v8 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::Status(a2);
  v75 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::Version(a2);
  if ( v8 == 1 )
    v5 = 1;
  v60 = v5;
  v9 = *a2;
  v57 = 0;
  if ( v9 )
  {
    LODWORD(v70) = 2123;
    *((_QWORD *)&v70 + 1) = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\base.h";
    v71 = 0;
    v11 = (**v9)(v9, winrt::impl::guid_v<Windows::Internal::Storage::Cloud::ICloudStoreData>, &v57);
    if ( v11 < 0 )
      winrt::throw_hresult((unsigned int)v11, &v70);
    v10 = v57;
  }
  else
  {
    v10 = 0;
  }
  v53 = 0;
  if ( v10 )
    (*(void (__fastcall **)(_QWORD *))(*v10 + 8LL))(v10);
  v65 = v10;
  if ( v10 )
    winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(&v57);
  v64 = 0;
  (*(void (__fastcall **)(_QWORD *, GUID *, __int64 *))*v10)(v10, &GUID_910745a7_98d9_4169_aa1d_9a7896a26170, &v64);
  if ( v64 && (LODWORD(v58) = 0, (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v64 + 48LL))(v64, &v58) >= 0) )
  {
    v12 = v58 & 1;
    if ( (v58 & 2) != 0 )
      v12 |= 2u;
    v53 = 1;
  }
  else
  {
    v12 = v60;
  }
  v55 = (a3 & 3) != 0;
  v13 = (_QWORD *)winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::ItemName(
                    a2,
                    &v61);
  v69 = (_QWORD *)*v13;
  v14 = v69;
  *v13 = 0;
  v57 = v14;
  if ( v61 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v61);
  v15 = (LPVOID *)winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::CollectionName(
                    &v57,
                    &v58);
  v62 = *v15;
  v16 = v62;
  *v15 = 0;
  v61 = v16;
  if ( v58 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v58);
  if ( v16 )
  {
    v17 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreCollectionName>::CustomName(
            &v61,
            &lpMem);
    v18 = &String1;
    if ( *(_QWORD *)v17 )
      v19 = *(const WCHAR **)(*(_QWORD *)v17 + 16LL);
    else
      v19 = &String1;
    v20 = lpMem;
    if ( lpMem )
    {
      v21 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v21 )
      {
        if ( v21 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v20);
      }
      lpMem = 0;
    }
    v23 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreCollectionName>::PartitionName(
            &v61,
            &v67);
    if ( *(_QWORD *)v23 )
      v24 = *(const WCHAR **)(*(_QWORD *)v23 + 16LL);
    else
      v24 = &String1;
    v25 = v67;
    if ( v67 )
    {
      v26 = _InterlockedDecrement((volatile signed __int32 *)v67 + 6);
      if ( v26 )
      {
        if ( v26 < 0 )
          abort();
      }
      else
      {
        v27 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v27, 0, v25);
      }
      v67 = 0;
    }
    v16 = v62;
  }
  else
  {
    v18 = &String1;
    v24 = &String1;
    v19 = &String1;
  }
  v84 = 0;
  v85 = 0;
  v86 = 15;
  LOBYTE(v84) = 0;
  v87 = 0;
  v88 = 0;
  LODWORD(v58) = wil::ProfileDataStore::UnmarshalAllTypes<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(
                   (_DWORD)a2,
                   (unsigned int)&v54,
                   (unsigned int)&v52,
                   v56,
                   (__int64)&v84,
                   v59);
  if ( !v53 )
    v12 = v52 != 0;
  v59 = v12;
  v56 = 0;
  v28 = *(_QWORD *)winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::CloudEtag(
                     a2,
                     &v68);
  if ( v28 )
    v29 = *(const WCHAR **)(v28 + 16);
  else
    v29 = &String1;
  v74 = v29;
  v77 = &v70;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v30 = -1;
  do
    ++v30;
  while ( v24[v30] );
  std::wstring::_Construct<1,unsigned short const *>(&v70, v24, v30);
  v67 = &v78;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v31 = -1;
  do
    ++v31;
  while ( v19[v31] );
  std::wstring::_Construct<1,unsigned short const *>(&v78, v19, v31);
  v32 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::InstanceName(
          &v57,
          &v62);
  if ( *(_QWORD *)v32 )
    v18 = *(const WCHAR **)(*(_QWORD *)v32 + 16LL);
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v33 = -1;
  do
    ++v33;
  while ( v18[v33] );
  std::wstring::_Construct<1,unsigned short const *>(&v81, v18, v33);
  v34 = wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>(
          v89,
          &v81,
          &v78,
          &v70);
  v77 = (__int128 *)operator new(0x108u);
  v35 = std::_Ref_count_obj2<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>::_Ref_count_obj2<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>(
          (_DWORD)v77,
          (unsigned int)&v84,
          v34,
          (unsigned int)&v75,
          (__int64)&v60,
          (__int64)&v63,
          (__int64)&v65,
          (__int64)&v52,
          (__int64)&v54,
          (__int64)&v55,
          (__int64)&v74,
          (__int64)&v58,
          (__int64)&v73,
          (__int64)&v56,
          (__int64)&v59);
  v36 = v76;
  *v76 = v35 + 16;
  v36[1] = v35;
  std::wstring::~wstring(v91, v37, v38);
  std::wstring::~wstring(v90, v39, v40);
  std::wstring::~wstring(v89, v41, v42);
  v43 = v62;
  if ( v62 )
  {
    v44 = _InterlockedDecrement((volatile signed __int32 *)v62 + 6);
    if ( v44 )
    {
      if ( v44 < 0 )
        abort();
    }
    else
    {
      v45 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v45, 0, v43);
    }
    v62 = 0;
  }
  v46 = v68;
  if ( v68 )
  {
    v47 = _InterlockedDecrement((volatile signed __int32 *)v68 + 6);
    if ( v47 )
    {
      if ( v47 < 0 )
        abort();
    }
    else
    {
      v48 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v48, 0, v46);
    }
    v68 = 0;
  }
  std::vector<unsigned char>::~vector<unsigned char>(&v87);
  std::string::~string(&v84);
  if ( v16 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v61);
  if ( v69 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v57);
  if ( v64 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  if ( v65 )
    (*(void (__fastcall **)(_QWORD *))(*v65 + 16LL))(v65);
  return v36;
}

```

## disassembly

```asm
0x1800402c8  mov     [rsp-8+arg_10], rbx
0x1800402cd  push    rbp
0x1800402ce  push    rsi
0x1800402cf  push    rdi
0x1800402d0  push    r12
0x1800402d2  push    r13
0x1800402d4  push    r14
0x1800402d6  push    r15
0x1800402d8  lea     rbp, [rsp-120h]
0x1800402e0  sub     rsp, 220h
0x1800402e7  mov     rax, cs:__security_cookie
0x1800402ee  xor     rax, rsp
0x1800402f1  mov     [rbp+150h+var_40], rax
0x1800402f8  mov     edi, r8d
0x1800402fb  mov     r14, rdx
0x1800402fe  mov     [rbp+150h+var_128], rcx
0x180040302  mov     [rbp+150h+var_170], rcx
0x180040306  xor     r12d, r12d
0x180040309  mov     esi, r12d
0x18004030c  mov     [rbp+150h+var_190], r12
0x180040310  lea     r15d, [r12+1]
0x180040315  mov     [rbp+150h+var_1D0], r15b
0x180040319  mov     [rbp+150h+var_1CE], r12b
0x18004031d  lea     rdx, [rbp+150h+var_1B4]
0x180040321  mov     rcx, r14
0x180040324  call    ?ResultCode@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData2@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::ResultCode(void)
0x180040329  mov     eax, [rax]
0x18004032b  mov     [rbp+150h+var_1B8], eax
0x18004032e  mov     rcx, r14
0x180040331  call    ?RetryAfter@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData2@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::RetryAfter(void)
0x180040336  mov     [rbp+150h+var_140], rax
0x18004033a  mov     rcx, r14
0x18004033d  call    ?DataDescriptionLanguage@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData2@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::DataDescriptionLanguage(void)
0x180040342  test    eax, eax
0x180040344  jz      short loc_180040354
0x180040346  cmp     eax, r15d
0x180040349  jnz     loc_1800408B7
0x18004034f  mov     eax, r15d
0x180040352  jmp     short loc_180040357
0x180040354  mov     eax, r12d
0x180040357  mov     [rbp+150h+var_1CC], eax
0x18004035a  mov     [rbp+150h+var_1A0], eax
0x18004035d  mov     rcx, r14
0x180040360  call    ?Status@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData@UICloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::Status(void)
0x180040365  mov     ebx, eax
0x180040367  mov     rcx, r14
0x18004036a  call    ?Version@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData@UICloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::Version(void)
0x18004036f  mov     [rbp+150h+var_130], rax
0x180040373  cmp     ebx, r15d
0x180040376  cmovz   esi, r15d
0x18004037a  mov     [rbp+150h+var_1B4], esi
0x18004037d  mov     rcx, [r14]
0x180040380  mov     [rbp+150h+var_1C8], r12
0x180040384  test    rcx, rcx
0x180040387  jnz     short loc_18004038E
0x180040389  mov     rbx, r12
0x18004038c  jmp     short loc_1800403CA
0x18004038e  mov     dword ptr [rbp+150h+var_168], 84Bh
0x180040395  lea     rax, aOnecoreuapInte_5; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x18004039c  mov     qword ptr [rbp+150h+var_168+8], rax
0x1800403a0  mov     [rbp+150h+var_158], r12
0x1800403a4  mov     rax, [rcx]
0x1800403a7  lea     r8, [rbp+150h+var_1C8]
0x1800403ab  lea     rdx, ??$guid_v@UICloudStoreData@Cloud@Storage@Internal@Windows@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<Windows::Internal::Storage::Cloud::ICloudStoreData>
0x1800403b2  mov     rax, [rax]
0x1800403b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403ba  test    eax, eax
0x1800403bc  js      loc_1800408AB
0x1800403c2  mov     rbx, [rbp+150h+var_1C8]
0x1800403c6  mov     [rbp+150h+var_1C8], rbx
0x1800403ca  mov     [rbp+150h+var_1CF], r12b
0x1800403ce  test    rbx, rbx
0x1800403d1  jz      short loc_1800403E3
0x1800403d3  mov     rax, [rbx]
0x1800403d6  mov     rcx, rbx
0x1800403d9  mov     rax, [rax+8]
0x1800403dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403e2  nop
0x1800403e3  mov     [rbp+150h+var_190], rbx
0x1800403e7  test    rbx, rbx
0x1800403ea  jz      short loc_1800403F6
0x1800403ec  lea     rcx, [rbp+150h+var_1C8]
0x1800403f0  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x1800403f5  nop
0x1800403f6  mov     [rbp+150h+var_198], r12
0x1800403fa  mov     rax, [rbx]
0x1800403fd  lea     r8, [rbp+150h+var_198]
0x180040401  lea     rdx, _GUID_910745a7_98d9_4169_aa1d_9a7896a26170
0x180040408  mov     rcx, rbx
0x18004040b  mov     rax, [rax]
0x18004040e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040413  nop
0x180040414  mov     rcx, [rbp+150h+var_198]
0x180040418  test    rcx, rcx
0x18004041b  jz      short loc_18004044A
0x18004041d  mov     dword ptr [rbp+150h+var_1C0], r12d
0x180040421  mov     rax, [rcx]
0x180040424  lea     rdx, [rbp+150h+var_1C0]
0x180040428  mov     rax, [rax+30h]
0x18004042c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040431  test    eax, eax
0x180040433  js      short loc_18004044A
0x180040435  mov     ebx, dword ptr [rbp+150h+var_1C0]
0x180040438  and     ebx, r15d
0x18004043b  test    byte ptr [rbp+150h+var_1C0], 2
0x18004043f  jz      short loc_180040444
0x180040441  or      ebx, 2
0x180040444  mov     [rbp+150h+var_1CF], r15b
0x180040448  jmp     short loc_18004044D
0x18004044a  mov     ebx, [rbp+150h+var_1B4]
0x18004044d  and     dil, 3
0x180040451  neg     dil
0x180040454  sbb     al, al
0x180040456  and     al, r15b
0x180040459  mov     [rbp+150h+var_1CD], al
0x18004045c  lea     rdx, [rbp+150h+var_1B0]
0x180040460  mov     rcx, r14
0x180040463  call    ?ItemName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData@UICloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::ItemName(void)
0x180040468  mov     rcx, [rax]
0x18004046b  mov     [rbp+150h+var_170], rcx
0x18004046f  mov     [rax], r12
0x180040472  mov     [rbp+150h+var_1C8], rcx
0x180040476  cmp     [rbp+150h+var_1B0], r12
0x18004047a  jz      short loc_180040485
0x18004047c  lea     rcx, [rbp+150h+var_1B0]
0x180040480  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180040485  lea     rdx, [rbp+150h+var_1C0]
0x180040489  lea     rcx, [rbp+150h+var_1C8]
0x18004048d  call    ?CollectionName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName@UICloudStoreItemName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::CollectionName(void)
0x180040492  mov     r15, [rax]
0x180040495  mov     [rbp+150h+var_1A8], r15
0x180040499  mov     [rax], r12
0x18004049c  mov     [rbp+150h+var_1B0], r15
0x1800404a0  cmp     [rbp+150h+var_1C0], r12
0x1800404a4  jz      short loc_1800404AF
0x1800404a6  lea     rcx, [rbp+150h+var_1C0]
0x1800404aa  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800404af  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800404b3  test    r15, r15
0x1800404b6  jz      loc_18004060E
0x1800404bc  lea     rdx, [rbp+150h+lpMem]
0x1800404c0  lea     rcx, [rbp+150h+var_1B0]
0x1800404c4  call    ?CustomName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName@UICloudStoreCollectionName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreCollectionName>::CustomName(void)
0x1800404c9  mov     r13, [rax]
0x1800404cc  lea     rsi, String1
0x1800404d3  test    r13, r13
0x1800404d6  jz      short loc_1800404DE
0x1800404d8  mov     r13, [r13+10h]
0x1800404dc  jmp     short loc_1800404E1
0x1800404de  mov     r13, rsi
0x1800404e1  mov     r15, [rbp+150h+lpMem]
0x1800404e5  test    r15, r15
0x1800404e8  jz      short loc_18004050E
0x1800404ea  mov     eax, edi
0x1800404ec  lock xadd [r15+18h], eax
0x1800404f2  sub     eax, 1
0x1800404f5  jnz     short loc_18004052A
0x1800404f7  nop
0x1800404f8  call    WINRT_IMPL_GetProcessHeap
0x1800404fd  mov     rcx, rax; hHeap
0x180040500  mov     r8, r15; lpMem
0x180040503  xor     edx, edx; dwFlags
0x180040505  call    WINRT_IMPL_HeapFree
0x18004050a  mov     [rbp+150h+lpMem], r12
0x18004050e  lea     rdx, [rbp+150h+var_180]
0x180040512  lea     rcx, [rbp+150h+var_1B0]
0x180040516  call    ?PartitionName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName@UICloudStoreCollectionName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreCollectionName>::PartitionName(void)
0x18004051b  mov     r12, [rax]
0x18004051e  test    r12, r12
0x180040521  jz      short loc_180040535
0x180040523  mov     r12, [r12+10h]
0x180040528  jmp     short loc_180040538
0x18004052a  test    eax, eax
0x18004052c  jns     short loc_18004050A
0x18004052e  call    cs:__imp_abort
0x180040535  mov     r12, rsi
0x180040538  mov     r15, [rbp+150h+var_180]
0x18004053c  test    r15, r15
0x18004053f  jz      short loc_18004056D
0x180040541  mov     eax, edi
0x180040543  lock xadd [r15+18h], eax
0x180040549  sub     eax, 1
0x18004054c  jnz     loc_1800405FF
0x180040552  nop
0x180040553  call    WINRT_IMPL_GetProcessHeap
0x180040558  mov     rcx, rax; hHeap
0x18004055b  mov     r8, r15; lpMem
0x18004055e  xor     edx, edx; dwFlags
0x180040560  call    WINRT_IMPL_HeapFree
0x180040565  mov     [rbp+150h+var_180], 0
0x18004056d  mov     r15, [rbp+150h+var_1A8]
0x180040571  xorps   xmm0, xmm0
0x180040574  movups  [rbp+150h+var_D8], xmm0
0x180040578  mov     [rbp+150h+var_C8], 0
0x180040583  mov     [rbp+150h+var_C0], 0Fh
0x18004058e  mov     byte ptr [rbp+150h+var_D8], 0
0x180040592  movdqu  [rbp+150h+var_B8], xmm0
0x18004059a  mov     [rbp+150h+var_A8], 0
0x1800405a5  mov     eax, [rbp+150h+var_1B8]
0x1800405a8  mov     dword ptr [rsp+250h+var_228], eax
0x1800405ac  lea     rax, [rbp+150h+var_D8]
0x1800405b0  mov     [rsp+250h+var_230], rax
0x1800405b5  mov     r9d, [rbp+150h+var_1CC]
0x1800405b9  lea     r8, [rbp+150h+var_1D0]
0x1800405bd  lea     rdx, [rbp+150h+var_1CE]
0x1800405c1  mov     rcx, r14
0x1800405c4  call    ??$UnmarshalAllTypes@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CAJAEBUCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@AEA_N1W4DataDescriptionLanguage@1@AEAUScenarioKeysItemPdr@Passkey@Security@Data@6@J@Z; wil::ProfileDataStore::UnmarshalAllTypes<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(winrt::Windows::Internal::Storage::Cloud::CloudStoreData const &,bool &,bool &,wil::DataDescriptionLanguage,Windows::Data::Security::Passkey::ScenarioKeysItemPdr &,long)
0x1800405c9  mov     dword ptr [rbp+150h+var_1C0], eax
0x1800405cc  xor     eax, eax
0x1800405ce  cmp     [rbp+150h+var_1CF], al
0x1800405d1  jnz     short loc_1800405DB
0x1800405d3  mov     ebx, eax
0x1800405d5  cmp     [rbp+150h+var_1D0], al
0x1800405d8  setnz   bl
0x1800405db  mov     [rbp+150h+var_1B8], ebx
0x1800405de  mov     [rbp+150h+var_1CC], eax
0x1800405e1  lea     rdx, [rbp+150h+var_178]
0x1800405e5  mov     rcx, r14
0x1800405e8  call    ?CloudEtag@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData2@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::CloudEtag(void)
0x1800405ed  nop
0x1800405ee  mov     rax, [rax]
0x1800405f1  xor     r14d, r14d
0x1800405f4  test    rax, rax
0x1800405f7  jz      short loc_180040620
0x1800405f9  mov     rax, [rax+10h]
0x1800405fd  jmp     short loc_180040623
0x1800405ff  test    eax, eax
0x180040601  jns     loc_180040565
0x180040607  call    cs:__imp_abort
0x18004060e  lea     rsi, String1
0x180040615  mov     r12, rsi
0x180040618  mov     r13, rsi
0x18004061b  jmp     loc_180040571
0x180040620  mov     rax, rsi
0x180040623  mov     [rbp+150h+var_138], rax
0x180040627  lea     rax, [rbp+150h+var_168]
0x18004062b  mov     [rbp+150h+var_120], rax
0x18004062f  xorps   xmm0, xmm0
0x180040632  movups  [rbp+150h+var_168], xmm0
0x180040636  mov     [rbp+150h+var_158], r14
0x18004063a  mov     [rbp+150h+var_150], r14
0x18004063e  mov     r8, rdi
0x180040641  inc     r8
0x180040644  cmp     [r12+r8*2], r14w
0x180040649  jnz     short loc_180040641
0x18004064b  mov     rdx, r12
0x18004064e  lea     rcx, [rbp+150h+var_168]
0x180040652  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180040657  nop
0x180040658  lea     rax, [rbp+150h+var_118]
0x18004065c  mov     [rbp+150h+var_180], rax
0x180040660  xorps   xmm0, xmm0
0x180040663  movups  [rbp+150h+var_118], xmm0
0x180040667  mov     [rbp+150h+var_108], r14
0x18004066b  mov     [rbp+150h+var_100], r14
0x18004066f  mov     r8, rdi
0x180040672  inc     r8
0x180040675  cmp     [r13+r8*2+0], r14w
0x18004067b  jnz     short loc_180040672
0x18004067d  mov     rdx, r13
0x180040680  lea     rcx, [rbp+150h+var_118]
0x180040684  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180040689  nop
0x18004068a  lea     rdx, [rbp+150h+var_1A8]
0x18004068e  lea     rcx, [rbp+150h+var_1C8]
0x180040692  call    ?InstanceName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName@UICloudStoreItemName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::InstanceName(void)
0x180040697  nop
0x180040698  mov     rcx, [rax]
0x18004069b  test    rcx, rcx
0x18004069e  jz      short loc_1800406A4
0x1800406a0  mov     rsi, [rcx+10h]
0x1800406a4  xorps   xmm0, xmm0
0x1800406a7  movups  [rbp+150h+var_F8], xmm0
0x1800406ab  mov     [rbp+150h+var_E8], r14
0x1800406af  mov     [rbp+150h+var_E0], r14
0x1800406b3  mov     r8, rdi
0x1800406b6  inc     r8
0x1800406b9  cmp     [rsi+r8*2], r14w
0x1800406be  jnz     short loc_1800406B6
0x1800406c0  mov     rdx, rsi
0x1800406c3  lea     rcx, [rbp+150h+var_F8]
0x1800406c7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800406cc  nop
0x1800406cd  lea     r9, [rbp+150h+var_168]
0x1800406d1  lea     r8, [rbp+150h+var_118]
0x1800406d5  lea     rdx, [rbp+150h+var_F8]
0x1800406d9  lea     rcx, [rbp+150h+var_A0]
0x1800406e0  call    ??0?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>(std::wstring,std::wstring,std::wstring)
0x1800406e5  mov     rbx, rax
0x1800406e8  mov     ecx, 108h; Size
0x1800406ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800406f2  mov     [rbp+150h+var_120], rax
0x1800406f6  lea     rcx, [rbp+150h+var_1B8]
0x1800406fa  mov     [rsp+250h+var_1E0], rcx
0x1800406ff  lea     rcx, [rbp+150h+var_1CC]
0x180040703  mov     [rsp+250h+var_1E8], rcx
0x180040708  lea     rcx, [rbp+150h+var_140]
0x18004070c  mov     [rsp+250h+var_1F0], rcx
0x180040711  lea     rcx, [rbp+150h+var_1C0]
0x180040715  mov     [rsp+250h+var_1F8], rcx
  ... truncated ...
```
