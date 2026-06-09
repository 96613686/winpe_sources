# `CmsHashTable::ParallelWork<`CmsBPlusTable::ParallelTuPageTableWork<void (&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,SmsWritePlan *),SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,SmsWritePlan *),SmsWritePlan * &)'::`2'::_lambda_1_>(ulong,`CmsBPlusTable::ParallelTuPageTableWork<void (&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,SmsWritePlan *),SmsWritePlan * &>(CmsTransactionContext *,CmsHashTable *,void (&)(CmsTransactionContext *,CmsHashTable *,ulong,ulong,SmsWritePlan *),SmsWritePlan * &)'::`2'::_lambda_1_ &&)'::`2'::_lambda_1_::operator()(void *)

- ea: `0x140055200`
- end: `0x140055659`
- name: `??R_lambda_1_@?1???$ParallelWork@V_lambda_1_@?1???$ParallelTuPageTableWork@A6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAUSmsWritePlan@@@ZAEAPEAU3@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@A6AX01KKPEAUSmsWritePlan@@@ZAEAPEAU5@@Z@@CmsHashTable@@QEAAJK$$QEAV0?1???$ParallelTuPageTableWork@A6AXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAUSmsWritePlan@@@ZAEAPEAU3@@CmsBPlusTable@@CAXPEAVCmsTransactionContext@@PEAV1@A6AX01KKPEAUSmsWritePlan@@@ZAEAPEAU4@@Z@@Z@QEBA@PEAX@Z`
- size: `1113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b5820`

## callees

- `0x14002b110`
- `0x1400340e0`
- `0x140053024`
- `0x1400530a0`
- `0x140055200`
- `0x1400b26e0`
- `0x1400c8574`
- `0x1401e9dc0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14005551c`
- `ntoskrnl!KeSetEvent` at `0x14005551c`
- `ntoskrnl!KdDebuggerEnabled` at `0x14005554f`
- `ntoskrnl!KdDebuggerEnabled` at `0x140055596`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400554f6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400554f6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400555ba`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400555ba`
- `ntoskrnl!ExAllocatePool2` at `0x140055299`
- `ntoskrnl!ExAllocatePool2` at `0x140055299`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140055257`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140055257`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f476a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f476a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140055541`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140055541`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f47a7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f47a7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400555d8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400555d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055412`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400555eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005560f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055648`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055412`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400555eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005560f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055648`

## string_xrefs

- `0x1400552b0`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
LONG __fastcall __R_lambda_1___1____ParallelWork_V_lambda_1___1____ParallelTuPageTableWork_A6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAUSmsWritePlan___ZAEAPEAU3__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAVCmsHashTable__A6AX01KKPEAUSmsWritePlan___ZAEAPEAU5__Z__CmsHashTable__QEAAJK__QEAV0_1____ParallelTuPageTableWork_A6AXPEAVCmsTransactionContext__PEAVCmsHashTable__KKPEAUSmsWritePlan___ZAEAPEAU3__CmsBPlusTable__CAXPEAVCmsTransactionContext__PEAV1_A6AX01KKPEAUSmsWritePlan___ZAEAPEAU4__Z__Z_QEBA_PEAX_Z(
        __int64 a1,
        volatile signed __int32 **a2)
{
  unsigned int v3; // r12d
  unsigned int v4; // r13d
  __int64 *v5; // rax
  __int64 v6; // r15
  __int64 v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // rdx
  __int64 Pool2; // rax
  PSLIST_ENTRY v11; // rbx
  int v12; // ecx
  _QWORD *p_Next; // rbx
  __int64 v14; // rsi
  char v15; // di
  __int64 v16; // r15
  __int64 v17; // rsi
  unsigned __int8 i; // dl
  __int64 v19; // rax
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  struct _SLIST_ENTRY *v23; // r8
  __int64 v24; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v25; // rcx
  signed __int32 v26; // ebp
  LONG result; // eax
  struct _NPAGED_LOOKASIDE_LIST *v28; // rcx
  struct _SLIST_ENTRY *v29; // rax
  __int64 v30; // rcx
  int v31; // [rsp+34h] [rbp-44h]
  _QWORD *v32; // [rsp+80h] [rbp+8h]
  _QWORD *v33; // [rsp+88h] [rbp+10h]
  void (__fastcall *v34)(_QWORD *, _QWORD, _QWORD, _QWORD, _QWORD); // [rsp+90h] [rbp+18h]

  v3 = *((_DWORD *)a2 + 7);
  v4 = *((_DWORD *)a2 + 6);
  v32 = (_QWORD *)*((_QWORD *)*a2 + 3);
  v33 = (_QWORD *)*((_QWORD *)*a2 + 2);
  v5 = *(__int64 **)*a2;
  v34 = (void (__fastcall *)(_QWORD *, _QWORD, _QWORD, _QWORD, _QWORD))*((_QWORD *)*a2 + 1);
  v6 = *v5;
  v7 = *(_QWORD *)(*v5 + 8);
  v8 = qword_140262408 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v8 >= 0xD50u )
  {
    if ( !*(_BYTE *)(v8 + 8) )
    {
      if ( (int)*(_QWORD *)(v8 + 88) > (int)HIDWORD(*(_QWORD *)(v8 + 88)) )
      {
        v12 = _InterlockedDecrement((volatile signed __int32 *)(v8 + 88));
        if ( v12 >= *(_DWORD *)(v8 + 92) && v12 >= 0 )
        {
          v11 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v8 + 64));
          goto LABEL_36;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v8 + 88));
      }
