# PMOSHOST_CONTEXT_HANDLE_TYPE_rundown

- ea: `0x180007aa0`
- end: `0x180007b77`
- name: `PMOSHOST_CONTEXT_HANDLE_TYPE_rundown`
- size: `215`
- prototype: `int __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180007300`
- `0x180007a90`

## callees

- `0x180006e20`
- `0x180007aa0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007b48`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007b48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b6b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180007b57`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180007b57`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007ad8`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007b30`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007ad8`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007b30`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007b09`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007b09`

## string_xrefs

- `0x180007abf`: `[MosHost] Service - rundown start`
- `0x180007b13`: `[MosHost] Service - rundown end, hr=0x%08x`

## pseudocode

```c
int __fastcall PMOSHOST_CONTEXT_HANDLE_TYPE_rundown(unsigned int a1)
{
  int v2; // eax
  int v3; // eax
  int result; // eax
  HANDLE v5; // rcx
  _BYTE Context[16]; // [rsp+30h] [rbp-28h] BYREF
  HANDLE WaitHandle; // [rsp+40h] [rbp-18h]
  HANDLE hEvent; // [rsp+48h] [rbp-10h]

  ScopedWatchdogTimer::ScopedWatchdogTimer(
    Context,
    30000,
    (void (*)(void))ScopedWatchdogHandlers::MosHostCloseContext_CrashOnTimerExpired);
  ZTraceHelperNoThis(5, "PMOSHOST_CONTEXT_HANDLE_TYPE_rundown", 415, "[MosHost] Service - rundown start");
  v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)qword_1800185D0 + 120LL))(qword_1800185D0, 0, a1);
  if ( v2 >= 0 )
    v3 = 0;
  else
    v3 = ZTraceReportPropagationNoThis(v2, "PMOSHOST_CONTEXT_HANDLE_TYPE_rundown", 418);
  result = ZTraceHelperNoThis(
             5,
             "PMOSHOST_CONTEXT_HANDLE_TYPE_rundown",
             422,
             "[MosHost] Service - rundown end, hr=0x%08x",
             v3);
  v5 = hEvent;
  if ( hEvent )
  {
    if ( WaitHandle )
    {
      SetEvent(hEvent);
      UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      v5 = hEvent;
      WaitHandle = 0;
    }
    return CloseHandle(v5);
  }
  return result;
}

```

## disassembly

```asm
0x180007aa0  push    rbx
0x180007aa2  sub     rsp, 50h
0x180007aa6  mov     rbx, rcx
0x180007aa9  lea     r8, ?MosHostCloseContext_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ; void (*)(void)
0x180007ab0  lea     rcx, [rsp+58h+Context]; Context
0x180007ab5  mov     edx, 7530h; unsigned int
0x180007aba  call    ??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))
0x180007abf  lea     r9, aMoshostService_6; "[MosHost] Service - rundown start"
0x180007ac6  mov     r8d, 19Fh
0x180007acc  lea     rdx, aPmoshostContex; "PMOSHOST_CONTEXT_HANDLE_TYPE_rundown"
0x180007ad3  mov     ecx, 5
0x180007ad8  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180007ade  mov     rcx, cs:qword_1800185D0
0x180007ae5  mov     r8d, ebx
0x180007ae8  xor     edx, edx
0x180007aea  mov     rax, [rcx]
0x180007aed  mov     rax, [rax+78h]
0x180007af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af6  test    eax, eax
0x180007af8  jns     short loc_180007B11
0x180007afa  mov     r8d, 1A2h
0x180007b00  lea     rdx, aPmoshostContex; "PMOSHOST_CONTEXT_HANDLE_TYPE_rundown"
0x180007b07  mov     ecx, eax
0x180007b09  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180007b0f  jmp     short loc_180007B13
0x180007b11  xor     eax, eax
0x180007b13  lea     r9, aMoshostService; "[MosHost] Service - rundown end, hr=0x%"...
0x180007b1a  mov     [rsp+58h+var_38], eax
0x180007b1e  mov     r8d, 1A6h
0x180007b24  lea     rdx, aPmoshostContex; "PMOSHOST_CONTEXT_HANDLE_TYPE_rundown"
0x180007b2b  mov     ecx, 5
0x180007b30  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180007b36  mov     rcx, [rsp+58h+hEvent]; hEvent
0x180007b3b  test    rcx, rcx
0x180007b3e  jz      short loc_180007B71
0x180007b40  cmp     [rsp+58h+WaitHandle], 0
0x180007b46  jz      short loc_180007B6B
0x180007b48  call    cs:__imp_SetEvent
0x180007b4e  mov     rcx, [rsp+58h+WaitHandle]; WaitHandle
0x180007b53  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180007b57  call    cs:__imp_UnregisterWaitEx
0x180007b5d  mov     rcx, [rsp+58h+hEvent]; hObject
0x180007b62  mov     [rsp+58h+WaitHandle], 0
0x180007b6b  call    cs:__imp_CloseHandle
0x180007b71  add     rsp, 50h
0x180007b75  pop     rbx
0x180007b76  retn
```
