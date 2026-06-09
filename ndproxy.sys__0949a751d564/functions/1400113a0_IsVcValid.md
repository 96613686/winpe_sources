# IsVcValid

- ea: `0x1400113a0`
- end: `0x14001146c`
- name: `IsVcValid`
- size: `204`
- prototype: `bool __fastcall(unsigned __int64, _QWORD *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140004760`
- `0x140011660`
- `0x140011ab0`
- `0x140012040`
- `0x140012210`
- `0x140012a00`
- `0x140012b20`
- `0x140012f00`
- `0x140013770`
- `0x140014310`
- `0x140014b20`
- `0x1400150f0`

## callees

- `0x1400113a0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001141e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001142c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001141e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001142c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140011405`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140011405`
- `NDIS!NdisReleaseRWLock` at `0x140011446`
- `NDIS!NdisReleaseRWLock` at `0x140011446`
- `NDIS!NdisAcquireRWLockRead` at `0x1400113d1`
- `NDIS!NdisAcquireRWLockRead` at `0x1400113d1`

## pseudocode

```c
bool __fastcall IsVcValid(unsigned __int64 a1, _QWORD *a2)
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
  return v4 != 0;
}

```

## disassembly

```asm
0x1400113a0  mov     [rsp+arg_8], rbx
0x1400113a5  mov     [rsp+arg_10], rsi
0x1400113aa  push    rdi
0x1400113ab  sub     rsp, 20h
0x1400113af  xor     eax, eax
0x1400113b1  mov     rsi, rdx
0x1400113b4  mov     rdi, rcx
0x1400113b7  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x1400113bc  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x1400113c3  lea     rdx, [rsp+28h+LockState]; LockState
0x1400113c8  xor     r8d, r8d; Flags
0x1400113cb  mov     [rsp+28h+LockState.Flags], al
0x1400113cf  xor     ebx, ebx
0x1400113d1  call    cs:__imp_NdisAcquireRWLockRead
0x1400113d8  nop     dword ptr [rax+rax+00h]
0x1400113dd  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+34h
0x1400113e3  cmp     rdi, rax
0x1400113e6  jnb     short loc_14001143A
0x1400113e8  lfence
0x1400113eb  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x1400113f2  mov     rbx, [rax+rdi*8]
0x1400113f6  test    rbx, rbx
0x1400113f9  jz      short loc_14001143A
0x1400113fb  lea     rdi, [rbx+200h]
0x140011402  mov     rcx, rdi; SpinLock
0x140011405  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001140c  nop     dword ptr [rax+rax+00h]
0x140011411  mov     eax, [rbx+20h]
0x140011414  mov     rcx, rdi; SpinLock
0x140011417  test    al, 2
0x140011419  jz      short loc_14001142C
0x14001141b  inc     dword ptr [rbx+1Ch]
0x14001141e  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140011425  nop     dword ptr [rax+rax+00h]
0x14001142a  jmp     short loc_14001143A
0x14001142c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140011433  nop     dword ptr [rax+rax+00h]
0x140011438  xor     ebx, ebx
0x14001143a  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x140011441  lea     rdx, [rsp+28h+LockState]; LockState
0x140011446  call    cs:__imp_NdisReleaseRWLock
0x14001144d  nop     dword ptr [rax+rax+00h]
0x140011452  test    rbx, rbx
0x140011455  mov     [rsi], rbx
0x140011458  mov     rbx, [rsp+28h+arg_8]
0x14001145d  mov     rsi, [rsp+28h+arg_10]
0x140011462  setnz   al
0x140011465  add     rsp, 20h
0x140011469  pop     rdi
0x14001146a  retn
```
