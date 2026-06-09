# TsClientOptionalComponent::GetOptionalComponentInfoForMstsc(uint,bool,TsClientOptionalComponent::OptionalComponentInfo &)

- ea: `0x14010a9a0`
- end: `0x14010adec`
- name: `?GetOptionalComponentInfoForMstsc@TsClientOptionalComponent@@YAJI_NAEAUOptionalComponentInfo@1@@Z`
- size: `1100`
- prototype: `int(TsClientOptionalComponent *__hidden this, unsigned int, bool, struct TsClientOptionalComponent::OptionalComponentInfo *)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140063080`

## callees

- `0x140004703`
- `0x140008a34`
- `0x14006057c`
- `0x1400605c0`
- `0x14006372c`
- `0x14010a7e8`
- `0x14010a958`
- `0x14010a97c`
- `0x14010a9a0`
- `0x14010adf4`
- `0x14010ae3c`
- `0x14010ae78`
- `0x140111220`

## import_xrefs

- `KERNEL32!FindNextFileW` at `0x14010ac72`
- `KERNEL32!FindNextFileW` at `0x14010ac72`
- `KERNEL32!FindFirstFileW` at `0x14010aba5`
- `KERNEL32!FindFirstFileW` at `0x14010aba5`
- `KERNEL32!GetLastError` at `0x14010ac80`
- `KERNEL32!GetLastError` at `0x14010ac80`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x14010ab55`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x14010ab55`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x14010abd0`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x14010abd0`
- `SHELL32!SHGetKnownFolderPath` at `0x14010ab04`
- `SHELL32!SHGetKnownFolderPath` at `0x14010ab04`
- `DismApi!DismGetFeatureInfo` at `0x14010aa17`
- `DismApi!DismGetFeatureInfo` at `0x14010ac21`
- `DismApi!DismGetFeatureInfo` at `0x14010aa17`
- `DismApi!DismGetFeatureInfo` at `0x14010ac21`

## string_xrefs

