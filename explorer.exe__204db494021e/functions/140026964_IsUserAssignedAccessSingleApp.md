# IsUserAssignedAccessSingleApp

- ea: `0x140026964`
- end: `0x140026b23`
- name: `IsUserAssignedAccessSingleApp`
- size: `447`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `14`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14001e264`
- `0x1400265b4`
- `0x140065d58`
- `0x14008eb00`
- `0x1400a9be0`
- `0x1400aa174`
- `0x1400aae5c`
- `0x1400ab0c0`
- `0x1400ab430`
- `0x1400ab9c8`
- `0x1400bb254`
- `0x1400c9f10`
- `0x1401ade48`
- `0x1401ae778`

## callees

- `0x140026964`
- `0x140026b2c`
- `0x14009ac68`
- `0x14009de4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026ae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026ae8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140026a0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140026a95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140026ad8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140026a0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140026a95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140026ad8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026a49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026a71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026a49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026a71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400269c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400269c2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400269ab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400269f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400269ab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400269f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140026a32`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140026a32`

## string_xrefs

- `0x140026a60`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x140026ab8`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x140026b01`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`

## pseudocode

```c
__int64 __fastcall IsUserAssignedAccessSingleApp(HANDLE TokenHandle)
{
  PSID *v2; // rbx
  const char *v3; // r9
  __int64 v4; // rdx
  int LastError; // edi
  unsigned int v6; // ebx
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
        v6 = IsUserSidAssignedAccessSingleApp(hMem);
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
0x140026964  mov     [rsp-8+arg_0], rbx
0x140026969  mov     [rsp-8+arg_10], rdi
0x14002696e  push    rbp
0x14002696f  mov     rbp, rsp
0x140026972  sub     rsp, 50h
0x140026976  xor     r9d, r9d; TokenInformationLength
0x140026979  mov     [rbp+hMem], 0
0x140026981  lea     rax, [rbp+TokenInformationLength]
0x140026985  mov     [rbp+var_18], 0
0x14002698d  xor     r8d, r8d; TokenInformation
0x140026990  mov     [rbp+var_10], 0
0x140026998  mov     rdi, rcx
0x14002699b  mov     [rbp+TokenInformationLength], 0
0x1400269a2  lea     edx, [r9+1]; TokenInformationClass
0x1400269a6  mov     qword ptr [rsp+50h+ReturnLength], rax; int
0x1400269ab  call    cs:__imp_GetTokenInformation
0x1400269b2  nop     dword ptr [rax+rax+00h]
0x1400269b7  test    eax, eax
0x1400269b9  jz      loc_140026AE8
0x1400269bf  mov     ecx, [rbp+TokenInformationLength]; cb
0x1400269c2  call    cs:__imp_CoTaskMemAlloc
0x1400269c9  nop     dword ptr [rax+rax+00h]
0x1400269ce  mov     rbx, rax
0x1400269d1  test    rax, rax
0x1400269d4  jz      loc_140026AB4
0x1400269da  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1400269de  lea     rax, [rbp+TokenInformationLength]
0x1400269e2  mov     r8, rbx; TokenInformation
0x1400269e5  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x1400269ea  mov     edx, 1; TokenInformationClass
0x1400269ef  mov     rcx, rdi; TokenHandle
0x1400269f2  call    cs:__imp_GetTokenInformation
0x1400269f9  nop     dword ptr [rax+rax+00h]
0x1400269fe  test    eax, eax
0x140026a00  jz      short loc_140026A57
0x140026a02  mov     rcx, [rbp+hMem]; hMem
0x140026a06  test    rcx, rcx
0x140026a09  jz      short loc_140026A1F
0x140026a0b  call    cs:__imp_LocalFree
0x140026a12  nop     dword ptr [rax+rax+00h]
0x140026a17  mov     [rbp+hMem], 0
0x140026a1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140026a23  lea     rdx, [rbp+hMem]; StringSid
0x140026a27  mov     [rbp+var_18], rax
0x140026a2b  mov     [rbp+var_10], rax
0x140026a2f  mov     rcx, [rbx]; Sid
0x140026a32  call    cs:__imp_ConvertSidToStringSidW
0x140026a39  nop     dword ptr [rax+rax+00h]
0x140026a3e  test    eax, eax
0x140026a40  jz      loc_140026B19
0x140026a46  mov     rcx, rbx; pv
0x140026a49  call    cs:__imp_CoTaskMemFree
0x140026a50  nop     dword ptr [rax+rax+00h]
0x140026a55  jmp     short loc_140026A81
0x140026a57  mov     edx, 21h ; '!'; void *
0x140026a5c  mov     rcx, [rbp+8]; this
0x140026a60  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140026a67  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140026a6c  mov     rcx, rbx; pv
0x140026a6f  mov     edi, eax
0x140026a71  call    cs:__imp_CoTaskMemFree
0x140026a78  nop     dword ptr [rax+rax+00h]
0x140026a7d  test    edi, edi
0x140026a7f  js      short loc_140026ACF
0x140026a81  mov     rcx, [rbp+hMem]
0x140026a85  call    IsUserSidAssignedAccessSingleApp
0x140026a8a  mov     rcx, [rbp+hMem]; hMem
0x140026a8e  mov     ebx, eax
0x140026a90  test    rcx, rcx
0x140026a93  jz      short loc_140026AA1
0x140026a95  call    cs:__imp_LocalFree
0x140026a9c  nop     dword ptr [rax+rax+00h]
0x140026aa1  mov     eax, ebx
0x140026aa3  mov     rbx, [rsp+50h+arg_0]
0x140026aa8  mov     rdi, [rsp+50h+arg_10]
0x140026aad  add     rsp, 50h
0x140026ab1  pop     rbp
0x140026ab2  retn
0x140026ab4  mov     rcx, [rbp+8]; this
0x140026ab8  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140026abf  mov     r9d, 8007000Eh; char *
0x140026ac5  mov     edx, 20h ; ' '; void *
0x140026aca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026acf  mov     rcx, [rbp+hMem]; hMem
0x140026ad3  test    rcx, rcx
0x140026ad6  jz      short loc_140026AE4
0x140026ad8  call    cs:__imp_LocalFree
0x140026adf  nop     dword ptr [rax+rax+00h]
0x140026ae4  xor     eax, eax
0x140026ae6  jmp     short loc_140026AA3
0x140026ae8  call    cs:__imp_GetLastError
0x140026aef  nop     dword ptr [rax+rax+00h]
0x140026af4  cmp     eax, 7Ah ; 'z'
0x140026af7  jz      loc_1400269BF
0x140026afd  mov     rcx, [rbp+8]; this
0x140026b01  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140026b08  mov     edx, 1Dh; void *
0x140026b0d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140026b12  mov     edi, eax
0x140026b14  jmp     loc_140026A7D
0x140026b19  mov     edx, 22h ; '"'
0x140026b1e  jmp     loc_140026A5C
```
