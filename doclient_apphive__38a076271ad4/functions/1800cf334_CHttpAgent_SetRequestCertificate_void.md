# CHttpAgent::_SetRequestCertificate(void *)

- ea: `0x1800cf334`
- end: `0x1800cf641`
- name: `?_SetRequestCertificate@CHttpAgent@@AEAAJPEAX@Z`
- size: `781`
- prototype: `__int64 __fastcall(CHttpAgent *__hidden this, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800ce610`

## callees

- `0x180008618`
- `0x18000933c`
- `0x180009ab4`
- `0x18000cdd0`
- `0x1800199b4`
- `0x180019c5c`
- `0x1800a1ea4`
- `0x1800cf144`
- `0x1800cf194`
- `0x1800cf334`
- `0x1800d0318`
- `0x1800d0b60`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cf59a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cf59a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cf584`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cf584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf4a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf4a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cf4b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cf4b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cf3fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cf41f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cf5c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cf5e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cf3fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cf41f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cf5c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cf5e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cf3df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cf5a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cf3df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cf5a4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800cf545`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800cf545`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800cf5bb`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800cf5bb`
- `CRYPT32!CertFreeCertificateContext` at `0x1800cf4b1`
- `CRYPT32!CertFreeCertificateContext` at `0x1800cf4b1`
- `WINHTTP!WinHttpSetOption` at `0x1800cf50b`
- `WINHTTP!WinHttpSetOption` at `0x1800cf55d`
- `WINHTTP!WinHttpSetOption` at `0x1800cf50b`
- `WINHTTP!WinHttpSetOption` at `0x1800cf55d`
- `WINHTTP!WinHttpQueryOption` at `0x1800cf486`
- `WINHTTP!WinHttpQueryOption` at `0x1800cf486`

## string_xrefs

- `0x1800cf4e7`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`
- `0x1800cf51a`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`
- `0x1800cf43e`: `CHttpAgent::_SetRequestCertificate`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHttpAgent::_SetRequestCertificate(CHttpAgent *this, void *a2)
{
  char *v3; // rsi
  char v4; // r13
  __int64 v5; // rax
  unsigned int LastError; // edi
  RTL_SRWLOCK *v7; // r14
  bool v8; // zf
  void *v9; // rbx
  int v10; // edx
  int v11; // ecx
  const char *v12; // r9
  __int64 v13; // rdx
  LPVOID *v14; // r15
  const CERT_CONTEXT *v15; // r12
  DWORD v16; // edi
  int CertificateContext; // eax
  char v18; // r15
  void *v19; // rcx
  unsigned int v20; // r8d
  const char *v21; // r9
  HANDLE v22; // rbx
  wil::details::in1diag3 *v23; // rcx
  int v25; // [rsp+20h] [rbp-50h]
  HANDLE Token; // [rsp+38h] [rbp-38h] BYREF
  __int128 v27; // [rsp+40h] [rbp-30h]
  HINTERNET hInternet; // [rsp+50h] [rbp-20h] BYREF
  _DWORD *Buffer; // [rsp+58h] [rbp-18h] BYREF
  DWORD dwBufferLength; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  hInternet = a2;
  v3 = (char *)this + 280;
  v27 = (unsigned __int64)this + 280;
  if ( (unsigned int)mtx_do_lock((char *)this + 280) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v3 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v3 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v4 = 1;
  BYTE8(v27) = 1;
  if ( *((_BYTE *)this + 387)
    || (v5 = std::map<void *,CHttpAgent::RequestCtx>::operator[]((char *)this + 24, &hInternet), *(_BYTE *)(v5 + 106)) )
  {
    LastError = -2147467260;
    goto LABEL_36;
  }
  if ( *(_BYTE *)(v5 + 104) )
  {
    LastError = -2147467259;
    goto LABEL_36;
  }
  *(_BYTE *)(v5 + 104) = 1;
  v7 = (RTL_SRWLOCK *)((char *)this + 264);
  AcquireSRWLockExclusive((PSRWLOCK)this + 33);
  if ( ++*((_DWORD *)this + 69) == 1 )
    _InterlockedExchange((volatile __int32 *)this + 68, 0);
  Token = (char *)this + 264;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 33);
  if ( !v3 )
    std::_Throw_system_error(1);
  v8 = (*((_DWORD *)v3 + 19))-- == 1;
  if ( v8 )
  {
    *((_DWORD *)v3 + 18) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)v3 + 2);
  }
  v4 = 0;
  LogMessage(4u, "CHttpAgent::_SetRequestCertificate", 0x558u, "Applying client certificate, request = 0x%p", hInternet);
  Token = (HANDLE)-1LL;
  CHttpAgent::_ImpersonateUserToken(this, &Token);
  v9 = hInternet;
  Buffer = 0;
  dwBufferLength = 8;
  if ( !WinHttpQueryOption(hInternet, 0x5Eu, &Buffer, &dwBufferLength) )
  {
    v13 = 1385;
LABEL_20:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v13,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                  v12);
    goto LABEL_21;
  }
  v14 = (LPVOID *)((char *)this + 104);
  v15 = (const CERT_CONTEXT *)*((_QWORD *)this + 13);
  if ( v15 )
  {
    v16 = GetLastError();
    CertFreeCertificateContext(v15);
    SetLastError(v16);
  }
  *v14 = 0;
  CertificateContext = FindCertificateContext(v11, v10, Buffer[2], *(_QWORD *)Buffer, (__int64)v14);
  LastError = CertificateContext;
  if ( CertificateContext >= 0 )
  {
    if ( WinHttpSetOption(hInternet, 0x2Fu, *v14, 0x28u) )
    {
      v18 = 0;
      LastError = 0;
      goto LABEL_23;
    }
    v13 = 1391;
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56C,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
    (const char *)(unsigned int)CertificateContext,
    v25);
LABEL_21:
  v18 = 1;
LABEL_23:
  v19 = Buffer;
  Buffer = 0;
  if ( v19 )
    GlobalFree(v19);
  if ( v18 && !WinHttpSetOption(v9, 0x2Fu, 0, 0) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x563, v20, v21);
  v22 = Token;
  if ( Token != (HANDLE)-1LL )
  {
    if ( !SetThreadToken(0, Token) )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    if ( v22 )
      CloseHandle(v22);
  }
  AcquireSRWLockExclusive(v7);
  v8 = HIDWORD(v7[1].Ptr)-- == 1;
  if ( v8 )
  {
    LODWORD(v7[1].Ptr) = 1;
    WakeByAddressAll(&v7[1]);
  }
  ReleaseSRWLockExclusive(v7);
LABEL_36:
  if ( v4 )
  {
    v8 = (*((_DWORD *)v3 + 19))-- == 1;
    if ( v8 )
    {
      *((_DWORD *)v3 + 18) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)v3 + 2);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800cf334  mov     [rsp-38h+arg_10], rbx
0x1800cf339  push    rbp
0x1800cf33a  push    rsi
0x1800cf33b  push    rdi
0x1800cf33c  push    r12
0x1800cf33e  push    r13
0x1800cf340  push    r14
0x1800cf342  push    r15
0x1800cf344  mov     rbp, rsp
0x1800cf347  sub     rsp, 70h
0x1800cf34b  mov     rax, cs:__security_cookie
0x1800cf352  xor     rax, rsp
0x1800cf355  mov     [rbp+var_8], rax
0x1800cf359  mov     rdi, rcx
0x1800cf35c  mov     [rbp+hInternet], rdx
0x1800cf360  xorps   xmm0, xmm0
0x1800cf363  movups  [rbp+var_30], xmm0
0x1800cf367  lea     rsi, [rcx+118h]
0x1800cf36e  mov     qword ptr [rbp+var_30], rsi
0x1800cf372  xor     r12d, r12d
0x1800cf375  mov     byte ptr [rbp+var_30+8], r12b
0x1800cf379  mov     rcx, rsi
0x1800cf37c  call    mtx_do_lock
0x1800cf381  test    eax, eax
0x1800cf383  jnz     loc_1800CF61E
0x1800cf389  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x1800cf390  jz      loc_1800CF629
0x1800cf396  mov     r13b, 1
0x1800cf399  mov     byte ptr [rbp+var_30+8], r13b
0x1800cf39d  cmp     [rdi+183h], r12b
0x1800cf3a4  jnz     loc_1800CF5CC
0x1800cf3aa  lea     rcx, [rdi+18h]
0x1800cf3ae  lea     rdx, [rbp+hInternet]
0x1800cf3b2  call    ??A?$map@PEAXURequestCtx@CHttpAgent@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXURequestCtx@CHttpAgent@@@std@@@4@@std@@QEAAAEAURequestCtx@CHttpAgent@@AEBQEAX@Z; std::map<void *,CHttpAgent::RequestCtx>::operator[](void * const &)
0x1800cf3b7  cmp     [rax+6Ah], r12b
0x1800cf3bb  jnz     loc_1800CF5CC
0x1800cf3c1  cmp     [rax+68h], r12b
0x1800cf3c5  jz      short loc_1800CF3D1
0x1800cf3c7  mov     edi, 80004005h
0x1800cf3cc  jmp     loc_1800CF5D1
0x1800cf3d1  mov     byte ptr [rax+68h], 1
0x1800cf3d5  lea     r14, [rdi+108h]
0x1800cf3dc  mov     rcx, r14; SRWLock
0x1800cf3df  call    cs:__imp_AcquireSRWLockExclusive
0x1800cf3e5  inc     dword ptr [r14+0Ch]
0x1800cf3e9  cmp     dword ptr [r14+0Ch], 1
0x1800cf3ee  jnz     short loc_1800CF3F7
0x1800cf3f0  mov     eax, r12d
0x1800cf3f3  xchg    eax, [r14+8]
0x1800cf3f7  mov     [rbp+Token], r14
0x1800cf3fb  mov     rcx, r14; SRWLock
0x1800cf3fe  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cf404  nop
0x1800cf405  test    rsi, rsi
0x1800cf408  jz      loc_1800CF613
0x1800cf40e  sub     dword ptr [rsi+4Ch], 1
0x1800cf412  jnz     short loc_1800CF425
0x1800cf414  mov     dword ptr [rsi+48h], 0FFFFFFFFh
0x1800cf41b  lea     rcx, [rsi+10h]; SRWLock
0x1800cf41f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cf425  mov     r13b, r12b
0x1800cf428  mov     rax, [rbp+hInternet]
0x1800cf42c  mov     qword ptr [rsp+70h+var_50], rax
0x1800cf431  lea     r9, aApplyingClient; "Applying client certificate, request = "...
0x1800cf438  mov     r8d, 558h; unsigned int
0x1800cf43e  lea     rdx, aChttpagentSetr; "CHttpAgent::_SetRequestCertificate"
0x1800cf445  mov     ecx, 4; unsigned __int8
0x1800cf44a  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800cf44f  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x1800cf457  lea     rdx, [rbp+Token]
0x1800cf45b  mov     rcx, rdi
0x1800cf45e  call    ?_ImpersonateUserToken@CHttpAgent@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@@Z; CHttpAgent::_ImpersonateUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800cf463  mov     rbx, [rbp+hInternet]
0x1800cf467  mov     [rbp+var_40], 1
0x1800cf46b  mov     [rbp+Buffer], r12
0x1800cf46f  mov     [rbp+dwBufferLength], 8
0x1800cf476  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x1800cf47a  lea     r8, [rbp+Buffer]; lpBuffer
0x1800cf47e  mov     edx, 5Eh ; '^'; dwOption
0x1800cf483  mov     rcx, rbx; hInternet
0x1800cf486  call    cs:__imp_WinHttpQueryOption
0x1800cf48c  test    eax, eax
0x1800cf48e  jnz     short loc_1800CF49A
0x1800cf490  mov     edx, 569h
0x1800cf495  jmp     loc_1800CF51A
0x1800cf49a  lea     r15, [rdi+68h]
0x1800cf49e  mov     r12, [r15]
0x1800cf4a1  test    r12, r12
0x1800cf4a4  jz      short loc_1800CF4BF
0x1800cf4a6  call    cs:__imp_GetLastError
0x1800cf4ac  mov     edi, eax
0x1800cf4ae  mov     rcx, r12; pCertContext
0x1800cf4b1  call    cs:__imp_CertFreeCertificateContext
0x1800cf4b7  mov     ecx, edi; dwErrCode
0x1800cf4b9  call    cs:__imp_SetLastError
0x1800cf4bf  xor     r12d, r12d
0x1800cf4c2  mov     [r15], r12
0x1800cf4c5  mov     qword ptr [rsp+70h+var_50], r15; int
0x1800cf4ca  mov     r8, [rbp+Buffer]
0x1800cf4ce  mov     r9, [r8]
0x1800cf4d1  mov     r8d, [r8+8]
0x1800cf4d5  call    FindCertificateContext
0x1800cf4da  mov     edi, eax
0x1800cf4dc  test    eax, eax
0x1800cf4de  jns     short loc_1800CF4FA
0x1800cf4e0  mov     rcx, [rbp+38h]; this
0x1800cf4e4  mov     r9d, eax; char *
0x1800cf4e7  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cf4ee  mov     edx, 56Ch; void *
0x1800cf4f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf4f8  jmp     short loc_1800CF52C
0x1800cf4fa  mov     r9d, 28h ; '('; dwBufferLength
0x1800cf500  mov     r8, [r15]; lpBuffer
0x1800cf503  lea     edx, [r9+7]; dwOption
0x1800cf507  mov     rcx, [rbp+hInternet]; hInternet
0x1800cf50b  call    cs:__imp_WinHttpSetOption
0x1800cf511  test    eax, eax
0x1800cf513  jnz     short loc_1800CF532
0x1800cf515  mov     edx, 56Fh; void *
0x1800cf51a  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cf521  mov     rcx, [rbp+38h]; this
0x1800cf525  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cf52a  mov     edi, eax
0x1800cf52c  mov     r15b, [rbp+var_40]
0x1800cf530  jmp     short loc_1800CF538
0x1800cf532  mov     r15b, r12b
0x1800cf535  mov     edi, r12d
0x1800cf538  mov     rcx, [rbp+Buffer]; hMem
0x1800cf53c  mov     [rbp+Buffer], r12
0x1800cf540  test    rcx, rcx
0x1800cf543  jz      short loc_1800CF54B
0x1800cf545  call    cs:__imp_GlobalFree
0x1800cf54b  test    r15b, r15b
0x1800cf54e  jz      short loc_1800CF575
0x1800cf550  xor     r9d, r9d; dwBufferLength
0x1800cf553  xor     r8d, r8d; lpBuffer
0x1800cf556  lea     edx, [r9+2Fh]; dwOption
0x1800cf55a  mov     rcx, rbx; hInternet
0x1800cf55d  call    cs:__imp_WinHttpSetOption
0x1800cf563  mov     rcx, [rbp+38h]; this
0x1800cf567  test    eax, eax
0x1800cf569  jnz     short loc_1800CF575
0x1800cf56b  mov     edx, 563h; void *
0x1800cf570  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800cf575  mov     rbx, [rbp+Token]
0x1800cf579  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800cf57d  jz      short loc_1800CF5A1
0x1800cf57f  mov     rdx, rbx; Token
0x1800cf582  xor     ecx, ecx; Thread
0x1800cf584  call    cs:__imp_SetThreadToken
0x1800cf58a  test    eax, eax
0x1800cf58c  jz      loc_1800CF63B
0x1800cf592  test    rbx, rbx
0x1800cf595  jz      short loc_1800CF5A1
0x1800cf597  mov     rcx, rbx; hObject
0x1800cf59a  call    cs:__imp_CloseHandle
0x1800cf5a0  nop
0x1800cf5a1  mov     rcx, r14; SRWLock
0x1800cf5a4  call    cs:__imp_AcquireSRWLockExclusive
0x1800cf5aa  add     dword ptr [r14+0Ch], 0FFFFFFFFh
0x1800cf5af  jnz     short loc_1800CF5C1
0x1800cf5b1  lea     rcx, [r14+8]; Address
0x1800cf5b5  mov     dword ptr [rcx], 1
0x1800cf5bb  call    cs:__imp_WakeByAddressAll
0x1800cf5c1  mov     rcx, r14; SRWLock
0x1800cf5c4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cf5ca  jmp     short loc_1800CF5D1
0x1800cf5cc  mov     edi, 80004004h
0x1800cf5d1  test    r13b, r13b
0x1800cf5d4  jz      short loc_1800CF5ED
0x1800cf5d6  sub     dword ptr [rsi+4Ch], 1
0x1800cf5da  jnz     short loc_1800CF5ED
0x1800cf5dc  mov     dword ptr [rsi+48h], 0FFFFFFFFh
0x1800cf5e3  lea     rcx, [rsi+10h]; SRWLock
0x1800cf5e7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cf5ed  mov     eax, edi
0x1800cf5ef  mov     rcx, [rbp+var_8]
0x1800cf5f3  xor     rcx, rsp; StackCookie
0x1800cf5f6  call    __security_check_cookie
0x1800cf5fb  mov     rbx, [rsp+70h+arg_10]
0x1800cf603  add     rsp, 70h
0x1800cf607  pop     r15
0x1800cf609  pop     r14
0x1800cf60b  pop     r13
0x1800cf60d  pop     r12
0x1800cf60f  pop     rdi
0x1800cf610  pop     rsi
0x1800cf611  pop     rbp
0x1800cf612  retn
0x1800cf613  mov     ecx, 1
0x1800cf618  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x1800cf61e  mov     ecx, 5; int
0x1800cf623  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800cf629  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x1800cf630  mov     ecx, 6; int
0x1800cf635  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800cf63b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
