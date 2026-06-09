# CMDCOM::ComMDShutdown(void)

- ea: `0x180019f40`
- end: `0x18001a046`
- name: `?ComMDShutdown@CMDCOM@@UEAAJXZ`
- size: `262`
- prototype: `__int64 __fastcall(CMDCOM *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180019f40`
- `0x180031010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001a004`
- `KERNEL32!WaitForSingleObject` at `0x18001a004`
- `KERNEL32!Sleep` at `0x180019fb3`
- `KERNEL32!Sleep` at `0x180019fb3`
- `KERNEL32!ReleaseSemaphore` at `0x18001a028`
- `KERNEL32!ReleaseSemaphore` at `0x18001a028`
- `KERNEL32!LeaveCriticalSection` at `0x180019f80`
- `KERNEL32!LeaveCriticalSection` at `0x180019f80`
- `KERNEL32!EnterCriticalSection` at `0x180019f54`
- `KERNEL32!EnterCriticalSection` at `0x180019f54`
- `IisRTL!RemoveWorkItem` at `0x180019f8c`
- `IisRTL!RemoveWorkItem` at `0x180019f98`
- `IisRTL!RemoveWorkItem` at `0x180019f8c`
- `IisRTL!RemoveWorkItem` at `0x180019f98`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a035`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a035`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180019fd4`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180019fd4`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDShutdown(struct _RTL_CRITICAL_SECTION *this)
{
  unsigned int DebugInfo; // edi
  unsigned int OwningThread; // esi
  int i; // edi
  unsigned int v5; // ebx

  DebugInfo = 0;
  OwningThread = 0;
  EnterCriticalSection(this + 2);
  if ( this[1].RecursionCount )
  {
    this[1].RecursionCount = 0;
    if ( LODWORD(this[1].OwningThread) )
    {
      OwningThread = (unsigned int)this[1].OwningThread;
      LODWORD(this[1].OwningThread) = 0;
    }
  }
  if ( LODWORD(this[3].DebugInfo) )
  {
    DebugInfo = (unsigned int)this[3].DebugInfo;
    LODWORD(this[3].DebugInfo) = 0;
  }
  LeaveCriticalSection(this + 2);
  if ( OwningThread )
    RemoveWorkItem(OwningThread);
  if ( DebugInfo )
    RemoveWorkItem(DebugInfo);
  for ( i = 0; _InterlockedIncrement(&this[1].LockCount) > 5 && i < 7; ++i )
  {
    _InterlockedDecrement(&this[1].LockCount);
    Sleep(0x3E8u);
  }
  _InterlockedDecrement(&this[1].LockCount);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
  v5 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, _QWORD))this->DebugInfo[6].ProcessLocksList.Flink)(
         this,
         0);
  if ( g_dwInitialized )
    WaitForSingleObject(g_hReadSaveSemaphore, 0xFFFFFFFF);
  g_bSaveDisallowed = 1;
  if ( g_dwInitialized )
    ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
  return v5;
}

```

## disassembly

```asm
0x180019f40  push    rbx
0x180019f42  push    rbp
0x180019f43  push    rsi
0x180019f44  push    rdi
0x180019f45  sub     rsp, 28h
0x180019f49  mov     rbx, rcx
0x180019f4c  xor     edi, edi
0x180019f4e  add     rcx, 50h ; 'P'; lpCriticalSection
0x180019f52  xor     esi, esi
0x180019f54  call    cs:__imp_EnterCriticalSection
0x180019f5a  cmp     [rbx+34h], esi
0x180019f5d  jz      short loc_180019F6D
0x180019f5f  mov     [rbx+34h], esi
0x180019f62  cmp     [rbx+38h], esi
0x180019f65  jz      short loc_180019F6D
0x180019f67  mov     esi, [rbx+38h]
0x180019f6a  mov     [rbx+38h], edi
0x180019f6d  cmp     [rbx+78h], edi
0x180019f70  jz      short loc_180019F7C
0x180019f72  mov     edi, [rbx+78h]
0x180019f75  mov     dword ptr [rbx+78h], 0
0x180019f7c  lea     rcx, [rbx+50h]; lpCriticalSection
0x180019f80  call    cs:__imp_LeaveCriticalSection
0x180019f86  test    esi, esi
0x180019f88  jz      short loc_180019F92
0x180019f8a  mov     ecx, esi
0x180019f8c  call    cs:__imp_?RemoveWorkItem@@YAHK@Z; RemoveWorkItem(ulong)
0x180019f92  test    edi, edi
0x180019f94  jz      short loc_180019F9E
0x180019f96  mov     ecx, edi
0x180019f98  call    cs:__imp_?RemoveWorkItem@@YAHK@Z; RemoveWorkItem(ulong)
0x180019f9e  xor     edi, edi
0x180019fa0  lea     esi, [rdi+1]
0x180019fa3  jmp     short loc_180019FBB
0x180019fa5  cmp     edi, 7
0x180019fa8  jge     short loc_180019FC9
0x180019faa  lock dec dword ptr [rbx+30h]
0x180019fae  mov     ecx, 3E8h; dwMilliseconds
0x180019fb3  call    cs:__imp_Sleep
0x180019fb9  add     edi, esi
0x180019fbb  mov     eax, esi
0x180019fbd  lock xadd [rbx+30h], eax
0x180019fc2  add     eax, esi
0x180019fc4  cmp     eax, 5
0x180019fc7  jg      short loc_180019FA5
0x180019fc9  lock dec dword ptr [rbx+30h]
0x180019fcd  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180019fd4  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180019fda  mov     rax, [rbx]
0x180019fdd  xor     edx, edx
0x180019fdf  mov     rcx, rbx
0x180019fe2  mov     rax, [rax+130h]
0x180019fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fee  mov     ecx, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180019ff4  mov     ebx, eax
0x180019ff6  test    ecx, ecx
0x180019ff8  jz      short loc_18001A00A
0x180019ffa  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hHandle
0x18001a001  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001a004  call    cs:__imp_WaitForSingleObject
0x18001a00a  mov     r8d, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001a011  mov     cs:?g_bSaveDisallowed@@3HA, esi; int g_bSaveDisallowed
0x18001a017  test    r8d, r8d
0x18001a01a  jz      short loc_18001A02E
0x18001a01c  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hSemaphore
0x18001a023  xor     r8d, r8d; lpPreviousCount
0x18001a026  mov     edx, esi; lReleaseCount
0x18001a028  call    cs:__imp_ReleaseSemaphore
0x18001a02e  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001a035  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001a03b  mov     eax, ebx
0x18001a03d  add     rsp, 28h
0x18001a041  pop     rdi
0x18001a042  pop     rsi
0x18001a043  pop     rbp
0x18001a044  pop     rbx
0x18001a045  retn
```
