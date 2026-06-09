# PrnSharedState::DllManager::LoadModule(wchar_t const *)

- ea: `0x1400459a4`
- end: `0x140045bde`
- name: `?LoadModule@DllManager@PrnSharedState@@QEAAPEAVLoadedModule@2@PEB_W@Z`
- size: `570`
- prototype: `struct PrnSharedState::LoadedModule *__fastcall(PrnSharedState::DllManager *this, const wchar_t *)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x1400135ac`
- `0x140014408`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x1400084a0`
- `0x14000fa40`
- `0x1400132e0`
- `0x1400172e8`
- `0x140045080`
- `0x14004530c`
- `0x1400459a4`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140045a69`
- `KERNEL32!LeaveCriticalSection` at `0x140045b03`
- `KERNEL32!LeaveCriticalSection` at `0x140045a69`
- `KERNEL32!LeaveCriticalSection` at `0x140045b03`

## string_xrefs

- `0x140045bae`: `DllManager::LoadModule needs valid path.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct PrnSharedState::LoadedModule *__fastcall PrnSharedState::DllManager::LoadModule(
        PrnSharedState::DllManager *this,
        const wchar_t *a2)
{
  char *v4; // rdi
  const struct SplException::TSystemException *v5; // r8
  const struct _GUID *v6; // r9
  const char *v7; // rdx
  unsigned int v8; // r8d
  PrnSharedState::LoadedModule *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rbx
  const struct SplException::TSystemException *v13; // r8
  const struct _GUID *v14; // r9
  unsigned int v15; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v16; // [rsp+28h] [rbp-D8h]
  HINSTANCE v17; // [rsp+30h] [rbp-D0h]
  PrnSharedState::LoadedModule *v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  char v22; // [rsp+60h] [rbp-A0h]
  _BYTE v23[160]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+110h] [rbp+10h] BYREF

  if ( !a2 || !*a2 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v23, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v23,
      0x80070057,
      v13,
      v14,
      v15,
      v16,
      v17);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v23,
      "DllManager::LoadModule needs valid path.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v23);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v4 = (char *)this + 24;
  v18 = (PrnSharedState::DllManager *)((char *)this + 24);
  NCoreLibrary::TCriticalSection::Enter((PrnSharedState::DllManager *)((char *)this + 24));
  if ( *((_BYTE *)this + 16) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v23, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v23,
      0x80004005,
      v5,
      v6,
      v15,
      v16,
      v17);
    SplException::TSystemException::Message((SplException::TSystemException *)v23, "Shutdown in progress!.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v23);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( !--*((_DWORD *)v4 + 11) )
    *((_DWORD *)v4 + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v4);
  v19 = 0;
  v20 = 0;
  v9 = (PrnSharedState::LoadedModule *)operator new(0x38u, v7, v8);
  v18 = v9;
  if ( v9 )
    v10 = PrnSharedState::LoadedModule::LoadedModule(v9, a2);
  else
    v10 = 0;
  v18 = 0;
  v19 = v10;
  PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(&v18);
  v18 = (PrnSharedState::LoadedModule *)v4;
  NCoreLibrary::TCriticalSection::Enter((NCoreLibrary::TCriticalSection *)v4);
  std::_Tree<std::_Tset_traits<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule>,PrnSharedState::lessLoadedModule,std::allocator<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule>>,0>>::_Emplace<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule> const &>(
    this,
    &v21,
    &v19);
  v18 = 0;
  v11 = *(_QWORD *)(v21 + 32);
  PrnExcept::SmartAddRef<PrnExcept::SharedString>(v11);
  PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(&v18);
  if ( !--*((_DWORD *)v4 + 11) )
    *((_DWORD *)v4 + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v4);
  if ( !v22
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_741966d44b4333880836975686564805_Traceguids);
  }
  v20 = 0;
  PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(&v20);
  PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(&v19);
  return (struct PrnSharedState::LoadedModule *)v11;
}

```

## disassembly