LABEL_9:
      v9 = *(unsigned int *)(v8 + 4);
      goto LABEL_3;
    }
    v28 = (struct _NPAGED_LOOKASIDE_LIST *)(v8 + 64);
    if ( *(_BYTE *)(v8 + 9) )
      v29 = (struct _SLIST_ENTRY *)ExAllocateFromNPagedLookasideList(v28);
    else
      v29 = (struct _SLIST_ENTRY *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v28);
    v11 = v29;
    CmsTransactionContext::InitializeTransactionMemoryBuffer(&v29->Next + 1);
LABEL_36:
    if ( v11 )
      goto LABEL_37;
    goto LABEL_9;
  }
  v8 = 0;
  v9 = 3424;
LABEL_3:
  Pool2 = ExAllocatePool2(66, v9, 1766871885);
  v11 = (PSLIST_ENTRY)Pool2;
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( !Pool2 )
    goto LABEL_10;
  CmsTransactionContext::InitializeTransactionMemoryBuffer((void *)(Pool2 + 16));
LABEL_37:
  v11->Next = (struct _SLIST_ENTRY *)v8;
  p_Next = &v11[1].Next;
  if ( !p_Next )
  {
LABEL_10:
    p_Next = CmsReservedPool::AllocateFromPool((CmsReservedPool *)(v7 + 160));
    CmsTransactionContext::InitializeTransactionMemoryBuffer(p_Next);
    v14 = 268468224;
    goto LABEL_11;
  }
  v14 = 0x8000;
