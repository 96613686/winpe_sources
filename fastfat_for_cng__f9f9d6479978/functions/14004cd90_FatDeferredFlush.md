# FatDeferredFlush

- ea: `0x14004cd90`
- end: `0x14004ce6f`
- name: `FatDeferredFlush`
- size: `223`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14003d880`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x14004ce0c`
- `ntoskrnl!CcFlushCache` at `0x14004ce0c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004cdcb`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004ce3a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004cdcb`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004ce3a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004cde2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004cde2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ce1c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ce2c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ce1c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ce2c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004cdf4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004cdf4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ce5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ce5a`
- `ntoskrnl!ObfDereferenceObject` at `0x14004ce49`
- `ntoskrnl!ObfDereferenceObject` at `0x14004ce49`

## pseudocode

```c
void __fastcall FatDeferredFlush(_QWORD *P)
{
  PSECTION_OBJECT_POINTERS *v1; // rdi
  __int64 v3; // rbx
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF
  __int64 v5; // [rsp+48h] [rbp+10h] BYREF
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  v1 = (PSECTION_OBJECT_POINTERS *)P[20];
  v6 = 0;
  v4 = 0;
  v5 = 0;
  FatDecodeFileObject(v1, &v6, &v4, &v5);
  IoSetTopLevelIrp((PIRP)1);
  v3 = v4;
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v4 + 8), 1u);
  ExAcquireResourceSharedLite(*(PERESOURCE *)(v3 + 16), 1u);
  CcFlushCache(v1[5], 0, 0, 0);
  ExReleaseResourceLite(*(PERESOURCE *)(v3 + 16));
  ExReleaseResourceLite(*(PERESOURCE *)(v3 + 8));
  IoSetTopLevelIrp(0);
  ObfDereferenceObject(v1);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14004cd90  mov     r11, rsp
0x14004cd93  push    rbx
0x14004cd94  push    rsi
0x14004cd95  push    rdi
0x14004cd96  sub     rsp, 20h
0x14004cd9a  mov     rdi, [rcx+0A0h]
0x14004cda1  lea     r9, [r11+10h]
0x14004cda5  xor     eax, eax
0x14004cda7  lea     r8, [r11+8]
0x14004cdab  mov     rsi, rcx
0x14004cdae  mov     [r11+18h], rax
0x14004cdb2  mov     rcx, rdi
0x14004cdb5  mov     [r11+8], rax
0x14004cdb9  lea     rdx, [r11+18h]
0x14004cdbd  mov     [r11+10h], rax
0x14004cdc1  call    FatDecodeFileObject
0x14004cdc6  mov     ecx, 1; Irp
0x14004cdcb  call    cs:__imp_IoSetTopLevelIrp
0x14004cdd2  nop     dword ptr [rax+rax+00h]
0x14004cdd7  mov     rbx, [rsp+38h+arg_0]
0x14004cddc  mov     dl, 1; Wait
0x14004cdde  mov     rcx, [rbx+8]; Resource
0x14004cde2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004cde9  nop     dword ptr [rax+rax+00h]
0x14004cdee  mov     rcx, [rbx+10h]; Resource
0x14004cdf2  mov     dl, 1; Wait
0x14004cdf4  call    cs:__imp_ExAcquireResourceSharedLite
0x14004cdfb  nop     dword ptr [rax+rax+00h]
0x14004ce00  mov     rcx, [rdi+28h]; SectionObjectPointer
0x14004ce04  xor     r9d, r9d; IoStatus
0x14004ce07  xor     r8d, r8d; Length
0x14004ce0a  xor     edx, edx; FileOffset
0x14004ce0c  call    cs:__imp_CcFlushCache
0x14004ce13  nop     dword ptr [rax+rax+00h]
0x14004ce18  mov     rcx, [rbx+10h]; Resource
0x14004ce1c  call    cs:__imp_ExReleaseResourceLite
0x14004ce23  nop     dword ptr [rax+rax+00h]
0x14004ce28  mov     rcx, [rbx+8]; Resource
0x14004ce2c  call    cs:__imp_ExReleaseResourceLite
0x14004ce33  nop     dword ptr [rax+rax+00h]
0x14004ce38  xor     ecx, ecx; Irp
0x14004ce3a  call    cs:__imp_IoSetTopLevelIrp
0x14004ce41  nop     dword ptr [rax+rax+00h]
0x14004ce46  mov     rcx, rdi; Object
0x14004ce49  call    cs:__imp_ObfDereferenceObject
0x14004ce50  nop     dword ptr [rax+rax+00h]
0x14004ce55  xor     edx, edx; Tag
0x14004ce57  mov     rcx, rsi; P
0x14004ce5a  call    cs:__imp_ExFreePoolWithTag
0x14004ce61  nop     dword ptr [rax+rax+00h]
0x14004ce66  add     rsp, 20h
0x14004ce6a  pop     rdi
0x14004ce6b  pop     rsi
0x14004ce6c  pop     rbx
0x14004ce6d  retn
```
