# wil::ProfileDataStore::MakeCloudStoreReferenceVector<Windows::Data::Security::Passkey::PasskeyItemPdr>(winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003ad68`
- end: `0x18003b2fd`
- name: `??$MakeCloudStoreReferenceVector@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$vector@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z`
- size: `1429`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x180025150`
- `0x180025aa0`
- `0x1800263f0`

## callees

- `0x180003080`
- `0x180003568`
- `0x180003c97`
- `0x180003cdf`
- `0x18000c95c`
- `0x18000ce74`
- `0x18000ee14`
- `0x18000f7fc`
- `0x18003ad68`
- `0x18004185c`
- `0x180042178`
- `0x180043f84`
- `0x180046a04`
- `0x180046ad0`
- `0x180048220`
- `0x1800484c0`
- `0x18004a6e8`
- `0x18004a788`
- `0x18004a7f4`
- `0x18004b060`
- `0x18004ccf0`
- `0x18004cf64`
- `0x18004dbd8`
- `0x18004ead4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b24a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b251`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b258`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b25f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b24a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b251`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b258`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b25f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003af39`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003af39`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_QWORD *__fastcall wil::ProfileDataStore::MakeCloudStoreReferenceVector<Windows::Data::Security::Passkey::PasskeyItemPdr>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  unsigned __int64 v6; // rsi
  __int64 v7; // r9
  __int64 v8; // rdi
  size_t v9; // rcx
  _QWORD *v10; // rbx
  void *v11; // rax
  int v12; // edi
  int v13; // r13d
  const WCHAR *v14; // rbx
  __int64 v15; // rax
  const WCHAR *v16; // rcx
  int v17; // esi
  void *v18; // rbx
  int v19; // ecx
  HANDLE ProcessHeap; // rax
  __int64 v21; // rax
  const WCHAR *v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rax
  const WCHAR *v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rax
  const WCHAR *v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  void *v37; // rbx
  int v38; // eax
  HANDLE v39; // rax
  void *v40; // rbx
  int v41; // eax
  HANDLE v42; // rax
  void *v43; // rbx
  int v44; // eax
  HANDLE v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // rax
  __int128 v50; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v51; // [rsp+40h] [rbp-C0h]
  __int64 v52; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v53; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v54; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v55; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+68h] [rbp-98h] BYREF
  __int64 v57; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v59; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v60[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v61; // [rsp+98h] [rbp-68h] BYREF
  int v62; // [rsp+A0h] [rbp-60h]
  __int128 v63; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v64; // [rsp+B8h] [rbp-48h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int128 v66; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v67; // [rsp+D8h] [rbp-28h]
  __int64 v68; // [rsp+E0h] [rbp-20h]
  __int128 v69; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v70; // [rsp+F8h] [rbp-8h]
  __int64 v71; // [rsp+100h] [rbp+0h]
  _QWORD *v72; // [rsp+108h] [rbp+8h]
  __int128 *v73; // [rsp+110h] [rbp+10h]
  __int128 *v74; // [rsp+118h] [rbp+18h]
  _BYTE v75[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v76[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v77[32]; // [rsp+170h] [rbp+70h] BYREF

  v72 = a2;
  winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::Items(
    a2,
    &v56);
  v50 = 0;
  v51 = 0;
  v53 = 0;
  if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v56, &v53) )
  {
    v6 = (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(&v56);
    v7 = v50;
    if ( v6 > 0xAAAAAAAAAAAAAAABuLL * ((v51 - (__int64)v50) >> 5) )
    {
      v8 = *((_QWORD *)&v50 + 1) - v50;
      v9 = 96 * v6;
      if ( 96 * v6 )
      {
        if ( v9 < 0x1000 )
        {
          v10 = operator new(v9);
        }
        else
        {
          if ( v9 + 39 < v9 )
            __scrt_throw_std_bad_array_new_length();
          v11 = operator new(v9 + 39);
          if ( !v11 )
            __fastfail(5u);
          v10 = (_QWORD *)(((unsigned __int64)v11 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v10 - 1) = v11;
        }
        v7 = v50;
      }
      else
      {
        v10 = 0;
      }
      std::_Uninitialized_move<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> *,std::allocator<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>>>(
        v7,
        *((_QWORD *)&v50 + 1),
        v10);
      std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>>::_Change_array(
        &v50,
        v10,
        0xAAAAAAAAAAAAAAABuLL * (v8 >> 5),
        v6);
    }
    winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::Items(
      a2,
      &v55);
    v61 = &v55;
    v12 = 0;
    v62 = 0;
    v13 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(&v55);
    while ( v12 != v13 )
    {
      winrt::impl::fast_iterator<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>>::operator*(
        &v61,
        &v57);
      winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::ItemName(
        &v57,
        &v52);
      if ( *(_QWORD *)(a3 + 24) <= 7u )
        v14 = (const WCHAR *)a3;
      else
        v14 = *(const WCHAR **)a3;
      v15 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::TypeName(
              &v52,
              &lpMem);
      if ( *(_QWORD *)v15 )
        v16 = *(const WCHAR **)(*(_QWORD *)v15 + 16LL);
      else
        v16 = &String1;
      v17 = CompareStringOrdinal(v16, -1, v14, -1, 1);
      v18 = lpMem;
      if ( lpMem )
      {
        v19 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
        if ( v19 )
        {
          if ( v19 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v18);
        }
        lpMem = 0;
      }
      if ( v17 == 2 )
      {
        winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::CollectionName(
          &v52,
          &v54);
        v73 = &v63;
        v21 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreCollectionName>::PartitionName(
                &v54,
                &v53);
        if ( *(_QWORD *)v21 )
          v22 = *(const WCHAR **)(*(_QWORD *)v21 + 16LL);
        else
          v22 = &String1;
        v63 = 0;
        v64 = 0;
        v65 = 0;
        v23 = -1;
        do
          ++v23;
        while ( v22[v23] );
        std::wstring::_Construct<1,unsigned short const *>(&v63, v22, v23);
        v74 = &v66;
        v24 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreCollectionName>::CustomName(
                &v54,
                v60);
        if ( *(_QWORD *)v24 )
          v25 = *(const WCHAR **)(*(_QWORD *)v24 + 16LL);
        else
          v25 = &String1;
        v66 = 0;
        v67 = 0;
        v68 = 0;
        v26 = -1;
        do
          ++v26;
        while ( v25[v26] );
        std::wstring::_Construct<1,unsigned short const *>(&v66, v25, v26);
        v27 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::InstanceName(
                &v52,
                &v59);
        if ( *(_QWORD *)v27 )
          v28 = *(const WCHAR **)(*(_QWORD *)v27 + 16LL);
        else
          v28 = &String1;
        v69 = 0;
        v70 = 0;
        v71 = 0;
        v29 = -1;
        do
          ++v29;
        while ( v28[v29] );
        std::wstring::_Construct<1,unsigned short const *>(&v69, v28, v29);
        v30 = wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>(
                v75,
                &v69,
                &v66,
                &v63);
        v31 = v30;
        v32 = *((_QWORD *)&v50 + 1);
        if ( *((_QWORD *)&v50 + 1) == v51 )
        {
          std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Emplace_reallocate<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>(
            &v50,
            *((_QWORD *)&v50 + 1),
            v30);
        }
        else
        {
          **((_OWORD **)&v50 + 1) = 0;
          *(_QWORD *)(v32 + 16) = 0;
          *(_QWORD *)(v32 + 24) = 0;
          *(_OWORD *)v32 = *(_OWORD *)v30;
          *(_OWORD *)(v32 + 16) = *(_OWORD *)(v30 + 16);
          *(_QWORD *)(v30 + 16) = 0;
          *(_QWORD *)(v30 + 24) = 7;
          *(_WORD *)v30 = 0;
          *(_OWORD *)(v32 + 32) = 0;
          *(_QWORD *)(v32 + 48) = 0;
          *(_QWORD *)(v32 + 56) = 0;
          *(_OWORD *)(v32 + 32) = *(_OWORD *)(v30 + 32);
          *(_OWORD *)(v32 + 48) = *(_OWORD *)(v30 + 48);
          *(_QWORD *)(v30 + 48) = 0;
          *(_QWORD *)(v30 + 56) = 7;
          *(_WORD *)(v30 + 32) = 0;
          *(_OWORD *)(v32 + 64) = 0;
          *(_QWORD *)(v32 + 80) = 0;
          *(_QWORD *)(v32 + 88) = 0;
          *(_OWORD *)(v32 + 64) = *(_OWORD *)(v30 + 64);
          *(_OWORD *)(v32 + 80) = *(_OWORD *)(v30 + 80);
          *(_QWORD *)(v30 + 80) = 0;
          *(_QWORD *)(v30 + 88) = 7;
          *(_WORD *)(v30 + 64) = 0;
          *((_QWORD *)&v50 + 1) += 96LL;
        }
        std::wstring::~wstring(v77, v32, v31);
        std::wstring::~wstring(v76, v33, v34);
        std::wstring::~wstring(v75, v35, v36);
        v37 = v59;
        if ( v59 )
        {
          v38 = _InterlockedDecrement((volatile signed __int32 *)v59 + 6);
          if ( v38 )
          {
            if ( v38 < 0 )
              abort();
          }
          else
          {
            v39 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v39, 0, v37);
          }
          v59 = 0;
        }
        v40 = v60[0];
        if ( v60[0] )
        {
          v41 = _InterlockedDecrement((volatile signed __int32 *)v60[0] + 6);
          if ( v41 )
          {
            if ( v41 < 0 )
              abort();
          }
          else
          {
            v42 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v42, 0, v40);
          }
          v60[0] = 0;
        }
        v43 = v53;
        if ( v53 )
        {
          v44 = _InterlockedDecrement((volatile signed __int32 *)v53 + 6);
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
          v53 = 0;
        }
        if ( v54 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v54);
      }
      if ( v52 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v52);
      if ( v57 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v57);
      v62 = ++v12;
    }
    if ( v55 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v55);
  }
  v46 = v51;
  v51 = 0;
  v47 = *((_QWORD *)&v50 + 1);
  v48 = v50;
  v50 = 0u;
  *a1 = v48;
  a1[1] = v47;
  a1[2] = v46;
  std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(&v50);
  if ( v56 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v56);
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  return a1;
}

