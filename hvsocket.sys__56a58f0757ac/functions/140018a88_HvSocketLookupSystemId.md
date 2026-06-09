# HvSocketLookupSystemId

- ea: `0x140018a88`
- end: `0x140018bc0`
- name: `HvSocketLookupSystemId`
- size: `312`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140004dec`
- `0x140006f1c`
- `0x14001e5ac`
- `0x140025280`

## callees

- `0x140001608`
- `0x14000a048`
- `0x14000bfe0`
- `0x140018a88`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018b0d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018b0d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018b01`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018b01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ba1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ba1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018abe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018abe`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018b8b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018b8b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018ace`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018ace`

## pseudocode

```c
__int64 __fastcall HvSocketLookupSystemId(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  signed __int64 v6; // rax
  bool v7; // cc
  signed __int64 v8; // rax
  void (__fastcall *v9)(__int64); // rax

  v4 = VmbusTlFindAndReferenceObjectInTable(a1, a1 + 1312, a2, 0);
  if ( !v4 )
    return 3221226021LL;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v4 + 16));
  *(_OWORD *)a3 = *(_OWORD *)(v4 + 104);
  *(_OWORD *)(a3 + 16) = *(_OWORD *)(v4 + 120);
  *(_OWORD *)(a3 + 32) = *(_OWORD *)(v4 + 136);
  *(_DWORD *)(a3 + 48) = *(_DWORD *)(v4 + 152);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v4 + 16));
  KeLeaveCriticalRegion();
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"HvSocketLookupSystemId",
      398,
      v4,
      *(_QWORD *)(v4 + 8),
      (__int64)"Dereference object");
  v6 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v4 + 8), 0xFFFFFFFFFFFFFFFFuLL);
  v7 = v6 <= 1;
  v8 = v6 - 1;
  if ( v7 )
  {
    if ( v8 )
      __fastfail(0xEu);
    v9 = *(void (__fastcall **)(__int64))(v4 + 80);
    if ( v9 )
      v9(v4);
    if ( *(_DWORD *)(v4 + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)v4, 0x69706E56u);
    }
    else if ( *(_DWORD *)(v4 + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v4 + 96), (PVOID)v4);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140018a88  mov     [rsp+arg_0], rbx
0x140018a8d  mov     [rsp+arg_8], rsi
0x140018a92  push    rdi
0x140018a93  sub     rsp, 30h
0x140018a97  mov     rsi, r8
0x140018a9a  xor     r9d, r9d
0x140018a9d  mov     r8, rdx
0x140018aa0  lea     rdx, [rcx+520h]
0x140018aa7  call    VmbusTlFindAndReferenceObjectInTable
0x140018aac  mov     rdi, rax
0x140018aaf  test    rax, rax
0x140018ab2  jnz     short loc_140018ABE
0x140018ab4  mov     eax, 0C0000225h
0x140018ab9  jmp     loc_140018BAF
0x140018abe  call    cs:__imp_KeEnterCriticalRegion
0x140018ac5  nop     dword ptr [rax+rax+00h]
0x140018aca  lea     rcx, [rdi+10h]; FastMutex
0x140018ace  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140018ad5  nop     dword ptr [rax+rax+00h]
0x140018ada  movups  xmm0, xmmword ptr [rdi+68h]
0x140018ade  lea     rcx, [rdi+10h]; FastMutex
0x140018ae2  movups  xmmword ptr [rsi], xmm0
0x140018ae5  movups  xmm1, xmmword ptr [rdi+78h]
0x140018ae9  movups  xmmword ptr [rsi+10h], xmm1
0x140018aed  movups  xmm0, xmmword ptr [rdi+88h]
0x140018af4  movups  xmmword ptr [rsi+20h], xmm0
0x140018af8  mov     eax, [rdi+98h]
0x140018afe  mov     [rsi+30h], eax
0x140018b01  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140018b08  nop     dword ptr [rax+rax+00h]
0x140018b0d  call    cs:__imp_KeLeaveCriticalRegion
0x140018b14  nop     dword ptr [rax+rax+00h]
0x140018b19  mov     eax, cs:dword_140013058
0x140018b1f  cmp     eax, 5
0x140018b22  jbe     short loc_140018B48
0x140018b24  mov     r9, [rdi+8]
0x140018b28  lea     rax, aDereferenceObj; "Dereference object"
0x140018b2f  mov     r8, rdi
0x140018b32  mov     [rsp+38h+var_18], rax
0x140018b37  mov     edx, 18Eh
0x140018b3c  lea     rcx, aHvsocketlookup; "HvSocketLookupSystemId"
0x140018b43  call    HvsocketTraceReferenceCount
0x140018b48  or      rax, 0FFFFFFFFFFFFFFFFh
0x140018b4c  lock xadd [rdi+8], rax
0x140018b52  sub     rax, 1
0x140018b56  jg      short loc_140018BAD
0x140018b58  test    rax, rax
0x140018b5b  jz      short loc_140018B66
0x140018b5d  mov     ecx, 0Eh
0x140018b62  int     29h; Win8: RtlFailFast(ecx)
0x140018b64  jmp     short loc_140018BAD
0x140018b66  mov     rax, [rdi+50h]
0x140018b6a  test    rax, rax
0x140018b6d  jz      short loc_140018B77
0x140018b6f  mov     rcx, rdi
0x140018b72  call    _guard_dispatch_icall
0x140018b77  mov     ecx, [rdi+58h]
0x140018b7a  sub     ecx, 1
0x140018b7d  jz      short loc_140018B99
0x140018b7f  cmp     ecx, 1
0x140018b82  jnz     short loc_140018BAD
0x140018b84  mov     rcx, [rdi+60h]; Lookaside
0x140018b88  mov     rdx, rdi; Entry
0x140018b8b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140018b92  nop     dword ptr [rax+rax+00h]
0x140018b97  jmp     short loc_140018BAD
0x140018b99  mov     edx, 69706E56h; Tag
0x140018b9e  mov     rcx, rdi; P
0x140018ba1  call    cs:__imp_ExFreePoolWithTag
0x140018ba8  nop     dword ptr [rax+rax+00h]
0x140018bad  xor     eax, eax
0x140018baf  mov     rbx, [rsp+38h+arg_0]
0x140018bb4  mov     rsi, [rsp+38h+arg_8]
0x140018bb9  add     rsp, 30h
0x140018bbd  pop     rdi
0x140018bbe  retn
```
