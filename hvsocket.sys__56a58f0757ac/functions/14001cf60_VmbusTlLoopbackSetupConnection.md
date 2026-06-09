# VmbusTlLoopbackSetupConnection

- ea: `0x14001cf60`
- end: `0x14001d2fd`
- name: `VmbusTlLoopbackSetupConnection`
- size: `925`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, installer_update`

## callees

- `0x140001350`
- `0x140002f34`
- `0x1400068ac`
- `0x14000975c`
- `0x1400098f4`
- `0x14000a048`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x14001bd20`
- `0x14001cf60`
- `0x14001febc`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d2c9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d2c9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001d2bd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001d2bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d20b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d2ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d20b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d2ad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001d15d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001d15d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001d1f5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001d297`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001d1f5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001d297`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001d16d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001d16d`

## pseudocode

```c
__int64 __fastcall VmbusTlLoopbackSetupConnection(__int64 a1, __int64 a2, char a3)
{
  PVOID v3; // rbx
  int v5; // eax
  int v6; // esi
  __int64 v7; // r8
  int v8; // edx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r14
  signed __int64 v12; // rax
  bool v13; // cc
  signed __int64 v14; // rax
  void (__fastcall *v15)(__int64); // rax
  signed __int64 v16; // rax
  signed __int64 v17; // rax
  void (__fastcall *v18)(PVOID); // rax
  PVOID Entry; // [rsp+40h] [rbp-30h] BYREF
  __int128 v21; // [rsp+48h] [rbp-28h] BYREF
  __int128 v22; // [rsp+58h] [rbp-18h] BYREF

  v3 = 0;
  Entry = 0;
  v21 = 0;
  v22 = 0;
  if ( !a3 )
  {
    v6 = -1073741637;
    if ( (unsigned int)dword_140013058 <= 2 )
      return (unsigned int)v6;
    HvsocketTraceEndpointGuidError((const int *)"VmbusTlLoopbackSetupConnection", 157, 3221225659LL, a2, a2 + 140);
    goto LABEL_23;
  }
  v5 = VmbusTlCreateObject(1u, 112, &Entry);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
    {
LABEL_6:
      v3 = Entry;
      goto LABEL_23;
    }
    v7 = (unsigned int)v5;
    v8 = 99;
LABEL_5:
    HvsocketTraceEndpointError((const int *)"VmbusTlLoopbackSetupConnection", v8, v7, a2);
    goto LABEL_6;
  }
  v6 = VmbusTlSetupConnectionId(a2);
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_6;
    v7 = (unsigned int)v6;
    v8 = 107;
    goto LABEL_5;
  }
  v3 = Entry;
  *(_QWORD *)(a2 + 696) = Entry;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlLoopbackSetupConnection",
      120,
      a2,
      *(_QWORD *)(a2 + 8),
      (const int *)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)(a2 + 8)) <= 1 )
    __fastfail(0xEu);
  v22 = *(_OWORD *)(a2 + 280);
  v9 = memcmp((const void *)(a2 + 280), &HV_GUID_CHILDREN, 0x10u);
  v10 = *(_QWORD *)(a2 + 736);
  if ( v9 )
  {
    v6 = VmbusTlResolvePartitionId(*(_QWORD *)(a2 + 112), v10, (int)a2 + 140, 0, (__int64)&v21);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceEndpointGuidError(
          (const int *)"VmbusTlLoopbackSetupConnection",
          137,
          (unsigned int)v6,
          a2,
          a2 + 140);
      goto LABEL_23;
    }
  }
  else
  {
    v21 = *(_OWORD *)(v10 + 232);
  }
  v6 = VmbusTlProcessNewConnection(*(_QWORD *)(a2 + 112), a2, &v21, &v22, &HV_GUID_ZERO, a2 + 156, a2 + 464, 3);
  if ( v6 >= 0 )
    return 259;