```

## disassembly

```asm
0x18003ad68  mov     [rsp-8+arg_18], rbx
0x18003ad6d  push    rbp
0x18003ad6e  push    rsi
0x18003ad6f  push    rdi
0x18003ad70  push    r12
0x18003ad72  push    r13
0x18003ad74  push    r14
0x18003ad76  push    r15
0x18003ad78  lea     rbp, [rsp-0A0h]
0x18003ad80  sub     rsp, 1A0h
0x18003ad87  mov     rax, cs:__security_cookie
0x18003ad8e  xor     rax, rsp
0x18003ad91  mov     [rbp+0D0h+var_40], rax
0x18003ad98  mov     r12, r8
0x18003ad9b  mov     r15, rdx
0x18003ad9e  mov     r14, rcx
0x18003ada1  mov     [rsp+1D0h+var_180], rcx
0x18003ada6  mov     [rbp+0D0h+var_C8], rdx
0x18003adaa  xor     esi, esi
0x18003adac  lea     rdx, [rsp+1D0h+var_168]
0x18003adb1  mov     rcx, r15
0x18003adb4  call    ?Items@?$consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult@UIGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::Items(void)
0x18003adb9  nop
0x18003adba  xorps   xmm0, xmm0
0x18003adbd  movdqu  [rsp+1D0h+var_1A0], xmm0
0x18003adc3  mov     [rsp+1D0h+var_190], rsi
0x18003adc8  mov     [rsp+1D0h+var_180], rsi
0x18003adcd  lea     rdx, [rsp+1D0h+var_180]
0x18003add2  lea     rcx, [rsp+1D0h+var_168]
0x18003add7  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18003addc  test    al, al
0x18003adde  jnz     loc_18003B277
0x18003ade4  lea     rcx, [rsp+1D0h+var_168]
0x18003ade9  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UCloudStoreData@Cloud@Storage@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(void)
0x18003adee  mov     esi, eax
0x18003adf0  mov     rax, [rsp+1D0h+var_190]
0x18003adf5  mov     r9, qword ptr [rsp+1D0h+var_1A0]
0x18003adfa  sub     rax, r9
0x18003adfd  sar     rax, 5
0x18003ae01  mov     r13, 0AAAAAAAAAAAAAAABh
0x18003ae0b  imul    rax, r13
0x18003ae0f  cmp     rsi, rax
0x18003ae12  jbe     loc_18003AE9F
0x18003ae18  mov     rdi, qword ptr [rsp+1D0h+var_1A0+8]
0x18003ae1d  sub     rdi, r9
0x18003ae20  lea     rcx, [rsi+rsi*2]
0x18003ae24  shl     rcx, 5; Size
0x18003ae28  test    rcx, rcx
0x18003ae2b  jnz     short loc_18003AE31
0x18003ae2d  xor     ebx, ebx
0x18003ae2f  jmp     short loc_18003AE74
0x18003ae31  cmp     rcx, 1000h
0x18003ae38  jb      short loc_18003AE67
0x18003ae3a  lea     rax, [rcx+27h]
0x18003ae3e  cmp     rax, rcx
0x18003ae41  jbe     loc_18003B2F7
0x18003ae47  mov     rcx, rax; Size
0x18003ae4a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ae4f  test    rax, rax
0x18003ae52  jnz     short loc_18003AE59
0x18003ae54  lea     ecx, [rax+5]
0x18003ae57  int     29h; Win8: RtlFailFast(ecx)
0x18003ae59  lea     rbx, [rax+27h]
0x18003ae5d  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18003ae61  mov     [rbx-8], rax
0x18003ae65  jmp     short loc_18003AE6F
0x18003ae67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ae6c  mov     rbx, rax
0x18003ae6f  mov     r9, qword ptr [rsp+1D0h+var_1A0]
0x18003ae74  mov     r8, rbx
0x18003ae77  mov     rdx, qword ptr [rsp+1D0h+var_1A0+8]
0x18003ae7c  mov     rcx, r9
0x18003ae7f  call    ??$_Uninitialized_move@PEAV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@YAPEAV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@QEAV12@0PEAV12@AEAV?$allocator@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@0@@Z; std::_Uninitialized_move<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> *,std::allocator<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>>>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> * const,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> * const,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> *,std::allocator<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>> &)
0x18003ae84  sar     rdi, 5
0x18003ae88  imul    rdi, r13
0x18003ae8c  mov     r9, rsi
0x18003ae8f  mov     r8, rdi
0x18003ae92  mov     rdx, rbx
0x18003ae95  lea     rcx, [rsp+1D0h+var_1A0]
0x18003ae9a  call    ?_Change_array@?$vector@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAXQEAV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@_K1@Z; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>>::_Change_array(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> * const,unsigned __int64,unsigned __int64)
0x18003ae9f  lea     rdx, [rsp+1D0h+var_170]
0x18003aea4  mov     rcx, r15
0x18003aea7  call    ?Items@?$consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult@UIGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::Items(void)
0x18003aeac  nop
0x18003aead  lea     rax, [rsp+1D0h+var_170]
0x18003aeb2  mov     [rbp+0D0h+var_138], rax
0x18003aeb6  xor     esi, esi
0x18003aeb8  mov     edi, esi
0x18003aeba  mov     [rbp+0D0h+var_130], esi
0x18003aebd  lea     rcx, [rsp+1D0h+var_170]
0x18003aec2  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UCloudStoreData@Cloud@Storage@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(void)
0x18003aec7  mov     r13d, eax
0x18003aeca  cmp     edi, r13d
0x18003aecd  jz      loc_18003B266
0x18003aed3  lea     rdx, [rsp+1D0h+var_160]
0x18003aed8  lea     rcx, [rbp+0D0h+var_138]
0x18003aedc  call    ??D?$fast_iterator@U?$IVectorView@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@QEBA?AUCloudStoreData@Cloud@Storage@Internal@Windows@2@XZ; winrt::impl::fast_iterator<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>>::operator*(void)
0x18003aee1  nop
0x18003aee2  lea     rdx, [rsp+1D0h+var_188]
0x18003aee7  lea     rcx, [rsp+1D0h+var_160]
0x18003aeec  call    ?ItemName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreData@UICloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreData<winrt::Windows::Internal::Storage::Cloud::ICloudStoreData>::ItemName(void)
0x18003aef1  nop
0x18003aef2  cmp     qword ptr [r12+18h], 7
0x18003aef8  jbe     short loc_18003AF00
0x18003aefa  mov     rbx, [r12]
0x18003aefe  jmp     short loc_18003AF03
0x18003af00  mov     rbx, r12
0x18003af03  lea     rdx, [rsp+1D0h+lpMem]
0x18003af08  lea     rcx, [rsp+1D0h+var_188]
0x18003af0d  call    ?TypeName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName@UICloudStoreItemName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::TypeName(void)
0x18003af12  mov     rcx, [rax]
0x18003af15  test    rcx, rcx
0x18003af18  jz      short loc_18003AF20
0x18003af1a  mov     rcx, [rcx+10h]
0x18003af1e  jmp     short loc_18003AF27
0x18003af20  lea     rcx, String1; lpString1
0x18003af27  mov     [rsp+1D0h+bIgnoreCase], 1; bIgnoreCase
0x18003af2f  or      r9d, 0FFFFFFFFh; cchCount2
0x18003af33  mov     r8, rbx; lpString2
0x18003af36  or      edx, r9d; cchCount1
0x18003af39  call    cs:__imp_CompareStringOrdinal
0x18003af3f  mov     esi, eax
0x18003af41  mov     rbx, [rsp+1D0h+lpMem]
0x18003af46  test    rbx, rbx
0x18003af49  jz      short loc_18003AF7E
0x18003af4b  or      ecx, 0FFFFFFFFh
0x18003af4e  lock xadd [rbx+18h], ecx
0x18003af53  sub     ecx, 1
0x18003af56  jnz     short loc_18003AF6D
0x18003af58  nop
0x18003af59  call    WINRT_IMPL_GetProcessHeap
0x18003af5e  mov     rcx, rax; hHeap
0x18003af61  mov     r8, rbx; lpMem
0x18003af64  xor     edx, edx; dwFlags
0x18003af66  call    WINRT_IMPL_HeapFree
0x18003af6b  jmp     short loc_18003AF75
0x18003af6d  test    ecx, ecx
0x18003af6f  js      loc_18003B24A
0x18003af75  mov     [rsp+1D0h+lpMem], 0
0x18003af7e  cmp     esi, 2
0x18003af81  jnz     loc_18003B21B
0x18003af87  lea     rdx, [rsp+1D0h+var_178]
0x18003af8c  lea     rcx, [rsp+1D0h+var_188]
0x18003af91  call    ?CollectionName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName@UICloudStoreItemName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::CollectionName(void)
0x18003af96  nop
0x18003af97  lea     rax, [rbp+0D0h+var_128]
0x18003af9b  mov     [rbp+0D0h+var_C0], rax
0x18003af9f  lea     rdx, [rsp+1D0h+var_180]
0x18003afa4  lea     rcx, [rsp+1D0h+var_178]
0x18003afa9  call    ?PartitionName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName@UICloudStoreCollectionName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreCollectionName>::PartitionName(void)
0x18003afae  nop
0x18003afaf  mov     rdx, [rax]
0x18003afb2  xor     esi, esi
0x18003afb4  test    rdx, rdx
0x18003afb7  jz      short loc_18003AFBF
0x18003afb9  mov     rdx, [rdx+10h]
0x18003afbd  jmp     short loc_18003AFC6
0x18003afbf  lea     rdx, String1
0x18003afc6  xorps   xmm0, xmm0
0x18003afc9  movups  [rbp+0D0h+var_128], xmm0
0x18003afcd  mov     [rbp+0D0h+var_118], rsi
0x18003afd1  mov     [rbp+0D0h+var_110], rsi
0x18003afd5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003afd9  mov     r8, rbx
0x18003afdc  inc     r8
0x18003afdf  cmp     [rdx+r8*2], si
0x18003afe4  jnz     short loc_18003AFDC
0x18003afe6  lea     rcx, [rbp+0D0h+var_128]
0x18003afea  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003afef  nop
0x18003aff0  lea     rax, [rbp+0D0h+var_108]
0x18003aff4  mov     [rbp+0D0h+var_B8], rax
0x18003aff8  lea     rdx, [rbp+0D0h+var_148]
0x18003affc  lea     rcx, [rsp+1D0h+var_178]
0x18003b001  call    ?CustomName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName@UICloudStoreCollectionName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreCollectionName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreCollectionName>::CustomName(void)
0x18003b006  nop
0x18003b007  mov     rdx, [rax]
0x18003b00a  test    rdx, rdx
0x18003b00d  jz      short loc_18003B015
0x18003b00f  mov     rdx, [rdx+10h]
0x18003b013  jmp     short loc_18003B01C
0x18003b015  lea     rdx, String1
0x18003b01c  xorps   xmm0, xmm0
0x18003b01f  movups  [rbp+0D0h+var_108], xmm0
0x18003b023  mov     [rbp+0D0h+var_F8], rsi
0x18003b027  mov     [rbp+0D0h+var_F0], rsi
0x18003b02b  mov     r8, rbx
0x18003b02e  inc     r8
0x18003b031  cmp     [rdx+r8*2], si
0x18003b036  jnz     short loc_18003B02E
0x18003b038  lea     rcx, [rbp+0D0h+var_108]
0x18003b03c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003b041  nop
0x18003b042  lea     rdx, [rbp+0D0h+var_150]
0x18003b046  lea     rcx, [rsp+1D0h+var_188]
0x18003b04b  call    ?InstanceName@?$consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName@UICloudStoreItemName@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStoreItemName<winrt::Windows::Internal::Storage::Cloud::ICloudStoreItemName>::InstanceName(void)
0x18003b050  nop
0x18003b051  mov     rdx, [rax]
0x18003b054  test    rdx, rdx
0x18003b057  jz      short loc_18003B05F
0x18003b059  mov     rdx, [rdx+10h]
0x18003b05d  jmp     short loc_18003B066
0x18003b05f  lea     rdx, String1
0x18003b066  xorps   xmm0, xmm0
0x18003b069  movups  [rbp+0D0h+var_E8], xmm0
0x18003b06d  mov     [rbp+0D0h+var_D8], rsi
0x18003b071  mov     [rbp+0D0h+var_D0], rsi
0x18003b075  mov     r8, rbx
0x18003b078  inc     r8
0x18003b07b  cmp     [rdx+r8*2], si
0x18003b080  jnz     short loc_18003B078
0x18003b082  lea     rcx, [rbp+0D0h+var_E8]
0x18003b086  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003b08b  nop
0x18003b08c  lea     r9, [rbp+0D0h+var_128]
0x18003b090  lea     r8, [rbp+0D0h+var_108]
0x18003b094  lea     rdx, [rbp+0D0h+var_E8]
0x18003b098  lea     rcx, [rbp+0D0h+var_A0]
0x18003b09c  call    ??0?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>(std::wstring,std::wstring,std::wstring)
0x18003b0a1  mov     r8, rax
0x18003b0a4  mov     rdx, qword ptr [rsp+1D0h+var_1A0+8]
0x18003b0a9  cmp     rdx, [rsp+1D0h+var_190]
0x18003b0ae  jz      loc_18003B13E
0x18003b0b4  xorps   xmm0, xmm0
0x18003b0b7  movups  xmmword ptr [rdx], xmm0
0x18003b0ba  mov     [rdx+10h], rsi
0x18003b0be  mov     [rdx+18h], rsi
0x18003b0c2  movups  xmm0, xmmword ptr [rax]
0x18003b0c5  movups  xmmword ptr [rdx], xmm0
0x18003b0c8  movups  xmm1, xmmword ptr [rax+10h]
0x18003b0cc  movups  xmmword ptr [rdx+10h], xmm1
0x18003b0d0  mov     [rax+10h], rsi
0x18003b0d4  mov     ecx, 7
0x18003b0d9  mov     [rax+18h], rcx
0x18003b0dd  mov     [rax], si
0x18003b0e0  xorps   xmm0, xmm0
0x18003b0e3  movups  xmmword ptr [rdx+20h], xmm0
0x18003b0e7  mov     [rdx+30h], rsi
0x18003b0eb  mov     [rdx+38h], rsi
0x18003b0ef  movups  xmm0, xmmword ptr [rax+20h]
0x18003b0f3  movups  xmmword ptr [rdx+20h], xmm0
0x18003b0f7  movups  xmm1, xmmword ptr [rax+30h]
0x18003b0fb  movups  xmmword ptr [rdx+30h], xmm1
0x18003b0ff  mov     [rax+30h], rsi
0x18003b103  mov     [rax+38h], rcx
0x18003b107  mov     [rax+20h], si
0x18003b10b  xorps   xmm0, xmm0
0x18003b10e  movups  xmmword ptr [rdx+40h], xmm0
0x18003b112  mov     [rdx+50h], rsi
0x18003b116  mov     [rdx+58h], rsi
0x18003b11a  movups  xmm0, xmmword ptr [rax+40h]
0x18003b11e  movups  xmmword ptr [rdx+40h], xmm0
0x18003b122  movups  xmm1, xmmword ptr [rax+50h]
0x18003b126  movups  xmmword ptr [rdx+50h], xmm1
0x18003b12a  mov     [rax+50h], rsi
0x18003b12e  mov     [rax+58h], rcx
0x18003b132  mov     [rax+40h], si
0x18003b136  add     qword ptr [rsp+1D0h+var_1A0+8], 60h ; '`'
0x18003b13c  jmp     short loc_18003B149
0x18003b13e  lea     rcx, [rsp+1D0h+var_1A0]
0x18003b143  call    ??$_Emplace_reallocate@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@?$vector@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAPEAV?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Emplace_reallocate<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr> * const,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr> &&)
0x18003b148  nop
0x18003b149  lea     rcx, [rbp+0D0h+var_60]
0x18003b14d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b152  lea     rcx, [rbp+0D0h+var_80]
0x18003b156  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b15b  lea     rcx, [rbp+0D0h+var_A0]
0x18003b15f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b164  nop
0x18003b165  mov     rbx, [rbp+0D0h+var_150]
0x18003b169  test    rbx, rbx
0x18003b16c  jz      short loc_18003B19C
0x18003b16e  or      eax, 0FFFFFFFFh
0x18003b171  lock xadd [rbx+18h], eax
0x18003b176  sub     eax, 1
0x18003b179  jnz     short loc_18003B190
0x18003b17b  nop
0x18003b17c  call    WINRT_IMPL_GetProcessHeap
0x18003b181  mov     rcx, rax; hHeap
0x18003b184  mov     r8, rbx; lpMem
0x18003b187  xor     edx, edx; dwFlags
0x18003b189  call    WINRT_IMPL_HeapFree
0x18003b18e  jmp     short loc_18003B198
0x18003b190  test    eax, eax
0x18003b192  js      loc_18003B251
0x18003b198  mov     [rbp+0D0h+var_150], rsi
0x18003b19c  mov     rbx, [rbp+0D0h+var_148]
0x18003b1a0  test    rbx, rbx
0x18003b1a3  jz      short loc_18003B1D3
0x18003b1a5  or      eax, 0FFFFFFFFh
0x18003b1a8  lock xadd [rbx+18h], eax
0x18003b1ad  sub     eax, 1
0x18003b1b0  jnz     short loc_18003B1C7
0x18003b1b2  nop
0x18003b1b3  call    WINRT_IMPL_GetProcessHeap
0x18003b1b8  mov     rcx, rax; hHeap
0x18003b1bb  mov     r8, rbx; lpMem
0x18003b1be  xor     edx, edx; dwFlags
0x18003b1c0  call    WINRT_IMPL_HeapFree
0x18003b1c5  jmp     short loc_18003B1CF
  ... truncated ...
```
