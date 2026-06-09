# CClfsAuthContainer::Initialize(unsigned __int64 *,ulong)

- ea: `0x140063844`
- end: `0x140063b7b`
- name: `?Initialize@CClfsAuthContainer@@QEAAJPEA_KK@Z`
- size: `823`
- prototype: `__int64 __fastcall(CClfsAuthContainer *__hidden this, unsigned __int64 *, unsigned int)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1400374cc`
- `0x14005ed70`
- `0x140062ef8`
- `0x1400632d4`

## callees

- `0x140007470`
- `0x14000f7bc`
- `0x14001009c`
- `0x140012a68`
- `0x140017f20`
- `0x140033a78`
- `0x140063844`
- `0x140075dcc`
- `0x140076384`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140063aa5`
- `ntoskrnl!ObfDereferenceObject` at `0x140063abe`
- `ntoskrnl!ObfDereferenceObject` at `0x14007aa25`
- `ntoskrnl!ObfDereferenceObject` at `0x14007aa44`
- `ntoskrnl!ObfDereferenceObject` at `0x140063aa5`
- `ntoskrnl!ObfDereferenceObject` at `0x140063abe`
- `ntoskrnl!ObfDereferenceObject` at `0x14007aa25`
- `ntoskrnl!ObfDereferenceObject` at `0x14007aa44`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006386f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140063992`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006386f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140063992`
- `ntoskrnl!KeClearEvent` at `0x1400638db`
- `ntoskrnl!KeClearEvent` at `0x140063902`
- `ntoskrnl!KeClearEvent` at `0x1400638db`
- `ntoskrnl!KeClearEvent` at `0x140063902`
- `ntoskrnl!KeInitializeEvent` at `0x140063953`
- `ntoskrnl!KeInitializeEvent` at `0x140063953`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063ad9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063b16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063b37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007aa65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007aabb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007aae5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063ad9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063b16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063b37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007aa65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007aabb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007aae5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140063921`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400639fe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140063921`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400639fe`

## pseudocode

