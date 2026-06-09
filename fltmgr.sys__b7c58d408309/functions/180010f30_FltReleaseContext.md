# FltReleaseContext

- ea: `0x180010f30`
- end: `0x1800113a1`
- name: `FltReleaseContext`
- size: `1137`
- prototype: `void __stdcall(PFLT_CONTEXT Context)`
- caller_count: `11`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180054680`
- `0x180055500`
- `0x180055570`
- `0x180055840`
- `0x1800558d0`
- `0x180055960`
- `0x180055a00`
- `0x180055d30`
- `0x180072360`
- `0x180077c20`
- `0x180080080`

## callees

- `0x180010400`
- `0x180010f30`
- `0x18001bb10`
- `0x180020080`
- `0x180024880`
- `0x180024c00`
- `0x18005dcc0`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x18001111e`
- `ntoskrnl!ExQueueWorkItem` at `0x18001111e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011085`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011085`
- `ntoskrnl!KeBugCheckEx` at `0x180011350`
- `ntoskrnl!KeBugCheckEx` at `0x180011350`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1800110d3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1800110d3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x180011109`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1800112e2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x180011109`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1800112e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1800111fb`
- `ntoskrnl!ObfDereferenceObject` at `0x18001136e`
- `ntoskrnl!ObfDereferenceObject` at `0x1800111fb`
- `ntoskrnl!ObfDereferenceObject` at `0x18001136e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180011068`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180011234`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180011317`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180011068`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180011234`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180011317`
- `ntoskrnl!KeGetCurrentIrql` at `0x180010f6a`
- `ntoskrnl!KeGetCurrentIrql` at `0x180010f6a`
- `ntoskrnl!ZwClose` at `0x180011380`
- `ntoskrnl!ZwClose` at `0x180011380`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180010ff9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180010ff9`
- `ntoskrnl!ExReleaseRundownProtection` at `0x18001100c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x18001100c`
- `ntoskrnl!RtlWalkFrameChain` at `0x1800112b7`
- `ntoskrnl!RtlWalkFrameChain` at `0x1800112b7`

## pseudocode

