# cxl::ImpersonateSelf::ImpersonateSelf(_SECURITY_IMPERSONATION_LEVEL)

- ea: `0x18009a8cc`
- end: `0x18009a95f`
- name: `??0ImpersonateSelf@cxl@@QEAA@W4_SECURITY_IMPERSONATION_LEVEL@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(cxl::ImpersonateSelf *__hidden this, enum _SECURITY_IMPERSONATION_LEVEL)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009b590`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc2c`
- `0x18001d284`
- `0x18009a8cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a90d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a90d`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18009a8ef`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18009a8ef`

## string_xrefs

- `0x18009a8f9`: `::ImpersonateSelf( level )`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
cxl::ImpersonateSelf *__fastcall cxl::ImpersonateSelf::ImpersonateSelf(
        cxl::ImpersonateSelf *this,
        enum _SECURITY_IMPERSONATION_LEVEL a2)
{
  __int64 v3; // rbx
  _DWORD v5[2]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v6[40]; // [rsp+28h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+50h] [rbp-88h] BYREF

  if ( !ImpersonateSelf(SecurityImpersonation) )
  {
    v3 = std::wstring::wstring(v6, L"::ImpersonateSelf( level )");
    v5[0] = GetLastError();
    v5[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v5, v3);
    throw (cxl::Exception *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18009a8cc  push    rbx
0x18009a8ce  sub     rsp, 0D0h
0x18009a8d5  mov     rax, cs:__security_cookie
0x18009a8dc  xor     rax, rsp
0x18009a8df  mov     [rsp+0D8h+var_18], rax
0x18009a8e7  mov     rbx, rcx
0x18009a8ea  mov     ecx, 2; ImpersonationLevel
0x18009a8ef  call    cs:__imp_ImpersonateSelf
0x18009a8f5  test    eax, eax
0x18009a8f7  jnz     short loc_18009A943
0x18009a8f9  lea     rdx, aImpersonatesel; "::ImpersonateSelf( level )"
0x18009a900  lea     rcx, [rsp+0D8h+var_B0]
0x18009a905  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18009a90a  mov     rbx, rax
0x18009a90d  call    cs:__imp_GetLastError
0x18009a913  mov     [rsp+0D8h+var_B8], eax
0x18009a917  mov     [rsp+0D8h+var_B4], 0
0x18009a91f  mov     r8, rbx
0x18009a922  lea     rdx, [rsp+0D8h+var_B8]
0x18009a927  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18009a92c  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009a931  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009a938  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18009a93d  call    _CxxThrowException_0
0x18009a943  mov     rax, rbx
0x18009a946  mov     rcx, [rsp+0D8h+var_18]
0x18009a94e  xor     rcx, rsp; StackCookie
0x18009a951  call    __security_check_cookie
0x18009a956  add     rsp, 0D0h
0x18009a95d  pop     rbx
0x18009a95e  retn
```
