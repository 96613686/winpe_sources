# RDPDYN_Shutdown

- ea: `0x140002d44`
- end: `0x140002ef3`
- name: `RDPDYN_Shutdown`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140017c70`

## callees

- `0x140001660`
- `0x140001d60`
- `0x140001e30`
- `0x140002d44`
- `0x140002f64`
- `0x140002fb0`
- `0x140004168`
- `0x1400050cc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002d79`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002de4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002e46`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002d79`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002de4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002e46`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002db4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e15`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e7c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002db4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e15`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e7c`
- `ntoskrnl!IofCompleteRequest` at `0x140002dd1`
- `ntoskrnl!IofCompleteRequest` at `0x140002dd1`

## pseudocode

```c
__int64 RDPDYN_Shutdown()
{
  KIRQL v0; // si
  struct tagSESSIONLIST *Lock; // rcx
  __int64 v2; // rax
  unsigned int v3; // ebp
  __int64 v4; // rbx
  KIRQL v5; // al
  __int64 v6; // rax
  __int64 v7; // rcx
  IRP *v8; // rdi
  void *v9; // rsi
  _QWORD **v10; // rdi
  _QWORD *v11; // rbx
  _QWORD *v12; // rax
  struct tagSESSIONLISTNODE *v13; // rbx
  int v15; // [rsp+50h] [rbp+8h] BYREF
  RefCount *v16; // [rsp+58h] [rbp+10h] BYREF
  void *v17; // [rsp+60h] [rbp+18h] BYREF

  v17 = 0;
  v15 = 0;
  v16 = 0;
  if ( WPP_MAIN_CB.DeviceQueue.Lock )
  {
    v0 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock);
    while ( 1 )
    {
      Lock = (struct tagSESSIONLIST *)WPP_MAIN_CB.DeviceQueue.Lock;
      v2 = *(_QWORD *)(WPP_MAIN_CB.DeviceQueue.Lock + 8);
      if ( v2 == WPP_MAIN_CB.DeviceQueue.Lock + 8 )
        break;
      v3 = *(_DWORD *)(v2 - 40);
      while ( 1 )
      {
        v6 = RDPEVNTLIST_DequeueRequest(Lock);
        v8 = (IRP *)v6;
        if ( !v6 )
          break;
        v4 = _InterlockedExchange64((volatile __int64 *)(v6 + 104), 0);
        KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v0);
        if ( v4 )
        {
          v8->IoStatus.Status = -1073741823;
          IofCompleteRequest(v8, 0);
        }
        v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock);
        Lock = (struct tagSESSIONLIST *)WPP_MAIN_CB.DeviceQueue.Lock;
        v0 = v5;
      }
      while ( (unsigned int)RDPEVNTLIST_DequeueEvent(v7, v3, &v15, &v17, &v16) )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v0);
        if ( v17 )
          operator delete(v17);
        if ( v16 )
          RefCount::Release(v16);
        v0 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock);
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v0);
    v9 = (void *)WPP_MAIN_CB.DeviceQueue.Lock;
    v10 = (_QWORD **)(WPP_MAIN_CB.DeviceQueue.Lock + 8);
    while ( 1 )
    {
      v11 = *v10;
      if ( *v10 == v10 )
        break;
      if ( (_QWORD **)v11[1] != v10 || (v12 = (_QWORD *)*v11, *(_QWORD **)(*v11 + 8LL) != v11) )
        __fastfail(3u);
      *v10 = v12;
      v13 = (struct tagSESSIONLISTNODE *)(v11 - 5);
      v12[1] = v10;
      CleanupSessionListNodeRequestList(v13);
      CleanupSessionListNodeEventList(v13);
      operator delete(v13);
    }
    operator delete(v9);
  }
  RDPDRPRT_Shutdown();
  return 0;
}

