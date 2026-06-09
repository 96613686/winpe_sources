# CmsTransactionContext::ReuseTransaction(void)

- ea: `0x140035300`
- end: `0x140035864`
- name: `?ReuseTransaction@CmsTransactionContext@@QEAAXXZ`
- size: `1380`
- prototype: `void __fastcall(CmsTransactionContext *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140012b30`
- `0x1400340e0`

## callees

- `0x140024d20`
- `0x1400352e8`
- `0x140035300`
- `0x140036df0`
- `0x1400770d0`
- `0x140078bd0`
- `0x1401e9dc0`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140035448`
- `ntoskrnl!KdDebuggerEnabled` at `0x140035775`
- `ntoskrnl!KdDebuggerEnabled` at `0x14003578b`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400357a1`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400357cb`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400357fc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140035572`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140035572`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400355d7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400355d7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f1f0f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f1f0f`
- `ntoskrnl!ExReleaseFastResource` at `0x14003566a`
- `ntoskrnl!ExReleaseFastResource` at `0x14003566a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400357eb`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400357eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003539a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035853`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003539a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035853`

## pseudocode

```c
void __fastcall CmsTransactionContext::ReuseTransaction(CmsTransactionContext *this, struct CmsStream *a2)
{
  char *v2; // rsi
  char **v3; // rdi
  char *v5; // r14
  struct SmsPage **v6; // rbp
  _QWORD *v7; // rdi
  _QWORD **v8; // rsi
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  _QWORD *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  char v14; // si
  __int64 i; // rdi
  char *v16; // r14
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 j; // rdi
  __int64 v20; // rax
  __int64 v21; // rcx
  CmsVolumeContainer *v22; // rcx
  struct SmsUndoRecord *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rsi
  struct _SLIST_ENTRY *v26; // r8
  struct _NPAGED_LOOKASIDE_LIST *v27; // rcx
  void *v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  bool v33; // zf
  __int64 v34; // rcx
  char *v35; // rax
  char **v36; // rcx
  struct SmsPage *v37; // rax
  __int64 v38; // rcx

  v2 = (char *)this + 808;
  v3 = (char **)*((_QWORD *)this + 101);
  if ( v3 != (char **)((char *)this + 808) )
  {
    do
    {
      v5 = *v3;
      v6 = (struct SmsPage **)(v3 - 14);
      if ( v3 != (char **)112 )
      {
        if ( v6[19] )
          CmsVolume::Unpin(*((CmsVolumeContainer ***)this + 1), this, v6 + 19, 3u);
        v35 = *v3;
        if ( *v3 )
        {
          if ( *((char ***)v35 + 1) != v3 || (v36 = (char **)v3[1], *v36 != (char *)v3) )
LABEL_70:
            __fastfail(3u);
          *v36 = v35;
          *((_QWORD *)v35 + 1) = v36;
          *(_OWORD *)v3 = 0;
        }
        v37 = v6[16];
        v6[13] = 0;
        v6[12] = 0;
        if ( v37 )
          *(_QWORD *)v37 = 0;
      }
      v3 = (char **)v5;
    }
    while ( v5 != v2 );
  }
  if ( *((_DWORD *)this + 49) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v7 = (_QWORD *)((char *)this + 664);
  v8 = (_QWORD **)((char *)this + 792);
  while ( 1 )
  {
    v9 = *v8;
    if ( *v8 == v8 )
      break;
    if ( (_QWORD **)v9[1] != v8 )
      goto LABEL_70;
    v10 = (_QWORD *)*v9;
    if ( *(_QWORD **)(*v9 + 8LL) != v9 )
      goto LABEL_70;
    *v8 = v10;
    v10[1] = v8;
    v11 = v9 - 2;
    v12 = *(v9 - 1);
    if ( v12 )
      *(_DWORD *)(v12 + 76) &= ~1u;
    v11[1] = 0;
    *v11 = 0;
    if ( v11 )
      ExFreePoolWithTag(v11, 0);
  }
  for ( ; v7 != v8; v7 += 4 )
  {
    v13 = v7[1];
    if ( v13 )
      *(_DWORD *)(v13 + 76) &= ~1u;
    v7[1] = 0;
    *v7 = 0;
  }
  *((_DWORD *)this + 49) = 0;
  *((_QWORD *)this + 13) = 0;
  if ( *((_QWORD *)this + 21) )
  {
    CmsTransactionContext::ReleaseReserveAllocationMap(this, a2);
    *((_QWORD *)this + 21) = 0;
  }
  v14 = (*(_QWORD *)this & 0x4000000000000LL) != 0;
  *(_QWORD *)this &= 0x13C023BC97BC31uLL;
  if ( *((_BYTE *)this + 131) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  for ( i = *((unsigned __int8 *)this + 132); (unsigned int)i < 0xD; i = (unsigned int)(i + 1) )
  {
    v16 = (char *)this + 8 * i;
    v17 = *((_QWORD *)v16 + 53);
    if ( !v17 )
      break;
    if ( *((_BYTE *)this + 2 * i + 528) || *((_BYTE *)this + 2 * i + 529) )
      ExReleasePushLockEx(*(_QWORD *)(v17 + 112) + 88LL, 0);
    v29 = *((_QWORD *)v16 + 53);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v29 + 8), 0xFFFFFFFF) == 1 && v29 )
      (**(void (__fastcall ***)(__int64, __int64))v29)(v29, 1);
  }
  v18 = *((unsigned __int8 *)this + 132);
  *((_QWORD *)this + v18 + 53) = 0;
  *((_WORD *)this + v18 + 264) = 0;
  if ( (_BYTE)KdDebuggerEnabled && *((_BYTE *)this + 131) != *((_BYTE *)this + 130) )
    __debugbreak();
  for ( j = *((unsigned __int8 *)this + 131); (unsigned int)j < *((unsigned __int8 *)this + 133); j = (unsigned int)(j + 1) )
  {
    v30 = *((_QWORD *)this + j + 70);
    if ( !v30 )
      break;
    if ( v30 == *((_QWORD *)this + 15) )
      *((_QWORD *)this + 15) = 0;
    v31 = *((_QWORD *)this + j + 70);
    if ( (*(_BYTE *)(v31 + 14) & 0x40) != 0 || (*(_DWORD *)(*(_QWORD *)(v31 + 24) + 44LL) & 0x80u) != 0 )
    {
      v33 = (*((_DWORD *)this + 48))-- == 1;
      if ( v33 )
        *(_QWORD *)this &= ~0x20000000000uLL;
    }
    v32 = *(_QWORD *)(*((_QWORD *)this + j + 70) + 72LL) + 8LL;
    a2 = (CmsTransactionContext *)((char *)this + 88 * (unsigned int)j + 1064);
    if ( a2 )
    {
      v33 = (*((_DWORD *)a2 + 18))-- == 1;
      if ( !v33 )
        goto LABEL_57;
      *((_DWORD *)a2 + 19) &= ~2u;
    }
    else
    {
      a2 = 0;
    }
    ExReleaseFastResource(v32, a2);
LABEL_57:
    v34 = *((_QWORD *)this + j + 70);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v34 + 8), 0xFFFFFFFF) == 1 && v34 )
      (**(void (__fastcall ***)(__int64, __int64))v34)(v34, 1);
    *((_QWORD *)this + j + 70) = 0;
  }
  v20 = *((unsigned __int8 *)this + 131);
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + v20 + 70) = 0;
  v21 = *((_QWORD *)this + 1);
  *((_BYTE *)this + 133) = *((_BYTE *)this + 131);
  if ( v21 )
  {
    v22 = *(CmsVolumeContainer **)(v21 + 3336);
    if ( v22 )
      CmsVolumeContainer::ReleasePinnedContainersAtEndOfTransaction(v22, this, v14);
  }
  if ( *((_DWORD *)this + 88) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  if ( *((_DWORD *)this + 89) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  *((_QWORD *)this + 44) = 0;
  if ( *((_DWORD *)this + 48) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v23 = (struct SmsUndoRecord *)*((_QWORD *)this + 19);
  *((_QWORD *)this + 15) = 0;
  for ( *((_WORD *)this + 106) = 0; v23; v23 = (struct SmsUndoRecord *)*((_QWORD *)this + 19) )
  {
    *((_QWORD *)this + 19) = *(_QWORD *)v23;
    CmsBPlusTable::FreeUndoRecord(v23, a2);
  }
  *((_QWORD *)this + 20) = 0;
  v24 = *((_QWORD *)this + 34);
  if ( v24 )
  {
    if ( *((_BYTE *)this + 293) )
    {
      *((_BYTE *)this + 136) = 0;
    }
    else
    {
      v25 = *(_QWORD *)(v24 - 16);
      v26 = (struct _SLIST_ENTRY *)(v24 - 16);
      if ( !v25 )
        goto LABEL_91;
      if ( *(_BYTE *)(v25 + 8) )
      {
        v27 = (struct _NPAGED_LOOKASIDE_LIST *)(v25 + 64);
        v28 = (void *)(v24 - 16);
        if ( *(_BYTE *)(v25 + 9) )
          ExFreeToNPagedLookasideList(v27, v28);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v27, v28);
        goto LABEL_39;
      }
      v38 = *(_QWORD *)(v25 + 88);
      if ( (int)v38 < *(_DWORD *)(v25 + 80) || SHIDWORD(v38) >= (int)v38 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v25 + 64), v26);
        _InterlockedIncrement((volatile signed __int32 *)(v25 + 88));
      }
      else
      {
LABEL_91:
        ExFreePoolWithTag(v26, 0);
      }
    }
LABEL_39:
    CmsTransactionContext::_unnamed_type_RunCopies_::Reset((char *)this + 272);
  }
  *((_BYTE *)this + 129) = 0;
  *((_BYTE *)this + 135) = 0;
  *((_QWORD *)this + 14) = 0;
}

```

