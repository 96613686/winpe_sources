# PmUpdatePartition(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,ulong,_PARTITION_INFORMATION_EX *)

- ea: `0x140007f70`
- end: `0x1400080fc`
- name: `?PmUpdatePartition@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@KPEAU_PARTITION_INFORMATION_EX@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _PARTITION_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *, int, struct _PARTITION_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x140008104`

## callees

- `0x140004e44`
- `0x140007f70`
- `0x14000b700`
- `0x14000c328`
- `0x1400206f0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140008055`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008055`
- `ntoskrnl!ObfDereferenceObject` at `0x1400080b9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400080b9`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14000807b`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14000807b`
- `ntoskrnl!KeClearEvent` at `0x140008068`
- `ntoskrnl!KeClearEvent` at `0x140008068`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14000802c`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14000802c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000801c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400080a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000801c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400080a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007fae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000808b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007fae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000808b`

## pseudocode

```c
__int64 __fastcall PmUpdatePartition(
        struct _DEVICE_EXTENSION *a1,
        struct _PARTITION_EXTENSION *a2,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a3,
        int a4,
        struct _PARTITION_INFORMATION_EX *a5)
{
  struct _PARTITION_INFORMATION_EX *v5; // rsi
  unsigned int v9; // r13d
  KIRQL v10; // al
  PDEVICE_OBJECT AttachedDeviceReference; // rbx
  KIRQL v12; // al
  __int64 result; // rax

  v5 = (struct _PARTITION_INFORMATION_EX *)((char *)a2 + 168);
  v9 = PmVerifyPropertyChange(a5, (struct _PARTITION_INFORMATION_EX *)((char *)a2 + 168));
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
  *((_DWORD *)a2 + 10) |= v9;
  *((_DWORD *)a2 + 40) = a4;
  *v5 = *a5;
  KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v10);
  AttachedDeviceReference = IoGetAttachedDeviceReference(*((PDEVICE_OBJECT *)a1 + 1));
  if ( AttachedDeviceReference != *((PDEVICE_OBJECT *)a2 + 2) )
  {
    KeWaitForSingleObject((char *)a2 + 344, Executive, 0, 0, 0);
    KeClearEvent((PRKEVENT)a2 + 17);
    ExWaitForRundownProtectionReleaseCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)a2 + 50));
    v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
    AttachedDeviceReference = (PDEVICE_OBJECT)_InterlockedExchange64(
                                                (volatile __int64 *)a2 + 2,
                                                (__int64)AttachedDeviceReference);
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v12);
    PartitionReleaseRundownExclusive(a2);
  }
  ObfDereferenceObject(AttachedDeviceReference);
  if ( (v9 & 0x20) == 0 )
    return 0;
  result = PmBuildStableGuid(a1, a2);
  if ( (int)result >= 0 )
    return PmBuildUniqueId(a1, a2);
  return result;
}