```asm
0x1400459a4  mov     [rsp-8+arg_10], rbx
0x1400459a9  push    rbp
0x1400459aa  push    rsi
0x1400459ab  push    rdi
0x1400459ac  push    r14
0x1400459ae  push    r15
0x1400459b0  lea     rbp, [rsp-0C0h]
0x1400459b8  sub     rsp, 1C0h
0x1400459bf  mov     rax, cs:__security_cookie
0x1400459c6  xor     rax, rsp
0x1400459c9  mov     [rbp+0E0h+var_30], rax
0x1400459d0  mov     r14, rdx
0x1400459d3  mov     rbx, rcx
0x1400459d6  xor     r15d, r15d
0x1400459d9  test    rdx, rdx
0x1400459dc  jz      loc_140045B8A
0x1400459e2  cmp     [rdx], r15w
0x1400459e6  jz      loc_140045B8A
0x1400459ec  lea     rdi, [rcx+18h]
0x1400459f0  mov     [rsp+1E0h+var_1A0], rdi
0x1400459f5  mov     rcx, rdi; this
0x1400459f8  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x1400459fd  nop
0x1400459fe  cmp     [rbx+10h], r15b
0x140045a02  jz      short loc_140045A58
0x140045a04  xor     r8d, r8d; unsigned int
0x140045a07  lea     rdx, asc_1400696D8; "-"
0x140045a0e  lea     rcx, [rsp+1E0h+var_170]; this
0x140045a13  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140045a18  nop
0x140045a19  mov     edx, 80004005h; unsigned int
0x140045a1e  lea     rcx, [rsp+1E0h+var_170]; this
0x140045a23  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140045a28  lea     rdx, aShutdownInProg; "Shutdown in progress!."
0x140045a2f  lea     rcx, [rsp+1E0h+var_170]; this
0x140045a34  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140045a39  lea     rdx, [rsp+1E0h+var_170]; struct SplException::THResultException *
0x140045a3e  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x140045a42  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140045a47  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140045a4e  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x140045a52  call    _CxxThrowException_0
0x140045a58  dec     dword ptr [rdi+2Ch]
0x140045a5b  mov     eax, [rdi+2Ch]
0x140045a5e  test    eax, eax
0x140045a60  jnz     short loc_140045A66
0x140045a62  mov     [rdi+28h], r15d
0x140045a66  mov     rcx, rdi; lpCriticalSection
0x140045a69  call    cs:__imp_LeaveCriticalSection
0x140045a6f  mov     [rsp+1E0h+var_198], r15
0x140045a74  mov     [rsp+1E0h+var_190], r15
0x140045a79  mov     ecx, 38h ; '8'; unsigned __int64
0x140045a7e  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x140045a83  mov     [rsp+1E0h+var_1A0], rax
0x140045a88  test    rax, rax
0x140045a8b  jz      short loc_140045A9A
0x140045a8d  mov     rdx, r14; wchar_t *
0x140045a90  mov     rcx, rax; this
0x140045a93  call    ??0LoadedModule@PrnSharedState@@QEAA@PEB_W@Z; PrnSharedState::LoadedModule::LoadedModule(wchar_t const *)
0x140045a98  jmp     short loc_140045A9D
0x140045a9a  mov     rax, r15
0x140045a9d  mov     [rsp+1E0h+var_1A0], r15
0x140045aa2  mov     [rsp+1E0h+var_198], rax
0x140045aa7  lea     rcx, [rsp+1E0h+var_1A0]
0x140045aac  call    ??$SmartRelease@VLoadedModule@PrnSharedState@@@PrnExcept@@YAXPEAPEAVLoadedModule@PrnSharedState@@@Z; PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(PrnSharedState::LoadedModule * *)
0x140045ab1  mov     [rsp+1E0h+var_1A0], rdi
0x140045ab6  mov     rcx, rdi; this
0x140045ab9  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x140045abe  nop
0x140045abf  lea     r8, [rsp+1E0h+var_198]
0x140045ac4  lea     rdx, [rsp+1E0h+var_188]
0x140045ac9  mov     rcx, rbx
0x140045acc  call    ??$_Emplace@AEBV?$TRefSmartPtr@VLoadedModule@PrnSharedState@@@PrnExcept@@@?$_Tree@V?$_Tset_traits@V?$TRefSmartPtr@VLoadedModule@PrnSharedState@@@PrnExcept@@UlessLoadedModule@PrnSharedState@@V?$allocator@V?$TRefSmartPtr@VLoadedModule@PrnSharedState@@@PrnExcept@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$TRefSmartPtr@VLoadedModule@PrnSharedState@@@PrnExcept@@PEAX@std@@_N@1@AEBV?$TRefSmartPtr@VLoadedModule@PrnSharedState@@@PrnExcept@@@Z; std::_Tree<std::_Tset_traits<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule>,PrnSharedState::lessLoadedModule,std::allocator<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule>>,0>>::_Emplace<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule> const &>(PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule> const &)
0x140045ad1  mov     rbx, [rsp+1E0h+var_188]
0x140045ad6  mov     [rsp+1E0h+var_1A0], r15
0x140045adb  mov     rbx, [rbx+20h]
0x140045adf  mov     rcx, rbx
0x140045ae2  call    ??$SmartAddRef@VSharedString@PrnExcept@@@PrnExcept@@YAXPEAVSharedString@0@@Z; PrnExcept::SmartAddRef<PrnExcept::SharedString>(PrnExcept::SharedString *)
0x140045ae7  lea     rcx, [rsp+1E0h+var_1A0]
0x140045aec  call    ??$SmartRelease@VLoadedModule@PrnSharedState@@@PrnExcept@@YAXPEAPEAVLoadedModule@PrnSharedState@@@Z; PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(PrnSharedState::LoadedModule * *)
0x140045af1  nop
0x140045af2  dec     dword ptr [rdi+2Ch]
0x140045af5  mov     eax, [rdi+2Ch]
0x140045af8  test    eax, eax
0x140045afa  jnz     short loc_140045B00
0x140045afc  mov     [rdi+28h], r15d
0x140045b00  mov     rcx, rdi; lpCriticalSection
0x140045b03  call    cs:__imp_LeaveCriticalSection
0x140045b09  cmp     [rsp+1E0h+var_180], r15b
0x140045b0e  jnz     short loc_140045B47
0x140045b10  lea     rax, WPP_GLOBAL_Control
0x140045b17  mov     rcx, cs:WPP_GLOBAL_Control
0x140045b1e  cmp     rcx, rax
0x140045b21  jz      short loc_140045B47
0x140045b23  test    byte ptr [rcx+1Ch], 8
0x140045b27  jz      short loc_140045B47
0x140045b29  cmp     byte ptr [rcx+19h], 2
0x140045b2d  jb      short loc_140045B47
0x140045b2f  mov     edx, 0Ch
0x140045b34  mov     r9, r14
0x140045b37  lea     r8, WPP_741966d44b4333880836975686564805_Traceguids
0x140045b3e  mov     rcx, [rcx+10h]
0x140045b42  call    WPP_SF_S
0x140045b47  mov     [rsp+1E0h+var_190], r15
0x140045b4c  lea     rcx, [rsp+1E0h+var_190]
0x140045b51  call    ??$SmartRelease@VLoadedModule@PrnSharedState@@@PrnExcept@@YAXPEAPEAVLoadedModule@PrnSharedState@@@Z; PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(PrnSharedState::LoadedModule * *)
0x140045b56  nop
0x140045b57  lea     rcx, [rsp+1E0h+var_198]
0x140045b5c  call    ??$SmartRelease@VLoadedModule@PrnSharedState@@@PrnExcept@@YAXPEAPEAVLoadedModule@PrnSharedState@@@Z; PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(PrnSharedState::LoadedModule * *)
0x140045b61  mov     rax, rbx
0x140045b64  mov     rcx, [rbp+0E0h+var_30]
0x140045b6b  xor     rcx, rsp; StackCookie
0x140045b6e  call    __security_check_cookie
0x140045b73  mov     rbx, [rsp+1E0h+arg_10]
0x140045b7b  add     rsp, 1C0h
0x140045b82  pop     r15
0x140045b84  pop     r14
0x140045b86  pop     rdi
0x140045b87  pop     rsi
0x140045b88  pop     rbp
0x140045b89  retn
0x140045b8a  xor     r8d, r8d; unsigned int
0x140045b8d  lea     rdx, asc_1400696D8; "-"
0x140045b94  lea     rcx, [rsp+1E0h+var_170]; this
0x140045b99  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140045b9e  nop
0x140045b9f  mov     edx, 80070057h; unsigned int
0x140045ba4  lea     rcx, [rsp+1E0h+var_170]; this
0x140045ba9  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140045bae  lea     rdx, aDllmanagerLoad; "DllManager::LoadModule needs valid path"...
0x140045bb5  lea     rcx, [rsp+1E0h+var_170]; this
0x140045bba  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140045bbf  lea     rdx, [rsp+1E0h+var_170]; struct SplException::THResultException *
0x140045bc4  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x140045bc8  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140045bcd  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140045bd4  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x140045bd8  call    _CxxThrowException_0
```
