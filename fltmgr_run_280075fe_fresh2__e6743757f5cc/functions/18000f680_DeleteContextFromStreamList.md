# DeleteContextFromStreamList

- ea: `0x18000f680`
- end: `0x18000f9c2`
- name: `DeleteContextFromStreamList`
- size: `834`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dc10`
- `0x180060fd0`

## callees

- `0x18000d600`
- `0x18000f680`
- `0x18000f9d0`
- `0x180014c10`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x18000f9b5`
- `ntoskrnl!KeBugCheckEx` at `0x18000f9b5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000f89d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000f8b3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000f89d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000f8b3`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18000f6c5`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18000f6c5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000f71d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000f7b1`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000f71d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18000f7b1`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000f81c`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000f81c`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18000f6d6`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18000f6d6`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000f711`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000f7a5`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000f711`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000f7a5`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000f851`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000f864`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000f851`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000f864`
- `ntoskrnl!IoUninitializeWorkItem` at `0x18000f883`
- `ntoskrnl!IoUninitializeWorkItem` at `0x18000f883`
- `ntoskrnl!RtlDelete` at `0x18000f77c`
- `ntoskrnl!RtlDelete` at `0x18000f77c`

## pseudocode

```c
__int64 __fastcall DeleteContextFromStreamList(
        __int64 a1,
        __int16 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        _QWORD *a5)
{
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rbp
  __int64 v10; // rbx
  bool v11; // cf
  ULONG_PTR v13; // rdi
  signed __int64 v14; // rax
  signed __int64 v15; // rbp
  __int64 v16; // rcx
  unsigned int v17; // edx
  signed __int64 v18; // r8
  __int64 v19; // rcx
  signed __int64 v20; // rax
  __int64 v21; // rax

  if ( a5 )
    *a5 = 0;
  if ( a2 == 16 )
  {
    v7 = 224;
  }
  else
  {
    if ( a2 != 8 )
      return 3221226021LL;
    v7 = 88;
  }
  v8 = v7 + a1;
  v9 = a1 + 72;
  KeEnterGuardedRegion();
  ExAcquireAutoExpandPushLockExclusive(v9, 0);
  if ( FltpVelocity )
  {
    v17 = 0;
    v18 = a3 | 1;
    while ( v17 < 8 )
    {
      v19 = v8 + 16LL * v17;
      do
        v20 = _InterlockedCompareExchange64((volatile signed __int64 *)v19, v18, a3);
      while ( v20 == v18 );
      if ( v20 == a3 )
      {
        v21 = *(_QWORD *)(v19 + 8);
        if ( v21 && (a4 == -1 || a4 == *(_QWORD *)(v21 + 64)) )
        {
          if ( v19 )
          {
            v13 = *(_QWORD *)(v19 + 8);
            *(_QWORD *)(v19 + 8) = 0;
            _InterlockedAnd64((volatile signed __int64 *)v19, 0);
            *(_QWORD *)(v13 + 48) = 0;
            *(_DWORD *)(v13 + 72) &= ~0x10000u;
            *(_OWORD *)(v13 + 24) = 0;
            *(_QWORD *)(v13 + 40) = 0;
            goto LABEL_21;
          }
          break;
        }
        _InterlockedAnd64((volatile signed __int64 *)v19, 0xFFFFFFFFFFFFFFFEuLL);
      }
      ++v17;
    }
  }
  v10 = *(_QWORD *)(v8 + 128);
  if ( !v10 )
  {
LABEL_11:
    ExReleaseAutoExpandPushLockExclusive(v9, 0);
    KeLeaveGuardedRegion();
    return 3221226021LL;
  }
  while ( 1 )
  {
    v11 = a3 < *(_QWORD *)(v10 + 32);
    if ( a3 == *(_QWORD *)(v10 + 32) )
      break;
LABEL_8:
    if ( v11 )
      v10 = *(_QWORD *)(v10 + 8);
    else
      v10 = *(_QWORD *)(v10 + 16);
    if ( !v10 )
      goto LABEL_11;
  }
  if ( a4 != *(_QWORD *)(v10 + 40) && a4 != -1 )
  {
    v11 = a4 < *(_QWORD *)(v10 + 40);
    goto LABEL_8;
  }
  v13 = v10 - 24;
  **(_QWORD **)(v10 + 24) = RtlDelete((PRTL_SPLAY_LINKS)v10);
  if ( (*(_DWORD *)(v10 + 48) & 0x10000) != 0 )
    _InterlockedAnd((volatile signed __int32 *)(v10 + 48), 0xFFFEFFFF);
LABEL_21:
  ExReleaseAutoExpandPushLockExclusive(v9, 0);
  KeLeaveGuardedRegion();
  if ( !v13 )
    return 3221226021LL;
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
  if ( a5 )
  {
    *a5 = v13 + 96;
    return 0;
  }
  else
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 80), 0xFFFFFFFF) != 1 )
      return 0;
    if ( (*(_DWORD *)(v13 + 72) & 0x10000) != 0 )
      KeBugCheckEx(0xF5u, 0x6Du, v13 + 96, v13, 0);
    if ( KeGetCurrentIrql() >= 2u )
    {
      *(_DWORD *)(v13 + 72) |= 2u;
      *(_WORD *)(v13 + 24) = -3804;
      *(_WORD *)(v13 + 26) = 40;
      *(_QWORD *)(v13 + 48) = DoFreeContext;
      *(_QWORD *)(v13 + 56) = v13;
      *(_QWORD *)(v13 + 32) = 0;
      FltpQueueThrottledWorkItem(v13 + 24, 1);
      return 0;
    }
    else
    {
      DoFreeContext((void ***)v13);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18000f680  mov     [rsp+arg_18], rsi
0x18000f685  push    rdi
0x18000f686  push    r14
0x18000f688  push    r15
0x18000f68a  sub     rsp, 30h
0x18000f68e  mov     r14, [rsp+48h+arg_20]
0x18000f693  xor     r15d, r15d
0x18000f696  mov     rsi, r9
0x18000f699  mov     rdi, r8
0x18000f69c  test    r14, r14
0x18000f69f  jz      short loc_18000F6A4
0x18000f6a1  mov     [r14], r15
0x18000f6a4  mov     [rsp+48h+arg_0], rbx
0x18000f6a9  mov     [rsp+48h+arg_10], rbp
0x18000f6ae  cmp     dx, 10h
0x18000f6b2  jnz     loc_18000F760
0x18000f6b8  mov     eax, 0E0h
0x18000f6bd  lea     rbx, [rax+rcx]
0x18000f6c1  lea     rbp, [rcx+48h]
0x18000f6c5  call    cs:__imp_KeEnterGuardedRegion
0x18000f6cc  nop     dword ptr [rax+rax+00h]
0x18000f6d1  xor     edx, edx
0x18000f6d3  mov     rcx, rbp
0x18000f6d6  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x18000f6dd  nop     dword ptr [rax+rax+00h]
0x18000f6e2  cmp     cs:FltpVelocity, r15b
0x18000f6e9  jnz     loc_18000F8C4
0x18000f6ef  mov     rbx, [rbx+80h]
0x18000f6f6  test    rbx, rbx
0x18000f6f9  jz      short loc_18000F70C
0x18000f6fb  cmp     rdi, [rbx+20h]
0x18000f6ff  jz      short loc_18000F748
0x18000f701  jb      short loc_18000F75A
0x18000f703  mov     rbx, [rbx+10h]
0x18000f707  test    rbx, rbx
0x18000f70a  jnz     short loc_18000F6FB
0x18000f70c  xor     edx, edx
0x18000f70e  mov     rcx, rbp
0x18000f711  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x18000f718  nop     dword ptr [rax+rax+00h]
0x18000f71d  call    cs:__imp_KeLeaveGuardedRegion
0x18000f724  nop     dword ptr [rax+rax+00h]
0x18000f729  mov     eax, 0C0000225h
0x18000f72e  mov     rbp, [rsp+48h+arg_10]
0x18000f733  mov     rbx, [rsp+48h+arg_0]
0x18000f738  mov     rsi, [rsp+48h+arg_18]
0x18000f73d  add     rsp, 30h
0x18000f741  pop     r15
0x18000f743  pop     r14
0x18000f745  pop     rdi
0x18000f746  retn
0x18000f748  cmp     rsi, [rbx+28h]
0x18000f74c  jz      short loc_18000F770
0x18000f74e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000f752  jz      short loc_18000F770
0x18000f754  cmp     rsi, [rbx+28h]
0x18000f758  jmp     short loc_18000F701
0x18000f75a  mov     rbx, [rbx+8]
0x18000f75e  jmp     short loc_18000F707
0x18000f760  cmp     dx, 8
0x18000f764  jnz     short loc_18000F729
0x18000f766  mov     eax, 58h ; 'X'
0x18000f76b  jmp     loc_18000F6BD
0x18000f770  test    rbx, rbx
0x18000f773  jz      short loc_18000F70C
0x18000f775  mov     rcx, rbx; Links
0x18000f778  lea     rdi, [rbx-18h]
0x18000f77c  call    cs:__imp_RtlDelete
0x18000f783  nop     dword ptr [rax+rax+00h]
0x18000f788  mov     rcx, [rbx+18h]
0x18000f78c  mov     [rcx], rax
0x18000f78f  mov     eax, [rbx+30h]
0x18000f792  bt      eax, 10h
0x18000f796  jnb     short loc_18000F7A0
0x18000f798  lock and dword ptr [rbx+30h], 0FFFEFFFFh
0x18000f7a0  xor     edx, edx
0x18000f7a2  mov     rcx, rbp
0x18000f7a5  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x18000f7ac  nop     dword ptr [rax+rax+00h]
0x18000f7b1  call    cs:__imp_KeLeaveGuardedRegion
0x18000f7b8  nop     dword ptr [rax+rax+00h]
0x18000f7bd  test    rdi, rdi
0x18000f7c0  jz      loc_18000F729
0x18000f7c6  mov     rax, [rdi+10h]
0x18000f7ca  mov     rcx, r15
0x18000f7cd  lock cmpxchg [rdi+10h], rcx
0x18000f7d3  mov     rbp, rax
0x18000f7d6  mov     ebx, 0FFFFFFFFh
0x18000f7db  test    rax, rax
0x18000f7de  jz      short loc_18000F7F9
0x18000f7e0  test    cs:byte_1800404C2, 1
0x18000f7e7  jnz     loc_18000F976
0x18000f7ed  mov     eax, ebx
0x18000f7ef  lock xadd [rbp+44h], eax
0x18000f7f4  cmp     eax, 1
0x18000f7f7  jz      short loc_18000F84D
0x18000f7f9  test    r14, r14
0x18000f7fc  jnz     short loc_18000F83F
0x18000f7fe  lock xadd [rdi+50h], ebx
0x18000f803  cmp     ebx, 1
0x18000f806  jz      short loc_18000F80F
0x18000f808  xor     eax, eax
0x18000f80a  jmp     loc_18000F72E
0x18000f80f  test    dword ptr [rdi+48h], 10000h
0x18000f816  jnz     loc_18000F99F
0x18000f81c  call    cs:__imp_KeGetCurrentIrql
0x18000f823  nop     dword ptr [rax+rax+00h]
0x18000f828  cmp     al, 2
0x18000f82a  jnb     loc_18000F910
0x18000f830  mov     rcx, rdi; P
0x18000f833  call    DoFreeContext
0x18000f838  xor     eax, eax
0x18000f83a  jmp     loc_18000F72E
0x18000f83f  lea     rax, [rdi+60h]
0x18000f843  mov     [r14], rax
0x18000f846  xor     eax, eax
0x18000f848  jmp     loc_18000F72E
0x18000f84d  lea     rcx, [rbp+48h]
0x18000f851  call    cs:__imp_ExCleanupAutoExpandPushLock
0x18000f858  nop     dword ptr [rax+rax+00h]
0x18000f85d  lea     rcx, [rbp+170h]
0x18000f864  call    cs:__imp_ExCleanupAutoExpandPushLock
0x18000f86b  nop     dword ptr [rax+rax+00h]
0x18000f870  mov     rcx, [rbp+168h]
0x18000f877  test    rcx, rcx
0x18000f87a  jz      short loc_18000F8A9
0x18000f87c  mov     rcx, [rcx+140h]; IoWorkItem
0x18000f883  call    cs:__imp_IoUninitializeWorkItem
0x18000f88a  nop     dword ptr [rax+rax+00h]
0x18000f88f  mov     rdx, [rbp+168h]; Entry
0x18000f896  lea     rcx, stru_18003F1C0; Lookaside
0x18000f89d  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000f8a4  nop     dword ptr [rax+rax+00h]
0x18000f8a9  mov     rdx, rbp; Entry
0x18000f8ac  lea     rcx, stru_18003EB40; Lookaside
0x18000f8b3  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000f8ba  nop     dword ptr [rax+rax+00h]
0x18000f8bf  jmp     loc_18000F7F9
0x18000f8c4  mov     r8, rdi
0x18000f8c7  mov     edx, r15d
0x18000f8ca  or      r8, 1
0x18000f8ce  cmp     edx, 8
0x18000f8d1  jnb     loc_18000F6EF
0x18000f8d7  mov     ecx, edx
0x18000f8d9  shl     rcx, 4
0x18000f8dd  add     rcx, rbx
0x18000f8e0  mov     rax, rdi
0x18000f8e3  lock cmpxchg [rcx], r8
0x18000f8e8  cmp     rax, r8
0x18000f8eb  jz      short loc_18000F8E0
0x18000f8ed  cmp     rax, rdi
0x18000f8f0  jnz     short loc_18000F90C
0x18000f8f2  mov     rax, [rcx+8]
0x18000f8f6  test    rax, rax
0x18000f8f9  jz      short loc_18000F907
0x18000f8fb  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000f8ff  jz      short loc_18000F945
0x18000f901  cmp     rsi, [rax+40h]
0x18000f905  jz      short loc_18000F945
0x18000f907  lock and qword ptr [rcx], 0FFFFFFFFFFFFFFFEh
0x18000f90c  inc     edx
0x18000f90e  jmp     short loc_18000F8CE
0x18000f910  or      dword ptr [rdi+48h], 2
0x18000f914  lea     rcx, [rdi+18h]
0x18000f918  mov     word ptr [rcx], 0F124h
0x18000f91d  lea     rax, DoFreeContext
0x18000f924  mov     word ptr [rdi+1Ah], 28h ; '('
0x18000f92a  mov     edx, 1
0x18000f92f  mov     [rdi+30h], rax
0x18000f933  mov     [rdi+38h], rdi
0x18000f937  mov     [rdi+20h], r15
0x18000f93b  call    FltpQueueThrottledWorkItem
0x18000f940  jmp     loc_18000F808
0x18000f945  test    rcx, rcx
0x18000f948  jz      loc_18000F6EF
0x18000f94e  mov     rdi, rax
0x18000f951  mov     [rcx+8], r15
0x18000f955  lock and [rcx], r15
0x18000f959  xor     eax, eax
0x18000f95b  mov     [rdi+30h], r15
0x18000f95f  and     dword ptr [rdi+48h], 0FFFEFFFFh
0x18000f966  xorps   xmm0, xmm0
0x18000f969  movups  xmmword ptr [rdi+18h], xmm0
0x18000f96d  mov     [rdi+28h], rax
0x18000f971  jmp     loc_18000F7A0
0x18000f976  mov     ecx, [rax+44h]
0x18000f979  lea     r8, aFltpreleasestr; "FltpReleaseStreamListCtrl"
0x18000f980  mov     [rsp+48h+var_20], ecx
0x18000f984  lea     rdx, StreamListCtrlSup_c754
0x18000f98b  mov     ecx, [rax+40h]
0x18000f98e  mov     r9, rbp
0x18000f991  mov     dword ptr [rsp+48h+BugCheckParameter4], ecx
0x18000f995  call    McTemplateU0spdd_EtwWriteTransfer
0x18000f99a  jmp     loc_18000F7ED
0x18000f99f  lea     r8, [rdi+60h]; BugCheckParameter2
0x18000f9a3  mov     [rsp+48h+BugCheckParameter4], r15; BugCheckParameter4
0x18000f9a8  mov     r9, rdi; BugCheckParameter3
0x18000f9ab  mov     edx, 6Dh ; 'm'; BugCheckParameter1
0x18000f9b0  mov     ecx, 0F5h; BugCheckCode
0x18000f9b5  call    cs:__imp_KeBugCheckEx
```
