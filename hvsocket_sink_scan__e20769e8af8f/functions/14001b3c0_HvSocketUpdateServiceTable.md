# HvSocketUpdateServiceTable

- ea: `0x14001b3c0`
- end: `0x14001b571`
- name: `HvSocketUpdateServiceTable`
- size: `433`
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
- `0x14001b3c0`
- `0x14001d530`
- `0x140022634`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b442`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b442`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001b436`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001b436`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b545`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b545`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b404`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b404`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b52f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b52f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001b417`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001b417`

## string_xrefs

- `0x14001b474`: `HvSocketUpdateServiceTable`
- `0x14001b4b1`: `HvSocketUpdateServiceTable`
- `0x14001b4e0`: `HvSocketUpdateServiceTable`

## pseudocode

```c
__int64 __fastcall HvSocketUpdateServiceTable(__int64 a1, unsigned int *a2)
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
    updated = VmbusTlUpdateServiceTable(v7, (__int64)(a2 + 2), *a2);
    v8 = updated;
    if ( updated < 0 && (unsigned int)dword_140013058 > 2 )
      HvsocketTraceGuidError("HvSocketUpdateServiceTable", 219, (unsigned int)updated, a1 + 120);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketUpdateServiceTable",
        226,
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
      HvsocketTraceGuidError("HvSocketUpdateServiceTable", 209, 3221225793LL, &v16);
  }
  return v8;
}

```

## disassembly

```asm
0x14001b3c0  mov     [rsp+arg_10], rbx
0x14001b3c5  push    rbp
0x14001b3c6  push    rsi
0x14001b3c7  push    rdi
0x14001b3c8  sub     rsp, 60h
0x14001b3cc  mov     rax, cs:__security_cookie
0x14001b3d3  xor     rax, rsp
0x14001b3d6  mov     [rsp+78h+var_28], rax
0x14001b3db  mov     rdi, [rcx+60h]
0x14001b3df  mov     rbp, rcx
0x14001b3e2  xorps   xmm0, xmm0
0x14001b3e5  mov     rsi, rdx
0x14001b3e8  lea     rdx, [rcx+68h]
0x14001b3ec  lea     rcx, [rsp+78h+var_48]
0x14001b3f1  movups  [rsp+78h+var_38], xmm0
0x14001b3f6  call    HvsocketAddressInfoToPartitionId
0x14001b3fb  movups  xmm1, xmmword ptr [rax]
0x14001b3fe  movdqu  [rsp+78h+var_38], xmm1
0x14001b404  call    cs:__imp_KeEnterCriticalRegion
0x14001b40b  nop     dword ptr [rax+rax+00h]
0x14001b410  lea     rbx, [rdi+10h]
0x14001b414  mov     rcx, rbx; FastMutex
0x14001b417  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001b41e  nop     dword ptr [rax+rax+00h]
0x14001b423  lea     rdx, [rsp+78h+var_38]
0x14001b428  mov     rcx, rdi
0x14001b42b  call    HvSocketFindAndReferenceAnyPartition
0x14001b430  mov     rcx, rbx; FastMutex
0x14001b433  mov     rdi, rax
0x14001b436  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001b43d  nop     dword ptr [rax+rax+00h]
0x14001b442  call    cs:__imp_KeLeaveCriticalRegion
0x14001b449  nop     dword ptr [rax+rax+00h]
0x14001b44e  test    rdi, rdi
0x14001b451  jnz     short loc_14001B485
0x14001b453  mov     eax, cs:dword_140013058
0x14001b459  mov     ebx, 0C0000141h
0x14001b45e  cmp     eax, 2
0x14001b461  jbe     loc_14001B551
0x14001b467  lea     r9, [rsp+78h+var_38]
0x14001b46c  mov     r8d, ebx
0x14001b46f  mov     edx, 0D1h
0x14001b474  lea     rcx, aHvsocketupdate; "HvSocketUpdateServiceTable"
0x14001b47b  call    HvsocketTraceGuidError
0x14001b480  jmp     loc_14001B551
0x14001b485  mov     r8d, [rsi]
0x14001b488  lea     rdx, [rsi+8]
0x14001b48c  mov     rcx, rdi
0x14001b48f  call    VmbusTlUpdateServiceTable
0x14001b494  mov     ebx, eax
0x14001b496  test    eax, eax
0x14001b498  jns     short loc_14001B4BD
0x14001b49a  mov     ecx, cs:dword_140013058
0x14001b4a0  cmp     ecx, 2
0x14001b4a3  jbe     short loc_14001B4BD
0x14001b4a5  lea     r9, [rbp+78h]
0x14001b4a9  mov     r8d, eax
0x14001b4ac  mov     edx, 0DBh
0x14001b4b1  lea     rcx, aHvsocketupdate; "HvSocketUpdateServiceTable"
0x14001b4b8  call    HvsocketTraceGuidError
0x14001b4bd  mov     eax, cs:dword_140013058
0x14001b4c3  cmp     eax, 5
0x14001b4c6  jbe     short loc_14001B4EC
0x14001b4c8  mov     r9, [rdi+8]
0x14001b4cc  lea     rax, aDereferenceObj; "Dereference object"
0x14001b4d3  mov     r8, rdi
0x14001b4d6  mov     [rsp+78h+var_58], rax
0x14001b4db  mov     edx, 0E2h
0x14001b4e0  lea     rcx, aHvsocketupdate; "HvSocketUpdateServiceTable"
0x14001b4e7  call    HvsocketTraceReferenceCount
0x14001b4ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001b4f0  lock xadd [rdi+8], rax
0x14001b4f6  sub     rax, 1
0x14001b4fa  jg      short loc_14001B551
0x14001b4fc  test    rax, rax
0x14001b4ff  jz      short loc_14001B50A
0x14001b501  mov     ecx, 0Eh
0x14001b506  int     29h; Win8: RtlFailFast(ecx)
0x14001b508  jmp     short loc_14001B551
0x14001b50a  mov     rax, [rdi+50h]
0x14001b50e  test    rax, rax
0x14001b511  jz      short loc_14001B51B
0x14001b513  mov     rcx, rdi
0x14001b516  call    _guard_dispatch_icall
0x14001b51b  mov     ecx, [rdi+58h]
0x14001b51e  sub     ecx, 1
0x14001b521  jz      short loc_14001B53D
0x14001b523  cmp     ecx, 1
0x14001b526  jnz     short loc_14001B551
0x14001b528  mov     rcx, [rdi+60h]; Lookaside
0x14001b52c  mov     rdx, rdi; Entry
0x14001b52f  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001b536  nop     dword ptr [rax+rax+00h]
0x14001b53b  jmp     short loc_14001B551
0x14001b53d  mov     edx, 69706E56h; Tag
0x14001b542  mov     rcx, rdi; P
0x14001b545  call    cs:__imp_ExFreePoolWithTag
0x14001b54c  nop     dword ptr [rax+rax+00h]
0x14001b551  mov     eax, ebx
0x14001b553  mov     rcx, [rsp+78h+var_28]
0x14001b558  xor     rcx, rsp; StackCookie
0x14001b55b  call    __security_check_cookie
0x14001b560  mov     rbx, [rsp+78h+arg_10]
0x14001b568  add     rsp, 60h
0x14001b56c  pop     rdi
0x14001b56d  pop     rsi
0x14001b56e  pop     rbp
0x14001b56f  retn
```
