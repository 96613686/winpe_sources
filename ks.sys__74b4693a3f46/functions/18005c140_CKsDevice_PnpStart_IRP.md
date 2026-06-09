# CKsDevice::PnpStart(_IRP *)

- ea: `0x18005c140`
- end: `0x18005c3c9`
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
- `0x180019c60`
- `0x18005b7c4`
- `0x18005bba4`
- `0x18005c140`
- `0x18005c618`
- `0x18005c69c`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x18005c236`
- `ntoskrnl!ExQueueWorkItem` at `0x18005c236`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18005c210`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18005c210`

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
    KspSetDeviceClassesState(this->m_Ext.Public.FunctionalDeviceObject, v18);
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
0x18005c140  push    rbx
0x18005c142  push    rbp
0x18005c143  push    rsi
0x18005c144  push    rdi
0x18005c145  push    r12
0x18005c147  push    r13
0x18005c149  push    r14
0x18005c14b  push    r15
0x18005c14d  sub     rsp, 38h
0x18005c151  mov     r15, rdx
0x18005c154  mov     rbx, rcx
0x18005c157  xor     r13d, r13d
0x18005c15a  lea     rax, WPP_RECORDER_INITIALIZED
0x18005c161  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005c168  lea     rdx, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c16f  lea     edi, [r13+1]
0x18005c173  jnz     loc_18005C329
0x18005c179  mov     rcx, [rbx+0E0h]; struct _DEVICE_OBJECT *
0x18005c180  call    ?GetDeviceHeaderEx@CKsDevice@@SAPEAU_KSDEVICE_HEADER_EX@@PEAU_DEVICE_OBJECT@@@Z; CKsDevice::GetDeviceHeaderEx(_DEVICE_OBJECT *)
0x18005c185  mov     rcx, [rbx]
0x18005c188  mov     r12, rax
0x18005c18b  mov     rbp, [r15+0B8h]
0x18005c192  mov     rax, [rcx+28h]
0x18005c196  mov     rcx, rbx
0x18005c199  call    _guard_dispatch_icall
0x18005c19e  lea     r14, [rbx+0C8h]
0x18005c1a5  mov     esi, r13d
0x18005c1a8  mov     rcx, [r14]
0x18005c1ab  test    rcx, rcx
0x18005c1ae  jnz     loc_18005C261
0x18005c1b4  mov     rax, [r14]
0x18005c1b7  test    rax, rax
0x18005c1ba  jz      loc_18005C297
0x18005c1c0  mov     rax, [rax]
0x18005c1c3  test    rax, rax
0x18005c1c6  jz      loc_18005C297
0x18005c1cc  mov     bpl, dil
0x18005c1cf  cmp     [rax+10h], r13
0x18005c1d3  jz      loc_18005C297
0x18005c1d9  mov     rax, [rbx]
0x18005c1dc  mov     rcx, rbx
0x18005c1df  mov     rax, [rax+30h]
0x18005c1e3  call    _guard_dispatch_icall
0x18005c1e8  test    bpl, bpl
0x18005c1eb  jz      loc_18005C29F
0x18005c1f1  lea     rbp, ?PostPnpStartWorker@CKsDevice@@SAXPEAX@Z; CKsDevice::PostPnpStartWorker(void *)
0x18005c1f8  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x18005c200  mov     rdx, rbp; Tag
0x18005c203  lea     r8, File; File
0x18005c20a  mov     r9d, edi; Line
0x18005c20d  mov     rcx, r12; RemoveLock
0x18005c210  call    cs:__imp_IoAcquireRemoveLockEx
0x18005c217  nop     dword ptr [rax+rax+00h]
0x18005c21c  mov     esi, eax
0x18005c21e  test    eax, eax
0x18005c220  js      short loc_18005C242
0x18005c222  lea     rcx, [rbx+1B8h]; WorkItem
0x18005c229  mov     edx, edi; QueueType
0x18005c22b  mov     [rcx+10h], rbp
0x18005c22f  mov     [rcx+18h], rbx
0x18005c233  mov     [rcx], r13
0x18005c236  call    cs:__imp_ExQueueWorkItem
0x18005c23d  nop     dword ptr [rax+rax+00h]
0x18005c242  mov     r8d, esi; int
0x18005c245  mov     rdx, r15; struct _IRP *
0x18005c248  call    ?CompleteIrp@CKsDevice@@QEAAJPEAU_IRP@@J@Z; CKsDevice::CompleteIrp(_IRP *,long)
0x18005c24d  mov     eax, esi
0x18005c24f  add     rsp, 38h
0x18005c253  pop     r15
0x18005c255  pop     r14
0x18005c257  pop     r13
0x18005c259  pop     r12
0x18005c25b  pop     rdi
0x18005c25c  pop     rsi
0x18005c25d  pop     rbp
0x18005c25e  pop     rbx
0x18005c25f  retn
0x18005c261  mov     rcx, [rcx]
0x18005c264  test    rcx, rcx
0x18005c267  jz      loc_18005C1B4
0x18005c26d  mov     rax, [rcx+8]
0x18005c271  test    rax, rax
0x18005c274  jz      loc_18005C1B4
0x18005c27a  mov     r9, [rbp+8]
0x18005c27e  mov     rdx, r15
0x18005c281  mov     r8, [rbp+10h]
0x18005c285  mov     rcx, r14
0x18005c288  call    _guard_dispatch_icall
0x18005c28d  mov     esi, eax
0x18005c28f  test    eax, eax
0x18005c291  jns     loc_18005C1B4
0x18005c297  mov     bpl, r13b
0x18005c29a  jmp     loc_18005C1D9
0x18005c29f  test    esi, esi
0x18005c2a1  js      loc_18005C359
0x18005c2a7  xor     edx, edx; unsigned __int8
0x18005c2a9  mov     [rbx+0F8h], dil
0x18005c2b0  mov     rcx, rbx; this
0x18005c2b3  call    ?ArmForRemoteWakeup@CKsDevice@@AEAAJE@Z; CKsDevice::ArmForRemoteWakeup(uchar)
0x18005c2b8  mov     rax, [rbx]
0x18005c2bb  mov     rcx, rbx
0x18005c2be  mov     rax, [rax+28h]
0x18005c2c2  call    _guard_dispatch_icall
0x18005c2c7  mov     rcx, [rbx+0E0h]
0x18005c2ce  mov     dl, dil
0x18005c2d1  call    KspSetDeviceClassesState
0x18005c2d6  mov     rax, [rbx]
0x18005c2d9  mov     rcx, rbx
0x18005c2dc  mov     rax, [rax+30h]
0x18005c2e0  call    _guard_dispatch_icall
0x18005c2e5  lea     rbp, WPP_RECORDER_INITIALIZED
0x18005c2ec  lea     r14, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c2f3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18005c2fa  jnz     loc_18005C399
0x18005c300  cmp     [rbx+0F8h], r13b
0x18005c307  jz      short loc_18005C324
0x18005c309  mov     [rbx+314h], r13b
0x18005c310  mov     rcx, rbx; this
0x18005c313  mov     [rbx+313h], dil
0x18005c31a  call    ?RedispatchPendingCreates@CKsDevice@@QEAAXXZ; CKsDevice::RedispatchPendingCreates(void)
0x18005c31f  jmp     loc_18005C242
0x18005c324  mov     dil, r13b
0x18005c327  jmp     short loc_18005C310
0x18005c329  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c330  cmp     [rcx+48h], r13w
0x18005c335  jz      loc_18005C179
0x18005c33b  mov     rcx, [rcx+40h]
0x18005c33f  mov     r9d, 35h ; '5'
0x18005c345  mov     qword ptr [rsp+78h+RemlockSize], rdx
0x18005c34a  mov     r8d, edi
0x18005c34d  mov     dl, 5
0x18005c34f  call    WPP_RECORDER_SF_
0x18005c354  jmp     loc_18005C179
0x18005c359  lea     rbp, WPP_RECORDER_INITIALIZED
0x18005c360  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18005c367  jz      short loc_18005C300
0x18005c369  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c370  lea     r14, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c377  mov     r9d, 37h ; '7'
0x18005c37d  mov     [rsp+78h+var_50], esi
0x18005c381  mov     r8d, edi
0x18005c384  mov     qword ptr [rsp+78h+RemlockSize], r14
0x18005c389  mov     dl, 4
0x18005c38b  mov     rcx, [rcx+40h]
0x18005c38f  call    WPP_RECORDER_SF_D
0x18005c394  jmp     loc_18005C2F3
0x18005c399  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c3a0  cmp     [rcx+48h], r13w
0x18005c3a5  jz      loc_18005C300
0x18005c3ab  mov     rcx, [rcx+40h]
0x18005c3af  mov     r9d, 38h ; '8'
0x18005c3b5  mov     r8d, edi
0x18005c3b8  mov     qword ptr [rsp+78h+RemlockSize], r14
0x18005c3bd  mov     dl, 5
0x18005c3bf  call    WPP_RECORDER_SF_
0x18005c3c4  jmp     loc_18005C300
```
