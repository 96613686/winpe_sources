# SspipApplyControlToken

- ea: `0x18000ad04`
- end: `0x18000ae0f`
- name: `SspipApplyControlToken`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800218c0`

## callees

- `0x180004074`
- `0x18000ad04`
- `0x1800108a0`
- `0x180010980`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x18000ad71`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000ad71`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000ad51`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000ad51`
- `ntoskrnl!PsGetProcessId` at `0x18000ad60`
- `ntoskrnl!PsGetProcessId` at `0x18000ad60`
- `msrpc!NdrClientCall3` at `0x18000addd`
- `msrpc!NdrClientCall3` at `0x18000addd`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall SspipApplyControlToken(_QWORD *a1, __int64 a2)
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
    if ( *(_QWORD *)&WPP_MAIN_CB.DeviceType )
    {
      return (CLIENT_CALL_RETURN)(*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD *, __int64))(*(_QWORD *)&WPP_MAIN_CB.DeviceType
                                                                                                  + 40LL))(
                                   0,
                                   &v10,
                                   v11,
                                   a2);
    }
    else
    {
      v9[1] = 0;
      return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo, 0xBu, 0, v9[0], &v10, v11, a2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ad04  mov     r11, rsp
0x18000ad07  push    rbx
0x18000ad08  sub     rsp, 80h
0x18000ad0f  mov     rax, cs:__security_cookie
0x18000ad16  xor     rax, rsp
0x18000ad19  mov     [rsp+88h+var_10], rax
0x18000ad1e  mov     rbx, rdx
0x18000ad21  mov     qword ptr [r11-40h], 0
0x18000ad29  xorps   xmm0, xmm0
0x18000ad2c  movups  [rsp+88h+var_30], xmm0
0x18000ad31  mov     rax, [rcx]
0x18000ad34  mov     [r11-20h], rax
0x18000ad38  mov     rax, [rcx+8]
0x18000ad3c  mov     [r11-18h], rax
0x18000ad40  lea     rcx, [r11-40h]
0x18000ad44  call    IsOkayToExecRpc
0x18000ad49  test    eax, eax
0x18000ad4b  js      loc_18000ADF8
0x18000ad51  call    cs:__imp_PsGetCurrentProcess
0x18000ad58  nop     dword ptr [rax+rax+00h]
0x18000ad5d  mov     rcx, rax; Process
0x18000ad60  call    cs:__imp_PsGetProcessId
0x18000ad67  nop     dword ptr [rax+rax+00h]
0x18000ad6c  mov     qword ptr [rsp+88h+var_30], rax
0x18000ad71  call    cs:__imp_PsGetCurrentThreadId
0x18000ad78  nop     dword ptr [rax+rax+00h]
0x18000ad7d  mov     qword ptr [rsp+88h+var_30+8], rax
0x18000ad82  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceType
0x18000ad89  test    rax, rax
0x18000ad8c  jz      short loc_18000ADA8
0x18000ad8e  mov     rax, [rax+28h]
0x18000ad92  mov     r9, rbx
0x18000ad95  lea     r8, [rsp+88h+var_20]
0x18000ad9a  lea     rdx, [rsp+88h+var_30]
0x18000ad9f  xor     ecx, ecx
0x18000ada1  call    _guard_dispatch_icall
0x18000ada6  jmp     short loc_18000ADF8
0x18000ada8  mov     [rsp+88h+var_38], 0
0x18000adb1  mov     [rsp+88h+var_58], rbx
0x18000adb6  lea     rax, [rsp+88h+var_20]
0x18000adbb  mov     [rsp+88h+var_60], rax
0x18000adc0  lea     rax, [rsp+88h+var_30]
0x18000adc5  mov     [rsp+88h+var_68], rax
0x18000adca  mov     r9, [rsp+88h+var_40]
0x18000adcf  xor     r8d, r8d; pReturnValue
0x18000add2  lea     edx, [r8+0Bh]; nProcNum
0x18000add6  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000addd  call    cs:__imp_NdrClientCall3
0x18000ade4  nop     dword ptr [rax+rax+00h]
0x18000ade9  mov     [rsp+88h+var_38], rax
0x18000adee  mov     [rsp+88h+var_48], eax
0x18000adf2  jmp     short loc_18000ADF8
0x18000adf4  mov     [rsp+88h+var_48], eax
0x18000adf8  mov     rcx, [rsp+88h+var_10]
0x18000adfd  xor     rcx, rsp; StackCookie
0x18000ae00  call    __security_check_cookie
0x18000ae05  add     rsp, 80h
0x18000ae0c  pop     rbx
0x18000ae0d  retn
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
