# ScheduleRequestAfterSoftwarePiece

- ea: `0x140003268`
- end: `0x14000351a`
- name: `ScheduleRequestAfterSoftwarePiece`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140001430`

## callees

- `0x14000292c`
- `0x14000305c`
- `0x14000322c`
- `0x140003268`
- `0x1400039d4`
- `0x140003aa8`
- `0x140003b38`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000343c`
- `ntoskrnl!KeSetEvent` at `0x14000343c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003294`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003294`
- `ntoskrnl!KeQueryPriorityThread` at `0x14000327f`
- `ntoskrnl!KeQueryPriorityThread` at `0x14000327f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400034fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400034fd`

## pseudocode

```c
char __fastcall ScheduleRequestAfterSoftwarePiece(__int64 a1)
{
  __int64 v1; // rsi
  KPRIORITY PriorityThread; // edi
  KIRQL v4; // al
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // r8d
  KIRQL v8; // bp
  char v9; // di
  __int64 v10; // rdx
  __int64 v11; // r8
  char *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax

  v1 = *(_QWORD *)a1;
  PriorityThread = KeQueryPriorityThread(*(PKTHREAD *)(a1 + 96));
  v4 = KeAcquireSpinLockRaiseToDpc(&g_spinlock);
  v5 = *(unsigned int *)(a1 + 128);
  v6 = (unsigned int)g_maxPrioritySoftware;
  v7 = g_nSwThreadsRunning - 1;
  v8 = v4;
  --g_nSwThreadsRunning;
  --g_SwThreadsRunning[v5];
  if ( (_DWORD)v5 == (_DWORD)v6 )
  {
    if ( v7 )
    {
      if ( !g_SwThreadsRunning[v6] )
      {
        do
          v6 = (unsigned int)(v6 - 1);
        while ( !g_SwThreadsRunning[v6] );
        g_maxPrioritySoftware = v6;
      }
    }
    else
    {
      g_maxPrioritySoftware = 0;
    }
  }
  *(_DWORD *)(a1 + 128) = PriorityThread;
  if ( *(_DWORD *)(a1 + 32) < *(_DWORD *)(v1 + 8) )
    *(_DWORD *)(a1 + 92) |= 1u;
  if ( *(_DWORD *)(a1 + 152) == 3 )
  {
    v9 = 0;
    goto LABEL_14;
  }
  if ( (unsigned __int8)IsAllowedOnHardware(a1) && TryRequestInHardware(a1, v10, v11) )
  {
    v9 = 1;
LABEL_14:
    if ( !dword_140007444 || (v12 = g_priorityQueueSw, dword_140007224 > (unsigned int)dword_140007444) )
      v12 = g_priorityQueueHw;
    v13 = *((unsigned int *)v12 + 1);
    if ( (_DWORD)v13 )
    {
      v14 = *(_QWORD *)&v12[16 * v13 + 8] - 136LL;
      if ( *(_QWORD *)&v12[16 * v13 + 8] != 136 )
      {
        if ( (unsigned __int8)shouldRunInSoftware(v14)
          || !*(_DWORD *)(v1 + 28)
          && dword_140007444
          && dword_140007444 < (unsigned int)dword_140007224
          && (v14 = *(_QWORD *)&g_priorityQueueSw[16 * dword_140007444 + 8] - 136LL,
              (unsigned __int8)shouldRunInSoftware(v14)) )
        {
          removeRequestFromPriorityQueue(v14);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              17,
              WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids,
              *(unsigned int *)(v14 + 156));
          }
          v15 = *(unsigned int *)(v14 + 128);
          *(_DWORD *)(v14 + 152) = 1;
          ++g_SwThreadsRunning[v15];
          if ( g_maxPrioritySoftware <= (unsigned int)v15 )
            g_maxPrioritySoftware = v15;
          ++g_nSwThreadsRunning;
          KeSetEvent((PRKEVENT)(v14 + 104), 0, 0);
        }
      }
    }
    goto LABEL_41;
  }
  if ( (unsigned __int8)shouldRunInSoftware(a1) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids,
        *(unsigned int *)(a1 + 156));
    v16 = *(unsigned int *)(a1 + 128);
    ++g_SwThreadsRunning[v16];
    if ( g_maxPrioritySoftware <= (unsigned int)v16 )
      g_maxPrioritySoftware = v16;
    ++g_nSwThreadsRunning;
    v9 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids,
        *(unsigned int *)(a1 + 156));
    addRequestToPriorityQueue(a1);
    v9 = 1;
  }
