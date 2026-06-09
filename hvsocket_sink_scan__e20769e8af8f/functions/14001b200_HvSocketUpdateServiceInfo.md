# HvSocketUpdateServiceInfo

- ea: `0x14001b200`
- end: `0x14001b3ad`
- name: `HvSocketUpdateServiceInfo`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x140009df0`
- `0x14000a048`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x1400190c8`
- `0x14001b200`
- `0x14001d530`
- `0x1400222b0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b282`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b282`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001b276`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001b276`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b381`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b381`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b244`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b244`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b36b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b36b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001b257`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001b257`

## string_xrefs

- `0x14001b2b4`: `HvSocketUpdateServiceInfo`
- `0x14001b2ed`: `HvSocketUpdateServiceInfo`
- `0x14001b31c`: `HvSocketUpdateServiceInfo`

## pseudocode

```c
__int64 __fastcall HvSocketUpdateServiceInfo(__int64 a1, PNPAGED_LOOKASIDE_LIST *a2)
{
  __int64 v2; // rdi
  __int64 v5; // rax
  struct _FAST_MUTEX *v6; // rcx
  __int64 v7; // rdi
  unsigned int v8; // ebx
  int updated; // eax
  signed __int64 v10; // rax
  bool v11; // cc
  signed __int64 v12; // rax
  void (__fastcall *v13)(__int64); // rax
  _BYTE v15[16]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v16; // [rsp+40h] [rbp-38h] BYREF

  v2 = *(_QWORD *)(a1 + 96);
  v16 = 0;
  v16 = *(_OWORD *)HvsocketAddressInfoToPartitionId(v15, a1 + 104);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v2 + 16));
  v5 = HvSocketFindAndReferenceAnyPartition(v2, &v16);
  v6 = (struct _FAST_MUTEX *)(v2 + 16);
  v7 = v5;
  ExReleaseFastMutexUnsafe(v6);
  KeLeaveCriticalRegion();
  if ( v7 )
  {
    updated = VmbusTlUpdateServiceInfo(v7, a2);
    v8 = updated;
    if ( updated < 0 && (unsigned int)dword_140013058 > 2 )
      HvsocketTraceGuidError("HvSocketUpdateServiceInfo", 269, (unsigned int)updated, a1 + 120);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketUpdateServiceInfo",
        276,
        v7,
        *(_QWORD *)(v7 + 8),
        (__int64)"Dereference object");
    v10 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v7 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v11 = v10 <= 1;
    v12 = v10 - 1;
    if ( v11 )
    {
      if ( v12 )
        __fastfail(0xEu);
      v13 = *(void (__fastcall **)(__int64))(v7 + 80);
      if ( v13 )
        v13(v7);
      if ( *(_DWORD *)(v7 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v7, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v7 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v7 + 96), (PVOID)v7);
      }
    }
  }
  else
  {
    v8 = -1073741503;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceGuidError("HvSocketUpdateServiceInfo", 262, 3221225793LL, &v16);
  }
  return v8;
}

