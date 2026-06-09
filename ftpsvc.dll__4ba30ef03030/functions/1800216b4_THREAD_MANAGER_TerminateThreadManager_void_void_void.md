# THREAD_MANAGER::TerminateThreadManager(void (*)(void *),void *)

- ea: `0x1800216b4`
- end: `0x18002187e`
- name: `?TerminateThreadManager@THREAD_MANAGER@@QEAAXP6AXPEAX@Z0@Z`
- size: `458`
- prototype: `void __fastcall(THREAD_MANAGER *__hidden this, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180021fec`

## callees

- `0x180001250`
- `0x180020348`
- `0x1800216b4`
- `0x180022098`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800216f2`
- `KERNEL32!SetEvent` at `0x1800216f2`
- `KERNEL32!LeaveCriticalSection` at `0x1800216e8`
- `KERNEL32!LeaveCriticalSection` at `0x1800216e8`
- `KERNEL32!EnterCriticalSection` at `0x1800216d7`
- `KERNEL32!EnterCriticalSection` at `0x1800216d7`
- `KERNEL32!Sleep` at `0x180021782`
- `KERNEL32!Sleep` at `0x180021782`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18002171b`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18002171b`
- `KERNEL32!DeleteCriticalSection` at `0x180021859`
- `KERNEL32!DeleteCriticalSection` at `0x180021859`
- `KERNEL32!HeapFree` at `0x18002180c`
- `KERNEL32!HeapFree` at `0x180021844`
- `KERNEL32!HeapFree` at `0x18002180c`
- `KERNEL32!HeapFree` at `0x180021844`
- `KERNEL32!CloseHandle` at `0x1800217cd`
- `KERNEL32!CloseHandle` at `0x1800217e4`
- `KERNEL32!CloseHandle` at `0x1800217cd`
- `KERNEL32!CloseHandle` at `0x1800217e4`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x180021829`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x180021829`
- `KERNEL32!GetProcessHeap` at `0x1800217fe`
- `KERNEL32!GetProcessHeap` at `0x180021836`
- `KERNEL32!GetProcessHeap` at `0x1800217fe`
- `KERNEL32!GetProcessHeap` at `0x180021836`
- `iisutil!PuDbgPrint` at `0x180021777`
- `iisutil!PuDbgPrint` at `0x1800217be`
- `iisutil!PuDbgPrint` at `0x180021777`
- `iisutil!PuDbgPrint` at `0x1800217be`

## string_xrefs

- `0x180021770`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x1800217b7`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x180021757`: `W3TP: Waiting for threads to drain, sleep 1000\n`
- `0x18002175e`: `THREAD_MANAGER::DrainThreads`
- `0x1800217a5`: `THREAD_MANAGER::DrainThreads`
- `0x18002179e`: `W3TP: All threads drained\n`

## pseudocode

```c
void __fastcall THREAD_MANAGER::TerminateThreadManager(THREAD_MANAGER *this, void (*a2)(void *), void *a3)
{
  int i; // ebx
  void *v6; // rdx
  _DWORD *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v12; // rcx
  void *v13; // rbx
  HANDLE v14; // rax

  if ( !*((_DWORD *)this + 12) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *((_DWORD *)this + 12) = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    SetEvent(*((HANDLE *)this + 12));
    for ( i = *((_DWORD *)this + 19); i >= 0; --i )
      THREAD_POOL_DATA::ThreadPoolStop(a3);
    v6 = (void *)*((_QWORD *)this + 7);
    if ( v6 )
    {
      DeleteTimerQueueTimer(0, v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      v7 = (_DWORD *)*((_QWORD *)this + 8);
      *((_QWORD *)this + 7) = 0;
      if ( v7 )
      {
        *v7 = 2017546324;
        operator delete(v7);
        *((_QWORD *)this + 8) = 0;
      }
    }
    while ( *((int *)this + 19) > 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
          1766,
          "THREAD_MANAGER::DrainThreads",
          "W3TP: Waiting for threads to drain, sleep 1000\n");
      Sleep(0x3E8u);
    }
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
        1770,
        "THREAD_MANAGER::DrainThreads",
        "W3TP: All threads drained\n");
  }
  v8 = (void *)*((_QWORD *)this + 12);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 12) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 11);
  if ( v9 )
  {
    CloseHandle(v9);
    *((_QWORD *)this + 11) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 19);
  if ( v10 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
    *((_QWORD *)this + 19) = 0;
  }
  v12 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)*((_QWORD *)this + 21);
  if ( v12 )
  {
    DeleteProcThreadAttributeList(v12);
    v13 = (void *)*((_QWORD *)this + 21);
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v13);
    *((_QWORD *)this + 21) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  THREAD_MANAGER::~THREAD_MANAGER(this);
  operator delete(this);
}

