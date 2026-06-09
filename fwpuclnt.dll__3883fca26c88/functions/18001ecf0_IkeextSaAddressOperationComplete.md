# IkeextSaAddressOperationComplete

- ea: `0x18001ecf0`
- end: `0x18001ed93`
- name: `IkeextSaAddressOperationComplete`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800034e0`
- `0x18000438c`
- `0x18000bd54`
- `0x180012bd0`
- `0x18001ecf0`
- `0x18004b010`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18001ed1a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001ed1a`

## string_xrefs

- `0x18001ed2d`: `RpcAsyncCompleteCall`
- `0x18001ed47`: `FwppProxyIkeSAUpdatePreferredAddressAsync`

## pseudocode

```c
__int64 __fastcall IkeextSaAddressOperationComplete(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // ecx
  __int64 v6; // rdx
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  unsigned int Reply; // [rsp+28h] [rbp-20h] BYREF

  v8 = a1;
  Reply = 0;
  v2 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)a1, &Reply);
  if ( v2 )
  {
    v4 = WfpReportSysErrorAsRpcStatus(v3, "RpcAsyncCompleteCall", v2);
  }
  else
  {
    v5 = 0;
    if ( !Reply )
      goto LABEL_6;
    v4 = WfpReportSysErrorAsWinError(0, "FwppProxyIkeSAUpdatePreferredAddressAsync", Reply);
  }
  v5 = v4;
LABEL_6:
  v6 = (unsigned __int16)v5;
  if ( (v5 & 0x1FFF0000) != 0x70000 )
    v6 = v5;
  (*(void (__fastcall **)(_QWORD, __int64))(a1 + 120))(*(_QWORD *)(a1 + 112), v6);
  return WfpMemFree(&v8);
}

```

## disassembly

```asm
0x18001ecf0  push    rbx
0x18001ecf2  sub     rsp, 40h
0x18001ecf6  mov     rax, cs:__security_cookie
0x18001ecfd  xor     rax, rsp
0x18001ed00  mov     [rsp+48h+var_18], rax
0x18001ed05  lea     rdx, [rsp+48h+Reply]; Reply
0x18001ed0a  mov     [rsp+48h+var_28], rcx
0x18001ed0f  mov     rbx, rcx
0x18001ed12  mov     [rsp+48h+Reply], 0
0x18001ed1a  call    cs:__imp_RpcAsyncCompleteCall
0x18001ed21  nop     dword ptr [rax+rax+00h]
0x18001ed26  test    eax, eax
0x18001ed28  jz      short loc_18001ED3B
0x18001ed2a  mov     r8d, eax
0x18001ed2d  lea     rdx, aRpcasynccomple_0; "RpcAsyncCompleteCall"
0x18001ed34  call    WfpReportSysErrorAsRpcStatus
0x18001ed39  jmp     short loc_18001ED53
0x18001ed3b  mov     r8d, [rsp+48h+Reply]
0x18001ed40  xor     ecx, ecx
0x18001ed42  test    r8d, r8d
0x18001ed45  jz      short loc_18001ED56
0x18001ed47  lea     rdx, aFwppproxyikesa; "FwppProxyIkeSAUpdatePreferredAddressAsy"...
0x18001ed4e  call    WfpReportSysErrorAsWinError
0x18001ed53  mov     rcx, rax
0x18001ed56  mov     eax, ecx
0x18001ed58  movzx   edx, cx
0x18001ed5b  and     eax, 1FFF0000h
0x18001ed60  cmp     eax, 70000h
0x18001ed65  mov     rax, [rbx+78h]
0x18001ed69  cmovnz  edx, ecx
0x18001ed6c  mov     rcx, [rbx+70h]
0x18001ed70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed75  lea     rcx, [rsp+48h+var_28]
0x18001ed7a  call    WfpMemFree
0x18001ed7f  mov     rcx, [rsp+48h+var_18]
0x18001ed84  xor     rcx, rsp; StackCookie
0x18001ed87  call    __security_check_cookie
0x18001ed8c  add     rsp, 40h
0x18001ed90  pop     rbx
0x18001ed91  retn
```