```

## disassembly

```asm
0x14001b200  mov     [rsp+arg_10], rbx
0x14001b205  push    rbp
0x14001b206  push    rsi
0x14001b207  push    rdi
0x14001b208  sub     rsp, 60h
0x14001b20c  mov     rax, cs:__security_cookie
0x14001b213  xor     rax, rsp
0x14001b216  mov     [rsp+78h+var_28], rax
0x14001b21b  mov     rdi, [rcx+60h]
0x14001b21f  mov     rsi, rcx
0x14001b222  xorps   xmm0, xmm0
0x14001b225  mov     rbp, rdx
0x14001b228  lea     rdx, [rcx+68h]
0x14001b22c  lea     rcx, [rsp+78h+var_48]
0x14001b231  movups  [rsp+78h+var_38], xmm0
0x14001b236  call    HvsocketAddressInfoToPartitionId
0x14001b23b  movups  xmm1, xmmword ptr [rax]
0x14001b23e  movdqu  [rsp+78h+var_38], xmm1
0x14001b244  call    cs:__imp_KeEnterCriticalRegion
0x14001b24b  nop     dword ptr [rax+rax+00h]
0x14001b250  lea     rbx, [rdi+10h]
0x14001b254  mov     rcx, rbx; FastMutex
0x14001b257  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001b25e  nop     dword ptr [rax+rax+00h]
0x14001b263  lea     rdx, [rsp+78h+var_38]
0x14001b268  mov     rcx, rdi
0x14001b26b  call    HvSocketFindAndReferenceAnyPartition
0x14001b270  mov     rcx, rbx; FastMutex
0x14001b273  mov     rdi, rax
0x14001b276  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001b27d  nop     dword ptr [rax+rax+00h]
0x14001b282  call    cs:__imp_KeLeaveCriticalRegion
0x14001b289  nop     dword ptr [rax+rax+00h]
0x14001b28e  test    rdi, rdi
0x14001b291  jnz     short loc_14001B2C5
0x14001b293  mov     eax, cs:dword_140013058
0x14001b299  mov     ebx, 0C0000141h
0x14001b29e  cmp     eax, 2
0x14001b2a1  jbe     loc_14001B38D
0x14001b2a7  lea     r9, [rsp+78h+var_38]
0x14001b2ac  mov     r8d, ebx
0x14001b2af  mov     edx, 106h
0x14001b2b4  lea     rcx, aHvsocketupdate_3; "HvSocketUpdateServiceInfo"
0x14001b2bb  call    HvsocketTraceGuidError
0x14001b2c0  jmp     loc_14001B38D
0x14001b2c5  mov     rdx, rbp
0x14001b2c8  mov     rcx, rdi
0x14001b2cb  call    VmbusTlUpdateServiceInfo
0x14001b2d0  mov     ebx, eax
0x14001b2d2  test    eax, eax
0x14001b2d4  jns     short loc_14001B2F9
0x14001b2d6  mov     ecx, cs:dword_140013058
0x14001b2dc  cmp     ecx, 2
0x14001b2df  jbe     short loc_14001B2F9
0x14001b2e1  lea     r9, [rsi+78h]
0x14001b2e5  mov     r8d, eax
0x14001b2e8  mov     edx, 10Dh
0x14001b2ed  lea     rcx, aHvsocketupdate_3; "HvSocketUpdateServiceInfo"
0x14001b2f4  call    HvsocketTraceGuidError
0x14001b2f9  mov     eax, cs:dword_140013058
0x14001b2ff  cmp     eax, 5
0x14001b302  jbe     short loc_14001B328
0x14001b304  mov     r9, [rdi+8]
0x14001b308  lea     rax, aDereferenceObj; "Dereference object"
0x14001b30f  mov     r8, rdi
0x14001b312  mov     [rsp+78h+var_58], rax
0x14001b317  mov     edx, 114h
0x14001b31c  lea     rcx, aHvsocketupdate_3; "HvSocketUpdateServiceInfo"
0x14001b323  call    HvsocketTraceReferenceCount
0x14001b328  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001b32c  lock xadd [rdi+8], rax
0x14001b332  sub     rax, 1
0x14001b336  jg      short loc_14001B38D
0x14001b338  test    rax, rax
0x14001b33b  jz      short loc_14001B346
0x14001b33d  mov     ecx, 0Eh
0x14001b342  int     29h; Win8: RtlFailFast(ecx)
0x14001b344  jmp     short loc_14001B38D
0x14001b346  mov     rax, [rdi+50h]
0x14001b34a  test    rax, rax
0x14001b34d  jz      short loc_14001B357
0x14001b34f  mov     rcx, rdi
0x14001b352  call    _guard_dispatch_icall
0x14001b357  mov     ecx, [rdi+58h]
0x14001b35a  sub     ecx, 1
0x14001b35d  jz      short loc_14001B379
0x14001b35f  cmp     ecx, 1
0x14001b362  jnz     short loc_14001B38D
0x14001b364  mov     rcx, [rdi+60h]; Lookaside
0x14001b368  mov     rdx, rdi; Entry
0x14001b36b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001b372  nop     dword ptr [rax+rax+00h]
0x14001b377  jmp     short loc_14001B38D
0x14001b379  mov     edx, 69706E56h; Tag
0x14001b37e  mov     rcx, rdi; P
0x14001b381  call    cs:__imp_ExFreePoolWithTag
0x14001b388  nop     dword ptr [rax+rax+00h]
0x14001b38d  mov     eax, ebx
0x14001b38f  mov     rcx, [rsp+78h+var_28]
0x14001b394  xor     rcx, rsp; StackCookie
0x14001b397  call    __security_check_cookie
0x14001b39c  mov     rbx, [rsp+78h+arg_10]
0x14001b3a4  add     rsp, 60h
0x14001b3a8  pop     rdi
0x14001b3a9  pop     rsi
0x14001b3aa  pop     rbp
0x14001b3ab  retn
```
