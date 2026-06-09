# HvSocketAddressInfoDestructor

- ea: `0x140018130`
- end: `0x14001833c`
- name: `HvSocketAddressInfoDestructor`
- size: `524`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x140009fa4`
- `0x14000a048`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x140018130`
- `0x1400190c8`
- `0x14001d568`
- `0x14001edd0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400181e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018265`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400181e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018265`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400181d6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018259`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400181d6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018259`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001830a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001830a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001819a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001822b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001819a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001822b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400182f4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400182f4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400181ad`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001823a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400181ad`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001823a`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400181c7`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400181c7`

## pseudocode

```c
void __fastcall HvSocketAddressInfoDestructor(__int64 a1)
{
  void *v1; // rbx
  int v2; // ebp
  __int64 v4; // r14
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int64 v7; // rbx
  signed __int64 v8; // rax
  bool v9; // cc
  signed __int64 v10; // rax
  void (__fastcall *v11)(__int64); // rax
  __int128 v12; // [rsp+30h] [rbp-68h] BYREF
  __int128 v13; // [rsp+40h] [rbp-58h] BYREF
  _OWORD Buf1[2]; // [rsp+50h] [rbp-48h] BYREF
  int v15; // [rsp+70h] [rbp-28h]

  v1 = (void *)(a1 + 104);
  v2 = *(_DWORD *)(a1 + 152);
  v4 = *(_QWORD *)(a1 + 96);
  v15 = v2;
  v5 = *(_OWORD *)(a1 + 120);
  v13 = *(_OWORD *)(a1 + 104);
  v6 = *(_OWORD *)(a1 + 136);
  Buf1[0] = v5;
  Buf1[1] = v6;
  if ( (unsigned int)dword_140013058 > 4 )
    HvsocketTraceMessage("Deleting address info.", a1 + 104);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v4 + 16));
  RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(*(_QWORD *)(a1 + 96) + 1312LL), v1);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v4 + 16));
  KeLeaveCriticalRegion();
  if ( (v2 & 1) == 0 || !memcmp(Buf1, &HV_GUID_ZERO, 0x10u) )
  {
    v12 = *(_OWORD *)HvsocketAddressInfoToPartitionId(&v12, &v13);
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v4 + 16));
    v7 = HvSocketFindAndReferenceUninitializedPartition(v4, &v12);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v4 + 16));
    KeLeaveCriticalRegion();
    if ( v7 )
    {
      VmbusTlCleanupPartition((char *)v7);
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"HvSocketAddressInfoDestructor",
          215,
          v7,
          *(_QWORD *)(v7 + 8),
          (__int64)"Dereference object");
      v8 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v7 + 8), 0xFFFFFFFFFFFFFFFFuLL);
      v9 = v8 <= 1;
      v10 = v8 - 1;
      if ( v9 )
      {
        if ( v10 )
          __fastfail(0xEu);
        v11 = *(void (__fastcall **)(__int64))(v7 + 80);
        if ( v11 )
          v11(v7);
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
  }
}

```

## disassembly

