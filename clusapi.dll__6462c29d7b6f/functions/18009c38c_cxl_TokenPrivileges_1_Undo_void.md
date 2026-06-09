# cxl::TokenPrivileges<1>::Undo(void *)

- ea: `0x18009c38c`
- end: `0x18009c450`
- name: `?Undo@?$TokenPrivileges@$00@cxl@@QEAAXPEAX@Z`
- size: `196`
- prototype: `__int64 __fastcall(PTOKEN_PRIVILEGES NewState, HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009a9f0`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc2c`
- `0x18001d284`
- `0x18009c38c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c401`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18009c3e3`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18009c3e3`

## string_xrefs

- `0x18009c3ed`: `::AdjustTokenPrivileges( TokenHandle, FALSE, &Header, 0, 0, 0)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __fastcall cxl::TokenPrivileges<1>::Undo(PTOKEN_PRIVILEGES NewState, HANDLE TokenHandle)
{
  BOOL result; // eax
  __int64 v3; // rbx
  _DWORD v4[2]; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v5[40]; // [rsp+38h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+60h] [rbp-88h] BYREF

  if ( NewState->Privileges[0].Attributes == 2 )
  {
    NewState->Privileges[0].Attributes = 4;
  }
  else if ( NewState->Privileges[0].Attributes == 4 )
  {
    NewState->Privileges[0].Attributes = 2;
  }
  result = AdjustTokenPrivileges(TokenHandle, 0, NewState, 0, 0, 0);
  if ( !result )
  {
    v3 = std::wstring::wstring(v5, L"::AdjustTokenPrivileges( TokenHandle, FALSE, &Header, 0, 0, 0)");
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
0x18009c38c  push    rbx
0x18009c38e  sub     rsp, 0E0h
0x18009c395  mov     rax, cs:__security_cookie
0x18009c39c  xor     rax, rsp
0x18009c39f  mov     [rsp+0E8h+var_18], rax
0x18009c3a7  mov     rax, rdx
0x18009c3aa  cmp     dword ptr [rcx+0Ch], 2
0x18009c3ae  jz      short loc_18009C3BF
0x18009c3b0  cmp     dword ptr [rcx+0Ch], 4
0x18009c3b4  jnz     short loc_18009C3C6
0x18009c3b6  mov     dword ptr [rcx+0Ch], 2
0x18009c3bd  jmp     short loc_18009C3C6
0x18009c3bf  mov     dword ptr [rcx+0Ch], 4
0x18009c3c6  mov     [rsp+0E8h+ReturnLength], 0; ReturnLength
0x18009c3cf  mov     [rsp+0E8h+PreviousState], 0; PreviousState
0x18009c3d8  xor     r9d, r9d; BufferLength
0x18009c3db  mov     r8, rcx; NewState
0x18009c3de  xor     edx, edx; DisableAllPrivileges
0x18009c3e0  mov     rcx, rax; TokenHandle
0x18009c3e3  call    cs:__imp_AdjustTokenPrivileges
0x18009c3e9  test    eax, eax
0x18009c3eb  jnz     short loc_18009C437
0x18009c3ed  lea     rdx, aAdjusttokenpri_0; "::AdjustTokenPrivileges( TokenHandle, F"...
0x18009c3f4  lea     rcx, [rsp+0E8h+var_B0]
0x18009c3f9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18009c3fe  mov     rbx, rax
0x18009c401  call    cs:__imp_GetLastError
0x18009c407  mov     [rsp+0E8h+var_B8], eax
0x18009c40b  mov     [rsp+0E8h+var_B4], 0
0x18009c413  mov     r8, rbx
0x18009c416  lea     rdx, [rsp+0E8h+var_B8]
0x18009c41b  lea     rcx, [rsp+0E8h+pExceptionObject]
0x18009c420  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009c425  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009c42c  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18009c431  call    _CxxThrowException_0
0x18009c437  mov     rcx, [rsp+0E8h+var_18]
0x18009c43f  xor     rcx, rsp; StackCookie
0x18009c442  call    __security_check_cookie
0x18009c447  add     rsp, 0E0h
0x18009c44e  pop     rbx
0x18009c44f  retn
```
