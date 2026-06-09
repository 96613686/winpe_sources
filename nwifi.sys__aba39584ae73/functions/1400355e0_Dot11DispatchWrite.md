# Dot11DispatchWrite

- ea: `0x1400355e0`
- end: `0x14003586f`
- name: `Dot11DispatchWrite`
- size: `655`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000e178`
- `0x140011908`
- `0x1400208f0`
- `0x140034d38`
- `0x1400355e0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140035695`
- `ntoskrnl!KeWaitForSingleObject` at `0x140035695`
- `ntoskrnl!KeSetEvent` at `0x1400357da`
- `ntoskrnl!KeSetEvent` at `0x14003582a`
- `ntoskrnl!KeSetEvent` at `0x1400357da`
- `ntoskrnl!KeSetEvent` at `0x14003582a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003564c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003564c`
- `ntoskrnl!IofCompleteRequest` at `0x14003584d`
- `ntoskrnl!IofCompleteRequest` at `0x14003584d`
- `NDIS!NdisReleaseRWLock` at `0x140035767`
- `NDIS!NdisReleaseRWLock` at `0x140035805`
- `NDIS!NdisReleaseRWLock` at `0x140035767`
- `NDIS!NdisReleaseRWLock` at `0x140035805`
- `NDIS!NdisAcquireRWLockRead` at `0x1400356e1`
- `NDIS!NdisAcquireRWLockRead` at `0x1400356e1`

## pseudocode

```c
__int64 __fastcall Dot11DispatchWrite(__int64 a1, IRP *a2)
{
  _MDL *MdlAddress; // rcx
  _FILE_OBJECT *FileObject; // r14
  void *FsContext; // rdi
  PVOID MappedSystemVa; // rax
  int v7; // ebx
  struct _VELAN *v8; // rdi
  struct DOT11_DRIVER *pDot11Driver; // rax
  _FILE_OBJECT *pSecurityEndpoint; // rax
  struct _NET_BUFFER_LIST *v11; // rdx
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF
  struct _NET_BUFFER_LIST *v14; // [rsp+60h] [rbp+18h]

  MdlAddress = a2->MdlAddress;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v14 = 0;
  FsContext = FileObject->FsContext;
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( !MdlAddress || MdlAddress->Next )
  {
    v7 = -1073741811;
    goto LABEL_31;
  }
  if ( (MdlAddress->MdlFlags & 5) != 0 )
    MappedSystemVa = MdlAddress->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
  if ( !MappedSystemVa )
  {
    v7 = -1073741670;
LABEL_31:
    a2->IoStatus.Status = v7;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
    return (unsigned int)v7;
  }
  if ( !FsContext )
  {
    v7 = -1073741808;
    goto LABEL_31;
  }
  v8 = (struct _VELAN *)*((_QWORD *)FsContext + 2);
  KeWaitForSingleObject(&v8->PnPMutex, Executive, 0, 0, 0);
  v8->PnPMutex.LockOwner = KeGetCurrentThread();
  if ( !v8->pAdapt || !v8->hMiniport || !v8->pVElanExt )
  {
    v7 = -1073741808;
    goto LABEL_29;
  }
  NdisAcquireRWLockRead(v8->pRWLock, &LockState, 0);
  pDot11Driver = v8->pDot11Driver;
  if ( pDot11Driver == &NetMon || pDot11Driver == &Manufacturing )
  {
    v7 = -1073741637;
    goto LABEL_27;
  }
  pSecurityEndpoint = v8->pSecurityEndpoint;
  if ( !pSecurityEndpoint )
  {
    v7 = -1073741808;
LABEL_27:
    NdisReleaseRWLock(v8->pRWLock, &LockState);
    goto LABEL_29;
  }
  if ( pSecurityEndpoint != FileObject && v8->pMSSecurityEndpoint != FileObject )
  {
    v7 = -1073741757;
    if ( v8->pIHVSecurityEndpoint != FileObject )
      v7 = -1073741790;
    goto LABEL_27;
  }
  v7 = Dot11BuildSecuritySendPacket(v8);
  NdisReleaseRWLock(v8->pRWLock, &LockState);
  if ( v7 < 0 )
  {
LABEL_29:
    v8->PnPMutex.LockOwner = 0;
    KeSetEvent(&v8->PnPMutex.Event, 1, 0);
    goto LABEL_31;
  }
  v11 = v14;
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  Dot11QueueSendPacket(v8, v11);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_615b6383d2ff36bd1729122bdb28558b_Traceguids, v14);
  Dot11FlushIntermediateSendQueue(v8);
  v8->PnPMutex.LockOwner = 0;
  KeSetEvent(&v8->PnPMutex.Event, 1, 0);
  return 259;
}

