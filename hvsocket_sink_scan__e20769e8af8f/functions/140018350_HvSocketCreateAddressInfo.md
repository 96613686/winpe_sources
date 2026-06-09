# HvSocketCreateAddressInfo

- ea: `0x140018350`
- end: `0x1400186ef`
- name: `HvSocketCreateAddressInfo`
- size: `927`
- prototype: `__int64 __fastcall(__int64, _OWORD *, char, _QWORD *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation`

## callees

- `0x140001350`
- `0x140001608`
- `0x140001828`
- `0x140009df0`
- `0x140009fa4`
- `0x14000a048`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x140018350`
- `0x1400188c4`
- `0x14001d304`
- `0x14001df1c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400185b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400185d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400185b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400185d0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400185a7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400185c4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400185a7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400185c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001868f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001868f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018540`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018540`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018679`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018679`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018553`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018553`

## string_xrefs

- `0x1400184d2`: `HvSocketCreateAddressInfo`
- `0x140018590`: `HvSocketCreateAddressInfo`
- `0x140018626`: `HvSocketCreateAddressInfo`
- `0x1400186b8`: `HvSocketCreateAddressInfo`
- `0x1400185ee`: `Created address info.`

## pseudocode

```c
__int64 __fastcall HvSocketCreateAddressInfo(__int64 a1, _OWORD *a2, char a3, _QWORD *a4)
{
  void *v8; // rax
  int v9; // eax
  char *v10; // rbx
  int inserted; // esi
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  signed __int64 v15; // rax
  bool v16; // cc
  signed __int64 v17; // rax
  void (__fastcall *v18)(char *); // rax
  PVOID Entry; // [rsp+30h] [rbp-88h] BYREF
  _OWORD v21[3]; // [rsp+38h] [rbp-80h] BYREF
  int v22; // [rsp+68h] [rbp-50h]

  if ( !memcmp(a2, &HV_GUID_ZERO, 0x10u)
    || !memcmp(a2, &HV_GUID_BROADCAST, 0x10u)
    || !memcmp(a2, &HV_GUID_CHILDREN, 0x10u)
    || !memcmp(a2, &HV_GUID_LOOPBACK, 0x10u)
    || !memcmp(a2, &HV_GUID_SILOHOST, 0x10u)
    || !memcmp(a2, &HV_GUID_PARENT, 0x10u) )
  {
    inserted = -1073741811;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceGuidError("HvSocketCreateAddressInfo", 72, 3221225485LL, a2);
    return (unsigned int)inserted;
  }
  v8 = (void *)VmbusTlFindAndReferenceObjectInTable(a1, a1 + 1312, a2, 0);
  Entry = v8;
  if ( v8
    || a3
    && ((v22 = 0, memset(v21, 0, sizeof(v21)), (int)HvSocketGetVmAddressInfo(a1, a2, v21) < 0)
      ? (v8 = 0)
      : (v8 = (void *)VmbusTlFindAndReferenceObjectInTable(a1, a1 + 1312, v21, 0)),
        (Entry = v8) != 0) )
  {
    *a4 = v8;
    return 0;
  }
  v9 = VmbusTlCreateObject(10, 160, &Entry);
  v10 = (char *)Entry;
  inserted = v9;
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_29;
    v12 = (unsigned int)v9;
    v13 = 108;
    goto LABEL_16;
  }
  *((_QWORD *)Entry + 10) = HvSocketAddressInfoDestructor;
  *((_QWORD *)v10 + 12) = a1;
  *(_OWORD *)(v10 + 104) = *a2;
  *(_OWORD *)(v10 + 120) = *a2;
  inserted = VmbusTlInsertObjectToTable(a1, a1 + 1312, a2, v10, 0);
  if ( inserted >= 0 )
  {
    if ( a3 )
    {
      KeEnterCriticalRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
      if ( !(unsigned __int8)HvSocketPartitionExists(a1, a2) )
      {
        LOBYTE(v14) = a3;
        inserted = HvSocketCreateUninitializedPartition(a1, a2, v14);
        if ( inserted < 0 )
        {
          if ( (unsigned int)dword_140013058 > 2 )
            HvsocketTraceGuidError("HvSocketCreateAddressInfo", 147, (unsigned int)inserted, a2);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
          KeLeaveCriticalRegion();
          goto LABEL_29;
        }
      }
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
      KeLeaveCriticalRegion();
    }
    *a4 = v10;
    if ( (unsigned int)dword_140013058 > 4 )
      HvsocketTraceMessage("Created address info.", a2);
    goto LABEL_29;
  }
  if ( (unsigned int)dword_140013058 > 2 )
  {
    v12 = (unsigned int)inserted;
    v13 = 131;
LABEL_16:
    HvsocketTraceGuidError("HvSocketCreateAddressInfo", v13, v12, a2);
  }
LABEL_29:
  if ( v10 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketCreateAddressInfo",
        167,
        (_DWORD)v10,
        *((_QWORD *)v10 + 1),
        (__int64)"Dereference object");
    v15 = _InterlockedExchangeAdd64((volatile signed __int64 *)v10 + 1, 0xFFFFFFFFFFFFFFFFuLL);
    v16 = v15 <= 1;
    v17 = v15 - 1;
    if ( v16 )
    {
      if ( v17 )
        __fastfail(0xEu);
      v18 = (void (__fastcall *)(char *))*((_QWORD *)v10 + 10);
      if ( v18 )
        v18(v10);
      if ( *((_DWORD *)v10 + 22) == 1 )
      {
        ExFreePoolWithTag(v10, 0x69706E56u);
      }
      else if ( *((_DWORD *)v10 + 22) == 2 )
      {
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v10 + 12), v10);
      }
    }
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x140018350  push    rbx
0x140018352  push    rsi
0x140018353  push    rdi
0x140018354  push    r12
0x140018356  push    r13
0x140018358  push    r14
0x14001835a  push    r15
0x14001835c  sub     rsp, 80h
0x140018363  mov     rax, cs:__security_cookie
0x14001836a  xor     rax, rsp
0x14001836d  mov     [rsp+0B8h+var_48], rax
0x140018372  mov     rdi, rdx
0x140018375  mov     r12b, r8b
0x140018378  mov     r14, rcx
0x14001837b  lea     rdx, HV_GUID_ZERO; Buf2
0x140018382  mov     ebx, 10h
0x140018387  mov     rcx, rdi; Buf1
0x14001838a  mov     r8d, ebx; Size
0x14001838d  mov     r13, r9
0x140018390  call    memcmp
0x140018395  test    eax, eax
0x140018397  jz      loc_1400186A5
0x14001839d  mov     r8d, ebx; Size
0x1400183a0  lea     rdx, HV_GUID_BROADCAST; Buf2
0x1400183a7  mov     rcx, rdi; Buf1
0x1400183aa  call    memcmp
0x1400183af  test    eax, eax
0x1400183b1  jz      loc_1400186A5
0x1400183b7  mov     r8d, ebx; Size
0x1400183ba  lea     rdx, HV_GUID_CHILDREN; Buf2
0x1400183c1  mov     rcx, rdi; Buf1
0x1400183c4  call    memcmp
0x1400183c9  test    eax, eax
0x1400183cb  jz      loc_1400186A5
0x1400183d1  mov     r8d, ebx; Size
0x1400183d4  lea     rdx, HV_GUID_LOOPBACK; Buf2
0x1400183db  mov     rcx, rdi; Buf1
0x1400183de  call    memcmp
0x1400183e3  test    eax, eax
0x1400183e5  jz      loc_1400186A5
0x1400183eb  mov     r8d, ebx; Size
0x1400183ee  lea     rdx, HV_GUID_SILOHOST; Buf2
0x1400183f5  mov     rcx, rdi; Buf1
0x1400183f8  call    memcmp
0x1400183fd  test    eax, eax
0x1400183ff  jz      loc_1400186A5
0x140018405  mov     r8d, ebx; Size
0x140018408  lea     rdx, HV_GUID_PARENT; Buf2
0x14001840f  mov     rcx, rdi; Buf1
0x140018412  call    memcmp
0x140018417  test    eax, eax
0x140018419  jz      loc_1400186A5
0x14001841f  lea     r15, [r14+520h]
0x140018426  xor     r9d, r9d
0x140018429  mov     rdx, r15
0x14001842c  mov     r8, rdi
0x14001842f  mov     rcx, r14
0x140018432  call    VmbusTlFindAndReferenceObjectInTable
0x140018437  mov     [rsp+0B8h+Entry], rax
0x14001843c  test    rax, rax
0x14001843f  jnz     loc_14001869D
0x140018445  test    r12b, r12b
0x140018448  jz      short loc_140018499
0x14001844a  xorps   xmm0, xmm0
0x14001844d  mov     [rsp+0B8h+var_50], eax
0x140018451  lea     r8, [rsp+0B8h+var_80]
0x140018456  mov     rdx, rdi
0x140018459  mov     rcx, r14
0x14001845c  movups  [rsp+0B8h+var_80], xmm0
0x140018461  movups  [rsp+0B8h+var_70], xmm0
0x140018466  movups  [rsp+0B8h+var_60], xmm0
0x14001846b  call    HvSocketGetVmAddressInfo
0x140018470  test    eax, eax
0x140018472  js      short loc_140018489
0x140018474  xor     r9d, r9d
0x140018477  lea     r8, [rsp+0B8h+var_80]
0x14001847c  mov     rdx, r15
0x14001847f  mov     rcx, r14
0x140018482  call    VmbusTlFindAndReferenceObjectInTable
0x140018487  jmp     short loc_14001848B
0x140018489  xor     eax, eax
0x14001848b  mov     [rsp+0B8h+Entry], rax
0x140018490  test    rax, rax
0x140018493  jnz     loc_14001869D
0x140018499  lea     r8, [rsp+0B8h+Entry]
0x14001849e  mov     edx, 0A0h
0x1400184a3  mov     ecx, 0Ah
0x1400184a8  call    VmbusTlCreateObject
0x1400184ad  mov     rbx, [rsp+0B8h+Entry]
0x1400184b2  mov     esi, eax
0x1400184b4  test    eax, eax
0x1400184b6  jns     short loc_1400184E3
0x1400184b8  mov     ecx, cs:dword_140013058
0x1400184be  cmp     ecx, 2
0x1400184c1  jbe     loc_1400185FA
0x1400184c7  mov     r8d, eax
0x1400184ca  mov     edx, 6Ch ; 'l'
0x1400184cf  mov     r9, rdi
0x1400184d2  lea     rcx, aHvsocketcreate_0; "HvSocketCreateAddressInfo"
0x1400184d9  call    HvsocketTraceGuidError
0x1400184de  jmp     loc_1400185FA
0x1400184e3  lea     rax, HvSocketAddressInfoDestructor
0x1400184ea  mov     byte ptr [rsp+0B8h+var_98], 0
0x1400184ef  mov     [rbx+50h], rax
0x1400184f3  mov     r9, rbx
0x1400184f6  mov     [rbx+60h], r14
0x1400184fa  mov     r8, rdi
0x1400184fd  movups  xmm0, xmmword ptr [rdi]
0x140018500  mov     rdx, r15
0x140018503  mov     rcx, r14
0x140018506  movdqu  xmmword ptr [rbx+68h], xmm0
0x14001850b  movups  xmm1, xmmword ptr [rdi]
0x14001850e  movdqu  xmmword ptr [rbx+78h], xmm1
0x140018513  call    VmbusTlInsertObjectToTable
0x140018518  mov     esi, eax
0x14001851a  test    eax, eax
0x14001851c  jns     short loc_140018537
0x14001851e  mov     eax, cs:dword_140013058
0x140018524  cmp     eax, 2
0x140018527  jbe     loc_1400185FA
0x14001852d  mov     r8d, esi
0x140018530  mov     edx, 83h
0x140018535  jmp     short loc_1400184CF
0x140018537  test    r12b, r12b
0x14001853a  jz      loc_1400185DC
0x140018540  call    cs:__imp_KeEnterCriticalRegion
0x140018547  nop     dword ptr [rax+rax+00h]
0x14001854c  lea     r15, [r14+10h]
0x140018550  mov     rcx, r15; FastMutex
0x140018553  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001855a  nop     dword ptr [rax+rax+00h]
0x14001855f  mov     rdx, rdi
0x140018562  mov     rcx, r14
0x140018565  call    HvSocketPartitionExists
0x14001856a  test    al, al
0x14001856c  jnz     short loc_1400185C1
0x14001856e  mov     r8b, r12b
0x140018571  mov     rdx, rdi
0x140018574  mov     rcx, r14
0x140018577  call    HvSocketCreateUninitializedPartition
0x14001857c  mov     esi, eax
0x14001857e  test    eax, eax
0x140018580  jns     short loc_1400185C1
0x140018582  mov     eax, cs:dword_140013058
0x140018588  cmp     eax, 2
0x14001858b  jbe     short loc_1400185A4
0x14001858d  mov     r9, rdi
0x140018590  lea     rcx, aHvsocketcreate_0; "HvSocketCreateAddressInfo"
0x140018597  mov     r8d, esi
0x14001859a  mov     edx, 93h
0x14001859f  call    HvsocketTraceGuidError
0x1400185a4  mov     rcx, r15; FastMutex
0x1400185a7  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400185ae  nop     dword ptr [rax+rax+00h]
0x1400185b3  call    cs:__imp_KeLeaveCriticalRegion
0x1400185ba  nop     dword ptr [rax+rax+00h]
0x1400185bf  jmp     short loc_1400185FA
0x1400185c1  mov     rcx, r15; FastMutex
0x1400185c4  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400185cb  nop     dword ptr [rax+rax+00h]
0x1400185d0  call    cs:__imp_KeLeaveCriticalRegion
0x1400185d7  nop     dword ptr [rax+rax+00h]
0x1400185dc  mov     [r13+0], rbx
0x1400185e0  mov     eax, cs:dword_140013058
0x1400185e6  cmp     eax, 4
0x1400185e9  jbe     short loc_1400185FA
0x1400185eb  mov     rdx, rdi
0x1400185ee  lea     rcx, aCreatedAddress; "Created address info."
0x1400185f5  call    HvsocketTraceMessage
0x1400185fa  test    rbx, rbx
0x1400185fd  jz      loc_1400186CC
0x140018603  mov     eax, cs:dword_140013058
0x140018609  cmp     eax, 5
0x14001860c  jbe     short loc_140018632
0x14001860e  mov     r9, [rbx+8]
0x140018612  lea     rax, aDereferenceObj; "Dereference object"
0x140018619  mov     r8, rbx
0x14001861c  mov     [rsp+0B8h+var_98], rax
0x140018621  mov     edx, 0A7h
0x140018626  lea     rcx, aHvsocketcreate_0; "HvSocketCreateAddressInfo"
0x14001862d  call    HvsocketTraceReferenceCount
0x140018632  or      rax, 0FFFFFFFFFFFFFFFFh
0x140018636  lock xadd [rbx+8], rax
0x14001863c  sub     rax, 1
0x140018640  jg      loc_1400186CC
0x140018646  test    rax, rax
0x140018649  jz      short loc_140018654
0x14001864b  mov     ecx, 0Eh
0x140018650  int     29h; Win8: RtlFailFast(ecx)
0x140018652  jmp     short loc_1400186CC
0x140018654  mov     rax, [rbx+50h]
0x140018658  test    rax, rax
0x14001865b  jz      short loc_140018665
0x14001865d  mov     rcx, rbx
0x140018660  call    _guard_dispatch_icall
0x140018665  mov     ecx, [rbx+58h]
0x140018668  sub     ecx, 1
0x14001866b  jz      short loc_140018687
0x14001866d  cmp     ecx, 1
0x140018670  jnz     short loc_1400186CC
0x140018672  mov     rcx, [rbx+60h]; Lookaside
0x140018676  mov     rdx, rbx; Entry
0x140018679  call    cs:__imp_ExFreeToNPagedLookasideList
0x140018680  nop     dword ptr [rax+rax+00h]
0x140018685  jmp     short loc_1400186CC
0x140018687  mov     edx, 69706E56h; Tag
0x14001868c  mov     rcx, rbx; P
0x14001868f  call    cs:__imp_ExFreePoolWithTag
0x140018696  nop     dword ptr [rax+rax+00h]
0x14001869b  jmp     short loc_1400186CC
0x14001869d  mov     [r13+0], rax
0x1400186a1  xor     eax, eax
0x1400186a3  jmp     short loc_1400186CE
0x1400186a5  mov     eax, cs:dword_140013058
0x1400186ab  mov     esi, 0C000000Dh
0x1400186b0  cmp     eax, 2
0x1400186b3  jbe     short loc_1400186CC
0x1400186b5  mov     r9, rdi
0x1400186b8  lea     rcx, aHvsocketcreate_0; "HvSocketCreateAddressInfo"
0x1400186bf  mov     r8d, esi
0x1400186c2  mov     edx, 48h ; 'H'
0x1400186c7  call    HvsocketTraceGuidError
0x1400186cc  mov     eax, esi
0x1400186ce  mov     rcx, [rsp+0B8h+var_48]
0x1400186d3  xor     rcx, rsp; StackCookie
0x1400186d6  call    __security_check_cookie
0x1400186db  add     rsp, 80h
0x1400186e2  pop     r15
0x1400186e4  pop     r14
0x1400186e6  pop     r13
0x1400186e8  pop     r12
0x1400186ea  pop     rdi
0x1400186eb  pop     rsi
0x1400186ec  pop     rbx
0x1400186ed  retn
```
