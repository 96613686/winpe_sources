# TsClientOptionalComponent::GetOptionalComponentInfoForMstsc(uint,bool,TsClientOptionalComponent::OptionalComponentInfo &)

- ea: `0x14010cb10`
- end: `0x14010cf5c`
- name: `?GetOptionalComponentInfoForMstsc@TsClientOptionalComponent@@YAJI_NAEAUOptionalComponentInfo@1@@Z`
- size: `1100`
- prototype: `int(TsClientOptionalComponent *__hidden this, unsigned int, bool, struct TsClientOptionalComponent::OptionalComponentInfo *)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400651f0`

## callees

- `0x140004703`
- `0x140008a34`
- `0x1400626ec`
- `0x140062730`
- `0x14006589c`
- `0x14010c958`
- `0x14010cac8`
- `0x14010caec`
- `0x14010cb10`
- `0x14010cf64`
- `0x14010cfac`
- `0x14010cfe8`
- `0x140113390`

## import_xrefs

- `KERNEL32!FindNextFileW` at `0x14010cde2`
- `KERNEL32!FindNextFileW` at `0x14010cde2`
- `KERNEL32!FindFirstFileW` at `0x14010cd15`
- `KERNEL32!FindFirstFileW` at `0x14010cd15`
- `KERNEL32!GetLastError` at `0x14010cdf0`
- `KERNEL32!GetLastError` at `0x14010cdf0`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x14010ccc5`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x14010ccc5`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x14010cd40`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x14010cd40`
- `SHELL32!SHGetKnownFolderPath` at `0x14010cc74`
- `SHELL32!SHGetKnownFolderPath` at `0x14010cc74`
- `DismApi!DismGetFeatureInfo` at `0x14010cb87`
- `DismApi!DismGetFeatureInfo` at `0x14010cd91`
- `DismApi!DismGetFeatureInfo` at `0x14010cb87`
- `DismApi!DismGetFeatureInfo` at `0x14010cd91`

## string_xrefs

- `0x14010ccbe`: `Servicing\Packages\Microsoft-Windows-TS-OptionalComponents-Package~*~~*.mum`
- `0x14010cb94`: `clientcore\termsrv\client\clientlibs\mstscuninstalllib\tsclientoptionalcomponent.cpp`
- `0x14010cd4d`: `PathCchRemoveExtension failed`
- `0x14010cc26`: `StringCchCopyW(FeatureName) failed`
- `0x14010ce70`: `StringCchCopyW(FeatureName) failed`
- `0x14010cbf8`: `StringCchCopyW(PackageName) failed`
- `0x14010ce2c`: `StringCchCopyW(PackageName) failed`
- `0x14010ccd8`: `PathAllocCombine(packageFilePattern) failed`
- `0x14010cc87`: `SHGetKnownFolderPath(FOLDERID_Windows) failed`

## pseudocode

