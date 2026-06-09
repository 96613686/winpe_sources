# FveQueueDelayedAutoWorkItemEx

- ea: `0x14002cc38`
- end: `0x14002d074`
- name: `FveQueueDelayedAutoWorkItemEx`
- size: `1084`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, __int64, __int64, __int64, __int64, LARGE_INTEGER DueTime)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140026aa4`
- `0x14002cbe0`
- `0x14002f124`

## callees

- `0x140029a38`
- `0x14002cc38`
- `0x14002d080`
- `0x14002d8e8`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14002cdd1`
- `ntoskrnl!ObfReferenceObject` at `0x14002cdd1`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002cc71`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002cc71`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14002cee2`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14002cee2`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002cf6a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002cf6a`
- `ntoskrnl!IoFreeWorkItem` at `0x14002d042`
- `ntoskrnl!IoFreeWorkItem` at `0x14002d042`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002cd16`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002cd16`
- `ntoskrnl!KeInitializeTimer` at `0x14002ce49`
- `ntoskrnl!KeInitializeTimer` at `0x14002ce49`
- `ntoskrnl!KeInitializeDpc` at `0x14002ce62`
- `ntoskrnl!KeInitializeDpc` at `0x14002ce62`
- `ntoskrnl!KeSetTimer` at `0x14002ce9a`
- `ntoskrnl!KeSetTimer` at `0x14002ce9a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cdf1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ceb7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cfeb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cdf1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ceb7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cfeb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002cca9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002cca9`
- `ntoskrnl!KeBugCheckEx` at `0x14002cf4f`
- `ntoskrnl!KeBugCheckEx` at `0x14002cf4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d008`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d028`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d056`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d008`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d028`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d056`
- `ntoskrnl!ExAllocatePool2` at `0x14002ccfa`
- `ntoskrnl!ExAllocatePool2` at `0x14002cfa2`
- `ntoskrnl!ExAllocatePool2` at `0x14002cfc2`
- `ntoskrnl!ExAllocatePool2` at `0x14002ccfa`
- `ntoskrnl!ExAllocatePool2` at `0x14002cfa2`
- `ntoskrnl!ExAllocatePool2` at `0x14002cfc2`

## pseudocode