```c
__int64 __fastcall CClfsAuthContainer::Initialize(CClfsAuthContainer *this, unsigned __int64 *a2, unsigned int a3)
{
  unsigned __int64 v3; // r12
  CClfsContainer *v6; // rax
  unsigned int v7; // edx
  CClfsContainer *v8; // rcx
  int EventObject; // edi
  enum _EVENT_TYPE v10; // ecx
  enum _EVENT_TYPE v11; // ecx
  struct _KEVENT *PoolWithTag; // rax
  enum _POOL_TYPE v13; // edx
  unsigned int v14; // r8d
  void *PageAlignedMemory; // rax
  __int64 v16; // rcx
  CClfsContainer *v17; // rax
  CClfsContainer *v18; // rcx
  SIZE_T v19; // rax
  PVOID v20; // rax
  unsigned int i; // r8d
  CClfsMerkleTree *v22; // rax
  CClfsMerkleTree *v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  __int64 v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx

  v3 = a3;
  v6 = (CClfsContainer *)ExAllocateFromPagedLookasideList(&CClfsContainer::m_laList);
  if ( v6 )
    v8 = CClfsContainer::CClfsContainer(v6, *((_DWORD *)this + 11), *((_DWORD *)this + 34) <= 1u);
  else
    v8 = 0;
  *((_QWORD *)this + 15) = v8;
  if ( !v8 )
    goto LABEL_5;
  (**(void (__fastcall ***)(CClfsContainer *))v8)(v8);
  EventObject = ClfsCreateEventObject(v10, (struct _KEVENT **)this + 3);
  if ( EventObject >= 0 )
  {
    KeClearEvent(*((PRKEVENT *)this + 3));
    EventObject = ClfsCreateEventObject(v11, (struct _KEVENT **)this + 4);
    if ( EventObject >= 0 )
    {
      KeClearEvent(*((PRKEVENT *)this + 4));
      PoolWithTag = (struct _KEVENT *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x38u, 0x73666C43u);
      *((_QWORD *)this + 14) = PoolWithTag;
      if ( !PoolWithTag
        || (PoolWithTag->Header.LockNV = 1,
            PoolWithTag->Header.WaitListHead.Flink = 0,
            LODWORD(PoolWithTag->Header.WaitListHead.Blink) = 0,
            KeInitializeEvent(PoolWithTag + 1, SynchronizationEvent, 0),
            PageAlignedMemory = AllocatePageAlignedMemory(0x1000u, v13, v14),
            (*((_QWORD *)this + 18) = PageAlignedMemory) == 0) )
      {
LABEL_5:
        EventObject = -1073741670;
        goto LABEL_30;
      }
      if ( !(unsigned int)Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline(v16)
        && *((_DWORD *)this + 34) <= 1u )
      {
        v17 = (CClfsContainer *)ExAllocateFromPagedLookasideList(&CClfsContainer::m_laList);
        if ( v17 )
          v18 = CClfsContainer::CClfsContainer(v17, *((_DWORD *)this + 11), 1u);
        else
          v18 = 0;
        *((_QWORD *)this + 16) = v18;
        if ( !v18 )
          goto LABEL_5;
        (**(void (__fastcall ***)(CClfsContainer *))v18)(v18);
      }
      if ( a2 )
      {
        *((_DWORD *)this + 48) = v3;
        v19 = 8 * v3;
        if ( !is_mul_ok(v3, 8u) )
          v19 = -1;
        v20 = ExAllocatePoolWithTag(PagedPool, v19, 0x73666C43u);
        *((_QWORD *)this + 23) = v20;
        if ( !v20 )
          goto LABEL_5;
        for ( i = 0; i < *((_DWORD *)this + 48); ++i )
          *(_QWORD *)(*((_QWORD *)this + 23) + 8LL * i) = a2[i];
      }
      v22 = (CClfsMerkleTree *)CClfsMerkleTree::MemAlloc();
      if ( v22 )
        v23 = CClfsMerkleTree::CClfsMerkleTree(v22);
      else
        v23 = 0;
      *((_QWORD *)this + 19) = v23;
      v24 = EventObject;
      if ( !v23 )
        v24 = -1073741670;
      EventObject = v24;
    }
  }
LABEL_30:
  if ( EventObject < 0 )
  {
    v25 = *((_QWORD *)this + 15);
    if ( v25 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
      *((_QWORD *)this + 15) = 0;
    }
    v26 = (void *)*((_QWORD *)this + 3);
    if ( v26 )
    {
      ObfDereferenceObject(v26);
      *((_QWORD *)this + 3) = 0;
    }
    v27 = (void *)*((_QWORD *)this + 4);
    if ( v27 )
    {
      ObfDereferenceObject(v27);
      *((_QWORD *)this + 4) = 0;
    }
    v28 = (void *)*((_QWORD *)this + 14);
    if ( v28 )
    {
      ExFreePoolWithTag(v28, 0);
      *((_QWORD *)this + 14) = 0;
    }
    v29 = *((_QWORD *)this + 16);
    if ( v29 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
      *((_QWORD *)this + 16) = 0;
    }
    v30 = (void *)*((_QWORD *)this + 18);
    if ( v30 )
    {
      ExFreePoolWithTag(v30, 0);
      *((_QWORD *)this + 18) = 0;
    }
    v31 = (void *)*((_QWORD *)this + 23);
    if ( v31 )
    {
      ExFreePoolWithTag(v31, 0);
      *((_QWORD *)this + 23) = 0;
    }
    *((_DWORD *)this + 48) = 0;
    v32 = (void *)*((_QWORD *)this + 19);
    if ( v32 )
    {
      CClfsMerkleTree::`scalar deleting destructor'(v32, v7);
      *((_QWORD *)this + 19) = 0;
    }
  }
  return (unsigned int)EventObject;
}

