# FwGetThreadToken

- ea: `0x18009a59c`
- end: `0x18009a6e3`
- name: `FwGetThreadToken`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800a1918`

## callees

- `0x18000a710`
- `0x1800729c0`
- `0x18009a59c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009a62e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009a62e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009a648`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009a648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a658`
- `RPCRT4!RpcImpersonateClient` at `0x18009a5cd`
- `RPCRT4!RpcImpersonateClient` at `0x18009a5cd`
- `RPCRT4!RpcRevertToSelf` at `0x18009a6b7`
- `RPCRT4!RpcRevertToSelf` at `0x18009a6b7`
- `fwbase!FwCloseHandle` at `0x18009a6a7`
- `fwbase!FwCloseHandle` at `0x18009a6a7`

## pseudocode

```c
__int64 __fastcall FwGetThreadToken(void *a1, void **a2)
{
  RPC_STATUS v3; // eax
  unsigned int v4; // ebx
  int v5; // esi
  __int64 v6; // rcx
  __int64 v7; // rdx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  TokenHandle = 0;
  *a2 = 0;
  v3 = RpcImpersonateClient(a1);
  v4 = v3;
  if ( v3 )
  {
    v5 = 0;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 32;
LABEL_7:
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v4);
    }
  }
  else
  {
    v5 = 1;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xAu, 1, &TokenHandle) )
    {
      v4 = 0;
      *a2 = TokenHandle;
      TokenHandle = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 33;
        goto LABEL_7;
      }
    }
  }
  FwCloseHandle(TokenHandle);
  if ( v5 )
    RpcRevertToSelf();
  return v4;
}

```

## disassembly

```asm
0x18009a59c  mov     [rsp+arg_10], rbx
0x18009a5a1  mov     [rsp+arg_18], rsi
0x18009a5a6  push    rdi
0x18009a5a7  sub     rsp, 30h
0x18009a5ab  mov     rax, cs:__security_cookie
0x18009a5b2  xor     rax, rsp
0x18009a5b5  mov     [rsp+38h+var_10], rax
0x18009a5ba  mov     rdi, rdx
0x18009a5bd  mov     [rsp+38h+TokenHandle], 0
0x18009a5c6  mov     qword ptr [rdx], 0
0x18009a5cd  call    cs:__imp_RpcImpersonateClient
0x18009a5d4  nop     dword ptr [rax+rax+00h]
0x18009a5d9  mov     ebx, eax
0x18009a5db  test    eax, eax
0x18009a5dd  jz      short loc_18009A629
0x18009a5df  xor     esi, esi
0x18009a5e1  test    eax, eax
0x18009a5e3  jle     short loc_18009A5EE
0x18009a5e5  movzx   ebx, ax
0x18009a5e8  or      ebx, 80070000h
0x18009a5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a5f5  lea     rax, WPP_GLOBAL_Control
0x18009a5fc  cmp     rcx, rax
0x18009a5ff  jz      loc_18009A6A2
0x18009a605  test    byte ptr [rcx+1Ch], 1
0x18009a609  jz      loc_18009A6A2
0x18009a60f  mov     edx, 20h ; ' '
0x18009a614  mov     rcx, [rcx+10h]
0x18009a618  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009a61f  mov     r9d, ebx
0x18009a622  call    WPP_SF_d
0x18009a627  jmp     short loc_18009A6A2
0x18009a629  mov     esi, 1
0x18009a62e  call    cs:__imp_GetCurrentThread
0x18009a635  nop     dword ptr [rax+rax+00h]
0x18009a63a  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18009a63f  mov     r8d, esi; OpenAsSelf
0x18009a642  mov     rcx, rax; ThreadHandle
0x18009a645  lea     edx, [rsi+9]; DesiredAccess
0x18009a648  call    cs:__imp_OpenThreadToken
0x18009a64f  nop     dword ptr [rax+rax+00h]
0x18009a654  test    eax, eax
0x18009a656  jnz     short loc_18009A693
0x18009a658  call    cs:__imp_GetLastError
0x18009a65f  nop     dword ptr [rax+rax+00h]
0x18009a664  mov     ebx, eax
0x18009a666  test    eax, eax
0x18009a668  jle     short loc_18009A673
0x18009a66a  movzx   ebx, ax
0x18009a66d  or      ebx, 80070000h
0x18009a673  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a67a  lea     rax, WPP_GLOBAL_Control
0x18009a681  cmp     rcx, rax
0x18009a684  jz      short loc_18009A6A2
0x18009a686  test    [rcx+1Ch], sil
0x18009a68a  jz      short loc_18009A6A2
0x18009a68c  mov     edx, 21h ; '!'
0x18009a691  jmp     short loc_18009A614
0x18009a693  mov     rcx, [rsp+38h+TokenHandle]
0x18009a698  xor     ebx, ebx
0x18009a69a  mov     [rdi], rcx
0x18009a69d  mov     [rsp+38h+TokenHandle], rbx
0x18009a6a2  mov     rcx, [rsp+38h+TokenHandle]
0x18009a6a7  call    cs:__imp_FwCloseHandle
0x18009a6ae  nop     dword ptr [rax+rax+00h]
0x18009a6b3  test    esi, esi
0x18009a6b5  jz      short loc_18009A6C3
0x18009a6b7  call    cs:__imp_RpcRevertToSelf
0x18009a6be  nop     dword ptr [rax+rax+00h]
0x18009a6c3  mov     eax, ebx
0x18009a6c5  mov     rcx, [rsp+38h+var_10]
0x18009a6ca  xor     rcx, rsp; StackCookie
0x18009a6cd  call    __security_check_cookie
0x18009a6d2  mov     rbx, [rsp+38h+arg_10]
0x18009a6d7  mov     rsi, [rsp+38h+arg_18]
0x18009a6dc  add     rsp, 30h
0x18009a6e0  pop     rdi
0x18009a6e1  retn
```