```

## disassembly

```asm
0x1800216b4  mov     [rsp+arg_0], rbx
0x1800216b9  mov     [rsp+arg_8], rsi
0x1800216be  push    rdi
0x1800216bf  sub     rsp, 30h
0x1800216c3  cmp     dword ptr [rcx+30h], 0
0x1800216c7  mov     rsi, r8
0x1800216ca  mov     rdi, rcx
0x1800216cd  jnz     loc_1800217C4
0x1800216d3  add     rcx, 8; lpCriticalSection
0x1800216d7  call    cs:__imp_EnterCriticalSection
0x1800216dd  lea     rcx, [rdi+8]; lpCriticalSection
0x1800216e1  mov     dword ptr [rdi+30h], 1
0x1800216e8  call    cs:__imp_LeaveCriticalSection
0x1800216ee  mov     rcx, [rdi+60h]; hEvent
0x1800216f2  call    cs:__imp_SetEvent
0x1800216f8  mov     ebx, [rdi+4Ch]
0x1800216fb  test    ebx, ebx
0x1800216fd  js      short loc_18002170C
0x1800216ff  mov     rcx, rsi; void *
0x180021702  call    ?ThreadPoolStop@THREAD_POOL_DATA@@SAXPEAX@Z; THREAD_POOL_DATA::ThreadPoolStop(void *)
0x180021707  sub     ebx, 1
0x18002170a  jns     short loc_1800216FF
0x18002170c  mov     rdx, [rdi+38h]; Timer
0x180021710  test    rdx, rdx
0x180021713  jz      short loc_180021788
0x180021715  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180021719  xor     ecx, ecx; TimerQueue
0x18002171b  call    cs:__imp_DeleteTimerQueueTimer
0x180021721  mov     rcx, [rdi+40h]; Block
0x180021725  mov     qword ptr [rdi+38h], 0
0x18002172d  test    rcx, rcx
0x180021730  jz      short loc_180021788
0x180021732  mov     dword ptr [rcx], 78415054h
0x180021738  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002173d  mov     qword ptr [rdi+40h], 0
0x180021745  jmp     short loc_180021788
0x180021747  test    byte ptr cs:g_dwDebugFlags, 3
0x18002174e  jz      short loc_18002177D
0x180021750  mov     rcx, cs:g_pDebug
0x180021757  lea     rax, aW3tpWaitingFor; "W3TP: Waiting for threads to drain, sle"...
0x18002175e  lea     r9, aThreadManagerD; "THREAD_MANAGER::DrainThreads"
0x180021765  mov     [rsp+38h+var_18], rax
0x18002176a  mov     r8d, 6E6h
0x180021770  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180021777  call    cs:__imp_PuDbgPrint
0x18002177d  mov     ecx, 3E8h; dwMilliseconds
0x180021782  call    cs:__imp_Sleep
0x180021788  cmp     dword ptr [rdi+4Ch], 0
0x18002178c  jg      short loc_180021747
0x18002178e  test    byte ptr cs:g_dwDebugFlags, 3
0x180021795  jz      short loc_1800217C4
0x180021797  mov     rcx, cs:g_pDebug
0x18002179e  lea     rax, aW3tpAllThreads; "W3TP: All threads drained\n"
0x1800217a5  lea     r9, aThreadManagerD; "THREAD_MANAGER::DrainThreads"
0x1800217ac  mov     [rsp+38h+var_18], rax
0x1800217b1  mov     r8d, 6EAh
0x1800217b7  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800217be  call    cs:__imp_PuDbgPrint
0x1800217c4  mov     rcx, [rdi+60h]; hObject
0x1800217c8  test    rcx, rcx
0x1800217cb  jz      short loc_1800217DB
0x1800217cd  call    cs:__imp_CloseHandle
0x1800217d3  mov     qword ptr [rdi+60h], 0
0x1800217db  mov     rcx, [rdi+58h]; hObject
0x1800217df  test    rcx, rcx
0x1800217e2  jz      short loc_1800217F2
0x1800217e4  call    cs:__imp_CloseHandle
0x1800217ea  mov     qword ptr [rdi+58h], 0
0x1800217f2  mov     rbx, [rdi+98h]
0x1800217f9  test    rbx, rbx
0x1800217fc  jz      short loc_18002181D
0x1800217fe  call    cs:__imp_GetProcessHeap
0x180021804  mov     r8, rbx; lpMem
0x180021807  xor     edx, edx; dwFlags
0x180021809  mov     rcx, rax; hHeap
0x18002180c  call    cs:__imp_HeapFree
0x180021812  mov     qword ptr [rdi+98h], 0
0x18002181d  mov     rcx, [rdi+0A8h]; lpAttributeList
0x180021824  test    rcx, rcx
0x180021827  jz      short loc_180021855
0x180021829  call    cs:__imp_DeleteProcThreadAttributeList
0x18002182f  mov     rbx, [rdi+0A8h]
0x180021836  call    cs:__imp_GetProcessHeap
0x18002183c  mov     r8, rbx; lpMem
0x18002183f  xor     edx, edx; dwFlags
0x180021841  mov     rcx, rax; hHeap
0x180021844  call    cs:__imp_HeapFree
0x18002184a  mov     qword ptr [rdi+0A8h], 0
0x180021855  lea     rcx, [rdi+8]; lpCriticalSection
0x180021859  call    cs:__imp_DeleteCriticalSection
0x18002185f  mov     rcx, rdi; this
0x180021862  call    ??1THREAD_MANAGER@@AEAA@XZ; THREAD_MANAGER::~THREAD_MANAGER(void)
0x180021867  mov     rcx, rdi; Block
0x18002186a  mov     rbx, [rsp+38h+arg_0]
0x18002186f  mov     rsi, [rsp+38h+arg_8]
0x180021874  add     rsp, 30h
0x180021878  pop     rdi
0x180021879  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
