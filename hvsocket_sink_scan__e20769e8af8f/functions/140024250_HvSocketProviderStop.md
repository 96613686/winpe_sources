# HvSocketProviderStop

- ea: `0x140024250`
- end: `0x140024468`
- name: `HvSocketProviderStop`
- size: `536`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140009cf8`
- `0x14000a048`
- `0x14000bfe0`
- `0x140024250`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024349`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024374`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024349`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024374`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002433d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140024368`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002433d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140024368`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002432e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024452`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002432e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024452`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140024262`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140024262`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024318`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002443c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024318`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002443c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140024275`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140024275`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x140024394`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x140024394`
- `NETIO!NmrDeregisterProvider` at `0x140024384`
- `NETIO!NmrDeregisterProvider` at `0x140024384`

## pseudocode

```c
void __fastcall HvSocketProviderStop(__int64 a1, __int64 a2, __int64 a3)
{
  signed __int64 v6; // rax
  bool v7; // cc
  signed __int64 v8; // rax
  void (__fastcall *v9)(__int64); // rax
  NTSTATUS v10; // eax
  signed __int64 v11; // rax
  signed __int64 v12; // rax
  void (__fastcall *v13)(__int64); // rax

  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 16));
  if ( a1 && *(_QWORD *)(a3 + 1432) == a1 )
    *(_OWORD *)(a3 + 1432) = 0;
  if ( *(_QWORD *)(a3 + 176) == a2 )
  {
    *(_QWORD *)(a3 + 176) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 16));
    KeLeaveCriticalRegion();
    NmrDeregisterProvider(*(HANDLE *)(a3 + 96));
    v10 = NmrWaitForProviderDeregisterComplete(*(HANDLE *)(a3 + 96));
    if ( v10 < 0 && (unsigned int)dword_140013058 > 2 )
      HvsocketTraceError("HvSocketProviderStop", 581, (unsigned int)v10, "Failed to deregister TL provider.");
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketProviderStop",
        587,
        a3,
        *(_QWORD *)(a3 + 8),
        (__int64)"Dereference object");
    v11 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a3 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v7 = v11 <= 1;
    v12 = v11 - 1;
    if ( v7 )
    {
      if ( v12 )
        __fastfail(0xEu);
      v13 = *(void (__fastcall **)(__int64))(a3 + 80);
      if ( v13 )
        v13(a3);
      if ( *(_DWORD *)(a3 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)a3, 0x69706E56u);
      }
      else if ( *(_DWORD *)(a3 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a3 + 96), (PVOID)a3);
      }
    }
  }
  else
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketProviderStop",
        558,
        a3,
        *(_QWORD *)(a3 + 8),
        (__int64)"Dereference object");
    v6 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a3 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v7 = v6 <= 1;
    v8 = v6 - 1;
    if ( v7 )
    {
      if ( v8 )
        __fastfail(0xEu);
      v9 = *(void (__fastcall **)(__int64))(a3 + 80);
      if ( v9 )
        v9(a3);
      if ( *(_DWORD *)(a3 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)a3, 0x69706E56u);
      }
      else if ( *(_DWORD *)(a3 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a3 + 96), (PVOID)a3);
      }
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 16));
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x140024250  push    rbx
0x140024252  push    rbp
0x140024253  push    rsi
0x140024254  push    rdi
0x140024255  sub     rsp, 38h
0x140024259  mov     rbx, r8
0x14002425c  mov     rbp, rdx
0x14002425f  mov     rsi, rcx
0x140024262  call    cs:__imp_KeEnterCriticalRegion
0x140024269  nop     dword ptr [rax+rax+00h]
0x14002426e  lea     rdi, [rbx+10h]
0x140024272  mov     rcx, rdi; FastMutex
0x140024275  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002427c  nop     dword ptr [rax+rax+00h]
0x140024281  test    rsi, rsi
0x140024284  jz      short loc_140024299
0x140024286  cmp     [rbx+598h], rsi
0x14002428d  jnz     short loc_140024299
0x14002428f  xorps   xmm0, xmm0
0x140024292  movups  xmmword ptr [rbx+598h], xmm0
0x140024299  cmp     [rbx+0B0h], rbp
0x1400242a0  jz      loc_14002435A
0x1400242a6  mov     eax, cs:dword_140013058
0x1400242ac  cmp     eax, 5
0x1400242af  jbe     short loc_1400242D5
0x1400242b1  mov     r9, [rbx+8]
0x1400242b5  lea     rax, aDereferenceObj; "Dereference object"
0x1400242bc  mov     r8, rbx
0x1400242bf  mov     [rsp+58h+var_38], rax
0x1400242c4  mov     edx, 22Eh
0x1400242c9  lea     rcx, aHvsocketprovid; "HvSocketProviderStop"
0x1400242d0  call    HvsocketTraceReferenceCount
0x1400242d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400242d9  lock xadd [rbx+8], rax
0x1400242df  sub     rax, 1
0x1400242e3  jg      short loc_14002433A
0x1400242e5  test    rax, rax
0x1400242e8  jz      short loc_1400242F3
0x1400242ea  mov     ecx, 0Eh
0x1400242ef  int     29h; Win8: RtlFailFast(ecx)
0x1400242f1  jmp     short loc_14002433A
0x1400242f3  mov     rax, [rbx+50h]
0x1400242f7  test    rax, rax
0x1400242fa  jz      short loc_140024304
0x1400242fc  mov     rcx, rbx
0x1400242ff  call    _guard_dispatch_icall
0x140024304  mov     ecx, [rbx+58h]
0x140024307  sub     ecx, 1
0x14002430a  jz      short loc_140024326
0x14002430c  cmp     ecx, 1
0x14002430f  jnz     short loc_14002433A
0x140024311  mov     rcx, [rbx+60h]; Lookaside
0x140024315  mov     rdx, rbx; Entry
0x140024318  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002431f  nop     dword ptr [rax+rax+00h]
0x140024324  jmp     short loc_14002433A
0x140024326  mov     edx, 69706E56h; Tag
0x14002432b  mov     rcx, rbx; P
0x14002432e  call    cs:__imp_ExFreePoolWithTag
0x140024335  nop     dword ptr [rax+rax+00h]
0x14002433a  mov     rcx, rdi; FastMutex
0x14002433d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140024344  nop     dword ptr [rax+rax+00h]
0x140024349  call    cs:__imp_KeLeaveCriticalRegion
0x140024350  nop     dword ptr [rax+rax+00h]
0x140024355  jmp     loc_14002445E
0x14002435a  mov     rcx, rdi; FastMutex
0x14002435d  mov     qword ptr [rbx+0B0h], 0
0x140024368  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002436f  nop     dword ptr [rax+rax+00h]
0x140024374  call    cs:__imp_KeLeaveCriticalRegion
0x14002437b  nop     dword ptr [rax+rax+00h]
0x140024380  mov     rcx, [rbx+60h]; NmrProviderHandle
0x140024384  call    cs:__imp_NmrDeregisterProvider
0x14002438b  nop     dword ptr [rax+rax+00h]
0x140024390  mov     rcx, [rbx+60h]; NmrProviderHandle
0x140024394  call    cs:__imp_NmrWaitForProviderDeregisterComplete
0x14002439b  nop     dword ptr [rax+rax+00h]
0x1400243a0  test    eax, eax
0x1400243a2  jns     short loc_1400243CA
0x1400243a4  mov     ecx, cs:dword_140013058
0x1400243aa  cmp     ecx, 2
0x1400243ad  jbe     short loc_1400243CA
0x1400243af  lea     r9, aFailedToDeregi; "Failed to deregister TL provider."
0x1400243b6  mov     r8d, eax
0x1400243b9  mov     edx, 245h
0x1400243be  lea     rcx, aHvsocketprovid; "HvSocketProviderStop"
0x1400243c5  call    HvsocketTraceError
0x1400243ca  mov     eax, cs:dword_140013058
0x1400243d0  cmp     eax, 5
0x1400243d3  jbe     short loc_1400243F9
0x1400243d5  mov     r9, [rbx+8]
0x1400243d9  lea     rax, aDereferenceObj; "Dereference object"
0x1400243e0  mov     r8, rbx
0x1400243e3  mov     [rsp+58h+var_38], rax
0x1400243e8  mov     edx, 24Bh
0x1400243ed  lea     rcx, aHvsocketprovid; "HvSocketProviderStop"
0x1400243f4  call    HvsocketTraceReferenceCount
0x1400243f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400243fd  lock xadd [rbx+8], rax
0x140024403  sub     rax, 1
0x140024407  jg      short loc_14002445E
0x140024409  test    rax, rax
0x14002440c  jz      short loc_140024417
0x14002440e  mov     ecx, 0Eh
0x140024413  int     29h; Win8: RtlFailFast(ecx)
0x140024415  jmp     short loc_14002445E
0x140024417  mov     rax, [rbx+50h]
0x14002441b  test    rax, rax
0x14002441e  jz      short loc_140024428
0x140024420  mov     rcx, rbx
0x140024423  call    _guard_dispatch_icall
0x140024428  mov     ecx, [rbx+58h]
0x14002442b  sub     ecx, 1
0x14002442e  jz      short loc_14002444A
0x140024430  cmp     ecx, 1
0x140024433  jnz     short loc_14002445E
0x140024435  mov     rcx, [rbx+60h]; Lookaside
0x140024439  mov     rdx, rbx; Entry
0x14002443c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140024443  nop     dword ptr [rax+rax+00h]
0x140024448  jmp     short loc_14002445E
0x14002444a  mov     edx, 69706E56h; Tag
0x14002444f  mov     rcx, rbx; P
0x140024452  call    cs:__imp_ExFreePoolWithTag
0x140024459  nop     dword ptr [rax+rax+00h]
0x14002445e  add     rsp, 38h
0x140024462  pop     rdi
0x140024463  pop     rsi
0x140024464  pop     rbp
0x140024465  pop     rbx
0x140024466  retn
```
