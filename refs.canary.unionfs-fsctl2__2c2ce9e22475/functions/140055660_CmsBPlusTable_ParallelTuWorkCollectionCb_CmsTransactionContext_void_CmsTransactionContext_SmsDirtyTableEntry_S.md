# CmsBPlusTable::ParallelTuWorkCollectionCb<CmsTransactionContext *,void (&)(CmsTransactionContext *,SmsDirtyTableEntry *,SmsDirtyTableEntry *),SmsDirtyTableEntry * &,SmsDirtyTableEntry * &>(CmsTransactionContext *,void (&)(CmsTransactionContext *,SmsDirtyTableEntry *,SmsDirtyTableEntry *),SmsDirtyTableEntry * &,SmsDirtyTableEntry * &)

- ea: `0x140055660`
- end: `0x140055ae9`
- name: `??$ParallelTuWorkCollectionCb@PEAVCmsTransactionContext@@A6AXPEAV1@PEAUSmsDirtyTableEntry@@1@ZAEAPEAU2@AEAPEAU2@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@A6AX0PEAUSmsDirtyTableEntry@@1@ZAEAPEAU2@3@Z`
- size: `1161`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14013f2a4`

## callees

- `0x14002b110`
- `0x1400340e0`
- `0x140053024`
- `0x1400530a0`
- `0x140055660`
- `0x1400c8574`
- `0x1401e9dc0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14005576f`
- `ntoskrnl!KeSetEvent` at `0x14005576f`
- `ntoskrnl!KdDebuggerEnabled` at `0x14005599b`
- `ntoskrnl!KdDebuggerEnabled` at `0x140055a0f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140055792`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140055792`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140055a33`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140055a33`
- `ntoskrnl!ExAllocatePool2` at `0x1400556c4`
- `ntoskrnl!ExAllocatePool2` at `0x1400556c4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140055683`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140055683`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f47be`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f47be`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005598a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005598a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f47fb`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f47fb`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140055a51`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140055a51`
- `ntoskrnl!ExReleasePushLockEx` at `0x140055784`
- `ntoskrnl!ExReleasePushLockEx` at `0x140055784`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400558a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055a64`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055a85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055ad8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400558a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055a64`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055a85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055ad8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140055aa6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140055aa6`

## string_xrefs

- `0x1400556db`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
void __fastcall CmsBPlusTable::ParallelTuWorkCollectionCb<CmsTransactionContext *,void (&)(CmsTransactionContext *,SmsDirtyTableEntry *,SmsDirtyTableEntry *),SmsDirtyTableEntry * &,SmsDirtyTableEntry * &>(
        __int64 a1,
        void (__fastcall *a2)(_QWORD *, _QWORD, _QWORD),
        _QWORD *a3,
        _QWORD *a4)
{
  __int64 v4; // rsi
  __int64 v9; // rdi
  __int64 v10; // rdx
  __int64 Pool2; // rax
  PSLIST_ENTRY v12; // rbx
  int v13; // ecx
  __int64 v14; // rdx
  signed __int32 v15; // ett
  _QWORD *p_Next; // rbx
  __int64 v17; // rsi
  char v18; // di
  __int64 v19; // rbp
  __int64 v20; // rsi
  unsigned __int8 i; // dl
  __int64 v22; // rax
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  struct _SLIST_ENTRY *v26; // r8
  __int64 v27; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v28; // rcx
  unsigned int j; // ecx
  __int64 v30; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v31; // rcx
  struct _SLIST_ENTRY *v32; // rax
  __int64 v33; // rcx
  int v34; // [rsp+24h] [rbp-54h]

  v4 = *(_QWORD *)(a1 + 8);
  v9 = qword_140262408 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v9 >= 0xD50u )
  {
    if ( !*(_BYTE *)(v9 + 8) )
    {
      if ( (int)*(_QWORD *)(v9 + 88) > (int)HIDWORD(*(_QWORD *)(v9 + 88)) )
      {
        v13 = _InterlockedDecrement((volatile signed __int32 *)(v9 + 88));
        if ( v13 >= *(_DWORD *)(v9 + 92) && v13 >= 0 )
        {
          v12 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v9 + 64));
          goto LABEL_44;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 88));
      }
