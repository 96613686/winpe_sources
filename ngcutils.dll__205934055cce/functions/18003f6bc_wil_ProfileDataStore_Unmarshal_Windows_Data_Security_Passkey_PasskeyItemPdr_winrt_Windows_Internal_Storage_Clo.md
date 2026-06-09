# wil::ProfileDataStore::Unmarshal<Windows::Data::Security::Passkey::PasskeyItemPdr>(winrt::Windows::Internal::Storage::Cloud::CloudStoreData const &,wil::ProfileDataStoreLoadOptions)

- ea: `0x18003f6bc`
- end: `0x18003fcd1`
- name: `??$Unmarshal@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@AEBUCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@W4ProfileDataStoreLoadOptions@1@@Z`
- size: `1557`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `broker_com_uri`

## callers

- `0x1800273a0`
- `0x18002a190`

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
- `0x18003f6bc`
- `0x1800408e4`
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

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003f922`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003f9fb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003fc89`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003fc98`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003f922`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003f9fb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003fc89`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003fc98`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_QWORD *__fastcall wil::ProfileDataStore::Unmarshal<Windows::Data::Security::Passkey::PasskeyItemPdr>(
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
  LODWORD(v58) = wil::ProfileDataStore::UnmarshalAllTypes<Windows::Data::Security::Passkey::PasskeyItemPdr>(
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
0x18003f6bc  mov     [rsp-8+arg_10], rbx
0x18003f6c1  push    rbp
0x18003f6c2  push    rsi
0x18003f6c3  push    rdi
0x18003f6c4  push    r12
0x18003f6c6  push    r13
0x18003f6c8  push    r14
0x18003f6ca  push    r15
0x18003f6cc  lea     rbp, [rsp-120h]
0x18003f6d4  sub     rsp, 220h
0x18003f6db  mov     rax, cs:__security_cookie
0x18003f6e2  xor     rax, rsp
0x18003f6e5  mov     [rbp+150h+var_40], rax
0x18003f6ec  mov     edi, r8d
0x18003f6ef  mov     r14, rdx
0x18003f6f2  mov     [rbp+150h+var_128], rcx
0x18003f6f6  mov     [rbp+150h+var_170], rcx
0x18003f6fa  xor     r12d, r12d
0x18003f6fd  mov     esi, r12d
0x18003f700  mov     [rbp+150h+var_190], r12
0x18003f704  lea     r15d, [r12+1]
0x18003f709  mov     [rbp+150h+var_1D0], r15b
0x18003f70d  mov     [rbp+150h+var_1CE], r12b
0x18003f711  lea     rdx, [rbp+150h+var_1B4]
0x18003f715  mov     rcx, r14
0x18003f718  call    ?ResultCode@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData2@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::ResultCode(void)
0x18003f71d  mov     eax, [rax]
0x18003f71f  mov     [rbp+150h+var_1B8], eax
0x18003f722  mov     rcx, r14
0x18003f725  call    ?RetryAfter@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData2@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::RetryAfter(void)
0x18003f72a  mov     [rbp+150h+var_140], rax
0x18003f72e  mov     rcx, r14
0x18003f731  call    ?DataDescriptionLanguage@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData2@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::DataDescriptionLanguage(void)
0x18003f736  test    eax, eax
0x18003f738  jz      short loc_18003F748
0x18003f73a  cmp     eax, r15d
0x18003f73d  jnz     loc_18003FCAB
0x18003f743  mov     eax, r15d
0x18003f746  jmp     short loc_18003F74B
0x18003f748  mov     eax, r12d
0x18003f74b  mov     [rbp+150h+var_1CC], eax
0x18003f74e  mov     [rbp+150h+var_1A0], eax
0x18003f751  mov     rcx, r14
0x18003f754  call    ?Status@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData@UICloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::Status(void)
0x18003f759  mov     ebx, eax
0x18003f75b  mov     rcx, r14
0x18003f75e  call    ?Version@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData@UICloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::Version(void)
0x18003f763  mov     [rbp+150h+var_130], rax
0x18003f767  cmp     ebx, r15d
0x18003f76a  cmovz   esi, r15d
0x18003f76e  mov     [rbp+150h+var_1B4], esi
0x18003f771  mov     rcx, [r14]
0x18003f774  mov     [rbp+150h+var_1C8], r12
0x18003f778  test    rcx, rcx
0x18003f77b  jnz     short loc_18003F782
0x18003f77d  mov     rbx, r12
0x18003f780  jmp     short loc_18003F7BE
0x18003f782  mov     dword ptr [rbp+150h+var_168], 84Bh
0x18003f789  lea     rax, aOnecoreuapInte_5; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x18003f790  mov     qword ptr [rbp+150h+var_168+8], rax
0x18003f794  mov     [rbp+150h+var_158], r12
0x18003f798  mov     rax, [rcx]
0x18003f79b  lea     r8, [rbp+150h+var_1C8]
0x18003f79f  lea     rdx, ??$guid_v@UICloudStoreData@Cloud@Storage@Internal@Windows@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<Windows::Internal::Storage::Cloud::ICloudStoreData>
0x18003f7a6  mov     rax, [rax]
0x18003f7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7ae  test    eax, eax
0x18003f7b0  js      loc_18003FC9F
0x18003f7b6  mov     rbx, [rbp+150h+var_1C8]
0x18003f7ba  mov     [rbp+150h+var_1C8], rbx
0x18003f7be  mov     [rbp+150h+var_1CF], r12b
0x18003f7c2  test    rbx, rbx
0x18003f7c5  jz      short loc_18003F7D7
0x18003f7c7  mov     rax, [rbx]
0x18003f7ca  mov     rcx, rbx
0x18003f7cd  mov     rax, [rax+8]
0x18003f7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7d6  nop
0x18003f7d7  mov     [rbp+150h+var_190], rbx
0x18003f7db  test    rbx, rbx
0x18003f7de  jz      short loc_18003F7EA
0x18003f7e0  lea     rcx, [rbp+150h+var_1C8]
0x18003f7e4  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x18003f7e9  nop
0x18003f7ea  mov     [rbp+150h+var_198], r12
0x18003f7ee  mov     rax, [rbx]
0x18003f7f1  lea     r8, [rbp+150h+var_198]
0x18003f7f5  lea     rdx, _GUID_910745a7_98d9_4169_aa1d_9a7896a26170
0x18003f7fc  mov     rcx, rbx
0x18003f7ff  mov     rax, [rax]
0x18003f802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f807  nop
0x18003f808  mov     rcx, [rbp+150h+var_198]
0x18003f80c  test    rcx, rcx
0x18003f80f  jz      short loc_18003F83E
0x18003f811  mov     dword ptr [rbp+150h+var_1C0], r12d
0x18003f815  mov     rax, [rcx]
0x18003f818  lea     rdx, [rbp+150h+var_1C0]
0x18003f81c  mov     rax, [rax+30h]
0x18003f820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f825  test    eax, eax
0x18003f827  js      short loc_18003F83E
0x18003f829  mov     ebx, dword ptr [rbp+150h+var_1C0]
0x18003f82c  and     ebx, r15d
0x18003f82f  test    byte ptr [rbp+150h+var_1C0], 2
0x18003f833  jz      short loc_18003F838
0x18003f835  or      ebx, 2
0x18003f838  mov     [rbp+150h+var_1CF], r15b
0x18003f83c  jmp     short loc_18003F841
0x18003f83e  mov     ebx, [rbp+150h+var_1B4]
0x18003f841  and     dil, 3
0x18003f845  neg     dil
0x18003f848  sbb     al, al
0x18003f84a  and     al, r15b
0x18003f84d  mov     [rbp+150h+var_1CD], al
0x18003f850  lea     rdx, [rbp+150h+var_1B0]
0x18003f854  mov     rcx, r14
0x18003f857  call    ?ItemName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData@UICloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::ItemName(void)
0x18003f85c  mov     rcx, [rax]
0x18003f85f  mov     [rbp+150h+var_170], rcx
0x18003f863  mov     [rax], r12
0x18003f866  mov     [rbp+150h+var_1C8], rcx
0x18003f86a  cmp     [rbp+150h+var_1B0], r12
0x18003f86e  jz      short loc_18003F879
0x18003f870  lea     rcx, [rbp+150h+var_1B0]
0x18003f874  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003f879  lea     rdx, [rbp+150h+var_1C0]
0x18003f87d  lea     rcx, [rbp+150h+var_1C8]
0x18003f881  call    ?CollectionName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName@UICloudStoreItemName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::CollectionName(void)
0x18003f886  mov     r15, [rax]
0x18003f889  mov     [rbp+150h+var_1A8], r15
0x18003f88d  mov     [rax], r12
0x18003f890  mov     [rbp+150h+var_1B0], r15
0x18003f894  cmp     [rbp+150h+var_1C0], r12
0x18003f898  jz      short loc_18003F8A3
0x18003f89a  lea     rcx, [rbp+150h+var_1C0]
0x18003f89e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003f8a3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003f8a7  test    r15, r15
0x18003f8aa  jz      loc_18003FA02
0x18003f8b0  lea     rdx, [rbp+150h+lpMem]
0x18003f8b4  lea     rcx, [rbp+150h+var_1B0]
0x18003f8b8  call    ?CustomName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName@UICloudStoreCollectionName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreCollectionName>::CustomName(void)
0x18003f8bd  mov     r13, [rax]
0x18003f8c0  lea     rsi, String1
0x18003f8c7  test    r13, r13
0x18003f8ca  jz      short loc_18003F8D2
0x18003f8cc  mov     r13, [r13+10h]
0x18003f8d0  jmp     short loc_18003F8D5
0x18003f8d2  mov     r13, rsi
0x18003f8d5  mov     r15, [rbp+150h+lpMem]
0x18003f8d9  test    r15, r15
0x18003f8dc  jz      short loc_18003F902
0x18003f8de  mov     eax, edi
0x18003f8e0  lock xadd [r15+18h], eax
0x18003f8e6  sub     eax, 1
0x18003f8e9  jnz     short loc_18003F91E
0x18003f8eb  nop
0x18003f8ec  call    WINRT_IMPL_GetProcessHeap
0x18003f8f1  mov     rcx, rax; hHeap
0x18003f8f4  mov     r8, r15; lpMem
0x18003f8f7  xor     edx, edx; dwFlags
0x18003f8f9  call    WINRT_IMPL_HeapFree
0x18003f8fe  mov     [rbp+150h+lpMem], r12
0x18003f902  lea     rdx, [rbp+150h+var_180]
0x18003f906  lea     rcx, [rbp+150h+var_1B0]
0x18003f90a  call    ?PartitionName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName@UICloudStoreCollectionName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreCollectionName>::PartitionName(void)
0x18003f90f  mov     r12, [rax]
0x18003f912  test    r12, r12
0x18003f915  jz      short loc_18003F929
0x18003f917  mov     r12, [r12+10h]
0x18003f91c  jmp     short loc_18003F92C
0x18003f91e  test    eax, eax
0x18003f920  jns     short loc_18003F8FE
0x18003f922  call    cs:__imp_abort
0x18003f929  mov     r12, rsi
0x18003f92c  mov     r15, [rbp+150h+var_180]
0x18003f930  test    r15, r15
0x18003f933  jz      short loc_18003F961
0x18003f935  mov     eax, edi
0x18003f937  lock xadd [r15+18h], eax
0x18003f93d  sub     eax, 1
0x18003f940  jnz     loc_18003F9F3
0x18003f946  nop
0x18003f947  call    WINRT_IMPL_GetProcessHeap
0x18003f94c  mov     rcx, rax; hHeap
0x18003f94f  mov     r8, r15; lpMem
0x18003f952  xor     edx, edx; dwFlags
0x18003f954  call    WINRT_IMPL_HeapFree
0x18003f959  mov     [rbp+150h+var_180], 0
0x18003f961  mov     r15, [rbp+150h+var_1A8]
0x18003f965  xorps   xmm0, xmm0
0x18003f968  movups  [rbp+150h+var_D8], xmm0
0x18003f96c  mov     [rbp+150h+var_C8], 0
0x18003f977  mov     [rbp+150h+var_C0], 0Fh
0x18003f982  mov     byte ptr [rbp+150h+var_D8], 0
0x18003f986  movdqu  [rbp+150h+var_B8], xmm0
0x18003f98e  mov     [rbp+150h+var_A8], 0
0x18003f999  mov     eax, [rbp+150h+var_1B8]
0x18003f99c  mov     dword ptr [rsp+250h+var_228], eax
0x18003f9a0  lea     rax, [rbp+150h+var_D8]
0x18003f9a4  mov     [rsp+250h+var_230], rax
0x18003f9a9  mov     r9d, [rbp+150h+var_1CC]
0x18003f9ad  lea     r8, [rbp+150h+var_1D0]
0x18003f9b1  lea     rdx, [rbp+150h+var_1CE]
0x18003f9b5  mov     rcx, r14
0x18003f9b8  call    ??$UnmarshalAllTypes@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CAJAEBUCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@AEA_N1W4DataDescriptionLanguage@1@AEAUPasskeyItemPdr@Passkey@Security@Data@6@J@Z; wil::ProfileDataStore::UnmarshalAllTypes<Windows::Data::Security::Passkey::PasskeyItemPdr>(winrt::Windows::Internal::Storage::Cloud::CloudStoreData const &,bool &,bool &,wil::DataDescriptionLanguage,Windows::Data::Security::Passkey::PasskeyItemPdr &,long)
0x18003f9bd  mov     dword ptr [rbp+150h+var_1C0], eax
0x18003f9c0  xor     eax, eax
0x18003f9c2  cmp     [rbp+150h+var_1CF], al
0x18003f9c5  jnz     short loc_18003F9CF
0x18003f9c7  mov     ebx, eax
0x18003f9c9  cmp     [rbp+150h+var_1D0], al
0x18003f9cc  setnz   bl
0x18003f9cf  mov     [rbp+150h+var_1B8], ebx
0x18003f9d2  mov     [rbp+150h+var_1CC], eax
0x18003f9d5  lea     rdx, [rbp+150h+var_178]
0x18003f9d9  mov     rcx, r14
0x18003f9dc  call    ?CloudEtag@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData2@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::CloudEtag(void)
0x18003f9e1  nop
0x18003f9e2  mov     rax, [rax]
0x18003f9e5  xor     r14d, r14d
0x18003f9e8  test    rax, rax
0x18003f9eb  jz      short loc_18003FA14
0x18003f9ed  mov     rax, [rax+10h]
0x18003f9f1  jmp     short loc_18003FA17
0x18003f9f3  test    eax, eax
0x18003f9f5  jns     loc_18003F959
0x18003f9fb  call    cs:__imp_abort
0x18003fa02  lea     rsi, String1
0x18003fa09  mov     r12, rsi
0x18003fa0c  mov     r13, rsi
0x18003fa0f  jmp     loc_18003F965
0x18003fa14  mov     rax, rsi
0x18003fa17  mov     [rbp+150h+var_138], rax
0x18003fa1b  lea     rax, [rbp+150h+var_168]
0x18003fa1f  mov     [rbp+150h+var_120], rax
0x18003fa23  xorps   xmm0, xmm0
0x18003fa26  movups  [rbp+150h+var_168], xmm0
0x18003fa2a  mov     [rbp+150h+var_158], r14
0x18003fa2e  mov     [rbp+150h+var_150], r14
0x18003fa32  mov     r8, rdi
0x18003fa35  inc     r8
0x18003fa38  cmp     [r12+r8*2], r14w
0x18003fa3d  jnz     short loc_18003FA35
0x18003fa3f  mov     rdx, r12
0x18003fa42  lea     rcx, [rbp+150h+var_168]
0x18003fa46  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003fa4b  nop
0x18003fa4c  lea     rax, [rbp+150h+var_118]
0x18003fa50  mov     [rbp+150h+var_180], rax
0x18003fa54  xorps   xmm0, xmm0
0x18003fa57  movups  [rbp+150h+var_118], xmm0
0x18003fa5b  mov     [rbp+150h+var_108], r14
0x18003fa5f  mov     [rbp+150h+var_100], r14
0x18003fa63  mov     r8, rdi
0x18003fa66  inc     r8
0x18003fa69  cmp     [r13+r8*2+0], r14w
0x18003fa6f  jnz     short loc_18003FA66
0x18003fa71  mov     rdx, r13
0x18003fa74  lea     rcx, [rbp+150h+var_118]
0x18003fa78  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003fa7d  nop
0x18003fa7e  lea     rdx, [rbp+150h+var_1A8]
0x18003fa82  lea     rcx, [rbp+150h+var_1C8]
0x18003fa86  call    ?InstanceName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName@UICloudStoreItemName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::InstanceName(void)
0x18003fa8b  nop
0x18003fa8c  mov     rcx, [rax]
0x18003fa8f  test    rcx, rcx
0x18003fa92  jz      short loc_18003FA98
0x18003fa94  mov     rsi, [rcx+10h]
0x18003fa98  xorps   xmm0, xmm0
0x18003fa9b  movups  [rbp+150h+var_F8], xmm0
0x18003fa9f  mov     [rbp+150h+var_E8], r14
0x18003faa3  mov     [rbp+150h+var_E0], r14
0x18003faa7  mov     r8, rdi
0x18003faaa  inc     r8
0x18003faad  cmp     [rsi+r8*2], r14w
0x18003fab2  jnz     short loc_18003FAAA
0x18003fab4  mov     rdx, rsi
0x18003fab7  lea     rcx, [rbp+150h+var_F8]
0x18003fabb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003fac0  nop
0x18003fac1  lea     r9, [rbp+150h+var_168]
0x18003fac5  lea     r8, [rbp+150h+var_118]
0x18003fac9  lea     rdx, [rbp+150h+var_F8]
0x18003facd  lea     rcx, [rbp+150h+var_A0]
0x18003fad4  call    ??0?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>(std::wstring,std::wstring,std::wstring)
0x18003fad9  mov     rbx, rax
0x18003fadc  mov     ecx, 108h; Size
0x18003fae1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003fae6  mov     [rbp+150h+var_120], rax
0x18003faea  lea     rcx, [rbp+150h+var_1B8]
0x18003faee  mov     [rsp+250h+var_1E0], rcx
0x18003faf3  lea     rcx, [rbp+150h+var_1CC]
0x18003faf7  mov     [rsp+250h+var_1E8], rcx
0x18003fafc  lea     rcx, [rbp+150h+var_140]
0x18003fb00  mov     [rsp+250h+var_1F0], rcx
0x18003fb05  lea     rcx, [rbp+150h+var_1C0]
0x18003fb09  mov     [rsp+250h+var_1F8], rcx
  ... truncated ...
```
