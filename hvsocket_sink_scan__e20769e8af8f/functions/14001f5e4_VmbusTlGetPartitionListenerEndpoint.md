# VmbusTlGetPartitionListenerEndpoint

- ea: `0x14001f5e4`
- end: `0x14001fe5f`
- name: `VmbusTlGetPartitionListenerEndpoint`
- size: `2171`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x14001c2d0`
- `0x14001e5ac`

## callees

- `0x1400095a0`
- `0x14000a048`
- `0x14000a154`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x14001f5e4`
- `0x140021ec0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f700`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f8d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001fa74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001fbd9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001fd1a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f700`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f8d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001fa74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001fbd9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001fd1a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001f6f4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001f8cb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001fa68`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001fbcd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001fd0e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001f6f4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001f8cb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001fa68`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001fbcd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001fd0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f7e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f87f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f9c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fb61`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fccc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fe03`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f7e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f87f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f9c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fb61`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fccc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fe03`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f6c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f893`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001fa3c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001fb9f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001fce0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f6c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f893`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001fa3c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001fb9f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001fce0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f7cb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f869`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f9b2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fb4b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fcb6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fded`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f7cb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f869`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f9b2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fb4b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fcb6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fded`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001f6d7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001f8a6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001fa4b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001fbaf`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001fcf0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001f6d7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001f8a6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001fa4b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001fbaf`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001fcf0`

## pseudocode

