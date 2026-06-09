# CDDPDEV::Flush(void)

- ea: `0x14000ef80`
- end: `0x14000f365`
- name: `?Flush@CDDPDEV@@QEAAJXZ`
- size: `997`
- prototype: `__int64 __fastcall(CDDPDEV *__hidden this)`
- caller_count: `26`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002504`
- `0x140004904`
- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x14000a254`
- `0x14000cf80`
- `0x14000d63c`
- `0x14000e580`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`
- `0x14001f778`
- `0x1400212b0`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`
- `0x140025090`
- `0x1400255b0`
- `0x140025c90`
- `0x1400261a0`
- `0x1400267f0`
- `0x140026d40`
- `0x140027370`
- `0x14002ee20`
- `0x140031820`

## callees

- `0x14000ef80`
- `0x14000fbb4`
- `0x140010670`
- `0x140010850`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000f134`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f134`
- `ntoskrnl!KeClearEvent` at `0x14000f147`
- `ntoskrnl!KeClearEvent` at `0x14000f147`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000efc8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000f00a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000f0a4`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000efc8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000f00a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000f0a4`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000f02c`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000f058`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000f02c`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000f058`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000efec`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f086`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f0b8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000efec`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f086`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f0b8`
- `ntoskrnl!KeSetEvent` at `0x14000f114`
- `ntoskrnl!KeSetEvent` at `0x14000f114`
- `ntoskrnl!DbgPrint` at `0x14000f192`
- `ntoskrnl!DbgPrint` at `0x14000f305`
- `ntoskrnl!DbgPrint` at `0x14000f192`
- `ntoskrnl!DbgPrint` at `0x14000f305`
- `ntoskrnl!KdDebuggerEnabled` at `0x14000f17f`
- `ntoskrnl!KdDebuggerEnabled` at `0x14000f2ee`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000f1b9`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000f32c`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000f1b9`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000f32c`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000f210`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000f263`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000f2b6`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000f210`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000f263`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000f2b6`
- `watchdog!WdLogSingleEntry0` at `0x14000f1a3`
- `watchdog!WdLogSingleEntry0` at `0x14000f1fa`
- `watchdog!WdLogSingleEntry0` at `0x14000f24d`
- `watchdog!WdLogSingleEntry0` at `0x14000f2a0`
- `watchdog!WdLogSingleEntry0` at `0x14000f316`
- `watchdog!WdLogSingleEntry0` at `0x14000f1a3`
- `watchdog!WdLogSingleEntry0` at `0x14000f1fa`
- `watchdog!WdLogSingleEntry0` at `0x14000f24d`
- `watchdog!WdLogSingleEntry0` at `0x14000f2a0`
- `watchdog!WdLogSingleEntry0` at `0x14000f316`

## string_xrefs

- `0x14000f18b`: `bFromWorkerThread is set for non worker thread in EnableWorkerThreadAccess`
- `0x14000f2fe`: `CddIssueCommand: worker thread submission mutex is not held\n`

## pseudocode

```c
__int64 __fastcall CDDPDEV::Flush(CDDPDEV *this)
{
  char v2; // bp
  __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v7; // rdi
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rax

  if ( (*((_DWORD *)this + 686) & 0x40) == 0 )
  {
    if ( KeGetCurrentIrql() )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 785;
      v9 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v9[3] = gCddImageInfo;
      v9[4] = (unsigned int)dword_14003E570;
      v9[5] = 215857758;
      WdLogGlobalForLineNumber = 785;
    }
    v7 = *((_QWORD *)this + 686);
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v7);
    *((_DWORD *)this + 912) = 0;
    if ( KeGetCurrentIrql() )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2021;
      v10 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v10[3] = gCddImageInfo;
      v10[4] = (unsigned int)dword_14003E570;
      v10[5] = 215857758;
      WdLogGlobalForLineNumber = 2021;
    }
    if ( *(struct _KTHREAD **)(*((_QWORD *)this + 686) + 8LL) != KeGetCurrentThread() && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("CddIssueCommand: worker thread submission mutex is not held\n");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 2025;
      v11 = (_QWORD *)WdLogNewEntry5_WdError();
      v11[3] = gCddImageInfo;
      v11[4] = (unsigned int)dword_14003E570;
      v11[5] = 215857758;
      WdLogGlobalForLineNumber = 2025;
      __debugbreak();
    }
    *((_QWORD *)this + 322) = KeGetCurrentThread();
    *((_DWORD *)this + 900) = 13;
    GetConnectedStandbyProcessName(this);
    KeSetEvent(*((PRKEVENT *)this + 326), 0, 0);
    KeWaitForSingleObject(*((PVOID *)this + 329), Executive, 0, 0, 0);
    KeClearEvent(*((PRKEVENT *)this + 326));
    v5 = v7;
    *((_QWORD *)this + 322) = 0;
    goto LABEL_12;
  }
  if ( *((struct _KTHREAD **)this + 321) == KeGetCurrentThread() )
  {
    v2 = 0;
  }
  else
  {
    v2 = 1;
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)this + 361));
  }
  if ( KeGetCurrentThread() == *((struct _KTHREAD **)this + 321) )
  {
    CDDPDEV::FlushGdiOutput(this, 0);
  }
  else
  {
    if ( KeGetCurrentIrql() )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 785;
      v8 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v8[3] = gCddImageInfo;
      v8[4] = (unsigned int)dword_14003E570;
      v8[5] = 215857758;
      WdLogGlobalForLineNumber = 785;
    }
    v3 = *((_QWORD *)this + 686);
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v3);
    *((_DWORD *)this + 912) = 0;
    CddIssueCommand(this, 13);
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v3);
  }
  v4 = *((_QWORD *)this + 1587);
  if ( *(_DWORD *)(v4 + 32) == *(_DWORD *)(v4 + 16) )
  {
    *(_DWORD *)(v4 + 2120) = 0;
    *(_BYTE *)(v4 + 2144) = 0;
  }
  if ( v2 )
  {
    v5 = *((_QWORD *)this + 361);
LABEL_12:
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v5);
  }
  return 0;
}

