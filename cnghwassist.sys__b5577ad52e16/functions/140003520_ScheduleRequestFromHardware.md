# ScheduleRequestFromHardware

- ea: `0x140003520`
- end: `0x1400037e6`
- name: `ScheduleRequestFromHardware`
- size: `710`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140002ea0`

## callees

- `0x14000292c`
- `0x14000322c`
- `0x140003520`
- `0x1400039d4`
- `0x140003aa8`
- `0x140003b38`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400035bc`
- `ntoskrnl!KeSetEvent` at `0x140003682`
- `ntoskrnl!KeSetEvent` at `0x140003787`
- `ntoskrnl!KeSetEvent` at `0x1400035bc`
- `ntoskrnl!KeSetEvent` at `0x140003682`
- `ntoskrnl!KeSetEvent` at `0x140003787`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140003605`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140003772`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140003605`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140003772`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000354f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000354f`
- `ntoskrnl!KeQueryPriorityThread` at `0x14000353a`
- `ntoskrnl!KeQueryPriorityThread` at `0x14000353a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400037cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400037cc`
- `ntoskrnl!KeClearEvent` at `0x140003596`
- `ntoskrnl!KeClearEvent` at `0x140003596`

## pseudocode

```c
void __fastcall ScheduleRequestFromHardware(__int64 **a1)
{
  __int64 *v1; // rbx
  __int64 v3; // rbp
  unsigned int PriorityThread; // edi
  KIRQL v5; // al
  unsigned int v6; // ecx
  _DWORD *v7; // r14
  KIRQL v8; // r15
  __int64 *v9; // rcx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // r8d
  __int64 v15; // rdx
  __int64 *v16; // rcx

  v1 = *a1;
  v3 = **a1;
  PriorityThread = KeQueryPriorityThread((PKTHREAD)(*a1)[12]);
  v5 = KeAcquireSpinLockRaiseToDpc(&g_spinlock);
  v6 = *((_DWORD *)v1 + 8);
  v7 = v1 + 19;
  *((_DWORD *)v1 + 32) = PriorityThread;
  v8 = v5;
  if ( !v6 )
    *v7 = 3;
  if ( v6 < *(_DWORD *)(v3 + 8) )
  {
    *((_DWORD *)v1 + 23) |= 1u;
    goto LABEL_5;
  }
  if ( *v7 == 3 || !(unsigned __int8)IsAllowedOnHardware(v1) || PriorityThread < dword_140007224 )
  {
LABEL_5:
    g_mHwThreadsIdle |= *((_DWORD *)a1 + 2);
    *a1 = 0;
    KeClearEvent((PRKEVENT)(a1 + 4));
    if ( *v7 == 3 )
    {
      KeSetEvent((PRKEVENT)(v1 + 13), 0, 0);
    }
    else if ( (unsigned __int8)shouldRunInSoftware(v1) )
    {
      v12 = *((unsigned int *)v1 + 32);
      *v7 = 1;
      ++g_SwThreadsRunning[v12];
      if ( g_maxPrioritySoftware <= (unsigned int)v12 )
        g_maxPrioritySoftware = v12;
      ++g_nSwThreadsRunning;
      KeSetEvent((PRKEVENT)(v1 + 13), 0, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids,
          *((unsigned int *)v1 + 39));
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids,
          *((unsigned int *)v1 + 39));
      addRequestToPriorityQueue(v1);
    }
    if ( dword_140007224 )
    {
      v1 = (__int64 *)(qword_140007228[2 * (unsigned int)dword_140007224] - 136);
      removeRequestFromPriorityQueue(v1);
      *((_DWORD *)v1 + 38) = 5;
      v13 = ~*((_DWORD *)a1 + 2);
      *a1 = v1;
      g_mHwThreadsIdle &= v13;
      if ( dword_1400077F4[0] )
      {
        v14 = g_maxPrioritySoftware;
        if ( *((_DWORD *)v1 + 32) > (unsigned int)g_maxPrioritySoftware )
          v14 = *((_DWORD *)v1 + 32);
        v15 = v14 + 1;
        if ( v14 >= 0xE )
          v15 = v14;
        if ( *((_DWORD *)a1 + 6) != (_DWORD)v15 )
        {
          v16 = a1[2];
          *((_DWORD *)a1 + 6) = v15;
          KeSetActualBasePriorityThread(v16, v15);
        }
      }
      KeSetEvent((PRKEVENT)(a1 + 4), 0, 0);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        v11 = 21;
        goto LABEL_39;
      }
    }
    goto LABEL_40;
  }
  if ( dword_1400077F4[0] )
  {
    if ( PriorityThread < 0xE )
      ++PriorityThread;
    if ( *((_DWORD *)a1 + 6) < PriorityThread )
    {
      v9 = a1[2];
      *((_DWORD *)a1 + 6) = PriorityThread;
      KeSetActualBasePriorityThread(v9, PriorityThread);
    }
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    v11 = 18;
LABEL_39:
    WPP_SF_D(v10->AttachedDevice, v11, WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids, *((unsigned int *)v1 + 39));
  }
