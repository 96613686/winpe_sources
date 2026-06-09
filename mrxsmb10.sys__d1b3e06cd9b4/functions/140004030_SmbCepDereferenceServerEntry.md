# SmbCepDereferenceServerEntry

- ea: `0x140004030`
- end: `0x1400041a5`
- name: `SmbCepDereferenceServerEntry`
- size: `373`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `18`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140002050`
- `0x140002614`
- `0x140003450`
- `0x14000cc00`
- `0x14000d314`
- `0x140011590`
- `0x140013660`
- `0x140013700`
- `0x140014a70`
- `0x140028310`
- `0x1400358dc`
- `0x140038f6c`
- `0x1400394f0`
- `0x14003e06c`
- `0x14003e364`
- `0x14003e934`
- `0x140042ee0`
- `0x14004eb70`

## callees

- `0x140004030`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000412f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000412f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004077`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004077`
- `ntoskrnl!KeSetEvent` at `0x14000410a`
- `ntoskrnl!KeSetEvent` at `0x14000410a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000414e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000414e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004142`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004142`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004064`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004064`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000404b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000404b`
- `rdbss!RxPostToWorkerThread` at `0x140004188`
- `rdbss!RxPostToWorkerThread` at `0x140004188`
- `mrxsmb!MRxSmbCancelRecurrentService` at `0x1400040db`
- `mrxsmb!MRxSmbCancelRecurrentService` at `0x1400040db`
- `mrxsmb!MRxSmbDeviceObject` at `0x14000415f`

## pseudocode

```c
void __fastcall SmbCepDereferenceServerEntry(char *pContext)
{
  char v2; // di
  char **v3; // rcx
  PVOID *v4; // rdx

  if ( pContext )
  {
    KeEnterCriticalRegion();
    v2 = 1;
    ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
    s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)pContext + 2, 0xFFFFFFFF) != 1 || *((_DWORD *)pContext + 2) )
    {
      v2 = 0;
    }
    else
    {
      *((_DWORD *)pContext + 3) = 9;
      v3 = (char **)*((_QWORD *)pContext + 4);
      if ( v3[1] != pContext + 32 || (v4 = (PVOID *)*((_QWORD *)pContext + 5), *v4 != pContext + 32) )
        __fastfail(3u);
      *v4 = v3;
      v3[1] = (char *)v4;
      if ( (__int64 *)s_DbServers == &s_DbServers )
        MRxSmbCancelRecurrentService(MRxSmbEchoProbeServiceContext);
      if ( (__int64 *)s_DbServers == &s_DbServers || s_DbServers == 32 )
      {
        if ( Event )
          KeSetEvent(Event, 0, 0);
      }
    }
    KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
    ExReleaseResourceLite(&s_SmbCeDbResource);
    KeLeaveCriticalRegion();
    if ( v2 )
    {
      *((_QWORD *)pContext + 34) = pContext + 264;
      *((_QWORD *)pContext + 33) = pContext + 264;
      RxPostToWorkerThread(
        MRxSmbDeviceObject,
        BackgroundWorkQueue,
        (PRX_WORK_QUEUE_ITEM)(pContext + 264),
        SmbCeTearDownServerEntry,
        pContext);
    }
  }
}

```

## disassembly

```asm
0x140004030  test    rcx, rcx
0x140004033  jz      locret_1400041A3
0x140004039  mov     [rsp+arg_8], rbx
0x14000403e  mov     [rsp+arg_10], rsi
0x140004043  push    rdi
0x140004044  sub     rsp, 30h
0x140004048  mov     rbx, rcx
0x14000404b  call    cs:__imp_KeEnterCriticalRegion
0x140004052  nop     dword ptr [rax+rax+00h]
0x140004057  mov     dil, 1
0x14000405a  lea     rcx, s_SmbCeDbResource; Resource
0x140004061  mov     dl, dil; Wait
0x140004064  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000406b  nop     dword ptr [rax+rax+00h]
0x140004070  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140004077  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000407e  nop     dword ptr [rax+rax+00h]
0x140004083  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140004089  or      eax, 0FFFFFFFFh
0x14000408c  lock xadd [rbx+8], eax
0x140004091  cmp     eax, 1
0x140004094  jnz     loc_14000411F
0x14000409a  cmp     dword ptr [rbx+8], 0
0x14000409e  jnz     short loc_14000411F
0x1400040a0  lea     rax, [rbx+20h]
0x1400040a4  mov     dword ptr [rbx+0Ch], 9
0x1400040ab  mov     rcx, [rax]
0x1400040ae  cmp     [rcx+8], rax
0x1400040b2  jnz     short loc_140004118
0x1400040b4  mov     rdx, [rax+8]
0x1400040b8  cmp     [rdx], rax
0x1400040bb  jnz     short loc_140004118
0x1400040bd  mov     [rdx], rcx
0x1400040c0  lea     rsi, s_DbServers
0x1400040c7  mov     [rcx+8], rdx
0x1400040cb  cmp     cs:s_DbServers, rsi
0x1400040d2  jnz     short loc_1400040E7
0x1400040d4  lea     rcx, MRxSmbEchoProbeServiceContext
0x1400040db  call    cs:__imp_MRxSmbCancelRecurrentService
0x1400040e2  nop     dword ptr [rax+rax+00h]
0x1400040e7  mov     rax, cs:s_DbServers
0x1400040ee  cmp     rax, rsi
0x1400040f1  jz      short loc_1400040F9
0x1400040f3  add     rax, 0FFFFFFFFFFFFFFE0h
0x1400040f7  jnz     short loc_140004122
0x1400040f9  mov     rcx, cs:Event; Event
0x140004100  test    rcx, rcx
0x140004103  jz      short loc_140004122
0x140004105  xor     r8d, r8d; Wait
0x140004108  xor     edx, edx; Increment
0x14000410a  call    cs:__imp_KeSetEvent
0x140004111  nop     dword ptr [rax+rax+00h]
0x140004116  jmp     short loc_140004122
0x140004118  mov     ecx, 3
0x14000411d  int     29h; Win8: RtlFailFast(ecx)
0x14000411f  xor     dil, dil
0x140004122  mov     dl, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x140004128  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000412f  call    cs:__imp_KeReleaseSpinLock
0x140004136  nop     dword ptr [rax+rax+00h]
0x14000413b  lea     rcx, s_SmbCeDbResource; Resource
0x140004142  call    cs:__imp_ExReleaseResourceLite
0x140004149  nop     dword ptr [rax+rax+00h]
0x14000414e  call    cs:__imp_KeLeaveCriticalRegion
0x140004155  nop     dword ptr [rax+rax+00h]
0x14000415a  test    dil, dil
0x14000415d  jz      short loc_140004194
0x14000415f  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140004166  lea     r8, [rbx+108h]; pWorkQueueItem
0x14000416d  mov     [r8+8], r8
0x140004171  lea     r9, SmbCeTearDownServerEntry; Routine
0x140004178  mov     [r8], r8
0x14000417b  mov     edx, 4; WorkQueueType
0x140004180  mov     [rsp+38h+pContext], rbx; pContext
0x140004185  mov     rcx, [rcx]; pMRxDeviceObject
0x140004188  call    cs:__imp_RxPostToWorkerThread
0x14000418f  nop     dword ptr [rax+rax+00h]
0x140004194  mov     rbx, [rsp+38h+arg_8]
0x140004199  mov     rsi, [rsp+38h+arg_10]
0x14000419e  add     rsp, 30h
0x1400041a2  pop     rdi
0x1400041a3  retn
```
