# cxl::ImpersonateUser::ImpersonateUser(void *,bool)

- ea: `0x1800a3680`
- end: `0x1800a3781`
- name: `??0ImpersonateUser@cxl@@QEAA@PEAX_N@Z`
- size: `257`
- prototype: `__int64 __fastcall(cxl::ImpersonateUser *__hidden this, HANDLE hToken, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a68bc`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc2c`
- `0x18001d284`
- `0x18009cef4`
- `0x1800a3680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a372e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a372e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a36b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a36b4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a3711`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a3711`

## string_xrefs

- `0x1800a36d2`: `userToken_.TryOpenThreadToken( TOKEN_QUERY | TOKEN_IMPERSONATE, TRUE )`
- `0x1800a371b`: `::ImpersonateLoggedOnUser( token )`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
cxl::ImpersonateUser *__fastcall cxl::ImpersonateUser::ImpersonateUser(cxl::ImpersonateUser *this, HANDLE hToken)
{
  HANDLE CurrentThread; // rax
  unsigned int v5; // edx
  int v6; // r8d
  unsigned int v7; // eax
  DWORD v8; // edi
  __int64 v9; // rax
  __int64 v10; // rbx
  DWORD LastError; // [rsp+20h] [rbp-69h] BYREF
  int v13; // [rsp+24h] [rbp-65h]
  cxl::ImpersonateUser *v14; // [rsp+28h] [rbp-61h]
  _BYTE v15[32]; // [rsp+30h] [rbp-59h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+50h] [rbp-39h] BYREF

  v14 = this;
  *((_QWORD *)this + 1) = 0;
  CurrentThread = GetCurrentThread();
  v7 = cxl::Token::TryOpenThreadToken(this, v5, v6, CurrentThread);
  v8 = v7;
  if ( v7 && v7 != 1008 )
  {
    v9 = std::wstring::wstring(v15, L"userToken_.TryOpenThreadToken( TOKEN_QUERY | TOKEN_IMPERSONATE, TRUE )");
    LastError = v8;
    v13 = 0;
    cxl::Exception::Exception(pExceptionObject, &LastError, v9);
    throw (cxl::Exception *)pExceptionObject;
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    v10 = std::wstring::wstring(v15, L"::ImpersonateLoggedOnUser( token )");
    LastError = GetLastError();
    v13 = 0;
    cxl::Exception::Exception(pExceptionObject, &LastError, v10);
    throw (cxl::Exception *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x1800a3680  mov     [rsp-8+arg_10], rbx
0x1800a3685  push    rbp
0x1800a3686  push    rsi
0x1800a3687  push    rdi
0x1800a3688  lea     rbp, [rsp-47h]
0x1800a368d  sub     rsp, 0D0h
0x1800a3694  mov     rax, cs:__security_cookie
0x1800a369b  xor     rax, rsp
0x1800a369e  mov     [rbp+57h+var_20], rax
0x1800a36a2  mov     rsi, rdx
0x1800a36a5  mov     rbx, rcx
0x1800a36a8  mov     [rbp+57h+var_B8], rcx
0x1800a36ac  mov     qword ptr [rcx+8], 0
0x1800a36b4  call    cs:__imp_GetCurrentThread
0x1800a36ba  mov     r9, rax; void *
0x1800a36bd  mov     rcx, rbx; this
0x1800a36c0  call    ?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z; cxl::Token::TryOpenThreadToken(ulong,int,void *)
0x1800a36c5  mov     edi, eax
0x1800a36c7  test    eax, eax
0x1800a36c9  jz      short loc_1800A370E
0x1800a36cb  cmp     eax, 3F0h
0x1800a36d0  jz      short loc_1800A370E
0x1800a36d2  lea     rdx, aUsertokenTryop; "userToken_.TryOpenThreadToken( TOKEN_QU"...
0x1800a36d9  lea     rcx, [rbp+57h+var_B0]
0x1800a36dd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800a36e2  nop
0x1800a36e3  mov     [rbp+57h+var_C0], edi
0x1800a36e6  mov     [rbp+57h+var_BC], 0
0x1800a36ed  mov     r8, rax
0x1800a36f0  lea     rdx, [rbp+57h+var_C0]
0x1800a36f4  lea     rcx, [rbp+57h+pExceptionObject]
0x1800a36f8  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800a36fd  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800a3704  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800a3708  call    _CxxThrowException_0
0x1800a370e  mov     rcx, rsi; hToken
0x1800a3711  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a3717  test    eax, eax
0x1800a3719  jnz     short loc_1800A375F
0x1800a371b  lea     rdx, aImpersonatelog; "::ImpersonateLoggedOnUser( token )"
0x1800a3722  lea     rcx, [rbp+57h+var_B0]
0x1800a3726  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800a372b  mov     rbx, rax
0x1800a372e  call    cs:__imp_GetLastError
0x1800a3734  mov     [rbp+57h+var_C0], eax
0x1800a3737  mov     [rbp+57h+var_BC], 0
0x1800a373e  mov     r8, rbx
0x1800a3741  lea     rdx, [rbp+57h+var_C0]
0x1800a3745  lea     rcx, [rbp+57h+pExceptionObject]
0x1800a3749  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800a374e  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800a3755  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800a3759  call    _CxxThrowException_0
0x1800a375f  mov     rax, rbx
0x1800a3762  mov     rcx, [rbp+57h+var_20]
0x1800a3766  xor     rcx, rsp; StackCookie
0x1800a3769  call    __security_check_cookie
0x1800a376e  mov     rbx, [rsp+0E0h+arg_10]
0x1800a3776  add     rsp, 0D0h
0x1800a377d  pop     rdi
0x1800a377e  pop     rsi
0x1800a377f  pop     rbp
0x1800a3780  retn
```