```

## disassembly

```asm
0x1400355e0  mov     [rsp+arg_0], rbx
0x1400355e5  mov     [rsp+arg_18], rbp
0x1400355ea  push    rsi
0x1400355eb  push    rdi
0x1400355ec  push    r14
0x1400355ee  sub     rsp, 30h
0x1400355f2  mov     rax, [rdx+0B8h]
0x1400355f9  mov     rsi, rdx
0x1400355fc  mov     rcx, [rdx+8]; MemoryDescriptorList
0x140035600  mov     r14, [rax+30h]
0x140035604  xor     eax, eax
0x140035606  mov     [rsp+48h+arg_10], rax
0x14003560b  mov     rdi, [r14+18h]
0x14003560f  mov     [rsp+48h+LockState.OldIrql], 0
0x140035614  mov     word ptr [rsp+48h+LockState.LockState], ax
0x140035619  test    rcx, rcx
0x14003561c  jz      loc_140035838
0x140035622  cmp     [rcx], rax
0x140035625  jnz     loc_140035838
0x14003562b  test    byte ptr [rcx+0Ah], 5
0x14003562f  jz      short loc_140035637
0x140035631  mov     rax, [rcx+18h]
0x140035635  jmp     short loc_140035658
0x140035637  xor     r9d, r9d; RequestedAddress
0x14003563a  mov     [rsp+48h+Priority], 40000010h; Priority
0x140035642  xor     edx, edx; AccessMode
0x140035644  mov     [rsp+48h+BugCheckOnFailure], eax; BugCheckOnFailure
0x140035648  lea     r8d, [r9+1]; CacheType
0x14003564c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140035653  nop     dword ptr [rax+rax+00h]
0x140035658  test    rax, rax
0x14003565b  jnz     short loc_140035667
0x14003565d  mov     ebx, 0C000009Ah
0x140035662  jmp     loc_14003583D
0x140035667  test    rdi, rdi
0x14003566a  jnz     short loc_140035676
0x14003566c  mov     ebx, 0C0000010h
0x140035671  jmp     loc_14003583D
0x140035676  mov     rdi, [rdi+10h]
0x14003567a  xor     r9d, r9d; Alertable
0x14003567d  xor     r8d, r8d; WaitMode
0x140035680  mov     qword ptr [rsp+48h+BugCheckOnFailure], 0; Timeout
0x140035689  xor     edx, edx; WaitReason
0x14003568b  lea     rbp, [rdi+1F70h]
0x140035692  mov     rcx, rbp; Object
0x140035695  call    cs:__imp_KeWaitForSingleObject
0x14003569c  nop     dword ptr [rax+rax+00h]
0x1400356a1  mov     rax, gs:188h
0x1400356aa  mov     [rbp+18h], rax
0x1400356ae  cmp     qword ptr [rdi+10h], 0
0x1400356b3  jz      loc_140035813
0x1400356b9  cmp     qword ptr [rdi+20h], 0
0x1400356be  jz      loc_140035813
0x1400356c4  cmp     qword ptr [rdi+1F68h], 0
0x1400356cc  jz      loc_140035813
0x1400356d2  mov     rcx, [rdi+90h]; Lock
0x1400356d9  lea     rdx, [rsp+48h+LockState]; LockState
0x1400356de  xor     r8d, r8d; Flags
0x1400356e1  call    cs:__imp_NdisAcquireRWLockRead
0x1400356e8  nop     dword ptr [rax+rax+00h]
0x1400356ed  mov     rax, [rdi+98h]
0x1400356f4  lea     rcx, ?NetMon@@3UDOT11_DRIVER@@A; DOT11_DRIVER NetMon
0x1400356fb  cmp     rax, rcx
0x1400356fe  jz      loc_1400357F4
0x140035704  lea     rcx, ?Manufacturing@@3UDOT11_DRIVER@@A; DOT11_DRIVER Manufacturing
0x14003570b  cmp     rax, rcx
0x14003570e  jz      loc_1400357F4
0x140035714  mov     rax, [rdi+1700h]
0x14003571b  test    rax, rax
0x14003571e  jz      loc_1400357ED
0x140035724  cmp     rax, r14
0x140035727  jz      short loc_140035749
0x140035729  cmp     [rdi+16F0h], r14
0x140035730  jz      short loc_140035749
0x140035732  cmp     [rdi+16F8h], r14
0x140035739  mov     ebx, 0C0000043h
0x14003573e  lea     eax, [rbx-21h]
0x140035741  cmovnz  ebx, eax
0x140035744  jmp     loc_1400357F9
0x140035749  lea     r8, [rsp+48h+arg_10]
0x14003574e  mov     rdx, rsi
0x140035751  mov     rcx, rdi; struct _VELAN *
0x140035754  call    Dot11BuildSecuritySendPacket
0x140035759  mov     rcx, [rdi+90h]; Lock
0x140035760  lea     rdx, [rsp+48h+LockState]; LockState
0x140035765  mov     ebx, eax
0x140035767  call    cs:__imp_NdisReleaseRWLock
0x14003576e  nop     dword ptr [rax+rax+00h]
0x140035773  test    ebx, ebx
0x140035775  js      loc_140035818
0x14003577b  mov     rax, [rsi+0B8h]
0x140035782  mov     rcx, rdi; struct _VELAN *
0x140035785  mov     rdx, [rsp+48h+arg_10]; struct _NET_BUFFER_LIST *
0x14003578a  or      byte ptr [rax+3], 1
0x14003578e  call    ?Dot11QueueSendPacket@@YAXPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@@Z; Dot11QueueSendPacket(_VELAN *,_NET_BUFFER_LIST *)
0x140035793  mov     rcx, cs:WPP_GLOBAL_Control
0x14003579a  lea     rax, WPP_GLOBAL_Control
0x1400357a1  cmp     rcx, rax
0x1400357a4  jz      short loc_1400357C0
0x1400357a6  mov     r9, [rsp+48h+arg_10]
0x1400357ab  lea     r8, WPP_615b6383d2ff36bd1729122bdb28558b_Traceguids
0x1400357b2  mov     rcx, [rcx+18h]
0x1400357b6  mov     edx, 0Ah
0x1400357bb  call    WPP_SF_q
0x1400357c0  mov     rcx, rdi; struct _VELAN *
0x1400357c3  call    ?Dot11FlushIntermediateSendQueue@@YAXPEAU_VELAN@@@Z; Dot11FlushIntermediateSendQueue(_VELAN *)
0x1400357c8  xor     r8d, r8d; Wait
0x1400357cb  mov     qword ptr [rbp+18h], 0
0x1400357d3  mov     rcx, rbp; Event
0x1400357d6  lea     edx, [r8+1]; Increment
0x1400357da  call    cs:__imp_KeSetEvent
0x1400357e1  nop     dword ptr [rax+rax+00h]
0x1400357e6  mov     eax, 103h
0x1400357eb  jmp     short loc_14003585B
0x1400357ed  mov     ebx, 0C0000010h
0x1400357f2  jmp     short loc_1400357F9
0x1400357f4  mov     ebx, 0C00000BBh
0x1400357f9  mov     rcx, [rdi+90h]; Lock
0x140035800  lea     rdx, [rsp+48h+LockState]; LockState
0x140035805  call    cs:__imp_NdisReleaseRWLock
0x14003580c  nop     dword ptr [rax+rax+00h]
0x140035811  jmp     short loc_140035818
0x140035813  mov     ebx, 0C0000010h
0x140035818  xor     r8d, r8d; Wait
0x14003581b  mov     qword ptr [rbp+18h], 0
0x140035823  mov     rcx, rbp; Event
0x140035826  lea     edx, [r8+1]; Increment
0x14003582a  call    cs:__imp_KeSetEvent
0x140035831  nop     dword ptr [rax+rax+00h]
0x140035836  jmp     short loc_14003583D
0x140035838  mov     ebx, 0C000000Dh
0x14003583d  xor     edx, edx; PriorityBoost
0x14003583f  mov     [rsi+30h], ebx
0x140035842  mov     rcx, rsi; Irp
0x140035845  mov     qword ptr [rsi+38h], 0
0x14003584d  call    cs:__imp_IofCompleteRequest
0x140035854  nop     dword ptr [rax+rax+00h]
0x140035859  mov     eax, ebx
0x14003585b  mov     rbx, [rsp+48h+arg_0]
0x140035860  mov     rbp, [rsp+48h+arg_18]
0x140035865  add     rsp, 30h
0x140035869  pop     r14
0x14003586b  pop     rdi
0x14003586c  pop     rsi
0x14003586d  retn
```
