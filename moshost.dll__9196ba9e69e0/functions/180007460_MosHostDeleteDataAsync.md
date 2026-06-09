# MosHostDeleteDataAsync

- ea: `0x180007460`
- end: `0x180007544`
- name: `MosHostDeleteDataAsync`
- size: `228`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006e20`
- `0x180007460`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007512`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007512`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007535`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007535`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800074fa`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800074fa`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180007521`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180007521`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800074e8`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800074e8`

## string_xrefs

- `0x1800074df`: `MosHostDeleteDataAsync`

## pseudocode

```c
RPC_STATUS __fastcall MosHostDeleteDataAsync(
        PRPC_ASYNC_STATE pAsync,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  int v8; // eax
  int v9; // r8d
  RPC_STATUS result; // eax
  HANDLE v11; // rcx
  int Reply; // [rsp+20h] [rbp-58h] BYREF
  _BYTE Context[16]; // [rsp+28h] [rbp-50h] BYREF
  HANDLE WaitHandle; // [rsp+38h] [rbp-40h]
  HANDLE hEvent; // [rsp+40h] [rbp-38h]

  Reply = 0;
  ScopedWatchdogTimer::ScopedWatchdogTimer(
    Context,
    0x493E0u,
    (void (*)(void))ScopedWatchdogHandlers::MosHostDeleteDataAsync_CrashOnTimerExpired);
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)qword_1800185D0 + 256LL))(qword_1800185D0, a2, 0);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)qword_1800185D0 + 144LL))(
           qword_1800185D0,
           a4,
           a3);
    if ( v8 >= 0 )
      goto LABEL_6;
    v9 = 335;
  }
  else
  {
    v9 = 333;
  }
  Reply = ZTraceReportPropagationNoThis(v8, "MosHostDeleteDataAsync", v9);
LABEL_6:
  result = RpcAsyncCompleteCall(pAsync, &Reply);
  v11 = hEvent;
  if ( hEvent )
  {
    if ( WaitHandle )
    {
      SetEvent(hEvent);
      UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      v11 = hEvent;
      WaitHandle = 0;
    }
    return CloseHandle(v11);
  }
  return result;
}

```

## disassembly

```asm
0x180007460  push    rbx
0x180007462  push    rbp
0x180007463  push    rsi
0x180007464  push    rdi
0x180007465  sub     rsp, 58h
0x180007469  mov     ebp, r8d
0x18000746c  mov     [rsp+78h+Reply], 0
0x180007474  mov     rbx, rdx
0x180007477  lea     r8, ?MosHostDeleteDataAsync_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ; void (*)(void)
0x18000747e  mov     rdi, rcx
0x180007481  mov     edx, 493E0h; unsigned int
0x180007486  lea     rcx, [rsp+78h+Context]; Context
0x18000748b  mov     esi, r9d
0x18000748e  call    ??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))
0x180007493  mov     rcx, cs:qword_1800185D0
0x18000749a  mov     edx, ebx
0x18000749c  xor     r8d, r8d
0x18000749f  mov     rax, [rcx]
0x1800074a2  mov     rax, [rax+100h]
0x1800074a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074ae  test    eax, eax
0x1800074b0  jns     short loc_1800074BA
0x1800074b2  mov     r8d, 14Dh
0x1800074b8  jmp     short loc_1800074DF
0x1800074ba  mov     rcx, cs:qword_1800185D0
0x1800074c1  mov     r8d, ebp
0x1800074c4  mov     edx, esi
0x1800074c6  mov     rax, [rcx]
0x1800074c9  mov     rax, [rax+90h]
0x1800074d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074d5  test    eax, eax
0x1800074d7  jns     short loc_1800074F2
0x1800074d9  mov     r8d, 14Fh
0x1800074df  lea     rdx, aMoshostdeleted; "MosHostDeleteDataAsync"
0x1800074e6  mov     ecx, eax
0x1800074e8  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800074ee  mov     [rsp+78h+Reply], eax
0x1800074f2  lea     rdx, [rsp+78h+Reply]; Reply
0x1800074f7  mov     rcx, rdi; pAsync
0x1800074fa  call    cs:__imp_RpcAsyncCompleteCall
0x180007500  mov     rcx, [rsp+78h+hEvent]; hEvent
0x180007505  test    rcx, rcx
0x180007508  jz      short loc_18000753B
0x18000750a  cmp     [rsp+78h+WaitHandle], 0
0x180007510  jz      short loc_180007535
0x180007512  call    cs:__imp_SetEvent
0x180007518  mov     rcx, [rsp+78h+WaitHandle]; WaitHandle
0x18000751d  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180007521  call    cs:__imp_UnregisterWaitEx
0x180007527  mov     rcx, [rsp+78h+hEvent]; hObject
0x18000752c  mov     [rsp+78h+WaitHandle], 0
0x180007535  call    cs:__imp_CloseHandle
0x18000753b  add     rsp, 58h
0x18000753f  pop     rdi
0x180007540  pop     rsi
0x180007541  pop     rbp
0x180007542  pop     rbx
0x180007543  retn
```