```c
__int64 __fastcall FveQueueDelayedAutoWorkItemEx(
        __int64 a1,
        void (__fastcall *a2)(PIRP Irp),
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        LARGE_INTEGER DueTime)
{
  ULONG_PTR v11; // r14
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v13; // rcx
  int v14; // r13d
  unsigned int v15; // edi
  ULONG_PTR v16; // rdx
  struct _KDPC *v17; // rbp
  struct _KTIMER *Pool2; // r15
  _QWORD *v19; // rsi
  LARGE_INTEGER v20; // rbx
  PIO_WORKITEM WorkItem; // rax
  _QWORD *v23; // rcx
  signed __int64 v24; // rax
  __int64 SystemUpTime; // rax
  struct _IO_WORKITEM *v26; // rcx
  KIRQL NewIrql; // [rsp+90h] [rbp+8h]
  signed __int64 NewIrqla; // [rsp+90h] [rbp+8h]

  v11 = a1 + 56;
  v13 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(a1 + 104);
  v14 = 1;
  if ( v13 )
  {
    v15 = -1073741738;
    LODWORD(v16) = ExAcquireRundownProtectionCacheAware(v13) == 0 ? 0xC0000056 : 0;
  }
  else
  {
    v16 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v11 + 16), *(PVOID *)v11, File, 1u, 0x20u);
    while ( 1 )
    {
      v15 = -1073741738;
      NewIrqla = *(_QWORD *)(v11 + 8);
      v24 = NewIrqla;
      if ( (NewIrqla & 0xFF000000000000LL) != 0 )
        break;
      if ( (_DWORD)v16 )
        KeBugCheckEx(0x120u, 0xEu, v11, v16, (unsigned int)NewIrqla);
      LODWORD(NewIrqla) = NewIrqla + 1;
      if ( v24 == _InterlockedCompareExchange64((volatile signed __int64 *)(v11 + 8), NewIrqla, v24) )
        goto LABEL_3;
    }
    if ( !(_DWORD)v16 )
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v11 + 16), *(PVOID *)v11, 0x20u);
    LODWORD(v16) = -1073741738;
  }
LABEL_3:
  if ( (v16 & 0x80000000) != 0LL )
    return (unsigned int)v16;
  v17 = 0;
  Pool2 = 0;
  v19 = 0;
  NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 936));
  if ( *(_DWORD *)(a1 + 948) )
    goto LABEL_39;
  if ( DueTime.QuadPart > 0 )
  {
    SystemUpTime = FveGetSystemUpTime();
    v20.QuadPart = SystemUpTime - DueTime.QuadPart;
    if ( SystemUpTime >= DueTime.QuadPart )
      v20.QuadPart = 0;
  }
  else
  {
    v20 = DueTime;
  }
  if ( v20.QuadPart
    && ((Pool2 = (struct _KTIMER *)ExAllocatePool2(64, 64, 809850438)) == 0
     || (v17 = (struct _KDPC *)ExAllocatePool2(64, 64, 809850438)) == 0)
    || (v19 = (_QWORD *)ExAllocatePool2(64, 120, 809850438)) == 0
    || (WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)a1), (v19[3] = WorkItem) == 0) )
  {
    v15 = -1073741670;
LABEL_39:
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 936), NewIrql);
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0x30455646u);
    goto LABEL_15;
  }
  v15 = 0;
  if ( a6 )
  {
    v15 = 259;
    *(_BYTE *)(*(_QWORD *)(a4 + 184) + 3LL) |= 1u;
  }
  v19[1] = v19;
  *v19 = v19;
  v19[8] = a3;
  v19[10] = a5;
  v19[11] = a7;
  v19[12] = a8;
  v19[13] = a9;
  v19[14] = a10;
  v19[4] = Pool2;
  v19[5] = v17;
  v19[6] = a1;
  *((_BYTE *)v19 + 16) = a2 == IoctlFveWorker;
  v19[7] = a2;
  v19[9] = a4;
  ObfReferenceObject(*(PVOID *)a1);
  if ( Pool2 )
  {
    KeInitializeTimer(Pool2);
    KeInitializeDpc(v17, FveWorkerAutoWorkerDpc, v19);
    v23 = *(_QWORD **)(a1 + 928);
    if ( *v23 != a1 + 920 )
      __fastfail(3u);
    v19[1] = v23;
    *v19 = a1 + 920;
    *v23 = v19;
    *(_QWORD *)(a1 + 928) = v19;
    KeSetTimer(Pool2, v20, v17);
    v17 = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 936), NewIrql);
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 936), NewIrql);
    FveWorkerAutoWorkerDpc(v17, v19, 0, 0);
  }
  v14 = 0;
  v19 = 0;
LABEL_15:
  if ( v17 )
    ExFreePoolWithTag(v17, 0x30455646u);
  if ( v19 )
  {
    v26 = (struct _IO_WORKITEM *)v19[3];
    if ( v26 )
      IoFreeWorkItem(v26);
    ExFreePoolWithTag(v19, 0x30455646u);
  }
  if ( v14 )
    FvepReleaseRemoveLock(v11);
  return v15;
}

```

## disassembly

