# VmbusTlSiloTerminateCallback

- ea: `0x140019a10`
- end: `0x140019b68`
- name: `VmbusTlSiloTerminateCallback`
- size: `344`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x140009cf8`
- `0x14000a048`
- `0x14000bfe0`
- `0x140019a10`
- `0x14001edd0`
- `0x14001f540`

## import_xrefs

- `ntoskrnl!PsGetSiloContainerId` at `0x140019a26`
- `ntoskrnl!PsGetSiloContainerId` at `0x140019a26`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019aa6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019aa6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140019a9a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140019a9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019b4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019b4b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019a6c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019a6c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019b35`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019b35`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140019a7c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140019a7c`

## pseudocode

```c
void __fastcall VmbusTlSiloTerminateCallback(__int64 a1)
{
  char *v1; // rsi
  __int64 SiloContainerId; // rdi
  __int64 v3; // rdi
  signed __int64 v4; // rax
  bool v5; // cc
  signed __int64 v6; // rax
  void (__fastcall *v7)(__int64); // rax

  v1 = (char *)VmbusProviderContext;
  SiloContainerId = PsGetSiloContainerId(a1);
  if ( SiloContainerId )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v1 + 16));
    v3 = VmbusTlFindAndReferencePartition(v1, SiloContainerId);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v1 + 16));
    KeLeaveCriticalRegion();
    if ( v3 )
    {
      VmbusTlCleanupPartition((char *)v3);
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlSiloTerminateCallback",
          177,
          v3,
          *(_QWORD *)(v3 + 8),
          (__int64)"Dereference object");
      v4 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v3 + 8), 0xFFFFFFFFFFFFFFFFuLL);
      v5 = v4 <= 1;
      v6 = v4 - 1;
      if ( v5 )
      {
        if ( v6 )
          __fastfail(0xEu);
        v7 = *(void (__fastcall **)(__int64))(v3 + 80);
        if ( v7 )
          v7(v3);
        if ( *(_DWORD *)(v3 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v3, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v3 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v3 + 96), (PVOID)v3);
        }
      }
    }
  }
  else if ( (unsigned int)dword_140013058 > 2 )
  {
    HvsocketTraceError(
      "VmbusTlSiloTerminateCallback",
      166,
      3221225485LL,
      "The host silo should not be terminated while hvsocket is running.");
  }
}

```

## disassembly

```asm
0x140019a10  mov     [rsp+arg_0], rbx
0x140019a15  mov     [rsp+arg_8], rsi
0x140019a1a  push    rdi
0x140019a1b  sub     rsp, 30h
0x140019a1f  mov     rsi, cs:VmbusProviderContext
0x140019a26  call    cs:__imp_PsGetSiloContainerId
0x140019a2d  nop     dword ptr [rax+rax+00h]
0x140019a32  mov     rdi, rax
0x140019a35  test    rax, rax
0x140019a38  jnz     short loc_140019A6C
0x140019a3a  mov     eax, cs:dword_140013058
0x140019a40  cmp     eax, 2
0x140019a43  jbe     loc_140019B57
0x140019a49  lea     r9, aTheHostSiloSho; "The host silo should not be terminated "...
0x140019a50  mov     edx, 0A6h
0x140019a55  mov     r8d, 0C000000Dh
0x140019a5b  lea     rcx, aVmbustlsiloter; "VmbusTlSiloTerminateCallback"
0x140019a62  call    HvsocketTraceError
0x140019a67  jmp     loc_140019B57
0x140019a6c  call    cs:__imp_KeEnterCriticalRegion
0x140019a73  nop     dword ptr [rax+rax+00h]
0x140019a78  lea     rcx, [rsi+10h]; FastMutex
0x140019a7c  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140019a83  nop     dword ptr [rax+rax+00h]
0x140019a88  mov     rdx, rdi
0x140019a8b  mov     rcx, rsi
0x140019a8e  call    VmbusTlFindAndReferencePartition
0x140019a93  lea     rcx, [rsi+10h]; FastMutex
0x140019a97  mov     rdi, rax
0x140019a9a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140019aa1  nop     dword ptr [rax+rax+00h]
0x140019aa6  call    cs:__imp_KeLeaveCriticalRegion
0x140019aad  nop     dword ptr [rax+rax+00h]
0x140019ab2  test    rdi, rdi
0x140019ab5  jz      loc_140019B57
0x140019abb  mov     rcx, rdi; P
0x140019abe  call    VmbusTlCleanupPartition
0x140019ac3  mov     ecx, cs:dword_140013058
0x140019ac9  cmp     ecx, 5
0x140019acc  jbe     short loc_140019AF2
0x140019ace  mov     r9, [rdi+8]
0x140019ad2  lea     rax, aDereferenceObj; "Dereference object"
0x140019ad9  mov     r8, rdi
0x140019adc  mov     [rsp+38h+var_18], rax
0x140019ae1  mov     edx, 0B1h
0x140019ae6  lea     rcx, aVmbustlsiloter; "VmbusTlSiloTerminateCallback"
0x140019aed  call    HvsocketTraceReferenceCount
0x140019af2  or      rax, 0FFFFFFFFFFFFFFFFh
0x140019af6  lock xadd [rdi+8], rax
0x140019afc  sub     rax, 1
0x140019b00  jg      short loc_140019B57
0x140019b02  test    rax, rax
0x140019b05  jz      short loc_140019B10
0x140019b07  mov     ecx, 0Eh
0x140019b0c  int     29h; Win8: RtlFailFast(ecx)
0x140019b0e  jmp     short loc_140019B57
0x140019b10  mov     rax, [rdi+50h]
0x140019b14  test    rax, rax
0x140019b17  jz      short loc_140019B21
0x140019b19  mov     rcx, rdi
0x140019b1c  call    _guard_dispatch_icall
0x140019b21  mov     ecx, [rdi+58h]
0x140019b24  sub     ecx, 1
0x140019b27  jz      short loc_140019B43
0x140019b29  cmp     ecx, 1
0x140019b2c  jnz     short loc_140019B57
0x140019b2e  mov     rcx, [rdi+60h]; Lookaside
0x140019b32  mov     rdx, rdi; Entry
0x140019b35  call    cs:__imp_ExFreeToNPagedLookasideList
0x140019b3c  nop     dword ptr [rax+rax+00h]
0x140019b41  jmp     short loc_140019B57
0x140019b43  mov     edx, 69706E56h; Tag
0x140019b48  mov     rcx, rdi; P
0x140019b4b  call    cs:__imp_ExFreePoolWithTag
0x140019b52  nop     dword ptr [rax+rax+00h]
0x140019b57  mov     rbx, [rsp+38h+arg_0]
0x140019b5c  mov     rsi, [rsp+38h+arg_8]
0x140019b61  add     rsp, 30h
0x140019b65  pop     rdi
0x140019b66  retn
```
