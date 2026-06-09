# FltGetStreamHandleContext

- ea: `0x1800093a0`
- end: `0x1800096d4`
- name: `FltGetStreamHandleContext`
- size: `820`
- prototype: `NTSTATUS __stdcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CONTEXT *Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007ed70`

## callees

- `0x1800093a0`
- `0x180009f20`
- `0x180009f80`
- `0x180014c10`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x180009513`
- `ntoskrnl!KeBugCheckEx` at `0x18000967e`
- `ntoskrnl!KeBugCheckEx` at `0x180009513`
- `ntoskrnl!KeBugCheckEx` at `0x18000967e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800095bd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800095d3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800095bd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800095d3`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180009432`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1800095e4`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180009432`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1800095e4`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000947e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180009531`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180009645`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180009690`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000947e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180009531`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180009645`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180009690`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x180009444`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x180009444`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x180009472`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x180009525`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x180009472`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x180009525`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x180009571`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x180009584`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x180009571`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x180009584`
- `ntoskrnl!IoUninitializeWorkItem` at `0x1800095a3`
- `ntoskrnl!IoUninitializeWorkItem` at `0x1800095a3`

## pseudocode

```c
NTSTATUS __stdcall FltGetStreamHandleContext(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CONTEXT *Context)
{
  NTSTATUS v6; // r12d
  unsigned int StreamListCtrl; // edi
  __int64 v8; // rax
  __int64 v9; // rcx
  bool v10; // cf
  int v11; // ecx
  NTSTATUS result; // eax
  ULONG_PTR v13; // r15
  unsigned int v14; // ecx
  unsigned __int64 v15; // r8
  volatile signed __int64 *v16; // rdx
  struct _FILE_OBJECT *v17; // rax
  ULONG_PTR v18; // r15

  v6 = -1073741275;
  StreamListCtrl = FltpGetStreamListCtrl(Instance->Volume);
  if ( (int)FltpDbgStatus(StreamListCtrl, "minkernel\\fs\\filtermgr\\filter\\contextsup.c", 4781, 3221226021LL) < 0 )
  {
    result = StreamListCtrl;
    *Context = 0;
    return result;
  }
  if ( Context )
    *Context = 0;
  if ( !FltpVelocity )
    goto LABEL_5;
  KeEnterGuardedRegion();
  v14 = 0;
  v15 = (unsigned __int64)FileObject | 1;
  while ( 1 )
  {
    if ( v14 >= 8 )
    {
      if ( !MEMORY[0x160] )
        goto LABEL_11;
      KeLeaveGuardedRegion();
LABEL_5:
      KeEnterGuardedRegion();
      v8 = ExAcquireAutoExpandPushLockShared(72, 0);
      v9 = MEMORY[0x160];
      while ( v9 )
      {
        v10 = (unsigned __int64)FileObject < *(_QWORD *)(v9 + 32);
        if ( FileObject == *(PFILE_OBJECT *)(v9 + 32) )
        {
          if ( Instance == *(PFLT_INSTANCE *)(v9 + 40) || Instance == (PFLT_INSTANCE)-1LL )
          {
            v13 = v9 - 24;
            if ( _InterlockedIncrement((volatile signed __int32 *)(v9 - 24 + 80)) == 1 )
              KeBugCheckEx(0xF5u, 0x6Eu, v13 + 96, v13, 0);
            ExReleaseAutoExpandPushLockShared(v8, 0);
            KeLeaveGuardedRegion();
            if ( v13 )
            {
              v6 = 0;
              *Context = (PFLT_CONTEXT)(v13 + 96);
            }
            goto LABEL_12;
          }
          v10 = (unsigned __int64)Instance < *(_QWORD *)(v9 + 40);
        }
        if ( v10 )
          v9 = *(_QWORD *)(v9 + 8);
        else
          v9 = *(_QWORD *)(v9 + 16);
      }
      ExReleaseAutoExpandPushLockShared(v8, 0);
LABEL_11:
      KeLeaveGuardedRegion();
      goto LABEL_12;
    }
    v16 = (volatile signed __int64 *)(16LL * v14 + 224);
    do
      v17 = (struct _FILE_OBJECT *)_InterlockedCompareExchange64(v16, v15, (signed __int64)FileObject);
    while ( v17 == (struct _FILE_OBJECT *)v15 );
    if ( v17 == FileObject )
      break;
LABEL_37:
    ++v14;
  }
  v18 = *(_QWORD *)(16LL * v14 + 0xE8);
  if ( !v18 || Instance != (PFLT_INSTANCE)-1LL && Instance != *(PFLT_INSTANCE *)(v18 + 64) )
  {
    _InterlockedAnd64(v16, 0xFFFFFFFFFFFFFFFEuLL);
    goto LABEL_37;
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)(v18 + 80)) == 1 )
    KeBugCheckEx(0xF5u, 0x6Eu, v18 + 96, v18, 0);
  _InterlockedAnd64(v16, 0xFFFFFFFFFFFFFFFEuLL);
  KeLeaveGuardedRegion();
  v6 = 0;
  *Context = (PFLT_CONTEXT)(v18 + 96);
