# VmbusTlCreateEndpoint

- ea: `0x140019b70`
- end: `0x140019fb5`
- name: `VmbusTlCreateEndpoint`
- size: `1093`
- prototype: `__int64 __fastcall(__int64, struct _KPROCESS *, unsigned int, _QWORD *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400193ec`
- `0x14001b74c`
- `0x1400213d0`

## callees

- `0x140001418`
- `0x14000975c`
- `0x140009c38`
- `0x140009cf8`
- `0x14000a048`
- `0x14000a2c8`
- `0x14000bfe0`
- `0x140019b70`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140019d2a`
- `ntoskrnl!ExAllocatePool2` at `0x140019d2a`
- `ntoskrnl!PsReturnPoolQuota` at `0x140019cc5`
- `ntoskrnl!PsReturnPoolQuota` at `0x140019cc5`
- `ntoskrnl!ObfDereferenceObject` at `0x140019cd4`
- `ntoskrnl!ObfDereferenceObject` at `0x140019cd4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019dc2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019dc2`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140019bf1`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140019bf1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140019db6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140019db6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019e12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019ebe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019e12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019ebe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019d60`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019d60`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019ea5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019ea5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140019d70`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140019d70`
- `ntoskrnl!PsGetProcessId` at `0x140019c15`
- `ntoskrnl!PsGetProcessId` at `0x140019c15`
- `ntoskrnl!ObfReferenceObject` at `0x140019c40`
- `ntoskrnl!ObfReferenceObject` at `0x140019c40`
- `NETIO!NetioInitializeWorkQueue` at `0x140019d9d`
- `NETIO!NetioInitializeWorkQueue` at `0x140019d9d`

## string_xrefs

- `0x140019c24`: `VmbusTlCreateEndpoint`
- `0x140019ca5`: `VmbusTlCreateEndpoint`
- `0x140019de9`: `VmbusTlCreateEndpoint`
- `0x140019e4c`: `VmbusTlCreateEndpoint`
- `0x140019f03`: `VmbusTlCreateEndpoint`
- `0x140019c96`: `Cannot create endpoint.`
- `0x140019f90`: `Endpoint created.`

## pseudocode

