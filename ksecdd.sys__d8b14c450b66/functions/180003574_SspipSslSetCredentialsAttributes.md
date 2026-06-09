# SspipSslSetCredentialsAttributes

- ea: `0x180003574`
- end: `0x180003659`
- name: `SspipSslSetCredentialsAttributes`
- size: `229`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180021980`

## callees

- `0x180003574`
- `0x180004074`
- `0x180010840`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1800035e1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1800035e1`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800035c1`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800035c1`
- `ntoskrnl!PsGetProcessId` at `0x1800035d0`
- `ntoskrnl!PsGetProcessId` at `0x1800035d0`
- `msrpc!NdrClientCall3` at `0x180003627`
- `msrpc!NdrClientCall3` at `0x180003627`
- `msrpc!I_RpcExceptionFilter` at `0x1800112d1`
- `msrpc!I_RpcExceptionFilter` at `0x1800112d1`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall SspipSslSetCredentialsAttributes(_QWORD *a1, __int64 a2)
{
  CLIENT_CALL_RETURN result; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  struct _KPROCESS *CurrentProcess; // rax
  _QWORD v9[2]; // [rsp+48h] [rbp-40h] BYREF
  __int128 v10; // [rsp+58h] [rbp-30h] BYREF
  _QWORD v11[2]; // [rsp+68h] [rbp-20h] BYREF

  v9[0] = 0;
  v10 = 0;
  v11[0] = *a1;
  v11[1] = a1[1];
  result.Simple = IsOkayToExecRpc(v9);
  if ( SLODWORD(result.Simple) >= 0 )
  {
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(v5, v4, v6, v7);
    *(_QWORD *)&v10 = PsGetProcessId(CurrentProcess);
    *((_QWORD *)&v10 + 1) = PsGetCurrentThreadId();
    v9[1] = 0;
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo, 0xAu, 0, v9[0], &v10, v11, a2);
  }
  return result;
}

```

## disassembly

```asm
0x180003574  mov     r11, rsp
0x180003577  push    rbx
0x180003578  sub     rsp, 80h
0x18000357f  mov     rax, cs:__security_cookie
0x180003586  xor     rax, rsp
0x180003589  mov     [rsp+88h+var_10], rax
0x18000358e  mov     rbx, rdx
0x180003591  mov     qword ptr [r11-40h], 0
0x180003599  xorps   xmm0, xmm0
0x18000359c  movups  [rsp+88h+var_30], xmm0
0x1800035a1  mov     rax, [rcx]
0x1800035a4  mov     [r11-20h], rax
0x1800035a8  mov     rax, [rcx+8]
0x1800035ac  mov     [r11-18h], rax
0x1800035b0  lea     rcx, [r11-40h]
0x1800035b4  call    IsOkayToExecRpc
0x1800035b9  test    eax, eax
0x1800035bb  js      loc_180003642
0x1800035c1  call    cs:__imp_PsGetCurrentProcess
0x1800035c8  nop     dword ptr [rax+rax+00h]
0x1800035cd  mov     rcx, rax; Process
0x1800035d0  call    cs:__imp_PsGetProcessId
0x1800035d7  nop     dword ptr [rax+rax+00h]
0x1800035dc  mov     qword ptr [rsp+88h+var_30], rax
0x1800035e1  call    cs:__imp_PsGetCurrentThreadId
0x1800035e8  nop     dword ptr [rax+rax+00h]
0x1800035ed  mov     qword ptr [rsp+88h+var_30+8], rax
0x1800035f2  mov     [rsp+88h+var_38], 0
0x1800035fb  mov     [rsp+88h+var_58], rbx
0x180003600  lea     rax, [rsp+88h+var_20]
0x180003605  mov     [rsp+88h+var_60], rax
0x18000360a  lea     rax, [rsp+88h+var_30]
0x18000360f  mov     [rsp+88h+var_68], rax
0x180003614  mov     r9, [rsp+88h+var_40]
0x180003619  xor     r8d, r8d; pReturnValue
0x18000361c  lea     edx, [r8+0Ah]; nProcNum
0x180003620  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180003627  call    cs:__imp_NdrClientCall3
0x18000362e  nop     dword ptr [rax+rax+00h]
0x180003633  mov     [rsp+88h+var_38], rax
0x180003638  mov     [rsp+88h+var_48], eax
0x18000363c  jmp     short loc_180003642
0x18000363e  mov     [rsp+88h+var_48], eax
0x180003642  mov     rcx, [rsp+88h+var_10]
0x180003647  xor     rcx, rsp; StackCookie
0x18000364a  call    __security_check_cookie
0x18000364f  add     rsp, 80h
0x180003656  pop     rbx
0x180003657  retn
0x1800112c3  push    rbp
0x1800112c5  sub     rsp, 40h
0x1800112c9  mov     rbp, rdx
0x1800112cc  mov     rcx, [rcx]
0x1800112cf  mov     ecx, [rcx]; ExceptionCode
0x1800112d1  call    cs:__imp_I_RpcExceptionFilter
0x1800112d8  nop     dword ptr [rax+rax+00h]
0x1800112dd  nop
0x1800112de  add     rsp, 40h
0x1800112e2  pop     rbp
0x1800112e3  retn
```
