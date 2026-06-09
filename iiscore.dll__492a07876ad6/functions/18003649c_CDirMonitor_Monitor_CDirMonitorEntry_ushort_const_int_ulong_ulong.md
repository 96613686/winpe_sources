# CDirMonitor::Monitor(CDirMonitorEntry *,ushort const *,int,ulong,ulong)

- ea: `0x18003649c`
- end: `0x1800366ad`
- name: `?Monitor@CDirMonitor@@QEAAHPEAVCDirMonitorEntry@@PEBGHKK@Z`
- size: `529`
- prototype: `__int64 __fastcall(CDirMonitor *this, struct CDirMonitorEntry *, const unsigned __int16 *, __int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018280`

## callees

- `0x1800363f0`
- `0x18003649c`
- `0x1800366b4`
- `0x180036748`
- `0x180037722`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036625`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036640`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036677`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036625`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036640`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036677`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036531`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036531`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800365b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036654`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800365b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036654`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036691`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036691`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003659d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003659d`
- `iisutil!PuDbgPrint` at `0x1800364f1`
- `iisutil!PuDbgPrint` at `0x1800364f1`
- `W3TP!ThreadPoolBindIoCompletionCallback` at `0x1800365e6`
- `W3TP!ThreadPoolBindIoCompletionCallback` at `0x1800365e6`

## string_xrefs

- `0x1800364ea`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`

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
0x18003649c  push    rbx
0x18003649e  push    rbp
0x18003649f  push    rsi
0x1800364a0  push    rdi
0x1800364a1  push    r14
0x1800364a3  push    r15
0x1800364a5  sub     rsp, 48h
0x1800364a9  mov     eax, cs:g_dwDebugFlags
0x1800364af  mov     rdi, r8
0x1800364b2  test    al, 3
0x1800364b4  mov     rbx, rdx
0x1800364b7  mov     rbp, rcx
0x1800364ba  setnz   r9b
0x1800364be  bt      eax, 10h
0x1800364c2  setb    al
0x1800364c5  test    al, r9b
0x1800364c8  jz      short loc_1800364FD
0x1800364ca  mov     rcx, cs:g_pDebug
0x1800364d1  lea     rax, aCdirmonitorMon; "[CDirMonitor] Monitoring new CDirMonito"...
0x1800364d8  lea     r9, aCdirmonitorMon_0; "CDirMonitor::Monitor"
0x1800364df  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x1800364e4  mov     r8d, 239h
0x1800364ea  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800364f1  call    cs:__imp_PuDbgPrint
0x1800364f8  nop     dword ptr [rax+rax+00h]
0x1800364fd  xor     r14d, r14d
0x180036500  test    rbx, rbx
0x180036503  jz      loc_18003668C
0x180036509  test    rdi, rdi
0x18003650c  jz      loc_18003668C
0x180036512  or      r15, 0FFFFFFFFFFFFFFFFh
0x180036516  mov     rax, r15
0x180036519  inc     rax
0x18003651c  cmp     [rdi+rax*2], r14w
0x180036521  jnz     short loc_180036519
0x180036523  lea     edx, [rax+1]
0x180036526  mov     [rbx+8], eax
0x180036529  add     rdx, rdx; uBytes
0x18003652c  mov     ecx, 40h ; '@'; uFlags
0x180036531  call    cs:__imp_LocalAlloc
0x180036538  nop     dword ptr [rax+rax+00h]
0x18003653d  mov     [rbx+10h], rax
0x180036541  mov     rcx, rax; void *
0x180036544  test    rax, rax
0x180036547  jnz     short loc_180036552
0x180036549  mov     [rbx+8], r14d
0x18003654d  jmp     loc_18003669D
0x180036552  mov     r8d, [rbx+8]
0x180036556  mov     rdx, rdi; Src
0x180036559  inc     r8d
0x18003655c  add     r8, r8; Size
0x18003655f  call    memcpy_0
0x180036564  mov     rax, [rbx]
0x180036567  mov     rcx, rbx
0x18003656a  mov     edx, [rsp+78h+arg_28]
0x180036571  mov     rax, [rax+18h]
0x180036575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003657a  xor     r9d, r9d; lpSecurityAttributes
0x18003657d  mov     [rsp+78h+hTemplateFile], r14; hTemplateFile
0x180036582  mov     [rsp+78h+dwFlagsAndAttributes], 42000000h; dwFlagsAndAttributes
0x18003658a  mov     rcx, rdi; lpFileName
0x18003658d  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180036595  lea     edx, [r9+1]; dwDesiredAccess
0x180036599  lea     r8d, [r9+7]; dwShareMode
0x18003659d  call    cs:__imp_CreateFileW
0x1800365a4  nop     dword ptr [rax+rax+00h]
0x1800365a9  mov     rdi, rax
0x1800365ac  cmp     rax, r15
0x1800365af  jnz     short loc_1800365C7
0x1800365b1  mov     rcx, [rbx+10h]; hMem
0x1800365b5  call    cs:__imp_LocalFree
0x1800365bc  nop     dword ptr [rax+rax+00h]
0x1800365c1  mov     [rbx+10h], r14
0x1800365c5  jmp     short loc_180036549
0x1800365c7  xor     r8d, r8d
0x1800365ca  mov     [rbx+28h], rdi
0x1800365ce  lea     rdx, ?DirMonOverlappedCompletionRoutine@@YAXKKPEAU_OVERLAPPED@@@Z; DirMonOverlappedCompletionRoutine(ulong,ulong,_OVERLAPPED *)
0x1800365d5  mov     dword ptr [rbx+34h], 0FDFh
0x1800365dc  mov     rcx, rdi
0x1800365df  mov     dword ptr [rbx+30h], 1
0x1800365e6  call    cs:__imp_?ThreadPoolBindIoCompletionCallback@@YAHPEAXP6AXKKPEAU_OVERLAPPED@@@ZK@Z; ThreadPoolBindIoCompletionCallback(void *,void (*)(ulong,ulong,_OVERLAPPED *),ulong)
0x1800365ed  nop     dword ptr [rax+rax+00h]
0x1800365f2  test    eax, eax
0x1800365f4  jz      short loc_180036674
0x1800365f6  mov     rdx, rbx
0x1800365f9  mov     rcx, rbp
0x1800365fc  call    ?InsertEntry@CDirMonitor@@QEAA?AW4LK_RETCODE@@PEAVCDirMonitorEntry@@@Z; CDirMonitor::InsertEntry(CDirMonitorEntry *)
0x180036601  mov     esi, eax
0x180036603  test    eax, eax
0x180036605  jnz     short loc_18003663D
0x180036607  mov     rcx, rbx; this
0x18003660a  call    ?RequestNotification@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::RequestNotification(void)
0x18003660f  test    eax, eax
0x180036611  jnz     short loc_180036636
0x180036613  mov     rdx, rbx
0x180036616  mov     rcx, rbp
0x180036619  call    ?RemoveEntry@CDirMonitor@@QEAA?AW4LK_RETCODE@@PEAVCDirMonitorEntry@@@Z; CDirMonitor::RemoveEntry(CDirMonitorEntry *)
0x18003661e  mov     rcx, rdi; hObject
0x180036621  mov     [rbx+28h], r15
0x180036625  call    cs:__imp_CloseHandle
0x18003662c  nop     dword ptr [rax+rax+00h]
0x180036631  jmp     loc_1800365B1
0x180036636  mov     eax, 1
0x18003663b  jmp     short loc_18003669F
0x18003663d  mov     rcx, rdi; hObject
0x180036640  call    cs:__imp_CloseHandle
0x180036647  nop     dword ptr [rax+rax+00h]
0x18003664c  mov     rcx, [rbx+10h]; hMem
0x180036650  mov     [rbx+28h], r15
0x180036654  call    cs:__imp_LocalFree
0x18003665b  nop     dword ptr [rax+rax+00h]
0x180036660  mov     [rbx+10h], r14
0x180036664  mov     [rbx+8], r14d
0x180036668  cmp     esi, 1
0x18003666b  jnz     short loc_18003669D
0x18003666d  mov     ecx, 0B7h
0x180036672  jmp     short loc_180036691
0x180036674  mov     rcx, rdi; hObject
0x180036677  call    cs:__imp_CloseHandle
0x18003667e  nop     dword ptr [rax+rax+00h]
0x180036683  mov     [rbx+28h], r15
0x180036687  jmp     loc_1800365B1
0x18003668c  mov     ecx, 57h ; 'W'; dwErrCode
0x180036691  call    cs:__imp_SetLastError
0x180036698  nop     dword ptr [rax+rax+00h]
0x18003669d  xor     eax, eax
0x18003669f  add     rsp, 48h
0x1800366a3  pop     r15
0x1800366a5  pop     r14
0x1800366a7  pop     rdi
0x1800366a8  pop     rsi
0x1800366a9  pop     rbp
0x1800366aa  pop     rbx
0x1800366ab  retn
```
