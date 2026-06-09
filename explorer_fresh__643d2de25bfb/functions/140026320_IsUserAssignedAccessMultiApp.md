# IsUserAssignedAccessMultiApp

- ea: `0x140026320`
- end: `0x1400264e7`
- name: `IsUserAssignedAccessMultiApp`
- size: `455`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `15`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140008bec`
- `0x14001e264`
- `0x140065d58`
- `0x14008eb00`
- `0x140090b10`
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

- `0x140026320`
- `0x140026ddc`
- `0x14009ac68`
- `0x14009de4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400264ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400264ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400263c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140026459`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002649c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400263c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140026459`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002649c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026405`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002642d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140026405`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002642d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002637e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002637e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140026367`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400263ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140026367`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400263ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400263ee`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400263ee`

## string_xrefs

- `0x14002641c`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x14002647c`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x1400264c5`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`

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
0x140026320  mov     [rsp-8+arg_0], rbx
0x140026325  mov     [rsp-8+arg_10], rdi
0x14002632a  push    rbp
0x14002632b  mov     rbp, rsp
0x14002632e  sub     rsp, 50h
0x140026332  xor     r9d, r9d; TokenInformationLength
0x140026335  mov     [rbp+hMem], 0
0x14002633d  lea     rax, [rbp+TokenInformationLength]
0x140026341  mov     [rbp+var_18], 0
0x140026349  xor     r8d, r8d; TokenInformation
0x14002634c  mov     [rbp+var_10], 0
0x140026354  mov     rdi, rcx
0x140026357  mov     [rbp+TokenInformationLength], 0
0x14002635e  lea     edx, [r9+1]; TokenInformationClass
0x140026362  mov     qword ptr [rsp+50h+ReturnLength], rax; int
0x140026367  call    cs:__imp_GetTokenInformation
0x14002636e  nop     dword ptr [rax+rax+00h]
0x140026373  test    eax, eax
0x140026375  jz      loc_1400264AC
0x14002637b  mov     ecx, [rbp+TokenInformationLength]; cb
0x14002637e  call    cs:__imp_CoTaskMemAlloc
0x140026385  nop     dword ptr [rax+rax+00h]
0x14002638a  mov     rbx, rax
0x14002638d  test    rax, rax
0x140026390  jz      loc_140026478
0x140026396  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14002639a  lea     rax, [rbp+TokenInformationLength]
0x14002639e  mov     r8, rbx; TokenInformation
0x1400263a1  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x1400263a6  mov     edx, 1; TokenInformationClass
0x1400263ab  mov     rcx, rdi; TokenHandle
0x1400263ae  call    cs:__imp_GetTokenInformation
0x1400263b5  nop     dword ptr [rax+rax+00h]
0x1400263ba  test    eax, eax
0x1400263bc  jz      short loc_140026413
0x1400263be  mov     rcx, [rbp+hMem]; hMem
0x1400263c2  test    rcx, rcx
0x1400263c5  jz      short loc_1400263DB
0x1400263c7  call    cs:__imp_LocalFree
0x1400263ce  nop     dword ptr [rax+rax+00h]
0x1400263d3  mov     [rbp+hMem], 0
0x1400263db  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400263df  lea     rdx, [rbp+hMem]; StringSid
0x1400263e3  mov     [rbp+var_18], rax
0x1400263e7  mov     [rbp+var_10], rax
0x1400263eb  mov     rcx, [rbx]; Sid
0x1400263ee  call    cs:__imp_ConvertSidToStringSidW
0x1400263f5  nop     dword ptr [rax+rax+00h]
0x1400263fa  test    eax, eax
0x1400263fc  jz      loc_1400264DD
0x140026402  mov     rcx, rbx; pv
0x140026405  call    cs:__imp_CoTaskMemFree
0x14002640c  nop     dword ptr [rax+rax+00h]
0x140026411  jmp     short loc_14002643D
0x140026413  mov     edx, 21h ; '!'; void *
0x140026418  mov     rcx, [rbp+8]; this
0x14002641c  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140026423  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140026428  mov     rcx, rbx; pv
0x14002642b  mov     edi, eax
0x14002642d  call    cs:__imp_CoTaskMemFree
0x140026434  nop     dword ptr [rax+rax+00h]
0x140026439  test    edi, edi
0x14002643b  js      short loc_140026493
0x14002643d  mov     rcx, [rbp+hMem]
0x140026441  xor     edx, edx
0x140026443  call    GetAssignedAccessTypeForUser
0x140026448  mov     rcx, [rbp+hMem]; hMem
0x14002644c  xor     ebx, ebx
0x14002644e  cmp     eax, 2
0x140026451  setz    bl
0x140026454  test    rcx, rcx
0x140026457  jz      short loc_140026465
0x140026459  call    cs:__imp_LocalFree
0x140026460  nop     dword ptr [rax+rax+00h]
0x140026465  mov     eax, ebx
0x140026467  mov     rbx, [rsp+50h+arg_0]
0x14002646c  mov     rdi, [rsp+50h+arg_10]
0x140026471  add     rsp, 50h
0x140026475  pop     rbp
0x140026476  retn
0x140026478  mov     rcx, [rbp+8]; this
0x14002647c  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140026483  mov     r9d, 8007000Eh; char *
0x140026489  mov     edx, 20h ; ' '; void *
0x14002648e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026493  mov     rcx, [rbp+hMem]; hMem
0x140026497  test    rcx, rcx
0x14002649a  jz      short loc_1400264A8
0x14002649c  call    cs:__imp_LocalFree
0x1400264a3  nop     dword ptr [rax+rax+00h]
0x1400264a8  xor     eax, eax
0x1400264aa  jmp     short loc_140026467
0x1400264ac  call    cs:__imp_GetLastError
0x1400264b3  nop     dword ptr [rax+rax+00h]
0x1400264b8  cmp     eax, 7Ah ; 'z'
0x1400264bb  jz      loc_14002637B
0x1400264c1  mov     rcx, [rbp+8]; this
0x1400264c5  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x1400264cc  mov     edx, 1Dh; void *
0x1400264d1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400264d6  mov     edi, eax
0x1400264d8  jmp     loc_140026439
0x1400264dd  mov     edx, 22h ; '"'
0x1400264e2  jmp     loc_140026418
```
