# DpiPdoPollingWorkItem

- ea: `0x1402c5ea0`
- end: `0x1402c6188`
- name: `DpiPdoPollingWorkItem`
- size: `744`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402a7628`

## callees

- `0x140022434`
- `0x140035f90`
- `0x140041db4`
- `0x140047ef8`
- `0x1402b0f3c`
- `0x1402b834c`
- `0x1402c5ea0`
- `0x140367720`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x1402c6159`
- `ntoskrnl!KeSetTimer` at `0x1402c6159`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402c5f69`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402c6036`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402c5f69`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402c6036`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402c60bc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402c60f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402c60bc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402c60f4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402c5f8f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402c604e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402c5f8f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402c604e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c60b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c60e8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c60b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c60e8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c5ef3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c6084`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c5ef3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c6084`
- `ntoskrnl!KeReleaseMutex` at `0x1402c5f43`
- `ntoskrnl!KeReleaseMutex` at `0x1402c60a1`
- `ntoskrnl!KeReleaseMutex` at `0x1402c5f43`
- `ntoskrnl!KeReleaseMutex` at `0x1402c60a1`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1402c610d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1402c610d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6123`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6123`
- `watchdog!WdLogSingleEntry1` at `0x1402c5ffa`
- `watchdog!WdLogSingleEntry1` at `0x1402c6020`
- `watchdog!WdLogSingleEntry1` at `0x1402c5ffa`
- `watchdog!WdLogSingleEntry1` at `0x1402c6020`

## pseudocode

```c
void __fastcall DpiPdoPollingWorkItem(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  __int64 v3; // r13
  int v4; // r15d
  __int64 v5; // r14
  __int64 v6; // rax
  __int64 v7; // rbp
  int v8; // r8d
  int v9; // r9d
  __int64 ChildDescriptor; // rbx
  _BYTE v11[8]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v12; // [rsp+48h] [rbp-50h]

  v11[0] = 0;
  CDisplayScenarioContextScope::ContextScopeConstructor((CDisplayScenarioContextScope *)v11, 0, 0xEu, 0);
  v3 = v12;
  v4 = 0;
  while ( 1 )
  {
    KeWaitForSingleObject(qword_1401630F0, Executive, 0, 0, 0);
    v5 = qword_1401630E0;
    if ( (__int64 *)qword_1401630E0 == &qword_1401630E0 )
    {
      v5 = 0;
      _InterlockedExchange(&dword_1401630D8, 0);
    }
    else
    {
      if ( *(__int64 **)(qword_1401630E0 + 8) != &qword_1401630E0
        || (v6 = *(_QWORD *)qword_1401630E0, *(_QWORD *)(*(_QWORD *)qword_1401630E0 + 8LL) != qword_1401630E0) )
      {
        __fastfail(3u);
      }
      qword_1401630E0 = *(_QWORD *)qword_1401630E0;
      *(_QWORD *)(v6 + 8) = &qword_1401630E0;
    }
    KeReleaseMutex((PRKMUTEX)qword_1401630F0, 0);
    if ( !v5 )
      break;
    v7 = *(_QWORD *)(*(_QWORD *)(v5 + 24) + 64LL);
    if ( !Context )
    {
      KeEnterCriticalRegion();
      if ( *(_BYTE *)(v7 + 484) )
        DpiCheckForOutstandingD3Requests(v7);
      ExAcquireResourceSharedLite(*(PERESOURCE *)(v7 + 168), 1u);
      if ( *(_DWORD *)(v7 + 236) == 2 )
      {
        if ( *(_DWORD *)(v7 + 4120) != 1 && *(_DWORD *)(v7 + 284) == 1 )
        {
          LOBYTE(v9) = *(_BYTE *)(v5 + 41);
          LOBYTE(v8) = *(_BYTE *)(v5 + 40);
          v4 = DpiFdoInvalidateChildStatus(
                 *(_QWORD *)(v5 + 24),
                 *(_DWORD *)(v5 + 32),
                 v8,
                 v9,
                 *(_BYTE *)(v5 + 42),
                 1,
                 v3);
LABEL_18:
          if ( *(_BYTE *)(v7 + 484) )
            DpiEnableD3Requests(*(_QWORD *)(v7 + 24));
          ExReleaseResourceLite(*(PERESOURCE *)(v7 + 168));
          KeLeaveCriticalRegion();
          goto LABEL_21;
        }
        v4 = -1073741661;
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 6512;
      }
      else
      {
        v4 = -1073741810;
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 6504;
      }
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite((PERESOURCE)(v7 + 3440), 1u);
      ChildDescriptor = DpiFdoGetChildDescriptor(v7, *(unsigned int *)(v5 + 32));
      KeWaitForSingleObject((PVOID)(v7 + 3544), Executive, 0, 0, 0);
      DpiFdoPendingCreatePdoCompletion(*(_QWORD *)(v5 + 24), ChildDescriptor);
      KeReleaseMutex((PRKMUTEX)(v7 + 3544), 0);
      ExReleaseResourceLite((PERESOURCE)(v7 + 3440));
      KeLeaveCriticalRegion();
      goto LABEL_18;
    }
LABEL_21:
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v7 + 64), (PVOID)v5, 0x20u);
    ExFreeToNPagedLookasideList(&stru_140162F40, (PVOID)v5);
    if ( v4 == 259 )
    {
      _InterlockedExchange(&dword_1401630D8, 0);
      KeSetTimer(&stru_140163050, (LARGE_INTEGER)-3000000LL, &stru_140163090);
      break;
    }
  }
  CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v11);
}

```

