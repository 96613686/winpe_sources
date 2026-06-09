# SspipNegQueryContextAttributes

- ea: `0x18000af24`
- end: `0x18000b040`
- name: `SspipNegQueryContextAttributes`
- size: `284`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, int, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800294a0`

## callees

- `0x180004074`
- `0x18000af24`
- `0x180010840`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x18000afb5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000afb5`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000af95`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000af95`
- `ntoskrnl!PsGetProcessId` at `0x18000afa4`
- `ntoskrnl!PsGetProcessId` at `0x18000afa4`
- `msrpc!NdrClientCall3` at `0x18000b004`
- `msrpc!NdrClientCall3` at `0x18000b004`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall SspipNegQueryContextAttributes(_QWORD *a1, int a2, _QWORD *a3)
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
  if ( a2 )
  {
    if ( a2 != 12 )
      return (CLIENT_CALL_RETURN)3221225485LL;
    v10 = a3;
    *a3 = 0;
  }
  else
  {
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
    result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo, 9u, 0, v11, &v13, v14, a2, &v10).Pointer;
    v12.Pointer = result.Pointer;
  }
  return result;
}

```

## disassembly

```asm
0x18000af24  push    rbx
0x18000af26  sub     rsp, 90h
0x18000af2d  mov     rax, cs:__security_cookie
0x18000af34  xor     rax, rsp
0x18000af37  mov     [rsp+98h+var_18], rax
0x18000af3f  mov     ebx, edx
0x18000af41  mov     [rsp+98h+var_48], 0
0x18000af4a  xorps   xmm0, xmm0
0x18000af4d  movups  [rsp+98h+var_38], xmm0
0x18000af52  test    edx, edx
0x18000af54  jnz     short loc_18000AF5D
0x18000af56  mov     [rsp+98h+var_50], r8
0x18000af5b  jmp     short loc_18000AF72
0x18000af5d  cmp     ebx, 0Ch
0x18000af60  jnz     loc_18000B021
0x18000af66  mov     [rsp+98h+var_50], r8
0x18000af6b  mov     qword ptr [r8], 0
0x18000af72  mov     rax, [rcx]
0x18000af75  mov     [rsp+98h+var_28], rax
0x18000af7a  mov     rax, [rcx+8]
0x18000af7e  mov     [rsp+98h+var_20], rax
0x18000af83  lea     rcx, [rsp+98h+var_48]
0x18000af88  call    IsOkayToExecRpc
0x18000af8d  test    eax, eax
0x18000af8f  js      loc_18000B026
0x18000af95  call    cs:__imp_PsGetCurrentProcess
0x18000af9c  nop     dword ptr [rax+rax+00h]
0x18000afa1  mov     rcx, rax; Process
0x18000afa4  call    cs:__imp_PsGetProcessId
0x18000afab  nop     dword ptr [rax+rax+00h]
0x18000afb0  mov     qword ptr [rsp+98h+var_38], rax
0x18000afb5  call    cs:__imp_PsGetCurrentThreadId
0x18000afbc  nop     dword ptr [rax+rax+00h]
0x18000afc1  mov     qword ptr [rsp+98h+var_38+8], rax
0x18000afc6  mov     [rsp+98h+var_40], 0
0x18000afcf  lea     rax, [rsp+98h+var_50]
0x18000afd4  mov     [rsp+98h+var_60], rax
0x18000afd9  mov     [rsp+98h+var_68], ebx
0x18000afdd  lea     rax, [rsp+98h+var_28]
0x18000afe2  mov     [rsp+98h+var_70], rax
0x18000afe7  lea     rax, [rsp+98h+var_38]
0x18000afec  mov     [rsp+98h+var_78], rax
0x18000aff1  mov     r9, [rsp+98h+var_48]
0x18000aff6  xor     r8d, r8d; pReturnValue
0x18000aff9  lea     edx, [r8+9]; nProcNum
0x18000affd  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000b004  call    cs:__imp_NdrClientCall3
0x18000b00b  nop     dword ptr [rax+rax+00h]
0x18000b010  mov     [rsp+98h+var_40], rax
0x18000b015  mov     [rsp+98h+var_58], eax
0x18000b019  jmp     short loc_18000B01F
0x18000b01b  mov     [rsp+98h+var_58], eax
0x18000b01f  jmp     short loc_18000B026
0x18000b021  mov     eax, 0C000000Dh
0x18000b026  mov     rcx, [rsp+98h+var_18]
0x18000b02e  xor     rcx, rsp; StackCookie
0x18000b031  call    __security_check_cookie
0x18000b036  add     rsp, 90h
0x18000b03d  pop     rbx
0x18000b03e  retn
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
