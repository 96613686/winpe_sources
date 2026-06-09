# FwpCleanupTraceThreadResources(void)

- ea: `0x180098750`
- end: `0x180098936`
- name: `?FwpCleanupTraceThreadResources@@YAXXZ`
- size: `486`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18006ed38`
- `0x180098d20`

## callees

- `0x180056574`
- `0x180056a14`
- `0x180098750`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800987c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800987c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800987d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800987d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098835`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098835`
- `api-ms-win-eventing-obsolete-l1-1-0!RemoveTraceCallback` at `0x180098761`
- `api-ms-win-eventing-obsolete-l1-1-0!RemoveTraceCallback` at `0x180098761`
- `fwbase!FwFree` at `0x18009886f`
- `fwbase!FwFree` at `0x18009889e`
- `fwbase!FwFree` at `0x18009886f`
- `fwbase!FwFree` at `0x18009889e`

## string_xrefs

- `0x180098774`: `FwpCleanupTraceThreadResources`
- `0x180098798`: `FwpCleanupTraceThreadResources`
- `0x1800987ff`: `FwpCleanupTraceThreadResources`
- `0x18009890f`: `FwpCleanupTraceThreadResources`

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
0x180098750  mov     [rsp+arg_0], rbx
0x180098755  push    rdi
0x180098756  sub     rsp, 20h
0x18009875a  lea     rcx, ?c_MakoInfoEventGuid@@3U_GUID@@A; pGuid
0x180098761  call    cs:__imp_RemoveTraceCallback
0x180098768  nop     dword ptr [rax+rax+00h]
0x18009876d  lea     r8, aGFile; "g_File"
0x180098774  lea     rdx, aFwpcleanuptrac; "FwpCleanupTraceThreadResources"
0x18009877b  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwFileLock
0x180098782  call    FwEnterCriticalSectionAndTrace
0x180098787  lea     r8, aGFile; "g_File"
0x18009878e  mov     cs:?g_fStoppingLogger@@3HA, 1; int g_fStoppingLogger
0x180098798  lea     rdx, aFwpcleanuptrac; "FwpCleanupTraceThreadResources"
0x18009879f  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwFileLock
0x1800987a6  call    FwLeaveCriticalSectionAndTrace
0x1800987ab  xor     ebx, ebx
0x1800987ad  lea     rdi, __ImageBase
0x1800987b4  mov     rcx, rva ?g_TPFileIO@@3PAPEAU_TP_IO@@A[rdi+rbx*8]; pio
0x1800987bc  test    rcx, rcx
0x1800987bf  jz      short loc_1800987EF
0x1800987c1  xor     edx, edx; fCancelPendingCallbacks
0x1800987c3  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800987ca  nop     dword ptr [rax+rax+00h]
0x1800987cf  mov     rcx, rva ?g_TPFileIO@@3PAPEAU_TP_IO@@A[rdi+rbx*8]; pio
0x1800987d7  call    cs:__imp_CloseThreadpoolIo
0x1800987de  nop     dword ptr [rax+rax+00h]
0x1800987e3  mov     rva ?g_TPFileIO@@3PAPEAU_TP_IO@@A[rdi+rbx*8], 0; _TP_IO * near * g_TPFileIO ...
0x1800987ef  inc     rbx
0x1800987f2  cmp     rbx, 3
0x1800987f6  jnz     short loc_1800987B4
0x1800987f8  lea     r8, aGFile; "g_File"
0x1800987ff  lea     rdx, aFwpcleanuptrac; "FwpCleanupTraceThreadResources"
0x180098806  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwFileLock
0x18009880d  call    FwEnterCriticalSectionAndTrace
0x180098812  xor     ebx, ebx
0x180098814  mov     ecx, dword ptr rva ?ProfileToFile@@3PAKA[rdi+rbx*4]; ulong near * ProfileToFile ...
0x18009881b  cmp     ecx, 3
0x18009881e  jnb     loc_1800988D3
0x180098824  mov     rdx, rva ?g_hFile@@3PAPEAXA[rdi+rcx*8]; void * near * g_hFile ...
0x18009882c  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180098830  jz      short loc_180098854
0x180098832  mov     rcx, rdx; hObject
0x180098835  call    cs:__imp_CloseHandle
0x18009883c  nop     dword ptr [rax+rax+00h]
0x180098841  mov     ecx, dword ptr rva ?ProfileToFile@@3PAKA[rdi+rbx*4]; ulong near * ProfileToFile ...
0x180098848  mov     rva ?g_hFile@@3PAPEAXA[rdi+rcx*8], 0FFFFFFFFFFFFFFFFh; void * near * g_hFile ...
0x180098854  mov     rdx, rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[rdi+rcx*8]; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x18009885c  mov     rva ?g_dwFileOffset@@3PAKA[rdi+rcx*4], 0; ulong near * g_dwFileOffset ...
0x180098867  test    rdx, rdx
0x18009886a  jz      short loc_18009888E
0x18009886c  mov     rcx, rdx
0x18009886f  call    cs:__imp_FwFree
0x180098876  nop     dword ptr [rax+rax+00h]
0x18009887b  mov     ecx, dword ptr rva ?ProfileToFile@@3PAKA[rdi+rbx*4]; ulong near * ProfileToFile ...
0x180098882  mov     rva ?g_pCurrentBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[rdi+rcx*8], 0; _FW_LOG_BUFFER * near * g_pCurrentBuffer ...
0x18009888e  mov     rdx, rva ?g_pReserveBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[rdi+rcx*8]; _FW_LOG_BUFFER * near * g_pReserveBuffer ...
0x180098896  test    rdx, rdx
0x180098899  jz      short loc_1800988BD
0x18009889b  mov     rcx, rdx
0x18009889e  call    cs:__imp_FwFree
0x1800988a5  nop     dword ptr [rax+rax+00h]
0x1800988aa  mov     ecx, dword ptr rva ?ProfileToFile@@3PAKA[rdi+rbx*4]; ulong near * ProfileToFile ...
0x1800988b1  mov     rva ?g_pReserveBuffer@@3PAPEAU_FW_LOG_BUFFER@@A[rdi+rcx*8], 0; _FW_LOG_BUFFER * near * g_pReserveBuffer ...
0x1800988bd  mov     rva ?g_ulDroppedEventCount@@3PAKA[rdi+rcx*4], 0; ulong near * g_ulDroppedEventCount ...
0x1800988c8  mov     dword ptr rva ?ProfileToFile@@3PAKA[rdi+rbx*4], 3; ulong near * ProfileToFile ...
0x1800988d3  inc     rbx
0x1800988d6  cmp     rbx, 3
0x1800988da  jnz     loc_180098814
0x1800988e0  xor     ecx, ecx
0x1800988e2  cmp     ecx, 3
0x1800988e5  jnb     short loc_1800988FE
0x1800988e7  mov     rva ?FileToProfile@@3PAW4_tag_FW_PROFILE_INDEX@@A[rdi+rcx*4], 3; _tag_FW_PROFILE_INDEX near * FileToProfile ...
0x1800988f2  mov     byte ptr [rcx+rdi+132550h], 0
0x1800988fa  inc     ecx
0x1800988fc  jmp     short loc_1800988E2
0x1800988fe  lea     r8, aGFile; "g_File"
0x180098905  mov     cs:?g_ulKernelEventsLost@@3KA, 0; ulong g_ulKernelEventsLost
0x18009890f  lea     rdx, aFwpcleanuptrac; "FwpCleanupTraceThreadResources"
0x180098916  mov     cs:?g_dwNumFiles@@3KA, 0; ulong g_dwNumFiles
0x180098920  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwFileLock
0x180098927  mov     rbx, [rsp+28h+arg_0]
0x18009892c  add     rsp, 20h
0x180098930  pop     rdi
0x180098931  jmp     FwLeaveCriticalSectionAndTrace
```
