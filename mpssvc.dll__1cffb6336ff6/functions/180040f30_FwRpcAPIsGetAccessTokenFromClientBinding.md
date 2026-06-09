# FwRpcAPIsGetAccessTokenFromClientBinding

- ea: `0x180040f30`
- end: `0x180041076`
- name: `FwRpcAPIsGetAccessTokenFromClientBinding`
- size: `326`
- prototype: `__int64 __fastcall(void *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180040d84`
- `0x1800c5f88`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x180040f30`
- `0x1800670c0`
- `0x18006f520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180040f7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180040f7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180040f68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180040f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ffe`
- `RPCRT4!RpcRevertToSelf` at `0x180040f98`
- `RPCRT4!RpcRevertToSelf` at `0x180040f98`
- `RPCRT4!RpcImpersonateClient` at `0x180040f5c`
- `RPCRT4!RpcImpersonateClient` at `0x180040f5c`

## string_xrefs

- `0x180041063`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwRpcAPIsGetAccessTokenFromClientBinding(void *a1, __int64 a2, _QWORD *a3)
{
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  HANDLE CurrentThread; // rax
  void *v7; // rax
  unsigned int v8; // eax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  TokenHandle = 0;
  *a3 = 0;
  v4 = RpcImpersonateClient(a1);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v5);
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v7 = TokenHandle;
      if ( !TokenHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v7 = TokenHandle;
      }
      *a3 = v7;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v5);
    }
    v8 = RpcRevertToSelf();
    if ( v8 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v8, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x180040f30  mov     [rsp+arg_8], rbx
0x180040f35  push    rdi
0x180040f36  sub     rsp, 30h
0x180040f3a  mov     rax, cs:__security_cookie
0x180040f41  xor     rax, rsp
0x180040f44  mov     [rsp+38h+var_10], rax
0x180040f49  mov     rdi, r8
0x180040f4c  mov     [rsp+38h+TokenHandle], 0
0x180040f55  mov     qword ptr [r8], 0
0x180040f5c  call    cs:__imp_RpcImpersonateClient
0x180040f62  mov     ebx, eax
0x180040f64  test    eax, eax
0x180040f66  jnz     short loc_180040FC0
0x180040f68  call    cs:__imp_GetCurrentThread
0x180040f6e  mov     rcx, rax; ThreadHandle
0x180040f71  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180040f76  lea     edx, [rbx+8]; DesiredAccess
0x180040f79  lea     r8d, [rbx+1]; OpenAsSelf
0x180040f7d  call    cs:__imp_OpenThreadToken
0x180040f83  test    eax, eax
0x180040f85  jz      short loc_180040FFE
0x180040f87  mov     rax, [rsp+38h+TokenHandle]
0x180040f8c  test    rax, rax
0x180040f8f  jz      loc_180041051
0x180040f95  mov     [rdi], rax
0x180040f98  call    cs:__imp_RpcRevertToSelf
0x180040f9e  test    eax, eax
0x180040fa0  jnz     loc_180041060
0x180040fa6  mov     eax, ebx
0x180040fa8  mov     rcx, [rsp+38h+var_10]
0x180040fad  xor     rcx, rsp; StackCookie
0x180040fb0  call    __security_check_cookie
0x180040fb5  mov     rbx, [rsp+38h+arg_8]
0x180040fba  add     rsp, 30h
0x180040fbe  pop     rdi
0x180040fbf  retn
0x180040fc0  jle     short loc_180040FCB
0x180040fc2  movzx   ebx, ax
0x180040fc5  or      ebx, 80070000h
0x180040fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180040fd2  lea     rax, WPP_GLOBAL_Control
0x180040fd9  cmp     rcx, rax
0x180040fdc  jz      short loc_180040FA6
0x180040fde  test    byte ptr [rcx+1Ch], 1
0x180040fe2  jz      short loc_180040FA6
0x180040fe4  mov     rcx, [rcx+10h]
0x180040fe8  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180040fef  mov     edx, 22h ; '"'
0x180040ff4  mov     r9d, ebx
0x180040ff7  call    WPP_SF_d
0x180040ffc  jmp     short loc_180040FA6
0x180040ffe  call    cs:__imp_GetLastError
0x180041004  mov     ebx, eax
0x180041006  test    eax, eax
0x180041008  jle     short loc_180041013
0x18004100a  movzx   ebx, ax
0x18004100d  or      ebx, 80070000h
0x180041013  mov     rcx, cs:WPP_GLOBAL_Control
0x18004101a  lea     rax, WPP_GLOBAL_Control
0x180041021  cmp     rcx, rax
0x180041024  jz      loc_180040F98
0x18004102a  test    byte ptr [rcx+1Ch], 1
0x18004102e  jz      loc_180040F98
0x180041034  mov     rcx, [rcx+10h]
0x180041038  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18004103f  mov     edx, 23h ; '#'
0x180041044  mov     r9d, ebx
0x180041047  call    WPP_SF_d
0x18004104c  jmp     loc_180040F98
0x180041051  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180041056  mov     rax, [rsp+38h+TokenHandle]
0x18004105b  jmp     loc_180040F95
0x180041060  xor     r8d, r8d
0x180041063  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x18004106a  mov     edx, eax
0x18004106c  call    MicrosoftTelemetryAssertTriggeredArgs
0x180041071  jmp     loc_180040FA6
```
