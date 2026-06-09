# FwpCleanupTraceThreadResources(void)

- ea: `0x1800939c4`
- end: `0x180093b86`
- name: `?FwpCleanupTraceThreadResources@@YAXXZ`
- size: `450`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18006bbe0`
- `0x180093f30`

## callees

- `0x1800520a4`
- `0x1800525a4`
- `0x1800939c4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180093a3f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180093a3f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180093a31`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180093a31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093a97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093a97`
- `api-ms-win-eventing-obsolete-l1-1-0!RemoveTraceCallback` at `0x1800939d5`
- `api-ms-win-eventing-obsolete-l1-1-0!RemoveTraceCallback` at `0x1800939d5`
- `fwbase!FwFree` at `0x180093acb`
- `fwbase!FwFree` at `0x180093af4`
- `fwbase!FwFree` at `0x180093acb`
- `fwbase!FwFree` at `0x180093af4`

## string_xrefs

- `0x1800939e2`: `FwpCleanupTraceThreadResources`
- `0x180093a06`: `FwpCleanupTraceThreadResources`
- `0x180093a61`: `FwpCleanupTraceThreadResources`
- `0x180093b5f`: `FwpCleanupTraceThreadResources`

## pseudocode

```c
void FwpCleanupTraceThreadResources(void)
{
  __int64 i; // rbx
  struct _TP_IO *v1; // rcx
  __int64 j; // rbx
  __int64 v3; // rcx
  struct _FW_LOG_BUFFER * near *v4; // rdx
  __int64 k; // rcx

  RemoveTraceCallback(&c_MakoInfoEventGuid);
  FwEnterCriticalSectionAndTrace(&g_FwFileLock, "FwpCleanupTraceThreadResources", "g_File");
  g_fStoppingLogger = 1;
  FwLeaveCriticalSectionAndTrace(&g_FwFileLock, "FwpCleanupTraceThreadResources", "g_File");
  for ( i = 0; i != 3; ++i )
  {
    v1 = (struct _TP_IO *)(&g_TPFileIO)[i];
    if ( v1 )
    {
      WaitForThreadpoolIoCallbacks(v1, 0);
      CloseThreadpoolIo((PTP_IO)(&g_TPFileIO)[i]);
      (&g_TPFileIO)[i] = 0;
    }
  }
  FwEnterCriticalSectionAndTrace(&g_FwFileLock, "FwpCleanupTraceThreadResources", "g_File");
  for ( j = 0; j != 3; ++j )
  {
    v3 = *((unsigned int *)&ProfileToFile + j);
    if ( (unsigned int)v3 < 3 )
    {
      if ( (&g_hFile)[v3] != (void * near *)-1LL )
      {
        CloseHandle((&g_hFile)[v3]);
        v3 = *((unsigned int *)&ProfileToFile + j);
        (&g_hFile)[v3] = (void * near *)-1LL;
      }
      v4 = (&g_pCurrentBuffer)[v3];
      *((_DWORD *)&g_dwFileOffset + v3) = 0;
      if ( v4 )
      {
        FwFree(v4);
        v3 = *((unsigned int *)&ProfileToFile + j);
        (&g_pCurrentBuffer)[v3] = 0;
      }
      if ( (&g_pReserveBuffer)[v3] )
      {
        FwFree((&g_pReserveBuffer)[v3]);
        v3 = *((unsigned int *)&ProfileToFile + j);
        (&g_pReserveBuffer)[v3] = 0;
      }
      *((_DWORD *)&g_ulDroppedEventCount + v3) = 0;
      *((_DWORD *)&ProfileToFile + j) = 3;
    }
  }
  for ( k = 0; (unsigned int)k < 3; k = (unsigned int)(k + 1) )
  {
    *((_DWORD *)&FileToProfile + k) = 3;
    *((_BYTE *)&g_fIOPending + k) = 0;
  }
  g_ulKernelEventsLost = 0;
  g_dwNumFiles = 0;
  FwLeaveCriticalSectionAndTrace(&g_FwFileLock, "FwpCleanupTraceThreadResources", "g_File");
}

```

## disassembly

