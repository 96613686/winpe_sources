# SspipSslQueryCredentialsAttributes

- ea: `0x18000b048`
- end: `0x18000b17c`
- name: `SspipSslQueryCredentialsAttributes`
- size: `308`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, int, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180021960`

## callees

- `0x180004074`
- `0x18000b048`
- `0x180010840`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x18000b0f1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000b0f1`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000b0d1`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000b0d1`
- `ntoskrnl!PsGetProcessId` at `0x18000b0e0`
- `ntoskrnl!PsGetProcessId` at `0x18000b0e0`
- `msrpc!NdrClientCall3` at `0x18000b140`
- `msrpc!NdrClientCall3` at `0x18000b140`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall SspipSslQueryCredentialsAttributes(_QWORD *a1, int a2, _QWORD *a3)
{
  CLIENT_CALL_RETURN result; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  struct _KPROCESS *CurrentProcess; // rax
  _QWORD *v10; // [rsp+48h] [rbp-50h] BYREF
  __int64 v11; // [rsp+50h] [rbp-48h] BYREF
  CLIENT_CALL_RETURN v12; // [rsp+58h] [rbp-40h]
  __int128 v13; // [rsp+60h] [rbp-38h] BYREF
  _QWORD v14[2]; // [rsp+70h] [rbp-28h] BYREF

  v11 = 0;
  v13 = 0;
  if ( a2 == 1 )
  {
    v10 = a3;
    *a3 = 0;
  }
  else if ( a2 == 86 )
  {
    v10 = a3;
    a3[1] = 0;
  }
  else
  {
    if ( (unsigned int)(a2 - 87) > 1 )
      return (CLIENT_CALL_RETURN)3221225485LL;
    v10 = a3;
  }
  v14[0] = *a1;
  v14[1] = a1[1];
  result.Simple = IsOkayToExecRpc(&v11);
  if ( SLODWORD(result.Simple) >= 0 )
  {
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(v6, v5, v7, v8);
    *(_QWORD *)&v13 = PsGetProcessId(CurrentProcess);
    *((_QWORD *)&v13 + 1) = PsGetCurrentThreadId();
    v12.Simple = 0;
    result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo, 8u, 0, v11, &v13, v14, a2, &v10).Pointer;
    v12.Pointer = result.Pointer;
  }
  return result;
}

```

## disassembly

```asm
0x18000b048  push    rbx
0x18000b04a  sub     rsp, 90h
0x18000b051  mov     rax, cs:__security_cookie
0x18000b058  xor     rax, rsp
0x18000b05b  mov     [rsp+98h+var_18], rax
0x18000b063  mov     ebx, edx
0x18000b065  mov     [rsp+98h+var_48], 0
0x18000b06e  xorps   xmm0, xmm0
0x18000b071  movups  [rsp+98h+var_38], xmm0
0x18000b076  cmp     edx, 1
0x18000b079  jnz     short loc_18000B089
0x18000b07b  mov     [rsp+98h+var_50], r8
0x18000b080  mov     qword ptr [r8], 0
0x18000b087  jmp     short loc_18000B0AE
0x18000b089  cmp     ebx, 56h ; 'V'
0x18000b08c  jnz     short loc_18000B09D
0x18000b08e  mov     [rsp+98h+var_50], r8
0x18000b093  mov     qword ptr [r8+8], 0
0x18000b09b  jmp     short loc_18000B0AE
0x18000b09d  lea     eax, [rdx-57h]
0x18000b0a0  cmp     eax, 1
0x18000b0a3  ja      loc_18000B15D
0x18000b0a9  mov     [rsp+98h+var_50], r8
0x18000b0ae  mov     rax, [rcx]
0x18000b0b1  mov     [rsp+98h+var_28], rax
0x18000b0b6  mov     rax, [rcx+8]
0x18000b0ba  mov     [rsp+98h+var_20], rax
0x18000b0bf  lea     rcx, [rsp+98h+var_48]
0x18000b0c4  call    IsOkayToExecRpc
0x18000b0c9  test    eax, eax
0x18000b0cb  js      loc_18000B162
0x18000b0d1  call    cs:__imp_PsGetCurrentProcess
0x18000b0d8  nop     dword ptr [rax+rax+00h]
0x18000b0dd  mov     rcx, rax; Process
0x18000b0e0  call    cs:__imp_PsGetProcessId
0x18000b0e7  nop     dword ptr [rax+rax+00h]
0x18000b0ec  mov     qword ptr [rsp+98h+var_38], rax
0x18000b0f1  call    cs:__imp_PsGetCurrentThreadId
0x18000b0f8  nop     dword ptr [rax+rax+00h]
0x18000b0fd  mov     qword ptr [rsp+98h+var_38+8], rax
0x18000b102  mov     [rsp+98h+var_40], 0
0x18000b10b  lea     rax, [rsp+98h+var_50]
0x18000b110  mov     [rsp+98h+var_60], rax
0x18000b115  mov     [rsp+98h+var_68], ebx
0x18000b119  lea     rax, [rsp+98h+var_28]
0x18000b11e  mov     [rsp+98h+var_70], rax
0x18000b123  lea     rax, [rsp+98h+var_38]
0x18000b128  mov     [rsp+98h+var_78], rax
0x18000b12d  mov     r9, [rsp+98h+var_48]
0x18000b132  xor     r8d, r8d; pReturnValue
0x18000b135  lea     edx, [r8+8]; nProcNum
0x18000b139  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000b140  call    cs:__imp_NdrClientCall3
0x18000b147  nop     dword ptr [rax+rax+00h]
0x18000b14c  mov     [rsp+98h+var_40], rax
0x18000b151  mov     [rsp+98h+var_58], eax
0x18000b155  jmp     short loc_18000B15B
0x18000b157  mov     [rsp+98h+var_58], eax
0x18000b15b  jmp     short loc_18000B162
0x18000b15d  mov     eax, 0C000000Dh
0x18000b162  mov     rcx, [rsp+98h+var_18]
0x18000b16a  xor     rcx, rsp; StackCookie
0x18000b16d  call    __security_check_cookie
0x18000b172  add     rsp, 90h
0x18000b179  pop     rbx
0x18000b17a  retn
0x180011431  push    rbp
0x180011433  sub     rsp, 40h
0x180011437  mov     rbp, rdx
0x18001143a  mov     rcx, [rcx]
0x18001143d  mov     ecx, [rcx]; ExceptionCode
0x18001143f  call    cs:__imp_I_RpcExceptionFilter
0x180011446  nop     dword ptr [rax+rax+00h]
0x18001144b  nop
0x18001144c  add     rsp, 40h
0x180011450  pop     rbp
0x180011451  retn
```
