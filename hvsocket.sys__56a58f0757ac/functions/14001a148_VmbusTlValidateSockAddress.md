# VmbusTlValidateSockAddress

- ea: `0x14001a148`
- end: `0x14001a3d9`
- name: `VmbusTlValidateSockAddress`
- size: `657`
- prototype: `__int64 __fastcall(__int64, _WORD *, int, __int64, char, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task`

## callers

- `0x140020b80`

## callees

- `0x140004f2c`
- `0x140009cf8`
- `0x140009df0`
- `0x14000a048`
- `0x14000a154`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x14001a148`
- `0x14001f540`
- `0x14001febc`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a28e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a28e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001a282`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001a282`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a391`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a391`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a254`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a254`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a37b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a37b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001a264`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001a264`

## pseudocode

```c
__int64 __fastcall VmbusTlValidateSockAddress(__int64 a1, _WORD *a2, int a3, __int64 a4, char a5, __int64 a6)
{
  unsigned int v6; // ebx
  const char *v11; // r9
  __int64 v12; // rdx
  const void *v13; // rdi
  int v14; // eax
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rdi
  signed __int64 v19; // rax
  bool v20; // cc
  signed __int64 v21; // rax
  void (__fastcall *v22)(__int64); // rax

  v6 = -1073741503;
  if ( *a2 == 34 )
  {
    if ( a2[1] )
    {
      if ( (unsigned int)dword_140013058 > 2 )
      {
        v11 = "Reserved field mismatch.";
        v12 = 700;
        goto LABEL_33;
      }
    }
    else
    {
      v13 = a2 + 2;
      if ( memcmp(a2 + 2, &HV_GUID_ZERO, 0x10u) && memcmp(v13, &HV_GUID_CHILDREN, 0x10u) )
      {
        v14 = VmbusTlResolvePartitionId(a1, a3, (_DWORD)v13, a5 != 0 ? 2 : 0, a6);
        v6 = v14;
        if ( v14 >= 0 )
        {
          KeEnterCriticalRegion();
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
          v18 = VmbusTlFindAndReferencePartition(a1, a6);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
          KeLeaveCriticalRegion();
          if ( v18 )
          {
            v6 = VmbusTlAuthenticateConnectSockAddress(v18, a2, a4);
            if ( (v6 & 0x80000000) == 0 )
            {
              v6 = 0;
            }
            else if ( (unsigned int)dword_140013058 > 2 )
            {
              HvsocketTraceServiceError((unsigned int)"VmbusTlValidateSockAddress", 743, v6, (_DWORD)a2 + 20, v18 + 232);
            }
            if ( (unsigned int)dword_140013058 > 5 )
              HvsocketTraceReferenceCount(
                (unsigned int)"VmbusTlValidateSockAddress",
                757,
                v18,
                *(_QWORD *)(v18 + 8),
                (__int64)"Dereference object");
            v19 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v18 + 8), 0xFFFFFFFFFFFFFFFFuLL);
            v20 = v19 <= 1;
            v21 = v19 - 1;
            if ( v20 )
            {
              if ( v21 )
                __fastfail(0xEu);
              v22 = *(void (__fastcall **)(__int64))(v18 + 80);
              if ( v22 )
                v22(v18);
              if ( *(_DWORD *)(v18 + 88) == 1 )
              {
                ExFreePoolWithTag((PVOID)v18, 0x69706E56u);
              }
              else if ( *(_DWORD *)(v18 + 88) == 2 )
              {
                ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v18 + 96), (PVOID)v18);
              }
            }
            return v6;
          }
          v16 = 3221225793LL;
          v6 = -1073741503;
          if ( (unsigned int)dword_140013058 <= 2 )
            return v6;
          v15 = a6;
          v17 = 733;
        }
        else
        {
          if ( (unsigned int)dword_140013058 <= 2 )
            return v6;
          v15 = (__int64)v13;
          v16 = (unsigned int)v14;
          v17 = 722;
        }
        HvsocketTraceGuidError("VmbusTlValidateSockAddress", v17, v16, v15);
        return v6;
      }
      if ( (unsigned int)dword_140013058 > 2 )
      {
        v11 = "Cannot connect to wildcard addresses.";
        v12 = 710;
        goto LABEL_33;
      }
    }
  }
  else if ( (unsigned int)dword_140013058 > 2 )
  {
    v11 = "Address family mismatch.";
    v12 = 694;
LABEL_33:
    HvsocketTraceError("VmbusTlValidateSockAddress", v12, 3221225793LL, v11);
  }
  return v6;
}

