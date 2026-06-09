# FltDeleteStreamHandleContext

- ea: `0x180010620`
- end: `0x1800109f6`
- name: `FltDeleteStreamHandleContext`
- size: `982`
- prototype: `NTSTATUS __stdcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CONTEXT *OldContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007e2b0`

## callees

- `0x180009f20`
- `0x180009f80`
- `0x180010620`
- `0x180010ab0`
- `0x180014c10`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180010867`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001087d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800108de`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800108f4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180010867`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001087d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800108de`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800108f4`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1800106ab`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1800106ab`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001070d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800107ad`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001098a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001070d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800107ad`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001098a`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1800106bd`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1800106bd`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180010701`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1800107a1`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18001097e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180010701`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1800107a1`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18001097e`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18001081b`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18001082e`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x180010892`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x1800108a5`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18001081b`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18001082e`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x180010892`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x1800108a5`
- `ntoskrnl!IoUninitializeWorkItem` at `0x18001084d`
- `ntoskrnl!IoUninitializeWorkItem` at `0x1800108c4`
- `ntoskrnl!IoUninitializeWorkItem` at `0x18001084d`
- `ntoskrnl!IoUninitializeWorkItem` at `0x1800108c4`
- `ntoskrnl!RtlDelete` at `0x180010778`
- `ntoskrnl!RtlDelete` at `0x180010778`

## pseudocode

```c
NTSTATUS __stdcall FltDeleteStreamHandleContext(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PFLT_CONTEXT *OldContext)
{
  NTSTATUS v6; // r12d
  unsigned int StreamListCtrl; // ebx
  __int64 v8; // rbx
  bool v9; // cf
  int v10; // ecx
  PRTL_SPLAY_LINKS *v12; // rdi
  ULONG_PTR v13; // rbx
  signed __int64 v14; // rax
  signed __int64 v15; // rdi
  __int64 v16; // rcx
  unsigned __int64 v17; // r8
  unsigned int i; // edx
  volatile signed __int64 *v19; // rcx
  struct _FILE_OBJECT *v20; // rax

  if ( OldContext )
    *OldContext = 0;
  v6 = -1073741275;
  StreamListCtrl = FltpGetStreamListCtrl(Instance->Volume);
  if ( (int)FltpDbgStatus(StreamListCtrl, "minkernel\\fs\\filtermgr\\filter\\contextsup.c", 4931, 3221226021LL) < 0 )
    return StreamListCtrl;
  if ( OldContext )
    *OldContext = 0;
  KeEnterGuardedRegion();
  ExAcquireAutoExpandPushLockExclusive(72, 0);
  if ( FltpVelocity )
  {
    v17 = (unsigned __int64)FileObject | 1;
    for ( i = 0; i < 8; ++i )
    {
      v19 = (volatile signed __int64 *)(16LL * i + 224);
      do
        v20 = (struct _FILE_OBJECT *)_InterlockedCompareExchange64(v19, v17, (signed __int64)FileObject);
      while ( v20 == (struct _FILE_OBJECT *)v17 );
      if ( v20 == FileObject )
      {
        v13 = *(_QWORD *)(16LL * i + 0xE8);
        if ( v13 && (Instance == (PFLT_INSTANCE)-1LL || Instance == *(PFLT_INSTANCE *)(v13 + 64)) )
        {
          *(_QWORD *)(16LL * i + 0xE8) = 0;
          _InterlockedAnd64(v19, 0);
          *(_DWORD *)(v13 + 72) &= ~0x10000u;
          *(_OWORD *)(v13 + 24) = 0;
          *(_QWORD *)(v13 + 40) = 0;
          *(_QWORD *)(v13 + 48) = 0;
          ExReleaseAutoExpandPushLockExclusive(72, 0);
          KeLeaveGuardedRegion();
          goto LABEL_24;
        }
        _InterlockedAnd64(v19, 0xFFFFFFFFFFFFFFFEuLL);
      }
    }
  }
  v8 = MEMORY[0x160];
  if ( !MEMORY[0x160] )
  {
LABEL_12:
    ExReleaseAutoExpandPushLockExclusive(72, 0);
    KeLeaveGuardedRegion();
    goto LABEL_13;
  }
  while ( 1 )
  {
    v9 = (unsigned __int64)FileObject < *(_QWORD *)(v8 + 32);
    if ( FileObject == *(PFILE_OBJECT *)(v8 + 32) )
      break;
LABEL_9:
    if ( v9 )
      v8 = *(_QWORD *)(v8 + 8);
    else
      v8 = *(_QWORD *)(v8 + 16);
    if ( !v8 )
      goto LABEL_12;
  }
  if ( Instance != *(PFLT_INSTANCE *)(v8 + 40) && Instance != (PFLT_INSTANCE)-1LL )
  {
    v9 = (unsigned __int64)Instance < *(_QWORD *)(v8 + 40);
    goto LABEL_9;
  }
  v12 = *(PRTL_SPLAY_LINKS **)(v8 + 24);
  *v12 = RtlDelete((PRTL_SPLAY_LINKS)v8);
  if ( (*(_DWORD *)(v8 + 48) & 0x10000) != 0 )
    _InterlockedAnd((volatile signed __int32 *)(v8 + 48), 0xFFFEFFFF);
  ExReleaseAutoExpandPushLockExclusive(72, 0);
  KeLeaveGuardedRegion();
  v13 = v8 - 24;
  if ( v13 )
  {
LABEL_24:
    v10 = 0;
    v14 = _InterlockedCompareExchange64((volatile signed __int64 *)(v13 + 16), 0, *(_QWORD *)(v13 + 16));
    v15 = v14;
    if ( v14 )
    {
      if ( (byte_1800404C2 & 1) != 0 )
        McTemplateU0spdd_EtwWriteTransfer(
          *(_DWORD *)(v14 + 64),
          (unsigned int)StreamListCtrlSup_c754,
          (unsigned int)"FltpReleaseStreamListCtrl",
          v14,
          *(_DWORD *)(v14 + 64),
          *(_DWORD *)(v14 + 68));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 68), 0xFFFFFFFF) == 1 )
      {
        ExCleanupAutoExpandPushLock(v15 + 72);
        ExCleanupAutoExpandPushLock(v15 + 368);
        v16 = *(_QWORD *)(v15 + 360);
        if ( v16 )
        {
          IoUninitializeWorkItem(*(PIO_WORKITEM *)(v16 + 320));
          ExFreeToNPagedLookasideList(&stru_18003F1C0, *(PVOID *)(v15 + 360));
        }
        ExFreeToNPagedLookasideList(&stru_18003EB40, (PVOID)v15);
      }
    }
    if ( OldContext )
    {
      v6 = 0;
      *OldContext = (PFLT_CONTEXT)(v13 + 96);
    }
    else
    {
      DoReleaseContext(v13);
      v6 = 0;
    }
  }