```c
__int64 __fastcall VmbusTlCreateEndpoint(__int64 a1, struct _KPROCESS *a2, unsigned int a3, _QWORD *a4)
{
  __int64 v8; // rbx
  ULONG_PTR v9; // rbp
  NTSTATUS v10; // esi
  HANDLE ProcessId; // rax
  int v12; // eax
  char *v13; // rbx
  __int64 Pool2; // rax
  __int64 v15; // rdx
  __int64 v16; // r9
  void *v17; // rcx
  signed __int64 v18; // rax
  bool v19; // cc
  signed __int64 v20; // rax
  void (__fastcall *v21)(char *); // rax
  unsigned int v22; // eax
  PVOID Entry; // [rsp+88h] [rbp+10h] BYREF

  Entry = 0;
  switch ( a3 )
  {
    case 1u:
      v8 = a1 + 320;
      v9 = 336;
      break;
    case 2u:
      v8 = a1 + 448;
      v9 = 1136;
      break;
    case 3u:
      v8 = a1 + 576;
      v9 = 432;
      break;
    default:
      v8 = 0;
      v9 = 0;
      break;
  }
  if ( a2 )
  {
    v10 = PsChargeProcessPoolQuota(a2, (POOL_TYPE)512, v9);
    if ( v10 < 0 )
    {
      if ( (unsigned int)dword_140013058 > 2 )
      {
        ProcessId = PsGetProcessId(a2);
        HvsocketTraceULongError("VmbusTlCreateEndpoint", 350, (unsigned int)v10, ProcessId);
      }
      return (unsigned int)v10;
    }
    ObfReferenceObject(a2);
    _InterlockedAdd64((volatile signed __int64 *)VmbusProviderContext + 161, v9);
    _InterlockedAdd64((volatile signed __int64 *)VmbusProviderContext + 162, 1u);
  }
  v12 = VmbusTlCreateObjectFromLookasideList(1, v8, &Entry);
  v13 = (char *)Entry;
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceError("VmbusTlCreateEndpoint", 368, (unsigned int)v12, "Cannot create endpoint.");
    if ( a2 )
    {
      PsReturnPoolQuota(a2, (POOL_TYPE)512, v9);
      ObfDereferenceObject(a2);
      _InterlockedAdd64((volatile signed __int64 *)VmbusProviderContext + 161, -(__int64)v9);
      _InterlockedDecrement64((volatile signed __int64 *)VmbusProviderContext + 162);
    }
    goto LABEL_28;
  }
  *((_DWORD *)Entry + 26) = a3;
  *((_QWORD *)v13 + 34) = a2;
  *((_QWORD *)v13 + 10) = VmbusTlEndpointDestructor;
  Pool2 = ExAllocatePool2(64, 56, 1768975958);
  *((_QWORD *)v13 + 24) = Pool2;
  if ( !Pool2 )
  {
    v10 = -1073741801;
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_28;
    v15 = 398;
    goto LABEL_27;
  }
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  v16 = *(_QWORD *)(a1 + 176);
  if ( v16 )
    v10 = NetioInitializeWorkQueue(*((_QWORD *)v13 + 24) + 8LL, VmbusTlEndpointActionWorkQueueRoutine, 0, v16);
  else
    v10 = -1073741436;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_28;
    v15 = 424;
LABEL_27:
    HvsocketTraceEndpointError("VmbusTlCreateEndpoint", v15, (unsigned int)v10, v13);
LABEL_28:
    if ( v13 )
    {
      v17 = (void *)*((_QWORD *)v13 + 24);
      if ( v17 )
      {
        ExFreePoolWithTag(v17, 0x69706E56u);
        *((_QWORD *)v13 + 24) = 0;
      }
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlCreateEndpoint",
          487,
          (_DWORD)v13,
          *((_QWORD *)v13 + 1),
          (__int64)"Dereference object");
      v18 = _InterlockedExchangeAdd64((volatile signed __int64 *)v13 + 1, 0xFFFFFFFFFFFFFFFFuLL);
      v19 = v18 <= 1;
      v20 = v18 - 1;
      if ( v19 )
      {
        if ( v20 )
          __fastfail(0xEu);
        v21 = (void (__fastcall *)(char *))*((_QWORD *)v13 + 10);
        if ( v21 )
          v21(v13);
        if ( *((_DWORD *)v13 + 22) == 1 )
        {
          ExFreePoolWithTag(v13, 0x69706E56u);
        }
        else if ( *((_DWORD *)v13 + 22) == 2 )
        {
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 12), v13);
        }
      }
    }
    return (unsigned int)v10;
  }
  *((_QWORD *)v13 + 39) = MEMORY[0xFFFFF78000000014];
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlCreateEndpoint",
      434,
      a1,
      *(_QWORD *)(a1 + 8),
      (__int64)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 8)) <= 1 )
    __fastfail(0xEu);
  *((_QWORD *)v13 + 14) = a1;
  *((_QWORD *)v13 + 16) = v13 + 120;
  *((_QWORD *)v13 + 15) = v13 + 120;
  _InterlockedAdd((volatile signed __int32 *)(a1 + 1136), 1u);
  switch ( a3 )
  {
    case 1u:
      _InterlockedAdd((volatile signed __int32 *)(a1 + 1140), 1u);
      break;
    case 2u:
      _InterlockedAdd((volatile signed __int32 *)(a1 + 1144), 1u);
      break;
    case 3u:
      _InterlockedAdd((volatile signed __int32 *)(a1 + 1148), 1u);
      break;
  }
  *((_QWORD *)v13 + 38) = 1;
  *((_QWORD *)v13 + 22) = -300000000;
  v22 = dword_140013058;
  *a4 = v13;
  if ( v22 > 4 )
    HvsocketTraceEndpointUlongMessage("Endpoint created.", v13, a3);
  return 0;
}

```

## disassembly

