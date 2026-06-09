# NdisAllocateNetBufferMdlAndData

- ea: `0x1400304b0`
- end: `0x14003084c`
- name: `NdisAllocateNetBufferMdlAndData`
- size: `924`
- prototype: `PNET_BUFFER __stdcall(NDIS_HANDLE PoolHandle)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1400304b0`
- `0x140032510`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140030662`
- `ntoskrnl!DbgPrint` at `0x140030662`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400306c2`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400306c2`
- `ntoskrnl!ExAllocatePool2` at `0x14003079b`
- `ntoskrnl!ExAllocatePool2` at `0x14003079b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400305ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030729`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030807`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400305ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030729`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030807`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030534`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400306f2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400307c8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030534`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400306f2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400307c8`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003058d`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003058d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400305c7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003073c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140030766`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400305c7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003073c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140030766`
- `ntoskrnl!ExQueryDepthSList` at `0x140030826`
- `ntoskrnl!ExQueryDepthSList` at `0x140030826`

## pseudocode

```c
PNET_BUFFER __stdcall NdisAllocateNetBufferMdlAndData(NDIS_HANDLE PoolHandle)
{
  PSLIST_ENTRY v2; // rbx
  unsigned int Number; // r15d
  int v4; // r12d
  unsigned __int64 v5; // rbx
  char *v6; // rsi
  KIRQL v7; // r14
  _SLIST_ENTRY *v8; // rsi
  int v9; // ecx
  __int64 v11; // r9
  unsigned __int64 v12; // r8
  __int16 v13; // dx
  int v14; // edx
  KIRQL v15; // al
  __int64 v16; // rdx
  unsigned __int64 v17; // rax
  struct _SLIST_ENTRY *Pool2; // rax
  KIRQL v19; // al
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  KIRQL v22; // r8
  _QWORD *v23; // rax

  v2 = 0;
  if ( !PoolHandle )
    return (PNET_BUFFER)v2;
  if ( (*((_DWORD *)PoolHandle + 20) & 1) == 0 )
  {
    DbgPrint("NdisAllocateNetBufferMdlAndData: Pool %p wrong pool type.\n", PoolHandle);
    return (PNET_BUFFER)v2;
  }
  if ( (*((_DWORD *)PoolHandle + 1) & 1) != 0 )
  {
    v4 = 0;
    v2 = (PSLIST_ENTRY)ndisPplAllocateFromSpecialPool((const struct _NDIS_POOL_HEADER *)PoolHandle);
    goto LABEL_10;
  }
  Number = KeGetPcr()->Prcb.Number;
  v4 = 1;
  if ( ndisMaxNumberOfProcessors != 1 )
  {
    v5 = (unsigned __int64)Number << 8;
    v6 = (char *)PoolHandle + v5 + 384;
    if ( !v6[216] )
    {
      v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v6 + 26);
      if ( !v6[216] )
      {
        ExInitializeLookasideListEx(
          (PLOOKASIDE_LIST_EX)v6,
          ndisAllocateFromNPagedPool,
          *(PFREE_FUNCTION_EX *)&v6[-v5 - 200],
          NonPagedPoolNx,
          0,
          *(unsigned int *)&v6[-v5 - 212],
          *(_DWORD *)&v6[-v5 - 216],
          0x400u);
        v6[216] = 1;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)v6 + 26, v7);
    }
    _InterlockedIncrement((volatile signed __int32 *)v6 + 5);
    v2 = ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v6 + 24));
    if ( v2 )
      goto LABEL_10;
    if ( ExQueryDepthSList(*((PSLIST_HEADER *)v6 + 25)) >= 0xAu )
    {
      v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v6 + 26);
      v16 = *((_QWORD *)v6 + 24);
      *((_QWORD *)v6 + 24) = *((_QWORD *)v6 + 25);
      *((_QWORD *)v6 + 25) = v16;
      KeReleaseSpinLock((PKSPIN_LOCK)v6 + 26, v15);
      v2 = ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v6 + 24));
      if ( v2 )
        goto LABEL_10;
    }
    _InterlockedIncrement((volatile signed __int32 *)v6 + 6);
  }
  _InterlockedIncrement((volatile signed __int32 *)PoolHandle + 37);
  v2 = ExpInterlockedPopEntrySList((PSLIST_HEADER)PoolHandle + 8);
  if ( v2 )
    goto LABEL_28;
  _InterlockedIncrement((volatile signed __int32 *)PoolHandle + 38);
  v17 = *((unsigned int *)PoolHandle + 43);
  if ( v17 + 32 >= v17
    && (Pool2 = (struct _SLIST_ENTRY *)ExAllocatePool2(66, v17 + 32, *((unsigned int *)PoolHandle + 42))) != 0 )
  {
    v2 = Pool2 + 2;
    Pool2->Next = 0;
    if ( Pool2 != (struct _SLIST_ENTRY *)-32LL )
    {
      Pool2->Next = (_SLIST_ENTRY *)PoolHandle;
      v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)PoolHandle + 1);
      v20 = *((_QWORD *)PoolHandle + 2);
      v21 = (char *)PoolHandle + 16;
      v22 = v19;
      if ( *(NDIS_HANDLE *)(v20 + 8) != (char *)PoolHandle + 16 )
        __fastfail(3u);
      v23 = &v2[-2].Next + 1;
      *v23 = v20;
      v23[1] = v21;
      *(_QWORD *)(v20 + 8) = (char *)v2 - 24;
      *v21 = (char *)v2 - 24;
      KeReleaseSpinLock((PKSPIN_LOCK)PoolHandle + 1, v22);
      v4 = 0;
LABEL_28:
      *((_DWORD *)&v2[-1].Next + 2) = Number;
      goto LABEL_10;
    }
  }
  else
  {
    v2 = 0;
  }
  v4 = 0;
LABEL_10:
  if ( !v2 )
    return 0;
  v8 = v2 + 11;
  if ( v4 )
  {
    *((_DWORD *)&v2[13].Next + 2) = *((_DWORD *)PoolHandle + 21);
    v8->Next = 0;
  }
  else
  {
    v11 = *((unsigned int *)PoolHandle + 21);
    v12 = (unsigned __int64)v8 + *((unsigned int *)PoolHandle + 22);
    v13 = (_WORD)v8 + *((_DWORD *)PoolHandle + 22);
    v8->Next = 0;
    *((_WORD *)&v2[11].Next + 5) = 0;
    *((_DWORD *)&v2[13].Next + 2) = v11;
    v2[13].Next = (_SLIST_ENTRY *)(v12 & 0xFFFFFFFFFFFFF000uLL);
    v14 = v13 & 0xFFF;
    *((_DWORD *)&v2[13].Next + 3) = v14;
    *((_WORD *)&v2[11].Next + 4) = 8 * ((((unsigned __int64)(unsigned __int16)v14 + v11 + 4095) >> 12) + 6);
    MmBuildMdlForNonPagedPool((PMDL)&v2[11]);
  }
  v9 = *((_DWORD *)PoolHandle + 21);
  v2->Next = 0;
  *((_QWORD *)&v2[3].Next + 1) = PoolHandle;
  *((_QWORD *)&v2->Next + 1) = v8;
  LODWORD(v2[1].Next) = v9;
  v2[2].Next = v8;
  *((_DWORD *)&v2[2].Next + 2) = v9;
  *((_DWORD *)&v2[1].Next + 2) = 0;
  LODWORD(v2[3].Next) = 0;
  *((_QWORD *)&v2[4].Next + 1) = 0;
  v2[4].Next = 0;
  *((_QWORD *)&v2[8].Next + 1) = 0;
  v2[8].Next = 0;
  *((_QWORD *)&v2[10].Next + 1) = 0;
  return (PNET_BUFFER)v2;
}

```