LABEL_23:
  if ( v3 )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 16));
    v11 = *((_QWORD *)v3 + 13);
    if ( v11 )
    {
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (const int *)"VmbusTlLoopbackSetupConnection",
          179,
          *((_QWORD *)v3 + 13),
          *(_QWORD *)(v11 + 8),
          (const int *)"Dereference object");
      v12 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v11 + 8), 0xFFFFFFFFFFFFFFFFuLL);
      v13 = v12 <= 1;
      v14 = v12 - 1;
      if ( v13 )
      {
        if ( v14 )
          __fastfail(0xEu);
        v15 = *(void (__fastcall **)(__int64))(v11 + 80);
        if ( v15 )
          v15(v11);
        if ( *(_DWORD *)(v11 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v11, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v11 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v11 + 96), (PVOID)v11);
        }
      }
      *((_QWORD *)v3 + 13) = 0;
    }
    VmbusTlLoopbackSetEndpointDeliveryQueue(a2);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlLoopbackSetupConnection",
        184,
        (__int64)v3,
        *((_QWORD *)v3 + 1),
        (const int *)"Dereference object");
    v16 = _InterlockedExchangeAdd64((volatile signed __int64 *)v3 + 1, 0xFFFFFFFFFFFFFFFFuLL);
    v13 = v16 <= 1;
    v17 = v16 - 1;
    if ( v13 )
    {
      if ( v17 )
        __fastfail(0xEu);
      v18 = (void (__fastcall *)(PVOID))*((_QWORD *)v3 + 10);
      if ( v18 )
        v18(v3);
      if ( *((_DWORD *)v3 + 22) == 1 )
      {
        ExFreePoolWithTag(v3, 0x69706E56u);
      }
      else if ( *((_DWORD *)v3 + 22) == 2 )
      {
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v3 + 12), v3);
      }
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 16));
    KeLeaveCriticalRegion();
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001cf60  mov     [rsp-28h+arg_0], rbx
0x14001cf65  mov     [rsp-28h+arg_10], rsi
0x14001cf6a  push    rbp
0x14001cf6b  push    rdi
0x14001cf6c  push    r12
0x14001cf6e  push    r14
0x14001cf70  push    r15
0x14001cf72  mov     rbp, rsp
0x14001cf75  sub     rsp, 70h
0x14001cf79  mov     rax, cs:__security_cookie
0x14001cf80  xor     rax, rsp
0x14001cf83  mov     [rbp+var_8], rax
0x14001cf87  xor     ebx, ebx
0x14001cf89  lea     r12, aVmbustlloopbac_6; "VmbusTlLoopbackSetupConnection"
0x14001cf90  mov     [rbp+Entry], rbx
0x14001cf94  xorps   xmm0, xmm0
0x14001cf97  xorps   xmm1, xmm1
0x14001cf9a  mov     rdi, rdx
0x14001cf9d  movups  [rbp+var_28], xmm0
0x14001cfa1  movups  [rbp+var_18], xmm1
0x14001cfa5  test    r8b, r8b
0x14001cfa8  jz      loc_14001D121
0x14001cfae  lea     r14d, [rbx+1]
0x14001cfb2  mov     ecx, r14d
0x14001cfb5  lea     r8, [rbp+Entry]
0x14001cfb9  lea     edx, [rbx+70h]
0x14001cfbc  call    VmbusTlCreateObject
0x14001cfc1  mov     esi, eax
0x14001cfc3  test    eax, eax
0x14001cfc5  jns     short loc_14001CFEC
0x14001cfc7  mov     ecx, cs:dword_140013058
0x14001cfcd  cmp     ecx, 2
0x14001cfd0  jbe     short loc_14001CFE3
0x14001cfd2  mov     r8d, eax
0x14001cfd5  lea     edx, [rbx+63h]
0x14001cfd8  mov     r9, rdi
0x14001cfdb  mov     rcx, r12
0x14001cfde  call    HvsocketTraceEndpointError
0x14001cfe3  mov     rbx, [rbp+Entry]
0x14001cfe7  jmp     loc_14001D154
0x14001cfec  mov     rcx, rdi
0x14001cfef  call    VmbusTlSetupConnectionId
0x14001cff4  mov     esi, eax
0x14001cff6  test    eax, eax
0x14001cff8  jns     short loc_14001D00F
0x14001cffa  mov     eax, cs:dword_140013058
0x14001d000  cmp     eax, 2
0x14001d003  jbe     short loc_14001CFE3
0x14001d005  mov     r8d, esi
0x14001d008  mov     edx, 6Bh ; 'k'
0x14001d00d  jmp     short loc_14001CFD8
0x14001d00f  mov     rbx, [rbp+Entry]
0x14001d013  mov     [rdi+2B8h], rbx
0x14001d01a  mov     eax, cs:dword_140013058
0x14001d020  cmp     eax, 5
0x14001d023  jbe     short loc_14001D045
0x14001d025  mov     r9, [rdi+8]
0x14001d029  lea     rax, aReferenceObjec; "Reference object"
0x14001d030  mov     r8, rdi
0x14001d033  mov     [rsp+70h+var_50], rax
0x14001d038  mov     edx, 78h ; 'x'
0x14001d03d  mov     rcx, r12
0x14001d040  call    HvsocketTraceReferenceCount
0x14001d045  mov     rax, r14
0x14001d048  lock xadd [rdi+8], rax
0x14001d04e  add     rax, r14
0x14001d051  cmp     rax, r14
0x14001d054  jg      short loc_14001D05D
0x14001d056  mov     ecx, 0Eh
0x14001d05b  int     29h; Win8: RtlFailFast(ecx)
0x14001d05d  lea     rcx, [rdi+118h]; Buf1
0x14001d064  mov     r8d, 10h; Size
0x14001d06a  movups  xmm0, xmmword ptr [rcx]
0x14001d06d  lea     rdx, HV_GUID_CHILDREN; Buf2
0x14001d074  movdqu  [rbp+var_18], xmm0
0x14001d079  call    memcmp
0x14001d07e  mov     rdx, [rdi+2E0h]
0x14001d085  test    eax, eax
0x14001d087  jnz     short loc_14001D0E5
0x14001d089  movups  xmm0, xmmword ptr [rdx+0E8h]
0x14001d090  movdqu  [rbp+var_28], xmm0
0x14001d095  mov     [rsp+70h+var_38], 3
0x14001d09d  lea     rax, [rdi+1D0h]
0x14001d0a4  mov     [rsp+70h+var_40], rax
0x14001d0a9  lea     rcx, [rdi+9Ch]
0x14001d0b0  mov     [rsp+70h+var_48], rcx
0x14001d0b5  lea     rax, HV_GUID_ZERO
0x14001d0bc  mov     rcx, [rdi+70h]
0x14001d0c0  lea     r9, [rbp+var_18]
0x14001d0c4  lea     r8, [rbp+var_28]
0x14001d0c8  mov     [rsp+70h+var_50], rax
0x14001d0cd  mov     rdx, rdi
0x14001d0d0  call    VmbusTlProcessNewConnection
0x14001d0d5  mov     esi, eax
0x14001d0d7  test    eax, eax
0x14001d0d9  js      short loc_14001D154
0x14001d0db  mov     esi, 103h
0x14001d0e0  jmp     loc_14001D2D5
0x14001d0e5  mov     rcx, [rdi+70h]
0x14001d0e9  lea     rax, [rbp+var_28]
0x14001d0ed  lea     r14, [rdi+8Ch]
0x14001d0f4  mov     [rsp+70h+var_50], rax
0x14001d0f9  mov     r8, r14
0x14001d0fc  xor     r9d, r9d
0x14001d0ff  call    VmbusTlResolvePartitionId
0x14001d104  mov     esi, eax
0x14001d106  test    eax, eax
0x14001d108  jns     short loc_14001D095
0x14001d10a  mov     eax, cs:dword_140013058
0x14001d110  cmp     eax, 2
0x14001d113  jbe     short loc_14001D154
0x14001d115  mov     [rsp+70h+var_50], r14
0x14001d11a  mov     edx, 89h
0x14001d11f  jmp     short loc_14001D146
0x14001d121  mov     eax, cs:dword_140013058
0x14001d127  mov     esi, 0C00000BBh
0x14001d12c  cmp     eax, 2
0x14001d12f  jbe     loc_14001D2D5
0x14001d135  lea     rax, [rdx+8Ch]
0x14001d13c  mov     edx, 9Dh
0x14001d141  mov     [rsp+70h+var_50], rax
0x14001d146  mov     r9, rdi
0x14001d149  mov     r8d, esi
0x14001d14c  mov     rcx, r12
0x14001d14f  call    HvsocketTraceEndpointGuidError
0x14001d154  test    rbx, rbx
0x14001d157  jz      loc_14001D2D5
0x14001d15d  call    cs:__imp_KeEnterCriticalRegion
0x14001d164  nop     dword ptr [rax+rax+00h]
0x14001d169  lea     rcx, [rdi+10h]; FastMutex
0x14001d16d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001d174  nop     dword ptr [rax+rax+00h]
0x14001d179  mov     r14, [rbx+68h]
0x14001d17d  lea     rcx, aDereferenceObj; "Dereference object"
0x14001d184  test    r14, r14
0x14001d187  jz      loc_14001D21F
0x14001d18d  mov     eax, cs:dword_140013058
0x14001d193  cmp     eax, 5
0x14001d196  jbe     short loc_14001D1B1
0x14001d198  mov     r9, [r14+8]
0x14001d19c  mov     r8, r14
0x14001d19f  mov     [rsp+70h+var_50], rcx
0x14001d1a4  mov     edx, 0B3h
0x14001d1a9  mov     rcx, r12
0x14001d1ac  call    HvsocketTraceReferenceCount
0x14001d1b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001d1b5  lock xadd [r14+8], rax
0x14001d1bb  sub     rax, 1
0x14001d1bf  jg      short loc_14001D217
0x14001d1c1  test    rax, rax
0x14001d1c4  jz      short loc_14001D1CF
0x14001d1c6  mov     ecx, 0Eh
0x14001d1cb  int     29h; Win8: RtlFailFast(ecx)
0x14001d1cd  jmp     short loc_14001D217
0x14001d1cf  mov     rax, [r14+50h]
0x14001d1d3  test    rax, rax
0x14001d1d6  jz      short loc_14001D1E0
0x14001d1d8  mov     rcx, r14
0x14001d1db  call    _guard_dispatch_icall
0x14001d1e0  mov     ecx, [r14+58h]
0x14001d1e4  sub     ecx, 1
0x14001d1e7  jz      short loc_14001D203
0x14001d1e9  cmp     ecx, 1
0x14001d1ec  jnz     short loc_14001D217
0x14001d1ee  mov     rcx, [r14+60h]; Lookaside
0x14001d1f2  mov     rdx, r14; Entry
0x14001d1f5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001d1fc  nop     dword ptr [rax+rax+00h]
0x14001d201  jmp     short loc_14001D217
0x14001d203  mov     edx, 69706E56h; Tag
0x14001d208  mov     rcx, r14; P
0x14001d20b  call    cs:__imp_ExFreePoolWithTag
0x14001d212  nop     dword ptr [rax+rax+00h]
0x14001d217  mov     qword ptr [rbx+68h], 0
0x14001d21f  xor     edx, edx
0x14001d221  mov     rcx, rdi
0x14001d224  call    VmbusTlLoopbackSetEndpointDeliveryQueue
0x14001d229  mov     eax, cs:dword_140013058
0x14001d22f  cmp     eax, 5
0x14001d232  jbe     short loc_14001D254
0x14001d234  mov     r9, [rbx+8]
0x14001d238  lea     rax, aDereferenceObj; "Dereference object"
0x14001d23f  mov     r8, rbx
0x14001d242  mov     [rsp+70h+var_50], rax
0x14001d247  mov     edx, 0B8h
0x14001d24c  mov     rcx, r12
0x14001d24f  call    HvsocketTraceReferenceCount
0x14001d254  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001d258  lock xadd [rbx+8], rax
0x14001d25e  sub     rax, 1
0x14001d262  jg      short loc_14001D2B9
0x14001d264  test    rax, rax
0x14001d267  jz      short loc_14001D272
0x14001d269  mov     ecx, 0Eh
0x14001d26e  int     29h; Win8: RtlFailFast(ecx)
0x14001d270  jmp     short loc_14001D2B9
0x14001d272  mov     rax, [rbx+50h]
0x14001d276  test    rax, rax
0x14001d279  jz      short loc_14001D283
0x14001d27b  mov     rcx, rbx
0x14001d27e  call    _guard_dispatch_icall
0x14001d283  mov     ecx, [rbx+58h]
0x14001d286  sub     ecx, 1
0x14001d289  jz      short loc_14001D2A5
0x14001d28b  cmp     ecx, 1
0x14001d28e  jnz     short loc_14001D2B9
0x14001d290  mov     rcx, [rbx+60h]; Lookaside
0x14001d294  mov     rdx, rbx; Entry
0x14001d297  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001d29e  nop     dword ptr [rax+rax+00h]
0x14001d2a3  jmp     short loc_14001D2B9
0x14001d2a5  mov     edx, 69706E56h; Tag
0x14001d2aa  mov     rcx, rbx; P
0x14001d2ad  call    cs:__imp_ExFreePoolWithTag
0x14001d2b4  nop     dword ptr [rax+rax+00h]
0x14001d2b9  lea     rcx, [rdi+10h]; FastMutex
0x14001d2bd  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001d2c4  nop     dword ptr [rax+rax+00h]
0x14001d2c9  call    cs:__imp_KeLeaveCriticalRegion
0x14001d2d0  nop     dword ptr [rax+rax+00h]
0x14001d2d5  mov     eax, esi
0x14001d2d7  mov     rcx, [rbp+var_8]
0x14001d2db  xor     rcx, rsp; StackCookie
0x14001d2de  call    __security_check_cookie
0x14001d2e3  lea     r11, [rsp+70h+var_s0]
0x14001d2e8  mov     rbx, [r11+30h]
0x14001d2ec  mov     rsi, [r11+40h]
0x14001d2f0  mov     rsp, r11
0x14001d2f3  pop     r15
0x14001d2f5  pop     r14
0x14001d2f7  pop     r12
0x14001d2f9  pop     rdi
0x14001d2fa  pop     rbp
0x14001d2fb  retn
```
