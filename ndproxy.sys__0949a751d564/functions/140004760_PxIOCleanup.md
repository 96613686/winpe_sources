# PxIOCleanup

- ea: `0x140004760`
- end: `0x1400049c6`
- name: `PxIOCleanup`
- size: `614`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001b54`
- `0x140004760`
- `0x1400113a0`
- `0x140011c00`
- `0x140015290`
- `0x1400156d8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000481f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400048c8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004944`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000481f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400048c8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004944`
- `ntoskrnl!IofCompleteRequest` at `0x140004935`
- `ntoskrnl!IofCompleteRequest` at `0x14000497f`
- `ntoskrnl!IofCompleteRequest` at `0x140004935`
- `ntoskrnl!IofCompleteRequest` at `0x14000497f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004870`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004924`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000495f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004870`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004924`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000495f`
- `NDIS!NdisReleaseRWLock` at `0x1400047f2`
- `NDIS!NdisReleaseRWLock` at `0x1400048b2`
- `NDIS!NdisReleaseRWLock` at `0x1400047f2`
- `NDIS!NdisReleaseRWLock` at `0x1400048b2`
- `NDIS!NdisAcquireRWLockRead` at `0x1400047c4`
- `NDIS!NdisAcquireRWLockRead` at `0x14000488d`
- `NDIS!NdisAcquireRWLockRead` at `0x1400047c4`
- `NDIS!NdisAcquireRWLockRead` at `0x14000488d`

## pseudocode

