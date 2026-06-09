# CertPropFreeListNode

- ea: `0x1800010c4`
- end: `0x18000126c`
- name: `CertPropFreeListNode`
- size: `424`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002690`
- `0x180014fa8`
- `0x180017f30`

## callees

- `0x1800010c4`
- `0x180001274`
- `0x18000132c`
- `0x180014a04`
- `0x180014a30`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000113d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000113d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180001130`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180001130`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001244`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001256`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001244`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001256`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001119`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001119`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800011cc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800011cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800010fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800010fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001167`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001167`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001110`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001110`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001198`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001198`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001179`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800011de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000121e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001179`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800011de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000121e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800011b6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800011b6`

## pseudocode

```c
void __fastcall CertPropFreeListNode(char *lpMem)
{
  char *v1; // rdi
  void *v3; // rcx
  struct _TP_CLEANUP_GROUP *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rdx
  void *v8; // rcx
  __int64 v9; // rcx
  void *v10; // rcx
  void *v11; // r8

  if ( lpMem )
  {
    v1 = lpMem + 24;
    ReaderMonitorStopThread(lpMem + 24);
    if ( *((_DWORD *)lpMem + 140) == 1 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)lpMem + 13);
      v3 = (void *)*((_QWORD *)lpMem + 64);
      if ( v3 )
        SetEvent(v3);
      LeaveCriticalSection((LPCRITICAL_SECTION)lpMem + 13);
    }
    v4 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)lpMem + 63);
    if ( v4 )
    {
      CloseThreadpoolCleanupGroupMembers(v4, 0, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)lpMem + 63));
      *((_QWORD *)lpMem + 63) = 0;
    }
    v5 = (void *)*((_QWORD *)lpMem + 31);
    *((_DWORD *)lpMem + 124) = 0;
    if ( v5 )
      WaitForSingleObject(v5, 0xFFFFFFFF);
    v6 = (void *)*((_QWORD *)lpMem + 31);
    if ( v6 )
    {
      CloseHandle(v6);
      *((_QWORD *)lpMem + 31) = 0;
    }
    v7 = (void *)*((_QWORD *)lpMem + 52);
    if ( v7 && SetThreadToken(0, v7) )
    {
      if ( g_RootsCleanupOption )
        CertPropRemoveRootCertificatesPerReaderList(lpMem, 0);
      RevertToSelf();
    }
    if ( *((_DWORD *)lpMem + 140) == 1 )
      DeleteCriticalSection((LPCRITICAL_SECTION)lpMem + 13);
    v8 = (void *)*((_QWORD *)lpMem + 64);
    if ( v8 )
    {
      CloseHandle(v8);
      *((_QWORD *)lpMem + 64) = 0;
    }
    if ( v1 )
    {
      v9 = *((_QWORD *)v1 + 14);
      if ( v9 )
      {
        I_ReaderListFree(v9);
        *((_QWORD *)v1 + 14) = 0;
      }
    }
    I_ReaderMonitorCleanup(v1);
    v10 = (void *)*((_QWORD *)lpMem + 52);
    if ( v10 )
    {
      CloseHandle(v10);
      *((_QWORD *)lpMem + 52) = 0;
    }
    v11 = (void *)*((_QWORD *)lpMem + 75);
    if ( v11 )
      HeapFree(g_hHeap, 0, v11);
    HeapFree(g_hHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x1800010c4  test    rcx, rcx
0x1800010c7  jz      locret_18000126B
0x1800010cd  mov     [rsp+arg_0], rbx
0x1800010d2  mov     [rsp+arg_8], rsi
0x1800010d7  push    rdi
0x1800010d8  sub     rsp, 20h
0x1800010dc  lea     rdi, [rcx+18h]
0x1800010e0  mov     rbx, rcx
0x1800010e3  mov     rcx, rdi
0x1800010e6  call    ReaderMonitorStopThread
0x1800010eb  cmp     dword ptr [rbx+230h], 1
0x1800010f2  jnz     short loc_18000111F
0x1800010f4  lea     rsi, [rbx+208h]
0x1800010fb  mov     rcx, rsi; lpCriticalSection
0x1800010fe  call    cs:__imp_EnterCriticalSection
0x180001104  mov     rcx, [rbx+200h]; hEvent
0x18000110b  test    rcx, rcx
0x18000110e  jz      short loc_180001116
0x180001110  call    cs:__imp_SetEvent
0x180001116  mov     rcx, rsi; lpCriticalSection
0x180001119  call    cs:__imp_LeaveCriticalSection
0x18000111f  mov     rcx, [rbx+1F8h]; ptpcg
0x180001126  test    rcx, rcx
0x180001129  jz      short loc_18000114E
0x18000112b  xor     r8d, r8d; pvCleanupContext
0x18000112e  xor     edx, edx; fCancelPendingCallbacks
0x180001130  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180001136  mov     rcx, [rbx+1F8h]; ptpcg
0x18000113d  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180001143  mov     qword ptr [rbx+1F8h], 0
0x18000114e  mov     rcx, [rbx+0F8h]; hHandle
0x180001155  mov     dword ptr [rbx+1F0h], 0
0x18000115f  test    rcx, rcx
0x180001162  jz      short loc_18000116D
0x180001164  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180001167  call    cs:__imp_WaitForSingleObject
0x18000116d  mov     rcx, [rbx+0F8h]; hObject
0x180001174  test    rcx, rcx
0x180001177  jz      short loc_18000118A
0x180001179  call    cs:__imp_CloseHandle
0x18000117f  mov     qword ptr [rbx+0F8h], 0
0x18000118a  mov     rdx, [rbx+1A0h]; Token
0x180001191  test    rdx, rdx
0x180001194  jz      short loc_1800011BC
0x180001196  xor     ecx, ecx; Thread
0x180001198  call    cs:__imp_SetThreadToken
0x18000119e  cmp     eax, 1
0x1800011a1  jnz     short loc_1800011BC
0x1800011a3  cmp     cs:g_RootsCleanupOption, 0
0x1800011aa  jz      short loc_1800011B6
0x1800011ac  xor     edx, edx
0x1800011ae  mov     rcx, rbx
0x1800011b1  call    CertPropRemoveRootCertificatesPerReaderList
0x1800011b6  call    cs:__imp_RevertToSelf
0x1800011bc  cmp     dword ptr [rbx+230h], 1
0x1800011c3  jnz     short loc_1800011D2
0x1800011c5  lea     rcx, [rbx+208h]; lpCriticalSection
0x1800011cc  call    cs:__imp_DeleteCriticalSection
0x1800011d2  mov     rcx, [rbx+200h]; hObject
0x1800011d9  test    rcx, rcx
0x1800011dc  jz      short loc_1800011EF
0x1800011de  call    cs:__imp_CloseHandle
0x1800011e4  mov     qword ptr [rbx+200h], 0
0x1800011ef  test    rdi, rdi
0x1800011f2  jz      short loc_18000120A
0x1800011f4  mov     rcx, [rdi+70h]
0x1800011f8  test    rcx, rcx
0x1800011fb  jz      short loc_18000120A
0x1800011fd  call    I_ReaderListFree
0x180001202  mov     qword ptr [rdi+70h], 0
0x18000120a  mov     rcx, rdi
0x18000120d  call    I_ReaderMonitorCleanup
0x180001212  mov     rcx, [rbx+1A0h]; hObject
0x180001219  test    rcx, rcx
0x18000121c  jz      short loc_18000122F
0x18000121e  call    cs:__imp_CloseHandle
0x180001224  mov     qword ptr [rbx+1A0h], 0
0x18000122f  mov     r8, [rbx+258h]; lpMem
0x180001236  test    r8, r8
0x180001239  jz      short loc_18000124A
0x18000123b  mov     rcx, cs:g_hHeap; hHeap
0x180001242  xor     edx, edx; dwFlags
0x180001244  call    cs:__imp_HeapFree
0x18000124a  mov     rcx, cs:g_hHeap; hHeap
0x180001251  mov     r8, rbx; lpMem
0x180001254  xor     edx, edx; dwFlags
0x180001256  call    cs:__imp_HeapFree
0x18000125c  mov     rbx, [rsp+28h+arg_0]
0x180001261  mov     rsi, [rsp+28h+arg_8]
0x180001266  add     rsp, 20h
0x18000126a  pop     rdi
0x18000126b  retn
```