```asm
0x140018130  mov     [rsp+arg_8], rbx
0x140018135  mov     [rsp+arg_10], rbp
0x14001813a  push    rsi
0x14001813b  push    rdi
0x14001813c  push    r14
0x14001813e  sub     rsp, 80h
0x140018145  mov     rax, cs:__security_cookie
0x14001814c  xor     rax, rsp
0x14001814f  mov     [rsp+98h+var_20], rax
0x140018154  mov     eax, cs:dword_140013058
0x14001815a  lea     rbx, [rcx+68h]
0x14001815e  mov     ebp, [rbx+30h]
0x140018161  mov     rsi, rcx
0x140018164  mov     r14, [rcx+60h]
0x140018168  mov     [rsp+98h+var_28], ebp
0x14001816c  movups  xmm0, xmmword ptr [rbx]
0x14001816f  movups  xmm1, xmmword ptr [rbx+10h]
0x140018173  movups  [rsp+98h+var_58], xmm0
0x140018178  movups  xmm0, xmmword ptr [rbx+20h]
0x14001817c  movups  [rsp+98h+Buf1], xmm1
0x140018181  movups  [rsp+98h+var_38], xmm0
0x140018186  cmp     eax, 4
0x140018189  jbe     short loc_14001819A
0x14001818b  mov     rdx, rbx
0x14001818e  lea     rcx, aDeletingAddres; "Deleting address info."
0x140018195  call    HvsocketTraceMessage
0x14001819a  call    cs:__imp_KeEnterCriticalRegion
0x1400181a1  nop     dword ptr [rax+rax+00h]
0x1400181a6  lea     rdi, [r14+10h]
0x1400181aa  mov     rcx, rdi; FastMutex
0x1400181ad  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400181b4  nop     dword ptr [rax+rax+00h]
0x1400181b9  mov     rcx, [rsi+60h]
0x1400181bd  mov     rdx, rbx; Buffer
0x1400181c0  add     rcx, 520h; Table
0x1400181c7  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400181ce  nop     dword ptr [rax+rax+00h]
0x1400181d3  mov     rcx, rdi; FastMutex
0x1400181d6  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400181dd  nop     dword ptr [rax+rax+00h]
0x1400181e2  call    cs:__imp_KeLeaveCriticalRegion
0x1400181e9  nop     dword ptr [rax+rax+00h]
0x1400181ee  test    bpl, 1
0x1400181f2  jz      short loc_140018213
0x1400181f4  mov     r8d, 10h; Size
0x1400181fa  lea     rdx, HV_GUID_ZERO; Buf2
0x140018201  lea     rcx, [rsp+98h+Buf1]; Buf1
0x140018206  call    memcmp
0x14001820b  test    eax, eax
0x14001820d  jnz     loc_140018316
0x140018213  lea     rdx, [rsp+98h+var_58]
0x140018218  lea     rcx, [rsp+98h+var_68]
0x14001821d  call    HvsocketAddressInfoToPartitionId
0x140018222  movups  xmm1, xmmword ptr [rax]
0x140018225  movdqu  [rsp+98h+var_68], xmm1
0x14001822b  call    cs:__imp_KeEnterCriticalRegion
0x140018232  nop     dword ptr [rax+rax+00h]
0x140018237  mov     rcx, rdi; FastMutex
0x14001823a  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140018241  nop     dword ptr [rax+rax+00h]
0x140018246  lea     rdx, [rsp+98h+var_68]
0x14001824b  mov     rcx, r14
0x14001824e  call    HvSocketFindAndReferenceUninitializedPartition
0x140018253  mov     rcx, rdi; FastMutex
0x140018256  mov     rbx, rax
0x140018259  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140018260  nop     dword ptr [rax+rax+00h]
0x140018265  call    cs:__imp_KeLeaveCriticalRegion
0x14001826c  nop     dword ptr [rax+rax+00h]
0x140018271  test    rbx, rbx
0x140018274  jz      loc_140018316
0x14001827a  mov     rcx, rbx; P
0x14001827d  call    VmbusTlCleanupPartition
0x140018282  mov     ecx, cs:dword_140013058
0x140018288  cmp     ecx, 5
0x14001828b  jbe     short loc_1400182B1
0x14001828d  mov     r9, [rbx+8]
0x140018291  lea     rax, aDereferenceObj; "Dereference object"
0x140018298  mov     r8, rbx
0x14001829b  mov     [rsp+98h+var_78], rax
0x1400182a0  mov     edx, 0D7h
0x1400182a5  lea     rcx, aHvsocketaddres; "HvSocketAddressInfoDestructor"
0x1400182ac  call    HvsocketTraceReferenceCount
0x1400182b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400182b5  lock xadd [rbx+8], rax
0x1400182bb  sub     rax, 1
0x1400182bf  jg      short loc_140018316
0x1400182c1  test    rax, rax
0x1400182c4  jz      short loc_1400182CF
0x1400182c6  mov     ecx, 0Eh
0x1400182cb  int     29h; Win8: RtlFailFast(ecx)
0x1400182cd  jmp     short loc_140018316
0x1400182cf  mov     rax, [rbx+50h]
0x1400182d3  test    rax, rax
0x1400182d6  jz      short loc_1400182E0
0x1400182d8  mov     rcx, rbx
0x1400182db  call    _guard_dispatch_icall
0x1400182e0  mov     ecx, [rbx+58h]
0x1400182e3  sub     ecx, 1
0x1400182e6  jz      short loc_140018302
0x1400182e8  cmp     ecx, 1
0x1400182eb  jnz     short loc_140018316
0x1400182ed  mov     rcx, [rbx+60h]; Lookaside
0x1400182f1  mov     rdx, rbx; Entry
0x1400182f4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400182fb  nop     dword ptr [rax+rax+00h]
0x140018300  jmp     short loc_140018316
0x140018302  mov     edx, 69706E56h; Tag
0x140018307  mov     rcx, rbx; P
0x14001830a  call    cs:__imp_ExFreePoolWithTag
0x140018311  nop     dword ptr [rax+rax+00h]
0x140018316  mov     rcx, [rsp+98h+var_20]
0x14001831b  xor     rcx, rsp; StackCookie
0x14001831e  call    __security_check_cookie
0x140018323  lea     r11, [rsp+98h+var_18]
0x14001832b  mov     rbx, [r11+28h]
0x14001832f  mov     rbp, [r11+30h]
0x140018333  mov     rsp, r11
0x140018336  pop     r14
0x140018338  pop     rdi
0x140018339  pop     rsi
0x14001833a  retn
```