```

## disassembly

```asm
0x140002d44  mov     rax, rsp
0x140002d47  mov     [rax+20h], rbx
0x140002d4b  push    rbp
0x140002d4c  push    rsi
0x140002d4d  push    rdi
0x140002d4e  sub     rsp, 30h
0x140002d52  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140002d59  mov     qword ptr [rax+18h], 0
0x140002d61  mov     dword ptr [rax+8], 0
0x140002d68  mov     qword ptr [rax+10h], 0
0x140002d70  test    rcx, rcx
0x140002d73  jz      loc_140002EDE
0x140002d79  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002d80  nop     dword ptr [rax+rax+00h]
0x140002d85  mov     sil, al
0x140002d88  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140002d8f  lea     rdx, [rcx+8]
0x140002d93  mov     rax, [rdx]
0x140002d96  cmp     rax, rdx
0x140002d99  jz      loc_140002E79
0x140002d9f  mov     ebp, [rax-28h]
0x140002da2  jmp     short loc_140002DFA
0x140002da4  xor     ebx, ebx
0x140002da6  mov     dl, sil; NewIrql
0x140002da9  xchg    rbx, [rdi+68h]
0x140002dad  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140002db4  call    cs:__imp_KeReleaseSpinLock
0x140002dbb  nop     dword ptr [rax+rax+00h]
0x140002dc0  test    rbx, rbx
0x140002dc3  jz      short loc_140002DDD
0x140002dc5  xor     edx, edx; PriorityBoost
0x140002dc7  mov     dword ptr [rdi+30h], 0C0000001h
0x140002dce  mov     rcx, rdi; Irp
0x140002dd1  call    cs:__imp_IofCompleteRequest
0x140002dd8  nop     dword ptr [rax+rax+00h]
0x140002ddd  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140002de4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002deb  nop     dword ptr [rax+rax+00h]
0x140002df0  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; struct tagSESSIONLIST *
0x140002df7  mov     sil, al
0x140002dfa  mov     edx, ebp
0x140002dfc  call    RDPEVNTLIST_DequeueRequest
0x140002e01  mov     rdi, rax
0x140002e04  test    rax, rax
0x140002e07  jnz     short loc_140002DA4
0x140002e09  jmp     short loc_140002E55
0x140002e0b  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140002e12  mov     dl, sil; NewIrql
0x140002e15  call    cs:__imp_KeReleaseSpinLock
0x140002e1c  nop     dword ptr [rax+rax+00h]
0x140002e21  mov     rcx, [rsp+48h+arg_10]; void *
0x140002e26  test    rcx, rcx
0x140002e29  jz      short loc_140002E30
0x140002e2b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002e30  mov     rcx, [rsp+48h+arg_8]; this
0x140002e35  test    rcx, rcx
0x140002e38  jz      short loc_140002E3F
0x140002e3a  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140002e3f  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140002e46  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002e4d  nop     dword ptr [rax+rax+00h]
0x140002e52  mov     sil, al
0x140002e55  lea     rax, [rsp+48h+arg_8]
0x140002e5a  mov     edx, ebp
0x140002e5c  lea     r9, [rsp+48h+arg_10]
0x140002e61  mov     [rsp+48h+var_28], rax
0x140002e66  lea     r8, [rsp+48h+arg_0]
0x140002e6b  call    RDPEVNTLIST_DequeueEvent
0x140002e70  test    eax, eax
0x140002e72  jnz     short loc_140002E0B
0x140002e74  jmp     loc_140002D88
0x140002e79  mov     dl, sil; NewIrql
0x140002e7c  call    cs:__imp_KeReleaseSpinLock
0x140002e83  nop     dword ptr [rax+rax+00h]
0x140002e88  mov     rsi, cs:WPP_MAIN_CB.DeviceQueue.Lock
0x140002e8f  lea     rdi, [rsi+8]
0x140002e93  mov     rbx, [rdi]
0x140002e96  cmp     rbx, rdi
0x140002e99  jz      short loc_140002ED6
0x140002e9b  cmp     [rbx+8], rdi
0x140002e9f  jnz     short loc_140002ECF
0x140002ea1  mov     rax, [rbx]
0x140002ea4  cmp     [rax+8], rbx
0x140002ea8  jnz     short loc_140002ECF
0x140002eaa  mov     [rdi], rax
0x140002ead  add     rbx, 0FFFFFFFFFFFFFFD8h
0x140002eb1  mov     rcx, rbx; struct tagSESSIONLISTNODE *
0x140002eb4  mov     [rax+8], rdi
0x140002eb8  call    ?CleanupSessionListNodeRequestList@@YAXPEAUtagSESSIONLISTNODE@@@Z; CleanupSessionListNodeRequestList(tagSESSIONLISTNODE *)
0x140002ebd  mov     rcx, rbx; struct tagSESSIONLISTNODE *
0x140002ec0  call    ?CleanupSessionListNodeEventList@@YAXPEAUtagSESSIONLISTNODE@@@Z; CleanupSessionListNodeEventList(tagSESSIONLISTNODE *)
0x140002ec5  mov     rcx, rbx; void *
0x140002ec8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002ecd  jmp     short loc_140002E93
0x140002ecf  mov     ecx, 3
0x140002ed4  int     29h; Win8: RtlFailFast(ecx)
0x140002ed6  mov     rcx, rsi; void *
0x140002ed9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002ede  call    RDPDRPRT_Shutdown
0x140002ee3  mov     rbx, [rsp+48h+arg_18]
0x140002ee8  xor     eax, eax
0x140002eea  add     rsp, 30h
0x140002eee  pop     rdi
0x140002eef  pop     rsi
0x140002ef0  pop     rbp
0x140002ef1  retn
```
