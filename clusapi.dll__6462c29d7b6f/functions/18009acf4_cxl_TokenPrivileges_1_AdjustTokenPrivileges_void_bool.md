# cxl::TokenPrivileges<1>::AdjustTokenPrivileges(void *,bool)

- ea: `0x18009acf4`
- end: `0x18009ad9c`
- name: `?AdjustTokenPrivileges@?$TokenPrivileges@$00@cxl@@QEAAXPEAX_N@Z`
- size: `168`
- prototype: `__int64 __fastcall(PTOKEN_PRIVILEGES NewState, HANDLE TokenHandle)`
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
- `0x18009acf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ad4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ad4d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18009ad2f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18009ad2f`

## string_xrefs

- `0x18009ad39`: `::AdjustTokenPrivileges( TokenHandle, DisableAllPrivileges, &Header, 0, 0, 0)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __fastcall cxl::TokenPrivileges<1>::AdjustTokenPrivileges(PTOKEN_PRIVILEGES NewState, HANDLE TokenHandle)
{
  BOOL result; // eax
  __int64 v3; // rbx
  _DWORD v4[2]; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v5[40]; // [rsp+38h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+60h] [rbp-88h] BYREF

  result = AdjustTokenPrivileges(TokenHandle, 0, NewState, 0, 0, 0);
  if ( !result )
  {
    v3 = std::wstring::wstring(v5, L"::AdjustTokenPrivileges( TokenHandle, DisableAllPrivileges, &Header, 0, 0, 0)");
    v4[0] = GetLastError();
    v4[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v4, v3);
    throw (cxl::Exception *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18009acf4  push    rbx
0x18009acf6  sub     rsp, 0E0h
0x18009acfd  mov     rax, cs:__security_cookie
0x18009ad04  xor     rax, rsp
0x18009ad07  mov     [rsp+0E8h+var_18], rax
0x18009ad0f  mov     rax, rdx
0x18009ad12  mov     [rsp+0E8h+ReturnLength], 0; ReturnLength
0x18009ad1b  mov     [rsp+0E8h+PreviousState], 0; PreviousState
0x18009ad24  xor     r9d, r9d; BufferLength
0x18009ad27  mov     r8, rcx; NewState
0x18009ad2a  xor     edx, edx; DisableAllPrivileges
0x18009ad2c  mov     rcx, rax; TokenHandle
0x18009ad2f  call    cs:__imp_AdjustTokenPrivileges
0x18009ad35  test    eax, eax
0x18009ad37  jnz     short loc_18009AD83
0x18009ad39  lea     rdx, aAdjusttokenpri; "::AdjustTokenPrivileges( TokenHandle, D"...
0x18009ad40  lea     rcx, [rsp+0E8h+var_B0]
0x18009ad45  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18009ad4a  mov     rbx, rax
0x18009ad4d  call    cs:__imp_GetLastError
0x18009ad53  mov     [rsp+0E8h+var_B8], eax
0x18009ad57  mov     [rsp+0E8h+var_B4], 0
0x18009ad5f  mov     r8, rbx
0x18009ad62  lea     rdx, [rsp+0E8h+var_B8]
0x18009ad67  lea     rcx, [rsp+0E8h+pExceptionObject]
0x18009ad6c  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009ad71  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009ad78  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18009ad7d  call    _CxxThrowException_0
0x18009ad83  mov     rcx, [rsp+0E8h+var_18]
0x18009ad8b  xor     rcx, rsp; StackCookie
0x18009ad8e  call    __security_check_cookie
0x18009ad93  add     rsp, 0E0h
0x18009ad9a  pop     rbx
0x18009ad9b  retn
```
