# UlpScavengerThread

- ea: `0x1c0018880`
- end: `0x1c0018a85`
- name: `UlpScavengerThread`
- size: `517`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1c0003e88`
- `0x1c0018430`
- `0x1c0018880`
- `0x1c001a4b0`
- `0x1c001b610`
- `0x1c008f21c`
- `0x1c008f374`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1c00189d3`
- `ntoskrnl!KeCancelTimer` at `0x1c00189d3`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1c0018a74`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1c0018a74`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1c0018987`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1c0018987`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1c00189bc`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1c00189bc`
- `ntoskrnl!PsTerminateSystemThread` at `0x1c0028da7`
- `ntoskrnl!PsTerminateSystemThread` at `0x1c0028da7`
- `ntoskrnl!KeReadStateEvent` at `0x1c0018906`
- `ntoskrnl!KeReadStateEvent` at `0x1c0018906`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0018958`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0018a0c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0018958`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0018a0c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0018926`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c00189eb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0018926`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c00189eb`

## pseudocode

```c
void __fastcall UlpScavengerThread(PVOID StartContext)
{
  int v1; // edi
  _QWORD *v2; // rax
  char v3; // bl
  __int64 v4; // rcx
  struct _EX_RUNDOWN_REF *v5; // rbx
  _QWORD Count[3]; // [rsp+48h] [rbp-C0h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-A8h] BYREF
  PVOID Object[6]; // [rsp+78h] [rbp-90h] BYREF
  struct _KWAIT_BLOCK WaitBlockArray; // [rsp+A8h] [rbp-60h] BYREF

  HIDWORD(Count[0]) = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(Object, 0, sizeof(Object));
  LOBYTE(Count[0]) = 0;
  *(_OWORD *)&Count[1] = 0;
  v1 = MEMORY[0xFFFFF78000000008];
  while ( !KeReadStateEvent(&UlScavengerTerminateThreadEvent) )
  {
    KeAcquireInStackQueuedSpinLock(&UlScavengerListLock, (PKLOCK_QUEUE_HANDLE)&LockHandle.LockQueue.Lock);
    UlpBuildScavengerWaitArray(
      v1,
      (unsigned int)Count + 4,
      (unsigned int)&Object[1],
      (unsigned int)Count,
      (__int64)&LockHandle);
    KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)&LockHandle.LockQueue.Lock);
    v3 = Count[0];
    if ( LOBYTE(Count[0]) )
      KeSetCoalescableTimer(&UlScavengerWaitTimer, (LARGE_INTEGER)LockHandle.LockQueue.Next, 0, 0x3E8u, 0);
    KeWaitForMultipleObjects(HIDWORD(Count[0]), &Object[1], WaitAny, Executive, 0, 0, 0, &WaitBlockArray);
    if ( v3 )
      KeCancelTimer(&UlScavengerWaitTimer);
    KeAcquireInStackQueuedSpinLock(&UlScavengerListLock, (PKLOCK_QUEUE_HANDLE)&LockHandle.LockQueue.Lock);
    v1 = MEMORY[0xFFFFF78000000008];
    UlpProcessExpiredScavengers(MEMORY[0xFFFFF78000000008], &Count[1]);
    KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)&LockHandle.LockQueue.Lock);
    while ( 1 )
    {
      v2 = (_QWORD *)Count[1];
      if ( (_QWORD *)Count[1] == &Count[1] )
        break;
      if ( *(_QWORD **)(Count[1] + 8LL) != &Count[1]
        || (v4 = *(_QWORD *)Count[1], *(_QWORD *)(*(_QWORD *)Count[1] + 8LL) != Count[1]) )
      {
        __fastfail(3u);
      }
      Count[1] = *(_QWORD *)Count[1];
      *(_QWORD *)(v4 + 8) = &Count[1];
      v5 = (struct _EX_RUNDOWN_REF *)(v2 - 10);
      *v2 = 0;
      v2[1] = 0;
      if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x40000) != 0 )
        WPP_SF_D(16, WPP_aca51a76c72d3da0cfc38652520975af_Traceguids);
      ((void (__fastcall *)(struct _EX_RUNDOWN_REF *))v5[5].Count)(v5);
      ExReleaseRundownProtection(v5 + 13);
    }
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x40000) != 0 )
    WPP_SF_(17, WPP_aca51a76c72d3da0cfc38652520975af_Traceguids);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x1c0018880  mov     rax, rsp
