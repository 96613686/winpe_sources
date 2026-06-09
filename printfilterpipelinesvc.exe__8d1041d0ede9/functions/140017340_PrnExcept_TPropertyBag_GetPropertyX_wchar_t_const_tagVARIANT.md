# PrnExcept::TPropertyBag::GetPropertyX(wchar_t const *,tagVARIANT *)

- ea: `0x140017340`
- end: `0x140017564`
- name: `?GetPropertyX@TPropertyBag@PrnExcept@@UEAAXPEB_WPEAUtagVARIANT@@@Z`
- size: `548`
- prototype: `void(PrnExcept::TPropertyBag *__hidden this, const wchar_t *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x1400172e8`
- `0x140017340`
- `0x140017700`
- `0x140017720`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x14004650c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14001748d`
- `KERNEL32!LeaveCriticalSection` at `0x14001748d`
- `OLEAUT32!__imp_VariantInit` at `0x140017441`
- `OLEAUT32!__imp_VariantInit` at `0x140017441`
- `OLEAUT32!__imp_VariantCopy` at `0x140017459`
- `OLEAUT32!__imp_VariantCopy` at `0x140017459`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall PrnExcept::TPropertyBag::GetPropertyX(
        PrnExcept::TPropertyBag *this,
        const wchar_t *a2,
        struct tagVARIANT *a3)
{
  const struct SplException::TSystemException *v6; // r8
  const struct _GUID *v7; // r9
  char *v8; // rbx
  char *v9; // rax
  __int64 v10; // rdi
  HRESULT v11; // eax
  int v12; // edx
  const char *v13; // r8
  unsigned int v14; // r9d
  const struct SplException::TSystemException *v15; // r8
  const struct _GUID *v16; // r9
  const struct SplException::TSystemException *v17; // r8
  const struct _GUID *v18; // r9
  unsigned int v19; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v20; // [rsp+28h] [rbp-D8h]
  HINSTANCE v21; // [rsp+30h] [rbp-D0h]
  char *v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h]
  char *v24; // [rsp+50h] [rbp-B0h]
  _BYTE v25[160]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+100h] [rbp+0h] BYREF

  if ( !a2 || !*a2 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v25, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v25,
      0x80070057,
      v17,
      v18,
      v19,
      v20,
      v21);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v25,
      "GetPropertyX pszName cannot be NULL or empty.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v25);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( !a3 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v25, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v25,
      0x80070057,
      v6,
      v7,
      v19,
      v20,
      v21);
    SplException::TSystemException::Message((SplException::TSystemException *)v25, "GetPropertyX pVar cannot be NULL.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v25);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v8 = (char *)this + 48;
  v24 = (char *)this + 48;
  NCoreLibrary::TCriticalSection::Enter((struct _RTL_CRITICAL_SECTION *)((char *)this + 48));
  v9 = (char *)this + 16;
  v22 = v9;
  v10 = 0;
  v23 = 0;
  if ( v9 )
  {
    v10 = *((_QWORD *)v9 + 2);
LABEL_7:
    v23 = v10;
    goto LABEL_8;
  }
  while ( 1 )
  {
LABEL_8:
    if ( (unsigned int)NCoreLibrary::TList<PrnExcept::PropertyElement>::TIterator::IsDone(&v22) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v25, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v25,
        0x80070490,
        v15,
        v16,
        v19,
        v20,
        v21);
      SplException::TSystemException::Message(
        (SplException::TSystemException *)v25,
        "GetPropertyX pszName %s not found in the bag.",
        (const char *)a2);
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v25);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( PrnExcept::PropertyElement::IsEqualPropertyName((PrnExcept::PropertyElement *)v10, a2) )
      break;
    if ( v10 )
    {
      v10 = *(_QWORD *)(v10 + 16);
      goto LABEL_7;
    }
  }
  VariantInit(a3);
  if ( *(_WORD *)(v10 + 40) == 0x4000 )
  {
    *(_OWORD *)&a3->vt = *(_OWORD *)(v10 + 40);
    a3->pRecInfo = *(IRecordInfo **)(v10 + 56);
  }
  else
  {
    v11 = VariantCopy(a3, (const VARIANTARG *)(v10 + 40));
    if ( v11 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v11, v12, v13, v14);
  }
  if ( !--*((_DWORD *)v8 + 11) )
    *((_DWORD *)v8 + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v8);
}

```

## disassembly

