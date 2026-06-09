# PrnExcept::ImpersonateTokenThroughScope::ImpersonateTokenThroughScope(void *)

- ea: `0x140016740`
- end: `0x14001691c`
- name: `??0ImpersonateTokenThroughScope@PrnExcept@@QEAA@PEAX@Z`
- size: `476`
- prototype: `PHANDLE __fastcall(PHANDLE TokenHandle, HANDLE Token)`
- caller_count: `7`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010800`
- `0x140011574`
- `0x140011a00`
- `0x140011ce0`
- `0x140015800`
- `0x1400163c0`
- `0x14001ac08`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x14000ea50`
- `0x140016740`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x14005c024`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x1400167c9`
- `ADVAPI32!OpenThreadToken` at `0x1400167c9`
- `ADVAPI32!SetThreadToken` at `0x1400167e9`
- `ADVAPI32!SetThreadToken` at `0x1400167e9`
- `KERNEL32!GetLastError` at `0x1400167d3`
- `KERNEL32!GetLastError` at `0x1400167d3`
- `KERNEL32!GetCurrentThread` at `0x14001678d`
- `KERNEL32!GetCurrentThread` at `0x1400167b4`
- `KERNEL32!GetCurrentThread` at `0x14001678d`
- `KERNEL32!GetCurrentThread` at `0x1400167b4`

## string_xrefs

- `0x140016896`: `OpenThreadToken failed.`
- `0x1400168ec`: `OpenThreadToken failed.`
- `0x140016840`: `SetThreadToken failed`

## pseudocode