## disassembly

```asm
0x1400304b0  mov     [rsp+arg_8], rbx
0x1400304b5  mov     [rsp+arg_10], rbp
0x1400304ba  push    rsi
0x1400304bb  push    rdi
0x1400304bc  push    r12
0x1400304be  push    r13
0x1400304c0  push    r15
0x1400304c2  sub     rsp, 40h
0x1400304c6  xor     r13d, r13d
0x1400304c9  mov     rdi, rcx
0x1400304cc  mov     ebx, r13d
0x1400304cf  test    rcx, rcx
0x1400304d2  jz      loc_14003063A
0x1400304d8  mov     eax, [rcx+50h]
0x1400304db  test    al, 1
0x1400304dd  jz      loc_140030658
0x1400304e3  mov     eax, [rcx+4]
0x1400304e6  test    al, 1
0x1400304e8  jnz     loc_1400306DB
0x1400304ee  mov     r15d, gs:1A4h
0x1400304f7  mov     r12d, 1
0x1400304fd  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, r12d; ulong ndisMaxNumberOfProcessors
0x140030504  jz      loc_140030758
0x14003050a  mov     ebx, r15d
0x14003050d  lea     rsi, [rcx+180h]
0x140030514  shl     rbx, 8
0x140030518  add     rsi, rbx
0x14003051b  cmp     [rsi+0D8h], r13b
0x140030522  jnz     loc_1400305BC
0x140030528  lea     rcx, [rsi+0D0h]; SpinLock
0x14003052f  mov     [rsp+68h+arg_0], r14
0x140030534  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003053b  nop     dword ptr [rax+rax+00h]
0x140030540  movzx   r14d, al
0x140030544  cmp     [rsi+0D8h], r13b
0x14003054b  jnz     short loc_1400305A0
0x14003054d  mov     [rsp+68h+Depth], 400h; Depth
0x140030554  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x14003055b  mov     r8, rsi
0x14003055e  mov     r9d, 200h; PoolType
0x140030564  sub     r8, rbx
0x140030567  mov     ecx, [r8-0D4h]
0x14003056e  mov     eax, [r8-0D8h]
0x140030575  mov     r8, [r8-0C8h]; Free
0x14003057c  mov     [rsp+68h+Tag], eax; Tag
0x140030580  mov     [rsp+68h+Size], rcx; Size
0x140030585  mov     rcx, rsi; Lookaside
0x140030588  mov     [rsp+68h+Flags], r13d; Flags
0x14003058d  call    cs:__imp_ExInitializeLookasideListEx
0x140030594  nop     dword ptr [rax+rax+00h]
0x140030599  mov     [rsi+0D8h], r12b
0x1400305a0  movzx   edx, r14b; NewIrql
0x1400305a4  lea     rcx, [rsi+0D0h]; SpinLock
0x1400305ab  call    cs:__imp_KeReleaseSpinLock
0x1400305b2  nop     dword ptr [rax+rax+00h]
0x1400305b7  mov     r14, [rsp+68h+arg_0]
0x1400305bc  lock inc dword ptr [rsi+14h]
0x1400305c0  mov     rcx, [rsi+0C0h]; ListHead
0x1400305c7  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400305ce  nop     dword ptr [rax+rax+00h]
0x1400305d3  mov     rbx, rax
0x1400305d6  test    rax, rax
0x1400305d9  jz      loc_14003081F
0x1400305df  test    rbx, rbx
0x1400305e2  jz      loc_1400306D3
0x1400305e8  lea     rsi, [rbx+0B0h]
0x1400305ef  test    r12d, r12d
0x1400305f2  jz      short loc_140030670
0x1400305f4  mov     eax, [rdi+54h]
0x1400305f7  mov     [rsi+28h], eax
0x1400305fa  mov     [rsi], r13
0x1400305fd  mov     ecx, [rdi+54h]
0x140030600  mov     [rbx], r13
0x140030603  mov     [rbx+38h], rdi
0x140030607  mov     [rbx+8], rsi
0x14003060b  mov     [rbx+10h], ecx
0x14003060e  mov     [rbx+20h], rsi
0x140030612  mov     [rbx+28h], ecx
0x140030615  mov     [rbx+18h], r13d
0x140030619  mov     [rbx+30h], r13d
0x14003061d  mov     [rbx+48h], r13
0x140030621  mov     [rbx+40h], r13
0x140030625  mov     [rbx+88h], r13
0x14003062c  mov     [rbx+80h], r13
0x140030633  mov     [rbx+0A8h], r13
0x14003063a  mov     rbp, [rsp+68h+arg_10]
0x140030642  mov     rax, rbx
0x140030645  mov     rbx, [rsp+68h+arg_8]
0x14003064a  add     rsp, 40h
0x14003064e  pop     r15
0x140030650  pop     r13
0x140030652  pop     r12
0x140030654  pop     rdi
0x140030655  pop     rsi
0x140030656  retn
0x140030658  mov     rdx, rdi
0x14003065b  lea     rcx, Format; "NdisAllocateNetBufferMdlAndData: Pool %"...
0x140030662  call    cs:__imp_DbgPrint
0x140030669  nop     dword ptr [rax+rax+00h]
0x14003066e  jmp     short loc_14003063A
0x140030670  mov     r8d, [rdi+58h]
0x140030674  mov     r9d, [rdi+54h]
0x140030678  add     r8, rsi
0x14003067b  mov     edx, r8d
0x14003067e  mov     [rsi], r13
0x140030681  mov     eax, edx
0x140030683  mov     [rsi+0Ah], r13w
0x140030688  and     eax, 0FFFh
0x14003068d  mov     [rsi+28h], r9d
0x140030691  lea     rcx, [r9+0FFFh]
0x140030698  and     r8, 0FFFFFFFFFFFFF000h
0x14003069f  add     rcx, rax
0x1400306a2  mov     [rsi+20h], r8
0x1400306a6  shr     rcx, 0Ch
0x1400306aa  and     edx, 0FFFh
0x1400306b0  add     cx, 6
0x1400306b4  mov     [rsi+2Ch], edx
0x1400306b7  shl     cx, 3
0x1400306bb  mov     [rsi+8], cx
0x1400306bf  mov     rcx, rsi; MemoryDescriptorList
0x1400306c2  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400306c9  nop     dword ptr [rax+rax+00h]
0x1400306ce  jmp     loc_1400305FD
0x1400306d3  mov     rbx, r13
0x1400306d6  jmp     loc_14003063A
0x1400306db  mov     r12d, r13d
0x1400306de  call    ?ndisPplAllocateFromSpecialPool@@YAPEAXPEBU_NDIS_POOL_HEADER@@@Z; ndisPplAllocateFromSpecialPool(_NDIS_POOL_HEADER const *)
0x1400306e3  mov     rbx, rax
0x1400306e6  jmp     loc_1400305DF
0x1400306eb  lea     rcx, [rsi+0D0h]; SpinLock
0x1400306f2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400306f9  nop     dword ptr [rax+rax+00h]
0x1400306fe  mov     rdx, [rsi+0C0h]
0x140030705  lea     rcx, [rsi+0D0h]; SpinLock
0x14003070c  movzx   r8d, al
0x140030710  mov     rax, [rsi+0C8h]
0x140030717  mov     [rsi+0C0h], rax
0x14003071e  mov     [rsi+0C8h], rdx
0x140030725  movzx   edx, r8b; NewIrql
0x140030729  call    cs:__imp_KeReleaseSpinLock
0x140030730  nop     dword ptr [rax+rax+00h]
0x140030735  mov     rcx, [rsi+0C0h]; ListHead
0x14003073c  call    cs:__imp_ExpInterlockedPopEntrySList
0x140030743  nop     dword ptr [rax+rax+00h]
0x140030748  mov     rbx, rax
0x14003074b  test    rax, rax
0x14003074e  jnz     loc_1400305DF
0x140030754  lock inc dword ptr [rsi+18h]
0x140030758  lea     rsi, [rdi+80h]
0x14003075f  lock inc dword ptr [rsi+14h]
0x140030763  mov     rcx, rsi; ListHead
0x140030766  call    cs:__imp_ExpInterlockedPopEntrySList
0x14003076d  nop     dword ptr [rax+rax+00h]
0x140030772  mov     rbx, rax
0x140030775  test    rax, rax
0x140030778  jnz     loc_140030816
0x14003077e  lock inc dword ptr [rsi+18h]
0x140030782  mov     eax, [rsi+2Ch]
0x140030785  lea     rdx, [rax+20h]
0x140030789  cmp     rdx, rax
0x14003078c  jb      loc_140030841
0x140030792  mov     r8d, [rsi+28h]
0x140030796  mov     ecx, 42h ; 'B'
0x14003079b  call    cs:__imp_ExAllocatePool2
0x1400307a2  nop     dword ptr [rax+rax+00h]
0x1400307a7  test    rax, rax
0x1400307aa  jz      loc_140030841
0x1400307b0  lea     rbx, [rax+20h]
0x1400307b4  mov     [rax], r13
0x1400307b7  test    rbx, rbx
0x1400307ba  jz      loc_140030844
0x1400307c0  lea     rcx, [rdi+8]; SpinLock
0x1400307c4  mov     [rbx-20h], rdi
0x1400307c8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400307cf  nop     dword ptr [rax+rax+00h]
0x1400307d4  mov     rdx, [rdi+10h]
0x1400307d8  lea     rcx, [rdi+10h]
0x1400307dc  movzx   r8d, al
0x1400307e0  cmp     [rdx+8], rcx
0x1400307e4  jz      short loc_1400307ED
0x1400307e6  mov     ecx, 3
0x1400307eb  int     29h; Win8: RtlFailFast(ecx)
0x1400307ed  lea     rax, [rbx-18h]
0x1400307f1  mov     [rax], rdx
0x1400307f4  mov     [rax+8], rcx
0x1400307f8  mov     [rdx+8], rax
0x1400307fc  movzx   edx, r8b; NewIrql
0x140030800  mov     [rcx], rax
0x140030803  lea     rcx, [rdi+8]; SpinLock
0x140030807  call    cs:__imp_KeReleaseSpinLock
0x14003080e  nop     dword ptr [rax+rax+00h]
0x140030813  mov     r12d, r13d
0x140030816  mov     [rbx-8], r15d
0x14003081a  jmp     loc_1400305DF
0x14003081f  mov     rcx, [rsi+0C8h]; SListHead
0x140030826  call    cs:__imp_ExQueryDepthSList
0x14003082d  nop     dword ptr [rax+rax+00h]
0x140030832  cmp     ax, 0Ah
0x140030836  jb      loc_140030754
0x14003083c  jmp     loc_1400306EB
0x140030841  mov     rbx, r13
0x140030844  mov     r12d, r13d
0x140030847  jmp     loc_1400305DF
```