```asm
0x140017340  mov     [rsp-8+arg_0], rbx
0x140017345  push    rbp
0x140017346  push    rsi
0x140017347  push    rdi
0x140017348  push    r14
0x14001734a  push    r15
0x14001734c  lea     rbp, [rsp-0B0h]
0x140017354  sub     rsp, 1B0h
0x14001735b  mov     rax, cs:__security_cookie
0x140017362  xor     rax, rsp
0x140017365  mov     [rbp+0D0h+var_30], rax
0x14001736c  mov     rsi, r8
0x14001736f  mov     r14, rdx
0x140017372  mov     rdi, rcx
0x140017375  xor     r15d, r15d
0x140017378  test    rdx, rdx
0x14001737b  jz      loc_140017510
0x140017381  cmp     [rdx], r15w
0x140017385  jz      loc_140017510
0x14001738b  test    r8, r8
0x14001738e  jnz     short loc_1400173E1
0x140017390  lea     rdx, asc_1400696D8; "-"
0x140017397  lea     rcx, [rsp+1D0h+var_170]; this
0x14001739c  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400173a1  nop
0x1400173a2  mov     edx, 80070057h; unsigned int
0x1400173a7  lea     rcx, [rsp+1D0h+var_170]; this
0x1400173ac  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400173b1  lea     rdx, aGetpropertyxPv; "GetPropertyX pVar cannot be NULL."
0x1400173b8  lea     rcx, [rsp+1D0h+var_170]; this
0x1400173bd  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400173c2  lea     rdx, [rsp+1D0h+var_170]; struct SplException::THResultException *
0x1400173c7  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x1400173cb  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400173d0  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400173d7  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x1400173db  call    _CxxThrowException_0
0x1400173e1  lea     rbx, [rcx+30h]
0x1400173e5  mov     [rsp+1D0h+var_180], rbx
0x1400173ea  mov     rcx, rbx; this
0x1400173ed  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x1400173f2  nop
0x1400173f3  lea     rax, [rdi+10h]
0x1400173f7  mov     [rsp+1D0h+var_190], rax
0x1400173fc  mov     rdi, r15
0x1400173ff  mov     [rsp+1D0h+var_188], r15
0x140017404  test    rax, rax
0x140017407  jz      short loc_140017412
0x140017409  mov     rdi, [rax+10h]
0x14001740d  mov     [rsp+1D0h+var_188], rdi
0x140017412  lea     rcx, [rsp+1D0h+var_190]
0x140017417  call    ?IsDone@TIterator@?$TList@VPropertyElement@PrnExcept@@@NCoreLibrary@@QEBAHXZ; NCoreLibrary::TList<PrnExcept::PropertyElement>::TIterator::IsDone(void)
0x14001741c  test    eax, eax
0x14001741e  jnz     loc_1400174B9
0x140017424  mov     rdx, r14; wchar_t *
0x140017427  mov     rcx, rdi; this
0x14001742a  call    ?IsEqualPropertyName@PropertyElement@PrnExcept@@QEAA_NPEB_W@Z; PrnExcept::PropertyElement::IsEqualPropertyName(wchar_t const *)
0x14001742f  test    al, al
0x140017431  jnz     short loc_14001743E
0x140017433  test    rdi, rdi
0x140017436  jz      short loc_140017412
0x140017438  mov     rdi, [rdi+10h]
0x14001743c  jmp     short loc_14001740D
0x14001743e  mov     rcx, rsi; pvarg
0x140017441  call    cs:__imp_VariantInit
0x140017447  mov     eax, 4000h
0x14001744c  cmp     [rdi+28h], ax
0x140017450  jz      short loc_14001746B
0x140017452  lea     rdx, [rdi+28h]; pvargSrc
0x140017456  mov     rcx, rsi; pvargDest
0x140017459  call    cs:__imp_VariantCopy
0x14001745f  test    eax, eax
0x140017461  jns     short loc_14001747C
0x140017463  mov     ecx, eax; this
0x140017465  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14001746b  movups  xmm0, xmmword ptr [rdi+28h]
0x14001746f  movups  xmmword ptr [rsi], xmm0
0x140017472  movsd   xmm1, qword ptr [rdi+38h]
0x140017477  movsd   qword ptr [rsi+10h], xmm1
0x14001747c  dec     dword ptr [rbx+2Ch]
0x14001747f  mov     eax, [rbx+2Ch]
0x140017482  test    eax, eax
0x140017484  jnz     short loc_14001748A
0x140017486  mov     [rbx+28h], r15d
0x14001748a  mov     rcx, rbx; lpCriticalSection
0x14001748d  call    cs:__imp_LeaveCriticalSection
0x140017493  mov     rcx, [rbp+0D0h+var_30]
0x14001749a  xor     rcx, rsp; StackCookie
0x14001749d  call    __security_check_cookie
0x1400174a2  mov     rbx, [rsp+1D0h+arg_0]
0x1400174aa  add     rsp, 1B0h
0x1400174b1  pop     r15
0x1400174b3  pop     r14
0x1400174b5  pop     rdi
0x1400174b6  pop     rsi
0x1400174b7  pop     rbp
0x1400174b8  retn
0x1400174b9  xor     r8d, r8d; unsigned int
0x1400174bc  lea     rdx, asc_1400696D8; "-"
0x1400174c3  lea     rcx, [rsp+1D0h+var_170]; this
0x1400174c8  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400174cd  nop
0x1400174ce  mov     edx, 80070490h; unsigned int
0x1400174d3  lea     rcx, [rsp+1D0h+var_170]; this
0x1400174d8  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400174dd  mov     r8, r14
0x1400174e0  lea     rdx, aGetpropertyxPs; "GetPropertyX pszName %s not found in th"...
0x1400174e7  lea     rcx, [rsp+1D0h+var_170]; this
0x1400174ec  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400174f1  lea     rdx, [rsp+1D0h+var_170]; struct SplException::THResultException *
0x1400174f6  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x1400174fa  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400174ff  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140017506  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x14001750a  call    _CxxThrowException_0
0x140017510  xor     r8d, r8d; unsigned int
0x140017513  lea     rdx, asc_1400696D8; "-"
0x14001751a  lea     rcx, [rsp+1D0h+var_170]; this
0x14001751f  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140017524  nop
0x140017525  mov     edx, 80070057h; unsigned int
0x14001752a  lea     rcx, [rsp+1D0h+var_170]; this
0x14001752f  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140017534  lea     rdx, aGetpropertyxPs_0; "GetPropertyX pszName cannot be NULL or "...
0x14001753b  lea     rcx, [rsp+1D0h+var_170]; this
0x140017540  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140017545  lea     rdx, [rsp+1D0h+var_170]; struct SplException::THResultException *
0x14001754a  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x14001754e  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140017553  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14001755a  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x14001755e  call    _CxxThrowException_0
```