LABEL_11:
  *p_Next = v14;
  p_Next[1] = v7;
  v15 = *((_BYTE *)p_Next + 220);
  *p_Next = *(_QWORD *)v6 | v14;
  *((_BYTE *)p_Next + 220) = *(_BYTE *)(v6 + 220);
  v34(p_Next, *v33, v4, v3, *v32);
  CmsTransactionContext::Commit((CmsTransactionContext *)p_Next, 0, 0, 0);
  v16 = p_Next[1];
  *p_Next = v14;
  v17 = v14 & 0x10000000;
  *((_BYTE *)p_Next + 220) = v15;
  if ( (p_Next[37] || *((_DWORD *)p_Next + 88) || *((_DWORD *)p_Next + 89)) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  for ( i = 0; i < *((_BYTE *)p_Next + 128); HIDWORD(p_Next[11 * v19 + 142]) &= ~1u )
    v19 = i++;
  v20 = (void *)p_Next[424];
  *((_BYTE *)p_Next + 128) = 0;
  if ( v20 )
  {
    ExFreePoolWithTag(v20, 0);
    p_Next[424] = 0;
    *((_DWORD *)p_Next + 850) = 0;
  }
  if ( (p_Next[417] & 1) != 0 )
  {
    v21 = (void *)p_Next[416];
    if ( v21 )
      ExFreePoolWithTag(v21, 0);
  }
  *((_DWORD *)p_Next + 835) = 32;
  p_Next[416] = p_Next + 418;
  *((_DWORD *)p_Next + 829) = v31;
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
  v22 = (void *)p_Next[108];
  if ( v22 )
  {
    ExFreePoolWithTag(v22, 0);
    p_Next[108] = 0;
  }
  if ( v17 )
  {
    CmsReservedPool::FreeToPool((CmsReservedPool *)(v16 + 160), p_Next);
  }
  else
  {
    v23 = (struct _SLIST_ENTRY *)(p_Next - 2);
    v24 = *(p_Next - 2);
    if ( !v24 )
      goto LABEL_47;
    if ( *(_BYTE *)(v24 + 8) )
    {
      v25 = (struct _NPAGED_LOOKASIDE_LIST *)(v24 + 64);
      if ( *(_BYTE *)(v24 + 9) )
        ExFreeToNPagedLookasideList(v25, v23);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v25, v23);
      goto LABEL_29;
    }
    v30 = *(_QWORD *)(v24 + 88);
    if ( (int)v30 < *(_DWORD *)(v24 + 80) || SHIDWORD(v30) >= (int)v30 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v24 + 64), v23);
      _InterlockedIncrement((volatile signed __int32 *)(v24 + 88));
    }
    else
    {
LABEL_47:
      ExFreePoolWithTag(v23, 0);
    }
  }
LABEL_29:
  v26 = _InterlockedExchangeAdd(a2[2], 0xFFFFFFFF);
  result = v26 - 1;
  if ( v26 == 1 )
    return KeSetEvent((PRKEVENT)a2[4], 0, 0);
  return result;
}

