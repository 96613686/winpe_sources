# Dot11DispatchWrite

- ea: `0x1400353c0`
- end: `0x14003564f`
- name: `Dot11DispatchWrite`
- size: `655`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000e188`
- `0x140011918`
- `0x1400208f0`
- `0x140034b18`
- `0x1400353c0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140035475`
- `ntoskrnl!KeWaitForSingleObject` at `0x140035475`
- `ntoskrnl!KeSetEvent` at `0x1400355ba`
- `ntoskrnl!KeSetEvent` at `0x14003560a`
- `ntoskrnl!KeSetEvent` at `0x1400355ba`
- `ntoskrnl!KeSetEvent` at `0x14003560a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003542c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003542c`
- `ntoskrnl!IofCompleteRequest` at `0x14003562d`
- `ntoskrnl!IofCompleteRequest` at `0x14003562d`
- `NDIS!NdisReleaseRWLock` at `0x140035547`
- `NDIS!NdisReleaseRWLock` at `0x1400355e5`
- `NDIS!NdisReleaseRWLock` at `0x140035547`
- `NDIS!NdisReleaseRWLock` at `0x1400355e5`
- `NDIS!NdisAcquireRWLockRead` at `0x1400354c1`
- `NDIS!NdisAcquireRWLockRead` at `0x1400354c1`

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
0x1400353c0  mov     [rsp+arg_0], rbx
0x1400353c5  mov     [rsp+arg_18], rbp
0x1400353ca  push    rsi
0x1400353cb  push    rdi
0x1400353cc  push    r14
0x1400353ce  sub     rsp, 30h
0x1400353d2  mov     rax, [rdx+0B8h]
0x1400353d9  mov     rsi, rdx
0x1400353dc  mov     rcx, [rdx+8]; MemoryDescriptorList
0x1400353e0  mov     r14, [rax+30h]
0x1400353e4  xor     eax, eax
0x1400353e6  mov     [rsp+48h+arg_10], rax
0x1400353eb  mov     rdi, [r14+18h]
0x1400353ef  mov     [rsp+48h+LockState.OldIrql], 0
0x1400353f4  mov     word ptr [rsp+48h+LockState.LockState], ax
0x1400353f9  test    rcx, rcx
0x1400353fc  jz      loc_140035618
0x140035402  cmp     [rcx], rax
0x140035405  jnz     loc_140035618
0x14003540b  test    byte ptr [rcx+0Ah], 5
0x14003540f  jz      short loc_140035417
0x140035411  mov     rax, [rcx+18h]
0x140035415  jmp     short loc_140035438
0x140035417  xor     r9d, r9d; RequestedAddress
0x14003541a  mov     [rsp+48h+Priority], 40000010h; Priority
0x140035422  xor     edx, edx; AccessMode
0x140035424  mov     [rsp+48h+BugCheckOnFailure], eax; BugCheckOnFailure
0x140035428  lea     r8d, [r9+1]; CacheType
0x14003542c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140035433  nop     dword ptr [rax+rax+00h]
0x140035438  test    rax, rax
0x14003543b  jnz     short loc_140035447
0x14003543d  mov     ebx, 0C000009Ah
0x140035442  jmp     loc_14003561D
0x140035447  test    rdi, rdi
0x14003544a  jnz     short loc_140035456
0x14003544c  mov     ebx, 0C0000010h
0x140035451  jmp     loc_14003561D
0x140035456  mov     rdi, [rdi+10h]
0x14003545a  xor     r9d, r9d; Alertable
0x14003545d  xor     r8d, r8d; WaitMode
0x140035460  mov     qword ptr [rsp+48h+BugCheckOnFailure], 0; Timeout
0x140035469  xor     edx, edx; WaitReason
0x14003546b  lea     rbp, [rdi+1F70h]
0x140035472  mov     rcx, rbp; Object
0x140035475  call    cs:__imp_KeWaitForSingleObject
0x14003547c  nop     dword ptr [rax+rax+00h]
0x140035481  mov     rax, gs:188h
0x14003548a  mov     [rbp+18h], rax
0x14003548e  cmp     qword ptr [rdi+10h], 0
0x140035493  jz      loc_1400355F3
0x140035499  cmp     qword ptr [rdi+20h], 0
0x14003549e  jz      loc_1400355F3
0x1400354a4  cmp     qword ptr [rdi+1F68h], 0
0x1400354ac  jz      loc_1400355F3
0x1400354b2  mov     rcx, [rdi+90h]; Lock
0x1400354b9  lea     rdx, [rsp+48h+LockState]; LockState
0x1400354be  xor     r8d, r8d; Flags
0x1400354c1  call    cs:__imp_NdisAcquireRWLockRead
0x1400354c8  nop     dword ptr [rax+rax+00h]
0x1400354cd  mov     rax, [rdi+98h]
0x1400354d4  lea     rcx, ?NetMon@@3UDOT11_DRIVER@@A; DOT11_DRIVER NetMon
0x1400354db  cmp     rax, rcx
0x1400354de  jz      loc_1400355D4
0x1400354e4  lea     rcx, ?Manufacturing@@3UDOT11_DRIVER@@A; DOT11_DRIVER Manufacturing
0x1400354eb  cmp     rax, rcx
0x1400354ee  jz      loc_1400355D4
0x1400354f4  mov     rax, [rdi+1700h]
0x1400354fb  test    rax, rax
0x1400354fe  jz      loc_1400355CD
0x140035504  cmp     rax, r14
0x140035507  jz      short loc_140035529
0x140035509  cmp     [rdi+16F0h], r14
0x140035510  jz      short loc_140035529
0x140035512  cmp     [rdi+16F8h], r14
0x140035519  mov     ebx, 0C0000043h
0x14003551e  lea     eax, [rbx-21h]
0x140035521  cmovnz  ebx, eax
0x140035524  jmp     loc_1400355D9
0x140035529  lea     r8, [rsp+48h+arg_10]
0x14003552e  mov     rdx, rsi
0x140035531  mov     rcx, rdi; struct _VELAN *
0x140035534  call    Dot11BuildSecuritySendPacket
0x140035539  mov     rcx, [rdi+90h]; Lock
0x140035540  lea     rdx, [rsp+48h+LockState]; LockState
0x140035545  mov     ebx, eax
0x140035547  call    cs:__imp_NdisReleaseRWLock
0x14003554e  nop     dword ptr [rax+rax+00h]
0x140035553  test    ebx, ebx
0x140035555  js      loc_1400355F8
0x14003555b  mov     rax, [rsi+0B8h]
0x140035562  mov     rcx, rdi; struct _VELAN *
0x140035565  mov     rdx, [rsp+48h+arg_10]; struct _NET_BUFFER_LIST *
0x14003556a  or      byte ptr [rax+3], 1
0x14003556e  call    ?Dot11QueueSendPacket@@YAXPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@@Z; Dot11QueueSendPacket(_VELAN *,_NET_BUFFER_LIST *)
0x140035573  mov     rcx, cs:WPP_GLOBAL_Control
0x14003557a  lea     rax, WPP_GLOBAL_Control
0x140035581  cmp     rcx, rax
0x140035584  jz      short loc_1400355A0
0x140035586  mov     r9, [rsp+48h+arg_10]
0x14003558b  lea     r8, WPP_615b6383d2ff36bd1729122bdb28558b_Traceguids
0x140035592  mov     rcx, [rcx+18h]
0x140035596  mov     edx, 0Ah
0x14003559b  call    WPP_SF_q
0x1400355a0  mov     rcx, rdi; struct _VELAN *
0x1400355a3  call    ?Dot11FlushIntermediateSendQueue@@YAXPEAU_VELAN@@@Z; Dot11FlushIntermediateSendQueue(_VELAN *)
0x1400355a8  xor     r8d, r8d; Wait
0x1400355ab  mov     qword ptr [rbp+18h], 0
0x1400355b3  mov     rcx, rbp; Event
0x1400355b6  lea     edx, [r8+1]; Increment
0x1400355ba  call    cs:__imp_KeSetEvent
0x1400355c1  nop     dword ptr [rax+rax+00h]
0x1400355c6  mov     eax, 103h
0x1400355cb  jmp     short loc_14003563B
0x1400355cd  mov     ebx, 0C0000010h
0x1400355d2  jmp     short loc_1400355D9
0x1400355d4  mov     ebx, 0C00000BBh
0x1400355d9  mov     rcx, [rdi+90h]; Lock
0x1400355e0  lea     rdx, [rsp+48h+LockState]; LockState
0x1400355e5  call    cs:__imp_NdisReleaseRWLock
0x1400355ec  nop     dword ptr [rax+rax+00h]
0x1400355f1  jmp     short loc_1400355F8
0x1400355f3  mov     ebx, 0C0000010h
0x1400355f8  xor     r8d, r8d; Wait
0x1400355fb  mov     qword ptr [rbp+18h], 0
0x140035603  mov     rcx, rbp; Event
0x140035606  lea     edx, [r8+1]; Increment
0x14003560a  call    cs:__imp_KeSetEvent
0x140035611  nop     dword ptr [rax+rax+00h]
0x140035616  jmp     short loc_14003561D
0x140035618  mov     ebx, 0C000000Dh
0x14003561d  xor     edx, edx; PriorityBoost
0x14003561f  mov     [rsi+30h], ebx
0x140035622  mov     rcx, rsi; Irp
0x140035625  mov     qword ptr [rsi+38h], 0
0x14003562d  call    cs:__imp_IofCompleteRequest
0x140035634  nop     dword ptr [rax+rax+00h]
0x140035639  mov     eax, ebx
0x14003563b  mov     rbx, [rsp+48h+arg_0]
0x140035640  mov     rbp, [rsp+48h+arg_18]
0x140035645  add     rsp, 30h
0x140035649  pop     r14
0x14003564b  pop     rdi
0x14003564c  pop     rsi
0x14003564d  retn
```