## disassembly

```asm
0x140035300  push    rbx
0x140035302  push    rbp
0x140035303  push    rsi
0x140035304  push    rdi
0x140035305  push    r14
0x140035307  push    r15
0x140035309  sub     rsp, 28h
0x14003530d  lea     rsi, [rcx+328h]
0x140035314  xor     r15d, r15d
0x140035317  mov     rdi, [rsi]
0x14003531a  mov     rbx, rcx
0x14003531d  cmp     rdi, rsi
0x140035320  jz      short loc_14003533A
0x140035322  mov     r14, [rdi]
0x140035325  lea     rbp, [rdi-70h]
0x140035329  test    rbp, rbp
0x14003532c  jnz     loc_1400356D5
0x140035332  mov     rdi, r14
0x140035335  cmp     r14, rsi
0x140035338  jnz     short loc_140035322
0x14003533a  cmp     [rbx+0C4h], r15d
0x140035341  jnz     loc_140035775
0x140035347  lea     rdi, [rbx+298h]
0x14003534e  lea     rsi, [rdi+80h]
0x140035355  mov     rax, [rsi]
0x140035358  cmp     rax, rsi
0x14003535b  jz      short loc_1400353A8
0x14003535d  cmp     [rax+8], rsi
0x140035361  jnz     loc_140035725
0x140035367  mov     rcx, [rax]
0x14003536a  cmp     [rcx+8], rax
0x14003536e  jnz     loc_140035725
0x140035374  mov     [rsi], rcx
0x140035377  mov     [rcx+8], rsi
0x14003537b  lea     rcx, [rax-10h]; P
0x14003537f  mov     rax, [rax-8]
0x140035383  test    rax, rax
0x140035386  jz      short loc_14003538C
0x140035388  and     dword ptr [rax+4Ch], 0FFFFFFFEh
0x14003538c  mov     [rcx+8], r15
0x140035390  mov     [rcx], r15
0x140035393  test    rcx, rcx
0x140035396  jz      short loc_140035355
0x140035398  xor     edx, edx; Tag
0x14003539a  call    cs:__imp_ExFreePoolWithTag
0x1400353a1  nop     dword ptr [rax+rax+00h]
0x1400353a6  jmp     short loc_140035355
0x1400353a8  cmp     rdi, rsi
0x1400353ab  jz      short loc_1400353CD
0x1400353ad  nop     dword ptr [rax]
0x1400353b0  mov     rax, [rdi+8]
0x1400353b4  test    rax, rax
0x1400353b7  jz      short loc_1400353BD
0x1400353b9  and     dword ptr [rax+4Ch], 0FFFFFFFEh
0x1400353bd  mov     [rdi+8], r15
0x1400353c1  mov     [rdi], r15
0x1400353c4  add     rdi, 20h ; ' '
0x1400353c8  cmp     rdi, rsi
0x1400353cb  jnz     short loc_1400353B0
0x1400353cd  mov     [rbx+0C4h], r15d
0x1400353d4  mov     [rbx+68h], r15
0x1400353d8  cmp     [rbx+0A8h], r15
0x1400353df  jnz     loc_1400357B7
0x1400353e5  mov     rax, [rbx]
0x1400353e8  mov     rcx, 13C023BC97BC31h
0x1400353f2  mov     rsi, rax
0x1400353f5  and     rax, rcx
0x1400353f8  shr     rsi, 32h
0x1400353fc  and     sil, 1
0x140035400  mov     [rbx], rax
0x140035403  cmp     [rbx+83h], r15b
0x14003540a  jnz     loc_1400357CB
0x140035410  movzx   edi, byte ptr [rbx+84h]
0x140035417  cmp     edi, 0Dh
0x14003541a  jnb     short loc_140035430
0x14003541c  lea     r14, [rbx+rdi*8]
0x140035420  mov     rcx, [r14+1A8h]
0x140035427  test    rcx, rcx
0x14003542a  jnz     loc_14003558C
0x140035430  movzx   eax, byte ptr [rbx+84h]
0x140035437  mov     [rbx+rax*8+1A8h], r15
0x14003543f  mov     [rbx+rax*2+210h], r15w
0x140035448  mov     rax, cs:KdDebuggerEnabled
0x14003544f  cmp     [rax], r15b
0x140035452  jnz     loc_140035740
0x140035458  movzx   edi, byte ptr [rbx+83h]
0x14003545f  movzx   eax, byte ptr [rbx+85h]
0x140035466  cmp     edi, eax
0x140035468  jb      loc_1400355F4
0x14003546e  movzx   eax, byte ptr [rbx+83h]
0x140035475  mov     [rbx+68h], r15
0x140035479  mov     [rbx+rax*8+230h], r15
0x140035481  mov     rcx, [rbx+8]
0x140035485  movzx   eax, byte ptr [rbx+83h]
0x14003548c  mov     [rbx+85h], al
0x140035492  test    rcx, rcx
0x140035495  jz      short loc_1400354AF
0x140035497  mov     rcx, [rcx+0D08h]; this
0x14003549e  test    rcx, rcx
0x1400354a1  jz      short loc_1400354AF
0x1400354a3  movzx   r8d, sil; unsigned __int8
0x1400354a7  mov     rdx, rbx; struct CmsTransactionContext *
0x1400354aa  call    ?ReleasePinnedContainersAtEndOfTransaction@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@E@Z; CmsVolumeContainer::ReleasePinnedContainersAtEndOfTransaction(CmsTransactionContext *,uchar)
0x1400354af  cmp     [rbx+160h], r15d
0x1400354b6  jnz     loc_14003578B
0x1400354bc  cmp     [rbx+164h], r15d
0x1400354c3  jnz     loc_1400357A1
0x1400354c9  mov     [rbx+160h], r15
0x1400354d0  cmp     [rbx+0C0h], r15d
0x1400354d7  jnz     loc_1400357FC
0x1400354dd  mov     rcx, [rbx+98h]; struct SmsUndoRecord *
0x1400354e4  mov     [rbx+78h], r15
0x1400354e8  mov     [rbx+0D4h], r15w
0x1400354f0  test    rcx, rcx
0x1400354f3  jnz     loc_140035812
0x1400354f9  mov     [rbx+0A0h], r15
0x140035500  mov     rax, [rbx+110h]
0x140035507  test    rax, rax
0x14003550a  jnz     short loc_14003552C
0x14003550c  mov     [rbx+81h], r15b
0x140035513  mov     [rbx+87h], r15b
0x14003551a  mov     [rbx+70h], r15
0x14003551e  add     rsp, 28h
0x140035522  pop     r15
0x140035524  pop     r14
0x140035526  pop     rdi
0x140035527  pop     rsi
0x140035528  pop     rbp
0x140035529  pop     rbx
0x14003552a  retn
0x14003552c  cmp     [rbx+125h], r15b
0x140035533  jz      short loc_14003554A
0x140035535  mov     [rbx+88h], r15b
0x14003553c  lea     rcx, [rbx+110h]
0x140035543  call    CmsTransactionContext___unnamed_type_RunCopies___Reset
0x140035548  jmp     short loc_14003550C
0x14003554a  mov     rsi, [rax-10h]
0x14003554e  lea     r8, [rax-10h]
0x140035552  test    rsi, rsi
0x140035555  jz      loc_14003584E
0x14003555b  cmp     [rsi+8], r15b
0x14003555f  jz      loc_140035832
0x140035565  lea     rcx, [rsi+40h]; Lookaside
0x140035569  mov     rdx, r8; Entry
0x14003556c  cmp     [rsi+9], r15b
0x140035570  jz      short loc_1400355D7
0x140035572  call    cs:__imp_ExFreeToNPagedLookasideList
0x140035579  nop     dword ptr [rax+rax+00h]
0x14003557e  lea     rcx, [rbx+110h]
0x140035585  call    CmsTransactionContext___unnamed_type_RunCopies___Reset
0x14003558a  jmp     short loc_14003550C
0x14003558c  cmp     [rbx+rdi*2+210h], r15b
0x140035594  jnz     loc_1400357E1
0x14003559a  cmp     [rbx+rdi*2+211h], r15b
0x1400355a2  jnz     loc_1400357E1
0x1400355a8  mov     rcx, [r14+1A8h]
0x1400355af  mov     eax, 0FFFFFFFFh
0x1400355b4  lock xadd [rcx+8], eax
0x1400355b9  cmp     eax, 1
0x1400355bc  jnz     short loc_1400355C7
0x1400355be  test    rcx, rcx
0x1400355c1  jnz     loc_1400356C0
0x1400355c7  inc     edi
0x1400355c9  cmp     edi, 0Dh
0x1400355cc  jnb     loc_140035430
0x1400355d2  jmp     loc_14003541C
0x1400355d7  call    cs:__imp_ExFreeToPagedLookasideList
0x1400355de  nop     dword ptr [rax+rax+00h]
0x1400355e3  lea     rcx, [rbx+110h]
0x1400355ea  call    CmsTransactionContext___unnamed_type_RunCopies___Reset
0x1400355ef  jmp     loc_14003550C
0x1400355f4  mov     r14, 0FFFFFDFFFFFFFFFFh
0x1400355fe  mov     rax, [rbx+rdi*8+230h]
0x140035606  mov     ebp, edi
0x140035608  test    rax, rax
0x14003560b  jz      loc_14003546E
0x140035611  cmp     rax, [rbx+78h]
0x140035615  jnz     short loc_14003561B
0x140035617  mov     [rbx+78h], r15
0x14003561b  mov     rcx, [rbx+rdi*8+230h]
0x140035623  test    byte ptr [rcx+0Eh], 40h
0x140035627  jnz     loc_140035760
0x14003562d  mov     rax, [rcx+18h]
0x140035631  mov     ecx, [rax+2Ch]
0x140035634  test    cl, cl
0x140035636  js      loc_140035760
0x14003563c  mov     rax, [rbx+rdi*8+230h]
0x140035644  imul    rdx, rbp, 58h ; 'X'
0x140035648  mov     rcx, [rax+48h]
0x14003564c  add     rdx, 428h
0x140035653  add     rcx, 8
0x140035657  add     rdx, rbx
0x14003565a  jz      loc_140035759
0x140035660  add     dword ptr [rdx+48h], 0FFFFFFFFh
0x140035664  jnz     short loc_140035676
0x140035666  and     dword ptr [rdx+4Ch], 0FFFFFFFDh
0x14003566a  call    cs:__imp_ExReleaseFastResource
0x140035671  nop     dword ptr [rax+rax+00h]
0x140035676  mov     rcx, [rbx+rdi*8+230h]
0x14003567e  mov     eax, 0FFFFFFFFh
0x140035683  lock xadd [rcx+8], eax
0x140035688  cmp     eax, 1
0x14003568b  jnz     short loc_1400356A2
0x14003568d  test    rcx, rcx
0x140035690  jz      short loc_1400356A2
0x140035692  mov     rax, [rcx]
0x140035695  mov     edx, 1
0x14003569a  mov     rax, [rax]
0x14003569d  call    _guard_dispatch_icall
0x1400356a2  mov     [rbx+rdi*8+230h], r15
0x1400356aa  inc     edi
0x1400356ac  movzx   eax, byte ptr [rbx+85h]
0x1400356b3  cmp     edi, eax
0x1400356b5  jb      loc_1400355FE
0x1400356bb  jmp     loc_14003546E
0x1400356c0  mov     rax, [rcx]
0x1400356c3  mov     edx, 1
0x1400356c8  mov     rax, [rax]
0x1400356cb  call    _guard_dispatch_icall
0x1400356d0  jmp     loc_1400355C7
0x1400356d5  lea     r8, [rbp+98h]; struct SmsPage **
0x1400356dc  cmp     [r8], r15
0x1400356df  jnz     short loc_14003572C
0x1400356e1  mov     rax, [rdi]
0x1400356e4  test    rax, rax
0x1400356e7  jz      short loc_140035705
0x1400356e9  cmp     [rax+8], rdi
0x1400356ed  jnz     short loc_140035725
0x1400356ef  mov     rcx, [rdi+8]
0x1400356f3  cmp     [rcx], rdi
0x1400356f6  jnz     short loc_140035725
0x1400356f8  mov     [rcx], rax
0x1400356fb  xorps   xmm0, xmm0
0x1400356fe  mov     [rax+8], rcx
0x140035702  movups  xmmword ptr [rdi], xmm0
0x140035705  mov     rax, [rbp+80h]
0x14003570c  mov     [rbp+68h], r15
0x140035710  mov     [rbp+60h], r15
0x140035714  test    rax, rax
0x140035717  jz      loc_140035332
0x14003571d  mov     [rax], r15
0x140035720  jmp     loc_140035332
0x140035725  mov     ecx, 3
0x14003572a  int     29h; Win8: RtlFailFast(ecx)
0x14003572c  mov     rcx, [rbx+8]; this
0x140035730  mov     r9d, 3; unsigned int
0x140035736  mov     rdx, rbx; struct CmsTransactionCore *
0x140035739  call    ?Unpin@CmsVolume@@QEAAXPEAVCmsTransactionCore@@PEAPEAUSmsPage@@K@Z; CmsVolume::Unpin(CmsTransactionCore *,SmsPage * *,ulong)
0x14003573e  jmp     short loc_1400356E1
0x140035740  movzx   eax, byte ptr [rbx+82h]
0x140035747  cmp     [rbx+83h], al
0x14003574d  jz      loc_140035458
0x140035753  int     3; Trap to Debugger
0x140035754  jmp     loc_140035458
0x140035759  xor     edx, edx; struct CmsStream *
0x14003575b  jmp     loc_14003566A
0x140035760  add     dword ptr [rbx+0C0h], 0FFFFFFFFh
0x140035767  jnz     loc_14003563C
0x14003576d  and     [rbx], r14
0x140035770  jmp     loc_14003563C
0x140035775  mov     rax, cs:KdDebuggerEnabled
0x14003577c  cmp     [rax], r15b
0x14003577f  jz      loc_140035347
0x140035785  int     3; Trap to Debugger
0x140035786  jmp     loc_140035347
0x14003578b  mov     rax, cs:KdDebuggerEnabled
0x140035792  cmp     [rax], r15b
0x140035795  jz      loc_1400354BC
0x14003579b  int     3; Trap to Debugger
0x14003579c  jmp     loc_1400354BC
0x1400357a1  mov     rax, cs:KdDebuggerEnabled
0x1400357a8  cmp     [rax], r15b
0x1400357ab  jz      loc_1400354C9
0x1400357b1  int     3; Trap to Debugger
0x1400357b2  jmp     loc_1400354C9
0x1400357b7  mov     rcx, rbx; this
0x1400357ba  call    ?ReleaseReserveAllocationMap@CmsTransactionContext@@QEAAXPEAVCmsStream@@@Z; CmsTransactionContext::ReleaseReserveAllocationMap(CmsStream *)
0x1400357bf  mov     [rbx+0A8h], r15
0x1400357c6  jmp     loc_1400353E5
0x1400357cb  mov     rax, cs:KdDebuggerEnabled
0x1400357d2  cmp     [rax], r15b
0x1400357d5  jz      loc_140035410
0x1400357db  int     3; Trap to Debugger
0x1400357dc  jmp     loc_140035410
0x1400357e1  mov     rcx, [rcx+70h]
0x1400357e5  xor     edx, edx
0x1400357e7  add     rcx, 58h ; 'X'
0x1400357eb  call    cs:__imp_ExReleasePushLockEx
0x1400357f2  nop     dword ptr [rax+rax+00h]
0x1400357f7  jmp     loc_1400355A8
0x1400357fc  mov     rax, cs:KdDebuggerEnabled
0x140035803  cmp     [rax], r15b
0x140035806  jz      loc_1400354DD
0x14003580c  int     3; Trap to Debugger
0x14003580d  jmp     loc_1400354DD
0x140035812  mov     rax, [rcx]
0x140035815  mov     [rbx+98h], rax
0x14003581c  call    ?FreeUndoRecord@CmsBPlusTable@@SAXPEAUSmsUndoRecord@@PEAVCmsTransactionContext@@K@Z; CmsBPlusTable::FreeUndoRecord(SmsUndoRecord *,CmsTransactionContext *,ulong)
0x140035821  mov     rcx, [rbx+98h]
0x140035828  test    rcx, rcx
  ... truncated ...
```
