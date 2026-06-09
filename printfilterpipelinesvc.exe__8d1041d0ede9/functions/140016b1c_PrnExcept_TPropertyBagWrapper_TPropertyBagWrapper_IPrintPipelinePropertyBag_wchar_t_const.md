# PrnExcept::TPropertyBagWrapper::TPropertyBagWrapper(IPrintPipelinePropertyBag *,wchar_t const *)

- ea: `0x140016b1c`
- end: `0x140016ca2`
- name: `??0TPropertyBagWrapper@PrnExcept@@QEAA@PEAUIPrintPipelinePropertyBag@@PEB_W@Z`
- size: `390`
- prototype: `PrnExcept::TPropertyBagWrapper *__fastcall(PrnExcept::TPropertyBagWrapper *this, struct IPrintPipelinePropertyBag *, WCHAR *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400135ac`
- `0x14001cf70`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x14000f9d8`
- `0x140010f04`
- `0x140011728`
- `0x140016714`
- `0x140016b1c`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x14004650c`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140016bab`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140016bab`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140016c75`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140016c75`
- `WINSPOOL!ClosePrinter` at `0x140016bcc`
- `WINSPOOL!OpenPrinterW` at `0x140016c0d`
- `WINSPOOL!OpenPrinterW` at `0x140016c0d`

## string_xrefs

- `0x140016c3d`: `TPropertyBagWrapper::TPropertyBagWrapper() OpenPrinter() failed.`

## pseudocode

```c
PrnExcept::TPropertyBagWrapper *__fastcall PrnExcept::TPropertyBagWrapper::TPropertyBagWrapper(
        PrnExcept::TPropertyBagWrapper *this,
        struct IPrintPipelinePropertyBag *a2,
        WCHAR *a3)
{
  NCoreLibrary *v6; // rcx
  int LastErrorAsFailHRNoBreak; // eax
  int v8; // edx
  const char *v9; // r8
  unsigned int v10; // r9d
  SplException *v11; // rcx
  NCoreLibrary *v12; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v14; // r8
  const struct _GUID *v15; // r9
  unsigned int v17; // [rsp+20h] [rbp-198h]
  const struct win_musl::TStringEllipseBase *v18; // [rsp+28h] [rbp-190h]
  HINSTANCE v19; // [rsp+30h] [rbp-188h]
  _BYTE v20[8]; // [rsp+40h] [rbp-178h] BYREF
  PrnExcept::TPropertyBagWrapper *v21; // [rsp+48h] [rbp-170h]
  _BYTE v22[160]; // [rsp+50h] [rbp-168h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-C8h] BYREF

  v21 = this;
  *(_QWORD *)this = &NCOMLibrary::TUnknown::`vftable';
  *((_DWORD *)this + 2) = 1852534389;
  *((_DWORD *)this + 3) = 1;
  _InterlockedIncrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
  *(_QWORD *)this = &PrnExcept::TPropertyBagWrapper::`vftable'{for `NCOMLibrary::TUnknown'};
  *((_QWORD *)this + 2) = &PrnExcept::TPropertyBagWrapper::`vftable'{for `IPrintPipelinePropertyBagX'};
  *((_DWORD *)this + 16) = 0;
  *((_DWORD *)this + 17) = 0;
  *((_DWORD *)this + 18) = -2147467259;
  *((_DWORD *)this + 17) = 0;
  *((_DWORD *)this + 16) = 0;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 24), 0x80000000) )
    LastErrorAsFailHRNoBreak = 0;
  else
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v6);
  *((_DWORD *)this + 18) = LastErrorAsFailHRNoBreak;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = ClosePrinter;
  *((_QWORD *)this + 12) = a2;
  PrnExcept::SmartAddRef<IPrintPipelineProgressReport>((__int64)a2);
  v11 = (SplException *)*((unsigned int *)this + 18);
  if ( (int)v11 < 0 )
    SplException::RealThrowFromHR(v11, v8, v9, v10);
  PrnExcept::ImpersonateClientThroughScope::ImpersonateClientThroughScope((PrnExcept::ImpersonateClientThroughScope *)v20);
  PrnExcept::SmartPrinterHandle::Free((PrnExcept::TPropertyBagWrapper *)((char *)this + 80));
  if ( !OpenPrinterW(a3, (LPHANDLE)this + 10, 0) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v22, "-", 0);
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v12);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v22,
      LastErrorAsHResult,
      v14,
      v15,
      v17,
      v18,
      v19);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v22,
      "TPropertyBagWrapper::TPropertyBagWrapper() OpenPrinter() failed.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v22);
    throw (SplException::THResultException *)pExceptionObject;
  }
  CoRevertToSelf();
  return this;
}