```c
__int64 __fastcall TsClientOptionalComponent::GetOptionalComponentInfoForMstsc(
        TsClientOptionalComponent *this,
        __int64 a2,
        unsigned __int16 *a3,
        struct TsClientOptionalComponent::OptionalComponentInfo *a4)
{
  unsigned int v5; // r15d
  __int64 v6; // rax
  const char *FeatureInfo; // rbx
  HRESULT LastErrorMsg; // ebx
  unsigned __int64 v9; // r11
  const char *v10; // rax
  __int64 v11; // rdx
  char *FirstFileW; // rbx
  char v13; // r14
  char v14; // di
  unsigned int v15; // eax
  __int64 v16; // rax
  unsigned int v17; // eax
  const char *v18; // r9
  __int64 v19; // rdx
  unsigned __int64 v20; // r11
  const char *v21; // rax
  __int64 v22; // rdx
  char *v24; // [rsp+20h] [rbp-E0h]
  const char *v25; // [rsp+28h] [rbp-D8h]
  const char *v26; // [rsp+28h] [rbp-D8h]
  PWSTR ppszPath; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPathOut; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  char *v30; // [rsp+48h] [rbp-B8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v5 = (unsigned int)this;
  memset_0(a3, 0, 0x414u);
  v29 = 0;
  v6 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>>::put(&v29);
  FeatureInfo = (const char *)(unsigned int)DismGetFeatureInfo(
                                              v5,
                                              L"Microsoft-RemoteDesktopConnection",
                                              L"@Foundation",
                                              1,
                                              v6);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x20,
    (unsigned int)"clientcore\\termsrv\\client\\clientlibs\\mstscuninstalllib\\tsclientoptionalcomponent.cpp",
    FeatureInfo,
    (int)"DismGetFeatureInfo(@Foundation) failed",
    v25);
  if ( (int)FeatureInfo >= 0 )
  {
    if ( *(_DWORD *)(v29 + 8) == 3 )
    {
LABEL_33:
      LastErrorMsg = -2147467259;
      goto LABEL_42;
    }
    if ( *(_DWORD *)(v29 + 8) != 4 )
    {
LABEL_35:
      LastErrorMsg = -2147021879;
      goto LABEL_42;
    }
    LastErrorMsg = StringCchCopyW(a3, 0x105u, L"@Foundation");
    if ( LastErrorMsg >= 0 )
    {
      LastErrorMsg = StringCchCopyW(a3 + 261, v9, L"Microsoft-RemoteDesktopConnection");
      if ( LastErrorMsg >= 0 )
      {
LABEL_31:
        LastErrorMsg = 0;
        goto LABEL_42;
      }
      v10 = "StringCchCopyW(FeatureName) failed";
      v11 = 39;
    }
    else
    {
      v10 = "StringCchCopyW(PackageName) failed";
      v11 = 38;
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v11,
      (unsigned int)"clientcore\\termsrv\\client\\clientlibs\\mstscuninstalllib\\tsclientoptionalcomponent.cpp",
      (const char *)(unsigned int)LastErrorMsg,
      (int)v10,
      v26);
LABEL_42:
    wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>(&v29);
    return (unsigned int)LastErrorMsg;
  }
  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  LastErrorMsg = SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &ppszPath);
  if ( LastErrorMsg < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x35,
      (unsigned int)"clientcore\\termsrv\\client\\clientlibs\\mstscuninstalllib\\tsclientoptionalcomponent.cpp",
      (const char *)(unsigned int)LastErrorMsg,
      (int)"SHGetKnownFolderPath(FOLDERID_Windows) failed",
      v26);
LABEL_41:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
    goto LABEL_42;
  }
  ppszPathOut = 0;
  LastErrorMsg = PathAllocCombine(
                   ppszPath,
                   L"Servicing\\Packages\\Microsoft-Windows-TS-OptionalComponents-Package~*~~*.mum",
                   0,
                   &ppszPathOut);
  if ( LastErrorMsg < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x38,
      (unsigned int)"clientcore\\termsrv\\client\\clientlibs\\mstscuninstalllib\\tsclientoptionalcomponent.cpp",
      (const char *)(unsigned int)LastErrorMsg,
      (int)"PathAllocCombine(packageFilePattern) failed",
      v26);
LABEL_40:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    goto LABEL_41;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  v30 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v18 = "FindFirstFileW failed";
    v19 = 60;
LABEL_38:
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)v19,
                     (unsigned int)"clientcore\\termsrv\\client\\clientlibs\\mstscuninstalllib\\tsclientoptionalcomponent.cpp",
                     v18,
                     v24);
LABEL_39:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v30);
    goto LABEL_40;
  }
  v13 = 0;
  v14 = 0;
  do
  {
    v15 = PathCchRemoveExtension(FindFileData.cFileName, 0x104u);
    if ( wil::details::in1diag3::Log_IfFailedMsg(
           retaddr,
           (void *)0x40,
           (unsigned int)"clientcore\\termsrv\\client\\clientlibs\\mstscuninstalllib\\tsclientoptionalcomponent.cpp",
           (const char *)v15,
           (int)"PathCchRemoveExtension failed",
           v26) >= 0 )
    {
      v16 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>>::put(&v29);
      v17 = DismGetFeatureInfo(v5, L"Microsoft-RemoteDesktopConnection", FindFileData.cFileName, 1, v16);
      if ( wil::details::in1diag3::Log_IfFailedMsg(
             retaddr,
             (void *)0x45,
             (unsigned int)"clientcore\\termsrv\\client\\clientlibs\\mstscuninstalllib\\tsclientoptionalcomponent.cpp",
             (const char *)v17,
             (int)"DismGetFeatureInfo failed",
             v26) >= 0 )
      {
        if ( v14 || *(_DWORD *)(v29 + 8) == 3 )
          v14 = 1;
        if ( *(_DWORD *)(v29 + 8) == 4 )
        {
          LastErrorMsg = StringCchCopyW(a3, 0x105u, FindFileData.cFileName);
          if ( LastErrorMsg < 0 )
          {
            v21 = "StringCchCopyW(PackageName) failed";
            v22 = 79;
LABEL_27:
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)v22,
              (unsigned int)"clientcore\\termsrv\\client\\clientlibs\\mstscuninstalllib\\tsclientoptionalcomponent.cpp",
              (const char *)(unsigned int)LastErrorMsg,
              (int)v21,
              v26);
            goto LABEL_39;
          }
          LastErrorMsg = StringCchCopyW(a3 + 261, v20, L"Microsoft-RemoteDesktopConnection");
          if ( LastErrorMsg < 0 )
          {
            v21 = "StringCchCopyW(FeatureName) failed";
            v22 = 80;
            goto LABEL_27;
          }
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v30);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
          goto LABEL_31;
        }
        v13 = 1;
      }
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  if ( GetLastError() != 18 )
  {
    v18 = "FindNextFileW failed";
    v19 = 86;
    goto LABEL_38;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v30);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
  if ( v14 )
    goto LABEL_33;
  if ( v13 )
    goto LABEL_35;
  wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>(&v29);
  return 2147942402LL;
}

```

