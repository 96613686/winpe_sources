# PxCancelSetQuery

- ea: `0x140010c30`
- end: `0x140010e03`
- name: `PxCancelSetQuery`
- size: `467`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001bc8`
- `0x140010c30`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010ccf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010ccf`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140010c8b`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140010c8b`
- `ntoskrnl!IofCompleteRequest` at `0x140010dae`
- `ntoskrnl!IofCompleteRequest` at `0x140010dae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d5a`
- `NDIS!NdisReleaseRWLock` at `0x140010d83`
- `NDIS!NdisReleaseRWLock` at `0x140010d83`
- `NDIS!NdisAcquireRWLockRead` at `0x140010ca6`
- `NDIS!NdisAcquireRWLockRead` at `0x140010ca6`

## pseudocode

```c
void __fastcall PxCancelSetQuery(__int64 a1, __int64 a2)
{
  char v2; // si
  PVOID v3; // rdi
  PKDPC i; // rbx
  KIRQL v6; // al
  PVOID *p_DeferredContext; // r8
  PVOID *DeferredContext; // rax
  PVOID *v9; // rcx
  PVOID **v10; // rdx
  _QWORD *SystemArgument2; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  v3 = 0;
  LockState.Flags = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids, a2);
  IoReleaseCancelSpinLock(*(_BYTE *)(a2 + 69));
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, &LockState, 0);
  for ( i = WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
        i != (PKDPC)&WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
        i = *(PKDPC *)&i->TargetInfoAsUlong )
  {
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&i[8].TargetInfoAsUlong);
    p_DeferredContext = &i[1].DeferredContext;
    LOBYTE(i[8].DpcListEntry.Next) = v6;
    DeferredContext = (PVOID *)i[1].DeferredContext;
    if ( DeferredContext != &i[1].DeferredContext )
    {
      while ( 1 )
      {
        v3 = DeferredContext[2];
        v9 = (PVOID *)*DeferredContext;
        if ( *((_BYTE *)v3 + 68) )
          break;
        DeferredContext = (PVOID *)*DeferredContext;
        if ( v9 == p_DeferredContext )
          goto LABEL_12;
      }
      if ( v9[1] != DeferredContext || (v10 = (PVOID **)DeferredContext[1], *v10 != DeferredContext) )
        __fastfail(3u);
      *v10 = v9;
      v2 = 1;
      v9[1] = v10;
    }
LABEL_12:
    if ( *p_DeferredContext == p_DeferredContext )
      LODWORD(i->DeferredContext) &= ~0x10u;
    if ( !v2 )
    {
      SystemArgument2 = i[1].SystemArgument2;
      if ( SystemArgument2 )
      {
        v3 = (PVOID)SystemArgument2[2];
        if ( *((_BYTE *)v3 + 68) )
        {
          v2 = 1;
          i[1].SystemArgument2 = 0;
        }
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)&i[8].TargetInfoAsUlong, (KIRQL)i[8].DpcListEntry.Next);
    if ( v2 )
      break;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, &LockState);
  if ( v2 )
  {
    _InterlockedExchange64((volatile __int64 *)v3 + 13, 0);
    *((_DWORD *)v3 + 12) = -1073741536;
    *((_QWORD *)v3 + 7) = 0;
    IofCompleteRequest((PIRP)v3, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids, a2);
}

```

## disassembly

