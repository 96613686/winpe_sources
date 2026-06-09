# NFrameCommon::IsControlAllowed(ulong,void *)

- ea: `0x14000b500`
- end: `0x14000b755`
- name: `?IsControlAllowed@NFrameCommon@@YAHKPEAX@Z`
- size: `597`
- prototype: `int(NFrameCommon *__hidden this, unsigned int, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001026c`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x1400071e8`
- `0x14000b500`
- `0x14000ea50`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x14005c024`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x14000b5b3`
- `ADVAPI32!OpenThreadToken` at `0x14000b5b3`
- `ADVAPI32!MapGenericMask` at `0x14000b5cd`
- `ADVAPI32!MapGenericMask` at `0x14000b5cd`
- `ADVAPI32!AccessCheck` at `0x14000b619`
- `ADVAPI32!AccessCheck` at `0x14000b619`
- `KERNEL32!GetCurrentThread` at `0x14000b578`
- `KERNEL32!GetCurrentThread` at `0x14000b59c`
- `KERNEL32!GetCurrentThread` at `0x14000b578`
- `KERNEL32!GetCurrentThread` at `0x14000b59c`

## string_xrefs

- `0x14000b6d5`: `GetCurrentThread failed.`
- `0x14000b727`: `GetCurrentThread failed.`
- `0x14000b67b`: `AccessCheck failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NFrameCommon::IsControlAllowed(NFrameCommon *this, void *a2, void *a3)
{
  HANDLE CurrentThread; // rax
  void **v5; // r9
  int v6; // ebx
  HANDLE v7; // rax
  void *v8; // rdx
  unsigned int v9; // ebx
  NCoreLibrary *v11; // rcx
  unsigned int v12; // eax
  const struct SplException::TSystemException *v13; // r8
  const struct _GUID *v14; // r9
  const struct SplException::TSystemException *v15; // r8
  const struct _GUID *v16; // r9
  NCoreLibrary *v17; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v19; // r8
  const struct _GUID *v20; // r9
  unsigned int PrivilegeSet; // [rsp+20h] [rbp-E0h]
  unsigned int PrivilegeSeta; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *PrivilegeSetLength; // [rsp+28h] [rbp-D8h]
  const struct win_musl::TStringEllipseBase *PrivilegeSetLengtha; // [rsp+28h] [rbp-D8h]
  HINSTANCE GrantedAccess; // [rsp+30h] [rbp-D0h]
  HINSTANCE GrantedAccessa; // [rsp+30h] [rbp-D0h]
  DWORD AccessMask[4]; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL AccessStatus; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v30; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v31; // [rsp+64h] [rbp-9Ch] BYREF
  struct _PRIVILEGE_SET v32; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v33[160]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+120h] [rbp+20h] BYREF

  AccessMask[0] = 0x10000000;
  AccessStatus = 0;
  v30 = 0;
  v31 = 20;
  TokenHandle = (void *)-1LL;
  memset(&v32, 0, sizeof(v32));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    CurrentThread = GetCurrentThread();
    v6 = SecurityHelper::OpenThreadToken(CurrentThread, 8u, &TokenHandle, v5);
    if ( v6 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v33, "-", 0);
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v33,
        v6,
        v15,
        v16,
        PrivilegeSet,
        PrivilegeSetLength,
        GrantedAccess);
      SplException::TSystemException::Message((SplException::TSystemException *)v33, "GetCurrentThread failed.");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v33);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  else
  {
    v7 = GetCurrentThread();
    if ( !OpenThreadToken(v7, 8u, 1, &TokenHandle) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v33, "-", 0);
      LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v17);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v33,
        LastErrorAsHResult,
        v19,
        v20,
        PrivilegeSet,
        PrivilegeSetLength,
        GrantedAccess);
      SplException::TSystemException::Message((SplException::TSystemException *)v33, "GetCurrentThread failed.");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v33);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  MapGenericMask(AccessMask, &NFrameCommon::gGenericMapping);
  v8 = TokenHandle;
  if ( TokenHandle == (void *)-1LL )
    v8 = 0;
  if ( !AccessCheck(a2, v8, AccessMask[0], &NFrameCommon::gGenericMapping, &v32, &v31, &v30, &AccessStatus) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v33, "-", 0);
    v12 = NCoreLibrary::GetLastErrorAsHResult(v11);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v33,
      v12,
      v13,
      v14,
      PrivilegeSeta,
      PrivilegeSetLengtha,
      GrantedAccessa);
    SplException::TSystemException::Message((SplException::TSystemException *)v33, "AccessCheck failed.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v33);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v9 = AccessStatus;
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&TokenHandle);
  return v9;
}

