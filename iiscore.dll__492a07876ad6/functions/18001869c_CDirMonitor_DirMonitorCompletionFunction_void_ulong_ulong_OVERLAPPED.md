# CDirMonitor::DirMonitorCompletionFunction(void *,ulong,ulong,_OVERLAPPED *)

- ea: `0x18001869c`
- end: `0x1800187f4`
- name: `?DirMonitorCompletionFunction@CDirMonitor@@SAXPEAXKKPEAU_OVERLAPPED@@@Z`
- size: `344`
- prototype: `void __fastcall(CDirMonitorEntry *this, unsigned int, unsigned int, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018660`

## callees

- `0x18001869c`
- `0x1800187fc`
- `0x180036748`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800186f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800186f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018729`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018729`
- `iisutil!PuDbgPrint` at `0x18001879e`
- `iisutil!PuDbgPrint` at `0x1800187e3`
- `iisutil!PuDbgPrint` at `0x18001879e`
- `iisutil!PuDbgPrint` at `0x1800187e3`

## string_xrefs

- `0x180018797`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x1800187dc`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x180018785`: `CDirMonitor::DirMonitorCompletionFunction`
- `0x1800187ca`: `CDirMonitor::DirMonitorCompletionFunction`

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
0x18001869c  mov     [rsp+arg_0], rbx
0x1800186a1  mov     [rsp+arg_8], rsi
0x1800186a6  push    rdi
0x1800186a7  sub     rsp, 30h
0x1800186ab  mov     eax, cs:g_dwDebugFlags
0x1800186b1  mov     edi, r8d
0x1800186b4  test    al, 3
0x1800186b6  mov     esi, edx
0x1800186b8  mov     rbx, rcx
0x1800186bb  setnz   r9b
0x1800186bf  bt      eax, 10h
0x1800186c3  setb    al
0x1800186c6  test    al, r9b
0x1800186c9  jnz     loc_180018773
0x1800186cf  lock inc dword ptr [rbx+24h]
0x1800186d3  mov     rcx, rbx; this
0x1800186d6  call    ?IORelease@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::IORelease(void)
0x1800186db  mov     rax, [rbx]
0x1800186de  mov     rcx, rbx
0x1800186e1  mov     rax, [rax+8]
0x1800186e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186ea  mov     eax, [rbx+68h]
0x1800186ed  test    eax, eax
0x1800186ef  jnz     short loc_180018735
0x1800186f1  mov     rcx, [rbx+60h]
0x1800186f5  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800186f9  call    cs:__imp_EnterCriticalSection
0x180018700  nop     dword ptr [rax+rax+00h]
0x180018705  mov     rax, [rbx]
0x180018708  mov     r8d, esi
0x18001870b  mov     edx, edi
0x18001870d  mov     rcx, rbx
0x180018710  mov     rax, [rax+20h]
0x180018714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018719  test    eax, eax
0x18001871b  jnz     loc_1800187AF
0x180018721  mov     rcx, [rbx+60h]
0x180018725  add     rcx, 48h ; 'H'; lpCriticalSection
0x180018729  call    cs:__imp_LeaveCriticalSection
0x180018730  nop     dword ptr [rax+rax+00h]
0x180018735  mov     rax, [rbx]
0x180018738  mov     rcx, rbx
0x18001873b  mov     rax, [rax+10h]
0x18001873f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018744  mov     rcx, rbx; this
0x180018747  call    ?IORelease@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::IORelease(void)
0x18001874c  mov     eax, cs:g_dwDebugFlags
0x180018752  test    al, 3
0x180018754  setnz   cl
0x180018757  bt      eax, 10h
0x18001875b  setb    al
0x18001875e  test    al, cl
0x180018760  jnz     short loc_1800187BC
0x180018762  mov     rbx, [rsp+38h+arg_0]
0x180018767  mov     rsi, [rsp+38h+arg_8]
0x18001876c  add     rsp, 30h
0x180018770  pop     rdi
0x180018771  retn
0x180018773  mov     rcx, cs:g_pDebug
0x18001877a  lea     rax, aCdirmonitorNot; "[CDirMonitor] Notification call-back be"...
0x180018781  mov     [rsp+38h+var_10], edi
0x180018785  lea     r9, aCdirmonitorDir; "CDirMonitor::DirMonitorCompletionFuncti"...
0x18001878c  mov     r8d, 2DEh
0x180018792  mov     [rsp+38h+var_18], rax
0x180018797  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001879e  call    cs:__imp_PuDbgPrint
0x1800187a5  nop     dword ptr [rax+rax+00h]
0x1800187aa  jmp     loc_1800186CF
0x1800187af  mov     rcx, rbx; this
0x1800187b2  call    ?RequestNotification@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::RequestNotification(void)
0x1800187b7  jmp     loc_180018721
0x1800187bc  mov     rcx, cs:g_pDebug
0x1800187c3  lea     rax, aCdirmonitorNot_0; "[CDirMonitor] Notification call-back en"...
0x1800187ca  lea     r9, aCdirmonitorDir; "CDirMonitor::DirMonitorCompletionFuncti"...
0x1800187d1  mov     [rsp+38h+var_18], rax
0x1800187d6  mov     r8d, 314h
0x1800187dc  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800187e3  call    cs:__imp_PuDbgPrint
0x1800187ea  nop     dword ptr [rax+rax+00h]
0x1800187ef  jmp     loc_180018762
```
