# SspipSslSetCredentialsAttributesEx

- ea: `0x18000b184`
- end: `0x18000b291`
- name: `SspipSslSetCredentialsAttributesEx`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800219d0`

## callees

- `0x180004074`
- `0x18000b184`
- `0x1800108a0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x18000b20d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000b20d`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000b1ed`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000b1ed`
- `ntoskrnl!PsGetProcessId` at `0x18000b1fc`
- `ntoskrnl!PsGetProcessId` at `0x18000b1fc`
- `msrpc!NdrClientCall3` at `0x18000b257`
- `msrpc!NdrClientCall3` at `0x18000b257`
- `msrpc!I_RpcExceptionFilter` at `0x1800114bf`
- `msrpc!I_RpcExceptionFilter` at `0x1800114bf`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall SspipSslSetCredentialsAttributesEx(_QWORD *a1, int a2, __int64 a3)
{
  CLIENT_CALL_RETURN result; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  struct _KPROCESS *CurrentProcess; // rax
  int v11; // [rsp+30h] [rbp-58h]
  _QWORD v12[2]; // [rsp+48h] [rbp-40h] BYREF
  __int128 v13; // [rsp+58h] [rbp-30h] BYREF
  _QWORD v14[2]; // [rsp+68h] [rbp-20h] BYREF

  v12[0] = 0;
  v13 = 0;
  if ( a2 == 96 || a2 == 115 )
  {
    v14[0] = *a1;
    v14[1] = a1[1];
    result.Simple = IsOkayToExecRpc(v12);
    if ( SLODWORD(result.Simple) >= 0 )
    {
      CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(v7, v6, v8, v9);
      *(_QWORD *)&v13 = PsGetProcessId(CurrentProcess);
      *((_QWORD *)&v13 + 1) = PsGetCurrentThreadId();
      v12[1] = 0;
      v11 = a2;
      return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo, 0x11u, 0, v12[0], &v13, v14, v11, a3);
    }
  }
  else
  {
    return (CLIENT_CALL_RETURN)3221225485LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000b184  mov     [rsp+arg_18], rbx
0x18000b189  push    rdi
0x18000b18a  sub     rsp, 80h
0x18000b191  mov     rax, cs:__security_cookie
0x18000b198  xor     rax, rsp
0x18000b19b  mov     [rsp+88h+var_10], rax
0x18000b1a0  mov     rdi, r8
0x18000b1a3  mov     ebx, edx
0x18000b1a5  mov     [rsp+88h+var_40], 0
0x18000b1ae  xorps   xmm0, xmm0
0x18000b1b1  movups  [rsp+88h+var_30], xmm0
0x18000b1b6  cmp     edx, 60h ; '`'
0x18000b1b9  jz      short loc_18000B1CA
0x18000b1bb  cmp     edx, 73h ; 's'
0x18000b1be  jz      short loc_18000B1CA
0x18000b1c0  mov     eax, 0C000000Dh
0x18000b1c5  jmp     loc_18000B272
0x18000b1ca  mov     rax, [rcx]
0x18000b1cd  mov     [rsp+88h+var_20], rax
0x18000b1d2  mov     rax, [rcx+8]
0x18000b1d6  mov     [rsp+88h+var_18], rax
0x18000b1db  lea     rcx, [rsp+88h+var_40]
0x18000b1e0  call    IsOkayToExecRpc
0x18000b1e5  test    eax, eax
0x18000b1e7  js      loc_18000B272
0x18000b1ed  call    cs:__imp_PsGetCurrentProcess
0x18000b1f4  nop     dword ptr [rax+rax+00h]
0x18000b1f9  mov     rcx, rax; Process
0x18000b1fc  call    cs:__imp_PsGetProcessId
0x18000b203  nop     dword ptr [rax+rax+00h]
0x18000b208  mov     qword ptr [rsp+88h+var_30], rax
0x18000b20d  call    cs:__imp_PsGetCurrentThreadId
0x18000b214  nop     dword ptr [rax+rax+00h]
0x18000b219  mov     qword ptr [rsp+88h+var_30+8], rax
0x18000b21e  mov     [rsp+88h+var_38], 0
0x18000b227  mov     [rsp+88h+var_50], rdi
0x18000b22c  mov     [rsp+88h+var_58], ebx
0x18000b230  lea     rax, [rsp+88h+var_20]
0x18000b235  mov     [rsp+88h+var_60], rax
0x18000b23a  lea     rax, [rsp+88h+var_30]
0x18000b23f  mov     [rsp+88h+var_68], rax
0x18000b244  mov     r9, [rsp+88h+var_40]
0x18000b249  xor     r8d, r8d; pReturnValue
0x18000b24c  lea     edx, [r8+11h]; nProcNum
0x18000b250  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000b257  call    cs:__imp_NdrClientCall3
0x18000b25e  nop     dword ptr [rax+rax+00h]
0x18000b263  mov     [rsp+88h+var_38], rax
0x18000b268  mov     [rsp+88h+var_48], eax
0x18000b26c  jmp     short loc_18000B272
0x18000b26e  mov     [rsp+88h+var_48], eax
0x18000b272  mov     rcx, [rsp+88h+var_10]
0x18000b277  xor     rcx, rsp; StackCookie
0x18000b27a  call    __security_check_cookie
0x18000b27f  mov     rbx, [rsp+88h+arg_18]
0x18000b287  add     rsp, 80h
0x18000b28e  pop     rdi
0x18000b28f  retn
0x1800114b1  push    rbp
0x1800114b3  sub     rsp, 40h
0x1800114b7  mov     rbp, rdx
0x1800114ba  mov     rcx, [rcx]
0x1800114bd  mov     ecx, [rcx]; ExceptionCode
0x1800114bf  call    cs:__imp_I_RpcExceptionFilter
0x1800114c6  nop     dword ptr [rax+rax+00h]
0x1800114cb  nop
0x1800114cc  add     rsp, 40h
0x1800114d0  pop     rbp
0x1800114d1  retn
```
