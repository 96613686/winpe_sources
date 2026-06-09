# CKsDevice::PnpStart(_IRP *)

- ea: `0x18005c2e0`
- end: `0x18005c569`
- name: `?PnpStart@CKsDevice@@QEAAJPEAU_IRP@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(CKsDevice *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180048c60`

## callees

- `0x18000b7bc`
- `0x18000c4c8`
- `0x18000c630`
- `0x180019cb0`
- `0x18005b964`
- `0x18005bd44`
- `0x18005c2e0`
- `0x18005c7b8`
- `0x18005c83c`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x18005c3d6`
- `ntoskrnl!ExQueueWorkItem` at `0x18005c3d6`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18005c3b0`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18005c3b0`

## pseudocode

```c
__int64 __fastcall CKsDevice::PnpStart(CKsDevice *this, struct _IRP *a2)
{
  __int64 *v4; // rdx
  unsigned __int8 v5; // di
  struct _KSDEVICE_HEADER_EX *DeviceHeader; // r12
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  _KSDEVICE *p_Public; // r14
  NTSTATUS v9; // esi
  const _KSDEVICE_DESCRIPTOR *Descriptor; // rcx
  const _KSDEVICE_DISPATCH *v11; // rax
  char v12; // bp
  int v13; // edx
  CKsDevice *v14; // rcx
  const _KSDEVICE_DISPATCH *Dispatch; // rcx
  int (__fastcall *Start)(_KSDEVICE *, _IRP *, _CM_RESOURCE_LIST *, _CM_RESOURCE_LIST *); // rax
  __int64 v18; // rdx
  int v19; // edx

  v4 = WPP_50288c75019938eedd86f8b19427641e_Traceguids;
  v5 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v4,
      1,
      53,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  DeviceHeader = CKsDevice::GetDeviceHeaderEx(this->m_Ext.Public.FunctionalDeviceObject);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  this->AcquireDevice(this);
  p_Public = &this->m_Ext.Public;
  v9 = 0;
  Descriptor = this->m_Ext.Public.Descriptor;
  if ( Descriptor
    && (Dispatch = Descriptor->Dispatch) != 0
    && (Start = Dispatch->Start) != 0
    && (v9 = Start(
               &this->m_Ext.Public,
               a2,
               CurrentStackLocation->Parameters.StartDevice.AllocatedResourcesTranslated,
               CurrentStackLocation->Parameters.StartDevice.AllocatedResources),
        v9 < 0)
    || !p_Public->Descriptor
    || (v11 = p_Public->Descriptor->Dispatch) == 0
    || (v12 = 1, !v11->PostStart) )
  {
    v12 = 0;
  }
  this->ReleaseDevice(this);
  if ( v12 )
  {
    v9 = IoAcquireRemoveLockEx(&DeviceHeader->RemoveLock, CKsDevice::PostPnpStartWorker, File, 1u, 0x20u);
    if ( v9 >= 0 )
    {
      this->m_PostPnpStartWorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)CKsDevice::PostPnpStartWorker;
      this->m_PostPnpStartWorkItem.Parameter = this;
      this->m_PostPnpStartWorkItem.List.Flink = 0;
      ExQueueWorkItem(&this->m_PostPnpStartWorkItem, DelayedWorkQueue);
    }
    goto LABEL_9;
  }
  if ( v9 >= 0 )
  {
    this->m_Ext.Public.Started = 1;
    CKsDevice::ArmForRemoteWakeup(this, 0);
    this->AcquireDevice(this);
    LOBYTE(v18) = 1;
    KspSetDeviceClassesState((__int64)this->m_Ext.Public.FunctionalDeviceObject, v18);
    this->ReleaseDevice(this);
LABEL_16:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v19) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        1,
        56,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    goto LABEL_17;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = 4;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      1,
      55,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
      v9);
    goto LABEL_16;
  }
LABEL_17:
  if ( this->m_Ext.Public.Started )
    this->m_FailCreates = 0;
  else
    v5 = 0;
  this->m_AllowIo = v5;
  CKsDevice::RedispatchPendingCreates(this);
