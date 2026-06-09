# WORK_QUEUE::~WORK_QUEUE(void)

- ea: `0x180040d5c`
- end: `0x180040e4e`
- name: `??1WORK_QUEUE@@AEAA@XZ`
- size: `242`
- prototype: `void __fastcall(WORK_QUEUE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002930`

## callees

- `0x180023758`
- `0x180040d5c`
- `0x180041290`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180040e2f`
- `ntdll!RtlDeleteCriticalSection` at `0x180040e38`
- `ntdll!RtlDeleteCriticalSection` at `0x180040e2f`
- `ntdll!RtlDeleteCriticalSection` at `0x180040e38`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180040d8d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180040d8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040db6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040e13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040db6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040e13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040d7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040e0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040d7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040e0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040dfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040dfa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180040e26`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180040e26`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180040da1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180040da1`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180040ddc`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180040ddc`

## pseudocode

```c
void __fastcall WORK_QUEUE::~WORK_QUEUE(WORK_QUEUE *this)
{
  EVENT *v1; // rdi
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  void *v4; // rcx
  void *v5; // rdx

  v1 = (WORK_QUEUE *)((char *)this + 16);
  if ( *((_DWORD *)this + 7) )
  {
    v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    v4 = *(void **)v1;
    *((_DWORD *)this + 6) = 1;
    ResetEvent(v4);
    v5 = (void *)*((_QWORD *)this + 12);
    if ( v5 && DeleteTimerQueueTimer(0, v5, 0) )
      *((_QWORD *)this + 12) = 0;
    LeaveCriticalSection(v3);
    if ( *(_QWORD *)this )
    {
      if ( !g_fProcessDetach )
      {
        while ( *((_DWORD *)this + 10)
             && PostQueuedCompletionStatus(*(HANDLE *)this, 0, 0, (LPOVERLAPPED)((char *)this + 184)) )
          EVENT::Wait(v1, 0xFFFFFFFF);
      }
      CloseHandle(*(HANDLE *)this);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
    if ( *((_DWORD *)this + 8) )
      FreeLibrary(g_hinst);
    RtlDeleteCriticalSection(v3);
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 144));
  }
  EVENT::~EVENT(v1);
}

```

## disassembly

```asm
0x180040d5c  push    rbx
0x180040d5e  push    rbp
0x180040d5f  push    rsi
0x180040d60  push    rdi
0x180040d61  sub     rsp, 28h
0x180040d65  cmp     dword ptr [rcx+1Ch], 0
0x180040d69  lea     rdi, [rcx+10h]
0x180040d6d  mov     rbx, rcx
0x180040d70  jz      loc_180040E3E
0x180040d76  lea     rbp, [rcx+68h]
0x180040d7a  mov     rcx, rbp; lpCriticalSection
0x180040d7d  call    cs:__imp_EnterCriticalSection
0x180040d83  mov     rcx, [rdi]; hEvent
0x180040d86  mov     dword ptr [rbx+18h], 1
0x180040d8d  call    cs:__imp_ResetEvent
0x180040d93  mov     rdx, [rbx+60h]; Timer
0x180040d97  test    rdx, rdx
0x180040d9a  jz      short loc_180040DB3
0x180040d9c  xor     r8d, r8d; CompletionEvent
0x180040d9f  xor     ecx, ecx; TimerQueue
0x180040da1  call    cs:__imp_DeleteTimerQueueTimer
0x180040da7  test    eax, eax
0x180040da9  jz      short loc_180040DB3
0x180040dab  mov     qword ptr [rbx+60h], 0
0x180040db3  mov     rcx, rbp; lpCriticalSection
0x180040db6  call    cs:__imp_LeaveCriticalSection
0x180040dbc  cmp     qword ptr [rbx], 0
0x180040dc0  jz      short loc_180040E00
0x180040dc2  cmp     cs:?g_fProcessDetach@@3HA, 0; int g_fProcessDetach
0x180040dc9  jnz     short loc_180040DF7
0x180040dcb  jmp     short loc_180040DF1
0x180040dcd  mov     rcx, [rbx]; CompletionPort
0x180040dd0  lea     r9, [rbx+0B8h]; lpOverlapped
0x180040dd7  xor     r8d, r8d; dwCompletionKey
0x180040dda  xor     edx, edx; dwNumberOfBytesTransferred
0x180040ddc  call    cs:__imp_PostQueuedCompletionStatus
0x180040de2  test    eax, eax
0x180040de4  jz      short loc_180040DF7
0x180040de6  or      edx, 0FFFFFFFFh; unsigned int
0x180040de9  mov     rcx, rdi; this
0x180040dec  call    ?Wait@EVENT@@QEAAJK@Z; EVENT::Wait(ulong)
0x180040df1  cmp     dword ptr [rbx+28h], 0
0x180040df5  ja      short loc_180040DCD
0x180040df7  mov     rcx, [rbx]; hObject
0x180040dfa  call    cs:__imp_CloseHandle
0x180040e00  lea     rsi, [rbx+90h]
0x180040e07  mov     rcx, rsi; lpCriticalSection
0x180040e0a  call    cs:__imp_EnterCriticalSection
0x180040e10  mov     rcx, rsi; lpCriticalSection
0x180040e13  call    cs:__imp_LeaveCriticalSection
0x180040e19  cmp     dword ptr [rbx+20h], 0
0x180040e1d  jz      short loc_180040E2C
0x180040e1f  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hLibModule
0x180040e26  call    cs:__imp_FreeLibrary
0x180040e2c  mov     rcx, rbp; CriticalSection
0x180040e2f  call    cs:__imp_RtlDeleteCriticalSection
0x180040e35  mov     rcx, rsi; CriticalSection
0x180040e38  call    cs:__imp_RtlDeleteCriticalSection
0x180040e3e  mov     rcx, rdi; this
0x180040e41  add     rsp, 28h
0x180040e45  pop     rdi
0x180040e46  pop     rsi
0x180040e47  pop     rbp
0x180040e48  pop     rbx
0x180040e49  jmp     ??1EVENT@@QEAA@XZ; EVENT::~EVENT(void)
```
