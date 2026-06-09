# NcaRpcAPIsGetAccessTokenFromClientBinding

- ea: `0x18001bec4`
- end: `0x18001c035`
- name: `NcaRpcAPIsGetAccessTokenFromClientBinding`
- size: `369`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001c8e0`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x18001bec4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf9b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001bf8b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001bf8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bf6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bf6e`
- `RPCRT4!RpcImpersonateClient` at `0x18001bf1a`
- `RPCRT4!RpcImpersonateClient` at `0x18001bf1a`
- `RPCRT4!RpcRevertToSelf` at `0x18001bfec`
- `RPCRT4!RpcRevertToSelf` at `0x18001bfec`

## pseudocode

```c
__int64 __fastcall NcaRpcAPIsGetAccessTokenFromClientBinding(RPC_BINDING_HANDLE BindingHandle, __int64 a2, void **a3)
{
  RPC_STATUS v5; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids);
  *a3 = 0;
  v5 = RpcImpersonateClient(BindingHandle);
  v6 = v5;
  if ( !v5 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v6 = 0;
      *a3 = TokenHandle;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids, v6);
    }
    RpcRevertToSelf();
    goto LABEL_18;
  }
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_19:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
        WPP_SF_d(v7[2], 37, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids, v6);
      return v6;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids, v6);
LABEL_18:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_19;
  }
  return v6;
}

```

## disassembly

```asm
0x18001bec4  mov     [rsp+arg_0], rbx
0x18001bec9  mov     [rsp+arg_8], rsi
0x18001bece  push    rdi
0x18001becf  sub     rsp, 20h
0x18001bed3  mov     rdi, r8
0x18001bed6  mov     [rsp+28h+TokenHandle], 0
0x18001bedf  mov     rbx, rcx
0x18001bee2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bee9  lea     rsi, WPP_GLOBAL_Control
0x18001bef0  cmp     rcx, rsi
0x18001bef3  jz      short loc_18001BF10
0x18001bef5  test    byte ptr [rcx+1Ch], 8
0x18001bef9  jz      short loc_18001BF10
0x18001befb  mov     rcx, [rcx+10h]
0x18001beff  lea     r8, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids
0x18001bf06  mov     edx, 22h ; '"'
0x18001bf0b  call    WPP_SF_
0x18001bf10  mov     rcx, rbx; BindingHandle
0x18001bf13  mov     qword ptr [rdi], 0
0x18001bf1a  call    cs:__imp_RpcImpersonateClient
0x18001bf21  nop     dword ptr [rax+rax+00h]
0x18001bf26  mov     ebx, eax
0x18001bf28  test    eax, eax
0x18001bf2a  jz      short loc_18001BF6E
0x18001bf2c  jle     short loc_18001BF37
0x18001bf2e  movzx   ebx, ax
0x18001bf31  or      ebx, 80070000h
0x18001bf37  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf3e  cmp     rcx, rsi
0x18001bf41  jz      loc_18001C022
0x18001bf47  test    byte ptr [rcx+1Ch], 1
0x18001bf4b  jz      loc_18001BFFF
0x18001bf51  mov     rcx, [rcx+10h]
0x18001bf55  lea     r8, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids
0x18001bf5c  mov     edx, 23h ; '#'
0x18001bf61  mov     r9d, ebx
0x18001bf64  call    WPP_SF_d
0x18001bf69  jmp     loc_18001BFF8
0x18001bf6e  call    cs:__imp_GetCurrentThread
0x18001bf75  nop     dword ptr [rax+rax+00h]
0x18001bf7a  mov     edx, 8; DesiredAccess
0x18001bf7f  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001bf84  mov     rcx, rax; ThreadHandle
0x18001bf87  lea     r8d, [rdx-7]; OpenAsSelf
0x18001bf8b  call    cs:__imp_OpenThreadToken
0x18001bf92  nop     dword ptr [rax+rax+00h]
0x18001bf97  test    eax, eax
0x18001bf99  jnz     short loc_18001BFE2
0x18001bf9b  call    cs:__imp_GetLastError
0x18001bfa2  nop     dword ptr [rax+rax+00h]
0x18001bfa7  mov     ebx, eax
0x18001bfa9  test    eax, eax
0x18001bfab  jle     short loc_18001BFB6
0x18001bfad  movzx   ebx, ax
0x18001bfb0  or      ebx, 80070000h
0x18001bfb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfbd  cmp     rcx, rsi
0x18001bfc0  jz      short loc_18001BFEC
0x18001bfc2  test    byte ptr [rcx+1Ch], 1
0x18001bfc6  jz      short loc_18001BFEC
0x18001bfc8  mov     rcx, [rcx+10h]
0x18001bfcc  lea     r8, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids
0x18001bfd3  mov     edx, 24h ; '$'
0x18001bfd8  mov     r9d, ebx
0x18001bfdb  call    WPP_SF_d
0x18001bfe0  jmp     short loc_18001BFEC
0x18001bfe2  mov     rax, [rsp+28h+TokenHandle]
0x18001bfe7  xor     ebx, ebx
0x18001bfe9  mov     [rdi], rax
0x18001bfec  call    cs:__imp_RpcRevertToSelf
0x18001bff3  nop     dword ptr [rax+rax+00h]
0x18001bff8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfff  cmp     rcx, rsi
0x18001c002  jz      short loc_18001C022
0x18001c004  test    byte ptr [rcx+1Ch], 8
0x18001c008  jz      short loc_18001C022
0x18001c00a  mov     rcx, [rcx+10h]
0x18001c00e  lea     r8, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids
0x18001c015  mov     edx, 25h ; '%'
0x18001c01a  mov     r9d, ebx
0x18001c01d  call    WPP_SF_d
0x18001c022  mov     rsi, [rsp+28h+arg_8]
0x18001c027  mov     eax, ebx
0x18001c029  mov     rbx, [rsp+28h+arg_0]
0x18001c02e  add     rsp, 20h
0x18001c032  pop     rdi
0x18001c033  retn
```
