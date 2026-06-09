# s_LRpcSIDKeyUnprotect

- ea: `0x18003b900`
- end: `0x18003ba98`
- name: `s_LRpcSIDKeyUnprotect`
- size: `408`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, __int64, unsigned int, __int64, _DWORD *, _QWORD *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18003b900`
- `0x18003baa0`
- `0x18003e010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18003b96d`
- `RPCRT4!RpcImpersonateClient` at `0x18003b96d`
- `RPCRT4!RpcRevertToSelf` at `0x18003ba54`
- `RPCRT4!RpcRevertToSelf` at `0x18003ba54`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x18003b9de`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x18003b9de`
- `NTASN1!__imp_RtlAsn1GetModuleHandle` at `0x18003b935`
- `NTASN1!__imp_RtlAsn1GetModuleHandle` at `0x18003b935`
- `KdsCli!SIDKeyUnprotect` at `0x18003ba1c`
- `KdsCli!SIDKeyUnprotect` at `0x18003ba1c`

## pseudocode

```c
__int64 __fastcall s_LRpcSIDKeyUnprotect(
        RPC_BINDING_HANDLE BindingHandle,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        _DWORD *a5,
        _QWORD *a6,
        int a7)
{
  __int64 v8; // r14
  __int64 ModuleHandle; // rdi
  const char *v11; // r8
  signed int v12; // ebx
  RPC_STATUS v13; // eax
  const char *v14; // r8
  signed int v15; // eax
  const char *v16; // r8
  unsigned int v17; // r9d
  __int64 v18; // rcx
  int v20; // [rsp+40h] [rbp-20h] BYREF
  __int64 v21; // [rsp+48h] [rbp-18h] BYREF
  __int64 v22; // [rsp+50h] [rbp-10h] BYREF

  v8 = a3;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  ModuleHandle = RtlAsn1GetModuleHandle(L"{34e4912d-f770-4f49-b020-96dd74c99d02}");
  if ( !ModuleHandle )
  {
    v12 = -2146893792;
    SidKeyDebugTraceError(0x80090020, "hr", v11, 0x96u);
    goto LABEL_13;
  }
  v13 = RpcImpersonateClient(BindingHandle);
  v12 = v13;
  if ( !v13 )
  {
    v15 = RtlAsn1DecodeAndAllocate(ModuleHandle, 22, 1, a4, v8, 0, &qword_18004C048, &v22);
    v12 = v15;
    if ( v15 >= 0 )
    {
      v15 = SIDKeyUnprotect(v22, &qword_18004C048, &v21, &v20, a7);
      v12 = v15;
      if ( v15 >= 0 )
      {
        v18 = v21;
        v12 = 0;
        v21 = 0;
        *a6 = v18;
        *a5 = v20;
        goto LABEL_12;
      }
      v17 = 191;
    }
    else
    {
      v17 = 178;
    }
    SidKeyDebugTraceError(v15, "hr", v16, v17);
LABEL_12:
    RpcRevertToSelf();
    goto LABEL_13;
  }
  SidKeyDebugTraceError(v13, "RpcStatus", v14, 0x9Fu);
  if ( v12 >= 0 )
    v12 = (unsigned __int16)v12 | 0x80010000;
LABEL_13:
  if ( v22 )
    off_18004C058();
  if ( v21 )
    off_18004C058();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003b900  push    rbp
0x18003b902  push    rbx
0x18003b903  push    rsi
0x18003b904  push    rdi
0x18003b905  push    r14
0x18003b907  mov     rbp, rsp
0x18003b90a  sub     rsp, 60h
0x18003b90e  mov     rbx, rcx
0x18003b911  mov     r14d, r8d
0x18003b914  lea     rcx, a34e4912dF7704f; "{34e4912d-f770-4f49-b020-96dd74c99d02}"
0x18003b91b  mov     [rbp+var_20], 0
0x18003b922  mov     rsi, r9
0x18003b925  mov     [rbp+var_18], 0
0x18003b92d  mov     [rbp+var_10], 0
0x18003b935  call    cs:__imp_RtlAsn1GetModuleHandle
0x18003b93c  nop     dword ptr [rax+rax+00h]
0x18003b941  mov     rdi, rax
0x18003b944  test    rax, rax
0x18003b947  jnz     short loc_18003B96A
0x18003b949  mov     r9d, 96h; unsigned int
0x18003b94f  lea     rdx, aHr; "hr"
0x18003b956  mov     ecx, 80090020h; unsigned int
0x18003b95b  mov     ebx, 80090020h
0x18003b960  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18003b965  jmp     loc_18003BA60
0x18003b96a  mov     rcx, rbx; BindingHandle
0x18003b96d  call    cs:__imp_RpcImpersonateClient
0x18003b974  nop     dword ptr [rax+rax+00h]
0x18003b979  mov     ebx, eax
0x18003b97b  test    eax, eax
0x18003b97d  jz      short loc_18003B9A9
0x18003b97f  mov     r9d, 9Fh; unsigned int
0x18003b985  lea     rdx, aRpcstatus; "RpcStatus"
0x18003b98c  mov     ecx, eax; unsigned int
0x18003b98e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18003b993  test    ebx, ebx
0x18003b995  js      loc_18003BA60
0x18003b99b  movzx   ebx, bx
0x18003b99e  or      ebx, 80010000h
0x18003b9a4  jmp     loc_18003BA60
0x18003b9a9  mov     rax, r14
0x18003b9ac  lea     rcx, [rbp+var_10]
0x18003b9b0  mov     [rsp+60h+var_28], rcx
0x18003b9b5  lea     r14, qword_18004C048
0x18003b9bc  mov     edx, 16h
0x18003b9c1  mov     [rsp+60h+var_30], r14
0x18003b9c6  mov     [rsp+60h+var_38], 0
0x18003b9cf  mov     r9, rsi
0x18003b9d2  mov     rcx, rdi
0x18003b9d5  mov     [rsp+60h+var_40], rax
0x18003b9da  lea     r8d, [rdx-15h]
0x18003b9de  call    cs:__imp_RtlAsn1DecodeAndAllocate
0x18003b9e5  nop     dword ptr [rax+rax+00h]
0x18003b9ea  mov     ebx, eax
0x18003b9ec  test    eax, eax
0x18003b9ee  jns     short loc_18003BA06
0x18003b9f0  mov     r9d, 0B2h; unsigned int
0x18003b9f6  lea     rdx, aHr; "hr"
0x18003b9fd  mov     ecx, eax; unsigned int
0x18003b9ff  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18003ba04  jmp     short loc_18003BA54
0x18003ba06  mov     eax, [rbp+arg_30]
0x18003ba09  lea     r9, [rbp+var_20]
0x18003ba0d  mov     rcx, [rbp+var_10]
0x18003ba11  lea     r8, [rbp+var_18]
0x18003ba15  mov     rdx, r14
0x18003ba18  mov     dword ptr [rsp+60h+var_40], eax
0x18003ba1c  call    cs:__imp_SIDKeyUnprotect
0x18003ba23  nop     dword ptr [rax+rax+00h]
0x18003ba28  mov     ebx, eax
0x18003ba2a  test    eax, eax
0x18003ba2c  jns     short loc_18003BA36
0x18003ba2e  mov     r9d, 0BFh
0x18003ba34  jmp     short loc_18003B9F6
0x18003ba36  mov     rcx, [rbp+var_18]
0x18003ba3a  xor     ebx, ebx
0x18003ba3c  mov     rax, [rbp+arg_28]
0x18003ba40  mov     [rbp+var_18], 0
0x18003ba48  mov     [rax], rcx
0x18003ba4b  mov     rax, [rbp+arg_20]
0x18003ba4f  mov     ecx, [rbp+var_20]
0x18003ba52  mov     [rax], ecx
0x18003ba54  call    cs:__imp_RpcRevertToSelf
0x18003ba5b  nop     dword ptr [rax+rax+00h]
0x18003ba60  mov     rcx, [rbp+var_10]
0x18003ba64  test    rcx, rcx
0x18003ba67  jz      short loc_18003BA75
0x18003ba69  mov     rax, cs:off_18004C058
0x18003ba70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba75  mov     rcx, [rbp+var_18]
0x18003ba79  test    rcx, rcx
0x18003ba7c  jz      short loc_18003BA8A
0x18003ba7e  mov     rax, cs:off_18004C058
0x18003ba85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba8a  mov     eax, ebx
0x18003ba8c  add     rsp, 60h
0x18003ba90  pop     r14
0x18003ba92  pop     rdi
0x18003ba93  pop     rsi
0x18003ba94  pop     rbx
0x18003ba95  pop     rbp
0x18003ba96  retn
```
