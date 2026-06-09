# CTcpServ::~CTcpServ(void)

- ea: `0x18006d4e0`
- end: `0x18006d64d`
- name: `??1CTcpServ@@QEAA@XZ`
- size: `365`
- prototype: `void __fastcall(CTcpServ *__hidden this)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18004a7f0`
- `0x18004ad5c`
- `0x18004ae0c`
- `0x18004afe4`

## callees

- `0x180047900`
- `0x18006d4e0`
- `0x18006db10`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800be0dc`
- `0x1800f8314`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d503`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d5a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d5a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d5b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d5b7`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18006d55f`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18006d55f`
- `WS2_32!__imp_closesocket` at `0x18006d5af`
- `WS2_32!__imp_closesocket` at `0x18006d5dc`
- `WS2_32!__imp_closesocket` at `0x18006d5eb`
- `WS2_32!__imp_closesocket` at `0x18006d5af`
- `WS2_32!__imp_closesocket` at `0x18006d5dc`
- `WS2_32!__imp_closesocket` at `0x18006d5eb`

## string_xrefs

- `0x18006d51d`: `_core.GetTaskThread().IsCurrentThread()`

## pseudocode

```c
void __fastcall CTcpServ::~CTcpServ(CTcpServ *this)
{
  __int64 v2; // rbx
  void *v3; // rcx
  void **v4; // rsi
  __int64 v5; // rdx
  SOCKET v6; // rbp
  DWORD LastError; // ebx
  SOCKET v8; // rcx
  SOCKET v9; // rcx
  volatile signed __int32 *v10; // rbx

  v2 = *(_QWORD *)(*(_QWORD *)this + 8LL);
  if ( *(_DWORD *)(v2 + 176) != GetCurrentThreadId() )
  {
    LogMessage(
      2u,
      "CTcpServ::~CTcpServ",
      0x6Cu,
      "TelemetryAssert (%s): %s",
      "_core.GetTaskThread().IsCurrentThread()",
      "Failed");
    DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
  }
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 != (void *)-1LL )
    CancelIoEx(v3, 0);
  v4 = (void **)((char *)this + 40);
  v5 = *((_QWORD *)this + 5);
  if ( v5 )
    CIoCompletionPort::DeregisterCallback(*(_QWORD *)this + 24LL, *(_QWORD *)(v5 + 32), (char *)this + 40);
  CTaskThread::Unschedule(*(CTaskThread **)(*(_QWORD *)this + 8LL), this);
  CTcpServ::_CloseAcceptSock(this);
  v6 = *((_QWORD *)this + 3);
  if ( v6 != -1 )
  {
    LastError = GetLastError();
    closesocket(v6);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 3) = -1;
  if ( *v4 )
    operator delete(*v4);
  v8 = *((_QWORD *)this + 4);
  if ( v8 != -1 )
    closesocket(v8);
  v9 = *((_QWORD *)this + 3);
  if ( v9 != -1 )
    closesocket(v9);
  v10 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  if ( v10 && !_InterlockedDecrement(v10 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
    if ( !_InterlockedDecrement(v10 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
  }
}

```

## disassembly

```asm
0x18006d4e0  mov     rax, rsp
0x18006d4e3  mov     [rax+8], rbx
0x18006d4e7  mov     [rax+10h], rbp
0x18006d4eb  mov     [rax+18h], rsi
0x18006d4ef  mov     [rax+20h], rdi
0x18006d4f3  push    r14
0x18006d4f5  sub     rsp, 30h
0x18006d4f9  mov     rdi, rcx
0x18006d4fc  mov     rax, [rcx]
0x18006d4ff  mov     rbx, [rax+8]
0x18006d503  call    cs:__imp_GetCurrentThreadId
0x18006d509  cmp     [rbx+0B0h], eax
0x18006d50f  jz      short loc_18006D550
0x18006d511  lea     rax, aFailed; "Failed"
0x18006d518  mov     [rsp+38h+var_10], rax
0x18006d51d  lea     rax, aCoreGettaskthr; "_core.GetTaskThread().IsCurrentThread()"
0x18006d524  mov     [rsp+38h+var_18], rax
0x18006d529  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x18006d530  mov     r8d, 6Ch ; 'l'; unsigned int
0x18006d536  lea     rdx, aCtcpservCtcpse_0; "CTcpServ::~CTcpServ"
0x18006d53d  lea     ecx, [r8-6Ah]; unsigned __int8
0x18006d541  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x18006d546  or      ecx, 0FFFFFFFFh; unsigned int
0x18006d549  mov     edx, ecx; unsigned int
0x18006d54b  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x18006d550  mov     rcx, [rdi+18h]; hFile
0x18006d554  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006d558  cmp     rcx, r14
0x18006d55b  jz      short loc_18006D565
0x18006d55d  xor     edx, edx; lpOverlapped
0x18006d55f  call    cs:__imp_CancelIoEx
0x18006d565  lea     rsi, [rdi+28h]
0x18006d569  mov     rdx, [rsi]
0x18006d56c  test    rdx, rdx
0x18006d56f  jz      short loc_18006D584
0x18006d571  mov     rcx, [rdi]
0x18006d574  add     rcx, 18h
0x18006d578  mov     r8, rsi
0x18006d57b  mov     rdx, [rdx+20h]
0x18006d57f  call    ?DeregisterCallback@CIoCompletionPort@@QEAAXPEBXPEAV?$unique_ptr@VCOverlappedIoOp@@U?$default_delete@VCOverlappedIoOp@@@std@@@std@@@Z; CIoCompletionPort::DeregisterCallback(void const *,std::unique_ptr<COverlappedIoOp> *)
0x18006d584  mov     rcx, [rdi]
0x18006d587  mov     rdx, rdi; void *
0x18006d58a  mov     rcx, [rcx+8]; this
0x18006d58e  call    ?Unschedule@CTaskThread@@QEAAXPEBX@Z; CTaskThread::Unschedule(void const *)
0x18006d593  mov     rcx, rdi; this
0x18006d596  call    ?_CloseAcceptSock@CTcpServ@@AEAAXXZ; CTcpServ::_CloseAcceptSock(void)
0x18006d59b  mov     rbp, [rdi+18h]
0x18006d59f  cmp     rbp, r14
0x18006d5a2  jz      short loc_18006D5BD
0x18006d5a4  call    cs:__imp_GetLastError
0x18006d5aa  mov     ebx, eax
0x18006d5ac  mov     rcx, rbp; s
0x18006d5af  call    cs:__imp_closesocket
0x18006d5b5  mov     ecx, ebx; dwErrCode
0x18006d5b7  call    cs:__imp_SetLastError
0x18006d5bd  mov     [rdi+18h], r14
0x18006d5c1  mov     rcx, [rsi]; Block
0x18006d5c4  test    rcx, rcx
0x18006d5c7  jz      short loc_18006D5D3
0x18006d5c9  mov     edx, 30h ; '0'
0x18006d5ce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006d5d3  mov     rcx, [rdi+20h]; s
0x18006d5d7  cmp     rcx, r14
0x18006d5da  jz      short loc_18006D5E2
0x18006d5dc  call    cs:__imp_closesocket
0x18006d5e2  mov     rcx, [rdi+18h]; s
0x18006d5e6  cmp     rcx, r14
0x18006d5e9  jz      short loc_18006D5F1
0x18006d5eb  call    cs:__imp_closesocket
0x18006d5f1  mov     rbx, [rdi+10h]
0x18006d5f5  test    rbx, rbx
0x18006d5f8  jz      short loc_18006D632
0x18006d5fa  mov     eax, r14d
0x18006d5fd  lock xadd [rbx+8], eax
0x18006d602  add     eax, r14d
0x18006d605  jnz     short loc_18006D632
0x18006d607  mov     rax, [rbx]
0x18006d60a  mov     rcx, rbx
0x18006d60d  mov     rax, [rax]
0x18006d610  call    _guard_dispatch_icall
0x18006d615  mov     eax, r14d
0x18006d618  lock xadd [rbx+0Ch], eax
0x18006d61d  add     eax, r14d
0x18006d620  jnz     short loc_18006D632
0x18006d622  mov     rax, [rbx]
0x18006d625  mov     rcx, rbx
0x18006d628  mov     rax, [rax+8]
0x18006d62c  call    _guard_dispatch_icall
0x18006d631  nop
0x18006d632  mov     rbx, [rsp+38h+arg_0]
0x18006d637  mov     rbp, [rsp+38h+arg_8]
0x18006d63c  mov     rsi, [rsp+38h+arg_10]
0x18006d641  mov     rdi, [rsp+38h+arg_18]
0x18006d646  add     rsp, 30h
0x18006d64a  pop     r14
0x18006d64c  retn
```
