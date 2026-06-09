# ReconnectAsyncBase<ulong>::operator()(ulong *)

- ea: `0x1800522bc`
- end: `0x180052364`
- name: `??R?$ReconnectAsyncBase@K@@QEAAKPEAK@Z`
- size: `168`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800511e4`
- `0x180051648`
- `0x180051a84`
- `0x180051eb8`

## callees

- `0x1800522bc`
- `0x18006f910`
- `0x1800b5010`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18005233c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005233c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800522ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800522ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800522f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800522f5`

## pseudocode

```c
__int64 __fastcall ReconnectAsyncBase<unsigned long>::operator()(__int64 a1, _DWORD *a2)
{
  DWORD LastError; // eax
  RPC_STATUS v6; // eax
  _DWORD *Reply; // [rsp+48h] [rbp+10h] BYREF

  Reply = a2;
  *a2 = 0;
  (**(void (__fastcall ***)(__int64))a1)(a1);
  if ( WaitForSingleObject(*(HANDLE *)(a1 + 120), 0xFFFFFFFF) == -1 )
  {
    LastError = GetLastError();
    *a2 = LastError;
    TraceMsg(
      4u,
      7u,
      (__int64)L"ReconnectAsyncBase<unsigned long>::operator ()",
      238,
      L"Could not wait event when calling async rpc function posting %d",
      LastError);
    return 0;
  }
  else
  {
    LODWORD(Reply) = 0;
    v6 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)(a1 + 8), &Reply);
    *a2 = v6;
    if ( !v6 )
      *a2 = 0;
    return (unsigned int)Reply;
  }
}

```

## disassembly

```asm
0x1800522bc  mov     [rsp+arg_0], rbx
0x1800522c1  mov     [rsp+Reply], rdx
0x1800522c6  push    rdi
0x1800522c7  sub     rsp, 30h
0x1800522cb  mov     rbx, rdx
0x1800522ce  mov     rdi, rcx
0x1800522d1  mov     dword ptr [rdx], 0
0x1800522d7  mov     rax, [rcx]
0x1800522da  mov     rax, [rax]
0x1800522dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522e2  nop
0x1800522e3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800522e6  mov     rcx, [rdi+78h]; hHandle
0x1800522ea  call    cs:__imp_WaitForSingleObject
0x1800522f0  cmp     eax, 0FFFFFFFFh
0x1800522f3  jnz     short loc_18005232B
0x1800522f5  call    cs:__imp_GetLastError
0x1800522fb  mov     [rbx], eax
0x1800522fd  mov     [rsp+38h+var_10], eax
0x180052301  lea     rax, aCouldNotWaitEv; "Could not wait event when calling async"...
0x180052308  mov     [rsp+38h+var_18], rax
0x18005230d  mov     r9d, 0EEh
0x180052313  lea     r8, aReconnectasync; "ReconnectAsyncBase<unsigned long>::oper"...
0x18005231a  mov     edx, 7
0x18005231f  lea     ecx, [rdx-3]
0x180052322  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180052327  xor     eax, eax
0x180052329  jmp     short loc_180052359
0x18005232b  mov     dword ptr [rsp+38h+Reply], 0
0x180052333  lea     rcx, [rdi+8]; pAsync
0x180052337  lea     rdx, [rsp+38h+Reply]; Reply
0x18005233c  call    cs:__imp_RpcAsyncCompleteCall
0x180052342  mov     [rbx], eax
0x180052344  test    eax, eax
0x180052346  jnz     short loc_18005234A
0x180052348  mov     [rbx], eax
0x18005234a  mov     eax, dword ptr [rsp+38h+Reply]
0x18005234e  jmp     short loc_180052359
0x180052350  mov     rcx, [rsp+38h+Reply]
0x180052355  mov     [rcx], eax
0x180052357  xor     eax, eax
0x180052359  mov     rbx, [rsp+38h+arg_0]
0x18005235e  add     rsp, 30h
0x180052362  pop     rdi
0x180052363  retn
```
