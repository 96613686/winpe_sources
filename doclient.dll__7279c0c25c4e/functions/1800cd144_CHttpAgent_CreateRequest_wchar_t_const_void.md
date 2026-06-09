# CHttpAgent::_CreateRequest(wchar_t const *,void * *)

- ea: `0x1800cd144`
- end: `0x1800cd459`
- name: `?_CreateRequest@CHttpAgent@@AEAAJPEB_WPEAPEAX@Z`
- size: `789`
- prototype: `int(CHttpAgent *__hidden this, const wchar_t *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800ccb24`

## callees

- `0x180008618`
- `0x180009ab4`
- `0x1800199b4`
- `0x180019c5c`
- `0x1800bd69c`
- `0x1800cd144`
- `0x1800cf144`
- `0x1800d0b60`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd3f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd3f8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cd3e6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cd3e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd28c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd3c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd410`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd28c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd3c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd410`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cd271`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cd3a2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cd271`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cd3a2`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800cd3b8`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800cd3b8`
- `WINHTTP!WinHttpSetOption` at `0x1800cd2a8`
- `WINHTTP!WinHttpSetOption` at `0x1800cd312`
- `WINHTTP!WinHttpSetOption` at `0x1800cd34d`
- `WINHTTP!WinHttpSetOption` at `0x1800cd373`
- `WINHTTP!WinHttpSetOption` at `0x1800cd2a8`
- `WINHTTP!WinHttpSetOption` at `0x1800cd312`
- `WINHTTP!WinHttpSetOption` at `0x1800cd34d`
- `WINHTTP!WinHttpSetOption` at `0x1800cd373`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800cd2e4`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800cd2e4`
- `WINHTTP!WinHttpOpenRequest` at `0x1800cd22b`
- `WINHTTP!WinHttpOpenRequest` at `0x1800cd22b`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cd3d0`
- `WINHTTP!WinHttpCloseHandle` at `0x1800cd3d0`

## string_xrefs

- `0x1800cd23d`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`
- `0x1800cd386`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CHttpAgent::_CreateRequest(CHttpAgent *this, const wchar_t *a2, void **a3)
{
  char *v6; // rdi
  unsigned int LastError; // esi
  DWORD dwFlags; // eax
  const WCHAR *v9; // r8
  const char *v10; // r9
  void *v11; // r14
  char v12; // r15
  RTL_SRWLOCK *v13; // rbx
  const char *v14; // r9
  __int64 v15; // rdx
  unsigned __int8 IsEnabled; // al
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // r8
  DWORD v20; // edx
  void *v21; // r8
  bool v22; // zf
  CHttpAgent *Buffer; // [rsp+70h] [rbp-9h] BYREF
  int v25; // [rsp+78h] [rbp-1h] BYREF
  LPCWSTR ppwszAcceptTypes[2]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a3 = 0;
  v6 = (char *)this + 280;
  if ( (unsigned int)mtx_do_lock((char *)this + 280) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v6 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v6 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( *((_BYTE *)this + 387) )
  {
    LastError = -2147467260;
    goto LABEL_33;
  }
  CHttpAgent::_ImpersonateUserToken((__int64)this);
  ppwszAcceptTypes[0] = L"*/*";
  ppwszAcceptTypes[1] = 0;
  dwFlags = 0;
  if ( *((_DWORD *)this + 39) == 2 )
    dwFlags = 0x800000;
  v9 = (const WCHAR *)((char *)this + 160);
  if ( *((_QWORD *)this + 23) > 7u )
    v9 = *(const WCHAR **)v9;
  v11 = WinHttpOpenRequest(*((HINTERNET *)this + 2), a2, v9, 0, 0, ppwszAcceptTypes, dwFlags);
  if ( !v11 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2E6,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                  v10);
    goto LABEL_33;
  }
  v12 = 1;
  v13 = (RTL_SRWLOCK *)((char *)this + 264);
  AcquireSRWLockExclusive((PSRWLOCK)this + 33);
  if ( ++*((_DWORD *)this + 69) == 1 )
    _InterlockedExchange((volatile __int32 *)this + 68, 0);
  ReleaseSRWLockExclusive((PSRWLOCK)this + 33);
  Buffer = this;
  if ( WinHttpSetOption(v11, 0x2Du, &Buffer, 8u) )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CertPinningCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CertPinningCheck>::GetImpl'::`2'::impl);
    if ( WinHttpSetStatusCallback(v11, CHttpAgent::_OnStatusCallback, (16 * IsEnabled) | 0x6B4800u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
    {
      v15 = 766;
    }
    else
    {
      v25 = 0;
      if ( !WinHttpSetOption(v11, 0x6Du, &v25, 4u) )
        wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x303, v17, v18);
      v19 = (_DWORD *)((char *)this + 152);
      if ( !*((_DWORD *)this + 38) )
        goto LABEL_24;
      v20 = 31;
      if ( *v19 == 1 )
        v20 = 79;
      if ( WinHttpSetOption(v11, v20, v19, 4u) )
      {
LABEL_24:
        v21 = (void *)*((_QWORD *)this + 13);
        if ( !v21 || WinHttpSetOption(v11, 0x2Fu, v21, 0x28u) )
        {
          v12 = 0;
          *a3 = v11;
          LastError = 0;
          goto LABEL_29;
        }
        v15 = 786;
      }
      else
      {
        v15 = 778;
      }
    }
  }
  else
  {
    v15 = 751;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v15,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                v14);