```asm
0x140019b70  mov     rax, rsp
0x140019b73  push    rbx
0x140019b74  push    rbp
0x140019b75  push    rsi
0x140019b76  push    rdi
0x140019b77  push    r12
0x140019b79  push    r13
0x140019b7b  push    r14
0x140019b7d  push    r15
0x140019b7f  sub     rsp, 38h
0x140019b83  mov     rdi, rcx
0x140019b86  mov     qword ptr [rax+10h], 0
0x140019b8e  mov     ecx, r8d
0x140019b91  mov     r12, r9
0x140019b94  mov     r15d, r8d
0x140019b97  mov     r14, rdx
0x140019b9a  sub     ecx, 1
0x140019b9d  jz      short loc_140019BCB
0x140019b9f  sub     ecx, 1
0x140019ba2  jz      short loc_140019BBD
0x140019ba4  cmp     ecx, 1
0x140019ba7  jz      short loc_140019BAF
0x140019ba9  xor     ebx, ebx
0x140019bab  xor     ebp, ebp
0x140019bad  jmp     short loc_140019BD7
0x140019baf  lea     rbx, [rdi+240h]
0x140019bb6  mov     ebp, 1B0h
0x140019bbb  jmp     short loc_140019BD7
0x140019bbd  lea     rbx, [rdi+1C0h]
0x140019bc4  mov     ebp, 470h
0x140019bc9  jmp     short loc_140019BD7
0x140019bcb  lea     rbx, [rdi+140h]
0x140019bd2  mov     ebp, 150h
0x140019bd7  mov     r13d, 1
0x140019bdd  test    r14, r14
0x140019be0  jz      loc_140019C6A
0x140019be6  mov     r8, rbp; Amount
0x140019be9  mov     edx, 200h; PoolType
0x140019bee  mov     rcx, r14; Process
0x140019bf1  call    cs:__imp_PsChargeProcessPoolQuota
0x140019bf8  nop     dword ptr [rax+rax+00h]
0x140019bfd  mov     esi, eax
0x140019bff  test    eax, eax
0x140019c01  jns     short loc_140019C3D
0x140019c03  mov     ecx, cs:dword_140013058
0x140019c09  cmp     ecx, 2
0x140019c0c  jbe     loc_140019FA1
0x140019c12  mov     rcx, r14; Process
0x140019c15  call    cs:__imp_PsGetProcessId
0x140019c1c  nop     dword ptr [rax+rax+00h]
0x140019c21  mov     r8d, esi
0x140019c24  lea     rcx, aVmbustlcreatee; "VmbusTlCreateEndpoint"
0x140019c2b  mov     r9, rax
0x140019c2e  mov     edx, 15Eh
0x140019c33  call    HvsocketTraceULongError
0x140019c38  jmp     loc_140019FA1
0x140019c3d  mov     rcx, r14; Object
0x140019c40  call    cs:__imp_ObfReferenceObject
0x140019c47  nop     dword ptr [rax+rax+00h]
0x140019c4c  mov     rax, cs:VmbusProviderContext
0x140019c53  lock add [rax+508h], rbp
0x140019c5b  mov     rax, cs:VmbusProviderContext
0x140019c62  lock add [rax+510h], r13
0x140019c6a  lea     r8, [rsp+78h+Entry]
0x140019c72  mov     rdx, rbx
0x140019c75  mov     ecx, r13d
0x140019c78  call    VmbusTlCreateObjectFromLookasideList
0x140019c7d  mov     rbx, [rsp+78h+Entry]
0x140019c85  mov     esi, eax
0x140019c87  test    eax, eax
0x140019c89  jns     short loc_140019D06
0x140019c8b  mov     ecx, cs:dword_140013058
0x140019c91  cmp     ecx, 2
0x140019c94  jbe     short loc_140019CB1
0x140019c96  lea     r9, aCannotCreateEn; "Cannot create endpoint."
0x140019c9d  mov     r8d, eax
0x140019ca0  mov     edx, 170h
0x140019ca5  lea     rcx, aVmbustlcreatee; "VmbusTlCreateEndpoint"
0x140019cac  call    HvsocketTraceError
0x140019cb1  test    r14, r14
0x140019cb4  jz      loc_140019DF8
0x140019cba  mov     r8, rbp; Amount
0x140019cbd  mov     edx, 200h; PoolType
0x140019cc2  mov     rcx, r14; Process
0x140019cc5  call    cs:__imp_PsReturnPoolQuota
0x140019ccc  nop     dword ptr [rax+rax+00h]
0x140019cd1  mov     rcx, r14; Object
0x140019cd4  call    cs:__imp_ObfDereferenceObject
0x140019cdb  nop     dword ptr [rax+rax+00h]
0x140019ce0  mov     rax, cs:VmbusProviderContext
0x140019ce7  neg     rbp
0x140019cea  lock add [rax+508h], rbp
0x140019cf2  mov     rax, cs:VmbusProviderContext
0x140019cf9  lock dec qword ptr [rax+510h]
0x140019d01  jmp     loc_140019DF8
0x140019d06  mov     [rbx+68h], r15d
0x140019d0a  lea     rax, VmbusTlEndpointDestructor
0x140019d11  mov     edx, 38h ; '8'
0x140019d16  mov     [rbx+110h], r14
0x140019d1d  mov     r8d, 69706E56h
0x140019d23  mov     [rbx+50h], rax
0x140019d27  lea     ecx, [rdx+8]
0x140019d2a  call    cs:__imp_ExAllocatePool2
0x140019d31  nop     dword ptr [rax+rax+00h]
0x140019d36  mov     [rbx+0C0h], rax
0x140019d3d  test    rax, rax
0x140019d40  jnz     short loc_140019D60
0x140019d42  mov     eax, cs:dword_140013058
0x140019d48  mov     esi, 0C0000017h
0x140019d4d  cmp     eax, 2
0x140019d50  jbe     loc_140019DF8
0x140019d56  mov     edx, 18Eh
0x140019d5b  jmp     loc_140019DE6
0x140019d60  call    cs:__imp_KeEnterCriticalRegion
0x140019d67  nop     dword ptr [rax+rax+00h]
0x140019d6c  lea     rcx, [rdi+10h]; FastMutex
0x140019d70  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140019d77  nop     dword ptr [rax+rax+00h]
0x140019d7c  mov     r9, [rdi+0B0h]
0x140019d83  test    r9, r9
0x140019d86  jz      short loc_140019DAD
0x140019d88  mov     rcx, [rbx+0C0h]
0x140019d8f  lea     rdx, VmbusTlEndpointActionWorkQueueRoutine
0x140019d96  add     rcx, 8
0x140019d9a  xor     r8d, r8d
0x140019d9d  call    cs:__imp_NetioInitializeWorkQueue
0x140019da4  nop     dword ptr [rax+rax+00h]
0x140019da9  mov     esi, eax
0x140019dab  jmp     short loc_140019DB2
0x140019dad  mov     esi, 0C0000184h
0x140019db2  lea     rcx, [rdi+10h]; FastMutex
0x140019db6  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140019dbd  nop     dword ptr [rax+rax+00h]
0x140019dc2  call    cs:__imp_KeLeaveCriticalRegion
0x140019dc9  nop     dword ptr [rax+rax+00h]
0x140019dce  test    esi, esi
0x140019dd0  jns     loc_140019ECF
0x140019dd6  mov     eax, cs:dword_140013058
0x140019ddc  cmp     eax, 2
0x140019ddf  jbe     short loc_140019DF8
0x140019de1  mov     edx, 1A8h
0x140019de6  mov     r9, rbx
0x140019de9  lea     rcx, aVmbustlcreatee; "VmbusTlCreateEndpoint"
0x140019df0  mov     r8d, esi
0x140019df3  call    HvsocketTraceEndpointError
0x140019df8  test    rbx, rbx
0x140019dfb  jz      loc_140019FA1
0x140019e01  mov     rcx, [rbx+0C0h]; P
0x140019e08  test    rcx, rcx
0x140019e0b  jz      short loc_140019E29
0x140019e0d  mov     edx, 69706E56h; Tag
0x140019e12  call    cs:__imp_ExFreePoolWithTag
0x140019e19  nop     dword ptr [rax+rax+00h]
0x140019e1e  mov     qword ptr [rbx+0C0h], 0
0x140019e29  mov     eax, cs:dword_140013058
0x140019e2f  cmp     eax, 5
0x140019e32  jbe     short loc_140019E58
0x140019e34  mov     r9, [rbx+8]
0x140019e38  lea     rax, aDereferenceObj; "Dereference object"
0x140019e3f  mov     r8, rbx
0x140019e42  mov     [rsp+78h+var_58], rax
0x140019e47  mov     edx, 1E7h
0x140019e4c  lea     rcx, aVmbustlcreatee; "VmbusTlCreateEndpoint"
0x140019e53  call    HvsocketTraceReferenceCount
0x140019e58  or      rax, 0FFFFFFFFFFFFFFFFh
0x140019e5c  lock xadd [rbx+8], rax
0x140019e62  sub     rax, r13
0x140019e65  jg      loc_140019FA1
0x140019e6b  test    rax, rax
0x140019e6e  jz      short loc_140019E7C
0x140019e70  mov     ecx, 0Eh
0x140019e75  int     29h; Win8: RtlFailFast(ecx)
0x140019e77  jmp     loc_140019FA1
0x140019e7c  mov     rax, [rbx+50h]
0x140019e80  test    rax, rax
0x140019e83  jz      short loc_140019E8D
0x140019e85  mov     rcx, rbx
0x140019e88  call    _guard_dispatch_icall
0x140019e8d  mov     ecx, [rbx+58h]
0x140019e90  sub     ecx, r13d
0x140019e93  jz      short loc_140019EB6
0x140019e95  cmp     ecx, r13d
0x140019e98  jnz     loc_140019FA1
0x140019e9e  mov     rcx, [rbx+60h]; Lookaside
0x140019ea2  mov     rdx, rbx; Entry
0x140019ea5  call    cs:__imp_ExFreeToNPagedLookasideList
0x140019eac  nop     dword ptr [rax+rax+00h]
0x140019eb1  jmp     loc_140019FA1
0x140019eb6  mov     edx, 69706E56h; Tag
0x140019ebb  mov     rcx, rbx; P
0x140019ebe  call    cs:__imp_ExFreePoolWithTag
0x140019ec5  nop     dword ptr [rax+rax+00h]
0x140019eca  jmp     loc_140019FA1
0x140019ecf  mov     rax, ds:0FFFFF78000000014h
0x140019ed9  mov     [rbx+138h], rax
0x140019ee0  mov     eax, cs:dword_140013058
0x140019ee6  cmp     eax, 5
0x140019ee9  jbe     short loc_140019F0F
0x140019eeb  mov     r9, [rdi+8]
0x140019eef  lea     rax, aReferenceObjec; "Reference object"
0x140019ef6  mov     r8, rdi
0x140019ef9  mov     [rsp+78h+var_58], rax
0x140019efe  mov     edx, 1B2h
0x140019f03  lea     rcx, aVmbustlcreatee; "VmbusTlCreateEndpoint"
0x140019f0a  call    HvsocketTraceReferenceCount
0x140019f0f  mov     rax, r13
0x140019f12  lock xadd [rdi+8], rax
0x140019f18  add     rax, r13
0x140019f1b  cmp     rax, r13
0x140019f1e  jg      short loc_140019F27
0x140019f20  mov     ecx, 0Eh
0x140019f25  int     29h; Win8: RtlFailFast(ecx)
0x140019f27  lea     rax, [rbx+78h]
0x140019f2b  mov     [rbx+70h], rdi
0x140019f2f  mov     [rax+8], rax
0x140019f33  mov     [rax], rax
0x140019f36  lock add [rdi+470h], r13d
0x140019f3e  mov     ecx, r15d
0x140019f41  sub     ecx, r13d
0x140019f44  jz      short loc_140019F64
0x140019f46  sub     ecx, r13d
0x140019f49  jz      short loc_140019F5A
0x140019f4b  cmp     ecx, r13d
0x140019f4e  jnz     short loc_140019F6C
0x140019f50  lock add [rdi+47Ch], r13d
0x140019f58  jmp     short loc_140019F6C
0x140019f5a  lock add [rdi+478h], r13d
0x140019f62  jmp     short loc_140019F6C
0x140019f64  lock add [rdi+474h], r13d
0x140019f6c  mov     [rbx+130h], r13
0x140019f73  mov     qword ptr [rbx+0B0h], 0FFFFFFFFEE1E5D00h
0x140019f7e  mov     eax, cs:dword_140013058
0x140019f84  mov     [r12], rbx
0x140019f88  cmp     eax, 4
0x140019f8b  jbe     short loc_140019F9F
0x140019f8d  mov     r8d, r15d
0x140019f90  lea     rcx, aEndpointCreate; "Endpoint created."
0x140019f97  mov     rdx, rbx
0x140019f9a  call    HvsocketTraceEndpointUlongMessage
0x140019f9f  xor     esi, esi
0x140019fa1  mov     eax, esi
0x140019fa3  add     rsp, 38h
0x140019fa7  pop     r15
0x140019fa9  pop     r14
0x140019fab  pop     r13
0x140019fad  pop     r12
0x140019faf  pop     rdi
0x140019fb0  pop     rsi
0x140019fb1  pop     rbp
0x140019fb2  pop     rbx
0x140019fb3  retn
```
