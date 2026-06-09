# DpiPdoPollingWorkItem

- ea: `0x1402bf450`
- end: `0x1402bf738`
- name: `DpiPdoPollingWorkItem`
- size: `744`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402a0c78`

## callees

- `0x140022264`
- `0x140035dc0`
- `0x140041b54`
- `0x140047cf8`
- `0x1402aa58c`
- `0x1402b199c`
- `0x1402bf450`
- `0x1403676e0`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x1402bf709`
- `ntoskrnl!KeSetTimer` at `0x1402bf709`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402bf519`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402bf5e6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402bf519`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402bf5e6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402bf66c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402bf6a4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402bf66c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402bf6a4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402bf53f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402bf5fe`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402bf53f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402bf5fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bf660`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bf698`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bf660`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bf698`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402bf4a3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402bf634`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402bf4a3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402bf634`
- `ntoskrnl!KeReleaseMutex` at `0x1402bf4f3`
- `ntoskrnl!KeReleaseMutex` at `0x1402bf651`
- `ntoskrnl!KeReleaseMutex` at `0x1402bf4f3`
- `ntoskrnl!KeReleaseMutex` at `0x1402bf651`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1402bf6bd`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1402bf6bd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bf6d3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bf6d3`
- `watchdog!WdLogSingleEntry1` at `0x1402bf5aa`
- `watchdog!WdLogSingleEntry1` at `0x1402bf5d0`
- `watchdog!WdLogSingleEntry1` at `0x1402bf5aa`
- `watchdog!WdLogSingleEntry1` at `0x1402bf5d0`

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
    KeWaitForSingleObject(qword_14015F070, Executive, 0, 0, 0);
    v5 = qword_14015F060;
    if ( (__int64 *)qword_14015F060 == &qword_14015F060 )
    {
      v5 = 0;
      _InterlockedExchange(&dword_14015F058, 0);
    }
    else
    {
      if ( *(__int64 **)(qword_14015F060 + 8) != &qword_14015F060
        || (v6 = *(_QWORD *)qword_14015F060, *(_QWORD *)(*(_QWORD *)qword_14015F060 + 8LL) != qword_14015F060) )
      {
        __fastfail(3u);
      }
      qword_14015F060 = *(_QWORD *)qword_14015F060;
      *(_QWORD *)(v6 + 8) = &qword_14015F060;
    }
    KeReleaseMutex((PRKMUTEX)qword_14015F070, 0);
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
        WdLogGlobalForLineNumber = 6497;
      }
      else
      {
        v4 = -1073741810;
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 6489;
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
    ExFreeToNPagedLookasideList(&stru_14015EEC0, (PVOID)v5);
    if ( v4 == 259 )
    {
      _InterlockedExchange(&dword_14015F058, 0);
      KeSetTimer(&stru_14015EFD0, (LARGE_INTEGER)-3000000LL, &stru_14015F010);
      break;
    }
  }
  CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v11);
}

```

## disassembly

