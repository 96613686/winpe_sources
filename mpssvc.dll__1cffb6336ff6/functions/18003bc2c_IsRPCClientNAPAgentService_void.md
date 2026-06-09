# IsRPCClientNAPAgentService(void *)

- ea: `0x18003bc2c`
- end: `0x18003be1d`
- name: `?IsRPCClientNAPAgentService@@YAHPEAX@Z`
- size: `497`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003b580`
- `0x1800c4010`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x18003bc2c`
- `0x1800670c0`
- `0x18006f520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003bc82`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003bc82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003bc6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003bc6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd8c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003bcd1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003bcd1`
- `RPCRT4!RpcRevertToSelf` at `0x18003bca5`
- `RPCRT4!RpcRevertToSelf` at `0x18003bca5`
- `RPCRT4!RpcImpersonateClient` at `0x18003bc5d`
- `RPCRT4!RpcImpersonateClient` at `0x18003bc5d`
- `fwbase!FwCloseHandle` at `0x18003bcde`
- `fwbase!FwCloseHandle` at `0x18003bcde`

## string_xrefs

- `0x18003bdea`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall IsRPCClientNAPAgentService(void *a1)
{
  void *v1; // rdi
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  unsigned int v5; // eax
  __int64 v6; // rcx
  signed int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r9
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
        MicrosoftTelemetryAssertTriggeredNoArgs();
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
    v5 = RpcRevertToSelf();
    if ( v5 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v5, 0);
    goto LABEL_7;
  }
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  v6 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v3);
LABEL_7:
    v6 = WPP_GLOBAL_Control;
  }
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( (_UNKNOWN *)v6 != &WPP_GLOBAL_Control && (*(_BYTE *)(v6 + 28) & 1) != 0 )
    {
      v9 = 18;
      v10 = v3;
      goto LABEL_16;
    }
  }
  else if ( !CheckTokenMembership(v1, &g_SidNAPAgentService, &IsMember) )
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v9 = 19;
      v10 = (unsigned int)v8;
LABEL_16:
      WPP_SF_d(*(_QWORD *)(v6 + 16), v9, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, v10);
    }
  }
  FwCloseHandle(v1);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x18003bc2c  mov     [rsp+arg_8], rbx
0x18003bc31  mov     [rsp+arg_10], rsi
0x18003bc36  push    rdi
0x18003bc37  sub     rsp, 40h
0x18003bc3b  mov     rax, cs:__security_cookie
0x18003bc42  xor     rax, rsp
0x18003bc45  mov     [rsp+48h+var_18], rax
0x18003bc4a  mov     [rsp+48h+IsMember], 0
0x18003bc52  xor     edi, edi
0x18003bc54  mov     [rsp+48h+TokenHandle], 0
0x18003bc5d  call    cs:__imp_RpcImpersonateClient
0x18003bc63  mov     ebx, eax
0x18003bc65  test    eax, eax
0x18003bc67  jnz     loc_18003BD43
0x18003bc6d  call    cs:__imp_GetCurrentThread
0x18003bc73  mov     rcx, rax; ThreadHandle
0x18003bc76  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18003bc7b  lea     edx, [rdi+8]; DesiredAccess
0x18003bc7e  lea     r8d, [rdi+1]; OpenAsSelf
0x18003bc82  call    cs:__imp_OpenThreadToken
0x18003bc88  lea     rsi, WPP_GLOBAL_Control
0x18003bc8f  test    eax, eax
0x18003bc91  jz      loc_18003BD8C
0x18003bc97  mov     rdi, [rsp+48h+TokenHandle]
0x18003bc9c  test    rdi, rdi
0x18003bc9f  jz      loc_18003BDD8
0x18003bca5  call    cs:__imp_RpcRevertToSelf
0x18003bcab  test    eax, eax
0x18003bcad  jnz     loc_18003BDE7
0x18003bcb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bcba  test    ebx, ebx
0x18003bcbc  js      loc_18003BDFD
0x18003bcc2  lea     r8, [rsp+48h+IsMember]; IsMember
0x18003bcc7  mov     rcx, rdi; TokenHandle
0x18003bcca  lea     rdx, ?g_SidNAPAgentService@@3PAEA; SidToCheck
0x18003bcd1  call    cs:__imp_CheckTokenMembership
0x18003bcd7  test    eax, eax
0x18003bcd9  jz      short loc_18003BD05
0x18003bcdb  mov     rcx, rdi
0x18003bcde  call    cs:__imp_FwCloseHandle
0x18003bce4  mov     eax, [rsp+48h+IsMember]
0x18003bce8  mov     rcx, [rsp+48h+var_18]
0x18003bced  xor     rcx, rsp; StackCookie
0x18003bcf0  call    __security_check_cookie
0x18003bcf5  mov     rbx, [rsp+48h+arg_8]
0x18003bcfa  mov     rsi, [rsp+48h+arg_10]
0x18003bcff  add     rsp, 40h
0x18003bd03  pop     rdi
0x18003bd04  retn
0x18003bd05  call    cs:__imp_GetLastError
0x18003bd0b  test    eax, eax
0x18003bd0d  jle     short loc_18003BD17
0x18003bd0f  movzx   eax, ax
0x18003bd12  or      eax, 80070000h
0x18003bd17  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bd1e  cmp     rcx, rsi
0x18003bd21  jz      short loc_18003BCDB
0x18003bd23  test    byte ptr [rcx+1Ch], 1
0x18003bd27  jz      short loc_18003BCDB
0x18003bd29  mov     edx, 13h
0x18003bd2e  mov     r9d, eax
0x18003bd31  mov     rcx, [rcx+10h]
0x18003bd35  lea     r8, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x18003bd3c  call    WPP_SF_d
0x18003bd41  jmp     short loc_18003BCDB
0x18003bd43  jle     short loc_18003BD4E
0x18003bd45  movzx   ebx, ax
0x18003bd48  or      ebx, 80070000h
0x18003bd4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bd55  lea     rsi, WPP_GLOBAL_Control
0x18003bd5c  cmp     rcx, rsi
0x18003bd5f  jz      loc_18003BCBA
0x18003bd65  test    byte ptr [rcx+1Ch], 1
0x18003bd69  jz      loc_18003BCBA
0x18003bd6f  mov     rcx, [rcx+10h]
0x18003bd73  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003bd7a  mov     edx, 22h ; '"'
0x18003bd7f  mov     r9d, ebx
0x18003bd82  call    WPP_SF_d
0x18003bd87  jmp     loc_18003BCB3
0x18003bd8c  call    cs:__imp_GetLastError
0x18003bd92  mov     ebx, eax
0x18003bd94  test    eax, eax
0x18003bd96  jle     short loc_18003BDA1
0x18003bd98  movzx   ebx, ax
0x18003bd9b  or      ebx, 80070000h
0x18003bda1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bda8  cmp     rcx, rsi
0x18003bdab  jz      loc_18003BCA5
0x18003bdb1  test    byte ptr [rcx+1Ch], 1
0x18003bdb5  jz      loc_18003BCA5
0x18003bdbb  mov     rcx, [rcx+10h]
0x18003bdbf  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003bdc6  mov     edx, 23h ; '#'
0x18003bdcb  mov     r9d, ebx
0x18003bdce  call    WPP_SF_d
0x18003bdd3  jmp     loc_18003BCA5
0x18003bdd8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003bddd  mov     rdi, [rsp+48h+TokenHandle]
0x18003bde2  jmp     loc_18003BCA5
0x18003bde7  xor     r8d, r8d
0x18003bdea  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x18003bdf1  mov     edx, eax
0x18003bdf3  call    MicrosoftTelemetryAssertTriggeredArgs
0x18003bdf8  jmp     loc_18003BCB3
0x18003bdfd  cmp     rcx, rsi
0x18003be00  jz      loc_18003BCDB
0x18003be06  test    byte ptr [rcx+1Ch], 1
0x18003be0a  jz      loc_18003BCDB
0x18003be10  mov     edx, 12h
0x18003be15  mov     r9d, ebx
0x18003be18  jmp     loc_18003BD31
```
