# CManipulationManager::CreateManipulationThread(void)

- ea: `0x1801e2f60`
- end: `0x1801e3083`
- name: `?CreateManipulationThread@CManipulationManager@@IEAAJXZ`
- size: `291`
- prototype: `__int64 __fastcall(CManipulationManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801eb1ac`

## callees

- `0x180050270`
- `0x1801e2f60`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801e3011`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801e3011`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1801e3001`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1801e3001`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1801e2ff4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1801e2ff4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801e2fb8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801e2fb8`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1801e2fe2`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1801e2fe2`

## string_xrefs

- `0x1801e2fd8`: `DWM Manipulation Thread`

## pseudocode

```c
__int64 __fastcall CManipulationManager::CreateManipulationThread(CManipulationManager *this)
{
  int v2; // eax
  unsigned int v3; // edi
  HANDLE v4; // rax
  DWORD v5; // ecx
  int v7; // r9d
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 152) )
  {
    v3 = -2147467260;
    dwCreationFlags = 919;
LABEL_10:
    v7 = v3;
    goto LABEL_7;
  }
  v2 = (*(__int64 (__fastcall **)(CManipulationManager *))(*(_QWORD *)this + 56LL))(this);
  v3 = v2;
  if ( v2 < 0 )
  {
    v7 = v2;
    dwCreationFlags = 922;
LABEL_7:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1803531A0, 3u, v7, dwCreationFlags, 0);
    return v3;
  }
  ThreadId = 0;
  v4 = CreateThread(0, 0, CManipulationManager::s_ThreadMain, this, 4u, &ThreadId);
  v5 = ThreadId;
  *((_QWORD *)this + 18) = v4;
  CManipulationManager::s_dwManipulationThreadId = v5;
  if ( !v4 )
  {
    v3 = -2147024882;
    dwCreationFlags = 936;
    goto LABEL_10;
  }
  SetThreadDescription(v4, L"DWM Manipulation Thread");
  SetThreadPriority(*((HANDLE *)this + 18), 16);
  ResumeThread(*((HANDLE *)this + 18));
  WaitForSingleObject(CManipulationManager::s_hManipThreadInitializedWaitEvent, 0xFFFFFFFF);
  return v3;
}

```

## disassembly

```asm
0x1801e2f60  mov     [rsp+arg_8], rbx
0x1801e2f65  push    rdi
0x1801e2f66  sub     rsp, 30h
0x1801e2f6a  cmp     byte ptr [rcx+98h], 0
0x1801e2f71  mov     rbx, rcx
0x1801e2f74  jnz     loc_1801E3050
0x1801e2f7a  mov     rax, [rcx]
0x1801e2f7d  mov     rax, [rax+38h]
0x1801e2f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2f86  mov     edi, eax
0x1801e2f88  test    eax, eax
0x1801e2f8a  js      loc_1801E3024
0x1801e2f90  lea     rax, [rsp+38h+ThreadId]
0x1801e2f95  mov     [rsp+38h+ThreadId], 0
0x1801e2f9d  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1801e2fa2  lea     r8, ?s_ThreadMain@CManipulationManager@@KAKPEAX@Z; lpStartAddress
0x1801e2fa9  mov     r9, rbx; lpParameter
0x1801e2fac  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1801e2fb4  xor     edx, edx; dwStackSize
0x1801e2fb6  xor     ecx, ecx; lpThreadAttributes
0x1801e2fb8  call    cs:__imp_CreateThread
0x1801e2fbe  mov     ecx, [rsp+38h+ThreadId]
0x1801e2fc2  mov     [rbx+90h], rax
0x1801e2fc9  mov     cs:?s_dwManipulationThreadId@CManipulationManager@@1KA, ecx; ulong CManipulationManager::s_dwManipulationThreadId
0x1801e2fcf  test    rax, rax
0x1801e2fd2  jz      loc_1801E3068
0x1801e2fd8  lea     rdx, aDwmManipulatio; "DWM Manipulation Thread"
0x1801e2fdf  mov     rcx, rax; hThread
0x1801e2fe2  call    cs:__imp_SetThreadDescription
0x1801e2fe8  mov     rcx, [rbx+90h]; hThread
0x1801e2fef  mov     edx, 10h; nPriority
0x1801e2ff4  call    cs:__imp_SetThreadPriority
0x1801e2ffa  mov     rcx, [rbx+90h]; hThread
0x1801e3001  call    cs:__imp_ResumeThread
0x1801e3007  mov     rcx, cs:?s_hManipThreadInitializedWaitEvent@CManipulationManager@@1PEAXEA; hHandle
0x1801e300e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801e3011  call    cs:__imp_WaitForSingleObject
0x1801e3017  mov     rbx, [rsp+38h+arg_8]
0x1801e301c  mov     eax, edi
0x1801e301e  add     rsp, 30h
0x1801e3022  pop     rdi
0x1801e3023  retn
0x1801e3024  mov     [rsp+38h+lpThreadId], 0; void *
0x1801e302d  mov     r9d, eax; int
0x1801e3030  mov     [rsp+38h+dwCreationFlags], 39Ah; unsigned int
0x1801e3038  mov     r8d, 3; unsigned int
0x1801e303e  lea     rdx, qword_1803531A0; int *
0x1801e3045  lea     ecx, [r8+11h]; unsigned int
0x1801e3049  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801e304e  jmp     short loc_1801E3017
0x1801e3050  mov     [rsp+38h+lpThreadId], 0
0x1801e3059  mov     edi, 80004004h
0x1801e305e  mov     [rsp+38h+dwCreationFlags], 397h
0x1801e3066  jmp     short loc_1801E307E
0x1801e3068  mov     [rsp+38h+lpThreadId], 0
0x1801e3071  mov     edi, 8007000Eh
0x1801e3076  mov     [rsp+38h+dwCreationFlags], 3A8h
0x1801e307e  mov     r9d, edi
0x1801e3081  jmp     short loc_1801E3038
```
