# CDirMonitor::Monitor(CDirMonitorEntry *,ushort const *,int,ulong,ulong)

- ea: `0x1800332a8`
- end: `0x180033479`
- name: `?Monitor@CDirMonitor@@QEAAHPEAVCDirMonitorEntry@@PEBGHKK@Z`
- size: `465`
- prototype: `__int64 __fastcall(CDirMonitor *this, struct CDirMonitorEntry *, const unsigned __int16 *, __int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016f10`

## callees

- `0x180033208`
- `0x1800332a8`
- `0x180033480`
- `0x180033508`
- `0x180034382`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033425`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033450`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033425`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033450`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033337`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033337`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800333af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033433`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800333af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033433`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033464`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033464`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003339d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003339d`
- `iisutil!PuDbgPrint` at `0x1800332fd`
- `iisutil!PuDbgPrint` at `0x1800332fd`
- `W3TP!ThreadPoolBindIoCompletionCallback` at `0x1800333da`
- `W3TP!ThreadPoolBindIoCompletionCallback` at `0x1800333da`

## string_xrefs

- `0x1800332f6`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`

## pseudocode

```c
__int64 __fastcall CDirMonitor::Monitor(
        CDirMonitor *this,
        struct CDirMonitorEntry *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 v9; // rax
  HLOCAL v10; // rax
  HANDLE FileW; // rax
  void *v12; // rdi
  int inserted; // esi
  void *v15; // rcx
  DWORD v16; // ecx

  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dirmon\\dirmon.cxx",
      569,
      "CDirMonitor::Monitor",
      "[CDirMonitor] Monitoring new CDirMonitorEntry\n");
  if ( !a2 || !a3 )
  {
    v16 = 87;
    goto LABEL_20;
  }
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  *((_DWORD *)a2 + 2) = v9;
  v10 = LocalAlloc(0x40u, 2LL * (unsigned int)(v9 + 1));
  *((_QWORD *)a2 + 2) = v10;
  if ( !v10 )
    goto LABEL_8;
  memcpy_0(v10, a3, 2LL * (unsigned int)(*((_DWORD *)a2 + 2) + 1));
  (*(void (__fastcall **)(struct CDirMonitorEntry *, _QWORD))(*(_QWORD *)a2 + 24LL))(a2, a6);
  FileW = CreateFileW(a3, 1u, 7u, 0, 3u, 0x42000000u, 0);
  v12 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    *((_QWORD *)a2 + 5) = FileW;
    *((_DWORD *)a2 + 13) = 4063;
    *((_DWORD *)a2 + 12) = 1;
    if ( !ThreadPoolBindIoCompletionCallback(FileW, DirMonOverlappedCompletionRoutine, 0) )
    {
      CloseHandle(v12);
      *((_QWORD *)a2 + 5) = -1;
      goto LABEL_10;
    }
    inserted = CDirMonitor::InsertEntry(this, a2);
    if ( !inserted )
    {
      if ( (unsigned int)CDirMonitorEntry::RequestNotification(a2) )
        return 1;
      CDirMonitor::RemoveEntry(this, a2);
      *((_QWORD *)a2 + 5) = -1;
      CloseHandle(v12);
      goto LABEL_10;
    }
    CloseHandle(v12);
    v15 = (void *)*((_QWORD *)a2 + 2);
    *((_QWORD *)a2 + 5) = -1;
    LocalFree(v15);
    *((_QWORD *)a2 + 2) = 0;
    *((_DWORD *)a2 + 2) = 0;
    if ( inserted != 1 )
      return 0;
    v16 = 183;
LABEL_20:
    SetLastError(v16);
    return 0;
  }
LABEL_10:
  LocalFree(*((HLOCAL *)a2 + 2));
  *((_QWORD *)a2 + 2) = 0;
LABEL_8:
  *((_DWORD *)a2 + 2) = 0;
  return 0;
}

```

## disassembly

