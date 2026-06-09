# TerminateOneTimeGlobals(void)

- ea: `0x180026b94`
- end: `0x180026cb1`
- name: `?TerminateOneTimeGlobals@@YAXXZ`
- size: `285`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180015b44`
- `0x18001f110`

## callees

- `0x180008a08`
- `0x180026b94`
- `0x180031010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180026c03`
- `KERNEL32!CloseHandle` at `0x180026c03`
- `KERNEL32!DeleteCriticalSection` at `0x180026be7`
- `KERNEL32!DeleteCriticalSection` at `0x180026c24`
- `KERNEL32!DeleteCriticalSection` at `0x180026be7`
- `KERNEL32!DeleteCriticalSection` at `0x180026c24`
- `MPR!WNetCancelConnection2W` at `0x180026bd1`
- `MPR!WNetCancelConnection2W` at `0x180026bd1`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x180026ba1`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x180026bb2`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x180026ba1`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x180026bb2`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026bc3`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026bc3`
- `IisRTL!??1CLKRHashTable@@QEAA@XZ` at `0x180026c6a`
- `IisRTL!??1CLKRHashTable@@QEAA@XZ` at `0x180026c92`
- `IisRTL!??1CLKRHashTable@@QEAA@XZ` at `0x180026c6a`
- `IisRTL!??1CLKRHashTable@@QEAA@XZ` at `0x180026c92`

## pseudocode

```c
void TerminateOneTimeGlobals(void)
{
  const WCHAR *Str; // rax
  void *v1; // rbx
  void *v2; // rbx

  if ( !STRU::IsEmpty((STRU *)g_struChangeNotificationDirectory) && !STRU::IsEmpty((STRU *)g_struUNCUserName) )
  {
    Str = STRU::QueryStr((STRU *)g_struChangeNotificationDirectory);
    WNetCancelConnection2W(Str, 0, 0);
  }
  if ( dword_180048758 )
  {
    DeleteCriticalSection(&CriticalSection);
    dword_180048758 = 0;
  }
  if ( g_hReadSaveSemaphore )
  {
    CloseHandle(g_hReadSaveSemaphore);
    g_hReadSaveSemaphore = 0;
  }
  if ( g_fcsEditWhileRunningInitialized )
  {
    DeleteCriticalSection(&g_csEditWhileRunning);
    g_fcsEditWhileRunningInitialized = 0;
  }
  if ( g_PointerMapper )
  {
    (**(void (__fastcall ***)(struct CIdToPointerMapper *, __int64))g_PointerMapper)(g_PointerMapper, 1);
    g_PointerMapper = 0;
  }
  v1 = g_phtData;
  if ( g_phtData )
  {
    CLKRHashTable::~CLKRHashTable((CLKRHashTable *)g_phtData);
    operator delete(v1);
    g_phtData = 0;
  }
  v2 = g_phtChildren;
  if ( g_phtChildren )
  {
    CLKRHashTable::~CLKRHashTable((CLKRHashTable *)g_phtChildren);
    operator delete(v2);
    g_phtChildren = 0;
  }
}

```

## disassembly

```asm
0x180026b94  push    rbx
0x180026b96  sub     rsp, 20h
0x180026b9a  lea     rcx, ?g_struChangeNotificationDirectory@@3VSTRU@@A; STRU g_struChangeNotificationDirectory
0x180026ba1  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180026ba7  test    al, al
0x180026ba9  jnz     short loc_180026BD7
0x180026bab  lea     rcx, ?g_struUNCUserName@@3VSTRU@@A; STRU g_struUNCUserName
0x180026bb2  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180026bb8  test    al, al
0x180026bba  jnz     short loc_180026BD7
0x180026bbc  lea     rcx, ?g_struChangeNotificationDirectory@@3VSTRU@@A; STRU g_struChangeNotificationDirectory
0x180026bc3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180026bc9  xor     r8d, r8d; fForce
0x180026bcc  xor     edx, edx; dwFlags
0x180026bce  mov     rcx, rax; lpName
0x180026bd1  call    cs:__imp_WNetCancelConnection2W
0x180026bd7  cmp     cs:dword_180048758, 0
0x180026bde  jz      short loc_180026BF7
0x180026be0  lea     rcx, CriticalSection; lpCriticalSection
0x180026be7  call    cs:__imp_DeleteCriticalSection
0x180026bed  mov     cs:dword_180048758, 0
0x180026bf7  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hObject
0x180026bfe  test    rcx, rcx
0x180026c01  jz      short loc_180026C14
0x180026c03  call    cs:__imp_CloseHandle
0x180026c09  mov     cs:?g_hReadSaveSemaphore@@3PEAXEA, 0; void * g_hReadSaveSemaphore
0x180026c14  cmp     cs:?g_fcsEditWhileRunningInitialized@@3HA, 0; int g_fcsEditWhileRunningInitialized
0x180026c1b  jz      short loc_180026C34
0x180026c1d  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180026c24  call    cs:__imp_DeleteCriticalSection
0x180026c2a  mov     cs:?g_fcsEditWhileRunningInitialized@@3HA, 0; int g_fcsEditWhileRunningInitialized
0x180026c34  mov     rcx, cs:?g_PointerMapper@@3PEAVCIdToPointerMapper@@EA; CIdToPointerMapper * g_PointerMapper
0x180026c3b  test    rcx, rcx
0x180026c3e  jz      short loc_180026C5B
0x180026c40  mov     rax, [rcx]
0x180026c43  mov     edx, 1
0x180026c48  mov     rax, [rax]
0x180026c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c50  mov     cs:?g_PointerMapper@@3PEAVCIdToPointerMapper@@EA, 0; CIdToPointerMapper * g_PointerMapper
0x180026c5b  mov     rbx, cs:?g_phtData@@3PEAVCBaseDataHashTable@@EA; CBaseDataHashTable * g_phtData
0x180026c62  test    rbx, rbx
0x180026c65  jz      short loc_180026C83
0x180026c67  mov     rcx, rbx
0x180026c6a  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180026c70  mov     rcx, rbx; Block
0x180026c73  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026c78  mov     cs:?g_phtData@@3PEAVCBaseDataHashTable@@EA, 0; CBaseDataHashTable * g_phtData
0x180026c83  mov     rbx, cs:?g_phtChildren@@3PEAVCChildNodeHashTable@@EA; CChildNodeHashTable * g_phtChildren
0x180026c8a  test    rbx, rbx
0x180026c8d  jz      short loc_180026CAB
0x180026c8f  mov     rcx, rbx
0x180026c92  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180026c98  mov     rcx, rbx; Block
0x180026c9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026ca0  mov     cs:?g_phtChildren@@3PEAVCChildNodeHashTable@@EA, 0; CChildNodeHashTable * g_phtChildren
0x180026cab  add     rsp, 20h
0x180026caf  pop     rbx
0x180026cb0  retn
```
