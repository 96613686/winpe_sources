# ATL::CComObject<CDetectionAndSharing>::~CComObject<CDetectionAndSharing>(void)

- ea: `0x180001c2c`
- end: `0x180001d59`
- name: `??1?$CComObject@VCDetectionAndSharing@@@ATL@@UEAA@XZ`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001d60`

## callees

- `0x180001c2c`
- `0x180005010`

## import_xrefs

- `msvcrt!free` at `0x180001d15`
- `msvcrt!free` at `0x180001d24`
- `msvcrt!free` at `0x180001d15`
- `msvcrt!free` at `0x180001d24`
- `ADVAPI32!CloseServiceHandle` at `0x180001ceb`
- `ADVAPI32!CloseServiceHandle` at `0x180001ceb`
- `KERNEL32!EnterCriticalSection` at `0x180001c4d`
- `KERNEL32!EnterCriticalSection` at `0x180001c4d`
- `KERNEL32!LeaveCriticalSection` at `0x180001cdc`
- `KERNEL32!LeaveCriticalSection` at `0x180001cdc`
- `KERNEL32!DeleteCriticalSection` at `0x180001d4d`
- `KERNEL32!DeleteCriticalSection` at `0x180001d4d`
- `KERNEL32!CloseHandle` at `0x180001ca5`
- `KERNEL32!CloseHandle` at `0x180001cbd`
- `KERNEL32!CloseHandle` at `0x180001ca5`
- `KERNEL32!CloseHandle` at `0x180001cbd`
- `KERNEL32!SetEvent` at `0x180001c88`
- `KERNEL32!SetEvent` at `0x180001c88`
- `KERNEL32!WaitForSingleObject` at `0x180001c98`
- `KERNEL32!WaitForSingleObject` at `0x180001c98`

## pseudocode

```c
void __fastcall ATL::CComObject<CDetectionAndSharing>::~CComObject<CDetectionAndSharing>(__int64 a1)
{
  SC_HANDLE v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx

  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CDetectionAndSharing>::`vftable';
  EnterCriticalSection(&g_cs);
  if ( !--g_lDtshInstanceCount && g_hFWMonitorThread && g_hFWMonitorEvent )
  {
    g_bFWMonitorCancelled = 1;
    SetEvent(g_hFWMonitorEvent);
    WaitForSingleObject(g_hFWMonitorThread, 0xFFFFFFFF);
    CloseHandle(g_hFWMonitorEvent);
    g_hFWMonitorEvent = 0;
    CloseHandle(g_hFWMonitorThread);
    g_hFWMonitorThread = 0;
    g_bFWMonitorCancelled = 0;
  }
  LeaveCriticalSection(&g_cs);
  v2 = *(SC_HANDLE *)(a1 + 64);
  if ( v2 )
  {
    CloseServiceHandle(v2);
    *(_QWORD *)(a1 + 64) = 0;
  }
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v3 = *(void **)(a1 + 112);
  if ( v3 )
    free(v3);
  v4 = *(void **)(a1 + 80);
  if ( v4 )
    free(v4);
  v5 = *(_QWORD *)(a1 + 72);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( *(_BYTE *)(a1 + 56) )
  {
    *(_BYTE *)(a1 + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
}

```

## disassembly

```asm
0x180001c2c  push    rbx
0x180001c2e  sub     rsp, 20h
0x180001c32  lea     rax, ??_7?$CComObject@VCDetectionAndSharing@@@ATL@@6B@; const ATL::CComObject<CDetectionAndSharing>::`vftable'
0x180001c39  mov     dword ptr [rcx+8], 0C0000001h
0x180001c40  mov     [rcx], rax
0x180001c43  mov     rbx, rcx
0x180001c46  lea     rcx, ?g_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001c4d  call    cs:__imp_EnterCriticalSection
0x180001c53  mov     eax, cs:?g_lDtshInstanceCount@@3JC; long volatile g_lDtshInstanceCount
0x180001c59  dec     eax
0x180001c5b  mov     cs:?g_lDtshInstanceCount@@3JC, eax; long volatile g_lDtshInstanceCount
0x180001c61  mov     eax, cs:?g_lDtshInstanceCount@@3JC; long volatile g_lDtshInstanceCount
0x180001c67  test    eax, eax
0x180001c69  jnz     short loc_180001CD5
0x180001c6b  cmp     cs:?g_hFWMonitorThread@@3PEAXEA, 0; void * g_hFWMonitorThread
0x180001c73  jz      short loc_180001CD5
0x180001c75  mov     rcx, cs:?g_hFWMonitorEvent@@3PEAXEA; hEvent
0x180001c7c  test    rcx, rcx
0x180001c7f  jz      short loc_180001CD5
0x180001c81  mov     cs:?g_bFWMonitorCancelled@@3EA, 1; uchar g_bFWMonitorCancelled
0x180001c88  call    cs:__imp_SetEvent
0x180001c8e  mov     rcx, cs:?g_hFWMonitorThread@@3PEAXEA; hHandle
0x180001c95  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180001c98  call    cs:__imp_WaitForSingleObject
0x180001c9e  mov     rcx, cs:?g_hFWMonitorEvent@@3PEAXEA; hObject
0x180001ca5  call    cs:__imp_CloseHandle
0x180001cab  mov     rcx, cs:?g_hFWMonitorThread@@3PEAXEA; hObject
0x180001cb2  mov     cs:?g_hFWMonitorEvent@@3PEAXEA, 0; void * g_hFWMonitorEvent
0x180001cbd  call    cs:__imp_CloseHandle
0x180001cc3  mov     cs:?g_hFWMonitorThread@@3PEAXEA, 0; void * g_hFWMonitorThread
0x180001cce  mov     cs:?g_bFWMonitorCancelled@@3EA, 0; uchar g_bFWMonitorCancelled
0x180001cd5  lea     rcx, ?g_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001cdc  call    cs:__imp_LeaveCriticalSection
0x180001ce2  mov     rcx, [rbx+40h]; hSCObject
0x180001ce6  test    rcx, rcx
0x180001ce9  jz      short loc_180001CF9
0x180001ceb  call    cs:__imp_CloseServiceHandle
0x180001cf1  mov     qword ptr [rbx+40h], 0
0x180001cf9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001d00  mov     rax, [rcx]
0x180001d03  mov     rax, [rax+10h]
0x180001d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d0c  mov     rcx, [rbx+70h]; Block
0x180001d10  test    rcx, rcx
0x180001d13  jz      short loc_180001D1B
0x180001d15  call    cs:__imp_free
0x180001d1b  mov     rcx, [rbx+50h]; Block
0x180001d1f  test    rcx, rcx
0x180001d22  jz      short loc_180001D2A
0x180001d24  call    cs:__imp_free
0x180001d2a  mov     rcx, [rbx+48h]
0x180001d2e  test    rcx, rcx
0x180001d31  jz      short loc_180001D3F
0x180001d33  mov     rax, [rcx]
0x180001d36  mov     rax, [rax+10h]
0x180001d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d3f  lea     rcx, [rbx+10h]; lpCriticalSection
0x180001d43  cmp     byte ptr [rcx+28h], 0
0x180001d47  jz      short loc_180001D53
0x180001d49  mov     byte ptr [rcx+28h], 0
0x180001d4d  call    cs:__imp_DeleteCriticalSection
0x180001d53  add     rsp, 20h
0x180001d57  pop     rbx
0x180001d58  retn
```
