# IsUserAssignedAccessSingleApp

- ea: `0x14003401c`
- end: `0x14003419e`
- name: `IsUserAssignedAccessSingleApp`
- size: `386`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `14`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400137b8`
- `0x140033c8c`
- `0x140062518`
- `0x140089140`
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

- `0x14003401c`
- `0x1400341a4`
- `0x1400954e0`
- `0x1400987b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034169`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400340b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140034123`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003415f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400340b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140034123`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003415f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400340e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400340e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140034105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140034074`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140034074`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140034063`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003409e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140034063`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003409e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400340d2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400340d2`

## string_xrefs

- `0x1400340f4`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x14003413f`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x14003417c`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`

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
        v6 = IsUserSidAssignedAccessSingleApp((unsigned __int16 *)hMem);
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
0x14003401c  mov     [rsp-8+arg_0], rbx
0x140034021  mov     [rsp-8+arg_10], rdi
0x140034026  push    rbp
0x140034027  mov     rbp, rsp
0x14003402a  sub     rsp, 50h
0x14003402e  xor     r9d, r9d; TokenInformationLength
0x140034031  mov     [rbp+hMem], 0
0x140034039  lea     rax, [rbp+TokenInformationLength]
0x14003403d  mov     [rbp+var_18], 0
0x140034045  xor     r8d, r8d; TokenInformation
0x140034048  mov     [rbp+var_10], 0
0x140034050  mov     rdi, rcx
0x140034053  mov     [rbp+TokenInformationLength], 0
0x14003405a  lea     edx, [r9+1]; TokenInformationClass
0x14003405e  mov     qword ptr [rsp+50h+ReturnLength], rax; int
0x140034063  call    cs:__imp_GetTokenInformation
0x140034069  test    eax, eax
0x14003406b  jz      loc_140034169
0x140034071  mov     ecx, [rbp+TokenInformationLength]; cb
0x140034074  call    cs:__imp_CoTaskMemAlloc
0x14003407a  mov     rbx, rax
0x14003407d  test    rax, rax
0x140034080  jz      loc_14003413B
0x140034086  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14003408a  lea     rax, [rbp+TokenInformationLength]
0x14003408e  mov     r8, rbx; TokenInformation
0x140034091  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x140034096  mov     edx, 1; TokenInformationClass
0x14003409b  mov     rcx, rdi; TokenHandle
0x14003409e  call    cs:__imp_GetTokenInformation
0x1400340a4  test    eax, eax
0x1400340a6  jz      short loc_1400340EB
0x1400340a8  mov     rcx, [rbp+hMem]; hMem
0x1400340ac  test    rcx, rcx
0x1400340af  jz      short loc_1400340BF
0x1400340b1  call    cs:__imp_LocalFree
0x1400340b7  mov     [rbp+hMem], 0
0x1400340bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400340c3  lea     rdx, [rbp+hMem]; StringSid
0x1400340c7  mov     [rbp+var_18], rax
0x1400340cb  mov     [rbp+var_10], rax
0x1400340cf  mov     rcx, [rbx]; Sid
0x1400340d2  call    cs:__imp_ConvertSidToStringSidW
0x1400340d8  test    eax, eax
0x1400340da  jz      loc_140034194
0x1400340e0  mov     rcx, rbx; pv
0x1400340e3  call    cs:__imp_CoTaskMemFree
0x1400340e9  jmp     short loc_14003410F
0x1400340eb  mov     edx, 21h ; '!'; void *
0x1400340f0  mov     rcx, [rbp+8]; this
0x1400340f4  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x1400340fb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140034100  mov     rcx, rbx; pv
0x140034103  mov     edi, eax
0x140034105  call    cs:__imp_CoTaskMemFree
0x14003410b  test    edi, edi
0x14003410d  js      short loc_140034156
0x14003410f  mov     rcx, [rbp+hMem]
0x140034113  call    IsUserSidAssignedAccessSingleApp
0x140034118  mov     rcx, [rbp+hMem]; hMem
0x14003411c  mov     ebx, eax
0x14003411e  test    rcx, rcx
0x140034121  jz      short loc_140034129
0x140034123  call    cs:__imp_LocalFree
0x140034129  mov     eax, ebx
0x14003412b  mov     rbx, [rsp+50h+arg_0]
0x140034130  mov     rdi, [rsp+50h+arg_10]
0x140034135  add     rsp, 50h
0x140034139  pop     rbp
0x14003413a  retn
0x14003413b  mov     rcx, [rbp+8]; this
0x14003413f  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140034146  mov     r9d, 8007000Eh; char *
0x14003414c  mov     edx, 20h ; ' '; void *
0x140034151  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140034156  mov     rcx, [rbp+hMem]; hMem
0x14003415a  test    rcx, rcx
0x14003415d  jz      short loc_140034165
0x14003415f  call    cs:__imp_LocalFree
0x140034165  xor     eax, eax
0x140034167  jmp     short loc_14003412B
0x140034169  call    cs:__imp_GetLastError
0x14003416f  cmp     eax, 7Ah ; 'z'
0x140034172  jz      loc_140034071
0x140034178  mov     rcx, [rbp+8]; this
0x14003417c  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140034183  mov     edx, 1Dh; void *
0x140034188  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14003418d  mov     edi, eax
0x14003418f  jmp     loc_14003410B
0x140034194  mov     edx, 22h ; '"'
0x140034199  jmp     loc_1400340F0
```
