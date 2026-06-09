# SplPipeline::ConfigLoader::AddSingleFilterServiceProvider(IPrintPipelinePropertyBag *,wchar_t const *,PrnSharedState::SharedState *,wchar_t const *,void *,wchar_t const *,bool,NCoreLibrary::TList<PrnExcept::PropertyBagElement> &)

- ea: `0x1400135ac`
- end: `0x140013a39`
- name: `?AddSingleFilterServiceProvider@ConfigLoader@SplPipeline@@AEAAXPEAUIPrintPipelinePropertyBag@@PEB_WPEAVSharedState@PrnSharedState@@1PEAX1_NAEAV?$TList@VPropertyBagElement@PrnExcept@@@NCoreLibrary@@@Z`
- size: `1165`
- prototype: `__int64 __fastcall(__int64, struct IPrintPipelinePropertyBag *, const wchar_t *, __int64, __int64, void *, wchar_t *String, char, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x140013a40`

## callees

- `0x140002070`
- `0x140002c68`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x140007654`
- `0x1400084a0`
- `0x14000dc6c`
- `0x14000f9d8`
- `0x14000fa68`
- `0x1400132e0`
- `0x1400135ac`
- `0x140014fd8`
- `0x140016b1c`
- `0x1400456fc`
- `0x1400459a4`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`
- `0x140046a98`
- `0x140046ab4`
- `0x14005742c`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x1400137e5`
- `KERNEL32!GetSystemDirectoryW` at `0x1400137e5`
- `KERNEL32!GetFileAttributesW` at `0x140013788`
- `KERNEL32!GetFileAttributesW` at `0x140013788`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14001379f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1400137b4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1400137c9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14001379f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1400137b4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1400137c9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140013719`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140013719`

## string_xrefs

- `0x14001369f`: `Invalid DLL Name`
- `0x140013748`: `Invalid DLL Path`
- `0x1400138ad`: `Invalid DLL Name.`
- `0x140013815`: `GetSystemDirectory failed.`

## pseudocode

```c
__int64 __fastcall SplPipeline::ConfigLoader::AddSingleFilterServiceProvider(
        __int64 a1,
        struct IPrintPipelinePropertyBag *a2,
        const wchar_t *a3,
        __int64 a4,
        __int64 a5,
        void *a6,
        wchar_t *String,
        char a8,
        __int64 a9)
{
  int FullPathFromFilename; // eax
  int IsValid; // esi
  const struct SplException::TSystemException *v14; // r8
  const struct _GUID *v15; // r9
  int v16; // eax
  int v17; // edx
  const char *v18; // r8
  unsigned int v19; // r9d
  const struct SplException::TSystemException *v20; // r8
  const struct _GUID *v21; // r9
  unsigned __int64 v22; // rdx
  NCoreLibrary *v23; // rcx
  unsigned int v24; // edx
  const struct SplException::TSystemException *v25; // r8
  const struct _GUID *v26; // r9
  int v27; // eax
  unsigned __int64 v28; // rdx
  const char *v29; // r8
  unsigned int v30; // r9d
  int v31; // eax
  int v32; // edx
  const char *v33; // r8
  unsigned int v34; // r9d
  NCoreLibrary *v35; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v37; // r8
  const struct _GUID *v38; // r9
  PrnSharedState::LoadedModule *Module; // rdi
  const char *v40; // rdx
  unsigned int v41; // r8d
  PrnExcept::TPropertyBagWrapper *v42; // rax
  unsigned __int64 v43; // rcx
  struct IPrintPipelinePropertyBag *v44; // rbx
  const char *v45; // rdx
  unsigned int v46; // r8d
  NCoreLibrary::TLink *v47; // rax
  NCoreLibrary::TLink *v48; // rdi
  int v49; // edx
  const char *v50; // r8
  unsigned int v51; // r9d
  unsigned int v53; // [rsp+20h] [rbp-5C8h]
  const struct win_musl::TStringEllipseBase *v54; // [rsp+28h] [rbp-5C0h]
  HINSTANCE v55; // [rsp+30h] [rbp-5B8h]
  PrnExcept::TPropertyBagWrapper *v56; // [rsp+40h] [rbp-5A8h] BYREF
  struct IPrintPipelinePropertyBag *v57; // [rsp+48h] [rbp-5A0h] BYREF
  PrnSharedState::LoadedModule *v58; // [rsp+50h] [rbp-598h] BYREF
  __int64 v59; // [rsp+58h] [rbp-590h]
  SplException::TSystemException *v60; // [rsp+68h] [rbp-580h] BYREF
  _BYTE v61[160]; // [rsp+70h] [rbp-578h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+110h] [rbp-4D8h] BYREF
  _BYTE v63[160]; // [rsp+1B0h] [rbp-438h] BYREF
  _BYTE v64[160]; // [rsp+250h] [rbp-398h] BYREF
  _BYTE v65[160]; // [rsp+2F0h] [rbp-2F8h] BYREF
  wchar_t Str[264]; // [rsp+390h] [rbp-258h] BYREF

  v59 = a9;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids);
  }
  memset_0(Str, 0, 0x208u);
  v58 = 0;
  FullPathFromFilename = GetFullPathFromFilename(a6, String, Str);
  IsValid = -2147024809;
  if ( FullPathFromFilename < 0 )
  {
    if ( FullPathFromFilename == -2147024809 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v61, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v61,
        0x80070057,
        v14,
        v15,
        v53,
        v54,
        v55);
      SplException::TSystemException::Message((SplException::TSystemException *)v61, "Invalid DLL Name");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v61);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v53 = (unsigned int)String;
    v16 = StringCchPrintfW(Str, 0x104u, L"%s\\3\\%s", a5);
    if ( v16 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v16, v17, v18, v19);
  }
  try
  {
    if ( wcsstr(Str, L"\\..\\") )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v61, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v61,
        0x80070057,
        v20,
        v21,
        v53,
        v54,
        v55);
      SplException::TSystemException::Message((SplException::TSystemException *)v61, "Invalid DLL Path");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)v63,
        (const struct SplException::THResultException *)v61);
      throw (SplException::THResultException *)v63;
    }
    if ( GetFileAttributesW(Str) == -1 )
    {
      if ( wcschr(String, 0x5Cu) || wcschr(String, 0x2Fu) || wcschr(String, 0x3Au) )
      {
        SplException::THResultException::THResultException((SplException::THResultException *)v61, "-", 0);
        LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v35);
        SplException::TSystemException::InternalInit(
          (SplException::TSystemException *)v61,
          LastErrorAsHResult,
          v37,
          v38,
          v53,
          v54,
          v55);
        SplException::TSystemException::Message((SplException::TSystemException *)v61, "Invalid DLL Name.");
        SplException::THResultException::THResultException(
          (SplException::THResultException *)v65,
          (const struct SplException::THResultException *)v61);
        throw (SplException::THResultException *)v65;
      }
      if ( !GetSystemDirectoryW(Str, 0x104u) )
      {
        SplException::THResultException::THResultException((SplException::THResultException *)v61, "-", 0);
        v24 = NCoreLibrary::GetLastErrorAsHResult(v23);
        SplException::TSystemException::InternalInit(
          (SplException::TSystemException *)v61,
          v24,
          v25,
          v26,
          v53,
          v54,
          v55);
        SplException::TSystemException::Message((SplException::TSystemException *)v61, "GetSystemDirectory failed.");
        SplException::THResultException::THResultException(
          (SplException::THResultException *)v64,
          (const struct SplException::THResultException *)v61);
        throw (SplException::THResultException *)v64;
      }
      v27 = StringCchCatW(Str, v22, L"\\");
      if ( v27 < 0 )
        SplException::RealThrowFromHR((SplException *)(unsigned int)v27, v28, v29, v30);
      v31 = StringCchCatW(Str, v28, String);
      if ( v31 < 0 )
        SplException::RealThrowFromHR((SplException *)(unsigned int)v31, v32, v33, v34);
    }
    Module = PrnSharedState::DllManager::LoadModule(*(PrnSharedState::DllManager **)(a4 + 40), Str);
    v57 = 0;
    v58 = Module;
    PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(&v57);
    v57 = 0;
    v42 = (PrnExcept::TPropertyBagWrapper *)operator new(0x68u, v40, v41);
    v56 = v42;
    if ( v42 )
      v43 = PrnExcept::TPropertyBagWrapper::TPropertyBagWrapper(v42, a2, a3);
    else
      v43 = 0;
    v44 = (struct IPrintPipelinePropertyBag *)((v43 + 16) & ((unsigned __int128)-(__int128)v43 >> 64));
    v56 = 0;
    v57 = v44;
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v56);
    PrnSharedState::LoadedModule::DrvPopulateServices(Module, v44);
    v56 = 0;
    v47 = (NCoreLibrary::TLink *)operator new(0x28u, v45, v46);
    v48 = v47;
    if ( v47 )
    {
      *((_DWORD *)v47 + 2) = 1802398836;
      *((_QWORD *)v47 + 2) = v47;
      *((_QWORD *)v47 + 3) = v47;
      *(_QWORD *)v47 = &PrnExcept::PropertyBagElement::`vftable';
      *((_QWORD *)v47 + 4) = v44;
      PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(v44);
    }
    else
    {
      v48 = 0;
    }
    NCoreLibrary::TGenericSP<PrnExcept::PropertyBagElement,NCoreLibrary::TAutoPtr<PrnExcept::PropertyBagElement>,PrnExcept::PropertyBagElement *,0,PrnExcept::PropertyBagElement const *>::Reset(&v56);
    if ( v48 )
    {
      v56 = v48;
      IsValid = NCoreLibrary::TLink::IsValid(v48);
      if ( IsValid >= 0 )
      {
        IsValid = NCoreLibrary::TLink::Link(*(NCoreLibrary::TLink **)(v59 + 32), v48);
        if ( IsValid >= 0 )
        {
          v56 = 0;
          NCoreLibrary::TGenericSP<PrnExcept::PropertyBagElement,NCoreLibrary::TAutoPtr<PrnExcept::PropertyBagElement>,PrnExcept::PropertyBagElement *,0,PrnExcept::PropertyBagElement const *>::Reset(&v56);
          PrnExcept::SmartRelease<IPartResourceDictionary>(&v57);
          return PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(&v58);
        }
      }
    }
    else
    {
      v56 = 0;
    }
    SplException::RealThrowFromHR((SplException *)(unsigned int)IsValid, v49, v50, v51);
  }
  catch ( SplException::TSystemException *v60 )
  {
    if ( a8 )
      throw;
    if ( SplException::gpfnExceptionLogger )
      SplException::gpfnExceptionLogger(v60);
  }
  if ( wcsstr(Str, L"\\..\\") )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v61, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v61,
      0x80070057,
      v20,
      v21,
      v53,
      v54,
      v55);
    SplException::TSystemException::Message((SplException::TSystemException *)v61, "Invalid DLL Path");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)v63,
      (const struct SplException::THResultException *)v61);
    throw (SplException::THResultException *)v63;
  }
}

```

## disassembly

```asm
0x1400135ac  push    rbx
0x1400135ae  push    rsi
0x1400135af  push    rdi
0x1400135b0  push    r12
0x1400135b2  push    r13
0x1400135b4  push    r14
0x1400135b6  push    r15
0x1400135b8  sub     rsp, 5B0h
0x1400135bf  mov     rax, cs:__security_cookie
0x1400135c6  xor     rax, rsp
0x1400135c9  mov     [rsp+5E8h+var_48], rax
0x1400135d1  mov     r15, r9
0x1400135d4  mov     r13, r8
0x1400135d7  mov     r12, rdx
0x1400135da  mov     r14, [rsp+5E8h+arg_20]
0x1400135e2  mov     rdi, [rsp+5E8h+arg_28]
0x1400135ea  mov     rbx, [rsp+5E8h+String]
0x1400135f2  mov     rax, [rsp+5E8h+arg_40]
0x1400135fa  mov     [rsp+5E8h+var_590], rax
0x1400135ff  lea     rax, WPP_GLOBAL_Control
0x140013606  mov     rcx, cs:WPP_GLOBAL_Control
0x14001360d  cmp     rcx, rax
0x140013610  jz      short loc_140013639
0x140013612  test    dword ptr [rcx+1Ch], 100h
0x140013619  jz      short loc_140013639
0x14001361b  cmp     byte ptr [rcx+19h], 1
0x14001361f  jb      short loc_140013639
0x140013621  mov     edx, 10h
0x140013626  mov     r9, rbx
0x140013629  lea     r8, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids
0x140013630  mov     rcx, [rcx+10h]
0x140013634  call    WPP_SF_S
0x140013639  xor     edx, edx; Val
0x14001363b  mov     r8d, 208h; Size
0x140013641  lea     rcx, [rsp+5E8h+Str]; void *
0x140013649  call    memset_0
0x14001364e  mov     [rsp+5E8h+var_598], 0
0x140013657  lea     r8, [rsp+5E8h+Str]; wchar_t *
0x14001365f  mov     rdx, rbx; String
0x140013662  mov     rcx, rdi; void *
0x140013665  call    GetFullPathFromFilename
0x14001366a  mov     esi, 80070057h
0x14001366f  test    eax, eax
0x140013671  jns     loc_140013707
0x140013677  cmp     eax, esi
0x140013679  jnz     short loc_1400136D7
0x14001367b  xor     r8d, r8d; unsigned int
0x14001367e  lea     rdx, asc_1400696D8; "-"
0x140013685  lea     rcx, [rsp+5E8h+var_578]; this
0x14001368a  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001368f  nop
0x140013690  mov     edx, 80070057h; unsigned int
0x140013695  lea     rcx, [rsp+5E8h+var_578]; this
0x14001369a  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14001369f  lea     rdx, aInvalidDllName; "Invalid DLL Name"
0x1400136a6  lea     rcx, [rsp+5E8h+var_578]; this
0x1400136ab  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400136b0  lea     rdx, [rsp+5E8h+var_578]; struct SplException::THResultException *
0x1400136b5  lea     rcx, [rsp+5E8h+pExceptionObject]; this
0x1400136bd  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400136c2  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400136c9  lea     rcx, [rsp+5E8h+pExceptionObject]; pExceptionObject
0x1400136d1  call    _CxxThrowException_0
0x1400136d7  mov     [rsp+5E8h+var_5C8], rbx
0x1400136dc  mov     r9, r14
0x1400136df  lea     r8, aS3S; "%s\\3\\%s"
0x1400136e6  mov     edx, 104h; unsigned __int64
0x1400136eb  lea     rcx, [rsp+5E8h+Str]; wchar_t *
0x1400136f3  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400136f8  xor     r14d, r14d
0x1400136fb  test    eax, eax
0x1400136fd  jns     short loc_14001370A
0x1400136ff  mov     ecx, eax; this
0x140013701  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140013707  xor     r14d, r14d
0x14001370a  lea     rdx, SubStr; "\\..\\"
0x140013711  lea     rcx, [rsp+5E8h+Str]; Str
0x140013719  call    cs:__imp_wcsstr
0x14001371f  test    rax, rax
0x140013722  jz      short loc_140013780
0x140013724  xor     r8d, r8d; unsigned int
0x140013727  lea     rdx, asc_1400696D8; "-"
0x14001372e  lea     rcx, [rsp+5E8h+var_578]; this
0x140013733  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140013738  nop
0x140013739  mov     edx, 80070057h; unsigned int
0x14001373e  lea     rcx, [rsp+5E8h+var_578]; this
0x140013743  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140013748  lea     rdx, aInvalidDllPath; "Invalid DLL Path"
0x14001374f  lea     rcx, [rsp+5E8h+var_578]; this
0x140013754  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140013759  lea     rdx, [rsp+5E8h+var_578]; struct SplException::THResultException *
0x14001375e  lea     rcx, [rsp+5E8h+var_438]; this
0x140013766  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001376b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140013772  lea     rcx, [rsp+5E8h+var_438]; pExceptionObject
0x14001377a  call    _CxxThrowException_0
0x140013780  lea     rcx, [rsp+5E8h+Str]; lpFileName
0x140013788  call    cs:__imp_GetFileAttributesW
0x14001378e  cmp     eax, 0FFFFFFFFh
0x140013791  jnz     loc_1400138E5
0x140013797  mov     edx, 5Ch ; '\'; Ch
0x14001379c  mov     rcx, rbx; Str
0x14001379f  call    cs:__imp_wcschr
0x1400137a5  test    rax, rax
0x1400137a8  jnz     loc_140013887
0x1400137ae  lea     edx, [rax+2Fh]; Ch
0x1400137b1  mov     rcx, rbx; Str
0x1400137b4  call    cs:__imp_wcschr
0x1400137ba  test    rax, rax
0x1400137bd  jnz     loc_140013887
0x1400137c3  lea     edx, [rax+3Ah]; Ch
0x1400137c6  mov     rcx, rbx; Str
0x1400137c9  call    cs:__imp_wcschr
0x1400137cf  test    rax, rax
0x1400137d2  jnz     loc_140013887
0x1400137d8  mov     edx, 104h; uSize
0x1400137dd  lea     rcx, [rsp+5E8h+Str]; lpBuffer
0x1400137e5  call    cs:__imp_GetSystemDirectoryW
0x1400137eb  test    eax, eax
0x1400137ed  jnz     short loc_14001384D
0x1400137ef  xor     r8d, r8d; unsigned int
0x1400137f2  lea     rdx, asc_1400696D8; "-"
0x1400137f9  lea     rcx, [rsp+5E8h+var_578]; this
0x1400137fe  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140013803  nop
0x140013804  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140013809  mov     edx, eax; unsigned int
0x14001380b  lea     rcx, [rsp+5E8h+var_578]; this
0x140013810  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140013815  lea     rdx, aGetsystemdirec; "GetSystemDirectory failed."
0x14001381c  lea     rcx, [rsp+5E8h+var_578]; this
0x140013821  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140013826  lea     rdx, [rsp+5E8h+var_578]; struct SplException::THResultException *
0x14001382b  lea     rcx, [rsp+5E8h+var_398]; this
0x140013833  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140013838  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14001383f  lea     rcx, [rsp+5E8h+var_398]; pExceptionObject
0x140013847  call    _CxxThrowException_0
0x14001384d  lea     r8, asc_1400691D8; "\\"
0x140013854  lea     rcx, [rsp+5E8h+Str]; wchar_t *
0x14001385c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140013861  test    eax, eax
0x140013863  jns     short loc_14001386C
0x140013865  mov     ecx, eax; this
0x140013867  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14001386c  mov     r8, rbx; wchar_t *
0x14001386f  lea     rcx, [rsp+5E8h+Str]; wchar_t *
0x140013877  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001387c  test    eax, eax
0x14001387e  jns     short loc_1400138E5
0x140013880  mov     ecx, eax; this
0x140013882  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140013887  xor     r8d, r8d; unsigned int
0x14001388a  lea     rdx, asc_1400696D8; "-"
0x140013891  lea     rcx, [rsp+5E8h+var_578]; this
0x140013896  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001389b  nop
0x14001389c  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x1400138a1  mov     edx, eax; unsigned int
0x1400138a3  lea     rcx, [rsp+5E8h+var_578]; this
0x1400138a8  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400138ad  lea     rdx, aInvalidDllName_0; "Invalid DLL Name."
0x1400138b4  lea     rcx, [rsp+5E8h+var_578]; this
0x1400138b9  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400138be  lea     rdx, [rsp+5E8h+var_578]; struct SplException::THResultException *
0x1400138c3  lea     rcx, [rsp+5E8h+var_2F8]; this
0x1400138cb  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400138d0  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400138d7  lea     rcx, [rsp+5E8h+var_2F8]; pExceptionObject
0x1400138df  call    _CxxThrowException_0
0x1400138e5  lea     rdx, [rsp+5E8h+Str]; wchar_t *
0x1400138ed  mov     rcx, [r15+28h]; this
0x1400138f1  call    ?LoadModule@DllManager@PrnSharedState@@QEAAPEAVLoadedModule@2@PEB_W@Z; PrnSharedState::DllManager::LoadModule(wchar_t const *)
0x1400138f6  mov     rdi, rax
0x1400138f9  mov     [rsp+5E8h+var_5A0], r14
0x1400138fe  mov     [rsp+5E8h+var_598], rax
0x140013903  lea     rcx, [rsp+5E8h+var_5A0]
0x140013908  call    ??$SmartRelease@VLoadedModule@PrnSharedState@@@PrnExcept@@YAXPEAPEAVLoadedModule@PrnSharedState@@@Z; PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(PrnSharedState::LoadedModule * *)
0x14001390d  mov     [rsp+5E8h+var_5A0], r14
0x140013912  mov     ecx, 68h ; 'h'; unsigned __int64
0x140013917  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x14001391c  mov     [rsp+5E8h+var_5A8], rax
0x140013921  test    rax, rax
0x140013924  jz      short loc_140013939
0x140013926  mov     r8, r13; wchar_t *
0x140013929  mov     rdx, r12; struct IPrintPipelinePropertyBag *
0x14001392c  mov     rcx, rax; this
0x14001392f  call    ??0TPropertyBagWrapper@PrnExcept@@QEAA@PEAUIPrintPipelinePropertyBag@@PEB_W@Z; PrnExcept::TPropertyBagWrapper::TPropertyBagWrapper(IPrintPipelinePropertyBag *,wchar_t const *)
0x140013934  mov     rcx, rax
0x140013937  jmp     short loc_14001393C
0x140013939  mov     rcx, r14
0x14001393c  lea     rax, [rcx+10h]
0x140013940  neg     rcx
0x140013943  sbb     rbx, rbx
0x140013946  and     rbx, rax
0x140013949  mov     [rsp+5E8h+var_5A8], r14
0x14001394e  mov     [rsp+5E8h+var_5A0], rbx
0x140013953  lea     rcx, [rsp+5E8h+var_5A8]
0x140013958  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001395d  mov     rdx, rbx; struct IPrintPipelinePropertyBag *
0x140013960  mov     rcx, rdi; this
0x140013963  call    ?DrvPopulateServices@LoadedModule@PrnSharedState@@QEAAXPEAUIPrintPipelinePropertyBag@@@Z; PrnSharedState::LoadedModule::DrvPopulateServices(IPrintPipelinePropertyBag *)
0x140013968  mov     [rsp+5E8h+var_5A8], r14
0x14001396d  mov     ecx, 28h ; '('; unsigned __int64
0x140013972  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x140013977  mov     rdi, rax
0x14001397a  test    rax, rax
0x14001397d  jz      short loc_1400139A6
0x14001397f  mov     dword ptr [rax+8], 6B6E6C74h
0x140013986  mov     [rax+10h], rax
0x14001398a  mov     [rax+18h], rax
0x14001398e  lea     rax, ??_7PropertyBagElement@PrnExcept@@6B@; const PrnExcept::PropertyBagElement::`vftable'
0x140013995  mov     [rdi], rax
0x140013998  mov     [rdi+20h], rbx
0x14001399c  mov     rcx, rbx
0x14001399f  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x1400139a4  jmp     short loc_1400139A9
0x1400139a6  mov     rdi, r14
0x1400139a9  lea     rcx, [rsp+5E8h+var_5A8]
0x1400139ae  call    ?Reset@?$TGenericSP@VPropertyBagElement@PrnExcept@@V?$TAutoPtr@VPropertyBagElement@PrnExcept@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<PrnExcept::PropertyBagElement,NCoreLibrary::TAutoPtr<PrnExcept::PropertyBagElement>,PrnExcept::PropertyBagElement *,0,PrnExcept::PropertyBagElement const *>::Reset(void)
0x1400139b3  test    rdi, rdi
0x1400139b6  jz      short loc_1400139FF
0x1400139b8  mov     [rsp+5E8h+var_5A8], rdi
0x1400139bd  mov     rcx, rdi; this
0x1400139c0  call    ?IsValid@TLink@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TLink::IsValid(void)
0x1400139c5  mov     esi, eax
0x1400139c7  test    eax, eax
0x1400139c9  js      short loc_140013A04
0x1400139cb  mov     rdx, rdi; struct NCoreLibrary::TLink *
0x1400139ce  mov     rcx, [rsp+5E8h+var_590]
0x1400139d3  mov     rcx, [rcx+20h]; this
0x1400139d7  call    ?Link@TLink@NCoreLibrary@@QEAAJPEAV12@@Z; NCoreLibrary::TLink::Link(NCoreLibrary::TLink *)
0x1400139dc  mov     esi, eax
0x1400139de  test    eax, eax
0x1400139e0  js      short loc_140013A04
0x1400139e2  mov     [rsp+5E8h+var_5A8], r14
0x1400139e7  lea     rcx, [rsp+5E8h+var_5A8]
0x1400139ec  call    ?Reset@?$TGenericSP@VPropertyBagElement@PrnExcept@@V?$TAutoPtr@VPropertyBagElement@PrnExcept@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<PrnExcept::PropertyBagElement,NCoreLibrary::TAutoPtr<PrnExcept::PropertyBagElement>,PrnExcept::PropertyBagElement *,0,PrnExcept::PropertyBagElement const *>::Reset(void)
0x1400139f1  nop
0x1400139f2  lea     rcx, [rsp+5E8h+var_5A0]
0x1400139f7  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400139fc  nop
0x1400139fd  jmp     short loc_140013A0C
0x1400139ff  mov     [rsp+5E8h+var_5A8], r14
0x140013a04  mov     ecx, esi; this
0x140013a06  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140013a0c  lea     rcx, [rsp+5E8h+var_598]
0x140013a11  call    ??$SmartRelease@VLoadedModule@PrnSharedState@@@PrnExcept@@YAXPEAPEAVLoadedModule@PrnSharedState@@@Z; PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(PrnSharedState::LoadedModule * *)
0x140013a16  mov     rcx, [rsp+5E8h+var_48]
0x140013a1e  xor     rcx, rsp; StackCookie
0x140013a21  call    __security_check_cookie
0x140013a26  add     rsp, 5B0h
0x140013a2d  pop     r15
0x140013a2f  pop     r14
0x140013a31  pop     r13
0x140013a33  pop     r12
0x140013a35  pop     rdi
0x140013a36  pop     rsi
0x140013a37  pop     rbx
0x140013a38  retn
```
