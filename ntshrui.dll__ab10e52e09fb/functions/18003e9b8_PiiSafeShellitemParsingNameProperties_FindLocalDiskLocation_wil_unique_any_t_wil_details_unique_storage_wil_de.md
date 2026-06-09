# PiiSafeShellitemParsingNameProperties::FindLocalDiskLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,uchar &)

- ea: `0x18003e9b8`
- end: `0x18003edfa`
- name: `?FindLocalDiskLocation@PiiSafeShellitemParsingNameProperties@@AEAA?AW4ShellitemParsingNameRootLoc@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAE@Z`
- size: `1090`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049dcc`

## callees

- `0x1800215e8`
- `0x1800254e0`
- `0x180026370`
- `0x18003cc58`
- `0x18003e9b8`
- `0x180043b40`
- `0x180044574`
- `0x18004cc40`
- `0x18005137c`
- `0x180051430`
- `0x180052364`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18003ec50`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18003ec50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ec9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003edc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ec9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003edc0`
- `SHELL32!__imp_PathComparePaths` at `0x18003ec6b`
- `SHELL32!__imp_PathComparePaths` at `0x18003ed96`
- `SHELL32!__imp_PathComparePaths` at `0x18003ec6b`
- `SHELL32!__imp_PathComparePaths` at `0x18003ed96`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall PiiSafeShellitemParsingNameProperties::FindLocalDiskLocation(
        __int64 a1,
        const unsigned __int16 *const *a2,
        unsigned __int8 *a3)
{
  PiiSafeFolderList *v5; // rax
  const unsigned __int16 **v6; // rax
  PiiSafeShellitemParsingNameProperties *v7; // rcx
  const unsigned __int16 **v8; // rsi
  unsigned __int8 v9; // di
  char IsEnabled; // al
  char v11; // r12
  __int64 v12; // rdx
  struct _GUID *v13; // r8
  char v14; // r15
  bool v15; // r12
  const wchar_t **v16; // rsi
  const wchar_t **v17; // rsi
  char v19; // [rsp+30h] [rbp-D0h]
  LPCWSTR lpStringSource; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v21; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v22; // [rsp+48h] [rbp-B8h]
  const wchar_t *v23; // [rsp+50h] [rbp-B0h]
  __int16 v24; // [rsp+58h] [rbp-A8h]
  const wchar_t *v25; // [rsp+60h] [rbp-A0h]
  __int16 v26; // [rsp+68h] [rbp-98h]
  const wchar_t *v27; // [rsp+70h] [rbp-90h]
  __int16 v28; // [rsp+78h] [rbp-88h]
  const wchar_t *v29; // [rsp+80h] [rbp-80h]
  __int16 v30; // [rsp+88h] [rbp-78h]
  const wchar_t *v31; // [rsp+90h] [rbp-70h]
  __int16 v32; // [rsp+98h] [rbp-68h]
  const wchar_t *v33; // [rsp+A0h] [rbp-60h]
  __int16 v34; // [rsp+A8h] [rbp-58h]
  const wchar_t *v35; // [rsp+B0h] [rbp-50h]
  __int16 v36; // [rsp+B8h] [rbp-48h]
  const wchar_t *v37; // [rsp+C0h] [rbp-40h]
  __int16 v38; // [rsp+C8h] [rbp-38h]
  const wchar_t *v39; // [rsp+D0h] [rbp-30h]
  __int16 v40; // [rsp+D8h] [rbp-28h]
  const wchar_t *v41; // [rsp+E0h] [rbp-20h]
  __int16 v42; // [rsp+E8h] [rbp-18h]
  const wchar_t *v43; // [rsp+F0h] [rbp-10h]
  __int16 v44; // [rsp+F8h] [rbp-8h]
  const wchar_t *v45; // [rsp+100h] [rbp+0h]
  __int16 v46; // [rsp+108h] [rbp+8h]
  const wchar_t *v47; // [rsp+110h] [rbp+10h] BYREF
  __int16 v48; // [rsp+118h] [rbp+18h]
  const wchar_t *v49; // [rsp+120h] [rbp+20h]
  __int16 v50; // [rsp+128h] [rbp+28h]
  const wchar_t *v51; // [rsp+130h] [rbp+30h]
  __int16 v52; // [rsp+138h] [rbp+38h]
  const wchar_t *v53; // [rsp+140h] [rbp+40h]
  __int16 v54; // [rsp+148h] [rbp+48h]
  const wchar_t *v55; // [rsp+150h] [rbp+50h]
  __int16 v56; // [rsp+158h] [rbp+58h]
  const wchar_t *v57; // [rsp+160h] [rbp+60h]
  __int16 v58; // [rsp+168h] [rbp+68h]
  const wchar_t *v59; // [rsp+170h] [rbp+70h]
  __int16 v60; // [rsp+178h] [rbp+78h]
  const wchar_t *v61; // [rsp+180h] [rbp+80h]
  __int16 v62; // [rsp+188h] [rbp+88h]
  const wchar_t *v63; // [rsp+190h] [rbp+90h]
  __int16 v64; // [rsp+198h] [rbp+98h]
  const wchar_t *v65; // [rsp+1A0h] [rbp+A0h]
  __int16 v66; // [rsp+1A8h] [rbp+A8h]
  const wchar_t *v67; // [rsp+1B0h] [rbp+B0h]
  __int16 v68; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v69; // [rsp+1C0h] [rbp+C0h]
  __int16 v70; // [rsp+1C8h] [rbp+C8h]
  const wchar_t *v71; // [rsp+1D0h] [rbp+D0h]
  __int16 v72; // [rsp+1D8h] [rbp+D8h]
  const wchar_t *v73; // [rsp+1E0h] [rbp+E0h]
  __int16 v74; // [rsp+1E8h] [rbp+E8h]
  __int128 Buf1; // [rsp+1F0h] [rbp+F0h] BYREF

  *a3 = 0;
  v5 = (PiiSafeFolderList *)wil::details::static_lazy<PiiSafeFolderList>::get(
                              a1,
                              _lambda_8a5fbf835690efcf02570e7e9326c5fe_::_lambda_invoker_cdecl_);
  if ( !v5 )
    return (char)v5;
  v6 = (const unsigned __int16 **)PiiSafeFolderList::ReturnMatchingKnownFolder(v5, *a2);
  v8 = v6;
  if ( !v6 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58459845>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58459845>::GetImpl'::`2'::impl) )
      LOBYTE(v5) = PiiSafeShellitemParsingNameHelpers::GetDriveOrUncRootLocation(*a2);
    else
      LOBYTE(v5) = 1;
    return (char)v5;
  }
  v9 = PiiSafeShellitemParsingNameProperties::CalculatePathDepth(v7, *v6, 0);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl);
  v11 = 11;
  if ( *((_BYTE *)v8 + 8) != 11 && (!IsEnabled || *((_BYTE *)v8 + 8) != 16) )
  {
    *a3 = v9;
    LOBYTE(v5) = *((_BYTE *)v8 + 8);
    return (char)v5;
  }
  v12 = -1;
  do
    ++v12;
  while ( (*v8)[v12] );
  details::safemake_cotaskmem_string_nothrow(&lpStringSource, &(*a2)[v12]);
  if ( !lpStringSource )
  {
    *a3 = v9;
    goto LABEL_36;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
  {
    v21 = L"\\Desktop";
    v22 = 3073;
    v23 = L"\\Downloads";
    v24 = 3585;
    v25 = L"\\Documents";
    v26 = 3329;
    v27 = L"\\Pictures\\Camera Roll";
    v28 = 3842;
    v29 = L"\\Pictures\\Screenshots";
    v30 = 5122;
    v31 = L"\\Pictures";
    v32 = 4097;
    v33 = L"\\Videos";
    v34 = 4609;
    v35 = L"\\Music";
    v36 = 4353;
    v37 = L"\\3D Objects";
    v38 = 4865;
    v39 = L"\\Onedrive -";
    v40 = 17921;
    v41 = L"\\Google Drive";
    v42 = 23041;
    v43 = L"\\Dropbox";
    v44 = 20481;
    v45 = L"\\Sharepoint";
    v46 = 25601;
    v17 = &v21;
    while ( (unsigned int)PathComparePaths(*v17, lpStringSource) == 1 )
    {
      v17 += 2;
      if ( v17 == &v47 )
        goto LABEL_34;
    }
    v9 += *((_BYTE *)v17 + 8);
    v11 = *((_BYTE *)v17 + 9);
LABEL_34:
    *a3 = v9;
    CoTaskMemFree((LPVOID)lpStringSource);
LABEL_36:
    LOBYTE(v5) = v11;
    return (char)v5;
  }
  v47 = L"\\Desktop";
  v48 = 3073;
  v49 = L"\\Downloads";
  v50 = 3585;
  v51 = L"\\Documents";
  v52 = 3329;
  v53 = L"\\Pictures\\Camera Roll";
  v54 = 3842;
  v55 = L"\\Pictures\\Screenshots";
  v56 = 5122;
  v57 = L"\\Pictures\\iCloud Photos\\Photos";
  v58 = 26115;
  v59 = L"\\Pictures";
  v60 = 4097;
  v61 = L"\\Videos";
  v62 = 4609;
  v63 = L"\\Music";
  v64 = 4353;
  v65 = L"\\3D Objects";
  v66 = 4865;
  v67 = L"\\OneDrive -";
  v68 = 17921;
  v14 = 70;
  v69 = L"\\Dropbox";
  v70 = 20481;
  v71 = L"\\Sharepoint";
  v72 = 25601;
  v73 = L"\\iCloudDrive";
  v74 = 25857;
  v19 = *((_BYTE *)v8 + 8);
  Buf1 = 0;
  v15 = (int)PiiSafeShellitemParsingNameHelpers::GetKnownFolderIdFromPath(
               *(PiiSafeShellitemParsingNameHelpers **)a2,
               (const unsigned __int16 *)&Buf1,
               v13) >= 0
     && memcmp_0(&Buf1, &GUID_NULL, 0x10u);
  v16 = &v47;
  while ( *((_BYTE *)v16 + 9) != 70 )
  {
    if ( (unsigned int)PathComparePaths(*v16, lpStringSource) != 1 )
    {
      v14 = *((_BYTE *)v16 + 9);
      goto LABEL_27;
    }
LABEL_24:
    v16 += 2;
    if ( v16 == (const wchar_t **)&Buf1 )
    {
      v14 = v19;
      goto LABEL_28;
    }
  }
  if ( FindStringOrdinal(0x100000u, lpStringSource, -1, *v16, -1, 1) )
    goto LABEL_24;
  if ( v15 )
  {
    v9 += 2;
    v14 = 71;
    goto LABEL_28;
  }
LABEL_27:
  v9 += *((_BYTE *)v16 + 8);
LABEL_28:
  *a3 = v9;
  CoTaskMemFree((LPVOID)lpStringSource);
  LOBYTE(v5) = v14;
  return (char)v5;
}