- `0x14010aa24`: `clientcore\termsrv\client\clientlibs\mstscuninstalllib\tsclientoptionalcomponent.cpp`
- `0x14010aab6`: `StringCchCopyW(FeatureName) failed`
- `0x14010ad00`: `StringCchCopyW(FeatureName) failed`
- `0x14010aa88`: `StringCchCopyW(PackageName) failed`
- `0x14010acbc`: `StringCchCopyW(PackageName) failed`
- `0x14010ab4e`: `Servicing\Packages\Microsoft-Windows-TS-OptionalComponents-Package~*~~*.mum`
- `0x14010ab68`: `PathAllocCombine(packageFilePattern) failed`
- `0x14010ab17`: `SHGetKnownFolderPath(FOLDERID_Windows) failed`
- `0x14010abdd`: `PathCchRemoveExtension failed`

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
0x14010a9a0  mov     [rsp-8+arg_8], rbx
0x14010a9a5  mov     [rsp-8+arg_18], rsi
0x14010a9aa  push    rbp
0x14010a9ab  push    rdi
0x14010a9ac  push    r13
0x14010a9ae  push    r14
0x14010a9b0  push    r15
0x14010a9b2  lea     rbp, [rsp-1B0h]
0x14010a9ba  sub     rsp, 2B0h
0x14010a9c1  mov     rax, cs:__security_cookie
0x14010a9c8  xor     rax, rsp
0x14010a9cb  mov     [rbp+1D0h+var_30], rax
0x14010a9d2  mov     rsi, r8
0x14010a9d5  mov     r15d, ecx
0x14010a9d8  mov     rcx, rsi; void *
0x14010a9db  xor     edx, edx; Val
0x14010a9dd  mov     r8d, 414h; Size
0x14010a9e3  call    memset_0
0x14010a9e8  lea     rcx, [rsp+2D0h+var_290]
0x14010a9ed  mov     [rsp+2D0h+var_290], 0
0x14010a9f6  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_DismFeatureInfo@@$$A6AJPEAX@Z$1?DismDelete@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAU_DismFeatureInfo@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>>::put(void)
0x14010a9fb  mov     r9d, 1
0x14010aa01  mov     [rsp+2D0h+var_2B0], rax
0x14010aa06  lea     r8, aFoundation; "@Foundation"
0x14010aa0d  mov     ecx, r15d
0x14010aa10  lea     rdx, aMicrosoftRemot; "Microsoft-RemoteDesktopConnection"
0x14010aa17  call    cs:__imp_DismGetFeatureInfo
0x14010aa1d  mov     rcx, [rbp+1D8h]; this
0x14010aa24  lea     r13, aClientcoreTerm_0; "clientcore\\termsrv\\client\\clientlibs"...
0x14010aa2b  mov     ebx, eax
0x14010aa2d  mov     r8, r13; unsigned int
0x14010aa30  lea     rax, aDismgetfeature_1; "DismGetFeatureInfo(@Foundation) failed"
0x14010aa37  mov     r9d, ebx; char *
0x14010aa3a  mov     edx, 20h ; ' '; void *
0x14010aa3f  mov     [rsp+2D0h+var_2B0], rax; char *
0x14010aa44  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14010aa49  test    ebx, ebx
0x14010aa4b  js      loc_14010AADE
0x14010aa51  mov     rax, [rsp+2D0h+var_290]
0x14010aa56  cmp     dword ptr [rax+8], 3
0x14010aa5a  jz      loc_14010AD56
0x14010aa60  cmp     dword ptr [rax+8], 4
0x14010aa64  jnz     loc_14010AD62
0x14010aa6a  mov     r11d, 105h
0x14010aa70  lea     r8, aFoundation; "@Foundation"
0x14010aa77  mov     edx, r11d; unsigned __int64
0x14010aa7a  mov     rcx, rsi; unsigned __int16 *
0x14010aa7d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14010aa82  mov     ebx, eax
0x14010aa84  test    eax, eax
0x14010aa86  jns     short loc_14010AA96
0x14010aa88  lea     rax, aStringcchcopyw_0; "StringCchCopyW(PackageName) failed"
0x14010aa8f  mov     edx, 26h ; '&'
0x14010aa94  jmp     short loc_14010AAC2
0x14010aa96  lea     rcx, [rsi+20Ah]; unsigned __int16 *
0x14010aa9d  mov     rdx, r11; unsigned __int64
0x14010aaa0  lea     r8, aMicrosoftRemot; "Microsoft-RemoteDesktopConnection"
0x14010aaa7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14010aaac  mov     ebx, eax
0x14010aaae  test    eax, eax
0x14010aab0  jns     loc_14010AD2C
0x14010aab6  lea     rax, aStringcchcopyw_1; "StringCchCopyW(FeatureName) failed"
0x14010aabd  mov     edx, 27h ; '''; void *
0x14010aac2  mov     rcx, [rbp+1D8h]; this
0x14010aac9  mov     r8, r13; unsigned int
0x14010aacc  mov     r9d, ebx; char *
0x14010aacf  mov     [rsp+2D0h+var_2B0], rax; int
0x14010aad4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14010aad9  jmp     loc_14010ADB5
0x14010aade  xor     edx, edx
0x14010aae0  mov     [rsp+2D0h+ppszPath], 0
0x14010aae9  lea     rcx, [rsp+2D0h+ppszPath]
0x14010aaee  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14010aaf3  lea     r9, [rsp+2D0h+ppszPath]; ppszPath
0x14010aaf8  xor     r8d, r8d; hToken
0x14010aafb  xor     edx, edx; dwFlags
0x14010aafd  lea     rcx, FOLDERID_Windows; rfid
0x14010ab04  call    cs:__imp_SHGetKnownFolderPath
0x14010ab0a  mov     ebx, eax
0x14010ab0c  test    eax, eax
0x14010ab0e  jns     short loc_14010AB38
0x14010ab10  mov     rcx, [rbp+1D8h]; this
0x14010ab17  lea     rax, aShgetknownfold_1; "SHGetKnownFolderPath(FOLDERID_Windows) "...
0x14010ab1e  mov     r9d, ebx; char *
0x14010ab21  mov     [rsp+2D0h+var_2B0], rax; int
0x14010ab26  mov     r8, r13; unsigned int
0x14010ab29  mov     edx, 35h ; '5'; void *
0x14010ab2e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14010ab33  jmp     loc_14010ADAB
0x14010ab38  mov     rcx, [rsp+2D0h+ppszPath]; pszPathIn
0x14010ab3d  lea     r9, [rsp+2D0h+ppszPathOut]; ppszPathOut
0x14010ab42  xor     r8d, r8d; dwFlags
0x14010ab45  mov     [rsp+2D0h+ppszPathOut], 0
0x14010ab4e  lea     rdx, aServicingPacka; "Servicing\\Packages\\Microsoft-Windows-"...
0x14010ab55  call    cs:__imp_PathAllocCombine
0x14010ab5b  mov     ebx, eax
0x14010ab5d  test    eax, eax
0x14010ab5f  jns     short loc_14010AB89
0x14010ab61  mov     rcx, [rbp+1D8h]; this
0x14010ab68  lea     rax, aPathalloccombi; "PathAllocCombine(packageFilePattern) fa"...
0x14010ab6f  mov     r9d, ebx; char *
0x14010ab72  mov     [rsp+2D0h+var_2B0], rax; int
0x14010ab77  mov     r8, r13; unsigned int
0x14010ab7a  mov     edx, 38h ; '8'; void *
0x14010ab7f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14010ab84  jmp     loc_14010ADA1
0x14010ab89  xor     edx, edx; Val
0x14010ab8b  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x14010ab90  mov     r8d, 250h; Size
0x14010ab96  call    memset_0
0x14010ab9b  mov     rcx, [rsp+2D0h+ppszPathOut]; lpFileName
0x14010aba0  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x14010aba5  call    cs:__imp_FindFirstFileW
0x14010abab  mov     rbx, rax
0x14010abae  mov     [rsp+2D0h+var_288], rax
0x14010abb3  dec     rax
0x14010abb6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14010abba  ja      loc_14010AD7A
0x14010abc0  xor     r14b, r14b
0x14010abc3  xor     dil, dil
0x14010abc6  mov     edx, 104h; cchPath
0x14010abcb  lea     rcx, [rsp+2D0h+FindFileData.cFileName]; pszPath
0x14010abd0  call    cs:__imp_PathCchRemoveExtension
0x14010abd6  mov     rcx, [rbp+1D8h]; this
0x14010abdd  lea     rdx, aPathcchremovee; "PathCchRemoveExtension failed"
0x14010abe4  mov     [rsp+2D0h+var_2B0], rdx; int
0x14010abe9  mov     r9d, eax; char *
0x14010abec  mov     edx, 40h ; '@'; void *
0x14010abf1  mov     r8, r13; unsigned int
0x14010abf4  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14010abf9  test    eax, eax
0x14010abfb  js      short loc_14010AC6A
0x14010abfd  lea     rcx, [rsp+2D0h+var_290]
0x14010ac02  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_DismFeatureInfo@@$$A6AJPEAX@Z$1?DismDelete@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAU_DismFeatureInfo@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>>::put(void)
0x14010ac07  mov     r9d, 1
0x14010ac0d  mov     [rsp+2D0h+var_2B0], rax
0x14010ac12  lea     r8, [rsp+2D0h+FindFileData.cFileName]
0x14010ac17  mov     ecx, r15d
0x14010ac1a  lea     rdx, aMicrosoftRemot; "Microsoft-RemoteDesktopConnection"
0x14010ac21  call    cs:__imp_DismGetFeatureInfo
0x14010ac27  mov     rcx, [rbp+1D8h]; this
0x14010ac2e  lea     rdx, aDismgetfeature_0; "DismGetFeatureInfo failed"
0x14010ac35  mov     [rsp+2D0h+var_2B0], rdx; int
0x14010ac3a  mov     r9d, eax; char *
0x14010ac3d  mov     edx, 45h ; 'E'; void *
0x14010ac42  mov     r8, r13; unsigned int
0x14010ac45  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14010ac4a  test    eax, eax
0x14010ac4c  js      short loc_14010AC6A
0x14010ac4e  mov     rax, [rsp+2D0h+var_290]
0x14010ac53  test    dil, dil
0x14010ac56  jnz     short loc_14010AC5E
0x14010ac58  cmp     dword ptr [rax+8], 3
0x14010ac5c  jnz     short loc_14010AC61
0x14010ac5e  mov     dil, 1
0x14010ac61  cmp     dword ptr [rax+8], 4
0x14010ac65  jz      short loc_14010ACA0
0x14010ac67  mov     r14b, 1
0x14010ac6a  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x14010ac6f  mov     rcx, rbx; hFindFile
0x14010ac72  call    cs:__imp_FindNextFileW
0x14010ac78  test    eax, eax
0x14010ac7a  jnz     loc_14010ABC6
0x14010ac80  call    cs:__imp_GetLastError
0x14010ac86  cmp     eax, 12h
0x14010ac89  jz      loc_14010AD33
0x14010ac8f  lea     r9, aFindnextfilewF; "FindNextFileW failed"
0x14010ac96  mov     edx, 56h ; 'V'
0x14010ac9b  jmp     loc_14010AD86
0x14010aca0  mov     r11d, 105h
0x14010aca6  lea     r8, [rsp+2D0h+FindFileData.cFileName]; unsigned __int16 *
0x14010acab  mov     edx, r11d; unsigned __int64
0x14010acae  mov     rcx, rsi; unsigned __int16 *
0x14010acb1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14010acb6  mov     ebx, eax
0x14010acb8  test    eax, eax
0x14010acba  jns     short loc_14010ACE4
0x14010acbc  lea     rax, aStringcchcopyw_0; "StringCchCopyW(PackageName) failed"
0x14010acc3  mov     edx, 4Fh ; 'O'; void *
0x14010acc8  mov     rcx, [rbp+1D8h]; this
0x14010accf  mov     r8, r13; unsigned int
0x14010acd2  mov     r9d, ebx; char *
0x14010acd5  mov     [rsp+2D0h+var_2B0], rax; int
0x14010acda  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14010acdf  jmp     loc_14010AD97
0x14010ace4  lea     rcx, [rsi+20Ah]; unsigned __int16 *
0x14010aceb  mov     rdx, r11; unsigned __int64
0x14010acee  lea     r8, aMicrosoftRemot; "Microsoft-RemoteDesktopConnection"
0x14010acf5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14010acfa  mov     ebx, eax
0x14010acfc  test    eax, eax
0x14010acfe  jns     short loc_14010AD0E
0x14010ad00  lea     rax, aStringcchcopyw_1; "StringCchCopyW(FeatureName) failed"
0x14010ad07  mov     edx, 50h ; 'P'
0x14010ad0c  jmp     short loc_14010ACC8
0x14010ad0e  lea     rcx, [rsp+2D0h+var_288]
0x14010ad13  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x14010ad18  lea     rcx, [rsp+2D0h+ppszPathOut]
0x14010ad1d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010ad22  lea     rcx, [rsp+2D0h+ppszPath]
0x14010ad27  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010ad2c  xor     ebx, ebx
0x14010ad2e  jmp     loc_14010ADB5
0x14010ad33  lea     rcx, [rsp+2D0h+var_288]
0x14010ad38  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x14010ad3d  lea     rcx, [rsp+2D0h+ppszPathOut]
0x14010ad42  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010ad47  lea     rcx, [rsp+2D0h+ppszPath]
0x14010ad4c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010ad51  test    dil, dil
0x14010ad54  jz      short loc_14010AD5D
0x14010ad56  mov     ebx, 80004005h
0x14010ad5b  jmp     short loc_14010ADB5
0x14010ad5d  test    r14b, r14b
0x14010ad60  jz      short loc_14010AD69
0x14010ad62  mov     ebx, 80070BC9h
0x14010ad67  jmp     short loc_14010ADB5
0x14010ad69  lea     rcx, [rsp+2D0h+var_290]
0x14010ad6e  call    ??1?$unique_storage@U?$resource_policy@PEAU_DismFeatureInfo@@$$A6AJPEAX@Z$1?DismDelete@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>(void)
0x14010ad73  mov     eax, 80070002h
0x14010ad78  jmp     short loc_14010ADC1
0x14010ad7a  lea     r9, aFindfirstfilew; "FindFirstFileW failed"
0x14010ad81  mov     edx, 3Ch ; '<'; void *
0x14010ad86  mov     rcx, [rbp+1D8h]; this
0x14010ad8d  mov     r8, r13; unsigned int
0x14010ad90  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14010ad95  mov     ebx, eax
0x14010ad97  lea     rcx, [rsp+2D0h+var_288]
0x14010ad9c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x14010ada1  lea     rcx, [rsp+2D0h+ppszPathOut]
0x14010ada6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010adab  lea     rcx, [rsp+2D0h+ppszPath]
0x14010adb0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010adb5  lea     rcx, [rsp+2D0h+var_290]
0x14010adba  call    ??1?$unique_storage@U?$resource_policy@PEAU_DismFeatureInfo@@$$A6AJPEAX@Z$1?DismDelete@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>(void)
0x14010adbf  mov     eax, ebx
0x14010adc1  mov     rcx, [rbp+1D0h+var_30]
0x14010adc8  xor     rcx, rsp; StackCookie
0x14010adcb  call    __security_check_cookie
0x14010add0  lea     r11, [rsp+2D0h+var_20]
0x14010add8  mov     rbx, [r11+38h]
0x14010addc  mov     rsi, [r11+48h]
0x14010ade0  mov     rsp, r11
0x14010ade3  pop     r15
0x14010ade5  pop     r14
0x14010ade7  pop     r13
0x14010ade9  pop     rdi
0x14010adea  pop     rbp
0x14010adeb  retn
```