```

## disassembly

```asm
0x140016b1c  mov     [rsp+arg_8], rbx
0x140016b21  push    rbp
0x140016b22  push    rsi
0x140016b23  push    rdi
0x140016b24  sub     rsp, 1A0h
0x140016b2b  mov     rax, cs:__security_cookie
0x140016b32  xor     rax, rsp
0x140016b35  mov     [rsp+1B8h+var_28], rax
0x140016b3d  mov     rbp, r8
0x140016b40  mov     rsi, rdx
0x140016b43  mov     rbx, rcx
0x140016b46  mov     [rsp+1B8h+var_170], rcx
0x140016b4b  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x140016b52  mov     [rcx], rax
0x140016b55  mov     dword ptr [rcx+8], 6E6B6E75h
0x140016b5c  mov     dword ptr [rcx+0Ch], 1
0x140016b63  lock inc cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x140016b6a  lea     rax, ??_7TPropertyBagWrapper@PrnExcept@@6BTUnknown@NCOMLibrary@@@; const PrnExcept::TPropertyBagWrapper::`vftable'{for `NCOMLibrary::TUnknown'}
0x140016b71  mov     [rcx], rax
0x140016b74  lea     rax, ??_7TPropertyBagWrapper@PrnExcept@@6BIPrintPipelinePropertyBagX@@@; const PrnExcept::TPropertyBagWrapper::`vftable'{for `IPrintPipelinePropertyBagX'}
0x140016b7b  mov     [rcx+10h], rax
0x140016b7f  mov     dword ptr [rcx+40h], 0
0x140016b86  mov     dword ptr [rcx+44h], 0
0x140016b8d  mov     dword ptr [rcx+48h], 80004005h
0x140016b94  mov     dword ptr [rcx+44h], 0
0x140016b9b  mov     dword ptr [rcx+40h], 0
0x140016ba2  mov     edx, 80000000h; dwSpinCount
0x140016ba7  add     rcx, 18h; lpCriticalSection
0x140016bab  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140016bb1  test    eax, eax
0x140016bb3  jz      short loc_140016BB9
0x140016bb5  xor     eax, eax
0x140016bb7  jmp     short loc_140016BBE
0x140016bb9  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140016bbe  mov     [rbx+48h], eax
0x140016bc1  lea     rdi, [rbx+50h]
0x140016bc5  mov     qword ptr [rdi], 0
0x140016bcc  mov     rax, cs:__imp_ClosePrinter
0x140016bd3  mov     [rdi+8], rax
0x140016bd7  mov     [rbx+60h], rsi
0x140016bdb  mov     rcx, rsi
0x140016bde  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x140016be3  nop
0x140016be4  mov     ecx, [rbx+48h]; this
0x140016be7  test    ecx, ecx
0x140016be9  jns     short loc_140016BF1
0x140016beb  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140016bf1  lea     rcx, [rsp+1B8h+var_178]; this
0x140016bf6  call    ??0ImpersonateClientThroughScope@PrnExcept@@QEAA@XZ; PrnExcept::ImpersonateClientThroughScope::ImpersonateClientThroughScope(void)
0x140016bfb  nop
0x140016bfc  mov     rcx, rdi; this
0x140016bff  call    ?Free@SmartPrinterHandle@PrnExcept@@AEAAXXZ; PrnExcept::SmartPrinterHandle::Free(void)
0x140016c04  xor     r8d, r8d; pDefault
0x140016c07  mov     rdx, rdi; phPrinter
0x140016c0a  mov     rcx, rbp; pPrinterName
0x140016c0d  call    cs:__imp_OpenPrinterW
0x140016c13  test    eax, eax
0x140016c15  jnz     short loc_140016C75
0x140016c17  xor     r8d, r8d; unsigned int
0x140016c1a  lea     rdx, asc_1400696D8; "-"
0x140016c21  lea     rcx, [rsp+1B8h+var_168]; this
0x140016c26  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140016c2b  nop
0x140016c2c  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140016c31  mov     edx, eax; unsigned int
0x140016c33  lea     rcx, [rsp+1B8h+var_168]; this
0x140016c38  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140016c3d  lea     rdx, aTpropertybagwr; "TPropertyBagWrapper::TPropertyBagWrappe"...
0x140016c44  lea     rcx, [rsp+1B8h+var_168]; this
0x140016c49  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140016c4e  lea     rdx, [rsp+1B8h+var_168]; struct SplException::THResultException *
0x140016c53  lea     rcx, [rsp+1B8h+pExceptionObject]; this
0x140016c5b  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140016c60  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140016c67  lea     rcx, [rsp+1B8h+pExceptionObject]; pExceptionObject
0x140016c6f  call    _CxxThrowException_0
0x140016c75  call    cs:__imp_CoRevertToSelf
0x140016c7b  nop
0x140016c7c  mov     rax, rbx
0x140016c7f  mov     rcx, [rsp+1B8h+var_28]
0x140016c87  xor     rcx, rsp; StackCookie
0x140016c8a  call    __security_check_cookie
0x140016c8f  mov     rbx, [rsp+1B8h+arg_8]
0x140016c97  add     rsp, 1A0h
0x140016c9e  pop     rdi
0x140016c9f  pop     rsi
0x140016ca0  pop     rbp
0x140016ca1  retn
```
