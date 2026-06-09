# SplFilters::StreamToXpsFilter::StartOperation(void)

- ea: `0x140027370`
- end: `0x140027731`
- name: `?StartOperation@StreamToXpsFilter@SplFilters@@UEAAJXZ`
- size: `961`
- prototype: `__int64 __fastcall(SplFilters::StreamToXpsFilter *__hidden this)`
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140007ce0`
- `0x1400086f8`
- `0x14000fa68`
- `0x14000fa98`
- `0x140011728`
- `0x14001d774`
- `0x140020dc0`
- `0x140027370`
- `0x14002f364`
- `0x140035304`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`
- `0x140051450`
- `0x1400520ec`
- `0x140063010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140027474`
- `KERNEL32!WaitForSingleObject` at `0x1400275f1`
- `KERNEL32!WaitForSingleObject` at `0x140027474`
- `KERNEL32!WaitForSingleObject` at `0x1400275f1`
- `XpsPushLayer!__imp_CreateXpsPrintPackageContent` at `0x140027553`
- `XpsPushLayer!__imp_CreateXpsPrintPackageContent` at `0x140027553`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SplFilters::StreamToXpsFilter::StartOperation(
        SplFilters::StreamToXpsFilter *this,
        const char *a2,
        unsigned int a3)
{
  SplFilters::StreamToXpsFilter *v3; // rsi
  unsigned int v4; // r14d
  void *v5; // r15
  __int64 v6; // rax
  void *v7; // rcx
  NCoreLibrary *v8; // rcx
  unsigned int LastErrorAsFailHRNoBreak; // edx
  const struct SplException::TSystemException *v10; // r8
  const struct _GUID *v11; // r9
  char v12; // bl
  _QWORD *Interface; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  int v16; // eax
  int v17; // edx
  const char *v18; // r8
  unsigned int v19; // r9d
  int v20; // eax
  int v21; // edx
  const char *v22; // r8
  unsigned int v23; // r9d
  int v24; // eax
  int v25; // edx
  const char *v26; // r8
  unsigned int v27; // r9d
  __int64 v28; // rbx
  struct IImgErrorInfo **v29; // r8
  SplException *v31; // rbx
  unsigned int v32; // [rsp+20h] [rbp-208h]
  const struct win_musl::TStringEllipseBase *v33; // [rsp+28h] [rbp-200h]
  HINSTANCE v34; // [rsp+30h] [rbp-1F8h]
  __int64 v35; // [rsp+40h] [rbp-1E8h] BYREF
  NCoreLibrary::TReferenceCount *v36; // [rsp+48h] [rbp-1E0h] BYREF
  __int64 v37; // [rsp+50h] [rbp-1D8h] BYREF
  __int64 v38; // [rsp+58h] [rbp-1D0h] BYREF
  struct IImgCreateErrorInfo v39; // [rsp+60h] [rbp-1C8h] BYREF
  NCoreLibrary::TReferenceCount *v40; // [rsp+68h] [rbp-1C0h] BYREF
  __int64 v41; // [rsp+70h] [rbp-1B8h] BYREF
  _BYTE v42[8]; // [rsp+78h] [rbp-1B0h] BYREF
  SplFilters::StreamToXpsFilter *v43; // [rsp+80h] [rbp-1A8h]
  SplException::TSystemException *v44; // [rsp+88h] [rbp-1A0h] BYREF
  _BYTE v45[160]; // [rsp+90h] [rbp-198h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+130h] [rbp-F8h] BYREF
  std::bad_alloc *v47; // [rsp+1D0h] [rbp-58h] BYREF
  std::exception *v48; // [rsp+1D8h] [rbp-50h] BYREF

  try
  {
    v3 = this;
    v43 = this;
    v4 = 0;
    v39.lpVtbl = 0;
    v40 = 0;
    v5 = operator new(0x18u, a2, a3);
    if ( v5 )
    {
      v6 = *((_QWORD *)v3 + 7);
      if ( v6 == -1 )
        v6 = 0;
      *((_DWORD *)v5 + 2) = 1;
      *(_QWORD *)v5 = &PrnExcept::SharedWindowsHandle::`vftable';
      *((_QWORD *)v5 + 2) = v6;
    }
    else
    {
      v5 = 0;
    }
    v36 = 0;
    v40 = (NCoreLibrary::TReferenceCount *)v5;
    PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(&v36);
    win_dox::to_interface<IOpcUri>::resolve(&v36);
    win_dox::EnsureCloneable(v42, &v36);
    if ( *((_BYTE *)v3 + 49) && (unsigned __int64)(*((_QWORD *)v3 + 8) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_94258a397080385d6808b2748fb65100_Traceguids);
      }
      v7 = (void *)*((_QWORD *)v3 + 8);
      if ( v7 == (void *)-1LL )
        v7 = 0;
      if ( WaitForSingleObject(v7, 0xFFFFFFFF) == -1 )
      {
        SplException::THResultException::THResultException((SplException::THResultException *)v45, "-", 0);
        LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v8);
        SplException::TSystemException::InternalInit(
          (SplException::TSystemException *)v45,
          LastErrorAsFailHRNoBreak,
          v10,
          v11,
          v32,
          v33,
          v34);
        SplException::TSystemException::Message(
          (SplException::TSystemException *)v45,
          "StreamToXpsFilter::StartOperation() : WaitForSingleObject failed");
        SplException::THResultException::THResultException(
          (SplException::THResultException *)pExceptionObject,
          (const struct SplException::THResultException *)v45);
        throw (SplException::THResultException *)pExceptionObject;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_94258a397080385d6808b2748fb65100_Traceguids);
      }
    }
    *((_BYTE *)v3 + 72) = 1;
    v38 = 0;
    v12 = *((_BYTE *)v3 + 49);
    Interface = (_QWORD *)win_dox::Stream::GetInterface(v42, &v41);
    LOBYTE(v14) = v12;
    LOBYTE(v15) = 1;
    v16 = CreateXpsPrintPackageContent(*Interface, v15, v14, 2, &v38);
    if ( v16 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v16, v17, v18, v19);
    if ( v41 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      v41 = 0;
    }
    XpsPiboMuslConstructed::GetPackageRelationshipReceiver(*((_QWORD *)v3 + 3), &v37, v5);
    v35 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 24LL))(v38, &v35);
    if ( v20 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v20, v21, v22, v23);
    v24 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 32LL))(v35, (v37 + 32) & -(__int64)(v37 != 0));
    if ( v24 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v24, v25, v26, v27);
    v28 = *((_QWORD *)v3 + 3);
    WaitForSingleObject(*((HANDLE *)v5 + 2), 0xFFFFFFFF);
    WaitingLockedQueue<IUnknown>::CloseQueue(*(_QWORD *)(v28 + 32) + 96LL);
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v35);
    if ( v37 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v37 + 16) + 16LL))(v37 + 16);
      v37 = 0;
    }
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v38);
    win_dox::Uri::~Uri((win_dox::Uri *)v42);
    win_dox::Uri::~Uri((win_dox::Uri *)&v36);
    PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(&v40);
  }
  catch ( SplException::TSystemException *v44 )
  {
    v31 = v44;
    if ( SplException::gpfnExceptionLogger )
      SplException::gpfnExceptionLogger(v44);
    LODWORD(v35) = SplException::GetErrorInfoFromException(v31, &v39, v29);
    v4 = v35;
    if ( (int)v35 < 0 )
    {
LABEL_34:
      v3 = v43;
      if ( *((_BYTE *)v43 + 73) && !*((_BYTE *)v43 + 49) && v4 == -2142171128 )
        v4 = -2147220992;
      (*(void (__fastcall **)(_QWORD, _QWORD, struct IImgCreateErrorInfoVtbl *))(**((_QWORD **)v43 + 5) + 24LL))(
        *((_QWORD *)v43 + 5),
        v4,
        v39.lpVtbl);
    }
    else
    {
      v3 = v43;
    }
  }
  catch ( std::bad_alloc *v47 )
  {
    LODWORD(v35) = -2147024882;
    v4 = -2147024882;
    goto LABEL_34;
  }
  catch ( std::exception *v48 )
  {
    LODWORD(v35) = -2147418113;
    v4 = -2147418113;
    goto LABEL_34;
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 5) + 32LL))(*((_QWORD *)v3 + 5));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_94258a397080385d6808b2748fb65100_Traceguids, v4);
  }
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v39);
  return v4;
}

```

## disassembly

```asm
0x140027370  push    rbx
0x140027372  push    rsi
0x140027373  push    rdi
0x140027374  push    r12
0x140027376  push    r14
0x140027378  push    r15
0x14002737a  sub     rsp, 1F8h
0x140027381  mov     rax, cs:__security_cookie
0x140027388  xor     rax, rsp
0x14002738b  mov     [rsp+228h+var_48], rax
0x140027393  mov     rsi, rcx
0x140027396  mov     [rsp+228h+var_1A8], rcx
0x14002739e  xor     edi, edi
0x1400273a0  mov     r14d, edi
0x1400273a3  mov     [rsp+228h+var_1C8], rdi
0x1400273a8  mov     [rsp+228h+var_1C0], rdi
0x1400273ad  lea     ebx, [rdi+18h]
0x1400273b0  mov     ecx, ebx; unsigned __int64
0x1400273b2  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1400273b7  mov     r15, rax
0x1400273ba  test    rax, rax
0x1400273bd  jz      short loc_1400273E3
0x1400273bf  mov     rax, [rsi+38h]
0x1400273c3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400273c7  cmovz   rax, rdi
0x1400273cb  mov     dword ptr [r15+8], 1
0x1400273d3  lea     rcx, ??_7SharedWindowsHandle@PrnExcept@@6B@; const PrnExcept::SharedWindowsHandle::`vftable'
0x1400273da  mov     [r15], rcx
0x1400273dd  mov     [r15+10h], rax
0x1400273e1  jmp     short loc_1400273E6
0x1400273e3  mov     r15, rdi
0x1400273e6  mov     [rsp+228h+var_1E0], rdi
0x1400273eb  mov     [rsp+228h+var_1C0], r15
0x1400273f0  lea     rcx, [rsp+228h+var_1E0]
0x1400273f5  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x1400273fa  mov     rdx, [rsi+10h]
0x1400273fe  lea     rcx, [rsp+228h+var_1E0]
0x140027403  call    ?resolve@?$to_interface@UIOpcUri@@@win_dox@@SA?AV?$scope@PEAUIOpcUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIOpcUri@@@Z; win_dox::to_interface<IOpcUri>::resolve(IOpcUri *)
0x140027408  nop
0x140027409  lea     rdx, [rsp+228h+var_1E0]
0x14002740e  lea     rcx, [rsp+228h+var_1B0]
0x140027413  call    ?EnsureCloneable@win_dox@@YA?AVStream@1@AEAV21@@Z; win_dox::EnsureCloneable(win_dox::Stream &)
0x140027418  nop
0x140027419  cmp     [rsi+31h], dil
0x14002741d  jz      loc_140027518
0x140027423  mov     rax, [rsi+40h]
0x140027427  dec     rax
0x14002742a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002742e  ja      loc_140027518
0x140027434  lea     r12, WPP_GLOBAL_Control
0x14002743b  mov     rcx, cs:WPP_GLOBAL_Control
0x140027442  cmp     rcx, r12
0x140027445  jz      short loc_140027465
0x140027447  test    byte ptr [rcx+1Ch], 8
0x14002744b  jz      short loc_140027465
0x14002744d  cmp     byte ptr [rcx+19h], 2
0x140027451  jb      short loc_140027465
0x140027453  mov     edx, ebx
0x140027455  lea     r8, WPP_94258a397080385d6808b2748fb65100_Traceguids
0x14002745c  mov     rcx, [rcx+10h]
0x140027460  call    WPP_SF_
0x140027465  mov     rcx, [rsi+40h]
0x140027469  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002746d  cmovz   rcx, rdi; hHandle
0x140027471  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140027474  call    cs:__imp_WaitForSingleObject
0x14002747a  cmp     eax, 0FFFFFFFFh
0x14002747d  jnz     short loc_1400274E9
0x14002747f  xor     r8d, r8d; unsigned int
0x140027482  lea     rdx, asc_1400696D8; "-"
0x140027489  lea     rcx, [rsp+228h+var_198]; this
0x140027491  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140027496  nop
0x140027497  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14002749c  mov     edx, eax; unsigned int
0x14002749e  lea     rcx, [rsp+228h+var_198]; this
0x1400274a6  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400274ab  lea     rdx, aStreamtoxpsfil; "StreamToXpsFilter::StartOperation() : W"...
0x1400274b2  lea     rcx, [rsp+228h+var_198]; this
0x1400274ba  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400274bf  lea     rdx, [rsp+228h+var_198]; struct SplException::THResultException *
0x1400274c7  lea     rcx, [rsp+228h+pExceptionObject]; this
0x1400274cf  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400274d4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400274db  lea     rcx, [rsp+228h+pExceptionObject]; pExceptionObject
0x1400274e3  call    _CxxThrowException_0
0x1400274e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400274f0  cmp     rcx, r12
0x1400274f3  jz      short loc_14002751F
0x1400274f5  test    byte ptr [rcx+1Ch], 8
0x1400274f9  jz      short loc_14002751F
0x1400274fb  cmp     byte ptr [rcx+19h], 2
0x1400274ff  jb      short loc_14002751F
0x140027501  mov     edx, 19h
0x140027506  lea     r8, WPP_94258a397080385d6808b2748fb65100_Traceguids
0x14002750d  mov     rcx, [rcx+10h]
0x140027511  call    WPP_SF_
0x140027516  jmp     short loc_14002751F
0x140027518  lea     r12, WPP_GLOBAL_Control
0x14002751f  mov     byte ptr [rsi+48h], 1
0x140027523  mov     [rsp+228h+var_1D0], rdi
0x140027528  mov     bl, [rsi+31h]
0x14002752b  lea     rdx, [rsp+228h+var_1B8]
0x140027530  lea     rcx, [rsp+228h+var_1B0]
0x140027535  call    ?GetInterface@Stream@win_dox@@QEAA?AV?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::Stream::GetInterface(void)
0x14002753a  nop
0x14002753b  lea     rcx, [rsp+228h+var_1D0]
0x140027540  mov     [rsp+228h+var_208], rcx
0x140027545  mov     r9d, 2
0x14002754b  mov     r8b, bl
0x14002754e  mov     dl, 1
0x140027550  mov     rcx, [rax]
0x140027553  call    cs:__imp_CreateXpsPrintPackageContent
0x140027559  test    eax, eax
0x14002755b  jns     short loc_140027565
0x14002755d  mov     ecx, eax; this
0x14002755f  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140027565  mov     rcx, [rsp+228h+var_1B8]
0x14002756a  test    rcx, rcx
0x14002756d  jz      short loc_140027580
0x14002756f  mov     rax, [rcx]
0x140027572  mov     rax, [rax+10h]
0x140027576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002757b  mov     [rsp+228h+var_1B8], rdi
0x140027580  mov     r8, r15
0x140027583  lea     rdx, [rsp+228h+var_1D8]
0x140027588  mov     rcx, [rsi+18h]
0x14002758c  call    ?GetPackageRelationshipReceiver@XpsPiboMuslConstructed@@QEAA?AV?$scope@PEAVPiboXpsPackageReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAVSharedWindowsHandle@PrnExcept@@@Z; XpsPiboMuslConstructed::GetPackageRelationshipReceiver(PrnExcept::SharedWindowsHandle *)
0x140027591  nop
0x140027592  mov     [rsp+228h+var_1E8], rdi
0x140027597  mov     rcx, [rsp+228h+var_1D0]
0x14002759c  mov     rax, [rcx]
0x14002759f  lea     rdx, [rsp+228h+var_1E8]
0x1400275a4  mov     rax, [rax+18h]
0x1400275a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400275ad  test    eax, eax
0x1400275af  jns     short loc_1400275B8
0x1400275b1  mov     ecx, eax; this
0x1400275b3  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400275b8  mov     rcx, [rsp+228h+var_1E8]
0x1400275bd  mov     rdx, [rsp+228h+var_1D8]
0x1400275c2  mov     r8, [rcx]
0x1400275c5  lea     rax, [rdx+20h]
0x1400275c9  neg     rdx
0x1400275cc  sbb     rdx, rdx
0x1400275cf  and     rdx, rax
0x1400275d2  mov     rax, [r8+20h]
0x1400275d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400275db  test    eax, eax
0x1400275dd  jns     short loc_1400275E6
0x1400275df  mov     ecx, eax; this
0x1400275e1  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400275e6  mov     rbx, [rsi+18h]
0x1400275ea  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400275ed  mov     rcx, [r15+10h]; hHandle
0x1400275f1  call    cs:__imp_WaitForSingleObject
0x1400275f7  mov     rcx, [rbx+20h]
0x1400275fb  add     rcx, 60h ; '`'
0x1400275ff  call    ?CloseQueue@?$WaitingLockedQueue@UIUnknown@@@@QEAAXXZ; WaitingLockedQueue<IUnknown>::CloseQueue(void)
0x140027604  nop
0x140027605  lea     rcx, [rsp+228h+var_1E8]
0x14002760a  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002760f  nop
0x140027610  mov     rax, [rsp+228h+var_1D8]
0x140027615  test    rax, rax
0x140027618  jz      short loc_14002762F
0x14002761a  lea     rcx, [rax+10h]
0x14002761e  mov     rax, [rcx]
0x140027621  mov     rax, [rax+10h]
0x140027625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002762a  mov     [rsp+228h+var_1D8], rdi
0x14002762f  lea     rcx, [rsp+228h+var_1D0]
0x140027634  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140027639  nop
0x14002763a  lea     rcx, [rsp+228h+var_1B0]; this
0x14002763f  call    ??1Uri@win_dox@@QEAA@XZ; win_dox::Uri::~Uri(void)
0x140027644  nop
0x140027645  lea     rcx, [rsp+228h+var_1E0]; this
0x14002764a  call    ??1Uri@win_dox@@QEAA@XZ; win_dox::Uri::~Uri(void)
0x14002764f  nop
0x140027650  lea     rcx, [rsp+228h+var_1C0]
0x140027655  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x14002765a  nop
0x14002765b  jmp     short loc_1400276BF
0x14002765d  mov     r14d, dword ptr [rsp+228h+var_1E8]
0x140027662  xor     edi, edi
0x140027664  test    r14d, r14d
0x140027667  js      short loc_14002767C
0x140027669  mov     rsi, [rsp+228h+var_1A8]
0x140027671  jmp     short loc_1400276B8
0x140027673  jmp     short $+2
0x140027675  mov     r14d, dword ptr [rsp+228h+var_1E8]
0x14002767a  xor     edi, edi
0x14002767c  mov     rsi, [rsp+228h+var_1A8]
0x140027684  cmp     [rsi+49h], dil
0x140027688  jz      short loc_1400276A0
0x14002768a  cmp     [rsi+31h], dil
0x14002768e  jnz     short loc_1400276A0
0x140027690  mov     eax, 80040200h
0x140027695  cmp     r14d, 80511008h
0x14002769c  cmovz   r14d, eax
0x1400276a0  mov     rcx, [rsi+28h]
0x1400276a4  mov     rax, [rcx]
0x1400276a7  mov     r8, [rsp+228h+var_1C8]
0x1400276ac  mov     edx, r14d
0x1400276af  mov     rax, [rax+18h]
0x1400276b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400276b8  lea     r12, WPP_GLOBAL_Control
0x1400276bf  mov     rcx, [rsi+28h]
0x1400276c3  mov     rax, [rcx]
0x1400276c6  mov     rax, [rax+20h]
0x1400276ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400276cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400276d6  cmp     rcx, r12
0x1400276d9  jz      short loc_140027703
0x1400276db  test    dword ptr [rcx+1Ch], 200h
0x1400276e2  jz      short loc_140027703
0x1400276e4  cmp     byte ptr [rcx+19h], 3
0x1400276e8  jb      short loc_140027703
0x1400276ea  mov     edx, 1Ah
0x1400276ef  mov     r9d, r14d
0x1400276f2  lea     r8, WPP_94258a397080385d6808b2748fb65100_Traceguids
0x1400276f9  mov     rcx, [rcx+10h]
0x1400276fd  call    WPP_SF_d
0x140027702  nop
0x140027703  lea     rcx, [rsp+228h+var_1C8]
0x140027708  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002770d  mov     eax, r14d
0x140027710  mov     rcx, [rsp+228h+var_48]
0x140027718  xor     rcx, rsp; StackCookie
0x14002771b  call    __security_check_cookie
0x140027720  add     rsp, 1F8h
0x140027727  pop     r15
0x140027729  pop     r14
0x14002772b  pop     r12
0x14002772d  pop     rdi
0x14002772e  pop     rsi
0x14002772f  pop     rbx
0x140027730  retn
```
