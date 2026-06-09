# VmbusTlAssociateConnectionToPartition

- ea: `0x14001e1c0`
- end: `0x14001e5a3`
- name: `VmbusTlAssociateConnectionToPartition`
- size: `995`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task`

## callers

- `0x14001c2d0`
- `0x140020b80`

## callees

- `0x140008960`
- `0x1400098f4`
- `0x14000a048`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x14001e1c0`
- `0x14001f540`
- `0x140021da4`
- `0x140021ec0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e285`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e44c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e285`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e44c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001e279`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001e440`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001e279`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001e440`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e4ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e578`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e4ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e578`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e249`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e2d0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e249`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e2d0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e4d6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e564`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e4d6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e564`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001e259`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001e2e0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001e259`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001e2e0`

## pseudocode

```c
__int64 __fastcall VmbusTlAssociateConnectionToPartition(__int64 a1, GUID *a2, GUID *a3, __int64 a4)
{
  PVOID v7; // rdi
  GUID v9; // xmm0
  __int64 v10; // rsi
  int v11; // ebx
  int v12; // eax
  __int64 v13; // rax
  void (__fastcall *v14)(__int64); // rax
  __int64 v15; // rax
  void (__fastcall *v16)(PVOID); // rax
  PVOID Entry; // [rsp+30h] [rbp-58h] BYREF
  GUID v19; // [rsp+38h] [rbp-50h] BYREF

  v7 = 0;
  if ( !memcmp(a3, &HV_GUID_PARENT, 0x10u) || !memcmp(a2, &HV_GUID_PARENT, 0x10u) )
  {
    v9 = HV_GUID_PARENT;
  }
  else if ( !memcmp(a3, &HV_GUID_CHILDREN, 0x10u) )
  {
    v9 = *a2;
  }
  else
  {
    v9 = *a3;
  }
  v19 = v9;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  v10 = VmbusTlFindAndReferencePartition(a1, &v19);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  if ( !v10 )
  {
    v11 = -1073741808;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointGuidError(
        (unsigned int)"VmbusTlAssociateConnectionToPartition",
        1403,
        -1073741808,
        a4,
        (__int64)&v19);
    return (unsigned int)v11;
  }
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v10 + 16));
  if ( *(_BYTE *)(v10 + 393) || *(_BYTE *)(v10 + 392) && !*(_BYTE *)(a4 + 185) )
  {
    v11 = -1073741252;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointGuidError(
        (unsigned int)"VmbusTlAssociateConnectionToPartition",
        1445,
        -1073741252,
        a4,
        (__int64)&v19);
    goto LABEL_27;
  }
  Entry = (PVOID)VmbusTlFindAndReferenceService(v10, a4 + 156);
  v7 = Entry;
  if ( Entry )
    goto LABEL_22;
  v12 = VmbusTlCreateTransientService(v10, a4 + 156, &Entry);
  v11 = v12;
  if ( v12 >= 0 )
  {
    v7 = Entry;
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlAssociateConnectionToPartition",
        1459,
        (_DWORD)Entry,
        *((_QWORD *)Entry + 1),
        (__int64)"Reference object");
    if ( _InterlockedIncrement64((volatile signed __int64 *)v7 + 1) <= 1 )
      __fastfail(0xEu);
LABEL_22:
    *(_QWORD *)(a4 + 736) = v10;
    *(_DWORD *)(a4 + 768) = *(_DWORD *)(v10 + 104);
    VmbusTlAssociateConnectionToService(v7, a4);
    v11 = 0;
    ++*(_DWORD *)(*(_QWORD *)(a4 + 736) + 408LL);
    if ( *(_BYTE *)(a4 + 185) )
      ++*(_DWORD *)(*(_QWORD *)(a4 + 736) + 412LL);
    *(_BYTE *)(a4 + 172) = 1;
    goto LABEL_27;
  }
  if ( (unsigned int)dword_140013058 > 2 )
    HvsocketTraceEndpointGuidError((unsigned int)"VmbusTlAssociateConnectionToPartition", 1455, v12, a4, a4 + 156);
  v7 = Entry;
LABEL_27:
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v10 + 16));
  KeLeaveCriticalRegion();
  if ( v11 < 0 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlAssociateConnectionToPartition",
        1494,
        v10,
        *(_QWORD *)(v10 + 8),
        (__int64)"Dereference object");
    v13 = _InterlockedDecrement64((volatile signed __int64 *)(v10 + 8));
    if ( v13 <= 0 )
    {
      if ( v13 )
        __fastfail(0xEu);
      v14 = *(void (__fastcall **)(__int64))(v10 + 80);
      if ( v14 )
        v14(v10);
      if ( *(_DWORD *)(v10 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v10, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v10 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v10 + 96), (PVOID)v10);
      }
    }
  }
  if ( v7 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlAssociateConnectionToPartition",
        1500,
        (_DWORD)v7,
        *((_QWORD *)v7 + 1),
        (__int64)"Dereference object");
    v15 = _InterlockedDecrement64((volatile signed __int64 *)v7 + 1);
    if ( v15 <= 0 )
    {
      if ( v15 )
        __fastfail(0xEu);
      v16 = (void (__fastcall *)(PVOID))*((_QWORD *)v7 + 10);
      if ( v16 )
        v16(v7);
      if ( *((_DWORD *)v7 + 22) == 1 )
      {
        ExFreePoolWithTag(v7, 0x69706E56u);
      }
      else if ( *((_DWORD *)v7 + 22) == 2 )
      {
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v7 + 12), v7);
      }
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14001e1c0  push    rbx
0x14001e1c2  push    rbp
0x14001e1c3  push    rsi
0x14001e1c4  push    rdi
0x14001e1c5  push    r12
0x14001e1c7  push    r14
0x14001e1c9  push    r15
0x14001e1cb  sub     rsp, 50h
0x14001e1cf  mov     rax, cs:__security_cookie
0x14001e1d6  xor     rax, rsp
0x14001e1d9  mov     [rsp+88h+var_40], rax
0x14001e1de  mov     rbx, r8
0x14001e1e1  mov     rsi, rdx
0x14001e1e4  mov     r14, rcx
0x14001e1e7  lea     rdx, HV_GUID_PARENT; Buf2
0x14001e1ee  xor     edi, edi
0x14001e1f0  mov     rcx, rbx; Buf1
0x14001e1f3  mov     rbp, r9
0x14001e1f6  lea     r15d, [rdi+10h]
0x14001e1fa  mov     r8d, r15d; Size
0x14001e1fd  call    memcmp
0x14001e202  test    eax, eax
0x14001e204  jz      short loc_14001E23C
0x14001e206  mov     r8d, r15d; Size
0x14001e209  lea     rdx, HV_GUID_PARENT; Buf2
0x14001e210  mov     rcx, rsi; Buf1
0x14001e213  call    memcmp
0x14001e218  test    eax, eax
0x14001e21a  jz      short loc_14001E23C
0x14001e21c  mov     r8d, r15d; Size
0x14001e21f  lea     rdx, HV_GUID_CHILDREN; Buf2
0x14001e226  mov     rcx, rbx; Buf1
0x14001e229  call    memcmp
0x14001e22e  test    eax, eax
0x14001e230  jz      short loc_14001E237
0x14001e232  movups  xmm0, xmmword ptr [rbx]
0x14001e235  jmp     short loc_14001E243
0x14001e237  movups  xmm0, xmmword ptr [rsi]
0x14001e23a  jmp     short loc_14001E243
0x14001e23c  movups  xmm0, xmmword ptr cs:HV_GUID_PARENT.Data1
0x14001e243  movdqu  [rsp+88h+var_50], xmm0
0x14001e249  call    cs:__imp_KeEnterCriticalRegion
0x14001e250  nop     dword ptr [rax+rax+00h]
0x14001e255  lea     rcx, [r14+10h]; FastMutex
0x14001e259  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001e260  nop     dword ptr [rax+rax+00h]
0x14001e265  lea     rdx, [rsp+88h+var_50]
0x14001e26a  mov     rcx, r14
0x14001e26d  call    VmbusTlFindAndReferencePartition
0x14001e272  lea     rcx, [r14+10h]; FastMutex
0x14001e276  mov     rsi, rax
0x14001e279  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001e280  nop     dword ptr [rax+rax+00h]
0x14001e285  call    cs:__imp_KeLeaveCriticalRegion
0x14001e28c  nop     dword ptr [rax+rax+00h]
0x14001e291  test    rsi, rsi
0x14001e294  jnz     short loc_14001E2D0
0x14001e296  mov     eax, cs:dword_140013058
0x14001e29c  mov     ebx, 0C0000010h
0x14001e2a1  cmp     eax, 2
0x14001e2a4  jbe     loc_14001E584
0x14001e2aa  lea     rax, [rsp+88h+var_50]
0x14001e2af  mov     r9, rbp
0x14001e2b2  mov     r8d, ebx
0x14001e2b5  mov     [rsp+88h+var_68], rax
0x14001e2ba  mov     edx, 57Bh
0x14001e2bf  lea     rcx, aVmbustlassocia_2; "VmbusTlAssociateConnectionToPartition"
0x14001e2c6  call    HvsocketTraceEndpointGuidError
0x14001e2cb  jmp     loc_14001E584
0x14001e2d0  call    cs:__imp_KeEnterCriticalRegion
0x14001e2d7  nop     dword ptr [rax+rax+00h]
0x14001e2dc  lea     rcx, [rsi+10h]; FastMutex
0x14001e2e0  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001e2e7  nop     dword ptr [rax+rax+00h]
0x14001e2ec  lea     r14, aVmbustlassocia_2; "VmbusTlAssociateConnectionToPartition"
0x14001e2f3  cmp     [rsi+189h], dil
0x14001e2fa  jnz     loc_14001E40F
0x14001e300  cmp     [rsi+188h], dil
0x14001e307  jz      short loc_14001E316
0x14001e309  cmp     [rbp+0B9h], dil
0x14001e310  jz      loc_14001E40F
0x14001e316  lea     r15, [rbp+9Ch]
0x14001e31d  mov     rcx, rsi
0x14001e320  mov     rdx, r15
0x14001e323  call    VmbusTlFindAndReferenceService
0x14001e328  mov     [rsp+88h+Entry], rax
0x14001e32d  mov     rdi, rax
0x14001e330  test    rax, rax
0x14001e333  jnz     loc_14001E3C7
0x14001e339  lea     r8, [rsp+88h+Entry]
0x14001e33e  mov     rdx, r15
0x14001e341  mov     rcx, rsi
0x14001e344  call    VmbusTlCreateTransientService
0x14001e349  mov     ebx, eax
0x14001e34b  test    eax, eax
0x14001e34d  jns     short loc_14001E37C
0x14001e34f  mov     ecx, cs:dword_140013058
0x14001e355  cmp     ecx, 2
0x14001e358  jbe     short loc_14001E372
0x14001e35a  mov     r9, rbp
0x14001e35d  mov     [rsp+88h+var_68], r15
0x14001e362  mov     r8d, eax
0x14001e365  mov     edx, 5AFh
0x14001e36a  mov     rcx, r14
0x14001e36d  call    HvsocketTraceEndpointGuidError
0x14001e372  mov     rdi, [rsp+88h+Entry]
0x14001e377  jmp     loc_14001E43C
0x14001e37c  mov     eax, cs:dword_140013058
0x14001e382  mov     rdi, [rsp+88h+Entry]
0x14001e387  cmp     eax, 5
0x14001e38a  jbe     short loc_14001E3AC
0x14001e38c  mov     r9, [rdi+8]
0x14001e390  lea     rax, aReferenceObjec; "Reference object"
0x14001e397  mov     r8, rdi
0x14001e39a  mov     [rsp+88h+var_68], rax
0x14001e39f  mov     edx, 5B3h
0x14001e3a4  mov     rcx, r14
0x14001e3a7  call    HvsocketTraceReferenceCount
0x14001e3ac  mov     eax, 1
0x14001e3b1  lock xadd [rdi+8], rax
0x14001e3b7  inc     rax
0x14001e3ba  cmp     rax, 1
0x14001e3be  jg      short loc_14001E3C7
0x14001e3c0  mov     ecx, 0Eh
0x14001e3c5  int     29h; Win8: RtlFailFast(ecx)
0x14001e3c7  mov     [rbp+2E0h], rsi
0x14001e3ce  mov     rdx, rbp
0x14001e3d1  mov     eax, [rsi+68h]
0x14001e3d4  mov     rcx, rdi
0x14001e3d7  mov     [rbp+300h], eax
0x14001e3dd  call    VmbusTlAssociateConnectionToService
0x14001e3e2  mov     rax, [rbp+2E0h]
0x14001e3e9  xor     ebx, ebx
0x14001e3eb  inc     dword ptr [rax+198h]
0x14001e3f1  cmp     [rbp+0B9h], bl
0x14001e3f7  jz      short loc_14001E406
0x14001e3f9  mov     rax, [rbp+2E0h]
0x14001e400  inc     dword ptr [rax+19Ch]
0x14001e406  mov     byte ptr [rbp+0ACh], 1
0x14001e40d  jmp     short loc_14001E43C
0x14001e40f  mov     eax, cs:dword_140013058
0x14001e415  mov     ebx, 0C000023Ch
0x14001e41a  cmp     eax, 2
0x14001e41d  jbe     short loc_14001E43C
0x14001e41f  lea     rax, [rsp+88h+var_50]
0x14001e424  mov     r9, rbp
0x14001e427  mov     r8d, ebx
0x14001e42a  mov     [rsp+88h+var_68], rax
0x14001e42f  mov     edx, 5A5h
0x14001e434  mov     rcx, r14
0x14001e437  call    HvsocketTraceEndpointGuidError
0x14001e43c  lea     rcx, [rsi+10h]; FastMutex
0x14001e440  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001e447  nop     dword ptr [rax+rax+00h]
0x14001e44c  call    cs:__imp_KeLeaveCriticalRegion
0x14001e453  nop     dword ptr [rax+rax+00h]
0x14001e458  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14001e45c  lea     r12, aDereferenceObj; "Dereference object"
0x14001e463  mov     r15d, 69706E56h
0x14001e469  test    ebx, ebx
0x14001e46b  jns     loc_14001E4F6
0x14001e471  mov     eax, cs:dword_140013058
0x14001e477  cmp     eax, 5
0x14001e47a  jbe     short loc_14001E495
0x14001e47c  mov     r9, [rsi+8]
0x14001e480  mov     r8, rsi
0x14001e483  mov     edx, 5D6h
0x14001e488  mov     [rsp+88h+var_68], r12
0x14001e48d  mov     rcx, r14
0x14001e490  call    HvsocketTraceReferenceCount
0x14001e495  mov     rax, rbp
0x14001e498  lock xadd [rsi+8], rax
0x14001e49e  add     rax, rbp
0x14001e4a1  test    rax, rax
0x14001e4a4  jg      short loc_14001E4F6
0x14001e4a6  jz      short loc_14001E4B1
0x14001e4a8  mov     ecx, 0Eh
0x14001e4ad  int     29h; Win8: RtlFailFast(ecx)
0x14001e4af  jmp     short loc_14001E4F6
0x14001e4b1  mov     rax, [rsi+50h]
0x14001e4b5  test    rax, rax
0x14001e4b8  jz      short loc_14001E4C2
0x14001e4ba  mov     rcx, rsi
0x14001e4bd  call    _guard_dispatch_icall
0x14001e4c2  mov     ecx, [rsi+58h]
0x14001e4c5  sub     ecx, 1
0x14001e4c8  jz      short loc_14001E4E4
0x14001e4ca  cmp     ecx, 1
0x14001e4cd  jnz     short loc_14001E4F6
0x14001e4cf  mov     rcx, [rsi+60h]; Lookaside
0x14001e4d3  mov     rdx, rsi; Entry
0x14001e4d6  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001e4dd  nop     dword ptr [rax+rax+00h]
0x14001e4e2  jmp     short loc_14001E4F6
0x14001e4e4  mov     edx, r15d; Tag
0x14001e4e7  mov     rcx, rsi; P
0x14001e4ea  call    cs:__imp_ExFreePoolWithTag
0x14001e4f1  nop     dword ptr [rax+rax+00h]
0x14001e4f6  test    rdi, rdi
0x14001e4f9  jz      loc_14001E584
0x14001e4ff  mov     eax, cs:dword_140013058
0x14001e505  cmp     eax, 5
0x14001e508  jbe     short loc_14001E523
0x14001e50a  mov     r9, [rdi+8]
0x14001e50e  mov     r8, rdi
0x14001e511  mov     edx, 5DCh
0x14001e516  mov     [rsp+88h+var_68], r12
0x14001e51b  mov     rcx, r14
0x14001e51e  call    HvsocketTraceReferenceCount
0x14001e523  mov     rax, rbp
0x14001e526  lock xadd [rdi+8], rax
0x14001e52c  add     rax, rbp
0x14001e52f  test    rax, rax
0x14001e532  jg      short loc_14001E584
0x14001e534  jz      short loc_14001E53F
0x14001e536  mov     ecx, 0Eh
0x14001e53b  int     29h; Win8: RtlFailFast(ecx)
0x14001e53d  jmp     short loc_14001E584
0x14001e53f  mov     rax, [rdi+50h]
0x14001e543  test    rax, rax
0x14001e546  jz      short loc_14001E550
0x14001e548  mov     rcx, rdi
0x14001e54b  call    _guard_dispatch_icall
0x14001e550  mov     ecx, [rdi+58h]
0x14001e553  sub     ecx, 1
0x14001e556  jz      short loc_14001E572
0x14001e558  cmp     ecx, 1
0x14001e55b  jnz     short loc_14001E584
0x14001e55d  mov     rcx, [rdi+60h]; Lookaside
0x14001e561  mov     rdx, rdi; Entry
0x14001e564  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001e56b  nop     dword ptr [rax+rax+00h]
0x14001e570  jmp     short loc_14001E584
0x14001e572  mov     edx, r15d; Tag
0x14001e575  mov     rcx, rdi; P
0x14001e578  call    cs:__imp_ExFreePoolWithTag
0x14001e57f  nop     dword ptr [rax+rax+00h]
0x14001e584  mov     eax, ebx
0x14001e586  mov     rcx, [rsp+88h+var_40]
0x14001e58b  xor     rcx, rsp; StackCookie
0x14001e58e  call    __security_check_cookie
0x14001e593  add     rsp, 50h
0x14001e597  pop     r15
0x14001e599  pop     r14
0x14001e59b  pop     r12
0x14001e59d  pop     rdi
0x14001e59e  pop     rsi
0x14001e59f  pop     rbp
0x14001e5a0  pop     rbx
0x14001e5a1  retn
```
