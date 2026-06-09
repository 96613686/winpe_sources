# IsRPCClientNAPAgentService(void *)

- ea: `0x18003941c`
- end: `0x18003963e`
- name: `?IsRPCClientNAPAgentService@@YAHPEAX@Z`
- size: `546`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180038cf0`
- `0x1800cb1f0`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x18003941c`
- `0x18006a710`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180039463`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180039463`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003947e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003947e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003951a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003951a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395a7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800394d9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800394d9`
- `RPCRT4!RpcImpersonateClient` at `0x18003944d`
- `RPCRT4!RpcImpersonateClient` at `0x18003944d`
- `RPCRT4!RpcRevertToSelf` at `0x1800394a7`
- `RPCRT4!RpcRevertToSelf` at `0x1800394a7`
- `fwbase!FwCloseHandle` at `0x1800394ec`
- `fwbase!FwCloseHandle` at `0x1800394ec`

## string_xrefs

- `0x18003960b`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall IsRPCClientNAPAgentService(void *a1)
{
  void *v1; // rdi
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  __int64 v5; // rcx
  unsigned int v6; // eax
  __int64 v7; // rcx
  signed int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  signed int LastError; // eax
  void *TokenHandle; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL IsMember; // [rsp+28h] [rbp-20h] BYREF

  IsMember = 0;
  v1 = 0;
  TokenHandle = 0;
  v2 = RpcImpersonateClient(a1);
  v3 = v2;
  if ( !v2 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v1 = TokenHandle;
      if ( !TokenHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v5);
        v1 = TokenHandle;
      }
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v3);
    }
    v6 = RpcRevertToSelf();
    if ( v6 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v6, 0);
    goto LABEL_7;
  }
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  v7 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v3);
LABEL_7:
    v7 = WPP_GLOBAL_Control;
  }
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( (_UNKNOWN *)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 1) != 0 )
    {
      v10 = 18;
      v11 = v3;
      goto LABEL_16;
    }
  }
  else if ( !CheckTokenMembership(v1, &g_SidNAPAgentService, &IsMember) )
  {
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v10 = 19;
      v11 = (unsigned int)v9;
LABEL_16:
      WPP_SF_d(*(_QWORD *)(v7 + 16), v10, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, v11);
    }
  }
  FwCloseHandle(v1);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x18003941c  mov     [rsp+arg_8], rbx
0x180039421  mov     [rsp+arg_10], rsi
0x180039426  push    rdi
0x180039427  sub     rsp, 40h
0x18003942b  mov     rax, cs:__security_cookie
0x180039432  xor     rax, rsp
0x180039435  mov     [rsp+48h+var_18], rax
0x18003943a  mov     [rsp+48h+IsMember], 0
0x180039442  xor     edi, edi
0x180039444  mov     [rsp+48h+TokenHandle], 0
0x18003944d  call    cs:__imp_RpcImpersonateClient
0x180039454  nop     dword ptr [rax+rax+00h]
0x180039459  mov     ebx, eax
0x18003945b  test    eax, eax
0x18003945d  jnz     loc_18003955E
0x180039463  call    cs:__imp_GetCurrentThread
0x18003946a  nop     dword ptr [rax+rax+00h]
0x18003946f  mov     rcx, rax; ThreadHandle
0x180039472  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180039477  lea     edx, [rdi+8]; DesiredAccess
0x18003947a  lea     r8d, [rdi+1]; OpenAsSelf
0x18003947e  call    cs:__imp_OpenThreadToken
0x180039485  nop     dword ptr [rax+rax+00h]
0x18003948a  lea     rsi, WPP_GLOBAL_Control
0x180039491  test    eax, eax
0x180039493  jz      loc_1800395A7
0x180039499  mov     rdi, [rsp+48h+TokenHandle]
0x18003949e  test    rdi, rdi
0x1800394a1  jz      loc_1800395F9
0x1800394a7  call    cs:__imp_RpcRevertToSelf
0x1800394ae  nop     dword ptr [rax+rax+00h]
0x1800394b3  test    eax, eax
0x1800394b5  jnz     loc_180039608
0x1800394bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800394c2  test    ebx, ebx
0x1800394c4  js      loc_18003961E
0x1800394ca  lea     r8, [rsp+48h+IsMember]; IsMember
0x1800394cf  mov     rcx, rdi; TokenHandle
0x1800394d2  lea     rdx, ?g_SidNAPAgentService@@3PAEA; SidToCheck
0x1800394d9  call    cs:__imp_CheckTokenMembership
0x1800394e0  nop     dword ptr [rax+rax+00h]
0x1800394e5  test    eax, eax
0x1800394e7  jz      short loc_18003951A
0x1800394e9  mov     rcx, rdi
0x1800394ec  call    cs:__imp_FwCloseHandle
0x1800394f3  nop     dword ptr [rax+rax+00h]
0x1800394f8  mov     eax, [rsp+48h+IsMember]
0x1800394fc  mov     rcx, [rsp+48h+var_18]
0x180039501  xor     rcx, rsp; StackCookie
0x180039504  call    __security_check_cookie
0x180039509  mov     rbx, [rsp+48h+arg_8]
0x18003950e  mov     rsi, [rsp+48h+arg_10]
0x180039513  add     rsp, 40h
0x180039517  pop     rdi
0x180039518  retn
0x18003951a  call    cs:__imp_GetLastError
0x180039521  nop     dword ptr [rax+rax+00h]
0x180039526  test    eax, eax
0x180039528  jle     short loc_180039532
0x18003952a  movzx   eax, ax
0x18003952d  or      eax, 80070000h
0x180039532  mov     rcx, cs:WPP_GLOBAL_Control
0x180039539  cmp     rcx, rsi
0x18003953c  jz      short loc_1800394E9
0x18003953e  test    byte ptr [rcx+1Ch], 1
0x180039542  jz      short loc_1800394E9
0x180039544  mov     edx, 13h
0x180039549  mov     r9d, eax
0x18003954c  mov     rcx, [rcx+10h]
0x180039550  lea     r8, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x180039557  call    WPP_SF_d
0x18003955c  jmp     short loc_1800394E9
0x18003955e  jle     short loc_180039569
0x180039560  movzx   ebx, ax
0x180039563  or      ebx, 80070000h
0x180039569  mov     rcx, cs:WPP_GLOBAL_Control
0x180039570  lea     rsi, WPP_GLOBAL_Control
0x180039577  cmp     rcx, rsi
0x18003957a  jz      loc_1800394C2
0x180039580  test    byte ptr [rcx+1Ch], 1
0x180039584  jz      loc_1800394C2
0x18003958a  mov     rcx, [rcx+10h]
0x18003958e  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180039595  mov     edx, 22h ; '"'
0x18003959a  mov     r9d, ebx
0x18003959d  call    WPP_SF_d
0x1800395a2  jmp     loc_1800394BB
0x1800395a7  call    cs:__imp_GetLastError
0x1800395ae  nop     dword ptr [rax+rax+00h]
0x1800395b3  mov     ebx, eax
0x1800395b5  test    eax, eax
0x1800395b7  jle     short loc_1800395C2
0x1800395b9  movzx   ebx, ax
0x1800395bc  or      ebx, 80070000h
0x1800395c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800395c9  cmp     rcx, rsi
0x1800395cc  jz      loc_1800394A7
0x1800395d2  test    byte ptr [rcx+1Ch], 1
0x1800395d6  jz      loc_1800394A7
0x1800395dc  mov     rcx, [rcx+10h]
0x1800395e0  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800395e7  mov     edx, 23h ; '#'
0x1800395ec  mov     r9d, ebx
0x1800395ef  call    WPP_SF_d
0x1800395f4  jmp     loc_1800394A7
0x1800395f9  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "localToken != NULL")
0x1800395fe  mov     rdi, [rsp+48h+TokenHandle]
0x180039603  jmp     loc_1800394A7
0x180039608  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcRevertToSelf")
0x18003960b  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180039612  mov     edx, eax
0x180039614  call    MicrosoftTelemetryAssertTriggeredArgs
0x180039619  jmp     loc_1800394BB
0x18003961e  cmp     rcx, rsi
0x180039621  jz      loc_1800394E9
0x180039627  test    byte ptr [rcx+1Ch], 1
0x18003962b  jz      loc_1800394E9
0x180039631  mov     edx, 12h
0x180039636  mov     r9d, ebx
0x180039639  jmp     loc_18003954C
```
