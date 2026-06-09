# Memory::Recycler::WaitForConcurrentThread(ulong,RecyclerWaitReason)

- ea: `0x18026a4e0`
- end: `0x18026a7c0`
- name: `?WaitForConcurrentThread@Recycler@Memory@@AEAAHKW4RecyclerWaitReason@@@Z`
- size: `736`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1801efdd0`
- `0x1801f1bbc`
- `0x180269db0`
- `0x18026a7c8`
- `0x18040a874`

## callees

- `0x180269d40`
- `0x18026a4e0`
- `0x180397a28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18026a55a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18026a55a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18026a61e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18026a690`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18026a61e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18026a690`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18026a515`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18026a58e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18026a515`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18026a58e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18026a52e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18026a52e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18026a5df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18026a63e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18026a5df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18026a63e`

## pseudocode

```c
_BOOL8 __fastcall Memory::Recycler::WaitForConcurrentThread(__int64 a1, DWORD a2, unsigned __int8 a3)
{
  void *v4; // rcx
  LONGLONG v5; // rbx
  bool v6; // si
  HANDLE CurrentProcess; // r15
  DWORD v8; // r14d
  void *v9; // rcx
  LONGLONG v11; // rsi
  __int64 v12; // rbx
  char v13; // r8
  _QWORD *v14; // r10
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // r9
  __int64 v18; // r9
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-50h] BYREF
  LARGE_INTEGER v20; // [rsp+38h] [rbp-48h] BYREF
  _FILETIME CreationTime; // [rsp+40h] [rbp-40h] BYREF
  struct _FILETIME ExitTime; // [rsp+48h] [rbp-38h] BYREF
  struct _FILETIME v23; // [rsp+50h] [rbp-30h] BYREF
  struct _FILETIME KernelTime; // [rsp+58h] [rbp-28h] BYREF
  struct _FILETIME UserTime; // [rsp+60h] [rbp-20h] BYREF
  struct _FILETIME v26; // [rsp+68h] [rbp-18h]
  struct _FILETIME v27; // [rsp+70h] [rbp-10h] BYREF
  struct _FILETIME v28; // [rsp+78h] [rbp-8h] BYREF

  v4 = *(void **)(a1 + 2184);
  if ( v4 )
    SetThreadPriority(v4, 0);
  v5 = 0;
  v6 = 0;
  KernelTime = 0;
  UserTime = 0;
  CurrentProcess = GetCurrentProcess();
  if ( Memory::RecyclerTelemetryInfo::ShouldStartTelemetryCapture((Memory::RecyclerTelemetryInfo *)(a1 + 108512)) )
  {
    v6 = Memory::RecyclerTelemetryInfo::IsOnScriptThread((Memory::RecyclerTelemetryInfo *)(a1 + 108512));
    if ( v6 )
    {
      PerformanceCount = Js::Tick::s_luBegin;
      QueryPerformanceCounter(&PerformanceCount);
      v5 = PerformanceCount.QuadPart - Js::Tick::s_luBegin.QuadPart;
      CreationTime = 0;
      ExitTime = 0;
      GetProcessTimes(CurrentProcess, &CreationTime, &ExitTime, &KernelTime, &UserTime);
    }
  }
  v8 = WaitForSingleObject(*(HANDLE *)(a1 + 2176), a2);
  if ( v6 )
  {
    v20 = Js::Tick::s_luBegin;
    QueryPerformanceCounter(&v20);
    v28 = 0;
    v27 = 0;
    v23 = 0;
    v11 = v20.QuadPart - Js::Tick::s_luBegin.QuadPart - v5;
    PerformanceCount.QuadPart = 0;
    GetProcessTimes(CurrentProcess, &v28, &v27, &v23, (LPFILETIME)&PerformanceCount);
    v12 = 0x7FFFFFFFFFFFFFFFLL;
    CreationTime = v23;
    ExitTime = KernelTime;
    v20 = PerformanceCount;
    v26 = UserTime;
    if ( v11 != 0x7FFFFFFFFFFFFFFFLL )
      v12 = 1000000 * v11 / Js::Tick::s_luFreq.QuadPart;
    v13 = *(_BYTE *)(a1 + 108544);
    v14 = (_QWORD *)(a1 + 108552);
    v15 = *(_QWORD *)(a1 + 108552);
    v16 = v15 + 8;
    if ( v15 == a1 + 108552 )
      v16 = 0;
    if ( v13 )
    {
      if ( v16 )
      {
        *(_QWORD *)(v16 + 8LL * a3 + 80) += v12;
        v13 = *(_BYTE *)(a1 + 108544);
      }
    }
    else
    {
      v13 = 0;
    }
    v17 = *v14 + 8LL;
    if ( (_QWORD *)*v14 == v14 )
      v17 = 0;
    if ( v13 && v17 )
    {
      *(_QWORD *)(v17 + 8LL * a3 + 136) += (v20.QuadPart - *(_QWORD *)&v26) / 0xAuLL;
      v13 = *(_BYTE *)(a1 + 108544);
    }
    v18 = *v14 + 8LL;
    if ( (_QWORD *)*v14 == v14 )
      v18 = 0;
    if ( v13 && v18 )
      *(_QWORD *)(v18 + 8LL * a3 + 192) += (*(_QWORD *)&CreationTime - *(_QWORD *)&ExitTime) / 0xAuLL;
  }
  v9 = *(void **)(a1 + 2184);
  if ( v9 )
  {
    if ( v8 == 258 )
    {
      *(_BYTE *)(a1 + 2147) = 1;
    }
    else
    {
      SetThreadPriority(v9, -1);
      *(_BYTE *)(a1 + 2147) = 0;
    }
  }
  return v8 == 0;
}