```asm
0x140010c30  mov     [rsp+arg_0], rbx
0x140010c35  mov     [rsp+arg_10], rbp
0x140010c3a  push    rsi
0x140010c3b  push    rdi
0x140010c3c  push    r12
0x140010c3e  push    r13
0x140010c40  push    r14
0x140010c42  sub     rsp, 20h
0x140010c46  xor     eax, eax
0x140010c48  xor     sil, sil
0x140010c4b  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x140010c50  xor     edi, edi
0x140010c52  mov     [rsp+48h+LockState.Flags], al
0x140010c56  mov     rbp, rdx
0x140010c59  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c60  lea     r12, WPP_GLOBAL_Control
0x140010c67  cmp     rcx, r12
0x140010c6a  jz      short loc_140010C88
0x140010c6c  cmp     byte ptr [rcx+29h], 5
0x140010c70  jb      short loc_140010C88
0x140010c72  mov     rcx, [rcx+18h]
0x140010c76  lea     edx, [rax+2Bh]
0x140010c79  mov     r9, rbp
0x140010c7c  lea     r8, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids
0x140010c83  call    WPP_SF_q
0x140010c88  mov     cl, [rbp+45h]; Irql
0x140010c8b  call    cs:__imp_IoReleaseCancelSpinLock
0x140010c92  nop     dword ptr [rax+rax+00h]
0x140010c97  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x140010c9e  lea     rdx, [rsp+48h+LockState]; LockState
0x140010ca3  xor     r8d, r8d; Flags
0x140010ca6  call    cs:__imp_NdisAcquireRWLockRead
0x140010cad  nop     dword ptr [rax+rax+00h]
0x140010cb2  mov     rbx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140010cb9  lea     r13, WPP_MAIN_CB.Queue+40h
0x140010cc0  jmp     loc_140010D6E
0x140010cc5  lea     r14, [rbx+200h]
0x140010ccc  mov     rcx, r14; SpinLock
0x140010ccf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010cd6  nop     dword ptr [rax+rax+00h]
0x140010cdb  lea     r8, [rbx+60h]
0x140010cdf  mov     [rbx+208h], al
0x140010ce5  mov     rax, [r8]
0x140010ce8  cmp     rax, r8
0x140010ceb  jz      short loc_140010D25
0x140010ced  mov     rdi, [rax+10h]
0x140010cf1  mov     rcx, [rax]
0x140010cf4  cmp     byte ptr [rdi+44h], 0
0x140010cf8  jnz     short loc_140010D04
0x140010cfa  mov     rax, rcx
0x140010cfd  cmp     rcx, r8
0x140010d00  jnz     short loc_140010CED
0x140010d02  jmp     short loc_140010D25
0x140010d04  cmp     [rcx+8], rax
0x140010d08  jnz     loc_140010DFC
0x140010d0e  mov     rdx, [rax+8]
0x140010d12  cmp     [rdx], rax
0x140010d15  jnz     loc_140010DFC
0x140010d1b  mov     [rdx], rcx
0x140010d1e  mov     sil, 1
0x140010d21  mov     [rcx+8], rdx
0x140010d25  cmp     [r8], r8
0x140010d28  jnz     short loc_140010D2E
0x140010d2a  and     dword ptr [rbx+20h], 0FFFFFFEFh
0x140010d2e  test    sil, sil
0x140010d31  jnz     short loc_140010D51
0x140010d33  mov     rax, [rbx+70h]
0x140010d37  test    rax, rax
0x140010d3a  jz      short loc_140010D51
0x140010d3c  mov     rdi, [rax+10h]
0x140010d40  cmp     [rdi+44h], sil
0x140010d44  jz      short loc_140010D51
0x140010d46  mov     sil, 1
0x140010d49  mov     qword ptr [rbx+70h], 0
0x140010d51  mov     dl, [rbx+208h]; NewIrql
0x140010d57  mov     rcx, r14; SpinLock
0x140010d5a  call    cs:__imp_KeReleaseSpinLock
0x140010d61  nop     dword ptr [rax+rax+00h]
0x140010d66  test    sil, sil
0x140010d69  jnz     short loc_140010D77
0x140010d6b  mov     rbx, [rbx]
0x140010d6e  cmp     rbx, r13
0x140010d71  jnz     loc_140010CC5
0x140010d77  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; Lock
0x140010d7e  lea     rdx, [rsp+48h+LockState]; LockState
0x140010d83  call    cs:__imp_NdisReleaseRWLock
0x140010d8a  nop     dword ptr [rax+rax+00h]
0x140010d8f  test    sil, sil
0x140010d92  jz      short loc_140010DBA
0x140010d94  xor     eax, eax
0x140010d96  xor     edx, edx; PriorityBoost
0x140010d98  xchg    rax, [rdi+68h]
0x140010d9c  mov     rcx, rdi; Irp
0x140010d9f  mov     dword ptr [rdi+30h], 0C0000120h
0x140010da6  mov     qword ptr [rdi+38h], 0
0x140010dae  call    cs:__imp_IofCompleteRequest
0x140010db5  nop     dword ptr [rax+rax+00h]
0x140010dba  mov     rcx, cs:WPP_GLOBAL_Control
0x140010dc1  cmp     rcx, r12
0x140010dc4  jz      short loc_140010DE4
0x140010dc6  cmp     byte ptr [rcx+29h], 4
0x140010dca  jb      short loc_140010DE4
0x140010dcc  mov     rcx, [rcx+18h]
0x140010dd0  lea     r8, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids
0x140010dd7  mov     edx, 2Ch ; ','
0x140010ddc  mov     r9, rbp
0x140010ddf  call    WPP_SF_q
0x140010de4  mov     rbx, [rsp+48h+arg_0]
0x140010de9  mov     rbp, [rsp+48h+arg_10]
0x140010dee  add     rsp, 20h
0x140010df2  pop     r14
0x140010df4  pop     r13
0x140010df6  pop     r12
0x140010df8  pop     rdi
0x140010df9  pop     rsi
0x140010dfa  retn
0x140010dfc  mov     ecx, 3
0x140010e01  int     29h; Win8: RtlFailFast(ecx)
```
