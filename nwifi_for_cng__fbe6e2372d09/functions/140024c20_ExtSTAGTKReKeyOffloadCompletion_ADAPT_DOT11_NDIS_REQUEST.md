# ExtSTAGTKReKeyOffloadCompletion(_ADAPT *,DOT11_NDIS_REQUEST *)

- ea: `0x140024c20`
- end: `0x140024d45`
- name: `?ExtSTAGTKReKeyOffloadCompletion@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z`
- size: `293`
- prototype: `void(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140020dc0`
- `0x140024c20`
- `0x140024ddc`
- `0x14006a744`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024d17`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024d17`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024d28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024d28`
- `NDIS!NdisAcquireRWLockWrite` at `0x140024c9d`
- `NDIS!NdisAcquireRWLockWrite` at `0x140024c9d`
- `NDIS!NdisReleaseRWLock` at `0x140024cc7`
- `NDIS!NdisReleaseRWLock` at `0x140024cc7`

## pseudocode

```c
void __fastcall ExtSTAGTKReKeyOffloadCompletion(struct _ADAPT *a1, struct DOT11_NDIS_REQUEST *a2)
{
  __int64 ndisStatus; // r9
  struct _NDIS_PM_PROTOCOL_OFFLOAD *InformationBuffer; // rsi
  struct EXTSTA_VELAN *pvContext1; // rdi
  struct _LOCK_STATE_EX LockState; // [rsp+38h] [rbp+10h] BYREF

  ndisStatus = (unsigned int)a2->ndisStatus;
  InformationBuffer = (struct _NDIS_PM_PROTOCOL_OFFLOAD *)a2->Request->DATA.QUERY_INFORMATION.InformationBuffer;
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( (_DWORD)ndisStatus )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids, ndisStatus);
  }
  else
  {
    pvContext1 = (struct EXTSTA_VELAN *)a2->pvContext1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids,
        InformationBuffer->ProtocolOffloadId);
    NdisAcquireRWLockWrite(pvContext1->pGenVElan->pRWLock, &LockState, 0);
    ExtSTAProcessOffloadedGTKProtocol(pvContext1, InformationBuffer);
    NdisReleaseRWLock(pvContext1->pGenVElan->pRWLock, &LockState);
  }
  Dot11FreeNdisRequestInformationBuffer(a2);
  if ( a2[-1].pCompletion )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)a2[-1].pCompletion, &a2[-1].pCompletion);
  else
    ExFreePoolWithTag(&a2[-1].pCompletion, (ULONG)a2[-1].pVElan);
}

```

## disassembly

```asm
0x140024c20  mov     [rsp+arg_0], rbx
0x140024c25  mov     [rsp+arg_10], rsi
0x140024c2a  push    rdi
0x140024c2b  sub     rsp, 20h
0x140024c2f  mov     rax, [rdx+8]
0x140024c33  mov     rbx, rdx
0x140024c36  mov     r9d, [rdx]
0x140024c39  mov     rsi, [rax+28h]
0x140024c3d  xor     eax, eax
0x140024c3f  mov     [rsp+28h+LockState.OldIrql], 0
0x140024c44  mov     word ptr [rsp+28h+LockState.LockState], ax
0x140024c49  test    r9d, r9d
0x140024c4c  jnz     loc_140024CD5
0x140024c52  mov     rdi, [rdx+110h]
0x140024c59  mov     rcx, cs:WPP_GLOBAL_Control
0x140024c60  lea     rax, WPP_GLOBAL_Control
0x140024c67  cmp     rcx, rax
0x140024c6a  jz      short loc_140024C87
0x140024c6c  mov     rcx, [rcx+18h]
0x140024c70  lea     edx, [r9+1Fh]
0x140024c74  mov     r9d, [rsi+94h]
0x140024c7b  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x140024c82  call    WPP_SF_d
0x140024c87  mov     rcx, [rdi+0A38h]
0x140024c8e  lea     rdx, [rsp+28h+LockState]; LockState
0x140024c93  xor     r8d, r8d; Flags
0x140024c96  mov     rcx, [rcx+90h]; Lock
0x140024c9d  call    cs:__imp_NdisAcquireRWLockWrite
0x140024ca4  nop     dword ptr [rax+rax+00h]
0x140024ca9  mov     rdx, rsi; struct _NDIS_PM_PROTOCOL_OFFLOAD *
0x140024cac  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140024caf  call    ?ExtSTAProcessOffloadedGTKProtocol@@YAXPEAUEXTSTA_VELAN@@PEAU_NDIS_PM_PROTOCOL_OFFLOAD@@@Z; ExtSTAProcessOffloadedGTKProtocol(EXTSTA_VELAN *,_NDIS_PM_PROTOCOL_OFFLOAD *)
0x140024cb4  mov     rcx, [rdi+0A38h]
0x140024cbb  lea     rdx, [rsp+28h+LockState]; LockState
0x140024cc0  mov     rcx, [rcx+90h]; Lock
0x140024cc7  call    cs:__imp_NdisReleaseRWLock
0x140024cce  nop     dword ptr [rax+rax+00h]
0x140024cd3  jmp     short loc_140024CFD
0x140024cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x140024cdc  lea     rax, WPP_GLOBAL_Control
0x140024ce3  cmp     rcx, rax
0x140024ce6  jz      short loc_140024CFD
0x140024ce8  mov     rcx, [rcx+18h]
0x140024cec  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x140024cf3  mov     edx, 20h ; ' '
0x140024cf8  call    WPP_SF_d
0x140024cfd  mov     rcx, rbx; struct DOT11_NDIS_REQUEST *
0x140024d00  call    ?Dot11FreeNdisRequestInformationBuffer@@YAXPEAUDOT11_NDIS_REQUEST@@@Z; Dot11FreeNdisRequestInformationBuffer(DOT11_NDIS_REQUEST *)
0x140024d05  lea     rcx, [rbx-10h]; P
0x140024d09  mov     rax, [rcx]
0x140024d0c  test    rax, rax
0x140024d0f  jz      short loc_140024D25
0x140024d11  mov     rdx, rcx; Entry
0x140024d14  mov     rcx, rax; Lookaside
0x140024d17  call    cs:__imp_ExFreeToNPagedLookasideList
0x140024d1e  nop     dword ptr [rax+rax+00h]
0x140024d23  jmp     short loc_140024D34
0x140024d25  mov     edx, [rcx+8]; Tag
0x140024d28  call    cs:__imp_ExFreePoolWithTag
0x140024d2f  nop     dword ptr [rax+rax+00h]
0x140024d34  mov     rbx, [rsp+28h+arg_0]
0x140024d39  mov     rsi, [rsp+28h+arg_10]
0x140024d3e  add     rsp, 20h
0x140024d42  pop     rdi
0x140024d43  retn
```