```

## disassembly

```asm
0x18026a4e0  mov     rax, rsp
0x18026a4e3  mov     [rax+20h], rbx
0x18026a4e7  mov     [rax+18h], r8b
0x18026a4eb  mov     [rax+10h], edx
0x18026a4ee  mov     [rax+8], rcx
0x18026a4f2  push    rbp
0x18026a4f3  push    rsi
0x18026a4f4  push    rdi
0x18026a4f5  push    r14
0x18026a4f7  push    r15
0x18026a4f9  mov     rbp, rsp
0x18026a4fc  sub     rsp, 80h
0x18026a503  mov     rdi, [rbp+arg_0]
0x18026a507  mov     rcx, [rdi+888h]; hThread
0x18026a50e  test    rcx, rcx
0x18026a511  jz      short loc_18026A521
0x18026a513  xor     edx, edx; nPriority
0x18026a515  call    cs:__imp_SetThreadPriority
0x18026a51c  nop     dword ptr [rax+rax+00h]
0x18026a521  xor     ebx, ebx
0x18026a523  xor     sil, sil
0x18026a526  mov     qword ptr [rbp+KernelTime.dwLowDateTime], rbx
0x18026a52a  mov     qword ptr [rbp+UserTime.dwLowDateTime], rbx
0x18026a52e  call    cs:__imp_GetCurrentProcess
0x18026a535  nop     dword ptr [rax+rax+00h]
0x18026a53a  lea     r14, [rdi+1A7E0h]
0x18026a541  mov     r15, rax
0x18026a544  mov     rcx, r14; this
0x18026a547  call    ?ShouldStartTelemetryCapture@RecyclerTelemetryInfo@Memory@@QEBA_NXZ; Memory::RecyclerTelemetryInfo::ShouldStartTelemetryCapture(void)
0x18026a54c  test    al, al
0x18026a54e  jnz     short loc_18026A5C1
0x18026a550  mov     edx, [rbp+dwMilliseconds]; dwMilliseconds
0x18026a553  mov     rcx, [rdi+880h]; hHandle
0x18026a55a  call    cs:__imp_WaitForSingleObject
0x18026a561  nop     dword ptr [rax+rax+00h]
0x18026a566  mov     r14d, eax
0x18026a569  test    sil, sil
0x18026a56c  jnz     loc_18026A62F
0x18026a572  mov     rcx, [rdi+888h]; hThread
0x18026a579  test    rcx, rcx
0x18026a57c  jz      short loc_18026A5A1
0x18026a57e  cmp     r14d, 102h
0x18026a585  jz      loc_18026A7B4
0x18026a58b  or      edx, 0FFFFFFFFh; nPriority
0x18026a58e  call    cs:__imp_SetThreadPriority
0x18026a595  nop     dword ptr [rax+rax+00h]
0x18026a59a  mov     byte ptr [rdi+863h], 0
0x18026a5a1  mov     rbx, [rsp+80h+arg_18]
0x18026a5a9  xor     eax, eax
0x18026a5ab  test    r14d, r14d
0x18026a5ae  setz    al
0x18026a5b1  add     rsp, 80h
0x18026a5b8  pop     r15
0x18026a5ba  pop     r14
0x18026a5bc  pop     rdi
0x18026a5bd  pop     rsi
0x18026a5be  pop     rbp
0x18026a5bf  retn
0x18026a5c1  mov     rcx, r14; this
0x18026a5c4  call    ?IsOnScriptThread@RecyclerTelemetryInfo@Memory@@QEBA_NXZ; Memory::RecyclerTelemetryInfo::IsOnScriptThread(void)
0x18026a5c9  mov     sil, al
0x18026a5cc  test    al, al
0x18026a5ce  jz      short loc_18026A550
0x18026a5d0  mov     rcx, qword ptr cs:?s_luBegin@Tick@Js@@0_KA; unsigned __int64 Js::Tick::s_luBegin ...
0x18026a5d7  mov     qword ptr [rbp+PerformanceCount], rcx
0x18026a5db  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18026a5df  call    cs:__imp_QueryPerformanceCounter
0x18026a5e6  nop     dword ptr [rax+rax+00h]
0x18026a5eb  mov     rbx, qword ptr [rbp+PerformanceCount]
0x18026a5ef  lea     rax, [rbp+UserTime]
0x18026a5f3  sub     rbx, qword ptr cs:?s_luBegin@Tick@Js@@0_KA; unsigned __int64 Js::Tick::s_luBegin ...
0x18026a5fa  lea     r9, [rbp+KernelTime]; lpKernelTime
0x18026a5fe  lea     r8, [rbp+ExitTime]; lpExitTime
0x18026a602  mov     [rsp+80h+lpUserTime], rax; lpUserTime
0x18026a607  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x18026a60b  mov     qword ptr [rbp+CreationTime.dwLowDateTime], 0
0x18026a613  mov     rcx, r15; hProcess
0x18026a616  mov     qword ptr [rbp+ExitTime.dwLowDateTime], 0
0x18026a61e  call    cs:__imp_GetProcessTimes
0x18026a625  nop     dword ptr [rax+rax+00h]
0x18026a62a  jmp     loc_18026A550
0x18026a62f  mov     rcx, qword ptr cs:?s_luBegin@Tick@Js@@0_KA; unsigned __int64 Js::Tick::s_luBegin ...
0x18026a636  mov     qword ptr [rbp+var_48], rcx
0x18026a63a  lea     rcx, [rbp+var_48]; lpPerformanceCount
0x18026a63e  call    cs:__imp_QueryPerformanceCounter
0x18026a645  nop     dword ptr [rax+rax+00h]
0x18026a64a  mov     rsi, qword ptr [rbp+var_48]
0x18026a64e  lea     rax, [rbp+PerformanceCount]
0x18026a652  sub     rsi, qword ptr cs:?s_luBegin@Tick@Js@@0_KA; unsigned __int64 Js::Tick::s_luBegin ...
0x18026a659  lea     r9, [rbp+var_30]; lpKernelTime
0x18026a65d  lea     r8, [rbp+var_10]; lpExitTime
0x18026a661  mov     qword ptr [rbp+var_8.dwLowDateTime], 0
0x18026a669  lea     rdx, [rbp+var_8]; lpCreationTime
0x18026a66d  mov     qword ptr [rbp+var_10.dwLowDateTime], 0
0x18026a675  mov     rcx, r15; hProcess
0x18026a678  mov     qword ptr [rbp+var_30.dwLowDateTime], 0
0x18026a680  sub     rsi, rbx
0x18026a683  mov     qword ptr [rbp+PerformanceCount], 0
0x18026a68b  mov     [rsp+80h+lpUserTime], rax; lpUserTime
0x18026a690  call    cs:__imp_GetProcessTimes
0x18026a697  nop     dword ptr [rax+rax+00h]
0x18026a69c  mov     eax, [rbp+var_30.dwHighDateTime]
0x18026a69f  mov     rbx, 7FFFFFFFFFFFFFFFh
0x18026a6a9  mov     [rbp+CreationTime.dwHighDateTime], eax
0x18026a6ac  mov     eax, [rbp+var_30.dwLowDateTime]
0x18026a6af  mov     [rbp+CreationTime.dwLowDateTime], eax
0x18026a6b2  mov     eax, [rbp+KernelTime.dwHighDateTime]
0x18026a6b5  mov     [rbp+ExitTime.dwHighDateTime], eax
0x18026a6b8  mov     eax, [rbp+KernelTime.dwLowDateTime]
0x18026a6bb  mov     [rbp+ExitTime.dwLowDateTime], eax
0x18026a6be  mov     eax, dword ptr [rbp+PerformanceCount+4]
0x18026a6c1  mov     dword ptr [rbp+var_48+4], eax
0x18026a6c4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18026a6c7  mov     dword ptr [rbp+var_48], eax
0x18026a6ca  mov     eax, [rbp+UserTime.dwHighDateTime]
0x18026a6cd  mov     dword ptr [rbp+var_18+4], eax
0x18026a6d0  mov     eax, [rbp+UserTime.dwLowDateTime]
0x18026a6d3  mov     dword ptr [rbp+var_18], eax
0x18026a6d6  cmp     rsi, rbx
0x18026a6d9  jz      short loc_18026A6EE
0x18026a6db  imul    rax, rsi, 0F4240h
0x18026a6e2  cqo
0x18026a6e4  idiv    qword ptr cs:?s_luFreq@Tick@Js@@0_KA; unsigned __int64 Js::Tick::s_luFreq ...
0x18026a6eb  mov     rbx, rax
0x18026a6ee  mov     r8b, [rdi+1A800h]
0x18026a6f5  lea     r10, [rdi+1A808h]
0x18026a6fc  mov     rdx, [r10]
0x18026a6ff  xor     ecx, ecx
0x18026a701  movzx   r11d, [rbp+arg_10]
0x18026a706  cmp     rdx, r10
0x18026a709  lea     r9, [rdx+8]
0x18026a70d  cmovz   r9, rcx
0x18026a711  test    r8b, r8b
0x18026a714  jz      short loc_18026A787
0x18026a716  test    r9, r9
0x18026a719  jz      short loc_18026A727
0x18026a71b  add     [r9+r11*8+50h], rbx
0x18026a720  mov     r8b, [rdi+1A800h]
0x18026a727  mov     rcx, [r10]
0x18026a72a  xor     eax, eax
0x18026a72c  cmp     rcx, r10
0x18026a72f  mov     rbx, 0CCCCCCCCCCCCCCCDh
0x18026a739  lea     r9, [rcx+8]
0x18026a73d  cmovz   r9, rax
0x18026a741  test    r8b, r8b
0x18026a744  jnz     short loc_18026A78C
0x18026a746  mov     rdx, [r10]
0x18026a749  xor     ecx, ecx
0x18026a74b  cmp     rdx, r10
0x18026a74e  lea     r9, [rdx+8]
0x18026a752  cmovz   r9, rcx
0x18026a756  test    r8b, r8b
0x18026a759  jz      loc_18026A572
0x18026a75f  test    r9, r9
0x18026a762  jz      loc_18026A572
0x18026a768  mov     rcx, qword ptr [rbp+CreationTime.dwLowDateTime]
0x18026a76c  mov     rax, rbx
0x18026a76f  sub     rcx, qword ptr [rbp+ExitTime.dwLowDateTime]
0x18026a773  mul     rcx
0x18026a776  shr     rdx, 3
0x18026a77a  add     [r9+r11*8+0C0h], rdx
0x18026a782  jmp     loc_18026A572
0x18026a787  xor     r8b, r8b
0x18026a78a  jmp     short loc_18026A727
0x18026a78c  test    r9, r9
0x18026a78f  jz      short loc_18026A746
0x18026a791  mov     rcx, qword ptr [rbp+var_48]
0x18026a795  mov     rax, rbx
0x18026a798  sub     rcx, [rbp+var_18]
0x18026a79c  mul     rcx
0x18026a79f  shr     rdx, 3
0x18026a7a3  add     [r9+r11*8+88h], rdx
0x18026a7ab  mov     r8b, [rdi+1A800h]
0x18026a7b2  jmp     short loc_18026A746
0x18026a7b4  mov     byte ptr [rdi+863h], 1
0x18026a7bb  jmp     loc_18026A5A1
```
