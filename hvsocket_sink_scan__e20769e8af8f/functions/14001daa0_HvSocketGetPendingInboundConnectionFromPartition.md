# HvSocketGetPendingInboundConnectionFromPartition

- ea: `0x14001daa0`
- end: `0x14001dcef`
- name: `HvSocketGetPendingInboundConnectionFromPartition`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x14001d728`

## callees

- `0x14000a048`
- `0x14000a154`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x14001daa0`
- `0x140021ec0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dafe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dc3a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dafe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dc3a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001daf2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001dc2e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001daf2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001dc2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dcc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dcc5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001dac4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001db4a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001dac4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001db4a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001dcaf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001dcaf`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001dad4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001db5a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001dad4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001db5a`

## pseudocode

```c
char __fastcall HvSocketGetPendingInboundConnectionFromPartition(__int64 a1, __int64 a2, const void *a3, __int64 a4)
{
  __int64 v8; // rdi
  char v10; // r13
  bool v11; // bp
  _QWORD *i; // rbx
  _QWORD *v13; // rsi
  unsigned int v14; // eax
  signed __int64 v15; // rax
  bool v16; // cc
  signed __int64 v17; // rax
  void (__fastcall *v18)(__int64); // rax

  *(_QWORD *)a4 = 0;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  v8 = VmbusTlFindAndReferenceService(a1, a2);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  if ( v8 )
  {
    v10 = 0;
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v8 + 16));
    v11 = memcmp(a3, &HV_GUID_ZERO, 0x10u) && memcmp(a3, (const void *)(a1 + 232), 0x10u);
    for ( i = *(_QWORD **)(v8 + 288); i != (_QWORD *)(v8 + 288); i = (_QWORD *)*i )
    {
      v13 = i - 15;
      if ( !v11 || !memcmp(v13 + 112, a3, 0x10u) )
      {
        v14 = dword_140013058;
        v10 = 1;
        *(_QWORD *)a4 = v13;
        if ( v14 > 5 )
          HvsocketTraceReferenceCount(
            (unsigned int)"HvSocketGetPendingInboundConnectionFromPartition",
            1709,
            (_DWORD)i - 120,
            v13[1],
            (__int64)"Reference object");
        if ( _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)a4 + 8LL)) <= 1 )
          __fastfail(0xEu);
        break;
      }
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v8 + 16));
    KeLeaveCriticalRegion();
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketGetPendingInboundConnectionFromPartition",
        1716,
        v8,
        *(_QWORD *)(v8 + 8),
        (__int64)"Dereference object");
    v15 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v8 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v16 = v15 <= 1;
    v17 = v15 - 1;
    if ( v16 )
    {
      if ( v17 )
        __fastfail(0xEu);
      v18 = *(void (__fastcall **)(__int64))(v8 + 80);
      if ( v18 )
        v18(v8);
      if ( *(_DWORD *)(v8 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v8, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v8 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v8 + 96), (PVOID)v8);
      }
    }
    return v10;
  }
  else
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceServiceError(
        (unsigned int)"HvSocketGetPendingInboundConnectionFromPartition",
        1678,
        -1073741275,
        a2,
        a1 + 232);
    return 0;
  }
}