```c
__int64 __fastcall VmbusTlGetPartitionListenerEndpoint(
        __int64 a1,
        __int64 a2,
        const void *a3,
        const void *a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v8; // rsi
  int v9; // ebx
  __int64 v10; // rax
  struct _FAST_MUTEX *v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // rax
  void (__fastcall *v14)(__int64); // rax
  char v15; // bl
  __int64 v16; // rax
  void (__fastcall *v17)(__int64); // rax
  struct _FAST_MUTEX *v18; // rsi
  __int64 v19; // rbx
  __int64 v20; // rdi
  __int64 v21; // rax
  void (__fastcall *v22)(__int64); // rax
  __int64 v23; // rdi
  __int64 v24; // rax
  void (__fastcall *v25)(__int64); // rax
  __int64 v26; // rdi
  __int64 v27; // rax
  void (__fastcall *v28)(__int64); // rax
  __int64 v29; // rdi
  __int64 v30; // rax
  void (__fastcall *v31)(__int64); // rax
  __int64 v33; // [rsp+30h] [rbp-48h]

  v33 = a1 + 232;
  v8 = a1;
  if ( memcmp((const void *)(a1 + 232), &HV_GUID_CHILDREN, 0x10u)
    || !memcmp(a3, &HV_GUID_CHILDREN, 0x10u)
    || !memcmp(a3, &HV_GUID_PARENT, 0x10u)
    || !memcmp(a3, &HV_GUID_ZERO, 0x10u) )
  {
    goto LABEL_35;
  }
  if ( !a2 )
  {
    v9 = -1073741275;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceServiceError((unsigned int)"VmbusTlGetPartitionListenerEndpoint", 686, -1073741275, a5, (__int64)a3);
    return (unsigned int)v9;
  }
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 16));
  v10 = VmbusTlFindAndReferenceService(a2, a5);
  v11 = (struct _FAST_MUTEX *)(a2 + 16);
  v12 = v10;
  ExReleaseFastMutexUnsafe(v11);
  KeLeaveCriticalRegion();
  if ( v12 )
  {
    if ( !*(_BYTE *)(v12 + 128) )
    {
      v9 = -1073741790;
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceServiceError(
          (unsigned int)"VmbusTlGetPartitionListenerEndpoint",
          709,
          -1073741790,
          a5,
          (__int64)a3);
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlGetPartitionListenerEndpoint",
          710,
          v12,
          *(_QWORD *)(v12 + 8),
          (__int64)"Dereference object");
      v13 = _InterlockedDecrement64((volatile signed __int64 *)(v12 + 8));
      if ( v13 <= 0 )
      {
        if ( v13 )
          __fastfail(0xEu);
        v14 = *(void (__fastcall **)(__int64))(v12 + 80);
        if ( v14 )
          v14(v12);
        if ( *(_DWORD *)(v12 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v12, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v12 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v12 + 96), (PVOID)v12);
        }
      }
LABEL_111:
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceServiceError((unsigned int)"VmbusTlGetPartitionListenerEndpoint", 789, v9, a5, v33);
      return (unsigned int)v9;
    }
    v15 = *(_BYTE *)(v12 + 152);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlGetPartitionListenerEndpoint",
        715,
        v12,
        *(_QWORD *)(v12 + 8),
        (__int64)"Dereference object");
    v16 = _InterlockedDecrement64((volatile signed __int64 *)(v12 + 8));
    if ( v16 <= 0 )
    {
      if ( v16 )
        __fastfail(0xEu);
      v17 = *(void (__fastcall **)(__int64))(v12 + 80);
      if ( v17 )
        v17(v12);
      if ( *(_DWORD *)(v12 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v12, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v12 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v12 + 96), (PVOID)v12);
      }
    }
    if ( v15 )
    {
LABEL_35:
      KeEnterCriticalRegion();
      v18 = (struct _FAST_MUTEX *)(v8 + 16);
      ExAcquireFastMutexUnsafe(v18);
      v19 = a1;
      v20 = VmbusTlFindAndReferenceService(a1, a5);
      ExReleaseFastMutexUnsafe(v18);
      KeLeaveCriticalRegion();
      if ( v20 )
      {
        v9 = VmbusTlFindAndReferenceServiceListener(v20, &HV_GUID_ZERO, a6);
        if ( (int)(v9 + 0x80000000) >= 0 && v9 != -1073741275 && (unsigned int)dword_140013058 > 2 )
          HvsocketTraceServiceError(
            (unsigned int)"VmbusTlFindAndReferenceListener",
            629,
            v9,
            a5,
            (__int64)&HV_GUID_ZERO);
        if ( (unsigned int)dword_140013058 > 5 )
          HvsocketTraceReferenceCount(
            (unsigned int)"VmbusTlFindAndReferenceListener",
            635,
            v20,
            *(_QWORD *)(v20 + 8),
            (__int64)"Dereference object");
        v21 = _InterlockedDecrement64((volatile signed __int64 *)(v20 + 8));
        if ( v21 <= 0 )
        {
          if ( v21 )
            __fastfail(0xEu);
          v22 = *(void (__fastcall **)(__int64))(v20 + 80);
          if ( v22 )
            v22(v20);
          if ( *(_DWORD *)(v20 + 88) == 1 )
          {
            ExFreePoolWithTag((PVOID)v20, 0x69706E56u);
          }
          else if ( *(_DWORD *)(v20 + 88) == 2 )
          {
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v20 + 96), (PVOID)v20);
          }
        }
        if ( v9 >= 0 )
          return (unsigned int)v9;
        v19 = a1;
      }
      if ( !memcmp((const void *)(v19 + 232), &HV_GUID_CHILDREN, 0x10u) )
      {
        if ( memcmp(a3, &HV_GUID_CHILDREN, 0x10u) )
        {
          if ( memcmp(a3, &HV_GUID_PARENT, 0x10u) )
          {
            KeEnterCriticalRegion();
            ExAcquireFastMutexUnsafe(v18);
            v23 = VmbusTlFindAndReferenceService(v19, a5);
            ExReleaseFastMutexUnsafe(v18);
            KeLeaveCriticalRegion();
            if ( v23 )
            {
              v9 = VmbusTlFindAndReferenceServiceListener(v23, &HV_GUID_CHILDREN, a6);
              if ( (int)(v9 + 0x80000000) >= 0 && v9 != -1073741275 && (unsigned int)dword_140013058 > 2 )
                HvsocketTraceServiceError(
                  (unsigned int)"VmbusTlFindAndReferenceListener",
                  629,
                  v9,
                  a5,
                  (__int64)&HV_GUID_CHILDREN);
              if ( (unsigned int)dword_140013058 > 5 )
                HvsocketTraceReferenceCount(
                  (unsigned int)"VmbusTlFindAndReferenceListener",
                  635,
                  v23,
                  *(_QWORD *)(v23 + 8),
                  (__int64)"Dereference object");
              v24 = _InterlockedDecrement64((volatile signed __int64 *)(v23 + 8));
              if ( v24 <= 0 )
              {
                if ( v24 )
                  __fastfail(0xEu);
                v25 = *(void (__fastcall **)(__int64))(v23 + 80);
                if ( v25 )
                  v25(v23);
                if ( *(_DWORD *)(v23 + 88) == 1 )
                {
                  ExFreePoolWithTag((PVOID)v23, 0x69706E56u);
                }
                else if ( *(_DWORD *)(v23 + 88) == 2 )
                {
                  ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v23 + 96), (PVOID)v23);
                }
              }
              if ( v9 >= 0 )
                return (unsigned int)v9;
            }
          }
        }
      }
      v8 = a1;
    }
  }
  if ( !memcmp(a4, &HV_GUID_ZERO, 0x10u) )
    goto LABEL_110;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v8 + 16));
  v26 = VmbusTlFindAndReferenceService(v8, a5);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v8 + 16));
  KeLeaveCriticalRegion();
  if ( !v26 )
    goto LABEL_110;
  v9 = VmbusTlFindAndReferenceServiceListener(v26, a4, a6);
  if ( (int)(v9 + 0x80000000) >= 0 && v9 != -1073741275 && (unsigned int)dword_140013058 > 2 )
    HvsocketTraceServiceError((unsigned int)"VmbusTlFindAndReferenceListener", 629, v9, a5, (__int64)a4);
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlFindAndReferenceListener",
      635,
      v26,
      *(_QWORD *)(v26 + 8),
      (__int64)"Dereference object");
  v27 = _InterlockedDecrement64((volatile signed __int64 *)(v26 + 8));
  if ( v27 <= 0 )
  {
    if ( v27 )
      __fastfail(0xEu);
    v28 = *(void (__fastcall **)(__int64))(v26 + 80);
    if ( v28 )
      v28(v26);
    if ( *(_DWORD *)(v26 + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)v26, 0x69706E56u);
    }
    else if ( *(_DWORD *)(v26 + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v26 + 96), (PVOID)v26);
    }
  }
  if ( v9 < 0 )
  {
LABEL_110:
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v8 + 16));
    v29 = VmbusTlFindAndReferenceService(v8, a5);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v8 + 16));
    KeLeaveCriticalRegion();
    if ( v29 )
    {
      v9 = VmbusTlFindAndReferenceServiceListener(v29, a3, a6);
      if ( (int)(v9 + 0x80000000) >= 0 && v9 != -1073741275 && (unsigned int)dword_140013058 > 2 )
        HvsocketTraceServiceError((unsigned int)"VmbusTlFindAndReferenceListener", 629, v9, a5, (__int64)a3);
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlFindAndReferenceListener",
          635,
          v29,
          *(_QWORD *)(v29 + 8),
          (__int64)"Dereference object");
      v30 = _InterlockedDecrement64((volatile signed __int64 *)(v29 + 8));
      if ( v30 <= 0 )
      {
        if ( v30 )
          __fastfail(0xEu);
        v31 = *(void (__fastcall **)(__int64))(v29 + 80);
        if ( v31 )
          v31(v29);
        if ( *(_DWORD *)(v29 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v29, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v29 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v29 + 96), (PVOID)v29);
        }
      }
    }
    else
    {
      v9 = -1073741275;
    }
    if ( v9 < 0 && v9 != -1073741275 )
      goto LABEL_111;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001f5e4  mov     [rsp+arg_8], rbx
0x14001f5e9  mov     [rsp+Buf1], r9
0x14001f5ee  mov     [rsp+arg_0], rcx
0x14001f5f3  push    rbp
0x14001f5f4  push    rsi
0x14001f5f5  push    rdi
0x14001f5f6  push    r12
0x14001f5f8  push    r13
0x14001f5fa  push    r14
0x14001f5fc  push    r15
0x14001f5fe  sub     rsp, 40h
0x14001f602  lea     rax, [rcx+0E8h]
0x14001f609  mov     r12, r8
0x14001f60c  mov     rdi, rdx
0x14001f60f  mov     [rsp+78h+var_48], rax
0x14001f614  mov     rsi, rcx
0x14001f617  lea     rbx, HV_GUID_CHILDREN
0x14001f61e  mov     rdx, rbx; Buf2
0x14001f621  mov     rcx, rax; Buf1
0x14001f624  mov     r8d, 10h; Size
0x14001f62a  call    memcmp
0x14001f62f  mov     r13, [rsp+78h+arg_20]
0x14001f637  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14001f63b  mov     r14d, 0C0000225h
0x14001f641  lea     r15d, [rbp+0Fh]
0x14001f645  test    eax, eax
0x14001f647  jnz     loc_14001F893
0x14001f64d  lea     r8d, [rbp+11h]; Size
0x14001f651  mov     rdx, rbx; Buf2
0x14001f654  mov     rcx, r12; Buf1
0x14001f657  call    memcmp
0x14001f65c  test    eax, eax
0x14001f65e  jz      loc_14001F893
0x14001f664  lea     ebx, [rbp+11h]
0x14001f667  mov     rcx, r12; Buf1
0x14001f66a  mov     r8d, ebx; Size
0x14001f66d  lea     rdx, HV_GUID_PARENT; Buf2
0x14001f674  call    memcmp
0x14001f679  test    eax, eax
0x14001f67b  jz      loc_14001F893
0x14001f681  mov     r8d, ebx; Size
0x14001f684  lea     rdx, HV_GUID_ZERO; Buf2
0x14001f68b  mov     rcx, r12; Buf1
0x14001f68e  call    memcmp
0x14001f693  test    eax, eax
0x14001f695  jz      loc_14001F893
0x14001f69b  test    rdi, rdi
0x14001f69e  jnz     short loc_14001F6C4
0x14001f6a0  mov     eax, cs:dword_140013058
0x14001f6a6  mov     ebx, r14d
0x14001f6a9  cmp     eax, 2
0x14001f6ac  jbe     loc_14001FE44
0x14001f6b2  mov     [rsp+78h+var_58], r12
0x14001f6b7  mov     r8d, r14d
0x14001f6ba  mov     edx, 2AEh
0x14001f6bf  jmp     loc_14001FE35
0x14001f6c4  call    cs:__imp_KeEnterCriticalRegion
0x14001f6cb  nop     dword ptr [rax+rax+00h]
0x14001f6d0  lea     rbx, [rdi+10h]
0x14001f6d4  mov     rcx, rbx; FastMutex
0x14001f6d7  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001f6de  nop     dword ptr [rax+rax+00h]
0x14001f6e3  mov     rdx, r13
0x14001f6e6  mov     rcx, rdi
0x14001f6e9  call    VmbusTlFindAndReferenceService
0x14001f6ee  mov     rcx, rbx; FastMutex
0x14001f6f1  mov     rdi, rax
0x14001f6f4  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001f6fb  nop     dword ptr [rax+rax+00h]
0x14001f700  call    cs:__imp_KeLeaveCriticalRegion
0x14001f707  nop     dword ptr [rax+rax+00h]
0x14001f70c  test    rdi, rdi
0x14001f70f  jz      loc_14001FB7D
0x14001f715  cmp     byte ptr [rdi+80h], 0
0x14001f71c  jnz     loc_14001F7F5
0x14001f722  mov     ecx, cs:dword_140013058
0x14001f728  mov     ebx, 0C0000022h
0x14001f72d  cmp     ecx, 2
0x14001f730  jbe     short loc_14001F74E
0x14001f732  mov     r9, r13
0x14001f735  mov     [rsp+78h+var_58], r12
0x14001f73a  mov     r8d, ebx
0x14001f73d  lea     rcx, aVmbustlgetpart; "VmbusTlGetPartitionListenerEndpoint"
0x14001f744  mov     edx, 2C5h
0x14001f749  call    HvsocketTraceServiceError
0x14001f74e  mov     eax, cs:dword_140013058
0x14001f754  cmp     eax, 5
0x14001f757  jbe     short loc_14001F77D
0x14001f759  mov     r9, [rdi+8]
0x14001f75d  lea     rax, aDereferenceObj; "Dereference object"
0x14001f764  mov     r8, rdi
0x14001f767  mov     [rsp+78h+var_58], rax
0x14001f76c  mov     edx, 2C6h
0x14001f771  lea     rcx, aVmbustlgetpart; "VmbusTlGetPartitionListenerEndpoint"
0x14001f778  call    HvsocketTraceReferenceCount
0x14001f77d  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14001f781  mov     rax, rbp
0x14001f784  lock xadd [rdi+8], rax
0x14001f78a  add     rax, rbp
0x14001f78d  test    rax, rax
0x14001f790  jg      loc_14001FE18
0x14001f796  jz      short loc_14001F7A2
0x14001f798  mov     rcx, r15
0x14001f79b  int     29h; Win8: RtlFailFast(ecx)
0x14001f79d  jmp     loc_14001FE18
0x14001f7a2  mov     rax, [rdi+50h]
0x14001f7a6  test    rax, rax
0x14001f7a9  jz      short loc_14001F7B3
0x14001f7ab  mov     rcx, rdi
0x14001f7ae  call    _guard_dispatch_icall
0x14001f7b3  mov     ecx, [rdi+58h]
0x14001f7b6  sub     ecx, 1
0x14001f7b9  jz      short loc_14001F7DC
0x14001f7bb  cmp     ecx, 1
0x14001f7be  jnz     loc_14001FE18
0x14001f7c4  mov     rcx, [rdi+60h]; Lookaside
0x14001f7c8  mov     rdx, rdi; Entry
0x14001f7cb  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001f7d2  nop     dword ptr [rax+rax+00h]
0x14001f7d7  jmp     loc_14001FE18
0x14001f7dc  mov     edx, 69706E56h; Tag
0x14001f7e1  mov     rcx, rdi; P
0x14001f7e4  call    cs:__imp_ExFreePoolWithTag
0x14001f7eb  nop     dword ptr [rax+rax+00h]
0x14001f7f0  jmp     loc_14001FE18
0x14001f7f5  mov     eax, cs:dword_140013058
0x14001f7fb  mov     bl, [rdi+98h]
0x14001f801  cmp     eax, 5
0x14001f804  jbe     short loc_14001F82A
0x14001f806  mov     r9, [rdi+8]
0x14001f80a  lea     rax, aDereferenceObj; "Dereference object"
0x14001f811  mov     r8, rdi
0x14001f814  mov     [rsp+78h+var_58], rax
0x14001f819  mov     edx, 2CBh
0x14001f81e  lea     rcx, aVmbustlgetpart; "VmbusTlGetPartitionListenerEndpoint"
0x14001f825  call    HvsocketTraceReferenceCount
0x14001f82a  mov     rax, rbp
0x14001f82d  lock xadd [rdi+8], rax
0x14001f833  add     rax, rbp
0x14001f836  test    rax, rax
0x14001f839  jg      short loc_14001F88B
0x14001f83b  jz      short loc_14001F844
0x14001f83d  mov     rcx, r15
0x14001f840  int     29h; Win8: RtlFailFast(ecx)
0x14001f842  jmp     short loc_14001F88B
0x14001f844  mov     rax, [rdi+50h]
0x14001f848  test    rax, rax
0x14001f84b  jz      short loc_14001F855
0x14001f84d  mov     rcx, rdi
0x14001f850  call    _guard_dispatch_icall
0x14001f855  mov     ecx, [rdi+58h]
0x14001f858  sub     ecx, 1
0x14001f85b  jz      short loc_14001F877
0x14001f85d  cmp     ecx, 1
0x14001f860  jnz     short loc_14001F88B
0x14001f862  mov     rcx, [rdi+60h]; Lookaside
0x14001f866  mov     rdx, rdi; Entry
0x14001f869  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001f870  nop     dword ptr [rax+rax+00h]
0x14001f875  jmp     short loc_14001F88B
0x14001f877  mov     edx, 69706E56h; Tag
0x14001f87c  mov     rcx, rdi; P
0x14001f87f  call    cs:__imp_ExFreePoolWithTag
0x14001f886  nop     dword ptr [rax+rax+00h]
0x14001f88b  test    bl, bl
0x14001f88d  jz      loc_14001FB7D
0x14001f893  call    cs:__imp_KeEnterCriticalRegion
0x14001f89a  nop     dword ptr [rax+rax+00h]
0x14001f89f  add     rsi, 10h
0x14001f8a3  mov     rcx, rsi; FastMutex
0x14001f8a6  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001f8ad  nop     dword ptr [rax+rax+00h]
0x14001f8b2  mov     rbx, [rsp+78h+arg_0]
0x14001f8ba  mov     rdx, r13
0x14001f8bd  mov     rcx, rbx
0x14001f8c0  call    VmbusTlFindAndReferenceService
0x14001f8c5  mov     rcx, rsi; FastMutex
0x14001f8c8  mov     rdi, rax
0x14001f8cb  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001f8d2  nop     dword ptr [rax+rax+00h]
0x14001f8d7  call    cs:__imp_KeLeaveCriticalRegion
0x14001f8de  nop     dword ptr [rax+rax+00h]
0x14001f8e3  test    rdi, rdi
0x14001f8e6  jz      loc_14001F9E4
0x14001f8ec  mov     r8, [rsp+78h+arg_28]
0x14001f8f4  lea     rdx, HV_GUID_ZERO
0x14001f8fb  mov     rcx, rdi
0x14001f8fe  call    VmbusTlFindAndReferenceServiceListener
0x14001f903  mov     ebx, eax
0x14001f905  mov     eax, 80000000h
0x14001f90a  lea     ecx, [rbx+rax]
0x14001f90d  test    eax, ecx
0x14001f90f  jnz     short loc_14001F944
0x14001f911  cmp     ebx, r14d
0x14001f914  jz      short loc_14001F944
0x14001f916  mov     eax, cs:dword_140013058
0x14001f91c  cmp     eax, 2
0x14001f91f  jbe     short loc_14001F944
0x14001f921  lea     rax, HV_GUID_ZERO
0x14001f928  mov     r9, r13
0x14001f92b  mov     r8d, ebx
0x14001f92e  mov     [rsp+78h+var_58], rax
0x14001f933  mov     edx, 275h
0x14001f938  lea     rcx, aVmbustlfindand_0; "VmbusTlFindAndReferenceListener"
0x14001f93f  call    HvsocketTraceServiceError
0x14001f944  mov     eax, cs:dword_140013058
0x14001f94a  cmp     eax, 5
0x14001f94d  jbe     short loc_14001F973
0x14001f94f  mov     r9, [rdi+8]
0x14001f953  lea     rax, aDereferenceObj; "Dereference object"
0x14001f95a  mov     r8, rdi
0x14001f95d  mov     [rsp+78h+var_58], rax
0x14001f962  mov     edx, 27Bh
0x14001f967  lea     rcx, aVmbustlfindand_0; "VmbusTlFindAndReferenceListener"
0x14001f96e  call    HvsocketTraceReferenceCount
0x14001f973  mov     rax, rbp
0x14001f976  lock xadd [rdi+8], rax
0x14001f97c  add     rax, rbp
0x14001f97f  test    rax, rax
0x14001f982  jg      short loc_14001F9D4
0x14001f984  jz      short loc_14001F98D
0x14001f986  mov     rcx, r15
0x14001f989  int     29h; Win8: RtlFailFast(ecx)
0x14001f98b  jmp     short loc_14001F9D4
0x14001f98d  mov     rax, [rdi+50h]
0x14001f991  test    rax, rax
0x14001f994  jz      short loc_14001F99E
0x14001f996  mov     rcx, rdi
0x14001f999  call    _guard_dispatch_icall
0x14001f99e  mov     ecx, [rdi+58h]
0x14001f9a1  sub     ecx, 1
0x14001f9a4  jz      short loc_14001F9C0
0x14001f9a6  cmp     ecx, 1
0x14001f9a9  jnz     short loc_14001F9D4
0x14001f9ab  mov     rcx, [rdi+60h]; Lookaside
0x14001f9af  mov     rdx, rdi; Entry
0x14001f9b2  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001f9b9  nop     dword ptr [rax+rax+00h]
0x14001f9be  jmp     short loc_14001F9D4
0x14001f9c0  mov     edx, 69706E56h; Tag
0x14001f9c5  mov     rcx, rdi; P
0x14001f9c8  call    cs:__imp_ExFreePoolWithTag
0x14001f9cf  nop     dword ptr [rax+rax+00h]
0x14001f9d4  test    ebx, ebx
0x14001f9d6  jns     loc_14001FE44
0x14001f9dc  mov     rbx, [rsp+78h+arg_0]
0x14001f9e4  lea     rdi, HV_GUID_CHILDREN
0x14001f9eb  mov     r8d, 10h; Size
0x14001f9f1  mov     rdx, rdi; Buf2
0x14001f9f4  lea     rcx, [rbx+0E8h]; Buf1
0x14001f9fb  call    memcmp
0x14001fa00  test    eax, eax
0x14001fa02  jnz     loc_14001FB75
0x14001fa08  lea     r8d, [rax+10h]; Size
0x14001fa0c  mov     rdx, rdi; Buf2
0x14001fa0f  mov     rcx, r12; Buf1
0x14001fa12  call    memcmp
0x14001fa17  test    eax, eax
0x14001fa19  jz      loc_14001FB75
0x14001fa1f  mov     r8d, 10h; Size
0x14001fa25  lea     rdx, HV_GUID_PARENT; Buf2
0x14001fa2c  mov     rcx, r12; Buf1
0x14001fa2f  call    memcmp
0x14001fa34  test    eax, eax
0x14001fa36  jz      loc_14001FB75
0x14001fa3c  call    cs:__imp_KeEnterCriticalRegion
0x14001fa43  nop     dword ptr [rax+rax+00h]
0x14001fa48  mov     rcx, rsi; FastMutex
0x14001fa4b  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001fa52  nop     dword ptr [rax+rax+00h]
0x14001fa57  mov     rdx, r13
0x14001fa5a  mov     rcx, rbx
0x14001fa5d  call    VmbusTlFindAndReferenceService
0x14001fa62  mov     rcx, rsi; FastMutex
0x14001fa65  mov     rdi, rax
0x14001fa68  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001fa6f  nop     dword ptr [rax+rax+00h]
0x14001fa74  call    cs:__imp_KeLeaveCriticalRegion
0x14001fa7b  nop     dword ptr [rax+rax+00h]
0x14001fa80  test    rdi, rdi
0x14001fa83  jz      loc_14001FB75
0x14001fa89  mov     r8, [rsp+78h+arg_28]
0x14001fa91  lea     rsi, HV_GUID_CHILDREN
0x14001fa98  mov     rdx, rsi
0x14001fa9b  mov     rcx, rdi
0x14001fa9e  call    VmbusTlFindAndReferenceServiceListener
0x14001faa3  mov     ebx, eax
0x14001faa5  mov     eax, 80000000h
0x14001faaa  lea     ecx, [rbx+rax]
0x14001faad  test    eax, ecx
0x14001faaf  jnz     short loc_14001FADD
0x14001fab1  cmp     ebx, r14d
0x14001fab4  jz      short loc_14001FADD
0x14001fab6  mov     eax, cs:dword_140013058
0x14001fabc  cmp     eax, 2
0x14001fabf  jbe     short loc_14001FADD
0x14001fac1  mov     r9, r13
0x14001fac4  mov     [rsp+78h+var_58], rsi
0x14001fac9  mov     r8d, ebx
0x14001facc  lea     rcx, aVmbustlfindand_0; "VmbusTlFindAndReferenceListener"
  ... truncated ...
```
