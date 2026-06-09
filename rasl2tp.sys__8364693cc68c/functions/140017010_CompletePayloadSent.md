# CompletePayloadSent

- ea: `0x140017010`
- end: `0x14001717f`
- name: `CompletePayloadSent`
- size: `367`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400013f0`
- `0x140003080`
- `0x140017010`
- `0x14001ac30`
- `0x14001b830`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001712e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001712e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017036`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017145`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001715b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017036`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017145`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001715b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400170eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400170eb`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001708c`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001708c`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400170be`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400170be`

## pseudocode

```c
void __fastcall CompletePayloadSent(PVOID Entry, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 v4; // rsi
  __int64 v5; // rbx
  __int64 v7; // rdx
  _QWORD *v8; // rax
  __int64 v9; // r8
  _QWORD *v10; // rdx

  v4 = *(_QWORD *)(a2 + 24);
  v5 = *a4;
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v4 + 960), Entry);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      36,
      WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids,
      *(unsigned __int16 *)(v5 + 36));
  }
  NdisAdvanceNetBufferDataStart(*(PNET_BUFFER *)(v5 + 48), *(_DWORD *)(*(_QWORD *)(v5 + 48) + 136LL), 1u, 0);
  v7 = *(_QWORD *)(*(_QWORD *)(v5 + 48) + 128LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 112), 0xFFFFFFFF) == 1 )
  {
    NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(*(_QWORD *)(v5 + 64) + 304LL), (PNET_BUFFER_LIST)v7, 0);
    DereferenceCall(a3);
  }
  DereferenceTunnel(*(_QWORD *)(v5 + 56));
  DereferenceVc(*(_QWORD *)(v5 + 64));
  NewIrql = KeAcquireSpinLockRaiseToDpc(&g_lockDebugPs);
  v8 = (_QWORD *)(v5 + 16);
  v9 = *(_QWORD *)(v5 + 16);
  if ( *(_QWORD *)(v9 + 8) != v5 + 16 || (v10 = *(_QWORD **)(v5 + 24), (_QWORD *)*v10 != v8) )
    __fastfail(3u);
  *v10 = v9;
  *(_QWORD *)(v9 + 8) = v10;
  *(_QWORD *)(v5 + 24) = v5 + 16;
  *v8 = v8;
  KeReleaseSpinLock(&g_lockDebugPs, NewIrql);
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v4 + 576), *(PVOID *)(v5 + 40));
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v4 + 832), (PVOID)v5);
}

```

## disassembly

```asm
0x140017010  mov     [rsp+arg_0], rbx
0x140017015  mov     [rsp+arg_8], rsi
0x14001701a  push    rdi
0x14001701b  sub     rsp, 20h
0x14001701f  mov     rsi, [rdx+18h]
0x140017023  mov     rax, rcx
0x140017026  mov     rbx, [r9]
0x140017029  mov     rdx, rax; Entry
0x14001702c  mov     rdi, r8
0x14001702f  lea     rcx, [rsi+3C0h]; Lookaside
0x140017036  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001703d  nop     dword ptr [rax+rax+00h]
0x140017042  mov     rcx, cs:WPP_GLOBAL_Control
0x140017049  lea     rax, WPP_GLOBAL_Control
0x140017050  cmp     rcx, rax
0x140017053  jz      short loc_14001707C
0x140017055  mov     eax, [rcx+2Ch]
0x140017058  test    al, 10h
0x14001705a  jz      short loc_14001707C
0x14001705c  cmp     byte ptr [rcx+29h], 4
0x140017060  jb      short loc_14001707C
0x140017062  movzx   r9d, word ptr [rbx+24h]
0x140017067  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x14001706e  mov     rcx, [rcx+18h]
0x140017072  mov     edx, 24h ; '$'
0x140017077  call    WPP_SF_d
0x14001707c  mov     rcx, [rbx+30h]; NetBuffer
0x140017080  xor     r9d, r9d; FreeMdlHandler
0x140017083  mov     r8b, 1; FreeMdl
0x140017086  mov     edx, [rcx+88h]; DataOffsetDelta
0x14001708c  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140017093  nop     dword ptr [rax+rax+00h]
0x140017098  mov     rax, [rbx+30h]
0x14001709c  mov     rdx, [rax+80h]; NetBufferLists
0x1400170a3  or      eax, 0FFFFFFFFh
0x1400170a6  lock xadd [rdx+70h], eax
0x1400170ab  cmp     eax, 1
0x1400170ae  jnz     short loc_1400170D2
0x1400170b0  mov     rcx, [rbx+40h]
0x1400170b4  xor     r8d, r8d; SendCompleteFlags
0x1400170b7  mov     rcx, [rcx+130h]; NdisVcHandle
0x1400170be  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x1400170c5  nop     dword ptr [rax+rax+00h]
0x1400170ca  mov     rcx, rdi
0x1400170cd  call    DereferenceCall
0x1400170d2  mov     rcx, [rbx+38h]
0x1400170d6  call    DereferenceTunnel
0x1400170db  mov     rcx, [rbx+40h]
0x1400170df  call    DereferenceVc
0x1400170e4  lea     rcx, g_lockDebugPs; SpinLock
0x1400170eb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400170f2  nop     dword ptr [rax+rax+00h]
0x1400170f7  mov     cs:NewIrql, al
0x1400170fd  lea     rax, [rbx+10h]
0x140017101  mov     r8, [rax]
0x140017104  cmp     [r8+8], rax
0x140017108  jnz     short loc_140017178
0x14001710a  mov     rdx, [rax+8]
0x14001710e  cmp     [rdx], rax
0x140017111  jnz     short loc_140017178
0x140017113  mov     [rdx], r8
0x140017116  lea     rcx, g_lockDebugPs; SpinLock
0x14001711d  mov     [r8+8], rdx
0x140017121  mov     [rax+8], rax
0x140017125  mov     [rax], rax
0x140017128  mov     dl, cs:NewIrql; NewIrql
0x14001712e  call    cs:__imp_KeReleaseSpinLock
0x140017135  nop     dword ptr [rax+rax+00h]
0x14001713a  mov     rdx, [rbx+28h]; Entry
0x14001713e  lea     rcx, [rsi+240h]; Lookaside
0x140017145  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001714c  nop     dword ptr [rax+rax+00h]
0x140017151  lea     rcx, [rsi+340h]; Lookaside
0x140017158  mov     rdx, rbx; Entry
0x14001715b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140017162  nop     dword ptr [rax+rax+00h]
0x140017167  mov     rbx, [rsp+28h+arg_0]
0x14001716c  mov     rsi, [rsp+28h+arg_8]
0x140017171  add     rsp, 20h
0x140017175  pop     rdi
0x140017176  retn
0x140017178  mov     ecx, 3
0x14001717d  int     29h; Win8: RtlFailFast(ecx)
```