```asm
0x14002cc38  mov     [rsp+arg_18], r9
0x14002cc3d  mov     [rsp+arg_10], r8
0x14002cc42  mov     [rsp+arg_8], rdx
0x14002cc47  push    rbx
0x14002cc48  push    rbp
0x14002cc49  push    rsi
0x14002cc4a  push    rdi
0x14002cc4b  push    r12
0x14002cc4d  push    r13
0x14002cc4f  push    r14
0x14002cc51  push    r15
0x14002cc53  sub     rsp, 48h
0x14002cc57  lea     r14, [rcx+38h]
0x14002cc5b  mov     r12, rcx
0x14002cc5e  mov     rcx, [r14+30h]; RunRefCacheAware
0x14002cc62  mov     r13d, 1
0x14002cc68  test    rcx, rcx
0x14002cc6b  jz      loc_14002CEC8
0x14002cc71  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14002cc78  nop     dword ptr [rax+rax+00h]
0x14002cc7d  neg     al
0x14002cc7f  mov     edi, 0C0000056h
0x14002cc84  sbb     edx, edx
0x14002cc86  not     edx
0x14002cc88  and     edx, edi
0x14002cc8a  test    edx, edx
0x14002cc8c  js      loc_14002CE42
0x14002cc92  lea     rax, [r12+3A8h]
0x14002cc9a  xor     ebp, ebp
0x14002cc9c  mov     rcx, rax; SpinLock
0x14002cc9f  mov     [rsp+88h+SpinLock], rax
0x14002cca4  xor     r15d, r15d
0x14002cca7  xor     esi, esi
0x14002cca9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002ccb0  nop     dword ptr [rax+rax+00h]
0x14002ccb5  mov     [rsp+88h+NewIrql], al
0x14002ccbc  cmp     [r12+3B4h], esi
0x14002ccc4  jnz     loc_14002CFDF
0x14002ccca  mov     rdi, qword ptr [rsp+88h+DueTime]
0x14002ccd2  test    rdi, rdi
0x14002ccd5  jg      loc_14002CF7D
0x14002ccdb  mov     rbx, rdi
0x14002ccde  mov     edi, 40h ; '@'
0x14002cce3  test    rbx, rbx
0x14002cce6  jnz     loc_14002CF96
0x14002ccec  mov     edx, 78h ; 'x'
0x14002ccf1  mov     r8d, 30455646h
0x14002ccf7  mov     rcx, rdi
0x14002ccfa  call    cs:__imp_ExAllocatePool2
0x14002cd01  nop     dword ptr [rax+rax+00h]
0x14002cd06  mov     rsi, rax
0x14002cd09  test    rax, rax
0x14002cd0c  jz      loc_14002CFDA
0x14002cd12  mov     rcx, [r12]; DeviceObject
0x14002cd16  call    cs:__imp_IoAllocateWorkItem
0x14002cd1d  nop     dword ptr [rax+rax+00h]
0x14002cd22  mov     [rsi+18h], rax
0x14002cd26  test    rax, rax
0x14002cd29  jz      loc_14002CFDA
0x14002cd2f  mov     rcx, [rsp+88h+arg_18]
0x14002cd37  xor     edi, edi
0x14002cd39  cmp     [rsp+88h+arg_28], edi
0x14002cd40  jz      short loc_14002CD52
0x14002cd42  mov     rax, [rcx+0B8h]
0x14002cd49  mov     edi, 103h
0x14002cd4e  or      [rax+3], r13b
0x14002cd52  mov     rdx, [rsp+88h+arg_8]
0x14002cd5a  mov     rax, [rsp+88h+arg_10]
0x14002cd62  mov     [rsi+8], rsi
0x14002cd66  mov     [rsi], rsi
0x14002cd69  mov     [rsi+40h], rax
0x14002cd6d  mov     rax, [rsp+88h+arg_20]
0x14002cd75  mov     [rsi+50h], rax
0x14002cd79  mov     rax, [rsp+88h+arg_30]
0x14002cd81  mov     [rsi+58h], rax
0x14002cd85  mov     rax, [rsp+88h+arg_38]
0x14002cd8d  mov     [rsi+60h], rax
0x14002cd91  mov     rax, [rsp+88h+arg_40]
0x14002cd99  mov     [rsi+68h], rax
0x14002cd9d  mov     rax, [rsp+88h+arg_48]
0x14002cda5  mov     [rsi+70h], rax
0x14002cda9  lea     rax, IoctlFveWorker
0x14002cdb0  cmp     rdx, rax
0x14002cdb3  mov     [rsi+20h], r15
0x14002cdb7  mov     [rsi+28h], rbp
0x14002cdbb  setz    al
0x14002cdbe  mov     [rsi+30h], r12
0x14002cdc2  mov     [rsi+10h], al
0x14002cdc5  mov     [rsi+38h], rdx
0x14002cdc9  mov     [rsi+48h], rcx
0x14002cdcd  mov     rcx, [r12]; Object
0x14002cdd1  call    cs:__imp_ObfReferenceObject
0x14002cdd8  nop     dword ptr [rax+rax+00h]
0x14002cddd  test    r15, r15
0x14002cde0  jnz     short loc_14002CE46
0x14002cde2  mov     dl, [rsp+88h+NewIrql]; NewIrql
0x14002cde9  lea     rcx, [r12+3A8h]; SpinLock
0x14002cdf1  call    cs:__imp_KeReleaseSpinLock
0x14002cdf8  nop     dword ptr [rax+rax+00h]
0x14002cdfd  xor     r9d, r9d; SystemArgument2
0x14002ce00  xor     r8d, r8d; SystemArgument1
0x14002ce03  mov     rdx, rsi; DeferredContext
0x14002ce06  mov     rcx, rbp; Dpc
0x14002ce09  call    FveWorkerAutoWorkerDpc
0x14002ce0e  xor     r13d, r13d
0x14002ce11  xor     esi, esi
0x14002ce13  test    rbp, rbp
0x14002ce16  jnz     loc_14002D020
0x14002ce1c  test    rsi, rsi
0x14002ce1f  jnz     loc_14002D039
0x14002ce25  test    r13d, r13d
0x14002ce28  jnz     loc_14002D067
0x14002ce2e  mov     eax, edi
0x14002ce30  add     rsp, 48h
0x14002ce34  pop     r15
0x14002ce36  pop     r14
0x14002ce38  pop     r13
0x14002ce3a  pop     r12
0x14002ce3c  pop     rdi
0x14002ce3d  pop     rsi
0x14002ce3e  pop     rbp
0x14002ce3f  pop     rbx
0x14002ce40  retn
0x14002ce42  mov     edi, edx
0x14002ce44  jmp     short loc_14002CE2E
0x14002ce46  mov     rcx, r15; Timer
0x14002ce49  call    cs:__imp_KeInitializeTimer
0x14002ce50  nop     dword ptr [rax+rax+00h]
0x14002ce55  mov     r8, rsi; DeferredContext
0x14002ce58  lea     rdx, FveWorkerAutoWorkerDpc; DeferredRoutine
0x14002ce5f  mov     rcx, rbp; Dpc
0x14002ce62  call    cs:__imp_KeInitializeDpc
0x14002ce69  nop     dword ptr [rax+rax+00h]
0x14002ce6e  lea     rax, [r12+398h]
0x14002ce76  mov     rcx, [rax+8]
0x14002ce7a  cmp     [rcx], rax
0x14002ce7d  jnz     loc_14002D019
0x14002ce83  mov     [rsi+8], rcx
0x14002ce87  mov     r8, rbp; Dpc
0x14002ce8a  mov     [rsi], rax
0x14002ce8d  mov     rdx, rbx; DueTime
0x14002ce90  mov     [rcx], rsi
0x14002ce93  mov     rcx, r15; Timer
0x14002ce96  mov     [rax+8], rsi
0x14002ce9a  call    cs:__imp_KeSetTimer
0x14002cea1  nop     dword ptr [rax+rax+00h]
0x14002cea6  mov     dl, [rsp+88h+NewIrql]; NewIrql
0x14002cead  lea     rcx, [r12+3A8h]; SpinLock
0x14002ceb5  xor     ebp, ebp
0x14002ceb7  call    cs:__imp_KeReleaseSpinLock
0x14002cebe  nop     dword ptr [rax+rax+00h]
0x14002cec3  jmp     loc_14002CE0E
0x14002cec8  mov     rdx, [r14]; Tag
0x14002cecb  lea     r8, File; File
0x14002ced2  mov     esi, 20h ; ' '
0x14002ced7  lea     rcx, [r14+10h]; RemoveLock
0x14002cedb  mov     r9d, r13d; Line
0x14002cede  mov     [rsp+88h+RemlockSize], esi; RemlockSize
0x14002cee2  call    cs:__imp_IoAcquireRemoveLockEx
0x14002cee9  nop     dword ptr [rax+rax+00h]
0x14002ceee  movsxd  rdx, eax
0x14002cef1  mov     rax, [r14+8]
0x14002cef5  mov     edi, 0C0000056h
0x14002cefa  mov     rcx, rax
0x14002cefd  mov     qword ptr [rsp+88h+NewIrql], rax
0x14002cf05  shr     rcx, 20h
0x14002cf09  test    ecx, 0FF0000h
0x14002cf0f  jnz     short loc_14002CF5C
0x14002cf11  test    edx, edx
0x14002cf13  jnz     short loc_14002CF33
0x14002cf15  add     dword ptr [rsp+88h+NewIrql], r13d
0x14002cf1d  mov     rcx, qword ptr [rsp+88h+NewIrql]
0x14002cf25  lock cmpxchg [r14+8], rcx
0x14002cf2b  jz      loc_14002CC8A
0x14002cf31  jmp     short loc_14002CEF1
0x14002cf33  mov     eax, dword ptr [rsp+88h+NewIrql]
0x14002cf3a  mov     r9, rdx; BugCheckParameter3
0x14002cf3d  mov     edx, 0Eh; BugCheckParameter1
0x14002cf42  mov     qword ptr [rsp+88h+RemlockSize], rax; BugCheckParameter4
0x14002cf47  mov     r8, r14; BugCheckParameter2
0x14002cf4a  mov     ecx, 120h; BugCheckCode
0x14002cf4f  call    cs:__imp_KeBugCheckEx
0x14002cf5c  test    edx, edx
0x14002cf5e  jnz     short loc_14002CF76
0x14002cf60  mov     rdx, [r14]; Tag
0x14002cf63  lea     rcx, [r14+10h]; RemoveLock
0x14002cf67  mov     r8d, esi; RemlockSize
0x14002cf6a  call    cs:__imp_IoReleaseRemoveLockEx
0x14002cf71  nop     dword ptr [rax+rax+00h]
0x14002cf76  mov     edx, edi
0x14002cf78  jmp     loc_14002CC8A
0x14002cf7d  call    FveGetSystemUpTime
0x14002cf82  xor     ecx, ecx
0x14002cf84  mov     rbx, rax
0x14002cf87  sub     rbx, rdi
0x14002cf8a  cmp     rax, rdi
0x14002cf8d  cmovge  rbx, rcx
0x14002cf91  jmp     loc_14002CCDE
0x14002cf96  mov     r8d, 30455646h
0x14002cf9c  mov     rdx, rdi
0x14002cf9f  mov     rcx, rdi
0x14002cfa2  call    cs:__imp_ExAllocatePool2
0x14002cfa9  nop     dword ptr [rax+rax+00h]
0x14002cfae  mov     r15, rax
0x14002cfb1  test    rax, rax
0x14002cfb4  jz      short loc_14002CFDA
0x14002cfb6  mov     r8d, 30455646h
0x14002cfbc  mov     rdx, rdi
0x14002cfbf  mov     rcx, rdi
0x14002cfc2  call    cs:__imp_ExAllocatePool2
0x14002cfc9  nop     dword ptr [rax+rax+00h]
0x14002cfce  mov     rbp, rax
0x14002cfd1  test    rax, rax
0x14002cfd4  jnz     loc_14002CCEC
0x14002cfda  mov     edi, 0C000009Ah
0x14002cfdf  mov     dl, [rsp+88h+NewIrql]; NewIrql
0x14002cfe6  mov     rcx, [rsp+88h+SpinLock]; SpinLock
0x14002cfeb  call    cs:__imp_KeReleaseSpinLock
0x14002cff2  nop     dword ptr [rax+rax+00h]
0x14002cff7  test    r15, r15
0x14002cffa  jz      loc_14002CE13
0x14002d000  mov     edx, 30455646h; Tag
0x14002d005  mov     rcx, r15; P
0x14002d008  call    cs:__imp_ExFreePoolWithTag
0x14002d00f  nop     dword ptr [rax+rax+00h]
0x14002d014  jmp     loc_14002CE13
0x14002d019  mov     ecx, 3
0x14002d01e  int     29h; Win8: RtlFailFast(ecx)
0x14002d020  mov     edx, 30455646h; Tag
0x14002d025  mov     rcx, rbp; P
0x14002d028  call    cs:__imp_ExFreePoolWithTag
0x14002d02f  nop     dword ptr [rax+rax+00h]
0x14002d034  jmp     loc_14002CE1C
0x14002d039  mov     rcx, [rsi+18h]; IoWorkItem
0x14002d03d  test    rcx, rcx
0x14002d040  jz      short loc_14002D04E
0x14002d042  call    cs:__imp_IoFreeWorkItem
0x14002d049  nop     dword ptr [rax+rax+00h]
0x14002d04e  mov     edx, 30455646h; Tag
0x14002d053  mov     rcx, rsi; P
0x14002d056  call    cs:__imp_ExFreePoolWithTag
0x14002d05d  nop     dword ptr [rax+rax+00h]
0x14002d062  jmp     loc_14002CE25
0x14002d067  mov     rcx, r14; BugCheckParameter2
0x14002d06a  call    FvepReleaseRemoveLock
0x14002d06f  jmp     loc_14002CE2E
```