LABEL_29:
  AcquireSRWLockExclusive(v13);
  v22 = HIDWORD(v13[1].Ptr)-- == 1;
  if ( v22 )
  {
    LODWORD(v13[1].Ptr) = 1;
    WakeByAddressAll(&v13[1]);
  }
  ReleaseSRWLockExclusive(v13);
  if ( v12 )
    WinHttpCloseHandle(v11);
LABEL_33:
  v22 = (*((_DWORD *)v6 + 19))-- == 1;
  if ( v22 )
  {
    *((_DWORD *)v6 + 18) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)v6 + 2);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800cd144  push    rbp
0x1800cd146  push    rbx
0x1800cd147  push    rsi
0x1800cd148  push    rdi
0x1800cd149  push    r12
0x1800cd14b  push    r14
0x1800cd14d  push    r15
0x1800cd14f  lea     rbp, [rsp-27h]
0x1800cd154  sub     rsp, 0A0h
0x1800cd15b  mov     rax, cs:__security_cookie
0x1800cd162  xor     rax, rsp
0x1800cd165  mov     [rbp+57h+var_40], rax
0x1800cd169  mov     r12, r8
0x1800cd16c  mov     rbx, rdx
0x1800cd16f  mov     rsi, rcx
0x1800cd172  mov     qword ptr [r8], 0
0x1800cd179  xorps   xmm0, xmm0
0x1800cd17c  movups  [rbp+57h+var_80], xmm0
0x1800cd180  lea     rdi, [rcx+118h]
0x1800cd187  mov     qword ptr [rbp+57h+var_80], rdi
0x1800cd18b  mov     byte ptr [rbp+57h+var_80+8], 0
0x1800cd18f  mov     rcx, rdi
0x1800cd192  call    mtx_do_lock
0x1800cd197  test    eax, eax
0x1800cd199  jnz     loc_1800CD43C
0x1800cd19f  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x1800cd1a6  jz      loc_1800CD447
0x1800cd1ac  mov     byte ptr [rbp+57h+var_80+8], 1
0x1800cd1b0  cmp     [rsi+183h], al
0x1800cd1b6  jz      short loc_1800CD1C2
0x1800cd1b8  mov     esi, 80004004h
0x1800cd1bd  jmp     loc_1800CD3FF
0x1800cd1c2  mov     [rbp+57h+Token], 0FFFFFFFFFFFFFFFFh
0x1800cd1ca  lea     rdx, [rbp+57h+Token]
0x1800cd1ce  mov     rcx, rsi
0x1800cd1d1  call    ?_ImpersonateUserToken@CHttpAgent@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@@Z; CHttpAgent::_ImpersonateUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800cd1d6  lea     rax, asc_18013CD60; "*/*"
0x1800cd1dd  mov     [rbp+57h+var_50], rax
0x1800cd1e1  mov     [rbp+57h+var_48], 0
0x1800cd1e9  xor     eax, eax
0x1800cd1eb  mov     ecx, 800000h
0x1800cd1f0  cmp     dword ptr [rsi+9Ch], 2
0x1800cd1f7  cmovz   eax, ecx
0x1800cd1fa  lea     r8, [rsi+0A0h]
0x1800cd201  cmp     qword ptr [r8+18h], 7
0x1800cd206  jbe     short loc_1800CD20B
0x1800cd208  mov     r8, [r8]; pwszObjectName
0x1800cd20b  mov     [rsp+0D0h+dwFlags], eax; dwFlags
0x1800cd20f  lea     rax, [rbp+57h+var_50]
0x1800cd213  mov     [rsp+0D0h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x1800cd218  mov     [rsp+0D0h+pwszReferrer], 0; pwszReferrer
0x1800cd221  xor     r9d, r9d; pwszVersion
0x1800cd224  mov     rdx, rbx; pwszVerb
0x1800cd227  mov     rcx, [rsi+10h]; hConnect
0x1800cd22b  call    cs:__imp_WinHttpOpenRequest
0x1800cd231  mov     r14, rax
0x1800cd234  test    rax, rax
0x1800cd237  jnz     short loc_1800CD255
0x1800cd239  mov     rcx, [rbp+5Fh]; this
0x1800cd23d  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cd244  mov     edx, 2E6h; void *
0x1800cd249  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cd24e  mov     esi, eax
0x1800cd250  jmp     loc_1800CD3D7
0x1800cd255  xorps   xmm0, xmm0
0x1800cd258  movups  [rbp+57h+var_70], xmm0
0x1800cd25c  mov     qword ptr [rbp+57h+var_70], r14
0x1800cd260  mov     r15b, 1
0x1800cd263  mov     byte ptr [rbp+57h+var_70+8], r15b
0x1800cd267  lea     rbx, [rsi+108h]
0x1800cd26e  mov     rcx, rbx; SRWLock
0x1800cd271  call    cs:__imp_AcquireSRWLockExclusive
0x1800cd277  inc     dword ptr [rbx+0Ch]
0x1800cd27a  cmp     dword ptr [rbx+0Ch], 1
0x1800cd27e  jnz     short loc_1800CD285
0x1800cd280  xor     eax, eax
0x1800cd282  xchg    eax, [rbx+8]
0x1800cd285  mov     [rbp+57h+var_90], rbx
0x1800cd289  mov     rcx, rbx; SRWLock
0x1800cd28c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cd292  nop
0x1800cd293  mov     [rbp+57h+Buffer], rsi
0x1800cd297  mov     r9d, 8; dwBufferLength
0x1800cd29d  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800cd2a1  lea     edx, [r9+25h]; dwOption
0x1800cd2a5  mov     rcx, r14; hInternet
0x1800cd2a8  call    cs:__imp_WinHttpSetOption
0x1800cd2ae  test    eax, eax
0x1800cd2b0  jnz     short loc_1800CD2BC
0x1800cd2b2  mov     edx, 2EFh
0x1800cd2b7  jmp     loc_1800CD382
0x1800cd2bc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CertPinningCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CertPinningCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CertPinningCheck> `wil::Feature<__WilFeatureTraits_Feature_CertPinningCheck>::GetImpl(void)'::`2'::impl
0x1800cd2c3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CertPinningCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CertPinningCheck>::__private_IsEnabled(void)
0x1800cd2c8  movzx   r8d, al
0x1800cd2cc  shl     r8d, 4
0x1800cd2d0  or      r8d, 6B4800h; dwNotificationFlags
0x1800cd2d7  xor     r9d, r9d; dwReserved
0x1800cd2da  lea     rdx, ?_OnStatusCallback@CHttpAgent@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x1800cd2e1  mov     rcx, r14; hInternet
0x1800cd2e4  call    cs:__imp_WinHttpSetStatusCallback
0x1800cd2ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800cd2ee  jnz     short loc_1800CD2FA
0x1800cd2f0  mov     edx, 2FEh
0x1800cd2f5  jmp     loc_1800CD382
0x1800cd2fa  mov     [rbp+57h+var_58], 0
0x1800cd301  mov     r9d, 4; dwBufferLength
0x1800cd307  lea     r8, [rbp+57h+var_58]; lpBuffer
0x1800cd30b  lea     edx, [r9+69h]; dwOption
0x1800cd30f  mov     rcx, r14; hInternet
0x1800cd312  call    cs:__imp_WinHttpSetOption
0x1800cd318  mov     rcx, [rbp+5Fh]; this
0x1800cd31c  test    eax, eax
0x1800cd31e  jnz     short loc_1800CD32A
0x1800cd320  mov     edx, 303h; void *
0x1800cd325  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800cd32a  lea     r8, [rsi+98h]; lpBuffer
0x1800cd331  cmp     dword ptr [r8], 0
0x1800cd335  jz      short loc_1800CD35E
0x1800cd337  mov     edx, 1Fh
0x1800cd33c  lea     eax, [rdx+30h]
0x1800cd33f  cmp     dword ptr [r8], 1
0x1800cd343  cmovz   edx, eax; dwOption
0x1800cd346  lea     r9d, [rax-4Bh]; dwBufferLength
0x1800cd34a  mov     rcx, r14; hInternet
0x1800cd34d  call    cs:__imp_WinHttpSetOption
0x1800cd353  test    eax, eax
0x1800cd355  jnz     short loc_1800CD35E
0x1800cd357  mov     edx, 30Ah
0x1800cd35c  jmp     short loc_1800CD382
0x1800cd35e  mov     r8, [rsi+68h]; lpBuffer
0x1800cd362  test    r8, r8
0x1800cd365  jz      short loc_1800CD396
0x1800cd367  mov     edx, 2Fh ; '/'; dwOption
0x1800cd36c  lea     r9d, [rdx-7]; dwBufferLength
0x1800cd370  mov     rcx, r14; hInternet
0x1800cd373  call    cs:__imp_WinHttpSetOption
0x1800cd379  test    eax, eax
0x1800cd37b  jnz     short loc_1800CD396
0x1800cd37d  mov     edx, 312h; void *
0x1800cd382  mov     rcx, [rbp+5Fh]; this
0x1800cd386  lea     r8, aCW1SSrcDeliver_73; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800cd38d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cd392  mov     esi, eax
0x1800cd394  jmp     short loc_1800CD39F
0x1800cd396  xor     r15b, r15b
0x1800cd399  mov     [r12], r14
0x1800cd39d  xor     esi, esi
0x1800cd39f  mov     rcx, rbx; SRWLock
0x1800cd3a2  call    cs:__imp_AcquireSRWLockExclusive
0x1800cd3a8  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x1800cd3ac  jnz     short loc_1800CD3BE
0x1800cd3ae  lea     rcx, [rbx+8]; Address
0x1800cd3b2  mov     dword ptr [rcx], 1
0x1800cd3b8  call    cs:__imp_WakeByAddressAll
0x1800cd3be  mov     rcx, rbx; SRWLock
0x1800cd3c1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cd3c7  nop
0x1800cd3c8  test    r15b, r15b
0x1800cd3cb  jz      short loc_1800CD3D7
0x1800cd3cd  mov     rcx, r14; hInternet
0x1800cd3d0  call    cs:__imp_WinHttpCloseHandle
0x1800cd3d6  nop
0x1800cd3d7  mov     rbx, [rbp+57h+Token]
0x1800cd3db  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800cd3df  jz      short loc_1800CD3FF
0x1800cd3e1  mov     rdx, rbx; Token
0x1800cd3e4  xor     ecx, ecx; Thread
0x1800cd3e6  call    cs:__imp_SetThreadToken
0x1800cd3ec  test    eax, eax
0x1800cd3ee  jz      short loc_1800CD436
0x1800cd3f0  test    rbx, rbx
0x1800cd3f3  jz      short loc_1800CD3FF
0x1800cd3f5  mov     rcx, rbx; hObject
0x1800cd3f8  call    cs:__imp_CloseHandle
0x1800cd3fe  nop
0x1800cd3ff  sub     dword ptr [rdi+4Ch], 1
0x1800cd403  jnz     short loc_1800CD416
0x1800cd405  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x1800cd40c  lea     rcx, [rdi+10h]; SRWLock
0x1800cd410  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cd416  mov     eax, esi
0x1800cd418  mov     rcx, [rbp+57h+var_40]
0x1800cd41c  xor     rcx, rsp; StackCookie
0x1800cd41f  call    __security_check_cookie
0x1800cd424  add     rsp, 0A0h
0x1800cd42b  pop     r15
0x1800cd42d  pop     r14
0x1800cd42f  pop     r12
0x1800cd431  pop     rdi
0x1800cd432  pop     rsi
0x1800cd433  pop     rbx
0x1800cd434  pop     rbp
0x1800cd435  retn
0x1800cd436  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800cd43c  mov     ecx, 5; int
0x1800cd441  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800cd447  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x1800cd44e  mov     ecx, 6; int
0x1800cd453  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