0x1c0018883  mov     [rax+8], rbx
0x1c0018887  mov     [rax+10h], rdi
0x1c001888b  mov     [rax+18h], r15
0x1c001888f  push    rbp
0x1c0018890  lea     rbp, [rax-0A8h]
0x1c0018897  sub     rsp, 1A0h
0x1c001889e  mov     rax, cs:__security_cookie
0x1c00188a5  xor     rax, rsp
0x1c00188a8  mov     [rbp+0A0h+var_10], rax
0x1c00188af  xor     eax, eax
0x1c00188b1  xorps   xmm0, xmm0
0x1c00188b4  and     dword ptr [rsp+1A0h+Count+4], eax
0x1c00188b8  mov     r15, 0FFFFF78000000008h
0x1c00188c2  and     [rsp+1A0h+LockHandle.LockQueue.Next], rax
0x1c00188c7  movups  xmmword ptr [rsp+1A0h+Object+8], xmm0
0x1c00188cc  mov     [rbp+0A0h+var_108], rax
0x1c00188d0  movups  [rbp+0A0h+var_118], xmm0
0x1c00188d4  mov     [rsp+1A0h+Object], rax
0x1c00188d9  movups  xmmword ptr [rsp+1A0h+LockHandle.LockQueue.Lock], xmm0
0x1c00188de  mov     [rsp+1A0h+Count], al
0x1c00188e2  movups  xmmword ptr [rsp+1A0h+Count+8], xmm0
0x1c00188e7  mov     rdi, [r15]
0x1c00188ea  jmp     short loc_1C00188FF
0x1c00188ec  mov     rax, qword ptr [rsp+1A0h+Count+8]
0x1c00188f1  lea     rcx, [rsp+1A0h+Count+8]
0x1c00188f6  cmp     rax, rcx
0x1c00188f9  jnz     loc_1C0018A1D
0x1c00188ff  lea     rcx, UlScavengerTerminateThreadEvent; Event
0x1c0018906  call    cs:__imp_KeReadStateEvent
0x1c001890d  nop     dword ptr [rax+rax+00h]
0x1c0018912  test    eax, eax
0x1c0018914  jnz     loc_1C0028D88
0x1c001891a  lea     rdx, [rsp+1A0h+LockHandle.LockQueue.Lock]; LockHandle
0x1c001891f  lea     rcx, UlScavengerListLock; SpinLock
0x1c0018926  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1c001892d  nop     dword ptr [rax+rax+00h]
0x1c0018932  lea     rax, [rsp+1A0h+LockHandle]
0x1c0018937  mov     rcx, rdi
0x1c001893a  lea     r9, [rsp+1A0h+Count]
0x1c001893f  mov     [rsp+1A0h+Dpc], rax; Dpc
0x1c0018944  lea     r8, [rsp+1A0h+Object+8]
0x1c0018949  lea     rdx, [rsp+1A0h+Count+4]
0x1c001894e  call    UlpBuildScavengerWaitArray
0x1c0018953  lea     rcx, [rsp+1A0h+LockHandle.LockQueue.Lock]; LockHandle
0x1c0018958  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1c001895f  nop     dword ptr [rax+rax+00h]
0x1c0018964  mov     bl, [rsp+1A0h+Count]
0x1c0018968  test    bl, bl
0x1c001896a  jz      short loc_1C0018993
0x1c001896c  and     [rsp+1A0h+Dpc], 0
0x1c0018972  lea     rcx, UlScavengerWaitTimer; Timer
0x1c0018979  mov     rdx, [rsp+1A0h+LockHandle.LockQueue.Next]; DueTime
0x1c001897e  mov     r9d, 3E8h; TolerableDelay
0x1c0018984  xor     r8d, r8d; Period
0x1c0018987  call    cs:__imp_KeSetCoalescableTimer
0x1c001898e  nop     dword ptr [rax+rax+00h]
0x1c0018993  mov     ecx, dword ptr [rsp+1A0h+Count+4]; Count
0x1c0018997  lea     rax, [rbp+0A0h+var_100]
0x1c001899b  mov     [rsp+1A0h+WaitBlockArray], rax; WaitBlockArray
0x1c00189a0  lea     rdx, [rsp+1A0h+Object+8]; Object
0x1c00189a5  and     [rsp+1A0h+var_170], 0
0x1c00189ab  xor     r9d, r9d; WaitReason
0x1c00189ae  mov     [rsp+1A0h+Alertable], 0; Alertable
0x1c00189b3  mov     byte ptr [rsp+1A0h+Dpc], 0; WaitMode
0x1c00189b8  lea     r8d, [r9+1]; WaitType
0x1c00189bc  call    cs:__imp_KeWaitForMultipleObjects
0x1c00189c3  nop     dword ptr [rax+rax+00h]
0x1c00189c8  test    bl, bl
0x1c00189ca  jz      short loc_1C00189DF
0x1c00189cc  lea     rcx, UlScavengerWaitTimer; PKTIMER
0x1c00189d3  call    cs:__imp_KeCancelTimer
0x1c00189da  nop     dword ptr [rax+rax+00h]
0x1c00189df  lea     rdx, [rsp+1A0h+LockHandle.LockQueue.Lock]; LockHandle
0x1c00189e4  lea     rcx, UlScavengerListLock; SpinLock
0x1c00189eb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1c00189f2  nop     dword ptr [rax+rax+00h]
0x1c00189f7  mov     rdi, [r15]
0x1c00189fa  lea     rdx, [rsp+1A0h+Count+8]
0x1c00189ff  mov     rcx, rdi
0x1c0018a02  call    UlpProcessExpiredScavengers
0x1c0018a07  lea     rcx, [rsp+1A0h+LockHandle.LockQueue.Lock]; LockHandle
0x1c0018a0c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1c0018a13  nop     dword ptr [rax+rax+00h]
0x1c0018a18  jmp     loc_1C00188EC
0x1c0018a1d  lea     rcx, [rsp+1A0h+Count+8]
0x1c0018a22  cmp     [rax+8], rcx
0x1c0018a26  jz      short loc_1C0018A2F
0x1c0018a28  mov     ecx, 3
0x1c0018a2d  int     29h; Win8: RtlFailFast(ecx)
0x1c0018a2f  mov     rcx, [rax]
0x1c0018a32  cmp     [rcx+8], rax
0x1c0018a36  jnz     short loc_1C0018A28
0x1c0018a38  mov     qword ptr [rsp+1A0h+Count+8], rcx
0x1c0018a3d  lea     rdx, [rsp+1A0h+Count+8]
0x1c0018a42  mov     [rcx+8], rdx
0x1c0018a46  lea     rbx, [rax-50h]
0x1c0018a4a  and     qword ptr [rax], 0
0x1c0018a4e  and     qword ptr [rax+8], 0
0x1c0018a53  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 40000h
0x1c0018a5d  jnz     loc_1C0028D6E
0x1c0018a63  mov     rax, [rbx+28h]
0x1c0018a67  mov     rcx, rbx
0x1c0018a6a  call    cs:__guard_dispatch_icall_fptr
0x1c0018a70  lea     rcx, [rbx+68h]; RunRef
0x1c0018a74  call    cs:__imp_ExReleaseRundownProtection
0x1c0018a7b  nop     dword ptr [rax+rax+00h]
0x1c0018a80  jmp     loc_1C00188EC
0x1c0028d6e  mov     r8d, [rbx]
0x1c0028d71  lea     rdx, WPP_aca51a76c72d3da0cfc38652520975af_Traceguids
0x1c0028d78  mov     ecx, 10h
0x1c0028d7d  call    WPP_SF_D
0x1c0028d82  nop
0x1c0028d83  jmp     loc_1C0018A63
0x1c0028d88  test    dword ptr cs:WPP_MAIN_CB.Queue, 40000h
0x1c0028d92  jz      short loc_1C0028DA5
0x1c0028d94  mov     ecx, 11h
0x1c0028d99  lea     rdx, WPP_aca51a76c72d3da0cfc38652520975af_Traceguids
0x1c0028da0  call    WPP_SF_
0x1c0028da5  xor     ecx, ecx; ExitStatus
0x1c0028da7  call    cs:__imp_PsTerminateSystemThread
0x1c0028dae  nop     dword ptr [rax+rax+00h]
0x1c0028db3  mov     rcx, [rbp+0A0h+var_10]
0x1c0028dba  xor     rcx, rsp; StackCookie
0x1c0028dbd  call    __security_check_cookie
0x1c0028dc2  lea     r11, [rsp+1A0h+var_s0]
0x1c0028dca  mov     rbx, [r11+10h]
0x1c0028dce  mov     rdi, [r11+18h]
0x1c0028dd2  mov     r15, [r11+20h]
0x1c0028dd6  mov     rsp, r11
0x1c0028dd9  pop     rbp
0x1c0028dda  retn
```
