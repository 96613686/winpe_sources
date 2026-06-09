# GetVcFromCtx

- ea: `0x140006e08`
- end: `0x140006ece`
- name: `GetVcFromCtx`
- size: `198`
- prototype: `void __fastcall(unsigned __int64, _QWORD *)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140001680`
- `0x1400019d0`
- `0x140003860`
- `0x14000f020`
- `0x14000f250`
- `0x14000f630`
- `0x14000f830`
- `0x14000fbb0`
- `0x14000fcb0`
- `0x140010240`
- `0x1400103c0`

## callees

- `0x140006e08`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140006e86`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140006e94`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140006e86`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140006e94`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140006e6d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140006e6d`
- `NDIS!NdisReleaseRWLock` at `0x140006eae`
- `NDIS!NdisReleaseRWLock` at `0x140006eae`
- `NDIS!NdisAcquireRWLockRead` at `0x140006e39`
- `NDIS!NdisAcquireRWLockRead` at `0x140006e39`

## pseudocode

```c
void __fastcall GetVcFromCtx(unsigned __int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  KSPIN_LOCK *v5; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v4 = 0;
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, &LockState, 0);
  if ( a1 < HIDWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) )
  {
    _mm_lfence();
    v4 = *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type + 8 * a1);
    if ( v4 )
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v4 + 512));
      v5 = (KSPIN_LOCK *)(v4 + 512);
      if ( (*(_DWORD *)(v4 + 32) & 2) != 0 )
      {
        ++*(_DWORD *)(v4 + 28);
        KeReleaseSpinLockFromDpcLevel(v5);
      }
      else
      {
        KeReleaseSpinLockFromDpcLevel(v5);
        v4 = 0;
      }
    }
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, &LockState);
  *a2 = v4;
}

```

## disassembly

```asm
0x140006e08  mov     [rsp+arg_8], rbx
0x140006e0d  mov     [rsp+arg_10], rsi
0x140006e12  push    rdi
0x140006e13  sub     rsp, 20h
0x140006e17  xor     eax, eax
0x140006e19  mov     rsi, rdx
0x140006e1c  mov     rdi, rcx
0x140006e1f  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x140006e24  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x140006e2b  lea     rdx, [rsp+28h+LockState]; LockState
0x140006e30  xor     r8d, r8d; Flags
0x140006e33  mov     [rsp+28h+LockState.Flags], al
0x140006e37  xor     ebx, ebx
0x140006e39  call    cs:__imp_NdisAcquireRWLockRead
0x140006e40  nop     dword ptr [rax+rax+00h]
0x140006e45  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+34h
0x140006e4b  cmp     rdi, rax
0x140006e4e  jnb     short loc_140006EA2
0x140006e50  lfence
0x140006e53  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x140006e5a  mov     rbx, [rax+rdi*8]
0x140006e5e  test    rbx, rbx
0x140006e61  jz      short loc_140006EA2
0x140006e63  lea     rdi, [rbx+200h]
0x140006e6a  mov     rcx, rdi; SpinLock
0x140006e6d  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140006e74  nop     dword ptr [rax+rax+00h]
0x140006e79  mov     eax, [rbx+20h]
0x140006e7c  mov     rcx, rdi; SpinLock
0x140006e7f  test    al, 2
0x140006e81  jz      short loc_140006E94
0x140006e83  inc     dword ptr [rbx+1Ch]
0x140006e86  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140006e8d  nop     dword ptr [rax+rax+00h]
0x140006e92  jmp     short loc_140006EA2
0x140006e94  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140006e9b  nop     dword ptr [rax+rax+00h]
0x140006ea0  xor     ebx, ebx
0x140006ea2  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x140006ea9  lea     rdx, [rsp+28h+LockState]; LockState
0x140006eae  call    cs:__imp_NdisReleaseRWLock
0x140006eb5  nop     dword ptr [rax+rax+00h]
0x140006eba  mov     [rsi], rbx
0x140006ebd  mov     rbx, [rsp+28h+arg_8]
0x140006ec2  mov     rsi, [rsp+28h+arg_10]
0x140006ec7  add     rsp, 20h
0x140006ecb  pop     rdi
0x140006ecc  retn
```
