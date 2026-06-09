# OdmlSvcOpen

- ea: `0x1800082d0`
- end: `0x180008452`
- name: `OdmlSvcOpen`
- size: `386`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006e20`
- `0x1800082d0`
- `0x18000a480`
- `0x18000a540`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000840e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000840e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008431`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008431`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000841d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000841d`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000832d`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000832d`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800083e3`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800083e3`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008370`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008370`

## string_xrefs

- `0x18000831f`: `[MosHost] OdmlSvcOpen, callerType = %d`
- `0x180008318`: `OdmlSvcOpen`

## pseudocode

```c
__int64 __fastcall OdmlSvcOpen(__int64 a1, unsigned int a2, __int64 a3, _QWORD *a4)
{
  __int64 ClientProcessId; // rsi
  int v9; // r8d
  int v10; // ecx
  char v11; // di
  int v12; // eax
  int v13; // eax
  int v14; // eax
  unsigned int v15; // ebx
  HANDLE v16; // rcx
  _BYTE Context[16]; // [rsp+30h] [rbp-48h] BYREF
  HANDLE WaitHandle; // [rsp+40h] [rbp-38h]
  HANDLE hEvent; // [rsp+48h] [rbp-30h]

  ClientProcessId = GetClientProcessId();
  ScopedWatchdogTimer::ScopedWatchdogTimer(
    Context,
    0x7530u,
    (void (*)(void))ScopedWatchdogHandlers::OdmlServiceOpen_CrashOnTimerExpired);
  ZTraceHelperNoThis(5, "OdmlSvcOpen", 35, "[MosHost] OdmlSvcOpen, callerType = %d", a2);
  if ( !a4 )
  {
    v9 = 37;
    v10 = -2147467261;
LABEL_13:
    v11 = 0;
LABEL_14:
    v13 = ZTraceReportOriginationNoThis(v10, "OdmlSvcOpen", v9);
    goto LABEL_15;
  }
  *a4 = 0;
  if ( _InterlockedCompareExchange(&dword_1800185C4, ClientProcessId, 0) )
  {
    v9 = 43;
    v10 = -2147024864;
    goto LABEL_13;
  }
  v11 = 1;
  v12 = ServiceManager_EnsureInstance();
  if ( v12 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)qword_1800185D0 + 192LL))(qword_1800185D0, a1);
    if ( v14 >= 0 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)qword_1800185D0 + 112LL))(
              qword_1800185D0,
              1,
              a2,
              (unsigned int)ClientProcessId,
              a3);
      v15 = v14;
      if ( v14 >= 0 )
      {
        *a4 = ClientProcessId;
        goto LABEL_18;
      }
      v9 = 51;
    }
    else
    {
      v9 = 47;
    }
    v10 = v14;
    goto LABEL_14;
  }
  v13 = ZTraceReportPropagationNoThis(v12, "OdmlSvcOpen", 45);
LABEL_15:
  v15 = v13;
  if ( v13 < 0 && v11 )
    _InterlockedExchange(&dword_1800185C4, 0);
LABEL_18:
  v16 = hEvent;
  if ( hEvent )
  {
    if ( WaitHandle )
    {
      SetEvent(hEvent);
      UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      v16 = hEvent;
      WaitHandle = 0;
    }
    CloseHandle(v16);
  }
  return v15;
}

```

## disassembly

