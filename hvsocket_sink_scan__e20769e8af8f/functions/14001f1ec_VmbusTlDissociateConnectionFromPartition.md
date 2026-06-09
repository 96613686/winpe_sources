# VmbusTlDissociateConnectionFromPartition

- ea: `0x14001f1ec`
- end: `0x14001f45e`
- name: `VmbusTlDissociateConnectionFromPartition`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x140005280`

## callees

- `0x140001508`
- `0x140001608`
- `0x140009060`
- `0x14000a048`
- `0x14000bfe0`
- `0x14001f1ec`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001f387`
- `ntoskrnl!KeSetEvent` at `0x14001f387`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f3aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f3aa`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001f39e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001f39e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f30f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f43c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f30f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f43c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f21f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f21f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f2f9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f426`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f2f9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f426`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001f22f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001f22f`

## pseudocode

```c
void __fastcall VmbusTlDissociateConnectionFromPartition(__int64 a1)
{
  bool v1; // zf
  __int64 v3; // rdi
  __int64 v4; // r9
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rax
  void (__fastcall *v8)(__int64); // rax
  __int64 v9; // rax
  int v10; // edx
  __int64 v11; // rdi
  __int64 v12; // rax
  void (__fastcall *v13)(__int64); // rax

  v1 = *(_QWORD *)(a1 + 872) == 0;
  *(_BYTE *)(a1 + 172) = 0;
  if ( !v1 )
    VmbusTlDissociateEndpointFromService((char *)a1);
  v3 = *(_QWORD *)(a1 + 736);
  if ( v3 )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v3 + 16));
    LOBYTE(v4) = 1;
    v6 = VmbusTlFindAndReferenceObjectInTable(*(_QWORD *)(a1 + 736), *(_QWORD *)(a1 + 736) + 256LL, a1 + 464, v4);
    if ( v6 == a1 )
      VmbusTlDeleteObjectFromTable(v5, (struct _RTL_AVL_TABLE *)(*(_QWORD *)(a1 + 736) + 256LL), (void *)(a1 + 464), a1);
    if ( v6 )
    {
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlDissociateConnectionFromPartition",
          1851,
          v6,
          *(_QWORD *)(v6 + 8),
          (__int64)"Dereference object");
      v7 = _InterlockedDecrement64((volatile signed __int64 *)(v6 + 8));
      if ( v7 <= 0 )
      {
        if ( v7 )
          __fastfail(0xEu);
        v8 = *(void (__fastcall **)(__int64))(v6 + 80);
        if ( v8 )
          v8(v6);
        if ( *(_DWORD *)(v6 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v6, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v6 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v6 + 96), (PVOID)v6);
        }
      }
    }
    --*(_DWORD *)(*(_QWORD *)(a1 + 736) + 408LL);
    if ( *(_BYTE *)(a1 + 185) )
      --*(_DWORD *)(*(_QWORD *)(a1 + 736) + 412LL);
    v9 = *(_QWORD *)(a1 + 736);
    if ( !*(_QWORD *)(v9 + 400) )
      goto LABEL_27;
    v10 = *(_DWORD *)(v9 + 408);
    if ( !*(_BYTE *)(v9 + 392) || *(_BYTE *)(v9 + 393) )
    {
      if ( !v10 )
LABEL_26:
        KeSetEvent(*(PRKEVENT *)(v9 + 400), 0, 0);
    }
    else if ( v10 == *(_DWORD *)(v9 + 412) )
    {
      goto LABEL_26;
    }
LABEL_27:
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 736) + 16LL));
    KeLeaveCriticalRegion();
    v11 = *(_QWORD *)(a1 + 736);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlDissociateConnectionFromPartition",
        1885,
        *(_QWORD *)(a1 + 736),
        *(_QWORD *)(v11 + 8),
        (__int64)"Dereference object");
    v12 = _InterlockedDecrement64((volatile signed __int64 *)(v11 + 8));
    if ( v12 <= 0 )
    {
      if ( v12 )
        __fastfail(0xEu);
      v13 = *(void (__fastcall **)(__int64))(v11 + 80);
      if ( v13 )
        v13(v11);
      if ( *(_DWORD *)(v11 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v11, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v11 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v11 + 96), (PVOID)v11);
      }
    }
    *(_QWORD *)(a1 + 736) = 0;
  }
}

```

