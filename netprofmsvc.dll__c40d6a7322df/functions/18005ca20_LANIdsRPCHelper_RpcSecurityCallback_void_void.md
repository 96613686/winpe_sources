# LANIdsRPCHelper::RpcSecurityCallback(void * *,void *)

- ea: `0x18005ca20`
- end: `0x18005cbb7`
- name: `?RpcSecurityCallback@LANIdsRPCHelper@@CAJPEAPEAXPEAX@Z`
- size: `407`
- prototype: `__int64 __fastcall(void **, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x180018968`
- `0x18005ca20`
- `0x1800a88a0`
- `0x1800a9738`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005cb0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005cb0a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005cb21`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005cb21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cb48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cb48`
- `RPCRT4!RpcRevertToSelf` at `0x18005cb2e`
- `RPCRT4!RpcRevertToSelf` at `0x18005cb36`
- `RPCRT4!RpcRevertToSelf` at `0x18005cb2e`
- `RPCRT4!RpcRevertToSelf` at `0x18005cb36`
- `RPCRT4!RpcImpersonateClient` at `0x18005cb00`
- `RPCRT4!RpcImpersonateClient` at `0x18005cb00`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x18005ca96`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x18005ca96`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18005cab6`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18005cab6`

## pseudocode

```c
__int64 __fastcall LANIdsRPCHelper::RpcSecurityCallback(void **a1, void *a2)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rcx
  HANDLE CurrentThread; // rax
  unsigned int v8; // ebx
  void *TokenHandle; // [rsp+28h] [rbp-A0h] BYREF
  unsigned int Type[4]; // [rsp+30h] [rbp-98h] BYREF
  _DWORD RpcCallAttributes[10]; // [rsp+40h] [rbp-88h] BYREF
  int v12; // [rsp+68h] [rbp-60h]
  int v13; // [rsp+6Ch] [rbp-5Ch]

  Type[0] = 0;
  TokenHandle = 0;
  memset_0(RpcCallAttributes, 0, 0x70u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f253abc5dcc438f866476f70819b5188_Traceguids);
  if ( I_RpcBindingInqTransportType(0, Type) )
    return 5;
  if ( Type[0] != 4 )
    return 5;
  RpcCallAttributes[0] = 2;
  if ( RpcServerInqCallAttributesW(0, RpcCallAttributes) )
    return 5;
  v5 = v12 & 6;
  if ( (_BYTE)v5 != 6 )
    return 5;
  if ( !v13 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v2, v3, v4);
    return 5;
  }
  if ( RpcImpersonateClient(0) )
    return 5;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v8 = RpcRevertToSelf();
  }
  else
  {
    v8 = 5;
    RpcRevertToSelf();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f253abc5dcc438f866476f70819b5188_Traceguids, v8);
    return 5;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_f253abc5dcc438f866476f70819b5188_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18005ca20  mov     [rsp+arg_0], rbx
0x18005ca25  push    r14
0x18005ca27  sub     rsp, 0C0h
0x18005ca2e  mov     rax, cs:__security_cookie
0x18005ca35  xor     rax, rsp
0x18005ca38  mov     [rsp+0C8h+var_18], rax
0x18005ca40  xor     edx, edx; Val
0x18005ca42  mov     [rsp+0C8h+Type], 0
0x18005ca4a  lea     rcx, [rsp+0C8h+RpcCallAttributes]; void *
0x18005ca4f  mov     [rsp+0C8h+TokenHandle], 0
0x18005ca58  lea     r8d, [rdx+70h]; Size
0x18005ca5c  call    memset_0
0x18005ca61  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ca68  lea     r14, WPP_GLOBAL_Control
0x18005ca6f  cmp     rcx, r14
0x18005ca72  jz      short loc_18005CA8F
0x18005ca74  test    byte ptr [rcx+1Ch], 8
0x18005ca78  jz      short loc_18005CA8F
0x18005ca7a  mov     rcx, [rcx+10h]
0x18005ca7e  lea     r8, WPP_f253abc5dcc438f866476f70819b5188_Traceguids
0x18005ca85  mov     edx, 0Ah
0x18005ca8a  call    WPP_SF_
0x18005ca8f  lea     rdx, [rsp+0C8h+Type]; Type
0x18005ca94  xor     ecx, ecx; Binding
0x18005ca96  call    cs:__imp_I_RpcBindingInqTransportType
0x18005ca9c  test    eax, eax
0x18005ca9e  jnz     short loc_18005CAD7
0x18005caa0  cmp     [rsp+0C8h+Type], 4
0x18005caa5  jnz     short loc_18005CAD7
0x18005caa7  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x18005caac  mov     [rsp+0C8h+RpcCallAttributes], 2
0x18005cab4  xor     ecx, ecx; ClientBinding
0x18005cab6  call    cs:__imp_RpcServerInqCallAttributesW
0x18005cabc  test    eax, eax
0x18005cabe  jnz     short loc_18005CAD7
0x18005cac0  mov     ecx, [rsp+0C8h+var_60]
0x18005cac4  and     ecx, 6
0x18005cac7  cmp     cl, 6
0x18005caca  jnz     short loc_18005CAD7
0x18005cacc  cmp     [rsp+0C8h+var_5C], eax
0x18005cad0  jnz     short loc_18005CAFE
0x18005cad2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005cad7  mov     eax, 5
0x18005cadc  mov     rcx, [rsp+0C8h+var_18]
0x18005cae4  xor     rcx, rsp; StackCookie
0x18005cae7  call    __security_check_cookie
0x18005caec  mov     rbx, [rsp+0C8h+arg_0]
0x18005caf4  add     rsp, 0C0h
0x18005cafb  pop     r14
0x18005cafd  retn
0x18005cafe  xor     ecx, ecx; BindingHandle
0x18005cb00  call    cs:__imp_RpcImpersonateClient
0x18005cb06  test    eax, eax
0x18005cb08  jnz     short loc_18005CAD7
0x18005cb0a  call    cs:__imp_GetCurrentThread
0x18005cb10  mov     edx, 8; DesiredAccess
0x18005cb15  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x18005cb1a  mov     rcx, rax; ThreadHandle
0x18005cb1d  lea     r8d, [rdx-7]; OpenAsSelf
0x18005cb21  call    cs:__imp_OpenThreadToken
0x18005cb27  test    eax, eax
0x18005cb29  jnz     short loc_18005CB36
0x18005cb2b  lea     ebx, [rax+5]
0x18005cb2e  call    cs:__imp_RpcRevertToSelf
0x18005cb34  jmp     short loc_18005CB3E
0x18005cb36  call    cs:__imp_RpcRevertToSelf
0x18005cb3c  mov     ebx, eax
0x18005cb3e  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x18005cb43  test    rcx, rcx
0x18005cb46  jz      short loc_18005CB4E
0x18005cb48  call    cs:__imp_CloseHandle
0x18005cb4e  test    ebx, ebx
0x18005cb50  jz      short loc_18005CB89
0x18005cb52  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cb59  cmp     rcx, r14
0x18005cb5c  jz      loc_18005CAD7
0x18005cb62  test    byte ptr [rcx+1Ch], 1
0x18005cb66  jz      loc_18005CAD7
0x18005cb6c  mov     rcx, [rcx+10h]
0x18005cb70  lea     r8, WPP_f253abc5dcc438f866476f70819b5188_Traceguids
0x18005cb77  mov     edx, 0Bh
0x18005cb7c  mov     r9d, ebx
0x18005cb7f  call    WPP_SF_d
0x18005cb84  jmp     loc_18005CAD7
0x18005cb89  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cb90  cmp     rcx, r14
0x18005cb93  jz      short loc_18005CBB0
0x18005cb95  test    byte ptr [rcx+1Ch], 8
0x18005cb99  jz      short loc_18005CBB0
0x18005cb9b  mov     rcx, [rcx+10h]
0x18005cb9f  lea     r8, WPP_f253abc5dcc438f866476f70819b5188_Traceguids
0x18005cba6  mov     edx, 0Ch
0x18005cbab  call    WPP_SF_
0x18005cbb0  xor     eax, eax
0x18005cbb2  jmp     loc_18005CADC
```
