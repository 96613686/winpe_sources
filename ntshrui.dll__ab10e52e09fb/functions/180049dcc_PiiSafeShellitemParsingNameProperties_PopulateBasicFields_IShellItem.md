# PiiSafeShellitemParsingNameProperties::PopulateBasicFields(IShellItem *)

- ea: `0x180049dcc`
- end: `0x18004a4a0`
- name: `?PopulateBasicFields@PiiSafeShellitemParsingNameProperties@@AEAAXPEAUIShellItem@@@Z`
- size: `1748`
- prototype: `void(PiiSafeShellitemParsingNameProperties *__hidden this, struct IShellItem *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180021548`

## callees

- `0x180008900`
- `0x180015ad0`
- `0x180016004`
- `0x180019670`
- `0x180019f78`
- `0x1800215e8`
- `0x180021660`
- `0x180024e44`
- `0x1800361f8`
- `0x1800388bc`
- `0x18003a4cc`
- `0x18003b680`
- `0x18003cc58`
- `0x18003e9b8`
- `0x1800440ec`
- `0x18004415c`
- `0x180044400`
- `0x180044dcc`
- `0x180045134`
- `0x180047a28`
- `0x1800491f0`
- `0x180049dcc`
- `0x18004aad8`
- `0x18004f14c`
- `0x18004f6cc`
- `0x180050fc8`
- `0x18005137c`
- `0x1800514a8`
- `0x180052cc4`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180049ff6`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180049ff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a028`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a09a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a12d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a1a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a1b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a2a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a2b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a30d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a31c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a3a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a028`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a09a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a12d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a1a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a1b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a2a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a2b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a30d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a31c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a3a1`
- `SHELL32!SHGetIDListFromObject` at `0x18004a3d1`
- `SHELL32!SHGetIDListFromObject` at `0x18004a3d1`
- `SHELL32!__imp_ILIsEqual` at `0x18004a438`
- `SHELL32!__imp_ILIsEqual` at `0x18004a456`
- `SHELL32!__imp_ILIsEqual` at `0x18004a438`
- `SHELL32!__imp_ILIsEqual` at `0x18004a456`

## string_xrefs