LABEL_9:
      v10 = *(unsigned int *)(v9 + 4);
      goto LABEL_3;
    }
    v31 = (struct _NPAGED_LOOKASIDE_LIST *)(v9 + 64);
    if ( *(_BYTE *)(v9 + 9) )
      v32 = (struct _SLIST_ENTRY *)ExAllocateFromNPagedLookasideList(v31);
    else
      v32 = (struct _SLIST_ENTRY *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v31);
    v12 = v32;
    CmsTransactionContext::InitializeTransactionMemoryBuffer(&v32->Next + 1);
LABEL_44:
    if ( v12 )
      goto LABEL_45;
    goto LABEL_9;
  }
  v9 = 0;
  v10 = 3424;
LABEL_3:
  Pool2 = ExAllocatePool2(66, v10, 1766871885);
  v12 = (PSLIST_ENTRY)Pool2;
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( !Pool2 )
    goto LABEL_18;
  CmsTransactionContext::InitializeTransactionMemoryBuffer((void *)(Pool2 + 16));
LABEL_45:
  v12->Next = (struct _SLIST_ENTRY *)v9;
  p_Next = &v12[1].Next;
  if ( !p_Next )
  {
LABEL_18:
    p_Next = CmsReservedPool::AllocateFromPool((CmsReservedPool *)(v4 + 160));
    CmsTransactionContext::InitializeTransactionMemoryBuffer(p_Next);
    p_Next[1] = v4;
    v17 = 268468224;
    goto LABEL_19;
  }
  p_Next[1] = v4;
  v17 = 0x8000;