```

## disassembly

```asm
0x18003e9b8  mov     [rsp-8+arg_0], rsi
0x18003e9bd  mov     [rsp-8+arg_18], rdi
0x18003e9c2  push    rbp
0x18003e9c3  push    r12
0x18003e9c5  push    r13
0x18003e9c7  push    r14
0x18003e9c9  push    r15
0x18003e9cb  lea     rbp, [rsp-110h]
0x18003e9d3  sub     rsp, 210h
0x18003e9da  mov     rax, cs:__security_cookie
0x18003e9e1  xor     rax, rsp
0x18003e9e4  mov     [rbp+130h+var_30], rax
0x18003e9eb  mov     r14, r8
0x18003e9ee  mov     r13, rdx
0x18003e9f1  xor     r15d, r15d
0x18003e9f4  mov     [r8], r15b
0x18003e9f7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8a5fbf835690efcf02570e7e9326c5fe_@@CA@XZ; _lambda_8a5fbf835690efcf02570e7e9326c5fe_::_lambda_invoker_cdecl_(void)
0x18003e9fe  call    ?get@?$static_lazy@VPiiSafeFolderList@@@details@wil@@QEAAPEAVPiiSafeFolderList@@P6AXXZ@Z; wil::details::static_lazy<PiiSafeFolderList>::get(void (*)(void))
0x18003ea03  test    rax, rax
0x18003ea06  jz      loc_18003EDCE
0x18003ea0c  mov     rdx, [r13+0]; unsigned __int16 *
0x18003ea10  mov     rcx, rax; this
0x18003ea13  call    ?ReturnMatchingKnownFolder@PiiSafeFolderList@@QEAAPEBVPiiSafeKnownFolder@@QEBG@Z; PiiSafeFolderList::ReturnMatchingKnownFolder(ushort const * const)
0x18003ea18  mov     rsi, rax
0x18003ea1b  test    rax, rax
0x18003ea1e  jnz     short loc_18003EA45
0x18003ea20  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58459845@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58459845@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58459845> `wil::Feature<__WilFeatureTraits_Feature_58459845>::GetImpl(void)'::`2'::impl
0x18003ea27  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58459845@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58459845>::__private_IsEnabled(void)
0x18003ea2c  test    al, al
0x18003ea2e  jz      short loc_18003EA3E
0x18003ea30  mov     rcx, [r13+0]
0x18003ea34  call    ?GetDriveOrUncRootLocation@PiiSafeShellitemParsingNameHelpers@@YA?AW4ShellitemParsingNameRootLoc@@PEBG@Z; PiiSafeShellitemParsingNameHelpers::GetDriveOrUncRootLocation(ushort const *)
0x18003ea39  jmp     loc_18003EDCE
0x18003ea3e  mov     al, 1
0x18003ea40  jmp     loc_18003EDCE
0x18003ea45  xor     r8d, r8d; bool
0x18003ea48  mov     rdx, [rax]; unsigned __int16 *
0x18003ea4b  call    ?CalculatePathDepth@PiiSafeShellitemParsingNameProperties@@AEAAEPEBG_N@Z; PiiSafeShellitemParsingNameProperties::CalculatePathDepth(ushort const *,bool)
0x18003ea50  mov     dil, al
0x18003ea53  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56275225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225> `wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl(void)'::`2'::impl
0x18003ea5a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(void)
0x18003ea5f  mov     r12b, 0Bh
0x18003ea62  cmp     [rsi+8], r12b
0x18003ea66  jz      short loc_18003EA7D
0x18003ea68  test    al, al
0x18003ea6a  jz      short loc_18003EA72
0x18003ea6c  cmp     byte ptr [rsi+8], 10h
0x18003ea70  jz      short loc_18003EA7D
0x18003ea72  mov     [r14], dil
0x18003ea75  mov     al, [rsi+8]
0x18003ea78  jmp     loc_18003EDCE
0x18003ea7d  mov     rax, [rsi]
0x18003ea80  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003ea84  inc     rdx
0x18003ea87  cmp     [rax+rdx*2], r15w
0x18003ea8c  jnz     short loc_18003EA84
0x18003ea8e  mov     rax, [r13+0]
0x18003ea92  lea     rdx, [rax+rdx*2]
0x18003ea96  lea     rcx, [rsp+230h+lpStringSource]
0x18003ea9b  call    details__safemake_cotaskmem_string_nothrow
0x18003eaa0  nop
0x18003eaa1  cmp     [rsp+230h+lpStringSource], r15
0x18003eaa6  jz      loc_18003EDC8
0x18003eaac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56275225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225> `wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl(void)'::`2'::impl
0x18003eab3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(void)
0x18003eab8  test    al, al
0x18003eaba  lea     rax, aDesktop; "\\Desktop"
0x18003eac1  jz      loc_18003ECAB
0x18003eac7  mov     [rbp+130h+var_120], rax
0x18003eacb  mov     [rbp+130h+var_118], 0C01h
0x18003ead1  lea     rax, aDownloads; "\\Downloads"
0x18003ead8  mov     [rbp+130h+var_110], rax
0x18003eadc  mov     [rbp+130h+var_108], 0E01h
0x18003eae2  lea     rax, aDocuments; "\\Documents"
0x18003eae9  mov     [rbp+130h+var_100], rax
0x18003eaed  mov     [rbp+130h+var_F8], 0D01h
0x18003eaf3  lea     rax, aPicturesCamera; "\\Pictures\\Camera Roll"
0x18003eafa  mov     [rbp+130h+var_F0], rax
0x18003eafe  mov     [rbp+130h+var_E8], 0F02h
0x18003eb04  lea     rax, aPicturesScreen; "\\Pictures\\Screenshots"
0x18003eb0b  mov     [rbp+130h+var_E0], rax
0x18003eb0f  mov     [rbp+130h+var_D8], 1402h
0x18003eb15  lea     rax, aPicturesIcloud; "\\Pictures\\iCloud Photos\\Photos"
0x18003eb1c  mov     [rbp+130h+var_D0], rax
0x18003eb20  mov     [rbp+130h+var_C8], 6603h
0x18003eb26  lea     rax, aPictures; "\\Pictures"
0x18003eb2d  mov     [rbp+130h+var_C0], rax
0x18003eb31  mov     [rbp+130h+var_B8], 1001h
0x18003eb37  lea     rax, aVideos; "\\Videos"
0x18003eb3e  mov     [rbp+130h+var_B0], rax
0x18003eb45  mov     [rbp+130h+var_A8], 1201h
0x18003eb4e  lea     rax, aMusic; "\\Music"
0x18003eb55  mov     [rbp+130h+var_A0], rax
0x18003eb5c  mov     [rbp+130h+var_98], 1101h
0x18003eb65  lea     rax, a3dObjects; "\\3D Objects"
0x18003eb6c  mov     [rbp+130h+var_90], rax
0x18003eb73  mov     [rbp+130h+var_88], 1301h
0x18003eb7c  lea     rax, aOnedrive_0; "\\OneDrive -"
0x18003eb83  mov     [rbp+130h+var_80], rax
0x18003eb8a  mov     [rbp+130h+var_78], 4601h
0x18003eb93  mov     r15b, 46h ; 'F'
0x18003eb96  lea     rax, aDropbox; "\\Dropbox"
0x18003eb9d  mov     [rbp+130h+var_70], rax
0x18003eba4  mov     [rbp+130h+var_68], 5001h
0x18003ebad  lea     rax, aSharepoint; "\\Sharepoint"
0x18003ebb4  mov     [rbp+130h+var_60], rax
0x18003ebbb  mov     [rbp+130h+var_58], 6401h
0x18003ebc4  lea     rax, aIclouddrive; "\\iCloudDrive"
0x18003ebcb  mov     [rbp+130h+var_50], rax
0x18003ebd2  mov     [rbp+130h+var_48], 6501h
0x18003ebdb  mov     al, [rsi+8]
0x18003ebde  mov     [rsp+230h+var_200], al
0x18003ebe2  xorps   xmm0, xmm0
0x18003ebe5  movups  [rbp+130h+Buf1], xmm0
0x18003ebec  lea     rdx, [rbp+130h+Buf1]; unsigned __int16 *
0x18003ebf3  mov     rcx, [r13+0]; this
0x18003ebf7  call    ?GetKnownFolderIdFromPath@PiiSafeShellitemParsingNameHelpers@@YAJPEBGPEAU_GUID@@@Z; PiiSafeShellitemParsingNameHelpers::GetKnownFolderIdFromPath(ushort const *,_GUID *)
0x18003ebfc  test    eax, eax
0x18003ebfe  js      short loc_18003EC22
0x18003ec00  mov     r8d, 10h; Size
0x18003ec06  lea     rdx, GUID_NULL; Buf2
0x18003ec0d  lea     rcx, [rbp+130h+Buf1]; Buf1
0x18003ec14  call    memcmp_0
0x18003ec19  test    eax, eax
0x18003ec1b  jz      short loc_18003EC22
0x18003ec1d  mov     r12b, 1
0x18003ec20  jmp     short loc_18003EC25
0x18003ec22  xor     r12b, r12b
0x18003ec25  lea     rsi, [rbp+130h+var_120]
0x18003ec29  mov     rdx, [rsp+230h+lpStringSource]; lpStringSource
0x18003ec2e  cmp     [rsi+9], r15b
0x18003ec32  jnz     short loc_18003EC68
0x18003ec34  mov     [rsp+230h+bIgnoreCase], 1; bIgnoreCase
0x18003ec3c  mov     [rsp+230h+cchValue], 0FFFFFFFFh; cchValue
0x18003ec44  mov     r9, [rsi]; lpStringValue
0x18003ec47  or      r8d, 0FFFFFFFFh; cchSource
0x18003ec4b  mov     ecx, 100000h; dwFindStringOrdinalFlags
0x18003ec50  call    cs:__imp_FindStringOrdinal
0x18003ec56  test    eax, eax
0x18003ec58  jnz     short loc_18003EC76
0x18003ec5a  test    r12b, r12b
0x18003ec5d  jz      short loc_18003EC91
0x18003ec5f  add     dil, 2
0x18003ec63  mov     r15b, 47h ; 'G'
0x18003ec66  jmp     short loc_18003EC95
0x18003ec68  mov     rcx, [rsi]
0x18003ec6b  call    cs:__imp_PathComparePaths
0x18003ec71  cmp     eax, 1
0x18003ec74  jnz     short loc_18003EC8D
0x18003ec76  add     rsi, 10h
0x18003ec7a  lea     rax, [rbp+130h+Buf1]
0x18003ec81  cmp     rsi, rax
0x18003ec84  jnz     short loc_18003EC29
0x18003ec86  mov     r15b, [rsp+230h+var_200]
0x18003ec8b  jmp     short loc_18003EC95
0x18003ec8d  mov     r15b, [rsi+9]
0x18003ec91  add     dil, [rsi+8]
0x18003ec95  mov     [r14], dil
0x18003ec98  mov     rcx, [rsp+230h+lpStringSource]; pv
0x18003ec9d  call    cs:__imp_CoTaskMemFree
0x18003eca3  mov     al, r15b
0x18003eca6  jmp     loc_18003EDCE
0x18003ecab  mov     [rsp+230h+var_1F0], rax
0x18003ecb0  mov     [rsp+230h+var_1E8], 0C01h
0x18003ecb7  lea     rax, aDownloads; "\\Downloads"
0x18003ecbe  mov     [rsp+230h+var_1E0], rax
0x18003ecc3  mov     [rsp+230h+var_1D8], 0E01h
0x18003ecca  lea     rax, aDocuments; "\\Documents"
0x18003ecd1  mov     [rsp+230h+var_1D0], rax
0x18003ecd6  mov     [rsp+230h+var_1C8], 0D01h
0x18003ecdd  lea     rax, aPicturesCamera; "\\Pictures\\Camera Roll"
0x18003ece4  mov     [rsp+230h+var_1C0], rax
0x18003ece9  mov     [rsp+230h+var_1B8], 0F02h
0x18003ecf0  lea     rax, aPicturesScreen; "\\Pictures\\Screenshots"
0x18003ecf7  mov     [rbp+130h+var_1B0], rax
0x18003ecfb  mov     [rbp+130h+var_1A8], 1402h
0x18003ed01  lea     rax, aPictures; "\\Pictures"
0x18003ed08  mov     [rbp+130h+var_1A0], rax
0x18003ed0c  mov     [rbp+130h+var_198], 1001h
0x18003ed12  lea     rax, aVideos; "\\Videos"
0x18003ed19  mov     [rbp+130h+var_190], rax
0x18003ed1d  mov     [rbp+130h+var_188], 1201h
0x18003ed23  lea     rax, aMusic; "\\Music"
0x18003ed2a  mov     [rbp+130h+var_180], rax
0x18003ed2e  mov     [rbp+130h+var_178], 1101h
0x18003ed34  lea     rax, a3dObjects; "\\3D Objects"
0x18003ed3b  mov     [rbp+130h+var_170], rax
0x18003ed3f  mov     [rbp+130h+var_168], 1301h
0x18003ed45  lea     rax, aOnedrive; "\\Onedrive -"
0x18003ed4c  mov     [rbp+130h+var_160], rax
0x18003ed50  mov     [rbp+130h+var_158], 4601h
0x18003ed56  lea     rax, aGoogleDrive; "\\Google Drive"
0x18003ed5d  mov     [rbp+130h+var_150], rax
0x18003ed61  mov     [rbp+130h+var_148], 5A01h
0x18003ed67  lea     rax, aDropbox; "\\Dropbox"
0x18003ed6e  mov     [rbp+130h+var_140], rax
0x18003ed72  mov     [rbp+130h+var_138], 5001h
0x18003ed78  lea     rax, aSharepoint; "\\Sharepoint"
0x18003ed7f  mov     [rbp+130h+var_130], rax
0x18003ed83  mov     [rbp+130h+var_128], 6401h
0x18003ed89  lea     rsi, [rsp+230h+var_1F0]
0x18003ed8e  mov     rdx, [rsp+230h+lpStringSource]
0x18003ed93  mov     rcx, [rsi]
0x18003ed96  call    cs:__imp_PathComparePaths
0x18003ed9c  cmp     eax, 1
0x18003ed9f  jnz     short loc_18003EDB0
0x18003eda1  add     rsi, 10h
0x18003eda5  lea     rax, [rbp+130h+var_120]
0x18003eda9  cmp     rsi, rax
0x18003edac  jnz     short loc_18003ED8E
0x18003edae  jmp     short loc_18003EDB8
0x18003edb0  add     dil, [rsi+8]
0x18003edb4  mov     r12b, [rsi+9]
0x18003edb8  mov     [r14], dil
0x18003edbb  mov     rcx, [rsp+230h+lpStringSource]; pv
0x18003edc0  call    cs:__imp_CoTaskMemFree
0x18003edc6  jmp     short loc_18003EDCB
0x18003edc8  mov     [r14], dil
0x18003edcb  mov     al, r12b
0x18003edce  mov     rcx, [rbp+130h+var_30]
0x18003edd5  xor     rcx, rsp; StackCookie
0x18003edd8  call    __security_check_cookie
0x18003eddd  lea     r11, [rsp+230h+var_20]
0x18003ede5  mov     rsi, [r11+30h]
0x18003ede9  mov     rdi, [r11+48h]
0x18003eded  mov     rsp, r11
0x18003edf0  pop     r15
0x18003edf2  pop     r14
0x18003edf4  pop     r13
0x18003edf6  pop     r12
0x18003edf8  pop     rbp
0x18003edf9  retn
```
