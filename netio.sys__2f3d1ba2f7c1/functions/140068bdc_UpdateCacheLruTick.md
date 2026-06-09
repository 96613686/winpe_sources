# UpdateCacheLruTick

- ea: `0x140068bdc`
- end: `0x140068cec`
- name: `UpdateCacheLruTick`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14004f7b0`

## callees

- `0x140009c50`
- `0x140068bdc`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140068c3d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140068c3d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140068cb0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140068cb0`
- `NDIS!NdisReleaseRWLock` at `0x140068cd6`
- `NDIS!NdisReleaseRWLock` at `0x140068cd6`
- `NDIS!NdisAcquireRWLockWrite` at `0x140068c24`
- `NDIS!NdisAcquireRWLockWrite` at `0x140068c24`

## pseudocode

```c
void __fastcall UpdateCacheLruTick(__int64 a1, _QWORD *a2, int a3, int a4)
{
  _DWORD *v8; // rax
  _QWORD *v9; // rdx
  _QWORD *v10; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+18h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !a3 )
    NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState, 1u);
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(*(_QWORD *)(a1 + 24) + 8LL), &LockHandle);
  ++**(_DWORD **)(a1 + 24);
  v8 = *(_DWORD **)(a1 + 24);
  if ( *v8 == 10 )
  {
    *v8 = 0;
    WfpRestructureHashtable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8));
  }
  if ( *(_DWORD *)(a1 + 4) > **(_DWORD **)(a1 + 16) || a4 )
  {
    v9 = (_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * (**(unsigned int **)(a1 + 24) + 1LL));
    v10 = (_QWORD *)*v9;
    if ( (_QWORD *)*v9 != v9 )
    {
      *a2 = v10;
      a2[1] = v9[1];
      v10[1] = a2;
      *(_QWORD *)a2[1] = a2;
      v9[1] = v9;
      *v9 = v9;
    }
  }
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  if ( !a3 )
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState);
}

```

## disassembly

```asm
0x140068bdc  mov     r11, rsp
0x140068bdf  push    rbx
0x140068be0  push    rbp
0x140068be1  push    rsi
0x140068be2  push    rdi
0x140068be3  sub     rsp, 48h
0x140068be7  xor     eax, eax
0x140068be9  xorps   xmm0, xmm0
0x140068bec  mov     [r11+18h], ax
0x140068bf1  mov     ebp, r9d
0x140068bf4  mov     [r11+1Ah], al
0x140068bf8  mov     esi, r8d
0x140068bfb  mov     rdi, rdx
0x140068bfe  mov     rbx, rcx
0x140068c01  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x140068c06  mov     [r11-38h], rax
0x140068c0a  test    r8d, r8d
0x140068c0d  jnz     short loc_140068C30
0x140068c0f  mov     rcx, cs:gWfpGlobal
0x140068c16  lea     rdx, [r11+18h]; LockState
0x140068c1a  mov     r8b, 1; Flags
0x140068c1d  mov     rcx, [rcx+6C0h]; Lock
0x140068c24  call    cs:__imp_NdisAcquireRWLockWrite
0x140068c2b  nop     dword ptr [rax+rax+00h]
0x140068c30  mov     rcx, [rbx+18h]
0x140068c34  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x140068c39  add     rcx, 8; SpinLock
0x140068c3d  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140068c44  nop     dword ptr [rax+rax+00h]
0x140068c49  mov     rax, [rbx+18h]
0x140068c4d  inc     dword ptr [rax]
0x140068c4f  mov     rax, [rbx+18h]
0x140068c53  cmp     dword ptr [rax], 0Ah
0x140068c56  jnz     short loc_140068C67
0x140068c58  mov     dword ptr [rax], 0
0x140068c5e  mov     rcx, [rbx+8]; HashTable
0x140068c62  call    WfpRestructureHashtable
0x140068c67  mov     ecx, [rbx+4]
0x140068c6a  mov     rax, [rbx+10h]
0x140068c6e  cmp     ecx, [rax]
0x140068c70  jg      short loc_140068C76
0x140068c72  test    ebp, ebp
0x140068c74  jz      short loc_140068CAB
0x140068c76  mov     rcx, [rbx+18h]
0x140068c7a  mov     edx, [rcx]
0x140068c7c  inc     rdx
0x140068c7f  shl     rdx, 4
0x140068c83  add     rdx, rcx
0x140068c86  mov     rcx, [rdx]
0x140068c89  cmp     rcx, rdx
0x140068c8c  jz      short loc_140068CAB
0x140068c8e  mov     [rdi], rcx
0x140068c91  mov     rax, [rdx+8]
0x140068c95  mov     [rdi+8], rax
0x140068c99  mov     [rcx+8], rdi
0x140068c9d  mov     rax, [rdi+8]
0x140068ca1  mov     [rax], rdi
0x140068ca4  mov     [rdx+8], rdx
0x140068ca8  mov     [rdx], rdx
0x140068cab  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140068cb0  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140068cb7  nop     dword ptr [rax+rax+00h]
0x140068cbc  test    esi, esi
0x140068cbe  jnz     short loc_140068CE2
0x140068cc0  mov     rcx, cs:gWfpGlobal
0x140068cc7  lea     rdx, [rsp+68h+LockState]; LockState
0x140068ccf  mov     rcx, [rcx+6C0h]; Lock
0x140068cd6  call    cs:__imp_NdisReleaseRWLock
0x140068cdd  nop     dword ptr [rax+rax+00h]
0x140068ce2  add     rsp, 48h
0x140068ce6  pop     rdi
0x140068ce7  pop     rsi
0x140068ce8  pop     rbp
0x140068ce9  pop     rbx
0x140068cea  retn
```
