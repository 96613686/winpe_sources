# lldpRxInfoTtlTimer

- ea: `0x1400049a0`
- end: `0x140004a58`
- name: `lldpRxInfoTtlTimer`
- size: `184`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003d80`
- `0x1400049a0`
- `0x140004a90`
- `0x140005dd0`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x140004a25`
- `NDIS!NdisReleaseRWLock` at `0x140004a25`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400049ca`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400049ca`

## pseudocode

```c
void __fastcall lldpRxInfoTtlTimer(
        struct _KDPC *Dpc,
        PVOID DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  char v5; // di
  int v6; // r8d
  __int64 v7; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+48h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v5 = 0;
  NdisAcquireRWLockWrite(*((PNDIS_RW_LOCK_EX *)DeferredContext + 120), &LockState, 1u);
  v7 = *((_QWORD *)DeferredContext + 121);
  if ( v7 )
  {
    if ( (BYTE1(WPP_MAIN_CB.SecurityDescriptor) & 1) != 0 )
      McTemplateK0qqbr1_EtwWriteTransfer(
        v7,
        (unsigned int)RemoteMibExpired,
        v6,
        *((_DWORD *)DeferredContext + 32),
        *(_DWORD *)(v7 + 12),
        v7 + 24);
    lldpDeleteNeighborOnPort(DeferredContext);
    v5 = 1;
  }
  NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)DeferredContext + 120), &LockState);
  if ( v5 )
  {
    lldpQueueChangeNotificationEx(DeferredContext);
    _InterlockedIncrement64((volatile signed __int64 *)DeferredContext + 110);
  }
}

```

## disassembly

```asm
0x1400049a0  mov     [rsp+arg_0], rbx
0x1400049a5  push    rdi
0x1400049a6  sub     rsp, 30h
0x1400049aa  mov     rbx, rdx
0x1400049ad  xor     eax, eax
0x1400049af  mov     r8b, 1; Flags
0x1400049b2  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x1400049b7  lea     rdx, [rsp+38h+LockState]; LockState
0x1400049bc  mov     [rsp+38h+LockState.Flags], al
0x1400049c0  xor     dil, dil
0x1400049c3  mov     rcx, [rbx+3C0h]; Lock
0x1400049ca  call    cs:__imp_NdisAcquireRWLockWrite
0x1400049d1  nop     dword ptr [rax+rax+00h]
0x1400049d6  mov     rcx, [rbx+3C8h]
0x1400049dd  test    rcx, rcx
0x1400049e0  jz      short loc_140004A19
0x1400049e2  test    byte ptr cs:WPP_MAIN_CB.SecurityDescriptor+1, 1
0x1400049e9  jz      short loc_140004A0E
0x1400049eb  mov     r9d, [rbx+80h]
0x1400049f2  lea     rax, [rcx+18h]
0x1400049f6  mov     [rsp+38h+var_10], rax
0x1400049fb  lea     rdx, RemoteMibExpired
0x140004a02  mov     eax, [rcx+0Ch]
0x140004a05  mov     [rsp+38h+var_18], eax
0x140004a09  call    McTemplateK0qqbr1_EtwWriteTransfer
0x140004a0e  mov     rcx, rbx
0x140004a11  call    lldpDeleteNeighborOnPort
0x140004a16  mov     dil, 1
0x140004a19  mov     rcx, [rbx+3C0h]; Lock
0x140004a20  lea     rdx, [rsp+38h+LockState]; LockState
0x140004a25  call    cs:__imp_NdisReleaseRWLock
0x140004a2c  nop     dword ptr [rax+rax+00h]
0x140004a31  test    dil, dil
0x140004a34  jz      short loc_140004A4C
0x140004a36  xor     edx, edx
0x140004a38  mov     rcx, rbx; Context
0x140004a3b  lea     r8d, [rdx+20h]
0x140004a3f  call    lldpQueueChangeNotificationEx
0x140004a44  lock inc qword ptr [rbx+370h]
0x140004a4c  mov     rbx, [rsp+38h+arg_0]
0x140004a51  add     rsp, 30h
0x140004a55  pop     rdi
0x140004a56  retn
```