LABEL_12:
  if ( (byte_1800404C2 & 1) != 0 )
    McTemplateU0spdd_EtwWriteTransfer(
      v11,
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
0x1800093a0  mov     [rsp+arg_18], rbx
0x1800093a5  push    rsi
0x1800093a6  push    rdi
0x1800093a7  push    r12
0x1800093a9  push    r13
0x1800093ab  push    r14
0x1800093ad  sub     rsp, 30h
0x1800093b1  mov     r14, r8
0x1800093b4  lea     r9, [rsp+58h+Entry]
0x1800093b9  mov     rsi, rcx
0x1800093bc  xor     r13d, r13d
0x1800093bf  mov     rcx, [rcx+40h]; OwnerId
0x1800093c3  xor     r8d, r8d
0x1800093c6  mov     [rsp+58h+Entry], r13
0x1800093cb  mov     rbx, rdx
0x1800093ce  call    FltpGetStreamListCtrl
0x1800093d3  mov     r12d, 0C0000225h
0x1800093d9  mov     [rsp+58h+var_30], r13
0x1800093de  mov     r9d, r12d
0x1800093e1  mov     dword ptr [rsp+58h+BugCheckParameter4], 0C00000BBh
0x1800093e9  mov     r8d, 12ADh
0x1800093ef  lea     rdx, aMinkernelFsFil_9; "minkernel\\fs\\filtermgr\\filter\\conte"...
0x1800093f6  mov     ecx, eax
0x1800093f8  mov     edi, eax
0x1800093fa  call    FltpDbgStatus
0x1800093ff  test    eax, eax
0x180009401  js      loc_180009555
0x180009407  mov     rdi, [rsp+58h+Entry]
0x18000940c  mov     [rsp+58h+arg_8], rbp
0x180009411  test    r14, r14
0x180009414  jz      short loc_180009419
0x180009416  mov     [r14], r13
0x180009419  cmp     cs:FltpVelocity, r13b
0x180009420  lea     rbp, [rdi+0E0h]
0x180009427  mov     [rsp+58h+arg_10], r15
0x18000942c  jnz     loc_1800095E4
0x180009432  call    cs:__imp_KeEnterGuardedRegion
0x180009439  nop     dword ptr [rax+rax+00h]
0x18000943e  lea     rcx, [rdi+48h]
0x180009442  xor     edx, edx
0x180009444  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x18000944b  nop     dword ptr [rax+rax+00h]
0x180009450  mov     rcx, [rbp+80h]
0x180009457  test    rcx, rcx
0x18000945a  jz      short loc_18000946D
0x18000945c  cmp     rbx, [rcx+20h]
0x180009460  jz      short loc_1800094CA
0x180009462  jb      short loc_1800094DC
0x180009464  mov     rcx, [rcx+10h]
0x180009468  test    rcx, rcx
0x18000946b  jnz     short loc_18000945C
0x18000946d  xor     edx, edx
0x18000946f  mov     rcx, rax
0x180009472  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x180009479  nop     dword ptr [rax+rax+00h]
0x18000947e  call    cs:__imp_KeLeaveGuardedRegion
0x180009485  nop     dword ptr [rax+rax+00h]
0x18000948a  test    cs:byte_1800404C2, 1
0x180009491  jnz     loc_1800096AB
0x180009497  mov     eax, 0FFFFFFFFh
0x18000949c  lock xadd [rdi+44h], eax
0x1800094a1  cmp     eax, 1
0x1800094a4  jz      loc_18000956D
0x1800094aa  mov     r15, [rsp+58h+arg_10]
0x1800094af  mov     eax, r12d
0x1800094b2  mov     rbp, [rsp+58h+arg_8]
0x1800094b7  mov     rbx, [rsp+58h+arg_18]
0x1800094bc  add     rsp, 30h
0x1800094c0  pop     r14
0x1800094c2  pop     r13
0x1800094c4  pop     r12
0x1800094c6  pop     rdi
0x1800094c7  pop     rsi
0x1800094c8  retn
0x1800094ca  cmp     rsi, [rcx+28h]
0x1800094ce  jz      short loc_1800094E2
0x1800094d0  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800094d4  jz      short loc_1800094E2
0x1800094d6  cmp     rsi, [rcx+28h]
0x1800094da  jmp     short loc_180009462
0x1800094dc  mov     rcx, [rcx+8]
0x1800094e0  jmp     short loc_180009468
0x1800094e2  test    rcx, rcx
0x1800094e5  jz      short loc_18000946D
0x1800094e7  lea     r15, [rcx-18h]
0x1800094eb  mov     ecx, 1
0x1800094f0  lock xadd [r15+50h], ecx
0x1800094f6  inc     ecx
0x1800094f8  cmp     ecx, 1
0x1800094fb  jnz     short loc_180009520
0x1800094fd  lea     r8, [r15+60h]; BugCheckParameter2
0x180009501  mov     [rsp+58h+BugCheckParameter4], r13; BugCheckParameter4
0x180009506  mov     r9, r15; BugCheckParameter3
0x180009509  mov     edx, 6Eh ; 'n'; BugCheckParameter1
0x18000950e  mov     ecx, 0F5h; BugCheckCode
0x180009513  call    cs:__imp_KeBugCheckEx
0x180009520  xor     edx, edx
0x180009522  mov     rcx, rax
0x180009525  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x18000952c  nop     dword ptr [rax+rax+00h]
0x180009531  call    cs:__imp_KeLeaveGuardedRegion
0x180009538  nop     dword ptr [rax+rax+00h]
0x18000953d  test    r15, r15
0x180009540  jz      loc_18000948A
0x180009546  lea     rax, [r15+60h]
0x18000954a  mov     r12d, r13d
0x18000954d  mov     [r14], rax
0x180009550  jmp     loc_18000948A
0x180009555  mov     rbx, [rsp+58h+arg_18]
0x18000955a  mov     eax, edi
0x18000955c  mov     [r14], r13
0x18000955f  add     rsp, 30h
0x180009563  pop     r14
0x180009565  pop     r13
0x180009567  pop     r12
0x180009569  pop     rdi
0x18000956a  pop     rsi
0x18000956b  retn
0x18000956d  lea     rcx, [rdi+48h]
0x180009571  call    cs:__imp_ExCleanupAutoExpandPushLock
0x180009578  nop     dword ptr [rax+rax+00h]
0x18000957d  lea     rcx, [rdi+170h]
0x180009584  call    cs:__imp_ExCleanupAutoExpandPushLock
0x18000958b  nop     dword ptr [rax+rax+00h]
0x180009590  mov     rcx, [rdi+168h]
0x180009597  test    rcx, rcx
0x18000959a  jz      short loc_1800095C9
0x18000959c  mov     rcx, [rcx+140h]; IoWorkItem
0x1800095a3  call    cs:__imp_IoUninitializeWorkItem
0x1800095aa  nop     dword ptr [rax+rax+00h]
0x1800095af  mov     rdx, [rdi+168h]; Entry
0x1800095b6  lea     rcx, stru_18003F1C0; Lookaside
0x1800095bd  call    cs:__imp_ExFreeToNPagedLookasideList
0x1800095c4  nop     dword ptr [rax+rax+00h]
0x1800095c9  mov     rdx, rdi; Entry
0x1800095cc  lea     rcx, stru_18003EB40; Lookaside
0x1800095d3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1800095da  nop     dword ptr [rax+rax+00h]
0x1800095df  jmp     loc_1800094AA
0x1800095e4  call    cs:__imp_KeEnterGuardedRegion
0x1800095eb  nop     dword ptr [rax+rax+00h]
0x1800095f0  mov     r8, rbx
0x1800095f3  mov     ecx, r13d
0x1800095f6  or      r8, 1
0x1800095fa  cmp     ecx, 8
0x1800095fd  jnb     short loc_180009638
0x1800095ff  mov     edx, ecx
0x180009601  shl     rdx, 4
0x180009605  add     rdx, rbp
0x180009608  mov     rax, rbx
0x18000960b  lock cmpxchg [rdx], r8
0x180009610  cmp     rax, r8
0x180009613  jz      short loc_180009608
0x180009615  cmp     rax, rbx
0x180009618  jnz     short loc_180009634
0x18000961a  mov     r15, [rdx+8]
0x18000961e  test    r15, r15
0x180009621  jz      short loc_18000962F
0x180009623  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180009627  jz      short loc_180009656
0x180009629  cmp     rsi, [r15+40h]
0x18000962d  jz      short loc_180009656
0x18000962f  lock and qword ptr [rdx], 0FFFFFFFFFFFFFFFEh
0x180009634  inc     ecx
0x180009636  jmp     short loc_1800095FA
0x180009638  cmp     [rbp+80h], r13
0x18000963f  jz      loc_18000947E
0x180009645  call    cs:__imp_KeLeaveGuardedRegion
0x18000964c  nop     dword ptr [rax+rax+00h]
0x180009651  jmp     loc_180009432
0x180009656  mov     ecx, 1
0x18000965b  lock xadd [r15+50h], ecx
0x180009661  inc     ecx
0x180009663  cmp     ecx, 1
0x180009666  jnz     short loc_18000968B
0x180009668  lea     r8, [r15+60h]; BugCheckParameter2
0x18000966c  mov     [rsp+58h+BugCheckParameter4], r13; BugCheckParameter4
0x180009671  mov     r9, r15; BugCheckParameter3
0x180009674  mov     edx, 6Eh ; 'n'; BugCheckParameter1
0x180009679  mov     ecx, 0F5h; BugCheckCode
0x18000967e  call    cs:__imp_KeBugCheckEx
0x18000968b  lock and qword ptr [rdx], 0FFFFFFFFFFFFFFFEh
0x180009690  call    cs:__imp_KeLeaveGuardedRegion
0x180009697  nop     dword ptr [rax+rax+00h]
0x18000969c  lea     rax, [r15+60h]
0x1800096a0  mov     r12d, r13d
0x1800096a3  mov     [r14], rax
0x1800096a6  jmp     loc_18000948A
0x1800096ab  mov     eax, [rdi+44h]
0x1800096ae  lea     r8, aFltpreleasestr; "FltpReleaseStreamListCtrl"
0x1800096b5  mov     dword ptr [rsp+58h+var_30], eax
0x1800096b9  lea     rdx, StreamListCtrlSup_c754
0x1800096c0  mov     eax, [rdi+40h]
0x1800096c3  mov     r9, rdi
0x1800096c6  mov     dword ptr [rsp+58h+BugCheckParameter4], eax
0x1800096ca  call    McTemplateU0spdd_EtwWriteTransfer
0x1800096cf  jmp     loc_180009497
```
