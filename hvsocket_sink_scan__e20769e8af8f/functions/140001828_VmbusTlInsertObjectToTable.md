# VmbusTlInsertObjectToTable

- ea: `0x140001828`
- end: `0x140001ac0`
- name: `VmbusTlInsertObjectToTable`
- size: `664`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140007034`
- `0x140008ab8`
- `0x140018350`

## callees

- `0x140001828`
- `0x140009df0`
- `0x14000a048`
- `0x14000bfa0`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400018f8`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400018f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400019dc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400019dc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400019d0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400019d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400019b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001a98`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400019b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001a98`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400018ba`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400018ba`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000199e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140001a82`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000199e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140001a82`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400018ca`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400018ca`

## pseudocode

```c
__int64 __fastcall VmbusTlInsertObjectToTable(__int64 a1, struct _RTL_AVL_TABLE *a2, __int128 *a3, __int64 a4, char a5)
{
  __int128 v9; // xmm0
  _QWORD *inserted; // rax
  int v11; // edi
  signed __int64 v12; // rax
  bool v13; // cc
  signed __int64 v14; // rax
  void (__fastcall *v15)(__int64); // rax
  signed __int64 v16; // rax
  signed __int64 v17; // rax
  void (__fastcall *v18)(__int64); // rax
  unsigned __int8 NewElement[8]; // [rsp+30h] [rbp-58h] BYREF
  __int128 Buffer; // [rsp+38h] [rbp-50h] BYREF
  __int64 v22; // [rsp+48h] [rbp-40h]

  v22 = 0;
  NewElement[0] = 0;
  Buffer = 0;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlInsertObjectToTable",
      319,
      a4,
      *(_QWORD *)(a4 + 8),
      (__int64)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)(a4 + 8)) <= 1 )
    __fastfail(0xEu);
  if ( !a5 )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  }
  v9 = *a3;
  v22 = a4;
  Buffer = v9;
  inserted = RtlInsertElementGenericTableAvl(a2, &Buffer, 0x18u, NewElement);
  if ( !inserted )
  {
    v11 = -1073741801;
    goto LABEL_24;
  }
  if ( !NewElement[0] )
  {
    if ( inserted[2] != a4 )
    {
      v11 = -1073741771;
      goto LABEL_24;
    }
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlInsertObjectToTable",
        347,
        a4,
        *(_QWORD *)(a4 + 8),
        (__int64)"Dereference object");
    v12 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a4 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v13 = v12 <= 1;
    v14 = v12 - 1;
    if ( v13 )
    {
      if ( v14 )
        __fastfail(0xEu);
      v15 = *(void (__fastcall **)(__int64))(a4 + 80);
      if ( v15 )
        v15(a4);
      if ( *(_DWORD *)(a4 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)a4, 0x69706E56u);
      }
      else if ( *(_DWORD *)(a4 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a4 + 96), (PVOID)a4);
      }
    }
  }
  v11 = 0;
LABEL_24:
  if ( !a5 )
  {
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    KeLeaveCriticalRegion();
  }
  if ( v11 < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceGuidError("VmbusTlInsertObjectToTable", 363, (unsigned int)v11, a3);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlInsertObjectToTable",
        364,
        a4,
        *(_QWORD *)(a4 + 8),
        (__int64)"Dereference object");
    v16 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a4 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v13 = v16 <= 1;
    v17 = v16 - 1;
    if ( v13 )
    {
      if ( v17 )
        __fastfail(0xEu);
      v18 = *(void (__fastcall **)(__int64))(a4 + 80);
      if ( v18 )
        v18(a4);
      if ( *(_DWORD *)(a4 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)a4, 0x69706E56u);
      }
      else if ( *(_DWORD *)(a4 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a4 + 96), (PVOID)a4);
      }
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140001828  push    rbx
0x14000182a  push    rbp
0x14000182b  push    rdi
0x14000182c  push    r12
0x14000182e  push    r14
0x140001830  sub     rsp, 60h
0x140001834  mov     rax, cs:__security_cookie
0x14000183b  xor     rax, rsp
0x14000183e  mov     [rsp+88h+var_38], rax
0x140001843  xor     eax, eax
0x140001845  xorps   xmm0, xmm0
0x140001848  mov     [rsp+88h+var_40], rax
0x14000184d  mov     rbx, r9
0x140001850  mov     [rsp+88h+NewElement], al
0x140001854  mov     r14, r8
0x140001857  mov     eax, cs:dword_140013058
0x14000185d  mov     rdi, rdx
0x140001860  mov     rbp, rcx
0x140001863  movups  [rsp+88h+Buffer], xmm0
0x140001868  cmp     eax, 5
0x14000186b  jbe     short loc_140001891
0x14000186d  mov     r9, [r9+8]
0x140001871  lea     rax, aReferenceObjec; "Reference object"
0x140001878  mov     r8, rbx
0x14000187b  mov     [rsp+88h+var_68], rax
0x140001880  mov     edx, 13Fh
0x140001885  lea     rcx, aVmbustlinserto; "VmbusTlInsertObjectToTable"
0x14000188c  call    HvsocketTraceReferenceCount
0x140001891  mov     eax, 1
0x140001896  lock xadd [rbx+8], rax
0x14000189c  inc     rax
0x14000189f  mov     r12d, 0Eh
0x1400018a5  cmp     rax, 1
0x1400018a9  jg      short loc_1400018B0
0x1400018ab  mov     ecx, r12d
0x1400018ae  int     29h; Win8: RtlFailFast(ecx)
0x1400018b0  cmp     [rsp+88h+arg_20], 0
0x1400018b8  jnz     short loc_1400018D6
0x1400018ba  call    cs:__imp_KeEnterCriticalRegion
0x1400018c1  nop     dword ptr [rax+rax+00h]
0x1400018c6  lea     rcx, [rbp+10h]; FastMutex
0x1400018ca  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400018d1  nop     dword ptr [rax+rax+00h]
0x1400018d6  movups  xmm0, xmmword ptr [r14]
0x1400018da  lea     r9, [rsp+88h+NewElement]; NewElement
0x1400018df  mov     [rsp+88h+var_40], rbx
0x1400018e4  mov     r8d, 18h; BufferSize
0x1400018ea  lea     rdx, [rsp+88h+Buffer]; Buffer
0x1400018ef  mov     rcx, rdi; Table
0x1400018f2  movdqu  [rsp+88h+Buffer], xmm0
0x1400018f8  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1400018ff  nop     dword ptr [rax+rax+00h]
0x140001904  lea     rcx, aDereferenceObj; "Dereference object"
0x14000190b  test    rax, rax
0x14000190e  jnz     short loc_14000191A
0x140001910  mov     edi, 0C0000017h
0x140001915  jmp     loc_1400019C2
0x14000191a  cmp     [rsp+88h+NewElement], 0
0x14000191f  jnz     loc_1400019C0
0x140001925  cmp     [rax+10h], rbx
0x140001929  jz      short loc_140001935
0x14000192b  mov     edi, 0C0000035h
0x140001930  jmp     loc_1400019C2
0x140001935  mov     eax, cs:dword_140013058
0x14000193b  cmp     eax, 5
0x14000193e  jbe     short loc_14000195D
0x140001940  mov     r9, [rbx+8]
0x140001944  mov     r8, rbx
0x140001947  mov     [rsp+88h+var_68], rcx
0x14000194c  mov     edx, 15Bh
0x140001951  lea     rcx, aVmbustlinserto; "VmbusTlInsertObjectToTable"
0x140001958  call    HvsocketTraceReferenceCount
0x14000195d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001961  lock xadd [rbx+8], rax
0x140001967  sub     rax, 1
0x14000196b  jg      short loc_1400019C0
0x14000196d  test    rax, rax
0x140001970  jz      short loc_140001979
0x140001972  mov     rcx, r12
0x140001975  int     29h; Win8: RtlFailFast(ecx)
0x140001977  jmp     short loc_1400019C0
0x140001979  mov     rax, [rbx+50h]
0x14000197d  test    rax, rax
0x140001980  jz      short loc_14000198A
0x140001982  mov     rcx, rbx
0x140001985  call    _guard_dispatch_icall
0x14000198a  mov     ecx, [rbx+58h]
0x14000198d  sub     ecx, 1
0x140001990  jz      short loc_1400019AC
0x140001992  cmp     ecx, 1
0x140001995  jnz     short loc_1400019C0
0x140001997  mov     rcx, [rbx+60h]; Lookaside
0x14000199b  mov     rdx, rbx; Entry
0x14000199e  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400019a5  nop     dword ptr [rax+rax+00h]
0x1400019aa  jmp     short loc_1400019C0
0x1400019ac  mov     edx, 69706E56h; Tag
0x1400019b1  mov     rcx, rbx; P
0x1400019b4  call    cs:__imp_ExFreePoolWithTag
0x1400019bb  nop     dword ptr [rax+rax+00h]
0x1400019c0  xor     edi, edi
0x1400019c2  cmp     [rsp+88h+arg_20], 0
0x1400019ca  jnz     short loc_1400019E8
0x1400019cc  lea     rcx, [rbp+10h]; FastMutex
0x1400019d0  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400019d7  nop     dword ptr [rax+rax+00h]
0x1400019dc  call    cs:__imp_KeLeaveCriticalRegion
0x1400019e3  nop     dword ptr [rax+rax+00h]
0x1400019e8  test    edi, edi
0x1400019ea  jns     loc_140001AA4
0x1400019f0  mov     eax, cs:dword_140013058
0x1400019f6  cmp     eax, 2
0x1400019f9  jbe     short loc_140001A12
0x1400019fb  mov     r9, r14
0x1400019fe  lea     rcx, aVmbustlinserto; "VmbusTlInsertObjectToTable"
0x140001a05  mov     r8d, edi
0x140001a08  mov     edx, 16Bh
0x140001a0d  call    HvsocketTraceGuidError
0x140001a12  mov     eax, cs:dword_140013058
0x140001a18  cmp     eax, 5
0x140001a1b  jbe     short loc_140001A41
0x140001a1d  mov     r9, [rbx+8]
0x140001a21  lea     rax, aDereferenceObj; "Dereference object"
0x140001a28  mov     r8, rbx
0x140001a2b  mov     [rsp+88h+var_68], rax
0x140001a30  mov     edx, 16Ch
0x140001a35  lea     rcx, aVmbustlinserto; "VmbusTlInsertObjectToTable"
0x140001a3c  call    HvsocketTraceReferenceCount
0x140001a41  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001a45  lock xadd [rbx+8], rax
0x140001a4b  sub     rax, 1
0x140001a4f  jg      short loc_140001AA4
0x140001a51  test    rax, rax
0x140001a54  jz      short loc_140001A5D
0x140001a56  mov     rcx, r12
0x140001a59  int     29h; Win8: RtlFailFast(ecx)
0x140001a5b  jmp     short loc_140001AA4
0x140001a5d  mov     rax, [rbx+50h]
0x140001a61  test    rax, rax
0x140001a64  jz      short loc_140001A6E
0x140001a66  mov     rcx, rbx
0x140001a69  call    _guard_dispatch_icall
0x140001a6e  mov     ecx, [rbx+58h]
0x140001a71  sub     ecx, 1
0x140001a74  jz      short loc_140001A90
0x140001a76  cmp     ecx, 1
0x140001a79  jnz     short loc_140001AA4
0x140001a7b  mov     rcx, [rbx+60h]; Lookaside
0x140001a7f  mov     rdx, rbx; Entry
0x140001a82  call    cs:__imp_ExFreeToNPagedLookasideList
0x140001a89  nop     dword ptr [rax+rax+00h]
0x140001a8e  jmp     short loc_140001AA4
0x140001a90  mov     edx, 69706E56h; Tag
0x140001a95  mov     rcx, rbx; P
0x140001a98  call    cs:__imp_ExFreePoolWithTag
0x140001a9f  nop     dword ptr [rax+rax+00h]
0x140001aa4  mov     eax, edi
0x140001aa6  mov     rcx, [rsp+88h+var_38]
0x140001aab  xor     rcx, rsp; StackCookie
0x140001aae  call    __security_check_cookie
0x140001ab3  add     rsp, 60h
0x140001ab7  pop     r14
0x140001ab9  pop     r12
0x140001abb  pop     rdi
0x140001abc  pop     rbp
0x140001abd  pop     rbx
0x140001abe  retn
```
