# DfsRootSynchronizeInit(void)

- ea: `0x14003b214`
- end: `0x14003b3b7`
- name: `?DfsRootSynchronizeInit@@YAKXZ`
- size: `419`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140018e88`

## callees

- `0x140005a94`
- `0x14003b214`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b253`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b2c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b360`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b253`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b2c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b360`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14003b23d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14003b23d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003b275`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003b275`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x14003b2b0`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x14003b2b0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14003b300`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14003b300`

## pseudocode

```c
__int64 DfsRootSynchronizeInit(void)
{
  DWORD LastError; // ebx
  HANDLE v1; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  qword_140071428 = (__int64)&qword_140071420;
  qword_140071420 = (__int64)&qword_140071420;
  LastError = 0;
  SyncCritSectionInit = InitializeCriticalSectionAndSpinCount(&stru_1400713F8, 0xFA0u);
  if ( SyncCritSectionInit || (LastError = GetLastError()) == 0 )
  {
    qword_1400713E8 = CreateEventW(0, 1, 0, 0);
    if ( qword_1400713E8 || (LastError = GetLastError()) == 0 )
    {
      DfsRootSyncHeader = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
      if ( DfsRootSyncHeader || (LastError = GetLastError()) == 0 )
      {
        ThreadId = 0;
        v1 = CreateThread(0, 0, DfsRootSyncThread, 0, 0, &ThreadId);
        if ( v1 )
        {
          qword_1400713F0 = v1;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && pWppControl
            && (pWppControl[7] & 0x20) != 0
            && *((_BYTE *)pWppControl + 25) )
          {
            WPP_SF_D(*((_QWORD *)pWppControl + 2), 10, WPP_cb615555625c386e55e485fc6c3c58a7_Traceguids, ThreadId);
          }
        }
        else
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && pWppControl
            && (pWppControl[7] & 0x20) != 0
            && *((_BYTE *)pWppControl + 25) )
          {
            WPP_SF_D(*((_QWORD *)pWppControl + 2), 11, WPP_cb615555625c386e55e485fc6c3c58a7_Traceguids, LastError);
          }
        }
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x14003b214  push    rbx
0x14003b216  sub     rsp, 30h
0x14003b21a  lea     rax, qword_140071420
0x14003b221  mov     edx, 0FA0h; dwSpinCount
0x14003b226  lea     rcx, stru_1400713F8; lpCriticalSection
0x14003b22d  mov     cs:qword_140071428, rax
0x14003b234  mov     cs:qword_140071420, rax
0x14003b23b  xor     ebx, ebx
0x14003b23d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14003b244  nop     dword ptr [rax+rax+00h]
0x14003b249  mov     cs:?SyncCritSectionInit@@3HA, eax; int SyncCritSectionInit
0x14003b24f  test    eax, eax
0x14003b251  jnz     short loc_14003B269
0x14003b253  call    cs:__imp_GetLastError
0x14003b25a  nop     dword ptr [rax+rax+00h]
0x14003b25f  mov     ebx, eax
0x14003b261  test    eax, eax
0x14003b263  jnz     loc_14003B3AE
0x14003b269  xor     r9d, r9d; lpName
0x14003b26c  xor     r8d, r8d; bInitialState
0x14003b26f  xor     ecx, ecx; lpEventAttributes
0x14003b271  lea     edx, [r9+1]; bManualReset
0x14003b275  call    cs:__imp_CreateEventW
0x14003b27c  nop     dword ptr [rax+rax+00h]
0x14003b281  mov     cs:qword_1400713E8, rax
0x14003b288  test    rax, rax
0x14003b28b  jnz     short loc_14003B2A3
0x14003b28d  call    cs:__imp_GetLastError
0x14003b294  nop     dword ptr [rax+rax+00h]
0x14003b299  mov     ebx, eax
0x14003b29b  test    eax, eax
0x14003b29d  jnz     loc_14003B3AE
0x14003b2a3  mov     r9d, 1F0003h; dwDesiredAccess
0x14003b2a9  xor     r8d, r8d; dwFlags
0x14003b2ac  xor     edx, edx; lpTimerName
0x14003b2ae  xor     ecx, ecx; lpTimerAttributes
0x14003b2b0  call    cs:__imp_CreateWaitableTimerExW
0x14003b2b7  nop     dword ptr [rax+rax+00h]
0x14003b2bc  mov     cs:?DfsRootSyncHeader@@3U_DFS_ROOT_SYNCHRONIZE_HEADER@@A, rax; _DFS_ROOT_SYNCHRONIZE_HEADER DfsRootSyncHeader
0x14003b2c3  test    rax, rax
0x14003b2c6  jnz     short loc_14003B2DE
0x14003b2c8  call    cs:__imp_GetLastError
0x14003b2cf  nop     dword ptr [rax+rax+00h]
0x14003b2d4  mov     ebx, eax
0x14003b2d6  test    eax, eax
0x14003b2d8  jnz     loc_14003B3AE
0x14003b2de  and     [rsp+38h+ThreadId], 0
0x14003b2e3  lea     rax, [rsp+38h+ThreadId]
0x14003b2e8  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14003b2ed  lea     r8, ?DfsRootSyncThread@@YAKPEAX@Z; lpStartAddress
0x14003b2f4  and     [rsp+38h+var_18], 0
0x14003b2f9  xor     r9d, r9d; lpParameter
0x14003b2fc  xor     edx, edx; dwStackSize
0x14003b2fe  xor     ecx, ecx; lpThreadAttributes
0x14003b300  call    cs:__imp_CreateThread
0x14003b307  nop     dword ptr [rax+rax+00h]
0x14003b30c  test    rax, rax
0x14003b30f  jz      short loc_14003B360
0x14003b311  mov     cs:qword_1400713F0, rax
0x14003b318  lea     rax, WPP_GLOBAL_Control
0x14003b31f  cmp     cs:WPP_GLOBAL_Control, rax
0x14003b326  jz      loc_14003B3AE
0x14003b32c  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003b333  test    rcx, rcx
0x14003b336  jz      short loc_14003B3AE
0x14003b338  test    byte ptr [rcx+1Ch], 20h
0x14003b33c  jz      short loc_14003B3AE
0x14003b33e  cmp     byte ptr [rcx+19h], 1
0x14003b342  jb      short loc_14003B3AE
0x14003b344  mov     r9d, [rsp+38h+ThreadId]
0x14003b349  lea     r8, WPP_cb615555625c386e55e485fc6c3c58a7_Traceguids
0x14003b350  mov     rcx, [rcx+10h]
0x14003b354  mov     edx, 0Ah
0x14003b359  call    WPP_SF_D
0x14003b35e  jmp     short loc_14003B3AE
0x14003b360  call    cs:__imp_GetLastError
0x14003b367  nop     dword ptr [rax+rax+00h]
0x14003b36c  mov     ebx, eax
0x14003b36e  lea     rax, WPP_GLOBAL_Control
0x14003b375  cmp     cs:WPP_GLOBAL_Control, rax
0x14003b37c  jz      short loc_14003B3AE
0x14003b37e  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003b385  test    rcx, rcx
0x14003b388  jz      short loc_14003B3AE
0x14003b38a  test    byte ptr [rcx+1Ch], 20h
0x14003b38e  jz      short loc_14003B3AE
0x14003b390  cmp     byte ptr [rcx+19h], 1
0x14003b394  jb      short loc_14003B3AE
0x14003b396  mov     rcx, [rcx+10h]
0x14003b39a  lea     r8, WPP_cb615555625c386e55e485fc6c3c58a7_Traceguids
0x14003b3a1  mov     edx, 0Bh
0x14003b3a6  mov     r9d, ebx
0x14003b3a9  call    WPP_SF_D
0x14003b3ae  mov     eax, ebx
0x14003b3b0  add     rsp, 30h
0x14003b3b4  pop     rbx
0x14003b3b5  retn
```
