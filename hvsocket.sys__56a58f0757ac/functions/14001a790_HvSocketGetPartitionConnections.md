# HvSocketGetPartitionConnections

- ea: `0x14001a790`
- end: `0x14001a9db`
- name: `HvSocketGetPartitionConnections`
- size: `587`
- prototype: `__int64 __fastcall(__int64, _OWORD *, int, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x140006f1c`
- `0x140009df0`
- `0x14000a048`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x14001a790`
- `0x14001f540`
- `0x140021f5c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a84d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a92b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a84d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a92b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001a841`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001a91f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001a841`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001a91f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a9bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a9bf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a7c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a80f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a88e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a7c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a80f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a88e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a9a9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a9a9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001a7d5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001a822`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001a8a1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001a7d5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001a822`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001a8a1`

## pseudocode

```c
__int64 __fastcall HvSocketGetPartitionConnections(__int64 a1, _OWORD *a2, int a3, __int64 a4, _DWORD *a5)
{
  struct _FAST_MUTEX *v9; // rbx
  const GUID *v10; // rdx
  __int64 v11; // rdi
  unsigned int v12; // ebx
  int v13; // ecx
  __int64 *i; // rax
  __int64 v15; // rdx
  int Connections; // eax
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
    v10 = &HV_GUID_CHILDREN;
  }
  else
  {
    v22[0] = 0;
    if ( !(unsigned __int8)VmbusTlMapSystemIdToPartitionId(a1, a2, v22) )
      v22[0] = *a2;
    KeEnterCriticalRegion();
    v9 = (struct _FAST_MUTEX *)(a1 + 16);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    v10 = (const GUID *)v22;
  }
  v11 = VmbusTlFindAndReferencePartition(a1, v10);
  ExReleaseFastMutexUnsafe(v9);
  KeLeaveCriticalRegion();
  if ( v11 )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v11 + 16));
    v13 = 0;
    for ( i = *(__int64 **)(v11 + 360); i != (__int64 *)(v11 + 360); i = (__int64 *)*i )
      v13 += *((_DWORD *)i + 52);
    v15 = (unsigned int)(a3 - 8);
    *a5 = v13;
    if ( (unsigned int)v15 >= 56 * v13 )
    {
      Connections = VmbusTlGetConnections(v11, v15, a4 + 8, a4);
      v12 = Connections;
      if ( Connections < 0 && (unsigned int)dword_140013058 > 2 )
        HvsocketTraceGuidError("HvSocketGetPartitionConnections", 398, (unsigned int)Connections, a2);
    }
    else
    {
      v12 = -1073741789;
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v11 + 16));
    KeLeaveCriticalRegion();
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketGetPartitionConnections",
        407,
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
      HvsocketTraceGuidError("HvSocketGetPartitionConnections", 378, 3221225793LL, a2);
  }
  return v12;
}