```c
void __stdcall FltReleaseContext(PFLT_CONTEXT Context)
{
  char *v2; // rbx
  KIRQL CurrentIrql; // al
  int v4; // esi
  int v5; // esi
  struct _EX_RUNDOWN_REF **v6; // r14
  __int16 v7; // ax
  struct _EX_RUNDOWN_REF *v8; // rax
  __int64 v9; // rdi
  __int16 v10; // ax
  int v11; // ecx
  int v12; // eax
  struct _EX_RUNDOWN_REF *v13; // rdi
  int v14; // ecx
  ULONG v15; // edx
  int v16; // ecx
  _QWORD *v17; // rcx
  void *v18; // r15
  volatile signed __int32 *Count; // rcx
  unsigned __int64 v20; // rbx
  void *v21; // rcx
  signed __int64 v22; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-38h] BYREF

  v2 = (char *)Context - 96;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Context - 4, 0xFFFFFFFF) != 1 )
    return;
  if ( (*((_DWORD *)v2 + 18) & 0x10000) != 0 )
    KeBugCheckEx(0xF5u, 0x6Du, (ULONG_PTR)Context, (ULONG_PTR)Context - 96, 0);
  CurrentIrql = KeGetCurrentIrql();
  v4 = *((_DWORD *)v2 + 18);
  if ( CurrentIrql < 2u )
  {
    v5 = *((_DWORD *)v2 + 18) & 2;
    v6 = (struct _EX_RUNDOWN_REF **)*((_QWORD *)v2 + 1);
    v7 = *((_WORD *)v6 + 12);
    if ( v7 == 32 )
    {
      v21 = *(void **)(*(_QWORD *)v2 + 8LL);
      if ( v21 != (void *)-1LL )
      {
        ObfDereferenceObject(v21);
        ZwClose(**(HANDLE **)v2);
      }
      if ( (*((_DWORD *)v2 + 18) & 4) != 0 )
      {
        v22 = _InterlockedCompareExchange64((volatile signed __int64 *)v2 + 2, 0, *((_QWORD *)v2 + 2));
        if ( v22 )
          FltpObjectPointerDereference(v22);
      }
    }
    else if ( v7 == 64 )
    {
      v18 = *(void **)(*(_QWORD *)v2 + 8LL);
      if ( **(_QWORD **)v2 )
        FltObjectDereference(**(PVOID **)v2);
      if ( v18 )
        ObfDereferenceObject(v18);
      memset(*(void **)v2, 0, 0x58u);
    }
    v8 = v6[1];
    if ( v8 )
      ((void (__fastcall *)(PFLT_CONTEXT, _QWORD))v8)(Context, *((unsigned __int16 *)v6 + 12));
    v9 = *((_QWORD *)v2 + 1);
    v10 = *(_WORD *)(v9 + 24);
    if ( v10 == 32 )
    {
      if ( *(_QWORD *)v2 )
        ExFreeToNPagedLookasideList(&stru_18003F040, *(PVOID *)v2);
    }
    else if ( v10 == 64 && *(_QWORD *)v2 )
    {
      ExFreeToNPagedLookasideList(&stru_18003F240, *(PVOID *)v2);
    }
    v11 = *(unsigned __int8 *)(v9 + 27);
    if ( v11 == 1 )
    {
      v12 = *((_DWORD *)v2 + 18);
      if ( (v12 & 1) != 0 )
      {
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(v9 + 192), v2);
LABEL_13:
        v13 = *v6;
        ExReleaseRundownProtection(*v6 + 1);
        if ( (FltGlobals & 0x2000) != 0 && (v13->Count & 0x2000000) != 0
          || (FltGlobals & 0x4000) != 0 && (v13->Count & 0x4000000) != 0
          || (FltGlobals & 0x8000) != 0 && (v13->Count & 0x1000000) != 0 )
        {
          Count = (volatile signed __int32 *)v13[4].Count;
          if ( Count )
          {
            v20 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(Count, 1u) + 1) & 0x3FF) << 7;
            *(_DWORD *)(v20 + v13[4].Count + 8) = -1;
            *(struct _EX_RUNDOWN_REF *)(v20 + v13[4].Count + 16) = v13[1];
            memset((void *)(v20 + v13[4].Count + 24), 0, 0x70u);
            RtlWalkFrameChain((PVOID *)(v20 + v13[4].Count + 24), 0xEu, 0);
          }
        }
        if ( v5 )
          FltpDequeueThrottledWorkItem(1);
        return;
      }
      if ( (v12 & 8) == 0 )
      {
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v9 + 64), v2);
        goto LABEL_13;
      }
      v15 = *(_DWORD *)(v9 + 232);
    }
    else
    {
      v14 = v11 - 2;
      if ( v14 )
      {
        if ( v14 == 1 )
          (*(void (__fastcall **)(char *, _QWORD))(v9 + 40))(v2, *(unsigned __int16 *)(v9 + 24));
        goto LABEL_13;
      }
      v15 = *(_DWORD *)(v9 + 32);
    }
    ExFreePoolWithTag(v2, v15);
    goto LABEL_13;
  }
  *((_DWORD *)v2 + 6) = 2683172;
  *((_DWORD *)v2 + 18) = v4 | 2;
  *((_QWORD *)v2 + 6) = DoFreeContext;
  *((_QWORD *)v2 + 4) = 0;
  *(_QWORD *)&LockHandle.OldIrql = 0;
  *((_QWORD *)v2 + 7) = v2;
  LockHandle.LockQueue = 0;
  KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
  if ( dword_18003FD50 >= (unsigned int)dword_18003FD54 )
  {
    if ( (byte_1800404C4 & 1) != 0 )
      McTemplateU0spddd_EtwWriteTransfer(
        dword_18003FD50,
        (unsigned int)WorkSup_c214,
        (unsigned int)"FltpQueueThrottledWorkItem",
        (_DWORD)v2 + 24,
        1,
        dword_18003FD50,
        dword_18003FD54);
    v17 = (_QWORD *)qword_18003FD48;
    if ( *(__int64 **)qword_18003FD48 != &qword_18003FD40 )
      __fastfail(3u);
    *((_QWORD *)v2 + 5) = qword_18003FD48;
    *((_QWORD *)v2 + 4) = &qword_18003FD40;
    *v17 = v2 + 32;
    qword_18003FD48 = (__int64)(v2 + 32);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  else
  {
    v16 = ++dword_18003FD50;
    if ( (byte_1800404C4 & 1) != 0 )
      McTemplateU0spddd_EtwWriteTransfer(
        v16,
        (unsigned int)WorkSup_c193,
        (unsigned int)"FltpQueueThrottledWorkItem",
        (_DWORD)v2 + 24,
        1,
        v16,
        dword_18003FD54);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    ExQueueWorkItem((PWORK_QUEUE_ITEM)v2 + 1, DelayedWorkQueue);
  }
}

```

## disassembly