```c
__int64 __fastcall PxIOCleanup(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebp
  int DeviceObject; // edi
  _BYTE *v6; // rbx
  KSPIN_LOCK *v7; // r14
  int v8; // eax
  KIRQL v10; // al
  IRP *Blink; // rbx
  _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF
  PVOID Entry; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  Entry = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids);
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, &LockState, 0);
  DeviceObject = (int)WPP_MAIN_CB.Queue.Wcb.DeviceObject;
  while ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) )
  {
    if ( !DeviceObject )
      break;
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, &LockState);
    if ( (unsigned __int8)IsVcValid(v2++, &Entry) )
    {
      v6 = Entry;
      v7 = (KSPIN_LOCK *)((char *)Entry + 512);
      v6[520] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 64);
      v8 = *((_DWORD *)v6 + 9);
      if ( (v8 & 0x1804) == 0 )
      {
        *((_DWORD *)v6 + 9) = v8 | 0x800;
        PxVcCleanup(v6, 0);
        PxTapiCompleteAllIrps(v6);
        --*((_DWORD *)v6 + 7);
      }
      if ( (*((_DWORD *)v6 + 7))-- == 1 )
        DoDerefVcWork(v6);
      else
        KeReleaseSpinLock(v7, v6[520]);
      --DeviceObject;
    }
    NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, &LockState, 0);
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, &LockState);
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
  Blink = (IRP *)WPP_MAIN_CB.Queue.ListEntry.Blink;
  LOBYTE(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) = v10;
  if ( WPP_MAIN_CB.Queue.ListEntry.Blink
    && WPP_MAIN_CB.Queue.ListEntry.Blink[12].Flink == *(struct _LIST_ENTRY **)(a2 + 192)
    && _InterlockedExchange64((volatile __int64 *)&WPP_MAIN_CB.Queue.ListEntry.Blink[6].Blink, 0) )
  {
    WPP_MAIN_CB.Queue.ListEntry.Blink = 0;
    Blink->IoStatus.Status = -1073741536;
    Blink->IoStatus.Information = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, (KIRQL)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
    IofCompleteRequest(Blink, 0);
    LOBYTE(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, (KIRQL)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
  *(_DWORD *)(a2 + 48) = 0;
  *(_QWORD *)(a2 + 56) = 0;
  IofCompleteRequest((PIRP)a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140004760  mov     [rsp+arg_0], rbx
0x140004765  push    rbp
0x140004766  push    rsi
0x140004767  push    rdi
0x140004768  push    r13
0x14000476a  push    r14
0x14000476c  sub     rsp, 20h
0x140004770  xor     ebp, ebp
0x140004772  mov     [rsp+48h+Entry], 0
0x14000477b  xor     eax, eax
0x14000477d  mov     rsi, rdx
0x140004780  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x140004785  mov     [rsp+48h+LockState.Flags], al
0x140004789  mov     rcx, cs:WPP_GLOBAL_Control
0x140004790  lea     r13, WPP_GLOBAL_Control
0x140004797  cmp     rcx, r13
0x14000479a  jz      short loc_1400047B5
0x14000479c  cmp     byte ptr [rcx+29h], 5
0x1400047a0  jb      short loc_1400047B5
0x1400047a2  mov     rcx, [rcx+18h]
0x1400047a6  lea     edx, [rbp+28h]
0x1400047a9  lea     r8, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids
0x1400047b0  call    WPP_SF_
0x1400047b5  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x1400047bc  lea     rdx, [rsp+48h+LockState]; LockState
0x1400047c1  xor     r8d, r8d; Flags
0x1400047c4  call    cs:__imp_NdisAcquireRWLockRead
0x1400047cb  nop     dword ptr [rax+rax+00h]
0x1400047d0  mov     edi, dword ptr cs:WPP_MAIN_CB.Queue+30h
0x1400047d6  test    edi, edi
0x1400047d8  jz      loc_1400048A6
0x1400047de  test    edi, edi
0x1400047e0  jz      loc_1400048A6
0x1400047e6  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x1400047ed  lea     rdx, [rsp+48h+LockState]; LockState
0x1400047f2  call    cs:__imp_NdisReleaseRWLock
0x1400047f9  nop     dword ptr [rax+rax+00h]
0x1400047fe  mov     ecx, ebp
0x140004800  lea     rdx, [rsp+48h+Entry]
0x140004805  call    IsVcValid
0x14000480a  inc     ebp
0x14000480c  test    al, al
0x14000480e  jz      short loc_14000487E
0x140004810  mov     rbx, [rsp+48h+Entry]
0x140004815  lea     r14, [rbx+200h]
0x14000481c  mov     rcx, r14; SpinLock
0x14000481f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004826  nop     dword ptr [rax+rax+00h]
0x14000482b  mov     [rbx+208h], al
0x140004831  mov     eax, [rbx+24h]
0x140004834  test    eax, 1804h
0x140004839  jnz     short loc_140004857
0x14000483b  bts     eax, 0Bh
0x14000483f  xor     edx, edx
0x140004841  mov     rcx, rbx
0x140004844  mov     [rbx+24h], eax
0x140004847  call    PxVcCleanup
0x14000484c  mov     rcx, rbx
0x14000484f  call    PxTapiCompleteAllIrps
0x140004854  dec     dword ptr [rbx+1Ch]
0x140004857  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x14000485b  jnz     short loc_140004867
0x14000485d  mov     rcx, rbx; Entry
0x140004860  call    DoDerefVcWork
0x140004865  jmp     short loc_14000487C
0x140004867  mov     dl, [rbx+208h]; NewIrql
0x14000486d  mov     rcx, r14; SpinLock
0x140004870  call    cs:__imp_KeReleaseSpinLock
0x140004877  nop     dword ptr [rax+rax+00h]
0x14000487c  dec     edi
0x14000487e  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x140004885  lea     rdx, [rsp+48h+LockState]; LockState
0x14000488a  xor     r8d, r8d; Flags
0x14000488d  call    cs:__imp_NdisAcquireRWLockRead
0x140004894  nop     dword ptr [rax+rax+00h]
0x140004899  cmp     dword ptr cs:WPP_MAIN_CB.Queue+30h, 0
0x1400048a0  jnz     loc_1400047DE
0x1400048a6  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x1400048ad  lea     rdx, [rsp+48h+LockState]; LockState
0x1400048b2  call    cs:__imp_NdisReleaseRWLock
0x1400048b9  nop     dword ptr [rax+rax+00h]
0x1400048be  lea     rdi, WPP_MAIN_CB.Queue+10h
0x1400048c5  mov     rcx, rdi; SpinLock
0x1400048c8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400048cf  nop     dword ptr [rax+rax+00h]
0x1400048d4  mov     rbx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400048db  mov     byte ptr cs:WPP_MAIN_CB.Queue+18h, al
0x1400048e1  test    rbx, rbx
0x1400048e4  jz      short loc_140004956
0x1400048e6  mov     rax, [rsi+0C0h]
0x1400048ed  cmp     [rbx+0C0h], rax
0x1400048f4  jnz     short loc_140004956
0x1400048f6  xor     eax, eax
0x1400048f8  xchg    rax, [rbx+68h]
0x1400048fc  test    rax, rax
0x1400048ff  jz      short loc_140004956
0x140004901  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, 0
0x14000490c  mov     rcx, rdi; SpinLock
0x14000490f  mov     dword ptr [rbx+30h], 0C0000120h
0x140004916  mov     qword ptr [rbx+38h], 0
0x14000491e  mov     dl, byte ptr cs:WPP_MAIN_CB.Queue+18h; NewIrql
0x140004924  call    cs:__imp_KeReleaseSpinLock
0x14000492b  nop     dword ptr [rax+rax+00h]
0x140004930  xor     edx, edx; PriorityBoost
0x140004932  mov     rcx, rbx; Irp
0x140004935  call    cs:__imp_IofCompleteRequest
0x14000493c  nop     dword ptr [rax+rax+00h]
0x140004941  mov     rcx, rdi; SpinLock
0x140004944  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000494b  nop     dword ptr [rax+rax+00h]
0x140004950  mov     byte ptr cs:WPP_MAIN_CB.Queue+18h, al
0x140004956  mov     dl, byte ptr cs:WPP_MAIN_CB.Queue+18h; NewIrql
0x14000495c  mov     rcx, rdi; SpinLock
0x14000495f  call    cs:__imp_KeReleaseSpinLock
0x140004966  nop     dword ptr [rax+rax+00h]
0x14000496b  xor     edx, edx; PriorityBoost
0x14000496d  mov     dword ptr [rsi+30h], 0
0x140004974  mov     rcx, rsi; Irp
0x140004977  mov     qword ptr [rsi+38h], 0
0x14000497f  call    cs:__imp_IofCompleteRequest
0x140004986  nop     dword ptr [rax+rax+00h]
0x14000498b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004992  cmp     rcx, r13
0x140004995  jz      short loc_1400049B2
0x140004997  cmp     byte ptr [rcx+29h], 5
0x14000499b  jb      short loc_1400049B2
0x14000499d  mov     rcx, [rcx+18h]
0x1400049a1  lea     r8, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids
0x1400049a8  mov     edx, 29h ; ')'
0x1400049ad  call    WPP_SF_
0x1400049b2  mov     rbx, [rsp+48h+arg_0]
0x1400049b7  xor     eax, eax
0x1400049b9  add     rsp, 20h
0x1400049bd  pop     r14
0x1400049bf  pop     r13
0x1400049c1  pop     rdi
0x1400049c2  pop     rsi
0x1400049c3  pop     rbp
0x1400049c4  retn
```