```

## disassembly

```asm
0x14001a790  push    rbx
0x14001a792  push    rbp
0x14001a793  push    rsi
0x14001a794  push    rdi
0x14001a795  push    r14
0x14001a797  push    r15
0x14001a799  sub     rsp, 48h
0x14001a79d  mov     rsi, rdx
0x14001a7a0  mov     r15d, r8d
0x14001a7a3  mov     rdi, rcx
0x14001a7a6  lea     rdx, HV_GUID_ZERO; Buf2
0x14001a7ad  mov     rcx, rsi; Buf1
0x14001a7b0  mov     r8d, 10h; Size
0x14001a7b6  mov     r14, r9
0x14001a7b9  call    memcmp
0x14001a7be  test    eax, eax
0x14001a7c0  jnz     short loc_14001A7EA
0x14001a7c2  call    cs:__imp_KeEnterCriticalRegion
0x14001a7c9  nop     dword ptr [rax+rax+00h]
0x14001a7ce  lea     rbx, [rdi+10h]
0x14001a7d2  mov     rcx, rbx; FastMutex
0x14001a7d5  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001a7dc  nop     dword ptr [rax+rax+00h]
0x14001a7e1  lea     rdx, HV_GUID_CHILDREN
0x14001a7e8  jmp     short loc_14001A833
0x14001a7ea  xorps   xmm0, xmm0
0x14001a7ed  lea     r8, [rsp+78h+var_48]
0x14001a7f2  mov     rdx, rsi
0x14001a7f5  mov     rcx, rdi
0x14001a7f8  movups  [rsp+78h+var_48], xmm0
0x14001a7fd  call    VmbusTlMapSystemIdToPartitionId
0x14001a802  test    al, al
0x14001a804  jnz     short loc_14001A80F
0x14001a806  movups  xmm0, xmmword ptr [rsi]
0x14001a809  movdqu  [rsp+78h+var_48], xmm0
0x14001a80f  call    cs:__imp_KeEnterCriticalRegion
0x14001a816  nop     dword ptr [rax+rax+00h]
0x14001a81b  lea     rbx, [rdi+10h]
0x14001a81f  mov     rcx, rbx; FastMutex
0x14001a822  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001a829  nop     dword ptr [rax+rax+00h]
0x14001a82e  lea     rdx, [rsp+78h+var_48]
0x14001a833  mov     rcx, rdi
0x14001a836  call    VmbusTlFindAndReferencePartition
0x14001a83b  mov     rcx, rbx; FastMutex
0x14001a83e  mov     rdi, rax
0x14001a841  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001a848  nop     dword ptr [rax+rax+00h]
0x14001a84d  call    cs:__imp_KeLeaveCriticalRegion
0x14001a854  nop     dword ptr [rax+rax+00h]
0x14001a859  test    rdi, rdi
0x14001a85c  jnz     short loc_14001A88E
0x14001a85e  mov     eax, cs:dword_140013058
0x14001a864  mov     ebx, 0C0000141h
0x14001a869  cmp     eax, 2
0x14001a86c  jbe     loc_14001A9CB
0x14001a872  mov     r9, rsi
0x14001a875  lea     rcx, aHvsocketgetpar; "HvSocketGetPartitionConnections"
0x14001a87c  mov     r8d, ebx
0x14001a87f  mov     edx, 17Ah
0x14001a884  call    HvsocketTraceGuidError
0x14001a889  jmp     loc_14001A9CB
0x14001a88e  call    cs:__imp_KeEnterCriticalRegion
0x14001a895  nop     dword ptr [rax+rax+00h]
0x14001a89a  lea     rbp, [rdi+10h]
0x14001a89e  mov     rcx, rbp; FastMutex
0x14001a8a1  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001a8a8  nop     dword ptr [rax+rax+00h]
0x14001a8ad  lea     rdx, [rdi+168h]
0x14001a8b4  xor     ecx, ecx
0x14001a8b6  mov     rax, [rdx]
0x14001a8b9  jmp     short loc_14001A8C4
0x14001a8bb  add     ecx, [rax+0D0h]
0x14001a8c1  mov     rax, [rax]
0x14001a8c4  cmp     rax, rdx
0x14001a8c7  jnz     short loc_14001A8BB
0x14001a8c9  mov     rax, [rsp+78h+arg_20]
0x14001a8d1  lea     edx, [r15-8]
0x14001a8d5  mov     [rax], ecx
0x14001a8d7  imul    eax, ecx, 38h ; '8'
0x14001a8da  cmp     edx, eax
0x14001a8dc  jnb     short loc_14001A8E5
0x14001a8de  mov     ebx, 0C0000023h
0x14001a8e3  jmp     short loc_14001A91C
0x14001a8e5  lea     r8, [r14+8]
0x14001a8e9  mov     r9, r14
0x14001a8ec  mov     rcx, rdi
0x14001a8ef  call    VmbusTlGetConnections
0x14001a8f4  mov     ebx, eax
0x14001a8f6  test    eax, eax
0x14001a8f8  jns     short loc_14001A91C
0x14001a8fa  mov     edx, cs:dword_140013058
0x14001a900  cmp     edx, 2
0x14001a903  jbe     short loc_14001A91C
0x14001a905  mov     r9, rsi
0x14001a908  lea     rcx, aHvsocketgetpar; "HvSocketGetPartitionConnections"
0x14001a90f  mov     r8d, eax
0x14001a912  mov     edx, 18Eh
0x14001a917  call    HvsocketTraceGuidError
0x14001a91c  mov     rcx, rbp; FastMutex
0x14001a91f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001a926  nop     dword ptr [rax+rax+00h]
0x14001a92b  call    cs:__imp_KeLeaveCriticalRegion
0x14001a932  nop     dword ptr [rax+rax+00h]
0x14001a937  mov     eax, cs:dword_140013058
0x14001a93d  cmp     eax, 5
0x14001a940  jbe     short loc_14001A966
0x14001a942  mov     r9, [rdi+8]
0x14001a946  lea     rax, aDereferenceObj; "Dereference object"
0x14001a94d  mov     r8, rdi
0x14001a950  mov     [rsp+78h+var_58], rax
0x14001a955  mov     edx, 197h
0x14001a95a  lea     rcx, aHvsocketgetpar; "HvSocketGetPartitionConnections"
0x14001a961  call    HvsocketTraceReferenceCount
0x14001a966  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001a96a  lock xadd [rdi+8], rax
0x14001a970  sub     rax, 1
0x14001a974  jg      short loc_14001A9CB
0x14001a976  test    rax, rax
0x14001a979  jz      short loc_14001A984
0x14001a97b  mov     ecx, 0Eh
0x14001a980  int     29h; Win8: RtlFailFast(ecx)
0x14001a982  jmp     short loc_14001A9CB
0x14001a984  mov     rax, [rdi+50h]
0x14001a988  test    rax, rax
0x14001a98b  jz      short loc_14001A995
0x14001a98d  mov     rcx, rdi
0x14001a990  call    _guard_dispatch_icall
0x14001a995  mov     ecx, [rdi+58h]
0x14001a998  sub     ecx, 1
0x14001a99b  jz      short loc_14001A9B7
0x14001a99d  cmp     ecx, 1
0x14001a9a0  jnz     short loc_14001A9CB
0x14001a9a2  mov     rcx, [rdi+60h]; Lookaside
0x14001a9a6  mov     rdx, rdi; Entry
0x14001a9a9  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001a9b0  nop     dword ptr [rax+rax+00h]
0x14001a9b5  jmp     short loc_14001A9CB
0x14001a9b7  mov     edx, 69706E56h; Tag
0x14001a9bc  mov     rcx, rdi; P
0x14001a9bf  call    cs:__imp_ExFreePoolWithTag
0x14001a9c6  nop     dword ptr [rax+rax+00h]
0x14001a9cb  mov     eax, ebx
0x14001a9cd  add     rsp, 48h
0x14001a9d1  pop     r15
0x14001a9d3  pop     r14
0x14001a9d5  pop     rdi
0x14001a9d6  pop     rsi
0x14001a9d7  pop     rbp
0x14001a9d8  pop     rbx
0x14001a9d9  retn
```