## disassembly

```asm
0x1402c5ea0  push    rbx
0x1402c5ea2  push    rbp
0x1402c5ea3  push    rsi
0x1402c5ea4  push    rdi
0x1402c5ea5  push    r12
0x1402c5ea7  push    r13
0x1402c5ea9  push    r14
0x1402c5eab  push    r15
0x1402c5ead  sub     rsp, 58h
0x1402c5eb1  xor     r9d, r9d; unsigned int
0x1402c5eb4  mov     [rsp+98h+var_58], 0
0x1402c5eb9  mov     r12, rdx
0x1402c5ebc  lea     rcx, [rsp+98h+var_58]; this
0x1402c5ec1  xor     edx, edx; struct _GUID *
0x1402c5ec3  lea     r8d, [r9+0Eh]; unsigned int
0x1402c5ec7  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x1402c5ecc  mov     r13, [rsp+98h+var_50]
0x1402c5ed1  lea     rbx, qword_1401630E0
0x1402c5ed8  xor     r15d, r15d
0x1402c5edb  mov     rcx, cs:qword_1401630F0; Object
0x1402c5ee2  xor     r9d, r9d; Alertable
0x1402c5ee5  xor     r8d, r8d; WaitMode
0x1402c5ee8  mov     [rsp+98h+Timeout], 0; Timeout
0x1402c5ef1  xor     edx, edx; WaitReason
0x1402c5ef3  call    cs:__imp_KeWaitForSingleObject
0x1402c5efa  nop     dword ptr [rax+rax+00h]
0x1402c5eff  mov     r14, cs:qword_1401630E0
0x1402c5f06  cmp     r14, rbx
0x1402c5f09  jnz     short loc_1402C5F18
0x1402c5f0b  xor     r14d, r14d
0x1402c5f0e  xor     eax, eax
0x1402c5f10  xchg    eax, cs:dword_1401630D8
0x1402c5f16  jmp     short loc_1402C5F3A
0x1402c5f18  cmp     [r14+8], rbx
0x1402c5f1c  jnz     loc_1402C6181
0x1402c5f22  mov     rax, [r14]
0x1402c5f25  cmp     [rax+8], r14
0x1402c5f29  jnz     loc_1402C6181
0x1402c5f2f  mov     cs:qword_1401630E0, rax
0x1402c5f36  mov     [rax+8], rbx
0x1402c5f3a  mov     rcx, cs:qword_1401630F0; Mutex
0x1402c5f41  xor     edx, edx; Wait
0x1402c5f43  call    cs:__imp_KeReleaseMutex
0x1402c5f4a  nop     dword ptr [rax+rax+00h]
0x1402c5f4f  test    r14, r14
0x1402c5f52  jz      loc_1402C6165
0x1402c5f58  mov     rax, [r14+18h]
0x1402c5f5c  mov     rbp, [rax+40h]
0x1402c5f60  test    r12, r12
0x1402c5f63  jnz     loc_1402C6100
0x1402c5f69  call    cs:__imp_KeEnterCriticalRegion
0x1402c5f70  nop     dword ptr [rax+rax+00h]
0x1402c5f75  cmp     [rbp+1E4h], r12b
0x1402c5f7c  jz      short loc_1402C5F86
0x1402c5f7e  mov     rcx, rbp
0x1402c5f81  call    DpiCheckForOutstandingD3Requests
0x1402c5f86  mov     rcx, [rbp+0A8h]; Resource
0x1402c5f8d  mov     dl, 1; Wait
0x1402c5f8f  call    cs:__imp_ExAcquireResourceSharedLite
0x1402c5f96  nop     dword ptr [rax+rax+00h]
0x1402c5f9b  movsxd  rax, dword ptr [rbp+0ECh]
0x1402c5fa2  cmp     eax, 2
0x1402c5fa5  jnz     short loc_1402C6012
0x1402c5fa7  cmp     dword ptr [rbp+1018h], 1
0x1402c5fae  jz      short loc_1402C5FE8
0x1402c5fb0  cmp     dword ptr [rbp+11Ch], 1
0x1402c5fb7  jnz     short loc_1402C5FE8
0x1402c5fb9  mov     al, [r14+2Ah]
0x1402c5fbd  mov     r9b, [r14+29h]
0x1402c5fc1  mov     r8b, [r14+28h]
0x1402c5fc5  mov     edx, [r14+20h]
0x1402c5fc9  mov     rcx, [r14+18h]
0x1402c5fcd  mov     [rsp+98h+var_68], r13
0x1402c5fd2  mov     [rsp+98h+var_70], 1
0x1402c5fd7  mov     byte ptr [rsp+98h+Timeout], al
0x1402c5fdb  call    DpiFdoInvalidateChildStatus
0x1402c5fe0  mov     r15d, eax
0x1402c5fe3  jmp     loc_1402C60CF
0x1402c5fe8  mov     r15d, 0C00000A3h
0x1402c5fee  movsxd  rdx, dword ptr [rbp+11Ch]
0x1402c5ff5  mov     ecx, 3
0x1402c5ffa  call    cs:__imp_WdLogSingleEntry1
0x1402c6001  nop     dword ptr [rax+rax+00h]
0x1402c6006  mov     cs:WdLogGlobalForLineNumber, 1970h
0x1402c6010  jmp     short loc_1402C6036
0x1402c6012  mov     r15d, 0C000000Eh
0x1402c6018  mov     rdx, rax
0x1402c601b  mov     ecx, 3
0x1402c6020  call    cs:__imp_WdLogSingleEntry1
0x1402c6027  nop     dword ptr [rax+rax+00h]
0x1402c602c  mov     cs:WdLogGlobalForLineNumber, 1968h
0x1402c6036  call    cs:__imp_KeEnterCriticalRegion
0x1402c603d  nop     dword ptr [rax+rax+00h]
0x1402c6042  lea     rsi, [rbp+0D70h]
0x1402c6049  mov     dl, 1; Wait
0x1402c604b  mov     rcx, rsi; Resource
0x1402c604e  call    cs:__imp_ExAcquireResourceSharedLite
0x1402c6055  nop     dword ptr [rax+rax+00h]
0x1402c605a  mov     edx, [r14+20h]
0x1402c605e  mov     rcx, rbp
0x1402c6061  call    DpiFdoGetChildDescriptor
0x1402c6066  lea     rdi, [rbp+0DD8h]
0x1402c606d  mov     [rsp+98h+Timeout], 0; Timeout
0x1402c6076  mov     rcx, rdi; Object
0x1402c6079  xor     r9d, r9d; Alertable
0x1402c607c  xor     r8d, r8d; WaitMode
0x1402c607f  xor     edx, edx; WaitReason
0x1402c6081  mov     rbx, rax
0x1402c6084  call    cs:__imp_KeWaitForSingleObject
0x1402c608b  nop     dword ptr [rax+rax+00h]
0x1402c6090  mov     rcx, [r14+18h]
0x1402c6094  mov     rdx, rbx
0x1402c6097  call    DpiFdoPendingCreatePdoCompletion
0x1402c609c  xor     edx, edx; Wait
0x1402c609e  mov     rcx, rdi; Mutex
0x1402c60a1  call    cs:__imp_KeReleaseMutex
0x1402c60a8  nop     dword ptr [rax+rax+00h]
0x1402c60ad  mov     rcx, rsi; Resource
0x1402c60b0  call    cs:__imp_ExReleaseResourceLite
0x1402c60b7  nop     dword ptr [rax+rax+00h]
0x1402c60bc  call    cs:__imp_KeLeaveCriticalRegion
0x1402c60c3  nop     dword ptr [rax+rax+00h]
0x1402c60c8  lea     rbx, qword_1401630E0
0x1402c60cf  cmp     byte ptr [rbp+1E4h], 0
0x1402c60d6  jz      short loc_1402C60E1
0x1402c60d8  mov     rcx, [rbp+18h]
0x1402c60dc  call    DpiEnableD3Requests
0x1402c60e1  mov     rcx, [rbp+0A8h]; Resource
0x1402c60e8  call    cs:__imp_ExReleaseResourceLite
0x1402c60ef  nop     dword ptr [rax+rax+00h]
0x1402c60f4  call    cs:__imp_KeLeaveCriticalRegion
0x1402c60fb  nop     dword ptr [rax+rax+00h]
0x1402c6100  lea     rcx, [rbp+40h]; RemoveLock
0x1402c6104  mov     r8d, 20h ; ' '; RemlockSize
0x1402c610a  mov     rdx, r14; Tag
0x1402c610d  call    cs:__imp_IoReleaseRemoveLockEx
0x1402c6114  nop     dword ptr [rax+rax+00h]
0x1402c6119  mov     rdx, r14; Entry
0x1402c611c  lea     rcx, stru_140162F40; Lookaside
0x1402c6123  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402c612a  nop     dword ptr [rax+rax+00h]
0x1402c612f  cmp     r15d, 103h
0x1402c6136  jnz     loc_1402C5EDB
0x1402c613c  xor     eax, eax
0x1402c613e  lea     r8, stru_140163090; Dpc
0x1402c6145  xchg    eax, cs:dword_1401630D8
0x1402c614b  mov     rdx, 0FFFFFFFFFFD23940h; DueTime
0x1402c6152  lea     rcx, stru_140163050; Timer
0x1402c6159  call    cs:__imp_KeSetTimer
0x1402c6160  nop     dword ptr [rax+rax+00h]
0x1402c6165  lea     rcx, [rsp+98h+var_58]; this
0x1402c616a  call    ??1CDisplayScenarioContextScope@@QEAA@XZ; CDisplayScenarioContextScope::~CDisplayScenarioContextScope(void)
0x1402c616f  add     rsp, 58h
0x1402c6173  pop     r15
0x1402c6175  pop     r14
0x1402c6177  pop     r13
0x1402c6179  pop     r12
0x1402c617b  pop     rdi
0x1402c617c  pop     rsi
0x1402c617d  pop     rbp
0x1402c617e  pop     rbx
0x1402c617f  retn
0x1402c6181  mov     ecx, 3
0x1402c6186  int     29h; Win8: RtlFailFast(ecx)
```
