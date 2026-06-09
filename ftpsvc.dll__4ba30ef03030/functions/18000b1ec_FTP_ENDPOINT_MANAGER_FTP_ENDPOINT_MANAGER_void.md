# FTP_ENDPOINT_MANAGER::~FTP_ENDPOINT_MANAGER(void)

- ea: `0x18000b1ec`
- end: `0x18000b280`
- name: `??1FTP_ENDPOINT_MANAGER@@QEAA@XZ`
- size: `148`
- prototype: `void __fastcall(FTP_ENDPOINT_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000b308`

## callees

- `0x18000b1ec`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x18000b204`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000b204`
- `KERNEL32!GetLastError` at `0x18000b217`
- `KERNEL32!GetLastError` at `0x18000b217`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000b260`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000b26a`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000b260`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000b26a`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000b279`
- `iisutil!PuDbgPrint` at `0x18000b248`
- `iisutil!PuDbgPrint` at `0x18000b248`

## string_xrefs

- `0x18000b236`: `Failed to delete timer (%d)\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall FTP_ENDPOINT_MANAGER::~FTP_ENDPOINT_MANAGER(FTP_ENDPOINT_MANAGER *this)
{
  void *v1; // rdx
  DWORD LastError; // eax

  v1 = (void *)*((_QWORD *)this + 11);
  if ( v1 )
  {
    if ( !DeleteTimerQueueTimer(0, v1, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_endpoint_manager\\ftp_endpoint_manager.cxx",
        346,
        "FTP_ENDPOINT_MANAGER::StopPendingConnectionsMonitor",
        "Failed to delete timer (%d)\n",
        LastError);
    }
    *((_QWORD *)this + 11) = 0;
  }
  *(_DWORD *)this = 1835365478;
  CReaderWriterLock3::~CReaderWriterLock3((FTP_ENDPOINT_MANAGER *)((char *)this + 100));
  CReaderWriterLock3::~CReaderWriterLock3((FTP_ENDPOINT_MANAGER *)((char *)this + 80));
  CLKRHashTable::~CLKRHashTable((FTP_ENDPOINT_MANAGER *)((char *)this + 8));
}

```

## disassembly

```asm
0x18000b1ec  push    rbx
0x18000b1ee  sub     rsp, 30h
0x18000b1f2  mov     rdx, [rcx+58h]; Timer
0x18000b1f6  mov     rbx, rcx
0x18000b1f9  test    rdx, rdx
0x18000b1fc  jz      short loc_18000B256
0x18000b1fe  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000b202  xor     ecx, ecx; TimerQueue
0x18000b204  call    cs:__imp_DeleteTimerQueueTimer
0x18000b20a  test    eax, eax
0x18000b20c  jnz     short loc_18000B24E
0x18000b20e  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b215  jz      short loc_18000B24E
0x18000b217  call    cs:__imp_GetLastError
0x18000b21d  mov     rcx, cs:g_pDebug
0x18000b224  lea     r9, aFtpEndpointMan; "FTP_ENDPOINT_MANAGER::StopPendingConnec"...
0x18000b22b  mov     [rsp+38h+var_10], eax
0x18000b22f  lea     rdx, aInetsrvIisIisr_9; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18000b236  lea     rax, aFailedToDelete; "Failed to delete timer (%d)\n"
0x18000b23d  mov     r8d, 15Ah
0x18000b243  mov     [rsp+38h+var_18], rax
0x18000b248  call    cs:__imp_PuDbgPrint
0x18000b24e  mov     qword ptr [rbx+58h], 0
0x18000b256  lea     rcx, [rbx+64h]
0x18000b25a  mov     dword ptr [rbx], 6D657466h
0x18000b260  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000b266  lea     rcx, [rbx+50h]
0x18000b26a  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000b270  lea     rcx, [rbx+8]
0x18000b274  add     rsp, 30h
0x18000b278  pop     rbx
0x18000b279  jmp     cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
```
