# RxDereferenceAndDeleteRxContext_Real

- ea: `0x1400037e0`
- end: `0x140003ad8`
- name: `RxDereferenceAndDeleteRxContext_Real`
- size: `760`
- prototype: `void __stdcall(PRX_CONTEXT RxContext)`
- caller_count: `28`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400013b0`
- `0x140001ae0`
- `0x140001b70`
- `0x1400027b0`
- `0x1400031a0`
- `0x140008910`
- `0x14000bbf0`
- `0x14000d1e0`
- `0x140012880`
- `0x140016890`
- `0x140017af0`
- `0x140024cf0`
- `0x140024e20`
- `0x140047970`
- `0x14004bed8`
- `0x14004cac0`
- `0x14004d498`
- `0x14004dff0`
- `0x14004fef0`
- `0x140050414`
- `0x1400511d0`
- `0x140057a80`
- `0x140063090`
- `0x14006e0d0`
- `0x140072d20`
- `0x140075940`
- `0x140075b10`
- `0x140077390`

## callees

- `0x1400037e0`
- `0x140003eb0`
- `0x140016e70`
- `0x140017370`
- `0x140025d00`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140003a05`
- `ntoskrnl!KeSetEvent` at `0x140003aa0`
- `ntoskrnl!KeSetEvent` at `0x140003a05`
- `ntoskrnl!KeSetEvent` at `0x140003aa0`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140003a88`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140003a88`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400038fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003913`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400039d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400038fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003913`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400039d9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000396d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000396d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000385c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000385c`

## pseudocode

```c
void __stdcall RxDereferenceAndDeleteRxContext_Real(PRX_CONTEXT RxContext)
{
  char v1; // si
  bool v3; // bp
  __int64 v4; // rdx
  __int64 v5; // r13
  KSPIN_LOCK *v6; // r14
  KIRQL v7; // r15
  int v8; // edi
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v10; // rax
  int RdbssDbgExtension; // esi
  LIST_ENTRY *p_ContextListEntry; // rax
  struct _RX_CONTEXT *Flink; // rcx
  struct _LIST_ENTRY *v14; // rdx
  __int64 *v15; // rcx
  ULONGLONG v16; // rdi
  __int64 v17; // rax
  __int64 *v18; // rdx
  PNON_PAGED_FCB NonPagedFcb; // r10
  struct _LIST_ENTRY *i; // rax
  struct _KEVENT *v21; // [rsp+80h] [rbp+8h]

  v1 = 0;
  v3 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_d95d50ceaf3b33ad81be3468c396533e_Traceguids, RxContext);
  }
  if ( RxContext )
    v4 = ((_BYTE)RxActiveContextNodeBucketSize
        * (unsigned __int8)LOWORD(RxContext->LowIoContext.ParamsFor.ReadWrite.Flags)
        + (unsigned __int8)(WORD1(RxContext->LowIoContext.ParamsFor.Locks.Length)
                          % (unsigned int)RxActiveContextNodeBucketSize))
       & 0x3F;
  else
    v4 = 0;
  v5 = 24 * v4;
  v6 = (KSPIN_LOCK *)&qword_140035700[24 * v4];
  v7 = KeAcquireSpinLockRaiseToDpc(v6);
  v8 = _InterlockedDecrement((volatile signed __int32 *)&RxContext->ReferenceCount);
  if ( v8 )
  {
LABEL_15:
    KeReleaseSpinLock(v6, v7);
    if ( v8 > 0 )
      return;
    goto LABEL_16;
  }
  Blink = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
  if ( Blink )
  {
    v10 = Blink[42].Blink;
    if ( v10 )
      ((void (__fastcall *)(PRX_CONTEXT))v10)(RxContext);
  }
  RdbssDbgExtension = (int)RxContext->RdbssDbgExtension;
  p_ContextListEntry = &RxContext->ContextListEntry;
  Flink = (struct _RX_CONTEXT *)RxContext->ContextListEntry.Flink;
  v3 = (RdbssDbgExtension & 0x8000000) != 0;
  if ( Flink != (struct _RX_CONTEXT *)&RxContext->ContextListEntry )
  {
    if ( Flink->ContextListEntry.Flink != p_ContextListEntry )
      goto LABEL_25;
    v14 = RxContext->ContextListEntry.Blink;
    if ( v14->Flink != p_ContextListEntry )
      goto LABEL_25;
    v14->Flink = (struct _LIST_ENTRY *)Flink;
    Flink->ContextListEntry.Flink = v14;
  }
  v1 = RdbssDbgExtension & 1;
  v15 = (__int64 *)qword_1400356D0[v5];
  if ( &qword_1400356D0[v5] != v15 )
  {
    while ( 1 )
    {
      NonPagedFcb = RxContext->NonPagedFcb;
      v21 = (struct _KEVENT *)(v15 - 46);
      if ( (PNON_PAGED_FCB)*(v15 - 36) == NonPagedFcb )
        break;
      v15 = (__int64 *)*v15;
      if ( &qword_1400356D0[v5] == v15 )
        goto LABEL_15;
    }
    for ( i = (&RxActiveContexts.Flink)[v5]; (LIST_ENTRY *)((char *)&RxActiveContexts + v5 * 8) != i; i = i->Flink )
    {
      if ( v15 - 46 != (__int64 *)&i[-1].Blink && (PNON_PAGED_FCB)i[4].Blink == NonPagedFcb )
        goto LABEL_14;
    }
    v17 = *v15;
    if ( *(__int64 **)(*v15 + 8) == v15 )
    {
      v18 = (__int64 *)v15[1];
      if ( (__int64 *)*v18 == v15 )
      {
        *v18 = v17;
        *(_QWORD *)(v17 + 8) = v18;
        KeReleaseSpinLock(v6, v7);
        RxContext->ReferenceCount = 0;
        v21[5].Header.LockNV &= ~0x100000u;
        KeSetEvent(v21 + 16, 0, 0);
        goto LABEL_17;
      }
    }
LABEL_25:
    __fastfail(3u);
  }
