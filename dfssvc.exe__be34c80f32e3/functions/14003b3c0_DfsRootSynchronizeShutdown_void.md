# DfsRootSynchronizeShutdown(void)

- ea: `0x14003b3c0`
- end: `0x14003b4bd`
- name: `?DfsRootSynchronizeShutdown@@YAXXZ`
- size: `253`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140019b88`

## callees

- `0x1400011c4`
- `0x14003b3c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003b3f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003b3f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003b448`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003b448`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14003b466`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14003b466`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003b3d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003b3d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b3e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b484`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b4a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b3e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b484`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b4a3`

## pseudocode

```c
void DfsRootSynchronizeShutdown(void)
{
  __int64 v0; // rcx
  __int64 v1; // rax

  WaitForSingleObject(qword_1400713F0, 0xFFFFFFFF);
  CloseHandle(qword_1400713F0);
  EnterCriticalSection(&stru_1400713F8);
  while ( 1 )
  {
    v0 = qword_140071420;
    if ( (__int64 *)qword_140071420 == &qword_140071420 )
      break;
    if ( *(__int64 **)(qword_140071420 + 8) != &qword_140071420
      || (v1 = *(_QWORD *)qword_140071420, *(_QWORD *)(*(_QWORD *)qword_140071420 + 8LL) != qword_140071420) )
    {
      __fastfail(3u);
    }
    qword_140071420 = *(_QWORD *)qword_140071420;
    *(_QWORD *)(v1 + 8) = &qword_140071420;
    operator delete((void *)(v0 - 16));
  }
  LeaveCriticalSection(&stru_1400713F8);
  if ( SyncCritSectionInit == 1 )
  {
    DeleteCriticalSection(&stru_1400713F8);
    SyncCritSectionInit = 0;
  }
  if ( DfsRootSyncHeader )
  {
    CloseHandle(DfsRootSyncHeader);
    DfsRootSyncHeader = 0;
  }
  if ( qword_1400713E8 )
  {
    CloseHandle(qword_1400713E8);
    qword_1400713E8 = 0;
  }
}

```

## disassembly

```asm
0x14003b3c0  push    rbx
0x14003b3c2  sub     rsp, 20h
0x14003b3c6  mov     rcx, cs:qword_1400713F0; hHandle
0x14003b3cd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14003b3d0  call    cs:__imp_WaitForSingleObject
0x14003b3d7  nop     dword ptr [rax+rax+00h]
0x14003b3dc  mov     rcx, cs:qword_1400713F0; hObject
0x14003b3e3  call    cs:__imp_CloseHandle
0x14003b3ea  nop     dword ptr [rax+rax+00h]
0x14003b3ef  lea     rcx, stru_1400713F8; lpCriticalSection
0x14003b3f6  call    cs:__imp_EnterCriticalSection
0x14003b3fd  nop     dword ptr [rax+rax+00h]
0x14003b402  lea     rbx, qword_140071420
0x14003b409  mov     rcx, cs:qword_140071420
0x14003b410  cmp     rcx, rbx
0x14003b413  jz      short loc_14003B441
0x14003b415  cmp     [rcx+8], rbx
0x14003b419  jnz     short loc_14003B43A
0x14003b41b  mov     rax, [rcx]
0x14003b41e  cmp     [rax+8], rcx
0x14003b422  jnz     short loc_14003B43A
0x14003b424  mov     cs:qword_140071420, rax
0x14003b42b  add     rcx, 0FFFFFFFFFFFFFFF0h; Block
0x14003b42f  mov     [rax+8], rbx
0x14003b433  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003b438  jmp     short loc_14003B409
0x14003b43a  mov     ecx, 3
0x14003b43f  int     29h; Win8: RtlFailFast(ecx)
0x14003b441  lea     rcx, stru_1400713F8; lpCriticalSection
0x14003b448  call    cs:__imp_LeaveCriticalSection
0x14003b44f  nop     dword ptr [rax+rax+00h]
0x14003b454  xor     ebx, ebx
0x14003b456  cmp     cs:?SyncCritSectionInit@@3HA, 1; int SyncCritSectionInit
0x14003b45d  jnz     short loc_14003B478
0x14003b45f  lea     rcx, stru_1400713F8; lpCriticalSection
0x14003b466  call    cs:__imp_DeleteCriticalSection
0x14003b46d  nop     dword ptr [rax+rax+00h]
0x14003b472  mov     cs:?SyncCritSectionInit@@3HA, ebx; int SyncCritSectionInit
0x14003b478  mov     rcx, cs:?DfsRootSyncHeader@@3U_DFS_ROOT_SYNCHRONIZE_HEADER@@A; hObject
0x14003b47f  test    rcx, rcx
0x14003b482  jz      short loc_14003B497
0x14003b484  call    cs:__imp_CloseHandle
0x14003b48b  nop     dword ptr [rax+rax+00h]
0x14003b490  mov     cs:?DfsRootSyncHeader@@3U_DFS_ROOT_SYNCHRONIZE_HEADER@@A, rbx; _DFS_ROOT_SYNCHRONIZE_HEADER DfsRootSyncHeader
0x14003b497  mov     rcx, cs:qword_1400713E8; hObject
0x14003b49e  test    rcx, rcx
0x14003b4a1  jz      short loc_14003B4B6
0x14003b4a3  call    cs:__imp_CloseHandle
0x14003b4aa  nop     dword ptr [rax+rax+00h]
0x14003b4af  mov     cs:qword_1400713E8, rbx
0x14003b4b6  add     rsp, 20h
0x14003b4ba  pop     rbx
0x14003b4bb  retn
```
