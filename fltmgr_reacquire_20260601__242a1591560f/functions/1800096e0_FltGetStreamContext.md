# FltGetStreamContext

- ea: `0x1800096e0`
- end: `0x1800099ee`
- name: `FltGetStreamContext`
- size: `782`
- prototype: `NTSTATUS __stdcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CONTEXT *Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007ecb0`

## callees

- `0x1800096e0`
- `0x180009f20`
- `0x180009f80`
- `0x180014c10`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x180009839`
- `ntoskrnl!KeBugCheckEx` at `0x180009998`
- `ntoskrnl!KeBugCheckEx` at `0x180009839`
- `ntoskrnl!KeBugCheckEx` at `0x180009998`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800098cb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800098e1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800098cb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800098e1`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180009768`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180009905`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180009768`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180009905`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800097b4`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180009857`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180009960`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800099aa`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800097b4`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180009857`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180009960`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800099aa`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x18000977a`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x18000977a`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1800097a8`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x18000984b`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1800097a8`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x18000984b`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000987f`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x180009892`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000987f`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x180009892`
- `ntoskrnl!IoUninitializeWorkItem` at `0x1800098b1`
- `ntoskrnl!IoUninitializeWorkItem` at `0x1800098b1`

## pseudocode

```c
NTSTATUS __stdcall FltGetStreamContext(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CONTEXT *Context)
{
  NTSTATUS v5; // r15d
  unsigned int StreamListCtrl; // edi
  __int64 v7; // rax
  volatile signed __int32 *v8; // rcx
  int v9; // ecx
  ULONG_PTR v11; // rbp
  unsigned int v12; // ecx
  unsigned __int64 v13; // r8
  volatile signed __int64 *v14; // rdx
  struct _FLT_INSTANCE *v15; // rax
  ULONG_PTR v16; // rbp

  v5 = -1073741275;
  StreamListCtrl = FltpGetStreamListCtrl(Instance->Volume);
  if ( (int)FltpDbgStatus(StreamListCtrl, "minkernel\\fs\\filtermgr\\filter\\contextsup.c", 4558, 3221226021LL) < 0 )
  {
    *Context = 0;
    return StreamListCtrl;
  }
  if ( Context )
    *Context = 0;
  if ( !FltpVelocity )
    goto LABEL_5;
  KeEnterGuardedRegion();
  v12 = 0;
  v13 = (unsigned __int64)Instance | 1;
  while ( 1 )
  {
    if ( v12 >= 8 )
    {
      if ( !MEMORY[0xD8] )
        goto LABEL_11;
      KeLeaveGuardedRegion();
LABEL_5:
      KeEnterGuardedRegion();
      v7 = ExAcquireAutoExpandPushLockShared(72, 0);
      v8 = (volatile signed __int32 *)MEMORY[0xD8];
      if ( MEMORY[0xD8] )
      {
        while ( Instance != *((PFLT_INSTANCE *)v8 + 4) )
        {
          if ( (unsigned __int64)Instance < *((_QWORD *)v8 + 4) )
            goto LABEL_17;
          v8 = (volatile signed __int32 *)*((_QWORD *)v8 + 2);
LABEL_9:
          if ( !v8 )
            goto LABEL_10;
        }
        if ( !*((_QWORD *)v8 + 5) )
        {
          v11 = (ULONG_PTR)(v8 - 6);
          if ( _InterlockedIncrement(v8 + 14) == 1 )
            KeBugCheckEx(0xF5u, 0x6Eu, v11 + 96, v11, 0);
          ExReleaseAutoExpandPushLockShared(v7, 0);
          KeLeaveGuardedRegion();
          if ( v11 )
          {
            v5 = 0;
            *Context = (PFLT_CONTEXT)(v11 + 96);
          }
          goto LABEL_12;
        }
LABEL_17:
        v8 = (volatile signed __int32 *)*((_QWORD *)v8 + 1);
        goto LABEL_9;
      }
LABEL_10:
      ExReleaseAutoExpandPushLockShared(v7, 0);
LABEL_11:
      KeLeaveGuardedRegion();
      goto LABEL_12;
    }
    v14 = (volatile signed __int64 *)(16LL * v12 + 88);
    do
      v15 = (struct _FLT_INSTANCE *)_InterlockedCompareExchange64(v14, v13, (signed __int64)Instance);
    while ( v15 == (struct _FLT_INSTANCE *)v13 );
    if ( v15 == Instance )
      break;
LABEL_34:
    ++v12;
  }
  v16 = *(_QWORD *)(16LL * v12 + 0x60);
  if ( !v16 || *(_QWORD *)(v16 + 64) )
  {
    _InterlockedAnd64(v14, 0xFFFFFFFFFFFFFFFEuLL);
    goto LABEL_34;
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)(v16 + 80)) == 1 )
    KeBugCheckEx(0xF5u, 0x6Eu, v16 + 96, v16, 0);
  _InterlockedAnd64(v14, 0xFFFFFFFFFFFFFFFEuLL);
  KeLeaveGuardedRegion();
  v5 = 0;
  *Context = (PFLT_CONTEXT)(v16 + 96);
LABEL_12:
  if ( (byte_1800404C2 & 1) != 0 )
    McTemplateU0spdd_EtwWriteTransfer(
      v9,
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
  return v5;
}

```

