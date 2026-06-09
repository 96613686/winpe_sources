# SetProtocolEvent

- ea: `0x14002ba10`
- end: `0x14002baa4`
- name: `SetProtocolEvent`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14002ba10`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14002ba8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ba8a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ba27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ba27`

## pseudocode

```c
__int64 __fastcall SetProtocolEvent(KSPIN_LOCK a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  PKSPIN_LOCK v5; // rbx
  KIRQL v7; // al
  PKSPIN_LOCK v8; // rcx
  unsigned int v9; // ebx

  v5 = ProtocolInfoTable;
  v7 = KeAcquireSpinLockRaiseToDpc(ProtocolInfoTable);
  v8 = ProtocolInfoTable;
  *((_BYTE *)v5 + 8) = v7;
  if ( (v8[3] & 0x18) == 8 )
  {
    *((_DWORD *)v8 + 6) |= 0x10u;
    v9 = 0;
  }
  else
  {
    v9 = 0;
    if ( !v8[4] )
    {
      v8[4] = a1;
      v9 = 259;
      *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
      _InterlockedExchange64((volatile __int64 *)(a1 + 104), (__int64)NdisWanCancelRoutine);
      goto LABEL_6;
    }
  }
  *a5 = 0;
LABEL_6:
  KeReleaseSpinLock(ProtocolInfoTable, *((_BYTE *)ProtocolInfoTable + 8));
  return v9;
}

```

## disassembly

```asm
0x14002ba10  mov     [rsp+arg_0], rbx
0x14002ba15  push    rdi
0x14002ba16  sub     rsp, 20h
0x14002ba1a  mov     rbx, cs:ProtocolInfoTable
0x14002ba21  mov     rdi, rcx
0x14002ba24  mov     rcx, rbx; SpinLock
0x14002ba27  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002ba2e  nop     dword ptr [rax+rax+00h]
0x14002ba33  mov     rcx, cs:ProtocolInfoTable
0x14002ba3a  mov     [rbx+8], al
0x14002ba3d  mov     edx, [rcx+18h]
0x14002ba40  mov     eax, edx
0x14002ba42  and     al, 18h
0x14002ba44  cmp     al, 8
0x14002ba46  jnz     short loc_14002BA59
0x14002ba48  or      edx, 10h
0x14002ba4b  mov     [rcx+18h], edx
0x14002ba4e  xor     ebx, ebx
0x14002ba50  mov     rax, [rsp+28h+arg_20]
0x14002ba55  mov     [rax], ebx
0x14002ba57  jmp     short loc_14002BA80
0x14002ba59  xor     ebx, ebx
0x14002ba5b  cmp     [rcx+20h], rbx
0x14002ba5f  jnz     short loc_14002BA50
0x14002ba61  mov     [rcx+20h], rdi
0x14002ba65  mov     ebx, 103h
0x14002ba6a  mov     rax, [rdi+0B8h]
0x14002ba71  or      byte ptr [rax+3], 1
0x14002ba75  lea     rax, NdisWanCancelRoutine
0x14002ba7c  xchg    rax, [rdi+68h]
0x14002ba80  mov     rcx, cs:ProtocolInfoTable; SpinLock
0x14002ba87  mov     dl, [rcx+8]; NewIrql
0x14002ba8a  call    cs:__imp_KeReleaseSpinLock
0x14002ba91  nop     dword ptr [rax+rax+00h]
0x14002ba96  mov     eax, ebx
0x14002ba98  mov     rbx, [rsp+28h+arg_0]
0x14002ba9d  add     rsp, 20h
0x14002baa1  pop     rdi
0x14002baa2  retn
```
