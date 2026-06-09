# PrnExcept::TPropertyBag::AddPropertyX(wchar_t const *,tagVARIANT const *)

- ea: `0x140016f70`
- end: `0x1400171c1`
- name: `?AddPropertyX@TPropertyBag@PrnExcept@@UEAAXPEB_WPEBUtagVARIANT@@@Z`
- size: `593`
- prototype: `void(PrnExcept::TPropertyBag *__hidden this, const wchar_t *, const struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `17`
- tags: ``

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140014fd8`
- `0x140016970`
- `0x1400169a4`
- `0x140016f70`
- `0x1400172e8`
- `0x140017700`
- `0x140017720`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`
- `0x140046a98`
- `0x140046ab4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140017139`
- `KERNEL32!LeaveCriticalSection` at `0x140017139`

## string_xrefs

- `0x140017090`: `AddPropertyX pszName %s is already in the bag.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall PrnExcept::TPropertyBag::AddPropertyX(
        PrnExcept::TPropertyBag *this,
        const wchar_t *a2,
        const struct tagVARIANT *a3)
{
  const struct SplException::TSystemException *v6; // r8
  const struct _GUID *v7; // r9
  char *v8; // rbx
  PrnExcept::PropertyElement *v9; // rdi
  const char *v10; // rdx
  unsigned int v11; // r8d
  const struct SplException::TSystemException *v12; // r8
  const struct _GUID *v13; // r9
  NCoreLibrary::TLink *v14; // rax
  PrnExcept::PropertyElement *v15; // rax
  int v16; // edx
  const char *v17; // r8
  unsigned int v18; // r9d
  int IsValid; // eax
  struct NCoreLibrary::TLink *v20; // rcx
  const struct SplException::TSystemException *v21; // r8
  const struct _GUID *v22; // r9
  unsigned int v23; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v24; // [rsp+28h] [rbp-D8h]
  HINSTANCE v25; // [rsp+30h] [rbp-D0h]
  NCoreLibrary::TLink *v26; // [rsp+40h] [rbp-C0h] BYREF
  PrnExcept::PropertyElement *v27; // [rsp+48h] [rbp-B8h]
  char *v28; // [rsp+50h] [rbp-B0h]
  _BYTE v29[160]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+100h] [rbp+0h] BYREF

  if ( !a2 || !*a2 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v29, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v29,
      0x80070057,
      v21,
      v22,
      v23,
      v24,
      v25);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v29,
      "AddPropertyX pszName cannot be NULL or empty.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v29);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( !a3 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v29, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v29,
      0x80070057,
      v6,
      v7,
      v23,
      v24,
      v25);
    SplException::TSystemException::Message((SplException::TSystemException *)v29, "AddPropertyX pVar cannot be NULL.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v29);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v8 = (char *)this + 48;
  v28 = (char *)this + 48;
  NCoreLibrary::TCriticalSection::Enter((struct _RTL_CRITICAL_SECTION *)((char *)this + 48));
  v26 = (PrnExcept::TPropertyBag *)((char *)this + 16);
  v9 = 0;
  v27 = 0;
  if ( this != (PrnExcept::TPropertyBag *)-16LL )
  {
    v9 = (PrnExcept::PropertyElement *)*((_QWORD *)this + 4);
LABEL_7:
    v27 = v9;
  }
  while ( !(unsigned int)NCoreLibrary::TList<PrnExcept::PropertyElement>::TIterator::IsDone(&v26) )
  {
    if ( PrnExcept::PropertyElement::IsEqualPropertyName(v9, a2) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v29, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v29,
        0x80070057,
        v12,
        v13,
        v23,
        v24,
        v25);
      SplException::TSystemException::Message(
        (SplException::TSystemException *)v29,
        "AddPropertyX pszName %s is already in the bag.",
        (const char *)a2);
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v29);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( v9 )
    {
      v9 = (PrnExcept::PropertyElement *)*((_QWORD *)v9 + 2);
      goto LABEL_7;
    }
  }
  v14 = (NCoreLibrary::TLink *)operator new(0x40u, v10, v11);
  v26 = v14;
  if ( v14 )
    v15 = PrnExcept::PropertyElement::PropertyElement(v14, a2, a3);
  else
    v15 = 0;
  NCoreLibrary::TAutoPtr<PrnExcept::PropertyElement>::TAutoPtr<PrnExcept::PropertyElement>(&v26, v15);
  if ( !v26 )
  {
    IsValid = -2147024809;
    goto LABEL_23;
  }
  IsValid = NCoreLibrary::TLink::IsValid(v26);
  if ( IsValid < 0 || (IsValid = NCoreLibrary::TLink::Link(*((NCoreLibrary::TLink **)this + 5), v20), IsValid < 0) )