```asm
0x1800082d0  mov     [rsp+arg_0], rbx
0x1800082d5  mov     [rsp+arg_8], rbp
0x1800082da  push    rsi
0x1800082db  push    rdi
0x1800082dc  push    r13
0x1800082de  push    r14
0x1800082e0  push    r15
0x1800082e2  sub     rsp, 50h
0x1800082e6  mov     r14, r9
0x1800082e9  mov     r15, r8
0x1800082ec  mov     ebx, edx
0x1800082ee  mov     rbp, rcx
0x1800082f1  call    ?GetClientProcessId@@YAKXZ; GetClientProcessId(void)
0x1800082f6  lea     r8, ?OdmlServiceOpen_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ; void (*)(void)
0x1800082fd  mov     esi, eax
0x1800082ff  mov     edx, 7530h; unsigned int
0x180008304  lea     rcx, [rsp+78h+Context]; Context
0x180008309  call    ??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))
0x18000830e  mov     r8d, 23h ; '#'
0x180008314  mov     dword ptr [rsp+78h+var_58], ebx
0x180008318  lea     r13, aOdmlsvcopen; "OdmlSvcOpen"
0x18000831f  lea     r9, aMoshostOdmlsvc_2; "[MosHost] OdmlSvcOpen, callerType = %d"
0x180008326  mov     rdx, r13
0x180008329  lea     ecx, [r8-1Eh]
0x18000832d  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180008333  test    r14, r14
0x180008336  jnz     short loc_180008346
0x180008338  lea     r8d, [r14+25h]
0x18000833c  mov     ecx, 80004003h
0x180008341  jmp     loc_1800083DD
0x180008346  mov     qword ptr [r14], 0
0x18000834d  xor     eax, eax
0x18000834f  lock cmpxchg cs:dword_1800185C4, esi
0x180008357  jnz     short loc_1800083D2
0x180008359  mov     edi, 1
0x18000835e  call    ?ServiceManager_EnsureInstance@@YAJXZ; ServiceManager_EnsureInstance(void)
0x180008363  test    eax, eax
0x180008365  jns     short loc_180008378
0x180008367  lea     r8d, [rdi+2Ch]
0x18000836b  mov     rdx, r13
0x18000836e  mov     ecx, eax
0x180008370  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008376  jmp     short loc_1800083E9
0x180008378  mov     rcx, cs:qword_1800185D0
0x18000837f  mov     rdx, rbp
0x180008382  mov     rax, [rcx]
0x180008385  mov     rax, [rax+0C0h]
0x18000838c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008391  test    eax, eax
0x180008393  jns     short loc_18000839F
0x180008395  mov     r8d, 2Fh ; '/'
0x18000839b  mov     ecx, eax
0x18000839d  jmp     short loc_1800083E0
0x18000839f  mov     rcx, cs:qword_1800185D0
0x1800083a6  mov     r9d, esi
0x1800083a9  mov     r8d, ebx
0x1800083ac  mov     [rsp+78h+var_58], r15
0x1800083b1  mov     edx, edi
0x1800083b3  mov     rax, [rcx]
0x1800083b6  mov     rax, [rax+70h]
0x1800083ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083bf  mov     ebx, eax
0x1800083c1  test    eax, eax
0x1800083c3  jns     short loc_1800083CD
0x1800083c5  mov     r8d, 33h ; '3'
0x1800083cb  jmp     short loc_18000839B
0x1800083cd  mov     [r14], rsi
0x1800083d0  jmp     short loc_1800083FC
0x1800083d2  mov     r8d, 2Bh ; '+'
0x1800083d8  mov     ecx, 80070020h
0x1800083dd  xor     dil, dil
0x1800083e0  mov     rdx, r13
0x1800083e3  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800083e9  mov     ebx, eax
0x1800083eb  test    eax, eax
0x1800083ed  jns     short loc_1800083FC
0x1800083ef  test    dil, dil
0x1800083f2  jz      short loc_1800083FC
0x1800083f4  xor     eax, eax
0x1800083f6  xchg    eax, cs:dword_1800185C4
0x1800083fc  mov     rcx, [rsp+78h+hEvent]; hEvent
0x180008401  test    rcx, rcx
0x180008404  jz      short loc_180008437
0x180008406  cmp     [rsp+78h+WaitHandle], 0
0x18000840c  jz      short loc_180008431
0x18000840e  call    cs:__imp_SetEvent
0x180008414  mov     rcx, [rsp+78h+WaitHandle]; WaitHandle
0x180008419  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000841d  call    cs:__imp_UnregisterWaitEx
0x180008423  mov     rcx, [rsp+78h+hEvent]; hObject
0x180008428  mov     [rsp+78h+WaitHandle], 0
0x180008431  call    cs:__imp_CloseHandle
0x180008437  lea     r11, [rsp+78h+var_28]
0x18000843c  mov     eax, ebx
0x18000843e  mov     rbx, [r11+30h]
0x180008442  mov     rbp, [r11+38h]
0x180008446  mov     rsp, r11
0x180008449  pop     r15
0x18000844b  pop     r14
0x18000844d  pop     r13
0x18000844f  pop     rdi
0x180008450  pop     rsi
0x180008451  retn
```
