# MapsPackageSvcOpen

- ea: `0x180009250`
- end: `0x180009390`
- name: `MapsPackageSvcOpen`
- size: `320`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x180006e20`
- `0x180009250`
- `0x18000a480`
- `0x18000a540`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009358`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009358`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000937b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000937b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180009367`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180009367`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800092a4`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180009340`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800092a4`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180009340`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800092f0`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800092f0`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800092be`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800092be`

## string_xrefs

- `0x180009296`: `[MosHost] MapsPackageSvcOpen, callerType = %d`
- `0x18000928f`: `MapsPackageSvcOpen`
- `0x180009332`: `[MosHost] Service - MapsPackageSvcOpen End.`

## pseudocode

```c
__int64 __fastcall MapsPackageSvcOpen(__int64 a1, unsigned int a2, __int64 a3, _QWORD *a4)
{
  __int64 ClientProcessId; // rdi
  int v9; // eax
  int v10; // r8d
  unsigned int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  HANDLE v14; // rcx
  _BYTE Context[16]; // [rsp+30h] [rbp-58h] BYREF
  HANDLE WaitHandle; // [rsp+40h] [rbp-48h]
  HANDLE hEvent; // [rsp+48h] [rbp-40h]

  ClientProcessId = (unsigned int)GetClientProcessId();
  ScopedWatchdogTimer::ScopedWatchdogTimer(
    Context,
    0x7530u,
    (void (*)(void))ScopedWatchdogHandlers::MapsPackageServiceOpen_CrashOnTimerExpired);
  ZTraceHelperNoThis(5, "MapsPackageSvcOpen", 29, "[MosHost] MapsPackageSvcOpen, callerType = %d", a2);
  v9 = ServiceManager_EnsureInstance();
  if ( v9 < 0 )
  {
    v10 = 31;
LABEL_3:
    v11 = ZTraceReportPropagationNoThis(v9, "MapsPackageSvcOpen", v10);
LABEL_4:
    v12 = v11;
    goto LABEL_10;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)qword_1800185D0 + 192LL))(qword_1800185D0, a1);
  if ( v13 < 0 )
  {
    v11 = ZTraceReportOriginationNoThis(v13, "MapsPackageSvcOpen", 33);
    goto LABEL_4;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)qword_1800185D0 + 112LL))(
         qword_1800185D0,
         5,
         a2,
         (unsigned int)ClientProcessId,
         a3);
  if ( v9 < 0 )
  {
    v10 = 36;
    goto LABEL_3;
  }
  v12 = 0;
  *a4 = ClientProcessId;
LABEL_10:
  ZTraceHelperNoThis(5, "MapsPackageSvcOpen", 43, "[MosHost] Service - MapsPackageSvcOpen End.");
  v14 = hEvent;
  if ( hEvent )
  {
    if ( WaitHandle )
    {
      SetEvent(hEvent);
      UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      v14 = hEvent;
      WaitHandle = 0;
    }
    CloseHandle(v14);
  }
  return v12;
}

```

## disassembly

```asm
0x180009250  push    rbx
0x180009252  push    rbp
0x180009253  push    rsi
0x180009254  push    rdi
0x180009255  push    r14
0x180009257  push    r15
0x180009259  sub     rsp, 58h
0x18000925d  mov     rsi, r9
0x180009260  mov     r14, r8
0x180009263  mov     ebx, edx
0x180009265  mov     rbp, rcx
0x180009268  call    ?GetClientProcessId@@YAKXZ; GetClientProcessId(void)
0x18000926d  lea     r8, ?MapsPackageServiceOpen_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ; void (*)(void)
0x180009274  mov     edi, eax
0x180009276  mov     edx, 7530h; unsigned int
0x18000927b  lea     rcx, [rsp+88h+Context]; Context
0x180009280  call    ??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))
0x180009285  mov     r8d, 1Dh
0x18000928b  mov     dword ptr [rsp+88h+var_68], ebx
0x18000928f  lea     r15, aMapspackagesvc_1; "MapsPackageSvcOpen"
0x180009296  lea     r9, aMoshostMapspac_2; "[MosHost] MapsPackageSvcOpen, callerTyp"...
0x18000929d  mov     rdx, r15
0x1800092a0  lea     ecx, [r8-18h]
0x1800092a4  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x1800092aa  call    ?ServiceManager_EnsureInstance@@YAJXZ; ServiceManager_EnsureInstance(void)
0x1800092af  test    eax, eax
0x1800092b1  jns     short loc_1800092C8
0x1800092b3  mov     r8d, 1Fh
0x1800092b9  mov     rdx, r15
0x1800092bc  mov     ecx, eax
0x1800092be  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800092c4  mov     ebx, eax
0x1800092c6  jmp     short loc_18000932C
0x1800092c8  mov     rcx, cs:qword_1800185D0
0x1800092cf  mov     rdx, rbp
0x1800092d2  mov     rax, [rcx]
0x1800092d5  mov     rax, [rax+0C0h]
0x1800092dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092e1  test    eax, eax
0x1800092e3  jns     short loc_1800092F8
0x1800092e5  mov     r8d, 21h ; '!'
0x1800092eb  mov     rdx, r15
0x1800092ee  mov     ecx, eax
0x1800092f0  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800092f6  jmp     short loc_1800092C4
0x1800092f8  mov     rcx, cs:qword_1800185D0
0x1800092ff  mov     r9d, edi
0x180009302  mov     r8d, ebx
0x180009305  mov     [rsp+88h+var_68], r14
0x18000930a  mov     edx, 5
0x18000930f  mov     rax, [rcx]
0x180009312  mov     rax, [rax+70h]
0x180009316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000931b  test    eax, eax
0x18000931d  jns     short loc_180009327
0x18000931f  mov     r8d, 24h ; '$'
0x180009325  jmp     short loc_1800092B9
0x180009327  xor     ebx, ebx
0x180009329  mov     [rsi], rdi
0x18000932c  mov     r8d, 2Bh ; '+'
0x180009332  lea     r9, aMoshostService_3; "[MosHost] Service - MapsPackageSvcOpen "...
0x180009339  mov     rdx, r15
0x18000933c  lea     ecx, [r8-26h]
0x180009340  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180009346  mov     rcx, [rsp+88h+hEvent]; hEvent
0x18000934b  test    rcx, rcx
0x18000934e  jz      short loc_180009381
0x180009350  cmp     [rsp+88h+WaitHandle], 0
0x180009356  jz      short loc_18000937B
0x180009358  call    cs:__imp_SetEvent
0x18000935e  mov     rcx, [rsp+88h+WaitHandle]; WaitHandle
0x180009363  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180009367  call    cs:__imp_UnregisterWaitEx
0x18000936d  mov     rcx, [rsp+88h+hEvent]; hObject
0x180009372  mov     [rsp+88h+WaitHandle], 0
0x18000937b  call    cs:__imp_CloseHandle
0x180009381  mov     eax, ebx
0x180009383  add     rsp, 58h
0x180009387  pop     r15
0x180009389  pop     r14
0x18000938b  pop     rdi
0x18000938c  pop     rsi
0x18000938d  pop     rbp
0x18000938e  pop     rbx
0x18000938f  retn
```
