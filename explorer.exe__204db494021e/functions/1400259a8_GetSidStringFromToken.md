# GetSidStringFromToken

- ea: `0x1400259a8`
- end: `0x140025b0c`
- name: `GetSidStringFromToken`
- size: `356`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPWSTR *StringSid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14001e1e0`
- `0x140137528`

## callees

- `0x1400259a8`
- `0x14009ac68`
- `0x14009de4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025abb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140025a3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140025a3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025a7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025a7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400259f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400259f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400259d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140025a22`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400259d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140025a22`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140025a63`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140025a63`

## string_xrefs

- `0x140025aa0`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x140025ad5`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x140025af2`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`

## pseudocode

```c
__int64 __fastcall GetSidStringFromToken(HANDLE TokenHandle, LPWSTR *StringSid)
{
  PSID *v4; // rdi
  const char *v5; // r9
  unsigned int LastError; // ebx
  const char *v8; // r9
  __int64 v9; // rdx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SIZE_T cb; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(cb) = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&cb) || GetLastError() == 122 )
  {
    v4 = (PSID *)CoTaskMemAlloc((unsigned int)cb);
    if ( !v4 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
        (const char *)0x8007000ELL,
        ReturnLength);
      return LastError;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v4, cb, (PDWORD)&cb) )
    {
      if ( *StringSid )
      {
        LocalFree(*StringSid);
        *StringSid = 0;
      }
      StringSid[1] = (LPWSTR)-1LL;
      StringSid[2] = (LPWSTR)-1LL;
      if ( ConvertSidToStringSidW(*v4, StringSid) )
      {
        LastError = 0;
LABEL_8:
        CoTaskMemFree(v4);
        return LastError;
      }
      v9 = 34;
    }
    else
    {
      v9 = 33;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
                  v5);
    goto LABEL_8;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x1D,
           (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
           v8);
}

```

## disassembly

```asm
0x1400259a8  mov     rax, rsp
0x1400259ab  mov     [rax+8], rbx
0x1400259af  mov     [rax+10h], rsi
0x1400259b3  push    rdi
0x1400259b4  sub     rsp, 30h
0x1400259b8  xor     r9d, r9d; TokenInformationLength
0x1400259bb  mov     dword ptr [rax+18h], 0
0x1400259c2  mov     rbx, rdx
0x1400259c5  lea     rax, [rax+18h]
0x1400259c9  xor     r8d, r8d; TokenInformation
0x1400259cc  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1400259d1  mov     rsi, rcx
0x1400259d4  lea     edx, [r9+1]; TokenInformationClass
0x1400259d8  call    cs:__imp_GetTokenInformation
0x1400259df  nop     dword ptr [rax+rax+00h]
0x1400259e4  test    eax, eax
0x1400259e6  jz      loc_140025ABB
0x1400259ec  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x1400259f0  call    cs:__imp_CoTaskMemAlloc
0x1400259f7  nop     dword ptr [rax+rax+00h]
0x1400259fc  mov     rdi, rax
0x1400259ff  test    rax, rax
0x140025a02  jz      loc_140025A9B
0x140025a08  mov     r9d, dword ptr [rsp+38h+cb]; TokenInformationLength
0x140025a0d  lea     rax, [rsp+38h+cb]
0x140025a12  mov     r8, rdi; TokenInformation
0x140025a15  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x140025a1a  mov     edx, 1; TokenInformationClass
0x140025a1f  mov     rcx, rsi; TokenHandle
0x140025a22  call    cs:__imp_GetTokenInformation
0x140025a29  nop     dword ptr [rax+rax+00h]
0x140025a2e  test    eax, eax
0x140025a30  jz      loc_140025AE8
0x140025a36  mov     rcx, [rbx]; hMem
0x140025a39  test    rcx, rcx
0x140025a3c  jz      short loc_140025A51
0x140025a3e  call    cs:__imp_LocalFree
0x140025a45  nop     dword ptr [rax+rax+00h]
0x140025a4a  mov     qword ptr [rbx], 0
0x140025a51  or      rax, 0FFFFFFFFFFFFFFFFh
0x140025a55  mov     rdx, rbx; StringSid
0x140025a58  mov     [rbx+8], rax
0x140025a5c  mov     [rbx+10h], rax
0x140025a60  mov     rcx, [rdi]; Sid
0x140025a63  call    cs:__imp_ConvertSidToStringSidW
0x140025a6a  nop     dword ptr [rax+rax+00h]
0x140025a6f  test    eax, eax
0x140025a71  jz      loc_140025B05
0x140025a77  xor     ebx, ebx
0x140025a79  mov     rcx, rdi; pv
0x140025a7c  call    cs:__imp_CoTaskMemFree
0x140025a83  nop     dword ptr [rax+rax+00h]
0x140025a88  mov     eax, ebx
0x140025a8a  mov     rbx, [rsp+38h+arg_0]
0x140025a8f  mov     rsi, [rsp+38h+arg_8]
0x140025a94  add     rsp, 30h
0x140025a98  pop     rdi
0x140025a99  retn
0x140025a9b  mov     rcx, [rsp+38h]; this
0x140025aa0  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140025aa7  mov     ebx, 8007000Eh
0x140025aac  mov     edx, 20h ; ' '; void *
0x140025ab1  mov     r9d, ebx; char *
0x140025ab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025ab9  jmp     short loc_140025A88
0x140025abb  call    cs:__imp_GetLastError
0x140025ac2  nop     dword ptr [rax+rax+00h]
0x140025ac7  cmp     eax, 7Ah ; 'z'
0x140025aca  jz      loc_1400259EC
0x140025ad0  mov     rcx, [rsp+38h]; this
0x140025ad5  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140025adc  mov     edx, 1Dh; void *
0x140025ae1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140025ae6  jmp     short loc_140025A8A
0x140025ae8  mov     edx, 21h ; '!'; void *
0x140025aed  mov     rcx, [rsp+38h]; this
0x140025af2  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140025af9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140025afe  mov     ebx, eax
0x140025b00  jmp     loc_140025A79
0x140025b05  mov     edx, 22h ; '"'
0x140025b0a  jmp     short loc_140025AED
```