LABEL_14:
  KeReleaseSpinLock(v6, v7);
LABEL_16:
  RxContext->ReferenceCount = 0;
LABEL_17:
  if ( v1 )
  {
    v16 = RxContextLookasideList.L.ListHead.Alignment
        + ((unsigned __int64)WORD1(RxContext->LowIoContext.ParamsFor.Locks.Length) << 7);
    if ( !*(_BYTE *)(v16 + 304) )
      PplpLazyInitializeLookasideList(RxContextLookasideList.L.ListHead.Alignment, v16 + 192);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v16 + 192), RxContext);
  }
  else if ( v3 )
  {
    ExpInterlockedPushEntrySList(&MustSucceedRxContextSList, (PSLIST_ENTRY)RxContext);
    KeSetEvent(&MustSucceedRxContextEvent, 0, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_d95d50ceaf3b33ad81be3468c396533e_Traceguids, RxContext);
  }
}

```

## disassembly

```asm
0x1400037e0  push    rbx
0x1400037e2  push    rbp
0x1400037e3  push    rsi
0x1400037e4  push    rdi
0x1400037e5  push    r12
0x1400037e7  push    r13
0x1400037e9  push    r14
0x1400037eb  push    r15
0x1400037ed  sub     rsp, 38h
0x1400037f1  xor     sil, sil
0x1400037f4  mov     rbx, rcx
0x1400037f7  xor     bpl, bpl
0x1400037fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140003801  lea     rax, WPP_GLOBAL_Control
0x140003808  cmp     rcx, rax
0x14000380b  jz      short loc_140003818
0x14000380d  mov     eax, [rcx+2Ch]
0x140003810  test    al, 2
0x140003812  jnz     loc_140003A16
0x140003818  test    rbx, rbx
0x14000381b  jz      loc_140003A44
0x140003821  movzx   eax, word ptr [rbx+1BAh]
0x140003828  xor     edx, edx
0x14000382a  div     cs:RxActiveContextNodeBucketSize
0x140003830  movzx   eax, word ptr [rbx+1B8h]
0x140003837  imul    eax, cs:RxActiveContextNodeBucketSize
0x14000383e  add     edx, eax
0x140003840  and     edx, 3Fh
0x140003843  lea     r13, [rdx+rdx*2]
0x140003847  shl     r13, 6
0x14000384b  lea     r14, RxActiveContexts
0x140003852  add     r14, 40h ; '@'
0x140003856  add     r14, r13
0x140003859  mov     rcx, r14; SpinLock
0x14000385c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003863  nop     dword ptr [rax+rax+00h]
0x140003868  movzx   r15d, al
0x14000386c  mov     edi, 0FFFFFFFFh
0x140003871  lock xadd [rbx+4], edi
0x140003876  sub     edi, 1
0x140003879  jnz     loc_14000390C
0x14000387f  mov     rax, [rbx+50h]
0x140003883  mov     rcx, [rax+160h]
0x14000388a  test    rcx, rcx
0x14000388d  jz      short loc_1400038A3
0x14000388f  mov     rax, [rcx+2A8h]
0x140003896  test    rax, rax
0x140003899  jz      short loc_1400038A3
0x14000389b  mov     rcx, rbx
0x14000389e  call    _guard_dispatch_icall
0x1400038a3  mov     esi, [rbx+78h]
0x1400038a6  lea     rax, [rbx+8]
0x1400038aa  mov     rcx, [rax]
0x1400038ad  mov     ebp, esi
0x1400038af  shr     ebp, 1Bh
0x1400038b2  and     bpl, 1
0x1400038b6  cmp     rcx, rax
0x1400038b9  jz      short loc_1400038D9
0x1400038bb  cmp     [rcx+8], rax
0x1400038bf  jnz     loc_1400039AF
0x1400038c5  mov     rdx, [rax+8]
0x1400038c9  cmp     [rdx], rax
0x1400038cc  jnz     loc_1400039AF
0x1400038d2  mov     [rdx], rcx
0x1400038d5  mov     [rcx+8], rdx
0x1400038d9  lea     r8, RxActiveContexts
0x1400038e0  and     sil, 1
0x1400038e4  lea     rax, [r8+10h]
0x1400038e8  add     rax, r13
0x1400038eb  mov     rcx, [rax]
0x1400038ee  cmp     rax, rcx
0x1400038f1  jnz     loc_140003A4B
0x1400038f7  movzx   edx, r15b; NewIrql
0x1400038fb  mov     rcx, r14; SpinLock
0x1400038fe  call    cs:__imp_KeReleaseSpinLock
0x140003905  nop     dword ptr [rax+rax+00h]
0x14000390a  jmp     short loc_140003927
0x14000390c  movzx   edx, r15b; NewIrql
0x140003910  mov     rcx, r14; SpinLock
0x140003913  call    cs:__imp_KeReleaseSpinLock
0x14000391a  nop     dword ptr [rax+rax+00h]
0x14000391f  test    edi, edi
0x140003921  jg      loc_1400039AB
0x140003927  mov     dword ptr [rbx+4], 0
0x14000392e  test    sil, sil
0x140003931  jz      loc_140003A75
0x140003937  movzx   edi, word ptr [rbx+1BAh]
0x14000393e  mov     rcx, qword ptr cs:RxContextLookasideList.L
0x140003945  shl     rdi, 7
0x140003949  add     rdi, rcx
0x14000394c  movzx   eax, byte ptr [rdi+130h]
0x140003953  test    al, al
0x140003955  jnz     short loc_140003963
0x140003957  lea     rdx, [rdi+0C0h]
0x14000395e  call    PplpLazyInitializeLookasideList
0x140003963  mov     rdx, rbx; Entry
0x140003966  lea     rcx, [rdi+0C0h]; Lookaside
0x14000396d  call    cs:__imp_ExFreeToLookasideListEx
0x140003974  nop     dword ptr [rax+rax+00h]
0x140003979  mov     rcx, cs:WPP_GLOBAL_Control
0x140003980  lea     rax, WPP_GLOBAL_Control
0x140003987  cmp     rcx, rax
0x14000398a  jz      short loc_140003997
0x14000398c  mov     eax, [rcx+2Ch]
0x14000398f  test    al, 2
0x140003991  jnz     loc_140003AB1
0x140003997  mov     al, 1
0x140003999  add     rsp, 38h
0x14000399d  pop     r15
0x14000399f  pop     r14
0x1400039a1  pop     r13
0x1400039a3  pop     r12
0x1400039a5  pop     rdi
0x1400039a6  pop     rsi
0x1400039a7  pop     rbp
0x1400039a8  pop     rbx
0x1400039a9  retn
0x1400039ab  xor     al, al
0x1400039ad  jmp     short loc_140003999
0x1400039af  mov     ecx, 3
0x1400039b4  int     29h; Win8: RtlFailFast(ecx)
0x1400039b6  mov     rax, [rcx]
0x1400039b9  cmp     [rax+8], rcx
0x1400039bd  jnz     short loc_1400039AF
0x1400039bf  mov     rdx, [rcx+8]
0x1400039c3  cmp     [rdx], rcx
0x1400039c6  jnz     short loc_1400039AF
0x1400039c8  mov     [rdx], rax
0x1400039cb  cmp     rdx, rax
0x1400039ce  mov     [rax+8], rdx
0x1400039d2  mov     rcx, r14; SpinLock
0x1400039d5  movzx   edx, r15b; NewIrql
0x1400039d9  call    cs:__imp_KeReleaseSpinLock
0x1400039e0  nop     dword ptr [rax+rax+00h]
0x1400039e5  mov     rcx, [rsp+78h+arg_0]
0x1400039ed  xor     eax, eax
0x1400039ef  mov     [rbx+4], eax
0x1400039f2  xor     r8d, r8d; Wait
0x1400039f5  xor     edx, edx; Increment
0x1400039f7  and     dword ptr [rcx+78h], 0FFEFFFFFh
0x1400039fe  add     rcx, 180h; Event
0x140003a05  call    cs:__imp_KeSetEvent
0x140003a0c  nop     dword ptr [rax+rax+00h]
0x140003a11  jmp     loc_14000392E
0x140003a16  cmp     byte ptr [rcx+29h], 4
0x140003a1a  jb      loc_140003818
0x140003a20  mov     eax, [rbx+4]
0x140003a23  lea     r8, WPP_d95d50ceaf3b33ad81be3468c396533e_Traceguids
0x140003a2a  mov     rcx, [rcx+18h]
0x140003a2e  mov     edx, 0Ch
0x140003a33  mov     r9, rbx
0x140003a36  mov     [rsp+78h+var_58], eax
0x140003a3a  call    WPP_SF_qD
0x140003a3f  jmp     loc_140003818
0x140003a44  xor     edx, edx
0x140003a46  jmp     loc_140003843
0x140003a4b  mov     r10, [rbx+50h]
0x140003a4f  lea     rdx, [rcx-170h]
0x140003a56  mov     [rsp+78h+arg_0], rdx
0x140003a5e  cmp     [rdx+50h], r10
0x140003a62  jnz     loc_140027010
0x140003a68  mov     rax, [r8+r13]
0x140003a6c  lea     r9, [r8+r13]
0x140003a70  jmp     loc_140027021
0x140003a75  test    bpl, bpl
0x140003a78  jz      loc_140003979
0x140003a7e  mov     rdx, rbx; ListEntry
0x140003a81  lea     rcx, MustSucceedRxContextSList; ListHead
0x140003a88  call    cs:__imp_ExpInterlockedPushEntrySList
0x140003a8f  nop     dword ptr [rax+rax+00h]
0x140003a94  xor     r8d, r8d; Wait
0x140003a97  lea     rcx, MustSucceedRxContextEvent; Event
0x140003a9e  xor     edx, edx; Increment
0x140003aa0  call    cs:__imp_KeSetEvent
0x140003aa7  nop     dword ptr [rax+rax+00h]
0x140003aac  jmp     loc_140003979
0x140003ab1  cmp     byte ptr [rcx+29h], 4
0x140003ab5  jb      loc_140003997
0x140003abb  mov     rcx, [rcx+18h]
0x140003abf  lea     r8, WPP_d95d50ceaf3b33ad81be3468c396533e_Traceguids
0x140003ac6  mov     edx, 0Dh
0x140003acb  mov     r9, rbx
0x140003ace  call    WPP_SF_q
0x140003ad3  jmp     loc_140003997
0x140027010  mov     rcx, [rcx]
0x140027013  cmp     rax, rcx
0x140027016  jz      loc_14000390C
0x14002701c  jmp     loc_140003A4B
0x140027021  cmp     r9, rax
0x140027024  jz      loc_1400039B6
0x14002702a  lea     r8, [rax-8]
0x14002702e  cmp     rdx, r8
0x140027031  jz      short loc_14002703D
0x140027033  cmp     [r8+50h], r10
0x140027037  jz      loc_1400038F7
0x14002703d  mov     rax, [rax]
0x140027040  jmp     short loc_140027021
```