```asm
0x1402bf450  push    rbx
0x1402bf452  push    rbp
0x1402bf453  push    rsi
0x1402bf454  push    rdi
0x1402bf455  push    r12
0x1402bf457  push    r13
0x1402bf459  push    r14
0x1402bf45b  push    r15
0x1402bf45d  sub     rsp, 58h
0x1402bf461  xor     r9d, r9d; unsigned int
0x1402bf464  mov     [rsp+98h+var_58], 0
0x1402bf469  mov     r12, rdx
0x1402bf46c  lea     rcx, [rsp+98h+var_58]; this
0x1402bf471  xor     edx, edx; struct _GUID *
0x1402bf473  lea     r8d, [r9+0Eh]; unsigned int
0x1402bf477  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x1402bf47c  mov     r13, [rsp+98h+var_50]
0x1402bf481  lea     rbx, qword_14015F060
0x1402bf488  xor     r15d, r15d
0x1402bf48b  mov     rcx, cs:qword_14015F070; Object
0x1402bf492  xor     r9d, r9d; Alertable
0x1402bf495  xor     r8d, r8d; WaitMode
0x1402bf498  mov     [rsp+98h+Timeout], 0; Timeout
0x1402bf4a1  xor     edx, edx; WaitReason
0x1402bf4a3  call    cs:__imp_KeWaitForSingleObject
0x1402bf4aa  nop     dword ptr [rax+rax+00h]
0x1402bf4af  mov     r14, cs:qword_14015F060
0x1402bf4b6  cmp     r14, rbx
0x1402bf4b9  jnz     short loc_1402BF4C8
0x1402bf4bb  xor     r14d, r14d
0x1402bf4be  xor     eax, eax
0x1402bf4c0  xchg    eax, cs:dword_14015F058
0x1402bf4c6  jmp     short loc_1402BF4EA
0x1402bf4c8  cmp     [r14+8], rbx
0x1402bf4cc  jnz     loc_1402BF731
0x1402bf4d2  mov     rax, [r14]
0x1402bf4d5  cmp     [rax+8], r14
0x1402bf4d9  jnz     loc_1402BF731
0x1402bf4df  mov     cs:qword_14015F060, rax
0x1402bf4e6  mov     [rax+8], rbx
0x1402bf4ea  mov     rcx, cs:qword_14015F070; Mutex
0x1402bf4f1  xor     edx, edx; Wait
0x1402bf4f3  call    cs:__imp_KeReleaseMutex
0x1402bf4fa  nop     dword ptr [rax+rax+00h]
0x1402bf4ff  test    r14, r14
0x1402bf502  jz      loc_1402BF715
0x1402bf508  mov     rax, [r14+18h]
0x1402bf50c  mov     rbp, [rax+40h]
0x1402bf510  test    r12, r12
0x1402bf513  jnz     loc_1402BF6B0
0x1402bf519  call    cs:__imp_KeEnterCriticalRegion
0x1402bf520  nop     dword ptr [rax+rax+00h]
0x1402bf525  cmp     [rbp+1E4h], r12b
0x1402bf52c  jz      short loc_1402BF536
0x1402bf52e  mov     rcx, rbp
0x1402bf531  call    DpiCheckForOutstandingD3Requests
0x1402bf536  mov     rcx, [rbp+0A8h]; Resource
0x1402bf53d  mov     dl, 1; Wait
0x1402bf53f  call    cs:__imp_ExAcquireResourceSharedLite
0x1402bf546  nop     dword ptr [rax+rax+00h]
0x1402bf54b  movsxd  rax, dword ptr [rbp+0ECh]
0x1402bf552  cmp     eax, 2
0x1402bf555  jnz     short loc_1402BF5C2
0x1402bf557  cmp     dword ptr [rbp+1018h], 1
0x1402bf55e  jz      short loc_1402BF598
0x1402bf560  cmp     dword ptr [rbp+11Ch], 1
0x1402bf567  jnz     short loc_1402BF598
0x1402bf569  mov     al, [r14+2Ah]
0x1402bf56d  mov     r9b, [r14+29h]
0x1402bf571  mov     r8b, [r14+28h]
0x1402bf575  mov     edx, [r14+20h]
0x1402bf579  mov     rcx, [r14+18h]
0x1402bf57d  mov     [rsp+98h+var_68], r13
0x1402bf582  mov     [rsp+98h+var_70], 1
0x1402bf587  mov     byte ptr [rsp+98h+Timeout], al
0x1402bf58b  call    DpiFdoInvalidateChildStatus
0x1402bf590  mov     r15d, eax
0x1402bf593  jmp     loc_1402BF67F
0x1402bf598  mov     r15d, 0C00000A3h
0x1402bf59e  movsxd  rdx, dword ptr [rbp+11Ch]
0x1402bf5a5  mov     ecx, 3
0x1402bf5aa  call    cs:__imp_WdLogSingleEntry1
0x1402bf5b1  nop     dword ptr [rax+rax+00h]
0x1402bf5b6  mov     cs:WdLogGlobalForLineNumber, 1961h
0x1402bf5c0  jmp     short loc_1402BF5E6
0x1402bf5c2  mov     r15d, 0C000000Eh
0x1402bf5c8  mov     rdx, rax
0x1402bf5cb  mov     ecx, 3
0x1402bf5d0  call    cs:__imp_WdLogSingleEntry1
0x1402bf5d7  nop     dword ptr [rax+rax+00h]
0x1402bf5dc  mov     cs:WdLogGlobalForLineNumber, 1959h
0x1402bf5e6  call    cs:__imp_KeEnterCriticalRegion
0x1402bf5ed  nop     dword ptr [rax+rax+00h]
0x1402bf5f2  lea     rsi, [rbp+0D70h]
0x1402bf5f9  mov     dl, 1; Wait
0x1402bf5fb  mov     rcx, rsi; Resource
0x1402bf5fe  call    cs:__imp_ExAcquireResourceSharedLite
0x1402bf605  nop     dword ptr [rax+rax+00h]
0x1402bf60a  mov     edx, [r14+20h]
0x1402bf60e  mov     rcx, rbp
0x1402bf611  call    DpiFdoGetChildDescriptor
0x1402bf616  lea     rdi, [rbp+0DD8h]
0x1402bf61d  mov     [rsp+98h+Timeout], 0; Timeout
0x1402bf626  mov     rcx, rdi; Object
0x1402bf629  xor     r9d, r9d; Alertable
0x1402bf62c  xor     r8d, r8d; WaitMode
0x1402bf62f  xor     edx, edx; WaitReason
0x1402bf631  mov     rbx, rax
0x1402bf634  call    cs:__imp_KeWaitForSingleObject
0x1402bf63b  nop     dword ptr [rax+rax+00h]
0x1402bf640  mov     rcx, [r14+18h]
0x1402bf644  mov     rdx, rbx
0x1402bf647  call    DpiFdoPendingCreatePdoCompletion
0x1402bf64c  xor     edx, edx; Wait
0x1402bf64e  mov     rcx, rdi; Mutex
0x1402bf651  call    cs:__imp_KeReleaseMutex
0x1402bf658  nop     dword ptr [rax+rax+00h]
0x1402bf65d  mov     rcx, rsi; Resource
0x1402bf660  call    cs:__imp_ExReleaseResourceLite
0x1402bf667  nop     dword ptr [rax+rax+00h]
0x1402bf66c  call    cs:__imp_KeLeaveCriticalRegion
0x1402bf673  nop     dword ptr [rax+rax+00h]
0x1402bf678  lea     rbx, qword_14015F060
0x1402bf67f  cmp     byte ptr [rbp+1E4h], 0
0x1402bf686  jz      short loc_1402BF691
0x1402bf688  mov     rcx, [rbp+18h]
0x1402bf68c  call    DpiEnableD3Requests
0x1402bf691  mov     rcx, [rbp+0A8h]; Resource
0x1402bf698  call    cs:__imp_ExReleaseResourceLite
0x1402bf69f  nop     dword ptr [rax+rax+00h]
0x1402bf6a4  call    cs:__imp_KeLeaveCriticalRegion
0x1402bf6ab  nop     dword ptr [rax+rax+00h]
0x1402bf6b0  lea     rcx, [rbp+40h]; RemoveLock
0x1402bf6b4  mov     r8d, 20h ; ' '; RemlockSize
0x1402bf6ba  mov     rdx, r14; Tag
0x1402bf6bd  call    cs:__imp_IoReleaseRemoveLockEx
0x1402bf6c4  nop     dword ptr [rax+rax+00h]
0x1402bf6c9  mov     rdx, r14; Entry
0x1402bf6cc  lea     rcx, stru_14015EEC0; Lookaside
0x1402bf6d3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402bf6da  nop     dword ptr [rax+rax+00h]
0x1402bf6df  cmp     r15d, 103h
0x1402bf6e6  jnz     loc_1402BF48B
0x1402bf6ec  xor     eax, eax
0x1402bf6ee  lea     r8, stru_14015F010; Dpc
0x1402bf6f5  xchg    eax, cs:dword_14015F058
0x1402bf6fb  mov     rdx, 0FFFFFFFFFFD23940h; DueTime
0x1402bf702  lea     rcx, stru_14015EFD0; Timer
0x1402bf709  call    cs:__imp_KeSetTimer
0x1402bf710  nop     dword ptr [rax+rax+00h]
0x1402bf715  lea     rcx, [rsp+98h+var_58]; this
0x1402bf71a  call    ??1CDisplayScenarioContextScope@@QEAA@XZ; CDisplayScenarioContextScope::~CDisplayScenarioContextScope(void)
0x1402bf71f  add     rsp, 58h
0x1402bf723  pop     r15
0x1402bf725  pop     r14
0x1402bf727  pop     r13
0x1402bf729  pop     r12
0x1402bf72b  pop     rdi
0x1402bf72c  pop     rsi
0x1402bf72d  pop     rbp
0x1402bf72e  pop     rbx
0x1402bf72f  retn
0x1402bf731  mov     ecx, 3
0x1402bf736  int     29h; Win8: RtlFailFast(ecx)
```