```asm
0x1800939c4  mov     [rsp+arg_0], rbx
0x1800939c9  push    rdi
0x1800939ca  sub     rsp, 20h
0x1800939ce  lea     rcx, ?c_MakoInfoEventGuid@@3U_GUID@@A; pGuid
0x1800939d5  call    cs:__imp_RemoveTraceCallback
0x1800939db  lea     r8, aGFile; "g_File"
0x1800939e2  lea     rdx, aFwpcleanuptrac; "FwpCleanupTraceThreadResources"
0x1800939e9  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwFileLock
0x1800939f0  call    FwEnterCriticalSectionAndTrace
0x1800939f5  lea     r8, aGFile; "g_File"
0x1800939fc  mov     cs:?g_fStoppingLogger@@3HA, 1; int g_fStoppingLogger
0x180093a06  lea     rdx, aFwpcleanuptrac; "FwpCleanupTraceThreadResources"
0x180093a0d  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwFileLock
0x180093a14  call    FwLeaveCriticalSectionAndTrace
0x180093a19  xor     ebx, ebx
0x180093a1b  lea     rdi, __ImageBase
0x180093a22  mov     rcx, rva ?g_TPFileIO@@3PAPEAU_TP_IO@@A[rdi+rbx*8]; pio
0x180093a2a  test    rcx, rcx
0x180093a2d  jz      short loc_180093A51
0x180093a2f  xor     edx, edx; fCancelPendingCallbacks
0x180093a31  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x180093a37  mov     rcx, rva ?g_TPFileIO@@3PAPEAU_TP_IO@@A[rdi+rbx*8]; pio
0x180093a3f  call    cs:__imp_CloseThreadpoolIo
0x180093a45  mov     rva ?g_TPFileIO@@3PAPEAU_TP_IO@@A[rdi+rbx*8], 0; _TP_IO * near * g_TPFileIO ...
0x180093a51  inc     rbx
0x180093a54  cmp     rbx, 3
0x180093a58  jnz     short loc_180093A22
0x180093a5a  lea     r8, aGFile; "g_File"
0x180093a61  lea     rdx, aFwpcleanuptrac; "FwpCleanupTraceThreadResources"
0x180093a68  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwFileLock
0x180093a6f  call    FwEnterCriticalSectionAndTrace
0x180093a74  xor     ebx, ebx
0x180093a76  mov     ecx, dword ptr rva ?ProfileToFile@@3PAKA[rdi+rbx*4]; ulong near * ProfileToFile ...
0x180093a7d  cmp     ecx, 3
0x180093a80  jnb     loc_180093B23
0x180093a86  mov     rdx, rva ?g_hFile@@3PAPEAXA[rdi+rcx*8]; void * near * g_hFile ...
0x180093a8e  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180093a92  jz      short loc_180093AB0
0x180093a94  mov     rcx, rdx; hObject
0x180093a97  call    cs:__imp_CloseHandle
0x180093a9d  mov     ecx, dword ptr rva ?ProfileToFile@@3PAKA[rdi+rbx*4]; ulong near * ProfileToFile ...
0x180093aa4  mov     rva ?g_hFile@@3PAPEAXA[rdi+rcx*8], 0FFFFFFFFFFFFFFFFh; void * near * g_hFile ...
0x180093ab0  mov     rdx, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[rdi+rcx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180093ab8  mov     rva ?g_dwFileOffset@@3PAKA[rdi+rcx*4], 0; ulong near * g_dwFileOffset ...
0x180093ac3  test    rdx, rdx
0x180093ac6  jz      short loc_180093AE4
0x180093ac8  mov     rcx, rdx
0x180093acb  call    cs:__imp_FwFree
0x180093ad1  mov     ecx, dword ptr rva ?ProfileToFile@@3PAKA[rdi+rbx*4]; ulong near * ProfileToFile ...
0x180093ad8  mov     rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[rdi+rcx*8], 0; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x180093ae4  mov     rdx, rva ?g_pReserveBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[rdi+rcx*8]; _FW_LOG_BUFFER * near * g_pReserveBuffer ...
0x180093aec  test    rdx, rdx
0x180093aef  jz      short loc_180093B0D
0x180093af1  mov     rcx, rdx
0x180093af4  call    cs:__imp_FwFree
0x180093afa  mov     ecx, dword ptr rva ?ProfileToFile@@3PAKA[rdi+rbx*4]; ulong near * ProfileToFile ...
0x180093b01  mov     rva ?g_pReserveBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[rdi+rcx*8], 0; _FW_LOG_BUFFER * near * g_pReserveBuffer ...
0x180093b0d  mov     rva ?g_ulDroppedEventCount@@3PAKA[rdi+rcx*4], 0; ulong near * g_ulDroppedEventCount ...
0x180093b18  mov     dword ptr rva ?ProfileToFile@@3PAKA[rdi+rbx*4], 3; ulong near * ProfileToFile ...
0x180093b23  inc     rbx
0x180093b26  cmp     rbx, 3
0x180093b2a  jnz     loc_180093A76
0x180093b30  xor     ecx, ecx
0x180093b32  cmp     ecx, 3
0x180093b35  jnb     short loc_180093B4E
0x180093b37  mov     rva ?FileToProfile@@3PAW4_tag_FW_PROFILE_INDEX@@A[rdi+rcx*4], 3; _tag_FW_PROFILE_INDEX near * FileToProfile ...
0x180093b42  mov     byte ptr [rcx+rdi+12C318h], 0
0x180093b4a  inc     ecx
0x180093b4c  jmp     short loc_180093B32
0x180093b4e  lea     r8, aGFile; "g_File"
0x180093b55  mov     cs:?g_ulKernelEventsLost@@3KA, 0; ulong g_ulKernelEventsLost
0x180093b5f  lea     rdx, aFwpcleanuptrac; "FwpCleanupTraceThreadResources"
0x180093b66  mov     cs:?g_dwNumFiles@@3KA, 0; ulong g_dwNumFiles
0x180093b70  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwFileLock
0x180093b77  mov     rbx, [rsp+28h+arg_0]
0x180093b7c  add     rsp, 20h
0x180093b80  pop     rdi
0x180093b81  jmp     FwLeaveCriticalSectionAndTrace
```
