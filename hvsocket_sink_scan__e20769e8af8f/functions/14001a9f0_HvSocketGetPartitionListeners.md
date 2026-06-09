# HvSocketGetPartitionListeners

- ea: `0x14001a9f0`
- end: `0x14001ac7d`
- name: `HvSocketGetPartitionListeners`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x140006f1c`
- `0x140009df0`
- `0x14000a048`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x14001a9f0`
- `0x14001d530`
- `0x14001f540`
- `0x1400220a8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001aab5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ab57`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001abcd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001aab5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ab57`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001abcd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001aaa9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ab4b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001abc1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001aaa9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ab4b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001abc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ac61`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ac61`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001aa22`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001aa77`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001aaf6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001aa22`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001aa77`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001aaf6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ac4b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ac4b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001aa35`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001aa8a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001ab09`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001aa35`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001aa8a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001ab09`

## pseudocode

```c
__int64 __fastcall HvSocketGetPartitionListeners(__int64 a1, _OWORD *a2, int a3, __int64 a4, _DWORD *a5)
{
  struct _FAST_MUTEX *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdi
  unsigned int v12; // ebx
  int v13; // ecx
  __int64 *i; // rax
  __int64 v15; // rdx
  int Listeners; // eax
  signed __int64 v17; // rax
  bool v18; // cc
  signed __int64 v19; // rax
  void (__fastcall *v20)(__int64); // rax
  _OWORD v22[4]; // [rsp+30h] [rbp-48h] BYREF

  if ( !memcmp(a2, &HV_GUID_ZERO, 0x10u) )
  {
    KeEnterCriticalRegion();
    v9 = (struct _FAST_MUTEX *)(a1 + 16);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    v10 = VmbusTlFindAndReferencePartition(a1, &HV_GUID_CHILDREN);
  }
  else
  {
    v22[0] = 0;
    if ( !(unsigned __int8)VmbusTlMapSystemIdToPartitionId(a1, a2, v22) )
      v22[0] = *a2;
    KeEnterCriticalRegion();
    v9 = (struct _FAST_MUTEX *)(a1 + 16);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    v10 = HvSocketFindAndReferenceAnyPartition(a1, v22);
  }
  v11 = v10;
  ExReleaseFastMutexUnsafe(v9);
  KeLeaveCriticalRegion();
  if ( v11 )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v11 + 16));
    v13 = 0;
    for ( i = *(__int64 **)(v11 + 360); i != (__int64 *)(v11 + 360); i = (__int64 *)*i )
      v13 += *((_DWORD *)i + 17);
    v15 = (unsigned int)(a3 - 8);
    *a5 = v13;
    if ( (unsigned int)v15 >= 56 * v13 )
    {
      Listeners = VmbusTlGetListeners(v11, v15, a4 + 8, a4);
      v12 = Listeners;
      if ( Listeners < 0 && (unsigned int)dword_140013058 > 2 )
        HvsocketTraceGuidError("HvSocketGetPartitionListeners", 480, (unsigned int)Listeners, a2);
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v11 + 16));
      KeLeaveCriticalRegion();
    }
    else
    {
      v12 = -1073741789;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v11 + 16));
      KeLeaveCriticalRegion();
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceGuidError("HvSocketGetPartitionListeners", 473, 3221225507LL, a2);
    }
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketGetPartitionListeners",
        488,
        v11,
        *(_QWORD *)(v11 + 8),
        (__int64)"Dereference object");
    v17 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v11 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v18 = v17 <= 1;
    v19 = v17 - 1;
    if ( v18 )
    {
      if ( v19 )
        __fastfail(0xEu);
      v20 = *(void (__fastcall **)(__int64))(v11 + 80);
      if ( v20 )
        v20(v11);
      if ( *(_DWORD *)(v11 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v11, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v11 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v11 + 96), (PVOID)v11);
      }
    }
  }
  else
  {
    v12 = -1073741503;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceGuidError("HvSocketGetPartitionListeners", 459, 3221225793LL, a2);
  }
  return v12;
}

