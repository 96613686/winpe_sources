# UMRxPrepareWorkerQueue

- ea: `0x1400062b0`
- end: `0x140006458`
- name: `UMRxPrepareWorkerQueue`
- size: `424`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f120`
- `0x14000f780`

## callees

- `0x14000163c`
- `0x1400017e4`
- `0x1400062b0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400062e2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000631e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000639c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140006424`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400062e2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000631e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000639c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140006424`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000635e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000635e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006377`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400063f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006377`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400063f3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006346`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006346`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400063bf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400063ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400063bf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400063ff`
- `ntoskrnl!KeInitializeQueue` at `0x1400063e4`
- `ntoskrnl!KeInitializeQueue` at `0x1400063e4`

## pseudocode

```c
void __fastcall UMRxPrepareWorkerQueue(__int64 a1)
{
  __int64 v2; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v4; // rbx
  HANDLE v5; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  __int64 v8; // rbx
  HANDLE v9; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v2 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v2, 99, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v5 = PsGetCurrentThreadId();
      WPP_SF_qq(v4, 100, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v5, a1);
    }
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 1456), 1u);
  if ( *(_BYTE *)(a1 + 1616) )
  {
    ExReleaseResourceLite((PERESOURCE)(a1 + 1456));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_q(v6, 101, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v7);
    }
    KeLeaveCriticalRegion();
  }
  else
  {
    *(_BYTE *)(a1 + 1616) = 1;
    *(_QWORD *)(a1 + 1608) = 0;
    KeInitializeQueue((PRKQUEUE)(a1 + 1392), 0);
    ExReleaseResourceLite((PERESOURCE)(a1 + 1456));
    KeLeaveCriticalRegion();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v9 = PsGetCurrentThreadId();
      WPP_SF_q(v8, 102, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v9);
    }
  }
}

```

## disassembly

```asm
0x1400062b0  mov     [rsp+arg_0], rbx
0x1400062b5  mov     [rsp+arg_8], rsi
0x1400062ba  push    rdi
0x1400062bb  sub     rsp, 30h
0x1400062bf  mov     rdi, rcx
0x1400062c2  mov     rbx, cs:WPP_GLOBAL_Control
0x1400062c9  lea     rsi, WPP_GLOBAL_Control
0x1400062d0  cmp     rbx, rsi
0x1400062d3  jz      short loc_140006346
0x1400062d5  test    dword ptr [rbx+2Ch], 800h
0x1400062dc  jz      short loc_140006305
0x1400062de  mov     rbx, [rbx+18h]
0x1400062e2  call    cs:__imp_PsGetCurrentThreadId
0x1400062e9  nop     dword ptr [rax+rax+00h]
0x1400062ee  mov     edx, 63h ; 'c'
0x1400062f3  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400062fa  mov     r9, rax
0x1400062fd  mov     rcx, rbx
0x140006300  call    WPP_SF_q
0x140006305  mov     rbx, cs:WPP_GLOBAL_Control
0x14000630c  cmp     rbx, rsi
0x14000630f  jz      short loc_140006346
0x140006311  test    dword ptr [rbx+2Ch], 200h
0x140006318  jz      short loc_140006346
0x14000631a  mov     rbx, [rbx+18h]
0x14000631e  call    cs:__imp_PsGetCurrentThreadId
0x140006325  nop     dword ptr [rax+rax+00h]
0x14000632a  mov     edx, 64h ; 'd'
0x14000632f  mov     [rsp+38h+var_18], rdi
0x140006334  mov     r9, rax
0x140006337  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x14000633e  mov     rcx, rbx
0x140006341  call    WPP_SF_qq
0x140006346  call    cs:__imp_KeEnterCriticalRegion
0x14000634d  nop     dword ptr [rax+rax+00h]
0x140006352  lea     rbx, [rdi+5B0h]
0x140006359  mov     dl, 1; Wait
0x14000635b  mov     rcx, rbx; Resource
0x14000635e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140006365  nop     dword ptr [rax+rax+00h]
0x14000636a  xor     eax, eax
0x14000636c  cmp     [rdi+650h], al
0x140006372  jz      short loc_1400063CD
0x140006374  mov     rcx, rbx; Resource
0x140006377  call    cs:__imp_ExReleaseResourceLite
0x14000637e  nop     dword ptr [rax+rax+00h]
0x140006383  mov     rbx, cs:WPP_GLOBAL_Control
0x14000638a  cmp     rbx, rsi
0x14000638d  jz      short loc_1400063BF
0x14000638f  test    dword ptr [rbx+2Ch], 400h
0x140006396  jz      short loc_1400063BF
0x140006398  mov     rbx, [rbx+18h]
0x14000639c  call    cs:__imp_PsGetCurrentThreadId
0x1400063a3  nop     dword ptr [rax+rax+00h]
0x1400063a8  mov     edx, 65h ; 'e'
0x1400063ad  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400063b4  mov     r9, rax
0x1400063b7  mov     rcx, rbx
0x1400063ba  call    WPP_SF_q
0x1400063bf  call    cs:__imp_KeLeaveCriticalRegion
0x1400063c6  nop     dword ptr [rax+rax+00h]
0x1400063cb  jmp     short loc_140006447
0x1400063cd  lea     rcx, [rdi+570h]; Queue
0x1400063d4  mov     byte ptr [rdi+650h], 1
0x1400063db  xor     edx, edx; Count
0x1400063dd  mov     [rdi+648h], rax
0x1400063e4  call    cs:__imp_KeInitializeQueue
0x1400063eb  nop     dword ptr [rax+rax+00h]
0x1400063f0  mov     rcx, rbx; Resource
0x1400063f3  call    cs:__imp_ExReleaseResourceLite
0x1400063fa  nop     dword ptr [rax+rax+00h]
0x1400063ff  call    cs:__imp_KeLeaveCriticalRegion
0x140006406  nop     dword ptr [rax+rax+00h]
0x14000640b  mov     rbx, cs:WPP_GLOBAL_Control
0x140006412  cmp     rbx, rsi
0x140006415  jz      short loc_140006447
0x140006417  test    dword ptr [rbx+2Ch], 800h
0x14000641e  jz      short loc_140006447
0x140006420  mov     rbx, [rbx+18h]
0x140006424  call    cs:__imp_PsGetCurrentThreadId
0x14000642b  nop     dword ptr [rax+rax+00h]
0x140006430  mov     edx, 66h ; 'f'
0x140006435  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x14000643c  mov     r9, rax
0x14000643f  mov     rcx, rbx
0x140006442  call    WPP_SF_q
0x140006447  mov     rbx, [rsp+38h+arg_0]
0x14000644c  mov     rsi, [rsp+38h+arg_8]
0x140006451  add     rsp, 30h
0x140006455  pop     rdi
0x140006456  retn
```
