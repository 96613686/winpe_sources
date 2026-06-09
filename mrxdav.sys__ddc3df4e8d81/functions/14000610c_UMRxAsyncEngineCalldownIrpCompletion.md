# UMRxAsyncEngineCalldownIrpCompletion

- ea: `0x14000610c`
- end: `0x1400062a8`
- name: `UMRxAsyncEngineCalldownIrpCompletion`
- size: `412`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140026dfc`
- `0x140026f54`

## callees

- `0x14000163c`
- `0x140001b64`
- `0x14000610c`
- `0x140006574`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14000614c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140006188`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400061e0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140006254`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000614c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140006188`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400061e0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140006254`
- `ntoskrnl!KeSetEvent` at `0x14000628b`
- `ntoskrnl!KeSetEvent` at `0x14000628b`
- `rdbss!RxPostToWorkerThread` at `0x140006224`
- `rdbss!RxPostToWorkerThread` at `0x140006224`

## pseudocode

```c
__int64 __fastcall UMRxAsyncEngineCalldownIrpCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbp
  char v5; // di
  __int64 v6; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v8; // rbx
  HANDLE v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rdi
  unsigned int v13; // eax
  int v14; // r8d
  __int64 v15; // rbx
  __int64 v16; // rdi
  unsigned int v17; // eax
  int v18; // r8d

  v3 = *(_QWORD *)(a3 + 208);
  v5 = *(_BYTE *)(v3 + 208) & 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v6, 42, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v9 = PsGetCurrentThreadId();
      WPP_SF_qqq(v8, 43, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v9, v3, a3);
    }
  }
  v10 = *(_QWORD *)(a3 + 72);
  if ( v5 )
  {
    if ( v10
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
    {
      v11 = *(_QWORD *)(v10 + 80);
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qqqZ(v12, 45, v14, v13, v3, a3, v11);
    }
    RxPostToWorkerThread(
      *(PRDBSS_DEVICE_OBJECT *)(a3 + 80),
      CriticalWorkQueue,
      (PRX_WORK_QUEUE_ITEM)(v3 + 144),
      (PRX_WORKERTHREAD_ROUTINE)UMRxResumeAsyncEngineContext,
      (PVOID)a3);
  }
  else
  {
    if ( v10
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
    {
      v15 = *(_QWORD *)(v10 + 80);
      v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v17 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qqqZ(v16, 46, v18, v17, v3, a3, v15);
    }
    KeSetEvent((PRKEVENT)(v3 + 448), 0, 0);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000610c  push    rbx
0x14000610e  push    rbp
0x14000610f  push    rsi
0x140006110  push    rdi
0x140006111  push    r14
0x140006113  sub     rsp, 40h
0x140006117  mov     rbp, [r8+0D0h]
0x14000611e  mov     rsi, r8
0x140006121  mov     dil, [rbp+0D0h]
0x140006128  and     dil, 1
0x14000612c  mov     rbx, cs:WPP_GLOBAL_Control
0x140006133  lea     r14, WPP_GLOBAL_Control
0x14000613a  cmp     rbx, r14
0x14000613d  jz      short loc_1400061B5
0x14000613f  test    dword ptr [rbx+2Ch], 800h
0x140006146  jz      short loc_14000616F
0x140006148  mov     rbx, [rbx+18h]
0x14000614c  call    cs:__imp_PsGetCurrentThreadId
0x140006153  nop     dword ptr [rax+rax+00h]
0x140006158  mov     edx, 2Ah ; '*'
0x14000615d  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140006164  mov     r9, rax
0x140006167  mov     rcx, rbx
0x14000616a  call    WPP_SF_q
0x14000616f  mov     rbx, cs:WPP_GLOBAL_Control
0x140006176  cmp     rbx, r14
0x140006179  jz      short loc_1400061B5
0x14000617b  test    dword ptr [rbx+2Ch], 200h
0x140006182  jz      short loc_1400061B5
0x140006184  mov     rbx, [rbx+18h]
0x140006188  call    cs:__imp_PsGetCurrentThreadId
0x14000618f  nop     dword ptr [rax+rax+00h]
0x140006194  mov     edx, 2Bh ; '+'
0x140006199  mov     [rsp+68h+var_40], rsi
0x14000619e  mov     r9, rax
0x1400061a1  mov     [rsp+68h+pContext], rbp
0x1400061a6  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400061ad  mov     rcx, rbx
0x1400061b0  call    WPP_SF_qqq
0x1400061b5  mov     rbx, [rsi+48h]
0x1400061b9  test    dil, dil
0x1400061bc  jz      short loc_140006232
0x1400061be  test    rbx, rbx
0x1400061c1  jz      short loc_14000620B
0x1400061c3  mov     rdi, cs:WPP_GLOBAL_Control
0x1400061ca  cmp     rdi, r14
0x1400061cd  jz      short loc_14000620B
0x1400061cf  test    dword ptr [rdi+2Ch], 400h
0x1400061d6  jz      short loc_14000620B
0x1400061d8  mov     rbx, [rbx+50h]
0x1400061dc  mov     rdi, [rdi+18h]
0x1400061e0  call    cs:__imp_PsGetCurrentThreadId
0x1400061e7  nop     dword ptr [rax+rax+00h]
0x1400061ec  mov     [rsp+68h+var_38], rbx
0x1400061f1  mov     edx, 2Dh ; '-'
0x1400061f6  mov     r9, rax
0x1400061f9  mov     [rsp+68h+var_40], rsi
0x1400061fe  mov     rcx, rdi
0x140006201  mov     [rsp+68h+pContext], rbp
0x140006206  call    WPP_SF_qqqZ
0x14000620b  mov     rcx, [rsi+50h]; pMRxDeviceObject
0x14000620f  lea     r8, [rbp+90h]; pWorkQueueItem
0x140006216  lea     r9, UMRxResumeAsyncEngineContext; Routine
0x14000621d  mov     [rsp+68h+pContext], rsi; pContext
0x140006222  xor     edx, edx; WorkQueueType
0x140006224  call    cs:__imp_RxPostToWorkerThread
0x14000622b  nop     dword ptr [rax+rax+00h]
0x140006230  jmp     short loc_140006297
0x140006232  test    rbx, rbx
0x140006235  jz      short loc_14000627F
0x140006237  mov     rdi, cs:WPP_GLOBAL_Control
0x14000623e  cmp     rdi, r14
0x140006241  jz      short loc_14000627F
0x140006243  test    dword ptr [rdi+2Ch], 400h
0x14000624a  jz      short loc_14000627F
0x14000624c  mov     rbx, [rbx+50h]
0x140006250  mov     rdi, [rdi+18h]
0x140006254  call    cs:__imp_PsGetCurrentThreadId
0x14000625b  nop     dword ptr [rax+rax+00h]
0x140006260  mov     [rsp+68h+var_38], rbx
0x140006265  mov     edx, 2Eh ; '.'
0x14000626a  mov     r9, rax
0x14000626d  mov     [rsp+68h+var_40], rsi
0x140006272  mov     rcx, rdi
0x140006275  mov     [rsp+68h+pContext], rbp
0x14000627a  call    WPP_SF_qqqZ
0x14000627f  lea     rcx, [rbp+1C0h]; Event
0x140006286  xor     r8d, r8d; Wait
0x140006289  xor     edx, edx; Increment
0x14000628b  call    cs:__imp_KeSetEvent
0x140006292  nop     dword ptr [rax+rax+00h]
0x140006297  mov     eax, 0C0000016h
0x14000629c  add     rsp, 40h
0x1400062a0  pop     r14
0x1400062a2  pop     rdi
0x1400062a3  pop     rsi
0x1400062a4  pop     rbp
0x1400062a5  pop     rbx
0x1400062a6  retn
```