LABEL_13:
  if ( (byte_1800404C2 & 1) != 0 )
    McTemplateU0spdd_EtwWriteTransfer(
      v10,
      (unsigned int)StreamListCtrlSup_c754,
      (unsigned int)"FltpReleaseStreamListCtrl",
      0,
      MEMORY[0x40],
      MEMORY[0x44]);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)0x44, 0xFFFFFFFF) == 1 )
  {
    ExCleanupAutoExpandPushLock(72);
    ExCleanupAutoExpandPushLock(368);
    if ( MEMORY[0x168] )
    {
      IoUninitializeWorkItem(*(PIO_WORKITEM *)(MEMORY[0x168] + 320LL));
      ExFreeToNPagedLookasideList(&stru_18003F1C0, MEMORY[0x168]);
    }
    ExFreeToNPagedLookasideList(&stru_18003EB40, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x180010620  mov     [rsp+arg_18], rbx
0x180010625  push    rbp
0x180010626  push    rsi
0x180010627  push    rdi
0x180010628  push    r12
0x18001062a  push    r14
0x18001062c  sub     rsp, 30h
0x180010630  xor     ebp, ebp
0x180010632  mov     rsi, r8
0x180010635  mov     [rsp+58h+Entry], rbp
0x18001063a  mov     rdi, rdx
0x18001063d  mov     r14, rcx
0x180010640  test    r8, r8
0x180010643  jz      short loc_180010648
0x180010645  mov     [r8], rbp
0x180010648  mov     rcx, [rcx+40h]; OwnerId
0x18001064c  lea     r9, [rsp+58h+Entry]
0x180010651  xor     r8d, r8d
0x180010654  call    FltpGetStreamListCtrl
0x180010659  mov     r12d, 0C0000225h
0x18001065f  mov     [rsp+58h+var_30], rbp
0x180010664  mov     r9d, r12d
0x180010667  mov     [rsp+58h+var_38], 0C00000BBh
0x18001066f  mov     r8d, 1343h
0x180010675  lea     rdx, aMinkernelFsFil_9; "minkernel\\fs\\filtermgr\\filter\\conte"...
0x18001067c  mov     ecx, eax
0x18001067e  mov     ebx, eax
0x180010680  call    FltpDbgStatus
0x180010685  test    eax, eax
0x180010687  js      loc_1800109EF
0x18001068d  mov     [rsp+58h+arg_8], r13
0x180010692  mov     [rsp+58h+arg_10], r15
0x180010697  mov     r15, [rsp+58h+Entry]
0x18001069c  test    rsi, rsi
0x18001069f  jz      short loc_1800106A4
0x1800106a1  mov     [rsi], rbp
0x1800106a4  lea     r13, [r15+0E0h]
0x1800106ab  call    cs:__imp_KeEnterGuardedRegion
0x1800106b2  nop     dword ptr [rax+rax+00h]
0x1800106b7  xor     edx, edx
0x1800106b9  lea     rcx, [r15+48h]
0x1800106bd  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x1800106c4  nop     dword ptr [rax+rax+00h]
0x1800106c9  cmp     cs:FltpVelocity, 0
0x1800106d0  mov     ebp, 0FFFFFFFFh
0x1800106d5  jnz     loc_180010905
0x1800106db  mov     rbx, [r13+80h]
0x1800106e2  test    rbx, rbx
0x1800106e5  jz      short loc_1800106F8
0x1800106e7  cmp     rdi, [rbx+20h]
0x1800106eb  jz      short loc_180010754
0x1800106ed  jb      short loc_180010766
0x1800106ef  mov     rbx, [rbx+10h]
0x1800106f3  test    rbx, rbx
0x1800106f6  jnz     short loc_1800106E7
0x1800106f8  lea     r14, [r15+48h]
0x1800106fc  xor     edx, edx
0x1800106fe  mov     rcx, r14
0x180010701  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x180010708  nop     dword ptr [rax+rax+00h]
0x18001070d  call    cs:__imp_KeLeaveGuardedRegion
0x180010714  nop     dword ptr [rax+rax+00h]
0x180010719  test    cs:byte_1800404C2, 1
0x180010720  mov     r13, [rsp+58h+arg_8]
0x180010725  jnz     loc_1800109C4
0x18001072b  lock xadd [r15+44h], ebp
0x180010731  cmp     ebp, 1
0x180010734  jz      loc_180010818
0x18001073a  mov     r15, [rsp+58h+arg_10]
0x18001073f  mov     eax, r12d
0x180010742  mov     rbx, [rsp+58h+arg_18]
0x180010747  add     rsp, 30h
0x18001074b  pop     r14
0x18001074d  pop     r12
0x18001074f  pop     rdi
0x180010750  pop     rsi
0x180010751  pop     rbp
0x180010752  retn
0x180010754  cmp     r14, [rbx+28h]
0x180010758  jz      short loc_18001076C
0x18001075a  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18001075e  jz      short loc_18001076C
0x180010760  cmp     r14, [rbx+28h]
0x180010764  jmp     short loc_1800106ED
0x180010766  mov     rbx, [rbx+8]
0x18001076a  jmp     short loc_1800106F3
0x18001076c  test    rbx, rbx
0x18001076f  jz      short loc_1800106F8
0x180010771  mov     rdi, [rbx+18h]
0x180010775  mov     rcx, rbx; Links
0x180010778  call    cs:__imp_RtlDelete
0x18001077f  nop     dword ptr [rax+rax+00h]
0x180010784  mov     [rdi], rax
0x180010787  mov     eax, [rbx+30h]
0x18001078a  bt      eax, 10h
0x18001078e  jnb     short loc_180010798
0x180010790  lock and dword ptr [rbx+30h], 0FFFEFFFFh
0x180010798  lea     r14, [r15+48h]
0x18001079c  xor     edx, edx
0x18001079e  mov     rcx, r14
0x1800107a1  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x1800107a8  nop     dword ptr [rax+rax+00h]
0x1800107ad  call    cs:__imp_KeLeaveGuardedRegion
0x1800107b4  nop     dword ptr [rax+rax+00h]
0x1800107b9  add     rbx, 0FFFFFFFFFFFFFFE8h
0x1800107bd  jz      loc_180010719
0x1800107c3  mov     rax, [rbx+10h]
0x1800107c7  xor     ecx, ecx
0x1800107c9  lock cmpxchg [rbx+10h], rcx
0x1800107cf  mov     rdi, rax
0x1800107d2  test    rax, rax
0x1800107d5  jz      short loc_1800107F4
0x1800107d7  test    cs:byte_1800404C2, 1
0x1800107de  jnz     loc_18001099B
0x1800107e4  mov     eax, ebp
0x1800107e6  lock xadd [rdi+44h], eax
0x1800107eb  cmp     eax, 1
0x1800107ee  jz      loc_18001088E
0x1800107f4  test    rsi, rsi
0x1800107f7  jnz     short loc_180010809
0x1800107f9  mov     rcx, rbx; BugCheckParameter3
0x1800107fc  call    DoReleaseContext
0x180010801  xor     r12d, r12d
0x180010804  jmp     loc_180010719
0x180010809  lea     rax, [rbx+60h]
0x18001080d  xor     r12d, r12d
0x180010810  mov     [rsi], rax
0x180010813  jmp     loc_180010719
0x180010818  mov     rcx, r14
0x18001081b  call    cs:__imp_ExCleanupAutoExpandPushLock
0x180010822  nop     dword ptr [rax+rax+00h]
0x180010827  lea     rcx, [r15+170h]
0x18001082e  call    cs:__imp_ExCleanupAutoExpandPushLock
0x180010835  nop     dword ptr [rax+rax+00h]
0x18001083a  mov     rcx, [r15+168h]
0x180010841  test    rcx, rcx
0x180010844  jz      short loc_180010873
0x180010846  mov     rcx, [rcx+140h]; IoWorkItem
0x18001084d  call    cs:__imp_IoUninitializeWorkItem
0x180010854  nop     dword ptr [rax+rax+00h]
0x180010859  mov     rdx, [r15+168h]; Entry
0x180010860  lea     rcx, stru_18003F1C0; Lookaside
0x180010867  call    cs:__imp_ExFreeToNPagedLookasideList
0x18001086e  nop     dword ptr [rax+rax+00h]
0x180010873  mov     rdx, r15; Entry
0x180010876  lea     rcx, stru_18003EB40; Lookaside
0x18001087d  call    cs:__imp_ExFreeToNPagedLookasideList
0x180010884  nop     dword ptr [rax+rax+00h]
0x180010889  jmp     loc_18001073A
0x18001088e  lea     rcx, [rdi+48h]
0x180010892  call    cs:__imp_ExCleanupAutoExpandPushLock
0x180010899  nop     dword ptr [rax+rax+00h]
0x18001089e  lea     rcx, [rdi+170h]
0x1800108a5  call    cs:__imp_ExCleanupAutoExpandPushLock
0x1800108ac  nop     dword ptr [rax+rax+00h]
0x1800108b1  mov     rcx, [rdi+168h]
0x1800108b8  test    rcx, rcx
0x1800108bb  jz      short loc_1800108EA
0x1800108bd  mov     rcx, [rcx+140h]; IoWorkItem
0x1800108c4  call    cs:__imp_IoUninitializeWorkItem
0x1800108cb  nop     dword ptr [rax+rax+00h]
0x1800108d0  mov     rdx, [rdi+168h]; Entry
0x1800108d7  lea     rcx, stru_18003F1C0; Lookaside
0x1800108de  call    cs:__imp_ExFreeToNPagedLookasideList
0x1800108e5  nop     dword ptr [rax+rax+00h]
0x1800108ea  mov     rdx, rdi; Entry
0x1800108ed  lea     rcx, stru_18003EB40; Lookaside
0x1800108f4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1800108fb  nop     dword ptr [rax+rax+00h]
0x180010900  jmp     loc_1800107F4
0x180010905  mov     r8, rdi
0x180010908  or      r8, 1
0x18001090c  xor     edx, edx
0x18001090e  cmp     edx, 8
0x180010911  jnb     loc_1800106DB
0x180010917  mov     ecx, edx
0x180010919  shl     rcx, 4
0x18001091d  add     rcx, r13
0x180010920  mov     rax, rdi
0x180010923  lock cmpxchg [rcx], r8
0x180010928  cmp     rax, r8
0x18001092b  jz      short loc_180010920
0x18001092d  cmp     rax, rdi
0x180010930  jnz     short loc_18001094C
0x180010932  mov     rbx, [rcx+8]
0x180010936  test    rbx, rbx
0x180010939  jz      short loc_180010947
0x18001093b  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18001093f  jz      short loc_180010950
0x180010941  cmp     r14, [rbx+40h]
0x180010945  jz      short loc_180010950
0x180010947  lock and qword ptr [rcx], 0FFFFFFFFFFFFFFFEh
0x18001094c  inc     edx
0x18001094e  jmp     short loc_18001090E
0x180010950  mov     qword ptr [rcx+8], 0
0x180010958  lock and qword ptr [rcx], 0
0x18001095d  and     dword ptr [rbx+48h], 0FFFEFFFFh
0x180010964  lea     r14, [r15+48h]
0x180010968  xor     eax, eax
0x18001096a  xorps   xmm0, xmm0
0x18001096d  movups  xmmword ptr [rbx+18h], xmm0
0x180010971  mov     rcx, r14
0x180010974  mov     [rbx+28h], rax
0x180010978  xor     edx, edx
0x18001097a  mov     [rbx+30h], rax
0x18001097e  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x180010985  nop     dword ptr [rax+rax+00h]
0x18001098a  call    cs:__imp_KeLeaveGuardedRegion
0x180010991  nop     dword ptr [rax+rax+00h]
0x180010996  jmp     loc_1800107C3
0x18001099b  mov     ecx, [rax+44h]
0x18001099e  lea     r8, aFltpreleasestr; "FltpReleaseStreamListCtrl"
0x1800109a5  mov     dword ptr [rsp+58h+var_30], ecx
0x1800109a9  lea     rdx, StreamListCtrlSup_c754
0x1800109b0  mov     ecx, [rax+40h]
0x1800109b3  mov     r9, rdi
0x1800109b6  mov     [rsp+58h+var_38], ecx
0x1800109ba  call    McTemplateU0spdd_EtwWriteTransfer
0x1800109bf  jmp     loc_1800107E4
0x1800109c4  mov     eax, [r15+44h]
0x1800109c8  lea     r8, aFltpreleasestr; "FltpReleaseStreamListCtrl"
0x1800109cf  mov     dword ptr [rsp+58h+var_30], eax
0x1800109d3  lea     rdx, StreamListCtrlSup_c754
0x1800109da  mov     eax, [r15+40h]
0x1800109de  mov     r9, r15
0x1800109e1  mov     [rsp+58h+var_38], eax
0x1800109e5  call    McTemplateU0spdd_EtwWriteTransfer
0x1800109ea  jmp     loc_18001072B
0x1800109ef  mov     eax, ebx
0x1800109f1  jmp     loc_180010742
```
