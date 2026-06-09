# PrnExcept::GetStringAttribute(IXMLDOMElement *,wchar_t const *,NCoreLibrary::TString *,PrnExcept::EGetAttrOpt)

- ea: `0x140014148`
- end: `0x140014402`
- name: `?GetStringAttribute@PrnExcept@@YAXPEAUIXMLDOMElement@@PEB_WPEAVTString@NCoreLibrary@@W4EGetAttrOpt@1@@Z`
- size: `698`
- prototype: `__int64 __fastcall(__int64, PrnExcept *, void **, int)`
- caller_count: `5`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x140013a40`
- `0x140013c8c`
- `0x140013ce4`
- `0x140013f2c`
- `0x140014408`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x1400123d8`
- `0x140013170`
- `0x140013250`
- `0x140013580`
- `0x140014148`
- `0x14001500c`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x14004650c`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1400142ad`
- `OLEAUT32!__imp_VariantInit` at `0x1400142ad`
- `OLEAUT32!__imp_VariantClear` at `0x14001437d`
- `OLEAUT32!__imp_VariantClear` at `0x14001437d`

## string_xrefs

- `0x1400141a4`: `pXMLElement cannot be NULL\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall PrnExcept::GetStringAttribute(__int64 a1, PrnExcept *a2, void **a3, int a4)
{
  const struct SplException::TSystemException *v8; // r8
  const struct _GUID *v9; // r9
  const struct SplException::TSystemException *v10; // r8
  const struct _GUID *v11; // r9
  const struct SplException::TSystemException *v12; // r8
  const struct _GUID *v13; // r9
  const wchar_t *v14; // rdx
  const char *v15; // r8
  unsigned int v16; // r9d
  wchar_t *v17; // rax
  NCoreLibrary::TString *v18; // rcx
  int v19; // eax
  int v20; // edx
  const char *v21; // r8
  unsigned int v22; // r9d
  const struct SplException::TSystemException *v23; // r8
  const struct _GUID *v24; // r9
  const struct SplException::TSystemException *v26; // r8
  const struct _GUID *v27; // r9
  unsigned int v28; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v29; // [rsp+28h] [rbp-D8h]
  HINSTANCE v30; // [rsp+30h] [rbp-D0h]
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG *p_pvarg; // [rsp+60h] [rbp-A0h]
  _BYTE v34[160]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+110h] [rbp+10h] BYREF

  if ( !a1 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v34, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v34,
      0x80070057,
      v8,
      v9,
      v28,
      v29,
      v30);
    SplException::TSystemException::Message((SplException::TSystemException *)v34, "pXMLElement cannot be NULL\n");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v34);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( !a2 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v34, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v34,
      0x80070057,
      v10,
      v11,
      v28,
      v29,
      v30);
    SplException::TSystemException::Message((SplException::TSystemException *)v34, "pszName cannot be NULL\n");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v34);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( !a3 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v34, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v34,
      0x80070057,
      v12,
      v13,
      v28,
      v29,
      v30);
    SplException::TSystemException::Message((SplException::TSystemException *)v34, "pString cannot be NULL\n");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v34);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v31 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  p_pvarg = &pvarg;
  VariantInit(&pvarg);
  v17 = PrnExcept::SysAllocString(a2, v14, v15, v16);
  NCoreLibrary::TAutoPtrBSTR::operator=(&v31, v17);
  if ( (*(unsigned int (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)a1 + 352LL))(a1, v31, &pvarg) )
  {
    if ( a4 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v34, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v34,
        0x80070490,
        v26,
        v27,
        v28,
        v29,
        v30);
      SplException::TSystemException::Message((SplException::TSystemException *)v34, "Attribute %ws was not found", a2);
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v34);
      throw (SplException::THResultException *)pExceptionObject;
    }
    NCoreLibrary::TString::vFree(v18, *a3);
    *a3 = &NCoreLibrary::TString::gszNullState;
  }
  else
  {
    if ( pvarg.vt != 8 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v34, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v34,
        0x80070057,
        v23,
        v24,
        v28,
        v29,
        v30);
      SplException::TSystemException::Message((SplException::TSystemException *)v34, "Attribute %ws cannot be NULL", a2);
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v34);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v19 = NCoreLibrary::TString::Update((NCoreLibrary::TString *)a3, pvarg.bstrVal);
    if ( v19 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v19, v20, v21, v22);
  }
  VariantClear(&pvarg);
  return NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(&v31);
}

```

