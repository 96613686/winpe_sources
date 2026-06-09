# FwRpcAPIsGetAccessTokenFromClientBinding

- ea: `0x1800414d0`
- end: `0x180041635`
- name: `FwRpcAPIsGetAccessTokenFromClientBinding`
- size: `357`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180041308`
- `0x1800cd464`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x1800414d0`
- `0x18006a710`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004150e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004150e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180041529`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180041529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415b7`
- `RPCRT4!RpcImpersonateClient` at `0x1800414fc`
- `RPCRT4!RpcImpersonateClient` at `0x1800414fc`
- `RPCRT4!RpcRevertToSelf` at `0x18004154a`
- `RPCRT4!RpcRevertToSelf` at `0x18004154a`

## string_xrefs

- `0x180041622`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwRpcAPIsGetAccessTokenFromClientBinding(void *a1, __int64 a2, _QWORD *a3)
{
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  HANDLE CurrentThread; // rax
  __int64 v7; // rcx
  void *v8; // rax
  unsigned int v9; // eax
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
      v8 = TokenHandle;
      if ( !TokenHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v7);
        v8 = TokenHandle;
      }
      *a3 = v8;
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
    v9 = RpcRevertToSelf();
    if ( v9 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v9, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x1800414d0  mov     [rsp+arg_8], rbx
0x1800414d5  push    rdi
0x1800414d6  sub     rsp, 30h
0x1800414da  mov     rax, cs:__security_cookie
0x1800414e1  xor     rax, rsp
0x1800414e4  mov     [rsp+38h+var_10], rax
0x1800414e9  mov     rdi, r8
0x1800414ec  mov     [rsp+38h+TokenHandle], 0
0x1800414f5  mov     qword ptr [r8], 0
0x1800414fc  call    cs:__imp_RpcImpersonateClient
0x180041503  nop     dword ptr [rax+rax+00h]
0x180041508  mov     ebx, eax
0x18004150a  test    eax, eax
0x18004150c  jnz     short loc_180041579
0x18004150e  call    cs:__imp_GetCurrentThread
0x180041515  nop     dword ptr [rax+rax+00h]
0x18004151a  mov     rcx, rax; ThreadHandle
0x18004151d  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180041522  lea     edx, [rbx+8]; DesiredAccess
0x180041525  lea     r8d, [rbx+1]; OpenAsSelf
0x180041529  call    cs:__imp_OpenThreadToken
0x180041530  nop     dword ptr [rax+rax+00h]
0x180041535  test    eax, eax
0x180041537  jz      short loc_1800415B7
0x180041539  mov     rax, [rsp+38h+TokenHandle]
0x18004153e  test    rax, rax
0x180041541  jz      loc_180041610
0x180041547  mov     [rdi], rax
0x18004154a  call    cs:__imp_RpcRevertToSelf
0x180041551  nop     dword ptr [rax+rax+00h]
0x180041556  test    eax, eax
0x180041558  jnz     loc_18004161F
0x18004155e  mov     eax, ebx
0x180041560  mov     rcx, [rsp+38h+var_10]
0x180041565  xor     rcx, rsp; StackCookie
0x180041568  call    __security_check_cookie
0x18004156d  mov     rbx, [rsp+38h+arg_8]
0x180041572  add     rsp, 30h
0x180041576  pop     rdi
0x180041577  retn
0x180041579  jle     short loc_180041584
0x18004157b  movzx   ebx, ax
0x18004157e  or      ebx, 80070000h
0x180041584  mov     rcx, cs:WPP_GLOBAL_Control
0x18004158b  lea     rax, WPP_GLOBAL_Control
0x180041592  cmp     rcx, rax
0x180041595  jz      short loc_18004155E
0x180041597  test    byte ptr [rcx+1Ch], 1
0x18004159b  jz      short loc_18004155E
0x18004159d  mov     rcx, [rcx+10h]
0x1800415a1  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800415a8  mov     edx, 22h ; '"'
0x1800415ad  mov     r9d, ebx
0x1800415b0  call    WPP_SF_d
0x1800415b5  jmp     short loc_18004155E
0x1800415b7  call    cs:__imp_GetLastError
0x1800415be  nop     dword ptr [rax+rax+00h]
0x1800415c3  mov     ebx, eax
0x1800415c5  test    eax, eax
0x1800415c7  jle     short loc_1800415D2
0x1800415c9  movzx   ebx, ax
0x1800415cc  or      ebx, 80070000h
0x1800415d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800415d9  lea     rax, WPP_GLOBAL_Control
0x1800415e0  cmp     rcx, rax
0x1800415e3  jz      loc_18004154A
0x1800415e9  test    byte ptr [rcx+1Ch], 1
0x1800415ed  jz      loc_18004154A
0x1800415f3  mov     rcx, [rcx+10h]
0x1800415f7  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800415fe  mov     edx, 23h ; '#'
0x180041603  mov     r9d, ebx
0x180041606  call    WPP_SF_d
0x18004160b  jmp     loc_18004154A
0x180041610  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "localToken != NULL")
0x180041615  mov     rax, [rsp+38h+TokenHandle]
0x18004161a  jmp     loc_180041547
0x18004161f  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcRevertToSelf")
0x180041622  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180041629  mov     edx, eax
0x18004162b  call    MicrosoftTelemetryAssertTriggeredArgs
0x180041630  jmp     loc_18004155E
```