- `0x180049e59`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x18004a3e2`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall PiiSafeShellitemParsingNameProperties::PopulateBasicFields(
        PiiSafeShellitemParsingNameProperties *this,
        struct IShellItem *a2)
{
  const unsigned __int16 **v4; // r12
  _WORD *v5; // rax
  unsigned __int8 v6; // al
  int v7; // eax
  bool v8; // r13
  char v9; // al
  char v10; // bl
  PiiSafeShellitemParsingNameProperties *v11; // rcx
  __int64 v12; // rdi
  char v13; // bl
  unsigned __int8 LocalDiskLocation; // r15
  unsigned __int8 v15; // al
  PWSTR v16; // rbx
  size_t v17; // rdx
  __int64 RelativeToRootPath; // rax
  __int64 *v19; // rdi
  __int64 v20; // rcx
  __int64 v21; // rax
  const unsigned __int16 *InstanceOfChar; // rax
  __int64 v23; // rax
  _QWORD *v24; // rdi
  __int64 v25; // rax
  const unsigned __int16 *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r8
  char v30; // di
  double v31; // xmm0_8
  __int64 v32; // r8
  char v33; // al
  HRESULT v34; // eax
  __int64 v35; // rcx
  unsigned __int8 RegistryRootLocation; // bl
  const ITEMIDLIST *HomePidl_NoThrow; // rbx
  const ITEMIDLIST *GalleryPidl_NoThrow; // rdi
  __int64 v39; // [rsp+20h] [rbp-40h] BYREF
  PWSTR pszPath; // [rsp+28h] [rbp-38h] BYREF
  LPVOID v41; // [rsp+30h] [rbp-30h] BYREF
  LPVOID v42; // [rsp+38h] [rbp-28h] BYREF
  LPITEMIDLIST ppidl[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v44; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  LPVOID pv; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v47; // [rsp+B0h] [rbp+50h] BYREF
  LPVOID v48; // [rsp+B8h] [rbp+58h] BYREF

  if ( !*((_BYTE *)this + 116) )
  {
    v4 = (const unsigned __int16 **)((char *)this + 88);
    v5 = (_WORD *)*((_QWORD *)this + 11);
    if ( v5 )
    {
      if ( *v5 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 28) - 100) <= 1 )
          v6 = -56;
        else
          v6 = PiiSafeShellitemParsingNameProperties::PopulateShellitemParsingNameRootType();
        *(_QWORD *)this |= (unsigned __int64)v6 << 52;
        v47 = 0;
        v7 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, unsigned int *))a2->lpVtbl->GetAttributes)(
               a2,
               2126589960,
               &v47);
        if ( v7 >= 0 )
        {
          LODWORD(pv) = 0;
          v8 = 1;
          if ( ((int (__fastcall *)(struct IShellItem *, __int64, LPVOID *))a2->lpVtbl->GetAttributes)(
                 a2,
                 541065216,
                 &pv) >= 0
            && ((unsigned int)pv & 0x20000000) != 0
            && ((unsigned int)pv & 0x400000) == 0 )
          {
            LODWORD(pv) = 0;
            if ( ((int (__fastcall *)(struct IShellItem *, __int64, LPVOID *))a2->lpVtbl->GetAttributes)(
                   a2,
                   541065216,
                   &pv) < 0
              || ((unsigned int)pv & 0x20400000) != 0x20400000 )
            {
              v8 = 0;
            }
          }
          v39 = 0;
          if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v39, a2) >= 0 )
          {
            LODWORD(pv) = 0;
            *(_OWORD *)ppidl = PKEY_Home_GraphFileType;
            LODWORD(v44) = 19;
            if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(&v39, ppidl, &pv) < 0
              || (v9 = 1, (unsigned int)((_DWORD)pv - 1) > 1) )
            {
              v9 = 0;
            }
            *((_BYTE *)this + 81) = v9;
          }
          if ( *((_DWORD *)this + 28) == 10 || (v10 = 0, *((_DWORD *)this + 28) == 102) )
            v10 = 1;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60851339>::GetImpl'::`2'::impl)
            && *((_DWORD *)this + 28) == 101 )
          {
            v10 = 1;
          }
          if ( v10 )
          {
            v12 = -1;
            do
              ++v12;
            while ( (*v4)[v12] );
            v13 = 0;
            LOBYTE(pv) = 0;
            if ( *((_DWORD *)this + 28) == 102 )
            {
              LocalDiskLocation = 119;
            }
            else
            {
              LocalDiskLocation = PiiSafeShellitemParsingNameProperties::FindLocalDiskLocation(v11, v4, &pv);
              v13 = (char)pv;
            }
            v15 = PiiSafeShellitemParsingNameProperties::CalculatePathDepth(v11, *v4, v8);
            *((_QWORD *)this + 1) |= (unsigned __int64)v47 << 32;
            LODWORD(pv) = (unsigned __int8)(v15 - v13);
            *(_QWORD *)this |= v15 | ((unsigned __int64)LocalDiskLocation << 40) | (unsigned int)((_DWORD)pv << 8);
            wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &pszPath,
              *v4,
              -1);
            v16 = pszPath;
            if ( v8 )
            {
              v17 = -1;
              do
                ++v17;
              while ( pszPath[v17] );
              PathCchRemoveFileSpec(pszPath, v17);
            }
            RelativeToRootPath = PiiSafeShellitemParsingNameProperties::GetRelativeToRootPath(
                                   &pv,
                                   &pszPath,
                                   (unsigned int)v12,
                                   (unsigned int)pv);
            v19 = (__int64 *)((char *)this + 96);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              (char *)this + 96,
              RelativeToRootPath);
            if ( pv )
              CoTaskMemFree(pv);
            v20 = *v19;
            if ( *v19 )
            {
              v21 = -1;
              do
                ++v21;
              while ( *(_WORD *)(v20 + 2 * v21) );
              *(_QWORD *)this |= (unsigned __int16)v21 << 16;
              *((_QWORD *)this + 9) |= PiiSafeShellitemParsingNameProperties::GetKeywords(v20, (char *)this + 96) << 32;
            }
            if ( v8 )
            {
              InstanceOfChar = PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(*v4, 0x5Cu);
              v23 = details::safemake_cotaskmem_string_nothrow(&pv, InstanceOfChar);
              v24 = (_QWORD *)((char *)this + 104);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                (char *)this + 104,
                v23);
              if ( pv )
                CoTaskMemFree(pv);
              if ( *v24 )
              {
                v25 = -1;
                do
                  ++v25;
                while ( *(_WORD *)(*v24 + 2 * v25) );
                *((_QWORD *)this + 1) |= (unsigned __int16)v25;
                v26 = PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(*v4, 0x2Eu);
                if ( v26 )
                {
                  ppidl[0] = 0;
                  ppidl[1] = 0;
                  v44 = 0;
                  v28 = -1;
                  do
                    ++v28;
                  while ( v26[v28] );
                  if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                              ppidl,
                              L"%lu:%.4s",
                              v28,
                              v26) >= 0 )
                  {
                    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      &pv,
                      ppidl[0],
                      -1);
                    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                      (char *)this + 16,
                      &pv);
                    if ( pv )
                      CoTaskMemFree(pv);
                  }
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(ppidl);
                }
                *((_QWORD *)this + 9) |= PiiSafeShellitemParsingNameProperties::GetKeywords(v27, (char *)this + 104);
              }
              else
              {
                PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(&v48, a2, &PKEY_FileExtension);
                if ( v48 )
                {
                  pv = 0;
                  v29 = -1;
                  do
                    ++v29;
                  while ( *((_WORD *)v48 + v29 + 1) );
                  if ( (int)wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                              &pv,
                              L"%lu:%.4s") >= 0 )
                    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                      (char *)this + 16,
                      &pv);
                  if ( pv )
                    CoTaskMemFree(pv);
                  if ( v48 )
                    CoTaskMemFree(v48);
                }
              }
              v30 = 0;
              LOBYTE(pv) = 0;
              v48 = 0;
              if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v48, a2) >= 0 )
              {
                *(_OWORD *)ppidl = PKEY_Home_Recommended;
                LODWORD(v44) = 20;
                wil::PropertyStoreHelperBase<IPropertyStore>::GetBoolean<_tagpropertykey>(&v48, ppidl, &pv);
                v30 = (char)pv;
              }
              Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v48);
              if ( v30 )
              {
                PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(
                  &v41,
                  a2,
                  PKEY_MsGraph_RecommendationReason);
                if ( v41 )
                {
                  v48 = 0;
                  ppidl[0] = (LPITEMIDLIST)v41;
                  ppidl[1] = (LPITEMIDLIST)&v48;
                  v31 = (int)_lambda_c3ddcf9081ed21b3602a2c72fc5f6745_::operator()(ppidl) < 0
                      ? DOUBLE_N1_0
                      : *(double *)&v48;
                  if ( v31 > -1.0 )
                    *((_DWORD *)this + 21) = (int)v31;
                }
                PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(&pv, a2, &PKEY_Home_DriveType);
                if ( pv )
                {
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                    (char *)this + 24,
                    &pv);
                  if ( pv )
                    CoTaskMemFree(pv);
                }
                if ( v41 )
                  CoTaskMemFree(v41);
              }
              PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(
                &v42,
                a2,
                PKEY_MsGraph_GraphFileType);
              if ( v42 )
              {
                pv = 0;
                v32 = -1;
                do
                  ++v32;
                while ( *((_WORD *)v42 + v32) );
                if ( (int)wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                            &pv,
                            L"%lu:%.50s") >= 0 )
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                    (char *)this + 32,
                    &pv);
                if ( pv )
                  CoTaskMemFree(pv);
                if ( v42 )
                  CoTaskMemFree(v42);
              }
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 40);
            *((_QWORD *)this + 6) = -1;
            *((_QWORD *)this + 7) = -1;
            SyncProviderTelemetryHelpers::GetProviderNameAndInfoFlags(
              a2,
              (unsigned __int16 **)this + 5,
              (PiiSafeShellitemParsingNameProperties *)((char *)this + 64));
            LODWORD(pv) = 0;
            if ( (int)IShellItem_GetFilePlaceholderStatus(a2, (ULONG *)&pv) < 0
              || ((unsigned __int8)pv & 0xA) != 8
              || (LODWORD(pv) = 0,
                  ((int (__fastcall *)(struct IShellItem *, __int64, LPVOID *))a2->lpVtbl->GetAttributes)(
                    a2,
                    541065216,
                    &pv) < 0)
              || (v33 = 1, (_DWORD)pv != 0x20000000) )
            {
              v33 = 0;
            }
            *((_BYTE *)this + 80) = v33;
            if ( v16 )
              CoTaskMemFree(v16);
          }
          else if ( *((_DWORD *)this + 28) == 11 )
          {
            pv = 0;
            ppidl[0] = (LPITEMIDLIST)&pv;
            ppidl[1] = 0;
            LOBYTE(v44) = 1;
            v34 = SHGetIDListFromObject((IUnknown *)a2, &ppidl[1]);
            if ( v34 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x4AC,
                (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
                (const char *)(unsigned int)v34,
                v39);
            wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(ppidl);
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
            {
              RegistryRootLocation = PiiSafeShellitemParsingNameProperties::TryGetRegistryRootLocation(v35, a2, &pv);
            }
            else
            {
              HomePidl_NoThrow = (const ITEMIDLIST *)GetHomePidl_NoThrow();
              GalleryPidl_NoThrow = (const ITEMIDLIST *)GetGalleryPidl_NoThrow();
              if ( HomePidl_NoThrow && ILIsEqual(HomePidl_NoThrow, (LPCITEMIDLIST)pv) )
              {
                RegistryRootLocation = 120;
              }
              else
              {
                RegistryRootLocation = 0;
                if ( GalleryPidl_NoThrow && ILIsEqual(GalleryPidl_NoThrow, (LPCITEMIDLIST)pv) )
                  RegistryRootLocation = 121;
              }
            }
            *(_QWORD *)this |= (unsigned __int64)RegistryRootLocation << 40;
            wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
              &pv,
              0);
          }
          *((_BYTE *)this + 116) = 1;
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v39);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x41A,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
            (const char *)(unsigned int)v7,
            v39);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180049dcc  mov     [rsp-38h+arg_8], rbx