```

## disassembly

```asm
0x14001a9f0  push    rbx
0x14001a9f2  push    rbp
0x14001a9f3  push    rsi
0x14001a9f4  push    rdi
0x14001a9f5  push    r14
0x14001a9f7  push    r15
0x14001a9f9  sub     rsp, 48h
0x14001a9fd  mov     rsi, rdx
0x14001aa00  mov     r15d, r8d
0x14001aa03  mov     rdi, rcx
0x14001aa06  lea     rdx, HV_GUID_ZERO; Buf2
0x14001aa0d  mov     rcx, rsi; Buf1
0x14001aa10  mov     r8d, 10h; Size
0x14001aa16  mov     r14, r9
0x14001aa19  call    memcmp
0x14001aa1e  test    eax, eax
0x14001aa20  jnz     short loc_14001AA52
0x14001aa22  call    cs:__imp_KeEnterCriticalRegion
0x14001aa29  nop     dword ptr [rax+rax+00h]
0x14001aa2e  lea     rbx, [rdi+10h]
0x14001aa32  mov     rcx, rbx; FastMutex
0x14001aa35  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001aa3c  nop     dword ptr [rax+rax+00h]
0x14001aa41  lea     rdx, HV_GUID_CHILDREN
0x14001aa48  mov     rcx, rdi
0x14001aa4b  call    VmbusTlFindAndReferencePartition
0x14001aa50  jmp     short loc_14001AAA3
0x14001aa52  xorps   xmm0, xmm0
0x14001aa55  lea     r8, [rsp+78h+var_48]
0x14001aa5a  mov     rdx, rsi
0x14001aa5d  mov     rcx, rdi
0x14001aa60  movups  [rsp+78h+var_48], xmm0
0x14001aa65  call    VmbusTlMapSystemIdToPartitionId
0x14001aa6a  test    al, al
0x14001aa6c  jnz     short loc_14001AA77
0x14001aa6e  movups  xmm0, xmmword ptr [rsi]
0x14001aa71  movdqu  [rsp+78h+var_48], xmm0
0x14001aa77  call    cs:__imp_KeEnterCriticalRegion
0x14001aa7e  nop     dword ptr [rax+rax+00h]
0x14001aa83  lea     rbx, [rdi+10h]
0x14001aa87  mov     rcx, rbx; FastMutex
0x14001aa8a  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001aa91  nop     dword ptr [rax+rax+00h]
0x14001aa96  lea     rdx, [rsp+78h+var_48]
0x14001aa9b  mov     rcx, rdi
0x14001aa9e  call    HvSocketFindAndReferenceAnyPartition
0x14001aaa3  mov     rcx, rbx; FastMutex
0x14001aaa6  mov     rdi, rax
0x14001aaa9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001aab0  nop     dword ptr [rax+rax+00h]
0x14001aab5  call    cs:__imp_KeLeaveCriticalRegion
0x14001aabc  nop     dword ptr [rax+rax+00h]
0x14001aac1  test    rdi, rdi
0x14001aac4  jnz     short loc_14001AAF6
0x14001aac6  mov     eax, cs:dword_140013058
0x14001aacc  mov     ebx, 0C0000141h
0x14001aad1  cmp     eax, 2
0x14001aad4  jbe     loc_14001AC6D
0x14001aada  mov     r9, rsi
0x14001aadd  lea     rcx, aHvsocketgetpar_0; "HvSocketGetPartitionListeners"
0x14001aae4  mov     r8d, ebx
0x14001aae7  mov     edx, 1CBh
0x14001aaec  call    HvsocketTraceGuidError
0x14001aaf1  jmp     loc_14001AC6D
0x14001aaf6  call    cs:__imp_KeEnterCriticalRegion
0x14001aafd  nop     dword ptr [rax+rax+00h]
0x14001ab02  lea     rbp, [rdi+10h]
0x14001ab06  mov     rcx, rbp; FastMutex
0x14001ab09  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001ab10  nop     dword ptr [rax+rax+00h]
0x14001ab15  lea     rdx, [rdi+168h]
0x14001ab1c  xor     ecx, ecx
0x14001ab1e  mov     rax, [rdx]
0x14001ab21  jmp     short loc_14001AB29
0x14001ab23  add     ecx, [rax+44h]
0x14001ab26  mov     rax, [rax]
0x14001ab29  cmp     rax, rdx
0x14001ab2c  jnz     short loc_14001AB23
0x14001ab2e  mov     rax, [rsp+78h+arg_20]
0x14001ab36  lea     edx, [r15-8]
0x14001ab3a  mov     [rax], ecx
0x14001ab3c  imul    eax, ecx, 38h ; '8'
0x14001ab3f  cmp     edx, eax
0x14001ab41  jnb     short loc_14001AB87
0x14001ab43  mov     rcx, rbp; FastMutex
0x14001ab46  mov     ebx, 0C0000023h
0x14001ab4b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001ab52  nop     dword ptr [rax+rax+00h]
0x14001ab57  call    cs:__imp_KeLeaveCriticalRegion
0x14001ab5e  nop     dword ptr [rax+rax+00h]
0x14001ab63  mov     eax, cs:dword_140013058
0x14001ab69  cmp     eax, 2
0x14001ab6c  jbe     short loc_14001ABD9
0x14001ab6e  mov     r9, rsi
0x14001ab71  lea     rcx, aHvsocketgetpar_0; "HvSocketGetPartitionListeners"
0x14001ab78  mov     r8d, ebx
0x14001ab7b  mov     edx, 1D9h
0x14001ab80  call    HvsocketTraceGuidError
0x14001ab85  jmp     short loc_14001ABD9
0x14001ab87  lea     r8, [r14+8]
0x14001ab8b  mov     r9, r14
0x14001ab8e  mov     rcx, rdi
0x14001ab91  call    VmbusTlGetListeners
0x14001ab96  mov     ebx, eax
0x14001ab98  test    eax, eax
0x14001ab9a  jns     short loc_14001ABBE
0x14001ab9c  mov     edx, cs:dword_140013058
0x14001aba2  cmp     edx, 2
0x14001aba5  jbe     short loc_14001ABBE
0x14001aba7  mov     r9, rsi
0x14001abaa  lea     rcx, aHvsocketgetpar_0; "HvSocketGetPartitionListeners"
0x14001abb1  mov     r8d, eax
0x14001abb4  mov     edx, 1E0h
0x14001abb9  call    HvsocketTraceGuidError
0x14001abbe  mov     rcx, rbp; FastMutex
0x14001abc1  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001abc8  nop     dword ptr [rax+rax+00h]
0x14001abcd  call    cs:__imp_KeLeaveCriticalRegion
0x14001abd4  nop     dword ptr [rax+rax+00h]
0x14001abd9  mov     eax, cs:dword_140013058
0x14001abdf  cmp     eax, 5
0x14001abe2  jbe     short loc_14001AC08
0x14001abe4  mov     r9, [rdi+8]
0x14001abe8  lea     rax, aDereferenceObj; "Dereference object"
0x14001abef  mov     r8, rdi
0x14001abf2  mov     [rsp+78h+var_58], rax
0x14001abf7  mov     edx, 1E8h
0x14001abfc  lea     rcx, aHvsocketgetpar_0; "HvSocketGetPartitionListeners"
0x14001ac03  call    HvsocketTraceReferenceCount
0x14001ac08  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001ac0c  lock xadd [rdi+8], rax
0x14001ac12  sub     rax, 1
0x14001ac16  jg      short loc_14001AC6D
0x14001ac18  test    rax, rax
0x14001ac1b  jz      short loc_14001AC26
0x14001ac1d  mov     ecx, 0Eh
0x14001ac22  int     29h; Win8: RtlFailFast(ecx)
0x14001ac24  jmp     short loc_14001AC6D
0x14001ac26  mov     rax, [rdi+50h]
0x14001ac2a  test    rax, rax
0x14001ac2d  jz      short loc_14001AC37
0x14001ac2f  mov     rcx, rdi
0x14001ac32  call    _guard_dispatch_icall
0x14001ac37  mov     ecx, [rdi+58h]
0x14001ac3a  sub     ecx, 1
0x14001ac3d  jz      short loc_14001AC59
0x14001ac3f  cmp     ecx, 1
0x14001ac42  jnz     short loc_14001AC6D
0x14001ac44  mov     rcx, [rdi+60h]; Lookaside
0x14001ac48  mov     rdx, rdi; Entry
0x14001ac4b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001ac52  nop     dword ptr [rax+rax+00h]
0x14001ac57  jmp     short loc_14001AC6D
0x14001ac59  mov     edx, 69706E56h; Tag
0x14001ac5e  mov     rcx, rdi; P
0x14001ac61  call    cs:__imp_ExFreePoolWithTag
0x14001ac68  nop     dword ptr [rax+rax+00h]
0x14001ac6d  mov     eax, ebx
0x14001ac6f  add     rsp, 48h
0x14001ac73  pop     r15
0x14001ac75  pop     r14
0x14001ac77  pop     rdi
0x14001ac78  pop     rsi
0x14001ac79  pop     rbp
0x14001ac7a  pop     rbx
0x14001ac7b  retn
```
