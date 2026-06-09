# VmbusTlUpdateWildcardDescriptorList

- ea: `0x140026868`
- end: `0x140026c20`
- name: `VmbusTlUpdateWildcardDescriptorList`
- size: `952`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14001b140`

## callees

- `0x140009cf8`
- `0x140009df0`
- `0x140009fa4`
- `0x14000a048`
- `0x14000bdd4`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x140026734`
- `0x140026868`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026bcf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026bcf`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140026954`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140026954`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026bc3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026bc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026b49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026b8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026b49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026b8f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400269b9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400269b9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140026a8c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140026b30`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140026a8c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140026b30`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400269c9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400269c9`

## string_xrefs

- `0x140026bf1`: `Invalid wildcard descriptor list size.`
- `0x140026a2e`: `VmbusTlUpdateWildcardDescriptorList`
- `0x140026aab`: `VmbusTlUpdateWildcardDescriptorList`
- `0x140026ae2`: `VmbusTlUpdateWildcardDescriptorList`
- `0x140026b71`: `VmbusTlUpdateWildcardDescriptorList`
- `0x140026c00`: `VmbusTlUpdateWildcardDescriptorList`
- `0x1400269a1`: `Invalid service ID found.`

## pseudocode

```c
__int64 __fastcall VmbusTlUpdateWildcardDescriptorList(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned __int64 v5; // r14
  __int64 v6; // r15
  __int64 v7; // rdx
  int v8; // edi
  __int64 v9; // r9
  char *v10; // rbx
  __int64 *v11; // rcx
  PNPAGED_LOOKASIDE_LIST **v12; // rdi
  PNPAGED_LOOKASIDE_LIST *v13; // rsi
  PNPAGED_LOOKASIDE_LIST *v14; // rbx
  PNPAGED_LOOKASIDE_LIST v15; // rcx
  PNPAGED_LOOKASIDE_LIST **v16; // rdx
  signed __int64 v17; // rax
  bool v18; // cc
  signed __int64 v19; // rax
  void (__fastcall *v20)(PNPAGED_LOOKASIDE_LIST *); // rax
  signed __int64 v21; // rax
  signed __int64 v22; // rax
  void (__fastcall *v23)(char *); // rax
  __int64 i; // [rsp+30h] [rbp-18h] BYREF
  __int64 *v26; // [rsp+38h] [rbp-10h]
  PVOID Entry; // [rsp+98h] [rbp+50h] BYREF

  Entry = 0;
  if ( a2 && a3 && (v5 = a3 / 0x18uLL, a3 == 24 * v5) )
  {
    v6 = 0;
    v26 = &i;
    for ( i = (__int64)&i; (unsigned int)v6 < (unsigned int)v5; v6 = (unsigned int)(v6 + 1) )
    {
      if ( !memcmp((const void *)(a2 + 24 * v6), &HV_GUID_BROADCAST, 0x10u)
        || !memcmp((const void *)(a2 + 24 * v6), &HV_GUID_ZERO, 0x10u) )
      {
        if ( (unsigned int)dword_140013058 > 4 )
          HvsocketTraceMessage("Invalid service ID found.", a2 + 24 * v6);
      }
      else
      {
        v8 = VmbusTlCreateWildcardDescriptor(a2 + 24 * v6, &Entry);
        if ( v8 < 0 )
        {
          if ( (unsigned int)dword_140013058 > 2 )
            HvsocketTraceGuidError("VmbusTlUpdateWildcardDescriptorList", 171, (unsigned int)v8, a2 + 24 * v6);
          return (unsigned int)v8;
        }
        v10 = (char *)Entry;
        LOBYTE(v9) = 1;
        LOBYTE(v7) = 1;
        v8 = SeCaptureSecurityDescriptor(*(_QWORD *)(a2 + 24 * v6 + 16), v7, 1, v9, (char *)Entry + 128);
        if ( v8 < 0 )
        {
          if ( (unsigned int)dword_140013058 > 2 )
            HvsocketTraceGuidError("VmbusTlUpdateWildcardDescriptorList", 185, (unsigned int)v8, a2 + 24 * v6);
          if ( (unsigned int)dword_140013058 > 5 )
            HvsocketTraceReferenceCount(
              (unsigned int)"VmbusTlUpdateWildcardDescriptorList",
              190,
              (_DWORD)v10,
              *((_QWORD *)v10 + 1),
              (__int64)"Dereference object");
          v21 = _InterlockedExchangeAdd64((volatile signed __int64 *)v10 + 1, 0xFFFFFFFFFFFFFFFFuLL);
          v18 = v21 <= 1;
          v22 = v21 - 1;
          if ( v18 )
          {
            if ( v22 )
              __fastfail(0xEu);
            v23 = (void (__fastcall *)(char *))*((_QWORD *)v10 + 10);
            if ( v23 )
              v23(v10);
            if ( *((_DWORD *)v10 + 22) == 1 )
            {
              ExFreePoolWithTag(v10, 0x69706E56u);
            }
            else if ( *((_DWORD *)v10 + 22) == 2 )
            {
              ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v10 + 12), v10);
            }
          }
          return (unsigned int)v8;
        }
        v11 = v26;
        if ( (__int64 *)*v26 != &i )
LABEL_44:
          __fastfail(3u);
        *((_QWORD *)v10 + 13) = v26;
        *((_QWORD *)v10 + 12) = &i;
        *v11 = (__int64)(v10 + 96);
        v26 = (__int64 *)(v10 + 96);
      }
    }
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    v12 = (PNPAGED_LOOKASIDE_LIST **)(a1 + 1416);
    while ( 1 )
    {
      v13 = *v12;
      if ( *v12 == (PNPAGED_LOOKASIDE_LIST *)v12 )
        break;
      v14 = v13 - 12;
      v15 = *v13;
      if ( (PNPAGED_LOOKASIDE_LIST *)(*v13)->L.ListHead.Region != v13 )
        goto LABEL_44;
      v16 = (PNPAGED_LOOKASIDE_LIST **)v13[1];
      if ( *v16 != v13 )
        goto LABEL_44;
      *v16 = (PNPAGED_LOOKASIDE_LIST *)v15;
      v15->L.ListHead.Region = (ULONGLONG)v16;
      v13[1] = (PNPAGED_LOOKASIDE_LIST)v13;
      *v13 = (PNPAGED_LOOKASIDE_LIST)v13;
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlUpdateWildcardDescriptorList",
          214,
          (_DWORD)v13 - 96,
          (unsigned int)v14[1],
          (__int64)"Dereference object");
      v17 = _InterlockedExchangeAdd64((volatile signed __int64 *)v14 + 1, 0xFFFFFFFFFFFFFFFFuLL);
      v18 = v17 <= 1;
      v19 = v17 - 1;
      if ( v18 )
      {
        if ( v19 )
          __fastfail(0xEu);
        v20 = (void (__fastcall *)(PNPAGED_LOOKASIDE_LIST *))v14[10];
        if ( v20 )
          v20(v13 - 12);
        if ( *((_DWORD *)v14 + 22) == 1 )
        {
          ExFreePoolWithTag(v13 - 12, 0x69706E56u);
        }
        else if ( *((_DWORD *)v14 + 22) == 2 )
        {
          ExFreeToNPagedLookasideList(*v13, v13 - 12);
        }
      }
    }
    DvAppendList(a1 + 1416, &i);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    KeLeaveCriticalRegion();
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceError(
        "VmbusTlUpdateWildcardDescriptorList",
        141,
        3221225485LL,
        "Invalid wildcard descriptor list size.");
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140026868  push    rbp
0x14002686a  push    rbx
0x14002686b  push    rsi
0x14002686c  push    rdi
0x14002686d  push    r12
0x14002686f  push    r13
0x140026871  push    r14
0x140026873  push    r15
0x140026875  mov     rbp, rsp
0x140026878  sub     rsp, 48h
0x14002687c  mov     [rbp+Entry], 0
0x140026884  mov     r12, rdx
0x140026887  mov     r13, rcx
0x14002688a  test    rdx, rdx
0x14002688d  jz      loc_140026BE1
0x140026893  test    r8d, r8d
0x140026896  jz      loc_140026BE1
0x14002689c  mov     r8d, r8d
0x14002689f  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400268a9  mul     r8
0x1400268ac  mov     r14, rdx
0x1400268af  shr     r14, 4
0x1400268b3  lea     rax, [r14+r14*2]
0x1400268b7  shl     rax, 3
0x1400268bb  cmp     r8, rax
0x1400268be  jnz     loc_140026BE1
0x1400268c4  lea     rax, [rbp+var_18]
0x1400268c8  xor     r15d, r15d
0x1400268cb  mov     [rbp+var_10], rax
0x1400268cf  lea     rax, [rbp+var_18]
0x1400268d3  mov     [rbp+var_18], rax
0x1400268d7  test    r14d, r14d
0x1400268da  jz      loc_1400269B9
0x1400268e0  lea     rcx, [r15+r15*2]
0x1400268e4  mov     r8d, 10h; Size
0x1400268ea  lea     rsi, [r12+rcx*8]
0x1400268ee  mov     rcx, rsi; Buf1
0x1400268f1  lea     rdx, HV_GUID_BROADCAST; Buf2
0x1400268f8  call    memcmp
0x1400268fd  test    eax, eax
0x1400268ff  jz      loc_140026993
0x140026905  mov     r8d, 10h; Size
0x14002690b  lea     rdx, HV_GUID_ZERO; Buf2
0x140026912  mov     rcx, rsi; Buf1
0x140026915  call    memcmp
0x14002691a  test    eax, eax
0x14002691c  jz      short loc_140026993
0x14002691e  lea     rdx, [rbp+Entry]
0x140026922  mov     rcx, rsi
0x140026925  call    VmbusTlCreateWildcardDescriptor
0x14002692a  mov     edi, eax
0x14002692c  test    eax, eax
0x14002692e  js      loc_140026B63
0x140026934  mov     rbx, [rbp+Entry]
0x140026938  mov     r8d, 1
0x14002693e  mov     rcx, [rsi+10h]
0x140026942  mov     r9b, 1
0x140026945  mov     dl, r8b
0x140026948  lea     rax, [rbx+80h]
0x14002694f  mov     [rsp+48h+var_28], rax
0x140026954  call    cs:__imp_SeCaptureSecurityDescriptor
0x14002695b  nop     dword ptr [rax+rax+00h]
0x140026960  mov     edi, eax
0x140026962  test    eax, eax
0x140026964  js      loc_140026A9D
0x14002696a  mov     rcx, [rbp+var_10]
0x14002696e  lea     rax, [rbp+var_18]
0x140026972  cmp     [rcx], rax
0x140026975  jnz     loc_140026BAC
0x14002697b  lea     rax, [rbx+60h]
0x14002697f  mov     [rax+8], rcx
0x140026983  lea     rdx, [rbp+var_18]
0x140026987  mov     [rax], rdx
0x14002698a  mov     [rcx], rax
0x14002698d  mov     [rbp+var_10], rax
0x140026991  jmp     short loc_1400269AD
0x140026993  mov     eax, cs:dword_140013058
0x140026999  cmp     eax, 4
0x14002699c  jbe     short loc_1400269AD
0x14002699e  mov     rdx, rsi
0x1400269a1  lea     rcx, aInvalidService; "Invalid service ID found."
0x1400269a8  call    HvsocketTraceMessage
0x1400269ad  inc     r15d
0x1400269b0  cmp     r15d, r14d
0x1400269b3  jb      loc_1400268E0
0x1400269b9  call    cs:__imp_KeEnterCriticalRegion
0x1400269c0  nop     dword ptr [rax+rax+00h]
0x1400269c5  lea     rcx, [r13+10h]; FastMutex
0x1400269c9  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400269d0  nop     dword ptr [rax+rax+00h]
0x1400269d5  lea     rdi, [r13+588h]
0x1400269dc  lea     r15, aDereferenceObj; "Dereference object"
0x1400269e3  mov     rsi, [rdi]
0x1400269e6  cmp     rsi, rdi
0x1400269e9  jz      loc_140026BB3
0x1400269ef  lea     rbx, [rsi-60h]
0x1400269f3  lea     rax, [rbx+60h]
0x1400269f7  mov     rcx, [rax]
0x1400269fa  cmp     [rcx+8], rax
0x1400269fe  jnz     loc_140026BAC
0x140026a04  mov     rdx, [rax+8]
0x140026a08  cmp     [rdx], rax
0x140026a0b  jnz     loc_140026BAC
0x140026a11  mov     [rdx], rcx
0x140026a14  mov     [rcx+8], rdx
0x140026a18  mov     [rax+8], rax
0x140026a1c  mov     [rax], rax
0x140026a1f  mov     eax, cs:dword_140013058
0x140026a25  cmp     eax, 5
0x140026a28  jbe     short loc_140026A47
0x140026a2a  mov     r9, [rbx+8]
0x140026a2e  lea     rcx, aVmbustlupdatew; "VmbusTlUpdateWildcardDescriptorList"
0x140026a35  mov     r8, rbx
0x140026a38  mov     [rsp+48h+var_28], r15
0x140026a3d  mov     edx, 0D6h
0x140026a42  call    HvsocketTraceReferenceCount
0x140026a47  or      rax, 0FFFFFFFFFFFFFFFFh
0x140026a4b  lock xadd [rbx+8], rax
0x140026a51  sub     rax, 1
0x140026a55  jg      short loc_1400269E3
0x140026a57  test    rax, rax
0x140026a5a  jnz     loc_140026BA0
0x140026a60  mov     rax, [rbx+50h]
0x140026a64  test    rax, rax
0x140026a67  jz      short loc_140026A71
0x140026a69  mov     rcx, rbx
0x140026a6c  call    _guard_dispatch_icall
0x140026a71  mov     edx, [rbx+58h]
0x140026a74  sub     edx, 1
0x140026a77  jz      loc_140026B87
0x140026a7d  cmp     edx, 1
0x140026a80  jnz     loc_1400269E3
0x140026a86  mov     rcx, [rsi]; Lookaside
0x140026a89  mov     rdx, rbx; Entry
0x140026a8c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140026a93  nop     dword ptr [rax+rax+00h]
0x140026a98  jmp     loc_1400269E3
0x140026a9d  mov     eax, cs:dword_140013058
0x140026aa3  cmp     eax, 2
0x140026aa6  jbe     short loc_140026ABF
0x140026aa8  mov     r9, rsi
0x140026aab  lea     rcx, aVmbustlupdatew; "VmbusTlUpdateWildcardDescriptorList"
0x140026ab2  mov     r8d, edi
0x140026ab5  mov     edx, 0B9h
0x140026aba  call    HvsocketTraceGuidError
0x140026abf  mov     eax, cs:dword_140013058
0x140026ac5  cmp     eax, 5
0x140026ac8  jbe     short loc_140026AEE
0x140026aca  mov     r9, [rbx+8]
0x140026ace  lea     r15, aDereferenceObj; "Dereference object"
0x140026ad5  mov     r8, rbx
0x140026ad8  mov     [rsp+48h+var_28], r15
0x140026add  mov     edx, 0BEh
0x140026ae2  lea     rcx, aVmbustlupdatew; "VmbusTlUpdateWildcardDescriptorList"
0x140026ae9  call    HvsocketTraceReferenceCount
0x140026aee  or      rax, 0FFFFFFFFFFFFFFFFh
0x140026af2  lock xadd [rbx+8], rax
0x140026af8  sub     rax, 1
0x140026afc  jg      loc_140026BDD
0x140026b02  test    rax, rax
0x140026b05  jnz     short loc_140026B5A
0x140026b07  mov     rax, [rbx+50h]
0x140026b0b  test    rax, rax
0x140026b0e  jz      short loc_140026B18
0x140026b10  mov     rcx, rbx
0x140026b13  call    _guard_dispatch_icall
0x140026b18  mov     ecx, [rbx+58h]
0x140026b1b  sub     ecx, 1
0x140026b1e  jz      short loc_140026B41
0x140026b20  cmp     ecx, 1
0x140026b23  jnz     loc_140026BDD
0x140026b29  mov     rcx, [rbx+60h]; Lookaside
0x140026b2d  mov     rdx, rbx; Entry
0x140026b30  call    cs:__imp_ExFreeToNPagedLookasideList
0x140026b37  nop     dword ptr [rax+rax+00h]
0x140026b3c  jmp     loc_140026BDD
0x140026b41  mov     edx, 69706E56h; Tag
0x140026b46  mov     rcx, rbx; P
0x140026b49  call    cs:__imp_ExFreePoolWithTag
0x140026b50  nop     dword ptr [rax+rax+00h]
0x140026b55  jmp     loc_140026BDD
0x140026b5a  mov     ecx, 0Eh
0x140026b5f  int     29h; Win8: RtlFailFast(ecx)
0x140026b61  jmp     short loc_140026BDD
0x140026b63  mov     eax, cs:dword_140013058
0x140026b69  cmp     eax, 2
0x140026b6c  jbe     short loc_140026BDD
0x140026b6e  mov     r9, rsi
0x140026b71  lea     rcx, aVmbustlupdatew; "VmbusTlUpdateWildcardDescriptorList"
0x140026b78  mov     r8d, edi
0x140026b7b  mov     edx, 0ABh
0x140026b80  call    HvsocketTraceGuidError
0x140026b85  jmp     short loc_140026BDD
0x140026b87  mov     edx, 69706E56h; Tag
0x140026b8c  mov     rcx, rbx; P
0x140026b8f  call    cs:__imp_ExFreePoolWithTag
0x140026b96  nop     dword ptr [rax+rax+00h]
0x140026b9b  jmp     loc_1400269E3
0x140026ba0  mov     ecx, 0Eh
0x140026ba5  int     29h; Win8: RtlFailFast(ecx)
0x140026ba7  jmp     loc_1400269E3
0x140026bac  mov     ecx, 3
0x140026bb1  int     29h; Win8: RtlFailFast(ecx)
0x140026bb3  lea     rdx, [rbp+var_18]
0x140026bb7  mov     rcx, rdi
0x140026bba  call    DvAppendList
0x140026bbf  lea     rcx, [r13+10h]; FastMutex
0x140026bc3  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140026bca  nop     dword ptr [rax+rax+00h]
0x140026bcf  call    cs:__imp_KeLeaveCriticalRegion
0x140026bd6  nop     dword ptr [rax+rax+00h]
0x140026bdb  xor     edi, edi
0x140026bdd  mov     eax, edi
0x140026bdf  jmp     short loc_140026C0E
0x140026be1  mov     ecx, cs:dword_140013058
0x140026be7  mov     ebx, 0C000000Dh
0x140026bec  cmp     ecx, 2
0x140026bef  jbe     short loc_140026C0C
0x140026bf1  lea     r9, aInvalidWildcar; "Invalid wildcard descriptor list size."
0x140026bf8  mov     r8d, ebx
0x140026bfb  mov     edx, 8Dh
0x140026c00  lea     rcx, aVmbustlupdatew; "VmbusTlUpdateWildcardDescriptorList"
0x140026c07  call    HvsocketTraceError
0x140026c0c  mov     eax, ebx
0x140026c0e  add     rsp, 48h
0x140026c12  pop     r15
0x140026c14  pop     r14
0x140026c16  pop     r13
0x140026c18  pop     r12
0x140026c1a  pop     rdi
0x140026c1b  pop     rsi
0x140026c1c  pop     rbx
0x140026c1d  pop     rbp
0x140026c1e  retn
```
