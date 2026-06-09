# cxl::EnableThreadPrivilege::GetCurrentThreadToken(void)

- ea: `0x18009b6ec`
- end: `0x18009b798`
- name: `?GetCurrentThreadToken@EnableThreadPrivilege@cxl@@AEAAPEAXXZ`
- size: `172`
- prototype: `void *__fastcall(cxl::EnableThreadPrivilege *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18009b590`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc2c`
- `0x18001d284`
- `0x18009b6ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b744`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009b710`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009b710`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009b726`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009b726`

## string_xrefs

- `0x18009b730`: `::OpenThreadToken(::GetCurrentThread(), MAXIMUM_ALLOWED, FALSE, &handle)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall cxl::EnableThreadPrivilege::GetCurrentThreadToken(cxl::EnableThreadPrivilege *this)
{
  HANDLE CurrentThread; // rax
  __int64 v2; // rbx
  _DWORD v4[2]; // [rsp+20h] [rbp-B8h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-B0h] BYREF
  _BYTE v6[32]; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+50h] [rbp-88h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000000u, 0, &TokenHandle) )
  {
    v2 = std::wstring::wstring(v6, L"::OpenThreadToken(::GetCurrentThread(), MAXIMUM_ALLOWED, FALSE, &handle)");
    v4[0] = GetLastError();
    v4[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v4, v2);
    throw (cxl::Exception *)pExceptionObject;
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x18009b6ec  push    rbx
0x18009b6ee  sub     rsp, 0D0h
0x18009b6f5  mov     rax, cs:__security_cookie
0x18009b6fc  xor     rax, rsp
0x18009b6ff  mov     [rsp+0D8h+var_18], rax
0x18009b707  mov     [rsp+0D8h+TokenHandle], 0
0x18009b710  call    cs:__imp_GetCurrentThread
0x18009b716  mov     rcx, rax; ThreadHandle
0x18009b719  lea     r9, [rsp+0D8h+TokenHandle]; TokenHandle
0x18009b71e  xor     r8d, r8d; OpenAsSelf
0x18009b721  mov     edx, 2000000h; DesiredAccess
0x18009b726  call    cs:__imp_OpenThreadToken
0x18009b72c  test    eax, eax
0x18009b72e  jnz     short loc_18009B77A
0x18009b730  lea     rdx, aOpenthreadtoke; "::OpenThreadToken(::GetCurrentThread(),"...
0x18009b737  lea     rcx, [rsp+0D8h+var_A8]
0x18009b73c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18009b741  mov     rbx, rax
0x18009b744  call    cs:__imp_GetLastError
0x18009b74a  mov     [rsp+0D8h+var_B8], eax
0x18009b74e  mov     [rsp+0D8h+var_B4], 0
0x18009b756  mov     r8, rbx
0x18009b759  lea     rdx, [rsp+0D8h+var_B8]
0x18009b75e  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18009b763  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009b768  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009b76f  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18009b774  call    _CxxThrowException_0
0x18009b77a  mov     rax, [rsp+0D8h+TokenHandle]
0x18009b77f  mov     rcx, [rsp+0D8h+var_18]
0x18009b787  xor     rcx, rsp; StackCookie
0x18009b78a  call    __security_check_cookie
0x18009b78f  add     rsp, 0D0h
0x18009b796  pop     rbx
0x18009b797  retn
```
