# PMAPSPACKAGE_CONTEXT_HANDLE_TYPE_rundown

- ea: `0x1800093a0`
- end: `0x180009478`
- name: `PMAPSPACKAGE_CONTEXT_HANDLE_TYPE_rundown`
- size: `216`
- prototype: `int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180009070`

## callees

- `0x180006e20`
- `0x1800093a0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009449`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009449`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000946c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000946c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180009458`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180009458`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800093d7`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180009431`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800093d7`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180009431`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000940b`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000940b`

## string_xrefs

- `0x1800093c5`: `[MosHost] Service - rundown start`
- `0x18000941f`: `[MosHost] Service - rundown end, hr=0x%08x`

## pseudocode

```c
int __fastcall PMAPSPACKAGE_CONTEXT_HANDLE_TYPE_rundown(unsigned int a1)
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
    (void (*)(void))ScopedWatchdogHandlers::MapsPackageServiceClose_CrashOnTimerExpired);
  ZTraceHelperNoThis(5, "PMAPSPACKAGE_CONTEXT_HANDLE_TYPE_rundown", 79, "[MosHost] Service - rundown start");
  v2 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)qword_1800185D0 + 120LL))(
         qword_1800185D0,
         5,
         a1);
  if ( v2 >= 0 )
    v3 = 0;
  else
    v3 = ZTraceReportPropagationNoThis(v2, "PMAPSPACKAGE_CONTEXT_HANDLE_TYPE_rundown", 81);
  result = ZTraceHelperNoThis(
             5,
             "PMAPSPACKAGE_CONTEXT_HANDLE_TYPE_rundown",
             85,
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
0x1800093a0  push    rbx
0x1800093a2  sub     rsp, 50h
0x1800093a6  mov     rbx, rcx
0x1800093a9  lea     r8, ?MapsPackageServiceClose_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ; void (*)(void)
0x1800093b0  lea     rcx, [rsp+58h+Context]; Context
0x1800093b5  mov     edx, 7530h; unsigned int
0x1800093ba  call    ??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))
0x1800093bf  mov     r8d, 4Fh ; 'O'
0x1800093c5  lea     r9, aMoshostService_6; "[MosHost] Service - rundown start"
0x1800093cc  lea     rdx, aPmapspackageCo; "PMAPSPACKAGE_CONTEXT_HANDLE_TYPE_rundow"...
0x1800093d3  lea     ecx, [r8-4Ah]
0x1800093d7  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x1800093dd  mov     rcx, cs:qword_1800185D0
0x1800093e4  mov     r8d, ebx
0x1800093e7  mov     edx, 5
0x1800093ec  mov     rax, [rcx]
0x1800093ef  mov     rax, [rax+78h]
0x1800093f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f8  test    eax, eax
0x1800093fa  jns     short loc_180009413
0x1800093fc  mov     r8d, 51h ; 'Q'
0x180009402  lea     rdx, aPmapspackageCo; "PMAPSPACKAGE_CONTEXT_HANDLE_TYPE_rundow"...
0x180009409  mov     ecx, eax
0x18000940b  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180009411  jmp     short loc_180009415
0x180009413  xor     eax, eax
0x180009415  mov     r8d, 55h ; 'U'
0x18000941b  mov     [rsp+58h+var_38], eax
0x18000941f  lea     r9, aMoshostService; "[MosHost] Service - rundown end, hr=0x%"...
0x180009426  lea     rdx, aPmapspackageCo; "PMAPSPACKAGE_CONTEXT_HANDLE_TYPE_rundow"...
0x18000942d  lea     ecx, [r8-50h]
0x180009431  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180009437  mov     rcx, [rsp+58h+hEvent]; hEvent
0x18000943c  test    rcx, rcx
0x18000943f  jz      short loc_180009472
0x180009441  cmp     [rsp+58h+WaitHandle], 0
0x180009447  jz      short loc_18000946C
0x180009449  call    cs:__imp_SetEvent
0x18000944f  mov     rcx, [rsp+58h+WaitHandle]; WaitHandle
0x180009454  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180009458  call    cs:__imp_UnregisterWaitEx
0x18000945e  mov     rcx, [rsp+58h+hEvent]; hObject
0x180009463  mov     [rsp+58h+WaitHandle], 0
0x18000946c  call    cs:__imp_CloseHandle
0x180009472  add     rsp, 50h
0x180009476  pop     rbx
0x180009477  retn
```
