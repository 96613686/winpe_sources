# UlpScavengerThread

- ea: `0x140099b10`
- end: `0x140099f03`
- name: `UlpScavengerThread`
- size: `1011`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140099b10`
- `0x140099f0c`
- `0x140167700`
- `0x1401677e0`
- `0x1401c3f58`
- `0x1401d9e44`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140099d36`
- `ntoskrnl!KeCancelTimer` at `0x140099d36`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140099d22`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140099d22`
- `ntoskrnl!PsTerminateSystemThread` at `0x140099e88`
- `ntoskrnl!PsTerminateSystemThread` at `0x140099e88`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140099cec`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140099cec`
- `ntoskrnl!KeReadStateEvent` at `0x140099b6d`
- `ntoskrnl!KeReadStateEvent` at `0x140099b6d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140099df2`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140099df2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140099b94`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140099d4e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140099b94`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140099d4e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140099cb8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140099d79`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140099cb8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140099d79`

## pseudocode

```c
void __fastcall UlpScavengerThread(PVOID StartContext)
{
  unsigned __int64 v1; // r14
  unsigned __int64 v2; // r9
  __int64 *v3; // r8
  __int64 v4; // rdi
  int v5; // r11d
  unsigned __int64 v6; // r10
  unsigned __int64 v7; // rax
  char v8; // si
  LARGE_INTEGER v9; // rbx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  unsigned int *v12; // rbx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  __int128 v15; // [rsp+40h] [rbp-C0h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-B0h] BYREF
  PVOID Object[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v18; // [rsp+78h] [rbp-88h]
  __int64 v19; // [rsp+88h] [rbp-78h]
  struct _KWAIT_BLOCK WaitBlockArray; // [rsp+90h] [rbp-70h] BYREF

  v19 = 0;
  *(_OWORD *)Object = 0;
  v18 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v15 = 0;
  v1 = MEMORY[0xFFFFF78000000008];
  while ( !KeReadStateEvent(&UlScavengerTerminateThreadEvent) )
  {
    KeAcquireInStackQueuedSpinLock(&UlScavengerListLock, &LockHandle);
    v2 = -1;
    v3 = (__int64 *)UlScavengerEnabledList;
    v4 = 0;
    v5 = 8;
    v6 = (-(__int64)(UlPartitionsActiveCount != 0) & 0xFFFFFFFF502A9280uLL) + 3000000000u;
    if ( (__int64 *)UlScavengerEnabledList == &UlScavengerEnabledList )
      goto LABEL_14;
    do
    {
      if ( *((_DWORD *)v3 - 15) == 1 )
      {
        v7 = *(v3 - 5);
        if ( v1 < v7 )
        {
          if ( v7 < v2 )
          {
            v2 = *(v3 - 5);
            goto LABEL_35;
          }
        }
        else if ( (unsigned int)v4 < 5 )
        {
          Object[v4] = (PVOID)*(v3 - 7);
          v4 = (unsigned int)(v4 + 1);
        }
      }
      else
      {
        v13 = *(v3 - 6);
        if ( v13 < v2 )
        {
          v14 = *((_BYTE *)v3 - 40) ? 50000000 * ((v13 + 49999999) / 0x2FAF080) : v13 + v6 - 1 - (v13 + v6 - 1) % v6;
          if ( v14 < v2 )
          {
            v2 = v14;
LABEL_35:
            v5 = *((_DWORD *)v3 - 16);
          }
        }
      }
      v3 = (__int64 *)*v3;
    }
    while ( v3 != &UlScavengerEnabledList );
    if ( v2 != -1 )
    {
      v8 = 1;
      v9.QuadPart = (v1 - v2) & ((v1 - (unsigned __int128)v2) >> 64);
      if ( (unsigned int)v4 < 5 )
      {
        Object[v4] = &UlScavengerWaitTimer;
        v4 = (unsigned int)(v4 + 1);
      }
      if ( (BYTE10(xmmword_1401A2CA0) & 8) != 0 )
        WPP_SF_Dd(1299, 14, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids, v9.QuadPart / -10000, v5);
      goto LABEL_16;
    }
LABEL_14:
    v8 = 0;
    v9.QuadPart = 0;
    if ( (BYTE10(xmmword_1401A2CA0) & 8) != 0 )
      WPP_SF_(1299, 15, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids);
LABEL_16:
    if ( (unsigned int)v4 < 5 )
    {
      Object[v4] = &UlScavengerTerminateThreadEvent;
      v4 = (unsigned int)(v4 + 1);
      if ( (unsigned int)v4 < 5 )
      {
        Object[v4] = &UlScavengerRefreshEvent;
        LODWORD(v4) = v4 + 1;
      }
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v8 )
      KeSetCoalescableTimer(&UlScavengerWaitTimer, v9, 0, 0x3E8u, 0);
    KeWaitForMultipleObjects(v4, Object, WaitAny, Executive, 0, 0, 0, &WaitBlockArray);
    if ( v8 )
      KeCancelTimer(&UlScavengerWaitTimer);
    KeAcquireInStackQueuedSpinLock(&UlScavengerListLock, &LockHandle);
    v1 = MEMORY[0xFFFFF78000000008];
    UlpProcessExpiredScavengers(MEMORY[0xFFFFF78000000008], &v15);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    while ( 1 )
    {
      v10 = (_QWORD *)v15;
      if ( (__int128 *)v15 == &v15 )
        break;
      if ( *(__int128 **)(v15 + 8) != &v15 || (v11 = *(_QWORD *)v15, *(_QWORD *)(*(_QWORD *)v15 + 8LL) != (_QWORD)v15) )
        __fastfail(3u);
      *(_QWORD *)&v15 = *(_QWORD *)v15;
      *(_QWORD *)(v11 + 8) = &v15;
      v12 = (unsigned int *)(v10 - 10);
      *v10 = 0;
      v10[1] = 0;
      if ( (BYTE10(xmmword_1401A2CA0) & 8) != 0 )
        WPP_SF_d(1299, 16, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids, *v12);
      (*((void (__fastcall **)(unsigned int *))v12 + 5))(v12);
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)v12 + 13);
    }
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_(1043, 17, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140099b10  push    rbp
0x140099b12  push    rbx
0x140099b13  push    rsi
0x140099b14  push    rdi
0x140099b15  push    r14
0x140099b17  lea     rbp, [rsp-90h]
0x140099b1f  sub     rsp, 190h
0x140099b26  mov     rax, cs:__security_cookie
0x140099b2d  xor     rax, rsp
0x140099b30  mov     [rbp+0B0h+var_30], rax
0x140099b37  xorps   xmm0, xmm0
0x140099b3a  xor     eax, eax
0x140099b3c  mov     [rbp+0B0h+var_128], rax
0x140099b40  mov     qword ptr [rsp+1B0h+LockHandle.OldIrql], rax
0x140099b45  mov     rax, 0FFFFF78000000008h
0x140099b4f  movups  xmmword ptr [rsp+1B0h+Object], xmm0
0x140099b54  movups  [rsp+1B0h+var_138], xmm0
0x140099b59  movups  xmmword ptr [rsp+1B0h+LockHandle.LockQueue.Next], xmm0
0x140099b5e  movups  [rsp+1B0h+var_170], xmm0
0x140099b63  mov     r14, [rax]
0x140099b66  lea     rcx, UlScavengerTerminateThreadEvent; Event
0x140099b6d  call    cs:__imp_KeReadStateEvent
0x140099b74  nop     dword ptr [rax+rax+00h]
0x140099b79  test    eax, eax
0x140099b7b  jnz     loc_140099E7D
0x140099b81  lea     rdx, [rsp+1B0h+LockHandle]; LockHandle
0x140099b86  lea     rcx, UlScavengerListLock; SpinLock
0x140099b8d  lea     rsi, UlScavengerEnabledList
0x140099b94  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140099b9b  nop     dword ptr [rax+rax+00h]
0x140099ba0  mov     eax, cs:UlPartitionsActiveCount
0x140099ba6  or      r9, 0FFFFFFFFFFFFFFFFh
0x140099baa  mov     r8, cs:UlScavengerEnabledList
0x140099bb1  xor     edi, edi
0x140099bb3  neg     eax
0x140099bb5  mov     r11d, 8
0x140099bbb  mov     rax, 0FFFFFFFF502A9280h
0x140099bc5  sbb     r10, r10
0x140099bc8  and     r10, rax
0x140099bcb  mov     eax, 0B2D05E00h
0x140099bd0  add     r10, rax
0x140099bd3  cmp     r8, rsi
0x140099bd6  jz      loc_140099C7B
0x140099bdc  cmp     dword ptr [r8-3Ch], 1
0x140099be1  jnz     loc_140099E00
0x140099be7  mov     rax, [r8-28h]
0x140099beb  cmp     r14, rax
0x140099bee  jb      loc_140099E3B
0x140099bf4  cmp     edi, 5
0x140099bf7  jnb     short loc_140099C04
0x140099bf9  mov     rax, [r8-38h]
0x140099bfd  mov     [rsp+rdi*8+1B0h+Object], rax
0x140099c02  inc     edi
0x140099c04  mov     r8, [r8]
0x140099c07  cmp     r8, rsi
0x140099c0a  jnz     short loc_140099BDC
0x140099c0c  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x140099c10  jz      short loc_140099C7B
0x140099c12  mov     rax, r14
0x140099c15  mov     sil, 1
0x140099c18  sub     rax, r9
0x140099c1b  cmp     r14, r9
0x140099c1e  sbb     rbx, rbx
0x140099c21  and     rbx, rax
0x140099c24  cmp     edi, 5
0x140099c27  jnb     short loc_140099C37
0x140099c29  lea     rcx, UlScavengerWaitTimer
0x140099c30  mov     [rsp+rdi*8+1B0h+Object], rcx
0x140099c35  inc     edi
0x140099c37  test    byte ptr cs:xmmword_1401A2CA0+0Ah, 8
0x140099c3e  jz      short loc_140099C8D
0x140099c40  mov     rax, 0CB923A29C779A6B5h
0x140099c4a  mov     dword ptr [rsp+1B0h+Dpc], r11d
0x140099c4f  imul    rbx
0x140099c52  mov     ecx, 513h
0x140099c57  lea     r8, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids
0x140099c5e  mov     r9, rdx
0x140099c61  mov     edx, 0Eh
0x140099c66  sar     r9, 0Bh
0x140099c6a  mov     rax, r9
0x140099c6d  shr     rax, 3Fh
0x140099c71  add     r9, rax
0x140099c74  call    WPP_SF_Dd
0x140099c79  jmp     short loc_140099C8D
0x140099c7b  xor     sil, sil
0x140099c7e  xor     ebx, ebx
0x140099c80  test    byte ptr cs:xmmword_1401A2CA0+0Ah, 8
0x140099c87  jnz     loc_140099EB2
0x140099c8d  cmp     edi, 5
0x140099c90  jnb     short loc_140099CB3
0x140099c92  lea     rcx, UlScavengerTerminateThreadEvent
0x140099c99  mov     [rsp+rdi*8+1B0h+Object], rcx
0x140099c9e  inc     edi
0x140099ca0  cmp     edi, 5
0x140099ca3  jnb     short loc_140099CB3
0x140099ca5  lea     rcx, UlScavengerRefreshEvent
0x140099cac  mov     [rsp+rdi*8+1B0h+Object], rcx
0x140099cb1  inc     edi
0x140099cb3  lea     rcx, [rsp+1B0h+LockHandle]; LockHandle
0x140099cb8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140099cbf  nop     dword ptr [rax+rax+00h]
0x140099cc4  test    sil, sil
0x140099cc7  jz      loc_140099E6A
0x140099ccd  mov     rdx, rbx; DueTime
0x140099cd0  mov     [rsp+1B0h+Dpc], 0; Dpc
0x140099cd9  lea     rbx, UlScavengerWaitTimer
0x140099ce0  mov     r9d, 3E8h; TolerableDelay
0x140099ce6  mov     rcx, rbx; Timer
0x140099ce9  xor     r8d, r8d; Period
0x140099cec  call    cs:__imp_KeSetCoalescableTimer
0x140099cf3  nop     dword ptr [rax+rax+00h]
0x140099cf8  xor     r9d, r9d; WaitReason
0x140099cfb  lea     rax, [rbp+0B0h+var_120]
0x140099cff  mov     [rsp+1B0h+WaitBlockArray], rax; WaitBlockArray
0x140099d04  lea     rdx, [rsp+1B0h+Object]; Object
0x140099d09  mov     [rsp+1B0h+Timeout], 0; Timeout
0x140099d12  mov     ecx, edi; Count
0x140099d14  mov     [rsp+1B0h+Alertable], 0; Alertable
0x140099d19  lea     r8d, [r9+1]; WaitType
0x140099d1d  mov     byte ptr [rsp+1B0h+Dpc], 0; WaitMode
0x140099d22  call    cs:__imp_KeWaitForMultipleObjects
0x140099d29  nop     dword ptr [rax+rax+00h]
0x140099d2e  test    sil, sil
0x140099d31  jz      short loc_140099D42
0x140099d33  mov     rcx, rbx; PKTIMER
0x140099d36  call    cs:__imp_KeCancelTimer
0x140099d3d  nop     dword ptr [rax+rax+00h]
0x140099d42  lea     rdx, [rsp+1B0h+LockHandle]; LockHandle
0x140099d47  lea     rcx, UlScavengerListLock; SpinLock
0x140099d4e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140099d55  nop     dword ptr [rax+rax+00h]
0x140099d5a  mov     rax, 0FFFFF78000000008h
0x140099d64  lea     rdx, [rsp+1B0h+var_170]
0x140099d69  mov     r14, [rax]
0x140099d6c  mov     rcx, r14
0x140099d6f  call    UlpProcessExpiredScavengers
0x140099d74  lea     rcx, [rsp+1B0h+LockHandle]; LockHandle
0x140099d79  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140099d80  nop     dword ptr [rax+rax+00h]
0x140099d85  mov     rax, qword ptr [rsp+1B0h+var_170]
0x140099d8a  lea     rcx, [rsp+1B0h+var_170]
0x140099d8f  cmp     rax, rcx
0x140099d92  jz      loc_140099B66
0x140099d98  lea     rcx, [rsp+1B0h+var_170]
0x140099d9d  cmp     [rax+8], rcx
0x140099da1  jnz     loc_140099E76
0x140099da7  mov     rcx, [rax]
0x140099daa  cmp     [rcx+8], rax
0x140099dae  jnz     loc_140099E76
0x140099db4  mov     qword ptr [rsp+1B0h+var_170], rcx
0x140099db9  lea     rdx, [rsp+1B0h+var_170]
0x140099dbe  mov     [rcx+8], rdx
0x140099dc2  lea     rbx, [rax-50h]
0x140099dc6  mov     qword ptr [rax], 0
0x140099dcd  mov     qword ptr [rax+8], 0
0x140099dd5  test    byte ptr cs:xmmword_1401A2CA0+0Ah, 8
0x140099ddc  jnz     loc_140099ECD
0x140099de2  mov     rax, [rbx+28h]
0x140099de6  mov     rcx, rbx
0x140099de9  call    _guard_dispatch_icall
0x140099dee  lea     rcx, [rbx+68h]; RunRef
0x140099df2  call    cs:__imp_ExReleaseRundownProtection
0x140099df9  nop     dword ptr [rax+rax+00h]
0x140099dfe  jmp     short loc_140099D85
0x140099e00  mov     rax, [r8-30h]
0x140099e04  cmp     rax, r9
0x140099e07  jnb     loc_140099C04
0x140099e0d  cmp     byte ptr [r8-28h], 0
0x140099e12  jnz     short loc_140099E49
0x140099e14  xor     edx, edx
0x140099e16  lea     rcx, [r10-1]
0x140099e1a  add     rcx, rax
0x140099e1d  mov     rax, rcx
0x140099e20  div     r10
0x140099e23  sub     rcx, rdx
0x140099e26  cmp     rcx, r9
0x140099e29  jnb     loc_140099C04
0x140099e2f  mov     r9, rcx
0x140099e32  mov     r11d, [r8-40h]
0x140099e36  jmp     loc_140099C04
0x140099e3b  cmp     rax, r9
0x140099e3e  jnb     loc_140099C04
0x140099e44  mov     r9, rax
0x140099e47  jmp     short loc_140099E32
0x140099e49  lea     rcx, [rax+2FAF07Fh]
0x140099e50  mov     rax, 0ABCC77118461CEFDh
0x140099e5a  mul     rcx
0x140099e5d  shr     rdx, 19h
0x140099e61  imul    rcx, rdx, 2FAF080h
0x140099e68  jmp     short loc_140099E26
0x140099e6a  lea     rbx, UlScavengerWaitTimer
0x140099e71  jmp     loc_140099CF8
0x140099e76  mov     ecx, 3
0x140099e7b  int     29h; Win8: RtlFailFast(ecx)
0x140099e7d  test    byte ptr cs:xmmword_1401A2CA0+2, 8
0x140099e84  jnz     short loc_140099EEB
0x140099e86  xor     ecx, ecx; ExitStatus
0x140099e88  call    cs:__imp_PsTerminateSystemThread
0x140099e8f  nop     dword ptr [rax+rax+00h]
0x140099e94  mov     rcx, [rbp+0B0h+var_30]
0x140099e9b  xor     rcx, rsp; StackCookie
0x140099e9e  call    __security_check_cookie
0x140099ea3  add     rsp, 190h
0x140099eaa  pop     r14
0x140099eac  pop     rdi
0x140099ead  pop     rsi
0x140099eae  pop     rbx
0x140099eaf  pop     rbp
0x140099eb0  retn
0x140099eb2  mov     edx, 0Fh
0x140099eb7  lea     r8, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids
0x140099ebe  mov     ecx, 513h
0x140099ec3  call    WPP_SF_
0x140099ec8  jmp     loc_140099C8D
0x140099ecd  mov     r9d, [rbx]
0x140099ed0  lea     r8, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids
0x140099ed7  mov     edx, 10h
0x140099edc  mov     ecx, 513h
0x140099ee1  call    WPP_SF_d
0x140099ee6  jmp     loc_140099DE2
0x140099eeb  mov     edx, 11h
0x140099ef0  lea     r8, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids
0x140099ef7  mov     ecx, 413h
0x140099efc  call    WPP_SF_
0x140099f01  jmp     short loc_140099E86
```
