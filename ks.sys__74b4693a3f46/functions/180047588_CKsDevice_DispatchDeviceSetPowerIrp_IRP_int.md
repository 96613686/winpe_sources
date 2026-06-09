# CKsDevice::DispatchDeviceSetPowerIrp(_IRP *,int *)

- ea: `0x180047588`
- end: `0x180047933`
- name: `?DispatchDeviceSetPowerIrp@CKsDevice@@AEAAJPEAU_IRP@@PEAH@Z`
- size: `939`
- prototype: `int(CKsDevice *__hidden this, struct _IRP *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047030`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180019c60`
- `0x180047588`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180047688`
- `ntoskrnl!KeReleaseMutex` at `0x180047688`
- `ntoskrnl!PoCallDriver` at `0x180047737`
- `ntoskrnl!PoCallDriver` at `0x1800477e4`
- `ntoskrnl!PoCallDriver` at `0x180047737`
- `ntoskrnl!PoCallDriver` at `0x1800477e4`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180047701`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1800478ad`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180047701`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1800478ad`
- `ntoskrnl!PoSetPowerState` at `0x1800475f7`
- `ntoskrnl!PoSetPowerState` at `0x1800475f7`
- `ntoskrnl!KeWaitForSingleObject` at `0x180047638`
- `ntoskrnl!KeWaitForSingleObject` at `0x180047638`
- `ntoskrnl!IofCompleteRequest` at `0x1800478be`
- `ntoskrnl!IofCompleteRequest` at `0x1800478be`

## pseudocode

```c
NTSTATUS __fastcall CKsDevice::DispatchDeviceSetPowerIrp(CKsDevice *this, struct _IRP *a2, int *a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  _IRP *m_SxIrp; // rbp
  struct _IRP *v6; // rdi
  _DEVICE_POWER_STATE DeviceState; // ebp
  int v9; // edx
  _DEVICE_POWER_STATE v10; // r12d
  CKsDevice *Blink; // rbp
  int v12; // edx
  const _KSDEVICE_DESCRIPTOR *Descriptor; // rax
  const _KSDEVICE_DISPATCH *Dispatch; // rax
  void (__fastcall *SetPower)(_KSDEVICE *, _IRP *, _DEVICE_POWER_STATE, _DEVICE_POWER_STATE); // rax
  int v16; // edx
  struct _IO_STACK_LOCATION *v18; // rax
  struct _IO_STACK_LOCATION *v19; // rax
  struct _IO_STACK_LOCATION *v20; // rax
  int v21; // edx
  _DEVICE_POWER_STATE v22; // [rsp+28h] [rbp-50h]
  ULONG LowPart; // [rsp+28h] [rbp-50h]
  _DEVICE_POWER_STATE DevicePowerState; // [rsp+28h] [rbp-50h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  m_SxIrp = this->m_SxIrp;
  v6 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      100,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  if ( m_SxIrp
    && CurrentStackLocation->MinorFunction == 2
    && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 1 )
  {
    m_SxIrp->IoStatus.Status = 0;
    this->m_SxIrp = 0;
    PoStartNextPowerIrp(m_SxIrp);
    IofCompleteRequest(m_SxIrp, 0);
  }
  DeviceState = CurrentStackLocation->Parameters.Power.State.DeviceState;
  if ( this->m_Ext.Public.DevicePowerState > DeviceState )
  {
    v18 = v6->Tail.Overlay.CurrentStackLocation;
    *a3 = 0;
    v18->Control |= 1u;
    v19 = v6->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v19[-1].MajorFunction = *(_OWORD *)&v19->MajorFunction;
    *(_OWORD *)&v19[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v19->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v19[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v19->Parameters.SetQuota + 6);
    v19[-1].FileObject = v19->FileObject;
    v19[-1].Control = 0;
    v20 = v6->Tail.Overlay.CurrentStackLocation;
    v20[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)CKsDevice::CompleteDevicePowerIrp;
    v20[-1].Context = this;
    v20[-1].Control = -32;
    PoCallDriver(this->m_Ext.Public.NextDeviceObject, v6);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      v22 = DeviceState;
      LOBYTE(v21) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v21,
        1,
        101,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
        v22);
    }
    return 259;
  }
  else
  {
    PoSetPowerState(this->m_Ext.Public.FunctionalDeviceObject, DevicePowerState, (POWER_STATE)DeviceState);
    if ( this->m_Ext.Public.DevicePowerState == CurrentStackLocation->Parameters.Read.ByteOffset.LowPart )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        DevicePowerState = this->m_Ext.Public.DevicePowerState;
        LOBYTE(v9) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          1,
          102,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
          DevicePowerState);
      }
      v6->IoStatus.Status = 0;
    }
    else
    {
      this->AcquireDevice(this);
      KeWaitForSingleObject(&this->m_PowerNotifyMutex, Executive, 0, 0, 0);
      v10 = this->m_Ext.Public.DevicePowerState;
      Blink = (CKsDevice *)this->m_PowerNotifyList.Blink;
      this->m_Ext.Public.DevicePowerState = CurrentStackLocation->Parameters.Power.State.DeviceState;
      while ( Blink != (CKsDevice *)&this->m_PowerNotifyList )
      {
        (*((void (__fastcall **)(IKsThermalNotification_vtbl *, _QWORD))Blink->QueryInterface + 3))(
          Blink->IKsThermalNotification::IUnknown::__vftable,
          (unsigned int)this->m_Ext.Public.DevicePowerState);
        Blink = (CKsDevice *)Blink->IKsDeviceFunctions::IUnknown::__vftable;
      }
      KeReleaseMutex(&this->m_PowerNotifyMutex, 0);
      Descriptor = this->m_Ext.Public.Descriptor;
      if ( Descriptor )
      {
        Dispatch = Descriptor->Dispatch;
        if ( Dispatch )
        {
          SetPower = Dispatch->SetPower;
          if ( SetPower )
            SetPower(&this->m_Ext.Public, v6, CurrentStackLocation->Parameters.Power.State.DeviceState, v10);
        }
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
        LOBYTE(v12) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          1,
          103,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
          LowPart);
      }
      this->ReleaseDevice(this);
    }
    v6->IoStatus.Status = 0;
    *a3 = 1;
    PoStartNextPowerIrp(v6);
    ++v6->CurrentLocation;
    ++v6->Tail.Overlay.CurrentStackLocation;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v16) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          1,
          104,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      }
    }
    return PoCallDriver(this->m_Ext.Public.NextDeviceObject, v6);
  }
}

```