```

## disassembly

```asm
0x140055200  mov     [rsp+arg_18], rbx
0x140055205  mov     [rsp+arg_0], rcx
0x14005520a  push    rbp
0x14005520b  push    rsi
0x14005520c  push    rdi
0x14005520d  push    r12
0x14005520f  push    r13
0x140055211  push    r14
0x140055213  push    r15
0x140055215  sub     rsp, 40h
0x140055219  mov     rax, [rdx]
0x14005521c  mov     r14, rdx
0x14005521f  mov     r12d, [rdx+1Ch]
0x140055223  mov     r13d, [rdx+18h]
0x140055227  mov     rcx, [rax+18h]
0x14005522b  mov     [rsp+78h+arg_0], rcx
0x140055233  mov     rcx, [rax+10h]
0x140055237  mov     [rsp+78h+arg_8], rcx
0x14005523f  mov     rcx, [rax+8]
0x140055243  mov     rax, [rax]
0x140055246  mov     [rsp+78h+arg_10], rcx
0x14005524e  xor     ecx, ecx; ProcNumber
0x140055250  mov     r15, [rax]
0x140055253  mov     rdi, [r15+8]
0x140055257  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14005525e  nop     dword ptr [rax+rax+00h]
0x140055263  xor     edx, edx
0x140055265  mov     ebp, 0FFFFFFFFh
0x14005526a  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140055270  lea     rsi, [rdx+rdx*2]
0x140055274  shl     rsi, 6
0x140055278  add     rsi, cs:qword_140262408
0x14005527f  cmp     dword ptr [rsi], 0D50h
0x140055285  jnb     short loc_1400552BD
0x140055287  xor     esi, esi
0x140055289  mov     edx, 0D60h
0x14005528e  mov     ecx, 42h ; 'B'
0x140055293  mov     r8d, 6950534Dh
0x140055299  call    cs:__imp_ExAllocatePool2
0x1400552a0  nop     dword ptr [rax+rax+00h]
0x1400552a5  mov     rbx, rax
0x1400552a8  test    al, 0Fh
0x1400552aa  jz      loc_1401F4788
0x1400552b0  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1400552b7  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x1400552bd  cmp     byte ptr [rsi+8], 0
0x1400552c1  jnz     loc_1400555AC
0x1400552c7  mov     rcx, [rsi+58h]
0x1400552cb  mov     rax, rcx
0x1400552ce  shr     rax, 20h
0x1400552d2  cmp     ecx, eax
0x1400552d4  jle     short loc_1400552F2
0x1400552d6  nop
0x1400552d7  mov     ecx, ebp
0x1400552d9  lock xadd [rsi+58h], ecx
0x1400552de  nop
0x1400552df  dec     ecx
0x1400552e1  mov     eax, [rsi+5Ch]
0x1400552e4  cmp     ecx, eax
0x1400552e6  jge     loc_1400555CC
0x1400552ec  nop
0x1400552ed  lock inc dword ptr [rsi+58h]
0x1400552f1  nop
0x1400552f2  mov     edx, [rsi+4]
0x1400552f5  jmp     short loc_14005528E
0x1400552f7  test    rbx, rbx
0x1400552fa  jnz     loc_14005557F
0x140055300  lea     rcx, [rdi+0A0h]; this
0x140055307  call    ?AllocateFromPool@CmsReservedPool@@QEAAPEAXXZ; CmsReservedPool::AllocateFromPool(void)
0x14005530c  mov     rcx, rax; void *
0x14005530f  mov     rbx, rax
0x140055312  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x140055317  mov     esi, 10008000h
0x14005531c  mov     rdx, [rsp+78h+arg_8]
0x140055324  mov     rcx, rsi
0x140055327  mov     rax, [rsp+78h+arg_10]
0x14005532f  mov     r9d, r12d
0x140055332  mov     [rbx], rsi
0x140055335  mov     r8d, r13d
0x140055338  mov     [rbx+8], rdi
0x14005533c  or      rcx, [r15]
0x14005533f  movzx   edi, byte ptr [rbx+0DCh]
0x140055346  mov     [rbx], rcx
0x140055349  movzx   ecx, byte ptr [r15+0DCh]
0x140055351  mov     [rbx+0DCh], cl
0x140055357  mov     rcx, [rsp+78h+arg_0]
0x14005535f  mov     rdx, [rdx]
0x140055362  mov     rcx, [rcx]
0x140055365  mov     [rsp+78h+var_58], rcx
0x14005536a  mov     rcx, rbx
0x14005536d  call    _guard_dispatch_icall
0x140055372  xor     r9d, r9d; unsigned __int8
0x140055375  xor     r8d, r8d; struct _SmsLsn *
0x140055378  xor     edx, edx; unsigned __int8
0x14005537a  mov     rcx, rbx; this
0x14005537d  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x140055382  mov     r15, [rbx+8]
0x140055386  mov     [rbx], rsi
0x140055389  and     esi, 10000000h
0x14005538f  mov     [rbx+0DCh], dil
0x140055396  cmp     qword ptr [rbx+128h], 0
0x14005539e  jnz     loc_14005554F
0x1400553a4  cmp     dword ptr [rbx+160h], 0
0x1400553ab  jnz     loc_14005554F
0x1400553b1  cmp     dword ptr [rbx+164h], 0
0x1400553b8  jnz     loc_14005554F
0x1400553be  xor     dl, dl
0x1400553c0  cmp     [rbx+80h], dl
0x1400553c6  jbe     short loc_1400553E1
0x1400553c8  movzx   eax, dl
0x1400553cb  inc     dl
0x1400553cd  imul    rcx, rax, 58h ; 'X'
0x1400553d1  and     dword ptr [rcx+rbx+474h], 0FFFFFFFEh
0x1400553d9  cmp     dl, [rbx+80h]
0x1400553df  jb      short loc_1400553C8
0x1400553e1  mov     rcx, [rbx+0D40h]; P
0x1400553e8  mov     byte ptr [rbx+80h], 0
0x1400553ef  test    rcx, rcx
0x1400553f2  jnz     loc_1400555E9
0x1400553f8  xor     r12d, r12d
0x1400553fb  test    byte ptr [rbx+0D08h], 1
0x140055402  jz      short loc_14005541E
0x140055404  mov     rcx, [rbx+0D00h]; P
0x14005540b  test    rcx, rcx
0x14005540e  jz      short loc_14005541E
0x140055410  xor     edx, edx; Tag
0x140055412  call    cs:__imp_ExFreePoolWithTag
0x140055419  nop     dword ptr [rax+rax+00h]
0x14005541e  lea     rax, [rbx+0D10h]
0x140055425  mov     dword ptr [rbx+0D0Ch], 20h ; ' '
0x14005542f  mov     [rbx+0D00h], rax
0x140055436  lea     rcx, [rbx+0C90h]; this
0x14005543d  mov     eax, [rsp+78h+var_44]
0x140055441  xorps   xmm0, xmm0
0x140055444  mov     [rbx+0CF4h], eax
0x14005544a  movups  xmmword ptr [rbx+0CE0h], xmm0
0x140055451  mov     [rbx+0CF0h], r12d
0x140055458  mov     [rbx+0CF8h], r12
0x14005545f  mov     byte ptr [rbx+0D08h], 0
0x140055466  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x14005546b  lea     rcx, [rbx+0C40h]; this
0x140055472  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140055477  lea     rcx, [rbx+0BF0h]; this
0x14005547e  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140055483  lea     rcx, [rbx+0BA0h]; this
0x14005548a  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x14005548f  lea     rcx, [rbx+0B50h]; this
0x140055496  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x14005549b  lea     rcx, [rbx+0B00h]; this
0x1400554a2  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x1400554a7  cmp     qword ptr [rbx+400h], 0
0x1400554af  jnz     loc_140055596
0x1400554b5  mov     rcx, [rbx+360h]; P
0x1400554bc  test    rcx, rcx
0x1400554bf  jnz     loc_14005560D
0x1400554c5  test    rsi, rsi
0x1400554c8  jnz     loc_140055565
0x1400554ce  lea     r8, [rbx-10h]
0x1400554d2  mov     rbx, [rbx-10h]
0x1400554d6  test    rbx, rbx
0x1400554d9  jz      loc_140055643
0x1400554df  cmp     [rbx+8], sil
0x1400554e3  jz      loc_140055627
0x1400554e9  lea     rcx, [rbx+40h]; Lookaside
0x1400554ed  mov     rdx, r8; Entry
0x1400554f0  cmp     [rbx+9], sil
0x1400554f4  jz      short loc_140055541
0x1400554f6  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400554fd  nop     dword ptr [rax+rax+00h]
0x140055502  mov     rax, [r14+10h]
0x140055506  nop
0x140055507  lock xadd [rax], ebp
0x14005550b  lea     eax, [rbp-1]
0x14005550e  nop
0x14005550f  test    eax, eax
0x140055511  jnz     short loc_140055528
0x140055513  mov     rcx, [r14+20h]; Event
0x140055517  xor     r8d, r8d; Wait
0x14005551a  xor     edx, edx; Increment
0x14005551c  call    cs:__imp_KeSetEvent
0x140055523  nop     dword ptr [rax+rax+00h]
0x140055528  mov     rbx, [rsp+78h+arg_18]
0x140055530  add     rsp, 40h
0x140055534  pop     r15
0x140055536  pop     r14
0x140055538  pop     r13
0x14005553a  pop     r12
0x14005553c  pop     rdi
0x14005553d  pop     rsi
0x14005553e  pop     rbp
0x14005553f  retn
0x140055541  call    cs:__imp_ExFreeToPagedLookasideList
0x140055548  nop     dword ptr [rax+rax+00h]
0x14005554d  jmp     short loc_140055502
0x14005554f  mov     rax, cs:KdDebuggerEnabled
0x140055556  cmp     byte ptr [rax], 0
0x140055559  jz      loc_1400553BE
0x14005555f  int     3; Trap to Debugger
0x140055560  jmp     loc_1400553BE
0x140055565  lea     rcx, [r15+0A0h]; this
0x14005556c  mov     rdx, rbx; void *
0x14005556f  call    ?FreeToPool@CmsReservedPool@@QEAAEPEAX@Z; CmsReservedPool::FreeToPool(void *)
0x140055574  jmp     short loc_140055502
0x140055576  test    rbx, rbx
0x140055579  jz      loc_1400552F2
0x14005557f  mov     [rbx], rsi
0x140055582  add     rbx, 10h
0x140055586  jz      loc_140055300
0x14005558c  mov     esi, 8000h
0x140055591  jmp     loc_14005531C
0x140055596  mov     rax, cs:KdDebuggerEnabled
0x14005559d  cmp     byte ptr [rax], 0
0x1400555a0  jz      loc_1400554B5
0x1400555a6  int     3; Trap to Debugger
0x1400555a7  jmp     loc_1400554B5
0x1400555ac  cmp     byte ptr [rsi+9], 0
0x1400555b0  lea     rcx, [rsi+40h]; Lookaside
0x1400555b4  jz      loc_1401F476A
0x1400555ba  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400555c1  nop     dword ptr [rax+rax+00h]
0x1400555c6  nop
0x1400555c7  jmp     loc_1401F4776
0x1400555cc  test    ecx, ecx
0x1400555ce  js      loc_1400552EC
0x1400555d4  lea     rcx, [rsi+40h]; ListHead
0x1400555d8  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400555df  nop     dword ptr [rax+rax+00h]
0x1400555e4  mov     rbx, rax
0x1400555e7  jmp     short loc_140055576
0x1400555e9  xor     edx, edx; Tag
0x1400555eb  call    cs:__imp_ExFreePoolWithTag
0x1400555f2  nop     dword ptr [rax+rax+00h]
0x1400555f7  xor     r12d, r12d
0x1400555fa  mov     [rbx+0D40h], r12
0x140055601  mov     [rbx+0D48h], r12d
0x140055608  jmp     loc_1400553FB
0x14005560d  xor     edx, edx; Tag
0x14005560f  call    cs:__imp_ExFreePoolWithTag
0x140055616  nop     dword ptr [rax+rax+00h]
0x14005561b  mov     [rbx+360h], r12
0x140055622  jmp     loc_1400554C5
0x140055627  mov     rcx, [rbx+58h]
0x14005562b  cmp     ecx, [rbx+50h]
0x14005562e  jl      loc_1401F47A0
0x140055634  mov     rax, rcx
0x140055637  shr     rax, 20h
0x14005563b  cmp     eax, ecx
0x14005563d  jge     loc_1401F47A0
0x140055643  xor     edx, edx; Tag
0x140055645  mov     rcx, r8; P
0x140055648  call    cs:__imp_ExFreePoolWithTag
0x14005564f  nop     dword ptr [rax+rax+00h]
0x140055654  jmp     loc_140055502
0x1401f476a  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f4771  nop     dword ptr [rax+rax+00h]
0x1401f4776  lea     rcx, [rax+8]; void *
0x1401f477a  mov     rbx, rax
0x1401f477d  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x1401f4782  nop
0x1401f4783  jmp     loc_140055576
0x1401f4788  test    rax, rax
0x1401f478b  jz      loc_1400552F7
0x1401f4791  lea     rcx, [rax+10h]; void *
0x1401f4795  call    ?InitializeTransactionMemoryBuffer@CmsTransactionContext@@SAXPEAX@Z; CmsTransactionContext::InitializeTransactionMemoryBuffer(void *)
0x1401f479a  nop
0x1401f479b  jmp     loc_14005557F
0x1401f47a0  lea     rcx, [rbx+40h]; ListHead
0x1401f47a4  mov     rdx, r8; ListEntry
0x1401f47a7  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f47ae  nop     dword ptr [rax+rax+00h]
0x1401f47b3  nop
0x1401f47b4  lock inc dword ptr [rbx+58h]
0x1401f47b8  nop
0x1401f47b9  jmp     loc_140055502
```
