# wil::ProfileDataStore::Unmarshal<Windows::Data::Security::Passkey::RecoveryItemPdr>(winrt::Windows::Internal::Storage::Cloud::CloudStoreData const &,wil::ProfileDataStoreLoadOptions)

- ea: `0x18003fcd8`
- end: `0x1800402bf`
- name: `??$Unmarshal@URecoveryItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$shared_ptr@V?$ProfileDataItem@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@AEBUCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@W4ProfileDataStoreLoadOptions@1@@Z`
- size: `1511`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x1800280d0`
- `0x18002a9f0`

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
- `0x18001ae30`
- `0x18001cdc4`
- `0x18003fcd8`
- `0x180040a48`
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

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003ff3e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003ffef`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180040277`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180040286`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003ff3e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003ffef`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180040277`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180040286`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_QWORD *__fastcall wil::ProfileDataStore::Unmarshal<Windows::Data::Security::Passkey::RecoveryItemPdr>(
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
  __int128 v80; // [rsp+150h] [rbp+50h] BYREF
  __int64 v81; // [rsp+160h] [rbp+60h]
  __int64 v82; // [rsp+168h] [rbp+68h]
  __int128 v83; // [rsp+170h] [rbp+70h] BYREF
  __int64 v84; // [rsp+180h] [rbp+80h]
  __int64 v85; // [rsp+188h] [rbp+88h]
  _BYTE v86[32]; // [rsp+190h] [rbp+90h] BYREF
  char v87[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v88[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

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
  v78 = 0;
  v79 = 0;
  LODWORD(v58) = wil::ProfileDataStore::UnmarshalAllTypes<Windows::Data::Security::Passkey::RecoveryItemPdr>(
                   (_DWORD)a2,
                   (unsigned int)&v54,
                   (unsigned int)&v52,
                   v56,
                   (__int64)&v78,
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
  v67 = &v80;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v31 = -1;
  do
    ++v31;
  while ( v19[v31] );
  std::wstring::_Construct<1,unsigned short const *>(&v80, v19, v31);
  v32 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::InstanceName(
          &v57,
          &v62);
  if ( *(_QWORD *)v32 )
    v18 = *(const WCHAR **)(*(_QWORD *)v32 + 16LL);
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v33 = -1;
  do
    ++v33;
  while ( v18[v33] );
  std::wstring::_Construct<1,unsigned short const *>(&v83, v18, v33);
  v34 = wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>(
          v86,
          &v83,
          &v80,
          &v70);
  v77 = (__int128 *)operator new(0xE8u);
  v35 = std::_Ref_count_obj2<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Ref_count_obj2<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>(
          (_DWORD)v77,
          (unsigned int)&v78,
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
  std::wstring::~wstring(v88, v37, v38);
  std::wstring::~wstring(v87, v39, v40);
  std::wstring::~wstring(v86, v41, v42);
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
  std::vector<unsigned char>::~vector<unsigned char>(&v78);
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
0x18003fcd8  mov     [rsp-8+arg_10], rbx
0x18003fcdd  push    rbp
0x18003fcde  push    rsi
0x18003fcdf  push    rdi
0x18003fce0  push    r12
0x18003fce2  push    r13
0x18003fce4  push    r14
0x18003fce6  push    r15
0x18003fce8  lea     rbp, [rsp-100h]
0x18003fcf0  sub     rsp, 200h
0x18003fcf7  mov     rax, cs:__security_cookie
0x18003fcfe  xor     rax, rsp
0x18003fd01  mov     [rbp+130h+var_40], rax
0x18003fd08  mov     edi, r8d
0x18003fd0b  mov     r14, rdx
0x18003fd0e  mov     [rbp+130h+var_108], rcx
0x18003fd12  mov     [rbp+130h+var_150], rcx
0x18003fd16  xor     r12d, r12d
0x18003fd19  mov     esi, r12d
0x18003fd1c  mov     [rbp+130h+var_170], r12
0x18003fd20  lea     r15d, [r12+1]
0x18003fd25  mov     [rbp+130h+var_1B0], r15b
0x18003fd29  mov     [rbp+130h+var_1AE], r12b
0x18003fd2d  lea     rdx, [rbp+130h+var_194]
0x18003fd31  mov     rcx, r14
0x18003fd34  call    ?ResultCode@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData2@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::ResultCode(void)
0x18003fd39  mov     eax, [rax]
0x18003fd3b  mov     [rbp+130h+var_198], eax
0x18003fd3e  mov     rcx, r14
0x18003fd41  call    ?RetryAfter@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData2@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::RetryAfter(void)
0x18003fd46  mov     [rbp+130h+var_120], rax
0x18003fd4a  mov     rcx, r14
0x18003fd4d  call    ?DataDescriptionLanguage@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData2@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::DataDescriptionLanguage(void)
0x18003fd52  test    eax, eax
0x18003fd54  jz      short loc_18003FD64
0x18003fd56  cmp     eax, r15d
0x18003fd59  jnz     loc_180040299
0x18003fd5f  mov     eax, r15d
0x18003fd62  jmp     short loc_18003FD67
0x18003fd64  mov     eax, r12d
0x18003fd67  mov     [rbp+130h+var_1AC], eax
0x18003fd6a  mov     [rbp+130h+var_180], eax
0x18003fd6d  mov     rcx, r14
0x18003fd70  call    ?Status@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData@UICloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::Status(void)
0x18003fd75  mov     ebx, eax
0x18003fd77  mov     rcx, r14
0x18003fd7a  call    ?Version@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData@UICloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::Version(void)
0x18003fd7f  mov     [rbp+130h+var_110], rax
0x18003fd83  cmp     ebx, r15d
0x18003fd86  cmovz   esi, r15d
0x18003fd8a  mov     [rbp+130h+var_194], esi
0x18003fd8d  mov     rcx, [r14]
0x18003fd90  mov     [rbp+130h+var_1A8], r12
0x18003fd94  test    rcx, rcx
0x18003fd97  jnz     short loc_18003FD9E
0x18003fd99  mov     rbx, r12
0x18003fd9c  jmp     short loc_18003FDDA
0x18003fd9e  mov     dword ptr [rbp+130h+var_148], 84Bh
0x18003fda5  lea     rax, aOnecoreuapInte_5; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x18003fdac  mov     qword ptr [rbp+130h+var_148+8], rax
0x18003fdb0  mov     [rbp+130h+var_138], r12
0x18003fdb4  mov     rax, [rcx]
0x18003fdb7  lea     r8, [rbp+130h+var_1A8]
0x18003fdbb  lea     rdx, ??$guid_v@UICloudStoreData@Cloud@Storage@Internal@Windows@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<Windows::Internal::Storage::Cloud::ICloudStoreData>
0x18003fdc2  mov     rax, [rax]
0x18003fdc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fdca  test    eax, eax
0x18003fdcc  js      loc_18004028D
0x18003fdd2  mov     rbx, [rbp+130h+var_1A8]
0x18003fdd6  mov     [rbp+130h+var_1A8], rbx
0x18003fdda  mov     [rbp+130h+var_1AF], r12b
0x18003fdde  test    rbx, rbx
0x18003fde1  jz      short loc_18003FDF3
0x18003fde3  mov     rax, [rbx]
0x18003fde6  mov     rcx, rbx
0x18003fde9  mov     rax, [rax+8]
0x18003fded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fdf2  nop
0x18003fdf3  mov     [rbp+130h+var_170], rbx
0x18003fdf7  test    rbx, rbx
0x18003fdfa  jz      short loc_18003FE06
0x18003fdfc  lea     rcx, [rbp+130h+var_1A8]
0x18003fe00  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)
0x18003fe05  nop
0x18003fe06  mov     [rbp+130h+var_178], r12
0x18003fe0a  mov     rax, [rbx]
0x18003fe0d  lea     r8, [rbp+130h+var_178]
0x18003fe11  lea     rdx, _GUID_910745a7_98d9_4169_aa1d_9a7896a26170
0x18003fe18  mov     rcx, rbx
0x18003fe1b  mov     rax, [rax]
0x18003fe1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe23  nop
0x18003fe24  mov     rcx, [rbp+130h+var_178]
0x18003fe28  test    rcx, rcx
0x18003fe2b  jz      short loc_18003FE5A
0x18003fe2d  mov     dword ptr [rbp+130h+var_1A0], r12d
0x18003fe31  mov     rax, [rcx]
0x18003fe34  lea     rdx, [rbp+130h+var_1A0]
0x18003fe38  mov     rax, [rax+30h]
0x18003fe3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe41  test    eax, eax
0x18003fe43  js      short loc_18003FE5A
0x18003fe45  mov     ebx, dword ptr [rbp+130h+var_1A0]
0x18003fe48  and     ebx, r15d
0x18003fe4b  test    byte ptr [rbp+130h+var_1A0], 2
0x18003fe4f  jz      short loc_18003FE54
0x18003fe51  or      ebx, 2
0x18003fe54  mov     [rbp+130h+var_1AF], r15b
0x18003fe58  jmp     short loc_18003FE5D
0x18003fe5a  mov     ebx, [rbp+130h+var_194]
0x18003fe5d  and     dil, 3
0x18003fe61  neg     dil
0x18003fe64  sbb     al, al
0x18003fe66  and     al, r15b
0x18003fe69  mov     [rbp+130h+var_1AD], al
0x18003fe6c  lea     rdx, [rbp+130h+var_190]
0x18003fe70  mov     rcx, r14
0x18003fe73  call    ?ItemName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData@UICloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::ItemName(void)
0x18003fe78  mov     rcx, [rax]
0x18003fe7b  mov     [rbp+130h+var_150], rcx
0x18003fe7f  mov     [rax], r12
0x18003fe82  mov     [rbp+130h+var_1A8], rcx
0x18003fe86  cmp     [rbp+130h+var_190], r12
0x18003fe8a  jz      short loc_18003FE95
0x18003fe8c  lea     rcx, [rbp+130h+var_190]
0x18003fe90  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003fe95  lea     rdx, [rbp+130h+var_1A0]
0x18003fe99  lea     rcx, [rbp+130h+var_1A8]
0x18003fe9d  call    ?CollectionName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName@UICloudStoreItemName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::CollectionName(void)
0x18003fea2  mov     r15, [rax]
0x18003fea5  mov     [rbp+130h+var_188], r15
0x18003fea9  mov     [rax], r12
0x18003feac  mov     [rbp+130h+var_190], r15
0x18003feb0  cmp     [rbp+130h+var_1A0], r12
0x18003feb4  jz      short loc_18003FEBF
0x18003feb6  lea     rcx, [rbp+130h+var_1A0]
0x18003feba  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003febf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003fec3  test    r15, r15
0x18003fec6  jz      loc_18003FFF6
0x18003fecc  lea     rdx, [rbp+130h+lpMem]
0x18003fed0  lea     rcx, [rbp+130h+var_190]
0x18003fed4  call    ?CustomName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName@UICloudStoreCollectionName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreCollectionName>::CustomName(void)
0x18003fed9  mov     r13, [rax]
0x18003fedc  lea     rsi, String1
0x18003fee3  test    r13, r13
0x18003fee6  jz      short loc_18003FEEE
0x18003fee8  mov     r13, [r13+10h]
0x18003feec  jmp     short loc_18003FEF1
0x18003feee  mov     r13, rsi
0x18003fef1  mov     r15, [rbp+130h+lpMem]
0x18003fef5  test    r15, r15
0x18003fef8  jz      short loc_18003FF1E
0x18003fefa  mov     eax, edi
0x18003fefc  lock xadd [r15+18h], eax
0x18003ff02  sub     eax, 1
0x18003ff05  jnz     short loc_18003FF3A
0x18003ff07  nop
0x18003ff08  call    WINRT_IMPL_GetProcessHeap
0x18003ff0d  mov     rcx, rax; hHeap
0x18003ff10  mov     r8, r15; lpMem
0x18003ff13  xor     edx, edx; dwFlags
0x18003ff15  call    WINRT_IMPL_HeapFree
0x18003ff1a  mov     [rbp+130h+lpMem], r12
0x18003ff1e  lea     rdx, [rbp+130h+var_160]
0x18003ff22  lea     rcx, [rbp+130h+var_190]
0x18003ff26  call    ?PartitionName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName@UICloudStoreCollectionName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreCollectionName>::PartitionName(void)
0x18003ff2b  mov     r12, [rax]
0x18003ff2e  test    r12, r12
0x18003ff31  jz      short loc_18003FF45
0x18003ff33  mov     r12, [r12+10h]
0x18003ff38  jmp     short loc_18003FF48
0x18003ff3a  test    eax, eax
0x18003ff3c  jns     short loc_18003FF1A
0x18003ff3e  call    cs:__imp_abort
0x18003ff45  mov     r12, rsi
0x18003ff48  mov     r15, [rbp+130h+var_160]
0x18003ff4c  test    r15, r15
0x18003ff4f  jz      short loc_18003FF7D
0x18003ff51  mov     eax, edi
0x18003ff53  lock xadd [r15+18h], eax
0x18003ff59  sub     eax, 1
0x18003ff5c  jnz     loc_18003FFEB
0x18003ff62  nop
0x18003ff63  call    WINRT_IMPL_GetProcessHeap
0x18003ff68  mov     rcx, rax; hHeap
0x18003ff6b  mov     r8, r15; lpMem
0x18003ff6e  xor     edx, edx; dwFlags
0x18003ff70  call    WINRT_IMPL_HeapFree
0x18003ff75  mov     [rbp+130h+var_160], 0
0x18003ff7d  mov     r15, [rbp+130h+var_188]
0x18003ff81  xorps   xmm0, xmm0
0x18003ff84  movdqu  [rbp+130h+var_F8], xmm0
0x18003ff89  mov     [rbp+130h+var_E8], 0
0x18003ff91  mov     eax, [rbp+130h+var_198]
0x18003ff94  mov     dword ptr [rsp+230h+var_208], eax
0x18003ff98  lea     rax, [rbp+130h+var_F8]
0x18003ff9c  mov     [rsp+230h+var_210], rax
0x18003ffa1  mov     r9d, [rbp+130h+var_1AC]
0x18003ffa5  lea     r8, [rbp+130h+var_1B0]
0x18003ffa9  lea     rdx, [rbp+130h+var_1AE]
0x18003ffad  mov     rcx, r14
0x18003ffb0  call    ??$UnmarshalAllTypes@URecoveryItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CAJAEBUCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@AEA_N1W4DataDescriptionLanguage@1@AEAURecoveryItemPdr@Passkey@Security@Data@6@J@Z; wil::ProfileDataStore::UnmarshalAllTypes<Windows::Data::Security::Passkey::RecoveryItemPdr>(winrt::Windows::Internal::Storage::Cloud::CloudStoreData const &,bool &,bool &,wil::DataDescriptionLanguage,Windows::Data::Security::Passkey::RecoveryItemPdr &,long)
0x18003ffb5  mov     dword ptr [rbp+130h+var_1A0], eax
0x18003ffb8  xor     eax, eax
0x18003ffba  cmp     [rbp+130h+var_1AF], al
0x18003ffbd  jnz     short loc_18003FFC7
0x18003ffbf  mov     ebx, eax
0x18003ffc1  cmp     [rbp+130h+var_1B0], al
0x18003ffc4  setnz   bl
0x18003ffc7  mov     [rbp+130h+var_198], ebx
0x18003ffca  mov     [rbp+130h+var_1AC], eax
0x18003ffcd  lea     rdx, [rbp+130h+var_158]
0x18003ffd1  mov     rcx, r14
0x18003ffd4  call    ?CloudEtag@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData2@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData2<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::CloudEtag(void)
0x18003ffd9  nop
0x18003ffda  mov     rax, [rax]
0x18003ffdd  xor     r14d, r14d
0x18003ffe0  test    rax, rax
0x18003ffe3  jz      short loc_180040008
0x18003ffe5  mov     rax, [rax+10h]
0x18003ffe9  jmp     short loc_18004000B
0x18003ffeb  test    eax, eax
0x18003ffed  jns     short loc_18003FF75
0x18003ffef  call    cs:__imp_abort
0x18003fff6  lea     rsi, String1
0x18003fffd  mov     r12, rsi
0x180040000  mov     r13, rsi
0x180040003  jmp     loc_18003FF81
0x180040008  mov     rax, rsi
0x18004000b  mov     [rbp+130h+var_118], rax
0x18004000f  lea     rax, [rbp+130h+var_148]
0x180040013  mov     [rbp+130h+var_100], rax
0x180040017  xorps   xmm0, xmm0
0x18004001a  movups  [rbp+130h+var_148], xmm0
0x18004001e  mov     [rbp+130h+var_138], r14
0x180040022  mov     [rbp+130h+var_130], r14
0x180040026  mov     r8, rdi
0x180040029  inc     r8
0x18004002c  cmp     [r12+r8*2], r14w
0x180040031  jnz     short loc_180040029
0x180040033  mov     rdx, r12
0x180040036  lea     rcx, [rbp+130h+var_148]
0x18004003a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004003f  nop
0x180040040  lea     rax, [rbp+130h+var_E0]
0x180040044  mov     [rbp+130h+var_160], rax
0x180040048  xorps   xmm0, xmm0
0x18004004b  movups  [rbp+130h+var_E0], xmm0
0x18004004f  mov     [rbp+130h+var_D0], r14
0x180040053  mov     [rbp+130h+var_C8], r14
0x180040057  mov     r8, rdi
0x18004005a  inc     r8
0x18004005d  cmp     [r13+r8*2+0], r14w
0x180040063  jnz     short loc_18004005A
0x180040065  mov     rdx, r13
0x180040068  lea     rcx, [rbp+130h+var_E0]
0x18004006c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180040071  nop
0x180040072  lea     rdx, [rbp+130h+var_188]
0x180040076  lea     rcx, [rbp+130h+var_1A8]
0x18004007a  call    ?InstanceName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName@UICloudStoreItemName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::InstanceName(void)
0x18004007f  nop
0x180040080  mov     rcx, [rax]
0x180040083  test    rcx, rcx
0x180040086  jz      short loc_18004008C
0x180040088  mov     rsi, [rcx+10h]
0x18004008c  xorps   xmm0, xmm0
0x18004008f  movups  [rbp+130h+var_C0], xmm0
0x180040093  mov     [rbp+130h+var_B0], r14
0x18004009a  mov     [rbp+130h+var_A8], r14
0x1800400a1  mov     r8, rdi
0x1800400a4  inc     r8
0x1800400a7  cmp     [rsi+r8*2], r14w
0x1800400ac  jnz     short loc_1800400A4
0x1800400ae  mov     rdx, rsi
0x1800400b1  lea     rcx, [rbp+130h+var_C0]
0x1800400b5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800400ba  nop
0x1800400bb  lea     r9, [rbp+130h+var_148]
0x1800400bf  lea     r8, [rbp+130h+var_E0]
0x1800400c3  lea     rdx, [rbp+130h+var_C0]
0x1800400c7  lea     rcx, [rbp+130h+var_A0]
0x1800400ce  call    ??0?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>(std::wstring,std::wstring,std::wstring)
0x1800400d3  mov     rbx, rax
0x1800400d6  mov     ecx, 0E8h; Size
0x1800400db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800400e0  mov     [rbp+130h+var_100], rax
0x1800400e4  lea     rcx, [rbp+130h+var_198]
0x1800400e8  mov     [rsp+230h+var_1C0], rcx
0x1800400ed  lea     rcx, [rbp+130h+var_1AC]
0x1800400f1  mov     [rsp+230h+var_1C8], rcx
0x1800400f6  lea     rcx, [rbp+130h+var_120]
0x1800400fa  mov     [rsp+230h+var_1D0], rcx
0x1800400ff  lea     rcx, [rbp+130h+var_1A0]
0x180040103  mov     [rsp+230h+var_1D8], rcx
0x180040108  lea     rcx, [rbp+130h+var_118]
0x18004010c  mov     [rsp+230h+var_1E0], rcx
0x180040111  lea     rcx, [rbp+130h+var_1AD]
0x180040115  mov     [rsp+230h+var_1E8], rcx
  ... truncated ...
```
