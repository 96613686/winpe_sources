# MosHostCreateContext

- ea: `0x180007350`
- end: `0x180007455`
- name: `MosHostCreateContext`
- size: `261`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x180006e20`
- `0x180007350`
- `0x18000a480`
- `0x18000a540`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007421`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007421`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007444`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007444`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180007430`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180007430`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007397`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007409`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007397`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180007409`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800073b5`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800073b5`

## string_xrefs

- `0x18000737e`: `[MosHost] Service - MosHostCreateContext Start`
- `0x18000738b`: `MosHostCreateContext`
- `0x1800073ac`: `MosHostCreateContext`
- `0x1800073fd`: `MosHostCreateContext`
- `0x1800073f0`: `[MosHost] Service - MosHostCreateContext End.`

## pseudocode

```c
__int64 __fastcall MosHostCreateContext(__int64 a1, unsigned int a2, __int64 a3, _QWORD *a4)
{
  __int64 ClientProcessId; // rdi
  int v8; // eax
  int v9; // r8d
  unsigned int v10; // ebx
  HANDLE v11; // rcx
  _BYTE Context[16]; // [rsp+30h] [rbp-48h] BYREF
  HANDLE WaitHandle; // [rsp+40h] [rbp-38h]
  HANDLE hEvent; // [rsp+48h] [rbp-30h]

  ClientProcessId = GetClientProcessId();
  ScopedWatchdogTimer::ScopedWatchdogTimer(
    Context,
    0x7530u,
    (void (*)(void))ScopedWatchdogHandlers::MosHostCreateContext_CrashOnTimerExpired);
  ZTraceHelperNoThis(5, "MosHostCreateContext", 363, "[MosHost] Service - MosHostCreateContext Start");
  v8 = ServiceManager_EnsureInstance();
  if ( v8 < 0 )
  {
    v9 = 365;
LABEL_3:
    v10 = ZTraceReportPropagationNoThis(v8, "MosHostCreateContext", v9);
    goto LABEL_7;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)qword_1800185D0 + 112LL))(
         qword_1800185D0,
         0,
         a2,
         (unsigned int)ClientProcessId,
         a3);
  if ( v8 < 0 )
  {
    v9 = 369;
    goto LABEL_3;
  }
  v10 = 0;
  *a4 = ClientProcessId;
LABEL_7:
  ZTraceHelperNoThis(5, "MosHostCreateContext", 376, "[MosHost] Service - MosHostCreateContext End.");
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
    CloseHandle(v11);
  }
  return v10;
}

```

## disassembly

```asm
0x180007350  push    rbx
0x180007352  push    rbp
0x180007353  push    rsi
0x180007354  push    rdi
0x180007355  sub     rsp, 58h
0x180007359  mov     rsi, r9
0x18000735c  mov     rbx, r8
0x18000735f  mov     ebp, edx
0x180007361  call    ?GetClientProcessId@@YAKXZ; GetClientProcessId(void)
0x180007366  lea     r8, ?MosHostCreateContext_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ; void (*)(void)
0x18000736d  mov     edi, eax
0x18000736f  mov     edx, 7530h; unsigned int
0x180007374  lea     rcx, [rsp+78h+Context]; Context
0x180007379  call    ??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))
0x18000737e  lea     r9, aMoshostService_1; "[MosHost] Service - MosHostCreateContex"...
0x180007385  mov     r8d, 16Bh
0x18000738b  lea     rdx, aMoshostcreatec; "MosHostCreateContext"
0x180007392  mov     ecx, 5
0x180007397  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18000739d  call    ?ServiceManager_EnsureInstance@@YAJXZ; ServiceManager_EnsureInstance(void)
0x1800073a2  test    eax, eax
0x1800073a4  jns     short loc_1800073BF
0x1800073a6  mov     r8d, 16Dh
0x1800073ac  lea     rdx, aMoshostcreatec; "MosHostCreateContext"
0x1800073b3  mov     ecx, eax
0x1800073b5  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800073bb  mov     ebx, eax
0x1800073bd  jmp     short loc_1800073F0
0x1800073bf  mov     rcx, cs:qword_1800185D0
0x1800073c6  mov     r9d, edi
0x1800073c9  mov     r8d, ebp
0x1800073cc  mov     [rsp+78h+var_58], rbx
0x1800073d1  xor     edx, edx
0x1800073d3  mov     rax, [rcx]
0x1800073d6  mov     rax, [rax+70h]
0x1800073da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073df  test    eax, eax
0x1800073e1  jns     short loc_1800073EB
0x1800073e3  mov     r8d, 171h
0x1800073e9  jmp     short loc_1800073AC
0x1800073eb  xor     ebx, ebx
0x1800073ed  mov     [rsi], rdi
0x1800073f0  lea     r9, aMoshostService_0; "[MosHost] Service - MosHostCreateContex"...
0x1800073f7  mov     r8d, 178h
0x1800073fd  lea     rdx, aMoshostcreatec; "MosHostCreateContext"
0x180007404  mov     ecx, 5
0x180007409  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18000740f  mov     rcx, [rsp+78h+hEvent]; hEvent
0x180007414  test    rcx, rcx
0x180007417  jz      short loc_18000744A
0x180007419  cmp     [rsp+78h+WaitHandle], 0
0x18000741f  jz      short loc_180007444
0x180007421  call    cs:__imp_SetEvent
0x180007427  mov     rcx, [rsp+78h+WaitHandle]; WaitHandle
0x18000742c  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180007430  call    cs:__imp_UnregisterWaitEx
0x180007436  mov     rcx, [rsp+78h+hEvent]; hObject
0x18000743b  mov     [rsp+78h+WaitHandle], 0
0x180007444  call    cs:__imp_CloseHandle
0x18000744a  mov     eax, ebx
0x18000744c  add     rsp, 58h
0x180007450  pop     rdi
0x180007451  pop     rsi
0x180007452  pop     rbp
0x180007453  pop     rbx
0x180007454  retn
```