LABEL_40:
  KeReleaseSpinLock(&g_spinlock, v8);
}

```

## disassembly

```asm
0x140003520  push    rbx
0x140003522  push    rbp
0x140003523  push    rsi
0x140003524  push    rdi
0x140003525  push    r14
0x140003527  push    r15
0x140003529  sub     rsp, 28h
0x14000352d  mov     rbx, [rcx]
0x140003530  mov     rsi, rcx
0x140003533  mov     rcx, [rbx+60h]; Thread
0x140003537  mov     rbp, [rbx]
0x14000353a  call    cs:__imp_KeQueryPriorityThread
0x140003541  nop     dword ptr [rax+rax+00h]
0x140003546  lea     rcx, g_spinlock; SpinLock
0x14000354d  mov     edi, eax
0x14000354f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003556  nop     dword ptr [rax+rax+00h]
0x14000355b  mov     ecx, [rbx+20h]
0x14000355e  lea     r14, [rbx+98h]
0x140003565  mov     [rbx+80h], edi
0x14000356b  mov     r15b, al
0x14000356e  test    ecx, ecx
0x140003570  jnz     short loc_140003579
0x140003572  mov     dword ptr [r14], 3
0x140003579  cmp     ecx, [rbp+8]
0x14000357c  jnb     short loc_1400035CD
0x14000357e  or      dword ptr [rbx+5Ch], 1
0x140003582  mov     eax, [rsi+8]
0x140003585  lea     rcx, [rsi+20h]; Event
0x140003589  or      cs:g_mHwThreadsIdle, eax
0x14000358f  mov     qword ptr [rsi], 0
0x140003596  call    cs:__imp_KeClearEvent
0x14000359d  nop     dword ptr [rax+rax+00h]
0x1400035a2  cmp     dword ptr [r14], 3
0x1400035a6  lea     rdi, WPP_GLOBAL_Control
0x1400035ad  jnz     loc_14000363D
0x1400035b3  lea     rcx, [rbx+68h]; Event
0x1400035b7  xor     r8d, r8d; Wait
0x1400035ba  xor     edx, edx; Increment
0x1400035bc  call    cs:__imp_KeSetEvent
0x1400035c3  nop     dword ptr [rax+rax+00h]
0x1400035c8  jmp     loc_1400036F6
0x1400035cd  cmp     dword ptr [r14], 3
0x1400035d1  jz      short loc_140003582
0x1400035d3  mov     rcx, rbx
0x1400035d6  call    IsAllowedOnHardware
0x1400035db  test    al, al
0x1400035dd  jz      short loc_140003582
0x1400035df  cmp     edi, cs:dword_140007224
0x1400035e5  jb      short loc_140003582
0x1400035e7  cmp     cs:dword_1400077F4, 0
0x1400035ee  jz      short loc_140003611
0x1400035f0  cmp     edi, 0Eh
0x1400035f3  jnb     short loc_1400035F7
0x1400035f5  inc     edi
0x1400035f7  cmp     [rsi+18h], edi
0x1400035fa  jnb     short loc_140003611
0x1400035fc  mov     rcx, [rsi+10h]
0x140003600  mov     edx, edi
0x140003602  mov     [rsi+18h], edi
0x140003605  call    cs:__imp_KeSetActualBasePriorityThread
0x14000360c  nop     dword ptr [rax+rax+00h]
0x140003611  mov     rcx, cs:WPP_GLOBAL_Control
0x140003618  lea     rdi, WPP_GLOBAL_Control
0x14000361f  cmp     rcx, rdi
0x140003622  jz      loc_1400037C2
0x140003628  mov     eax, [rcx+2Ch]
0x14000362b  test    al, 4
0x14000362d  jz      loc_1400037C2
0x140003633  mov     edx, 12h
0x140003638  jmp     loc_1400037AB
0x14000363d  mov     rcx, rbx
0x140003640  call    shouldRunInSoftware
0x140003645  test    al, al
0x140003647  jz      short loc_1400036BF
0x140003649  mov     eax, [rbx+80h]
0x14000364f  mov     dword ptr [r14], 1
0x140003656  lea     r14, cs:140000000h
0x14000365d  inc     rva g_SwThreadsRunning[r14+rax*4]
0x140003665  cmp     cs:g_maxPrioritySoftware, eax
0x14000366b  ja      short loc_140003673
0x14000366d  mov     cs:g_maxPrioritySoftware, eax
0x140003673  inc     cs:g_nSwThreadsRunning
0x140003679  lea     rcx, [rbx+68h]; Event
0x14000367d  xor     r8d, r8d; Wait
0x140003680  xor     edx, edx; Increment
0x140003682  call    cs:__imp_KeSetEvent
0x140003689  nop     dword ptr [rax+rax+00h]
0x14000368e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003695  cmp     rcx, rdi
0x140003698  jz      short loc_1400036FD
0x14000369a  mov     eax, [rcx+2Ch]
0x14000369d  test    al, 4
0x14000369f  jz      short loc_1400036FD
0x1400036a1  mov     r9d, [rbx+9Ch]
0x1400036a8  lea     r8, WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids
0x1400036af  mov     rcx, [rcx+18h]
0x1400036b3  mov     edx, 13h
0x1400036b8  call    WPP_SF_D
0x1400036bd  jmp     short loc_1400036FD
0x1400036bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400036c6  cmp     rcx, rdi
0x1400036c9  jz      short loc_1400036EE
0x1400036cb  mov     eax, [rcx+2Ch]
0x1400036ce  test    al, 4
0x1400036d0  jz      short loc_1400036EE
0x1400036d2  mov     r9d, [rbx+9Ch]
0x1400036d9  lea     r8, WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids
0x1400036e0  mov     rcx, [rcx+18h]
0x1400036e4  mov     edx, 14h
0x1400036e9  call    WPP_SF_D
0x1400036ee  mov     rcx, rbx
0x1400036f1  call    addRequestToPriorityQueue
0x1400036f6  lea     r14, cs:140000000h
0x1400036fd  mov     eax, cs:dword_140007224
0x140003703  test    eax, eax
0x140003705  jz      loc_1400037C2
0x14000370b  add     rax, rax
0x14000370e  mov     rbx, rva qword_140007228[r14+rax*8]
0x140003716  sub     rbx, 88h
0x14000371d  mov     rcx, rbx
0x140003720  call    removeRequestFromPriorityQueue
0x140003725  mov     dword ptr [rbx+98h], 5
0x14000372f  mov     eax, [rsi+8]
0x140003732  not     eax
0x140003734  mov     [rsi], rbx
0x140003737  and     cs:g_mHwThreadsIdle, eax
0x14000373d  cmp     cs:dword_1400077F4, 0
0x140003744  jz      short loc_14000377E
0x140003746  mov     eax, [rbx+80h]
0x14000374c  mov     r8d, cs:g_maxPrioritySoftware
0x140003753  cmp     eax, r8d
0x140003756  cmova   r8d, eax
0x14000375a  cmp     r8d, 0Eh
0x14000375e  lea     edx, [r8+1]
0x140003762  cmovnb  edx, r8d
0x140003766  cmp     [rsi+18h], edx
0x140003769  jz      short loc_14000377E
0x14000376b  mov     rcx, [rsi+10h]
0x14000376f  mov     [rsi+18h], edx
0x140003772  call    cs:__imp_KeSetActualBasePriorityThread
0x140003779  nop     dword ptr [rax+rax+00h]
0x14000377e  xor     r8d, r8d; Wait
0x140003781  lea     rcx, [rsi+20h]; Event
0x140003785  xor     edx, edx; Increment
0x140003787  call    cs:__imp_KeSetEvent
0x14000378e  nop     dword ptr [rax+rax+00h]
0x140003793  mov     rcx, cs:WPP_GLOBAL_Control
0x14000379a  cmp     rcx, rdi
0x14000379d  jz      short loc_1400037C2
0x14000379f  mov     eax, [rcx+2Ch]
0x1400037a2  test    al, 4
0x1400037a4  jz      short loc_1400037C2
0x1400037a6  mov     edx, 15h
0x1400037ab  mov     r9d, [rbx+9Ch]
0x1400037b2  lea     r8, WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids
0x1400037b9  mov     rcx, [rcx+18h]
0x1400037bd  call    WPP_SF_D
0x1400037c2  mov     dl, r15b; NewIrql
0x1400037c5  lea     rcx, g_spinlock; SpinLock
0x1400037cc  call    cs:__imp_KeReleaseSpinLock
0x1400037d3  nop     dword ptr [rax+rax+00h]
0x1400037d8  add     rsp, 28h
0x1400037dc  pop     r15
0x1400037de  pop     r14
0x1400037e0  pop     rdi
0x1400037e1  pop     rsi
0x1400037e2  pop     rbp
0x1400037e3  pop     rbx
0x1400037e4  retn
```