LABEL_41:
  KeReleaseSpinLock(&g_spinlock, v8);
  return v9;
}

```

## disassembly

```asm
0x140003268  push    rbx
0x14000326a  push    rbp
0x14000326b  push    rsi
0x14000326c  push    rdi
0x14000326d  push    r12
0x14000326f  push    r13
0x140003271  sub     rsp, 28h
0x140003275  mov     rsi, [rcx]
0x140003278  mov     rbx, rcx
0x14000327b  mov     rcx, [rcx+60h]; Thread
0x14000327f  call    cs:__imp_KeQueryPriorityThread
0x140003286  nop     dword ptr [rax+rax+00h]
0x14000328b  lea     rcx, g_spinlock; SpinLock
0x140003292  mov     edi, eax
0x140003294  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000329b  nop     dword ptr [rax+rax+00h]
0x1400032a0  mov     edx, [rbx+80h]
0x1400032a6  lea     r12, g_SwThreadsRunning
0x1400032ad  mov     r8d, cs:g_nSwThreadsRunning
0x1400032b4  or      r9d, 0FFFFFFFFh
0x1400032b8  mov     ecx, cs:g_maxPrioritySoftware
0x1400032be  add     r8d, r9d
0x1400032c1  mov     bpl, al
0x1400032c4  mov     cs:g_nSwThreadsRunning, r8d
0x1400032cb  add     [r12+rdx*4], r9d
0x1400032cf  cmp     edx, ecx
0x1400032d1  jnz     short loc_1400032F8
0x1400032d3  test    r8d, r8d
0x1400032d6  jnz     short loc_1400032E1
0x1400032d8  mov     cs:g_maxPrioritySoftware, r8d
0x1400032df  jmp     short loc_1400032F8
0x1400032e1  cmp     dword ptr [r12+rcx*4], 0
0x1400032e6  jnz     short loc_1400032F8
0x1400032e8  add     ecx, r9d
0x1400032eb  cmp     dword ptr [r12+rcx*4], 0
0x1400032f0  jz      short loc_1400032E8
0x1400032f2  mov     cs:g_maxPrioritySoftware, ecx
0x1400032f8  mov     [rbx+80h], edi
0x1400032fe  mov     eax, [rsi+8]
0x140003301  cmp     [rbx+20h], eax
0x140003304  jnb     short loc_14000330A
0x140003306  or      dword ptr [rbx+5Ch], 1
0x14000330a  cmp     dword ptr [rbx+98h], 3
0x140003311  jnz     short loc_140003318
0x140003313  xor     dil, dil
0x140003316  jmp     short loc_14000333B
0x140003318  mov     rcx, rbx
0x14000331b  call    IsAllowedOnHardware
0x140003320  test    al, al
0x140003322  jz      loc_14000344D
0x140003328  mov     rcx, rbx
0x14000332b  call    TryRequestInHardware
0x140003330  test    al, al
0x140003332  jz      loc_14000344D
0x140003338  mov     dil, 1
0x14000333b  mov     eax, cs:dword_140007444
0x140003341  lea     r13, g_priorityQueueSw
0x140003348  test    eax, eax
0x14000334a  jz      short loc_140003357
0x14000334c  cmp     cs:dword_140007224, eax
0x140003352  mov     rcx, r13
0x140003355  jbe     short loc_14000335E
0x140003357  lea     rcx, g_priorityQueueHw
0x14000335e  mov     eax, [rcx+4]
0x140003361  test    eax, eax
0x140003363  jz      loc_1400034F3
0x140003369  add     rax, rax
0x14000336c  mov     rbx, [rcx+rax*8+8]
0x140003371  add     rbx, 0FFFFFFFFFFFFFF78h
0x140003378  jz      loc_1400034F3
0x14000337e  mov     rcx, rbx
0x140003381  call    shouldRunInSoftware
0x140003386  test    al, al
0x140003388  jnz     short loc_1400033CD
0x14000338a  cmp     dword ptr [rsi+1Ch], 0
0x14000338e  jnz     loc_1400034F3
0x140003394  mov     eax, cs:dword_140007444
0x14000339a  test    eax, eax
0x14000339c  jz      loc_1400034F3
0x1400033a2  cmp     eax, cs:dword_140007224
0x1400033a8  jnb     loc_1400034F3
0x1400033ae  add     rax, rax
0x1400033b1  mov     rbx, [r13+rax*8+8]
0x1400033b6  add     rbx, 0FFFFFFFFFFFFFF78h
0x1400033bd  mov     rcx, rbx
0x1400033c0  call    shouldRunInSoftware
0x1400033c5  test    al, al
0x1400033c7  jz      loc_1400034F3
0x1400033cd  mov     rcx, rbx
0x1400033d0  call    removeRequestFromPriorityQueue
0x1400033d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400033dc  lea     rax, WPP_GLOBAL_Control
0x1400033e3  cmp     rcx, rax
0x1400033e6  jz      short loc_14000340B
0x1400033e8  mov     eax, [rcx+2Ch]
0x1400033eb  test    al, 4
0x1400033ed  jz      short loc_14000340B
0x1400033ef  mov     r9d, [rbx+9Ch]
0x1400033f6  lea     r8, WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids
0x1400033fd  mov     rcx, [rcx+18h]
0x140003401  mov     edx, 11h
0x140003406  call    WPP_SF_D
0x14000340b  mov     eax, [rbx+80h]
0x140003411  mov     dword ptr [rbx+98h], 1
0x14000341b  inc     dword ptr [r12+rax*4]
0x14000341f  cmp     cs:g_maxPrioritySoftware, eax
0x140003425  ja      short loc_14000342D
0x140003427  mov     cs:g_maxPrioritySoftware, eax
0x14000342d  inc     cs:g_nSwThreadsRunning
0x140003433  lea     rcx, [rbx+68h]; Event
0x140003437  xor     r8d, r8d; Wait
0x14000343a  xor     edx, edx; Increment
0x14000343c  call    cs:__imp_KeSetEvent
0x140003443  nop     dword ptr [rax+rax+00h]
0x140003448  jmp     loc_1400034F3
0x14000344d  mov     rcx, rbx
0x140003450  call    shouldRunInSoftware
0x140003455  test    al, al
0x140003457  jz      short loc_1400034B2
0x140003459  mov     rcx, cs:WPP_GLOBAL_Control
0x140003460  lea     rax, WPP_GLOBAL_Control
0x140003467  cmp     rcx, rax
0x14000346a  jz      short loc_14000348F
0x14000346c  mov     eax, [rcx+2Ch]
0x14000346f  test    al, 4
0x140003471  jz      short loc_14000348F
0x140003473  mov     r9d, [rbx+9Ch]
0x14000347a  lea     r8, WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids
0x140003481  mov     rcx, [rcx+18h]
0x140003485  mov     edx, 0Fh
0x14000348a  call    WPP_SF_D
0x14000348f  mov     eax, [rbx+80h]
0x140003495  inc     dword ptr [r12+rax*4]
0x140003499  cmp     cs:g_maxPrioritySoftware, eax
0x14000349f  ja      short loc_1400034A7
0x1400034a1  mov     cs:g_maxPrioritySoftware, eax
0x1400034a7  inc     cs:g_nSwThreadsRunning
0x1400034ad  xor     dil, dil
0x1400034b0  jmp     short loc_1400034F3
0x1400034b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400034b9  lea     rax, WPP_GLOBAL_Control
0x1400034c0  cmp     rcx, rax
0x1400034c3  jz      short loc_1400034E8
0x1400034c5  mov     eax, [rcx+2Ch]
0x1400034c8  test    al, 4
0x1400034ca  jz      short loc_1400034E8
0x1400034cc  mov     r9d, [rbx+9Ch]
0x1400034d3  lea     r8, WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids
0x1400034da  mov     rcx, [rcx+18h]
0x1400034de  mov     edx, 10h
0x1400034e3  call    WPP_SF_D
0x1400034e8  mov     rcx, rbx
0x1400034eb  call    addRequestToPriorityQueue
0x1400034f0  mov     dil, 1
0x1400034f3  mov     dl, bpl; NewIrql
0x1400034f6  lea     rcx, g_spinlock; SpinLock
0x1400034fd  call    cs:__imp_KeReleaseSpinLock
0x140003504  nop     dword ptr [rax+rax+00h]
0x140003509  mov     al, dil
0x14000350c  add     rsp, 28h
0x140003510  pop     r13
0x140003512  pop     r12
0x140003514  pop     rdi
0x140003515  pop     rsi
0x140003516  pop     rbp
0x140003517  pop     rbx
0x140003518  retn
```