## disassembly

```asm
0x14001f1ec  push    rbx
0x14001f1ee  push    rsi
0x14001f1ef  push    rdi
0x14001f1f0  push    r12
0x14001f1f2  sub     rsp, 38h
0x14001f1f6  cmp     qword ptr [rcx+368h], 0
0x14001f1fe  mov     rbx, rcx
0x14001f201  mov     byte ptr [rcx+0ACh], 0
0x14001f208  jz      short loc_14001F20F
0x14001f20a  call    VmbusTlDissociateEndpointFromService
0x14001f20f  mov     rdi, [rbx+2E0h]
0x14001f216  test    rdi, rdi
0x14001f219  jz      loc_14001F453
0x14001f21f  call    cs:__imp_KeEnterCriticalRegion
0x14001f226  nop     dword ptr [rax+rax+00h]
0x14001f22b  lea     rcx, [rdi+10h]; FastMutex
0x14001f22f  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001f236  nop     dword ptr [rax+rax+00h]
0x14001f23b  mov     rcx, [rbx+2E0h]
0x14001f242  lea     rsi, [rbx+1D0h]
0x14001f249  mov     r9b, 1
0x14001f24c  mov     r8, rsi
0x14001f24f  lea     rdx, [rcx+100h]
0x14001f256  call    VmbusTlFindAndReferenceObjectInTable
0x14001f25b  mov     rdi, rax
0x14001f25e  cmp     rax, rbx
0x14001f261  jnz     short loc_14001F27C
0x14001f263  mov     rdx, [rbx+2E0h]
0x14001f26a  mov     r9, rbx
0x14001f26d  add     rdx, 100h
0x14001f274  mov     r8, rsi
0x14001f277  call    VmbusTlDeleteObjectFromTable
0x14001f27c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14001f280  lea     r12, aDereferenceObj; "Dereference object"
0x14001f287  test    rdi, rdi
0x14001f28a  jz      loc_14001F31B
0x14001f290  mov     eax, cs:dword_140013058
0x14001f296  cmp     eax, 5
0x14001f299  jbe     short loc_14001F2B8
0x14001f29b  mov     r9, [rdi+8]
0x14001f29f  lea     rcx, aVmbustldissoci_1; "VmbusTlDissociateConnectionFromPartitio"...
0x14001f2a6  mov     r8, rdi
0x14001f2a9  mov     [rsp+58h+var_38], r12
0x14001f2ae  mov     edx, 73Bh
0x14001f2b3  call    HvsocketTraceReferenceCount
0x14001f2b8  mov     rax, rsi
0x14001f2bb  lock xadd [rdi+8], rax
0x14001f2c1  add     rax, rsi
0x14001f2c4  test    rax, rax
0x14001f2c7  jg      short loc_14001F31B
0x14001f2c9  jz      short loc_14001F2D4
0x14001f2cb  mov     ecx, 0Eh
0x14001f2d0  int     29h; Win8: RtlFailFast(ecx)
0x14001f2d2  jmp     short loc_14001F31B
0x14001f2d4  mov     rax, [rdi+50h]
0x14001f2d8  test    rax, rax
0x14001f2db  jz      short loc_14001F2E5
0x14001f2dd  mov     rcx, rdi
0x14001f2e0  call    _guard_dispatch_icall
0x14001f2e5  mov     ecx, [rdi+58h]
0x14001f2e8  sub     ecx, 1
0x14001f2eb  jz      short loc_14001F307
0x14001f2ed  cmp     ecx, 1
0x14001f2f0  jnz     short loc_14001F31B
0x14001f2f2  mov     rcx, [rdi+60h]; Lookaside
0x14001f2f6  mov     rdx, rdi; Entry
0x14001f2f9  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001f300  nop     dword ptr [rax+rax+00h]
0x14001f305  jmp     short loc_14001F31B
0x14001f307  mov     edx, 69706E56h; Tag
0x14001f30c  mov     rcx, rdi; P
0x14001f30f  call    cs:__imp_ExFreePoolWithTag
0x14001f316  nop     dword ptr [rax+rax+00h]
0x14001f31b  mov     rax, [rbx+2E0h]
0x14001f322  or      ecx, 0FFFFFFFFh
0x14001f325  add     [rax+198h], ecx
0x14001f32b  cmp     byte ptr [rbx+0B9h], 0
0x14001f332  jz      short loc_14001F341
0x14001f334  mov     rax, [rbx+2E0h]
0x14001f33b  add     [rax+19Ch], ecx
0x14001f341  mov     rax, [rbx+2E0h]
0x14001f348  mov     r9, [rax+190h]
0x14001f34f  test    r9, r9
0x14001f352  jz      short loc_14001F393
0x14001f354  mov     edx, [rax+198h]
0x14001f35a  test    edx, edx
0x14001f35c  setz    cl
0x14001f35f  cmp     byte ptr [rax+188h], 0
0x14001f366  jz      short loc_14001F37B
0x14001f368  cmp     byte ptr [rax+189h], 0
0x14001f36f  jnz     short loc_14001F37B
0x14001f371  cmp     edx, [rax+19Ch]
0x14001f377  jnz     short loc_14001F393
0x14001f379  jmp     short loc_14001F37F
0x14001f37b  test    cl, cl
0x14001f37d  jz      short loc_14001F393
0x14001f37f  xor     r8d, r8d; Wait
0x14001f382  xor     edx, edx; Increment
0x14001f384  mov     rcx, r9; Event
0x14001f387  call    cs:__imp_KeSetEvent
0x14001f38e  nop     dword ptr [rax+rax+00h]
0x14001f393  mov     rcx, [rbx+2E0h]
0x14001f39a  add     rcx, 10h; FastMutex
0x14001f39e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001f3a5  nop     dword ptr [rax+rax+00h]
0x14001f3aa  call    cs:__imp_KeLeaveCriticalRegion
0x14001f3b1  nop     dword ptr [rax+rax+00h]
0x14001f3b6  mov     eax, cs:dword_140013058
0x14001f3bc  mov     rdi, [rbx+2E0h]
0x14001f3c3  cmp     eax, 5
0x14001f3c6  jbe     short loc_14001F3E5
0x14001f3c8  mov     r9, [rdi+8]
0x14001f3cc  lea     rcx, aVmbustldissoci_1; "VmbusTlDissociateConnectionFromPartitio"...
0x14001f3d3  mov     r8, rdi
0x14001f3d6  mov     [rsp+58h+var_38], r12
0x14001f3db  mov     edx, 75Dh
0x14001f3e0  call    HvsocketTraceReferenceCount
0x14001f3e5  mov     rax, rsi
0x14001f3e8  lock xadd [rdi+8], rax
0x14001f3ee  add     rax, rsi
0x14001f3f1  test    rax, rax
0x14001f3f4  jg      short loc_14001F448
0x14001f3f6  jz      short loc_14001F401
0x14001f3f8  mov     ecx, 0Eh
0x14001f3fd  int     29h; Win8: RtlFailFast(ecx)
0x14001f3ff  jmp     short loc_14001F448
0x14001f401  mov     rax, [rdi+50h]
0x14001f405  test    rax, rax
0x14001f408  jz      short loc_14001F412
0x14001f40a  mov     rcx, rdi
0x14001f40d  call    _guard_dispatch_icall
0x14001f412  mov     ecx, [rdi+58h]
0x14001f415  sub     ecx, 1
0x14001f418  jz      short loc_14001F434
0x14001f41a  cmp     ecx, 1
0x14001f41d  jnz     short loc_14001F448
0x14001f41f  mov     rcx, [rdi+60h]; Lookaside
0x14001f423  mov     rdx, rdi; Entry
0x14001f426  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001f42d  nop     dword ptr [rax+rax+00h]
0x14001f432  jmp     short loc_14001F448
0x14001f434  mov     edx, 69706E56h; Tag
0x14001f439  mov     rcx, rdi; P
0x14001f43c  call    cs:__imp_ExFreePoolWithTag
0x14001f443  nop     dword ptr [rax+rax+00h]
0x14001f448  mov     qword ptr [rbx+2E0h], 0
0x14001f453  add     rsp, 38h
0x14001f457  pop     r12
0x14001f459  pop     rdi
0x14001f45a  pop     rsi
0x14001f45b  pop     rbx
0x14001f45c  retn
```