```

## disassembly

```asm
0x14001a148  push    rbx
0x14001a14a  push    rbp
0x14001a14b  push    rsi
0x14001a14c  push    rdi
0x14001a14d  push    r12
0x14001a14f  push    r13
0x14001a151  push    r14
0x14001a153  push    r15
0x14001a155  sub     rsp, 38h
0x14001a159  cmp     word ptr [rdx], 22h ; '"'
0x14001a15d  mov     ebp, 0C0000141h
0x14001a162  mov     ebx, ebp
0x14001a164  mov     r15, r9
0x14001a167  mov     r12, r8
0x14001a16a  mov     rsi, rdx
0x14001a16d  mov     r14, rcx
0x14001a170  jz      short loc_14001A192
0x14001a172  mov     eax, cs:dword_140013058
0x14001a178  cmp     eax, 2
0x14001a17b  jbe     loc_14001A3C5
0x14001a181  lea     r9, aAddressFamilyM; "Address family mismatch."
0x14001a188  mov     edx, 2B6h
0x14001a18d  jmp     loc_14001A3B6
0x14001a192  xor     r13d, r13d
0x14001a195  cmp     [rdx+2], r13w
0x14001a19a  jz      short loc_14001A1BC
0x14001a19c  mov     eax, cs:dword_140013058
0x14001a1a2  cmp     eax, 2
0x14001a1a5  jbe     loc_14001A3C5
0x14001a1ab  lea     r9, aReservedFieldM; "Reserved field mismatch."
0x14001a1b2  mov     edx, 2BCh
0x14001a1b7  jmp     loc_14001A3B6
0x14001a1bc  lea     rdi, [rdx+4]
0x14001a1c0  mov     r8d, 10h; Size
0x14001a1c6  mov     rcx, rdi; Buf1
0x14001a1c9  lea     rdx, HV_GUID_ZERO; Buf2
0x14001a1d0  call    memcmp
0x14001a1d5  test    eax, eax
0x14001a1d7  jz      loc_14001A39F
0x14001a1dd  mov     r8d, 10h; Size
0x14001a1e3  lea     rdx, HV_GUID_CHILDREN; Buf2
0x14001a1ea  mov     rcx, rdi; Buf1
0x14001a1ed  call    memcmp
0x14001a1f2  test    eax, eax
0x14001a1f4  jz      loc_14001A39F
0x14001a1fa  neg     [rsp+78h+arg_20]
0x14001a201  mov     r8, rdi
0x14001a204  mov     rbp, [rsp+78h+arg_28]
0x14001a20c  mov     rdx, r12
0x14001a20f  sbb     r9d, r9d
0x14001a212  mov     [rsp+78h+var_58], rbp
0x14001a217  and     r9d, 2
0x14001a21b  mov     rcx, r14
0x14001a21e  call    VmbusTlResolvePartitionId
0x14001a223  mov     ebx, eax
0x14001a225  test    eax, eax
0x14001a227  jns     short loc_14001A254
0x14001a229  mov     ecx, cs:dword_140013058
0x14001a22f  cmp     ecx, 2
0x14001a232  jbe     loc_14001A3C5
0x14001a238  mov     r9, rdi
0x14001a23b  mov     r8d, eax
0x14001a23e  mov     edx, 2D2h
0x14001a243  lea     rcx, aVmbustlvalidat; "VmbusTlValidateSockAddress"
0x14001a24a  call    HvsocketTraceGuidError
0x14001a24f  jmp     loc_14001A3C5
0x14001a254  call    cs:__imp_KeEnterCriticalRegion
0x14001a25b  nop     dword ptr [rax+rax+00h]
0x14001a260  lea     rcx, [r14+10h]; FastMutex
0x14001a264  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001a26b  nop     dword ptr [rax+rax+00h]
0x14001a270  mov     rdx, rbp
0x14001a273  mov     rcx, r14
0x14001a276  call    VmbusTlFindAndReferencePartition
0x14001a27b  lea     rcx, [r14+10h]; FastMutex
0x14001a27f  mov     rdi, rax
0x14001a282  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001a289  nop     dword ptr [rax+rax+00h]
0x14001a28e  call    cs:__imp_KeLeaveCriticalRegion
0x14001a295  nop     dword ptr [rax+rax+00h]
0x14001a29a  test    rdi, rdi
0x14001a29d  jnz     short loc_14001A2C1
0x14001a29f  mov     eax, cs:dword_140013058
0x14001a2a5  mov     r8d, 0C0000141h
0x14001a2ab  mov     ebx, r8d
0x14001a2ae  cmp     eax, 2
0x14001a2b1  jbe     loc_14001A3C5
0x14001a2b7  mov     r9, rbp
0x14001a2ba  mov     edx, 2DDh
0x14001a2bf  jmp     short loc_14001A243
0x14001a2c1  mov     r8, r15
0x14001a2c4  mov     rdx, rsi
0x14001a2c7  mov     rcx, rdi
0x14001a2ca  call    VmbusTlAuthenticateConnectSockAddress
0x14001a2cf  mov     ebx, eax
0x14001a2d1  test    eax, eax
0x14001a2d3  jns     short loc_14001A306
0x14001a2d5  mov     eax, cs:dword_140013058
0x14001a2db  cmp     eax, 2
0x14001a2de  jbe     short loc_14001A309
0x14001a2e0  lea     rax, [rdi+0E8h]
0x14001a2e7  mov     r8d, ebx
0x14001a2ea  lea     r9, [rsi+14h]
0x14001a2ee  mov     [rsp+78h+var_58], rax
0x14001a2f3  mov     edx, 2E7h
0x14001a2f8  lea     rcx, aVmbustlvalidat; "VmbusTlValidateSockAddress"
0x14001a2ff  call    HvsocketTraceServiceError
0x14001a304  jmp     short loc_14001A309
0x14001a306  mov     ebx, r13d
0x14001a309  mov     eax, cs:dword_140013058
0x14001a30f  cmp     eax, 5
0x14001a312  jbe     short loc_14001A338
0x14001a314  mov     r9, [rdi+8]
0x14001a318  lea     rax, aDereferenceObj; "Dereference object"
0x14001a31f  mov     r8, rdi
0x14001a322  mov     [rsp+78h+var_58], rax
0x14001a327  mov     edx, 2F5h
0x14001a32c  lea     rcx, aVmbustlvalidat; "VmbusTlValidateSockAddress"
0x14001a333  call    HvsocketTraceReferenceCount
0x14001a338  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001a33c  lock xadd [rdi+8], rax
0x14001a342  sub     rax, 1
0x14001a346  jg      short loc_14001A3C5
0x14001a348  test    rax, rax
0x14001a34b  jz      short loc_14001A356
0x14001a34d  mov     ecx, 0Eh
0x14001a352  int     29h; Win8: RtlFailFast(ecx)
0x14001a354  jmp     short loc_14001A3C5
0x14001a356  mov     rax, [rdi+50h]
0x14001a35a  test    rax, rax
0x14001a35d  jz      short loc_14001A367
0x14001a35f  mov     rcx, rdi
0x14001a362  call    _guard_dispatch_icall
0x14001a367  mov     ecx, [rdi+58h]
0x14001a36a  sub     ecx, 1
0x14001a36d  jz      short loc_14001A389
0x14001a36f  cmp     ecx, 1
0x14001a372  jnz     short loc_14001A3C5
0x14001a374  mov     rcx, [rdi+60h]; Lookaside
0x14001a378  mov     rdx, rdi; Entry
0x14001a37b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001a382  nop     dword ptr [rax+rax+00h]
0x14001a387  jmp     short loc_14001A3C5
0x14001a389  mov     edx, 69706E56h; Tag
0x14001a38e  mov     rcx, rdi; P
0x14001a391  call    cs:__imp_ExFreePoolWithTag
0x14001a398  nop     dword ptr [rax+rax+00h]
0x14001a39d  jmp     short loc_14001A3C5
0x14001a39f  mov     eax, cs:dword_140013058
0x14001a3a5  cmp     eax, 2
0x14001a3a8  jbe     short loc_14001A3C5
0x14001a3aa  lea     r9, aCannotConnectT; "Cannot connect to wildcard addresses."
0x14001a3b1  mov     edx, 2C6h
0x14001a3b6  mov     r8d, ebp
0x14001a3b9  lea     rcx, aVmbustlvalidat; "VmbusTlValidateSockAddress"
0x14001a3c0  call    HvsocketTraceError
0x14001a3c5  mov     eax, ebx
0x14001a3c7  add     rsp, 38h
0x14001a3cb  pop     r15
0x14001a3cd  pop     r14
0x14001a3cf  pop     r13
0x14001a3d1  pop     r12
0x14001a3d3  pop     rdi
0x14001a3d4  pop     rsi
0x14001a3d5  pop     rbp
0x14001a3d6  pop     rbx
0x14001a3d7  retn
```
