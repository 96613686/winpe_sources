# SetDoSvcStartType(bool)

- ea: `0x1800acd4c`
- end: `0x1800acf42`
- name: `?SetDoSvcStartType@@YAJ_N@Z`
- size: `502`
- prototype: `__int64 __fastcall(unsigned __int8)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18007d520`
- `0x18007ef30`

## callees

- `0x180008618`
- `0x18000933c`
- `0x1800a1ea4`
- `0x1800acc2c`
- `0x1800acd4c`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!ChangeServiceConfigA` at `0x1800ace90`
- `api-ms-win-service-winsvc-l1-1-0!ChangeServiceConfigA` at `0x1800ace90`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800acdd0`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800acdd0`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800acd86`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800acd86`
- `api-ms-win-service-winsvc-l1-1-0!ChangeServiceConfig2A` at `0x1800acecf`
- `api-ms-win-service-winsvc-l1-1-0!ChangeServiceConfig2A` at `0x1800acecf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800acf01`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800acf10`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800acf01`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800acf10`

## string_xrefs

- `0x1800aced9`: `New service start type: %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall SetDoSvcStartType(unsigned __int8 a1)
{
  DWORD v1; // ebp
  SC_HANDLE v2; // rax
  const char *v3; // r9
  SC_HANDLE v4; // rdi
  bool v5; // r15
  unsigned int LastError; // esi
  SC_HANDLE v7; // rax
  const char *v8; // r9
  SC_HANDLE v9; // rbx
  bool v10; // r14
  __int64 v11; // rdx
  int ServiceStartType; // eax
  int lpBinaryPathName; // [rsp+20h] [rbp-78h]
  int Info; // [rsp+70h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v1 = a1 + 2;
  v2 = OpenSCManagerA(0, 0, 0x80000000);
  v4 = v2;
  v5 = v2 != 0;
  if ( !v2 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x34E,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
                  v3);
    goto LABEL_17;
  }
  v7 = OpenServiceA(v2, "dosvc", 0xC0000000);
  v9 = v7;
  v10 = v7 != 0;
  if ( !v7 )
  {
    v11 = 849;
LABEL_10:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v11,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
                  v8);
    goto LABEL_15;
  }
  Info = 0;
  ServiceStartType = GetServiceStartType(v7);
  LastError = ServiceStartType;
  if ( ServiceStartType < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x354,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
      (const char *)(unsigned int)ServiceStartType,
      lpBinaryPathName);
    goto LABEL_15;
  }
  if ( v1 != Info )
  {
    if ( !ChangeServiceConfigA(v9, 0xFFFFFFFF, v1, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      v11 = 866;
      goto LABEL_10;
    }
    if ( v1 == 2 )
    {
      Info = 1;
      ChangeServiceConfig2A(v9, 3u, &Info);
    }
    LogMessage(4u, "SetDoSvcStartType", 0x36Au, "New service start type: %u", v1);
  }
  LastError = 0;
LABEL_15:
  if ( v10 )
    CloseServiceHandle(v9);
LABEL_17:
  if ( v5 )
    CloseServiceHandle(v4);
  return LastError;
}

```

## disassembly