LABEL_23:
    SplException::RealThrowFromHR((SplException *)(unsigned int)IsValid, v16, v17, v18);
  v26 = 0;
  NCoreLibrary::TGenericSP<PrnExcept::PropertyBagElement,NCoreLibrary::TAutoPtr<PrnExcept::PropertyBagElement>,PrnExcept::PropertyBagElement *,0,PrnExcept::PropertyBagElement const *>::Reset(&v26);
  if ( !--*((_DWORD *)v8 + 11) )
    *((_DWORD *)v8 + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v8);
}

```

## disassembly

```asm
0x140016f70  push    rbp
0x140016f72  push    rbx
0x140016f73  push    rsi
0x140016f74  push    rdi
0x140016f75  push    r12
0x140016f77  push    r14
0x140016f79  push    r15
0x140016f7b  lea     rbp, [rsp-0B0h]
0x140016f83  sub     rsp, 1B0h
0x140016f8a  mov     rax, cs:__security_cookie
0x140016f91  xor     rax, rsp
0x140016f94  mov     [rbp+0E0h+var_40], rax
0x140016f9b  mov     r15, r8
0x140016f9e  mov     rsi, rdx
0x140016fa1  mov     r14, rcx
0x140016fa4  xor     r12d, r12d
0x140016fa7  test    rdx, rdx
0x140016faa  jz      loc_14001716D
0x140016fb0  cmp     [rdx], r12w
0x140016fb4  jz      loc_14001716D
0x140016fba  test    r8, r8
0x140016fbd  jnz     short loc_140017010
0x140016fbf  lea     rdx, asc_1400696D8; "-"
0x140016fc6  lea     rcx, [rsp+1E0h+var_180]; this
0x140016fcb  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140016fd0  nop
0x140016fd1  mov     edx, 80070057h; unsigned int
0x140016fd6  lea     rcx, [rsp+1E0h+var_180]; this
0x140016fdb  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140016fe0  lea     rdx, aAddpropertyxPv; "AddPropertyX pVar cannot be NULL."
0x140016fe7  lea     rcx, [rsp+1E0h+var_180]; this
0x140016fec  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140016ff1  lea     rdx, [rsp+1E0h+var_180]; struct SplException::THResultException *
0x140016ff6  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x140016ffa  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140016fff  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140017006  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x14001700a  call    _CxxThrowException_0
0x140017010  lea     rbx, [rcx+30h]
0x140017014  mov     [rsp+1E0h+var_190], rbx
0x140017019  mov     rcx, rbx; this
0x14001701c  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x140017021  nop
0x140017022  lea     rax, [r14+10h]
0x140017026  mov     [rsp+1E0h+var_1A0], rax
0x14001702b  mov     rdi, r12
0x14001702e  mov     [rsp+1E0h+var_198], r12
0x140017033  test    rax, rax
0x140017036  jz      short loc_140017041
0x140017038  mov     rdi, [rax+10h]
0x14001703c  mov     [rsp+1E0h+var_198], rdi
0x140017041  lea     rcx, [rsp+1E0h+var_1A0]
0x140017046  call    ?IsDone@TIterator@?$TList@VPropertyElement@PrnExcept@@@NCoreLibrary@@QEBAHXZ; NCoreLibrary::TList<PrnExcept::PropertyElement>::TIterator::IsDone(void)
0x14001704b  test    eax, eax
0x14001704d  jnz     short loc_1400170C0
0x14001704f  mov     rdx, rsi; wchar_t *
0x140017052  mov     rcx, rdi; this
0x140017055  call    ?IsEqualPropertyName@PropertyElement@PrnExcept@@QEAA_NPEB_W@Z; PrnExcept::PropertyElement::IsEqualPropertyName(wchar_t const *)
0x14001705a  test    al, al
0x14001705c  jnz     short loc_140017069
0x14001705e  test    rdi, rdi
0x140017061  jz      short loc_140017041
0x140017063  mov     rdi, [rdi+10h]
0x140017067  jmp     short loc_14001703C
0x140017069  xor     r8d, r8d; unsigned int
0x14001706c  lea     rdx, asc_1400696D8; "-"
0x140017073  lea     rcx, [rsp+1E0h+var_180]; this
0x140017078  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001707d  nop
0x14001707e  mov     edx, 80070057h; unsigned int
0x140017083  lea     rcx, [rsp+1E0h+var_180]; this
0x140017088  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14001708d  mov     r8, rsi
0x140017090  lea     rdx, aAddpropertyxPs_0; "AddPropertyX pszName %s is already in t"...
0x140017097  lea     rcx, [rsp+1E0h+var_180]; this
0x14001709c  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400170a1  lea     rdx, [rsp+1E0h+var_180]; struct SplException::THResultException *
0x1400170a6  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x1400170aa  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400170af  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400170b6  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x1400170ba  call    _CxxThrowException_0
0x1400170c0  mov     ecx, 40h ; '@'; unsigned __int64
0x1400170c5  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1400170ca  mov     [rsp+1E0h+var_1A0], rax
0x1400170cf  test    rax, rax
0x1400170d2  jz      short loc_1400170E4
0x1400170d4  mov     r8, r15; struct tagVARIANT *
0x1400170d7  mov     rdx, rsi; wchar_t *
0x1400170da  mov     rcx, rax; this
0x1400170dd  call    ??0PropertyElement@PrnExcept@@QEAA@PEB_WPEBUtagVARIANT@@@Z; PrnExcept::PropertyElement::PropertyElement(wchar_t const *,tagVARIANT const *)
0x1400170e2  jmp     short loc_1400170E7
0x1400170e4  mov     rax, r12
0x1400170e7  mov     rdx, rax
0x1400170ea  lea     rcx, [rsp+1E0h+var_1A0]
0x1400170ef  call    ??0?$TAutoPtr@VPropertyElement@PrnExcept@@@NCoreLibrary@@QEAA@PEAVPropertyElement@PrnExcept@@@Z; NCoreLibrary::TAutoPtr<PrnExcept::PropertyElement>::TAutoPtr<PrnExcept::PropertyElement>(PrnExcept::PropertyElement *)
0x1400170f4  nop
0x1400170f5  mov     rcx, [rsp+1E0h+var_1A0]; this
0x1400170fa  test    rcx, rcx
0x1400170fd  jz      short loc_140017160
0x1400170ff  call    ?IsValid@TLink@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TLink::IsValid(void)
0x140017104  test    eax, eax
0x140017106  js      short loc_140017165
0x140017108  mov     rdx, rcx; struct NCoreLibrary::TLink *
0x14001710b  mov     rcx, [r14+28h]; this
0x14001710f  call    ?Link@TLink@NCoreLibrary@@QEAAJPEAV12@@Z; NCoreLibrary::TLink::Link(NCoreLibrary::TLink *)
0x140017114  test    eax, eax
0x140017116  js      short loc_140017165
0x140017118  mov     [rsp+1E0h+var_1A0], r12
0x14001711d  lea     rcx, [rsp+1E0h+var_1A0]
0x140017122  call    ?Reset@?$TGenericSP@VPropertyBagElement@PrnExcept@@V?$TAutoPtr@VPropertyBagElement@PrnExcept@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<PrnExcept::PropertyBagElement,NCoreLibrary::TAutoPtr<PrnExcept::PropertyBagElement>,PrnExcept::PropertyBagElement *,0,PrnExcept::PropertyBagElement const *>::Reset(void)
0x140017127  nop
0x140017128  dec     dword ptr [rbx+2Ch]
0x14001712b  mov     eax, [rbx+2Ch]
0x14001712e  test    eax, eax
0x140017130  jnz     short loc_140017136
0x140017132  mov     [rbx+28h], r12d
0x140017136  mov     rcx, rbx; lpCriticalSection
0x140017139  call    cs:__imp_LeaveCriticalSection
0x14001713f  mov     rcx, [rbp+0E0h+var_40]
0x140017146  xor     rcx, rsp; StackCookie
0x140017149  call    __security_check_cookie
0x14001714e  add     rsp, 1B0h
0x140017155  pop     r15
0x140017157  pop     r14
0x140017159  pop     r12
0x14001715b  pop     rdi
0x14001715c  pop     rsi
0x14001715d  pop     rbx
0x14001715e  pop     rbp
0x14001715f  retn
0x140017160  mov     eax, 80070057h
0x140017165  mov     ecx, eax; this
0x140017167  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14001716d  xor     r8d, r8d; unsigned int
0x140017170  lea     rdx, asc_1400696D8; "-"
0x140017177  lea     rcx, [rsp+1E0h+var_180]; this
0x14001717c  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140017181  nop
0x140017182  mov     edx, 80070057h; unsigned int
0x140017187  lea     rcx, [rsp+1E0h+var_180]; this
0x14001718c  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140017191  lea     rdx, aAddpropertyxPs; "AddPropertyX pszName cannot be NULL or "...
0x140017198  lea     rcx, [rsp+1E0h+var_180]; this
0x14001719d  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400171a2  lea     rdx, [rsp+1E0h+var_180]; struct SplException::THResultException *
0x1400171a7  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x1400171ab  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400171b0  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400171b7  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x1400171bb  call    _CxxThrowException_0
```