LABEL_19:
  *p_Next = v17;
  v18 = *((_BYTE *)p_Next + 220);
  *p_Next = *(_QWORD *)a1 | v17;
  *((_BYTE *)p_Next + 220) = *(_BYTE *)(a1 + 220);
  a2(p_Next, *a3, *a4);
  CmsTransactionContext::Commit((CmsTransactionContext *)p_Next, 0, 0, 0);
  v19 = p_Next[1];
  *p_Next = v17;
  v20 = v17 & 0x10000000;
  *((_BYTE *)p_Next + 220) = v18;
  if ( (p_Next[37] || *((_DWORD *)p_Next + 88) || *((_DWORD *)p_Next + 89)) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  for ( i = 0; i < *((_BYTE *)p_Next + 128); HIDWORD(p_Next[11 * v22 + 142]) &= ~1u )
    v22 = i++;
  v23 = (void *)p_Next[424];
  *((_BYTE *)p_Next + 128) = 0;
  if ( v23 )
  {
    ExFreePoolWithTag(v23, 0);
    p_Next[424] = 0;
    *((_DWORD *)p_Next + 850) = 0;
  }
  if ( (p_Next[417] & 1) != 0 )
  {
    v24 = (void *)p_Next[416];
    if ( v24 )
      ExFreePoolWithTag(v24, 0);
  }
  *((_DWORD *)p_Next + 835) = 32;
  p_Next[416] = p_Next + 418;
  *((_DWORD *)p_Next + 829) = v34;
  *((_OWORD *)p_Next + 206) = 0;
  *((_DWORD *)p_Next + 828) = 0;
  p_Next[415] = 0;
  *((_BYTE *)p_Next + 3336) = 0;
  CmsRowWithBuffer::Reset((CmsRowWithBuffer *)(p_Next + 402));
  CmsRowWithBuffer::Reset((CmsRowWithBuffer *)(p_Next + 392));
  CmsRowWithBuffer::Reset((CmsRowWithBuffer *)(p_Next + 382));
  CmsRowWithBuffer::Reset((CmsRowWithBuffer *)(p_Next + 372));
  CmsRowWithBuffer::Reset((CmsRowWithBuffer *)(p_Next + 362));
  CmsRowWithBuffer::Reset((CmsRowWithBuffer *)(p_Next + 352));
  if ( p_Next[128] && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v25 = (void *)p_Next[108];
  if ( v25 )
  {
    ExFreePoolWithTag(v25, 0);
    p_Next[108] = 0;
  }
  if ( !v20 )
  {
    v26 = (struct _SLIST_ENTRY *)(p_Next - 2);
    v27 = *(p_Next - 2);
    if ( v27 )
    {
      if ( *(_BYTE *)(v27 + 8) )
      {
        v28 = (struct _NPAGED_LOOKASIDE_LIST *)(v27 + 64);
        if ( *(_BYTE *)(v27 + 9) )
          ExFreeToNPagedLookasideList(v28, v26);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v28, v26);
        return;
      }
      v33 = *(_QWORD *)(v27 + 88);
      if ( (int)v33 < *(_DWORD *)(v27 + 80) || SHIDWORD(v33) >= (int)v33 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v27 + 64), v26);
        _InterlockedIncrement((volatile signed __int32 *)(v27 + 88));
        return;
      }
    }
    ExFreePoolWithTag(v26, 0);
    return;
  }
  if ( *(_DWORD *)(v19 + 172) )
  {
    for ( j = 0; j < *(_DWORD *)(v19 + 168); ++j )
    {
      v30 = 16LL * j;
      if ( *(_QWORD **)(v30 + *(_QWORD *)(v19 + 160)) == p_Next )
      {
        if ( *(_BYTE *)(v19 + 216) )
          ExAcquirePushLockExclusiveEx(v19 + 208, 0);
        v14 = v30 + *(_QWORD *)(v19 + 160);
        _m_prefetchw((const void *)(v14 + 8));
        do
          v15 = *(_DWORD *)(v14 + 8);
        while ( v15 != _InterlockedCompareExchange((volatile signed __int32 *)(v14 + 8), v15 & 0xFFFFFFFE, v15) );
        _InterlockedDecrement((volatile signed __int32 *)(v19 + 172));
        if ( *(_BYTE *)(v19 + 216) )
        {
          KeSetEvent((PRKEVENT)(v19 + 184), 0, 0);
          ExReleasePushLockEx(v19 + 208, 0);
        }
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x140055660  push    rbx
0x140055662  push    rbp
0x140055663  push    rsi
0x140055664  push    rdi
0x140055665  push    r12
0x140055667  push    r13
0x140055669  push    r14
0x14005566b  push    r15
0x14005566d  sub     rsp, 38h
0x140055671  mov     rsi, [rcx+8]
0x140055675  mov     rbp, rcx
0x140055678  xor     ecx, ecx; ProcNumber
0x14005567a  mov     r14, r9
0x14005567d  mov     r15, r8
0x140055680  mov     r12, rdx
0x140055683  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14005568a  nop     dword ptr [rax+rax+00h]
0x14005568f  xor     edx, edx
0x140055691  xor     r13d, r13d
0x140055694  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14005569a  lea     rdi, [rdx+rdx*2]
0x14005569e  shl     rdi, 6
0x1400556a2  add     rdi, cs:qword_140262408
0x1400556a9  cmp     dword ptr [rdi], 0D50h
0x1400556af  jnb     short loc_1400556E8
0x1400556b1  mov     edi, r13d
0x1400556b4  mov     edx, 0D60h
0x1400556b9  mov     ecx, 42h ; 'B'
0x1400556be  mov     r8d, 6950534Dh
0x1400556c4  call    cs:__imp_ExAllocatePool2
0x1400556cb  nop     dword ptr [rax+rax+00h]
0x1400556d0  mov     rbx, rax
0x1400556d3  test    al, 0Fh
0x1400556d5  jz      loc_1401F47DC
0x1400556db  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1400556e2  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x1400556e8  cmp     [rdi+8], r13b
0x1400556ec  jnz     loc_140055A25
0x1400556f2  mov     rcx, [rdi+58h]
0x1400556f6  mov     rax, rcx
0x1400556f9  shr     rax, 20h
0x1400556fd  cmp     ecx, eax
0x1400556ff  jle     short loc_140055720
0x140055701  nop
0x140055702  mov     ecx, 0FFFFFFFFh
0x140055707  lock xadd [rdi+58h], ecx
0x14005570c  nop
0x14005570d  dec     ecx
0x14005570f  mov     eax, [rdi+5Ch]
0x140055712  cmp     ecx, eax
0x140055714  jge     loc_140055A45
0x14005571a  nop
0x14005571b  lock inc dword ptr [rdi+58h]
0x14005571f  nop
0x140055720  mov     edx, [rdi+4]
0x140055723  jmp     short loc_1400556B9
0x140055725  cmp     [rbp+0D8h], r13b
0x14005572c  jnz     loc_140055A9D
0x140055732  mov     rdx, [rbp+0A0h]
0x140055739  add     rdx, rdi
0x14005573c  prefetchw byte ptr [rdx+8]
0x140055740  mov     eax, [rdx+8]
0x140055743  mov     ecx, eax
0x140055745  and     ecx, 0FFFFFFFEh
0x140055748  nop
0x140055749  lock cmpxchg [rdx+8], ecx
0x14005574e  nop
0x14005574f  jnz     short loc_140055740
0x140055751  nop
0x140055752  lock dec dword ptr [rbp+0ACh]
0x140055759  nop
0x14005575a  cmp     [rbp+0D8h], r13b
0x140055761  jz      short loc_14005579E
0x140055763  lea     rcx, [rbp+0B8h]; Event
0x14005576a  xor     r8d, r8d; Wait
0x14005576d  xor     edx, edx; Increment
0x14005576f  call    cs:__imp_KeSetEvent
0x140055776  nop     dword ptr [rax+rax+00h]
0x14005577b  lea     rcx, [rbp+0D0h]
0x140055782  xor     edx, edx
0x140055784  call    cs:__imp_ExReleasePushLockEx
0x14005578b  nop     dword ptr [rax+rax+00h]
0x140055790  jmp     short loc_14005579E
0x140055792  call    cs:__imp_ExFreeToNPagedLookasideList
0x140055799  nop     dword ptr [rax+rax+00h]
0x14005579e  add     rsp, 38h
0x1400557a2  pop     r15
0x1400557a4  pop     r14
0x1400557a6  pop     r13
0x1400557a8  pop     r12
0x1400557aa  pop     rdi
0x1400557ab  pop     rsi
0x1400557ac  pop     rbp
0x1400557ad  pop     rbx
0x1400557ae  retn
0x1400557b0  test    rbx, rbx
0x1400557b3  jnz     loc_1400559F4
0x1400557b9  lea     rcx, [rsi+0A0h]; this
0x1400557c0  call    ?AllocateFromPool@CmsReservedPool@@QEAAPEAXXZ; CmsReservedPool::AllocateFromPool(void)
0x1400557c5  mov     rcx, rax; void *
0x1400557c8  mov     rbx, rax
0x1400557cb  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x1400557d0  mov     [rbx+8], rsi
0x1400557d4  mov     esi, 10008000h
0x1400557d9  mov     [rbx], rsi
0x1400557dc  mov     rax, rsi
0x1400557df  or      rax, [rbp+0]
0x1400557e3  mov     rcx, rbx
0x1400557e6  movzx   edi, byte ptr [rbx+0DCh]
0x1400557ed  mov     [rbx], rax
0x1400557f0  movzx   eax, byte ptr [rbp+0DCh]
0x1400557f7  mov     [rbx+0DCh], al
0x1400557fd  mov     rax, r12
0x140055800  mov     r8, [r14]
0x140055803  mov     rdx, [r15]
0x140055806  call    _guard_dispatch_icall
0x14005580b  xor     r9d, r9d; unsigned __int8
0x14005580e  xor     r8d, r8d; struct _SmsLsn *
0x140055811  xor     edx, edx; unsigned __int8
0x140055813  mov     rcx, rbx; this
0x140055816  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x14005581b  mov     rbp, [rbx+8]
0x14005581f  mov     [rbx], rsi
0x140055822  and     esi, 10000000h
0x140055828  mov     [rbx+0DCh], dil
0x14005582f  cmp     [rbx+128h], r13
0x140055836  jnz     loc_14005599B
0x14005583c  cmp     [rbx+160h], r13d
0x140055843  jnz     loc_14005599B
0x140055849  cmp     [rbx+164h], r13d
0x140055850  jnz     loc_14005599B
0x140055856  xor     dl, dl
0x140055858  cmp     [rbx+80h], dl
0x14005585e  jbe     short loc_140055879
0x140055860  movzx   eax, dl
0x140055863  inc     dl
0x140055865  imul    rcx, rax, 58h ; 'X'
0x140055869  and     dword ptr [rcx+rbx+474h], 0FFFFFFFEh
0x140055871  cmp     dl, [rbx+80h]
0x140055877  jb      short loc_140055860
0x140055879  mov     rcx, [rbx+0D40h]; P
0x140055880  mov     [rbx+80h], r13b
0x140055887  test    rcx, rcx
0x14005588a  jnz     loc_140055A62
0x140055890  test    byte ptr [rbx+0D08h], 1
0x140055897  jz      short loc_1400558B3
0x140055899  mov     rcx, [rbx+0D00h]; P
0x1400558a0  test    rcx, rcx
0x1400558a3  jz      short loc_1400558B3
0x1400558a5  xor     edx, edx; Tag
0x1400558a7  call    cs:__imp_ExFreePoolWithTag
0x1400558ae  nop     dword ptr [rax+rax+00h]
0x1400558b3  lea     rax, [rbx+0D10h]
0x1400558ba  mov     dword ptr [rbx+0D0Ch], 20h ; ' '
0x1400558c4  mov     [rbx+0D00h], rax
0x1400558cb  lea     rcx, [rbx+0C90h]; this
0x1400558d2  mov     eax, [rsp+78h+var_54]
0x1400558d6  xorps   xmm0, xmm0
0x1400558d9  mov     [rbx+0CF4h], eax
0x1400558df  movups  xmmword ptr [rbx+0CE0h], xmm0
0x1400558e6  mov     [rbx+0CF0h], r13d
0x1400558ed  mov     [rbx+0CF8h], r13
0x1400558f4  mov     [rbx+0D08h], r13b
0x1400558fb  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140055900  lea     rcx, [rbx+0C40h]; this
0x140055907  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x14005590c  lea     rcx, [rbx+0BF0h]; this
0x140055913  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140055918  lea     rcx, [rbx+0BA0h]; this
0x14005591f  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140055924  lea     rcx, [rbx+0B50h]; this
0x14005592b  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140055930  lea     rcx, [rbx+0B00h]; this
0x140055937  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x14005593c  cmp     [rbx+400h], r13
0x140055943  jnz     loc_140055A0F
0x140055949  mov     rcx, [rbx+360h]; P
0x140055950  test    rcx, rcx
0x140055953  jnz     loc_140055A83
0x140055959  test    rsi, rsi
0x14005595c  jnz     short loc_1400559B1
0x14005595e  lea     r8, [rbx-10h]
0x140055962  mov     rbx, [rbx-10h]
0x140055966  test    rbx, rbx
0x140055969  jz      loc_140055AD3
0x14005596f  cmp     [rbx+8], r13b
0x140055973  jz      loc_140055AB7
0x140055979  lea     rcx, [rbx+40h]; Lookaside
0x14005597d  mov     rdx, r8; Entry
0x140055980  cmp     [rbx+9], r13b
0x140055984  jnz     loc_140055792
0x14005598a  call    cs:__imp_ExFreeToPagedLookasideList
0x140055991  nop     dword ptr [rax+rax+00h]
0x140055996  jmp     loc_14005579E
0x14005599b  mov     rax, cs:KdDebuggerEnabled
0x1400559a2  cmp     [rax], r13b
0x1400559a5  jz      loc_140055856
0x1400559ab  int     3; Trap to Debugger
0x1400559ac  jmp     loc_140055856
0x1400559b1  mov     eax, [rbp+0ACh]
0x1400559b7  test    eax, eax
0x1400559b9  jz      loc_14005579E
0x1400559bf  mov     edx, [rbp+0A8h]
0x1400559c5  mov     ecx, r13d
0x1400559c8  cmp     ecx, edx
0x1400559ca  jnb     loc_14005579E
0x1400559d0  mov     rax, [rbp+0A0h]
0x1400559d7  mov     edi, ecx
0x1400559d9  shl     rdi, 4
0x1400559dd  cmp     [rdi+rax], rbx
0x1400559e1  jz      loc_140055725
0x1400559e7  inc     ecx
0x1400559e9  jmp     short loc_1400559C8
0x1400559eb  test    rbx, rbx
0x1400559ee  jz      loc_140055720
0x1400559f4  mov     [rbx], rdi
0x1400559f7  add     rbx, 10h
0x1400559fb  jz      loc_1400557B9
0x140055a01  mov     [rbx+8], rsi
0x140055a05  mov     esi, 8000h
0x140055a0a  jmp     loc_1400557D9
0x140055a0f  mov     rax, cs:KdDebuggerEnabled
0x140055a16  cmp     [rax], r13b
0x140055a19  jz      loc_140055949
0x140055a1f  int     3; Trap to Debugger
0x140055a20  jmp     loc_140055949
0x140055a25  lea     rcx, [rdi+40h]; Lookaside
0x140055a29  cmp     [rdi+9], r13b
0x140055a2d  jz      loc_1401F47BE
0x140055a33  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140055a3a  nop     dword ptr [rax+rax+00h]
0x140055a3f  nop
0x140055a40  jmp     loc_1401F47CA
0x140055a45  test    ecx, ecx
0x140055a47  js      loc_14005571A
0x140055a4d  lea     rcx, [rdi+40h]; ListHead
0x140055a51  call    cs:__imp_ExpInterlockedPopEntrySList
0x140055a58  nop     dword ptr [rax+rax+00h]
0x140055a5d  mov     rbx, rax
0x140055a60  jmp     short loc_1400559EB
0x140055a62  xor     edx, edx; Tag
0x140055a64  call    cs:__imp_ExFreePoolWithTag
0x140055a6b  nop     dword ptr [rax+rax+00h]
0x140055a70  mov     [rbx+0D40h], r13
0x140055a77  mov     [rbx+0D48h], r13d
0x140055a7e  jmp     loc_140055890
0x140055a83  xor     edx, edx; Tag
0x140055a85  call    cs:__imp_ExFreePoolWithTag
0x140055a8c  nop     dword ptr [rax+rax+00h]
0x140055a91  mov     [rbx+360h], r13
0x140055a98  jmp     loc_140055959
0x140055a9d  lea     rcx, [rbp+0D0h]
0x140055aa4  xor     edx, edx
0x140055aa6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140055aad  nop     dword ptr [rax+rax+00h]
0x140055ab2  jmp     loc_140055732
0x140055ab7  mov     rcx, [rbx+58h]
0x140055abb  cmp     ecx, [rbx+50h]
0x140055abe  jl      loc_1401F47F4
0x140055ac4  mov     rax, rcx
0x140055ac7  shr     rax, 20h
0x140055acb  cmp     eax, ecx
0x140055acd  jge     loc_1401F47F4
0x140055ad3  xor     edx, edx; Tag
0x140055ad5  mov     rcx, r8; P
0x140055ad8  call    cs:__imp_ExFreePoolWithTag
0x140055adf  nop     dword ptr [rax+rax+00h]
0x140055ae4  jmp     loc_14005579E
0x1401f47be  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f47c5  nop     dword ptr [rax+rax+00h]
0x1401f47ca  lea     rcx, [rax+8]; void *
0x1401f47ce  mov     rbx, rax
0x1401f47d1  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x1401f47d6  nop
0x1401f47d7  jmp     loc_1400559EB
0x1401f47dc  test    rax, rax
0x1401f47df  jz      loc_1400557B0
0x1401f47e5  lea     rcx, [rax+10h]; void *
0x1401f47e9  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x1401f47ee  nop
0x1401f47ef  jmp     loc_1400559F4
0x1401f47f4  lea     rcx, [rbx+40h]; ListHead
0x1401f47f8  mov     rdx, r8; ListEntry
0x1401f47fb  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f4802  nop     dword ptr [rax+rax+00h]
0x1401f4807  nop
0x1401f4808  lock inc dword ptr [rbx+58h]
0x1401f480c  nop
0x1401f480d  jmp     loc_14005579E
```