```asm
0x1800332a8  push    rbx
0x1800332aa  push    rbp
0x1800332ab  push    rsi
0x1800332ac  push    rdi
0x1800332ad  push    r14
0x1800332af  push    r15
0x1800332b1  sub     rsp, 48h
0x1800332b5  mov     eax, cs:g_dwDebugFlags
0x1800332bb  mov     rdi, r8
0x1800332be  test    al, 3
0x1800332c0  mov     rbx, rdx
0x1800332c3  mov     rbp, rcx
0x1800332c6  setnz   r9b
0x1800332ca  bt      eax, 10h
0x1800332ce  setb    al
0x1800332d1  test    al, r9b
0x1800332d4  jz      short loc_180033303
0x1800332d6  mov     rcx, cs:g_pDebug
0x1800332dd  lea     rax, aCdirmonitorMon; "[CDirMonitor] Monitoring new CDirMonito"...
0x1800332e4  lea     r9, aCdirmonitorMon_0; "CDirMonitor::Monitor"
0x1800332eb  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x1800332f0  mov     r8d, 239h
0x1800332f6  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800332fd  call    cs:__imp_PuDbgPrint
0x180033303  xor     r14d, r14d
0x180033306  test    rbx, rbx
0x180033309  jz      loc_18003345F
0x18003330f  test    rdi, rdi
0x180033312  jz      loc_18003345F
0x180033318  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003331c  mov     rax, r15
0x18003331f  inc     rax
0x180033322  cmp     [rdi+rax*2], r14w
0x180033327  jnz     short loc_18003331F
0x180033329  lea     edx, [rax+1]
0x18003332c  mov     [rbx+8], eax
0x18003332f  add     rdx, rdx; uBytes
0x180033332  mov     ecx, 40h ; '@'; uFlags
0x180033337  call    cs:__imp_LocalAlloc
0x18003333d  mov     [rbx+10h], rax
0x180033341  mov     rcx, rax; void *
0x180033344  test    rax, rax
0x180033347  jnz     short loc_180033352
0x180033349  mov     [rbx+8], r14d
0x18003334d  jmp     loc_18003346A
0x180033352  mov     r8d, [rbx+8]
0x180033356  mov     rdx, rdi; Src
0x180033359  inc     r8d
0x18003335c  add     r8, r8; Size
0x18003335f  call    memcpy_0
0x180033364  mov     rax, [rbx]
0x180033367  mov     rcx, rbx
0x18003336a  mov     edx, [rsp+78h+arg_28]
0x180033371  mov     rax, [rax+18h]
0x180033375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003337a  xor     r9d, r9d; lpSecurityAttributes
0x18003337d  mov     [rsp+78h+hTemplateFile], r14; hTemplateFile
0x180033382  mov     [rsp+78h+dwFlagsAndAttributes], 42000000h; dwFlagsAndAttributes
0x18003338a  mov     rcx, rdi; lpFileName
0x18003338d  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180033395  lea     edx, [r9+1]; dwDesiredAccess
0x180033399  lea     r8d, [r9+7]; dwShareMode
0x18003339d  call    cs:__imp_CreateFileW
0x1800333a3  mov     rdi, rax
0x1800333a6  cmp     rax, r15
0x1800333a9  jnz     short loc_1800333BB
0x1800333ab  mov     rcx, [rbx+10h]; hMem
0x1800333af  call    cs:__imp_LocalFree
0x1800333b5  mov     [rbx+10h], r14
0x1800333b9  jmp     short loc_180033349
0x1800333bb  xor     r8d, r8d
0x1800333be  mov     [rbx+28h], rdi
0x1800333c2  lea     rdx, ?DirMonOverlappedCompletionRoutine@@YAXKKPEAU_OVERLAPPED@@@Z; DirMonOverlappedCompletionRoutine(ulong,ulong,_OVERLAPPED *)
0x1800333c9  mov     dword ptr [rbx+34h], 0FDFh
0x1800333d0  mov     rcx, rdi
0x1800333d3  mov     dword ptr [rbx+30h], 1
0x1800333da  call    cs:__imp_?ThreadPoolBindIoCompletionCallback@@YAHPEAXP6AXKKPEAU_OVERLAPPED@@@ZK@Z; ThreadPoolBindIoCompletionCallback(void *,void (*)(ulong,ulong,_OVERLAPPED *),ulong)
0x1800333e0  test    eax, eax
0x1800333e2  jz      short loc_18003344D
0x1800333e4  mov     rdx, rbx
0x1800333e7  mov     rcx, rbp
0x1800333ea  call    ?InsertEntry@CDirMonitor@@QEAA?AW4LK_RETCODE@@PEAVCDirMonitorEntry@@@Z; CDirMonitor::InsertEntry(CDirMonitorEntry *)
0x1800333ef  mov     esi, eax
0x1800333f1  test    eax, eax
0x1800333f3  jnz     short loc_180033422
0x1800333f5  mov     rcx, rbx; this
0x1800333f8  call    ?RequestNotification@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::RequestNotification(void)
0x1800333fd  test    eax, eax
0x1800333ff  jnz     short loc_18003341B
0x180033401  mov     rdx, rbx
0x180033404  mov     rcx, rbp
0x180033407  call    ?RemoveEntry@CDirMonitor@@QEAA?AW4LK_RETCODE@@PEAVCDirMonitorEntry@@@Z; CDirMonitor::RemoveEntry(CDirMonitorEntry *)
0x18003340c  mov     rcx, rdi; hObject
0x18003340f  mov     [rbx+28h], r15
0x180033413  call    cs:__imp_CloseHandle
0x180033419  jmp     short loc_1800333AB
0x18003341b  mov     eax, 1
0x180033420  jmp     short loc_18003346C
0x180033422  mov     rcx, rdi; hObject
0x180033425  call    cs:__imp_CloseHandle
0x18003342b  mov     rcx, [rbx+10h]; hMem
0x18003342f  mov     [rbx+28h], r15
0x180033433  call    cs:__imp_LocalFree
0x180033439  mov     [rbx+10h], r14
0x18003343d  mov     [rbx+8], r14d
0x180033441  cmp     esi, 1
0x180033444  jnz     short loc_18003346A
0x180033446  mov     ecx, 0B7h
0x18003344b  jmp     short loc_180033464
0x18003344d  mov     rcx, rdi; hObject
0x180033450  call    cs:__imp_CloseHandle
0x180033456  mov     [rbx+28h], r15
0x18003345a  jmp     loc_1800333AB
0x18003345f  mov     ecx, 57h ; 'W'; dwErrCode
0x180033464  call    cs:__imp_SetLastError
0x18003346a  xor     eax, eax
0x18003346c  add     rsp, 48h
0x180033470  pop     r15
0x180033472  pop     r14
0x180033474  pop     rdi
0x180033475  pop     rsi
0x180033476  pop     rbp
0x180033477  pop     rbx
0x180033478  retn
```
