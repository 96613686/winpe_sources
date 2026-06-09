# IkeIsRemoteTokenMachine

- ea: `0x180080b38`
- end: `0x180080c97`
- name: `IkeIsRemoteTokenMachine`
- size: `351`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004ee6c`

## callees

- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x180050850`
- `0x180080a94`
- `0x180080b38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c0b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080b9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080c01`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080b9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080c01`

## string_xrefs

- `0x180080c18`: `GetTokenInformation`
- `0x180080b70`: `IkeIsRemoteTokenMachine`
- `0x180080bb5`: `IkeIsRemoteTokenMachine`
- `0x180080c5e`: `IkeIsRemoteTokenMachine`
- `0x180080c6a`: `IkeIsRemoteTokenMachine`

## pseudocode

```c
__int64 __fastcall IkeIsRemoteTokenMachine(HANDLE TokenHandle, _DWORD *a2)
{
  DWORD v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rsi
  LPVOID v7; // rdi
  DWORD LastError; // eax
  __int64 v9; // rcx
  unsigned int i; // ebx
  LPVOID TokenInformation; // [rsp+30h] [rbp-38h] BYREF
  DWORD TokenInformationLength; // [rsp+38h] [rbp-30h] BYREF

  TokenInformation = 0;
  TokenInformationLength = 0;
  TraceLogHelper("IkeIsRemoteTokenMachine", 1);
  *a2 = 0;
  if ( GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength) || (v4 = GetLastError(), v4 == 122) )
  {
    v7 = TokenInformation;
    v6 = WfpMemAlloc(TokenInformationLength, 0);
    if ( !v6 )
    {
      if ( GetTokenInformation(
             TokenHandle,
             TokenGroups,
             TokenInformation,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        for ( i = 0; i < *(_DWORD *)TokenInformation; ++i )
        {
          if ( (unsigned int)IkeIsRemoteSidMachine(*((_QWORD *)TokenInformation + 2 * i + 1)) )
          {
            *a2 = 1;
            break;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v6 = WfpReportSysErrorAsWinError(v9, "GetTokenInformation", LastError, 1);
      }
    }
    if ( v7 )
      WfpMemFree(&TokenInformation);
  }
  else
  {
    v6 = WfpReportSysErrorAsWinError(v5, "IkeIsRemoteTokenMachine", v4, 1);
  }
  TraceLogHelper("IkeIsRemoteTokenMachine", 0);
  return IkeReturnError(v6, "IkeIsRemoteTokenMachine");
}

```

## disassembly

```asm
0x180080b38  mov     [rsp+arg_10], rbx
0x180080b3d  push    rsi
0x180080b3e  push    rdi
0x180080b3f  push    r14
0x180080b41  sub     rsp, 50h
0x180080b45  mov     rax, cs:__security_cookie
0x180080b4c  xor     rax, rsp
0x180080b4f  mov     [rsp+68h+var_28], rax
0x180080b54  mov     r14, rdx
0x180080b57  mov     [rsp+68h+TokenInformation], 0
0x180080b60  mov     rbx, rcx
0x180080b63  mov     [rsp+68h+TokenInformationLength], 0
0x180080b6b  mov     edx, 1
0x180080b70  lea     rcx, aIkeisremotetok; "IkeIsRemoteTokenMachine"
0x180080b77  call    TraceLogHelper
0x180080b7c  xor     r9d, r9d; TokenInformationLength
0x180080b7f  mov     dword ptr [r14], 0
0x180080b86  lea     rax, [rsp+68h+TokenInformationLength]
0x180080b8b  xor     r8d, r8d; TokenInformation
0x180080b8e  mov     rcx, rbx; TokenHandle
0x180080b91  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180080b96  lea     edx, [r9+2]; TokenInformationClass
0x180080b9a  call    cs:__imp_GetTokenInformation
0x180080ba0  test    eax, eax
0x180080ba2  jnz     short loc_180080BCC
0x180080ba4  call    cs:__imp_GetLastError
0x180080baa  cmp     eax, 7Ah ; 'z'
0x180080bad  jz      short loc_180080BCC
0x180080baf  mov     r9d, 1
0x180080bb5  lea     rdx, aIkeisremotetok; "IkeIsRemoteTokenMachine"
0x180080bbc  mov     r8d, eax
0x180080bbf  call    WfpReportSysErrorAsWinError
0x180080bc4  mov     rsi, rax
0x180080bc7  jmp     loc_180080C5C
0x180080bcc  mov     ecx, [rsp+68h+TokenInformationLength]; dwBytes
0x180080bd0  lea     r8, [rsp+68h+TokenInformation]
0x180080bd5  xor     edx, edx; dwFlags
0x180080bd7  call    WfpMemAlloc
0x180080bdc  mov     rdi, [rsp+68h+TokenInformation]
0x180080be1  mov     rsi, rax
0x180080be4  test    rax, rax
0x180080be7  jnz     short loc_180080C4D
0x180080be9  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x180080bee  lea     rax, [rsp+68h+TokenInformationLength]
0x180080bf3  mov     r8, rdi; TokenInformation
0x180080bf6  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180080bfb  lea     edx, [rsi+2]; TokenInformationClass
0x180080bfe  mov     rcx, rbx; TokenHandle
0x180080c01  call    cs:__imp_GetTokenInformation
0x180080c07  test    eax, eax
0x180080c09  jnz     short loc_180080C29
0x180080c0b  call    cs:__imp_GetLastError
0x180080c11  mov     r8d, eax
0x180080c14  lea     r9d, [rsi+1]
0x180080c18  lea     rdx, aGettokeninform; "GetTokenInformation"
0x180080c1f  call    WfpReportSysErrorAsWinError
0x180080c24  mov     rsi, rax
0x180080c27  jmp     short loc_180080C4D
0x180080c29  xor     ebx, ebx
0x180080c2b  cmp     ebx, [rdi]
0x180080c2d  jnb     short loc_180080C4D
0x180080c2f  mov     ecx, ebx
0x180080c31  add     rcx, rcx
0x180080c34  mov     rcx, [rdi+rcx*8+8]
0x180080c39  call    IkeIsRemoteSidMachine
0x180080c3e  test    eax, eax
0x180080c40  jnz     short loc_180080C46
0x180080c42  inc     ebx
0x180080c44  jmp     short loc_180080C2B
0x180080c46  mov     dword ptr [r14], 1
0x180080c4d  test    rdi, rdi
0x180080c50  jz      short loc_180080C5C
0x180080c52  lea     rcx, [rsp+68h+TokenInformation]
0x180080c57  call    WfpMemFree
0x180080c5c  xor     edx, edx
0x180080c5e  lea     rcx, aIkeisremotetok; "IkeIsRemoteTokenMachine"
0x180080c65  call    TraceLogHelper
0x180080c6a  lea     rdx, aIkeisremotetok; "IkeIsRemoteTokenMachine"
0x180080c71  mov     rcx, rsi
0x180080c74  call    IkeReturnError
0x180080c79  mov     rcx, [rsp+68h+var_28]
0x180080c7e  xor     rcx, rsp; StackCookie
0x180080c81  call    __security_check_cookie
0x180080c86  mov     rbx, [rsp+68h+arg_10]
0x180080c8e  add     rsp, 50h
0x180080c92  pop     r14
0x180080c94  pop     rdi
0x180080c95  pop     rsi
0x180080c96  retn
```
