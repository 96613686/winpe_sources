# IsUserAssignedAccessMultiApp

- ea: `0x140033a3c`
- end: `0x140033bc6`
- name: `IsUserAssignedAccessMultiApp`
- size: `394`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `15`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400137b8`
- `0x14001b4b4`
- `0x140062518`
- `0x140089140`
- `0x14008bab4`
- `0x1400a3820`
- `0x1400a3da0`
- `0x1400a4d00`
- `0x1400a4f24`
- `0x1400a528c`
- `0x1400a58f0`
- `0x1400b4ba8`
- `0x1400c3480`
- `0x1401ada70`
- `0x1401aedcc`

## callees

- `0x140033a3c`
- `0x1400345a0`
- `0x1400954e0`
- `0x1400987b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033b91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140033ad1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140033b4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140033b87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140033ad1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140033b4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140033b87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033b25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033b25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140033a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140033a94`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140033a83`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140033abe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140033a83`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140033abe`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140033af2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140033af2`

## string_xrefs

- `0x140033b14`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x140033b67`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x140033ba4`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`

## pseudocode

```c
_BOOL8 __fastcall IsUserAssignedAccessMultiApp(HANDLE TokenHandle)
{
  PSID *v2; // rbx
  const char *v3; // r9
  __int64 v4; // rdx
  int LastError; // edi
  BOOL v6; // ebx
  const char *v8; // r9
  int ReturnLength; // [rsp+20h] [rbp-30h]
  HLOCAL hMem; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+38h] [rbp-18h]
  __int64 v12; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  DWORD TokenInformationLength; // [rsp+68h] [rbp+18h] BYREF

  hMem = 0;
  v11 = 0;
  v12 = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
  {
    v2 = (PSID *)CoTaskMemAlloc(TokenInformationLength);
    if ( !v2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
        (const char *)0x8007000ELL,
        ReturnLength);
      goto LABEL_13;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
    {
      v11 = -1;
      v12 = -1;
      if ( ConvertSidToStringSidW(*v2, (LPWSTR *)&hMem) )
      {
        CoTaskMemFree(v2);
LABEL_9:
        v6 = GetAssignedAccessTypeForUser((unsigned __int16 *)hMem) == 2;
        if ( hMem )
          LocalFree(hMem);
        return v6;
      }
      v4 = 34;
    }
    else
    {
      v4 = 33;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v4,
                  (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
                  v3);
    CoTaskMemFree(v2);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1D,
                  (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
                  v8);
  }
  if ( LastError >= 0 )
    goto LABEL_9;
LABEL_13:
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x140033a3c  mov     [rsp-8+arg_0], rbx
0x140033a41  mov     [rsp-8+arg_10], rdi
0x140033a46  push    rbp
0x140033a47  mov     rbp, rsp
0x140033a4a  sub     rsp, 50h
0x140033a4e  xor     r9d, r9d; TokenInformationLength
0x140033a51  mov     [rbp+hMem], 0
0x140033a59  lea     rax, [rbp+TokenInformationLength]
0x140033a5d  mov     [rbp+var_18], 0
0x140033a65  xor     r8d, r8d; TokenInformation
0x140033a68  mov     [rbp+var_10], 0
0x140033a70  mov     rdi, rcx
0x140033a73  mov     [rbp+TokenInformationLength], 0
0x140033a7a  lea     edx, [r9+1]; TokenInformationClass
0x140033a7e  mov     qword ptr [rsp+50h+ReturnLength], rax; int
0x140033a83  call    cs:__imp_GetTokenInformation
0x140033a89  test    eax, eax
0x140033a8b  jz      loc_140033B91
0x140033a91  mov     ecx, [rbp+TokenInformationLength]; cb
0x140033a94  call    cs:__imp_CoTaskMemAlloc
0x140033a9a  mov     rbx, rax
0x140033a9d  test    rax, rax
0x140033aa0  jz      loc_140033B63
0x140033aa6  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140033aaa  lea     rax, [rbp+TokenInformationLength]
0x140033aae  mov     r8, rbx; TokenInformation
0x140033ab1  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x140033ab6  mov     edx, 1; TokenInformationClass
0x140033abb  mov     rcx, rdi; TokenHandle
0x140033abe  call    cs:__imp_GetTokenInformation
0x140033ac4  test    eax, eax
0x140033ac6  jz      short loc_140033B0B
0x140033ac8  mov     rcx, [rbp+hMem]; hMem
0x140033acc  test    rcx, rcx
0x140033acf  jz      short loc_140033ADF
0x140033ad1  call    cs:__imp_LocalFree
0x140033ad7  mov     [rbp+hMem], 0
0x140033adf  or      rax, 0FFFFFFFFFFFFFFFFh
0x140033ae3  lea     rdx, [rbp+hMem]; StringSid
0x140033ae7  mov     [rbp+var_18], rax
0x140033aeb  mov     [rbp+var_10], rax
0x140033aef  mov     rcx, [rbx]; Sid
0x140033af2  call    cs:__imp_ConvertSidToStringSidW
0x140033af8  test    eax, eax
0x140033afa  jz      loc_140033BBC
0x140033b00  mov     rcx, rbx; pv
0x140033b03  call    cs:__imp_CoTaskMemFree
0x140033b09  jmp     short loc_140033B2F
0x140033b0b  mov     edx, 21h ; '!'; void *
0x140033b10  mov     rcx, [rbp+8]; this
0x140033b14  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140033b1b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140033b20  mov     rcx, rbx; pv
0x140033b23  mov     edi, eax
0x140033b25  call    cs:__imp_CoTaskMemFree
0x140033b2b  test    edi, edi
0x140033b2d  js      short loc_140033B7E
0x140033b2f  mov     rcx, [rbp+hMem]
0x140033b33  xor     edx, edx
0x140033b35  call    GetAssignedAccessTypeForUser
0x140033b3a  mov     rcx, [rbp+hMem]; hMem
0x140033b3e  xor     ebx, ebx
0x140033b40  cmp     eax, 2
0x140033b43  setz    bl
0x140033b46  test    rcx, rcx
0x140033b49  jz      short loc_140033B51
0x140033b4b  call    cs:__imp_LocalFree
0x140033b51  mov     eax, ebx
0x140033b53  mov     rbx, [rsp+50h+arg_0]
0x140033b58  mov     rdi, [rsp+50h+arg_10]
0x140033b5d  add     rsp, 50h
0x140033b61  pop     rbp
0x140033b62  retn
0x140033b63  mov     rcx, [rbp+8]; this
0x140033b67  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140033b6e  mov     r9d, 8007000Eh; char *
0x140033b74  mov     edx, 20h ; ' '; void *
0x140033b79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140033b7e  mov     rcx, [rbp+hMem]; hMem
0x140033b82  test    rcx, rcx
0x140033b85  jz      short loc_140033B8D
0x140033b87  call    cs:__imp_LocalFree
0x140033b8d  xor     eax, eax
0x140033b8f  jmp     short loc_140033B53
0x140033b91  call    cs:__imp_GetLastError
0x140033b97  cmp     eax, 7Ah ; 'z'
0x140033b9a  jz      loc_140033A91
0x140033ba0  mov     rcx, [rbp+8]; this
0x140033ba4  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140033bab  mov     edx, 1Dh; void *
0x140033bb0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140033bb5  mov     edi, eax
0x140033bb7  jmp     loc_140033B2B
0x140033bbc  mov     edx, 22h ; '"'
0x140033bc1  jmp     loc_140033B10
```
