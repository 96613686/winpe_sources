# COfflineFilesService::~COfflineFilesService(void)

- ea: `0x180024e8c`
- end: `0x180024f87`
- name: `??1COfflineFilesService@@EEAA@XZ`
- size: `251`
- prototype: `void __fastcall(COfflineFilesService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180024e50`

## callees

- `0x180024e8c`
- `0x18004fef4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024f0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024f0e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024f4a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024f4a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180024f1e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180024f1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024f28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024f28`

## pseudocode

```c
void __fastcall COfflineFilesService::~COfflineFilesService(COfflineFilesService *this)
{
  __int64 v2; // rcx
  __int64 v3; // rbx

  *(_QWORD *)this = &COfflineFilesService::`vftable'{for `CMonitoredObject'};
  *((_QWORD *)this + 2) = &COfflineFilesService::`vftable'{for `IOfflineFilesService2'};
  if ( *((_DWORD *)this + 18) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v2 = *((_QWORD *)this + 10);
  if ( v2 )
  {
    *((_QWORD *)this + 10) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  *(_QWORD *)this = &CMonitoredObject::`vftable';
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_35f7768de0a037dc6f6ad00626564c6d_Traceguids, this);
  if ( *((_DWORD *)this + 3) )
  {
    v3 = g_invsemTasksInProgress;
    if ( g_invsemTasksInProgress )
    {
      _InterlockedIncrement((volatile signed __int32 *)(g_invsemTasksInProgress + 8));
      EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 32));
      if ( (*(_DWORD *)(v3 + 24))-- == 1 )
        SetEvent(*(HANDLE *)(v3 + 16));
      LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 32));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 8), 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
    }
  }
}

```

## disassembly

```asm
0x180024e8c  mov     [rsp+arg_8], rbx
0x180024e91  push    rdi
0x180024e92  sub     rsp, 20h
0x180024e96  lea     rax, ??_7COfflineFilesService@@6BCMonitoredObject@@@; const COfflineFilesService::`vftable'{for `CMonitoredObject'}
0x180024e9d  xor     edi, edi
0x180024e9f  mov     rbx, rcx
0x180024ea2  mov     [rcx], rax
0x180024ea5  lea     rax, ??_7COfflineFilesService@@6BIOfflineFilesService2@@@; const COfflineFilesService::`vftable'{for `IOfflineFilesService2'}
0x180024eac  mov     [rcx+10h], rax
0x180024eb0  cmp     [rcx+48h], edi
0x180024eb3  jnz     loc_180024F46
0x180024eb9  mov     rcx, [rbx+50h]
0x180024ebd  test    rcx, rcx
0x180024ec0  jz      short loc_180024ED2
0x180024ec2  mov     [rbx+50h], rdi
0x180024ec6  mov     rax, [rcx]
0x180024ec9  mov     rax, [rax+10h]
0x180024ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ed2  lea     rax, ??_7CMonitoredObject@@6B@; const CMonitoredObject::`vftable'
0x180024ed9  mov     [rbx], rax
0x180024edc  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ee3  lea     rax, WPP_GLOBAL_Control
0x180024eea  cmp     rcx, rax
0x180024eed  jz      short loc_180024EF5
0x180024eef  test    byte ptr [rcx+1Ch], 8
0x180024ef3  jnz     short loc_180024F6A
0x180024ef5  cmp     [rbx+0Ch], edi
0x180024ef8  jz      short loc_180024F3B
0x180024efa  mov     rbx, cs:?g_invsemTasksInProgress@@3VCInvSemaphore@@A; CInvSemaphore g_invsemTasksInProgress
0x180024f01  test    rbx, rbx
0x180024f04  jz      short loc_180024F3B
0x180024f06  lock inc dword ptr [rbx+8]
0x180024f0a  lea     rcx, [rbx+20h]; lpCriticalSection
0x180024f0e  call    cs:__imp_EnterCriticalSection
0x180024f14  sub     dword ptr [rbx+18h], 1
0x180024f18  jnz     short loc_180024F24
0x180024f1a  mov     rcx, [rbx+10h]; hEvent
0x180024f1e  call    cs:__imp_SetEvent
0x180024f24  lea     rcx, [rbx+20h]; lpCriticalSection
0x180024f28  call    cs:__imp_LeaveCriticalSection
0x180024f2e  or      eax, 0FFFFFFFFh
0x180024f31  lock xadd [rbx+8], eax
0x180024f36  cmp     eax, 1
0x180024f39  jz      short loc_180024F55
0x180024f3b  mov     rbx, [rsp+28h+arg_8]
0x180024f40  add     rsp, 20h
0x180024f44  pop     rdi
0x180024f45  retn
0x180024f46  add     rcx, 20h ; ' '; lpCriticalSection
0x180024f4a  call    cs:__imp_DeleteCriticalSection
0x180024f50  jmp     loc_180024EB9
0x180024f55  mov     rax, [rbx]
0x180024f58  mov     edx, 1
0x180024f5d  mov     rcx, rbx
0x180024f60  mov     rax, [rax]
0x180024f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f68  jmp     short loc_180024F3B
0x180024f6a  mov     rcx, [rcx+10h]
0x180024f6e  lea     r8, WPP_35f7768de0a037dc6f6ad00626564c6d_Traceguids
0x180024f75  mov     edx, 10h
0x180024f7a  mov     r9, rbx
0x180024f7d  call    WPP_SF_q
0x180024f82  jmp     loc_180024EF5
```