```

## disassembly

```asm
0x14000b500  mov     [rsp-8+arg_0], rbx
0x14000b505  mov     [rsp-8+arg_10], rdi
0x14000b50a  push    rbp
0x14000b50b  lea     rbp, [rsp-0D0h]
0x14000b513  sub     rsp, 1D0h
0x14000b51a  mov     rax, cs:__security_cookie
0x14000b521  xor     rax, rsp
0x14000b524  mov     [rbp+0D0h+var_10], rax
0x14000b52b  mov     rdi, rdx
0x14000b52e  mov     [rsp+1D0h+AccessMask], 10000000h
0x14000b536  mov     [rsp+1D0h+var_180], 0
0x14000b53e  mov     [rsp+1D0h+var_170], 0
0x14000b546  xorps   xmm0, xmm0
0x14000b549  movdqu  xmmword ptr [rsp+1D0h+var_168.Control], xmm0
0x14000b54f  mov     [rsp+1D0h+var_16C], 14h
0x14000b557  mov     [rsp+1D0h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x14000b560  mov     [rsp+1D0h+var_168.PrivilegeCount], 0
0x14000b568  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x14000b56f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x14000b574  test    al, al
0x14000b576  jz      short loc_14000B59C
0x14000b578  call    cs:__imp_GetCurrentThread
0x14000b57e  lea     r8, [rsp+1D0h+TokenHandle]; TokenHandle
0x14000b583  mov     edx, 8; DesiredAccess
0x14000b588  mov     rcx, rax; ThreadHandle
0x14000b58b  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x14000b590  mov     ebx, eax
0x14000b592  test    eax, eax
0x14000b594  jnz     loc_14000B6A9
0x14000b59a  jmp     short loc_14000B5C1
0x14000b59c  call    cs:__imp_GetCurrentThread
0x14000b5a2  lea     r9, [rsp+1D0h+TokenHandle]; TokenHandle
0x14000b5a7  mov     edx, 8; DesiredAccess
0x14000b5ac  lea     r8d, [rdx-7]; OpenAsSelf
0x14000b5b0  mov     rcx, rax; ThreadHandle
0x14000b5b3  call    cs:__imp_OpenThreadToken
0x14000b5b9  test    eax, eax
0x14000b5bb  jz      loc_14000B703
0x14000b5c1  lea     rdx, ?gGenericMapping@NFrameCommon@@3U_GENERIC_MAPPING@@A; GenericMapping
0x14000b5c8  lea     rcx, [rsp+1D0h+AccessMask]; AccessMask
0x14000b5cd  call    cs:__imp_MapGenericMask
0x14000b5d3  mov     rdx, [rsp+1D0h+TokenHandle]
0x14000b5d8  xor     eax, eax
0x14000b5da  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14000b5de  cmovz   rdx, rax; ClientToken
0x14000b5e2  lea     rax, [rsp+1D0h+var_180]
0x14000b5e7  mov     [rsp+1D0h+AccessStatus], rax; AccessStatus
0x14000b5ec  lea     rax, [rsp+1D0h+var_170]
0x14000b5f1  mov     [rsp+1D0h+GrantedAccess], rax; HINSTANCE
0x14000b5f6  lea     rax, [rsp+1D0h+var_16C]
0x14000b5fb  mov     [rsp+1D0h+PrivilegeSetLength], rax; struct win_musl::TStringEllipseBase *
0x14000b600  lea     rax, [rsp+1D0h+var_168]
0x14000b605  mov     [rsp+1D0h+PrivilegeSet], rax; unsigned int
0x14000b60a  lea     r9, ?gGenericMapping@NFrameCommon@@3U_GENERIC_MAPPING@@A; GenericMapping
0x14000b611  mov     r8d, [rsp+1D0h+AccessMask]; DesiredAccess
0x14000b616  mov     rcx, rdi; pSecurityDescriptor
0x14000b619  call    cs:__imp_AccessCheck
0x14000b61f  test    eax, eax
0x14000b621  jz      short loc_14000B657
0x14000b623  mov     ebx, [rsp+1D0h+var_180]
0x14000b627  lea     rcx, [rsp+1D0h+TokenHandle]
0x14000b62c  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x14000b631  mov     eax, ebx
0x14000b633  mov     rcx, [rbp+0D0h+var_10]
0x14000b63a  xor     rcx, rsp; StackCookie
0x14000b63d  call    __security_check_cookie
0x14000b642  lea     r11, [rsp+1D0h+var_s0]
0x14000b64a  mov     rbx, [r11+10h]
0x14000b64e  mov     rdi, [r11+20h]
0x14000b652  mov     rsp, r11
0x14000b655  pop     rbp
0x14000b656  retn
0x14000b657  xor     r8d, r8d; unsigned int
0x14000b65a  lea     rdx, asc_1400696D8; "-"
0x14000b661  lea     rcx, [rbp+0D0h+var_150]; this
0x14000b665  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14000b66a  nop
0x14000b66b  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14000b670  mov     edx, eax; unsigned int
0x14000b672  lea     rcx, [rbp+0D0h+var_150]; this
0x14000b676  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14000b67b  lea     rdx, aAccesscheckFai; "AccessCheck failed."
0x14000b682  lea     rcx, [rbp+0D0h+var_150]; this
0x14000b686  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14000b68b  lea     rdx, [rbp+0D0h+var_150]; struct SplException::THResultException *
0x14000b68f  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x14000b693  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14000b698  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14000b69f  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x14000b6a3  call    _CxxThrowException_0
0x14000b6a9  xor     r8d, r8d; unsigned int
0x14000b6ac  lea     rdx, asc_1400696D8; "-"
0x14000b6b3  lea     rcx, [rbp+0D0h+var_150]; this
0x14000b6b7  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14000b6bc  nop
0x14000b6bd  test    ebx, ebx
0x14000b6bf  jle     short loc_14000B6CA
0x14000b6c1  movzx   ebx, bx
0x14000b6c4  or      ebx, 80070000h
0x14000b6ca  mov     edx, ebx; unsigned int
0x14000b6cc  lea     rcx, [rbp+0D0h+var_150]; this
0x14000b6d0  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14000b6d5  lea     rdx, aGetcurrentthre; "GetCurrentThread failed."
0x14000b6dc  lea     rcx, [rbp+0D0h+var_150]; this
0x14000b6e0  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14000b6e5  lea     rdx, [rbp+0D0h+var_150]; struct SplException::THResultException *
0x14000b6e9  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x14000b6ed  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14000b6f2  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14000b6f9  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x14000b6fd  call    _CxxThrowException_0
0x14000b703  xor     r8d, r8d; unsigned int
0x14000b706  lea     rdx, asc_1400696D8; "-"
0x14000b70d  lea     rcx, [rbp+0D0h+var_150]; this
0x14000b711  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14000b716  nop
0x14000b717  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14000b71c  mov     edx, eax; unsigned int
0x14000b71e  lea     rcx, [rbp+0D0h+var_150]; this
0x14000b722  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14000b727  lea     rdx, aGetcurrentthre; "GetCurrentThread failed."
0x14000b72e  lea     rcx, [rbp+0D0h+var_150]; this
0x14000b732  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14000b737  lea     rdx, [rbp+0D0h+var_150]; struct SplException::THResultException *
0x14000b73b  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x14000b73f  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14000b744  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14000b74b  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x14000b74f  call    _CxxThrowException_0
```