```

## disassembly

```asm
0x14001daa0  push    rbx
0x14001daa2  push    rbp
0x14001daa3  push    rsi
0x14001daa4  push    rdi
0x14001daa5  push    r12
0x14001daa7  push    r13
0x14001daa9  push    r14
0x14001daab  push    r15
0x14001daad  sub     rsp, 38h
0x14001dab1  mov     r15, r9
0x14001dab4  mov     qword ptr [r9], 0
0x14001dabb  mov     r12, r8
0x14001dabe  mov     rbp, rdx
0x14001dac1  mov     rsi, rcx
0x14001dac4  call    cs:__imp_KeEnterCriticalRegion
0x14001dacb  nop     dword ptr [rax+rax+00h]
0x14001dad0  lea     rcx, [rsi+10h]; FastMutex
0x14001dad4  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001dadb  nop     dword ptr [rax+rax+00h]
0x14001dae0  mov     rdx, rbp
0x14001dae3  mov     rcx, rsi
0x14001dae6  call    VmbusTlFindAndReferenceService
0x14001daeb  lea     rcx, [rsi+10h]; FastMutex
0x14001daef  mov     rdi, rax
0x14001daf2  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001daf9  nop     dword ptr [rax+rax+00h]
0x14001dafe  call    cs:__imp_KeLeaveCriticalRegion
0x14001db05  nop     dword ptr [rax+rax+00h]
0x14001db0a  test    rdi, rdi
0x14001db0d  jnz     short loc_14001DB47
0x14001db0f  mov     eax, cs:dword_140013058
0x14001db15  cmp     eax, 2
0x14001db18  jbe     short loc_14001DB40
0x14001db1a  lea     rax, [rsi+0E8h]
0x14001db21  mov     r9, rbp
0x14001db24  mov     edx, 68Eh
0x14001db29  mov     [rsp+78h+var_58], rax
0x14001db2e  mov     r8d, 0C0000225h
0x14001db34  lea     rcx, aHvsocketgetpen; "HvSocketGetPendingInboundConnectionFrom"...
0x14001db3b  call    HvsocketTraceServiceError
0x14001db40  xor     al, al
0x14001db42  jmp     loc_14001DCDD
0x14001db47  xor     r13b, r13b
0x14001db4a  call    cs:__imp_KeEnterCriticalRegion
0x14001db51  nop     dword ptr [rax+rax+00h]
0x14001db56  lea     rcx, [rdi+10h]; FastMutex
0x14001db5a  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001db61  nop     dword ptr [rax+rax+00h]
0x14001db66  mov     ebx, 10h
0x14001db6b  lea     rdx, HV_GUID_ZERO; Buf2
0x14001db72  mov     r8d, ebx; Size
0x14001db75  mov     rcx, r12; Buf1
0x14001db78  call    memcmp
0x14001db7d  test    eax, eax
0x14001db7f  jz      short loc_14001DB9C
0x14001db81  lea     rdx, [rsi+0E8h]; Buf2
0x14001db88  mov     r8d, ebx; Size
0x14001db8b  mov     rcx, r12; Buf1
0x14001db8e  call    memcmp
0x14001db93  test    eax, eax
0x14001db95  jz      short loc_14001DB9C
0x14001db97  mov     bpl, 1
0x14001db9a  jmp     short loc_14001DB9F
0x14001db9c  xor     bpl, bpl
0x14001db9f  lea     r14, [rdi+120h]
0x14001dba6  mov     rbx, [r14]
0x14001dba9  jmp     short loc_14001DBD0
0x14001dbab  lea     rsi, [rbx-78h]
0x14001dbaf  test    bpl, bpl
0x14001dbb2  jz      short loc_14001DBD7
0x14001dbb4  lea     rcx, [rsi+380h]; Buf1
0x14001dbbb  mov     r8d, 10h; Size
0x14001dbc1  mov     rdx, r12; Buf2
0x14001dbc4  call    memcmp
0x14001dbc9  test    eax, eax
0x14001dbcb  jz      short loc_14001DBD7
0x14001dbcd  mov     rbx, [rbx]
0x14001dbd0  cmp     rbx, r14
0x14001dbd3  jnz     short loc_14001DBAB
0x14001dbd5  jmp     short loc_14001DC2A
0x14001dbd7  mov     eax, cs:dword_140013058
0x14001dbdd  mov     r13b, 1
0x14001dbe0  mov     [r15], rsi
0x14001dbe3  cmp     eax, 5
0x14001dbe6  jbe     short loc_14001DC0C
0x14001dbe8  mov     r9, [rsi+8]
0x14001dbec  lea     rax, aReferenceObjec; "Reference object"
0x14001dbf3  mov     r8, rsi
0x14001dbf6  mov     [rsp+78h+var_58], rax
0x14001dbfb  mov     edx, 6ADh
0x14001dc00  lea     rcx, aHvsocketgetpen; "HvSocketGetPendingInboundConnectionFrom"...
0x14001dc07  call    HvsocketTraceReferenceCount
0x14001dc0c  mov     rax, [r15]
0x14001dc0f  mov     edx, 1
0x14001dc14  lock xadd [rax+8], rdx
0x14001dc1a  inc     rdx
0x14001dc1d  cmp     rdx, 1
0x14001dc21  jg      short loc_14001DC2A
0x14001dc23  mov     ecx, 0Eh
0x14001dc28  int     29h; Win8: RtlFailFast(ecx)
0x14001dc2a  lea     rcx, [rdi+10h]; FastMutex
0x14001dc2e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001dc35  nop     dword ptr [rax+rax+00h]
0x14001dc3a  call    cs:__imp_KeLeaveCriticalRegion
0x14001dc41  nop     dword ptr [rax+rax+00h]
0x14001dc46  mov     eax, cs:dword_140013058
0x14001dc4c  cmp     eax, 5
0x14001dc4f  jbe     short loc_14001DC75
0x14001dc51  mov     r9, [rdi+8]
0x14001dc55  lea     rax, aDereferenceObj; "Dereference object"
0x14001dc5c  mov     r8, rdi
0x14001dc5f  mov     [rsp+78h+var_58], rax
0x14001dc64  mov     edx, 6B4h
0x14001dc69  lea     rcx, aHvsocketgetpen; "HvSocketGetPendingInboundConnectionFrom"...
0x14001dc70  call    HvsocketTraceReferenceCount
0x14001dc75  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001dc79  lock xadd [rdi+8], rax
0x14001dc7f  sub     rax, 1
0x14001dc83  jg      short loc_14001DCDA
0x14001dc85  test    rax, rax
0x14001dc88  jnz     short loc_14001DCD3
0x14001dc8a  mov     rax, [rdi+50h]
0x14001dc8e  test    rax, rax
0x14001dc91  jz      short loc_14001DC9B
0x14001dc93  mov     rcx, rdi
0x14001dc96  call    _guard_dispatch_icall
0x14001dc9b  mov     ecx, [rdi+58h]
0x14001dc9e  sub     ecx, 1
0x14001dca1  jz      short loc_14001DCBD
0x14001dca3  cmp     ecx, 1
0x14001dca6  jnz     short loc_14001DCDA
0x14001dca8  mov     rcx, [rdi+60h]; Lookaside
0x14001dcac  mov     rdx, rdi; Entry
0x14001dcaf  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001dcb6  nop     dword ptr [rax+rax+00h]
0x14001dcbb  jmp     short loc_14001DCDA
0x14001dcbd  mov     edx, 69706E56h; Tag
0x14001dcc2  mov     rcx, rdi; P
0x14001dcc5  call    cs:__imp_ExFreePoolWithTag
0x14001dccc  nop     dword ptr [rax+rax+00h]
0x14001dcd1  jmp     short loc_14001DCDA
0x14001dcd3  mov     ecx, 0Eh
0x14001dcd8  int     29h; Win8: RtlFailFast(ecx)
0x14001dcda  mov     al, r13b
0x14001dcdd  add     rsp, 38h
0x14001dce1  pop     r15
0x14001dce3  pop     r14
0x14001dce5  pop     r13
0x14001dce7  pop     r12
0x14001dce9  pop     rdi
0x14001dcea  pop     rsi
0x14001dceb  pop     rbp
0x14001dcec  pop     rbx
0x14001dced  retn
```
