# MapsStorageSvcOpen

- ea: `0x180008ce0`
- end: `0x180008e1f`
- name: `MapsStorageSvcOpen`
- size: `319`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006e20`
- `0x180008ce0`
- `0x18000a480`
- `0x18000a540`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008de7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008de7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e0a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180008df6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180008df6`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180008d2d`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180008d2d`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008dbc`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008dbc`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008d6d`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008d6d`

## string_xrefs

- `0x180008d1f`: `[MosHost] Service - MapsStorageSvcOpen Start`
- `0x180008d18`: `MapsStorageSvcOpen`

## pseudocode

```c
__int64 __fastcall MapsStorageSvcOpen(__int64 a1, unsigned int a2, __int64 a3, _QWORD *a4)
{
  __int64 ClientProcessId; // rsi
  int v8; // r8d
  int v9; // ecx
  char v10; // di
  int v11; // eax
  int v12; // r8d
  int v13; // eax
  unsigned int v14; // ebx
  HANDLE v15; // rcx
  _BYTE Context[16]; // [rsp+30h] [rbp-58h] BYREF
  HANDLE WaitHandle; // [rsp+40h] [rbp-48h]
  HANDLE hEvent; // [rsp+48h] [rbp-40h]

  ClientProcessId = (unsigned int)GetClientProcessId();
  ScopedWatchdogTimer::ScopedWatchdogTimer(
    Context,
    0x7530u,
    (void (*)(void))ScopedWatchdogHandlers::MapsStorageServiceOpen_CrashOnTimerExpired);
  ZTraceHelperNoThis(5, "MapsStorageSvcOpen", 38, "[MosHost] Service - MapsStorageSvcOpen Start");
  if ( !a4 )
  {
    v8 = 40;
    v9 = -2147467261;
LABEL_11:
    v10 = 0;
    v13 = ZTraceReportOriginationNoThis(v9, "MapsStorageSvcOpen", v8);
    goto LABEL_12;
  }
  *a4 = 0;
  if ( _InterlockedCompareExchange(&dword_1800185C8, ClientProcessId, 0) )
  {
    v8 = 46;
    v9 = -2147024864;
    goto LABEL_11;
  }
  v10 = 1;
  v11 = ServiceManager_EnsureInstance();
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)qword_1800185D0 + 112LL))(
            qword_1800185D0,
            4,
            a2,
            (unsigned int)ClientProcessId,
            a3);
    if ( v11 >= 0 )
    {
      v14 = 0;
      *a4 = ClientProcessId;
      goto LABEL_15;
    }
    v12 = 52;
  }
  else
  {
    v12 = 48;
  }
  v13 = ZTraceReportPropagationNoThis(v11, "MapsStorageSvcOpen", v12);
LABEL_12:
  v14 = v13;
  if ( v13 < 0 && v10 )
    _InterlockedExchange(&dword_1800185C8, 0);
LABEL_15:
  v15 = hEvent;
  if ( hEvent )
  {
    if ( WaitHandle )
    {
      SetEvent(hEvent);
      UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      v15 = hEvent;
      WaitHandle = 0;
    }
    CloseHandle(v15);
  }
  return v14;
}

```

## disassembly

```asm
0x180008ce0  push    rbx
0x180008ce2  push    rbp
0x180008ce3  push    rsi
0x180008ce4  push    rdi
0x180008ce5  push    r12
0x180008ce7  push    r14
0x180008ce9  sub     rsp, 58h
0x180008ced  mov     r14, r9
0x180008cf0  mov     rbx, r8
0x180008cf3  mov     ebp, edx
0x180008cf5  call    ?GetClientProcessId@@YAKXZ; GetClientProcessId(void)
0x180008cfa  lea     r8, ?MapsStorageServiceOpen_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ; void (*)(void)
0x180008d01  mov     esi, eax
0x180008d03  mov     edx, 7530h; unsigned int
0x180008d08  lea     rcx, [rsp+88h+Context]; Context
0x180008d0d  call    ??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))
0x180008d12  mov     r8d, 26h ; '&'
0x180008d18  lea     r12, aMapsstoragesvc_4; "MapsStorageSvcOpen"
0x180008d1f  lea     r9, aMoshostService_4; "[MosHost] Service - MapsStorageSvcOpen "...
0x180008d26  mov     rdx, r12
0x180008d29  lea     ecx, [r8-21h]
0x180008d2d  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180008d33  test    r14, r14
0x180008d36  jnz     short loc_180008D43
0x180008d38  lea     r8d, [r14+28h]
0x180008d3c  mov     ecx, 80004003h
0x180008d41  jmp     short loc_180008DB6
0x180008d43  mov     qword ptr [r14], 0
0x180008d4a  xor     eax, eax
0x180008d4c  lock cmpxchg cs:dword_1800185C8, esi
0x180008d54  jnz     short loc_180008DAB
0x180008d56  mov     dil, 1
0x180008d59  call    ?ServiceManager_EnsureInstance@@YAJXZ; ServiceManager_EnsureInstance(void)
0x180008d5e  test    eax, eax
0x180008d60  jns     short loc_180008D75
0x180008d62  mov     r8d, 30h ; '0'
0x180008d68  mov     rdx, r12
0x180008d6b  mov     ecx, eax
0x180008d6d  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008d73  jmp     short loc_180008DC2
0x180008d75  mov     rcx, cs:qword_1800185D0
0x180008d7c  mov     r9d, esi
0x180008d7f  mov     r8d, ebp
0x180008d82  mov     [rsp+88h+var_68], rbx
0x180008d87  mov     edx, 4
0x180008d8c  mov     rax, [rcx]
0x180008d8f  mov     rax, [rax+70h]
0x180008d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d98  test    eax, eax
0x180008d9a  jns     short loc_180008DA4
0x180008d9c  mov     r8d, 34h ; '4'
0x180008da2  jmp     short loc_180008D68
0x180008da4  xor     ebx, ebx
0x180008da6  mov     [r14], rsi
0x180008da9  jmp     short loc_180008DD5
0x180008dab  mov     r8d, 2Eh ; '.'
0x180008db1  mov     ecx, 80070020h
0x180008db6  xor     dil, dil
0x180008db9  mov     rdx, r12
0x180008dbc  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180008dc2  mov     ebx, eax
0x180008dc4  test    eax, eax
0x180008dc6  jns     short loc_180008DD5
0x180008dc8  test    dil, dil
0x180008dcb  jz      short loc_180008DD5
0x180008dcd  xor     eax, eax
0x180008dcf  xchg    eax, cs:dword_1800185C8
0x180008dd5  mov     rcx, [rsp+88h+hEvent]; hEvent
0x180008dda  test    rcx, rcx
0x180008ddd  jz      short loc_180008E10
0x180008ddf  cmp     [rsp+88h+WaitHandle], 0
0x180008de5  jz      short loc_180008E0A
0x180008de7  call    cs:__imp_SetEvent
0x180008ded  mov     rcx, [rsp+88h+WaitHandle]; WaitHandle
0x180008df2  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180008df6  call    cs:__imp_UnregisterWaitEx
0x180008dfc  mov     rcx, [rsp+88h+hEvent]; hObject
0x180008e01  mov     [rsp+88h+WaitHandle], 0
0x180008e0a  call    cs:__imp_CloseHandle
0x180008e10  mov     eax, ebx
0x180008e12  add     rsp, 58h
0x180008e16  pop     r14
0x180008e18  pop     r12
0x180008e1a  pop     rdi
0x180008e1b  pop     rsi
0x180008e1c  pop     rbp
0x180008e1d  pop     rbx
0x180008e1e  retn
```
