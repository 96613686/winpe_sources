# CDirMonitor::DirMonitorCompletionFunction(void *,ulong,ulong,_OVERLAPPED *)

- ea: `0x1800172b4`
- end: `0x1800173f3`
- name: `?DirMonitorCompletionFunction@CDirMonitor@@SAXPEAXKKPEAU_OVERLAPPED@@@Z`
- size: `319`
- prototype: `void __fastcall(CDirMonitorEntry *this, unsigned int, unsigned int, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017280`

## callees

- `0x1800172b4`
- `0x1800173fc`
- `0x180033508`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017311`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017311`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001733b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001733b`
- `iisutil!PuDbgPrint` at `0x1800173a9`
- `iisutil!PuDbgPrint` at `0x1800173e8`
- `iisutil!PuDbgPrint` at `0x1800173a9`
- `iisutil!PuDbgPrint` at `0x1800173e8`

## string_xrefs

- `0x1800173a2`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x1800173e1`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x180017390`: `CDirMonitor::DirMonitorCompletionFunction`
- `0x1800173cf`: `CDirMonitor::DirMonitorCompletionFunction`

## pseudocode

```c
void __fastcall CDirMonitor::DirMonitorCompletionFunction(
        CDirMonitorEntry *this,
        unsigned int a2,
        unsigned int a3,
        struct _OVERLAPPED *a4)
{
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dirmon\\dirmon.cxx",
      734,
      "CDirMonitor::DirMonitorCompletionFunction",
      "[CDirMonitor] Notification call-back begining. Status %d\n",
      a3);
  _InterlockedIncrement((volatile signed __int32 *)this + 9);
  CDirMonitorEntry::IORelease(this);
  (*(void (__fastcall **)(CDirMonitorEntry *))(*(_QWORD *)this + 8LL))(this);
  if ( !*((_DWORD *)this + 26) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 12) + 72LL));
    if ( (*(unsigned int (__fastcall **)(CDirMonitorEntry *, _QWORD, _QWORD))(*(_QWORD *)this + 32LL))(this, a3, a2) )
      CDirMonitorEntry::RequestNotification(this);
    LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 12) + 72LL));
  }
  (*(void (__fastcall **)(CDirMonitorEntry *))(*(_QWORD *)this + 16LL))(this);
  CDirMonitorEntry::IORelease(this);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dirmon\\dirmon.cxx",
      788,
      "CDirMonitor::DirMonitorCompletionFunction",
      "[CDirMonitor] Notification call-back ending\n");
}

```

## disassembly

```asm
0x1800172b4  mov     [rsp+arg_0], rbx
0x1800172b9  mov     [rsp+arg_8], rsi
0x1800172be  push    rdi
0x1800172bf  sub     rsp, 30h
0x1800172c3  mov     eax, cs:g_dwDebugFlags
0x1800172c9  mov     edi, r8d
0x1800172cc  test    al, 3
0x1800172ce  mov     esi, edx
0x1800172d0  mov     rbx, rcx
0x1800172d3  setnz   r9b
0x1800172d7  bt      eax, 10h
0x1800172db  setb    al
0x1800172de  test    al, r9b
0x1800172e1  jnz     loc_18001737E
0x1800172e7  lock inc dword ptr [rbx+24h]
0x1800172eb  mov     rcx, rbx; this
0x1800172ee  call    ?IORelease@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::IORelease(void)
0x1800172f3  mov     rax, [rbx]
0x1800172f6  mov     rcx, rbx
0x1800172f9  mov     rax, [rax+8]
0x1800172fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017302  mov     eax, [rbx+68h]
0x180017305  test    eax, eax
0x180017307  jnz     short loc_180017341
0x180017309  mov     rcx, [rbx+60h]
0x18001730d  add     rcx, 48h ; 'H'; lpCriticalSection
0x180017311  call    cs:__imp_EnterCriticalSection
0x180017317  mov     rax, [rbx]
0x18001731a  mov     r8d, esi
0x18001731d  mov     edx, edi
0x18001731f  mov     rcx, rbx
0x180017322  mov     rax, [rax+20h]
0x180017326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001732b  test    eax, eax
0x18001732d  jnz     loc_1800173B4
0x180017333  mov     rcx, [rbx+60h]
0x180017337  add     rcx, 48h ; 'H'; lpCriticalSection
0x18001733b  call    cs:__imp_LeaveCriticalSection
0x180017341  mov     rax, [rbx]
0x180017344  mov     rcx, rbx
0x180017347  mov     rax, [rax+10h]
0x18001734b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017350  mov     rcx, rbx; this
0x180017353  call    ?IORelease@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::IORelease(void)
0x180017358  mov     eax, cs:g_dwDebugFlags
0x18001735e  test    al, 3
0x180017360  setnz   cl
0x180017363  bt      eax, 10h
0x180017367  setb    al
0x18001736a  test    al, cl
0x18001736c  jnz     short loc_1800173C1
0x18001736e  mov     rbx, [rsp+38h+arg_0]
0x180017373  mov     rsi, [rsp+38h+arg_8]
0x180017378  add     rsp, 30h
0x18001737c  pop     rdi
0x18001737d  retn
0x18001737e  mov     rcx, cs:g_pDebug
0x180017385  lea     rax, aCdirmonitorNot; "[CDirMonitor] Notification call-back be"...
0x18001738c  mov     [rsp+38h+var_10], edi
0x180017390  lea     r9, aCdirmonitorDir; "CDirMonitor::DirMonitorCompletionFuncti"...
0x180017397  mov     r8d, 2DEh
0x18001739d  mov     [rsp+38h+var_18], rax
0x1800173a2  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800173a9  call    cs:__imp_PuDbgPrint
0x1800173af  jmp     loc_1800172E7
0x1800173b4  mov     rcx, rbx; this
0x1800173b7  call    ?RequestNotification@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::RequestNotification(void)
0x1800173bc  jmp     loc_180017333
0x1800173c1  mov     rcx, cs:g_pDebug
0x1800173c8  lea     rax, aCdirmonitorNot_0; "[CDirMonitor] Notification call-back en"...
0x1800173cf  lea     r9, aCdirmonitorDir; "CDirMonitor::DirMonitorCompletionFuncti"...
0x1800173d6  mov     [rsp+38h+var_18], rax
0x1800173db  mov     r8d, 314h
0x1800173e1  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800173e8  call    cs:__imp_PuDbgPrint
0x1800173ee  jmp     loc_18001736E
```