LABEL_9:
  CKsDevice::CompleteIrp(v14, a2, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005c2e0  push    rbx
0x18005c2e2  push    rbp
0x18005c2e3  push    rsi
0x18005c2e4  push    rdi
0x18005c2e5  push    r12
0x18005c2e7  push    r13
0x18005c2e9  push    r14
0x18005c2eb  push    r15
0x18005c2ed  sub     rsp, 38h
0x18005c2f1  mov     r15, rdx
0x18005c2f4  mov     rbx, rcx
0x18005c2f7  xor     r13d, r13d
0x18005c2fa  lea     rax, WPP_RECORDER_INITIALIZED
0x18005c301  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005c308  lea     rdx, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c30f  lea     edi, [r13+1]
0x18005c313  jnz     loc_18005C4C9
0x18005c319  mov     rcx, [rbx+0E0h]; struct _DEVICE_OBJECT *
0x18005c320  call    ?GetDeviceHeaderEx@CKsDevice@@SAPEAU_KSDEVICE_HEADER_EX@@PEAU_DEVICE_OBJECT@@@Z; CKsDevice::GetDeviceHeaderEx(_DEVICE_OBJECT *)
0x18005c325  mov     rcx, [rbx]
0x18005c328  mov     r12, rax
0x18005c32b  mov     rbp, [r15+0B8h]
0x18005c332  mov     rax, [rcx+28h]
0x18005c336  mov     rcx, rbx
0x18005c339  call    _guard_dispatch_icall
0x18005c33e  lea     r14, [rbx+0C8h]
0x18005c345  mov     esi, r13d
0x18005c348  mov     rcx, [r14]
0x18005c34b  test    rcx, rcx
0x18005c34e  jnz     loc_18005C401
0x18005c354  mov     rax, [r14]
0x18005c357  test    rax, rax
0x18005c35a  jz      loc_18005C437
0x18005c360  mov     rax, [rax]
0x18005c363  test    rax, rax
0x18005c366  jz      loc_18005C437
0x18005c36c  mov     bpl, dil
0x18005c36f  cmp     [rax+10h], r13
0x18005c373  jz      loc_18005C437
0x18005c379  mov     rax, [rbx]
0x18005c37c  mov     rcx, rbx
0x18005c37f  mov     rax, [rax+30h]
0x18005c383  call    _guard_dispatch_icall
0x18005c388  test    bpl, bpl
0x18005c38b  jz      loc_18005C43F
0x18005c391  lea     rbp, ?PostPnpStartWorker@CKsDevice@@SAXPEAX@Z; CKsDevice::PostPnpStartWorker(void *)
0x18005c398  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x18005c3a0  mov     rdx, rbp; Tag
0x18005c3a3  lea     r8, File; File
0x18005c3aa  mov     r9d, edi; Line
0x18005c3ad  mov     rcx, r12; RemoveLock
0x18005c3b0  call    cs:__imp_IoAcquireRemoveLockEx
0x18005c3b7  nop     dword ptr [rax+rax+00h]
0x18005c3bc  mov     esi, eax
0x18005c3be  test    eax, eax
0x18005c3c0  js      short loc_18005C3E2
0x18005c3c2  lea     rcx, [rbx+1B8h]; WorkItem
0x18005c3c9  mov     edx, edi; QueueType
0x18005c3cb  mov     [rcx+10h], rbp
0x18005c3cf  mov     [rcx+18h], rbx
0x18005c3d3  mov     [rcx], r13
0x18005c3d6  call    cs:__imp_ExQueueWorkItem
0x18005c3dd  nop     dword ptr [rax+rax+00h]
0x18005c3e2  mov     r8d, esi; int
0x18005c3e5  mov     rdx, r15; struct _IRP *
0x18005c3e8  call    ?CompleteIrp@CKsDevice@@QEAAJPEAU_IRP@@J@Z; CKsDevice::CompleteIrp(_IRP *,long)
0x18005c3ed  mov     eax, esi
0x18005c3ef  add     rsp, 38h
0x18005c3f3  pop     r15
0x18005c3f5  pop     r14
0x18005c3f7  pop     r13
0x18005c3f9  pop     r12
0x18005c3fb  pop     rdi
0x18005c3fc  pop     rsi
0x18005c3fd  pop     rbp
0x18005c3fe  pop     rbx
0x18005c3ff  retn
0x18005c401  mov     rcx, [rcx]
0x18005c404  test    rcx, rcx
0x18005c407  jz      loc_18005C354
0x18005c40d  mov     rax, [rcx+8]
0x18005c411  test    rax, rax
0x18005c414  jz      loc_18005C354
0x18005c41a  mov     r9, [rbp+8]
0x18005c41e  mov     rdx, r15
0x18005c421  mov     r8, [rbp+10h]
0x18005c425  mov     rcx, r14
0x18005c428  call    _guard_dispatch_icall
0x18005c42d  mov     esi, eax
0x18005c42f  test    eax, eax
0x18005c431  jns     loc_18005C354
0x18005c437  mov     bpl, r13b
0x18005c43a  jmp     loc_18005C379
0x18005c43f  test    esi, esi
0x18005c441  js      loc_18005C4F9
0x18005c447  xor     edx, edx; unsigned __int8
0x18005c449  mov     [rbx+0F8h], dil
0x18005c450  mov     rcx, rbx; this
0x18005c453  call    ?ArmForRemoteWakeup@CKsDevice@@AEAAJE@Z; CKsDevice::ArmForRemoteWakeup(uchar)
0x18005c458  mov     rax, [rbx]
0x18005c45b  mov     rcx, rbx
0x18005c45e  mov     rax, [rax+28h]
0x18005c462  call    _guard_dispatch_icall
0x18005c467  mov     rcx, [rbx+0E0h]
0x18005c46e  mov     dl, dil
0x18005c471  call    KspSetDeviceClassesState
0x18005c476  mov     rax, [rbx]
0x18005c479  mov     rcx, rbx
0x18005c47c  mov     rax, [rax+30h]
0x18005c480  call    _guard_dispatch_icall
0x18005c485  lea     rbp, WPP_RECORDER_INITIALIZED
0x18005c48c  lea     r14, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c493  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18005c49a  jnz     loc_18005C539
0x18005c4a0  cmp     [rbx+0F8h], r13b
0x18005c4a7  jz      short loc_18005C4C4
0x18005c4a9  mov     [rbx+314h], r13b
0x18005c4b0  mov     rcx, rbx; this
0x18005c4b3  mov     [rbx+313h], dil
0x18005c4ba  call    ?RedispatchPendingCreates@CKsDevice@@QEAAXXZ; CKsDevice::RedispatchPendingCreates(void)
0x18005c4bf  jmp     loc_18005C3E2
0x18005c4c4  mov     dil, r13b
0x18005c4c7  jmp     short loc_18005C4B0
0x18005c4c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c4d0  cmp     [rcx+48h], r13w
0x18005c4d5  jz      loc_18005C319
0x18005c4db  mov     rcx, [rcx+40h]
0x18005c4df  mov     r9d, 35h ; '5'
0x18005c4e5  mov     qword ptr [rsp+78h+RemlockSize], rdx
0x18005c4ea  mov     r8d, edi
0x18005c4ed  mov     dl, 5
0x18005c4ef  call    WPP_RECORDER_SF_
0x18005c4f4  jmp     loc_18005C319
0x18005c4f9  lea     rbp, WPP_RECORDER_INITIALIZED
0x18005c500  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18005c507  jz      short loc_18005C4A0
0x18005c509  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c510  lea     r14, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c517  mov     r9d, 37h ; '7'
0x18005c51d  mov     [rsp+78h+var_50], esi
0x18005c521  mov     r8d, edi
0x18005c524  mov     qword ptr [rsp+78h+RemlockSize], r14
0x18005c529  mov     dl, 4
0x18005c52b  mov     rcx, [rcx+40h]
0x18005c52f  call    WPP_RECORDER_SF_D
0x18005c534  jmp     loc_18005C493
0x18005c539  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c540  cmp     [rcx+48h], r13w
0x18005c545  jz      loc_18005C4A0
0x18005c54b  mov     rcx, [rcx+40h]
0x18005c54f  mov     r9d, 38h ; '8'
0x18005c555  mov     r8d, edi
0x18005c558  mov     qword ptr [rsp+78h+RemlockSize], r14
0x18005c55d  mov     dl, 5
0x18005c55f  call    WPP_RECORDER_SF_
0x18005c564  jmp     loc_18005C4A0
```