## disassembly

```asm
0x180047588  push    rbx
0x18004758a  push    rbp
0x18004758b  push    rsi
0x18004758c  push    rdi
0x18004758d  push    r12
0x18004758f  push    r13
0x180047591  push    r14
0x180047593  push    r15
0x180047595  sub     rsp, 38h
0x180047599  mov     rsi, [rdx+0B8h]
0x1800475a0  mov     r13, r8
0x1800475a3  mov     rbp, [rcx+3C0h]
0x1800475aa  mov     rdi, rdx
0x1800475ad  mov     rbx, rcx
0x1800475b0  xor     r15d, r15d
0x1800475b3  lea     rax, WPP_RECORDER_INITIALIZED
0x1800475ba  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800475c1  lea     r12, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x1800475c8  lea     r14d, [r15+1]
0x1800475cc  jnz     loc_180047755
0x1800475d2  test    rbp, rbp
0x1800475d5  jnz     loc_18004788B
0x1800475db  mov     ebp, [rsi+18h]
0x1800475de  cmp     [rbx+100h], ebp
0x1800475e4  jg      loc_180047785
0x1800475ea  mov     rcx, [rbx+0E0h]; DeviceObject
0x1800475f1  mov     r8d, ebp; State
0x1800475f4  mov     edx, r14d; Type
0x1800475f7  call    cs:__imp_PoSetPowerState
0x1800475fe  nop     dword ptr [rax+rax+00h]
0x180047603  mov     eax, [rbx+100h]
0x180047609  cmp     eax, [rsi+18h]
0x18004760c  jz      loc_18004780A
0x180047612  mov     rax, [rbx]
0x180047615  mov     rcx, rbx
0x180047618  mov     rax, [rax+28h]
0x18004761c  call    _guard_dispatch_icall
0x180047621  lea     r14, [rbx+2C8h]
0x180047628  mov     [rsp+78h+Timeout], r15; Timeout
0x18004762d  mov     rcx, r14; Object
0x180047630  xor     r9d, r9d; Alertable
0x180047633  xor     r8d, r8d; WaitMode
0x180047636  xor     edx, edx; WaitReason
0x180047638  call    cs:__imp_KeWaitForSingleObject
0x18004763f  nop     dword ptr [rax+rax+00h]
0x180047644  mov     eax, [rsi+18h]
0x180047647  lea     r15, [rbx+2B8h]
0x18004764e  mov     r12d, [rbx+100h]
0x180047655  mov     rbp, [rbx+2C0h]
0x18004765c  mov     [rbx+100h], eax
0x180047662  jmp     short loc_18004767E
0x180047664  mov     rcx, [rbp+10h]
0x180047668  mov     edx, [rbx+100h]
0x18004766e  mov     rax, [rcx]
0x180047671  mov     rax, [rax+18h]
0x180047675  call    _guard_dispatch_icall
0x18004767a  mov     rbp, [rbp+8]
0x18004767e  cmp     rbp, r15
0x180047681  jnz     short loc_180047664
0x180047683  xor     edx, edx; Wait
0x180047685  mov     rcx, r14; Mutex
0x180047688  call    cs:__imp_KeReleaseMutex
0x18004768f  nop     dword ptr [rax+rax+00h]
0x180047694  lea     rcx, [rbx+0C8h]
0x18004769b  xor     r15d, r15d
0x18004769e  mov     rax, [rcx]
0x1800476a1  test    rax, rax
0x1800476a4  jz      short loc_1800476C6
0x1800476a6  mov     rax, [rax]
0x1800476a9  test    rax, rax
0x1800476ac  jz      short loc_1800476C6
0x1800476ae  mov     rax, [rax+60h]
0x1800476b2  test    rax, rax
0x1800476b5  jz      short loc_1800476C6
0x1800476b7  mov     r8d, [rsi+18h]
0x1800476bb  mov     r9d, r12d
0x1800476be  mov     rdx, rdi
0x1800476c1  call    _guard_dispatch_icall
0x1800476c6  lea     rcx, WPP_RECORDER_INITIALIZED
0x1800476cd  mov     r14d, 1
0x1800476d3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1800476da  lea     r12, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x1800476e1  jnz     loc_180047854
0x1800476e7  mov     rax, [rbx]
0x1800476ea  mov     rcx, rbx
0x1800476ed  mov     rax, [rax+30h]
0x1800476f1  call    _guard_dispatch_icall
0x1800476f6  mov     rcx, rdi; Irp
0x1800476f9  mov     [rdi+30h], r15d
0x1800476fd  mov     [r13+0], r14d
0x180047701  call    cs:__imp_PoStartNextPowerIrp
0x180047708  nop     dword ptr [rax+rax+00h]
0x18004770d  add     [rdi+43h], r14b
0x180047711  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x180047719  lea     rax, WPP_RECORDER_INITIALIZED
0x180047720  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180047727  jnz     loc_1800478CF
0x18004772d  mov     rcx, [rbx+0F0h]; DeviceObject
0x180047734  mov     rdx, rdi; Irp
0x180047737  call    cs:__imp_PoCallDriver
0x18004773e  nop     dword ptr [rax+rax+00h]
0x180047743  add     rsp, 38h
0x180047747  pop     r15
0x180047749  pop     r14
0x18004774b  pop     r13
0x18004774d  pop     r12
0x18004774f  pop     rdi
0x180047750  pop     rsi
0x180047751  pop     rbp
0x180047752  pop     rbx
0x180047753  retn
0x180047755  mov     rcx, cs:WPP_GLOBAL_Control
0x18004775c  cmp     [rcx+48h], r15w
0x180047761  jz      loc_1800475D2
0x180047767  mov     rcx, [rcx+40h]
0x18004776b  mov     r9d, 64h ; 'd'
0x180047771  mov     r8d, r14d
0x180047774  mov     [rsp+78h+Timeout], r12
0x180047779  mov     dl, 5
0x18004777b  call    WPP_RECORDER_SF_
0x180047780  jmp     loc_1800475D2
0x180047785  mov     rax, [rdi+0B8h]
0x18004778c  lea     rcx, ?CompleteDevicePowerIrp@CKsDevice@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAV1@@Z; CKsDevice::CompleteDevicePowerIrp(_DEVICE_OBJECT *,_IRP *,CKsDevice *)
0x180047793  mov     rdx, rdi; Irp
0x180047796  mov     [r13+0], r15d
0x18004779a  or      [rax+3], r14b
0x18004779e  mov     rax, [rdi+0B8h]
0x1800477a5  movups  xmm0, xmmword ptr [rax]
0x1800477a8  movups  xmmword ptr [rax-48h], xmm0
0x1800477ac  movups  xmm1, xmmword ptr [rax+10h]
0x1800477b0  movups  xmmword ptr [rax-38h], xmm1
0x1800477b4  movups  xmm0, xmmword ptr [rax+20h]
0x1800477b8  movups  xmmword ptr [rax-28h], xmm0
0x1800477bc  movsd   xmm1, qword ptr [rax+30h]
0x1800477c1  movsd   qword ptr [rax-18h], xmm1
0x1800477c6  mov     [rax-45h], r15b
0x1800477ca  mov     rax, [rdi+0B8h]
0x1800477d1  mov     [rax-10h], rcx
0x1800477d5  mov     [rax-8], rbx
0x1800477d9  mov     byte ptr [rax-45h], 0E0h
0x1800477dd  mov     rcx, [rbx+0F0h]; DeviceObject
0x1800477e4  call    cs:__imp_PoCallDriver
0x1800477eb  nop     dword ptr [rax+rax+00h]
0x1800477f0  lea     rcx, WPP_RECORDER_INITIALIZED
0x1800477f7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1800477fe  jnz     short loc_180047827
0x180047800  mov     eax, 103h
0x180047805  jmp     loc_180047743
0x18004780a  lea     rcx, WPP_RECORDER_INITIALIZED
0x180047811  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180047818  jnz     loc_1800478FF
0x18004781e  mov     [rdi+30h], r15d
0x180047822  jmp     loc_1800476F6
0x180047827  mov     rcx, cs:WPP_GLOBAL_Control
0x18004782e  cmp     [rcx+48h], r15w
0x180047833  jz      short loc_180047800
0x180047835  mov     rcx, [rcx+40h]
0x180047839  mov     r9d, 65h ; 'e'
0x18004783f  mov     [rsp+78h+var_50], ebp
0x180047843  mov     r8d, r14d
0x180047846  mov     dl, 5
0x180047848  mov     [rsp+78h+Timeout], r12
0x18004784d  call    WPP_RECORDER_SF_D
0x180047852  jmp     short loc_180047800
0x180047854  mov     rcx, cs:WPP_GLOBAL_Control
0x18004785b  cmp     [rcx+48h], r15w
0x180047860  jz      loc_1800476E7
0x180047866  mov     eax, [rsi+18h]
0x180047869  mov     r9d, 67h ; 'g'
0x18004786f  mov     rcx, [rcx+40h]
0x180047873  mov     r8d, r14d
0x180047876  mov     [rsp+78h+var_50], eax
0x18004787a  mov     dl, 5
0x18004787c  mov     [rsp+78h+Timeout], r12
0x180047881  call    WPP_RECORDER_SF_D
0x180047886  jmp     loc_1800476E7
0x18004788b  cmp     byte ptr [rsi+1], 2
0x18004788f  jnz     loc_1800475DB
0x180047895  cmp     [rsi+18h], r14d
0x180047899  jnz     loc_1800475DB
0x18004789f  mov     [rbp+30h], r15d
0x1800478a3  mov     rcx, rbp; Irp
0x1800478a6  mov     [rbx+3C0h], r15
0x1800478ad  call    cs:__imp_PoStartNextPowerIrp
0x1800478b4  nop     dword ptr [rax+rax+00h]
0x1800478b9  xor     edx, edx; PriorityBoost
0x1800478bb  mov     rcx, rbp; Irp
0x1800478be  call    cs:__imp_IofCompleteRequest
0x1800478c5  nop     dword ptr [rax+rax+00h]
0x1800478ca  jmp     loc_1800475DB
0x1800478cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800478d6  cmp     [rcx+48h], r15w
0x1800478db  jz      loc_18004772D
0x1800478e1  mov     rcx, [rcx+40h]
0x1800478e5  mov     r9d, 68h ; 'h'
0x1800478eb  mov     r8d, r14d
0x1800478ee  mov     [rsp+78h+Timeout], r12
0x1800478f3  mov     dl, 5
0x1800478f5  call    WPP_RECORDER_SF_
0x1800478fa  jmp     loc_18004772D
0x1800478ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180047906  cmp     [rcx+48h], r15w
0x18004790b  jz      loc_18004781E
0x180047911  mov     rcx, [rcx+40h]
0x180047915  mov     r9d, 66h ; 'f'
0x18004791b  mov     [rsp+78h+var_50], eax
0x18004791f  mov     r8d, r14d
0x180047922  mov     dl, 5
0x180047924  mov     [rsp+78h+Timeout], r12
0x180047929  call    WPP_RECORDER_SF_D
0x18004792e  jmp     loc_18004781E
```
