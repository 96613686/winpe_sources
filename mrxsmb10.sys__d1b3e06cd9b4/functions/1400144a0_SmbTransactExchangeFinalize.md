# SmbTransactExchangeFinalize

- ea: `0x1400144a0`
- end: `0x1400145d8`
- name: `SmbTransactExchangeFinalize`
- size: `312`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140009340`
- `0x14000e01c`
- `0x14000ebd8`
- `0x1400144a0`
- `0x14004f060`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140014582`
- `ntoskrnl!KeGetCurrentIrql` at `0x140014582`
- `rdbss!RxPostToWorkerThread` at `0x1400145b4`
- `rdbss!RxPostToWorkerThread` at `0x1400145b4`
- `mrxsmb!MRxSmbDeviceObject` at `0x140014592`

## pseudocode

```c
__int64 __fastcall SmbTransactExchangeFinalize(unsigned int *Context)
{
  __int64 v2; // r9
  unsigned int v3; // r8d
  __int64 v4; // r9

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, Context);
  if ( (Context[18] & 1) != 0 )
    SmbCeDissociateMidFromExchange(*((_QWORD *)Context + 10), Context);
  v2 = Context[108];
  if ( (_DWORD)v2 )
  {
    v3 = Context[109];
    if ( (_DWORD)v2 != v3
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v2, v3);
    }
  }
  v4 = Context[98];
  if ( (_DWORD)v4
    && (_DWORD)v4 != Context[99]
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v4, Context[99]);
  }
  if ( KeGetCurrentIrql() < 2u )
    SmbCeDiscardTransactExchange((unsigned __int8 *)Context);
  else
    RxPostToWorkerThread(
      MRxSmbDeviceObject,
      NormalWorkQueue,
      (PRX_WORK_QUEUE_ITEM)(Context + 44),
      (PRX_WORKERTHREAD_ROUTINE)SmbCeDiscardTransactExchange,
      Context);
  return 0;
}

```

## disassembly

```asm
0x1400144a0  mov     [rsp+arg_0], rbx
0x1400144a5  push    rdi
0x1400144a6  sub     rsp, 30h
0x1400144aa  mov     rbx, rcx
0x1400144ad  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400144b4  lea     rdi, WPP_GLOBAL_Control
0x1400144bb  cmp     rcx, rdi
0x1400144be  jz      short loc_1400144E1
0x1400144c0  test    dword ptr [rcx+2Ch], 200h
0x1400144c7  jz      short loc_1400144E1
0x1400144c9  mov     rcx, [rcx+18h]
0x1400144cd  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x1400144d4  mov     edx, 4Bh ; 'K'
0x1400144d9  mov     r9, rbx
0x1400144dc  call    WPP_SF_q
0x1400144e1  mov     eax, [rbx+48h]
0x1400144e4  test    al, 1
0x1400144e6  jz      short loc_1400144F4
0x1400144e8  mov     rcx, [rbx+50h]
0x1400144ec  mov     rdx, rbx
0x1400144ef  call    SmbCeDissociateMidFromExchange
0x1400144f4  mov     r9d, [rbx+1B0h]
0x1400144fb  test    r9d, r9d
0x1400144fe  jz      short loc_14001453B
0x140014500  mov     r8d, [rbx+1B4h]
0x140014507  cmp     r9d, r8d
0x14001450a  jz      short loc_14001453B
0x14001450c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140014513  cmp     rcx, rdi
0x140014516  jz      short loc_14001453B
0x140014518  test    dword ptr [rcx+2Ch], 400h
0x14001451f  jz      short loc_14001453B
0x140014521  mov     rcx, [rcx+18h]
0x140014525  mov     edx, 4Ch ; 'L'
0x14001452a  mov     dword ptr [rsp+38h+pContext], r8d
0x14001452f  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140014536  call    WPP_SF_Dd
0x14001453b  mov     r9d, [rbx+188h]
0x140014542  test    r9d, r9d
0x140014545  jz      short loc_140014582
0x140014547  mov     r10d, [rbx+18Ch]
0x14001454e  cmp     r9d, r10d
0x140014551  jz      short loc_140014582
0x140014553  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001455a  cmp     rcx, rdi
0x14001455d  jz      short loc_140014582
0x14001455f  test    dword ptr [rcx+2Ch], 400h
0x140014566  jz      short loc_140014582
0x140014568  mov     rcx, [rcx+18h]
0x14001456c  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140014573  mov     edx, 4Dh ; 'M'
0x140014578  mov     dword ptr [rsp+38h+pContext], r10d
0x14001457d  call    WPP_SF_Dd
0x140014582  call    cs:__imp_KeGetCurrentIrql
0x140014589  nop     dword ptr [rax+rax+00h]
0x14001458e  cmp     al, 2
0x140014590  jb      short loc_1400145C2
0x140014592  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140014599  lea     r8, [rbx+0B0h]; pWorkQueueItem
0x1400145a0  lea     r9, SmbCeDiscardTransactExchange; Routine
0x1400145a7  mov     [rsp+38h+pContext], rbx; pContext
0x1400145ac  mov     edx, 3; WorkQueueType
0x1400145b1  mov     rcx, [rcx]; pMRxDeviceObject
0x1400145b4  call    cs:__imp_RxPostToWorkerThread
0x1400145bb  nop     dword ptr [rax+rax+00h]
0x1400145c0  jmp     short loc_1400145CA
0x1400145c2  mov     rcx, rbx; Context
0x1400145c5  call    SmbCeDiscardTransactExchange
0x1400145ca  mov     rbx, [rsp+38h+arg_0]
0x1400145cf  xor     eax, eax
0x1400145d1  add     rsp, 30h
0x1400145d5  pop     rdi
0x1400145d6  retn
```