```

## disassembly

```asm
0x140007f70  push    rbx
0x140007f72  push    rbp
0x140007f73  push    rsi
0x140007f74  push    rdi
0x140007f75  push    r12
0x140007f77  push    r13
0x140007f79  push    r14
0x140007f7b  push    r15
0x140007f7d  sub     rsp, 38h
0x140007f81  mov     rdi, [rsp+78h+arg_20]
0x140007f89  lea     rsi, [rdx+0A8h]
0x140007f90  mov     rbp, rdx
0x140007f93  mov     r14, rcx
0x140007f96  mov     rdx, rsi; struct _PARTITION_INFORMATION_EX *
0x140007f99  mov     rcx, rdi; struct _PARTITION_INFORMATION_EX *
0x140007f9c  mov     ebx, r9d
0x140007f9f  xor     r12d, r12d
0x140007fa2  call    ?PmVerifyPropertyChange@@YAKPEAU_PARTITION_INFORMATION_EX@@0@Z; PmVerifyPropertyChange(_PARTITION_INFORMATION_EX *,_PARTITION_INFORMATION_EX *)
0x140007fa7  lea     rcx, [r14+70h]; SpinLock
0x140007fab  mov     r13d, eax
0x140007fae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007fb5  nop     dword ptr [rax+rax+00h]
0x140007fba  movzx   edx, al; NewIrql
0x140007fbd  lea     rcx, [r14+70h]; SpinLock
0x140007fc1  mov     eax, [rbp+28h]
0x140007fc4  or      eax, r13d
0x140007fc7  mov     [rbp+28h], eax
0x140007fca  mov     [rbp+0A0h], ebx
0x140007fd0  movups  xmm0, xmmword ptr [rdi]
0x140007fd3  movups  xmmword ptr [rsi], xmm0
0x140007fd6  movups  xmm1, xmmword ptr [rdi+10h]
0x140007fda  movups  xmmword ptr [rsi+10h], xmm1
0x140007fde  movups  xmm0, xmmword ptr [rdi+20h]
0x140007fe2  movups  xmmword ptr [rsi+20h], xmm0
0x140007fe6  movups  xmm1, xmmword ptr [rdi+30h]
0x140007fea  movups  xmmword ptr [rsi+30h], xmm1
0x140007fee  movups  xmm0, xmmword ptr [rdi+40h]
0x140007ff2  movups  xmmword ptr [rsi+40h], xmm0
0x140007ff6  movups  xmm1, xmmword ptr [rdi+50h]
0x140007ffa  movups  xmmword ptr [rsi+50h], xmm1
0x140007ffe  movups  xmm0, xmmword ptr [rdi+60h]
0x140008002  movups  xmmword ptr [rsi+60h], xmm0
0x140008006  movups  xmm1, xmmword ptr [rdi+70h]
0x14000800a  movups  xmmword ptr [rsi+70h], xmm1
0x14000800e  movups  xmm0, xmmword ptr [rdi+80h]
0x140008015  movups  xmmword ptr [rsi+80h], xmm0
0x14000801c  call    cs:__imp_KeReleaseSpinLock
0x140008023  nop     dword ptr [rax+rax+00h]
0x140008028  mov     rcx, [r14+8]; DeviceObject
0x14000802c  call    cs:__imp_IoGetAttachedDeviceReference
0x140008033  nop     dword ptr [rax+rax+00h]
0x140008038  mov     rbx, rax
0x14000803b  cmp     rax, [rbp+10h]
0x14000803f  jz      short loc_1400080B6
0x140008041  lea     rcx, [rbp+158h]; Object
0x140008048  mov     [rsp+78h+Timeout], r12; Timeout
0x14000804d  xor     r9d, r9d; Alertable
0x140008050  xor     r8d, r8d; WaitMode
0x140008053  xor     edx, edx; WaitReason
0x140008055  call    cs:__imp_KeWaitForSingleObject
0x14000805c  nop     dword ptr [rax+rax+00h]
0x140008061  lea     rcx, [rbp+198h]; Event
0x140008068  call    cs:__imp_KeClearEvent
0x14000806f  nop     dword ptr [rax+rax+00h]
0x140008074  mov     rcx, [rbp+190h]; RunRef
0x14000807b  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140008082  nop     dword ptr [rax+rax+00h]
0x140008087  lea     rcx, [r14+70h]; SpinLock
0x14000808b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008092  nop     dword ptr [rax+rax+00h]
0x140008097  xchg    rbx, [rbp+10h]
0x14000809b  movzx   edx, al; NewIrql
0x14000809e  lea     rcx, [r14+70h]; SpinLock
0x1400080a2  call    cs:__imp_KeReleaseSpinLock
0x1400080a9  nop     dword ptr [rax+rax+00h]
0x1400080ae  mov     rcx, rbp; struct _PARTITION_EXTENSION *
0x1400080b1  call    ?PartitionReleaseRundownExclusive@@YAXPEAU_PARTITION_EXTENSION@@@Z; PartitionReleaseRundownExclusive(_PARTITION_EXTENSION *)
0x1400080b6  mov     rcx, rbx; Object
0x1400080b9  call    cs:__imp_ObfDereferenceObject
0x1400080c0  nop     dword ptr [rax+rax+00h]
0x1400080c5  test    r13b, 20h
0x1400080c9  jz      short loc_1400080E7
0x1400080cb  mov     rdx, rbp; struct _PARTITION_EXTENSION *
0x1400080ce  mov     rcx, r14; struct _DEVICE_EXTENSION *
0x1400080d1  call    ?PmBuildStableGuid@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@@Z; PmBuildStableGuid(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *)
0x1400080d6  test    eax, eax
0x1400080d8  js      short loc_1400080EA
0x1400080da  mov     rdx, rbp; struct _PARTITION_EXTENSION *
0x1400080dd  mov     rcx, r14; struct _DEVICE_EXTENSION *
0x1400080e0  call    ?PmBuildUniqueId@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@@Z; PmBuildUniqueId(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *)
0x1400080e5  jmp     short loc_1400080EA
0x1400080e7  mov     eax, r12d
0x1400080ea  add     rsp, 38h
0x1400080ee  pop     r15
0x1400080f0  pop     r14
0x1400080f2  pop     r13
0x1400080f4  pop     r12
0x1400080f6  pop     rdi
0x1400080f7  pop     rsi
0x1400080f8  pop     rbp
0x1400080f9  pop     rbx
0x1400080fa  retn
```