```asm
0x180010f30  push    rbx
0x180010f32  push    rdi
0x180010f33  sub     rsp, 68h
0x180010f37  mov     rdi, rcx
0x180010f3a  lea     rbx, [rcx-60h]
0x180010f3e  mov     eax, 0FFFFFFFFh
0x180010f43  lock xadd [rbx+50h], eax
0x180010f48  cmp     eax, 1
0x180010f4b  jz      short loc_180010F55
0x180010f4d  add     rsp, 68h
0x180010f51  pop     rdi
0x180010f52  pop     rbx
0x180010f53  retn
0x180010f55  test    dword ptr [rbx+48h], 10000h
0x180010f5c  jnz     loc_180011339
0x180010f62  mov     [rsp+78h+arg_8], rsi
0x180010f6a  call    cs:__imp_KeGetCurrentIrql
0x180010f71  nop     dword ptr [rax+rax+00h]
0x180010f76  mov     esi, [rbx+48h]
0x180010f79  cmp     al, 2
0x180010f7b  jnb     loc_180011096
0x180010f81  mov     [rsp+78h+arg_10], r14
0x180010f89  and     esi, 2
0x180010f8c  mov     r14, [rbx+8]
0x180010f90  movzx   eax, word ptr [r14+18h]
0x180010f95  cmp     ax, 20h ; ' '
0x180010f99  jz      loc_18001135D
0x180010f9f  cmp     ax, 40h ; '@'
0x180010fa3  jz      loc_1800111DA
0x180010fa9  mov     rax, [r14+8]
0x180010fad  test    rax, rax
0x180010fb0  jz      short loc_180010FBF
0x180010fb2  movzx   edx, word ptr [r14+18h]
0x180010fb7  mov     rcx, rdi
0x180010fba  call    _guard_dispatch_icall
0x180010fbf  mov     rdi, [rbx+8]
0x180010fc3  movzx   eax, word ptr [rdi+18h]
0x180010fc7  cmp     ax, 20h ; ' '
0x180010fcb  jz      loc_180011304
0x180010fd1  cmp     ax, 40h ; '@'
0x180010fd5  jz      loc_180011221
0x180010fdb  movzx   ecx, byte ptr [rdi+1Bh]
0x180010fdf  cmp     ecx, 1
0x180010fe2  jnz     loc_180011076
0x180010fe8  mov     eax, [rbx+48h]
0x180010feb  test    cl, al
0x180010fed  jz      short loc_180011059
0x180010fef  lea     rcx, [rdi+0C0h]; Lookaside
0x180010ff6  mov     rdx, rbx; Entry
0x180010ff9  call    cs:__imp_ExFreeToPagedLookasideList
0x180011000  nop     dword ptr [rax+rax+00h]
0x180011005  mov     rdi, [r14]
0x180011008  lea     rcx, [rdi+8]; RunRef
0x18001100c  call    cs:__imp_ExReleaseRundownProtection
0x180011013  nop     dword ptr [rax+rax+00h]
0x180011018  mov     ecx, cs:FltGlobals
0x18001101e  bt      ecx, 0Dh
0x180011022  jb      loc_1800112F3
0x180011028  bt      ecx, 0Eh
0x18001102c  jb      loc_180011245
0x180011032  bt      ecx, 0Fh
0x180011036  jb      loc_180011328
0x18001103c  mov     r14, [rsp+78h+arg_10]
0x180011044  test    esi, esi
0x180011046  jnz     loc_180011392
0x18001104c  mov     rsi, [rsp+78h+arg_8]
0x180011054  jmp     loc_180010F4D
0x180011059  test    al, 8
0x18001105b  jnz     loc_180011155
0x180011061  lea     rcx, [rdi+40h]; Lookaside
0x180011065  mov     rdx, rbx; Entry
0x180011068  call    cs:__imp_ExFreeToNPagedLookasideList
0x18001106f  nop     dword ptr [rax+rax+00h]
0x180011074  jmp     short loc_180011005
0x180011076  sub     ecx, 2
0x180011079  jnz     loc_180011137
0x18001107f  mov     edx, [rdi+20h]; Tag
0x180011082  mov     rcx, rbx; P
0x180011085  call    cs:__imp_ExFreePoolWithTag
0x18001108c  nop     dword ptr [rax+rax+00h]
0x180011091  jmp     loc_180011005
0x180011096  mov     dword ptr [rbx+18h], 28F124h
0x18001109d  lea     rax, DoFreeContext
0x1800110a4  xor     ecx, ecx
0x1800110a6  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x1800110ab  xorps   xmm0, xmm0
0x1800110ae  or      esi, 2
0x1800110b1  mov     [rbx+48h], esi
0x1800110b4  mov     [rbx+30h], rax
0x1800110b8  xor     eax, eax
0x1800110ba  mov     [rbx+20h], rcx
0x1800110be  lea     rcx, SpinLock; SpinLock
0x1800110c5  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x1800110ca  mov     [rbx+38h], rbx
0x1800110ce  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x1800110d3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1800110da  nop     dword ptr [rax+rax+00h]
0x1800110df  mov     ecx, cs:dword_18003FD50
0x1800110e5  mov     edx, cs:dword_18003FD54
0x1800110eb  cmp     ecx, edx
0x1800110ed  jnb     short loc_180011160
0x1800110ef  inc     ecx
0x1800110f1  test    cs:byte_1800404C4, 1
0x1800110f8  mov     cs:dword_18003FD50, ecx
0x1800110fe  jnz     loc_1800111AE
0x180011104  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x180011109  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x180011110  nop     dword ptr [rax+rax+00h]
0x180011115  lea     rcx, [rbx+20h]; WorkItem
0x180011119  mov     edx, 1; QueueType
0x18001111e  call    cs:__imp_ExQueueWorkItem
0x180011125  nop     dword ptr [rax+rax+00h]
0x18001112a  mov     rsi, [rsp+78h+arg_8]
0x180011132  jmp     loc_180010F4D
0x180011137  cmp     ecx, 1
0x18001113a  jnz     loc_180011005
0x180011140  mov     rax, [rdi+28h]
0x180011144  mov     rcx, rbx
0x180011147  movzx   edx, word ptr [rdi+18h]
0x18001114b  call    _guard_dispatch_icall
0x180011150  jmp     loc_180011005
0x180011155  mov     edx, [rdi+0E8h]
0x18001115b  jmp     loc_180011082
0x180011160  test    cs:byte_1800404C4, 1
0x180011167  jz      short loc_180011190
0x180011169  mov     [rsp+78h+var_48], edx
0x18001116d  lea     r9, [rbx+18h]
0x180011171  mov     [rsp+78h+var_50], ecx
0x180011175  lea     rdx, WorkSup_c214
0x18001117c  lea     r8, aFltpqueuethrot; "FltpQueueThrottledWorkItem"
0x180011183  mov     dword ptr [rsp+78h+BugCheckParameter4], 1
0x18001118b  call    McTemplateU0spddd_EtwWriteTransfer
0x180011190  mov     rcx, cs:qword_18003FD48
0x180011197  lea     rdx, qword_18003FD40
0x18001119e  cmp     [rcx], rdx
0x1800111a1  jz      loc_1800112C8
0x1800111a7  mov     ecx, 3
0x1800111ac  int     29h; Win8: RtlFailFast(ecx)
0x1800111ae  mov     [rsp+78h+var_48], edx
0x1800111b2  lea     r9, [rbx+18h]
0x1800111b6  mov     [rsp+78h+var_50], ecx
0x1800111ba  lea     rdx, WorkSup_c193
0x1800111c1  lea     r8, aFltpqueuethrot; "FltpQueueThrottledWorkItem"
0x1800111c8  mov     dword ptr [rsp+78h+BugCheckParameter4], 1
0x1800111d0  call    McTemplateU0spddd_EtwWriteTransfer
0x1800111d5  jmp     loc_180011104
0x1800111da  mov     rax, [rbx]
0x1800111dd  mov     [rsp+78h+var_18], r15
0x1800111e2  mov     rcx, [rax]; FltObject
0x1800111e5  mov     r15, [rax+8]
0x1800111e9  test    rcx, rcx
0x1800111ec  jz      short loc_1800111F3
0x1800111ee  call    FltObjectDereference
0x1800111f3  test    r15, r15
0x1800111f6  jz      short loc_180011207
0x1800111f8  mov     rcx, r15; Object
0x1800111fb  call    cs:__imp_ObfDereferenceObject
0x180011202  nop     dword ptr [rax+rax+00h]
0x180011207  mov     rcx, [rbx]; void *
0x18001120a  xor     edx, edx; Val
0x18001120c  mov     r8d, 58h ; 'X'; Size
0x180011212  call    memset
0x180011217  mov     r15, [rsp+78h+var_18]
0x18001121c  jmp     loc_180010FA9
0x180011221  mov     rdx, [rbx]; Entry
0x180011224  test    rdx, rdx
0x180011227  jz      loc_180010FDB
0x18001122d  lea     rcx, stru_18003F240; Lookaside
0x180011234  call    cs:__imp_ExFreeToNPagedLookasideList
0x18001123b  nop     dword ptr [rax+rax+00h]
0x180011240  jmp     loc_180010FDB
0x180011245  test    dword ptr [rdi], 4000000h
0x18001124b  jz      loc_180011032
0x180011251  mov     rcx, [rdi+20h]
0x180011255  test    rcx, rcx
0x180011258  jz      loc_18001103C
0x18001125e  mov     ebx, 1
0x180011263  lock xadd [rcx], ebx
0x180011267  mov     rax, [rdi+20h]
0x18001126b  inc     ebx
0x18001126d  and     ebx, 3FFh
0x180011273  xor     edx, edx; Val
0x180011275  shl     rbx, 7
0x180011279  mov     r8d, 70h ; 'p'; Size
0x18001127f  mov     dword ptr [rbx+rax+8], 0FFFFFFFFh
0x180011287  mov     rcx, [rdi+20h]
0x18001128b  mov     rax, [rdi+8]
0x18001128f  mov     [rbx+rcx+10h], rax
0x180011294  mov     rcx, [rdi+20h]
0x180011298  add     rcx, 18h
0x18001129c  add     rcx, rbx; void *
0x18001129f  call    memset
0x1800112a4  mov     rcx, [rdi+20h]
0x1800112a8  xor     r8d, r8d; Flags
0x1800112ab  add     rcx, 18h
0x1800112af  mov     edx, 0Eh; Count
0x1800112b4  add     rcx, rbx; Callers
0x1800112b7  call    cs:__imp_RtlWalkFrameChain
0x1800112be  nop     dword ptr [rax+rax+00h]
0x1800112c3  jmp     loc_18001103C
0x1800112c8  lea     rax, [rbx+20h]
0x1800112cc  mov     [rax+8], rcx
0x1800112d0  mov     [rax], rdx
0x1800112d3  mov     [rcx], rax
0x1800112d6  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1800112db  mov     cs:qword_18003FD48, rax
0x1800112e2  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1800112e9  nop     dword ptr [rax+rax+00h]
0x1800112ee  jmp     loc_18001104C
0x1800112f3  test    dword ptr [rdi], 2000000h
0x1800112f9  jnz     loc_180011251
0x1800112ff  jmp     loc_180011028
0x180011304  mov     rdx, [rbx]; Entry
0x180011307  test    rdx, rdx
0x18001130a  jz      loc_180010FDB
0x180011310  lea     rcx, stru_18003F040; Lookaside
0x180011317  call    cs:__imp_ExFreeToNPagedLookasideList
0x18001131e  nop     dword ptr [rax+rax+00h]
0x180011323  jmp     loc_180010FDB
0x180011328  test    dword ptr [rdi], 1000000h
0x18001132e  jz      loc_18001103C
0x180011334  jmp     loc_180011251
0x180011339  xor     ecx, ecx
0x18001133b  mov     r9, rbx; BugCheckParameter3
0x18001133e  mov     [rsp+78h+BugCheckParameter4], rcx; BugCheckParameter4
0x180011343  mov     r8, rdi; BugCheckParameter2
0x180011346  mov     ecx, 0F5h; BugCheckCode
0x18001134b  mov     edx, 6Dh ; 'm'; BugCheckParameter1
0x180011350  call    cs:__imp_KeBugCheckEx
0x18001135d  mov     rax, [rbx]
0x180011360  mov     rcx, [rax+8]; Object
0x180011364  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011368  jz      loc_180025D50
0x18001136e  call    cs:__imp_ObfDereferenceObject
0x180011375  nop     dword ptr [rax+rax+00h]
0x18001137a  mov     rcx, [rbx]
0x18001137d  mov     rcx, [rcx]; Handle
0x180011380  call    cs:__imp_ZwClose
0x180011387  nop     dword ptr [rax+rax+00h]
0x18001138c  nop
0x18001138d  jmp     loc_180025D50
0x180011392  mov     ecx, 1
0x180011397  call    FltpDequeueThrottledWorkItem
0x18001139c  jmp     loc_18001104C
0x180025d50  mov     eax, [rbx+48h]
0x180025d53  test    al, 4
0x180025d55  jz      loc_180010FA9
0x180025d5b  mov     rax, [rbx+10h]
0x180025d5f  xor     ecx, ecx
0x180025d61  lock cmpxchg [rbx+10h], rcx
0x180025d67  test    rax, rax
0x180025d6a  jz      loc_180010FA9
0x180025d70  mov     rcx, rax
0x180025d73  call    FltpObjectPointerDereference
0x180025d78  nop
0x180025d79  jmp     loc_180010FA9
```