```asm
0x1800acd4c  mov     [rsp+arg_8], rbx
0x1800acd51  mov     [rsp+arg_10], rbp
0x1800acd56  mov     [rsp+arg_18], rsi
0x1800acd5b  push    rdi
0x1800acd5c  push    r14
0x1800acd5e  push    r15
0x1800acd60  sub     rsp, 80h
0x1800acd67  mov     rax, cs:__security_cookie
0x1800acd6e  xor     rax, rsp
0x1800acd71  mov     [rsp+98h+var_20], rax
0x1800acd76  movzx   ebp, cl
0x1800acd79  add     ebp, 2
0x1800acd7c  xor     edx, edx; lpDatabaseName
0x1800acd7e  xor     ecx, ecx; lpMachineName
0x1800acd80  mov     r8d, 80000000h; dwDesiredAccess
0x1800acd86  call    cs:__imp_OpenSCManagerA
0x1800acd8c  mov     rdi, rax
0x1800acd8f  mov     [rsp+98h+var_38], rax
0x1800acd94  test    rax, rax
0x1800acd97  setnz   r15b
0x1800acd9b  test    rax, rax
0x1800acd9e  jnz     short loc_1800ACDC0
0x1800acda0  mov     rcx, [rsp+98h]; this
0x1800acda8  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800acdaf  mov     edx, 34Eh; void *
0x1800acdb4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800acdb9  mov     esi, eax
0x1800acdbb  jmp     loc_1800ACF08
0x1800acdc0  mov     r8d, 0C0000000h; dwDesiredAccess
0x1800acdc6  lea     rdx, ServiceName; "dosvc"
0x1800acdcd  mov     rcx, rdi; hSCManager
0x1800acdd0  call    cs:__imp_OpenServiceA
0x1800acdd6  mov     rbx, rax
0x1800acdd9  mov     [rsp+98h+var_30], rax
0x1800acdde  test    rax, rax
0x1800acde1  setnz   r14b
0x1800acde5  test    rax, rax
0x1800acde8  jnz     short loc_1800ACDF4
0x1800acdea  mov     edx, 351h
0x1800acdef  jmp     loc_1800ACE9F
0x1800acdf4  mov     [rsp+98h+Info], 0
0x1800acdfc  lea     rdx, [rsp+98h+Info]
0x1800ace01  mov     rcx, rbx; hService
0x1800ace04  call    _GetServiceStartType
0x1800ace09  mov     esi, eax
0x1800ace0b  test    eax, eax
0x1800ace0d  jns     short loc_1800ACE30
0x1800ace0f  mov     rcx, [rsp+98h]; this
0x1800ace17  mov     r9d, eax; char *
0x1800ace1a  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ace21  mov     edx, 354h; void *
0x1800ace26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ace2b  jmp     loc_1800ACEF9
0x1800ace30  cmp     [rsp+98h+Info], 4
0x1800ace35  jz      loc_1800ACEF7
0x1800ace3b  cmp     ebp, [rsp+98h+Info]
0x1800ace3f  jz      loc_1800ACEF7
0x1800ace45  mov     [rsp+98h+lpDisplayName], 0; lpDisplayName
0x1800ace4e  mov     [rsp+98h+lpPassword], 0; lpPassword
0x1800ace57  mov     [rsp+98h+lpServiceStartName], 0; lpServiceStartName
0x1800ace60  mov     [rsp+98h+lpDependencies], 0; lpDependencies
0x1800ace69  mov     [rsp+98h+lpdwTagId], 0; lpdwTagId
0x1800ace72  mov     [rsp+98h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x1800ace7b  mov     [rsp+98h+lpBinaryPathName], 0; lpBinaryPathName
0x1800ace84  or      edx, 0FFFFFFFFh; dwServiceType
0x1800ace87  mov     r9d, edx; dwErrorControl
0x1800ace8a  mov     r8d, ebp; dwStartType
0x1800ace8d  mov     rcx, rbx; hService
0x1800ace90  call    cs:__imp_ChangeServiceConfigA
0x1800ace96  test    eax, eax
0x1800ace98  jnz     short loc_1800ACEB7
0x1800ace9a  mov     edx, 362h; void *
0x1800ace9f  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800acea6  mov     rcx, [rsp+98h]; this
0x1800aceae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800aceb3  mov     esi, eax
0x1800aceb5  jmp     short loc_1800ACEF9
0x1800aceb7  cmp     ebp, 2
0x1800aceba  jnz     short loc_1800ACED5
0x1800acebc  mov     [rsp+98h+Info], 1
0x1800acec4  lea     r8, [rsp+98h+Info]; lpInfo
0x1800acec9  lea     edx, [rbp+1]; dwInfoLevel
0x1800acecc  mov     rcx, rbx; hService
0x1800acecf  call    cs:__imp_ChangeServiceConfig2A
0x1800aced5  mov     dword ptr [rsp+98h+lpBinaryPathName], ebp
0x1800aced9  lea     r9, aNewServiceStar; "New service start type: %u"
0x1800acee0  mov     r8d, 36Ah; unsigned int
0x1800acee6  lea     rdx, aSetdosvcstartt; "SetDoSvcStartType"
0x1800aceed  mov     ecx, 4; unsigned __int8
0x1800acef2  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800acef7  xor     esi, esi
0x1800acef9  test    r14b, r14b
0x1800acefc  jz      short loc_1800ACF08
0x1800acefe  mov     rcx, rbx; hSCObject
0x1800acf01  call    cs:__imp_CloseServiceHandle
0x1800acf07  nop
0x1800acf08  test    r15b, r15b
0x1800acf0b  jz      short loc_1800ACF16
0x1800acf0d  mov     rcx, rdi; hSCObject
0x1800acf10  call    cs:__imp_CloseServiceHandle
0x1800acf16  mov     eax, esi
0x1800acf18  mov     rcx, [rsp+98h+var_20]
0x1800acf1d  xor     rcx, rsp; StackCookie
0x1800acf20  call    __security_check_cookie
0x1800acf25  lea     r11, [rsp+98h+var_18]
0x1800acf2d  mov     rbx, [r11+28h]
0x1800acf31  mov     rbp, [r11+30h]
0x1800acf35  mov     rsi, [r11+38h]
0x1800acf39  mov     rsp, r11
0x1800acf3c  pop     r15
0x1800acf3e  pop     r14
0x1800acf40  pop     rdi
0x1800acf41  retn
```