0x180049dd1  push    rbp
0x180049dd2  push    rsi
0x180049dd3  push    rdi
0x180049dd4  push    r12
0x180049dd6  push    r13
0x180049dd8  push    r14
0x180049dda  push    r15
0x180049ddc  mov     rbp, rsp
0x180049ddf  sub     rsp, 60h
0x180049de3  mov     r14, rdx
0x180049de6  mov     rsi, rcx
0x180049de9  xor     r15d, r15d
0x180049dec  cmp     [rcx+74h], r15b
0x180049df0  jnz     loc_18004A488
0x180049df6  lea     r12, [rcx+58h]
0x180049dfa  mov     rax, [r12]
0x180049dfe  test    rax, rax
0x180049e01  jz      loc_18004A488
0x180049e07  cmp     [rax], r15w
0x180049e0b  jz      loc_18004A488
0x180049e11  mov     eax, [rcx+70h]
0x180049e14  sub     eax, 64h ; 'd'
0x180049e17  lea     edi, [r15+1]
0x180049e1b  cmp     eax, edi
0x180049e1d  jbe     short loc_180049E26
0x180049e1f  call    ?PopulateShellitemParsingNameRootType@PiiSafeShellitemParsingNameProperties@@AEAA?AW4ShellitemParsingNameRootType@@XZ; PiiSafeShellitemParsingNameProperties::PopulateShellitemParsingNameRootType(void)
0x180049e24  jmp     short loc_180049E28
0x180049e26  mov     al, 0C8h
0x180049e28  movzx   eax, al
0x180049e2b  shl     rax, 34h
0x180049e2f  or      [rsi], rax
0x180049e32  mov     [rbp+arg_10], r15d
0x180049e36  mov     rax, [r14]
0x180049e39  lea     r8, [rbp+arg_10]
0x180049e3d  mov     edx, 7EC13008h
0x180049e42  mov     rcx, r14
0x180049e45  mov     rax, [rax+30h]
0x180049e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e4e  mov     rcx, [rbp+38h]; this
0x180049e52  test    eax, eax
0x180049e54  jns     short loc_180049E6F
0x180049e56  mov     r9d, eax; char *
0x180049e59  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180049e60  mov     edx, 41Ah; void *
0x180049e65  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049e6a  jmp     loc_18004A488
0x180049e6f  mov     dword ptr [rbp+pv], r15d
0x180049e73  mov     rax, [r14]
0x180049e76  lea     r8, [rbp+pv]
0x180049e7a  mov     ebx, 20400000h
0x180049e7f  mov     edx, ebx
0x180049e81  mov     rcx, r14
0x180049e84  mov     rax, [rax+30h]
0x180049e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e8d  test    eax, eax
0x180049e8f  js      short loc_180049ECE
0x180049e91  test    dword ptr [rbp+pv], 20000000h
0x180049e98  jz      short loc_180049ECE
0x180049e9a  test    dword ptr [rbp+pv], 400000h
0x180049ea1  jnz     short loc_180049ECE
0x180049ea3  mov     dword ptr [rbp+pv], r15d
0x180049ea7  mov     rax, [r14]
0x180049eaa  lea     r8, [rbp+pv]
0x180049eae  mov     edx, ebx
0x180049eb0  mov     rcx, r14
0x180049eb3  mov     rax, [rax+30h]
0x180049eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ebc  test    eax, eax
0x180049ebe  js      short loc_180049EC9
0x180049ec0  mov     eax, dword ptr [rbp+pv]
0x180049ec3  and     eax, ebx
0x180049ec5  cmp     eax, ebx
0x180049ec7  jz      short loc_180049ECE
0x180049ec9  mov     r13b, r15b
0x180049ecc  jmp     short loc_180049ED1
0x180049ece  mov     r13b, dil
0x180049ed1  mov     [rbp+var_40], r15
0x180049ed5  mov     rdx, r14
0x180049ed8  lea     rcx, [rbp+var_40]
0x180049edc  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x180049ee1  test    eax, eax
0x180049ee3  js      short loc_180049F24
0x180049ee5  mov     dword ptr [rbp+pv], r15d
0x180049ee9  movups  xmm0, cs:PKEY_Home_GraphFileType
0x180049ef0  movaps  xmmword ptr [rbp+ppidl], xmm0
0x180049ef4  mov     eax, cs:dword_18007E7D8
0x180049efa  mov     dword ptr [rbp+var_10], eax
0x180049efd  lea     r8, [rbp+pv]
0x180049f01  lea     rdx, [rbp+ppidl]
0x180049f05  lea     rcx, [rbp+var_40]
0x180049f09  call    ??$GetUInt32@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAK@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x180049f0e  test    eax, eax
0x180049f10  js      short loc_180049F1E
0x180049f12  mov     eax, dword ptr [rbp+pv]
0x180049f15  dec     eax
0x180049f17  cmp     eax, edi
0x180049f19  mov     al, dil
0x180049f1c  jbe     short loc_180049F21
0x180049f1e  mov     al, r15b
0x180049f21  mov     [rsi+51h], al
0x180049f24  cmp     dword ptr [rsi+70h], 0Ah
0x180049f28  jz      short loc_180049F33
0x180049f2a  cmp     dword ptr [rsi+70h], 66h ; 'f'
0x180049f2e  mov     bl, r15b
0x180049f31  jnz     short loc_180049F36
0x180049f33  mov     bl, dil
0x180049f36  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60851339@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339> `wil::Feature<__WilFeatureTraits_Feature_60851339>::GetImpl(void)'::`2'::impl
0x180049f3d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339>::__private_IsEnabled(void)
0x180049f42  test    al, al
0x180049f44  jz      short loc_180049F50
0x180049f46  movzx   ebx, bl
0x180049f49  cmp     dword ptr [rsi+70h], 65h ; 'e'
0x180049f4d  cmovz   ebx, edi
0x180049f50  test    bl, bl
0x180049f52  jz      loc_18004A3AC
0x180049f58  mov     rax, [r12]
0x180049f5c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180049f60  inc     rdi
0x180049f63  cmp     [rax+rdi*2], r15w
0x180049f68  jnz     short loc_180049F60
0x180049f6a  mov     bl, r15b
0x180049f6d  mov     byte ptr [rbp+pv], bl
0x180049f70  cmp     dword ptr [rsi+70h], 66h ; 'f'
0x180049f74  jnz     short loc_180049F7B
0x180049f76  mov     r15b, 77h ; 'w'
0x180049f79  jmp     short loc_180049F8D
0x180049f7b  lea     r8, [rbp+pv]
0x180049f7f  mov     rdx, r12
0x180049f82  call    ?FindLocalDiskLocation@PiiSafeShellitemParsingNameProperties@@AEAA?AW4ShellitemParsingNameRootLoc@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAE@Z; PiiSafeShellitemParsingNameProperties::FindLocalDiskLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,uchar &)
0x180049f87  mov     r15b, al
0x180049f8a  mov     bl, byte ptr [rbp+pv]
0x180049f8d  mov     r8b, r13b; bool
0x180049f90  mov     rdx, [r12]; unsigned __int16 *
0x180049f94  call    ?CalculatePathDepth@PiiSafeShellitemParsingNameProperties@@AEAAEPEBG_N@Z; PiiSafeShellitemParsingNameProperties::CalculatePathDepth(ushort const *,bool)
0x180049f99  mov     ecx, [rbp+arg_10]
0x180049f9c  shl     rcx, 20h
0x180049fa0  or      [rsi+8], rcx
0x180049fa4  mov     cl, al
0x180049fa6  sub     cl, bl
0x180049fa8  movzx   ecx, cl
0x180049fab  mov     dword ptr [rbp+pv], ecx
0x180049fae  shl     ecx, 8
0x180049fb1  mov     edx, ecx
0x180049fb3  movzx   ecx, r15b
0x180049fb7  shl     rcx, 28h
0x180049fbb  or      rdx, rcx
0x180049fbe  movzx   eax, al
0x180049fc1  or      rdx, rax
0x180049fc4  or      [rsi], rdx
0x180049fc7  or      r8, 0FFFFFFFFFFFFFFFFh
0x180049fcb  mov     rdx, [r12]
0x180049fcf  lea     rcx, [rbp+pszPath]
0x180049fd3  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180049fd8  nop
0x180049fd9  mov     rbx, [rbp+pszPath]
0x180049fdd  xor     r15d, r15d
0x180049fe0  test    r13b, r13b
0x180049fe3  jz      short loc_180049FFC
0x180049fe5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180049fe9  inc     rdx; cchPath
0x180049fec  cmp     [rbx+rdx*2], r15w
0x180049ff1  jnz     short loc_180049FE9
0x180049ff3  mov     rcx, rbx; pszPath
0x180049ff6  call    cs:__imp_PathCchRemoveFileSpec
0x180049ffc  mov     r8d, edi
0x180049fff  mov     r9d, dword ptr [rbp+pv]
0x18004a003  lea     rdx, [rbp+pszPath]
0x18004a007  lea     rcx, [rbp+pv]
0x18004a00b  call    ?GetRelativeToRootPath@PiiSafeShellitemParsingNameProperties@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV23@KK@Z; PiiSafeShellitemParsingNameProperties::GetRelativeToRootPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,ulong,ulong)
0x18004a010  lea     rdi, [rsi+60h]
0x18004a014  mov     rdx, rax
0x18004a017  mov     rcx, rdi
0x18004a01a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004a01f  mov     rcx, [rbp+pv]; pv
0x18004a023  test    rcx, rcx
0x18004a026  jz      short loc_18004A02E
0x18004a028  call    cs:__imp_CoTaskMemFree
0x18004a02e  mov     rcx, [rdi]
0x18004a031  test    rcx, rcx
0x18004a034  jz      short loc_18004A05F
0x18004a036  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a03a  inc     rax
0x18004a03d  cmp     [rcx+rax*2], r15w
0x18004a042  jnz     short loc_18004A03A
0x18004a044  movzx   eax, ax
0x18004a047  shl     eax, 10h
0x18004a04a  cdqe
0x18004a04c  or      [rsi], rax
0x18004a04f  mov     rdx, rdi
0x18004a052  call    ?GetKeywords@PiiSafeShellitemParsingNameProperties@@AEAA_KAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PiiSafeShellitemParsingNameProperties::GetKeywords(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x18004a057  shl     rax, 20h
0x18004a05b  or      [rsi+48h], rax
0x18004a05f  test    r13b, r13b
0x18004a062  jz      loc_18004A322
0x18004a068  mov     edx, 5Ch ; '\'; unsigned __int16
0x18004a06d  mov     rcx, [r12]; unsigned __int16 *
0x18004a071  call    ?LastInstanceOfChar@PiiSafeShellitemParsingNameProperties@@CAPEBGPEBGG@Z; PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(ushort const *,ushort)
0x18004a076  mov     rdx, rax
0x18004a079  lea     rcx, [rbp+pv]
0x18004a07d  call    details__safemake_cotaskmem_string_nothrow
0x18004a082  lea     rdi, [rsi+68h]
0x18004a086  mov     rdx, rax
0x18004a089  mov     rcx, rdi
0x18004a08c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004a091  mov     rcx, [rbp+pv]; pv
0x18004a095  test    rcx, rcx
0x18004a098  jz      short loc_18004A0A0
0x18004a09a  call    cs:__imp_CoTaskMemFree
0x18004a0a0  mov     rdx, [rdi]
0x18004a0a3  test    rdx, rdx
0x18004a0a6  jz      loc_18004A14A
0x18004a0ac  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004a0b0  mov     rax, r13
0x18004a0b3  inc     rax
0x18004a0b6  cmp     [rdx+rax*2], r15w
0x18004a0bb  jnz     short loc_18004A0B3
0x18004a0bd  movzx   eax, ax
0x18004a0c0  or      [rsi+8], rax
0x18004a0c4  mov     edx, 2Eh ; '.'; unsigned __int16
0x18004a0c9  mov     rcx, [r12]; unsigned __int16 *
0x18004a0cd  call    ?LastInstanceOfChar@PiiSafeShellitemParsingNameProperties@@CAPEBGPEBGG@Z; PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(ushort const *,ushort)
0x18004a0d2  test    rax, rax
0x18004a0d5  jz      short loc_18004A13C
0x18004a0d7  mov     [rbp+ppidl], r15
0x18004a0db  mov     [rbp+ppidl+8], r15
0x18004a0df  mov     [rbp+var_10], r15
0x18004a0e3  mov     r8, r13
0x18004a0e6  inc     r8
0x18004a0e9  cmp     [rax+r8*2], r15w
0x18004a0ee  jnz     short loc_18004A0E6
0x18004a0f0  mov     r9, rax
0x18004a0f3  lea     rdx, aLu4s; "%lu:%.4s"
0x18004a0fa  lea     rcx, [rbp+ppidl]
0x18004a0fe  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18004a103  test    eax, eax
0x18004a105  js      short loc_18004A133
0x18004a107  mov     r8, r13
0x18004a10a  mov     rdx, [rbp+ppidl]
0x18004a10e  lea     rcx, [rbp+pv]
0x18004a112  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004a117  lea     rcx, [rsi+10h]
0x18004a11b  lea     rdx, [rbp+pv]
0x18004a11f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004a124  mov     rcx, [rbp+pv]; pv
0x18004a128  test    rcx, rcx
0x18004a12b  jz      short loc_18004A133
0x18004a12d  call    cs:__imp_CoTaskMemFree
0x18004a133  lea     rcx, [rbp+ppidl]
0x18004a137  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004a13c  mov     rdx, rdi
0x18004a13f  call    ?GetKeywords@PiiSafeShellitemParsingNameProperties@@AEAA_KAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PiiSafeShellitemParsingNameProperties::GetKeywords(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x18004a144  or      [rsi+48h], rax
0x18004a148  jmp     short loc_18004A1BE
0x18004a14a  lea     r8, PKEY_FileExtension
0x18004a151  mov     rdx, r14
0x18004a154  lea     rcx, [rbp+arg_18]
0x18004a158  call    ?TryGetStringPropertyFromShellItem@PiiSafeShellitemParsingNameProperties@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIShellItem@@AEBU_tagpropertykey@@@Z; PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(IShellItem *,_tagpropertykey const &)
0x18004a15d  mov     rax, [rbp+arg_18]
0x18004a161  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004a165  test    rax, rax
0x18004a168  jz      short loc_18004A1BE
0x18004a16a  lea     r9, [rax+2]
0x18004a16e  mov     [rbp+pv], r15
0x18004a172  mov     r8, r13
0x18004a175  inc     r8
0x18004a178  cmp     [r9+r8*2], r15w
0x18004a17d  jnz     short loc_18004A175
0x18004a17f  lea     rdx, aLu4s; "%lu:%.4s"
0x18004a186  lea     rcx, [rbp+pv]
0x18004a18a  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004a18f  test    eax, eax
0x18004a191  js      short loc_18004A1A0
0x18004a193  lea     rcx, [rsi+10h]
0x18004a197  lea     rdx, [rbp+pv]
0x18004a19b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004a1a0  mov     rcx, [rbp+pv]; pv
0x18004a1a4  test    rcx, rcx
0x18004a1a7  jz      short loc_18004A1AF
0x18004a1a9  call    cs:__imp_CoTaskMemFree
0x18004a1af  mov     rcx, [rbp+arg_18]; pv
0x18004a1b3  test    rcx, rcx
0x18004a1b6  jz      short loc_18004A1BE
0x18004a1b8  call    cs:__imp_CoTaskMemFree
0x18004a1be  mov     dil, r15b
0x18004a1c1  mov     byte ptr [rbp+pv], r15b
0x18004a1c5  mov     [rbp+arg_18], r15
0x18004a1c9  mov     rdx, r14
0x18004a1cc  lea     rcx, [rbp+arg_18]
0x18004a1d0  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x18004a1d5  test    eax, eax
0x18004a1d7  js      short loc_18004A202
0x18004a1d9  movups  xmm0, cs:PKEY_Home_Recommended
0x18004a1e0  movaps  xmmword ptr [rbp+ppidl], xmm0
0x18004a1e4  mov     eax, cs:dword_180082D10
0x18004a1ea  mov     dword ptr [rbp+var_10], eax
0x18004a1ed  lea     r8, [rbp+pv]
0x18004a1f1  lea     rdx, [rbp+ppidl]
0x18004a1f5  lea     rcx, [rbp+arg_18]
0x18004a1f9  call    ??$GetBoolean@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEA_N@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetBoolean<_tagpropertykey>(_tagpropertykey,bool *)
  ... truncated ...
```
