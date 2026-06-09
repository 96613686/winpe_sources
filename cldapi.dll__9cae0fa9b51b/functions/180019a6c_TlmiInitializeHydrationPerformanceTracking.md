# TlmiInitializeHydrationPerformanceTracking

- ea: `0x180019a6c`
- end: `0x180019be3`
- name: `TlmiInitializeHydrationPerformanceTracking`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012c28`

## callees

- `0x180019a6c`
- `0x18001b518`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019a87`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019a87`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019bd0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019bd0`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180019b52`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180019b83`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180019b52`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180019b83`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180019bae`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180019bae`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019ac0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019ac0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019ae6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019b0e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019ae6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019b0e`

## pseudocode

```c
char TlmiInitializeHydrationPerformanceTracking()
{
  char result; // al

  result = byte_18002AA58;
  if ( !byte_18002AA58 )
  {
    RtlAcquireSRWLockExclusive(&qword_18002AA60);
    if ( !byte_18002AA58 )
    {
      qword_18002AB58 = CreateThread(0, 0, TlmiHydrationPerformanceWorker, 0, 4u, 0);
      if ( qword_18002AB58 )
      {
        hEvent = CreateEventW(0, 0, 0, 0);
        if ( hEvent )
        {
          qword_18002AB50 = CreateEventW(0, 1, 0, 0);
          if ( qword_18002AB50 )
          {
            RtlInitializeGenericTableAvl(
              &stru_18002AA70,
              TlmiHPTableCompare,
              CfpOplockCompletionKeyTableAllocate,
              CfpSyncRootTableFree,
              0);
            RtlInitializeGenericTableAvl(
              &stru_18002AAD8,
              TlmiHPTableCompare,
              CfpOplockCompletionKeyTableAllocate,
              CfpSyncRootTableFree,
              0);
            qword_18002AA68 = &stru_18002AA70;
            dword_18002AB40 = 0;
            byte_18002AA58 = 1;
            ResumeThread(qword_18002AB58);
          }
        }
      }
    }
    if ( !byte_18002AA58 )
      TlmiUninitializeHydrationPerformanceTracking();
    return RtlReleaseSRWLockExclusive(&qword_18002AA60);
  }
  return result;
}

```

## disassembly

```asm
0x180019a6c  push    rbx
0x180019a6e  sub     rsp, 30h
0x180019a72  mov     al, cs:byte_18002AA58
0x180019a78  test    al, al
0x180019a7a  jnz     loc_180019BDC
0x180019a80  lea     rcx, qword_18002AA60
0x180019a87  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180019a8e  nop     dword ptr [rax+rax+00h]
0x180019a93  mov     al, cs:byte_18002AA58
0x180019a99  test    al, al
0x180019a9b  jnz     loc_180019BBA
0x180019aa1  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180019aaa  lea     r8, TlmiHydrationPerformanceWorker; lpStartAddress
0x180019ab1  xor     r9d, r9d; lpParameter
0x180019ab4  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180019abc  xor     edx, edx; dwStackSize
0x180019abe  xor     ecx, ecx; lpThreadAttributes
0x180019ac0  call    cs:__imp_CreateThread
0x180019ac7  nop     dword ptr [rax+rax+00h]
0x180019acc  mov     cs:qword_18002AB58, rax
0x180019ad3  test    rax, rax
0x180019ad6  jz      loc_180019BBA
0x180019adc  xor     r9d, r9d; lpName
0x180019adf  xor     r8d, r8d; bInitialState
0x180019ae2  xor     edx, edx; bManualReset
0x180019ae4  xor     ecx, ecx; lpEventAttributes
0x180019ae6  call    cs:__imp_CreateEventW
0x180019aed  nop     dword ptr [rax+rax+00h]
0x180019af2  mov     cs:hEvent, rax
0x180019af9  test    rax, rax
0x180019afc  jz      loc_180019BBA
0x180019b02  xor     r9d, r9d; lpName
0x180019b05  xor     r8d, r8d; bInitialState
0x180019b08  xor     ecx, ecx; lpEventAttributes
0x180019b0a  lea     edx, [r9+1]; bManualReset
0x180019b0e  call    cs:__imp_CreateEventW
0x180019b15  nop     dword ptr [rax+rax+00h]
0x180019b1a  mov     cs:qword_18002AB50, rax
0x180019b21  test    rax, rax
0x180019b24  jz      loc_180019BBA
0x180019b2a  lea     rbx, stru_18002AA70
0x180019b31  mov     qword ptr [rsp+38h+dwCreationFlags], 0; TableContext
0x180019b3a  mov     rcx, rbx; Table
0x180019b3d  lea     r9, CfpSyncRootTableFree; FreeRoutine
0x180019b44  lea     r8, CfpOplockCompletionKeyTableAllocate; AllocateRoutine
0x180019b4b  lea     rdx, TlmiHPTableCompare; CompareRoutine
0x180019b52  call    cs:__imp_RtlInitializeGenericTableAvl
0x180019b59  nop     dword ptr [rax+rax+00h]
0x180019b5e  lea     r9, CfpSyncRootTableFree; FreeRoutine
0x180019b65  mov     qword ptr [rsp+38h+dwCreationFlags], 0; TableContext
0x180019b6e  lea     r8, CfpOplockCompletionKeyTableAllocate; AllocateRoutine
0x180019b75  lea     rdx, TlmiHPTableCompare; CompareRoutine
0x180019b7c  lea     rcx, stru_18002AAD8; Table
0x180019b83  call    cs:__imp_RtlInitializeGenericTableAvl
0x180019b8a  nop     dword ptr [rax+rax+00h]
0x180019b8f  mov     rcx, cs:qword_18002AB58; hThread
0x180019b96  mov     cs:qword_18002AA68, rbx
0x180019b9d  mov     cs:dword_18002AB40, 0
0x180019ba7  mov     cs:byte_18002AA58, 1
0x180019bae  call    cs:__imp_ResumeThread
0x180019bb5  nop     dword ptr [rax+rax+00h]
0x180019bba  mov     al, cs:byte_18002AA58
0x180019bc0  test    al, al
0x180019bc2  jnz     short loc_180019BC9
0x180019bc4  call    TlmiUninitializeHydrationPerformanceTracking
0x180019bc9  lea     rcx, qword_18002AA60
0x180019bd0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180019bd7  nop     dword ptr [rax+rax+00h]
0x180019bdc  add     rsp, 30h
0x180019be0  pop     rbx
0x180019be1  retn
```
