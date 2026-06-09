# PrnExcept::LoadXmlAndGetRootNode(wchar_t const *,wchar_t const *)

- ea: `0x140014af4`
- end: `0x140014e84`
- name: `?LoadXmlAndGetRootNode@PrnExcept@@YAPEAUIXMLDOMNode@@PEB_W0@Z`
- size: `912`
- prototype: `struct IXMLDOMNode *__fastcall(wchar_t *this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012404`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x14000fa68`
- `0x14000fdf8`
- `0x1400123d8`
- `0x140013170`
- `0x140013580`
- `0x140014af4`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x14004650c`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x140014d0f`
- `OLEAUT32!__imp_VariantClear` at `0x140014d0f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140014ba1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140014ba1`

## string_xrefs

- `0x140014b4b`: `Must specify an input XML file.\n`
- `0x140014bef`: `LoadXmlAndGetRootNode() : TBstrVT construction failed to allocate memory for bstrVal.`
- `0x140014ded`: `IXMLDOMDocument->load failed. File %ws Error %u Description %ws`
- `0x140014e50`: `IXMLDOMDocument->load failed. File %ws`
- `0x140014cc7`: `IXMLDOMDocument->selectSingleNode failed. File %ws`

## pseudocode

```c
struct IXMLDOMNode *__fastcall PrnExcept::LoadXmlAndGetRootNode(wchar_t *this, const wchar_t *a2, const wchar_t *a3)
{
  const struct SplException::TSystemException *v4; // r8
  const struct _GUID *v5; // r9
  HRESULT v6; // eax
  int v7; // edx
  const char *v8; // r8
  unsigned int v9; // r9d
  const struct SplException::TSystemException *v10; // r8
  const struct _GUID *v11; // r9
  const wchar_t *v12; // rdx
  const char *v13; // r8
  unsigned int v14; // r9d
  wchar_t *v15; // rax
  const struct SplException::TSystemException *v16; // r8
  const struct _GUID *v17; // r9
  __int64 v18; // rbx
  const struct SplException::TSystemException *v20; // r8
  const struct _GUID *v21; // r9
  const struct SplException::TSystemException *v22; // r8
  const struct _GUID *v23; // r9
  unsigned int ppv; // [rsp+20h] [rbp-E0h]
  unsigned int ppva; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v26; // [rsp+28h] [rbp-D8h]
  HINSTANCE v27; // [rsp+30h] [rbp-D0h]
  __int16 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG v35; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v36[160]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v38[160]; // [rsp+1F0h] [rbp+F0h] BYREF

  if ( !this )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v36, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v36,
      0x80070057,
      v4,
      v5,
      ppv,
      v26,
      v27);
    SplException::TSystemException::Message((SplException::TSystemException *)v36, "Must specify an input XML file.\n");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v36);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v30 = 0;
  v31 = 0;
  v6 = CoCreateInstance(&GUID_88d96a06_f192_11d4_a65f_0040963251e5, 0, 1u, &IID_IXMLDOMDocument, &v30);
  if ( v6 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v6, v7, v8, v9);
  PrnExcept::TBstrVT::TBstrVT((PrnExcept::TBstrVT *)&pvarg, this);
  v28 = 0;
  if ( !pvarg.llVal )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v36, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v36,
      0x8007000E,
      v10,
      v11,
      ppva,
      v26,
      v27);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v36,
      "LoadXmlAndGetRootNode() : TBstrVT construction failed to allocate memory for bstrVal.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v36);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v35 = pvarg;
  if ( (*(unsigned int (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(*(_QWORD *)v30 + 464LL))(v30, &v35, &v28) == 1
    || !v28 )
  {
    v32 = 0;
    if ( (*(int (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v30 + 480LL))(v30, &v32) >= 0 )
    {
      v33 = 0;
      LODWORD(v29) = 0;
      if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 56LL))(v32, &v29) >= 0
        && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 72LL))(v32, &v33) >= 0 )
      {
        SplException::THResultException::THResultException((SplException::THResultException *)v36, "-", 0);
        SplException::TSystemException::InternalInit(
          (SplException::TSystemException *)v36,
          0x80004005,
          v20,
          v21,
          ppva,
          v26,
          v27);
        SplException::TSystemException::Message(
          (SplException::TSystemException *)v36,
          "IXMLDOMDocument->load failed. File %ws Error %u Description %ws",
          this,
          (unsigned int)v29,
          v33);
        SplException::THResultException::THResultException(
          (SplException::THResultException *)v38,
          (const struct SplException::THResultException *)v36);
        throw (SplException::THResultException *)v38;
      }
      NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(&v33);
    }
    SplException::THResultException::THResultException((SplException::THResultException *)pExceptionObject, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)pExceptionObject,
      0x80004005,
      v22,
      v23,
      ppva,
      v26,
      v27);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)pExceptionObject,
      "IXMLDOMDocument->load failed. File %ws",
      this);
    SplException::THResultException::THResultException(
      (SplException::THResultException *)v38,
      (const struct SplException::THResultException *)pExceptionObject);
    throw (SplException::THResultException *)v38;
  }
  v29 = 0;
  v15 = PrnExcept::SysAllocString((PrnExcept *)L"Filters", v12, v13, v14);
  NCoreLibrary::TAutoPtrBSTR::operator=(&v29, v15);
  if ( (*(unsigned int (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v30 + 296LL))(v30, v29, &v31) == 1 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v36, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v36,
      0x80004005,
      v16,
      v17,
      ppva,
      v26,
      v27);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v36,
      "IXMLDOMDocument->selectSingleNode failed. File %ws",
      this);
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v36);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v18 = v31;
  v31 = 0;
  NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(&v29);
  VariantClear(&pvarg);
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v31);
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v30);
  return (struct IXMLDOMNode *)v18;
}

