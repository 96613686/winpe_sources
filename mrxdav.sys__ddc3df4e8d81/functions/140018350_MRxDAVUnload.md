# MRxDAVUnload

- ea: `0x140018350`
- end: `0x1400185b8`
- name: `MRxDAVUnload`
- size: `616`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140018350`
- `0x140026c10`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001838c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400183c4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001843d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018475`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400184c0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018509`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001858b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001838c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400183c4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001843d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018475`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400184c0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018509`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001858b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400183f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400183f6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001841a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001841a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001852f`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018542`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018555`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018568`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001852f`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018542`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018555`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018568`
- `rdbss!RxUnregisterMinirdr` at `0x1400184e6`
- `rdbss!RxUnregisterMinirdr` at `0x1400184e6`

## pseudocode

```c
NTSTATUS __fastcall MRxDAVUnload(__int64 a1)
{
  struct _RDBSS_DEVICE_OBJECT *v1; // rsi
  __int64 v3; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v5; // rbx
  HANDLE v6; // rax
  __int64 v7; // rbx
  HANDLE v8; // rax
  __int64 v9; // rbx
  HANDLE v10; // rax
  int v11; // edi
  __int64 v12; // rbx
  HANDLE v13; // rax
  __int64 v14; // rbx
  HANDLE v15; // rax
  NTSTATUS result; // eax
  __int64 v17; // rbx
  HANDLE v18; // rax

  v1 = g_MRxDAVDeviceObject;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
    {
      v3 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v3, 22, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v5 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v6 = PsGetCurrentThreadId();
      WPP_SF_qq(v5, 23, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v6, a1);
    }
  }
  if ( DavExchangeDeviceName )
    ExFreePoolWithTag(DavExchangeDeviceName, 0);
  KeWaitForSingleObject(&TimerThreadEvent, Executive, 0, 0, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v8 = PsGetCurrentThreadId();
      WPP_SF_q(v7, 42, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v8);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v10 = PsGetCurrentThreadId();
      WPP_SF_qq(v9, 43, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v10, v1);
    }
  }
  v11 = UMRxCleanUpDeviceObject(v1);
  if ( v11 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v13 = PsGetCurrentThreadId();
    WPP_SF_qD(v12, 44, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v13, v11);
  }
  RxUnregisterMinirdr(v1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
  {
    v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v15 = PsGetCurrentThreadId();
    WPP_SF_q(v14, 45, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v15);
  }
  ExDeleteResourceLite(&MRxDAVTimerThreadLock);
  ExDeleteResourceLite(&LockTokenEntryListLock);
  ExDeleteResourceLite(&LockConflictEntryListLock);
  result = ExDeleteResourceLite(&QueueLockRefreshWorkItemLock);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
    {
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v18 = PsGetCurrentThreadId();
      return WPP_SF_q(v17, 24, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v18);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140018350  push    rbx
0x140018352  push    rbp
0x140018353  push    rsi
0x140018354  push    rdi
0x140018355  push    r14
0x140018357  push    r15
0x140018359  sub     rsp, 38h
0x14001835d  mov     rsi, cs:g_MRxDAVDeviceObject
0x140018364  mov     rdi, rcx
0x140018367  mov     rbx, cs:WPP_GLOBAL_Control
0x14001836e  lea     rbp, WPP_GLOBAL_Control
0x140018375  lea     r14, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids
0x14001837c  cmp     rbx, rbp
0x14001837f  jz      short loc_1400183E8
0x140018381  bt      dword ptr [rbx+2Ch], 0Eh
0x140018386  jnb     short loc_1400183AB
0x140018388  mov     rbx, [rbx+18h]
0x14001838c  call    cs:__imp_PsGetCurrentThreadId
0x140018393  nop     dword ptr [rax+rax+00h]
0x140018398  mov     edx, 16h
0x14001839d  mov     r8, r14
0x1400183a0  mov     r9, rax
0x1400183a3  mov     rcx, rbx
0x1400183a6  call    WPP_SF_q
0x1400183ab  mov     rbx, cs:WPP_GLOBAL_Control
0x1400183b2  cmp     rbx, rbp
0x1400183b5  jz      short loc_1400183E8
0x1400183b7  test    dword ptr [rbx+2Ch], 2000h
0x1400183be  jz      short loc_1400183E8
0x1400183c0  mov     rbx, [rbx+18h]
0x1400183c4  call    cs:__imp_PsGetCurrentThreadId
0x1400183cb  nop     dword ptr [rax+rax+00h]
0x1400183d0  mov     edx, 17h
0x1400183d5  mov     [rsp+68h+Timeout], rdi
0x1400183da  mov     r9, rax
0x1400183dd  mov     r8, r14
0x1400183e0  mov     rcx, rbx
0x1400183e3  call    WPP_SF_qq
0x1400183e8  mov     rcx, cs:DavExchangeDeviceName; P
0x1400183ef  test    rcx, rcx
0x1400183f2  jz      short loc_140018402
0x1400183f4  xor     edx, edx; Tag
0x1400183f6  call    cs:__imp_ExFreePoolWithTag
0x1400183fd  nop     dword ptr [rax+rax+00h]
0x140018402  xor     r9d, r9d; Alertable
0x140018405  mov     [rsp+68h+Timeout], 0; Timeout
0x14001840e  xor     r8d, r8d; WaitMode
0x140018411  lea     rcx, TimerThreadEvent; Object
0x140018418  xor     edx, edx; WaitReason
0x14001841a  call    cs:__imp_KeWaitForSingleObject
0x140018421  nop     dword ptr [rax+rax+00h]
0x140018426  mov     rbx, cs:WPP_GLOBAL_Control
0x14001842d  cmp     rbx, rbp
0x140018430  jz      short loc_140018499
0x140018432  bt      dword ptr [rbx+2Ch], 0Eh
0x140018437  jnb     short loc_14001845C
0x140018439  mov     rbx, [rbx+18h]
0x14001843d  call    cs:__imp_PsGetCurrentThreadId
0x140018444  nop     dword ptr [rax+rax+00h]
0x140018449  mov     edx, 2Ah ; '*'
0x14001844e  mov     r8, r14
0x140018451  mov     r9, rax
0x140018454  mov     rcx, rbx
0x140018457  call    WPP_SF_q
0x14001845c  mov     rbx, cs:WPP_GLOBAL_Control
0x140018463  cmp     rbx, rbp
0x140018466  jz      short loc_140018499
0x140018468  test    dword ptr [rbx+2Ch], 2000h
0x14001846f  jz      short loc_140018499
0x140018471  mov     rbx, [rbx+18h]
0x140018475  call    cs:__imp_PsGetCurrentThreadId
0x14001847c  nop     dword ptr [rax+rax+00h]
0x140018481  mov     edx, 2Bh ; '+'
0x140018486  mov     [rsp+68h+Timeout], rsi
0x14001848b  mov     r9, rax
0x14001848e  mov     r8, r14
0x140018491  mov     rcx, rbx
0x140018494  call    WPP_SF_qq
0x140018499  mov     rcx, rsi
0x14001849c  call    UMRxCleanUpDeviceObject
0x1400184a1  mov     edi, eax
0x1400184a3  test    eax, eax
0x1400184a5  jns     short loc_1400184E3
0x1400184a7  mov     rbx, cs:WPP_GLOBAL_Control
0x1400184ae  cmp     rbx, rbp
0x1400184b1  jz      short loc_1400184E3
0x1400184b3  test    dword ptr [rbx+2Ch], 2000h
0x1400184ba  jz      short loc_1400184E3
0x1400184bc  mov     rbx, [rbx+18h]
0x1400184c0  call    cs:__imp_PsGetCurrentThreadId
0x1400184c7  nop     dword ptr [rax+rax+00h]
0x1400184cc  mov     edx, 2Ch ; ','
0x1400184d1  mov     dword ptr [rsp+68h+Timeout], edi
0x1400184d5  mov     r9, rax
0x1400184d8  mov     r8, r14
0x1400184db  mov     rcx, rbx
0x1400184de  call    WPP_SF_qD
0x1400184e3  mov     rcx, rsi; RxDeviceObject
0x1400184e6  call    cs:__imp_RxUnregisterMinirdr
0x1400184ed  nop     dword ptr [rax+rax+00h]
0x1400184f2  mov     rbx, cs:WPP_GLOBAL_Control
0x1400184f9  cmp     rbx, rbp
0x1400184fc  jz      short loc_140018528
0x1400184fe  bt      dword ptr [rbx+2Ch], 0Eh
0x140018503  jnb     short loc_140018528
0x140018505  mov     rbx, [rbx+18h]
0x140018509  call    cs:__imp_PsGetCurrentThreadId
0x140018510  nop     dword ptr [rax+rax+00h]
0x140018515  mov     edx, 2Dh ; '-'
0x14001851a  mov     r8, r14
0x14001851d  mov     r9, rax
0x140018520  mov     rcx, rbx
0x140018523  call    WPP_SF_q
0x140018528  lea     rcx, MRxDAVTimerThreadLock; Resource
0x14001852f  call    cs:__imp_ExDeleteResourceLite
0x140018536  nop     dword ptr [rax+rax+00h]
0x14001853b  lea     rcx, LockTokenEntryListLock; Resource
0x140018542  call    cs:__imp_ExDeleteResourceLite
0x140018549  nop     dword ptr [rax+rax+00h]
0x14001854e  lea     rcx, LockConflictEntryListLock; Resource
0x140018555  call    cs:__imp_ExDeleteResourceLite
0x14001855c  nop     dword ptr [rax+rax+00h]
0x140018561  lea     rcx, QueueLockRefreshWorkItemLock; Resource
0x140018568  call    cs:__imp_ExDeleteResourceLite
0x14001856f  nop     dword ptr [rax+rax+00h]
0x140018574  mov     rbx, cs:WPP_GLOBAL_Control
0x14001857b  cmp     rbx, rbp
0x14001857e  jz      short loc_1400185AA
0x140018580  bt      dword ptr [rbx+2Ch], 0Eh
0x140018585  jnb     short loc_1400185AA
0x140018587  mov     rbx, [rbx+18h]
0x14001858b  call    cs:__imp_PsGetCurrentThreadId
0x140018592  nop     dword ptr [rax+rax+00h]
0x140018597  mov     edx, 18h
0x14001859c  mov     r8, r14
0x14001859f  mov     r9, rax
0x1400185a2  mov     rcx, rbx
0x1400185a5  call    WPP_SF_q
0x1400185aa  add     rsp, 38h
0x1400185ae  pop     r15
0x1400185b0  pop     r14
0x1400185b2  pop     rdi
0x1400185b3  pop     rsi
0x1400185b4  pop     rbp
0x1400185b5  pop     rbx
0x1400185b6  retn
```