```

## disassembly

```asm
0x140063844  mov     [rsp+arg_0], rcx
0x140063849  push    rbx
0x14006384a  push    rdi
0x14006384b  push    r12
0x14006384d  push    r13
0x14006384f  push    r14
0x140063851  push    r15
0x140063853  sub     rsp, 38h
0x140063857  mov     r12d, r8d
0x14006385a  mov     r15, rdx
0x14006385d  mov     rbx, rcx
0x140063860  xor     r13d, r13d
0x140063863  mov     [rsp+68h+var_48], r13d
0x140063868  lea     rcx, ?m_laList@CClfsContainer@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14006386f  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140063876  nop     dword ptr [rax+rax+00h]
0x14006387b  test    rax, rax
0x14006387e  jz      short loc_14006389B
0x140063880  cmp     dword ptr [rbx+88h], 1
0x140063887  setbe   r8b; unsigned __int8
0x14006388b  mov     edx, [rbx+2Ch]; unsigned int
0x14006388e  mov     rcx, rax; this
0x140063891  call    ??0CClfsContainer@@QEAA@KE@Z; CClfsContainer::CClfsContainer(ulong,uchar)
0x140063896  mov     rcx, rax
0x140063899  jmp     short loc_14006389E
0x14006389b  mov     rcx, r13
0x14006389e  mov     [rbx+78h], rcx
0x1400638a2  test    rcx, rcx
0x1400638a5  jnz     short loc_1400638B5
0x1400638a7  mov     edi, 0C000009Ah
0x1400638ac  mov     [rsp+68h+var_48], edi
0x1400638b0  jmp     loc_140063A7B
0x1400638b5  mov     rax, [rcx]
0x1400638b8  mov     rax, [rax]
0x1400638bb  call    _guard_dispatch_icall
0x1400638c0  lea     rdx, [rbx+18h]; struct _KEVENT **
0x1400638c4  call    ?ClfsCreateEventObject@@YAJW4_EVENT_TYPE@@AEAPEAU_KEVENT@@@Z; ClfsCreateEventObject(_EVENT_TYPE,_KEVENT * &)
0x1400638c9  mov     edi, eax
0x1400638cb  mov     [rsp+68h+var_48], eax
0x1400638cf  test    eax, eax
0x1400638d1  js      loc_140063A7B
0x1400638d7  mov     rcx, [rbx+18h]; Event
0x1400638db  call    cs:__imp_KeClearEvent
0x1400638e2  nop     dword ptr [rax+rax+00h]
0x1400638e7  lea     rdx, [rbx+20h]; struct _KEVENT **
0x1400638eb  call    ?ClfsCreateEventObject@@YAJW4_EVENT_TYPE@@AEAPEAU_KEVENT@@@Z; ClfsCreateEventObject(_EVENT_TYPE,_KEVENT * &)
0x1400638f0  mov     edi, eax
0x1400638f2  mov     [rsp+68h+var_48], eax
0x1400638f6  test    eax, eax
0x1400638f8  js      loc_140063A7B
0x1400638fe  mov     rcx, [rbx+20h]; Event
0x140063902  call    cs:__imp_KeClearEvent
0x140063909  nop     dword ptr [rax+rax+00h]
0x14006390e  mov     r14d, 73666C43h
0x140063914  mov     r8d, r14d; Tag
0x140063917  mov     edx, 38h ; '8'; NumberOfBytes
0x14006391c  mov     ecx, 200h; PoolType
0x140063921  call    cs:__imp_ExAllocatePoolWithTag
0x140063928  nop     dword ptr [rax+rax+00h]
0x14006392d  mov     [rbx+70h], rax
0x140063931  test    rax, rax
0x140063934  jz      loc_1400638A7
0x14006393a  mov     dword ptr [rax], 1
0x140063940  mov     [rax+8], r13
0x140063944  mov     [rax+10h], r13d
0x140063948  lea     rcx, [rax+18h]; Event
0x14006394c  xor     r8d, r8d; State
0x14006394f  lea     edx, [r8+1]; Type
0x140063953  call    cs:__imp_KeInitializeEvent
0x14006395a  nop     dword ptr [rax+rax+00h]
0x14006395f  mov     ecx, 1000h; NumberOfBytes
0x140063964  call    ?AllocatePageAlignedMemory@@YAPEAX_KW4_POOL_TYPE@@K@Z; AllocatePageAlignedMemory(unsigned __int64,_POOL_TYPE,ulong)
0x140063969  mov     [rbx+90h], rax
0x140063970  test    rax, rax
0x140063973  jz      loc_1400638A7
0x140063979  call    Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline
0x14006397e  test    eax, eax
0x140063980  jnz     short loc_1400639D4
0x140063982  cmp     dword ptr [rbx+88h], 1
0x140063989  ja      short loc_1400639D4
0x14006398b  lea     rcx, ?m_laList@CClfsContainer@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140063992  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140063999  nop     dword ptr [rax+rax+00h]
0x14006399e  test    rax, rax
0x1400639a1  jz      short loc_1400639B6
0x1400639a3  mov     r8b, 1; unsigned __int8
0x1400639a6  mov     edx, [rbx+2Ch]; unsigned int
0x1400639a9  mov     rcx, rax; this
0x1400639ac  call    ??0CClfsContainer@@QEAA@KE@Z; CClfsContainer::CClfsContainer(ulong,uchar)
0x1400639b1  mov     rcx, rax
0x1400639b4  jmp     short loc_1400639B9
0x1400639b6  mov     rcx, r13
0x1400639b9  mov     [rbx+80h], rcx
0x1400639c0  test    rcx, rcx
0x1400639c3  jz      loc_1400638A7
0x1400639c9  mov     rax, [rcx]
0x1400639cc  mov     rax, [rax]
0x1400639cf  call    _guard_dispatch_icall
0x1400639d4  test    r15, r15
0x1400639d7  jz      short loc_140063A47
0x1400639d9  mov     [rbx+0C0h], r12d
0x1400639e0  mov     eax, 8
0x1400639e5  mul     r12
0x1400639e8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400639ef  cmovb   rax, rcx
0x1400639f3  mov     r8d, r14d; Tag
0x1400639f6  mov     rdx, rax; NumberOfBytes
0x1400639f9  mov     ecx, 1; PoolType
0x1400639fe  call    cs:__imp_ExAllocatePoolWithTag
0x140063a05  nop     dword ptr [rax+rax+00h]
0x140063a0a  mov     [rbx+0B8h], rax
0x140063a11  test    rax, rax
0x140063a14  jz      loc_1400638A7
0x140063a1a  mov     r8d, r13d
0x140063a1d  mov     [rsp+68h+var_44], r13d
0x140063a22  cmp     r8d, [rbx+0C0h]
0x140063a29  jnb     short loc_140063A47
0x140063a2b  mov     edx, r8d
0x140063a2e  mov     rcx, [rbx+0B8h]
0x140063a35  mov     rax, [r15+rdx*8]
0x140063a39  mov     [rcx+rdx*8], rax
0x140063a3d  inc     r8d
0x140063a40  mov     [rsp+68h+var_44], r8d
0x140063a45  jmp     short loc_140063A22
0x140063a47  call    ?MemAlloc@CClfsMerkleTree@@CAPEAXXZ; CClfsMerkleTree::MemAlloc(void)
0x140063a4c  test    rax, rax
0x140063a4f  jz      short loc_140063A5E
0x140063a51  mov     rcx, rax; this
0x140063a54  call    ??0CClfsMerkleTree@@QEAA@XZ; CClfsMerkleTree::CClfsMerkleTree(void)
0x140063a59  mov     rcx, rax
0x140063a5c  jmp     short loc_140063A61
0x140063a5e  mov     rcx, r13
0x140063a61  mov     [rbx+98h], rcx
0x140063a68  mov     eax, edi
0x140063a6a  mov     edi, 0C000009Ah
0x140063a6f  test    rcx, rcx
0x140063a72  cmovz   eax, edi
0x140063a75  mov     edi, eax
0x140063a77  mov     [rsp+68h+var_48], eax
0x140063a7b  test    edi, edi
0x140063a7d  jns     loc_140063B69
0x140063a83  mov     rcx, [rbx+78h]
0x140063a87  test    rcx, rcx
0x140063a8a  jz      short loc_140063A9C
0x140063a8c  mov     rax, [rcx]
0x140063a8f  mov     rax, [rax+8]
0x140063a93  call    _guard_dispatch_icall
0x140063a98  mov     [rbx+78h], r13
0x140063a9c  mov     rcx, [rbx+18h]; Object
0x140063aa0  test    rcx, rcx
0x140063aa3  jz      short loc_140063AB5
0x140063aa5  call    cs:__imp_ObfDereferenceObject
0x140063aac  nop     dword ptr [rax+rax+00h]
0x140063ab1  mov     [rbx+18h], r13
0x140063ab5  mov     rcx, [rbx+20h]; Object
0x140063ab9  test    rcx, rcx
0x140063abc  jz      short loc_140063ACE
0x140063abe  call    cs:__imp_ObfDereferenceObject
0x140063ac5  nop     dword ptr [rax+rax+00h]
0x140063aca  mov     [rbx+20h], r13
0x140063ace  mov     rcx, [rbx+70h]; P
0x140063ad2  test    rcx, rcx
0x140063ad5  jz      short loc_140063AE9
0x140063ad7  xor     edx, edx; Tag
0x140063ad9  call    cs:__imp_ExFreePoolWithTag
0x140063ae0  nop     dword ptr [rax+rax+00h]
0x140063ae5  mov     [rbx+70h], r13
0x140063ae9  mov     rcx, [rbx+80h]
0x140063af0  test    rcx, rcx
0x140063af3  jz      short loc_140063B08
0x140063af5  mov     rax, [rcx]
0x140063af8  mov     rax, [rax+8]
0x140063afc  call    _guard_dispatch_icall
0x140063b01  mov     [rbx+80h], r13
0x140063b08  mov     rcx, [rbx+90h]; P
0x140063b0f  test    rcx, rcx
0x140063b12  jz      short loc_140063B29
0x140063b14  xor     edx, edx; Tag
0x140063b16  call    cs:__imp_ExFreePoolWithTag
0x140063b1d  nop     dword ptr [rax+rax+00h]
0x140063b22  mov     [rbx+90h], r13
0x140063b29  mov     rcx, [rbx+0B8h]; P
0x140063b30  test    rcx, rcx
0x140063b33  jz      short loc_140063B4A
0x140063b35  xor     edx, edx; Tag
0x140063b37  call    cs:__imp_ExFreePoolWithTag
0x140063b3e  nop     dword ptr [rax+rax+00h]
0x140063b43  mov     [rbx+0B8h], r13
0x140063b4a  mov     [rbx+0C0h], r13d
0x140063b51  mov     rcx, [rbx+98h]; Entry
0x140063b58  test    rcx, rcx
0x140063b5b  jz      short loc_140063B69
0x140063b5d  call    ??_GCClfsMerkleTree@@QEAAPEAXI@Z; CClfsMerkleTree::`scalar deleting destructor'(uint)
0x140063b62  mov     [rbx+98h], r13
0x140063b69  mov     eax, edi
0x140063b6b  add     rsp, 38h
0x140063b6f  pop     r15
0x140063b71  pop     r14
0x140063b73  pop     r13
0x140063b75  pop     r12
0x140063b77  pop     rdi
0x140063b78  pop     rbx
0x140063b79  retn
0x14007a9df  push    rbx
0x14007a9e1  push    rbp
0x14007a9e2  sub     rsp, 28h
0x14007a9e6  mov     rbp, rdx
0x14007a9e9  cmp     dword ptr [rbp+20h], 0
0x14007a9ed  jge     loc_14007AB2D
0x14007a9f3  mov     rbx, [rbp+70h]
0x14007a9f7  cmp     qword ptr [rbx+78h], 0
0x14007a9fc  jz      short loc_14007AA1A
0x14007a9fe  mov     rax, [rbx+78h]
0x14007aa02  mov     rcx, [rax]
0x14007aa05  mov     rax, [rcx+8]
0x14007aa09  mov     rcx, [rbx+78h]
0x14007aa0d  call    _guard_dispatch_icall
0x14007aa12  mov     qword ptr [rbx+78h], 0
0x14007aa1a  cmp     qword ptr [rbx+18h], 0
0x14007aa1f  jz      short loc_14007AA39
0x14007aa21  mov     rcx, [rbx+18h]; Object
0x14007aa25  call    cs:__imp_ObfDereferenceObject
0x14007aa2c  nop     dword ptr [rax+rax+00h]
0x14007aa31  mov     qword ptr [rbx+18h], 0
0x14007aa39  cmp     qword ptr [rbx+20h], 0
0x14007aa3e  jz      short loc_14007AA58
0x14007aa40  mov     rcx, [rbx+20h]; Object
0x14007aa44  call    cs:__imp_ObfDereferenceObject
0x14007aa4b  nop     dword ptr [rax+rax+00h]
0x14007aa50  mov     qword ptr [rbx+20h], 0
0x14007aa58  cmp     qword ptr [rbx+70h], 0
0x14007aa5d  jz      short loc_14007AA79
0x14007aa5f  xor     edx, edx; Tag
0x14007aa61  mov     rcx, [rbx+70h]; P
0x14007aa65  call    cs:__imp_ExFreePoolWithTag
0x14007aa6c  nop     dword ptr [rax+rax+00h]
0x14007aa71  mov     qword ptr [rbx+70h], 0
0x14007aa79  cmp     qword ptr [rbx+80h], 0
0x14007aa81  jz      short loc_14007AAA8
0x14007aa83  mov     rax, [rbx+80h]
0x14007aa8a  mov     rcx, [rax]
0x14007aa8d  mov     rax, [rcx+8]
0x14007aa91  mov     rcx, [rbx+80h]
0x14007aa98  call    _guard_dispatch_icall
0x14007aa9d  mov     qword ptr [rbx+80h], 0
0x14007aaa8  cmp     qword ptr [rbx+90h], 0
0x14007aab0  jz      short loc_14007AAD2
0x14007aab2  xor     edx, edx; Tag
0x14007aab4  mov     rcx, [rbx+90h]; P
0x14007aabb  call    cs:__imp_ExFreePoolWithTag
0x14007aac2  nop     dword ptr [rax+rax+00h]
0x14007aac7  mov     qword ptr [rbx+90h], 0
0x14007aad2  cmp     qword ptr [rbx+0B8h], 0
0x14007aada  jz      short loc_14007AAFC
0x14007aadc  xor     edx, edx; Tag
0x14007aade  mov     rcx, [rbx+0B8h]; P
0x14007aae5  call    cs:__imp_ExFreePoolWithTag
0x14007aaec  nop     dword ptr [rax+rax+00h]
0x14007aaf1  mov     qword ptr [rbx+0B8h], 0
0x14007aafc  mov     dword ptr [rbx+0C0h], 0
0x14007ab06  cmp     qword ptr [rbx+98h], 0
0x14007ab0e  jz      short loc_14007AB2D
0x14007ab10  mov     rcx, [rbx+98h]; Entry
0x14007ab17  test    rcx, rcx
0x14007ab1a  jz      short loc_14007AB22
0x14007ab1c  call    ??_GCClfsMerkleTree@@QEAAPEAXI@Z; CClfsMerkleTree::`scalar deleting destructor'(uint)
0x14007ab21  nop
0x14007ab22  mov     qword ptr [rbx+98h], 0
0x14007ab2d  add     rsp, 28h
0x14007ab31  pop     rbp
0x14007ab32  pop     rbx
0x14007ab33  retn
```
