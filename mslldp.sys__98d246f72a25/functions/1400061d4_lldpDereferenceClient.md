# lldpDereferenceClient

- ea: `0x1400061d4`
- end: `0x140006285`
- name: `lldpDereferenceClient`
- size: `177`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000458c`
- `0x14000613c`
- `0x14000ef10`
- `0x14000efd0`
- `0x14000fca0`

## callees

- `0x1400061d4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006206`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006206`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006256`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006256`
- `NETIO!NmrProviderDetachClientComplete` at `0x14000626d`
- `NETIO!NmrProviderDetachClientComplete` at `0x14000626d`

## pseudocode

```c
void __fastcall lldpDereferenceClient(__int64 a1)
{
  void *v2; // rdi
  PKDPC BufferChainingDpc; // rax
  SINGLE_LIST_ENTRY *p_DpcListEntry; // rcx

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1
    && _InterlockedExchange((volatile __int32 *)(a1 + 20), 0) )
  {
    v2 = *(void **)(a1 + 32);
    LOBYTE(WPP_MAIN_CB.Queue.Wcb.DeviceObject) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters);
    BufferChainingDpc = WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
    if ( WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc == (PKDPC)a1 )
    {
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc = *(PKDPC *)(a1 + 8);
    }
    else
    {
      while ( 1 )
      {
        p_DpcListEntry = &BufferChainingDpc->DpcListEntry;
        BufferChainingDpc = (PKDPC)BufferChainingDpc->DpcListEntry.Next;
        if ( !BufferChainingDpc )
          break;
        if ( BufferChainingDpc == (PKDPC)a1 )
        {
          p_DpcListEntry->Next = *(struct _SINGLE_LIST_ENTRY **)(a1 + 8);
          break;
        }
      }
    }
    KeReleaseSpinLock(
      (PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters,
      (KIRQL)WPP_MAIN_CB.Queue.Wcb.DeviceObject);
    *(_QWORD *)(a1 + 32) = 0;
    NmrProviderDetachClientComplete(v2);
  }
}

```

## disassembly

```asm
0x1400061d4  mov     [rsp+arg_0], rbx
0x1400061d9  push    rdi
0x1400061da  sub     rsp, 20h
0x1400061de  mov     rbx, rcx
0x1400061e1  or      eax, 0FFFFFFFFh
0x1400061e4  lock xadd [rcx+10h], eax
0x1400061e9  cmp     eax, 1
0x1400061ec  jnz     loc_140006279
0x1400061f2  xor     eax, eax
0x1400061f4  xchg    eax, [rcx+14h]
0x1400061f7  test    eax, eax
0x1400061f9  jz      short loc_140006279
0x1400061fb  mov     rdi, [rcx+20h]
0x1400061ff  lea     rcx, WPP_MAIN_CB.Queue+28h; SpinLock
0x140006206  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000620d  nop     dword ptr [rax+rax+00h]
0x140006212  mov     byte ptr cs:WPP_MAIN_CB.Queue+30h, al
0x140006218  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000621f  cmp     rax, rbx
0x140006222  jnz     short loc_140006231
0x140006224  mov     rax, [rbx+8]
0x140006228  mov     qword ptr cs:WPP_MAIN_CB.Queue+40h, rax
0x14000622f  jmp     short loc_140006249
0x140006231  lea     rcx, [rax+8]
0x140006235  mov     rax, [rcx]
0x140006238  test    rax, rax
0x14000623b  jz      short loc_140006249
0x14000623d  cmp     rax, rbx
0x140006240  jnz     short loc_140006231
0x140006242  mov     rax, [rbx+8]
0x140006246  mov     [rcx], rax
0x140006249  mov     dl, byte ptr cs:WPP_MAIN_CB.Queue+30h; NewIrql
0x14000624f  lea     rcx, WPP_MAIN_CB.Queue+28h; SpinLock
0x140006256  call    cs:__imp_KeReleaseSpinLock
0x14000625d  nop     dword ptr [rax+rax+00h]
0x140006262  mov     rcx, rdi; NmrBindingHandle
0x140006265  mov     qword ptr [rbx+20h], 0
0x14000626d  call    cs:__imp_NmrProviderDetachClientComplete
0x140006274  nop     dword ptr [rax+rax+00h]
0x140006279  mov     rbx, [rsp+28h+arg_0]
0x14000627e  add     rsp, 20h
0x140006282  pop     rdi
0x140006283  retn
```
