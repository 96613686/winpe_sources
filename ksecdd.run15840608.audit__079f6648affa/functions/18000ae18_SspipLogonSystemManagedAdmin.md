# SspipLogonSystemManagedAdmin

- ea: `0x18000ae18`
- end: `0x18000af1d`
- name: `SspipLogonSystemManagedAdmin`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180021970`

## callees

- `0x180004074`
- `0x18000ae18`
- `0x1800108a0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x18000ae8a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000ae8a`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000ae6a`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000ae6a`
- `ntoskrnl!PsGetProcessId` at `0x18000ae79`
- `ntoskrnl!PsGetProcessId` at `0x18000ae79`
- `msrpc!NdrClientCall3` at `0x18000aed0`
- `msrpc!NdrClientCall3` at `0x18000aed0`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall SspipLogonSystemManagedAdmin(__int64 a1, _QWORD *a2)
{
  CLIENT_CALL_RETURN result; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v10; // [rsp+48h] [rbp-40h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h] BYREF
  CLIENT_CALL_RETURN v12; // [rsp+58h] [rbp-30h]
  _QWORD *v13; // [rsp+60h] [rbp-28h]
  __int128 v14; // [rsp+68h] [rbp-20h] BYREF

  v13 = a2;
  v10 = 0;
  v14 = 0;
  v11 = 0;
  result.Simple = IsOkayToExecRpc(&v10);
  if ( SLODWORD(result.Simple) >= 0 )
  {
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(v6, v5, v7, v8);
    *(_QWORD *)&v14 = PsGetProcessId(CurrentProcess);
    *((_QWORD *)&v14 + 1) = PsGetCurrentThreadId();
    v12.Simple = 0;
    result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo, 0xDu, 0, v10, &v14, a1, &v11).Pointer;
    v12.Pointer = result.Pointer;
    if ( SLODWORD(result.Simple) >= 0 )
    {
      *a2 = v11;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ae18  mov     r11, rsp
0x18000ae1b  mov     [r11+18h], rbx
0x18000ae1f  push    rdi
0x18000ae20  sub     rsp, 80h
0x18000ae27  mov     rax, cs:__security_cookie
0x18000ae2e  xor     rax, rsp
0x18000ae31  mov     [rsp+88h+var_10], rax
0x18000ae36  mov     rdi, rdx
0x18000ae39  mov     rbx, rcx
0x18000ae3c  mov     [rsp+88h+var_28], rdx
0x18000ae41  mov     qword ptr [r11-40h], 0
0x18000ae49  xorps   xmm0, xmm0
0x18000ae4c  movups  [rsp+88h+var_20], xmm0
0x18000ae51  mov     qword ptr [r11-38h], 0
0x18000ae59  lea     rcx, [r11-40h]
0x18000ae5d  call    IsOkayToExecRpc
0x18000ae62  test    eax, eax
0x18000ae64  js      loc_18000AEFE
0x18000ae6a  call    cs:__imp_PsGetCurrentProcess
0x18000ae71  nop     dword ptr [rax+rax+00h]
0x18000ae76  mov     rcx, rax; Process
0x18000ae79  call    cs:__imp_PsGetProcessId
0x18000ae80  nop     dword ptr [rax+rax+00h]
0x18000ae85  mov     qword ptr [rsp+88h+var_20], rax
0x18000ae8a  call    cs:__imp_PsGetCurrentThreadId
0x18000ae91  nop     dword ptr [rax+rax+00h]
0x18000ae96  mov     qword ptr [rsp+88h+var_20+8], rax
0x18000ae9b  mov     [rsp+88h+var_30], 0
0x18000aea4  lea     rax, [rsp+88h+var_38]
0x18000aea9  mov     [rsp+88h+var_58], rax
0x18000aeae  mov     [rsp+88h+var_60], rbx
0x18000aeb3  lea     rax, [rsp+88h+var_20]
0x18000aeb8  mov     [rsp+88h+var_68], rax
0x18000aebd  mov     r9, [rsp+88h+var_40]
0x18000aec2  xor     r8d, r8d; pReturnValue
0x18000aec5  lea     edx, [r8+0Dh]; nProcNum
0x18000aec9  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000aed0  call    cs:__imp_NdrClientCall3
0x18000aed7  nop     dword ptr [rax+rax+00h]
0x18000aedc  mov     [rsp+88h+var_30], rax
0x18000aee1  mov     [rsp+88h+var_48], eax
0x18000aee5  jmp     short loc_18000AEF0
0x18000aee7  mov     [rsp+88h+var_48], eax
0x18000aeeb  mov     rdi, [rsp+88h+var_28]
0x18000aef0  test    eax, eax
0x18000aef2  js      short loc_18000AEFE
0x18000aef4  mov     rax, [rsp+88h+var_38]
0x18000aef9  mov     [rdi], rax
0x18000aefc  xor     eax, eax
0x18000aefe  mov     rcx, [rsp+88h+var_10]
0x18000af03  xor     rcx, rsp; StackCookie
0x18000af06  call    __security_check_cookie
0x18000af0b  mov     rbx, [rsp+88h+arg_10]
0x18000af13  add     rsp, 80h
0x18000af1a  pop     rdi
0x18000af1b  retn
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