```c
PHANDLE __fastcall PrnExcept::ImpersonateTokenThroughScope::ImpersonateTokenThroughScope(
        PHANDLE TokenHandle,
        HANDLE Token)
{
  HANDLE CurrentThread; // rax
  void **v5; // r9
  unsigned int v6; // eax
  HANDLE v7; // rax
  NCoreLibrary *v9; // rcx
  unsigned int v10; // eax
  const struct SplException::TSystemException *v11; // r8
  const struct _GUID *v12; // r9
  NCoreLibrary *v13; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v15; // r8
  const struct _GUID *v16; // r9
  NCoreLibrary *v17; // rcx
  unsigned int v18; // eax
  const struct SplException::TSystemException *v19; // r8
  const struct _GUID *v20; // r9
  unsigned int v21; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v22; // [rsp+28h] [rbp-D8h]
  HINSTANCE v23; // [rsp+30h] [rbp-D0h]
  _BYTE v24[160]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-10h] BYREF

  *TokenHandle = (void *)-1LL;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    CurrentThread = GetCurrentThread();
    v6 = SecurityHelper::OpenThreadToken(CurrentThread, 4u, TokenHandle, v5);
    if ( v6 && v6 != 1008 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v24, "-", 0);
      LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v13);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v24,
        LastErrorAsHResult,
        v15,
        v16,
        v21,
        v22,
        v23);
      SplException::TSystemException::Message((SplException::TSystemException *)v24, "OpenThreadToken failed.");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v24);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  else
  {
    v7 = GetCurrentThread();
    if ( !OpenThreadToken(v7, 4u, 1, TokenHandle) && GetLastError() != 1008 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v24, "-", 0);
      v18 = NCoreLibrary::GetLastErrorAsHResult(v17);
      SplException::TSystemException::InternalInit((SplException::TSystemException *)v24, v18, v19, v20, v21, v22, v23);
      SplException::TSystemException::Message((SplException::TSystemException *)v24, "OpenThreadToken failed.");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v24);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  if ( !SetThreadToken(0, Token) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v24, "-", 0);
    v10 = NCoreLibrary::GetLastErrorAsHResult(v9);
    SplException::TSystemException::InternalInit((SplException::TSystemException *)v24, v10, v11, v12, v21, v22, v23);
    SplException::TSystemException::Message((SplException::TSystemException *)v24, "SetThreadToken failed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v24);
    throw (SplException::THResultException *)pExceptionObject;
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x140016740  mov     [rsp-8+arg_10], rbx
0x140016745  mov     [rsp-8+arg_18], rdi
0x14001674a  push    rbp
0x14001674b  lea     rbp, [rsp-0A0h]
0x140016753  sub     rsp, 1A0h
0x14001675a  mov     rax, cs:__security_cookie
0x140016761  xor     rax, rsp
0x140016764  mov     [rbp+0A0h+var_10], rax
0x14001676b  mov     rdi, rdx
0x14001676e  mov     rbx, rcx
0x140016771  mov     [rsp+1A0h+var_160], rcx
0x140016776  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x14001677d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140016784  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140016789  test    al, al
0x14001678b  jz      short loc_1400167B4
0x14001678d  call    cs:__imp_GetCurrentThread
0x140016793  mov     r8, rbx; TokenHandle
0x140016796  mov     edx, 4; DesiredAccess
0x14001679b  mov     rcx, rax; ThreadHandle
0x14001679e  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x1400167a3  test    eax, eax
0x1400167a5  jz      short loc_1400167E4
0x1400167a7  cmp     eax, 3F0h
0x1400167ac  jnz     loc_140016870
0x1400167b2  jmp     short loc_1400167E4
0x1400167b4  call    cs:__imp_GetCurrentThread
0x1400167ba  mov     r9, rbx; TokenHandle
0x1400167bd  mov     edx, 4; DesiredAccess
0x1400167c2  lea     r8d, [rdx-3]; OpenAsSelf
0x1400167c6  mov     rcx, rax; ThreadHandle
0x1400167c9  call    cs:__imp_OpenThreadToken
0x1400167cf  test    eax, eax
0x1400167d1  jnz     short loc_1400167E4
0x1400167d3  call    cs:__imp_GetLastError
0x1400167d9  cmp     eax, 3F0h
0x1400167de  jnz     loc_1400168C6
0x1400167e4  mov     rdx, rdi; Token
0x1400167e7  xor     ecx, ecx; Thread
0x1400167e9  call    cs:__imp_SetThreadToken
0x1400167ef  test    eax, eax
0x1400167f1  jz      short loc_14001681A
0x1400167f3  mov     rax, rbx
0x1400167f6  mov     rcx, [rbp+0A0h+var_10]
0x1400167fd  xor     rcx, rsp; StackCookie
0x140016800  call    __security_check_cookie
0x140016805  lea     r11, [rsp+1A0h+var_s0]
0x14001680d  mov     rbx, [r11+20h]
0x140016811  mov     rdi, [r11+28h]
0x140016815  mov     rsp, r11
0x140016818  pop     rbp
0x140016819  retn
0x14001681a  xor     r8d, r8d; unsigned int
0x14001681d  lea     rdx, asc_1400696D8; "-"
0x140016824  lea     rcx, [rsp+1A0h+var_150]; this
0x140016829  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001682e  nop
0x14001682f  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140016834  mov     edx, eax; unsigned int
0x140016836  lea     rcx, [rsp+1A0h+var_150]; this
0x14001683b  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140016840  lea     rdx, aSetthreadtoken; "SetThreadToken failed"
0x140016847  lea     rcx, [rsp+1A0h+var_150]; this
0x14001684c  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140016851  lea     rdx, [rsp+1A0h+var_150]; struct SplException::THResultException *
0x140016856  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x14001685a  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001685f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140016866  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x14001686a  call    _CxxThrowException_0
0x140016870  xor     r8d, r8d; unsigned int
0x140016873  lea     rdx, asc_1400696D8; "-"
0x14001687a  lea     rcx, [rsp+1A0h+var_150]; this
0x14001687f  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140016884  nop
0x140016885  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14001688a  mov     edx, eax; unsigned int
0x14001688c  lea     rcx, [rsp+1A0h+var_150]; this
0x140016891  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140016896  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed."
0x14001689d  lea     rcx, [rsp+1A0h+var_150]; this
0x1400168a2  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400168a7  lea     rdx, [rsp+1A0h+var_150]; struct SplException::THResultException *
0x1400168ac  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x1400168b0  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400168b5  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400168bc  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x1400168c0  call    _CxxThrowException_0
0x1400168c6  xor     r8d, r8d; unsigned int
0x1400168c9  lea     rdx, asc_1400696D8; "-"
0x1400168d0  lea     rcx, [rsp+1A0h+var_150]; this
0x1400168d5  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400168da  nop
0x1400168db  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x1400168e0  mov     edx, eax; unsigned int
0x1400168e2  lea     rcx, [rsp+1A0h+var_150]; this
0x1400168e7  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400168ec  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed."
0x1400168f3  lea     rcx, [rsp+1A0h+var_150]; this
0x1400168f8  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400168fd  lea     rdx, [rsp+1A0h+var_150]; struct SplException::THResultException *
0x140016902  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x140016906  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001690b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140016912  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x140016916  call    _CxxThrowException_0
```
