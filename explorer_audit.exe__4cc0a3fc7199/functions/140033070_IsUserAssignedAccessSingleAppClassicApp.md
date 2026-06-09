# IsUserAssignedAccessSingleAppClassicApp

- ea: `0x140033070`
- end: `0x1400331fa`
- name: `IsUserAssignedAccessSingleAppClassicApp`
- size: `394`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `13`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400137b8`
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

- `0x140033070`
- `0x1400345a0`
- `0x1400954e0`
- `0x1400987b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400331c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400331c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140033105`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003317f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400331bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140033105`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003317f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400331bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033137`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033159`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033137`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033159`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400330c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400330c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400330b7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400330f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400330b7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400330f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140033126`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140033126`

## string_xrefs

- `0x140033148`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x14003319b`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x1400331d8`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`

## pseudocode

```c
_BOOL8 __fastcall IsUserAssignedAccessSingleAppClassicApp(HANDLE TokenHandle)
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
        v6 = GetAssignedAccessTypeForUser((unsigned __int16 *)hMem) == 3;
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
0x140033070  mov     [rsp-8+arg_0], rbx
0x140033075  mov     [rsp-8+arg_10], rdi
0x14003307a  push    rbp
0x14003307b  mov     rbp, rsp
0x14003307e  sub     rsp, 50h
0x140033082  xor     r9d, r9d; TokenInformationLength
0x140033085  mov     [rbp+hMem], 0
0x14003308d  lea     rax, [rbp+TokenInformationLength]
0x140033091  mov     [rbp+var_18], 0
0x140033099  xor     r8d, r8d; TokenInformation
0x14003309c  mov     [rbp+var_10], 0
0x1400330a4  mov     rdi, rcx
0x1400330a7  mov     [rbp+TokenInformationLength], 0
0x1400330ae  lea     edx, [r9+1]; TokenInformationClass
0x1400330b2  mov     qword ptr [rsp+50h+ReturnLength], rax; int
0x1400330b7  call    cs:__imp_GetTokenInformation
0x1400330bd  test    eax, eax
0x1400330bf  jz      loc_1400331C5
0x1400330c5  mov     ecx, [rbp+TokenInformationLength]; cb
0x1400330c8  call    cs:__imp_CoTaskMemAlloc
0x1400330ce  mov     rbx, rax
0x1400330d1  test    rax, rax
0x1400330d4  jz      loc_140033197
0x1400330da  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1400330de  lea     rax, [rbp+TokenInformationLength]
0x1400330e2  mov     r8, rbx; TokenInformation
0x1400330e5  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x1400330ea  mov     edx, 1; TokenInformationClass
0x1400330ef  mov     rcx, rdi; TokenHandle
0x1400330f2  call    cs:__imp_GetTokenInformation
0x1400330f8  test    eax, eax
0x1400330fa  jz      short loc_14003313F
0x1400330fc  mov     rcx, [rbp+hMem]; hMem
0x140033100  test    rcx, rcx
0x140033103  jz      short loc_140033113
0x140033105  call    cs:__imp_LocalFree
0x14003310b  mov     [rbp+hMem], 0
0x140033113  or      rax, 0FFFFFFFFFFFFFFFFh
0x140033117  lea     rdx, [rbp+hMem]; StringSid
0x14003311b  mov     [rbp+var_18], rax
0x14003311f  mov     [rbp+var_10], rax
0x140033123  mov     rcx, [rbx]; Sid
0x140033126  call    cs:__imp_ConvertSidToStringSidW
0x14003312c  test    eax, eax
0x14003312e  jz      loc_1400331F0
0x140033134  mov     rcx, rbx; pv
0x140033137  call    cs:__imp_CoTaskMemFree
0x14003313d  jmp     short loc_140033163
0x14003313f  mov     edx, 21h ; '!'; void *
0x140033144  mov     rcx, [rbp+8]; this
0x140033148  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x14003314f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140033154  mov     rcx, rbx; pv
0x140033157  mov     edi, eax
0x140033159  call    cs:__imp_CoTaskMemFree
0x14003315f  test    edi, edi
0x140033161  js      short loc_1400331B2
0x140033163  mov     rcx, [rbp+hMem]
0x140033167  mov     dl, 1
0x140033169  call    GetAssignedAccessTypeForUser
0x14003316e  mov     rcx, [rbp+hMem]; hMem
0x140033172  xor     ebx, ebx
0x140033174  cmp     eax, 3
0x140033177  setz    bl
0x14003317a  test    rcx, rcx
0x14003317d  jz      short loc_140033185
0x14003317f  call    cs:__imp_LocalFree
0x140033185  mov     eax, ebx
0x140033187  mov     rbx, [rsp+50h+arg_0]
0x14003318c  mov     rdi, [rsp+50h+arg_10]
0x140033191  add     rsp, 50h
0x140033195  pop     rbp
0x140033196  retn
0x140033197  mov     rcx, [rbp+8]; this
0x14003319b  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x1400331a2  mov     r9d, 8007000Eh; char *
0x1400331a8  mov     edx, 20h ; ' '; void *
0x1400331ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400331b2  mov     rcx, [rbp+hMem]; hMem
0x1400331b6  test    rcx, rcx
0x1400331b9  jz      short loc_1400331C1
0x1400331bb  call    cs:__imp_LocalFree
0x1400331c1  xor     eax, eax
0x1400331c3  jmp     short loc_140033187
0x1400331c5  call    cs:__imp_GetLastError
0x1400331cb  cmp     eax, 7Ah ; 'z'
0x1400331ce  jz      loc_1400330C5
0x1400331d4  mov     rcx, [rbp+8]; this
0x1400331d8  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x1400331df  mov     edx, 1Dh; void *
0x1400331e4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400331e9  mov     edi, eax
0x1400331eb  jmp     loc_14003315F
0x1400331f0  mov     edx, 22h ; '"'
0x1400331f5  jmp     loc_140033144
```
