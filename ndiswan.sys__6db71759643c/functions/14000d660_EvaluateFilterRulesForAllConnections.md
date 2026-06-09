# EvaluateFilterRulesForAllConnections

- ea: `0x14000d660`
- end: `0x14000d760`
- name: `EvaluateFilterRulesForAllConnections`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d770`

## callees

- `0x14000d4e8`
- `0x14000d660`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000d70c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d70c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d6c5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d6c5`
- `NDIS!NdisReleaseRWLock` at `0x14000d740`
- `NDIS!NdisReleaseRWLock` at `0x14000d740`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000d68c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000d68c`

## pseudocode

```c
void EvaluateFilterRulesForAllConnections()
{
  __int64 v0; // rbx
  __int64 v1; // rsi
  int v2; // ebp
  __int64 v3; // rcx
  unsigned int v4; // edx
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(ConnTableLock, &LockState, 0);
  v0 = *((unsigned int *)ConnectionTable + 5);
  v1 = *((_QWORD *)ConnectionTable + 8);
  v2 = *((_DWORD *)ConnectionTable + 1);
  if ( !(_DWORD)v0 )
    v0 = 1;
  do
  {
    v3 = *(_QWORD *)(v1 + 8 * v0);
    if ( v3 )
    {
      *(_BYTE *)(*(_QWORD *)(v1 + 8 * v0) + 1776LL) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 1768));
      *(_BYTE *)(*(_QWORD *)(v1 + 8 * v0) + 2436LL) = EvaluateFilterRule(
                                                        *(_DWORD *)(*(_QWORD *)(v1 + 8 * v0) + 2440LL),
                                                        (const wchar_t *)(*(_QWORD *)(v1 + 8 * v0) + 1792LL));
      KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v1 + 8 * v0) + 1768LL), *(_BYTE *)(*(_QWORD *)(v1 + 8 * v0) + 1776LL));
    }
    v4 = (unsigned int)(v0 + 1) % *((_DWORD *)ConnectionTable + 1);
    v0 = v4;
    if ( !v4 )
      v0 = 1;
    --v2;
  }
  while ( v2 );
  NdisReleaseRWLock(ConnTableLock, &LockState);
}

```

## disassembly

```asm
0x14000d660  mov     [rsp+arg_8], rbx
0x14000d665  mov     [rsp+arg_10], rbp
0x14000d66a  push    rsi
0x14000d66b  push    rdi
0x14000d66c  push    r14
0x14000d66e  sub     rsp, 20h
0x14000d672  mov     rcx, cs:ConnTableLock; Lock
0x14000d679  lea     rdx, [rsp+38h+LockState]; LockState
0x14000d67e  xor     eax, eax
0x14000d680  xor     r8d, r8d; Flags
0x14000d683  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x14000d688  mov     [rsp+38h+LockState.Flags], al
0x14000d68c  call    cs:__imp_NdisAcquireRWLockWrite
0x14000d693  nop     dword ptr [rax+rax+00h]
0x14000d698  mov     rcx, cs:ConnectionTable
0x14000d69f  mov     r14d, 1
0x14000d6a5  mov     ebx, [rcx+14h]
0x14000d6a8  test    ebx, ebx
0x14000d6aa  mov     rsi, [rcx+40h]
0x14000d6ae  mov     ebp, [rcx+4]
0x14000d6b1  cmovz   ebx, r14d
0x14000d6b5  mov     rcx, [rsi+rbx*8]
0x14000d6b9  test    rcx, rcx
0x14000d6bc  jz      short loc_14000D718
0x14000d6be  add     rcx, 6E8h; SpinLock
0x14000d6c5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d6cc  nop     dword ptr [rax+rax+00h]
0x14000d6d1  mov     rcx, [rsi+rbx*8]
0x14000d6d5  mov     [rcx+6F0h], al
0x14000d6db  mov     rcx, [rsi+rbx*8]
0x14000d6df  lea     rdx, [rcx+700h]
0x14000d6e6  mov     ecx, [rcx+988h]
0x14000d6ec  call    EvaluateFilterRule
0x14000d6f1  mov     rcx, [rsi+rbx*8]
0x14000d6f5  mov     [rcx+984h], al
0x14000d6fb  mov     rdx, [rsi+rbx*8]
0x14000d6ff  lea     rcx, [rdx+6E8h]; SpinLock
0x14000d706  mov     dl, [rdx+6F0h]; NewIrql
0x14000d70c  call    cs:__imp_KeReleaseSpinLock
0x14000d713  nop     dword ptr [rax+rax+00h]
0x14000d718  mov     rcx, cs:ConnectionTable
0x14000d71f  lea     eax, [rbx+1]
0x14000d722  xor     edx, edx
0x14000d724  div     dword ptr [rcx+4]
0x14000d727  test    edx, edx
0x14000d729  mov     ebx, edx
0x14000d72b  cmovz   ebx, r14d
0x14000d72f  add     ebp, 0FFFFFFFFh
0x14000d732  jnz     short loc_14000D6B5
0x14000d734  mov     rcx, cs:ConnTableLock; Lock
0x14000d73b  lea     rdx, [rsp+38h+LockState]; LockState
0x14000d740  call    cs:__imp_NdisReleaseRWLock
0x14000d747  nop     dword ptr [rax+rax+00h]
0x14000d74c  mov     rbx, [rsp+38h+arg_8]
0x14000d751  mov     rbp, [rsp+38h+arg_10]
0x14000d756  add     rsp, 20h
0x14000d75a  pop     r14
0x14000d75c  pop     rdi
0x14000d75d  pop     rsi
0x14000d75e  retn
```