```

## disassembly

```asm
0x14000ef80  mov     [rsp+arg_8], rbx
0x14000ef85  mov     [rsp+arg_10], rsi
0x14000ef8a  push    rdi
0x14000ef8b  sub     rsp, 30h
0x14000ef8f  mov     eax, [rcx+0AB8h]
0x14000ef95  mov     rbx, rcx
0x14000ef98  test    al, 40h
0x14000ef9a  jz      loc_14000F086
0x14000efa0  mov     rcx, [rcx+0A08h]
0x14000efa7  mov     rax, gs:188h
0x14000efb0  mov     [rsp+38h+arg_0], rbp
0x14000efb5  cmp     rcx, rax
0x14000efb8  jz      loc_14000F171
0x14000efbe  mov     rcx, [rbx+0B48h]
0x14000efc5  mov     bpl, 1
0x14000efc8  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000efcf  nop     dword ptr [rax+rax+00h]
0x14000efd4  mov     rax, gs:188h
0x14000efdd  xor     esi, esi
0x14000efdf  cmp     rax, [rbx+0A08h]
0x14000efe6  jz      loc_14000F162
0x14000efec  call    cs:__imp_KeGetCurrentIrql
0x14000eff3  nop     dword ptr [rax+rax+00h]
0x14000eff8  test    al, al
0x14000effa  jnz     loc_14000F1F5
0x14000f000  mov     rdi, [rbx+1570h]
0x14000f007  mov     rcx, rdi
0x14000f00a  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000f011  nop     dword ptr [rax+rax+00h]
0x14000f016  mov     edx, 0Dh
0x14000f01b  mov     [rbx+0E40h], esi
0x14000f021  mov     rcx, rbx
0x14000f024  call    ?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z; CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)
0x14000f029  mov     rcx, rdi
0x14000f02c  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000f033  nop     dword ptr [rax+rax+00h]
0x14000f038  mov     rdx, [rbx+3198h]
0x14000f03f  mov     ecx, [rdx+10h]
0x14000f042  cmp     [rdx+20h], ecx
0x14000f045  jz      short loc_14000F077
0x14000f047  test    bpl, bpl
0x14000f04a  mov     rbp, [rsp+38h+arg_0]
0x14000f04f  jz      short loc_14000F064
0x14000f051  mov     rcx, [rbx+0B48h]
0x14000f058  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000f05f  nop     dword ptr [rax+rax+00h]
0x14000f064  mov     rbx, [rsp+38h+arg_8]
0x14000f069  xor     eax, eax
0x14000f06b  mov     rsi, [rsp+38h+arg_10]
0x14000f070  add     rsp, 30h
0x14000f074  pop     rdi
0x14000f075  retn
0x14000f077  mov     [rdx+848h], esi
0x14000f07d  mov     [rdx+860h], sil
0x14000f084  jmp     short loc_14000F047
0x14000f086  call    cs:__imp_KeGetCurrentIrql
0x14000f08d  nop     dword ptr [rax+rax+00h]
0x14000f092  test    al, al
0x14000f094  jnz     loc_14000F248
0x14000f09a  mov     rdi, [rbx+1570h]
0x14000f0a1  mov     rcx, rdi
0x14000f0a4  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000f0ab  nop     dword ptr [rax+rax+00h]
0x14000f0b0  xor     esi, esi
0x14000f0b2  mov     [rbx+0E40h], esi
0x14000f0b8  call    cs:__imp_KeGetCurrentIrql
0x14000f0bf  nop     dword ptr [rax+rax+00h]
0x14000f0c4  test    al, al
0x14000f0c6  jnz     loc_14000F29B
0x14000f0cc  mov     rcx, gs:188h
0x14000f0d5  mov     rax, [rbx+1570h]
0x14000f0dc  cmp     [rax+8], rcx
0x14000f0e0  jnz     loc_14000F2EE
0x14000f0e6  mov     rax, gs:188h
0x14000f0ef  mov     rcx, rbx; struct CDDPDEV *
0x14000f0f2  mov     [rbx+0A10h], rax
0x14000f0f9  mov     dword ptr [rbx+0E10h], 0Dh
0x14000f103  call    ?GetConnectedStandbyProcessName@@YAXPEAUCDDPDEV@@@Z; GetConnectedStandbyProcessName(CDDPDEV *)
0x14000f108  mov     rcx, [rbx+0A30h]; Event
0x14000f10f  xor     r8d, r8d; Wait
0x14000f112  xor     edx, edx; Increment
0x14000f114  call    cs:__imp_KeSetEvent
0x14000f11b  nop     dword ptr [rax+rax+00h]
0x14000f120  mov     rcx, [rbx+0A48h]; Object
0x14000f127  xor     r9d, r9d; Alertable
0x14000f12a  xor     r8d, r8d; WaitMode
0x14000f12d  mov     [rsp+38h+Timeout], rsi; Timeout
0x14000f132  xor     edx, edx; WaitReason
0x14000f134  call    cs:__imp_KeWaitForSingleObject
0x14000f13b  nop     dword ptr [rax+rax+00h]
0x14000f140  mov     rcx, [rbx+0A30h]; Event
0x14000f147  call    cs:__imp_KeClearEvent
0x14000f14e  nop     dword ptr [rax+rax+00h]
0x14000f153  mov     rcx, rdi
0x14000f156  mov     [rbx+0A10h], rsi
0x14000f15d  jmp     loc_14000F058
0x14000f162  xor     edx, edx; unsigned int
0x14000f164  mov     rcx, rbx; this
0x14000f167  call    ?FlushGdiOutput@CDDPDEV@@QEAAXI@Z; CDDPDEV::FlushGdiOutput(uint)
0x14000f16c  jmp     loc_14000F038
0x14000f171  mov     rax, gs:188h
0x14000f17a  cmp     rax, rcx
0x14000f17d  jz      short loc_14000F1ED
0x14000f17f  mov     rax, cs:KdDebuggerEnabled
0x14000f186  cmp     byte ptr [rax], 0
0x14000f189  jz      short loc_14000F1ED
0x14000f18b  lea     rcx, aBfromworkerthr; "bFromWorkerThread is set for non worker"...
0x14000f192  call    cs:__imp_DbgPrint
0x14000f199  nop     dword ptr [rax+rax+00h]
0x14000f19e  mov     ecx, 2
0x14000f1a3  call    cs:__imp_WdLogSingleEntry0
0x14000f1aa  nop     dword ptr [rax+rax+00h]
0x14000f1af  mov     cs:WdLogGlobalForLineNumber, 340h
0x14000f1b9  call    cs:__imp_WdLogNewEntry5_WdError
0x14000f1c0  nop     dword ptr [rax+rax+00h]
0x14000f1c5  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000f1cc  mov     [rax+18h], rcx
0x14000f1d0  mov     ecx, cs:dword_14003E570
0x14000f1d6  mov     [rax+20h], rcx
0x14000f1da  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000f1e2  mov     cs:WdLogGlobalForLineNumber, 340h
0x14000f1ec  int     3; Trap to Debugger
0x14000f1ed  xor     bpl, bpl
0x14000f1f0  jmp     loc_14000EFD4
0x14000f1f5  mov     ecx, 1
0x14000f1fa  call    cs:__imp_WdLogSingleEntry0
0x14000f201  nop     dword ptr [rax+rax+00h]
0x14000f206  mov     cs:WdLogGlobalForLineNumber, 311h
0x14000f210  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14000f217  nop     dword ptr [rax+rax+00h]
0x14000f21c  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000f223  mov     [rax+18h], rcx
0x14000f227  mov     ecx, cs:dword_14003E570
0x14000f22d  mov     [rax+20h], rcx
0x14000f231  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000f239  mov     cs:WdLogGlobalForLineNumber, 311h
0x14000f243  jmp     loc_14000F000
0x14000f248  mov     ecx, 1
0x14000f24d  call    cs:__imp_WdLogSingleEntry0
0x14000f254  nop     dword ptr [rax+rax+00h]
0x14000f259  mov     cs:WdLogGlobalForLineNumber, 311h
0x14000f263  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14000f26a  nop     dword ptr [rax+rax+00h]
0x14000f26f  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000f276  mov     [rax+18h], rcx
0x14000f27a  mov     ecx, cs:dword_14003E570
0x14000f280  mov     [rax+20h], rcx
0x14000f284  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000f28c  mov     cs:WdLogGlobalForLineNumber, 311h
0x14000f296  jmp     loc_14000F09A
0x14000f29b  mov     ecx, 1
0x14000f2a0  call    cs:__imp_WdLogSingleEntry0
0x14000f2a7  nop     dword ptr [rax+rax+00h]
0x14000f2ac  mov     cs:WdLogGlobalForLineNumber, 7E5h
0x14000f2b6  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14000f2bd  nop     dword ptr [rax+rax+00h]
0x14000f2c2  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000f2c9  mov     [rax+18h], rcx
0x14000f2cd  mov     ecx, cs:dword_14003E570
0x14000f2d3  mov     [rax+20h], rcx
0x14000f2d7  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000f2df  mov     cs:WdLogGlobalForLineNumber, 7E5h
0x14000f2e9  jmp     loc_14000F0CC
0x14000f2ee  mov     rax, cs:KdDebuggerEnabled
0x14000f2f5  cmp     [rax], sil
0x14000f2f8  jz      loc_14000F0E6
0x14000f2fe  lea     rcx, aCddissuecomman; "CddIssueCommand: worker thread submissi"...
0x14000f305  call    cs:__imp_DbgPrint
0x14000f30c  nop     dword ptr [rax+rax+00h]
0x14000f311  mov     ecx, 2
0x14000f316  call    cs:__imp_WdLogSingleEntry0
0x14000f31d  nop     dword ptr [rax+rax+00h]
0x14000f322  mov     cs:WdLogGlobalForLineNumber, 7E9h
0x14000f32c  call    cs:__imp_WdLogNewEntry5_WdError
0x14000f333  nop     dword ptr [rax+rax+00h]
0x14000f338  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000f33f  mov     [rax+18h], rcx
0x14000f343  mov     ecx, cs:dword_14003E570
0x14000f349  mov     [rax+20h], rcx
0x14000f34d  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000f355  mov     cs:WdLogGlobalForLineNumber, 7E9h
0x14000f35f  int     3; Trap to Debugger
0x14000f360  jmp     loc_14000F0E6
```
