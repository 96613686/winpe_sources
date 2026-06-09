# MRxSmbpPostBindUnbindForBrowser

- ea: `0x140021470`
- end: `0x1400215a9`
- name: `MRxSmbpPostBindUnbindForBrowser`
- size: `313`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14008f080`
- `0x14008f7e0`
- `0x140090280`

## callees

- `0x140021470`
- `0x140059f00`
- `0x14005a200`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021504`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021504`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002155e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002155e`
- `ntoskrnl!ExAllocatePool2` at `0x140021497`
- `ntoskrnl!ExAllocatePool2` at `0x140021497`
- `rdbss!RxPostToWorkerThread` at `0x14002158a`
- `rdbss!RxPostToWorkerThread` at `0x14002158a`

## pseudocode

```c
__int64 __fastcall MRxSmbpPostBindUnbindForBrowser(const void **a1, char a2)
{
  char *Pool2; // rax
  char *pContext; // rbx
  bool v7; // bp
  __int16 v8; // ax
  KIRQL v9; // dl
  _QWORD *v10; // rcx

  Pool2 = (char *)ExAllocatePool2(66, *(unsigned __int16 *)a1 + 104LL, 1950578770);
  pContext = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v7 = 0;
  memset(Pool2, 0, 0x68u);
  pContext[96] = a2;
  v8 = *(_WORD *)a1;
  *((_WORD *)pContext + 33) = *(_WORD *)a1;
  *((_WORD *)pContext + 32) = v8;
  *((_QWORD *)pContext + 9) = pContext + 104;
  memmove(pContext + 104, a1[1], *(unsigned __int16 *)a1);
  v9 = KeAcquireSpinLockRaiseToDpc(&BrowserTdiRequestLock);
  if ( (__int64 *)BrowserTdiRequestList == &BrowserTdiRequestList )
    v7 = BrowserTdiRequestActive == 0;
  v10 = (_QWORD *)qword_140070DC8;
  if ( *(__int64 **)qword_140070DC8 != &BrowserTdiRequestList )
    __fastfail(3u);
  *((_QWORD *)pContext + 11) = qword_140070DC8;
  *((_QWORD *)pContext + 10) = &BrowserTdiRequestList;
  *v10 = pContext + 80;
  qword_140070DC8 = (__int64)(pContext + 80);
  KeReleaseSpinLock(&BrowserTdiRequestLock, v9);
  if ( v7 )
    RxPostToWorkerThread(
      MRxSmbDeviceObject,
      BackgroundWorkQueue,
      (PRX_WORK_QUEUE_ITEM)pContext,
      MRxSmbPnpBindBrowserWorker,
      pContext);
  return 0;
}

```

## disassembly

```asm
0x140021470  mov     [rsp+arg_8], rbx
0x140021475  mov     [rsp+arg_10], rsi
0x14002147a  push    rdi
0x14002147b  sub     rsp, 30h
0x14002147f  movzx   esi, dl
0x140021482  mov     rdi, rcx
0x140021485  movzx   edx, word ptr [rcx]
0x140021488  mov     r8d, 74437852h
0x14002148e  add     rdx, 68h ; 'h'
0x140021492  mov     ecx, 42h ; 'B'
0x140021497  call    cs:__imp_ExAllocatePool2
0x14002149e  nop     dword ptr [rax+rax+00h]
0x1400214a3  mov     rbx, rax
0x1400214a6  test    rax, rax
0x1400214a9  jnz     short loc_1400214C1
0x1400214ab  mov     eax, 0C000009Ah
0x1400214b0  mov     rbx, [rsp+38h+arg_8]
0x1400214b5  mov     rsi, [rsp+38h+arg_10]
0x1400214ba  add     rsp, 30h
0x1400214be  pop     rdi
0x1400214bf  retn
0x1400214c1  mov     [rsp+38h+arg_0], rbp
0x1400214c6  xor     edx, edx; Val
0x1400214c8  mov     r8d, 68h ; 'h'; Size
0x1400214ce  mov     rcx, rbx; void *
0x1400214d1  xor     bpl, bpl
0x1400214d4  call    memset
0x1400214d9  mov     [rbx+60h], sil
0x1400214dd  lea     rcx, [rbx+68h]; void *
0x1400214e1  movzx   eax, word ptr [rdi]
0x1400214e4  mov     [rbx+42h], ax
0x1400214e8  mov     [rbx+40h], ax
0x1400214ec  mov     [rbx+48h], rcx
0x1400214f0  movzx   r8d, word ptr [rdi]; Size
0x1400214f4  mov     rdx, [rdi+8]; Src
0x1400214f8  call    memmove
0x1400214fd  lea     rcx, BrowserTdiRequestLock; SpinLock
0x140021504  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002150b  nop     dword ptr [rax+rax+00h]
0x140021510  lea     r8, BrowserTdiRequestList
0x140021517  movzx   edx, al; NewIrql
0x14002151a  cmp     cs:BrowserTdiRequestList, r8
0x140021521  jnz     short loc_140021536
0x140021523  cmp     cs:BrowserTdiRequestActive, 0
0x14002152a  mov     eax, 1
0x14002152f  movzx   ebp, bpl
0x140021533  cmovz   ebp, eax
0x140021536  mov     rcx, cs:qword_140070DC8
0x14002153d  cmp     [rcx], r8
0x140021540  jnz     short loc_1400215A2
0x140021542  lea     rax, [rbx+50h]
0x140021546  mov     [rax+8], rcx
0x14002154a  mov     [rax], r8
0x14002154d  mov     [rcx], rax
0x140021550  lea     rcx, BrowserTdiRequestLock; SpinLock
0x140021557  mov     cs:qword_140070DC8, rax
0x14002155e  call    cs:__imp_KeReleaseSpinLock
0x140021565  nop     dword ptr [rax+rax+00h]
0x14002156a  test    bpl, bpl
0x14002156d  jz      short loc_140021596
0x14002156f  mov     rcx, cs:MRxSmbDeviceObject; pMRxDeviceObject
0x140021576  lea     r9, MRxSmbPnpBindBrowserWorker; Routine
0x14002157d  mov     r8, rbx; pWorkQueueItem
0x140021580  mov     [rsp+38h+pContext], rbx; pContext
0x140021585  mov     edx, 4; WorkQueueType
0x14002158a  call    cs:__imp_RxPostToWorkerThread
0x140021591  nop     dword ptr [rax+rax+00h]
0x140021596  mov     rbp, [rsp+38h+arg_0]
0x14002159b  xor     eax, eax
0x14002159d  jmp     loc_1400214B0
0x1400215a2  mov     ecx, 3
0x1400215a7  int     29h; Win8: RtlFailFast(ecx)
```