## disassembly

```asm
0x1800096e0  push    rbx
0x1800096e2  push    rdi
0x1800096e3  push    r12
0x1800096e5  push    r14
0x1800096e7  push    r15
0x1800096e9  sub     rsp, 30h
0x1800096ed  mov     r14, r8
0x1800096f0  lea     r9, [rsp+58h+Entry]
0x1800096f5  mov     rbx, rcx
0x1800096f8  xor     r12d, r12d
0x1800096fb  mov     rcx, [rcx+40h]; OwnerId
0x1800096ff  xor     r8d, r8d
0x180009702  mov     [rsp+58h+Entry], r12
0x180009707  call    FltpGetStreamListCtrl
0x18000970c  mov     r15d, 0C0000225h
0x180009712  mov     [rsp+58h+var_30], r12
0x180009717  mov     r9d, r15d
0x18000971a  mov     dword ptr [rsp+58h+BugCheckParameter4], 0C00000BBh
0x180009722  mov     r8d, 11CEh
0x180009728  lea     rdx, aMinkernelFsFil_9; "minkernel\\fs\\filtermgr\\filter\\conte"...
0x18000972f  mov     ecx, eax
0x180009731  mov     edi, eax
0x180009733  call    FltpDbgStatus
0x180009738  test    eax, eax
0x18000973a  js      loc_1800098F2
0x180009740  mov     rdi, [rsp+58h+Entry]
0x180009745  mov     [rsp+58h+arg_10], rsi
0x18000974a  test    r14, r14
0x18000974d  jz      short loc_180009752
0x18000974f  mov     [r14], r12
0x180009752  cmp     cs:FltpVelocity, r12b
0x180009759  lea     rsi, [rdi+58h]
0x18000975d  mov     [rsp+58h+arg_8], rbp
0x180009762  jnz     loc_180009905
0x180009768  call    cs:__imp_KeEnterGuardedRegion
0x18000976f  nop     dword ptr [rax+rax+00h]
0x180009774  lea     rcx, [rdi+48h]
0x180009778  xor     edx, edx
0x18000977a  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x180009781  nop     dword ptr [rax+rax+00h]
0x180009786  mov     rcx, [rsi+80h]
0x18000978d  test    rcx, rcx
0x180009790  jz      short loc_1800097A3
0x180009792  cmp     rbx, [rcx+20h]
0x180009796  jz      short loc_1800097FB
0x180009798  jb      short loc_180009803
0x18000979a  mov     rcx, [rcx+10h]
0x18000979e  test    rcx, rcx
0x1800097a1  jnz     short loc_180009792
0x1800097a3  xor     edx, edx
0x1800097a5  mov     rcx, rax
0x1800097a8  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x1800097af  nop     dword ptr [rax+rax+00h]
0x1800097b4  call    cs:__imp_KeLeaveGuardedRegion
0x1800097bb  nop     dword ptr [rax+rax+00h]
0x1800097c0  test    cs:byte_1800404C2, 1
0x1800097c7  jnz     loc_1800099C5
0x1800097cd  mov     eax, 0FFFFFFFFh
0x1800097d2  lock xadd [rdi+44h], eax
0x1800097d7  cmp     eax, 1
0x1800097da  jz      loc_18000987B
0x1800097e0  mov     rbp, [rsp+58h+arg_8]
0x1800097e5  mov     eax, r15d
0x1800097e8  mov     rsi, [rsp+58h+arg_10]
0x1800097ed  add     rsp, 30h
0x1800097f1  pop     r15
0x1800097f3  pop     r14
0x1800097f5  pop     r12
0x1800097f7  pop     rdi
0x1800097f8  pop     rbx
0x1800097f9  retn
0x1800097fb  cmp     [rcx+28h], r12
0x1800097ff  jz      short loc_180009809
0x180009801  jbe     short loc_18000979A
0x180009803  mov     rcx, [rcx+8]
0x180009807  jmp     short loc_18000979E
0x180009809  test    rcx, rcx
0x18000980c  jz      short loc_1800097A3
0x18000980e  lea     rbp, [rcx-18h]
0x180009812  mov     ecx, 1
0x180009817  lock xadd [rbp+50h], ecx
0x18000981c  inc     ecx
0x18000981e  cmp     ecx, 1
0x180009821  jnz     short loc_180009846
0x180009823  lea     r8, [rbp+60h]; BugCheckParameter2
0x180009827  mov     [rsp+58h+BugCheckParameter4], r12; BugCheckParameter4
0x18000982c  mov     r9, rbp; BugCheckParameter3
0x18000982f  mov     edx, 6Eh ; 'n'; BugCheckParameter1
0x180009834  mov     ecx, 0F5h; BugCheckCode
0x180009839  call    cs:__imp_KeBugCheckEx
0x180009846  xor     edx, edx
0x180009848  mov     rcx, rax
0x18000984b  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x180009852  nop     dword ptr [rax+rax+00h]
0x180009857  call    cs:__imp_KeLeaveGuardedRegion
0x18000985e  nop     dword ptr [rax+rax+00h]
0x180009863  test    rbp, rbp
0x180009866  jz      loc_1800097C0
0x18000986c  lea     rax, [rbp+60h]
0x180009870  mov     r15d, r12d
0x180009873  mov     [r14], rax
0x180009876  jmp     loc_1800097C0
0x18000987b  lea     rcx, [rdi+48h]
0x18000987f  call    cs:__imp_ExCleanupAutoExpandPushLock
0x180009886  nop     dword ptr [rax+rax+00h]
0x18000988b  lea     rcx, [rdi+170h]
0x180009892  call    cs:__imp_ExCleanupAutoExpandPushLock
0x180009899  nop     dword ptr [rax+rax+00h]
0x18000989e  mov     rcx, [rdi+168h]
0x1800098a5  test    rcx, rcx
0x1800098a8  jz      short loc_1800098D7
0x1800098aa  mov     rcx, [rcx+140h]; IoWorkItem
0x1800098b1  call    cs:__imp_IoUninitializeWorkItem
0x1800098b8  nop     dword ptr [rax+rax+00h]
0x1800098bd  mov     rdx, [rdi+168h]; Entry
0x1800098c4  lea     rcx, stru_18003F1C0; Lookaside
0x1800098cb  call    cs:__imp_ExFreeToNPagedLookasideList
0x1800098d2  nop     dword ptr [rax+rax+00h]
0x1800098d7  mov     rdx, rdi; Entry
0x1800098da  lea     rcx, stru_18003EB40; Lookaside
0x1800098e1  call    cs:__imp_ExFreeToNPagedLookasideList
0x1800098e8  nop     dword ptr [rax+rax+00h]
0x1800098ed  jmp     loc_1800097E0
0x1800098f2  mov     [r14], r12
0x1800098f5  mov     eax, edi
0x1800098f7  add     rsp, 30h
0x1800098fb  pop     r15
0x1800098fd  pop     r14
0x1800098ff  pop     r12
0x180009901  pop     rdi
0x180009902  pop     rbx
0x180009903  retn
0x180009905  call    cs:__imp_KeEnterGuardedRegion
0x18000990c  nop     dword ptr [rax+rax+00h]
0x180009911  mov     r8, rbx
0x180009914  mov     ecx, r12d
0x180009917  or      r8, 1
0x18000991b  cmp     ecx, 8
0x18000991e  jnb     short loc_180009953
0x180009920  mov     edx, ecx
0x180009922  shl     rdx, 4
0x180009926  add     rdx, rsi
0x180009929  mov     rax, rbx
0x18000992c  lock cmpxchg [rdx], r8
0x180009931  cmp     rax, r8
0x180009934  jz      short loc_180009929
0x180009936  cmp     rax, rbx
0x180009939  jnz     short loc_18000994F
0x18000993b  mov     rbp, [rdx+8]
0x18000993f  test    rbp, rbp
0x180009942  jz      short loc_18000994A
0x180009944  cmp     [rbp+40h], r12
0x180009948  jz      short loc_180009971
0x18000994a  lock and qword ptr [rdx], 0FFFFFFFFFFFFFFFEh
0x18000994f  inc     ecx
0x180009951  jmp     short loc_18000991B
0x180009953  cmp     [rsi+80h], r12
0x18000995a  jz      loc_1800097B4
0x180009960  call    cs:__imp_KeLeaveGuardedRegion
0x180009967  nop     dword ptr [rax+rax+00h]
0x18000996c  jmp     loc_180009768
0x180009971  mov     ecx, 1
0x180009976  lock xadd [rbp+50h], ecx
0x18000997b  inc     ecx
0x18000997d  cmp     ecx, 1
0x180009980  jnz     short loc_1800099A5
0x180009982  lea     r8, [rbp+60h]; BugCheckParameter2
0x180009986  mov     [rsp+58h+BugCheckParameter4], r12; BugCheckParameter4
0x18000998b  mov     r9, rbp; BugCheckParameter3
0x18000998e  mov     edx, 6Eh ; 'n'; BugCheckParameter1
0x180009993  mov     ecx, 0F5h; BugCheckCode
0x180009998  call    cs:__imp_KeBugCheckEx
0x1800099a5  lock and qword ptr [rdx], 0FFFFFFFFFFFFFFFEh
0x1800099aa  call    cs:__imp_KeLeaveGuardedRegion
0x1800099b1  nop     dword ptr [rax+rax+00h]
0x1800099b6  lea     rax, [rbp+60h]
0x1800099ba  mov     r15d, r12d
0x1800099bd  mov     [r14], rax
0x1800099c0  jmp     loc_1800097C0
0x1800099c5  mov     eax, [rdi+44h]
0x1800099c8  lea     r8, aFltpreleasestr; "FltpReleaseStreamListCtrl"
0x1800099cf  mov     dword ptr [rsp+58h+var_30], eax
0x1800099d3  lea     rdx, StreamListCtrlSup_c754
0x1800099da  mov     eax, [rdi+40h]
0x1800099dd  mov     r9, rdi
0x1800099e0  mov     dword ptr [rsp+58h+BugCheckParameter4], eax
0x1800099e4  call    McTemplateU0spdd_EtwWriteTransfer
0x1800099e9  jmp     loc_1800097CD
```
