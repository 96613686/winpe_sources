# FveQueueDelayedAutoWorkItemEx

- ea: `0x14002dc38`
- end: `0x14002e074`
- name: `FveQueueDelayedAutoWorkItemEx`
- size: `1084`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, __int64, __int64, __int64, __int64, LARGE_INTEGER DueTime)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140027aa4`
- `0x14002dbe0`
- `0x140030124`

## callees

- `0x14002aa38`
- `0x14002dc38`
- `0x14002e080`
- `0x14002e8e8`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14002ddd1`
- `ntoskrnl!ObfReferenceObject` at `0x14002ddd1`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002dc71`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002dc71`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14002dee2`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14002dee2`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002df6a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002df6a`
- `ntoskrnl!IoFreeWorkItem` at `0x14002e042`
- `ntoskrnl!IoFreeWorkItem` at `0x14002e042`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002dd16`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002dd16`
- `ntoskrnl!KeInitializeTimer` at `0x14002de49`
- `ntoskrnl!KeInitializeTimer` at `0x14002de49`
- `ntoskrnl!KeInitializeDpc` at `0x14002de62`
- `ntoskrnl!KeInitializeDpc` at `0x14002de62`
- `ntoskrnl!KeSetTimer` at `0x14002de9a`
- `ntoskrnl!KeSetTimer` at `0x14002de9a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ddf1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002deb7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002dfeb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ddf1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002deb7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002dfeb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002dca9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002dca9`
- `ntoskrnl!KeBugCheckEx` at `0x14002df4f`
- `ntoskrnl!KeBugCheckEx` at `0x14002df4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e008`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e028`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e056`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e008`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e028`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e056`
- `ntoskrnl!ExAllocatePool2` at `0x14002dcfa`
- `ntoskrnl!ExAllocatePool2` at `0x14002dfa2`
- `ntoskrnl!ExAllocatePool2` at `0x14002dfc2`
- `ntoskrnl!ExAllocatePool2` at `0x14002dcfa`
- `ntoskrnl!ExAllocatePool2` at `0x14002dfa2`
- `ntoskrnl!ExAllocatePool2` at `0x14002dfc2`

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
0x14002dc38  mov     [rsp+arg_18], r9
0x14002dc3d  mov     [rsp+arg_10], r8
0x14002dc42  mov     [rsp+arg_8], rdx
0x14002dc47  push    rbx
0x14002dc48  push    rbp
0x14002dc49  push    rsi
0x14002dc4a  push    rdi
0x14002dc4b  push    r12
0x14002dc4d  push    r13
0x14002dc4f  push    r14
0x14002dc51  push    r15
0x14002dc53  sub     rsp, 48h
0x14002dc57  lea     r14, [rcx+38h]
0x14002dc5b  mov     r12, rcx
0x14002dc5e  mov     rcx, [r14+30h]; RunRefCacheAware
0x14002dc62  mov     r13d, 1
0x14002dc68  test    rcx, rcx
0x14002dc6b  jz      loc_14002DEC8
0x14002dc71  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14002dc78  nop     dword ptr [rax+rax+00h]
0x14002dc7d  neg     al
0x14002dc7f  mov     edi, 0C0000056h
0x14002dc84  sbb     edx, edx
0x14002dc86  not     edx
0x14002dc88  and     edx, edi
0x14002dc8a  test    edx, edx
0x14002dc8c  js      loc_14002DE42
0x14002dc92  lea     rax, [r12+3A8h]
0x14002dc9a  xor     ebp, ebp
0x14002dc9c  mov     rcx, rax; SpinLock
0x14002dc9f  mov     [rsp+88h+SpinLock], rax
0x14002dca4  xor     r15d, r15d
0x14002dca7  xor     esi, esi
0x14002dca9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002dcb0  nop     dword ptr [rax+rax+00h]
0x14002dcb5  mov     [rsp+88h+NewIrql], al
0x14002dcbc  cmp     [r12+3B4h], esi
0x14002dcc4  jnz     loc_14002DFDF
0x14002dcca  mov     rdi, qword ptr [rsp+88h+DueTime]
0x14002dcd2  test    rdi, rdi
0x14002dcd5  jg      loc_14002DF7D
0x14002dcdb  mov     rbx, rdi
0x14002dcde  mov     edi, 40h ; '@'
0x14002dce3  test    rbx, rbx
0x14002dce6  jnz     loc_14002DF96
0x14002dcec  mov     edx, 78h ; 'x'
0x14002dcf1  mov     r8d, 30455646h
0x14002dcf7  mov     rcx, rdi
0x14002dcfa  call    cs:__imp_ExAllocatePool2
0x14002dd01  nop     dword ptr [rax+rax+00h]
0x14002dd06  mov     rsi, rax
0x14002dd09  test    rax, rax
0x14002dd0c  jz      loc_14002DFDA
0x14002dd12  mov     rcx, [r12]; DeviceObject
0x14002dd16  call    cs:__imp_IoAllocateWorkItem
0x14002dd1d  nop     dword ptr [rax+rax+00h]
0x14002dd22  mov     [rsi+18h], rax
0x14002dd26  test    rax, rax
0x14002dd29  jz      loc_14002DFDA
0x14002dd2f  mov     rcx, [rsp+88h+arg_18]
0x14002dd37  xor     edi, edi
0x14002dd39  cmp     [rsp+88h+arg_28], edi
0x14002dd40  jz      short loc_14002DD52
0x14002dd42  mov     rax, [rcx+0B8h]
0x14002dd49  mov     edi, 103h
0x14002dd4e  or      [rax+3], r13b
0x14002dd52  mov     rdx, [rsp+88h+arg_8]
0x14002dd5a  mov     rax, [rsp+88h+arg_10]
0x14002dd62  mov     [rsi+8], rsi
0x14002dd66  mov     [rsi], rsi
0x14002dd69  mov     [rsi+40h], rax
0x14002dd6d  mov     rax, [rsp+88h+arg_20]
0x14002dd75  mov     [rsi+50h], rax
0x14002dd79  mov     rax, [rsp+88h+arg_30]
0x14002dd81  mov     [rsi+58h], rax
0x14002dd85  mov     rax, [rsp+88h+arg_38]
0x14002dd8d  mov     [rsi+60h], rax
0x14002dd91  mov     rax, [rsp+88h+arg_40]
0x14002dd99  mov     [rsi+68h], rax
0x14002dd9d  mov     rax, [rsp+88h+arg_48]
0x14002dda5  mov     [rsi+70h], rax
0x14002dda9  lea     rax, IoctlFveWorker
0x14002ddb0  cmp     rdx, rax
0x14002ddb3  mov     [rsi+20h], r15
0x14002ddb7  mov     [rsi+28h], rbp
0x14002ddbb  setz    al
0x14002ddbe  mov     [rsi+30h], r12
0x14002ddc2  mov     [rsi+10h], al
0x14002ddc5  mov     [rsi+38h], rdx
0x14002ddc9  mov     [rsi+48h], rcx
0x14002ddcd  mov     rcx, [r12]; Object
0x14002ddd1  call    cs:__imp_ObfReferenceObject
0x14002ddd8  nop     dword ptr [rax+rax+00h]
0x14002dddd  test    r15, r15
0x14002dde0  jnz     short loc_14002DE46
0x14002dde2  mov     dl, [rsp+88h+NewIrql]; NewIrql
0x14002dde9  lea     rcx, [r12+3A8h]; SpinLock
0x14002ddf1  call    cs:__imp_KeReleaseSpinLock
0x14002ddf8  nop     dword ptr [rax+rax+00h]
0x14002ddfd  xor     r9d, r9d; SystemArgument2
0x14002de00  xor     r8d, r8d; SystemArgument1
0x14002de03  mov     rdx, rsi; DeferredContext
0x14002de06  mov     rcx, rbp; Dpc
0x14002de09  call    FveWorkerAutoWorkerDpc
0x14002de0e  xor     r13d, r13d
0x14002de11  xor     esi, esi
0x14002de13  test    rbp, rbp
0x14002de16  jnz     loc_14002E020
0x14002de1c  test    rsi, rsi
0x14002de1f  jnz     loc_14002E039
0x14002de25  test    r13d, r13d
0x14002de28  jnz     loc_14002E067
0x14002de2e  mov     eax, edi
0x14002de30  add     rsp, 48h
0x14002de34  pop     r15
0x14002de36  pop     r14
0x14002de38  pop     r13
0x14002de3a  pop     r12
0x14002de3c  pop     rdi
0x14002de3d  pop     rsi
0x14002de3e  pop     rbp
0x14002de3f  pop     rbx
0x14002de40  retn
0x14002de42  mov     edi, edx
0x14002de44  jmp     short loc_14002DE2E
0x14002de46  mov     rcx, r15; Timer
0x14002de49  call    cs:__imp_KeInitializeTimer
0x14002de50  nop     dword ptr [rax+rax+00h]
0x14002de55  mov     r8, rsi; DeferredContext
0x14002de58  lea     rdx, FveWorkerAutoWorkerDpc; DeferredRoutine
0x14002de5f  mov     rcx, rbp; Dpc
0x14002de62  call    cs:__imp_KeInitializeDpc
0x14002de69  nop     dword ptr [rax+rax+00h]
0x14002de6e  lea     rax, [r12+398h]
0x14002de76  mov     rcx, [rax+8]
0x14002de7a  cmp     [rcx], rax
0x14002de7d  jnz     loc_14002E019
0x14002de83  mov     [rsi+8], rcx
0x14002de87  mov     r8, rbp; Dpc
0x14002de8a  mov     [rsi], rax
0x14002de8d  mov     rdx, rbx; DueTime
0x14002de90  mov     [rcx], rsi
0x14002de93  mov     rcx, r15; Timer
0x14002de96  mov     [rax+8], rsi
0x14002de9a  call    cs:__imp_KeSetTimer
0x14002dea1  nop     dword ptr [rax+rax+00h]
0x14002dea6  mov     dl, [rsp+88h+NewIrql]; NewIrql
0x14002dead  lea     rcx, [r12+3A8h]; SpinLock
0x14002deb5  xor     ebp, ebp
0x14002deb7  call    cs:__imp_KeReleaseSpinLock
0x14002debe  nop     dword ptr [rax+rax+00h]
0x14002dec3  jmp     loc_14002DE0E
0x14002dec8  mov     rdx, [r14]; Tag
0x14002decb  lea     r8, File; File
0x14002ded2  mov     esi, 20h ; ' '
0x14002ded7  lea     rcx, [r14+10h]; RemoveLock
0x14002dedb  mov     r9d, r13d; Line
0x14002dede  mov     [rsp+88h+RemlockSize], esi; RemlockSize
0x14002dee2  call    cs:__imp_IoAcquireRemoveLockEx
0x14002dee9  nop     dword ptr [rax+rax+00h]
0x14002deee  movsxd  rdx, eax
0x14002def1  mov     rax, [r14+8]
0x14002def5  mov     edi, 0C0000056h
0x14002defa  mov     rcx, rax
0x14002defd  mov     qword ptr [rsp+88h+NewIrql], rax
0x14002df05  shr     rcx, 20h
0x14002df09  test    ecx, 0FF0000h
0x14002df0f  jnz     short loc_14002DF5C
0x14002df11  test    edx, edx
0x14002df13  jnz     short loc_14002DF33
0x14002df15  add     dword ptr [rsp+88h+NewIrql], r13d
0x14002df1d  mov     rcx, qword ptr [rsp+88h+NewIrql]
0x14002df25  lock cmpxchg [r14+8], rcx
0x14002df2b  jz      loc_14002DC8A
0x14002df31  jmp     short loc_14002DEF1
0x14002df33  mov     eax, dword ptr [rsp+88h+NewIrql]
0x14002df3a  mov     r9, rdx; BugCheckParameter3
0x14002df3d  mov     edx, 0Eh; BugCheckParameter1
0x14002df42  mov     qword ptr [rsp+88h+RemlockSize], rax; BugCheckParameter4
0x14002df47  mov     r8, r14; BugCheckParameter2
0x14002df4a  mov     ecx, 120h; BugCheckCode
0x14002df4f  call    cs:__imp_KeBugCheckEx
0x14002df5c  test    edx, edx
0x14002df5e  jnz     short loc_14002DF76
0x14002df60  mov     rdx, [r14]; Tag
0x14002df63  lea     rcx, [r14+10h]; RemoveLock
0x14002df67  mov     r8d, esi; RemlockSize
0x14002df6a  call    cs:__imp_IoReleaseRemoveLockEx
0x14002df71  nop     dword ptr [rax+rax+00h]
0x14002df76  mov     edx, edi
0x14002df78  jmp     loc_14002DC8A
0x14002df7d  call    FveGetSystemUpTime
0x14002df82  xor     ecx, ecx
0x14002df84  mov     rbx, rax
0x14002df87  sub     rbx, rdi
0x14002df8a  cmp     rax, rdi
0x14002df8d  cmovge  rbx, rcx
0x14002df91  jmp     loc_14002DCDE
0x14002df96  mov     r8d, 30455646h
0x14002df9c  mov     rdx, rdi
0x14002df9f  mov     rcx, rdi
0x14002dfa2  call    cs:__imp_ExAllocatePool2
0x14002dfa9  nop     dword ptr [rax+rax+00h]
0x14002dfae  mov     r15, rax
0x14002dfb1  test    rax, rax
0x14002dfb4  jz      short loc_14002DFDA
0x14002dfb6  mov     r8d, 30455646h
0x14002dfbc  mov     rdx, rdi
0x14002dfbf  mov     rcx, rdi
0x14002dfc2  call    cs:__imp_ExAllocatePool2
0x14002dfc9  nop     dword ptr [rax+rax+00h]
0x14002dfce  mov     rbp, rax
0x14002dfd1  test    rax, rax
0x14002dfd4  jnz     loc_14002DCEC
0x14002dfda  mov     edi, 0C000009Ah
0x14002dfdf  mov     dl, [rsp+88h+NewIrql]; NewIrql
0x14002dfe6  mov     rcx, [rsp+88h+SpinLock]; SpinLock
0x14002dfeb  call    cs:__imp_KeReleaseSpinLock
0x14002dff2  nop     dword ptr [rax+rax+00h]
0x14002dff7  test    r15, r15
0x14002dffa  jz      loc_14002DE13
0x14002e000  mov     edx, 30455646h; Tag
0x14002e005  mov     rcx, r15; P
0x14002e008  call    cs:__imp_ExFreePoolWithTag
0x14002e00f  nop     dword ptr [rax+rax+00h]
0x14002e014  jmp     loc_14002DE13
0x14002e019  mov     ecx, 3
0x14002e01e  int     29h; Win8: RtlFailFast(ecx)
0x14002e020  mov     edx, 30455646h; Tag
0x14002e025  mov     rcx, rbp; P
0x14002e028  call    cs:__imp_ExFreePoolWithTag
0x14002e02f  nop     dword ptr [rax+rax+00h]
0x14002e034  jmp     loc_14002DE1C
0x14002e039  mov     rcx, [rsi+18h]; IoWorkItem
0x14002e03d  test    rcx, rcx
0x14002e040  jz      short loc_14002E04E
0x14002e042  call    cs:__imp_IoFreeWorkItem
0x14002e049  nop     dword ptr [rax+rax+00h]
0x14002e04e  mov     edx, 30455646h; Tag
0x14002e053  mov     rcx, rsi; P
0x14002e056  call    cs:__imp_ExFreePoolWithTag
0x14002e05d  nop     dword ptr [rax+rax+00h]
0x14002e062  jmp     loc_14002DE25
0x14002e067  mov     rcx, r14; BugCheckParameter2
0x14002e06a  call    FvepReleaseRemoveLock
0x14002e06f  jmp     loc_14002DE2E
```