```

## disassembly

```asm
0x140014af4  mov     [rsp-8+arg_8], rbx
0x140014af9  mov     [rsp-8+arg_10], rdi
0x140014afe  push    rbp
0x140014aff  lea     rbp, [rsp-1A0h]
0x140014b07  sub     rsp, 2A0h
0x140014b0e  mov     rax, cs:__security_cookie
0x140014b15  xor     rax, rsp
0x140014b18  mov     [rbp+1A0h+var_10], rax
0x140014b1f  mov     rbx, rcx
0x140014b22  xor     edi, edi
0x140014b24  test    rcx, rcx
0x140014b27  jnz     short loc_140014B79
0x140014b29  xor     r8d, r8d; unsigned int
0x140014b2c  lea     rdx, asc_1400696D8; "-"
0x140014b33  lea     rcx, [rbp+1A0h+var_1F0]; this
0x140014b37  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140014b3c  nop
0x140014b3d  mov     edx, 80070057h; unsigned int
0x140014b42  lea     rcx, [rbp+1A0h+var_1F0]; this
0x140014b46  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140014b4b  lea     rdx, aMustSpecifyAnI; "Must specify an input XML file.\n"
0x140014b52  lea     rcx, [rbp+1A0h+var_1F0]; this
0x140014b56  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140014b5b  lea     rdx, [rbp+1A0h+var_1F0]; struct SplException::THResultException *
0x140014b5f  lea     rcx, [rbp+1A0h+pExceptionObject]; this
0x140014b63  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140014b68  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140014b6f  lea     rcx, [rbp+1A0h+pExceptionObject]; pExceptionObject
0x140014b73  call    _CxxThrowException_0
0x140014b79  mov     [rsp+2A0h+var_250], rdi
0x140014b7e  mov     [rsp+2A0h+var_248], rdi
0x140014b83  lea     rax, [rsp+2A0h+var_250]
0x140014b88  mov     [rsp+2A0h+ppv], rax; unsigned int
0x140014b8d  lea     r9, IID_IXMLDOMDocument; riid
0x140014b94  xor     edx, edx; pUnkOuter
0x140014b96  lea     r8d, [rdx+1]; dwClsContext
0x140014b9a  lea     rcx, _GUID_88d96a06_f192_11d4_a65f_0040963251e5; rclsid
0x140014ba1  call    cs:__imp_CoCreateInstance
0x140014ba7  test    eax, eax
0x140014ba9  jns     short loc_140014BB3
0x140014bab  mov     ecx, eax; this
0x140014bad  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140014bb3  mov     rdx, rbx; wchar_t *
0x140014bb6  lea     rcx, [rsp+2A0h+pvarg]; this
0x140014bbb  call    ??0TBstrVT@PrnExcept@@QEAA@PEB_W@Z; PrnExcept::TBstrVT::TBstrVT(wchar_t const *)
0x140014bc0  nop
0x140014bc1  mov     [rsp+2A0h+var_260], di
0x140014bc6  cmp     qword ptr [rsp+2A0h+pvarg+8], rdi
0x140014bcb  jnz     short loc_140014C1D
0x140014bcd  xor     r8d, r8d; unsigned int
0x140014bd0  lea     rdx, asc_1400696D8; "-"
0x140014bd7  lea     rcx, [rbp+1A0h+var_1F0]; this
0x140014bdb  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140014be0  nop
0x140014be1  mov     edx, 8007000Eh; unsigned int
0x140014be6  lea     rcx, [rbp+1A0h+var_1F0]; this
0x140014bea  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140014bef  lea     rdx, aLoadxmlandgetr; "LoadXmlAndGetRootNode() : TBstrVT const"...
0x140014bf6  lea     rcx, [rbp+1A0h+var_1F0]; this
0x140014bfa  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140014bff  lea     rdx, [rbp+1A0h+var_1F0]; struct SplException::THResultException *
0x140014c03  lea     rcx, [rbp+1A0h+pExceptionObject]; this
0x140014c07  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140014c0c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140014c13  lea     rcx, [rbp+1A0h+pExceptionObject]; pExceptionObject
0x140014c17  call    _CxxThrowException_0
0x140014c1d  mov     rcx, [rsp+2A0h+var_250]
0x140014c22  movups  xmm0, xmmword ptr [rsp+2A0h+pvarg]
0x140014c27  movaps  [rbp+1A0h+var_210], xmm0
0x140014c2b  movsd   xmm1, qword ptr [rbp+1A0h+pvarg+10h]
0x140014c30  movsd   [rbp+1A0h+var_200], xmm1
0x140014c35  mov     rax, [rcx]
0x140014c38  lea     r8, [rsp+2A0h+var_260]
0x140014c3d  lea     rdx, [rbp+1A0h+var_210]
0x140014c41  mov     rax, [rax+1D0h]
0x140014c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014c4d  cmp     eax, 1
0x140014c50  jz      loc_140014D52
0x140014c56  cmp     [rsp+2A0h+var_260], di
0x140014c5b  jz      loc_140014D52
0x140014c61  mov     [rsp+2A0h+var_258], rdi
0x140014c66  lea     rcx, aFilters; "Filters"
0x140014c6d  call    ?SysAllocString@PrnExcept@@YAPEA_WPEB_WPEBDK@Z; PrnExcept::SysAllocString(wchar_t const *,char const *,ulong)
0x140014c72  mov     rdx, rax
0x140014c75  lea     rcx, [rsp+2A0h+var_258]
0x140014c7a  call    ??4TAutoPtrBSTR@NCoreLibrary@@QEAAPEA_WPEA_W@Z; NCoreLibrary::TAutoPtrBSTR::operator=(wchar_t *)
0x140014c7f  mov     rcx, [rsp+2A0h+var_250]
0x140014c84  mov     rax, [rcx]
0x140014c87  lea     r8, [rsp+2A0h+var_248]
0x140014c8c  mov     rdx, [rsp+2A0h+var_258]
0x140014c91  mov     rax, [rax+128h]
0x140014c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014c9d  cmp     eax, 1
0x140014ca0  jnz     short loc_140014CF5
0x140014ca2  xor     r8d, r8d; unsigned int
0x140014ca5  lea     rdx, asc_1400696D8; "-"
0x140014cac  lea     rcx, [rbp+1A0h+var_1F0]; this
0x140014cb0  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140014cb5  nop
0x140014cb6  mov     edx, 80004005h; unsigned int
0x140014cbb  lea     rcx, [rbp+1A0h+var_1F0]; this
0x140014cbf  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140014cc4  mov     r8, rbx
0x140014cc7  lea     rdx, aIxmldomdocumen; "IXMLDOMDocument->selectSingleNode faile"...
0x140014cce  lea     rcx, [rbp+1A0h+var_1F0]; this
0x140014cd2  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140014cd7  lea     rdx, [rbp+1A0h+var_1F0]; struct SplException::THResultException *
0x140014cdb  lea     rcx, [rbp+1A0h+pExceptionObject]; this
0x140014cdf  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140014ce4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140014ceb  lea     rcx, [rbp+1A0h+pExceptionObject]; pExceptionObject
0x140014cef  call    _CxxThrowException_0
0x140014cf5  mov     rbx, [rsp+2A0h+var_248]
0x140014cfa  mov     [rsp+2A0h+var_248], rdi
0x140014cff  lea     rcx, [rsp+2A0h+var_258]
0x140014d04  call    ?Reset@?$TGenericSP@PEA_WVTAutoPtrBSTR@NCoreLibrary@@PEA_W$0A@PEBQEA_W@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(void)
0x140014d09  nop
0x140014d0a  lea     rcx, [rsp+2A0h+pvarg]; pvarg
0x140014d0f  call    cs:__imp_VariantClear
0x140014d15  nop
0x140014d16  lea     rcx, [rsp+2A0h+var_248]
0x140014d1b  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140014d20  nop
0x140014d21  lea     rcx, [rsp+2A0h+var_250]
0x140014d26  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140014d2b  mov     rax, rbx
0x140014d2e  mov     rcx, [rbp+1A0h+var_10]
0x140014d35  xor     rcx, rsp; StackCookie
0x140014d38  call    __security_check_cookie
0x140014d3d  lea     r11, [rsp+2A0h+var_s0]
0x140014d45  mov     rbx, [r11+18h]
0x140014d49  mov     rdi, [r11+20h]
0x140014d4d  mov     rsp, r11
0x140014d50  pop     rbp
0x140014d51  retn
0x140014d52  mov     [rsp+2A0h+var_240], rdi
0x140014d57  mov     rcx, [rsp+2A0h+var_250]
0x140014d5c  mov     rax, [rcx]
0x140014d5f  lea     rdx, [rsp+2A0h+var_240]
0x140014d64  mov     rax, [rax+1E0h]
0x140014d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014d70  test    eax, eax
0x140014d72  js      loc_140014E2B
0x140014d78  mov     [rsp+2A0h+var_238], rdi
0x140014d7d  mov     dword ptr [rsp+2A0h+var_258], edi
0x140014d81  mov     rcx, [rsp+2A0h+var_240]
0x140014d86  mov     rax, [rcx]
0x140014d89  lea     rdx, [rsp+2A0h+var_258]
0x140014d8e  mov     rax, [rax+38h]
0x140014d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014d97  test    eax, eax
0x140014d99  js      loc_140014E21
0x140014d9f  mov     rcx, [rsp+2A0h+var_240]
0x140014da4  mov     rax, [rcx]
0x140014da7  lea     rdx, [rsp+2A0h+var_238]
0x140014dac  mov     rax, [rax+48h]
0x140014db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014db5  test    eax, eax
0x140014db7  js      short loc_140014E21
0x140014db9  xor     r8d, r8d; unsigned int
0x140014dbc  lea     rdx, asc_1400696D8; "-"
0x140014dc3  lea     rcx, [rbp+1A0h+var_1F0]; this
0x140014dc7  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140014dcc  nop
0x140014dcd  mov     edx, 80004005h; unsigned int
0x140014dd2  lea     rcx, [rbp+1A0h+var_1F0]; this
0x140014dd6  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140014ddb  mov     rax, [rsp+2A0h+var_238]
0x140014de0  mov     [rsp+2A0h+ppv], rax
0x140014de5  mov     r9d, dword ptr [rsp+2A0h+var_258]
0x140014dea  mov     r8, rbx
0x140014ded  lea     rdx, aIxmldomdocumen_0; "IXMLDOMDocument->load failed. File %ws "...
0x140014df4  lea     rcx, [rbp+1A0h+var_1F0]; this
0x140014df8  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140014dfd  lea     rdx, [rbp+1A0h+var_1F0]; struct SplException::THResultException *
0x140014e01  lea     rcx, [rbp+1A0h+var_B0]; this
0x140014e08  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140014e0d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140014e14  lea     rcx, [rbp+1A0h+var_B0]; pExceptionObject
0x140014e1b  call    _CxxThrowException_0
0x140014e21  lea     rcx, [rsp+2A0h+var_238]
0x140014e26  call    ?Reset@?$TGenericSP@PEA_WVTAutoPtrBSTR@NCoreLibrary@@PEA_W$0A@PEBQEA_W@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(void)
0x140014e2b  xor     r8d, r8d; unsigned int
0x140014e2e  lea     rdx, asc_1400696D8; "-"
0x140014e35  lea     rcx, [rbp+1A0h+pExceptionObject]; this
0x140014e39  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140014e3e  nop
0x140014e3f  mov     edx, 80004005h; unsigned int
0x140014e44  lea     rcx, [rbp+1A0h+pExceptionObject]; this
0x140014e48  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140014e4d  mov     r8, rbx
0x140014e50  lea     rdx, aIxmldomdocumen_1; "IXMLDOMDocument->load failed. File %ws"
0x140014e57  lea     rcx, [rbp+1A0h+pExceptionObject]; this
0x140014e5b  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140014e60  lea     rdx, [rbp+1A0h+pExceptionObject]; struct SplException::THResultException *
0x140014e64  lea     rcx, [rbp+1A0h+var_B0]; this
0x140014e6b  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140014e70  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140014e77  lea     rcx, [rbp+1A0h+var_B0]; pExceptionObject
0x140014e7e  call    _CxxThrowException_0
```