## disassembly

```asm
0x140014148  push    rbp
0x14001414a  push    rbx
0x14001414b  push    rsi
0x14001414c  push    rdi
0x14001414d  push    r14
0x14001414f  lea     rbp, [rsp-0C0h]
0x140014157  sub     rsp, 1C0h
0x14001415e  mov     rax, cs:__security_cookie
0x140014165  xor     rax, rsp
0x140014168  mov     [rbp+0E0h+var_30], rax
0x14001416f  mov     r14d, r9d
0x140014172  mov     rbx, r8
0x140014175  mov     rdi, rdx
0x140014178  mov     rsi, rcx
0x14001417b  test    rcx, rcx
0x14001417e  jnz     short loc_1400141D4
0x140014180  xor     r8d, r8d; unsigned int
0x140014183  lea     rdx, asc_1400696D8; "-"
0x14001418a  lea     rcx, [rsp+1E0h+var_170]; this
0x14001418f  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140014194  nop
0x140014195  mov     edx, 80070057h; unsigned int
0x14001419a  lea     rcx, [rsp+1E0h+var_170]; this
0x14001419f  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400141a4  lea     rdx, aPxmlelementCan; "pXMLElement cannot be NULL\n"
0x1400141ab  lea     rcx, [rsp+1E0h+var_170]; this
0x1400141b0  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400141b5  lea     rdx, [rsp+1E0h+var_170]; struct SplException::THResultException *
0x1400141ba  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x1400141be  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400141c3  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400141ca  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x1400141ce  call    _CxxThrowException_0
0x1400141d4  test    rdi, rdi
0x1400141d7  jnz     short loc_14001422D
0x1400141d9  xor     r8d, r8d; unsigned int
0x1400141dc  lea     rdx, asc_1400696D8; "-"
0x1400141e3  lea     rcx, [rsp+1E0h+var_170]; this
0x1400141e8  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400141ed  nop
0x1400141ee  mov     edx, 80070057h; unsigned int
0x1400141f3  lea     rcx, [rsp+1E0h+var_170]; this
0x1400141f8  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400141fd  lea     rdx, aPsznameCannotB; "pszName cannot be NULL\n"
0x140014204  lea     rcx, [rsp+1E0h+var_170]; this
0x140014209  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14001420e  lea     rdx, [rsp+1E0h+var_170]; struct SplException::THResultException *
0x140014213  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x140014217  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001421c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140014223  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x140014227  call    _CxxThrowException_0
0x14001422d  test    rbx, rbx
0x140014230  jnz     short loc_140014286
0x140014232  xor     r8d, r8d; unsigned int
0x140014235  lea     rdx, asc_1400696D8; "-"
0x14001423c  lea     rcx, [rsp+1E0h+var_170]; this
0x140014241  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140014246  nop
0x140014247  mov     edx, 80070057h; unsigned int
0x14001424c  lea     rcx, [rsp+1E0h+var_170]; this
0x140014251  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140014256  lea     rdx, aPstringCannotB; "pString cannot be NULL\n"
0x14001425d  lea     rcx, [rsp+1E0h+var_170]; this
0x140014262  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140014267  lea     rdx, [rsp+1E0h+var_170]; struct SplException::THResultException *
0x14001426c  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x140014270  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140014275  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14001427c  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x140014280  call    _CxxThrowException_0
0x140014286  mov     [rsp+1E0h+var_1A0], 0
0x14001428f  xorps   xmm0, xmm0
0x140014292  xor     eax, eax
0x140014294  movups  xmmword ptr [rsp+1E0h+pvarg], xmm0
0x140014299  mov     qword ptr [rsp+1E0h+pvarg+10h], rax
0x14001429e  lea     rax, [rsp+1E0h+pvarg]
0x1400142a3  mov     [rsp+1E0h+var_180], rax
0x1400142a8  lea     rcx, [rsp+1E0h+pvarg]; pvarg
0x1400142ad  call    cs:__imp_VariantInit
0x1400142b3  nop
0x1400142b4  mov     rcx, rdi; this
0x1400142b7  call    ?SysAllocString@PrnExcept@@YAPEA_WPEB_WPEBDK@Z; PrnExcept::SysAllocString(wchar_t const *,char const *,ulong)
0x1400142bc  mov     rdx, rax
0x1400142bf  lea     rcx, [rsp+1E0h+var_1A0]
0x1400142c4  call    ??4TAutoPtrBSTR@NCoreLibrary@@QEAAPEA_WPEA_W@Z; NCoreLibrary::TAutoPtrBSTR::operator=(wchar_t *)
0x1400142c9  mov     rax, [rsi]
0x1400142cc  lea     r8, [rsp+1E0h+pvarg]
0x1400142d1  mov     rdx, [rsp+1E0h+var_1A0]
0x1400142d6  mov     rcx, rsi
0x1400142d9  mov     rax, [rax+160h]
0x1400142e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400142e5  test    eax, eax
0x1400142e7  jnz     short loc_140014361
0x1400142e9  cmp     word ptr [rsp+1E0h+pvarg], 8
0x1400142ef  jnz     short loc_14001430A
0x1400142f1  mov     rdx, qword ptr [rsp+1E0h+pvarg+8]; wchar_t *
0x1400142f6  mov     rcx, rbx; this
0x1400142f9  call    ?Update@TString@NCoreLibrary@@QEAAJPEB_W@Z; NCoreLibrary::TString::Update(wchar_t const *)
0x1400142fe  test    eax, eax
0x140014300  jns     short loc_140014378
0x140014302  mov     ecx, eax; this
0x140014304  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14001430a  xor     r8d, r8d; unsigned int
0x14001430d  lea     rdx, asc_1400696D8; "-"
0x140014314  lea     rcx, [rsp+1E0h+var_170]; this
0x140014319  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001431e  nop
0x14001431f  mov     edx, 80070057h; unsigned int
0x140014324  lea     rcx, [rsp+1E0h+var_170]; this
0x140014329  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14001432e  mov     r8, rdi
0x140014331  lea     rdx, aAttributeWsCan; "Attribute %ws cannot be NULL"
0x140014338  lea     rcx, [rsp+1E0h+var_170]; this
0x14001433d  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140014342  lea     rdx, [rsp+1E0h+var_170]; struct SplException::THResultException *
0x140014347  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x14001434b  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140014350  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140014357  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x14001435b  call    _CxxThrowException_0
0x140014361  test    r14d, r14d
0x140014364  jnz     short loc_1400143AB
0x140014366  mov     rdx, [rbx]; void *
0x140014369  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x14001436e  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PA_WA; wchar_t near * NCoreLibrary::TString::gszNullState
0x140014375  mov     [rbx], rax
0x140014378  lea     rcx, [rsp+1E0h+pvarg]; pvarg
0x14001437d  call    cs:__imp_VariantClear
0x140014383  nop
0x140014384  lea     rcx, [rsp+1E0h+var_1A0]
0x140014389  call    ?Reset@?$TGenericSP@PEA_WVTAutoPtrBSTR@NCoreLibrary@@PEA_W$0A@PEBQEA_W@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(void)
0x14001438e  mov     rcx, [rbp+0E0h+var_30]
0x140014395  xor     rcx, rsp; StackCookie
0x140014398  call    __security_check_cookie
0x14001439d  add     rsp, 1C0h
0x1400143a4  pop     r14
0x1400143a6  pop     rdi
0x1400143a7  pop     rsi
0x1400143a8  pop     rbx
0x1400143a9  pop     rbp
0x1400143aa  retn
0x1400143ab  xor     r8d, r8d; unsigned int
0x1400143ae  lea     rdx, asc_1400696D8; "-"
0x1400143b5  lea     rcx, [rsp+1E0h+var_170]; this
0x1400143ba  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400143bf  nop
0x1400143c0  mov     edx, 80070490h; unsigned int
0x1400143c5  lea     rcx, [rsp+1E0h+var_170]; this
0x1400143ca  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400143cf  mov     r8, rdi
0x1400143d2  lea     rdx, aAttributeWsWas; "Attribute %ws was not found"
0x1400143d9  lea     rcx, [rsp+1E0h+var_170]; this
0x1400143de  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400143e3  lea     rdx, [rsp+1E0h+var_170]; struct SplException::THResultException *
0x1400143e8  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x1400143ec  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400143f1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400143f8  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x1400143fc  call    _CxxThrowException_0
```
