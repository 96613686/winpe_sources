# TlmiInitializeRunawayHydrationDetection

- ea: `0x180019d54`
- end: `0x180019ea5`
- name: `TlmiInitializeRunawayHydrationDetection`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012c28`

## callees

- `0x180019d54`
- `0x18001b5bc`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019d6d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180019d6d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019e93`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019e93`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180019dac`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180019dac`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180019e71`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180019e71`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019e36`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019e36`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019e55`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019e55`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019dd7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019dff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019dd7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019dff`

## pseudocode

```c
char TlmiInitializeRunawayHydrationDetection()
{
  char result; // al

  result = byte_18002A9B0;
  if ( !byte_18002A9B0 )
  {
    RtlAcquireSRWLockExclusive(&qword_18002A9B8);
    if ( !byte_18002A9B0 )
    {
      RtlInitializeGenericTableAvl(
        &stru_18002A9C8,
        TlmiRHAppTableCompare,
        CfpOplockCompletionKeyTableAllocate,
        TlmiRHAppTableFree,
        0);
      *((_QWORD *)&xmmword_18002AA30 + 1) = &xmmword_18002AA30;
      *(_QWORD *)&xmmword_18002AA30 = &xmmword_18002AA30;
      qword_18002AA40 = CreateEventW(0, 0, 0, 0);
      if ( qword_18002AA40 )
      {
        qword_18002AA48 = CreateEventW(0, 1, 0, 0);
        if ( qword_18002AA48 )
        {
          qword_18002AA50 = CreateThread(0, 0, TlmiRunawayHydrationWorker, 0, 4u, 0);
          if ( qword_18002AA50 )
          {
            byte_18002A9B0 = 1;
            qword_18002A9C0 = GetTickCount();
            ResumeThread(qword_18002AA50);
          }
        }
      }
    }
    if ( !byte_18002A9B0 )
      TlmiUninitializeRunawayHydrationDetection();
    return RtlReleaseSRWLockExclusive(&qword_18002A9B8);
  }
  return result;
}

```

## disassembly

```asm
0x180019d54  sub     rsp, 38h
0x180019d58  mov     al, cs:byte_18002A9B0
0x180019d5e  test    al, al
0x180019d60  jnz     loc_180019E9F
0x180019d66  lea     rcx, qword_18002A9B8
0x180019d6d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180019d74  nop     dword ptr [rax+rax+00h]
0x180019d79  mov     al, cs:byte_18002A9B0
0x180019d7f  test    al, al
0x180019d81  jnz     loc_180019E7D
0x180019d87  lea     r9, TlmiRHAppTableFree; FreeRoutine
0x180019d8e  mov     [rsp+38h+TableContext], 0; TableContext
0x180019d97  lea     r8, CfpOplockCompletionKeyTableAllocate; AllocateRoutine
0x180019d9e  lea     rdx, TlmiRHAppTableCompare; CompareRoutine
0x180019da5  lea     rcx, stru_18002A9C8; Table
0x180019dac  call    cs:__imp_RtlInitializeGenericTableAvl
0x180019db3  nop     dword ptr [rax+rax+00h]
0x180019db8  lea     rax, xmmword_18002AA30
0x180019dbf  xor     r9d, r9d; lpName
0x180019dc2  xor     r8d, r8d; bInitialState
0x180019dc5  mov     qword ptr cs:xmmword_18002AA30+8, rax
0x180019dcc  xor     edx, edx; bManualReset
0x180019dce  mov     qword ptr cs:xmmword_18002AA30, rax
0x180019dd5  xor     ecx, ecx; lpEventAttributes
0x180019dd7  call    cs:__imp_CreateEventW
0x180019dde  nop     dword ptr [rax+rax+00h]
0x180019de3  mov     cs:qword_18002AA40, rax
0x180019dea  test    rax, rax
0x180019ded  jz      loc_180019E7D
0x180019df3  xor     r9d, r9d; lpName
0x180019df6  xor     r8d, r8d; bInitialState
0x180019df9  xor     ecx, ecx; lpEventAttributes
0x180019dfb  lea     edx, [r9+1]; bManualReset
0x180019dff  call    cs:__imp_CreateEventW
0x180019e06  nop     dword ptr [rax+rax+00h]
0x180019e0b  mov     cs:qword_18002AA48, rax
0x180019e12  test    rax, rax
0x180019e15  jz      short loc_180019E7D
0x180019e17  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180019e20  lea     r8, TlmiRunawayHydrationWorker; lpStartAddress
0x180019e27  xor     r9d, r9d; lpParameter
0x180019e2a  mov     dword ptr [rsp+38h+TableContext], 4; dwCreationFlags
0x180019e32  xor     edx, edx; dwStackSize
0x180019e34  xor     ecx, ecx; lpThreadAttributes
0x180019e36  call    cs:__imp_CreateThread
0x180019e3d  nop     dword ptr [rax+rax+00h]
0x180019e42  mov     cs:qword_18002AA50, rax
0x180019e49  test    rax, rax
0x180019e4c  jz      short loc_180019E7D
0x180019e4e  mov     cs:byte_18002A9B0, 1
0x180019e55  call    cs:__imp_GetTickCount
0x180019e5c  nop     dword ptr [rax+rax+00h]
0x180019e61  mov     rcx, cs:qword_18002AA50; hThread
0x180019e68  mov     eax, eax
0x180019e6a  mov     cs:qword_18002A9C0, rax
0x180019e71  call    cs:__imp_ResumeThread
0x180019e78  nop     dword ptr [rax+rax+00h]
0x180019e7d  mov     al, cs:byte_18002A9B0
0x180019e83  test    al, al
0x180019e85  jnz     short loc_180019E8C
0x180019e87  call    TlmiUninitializeRunawayHydrationDetection
0x180019e8c  lea     rcx, qword_18002A9B8
0x180019e93  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180019e9a  nop     dword ptr [rax+rax+00h]
0x180019e9f  add     rsp, 38h
0x180019ea3  retn
```