## disassembly

```asm
0x14010cb10  mov     [rsp-8+arg_8], rbx
0x14010cb15  mov     [rsp-8+arg_18], rsi
0x14010cb1a  push    rbp
0x14010cb1b  push    rdi
0x14010cb1c  push    r13
0x14010cb1e  push    r14
0x14010cb20  push    r15
0x14010cb22  lea     rbp, [rsp-1B0h]
0x14010cb2a  sub     rsp, 2B0h
0x14010cb31  mov     rax, cs:__security_cookie
0x14010cb38  xor     rax, rsp
0x14010cb3b  mov     [rbp+1D0h+var_30], rax
0x14010cb42  mov     rsi, r8
0x14010cb45  mov     r15d, ecx
0x14010cb48  mov     rcx, rsi; void *
0x14010cb4b  xor     edx, edx; Val
0x14010cb4d  mov     r8d, 414h; Size
0x14010cb53  call    memset_0
0x14010cb58  lea     rcx, [rsp+2D0h+var_290]
0x14010cb5d  mov     [rsp+2D0h+var_290], 0
0x14010cb66  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_DismFeatureInfo@@$$A6AJPEAX@Z$1?DismDelete@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAU_DismFeatureInfo@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>>::put(void)
0x14010cb6b  mov     r9d, 1
0x14010cb71  mov     [rsp+2D0h+var_2B0], rax
0x14010cb76  lea     r8, aFoundation; "@Foundation"
0x14010cb7d  mov     ecx, r15d
0x14010cb80  lea     rdx, aMicrosoftRemot; "Microsoft-RemoteDesktopConnection"
0x14010cb87  call    cs:__imp_DismGetFeatureInfo
0x14010cb8d  mov     rcx, [rbp+1D8h]; this
0x14010cb94  lea     r13, aClientcoreTerm_0; "clientcore\\termsrv\\client\\clientlibs"...
0x14010cb9b  mov     ebx, eax
0x14010cb9d  mov     r8, r13; unsigned int
0x14010cba0  lea     rax, aDismgetfeature_1; "DismGetFeatureInfo(@Foundation) failed"
0x14010cba7  mov     r9d, ebx; char *
0x14010cbaa  mov     edx, 20h ; ' '; void *
0x14010cbaf  mov     [rsp+2D0h+var_2B0], rax; char *
0x14010cbb4  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14010cbb9  test    ebx, ebx
0x14010cbbb  js      loc_14010CC4E
0x14010cbc1  mov     rax, [rsp+2D0h+var_290]
0x14010cbc6  cmp     dword ptr [rax+8], 3
0x14010cbca  jz      loc_14010CEC6
0x14010cbd0  cmp     dword ptr [rax+8], 4
0x14010cbd4  jnz     loc_14010CED2
0x14010cbda  mov     r11d, 105h
0x14010cbe0  lea     r8, aFoundation; "@Foundation"
0x14010cbe7  mov     edx, r11d; unsigned __int64
0x14010cbea  mov     rcx, rsi; unsigned __int16 *
0x14010cbed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14010cbf2  mov     ebx, eax
0x14010cbf4  test    eax, eax
0x14010cbf6  jns     short loc_14010CC06
0x14010cbf8  lea     rax, aStringcchcopyw_0; "StringCchCopyW(PackageName) failed"
0x14010cbff  mov     edx, 26h ; '&'
0x14010cc04  jmp     short loc_14010CC32
0x14010cc06  lea     rcx, [rsi+20Ah]; unsigned __int16 *
0x14010cc0d  mov     rdx, r11; unsigned __int64
0x14010cc10  lea     r8, aMicrosoftRemot; "Microsoft-RemoteDesktopConnection"
0x14010cc17  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14010cc1c  mov     ebx, eax
0x14010cc1e  test    eax, eax
0x14010cc20  jns     loc_14010CE9C
0x14010cc26  lea     rax, aStringcchcopyw_1; "StringCchCopyW(FeatureName) failed"
0x14010cc2d  mov     edx, 27h ; '''; void *
0x14010cc32  mov     rcx, [rbp+1D8h]; this
0x14010cc39  mov     r8, r13; unsigned int
0x14010cc3c  mov     r9d, ebx; char *
0x14010cc3f  mov     [rsp+2D0h+var_2B0], rax; int
0x14010cc44  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14010cc49  jmp     loc_14010CF25
0x14010cc4e  xor     edx, edx
0x14010cc50  mov     [rsp+2D0h+ppszPath], 0
0x14010cc59  lea     rcx, [rsp+2D0h+ppszPath]
0x14010cc5e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14010cc63  lea     r9, [rsp+2D0h+ppszPath]; ppszPath
0x14010cc68  xor     r8d, r8d; hToken
0x14010cc6b  xor     edx, edx; dwFlags
0x14010cc6d  lea     rcx, FOLDERID_Windows; rfid
0x14010cc74  call    cs:__imp_SHGetKnownFolderPath
0x14010cc7a  mov     ebx, eax
0x14010cc7c  test    eax, eax
0x14010cc7e  jns     short loc_14010CCA8
0x14010cc80  mov     rcx, [rbp+1D8h]; this
0x14010cc87  lea     rax, aShgetknownfold_1; "SHGetKnownFolderPath(FOLDERID_Windows) "...
0x14010cc8e  mov     r9d, ebx; char *
0x14010cc91  mov     [rsp+2D0h+var_2B0], rax; int
0x14010cc96  mov     r8, r13; unsigned int
0x14010cc99  mov     edx, 35h ; '5'; void *
0x14010cc9e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14010cca3  jmp     loc_14010CF1B
0x14010cca8  mov     rcx, [rsp+2D0h+ppszPath]; pszPathIn
0x14010ccad  lea     r9, [rsp+2D0h+ppszPathOut]; ppszPathOut
0x14010ccb2  xor     r8d, r8d; dwFlags
0x14010ccb5  mov     [rsp+2D0h+ppszPathOut], 0
0x14010ccbe  lea     rdx, aServicingPacka; "Servicing\\Packages\\Microsoft-Windows-"...
0x14010ccc5  call    cs:__imp_PathAllocCombine
0x14010cccb  mov     ebx, eax
0x14010cccd  test    eax, eax
0x14010cccf  jns     short loc_14010CCF9
0x14010ccd1  mov     rcx, [rbp+1D8h]; this
0x14010ccd8  lea     rax, aPathalloccombi; "PathAllocCombine(packageFilePattern) fa"...
0x14010ccdf  mov     r9d, ebx; char *
0x14010cce2  mov     [rsp+2D0h+var_2B0], rax; int
0x14010cce7  mov     r8, r13; unsigned int
0x14010ccea  mov     edx, 38h ; '8'; void *
0x14010ccef  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14010ccf4  jmp     loc_14010CF11
0x14010ccf9  xor     edx, edx; Val
0x14010ccfb  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x14010cd00  mov     r8d, 250h; Size
0x14010cd06  call    memset_0
0x14010cd0b  mov     rcx, [rsp+2D0h+ppszPathOut]; lpFileName
0x14010cd10  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x14010cd15  call    cs:__imp_FindFirstFileW
0x14010cd1b  mov     rbx, rax
0x14010cd1e  mov     [rsp+2D0h+var_288], rax
0x14010cd23  dec     rax
0x14010cd26  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14010cd2a  ja      loc_14010CEEA
0x14010cd30  xor     r14b, r14b
0x14010cd33  xor     dil, dil
0x14010cd36  mov     edx, 104h; cchPath
0x14010cd3b  lea     rcx, [rsp+2D0h+FindFileData.cFileName]; pszPath
0x14010cd40  call    cs:__imp_PathCchRemoveExtension
0x14010cd46  mov     rcx, [rbp+1D8h]; this
0x14010cd4d  lea     rdx, aPathcchremovee; "PathCchRemoveExtension failed"
0x14010cd54  mov     [rsp+2D0h+var_2B0], rdx; int
0x14010cd59  mov     r9d, eax; char *
0x14010cd5c  mov     edx, 40h ; '@'; void *
0x14010cd61  mov     r8, r13; unsigned int
0x14010cd64  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14010cd69  test    eax, eax
0x14010cd6b  js      short loc_14010CDDA
0x14010cd6d  lea     rcx, [rsp+2D0h+var_290]
0x14010cd72  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_DismFeatureInfo@@$$A6AJPEAX@Z$1?DismDelete@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAU_DismFeatureInfo@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>>::put(void)
0x14010cd77  mov     r9d, 1
0x14010cd7d  mov     [rsp+2D0h+var_2B0], rax
0x14010cd82  lea     r8, [rsp+2D0h+FindFileData.cFileName]
0x14010cd87  mov     ecx, r15d
0x14010cd8a  lea     rdx, aMicrosoftRemot; "Microsoft-RemoteDesktopConnection"
0x14010cd91  call    cs:__imp_DismGetFeatureInfo
0x14010cd97  mov     rcx, [rbp+1D8h]; this
0x14010cd9e  lea     rdx, aDismgetfeature_0; "DismGetFeatureInfo failed"
0x14010cda5  mov     [rsp+2D0h+var_2B0], rdx; int
0x14010cdaa  mov     r9d, eax; char *
0x14010cdad  mov     edx, 45h ; 'E'; void *
0x14010cdb2  mov     r8, r13; unsigned int
0x14010cdb5  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14010cdba  test    eax, eax
0x14010cdbc  js      short loc_14010CDDA
0x14010cdbe  mov     rax, [rsp+2D0h+var_290]
0x14010cdc3  test    dil, dil
0x14010cdc6  jnz     short loc_14010CDCE
0x14010cdc8  cmp     dword ptr [rax+8], 3
0x14010cdcc  jnz     short loc_14010CDD1
0x14010cdce  mov     dil, 1
0x14010cdd1  cmp     dword ptr [rax+8], 4
0x14010cdd5  jz      short loc_14010CE10
0x14010cdd7  mov     r14b, 1
0x14010cdda  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x14010cddf  mov     rcx, rbx; hFindFile
0x14010cde2  call    cs:__imp_FindNextFileW
0x14010cde8  test    eax, eax
0x14010cdea  jnz     loc_14010CD36
0x14010cdf0  call    cs:__imp_GetLastError
0x14010cdf6  cmp     eax, 12h
0x14010cdf9  jz      loc_14010CEA3
0x14010cdff  lea     r9, aFindnextfilewF; "FindNextFileW failed"
0x14010ce06  mov     edx, 56h ; 'V'
0x14010ce0b  jmp     loc_14010CEF6
0x14010ce10  mov     r11d, 105h
0x14010ce16  lea     r8, [rsp+2D0h+FindFileData.cFileName]; unsigned __int16 *
0x14010ce1b  mov     edx, r11d; unsigned __int64
0x14010ce1e  mov     rcx, rsi; unsigned __int16 *
0x14010ce21  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14010ce26  mov     ebx, eax
0x14010ce28  test    eax, eax
0x14010ce2a  jns     short loc_14010CE54
0x14010ce2c  lea     rax, aStringcchcopyw_0; "StringCchCopyW(PackageName) failed"
0x14010ce33  mov     edx, 4Fh ; 'O'; void *
0x14010ce38  mov     rcx, [rbp+1D8h]; this
0x14010ce3f  mov     r8, r13; unsigned int
0x14010ce42  mov     r9d, ebx; char *
0x14010ce45  mov     [rsp+2D0h+var_2B0], rax; int
0x14010ce4a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14010ce4f  jmp     loc_14010CF07
0x14010ce54  lea     rcx, [rsi+20Ah]; unsigned __int16 *
0x14010ce5b  mov     rdx, r11; unsigned __int64
0x14010ce5e  lea     r8, aMicrosoftRemot; "Microsoft-RemoteDesktopConnection"
0x14010ce65  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14010ce6a  mov     ebx, eax
0x14010ce6c  test    eax, eax
0x14010ce6e  jns     short loc_14010CE7E
0x14010ce70  lea     rax, aStringcchcopyw_1; "StringCchCopyW(FeatureName) failed"
0x14010ce77  mov     edx, 50h ; 'P'
0x14010ce7c  jmp     short loc_14010CE38
0x14010ce7e  lea     rcx, [rsp+2D0h+var_288]
0x14010ce83  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x14010ce88  lea     rcx, [rsp+2D0h+ppszPathOut]
0x14010ce8d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010ce92  lea     rcx, [rsp+2D0h+ppszPath]
0x14010ce97  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010ce9c  xor     ebx, ebx
0x14010ce9e  jmp     loc_14010CF25
0x14010cea3  lea     rcx, [rsp+2D0h+var_288]
0x14010cea8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x14010cead  lea     rcx, [rsp+2D0h+ppszPathOut]
0x14010ceb2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010ceb7  lea     rcx, [rsp+2D0h+ppszPath]
0x14010cebc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010cec1  test    dil, dil
0x14010cec4  jz      short loc_14010CECD
0x14010cec6  mov     ebx, 80004005h
0x14010cecb  jmp     short loc_14010CF25
0x14010cecd  test    r14b, r14b
0x14010ced0  jz      short loc_14010CED9
0x14010ced2  mov     ebx, 80070BC9h
0x14010ced7  jmp     short loc_14010CF25
0x14010ced9  lea     rcx, [rsp+2D0h+var_290]
0x14010cede  call    ??1?$unique_storage@U?$resource_policy@PEAU_DismFeatureInfo@@$$A6AJPEAX@Z$1?DismDelete@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>(void)
0x14010cee3  mov     eax, 80070002h
0x14010cee8  jmp     short loc_14010CF31
0x14010ceea  lea     r9, aFindfirstfilew; "FindFirstFileW failed"
0x14010cef1  mov     edx, 3Ch ; '<'; void *
0x14010cef6  mov     rcx, [rbp+1D8h]; this
0x14010cefd  mov     r8, r13; unsigned int
0x14010cf00  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14010cf05  mov     ebx, eax
0x14010cf07  lea     rcx, [rsp+2D0h+var_288]
0x14010cf0c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x14010cf11  lea     rcx, [rsp+2D0h+ppszPathOut]
0x14010cf16  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010cf1b  lea     rcx, [rsp+2D0h+ppszPath]
0x14010cf20  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010cf25  lea     rcx, [rsp+2D0h+var_290]
0x14010cf2a  call    ??1?$unique_storage@U?$resource_policy@PEAU_DismFeatureInfo@@$$A6AJPEAX@Z$1?DismDelete@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>(void)
0x14010cf2f  mov     eax, ebx
0x14010cf31  mov     rcx, [rbp+1D0h+var_30]
0x14010cf38  xor     rcx, rsp; StackCookie
0x14010cf3b  call    __security_check_cookie
0x14010cf40  lea     r11, [rsp+2D0h+var_20]
0x14010cf48  mov     rbx, [r11+38h]
0x14010cf4c  mov     rsi, [r11+48h]
0x14010cf50  mov     rsp, r11
0x14010cf53  pop     r15
0x14010cf55  pop     r14
0x14010cf57  pop     r13
0x14010cf59  pop     rdi
0x14010cf5a  pop     rbp
0x14010cf5b  retn
```
