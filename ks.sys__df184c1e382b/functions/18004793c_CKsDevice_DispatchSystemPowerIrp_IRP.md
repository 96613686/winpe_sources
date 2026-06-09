# CKsDevice::DispatchSystemPowerIrp(_IRP *)

- ea: `0x18004793c`
- end: `0x180047cd0`
- name: `?DispatchSystemPowerIrp@CKsDevice@@AEAAJPEAU_IRP@@@Z`
- size: `916`
- prototype: `__int64 __fastcall(CKsDevice *__hidden this, PIRP Irp)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047030`

## callees

- `0x18000b7bc`
- `0x18000da50`
- `0x18000fe40`
- `0x180019cb0`
- `0x18004793c`
- `0x180047cd8`

## import_xrefs

- `ntoskrnl!PoCallDriver` at `0x180047adb`
- `ntoskrnl!PoCallDriver` at `0x180047adb`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180047c7c`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180047c7c`
- `ntoskrnl!IofCompleteRequest` at `0x180047c8d`
- `ntoskrnl!IofCompleteRequest` at `0x180047c8d`

## pseudocode

```c
__int64 __fastcall CKsDevice::DispatchSystemPowerIrp(CKsDevice *this, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  PIRP v3; // rdi
  int v5; // edx
  int v6; // r8d
  __int64 LowPart; // r9
  int v8; // esi
  const _KSDEVICE_DESCRIPTOR *Descriptor; // rax
  int (__fastcall *QueryPower)(_KSDEVICE *, _IRP *, _DEVICE_POWER_STATE, _DEVICE_POWER_STATE, _SYSTEM_POWER_STATE, _SYSTEM_POWER_STATE, POWER_ACTION); // rax
  struct _IO_STACK_LOCATION *v11; // rax
  struct _IO_STACK_LOCATION *v12; // rax
  int v13; // edx
  unsigned int m_ActivePinCount; // eax
  int v16; // edx

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v3 = Irp;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(Irp) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      1,
      93,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  if ( CurrentStackLocation->MinorFunction != 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(Irp) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)Irp,
        1,
        97,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    this->AcquireDevice(this);
    this->m_Ext.Public.SystemPowerState = CurrentStackLocation->Parameters.Power.State.SystemState;
    this->ReleaseDevice(this);
    CKsDevice::RedispatchPendingRuns(this);
    goto LABEL_15;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(Irp) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      1,
      94,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  this->AcquireDevice(this);
  LowPart = (int)CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( (_DWORD)LowPart == 6 )
  {
    m_ActivePinCount = this->m_ActivePinCount;
    if ( m_ActivePinCount )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v5) = 5;
        WPP_RECORDER_SF_qqd(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          v6,
          95,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
          (char)this->m_Ext.Public.FunctionalDeviceObject,
          (char)v3,
          m_ActivePinCount);
      }
      v8 = -1073741823;
      goto LABEL_13;
    }
  }
  v8 = 0;
  Descriptor = this->m_Ext.Public.Descriptor;
  if ( Descriptor )
  {
    if ( Descriptor->Dispatch )
    {
      QueryPower = Descriptor->Dispatch->QueryPower;
      if ( QueryPower )
      {
        v8 = QueryPower(
               &this->m_Ext.Public,
               v3,
               this->m_DeviceStateMap[LowPart],
               this->m_Ext.Public.DevicePowerState,
               (_SYSTEM_POWER_STATE)LowPart,
               this->m_Ext.Public.SystemPowerState,
               CurrentStackLocation->Parameters.Power.ShutdownType);
        if ( v8 < 0 )
        {
LABEL_13:
          this->ReleaseDevice(this);
          CKsDevice::RedispatchPendingRuns(this);
          goto LABEL_14;
        }
      }
    }
  }
  if ( !CurrentStackLocation->Parameters.Create.Options && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 6 )
  {
    this->m_RunsMayProceed = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v5) = 5;
        WPP_RECORDER_SF_qq(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          v6,
          96,
          (char)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
          (char)this->m_Ext.Public.FunctionalDeviceObject);
      }
    }
  }
  this->ReleaseDevice(this);
LABEL_14:
  if ( v8 >= 0 )
  {
LABEL_15:
    v3->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    v11 = v3->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v11[-1].MajorFunction = *(_OWORD *)&v11->MajorFunction;
    *(_OWORD *)&v11[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v11->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v11[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v11->Parameters.SetQuota + 6);
    v11[-1].FileObject = v11->FileObject;
    v11[-1].Control = 0;
    v12 = v3->Tail.Overlay.CurrentStackLocation;
    v12[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)CKsDevice::CompleteSystemPowerIrp;
    v12[-1].Context = this;
    v12[-1].Control = -32;
    PoCallDriver(this->m_Ext.Public.NextDeviceObject, v3);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v13) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          1,
          98,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      }
    }
    return 259;
  }
  v3->IoStatus.Status = v8;
  PoStartNextPowerIrp(v3);
  IofCompleteRequest(v3, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v16) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      1,
      99,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004793c  push    rbx
0x18004793e  push    rbp
0x18004793f  push    rsi
0x180047940  push    rdi
0x180047941  push    r12
0x180047943  push    r13
0x180047945  push    r14
0x180047947  push    r15
0x180047949  sub     rsp, 48h
0x18004794d  mov     rbp, [rdx+0B8h]
0x180047954  mov     rdi, rdx
0x180047957  mov     rbx, rcx
0x18004795a  xor     r14d, r14d
0x18004795d  lea     r15, WPP_RECORDER_INITIALIZED
0x180047964  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18004796b  lea     r12, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180047972  lea     r13d, [r14+1]
0x180047976  jnz     loc_180047B07
0x18004797c  cmp     byte ptr [rbp+1], 3
0x180047980  jz      short loc_1800479C3
0x180047982  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180047989  jnz     loc_180047B90
0x18004798f  mov     rax, [rbx]
0x180047992  mov     rcx, rbx
0x180047995  mov     rax, [rax+28h]
0x180047999  call    _guard_dispatch_icall
0x18004799e  mov     eax, [rbp+18h]
0x1800479a1  mov     rcx, rbx
0x1800479a4  mov     [rbx+0FCh], eax
0x1800479aa  mov     rax, [rbx]
0x1800479ad  mov     rax, [rax+30h]
0x1800479b1  call    _guard_dispatch_icall
0x1800479b6  mov     rcx, rbx; this
0x1800479b9  call    ?RedispatchPendingRuns@CKsDevice@@QEAAXXZ; CKsDevice::RedispatchPendingRuns(void)
0x1800479be  jmp     loc_180047A80
0x1800479c3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800479ca  jnz     loc_180047B60
0x1800479d0  mov     rax, [rbx]
0x1800479d3  mov     rcx, rbx
0x1800479d6  mov     rax, [rax+28h]
0x1800479da  call    _guard_dispatch_icall
0x1800479df  movsxd  r9, dword ptr [rbp+18h]
0x1800479e3  cmp     r9d, 6
0x1800479e7  jz      loc_180047C1C
0x1800479ed  lea     r10, [rbx+0C8h]
0x1800479f4  mov     esi, r14d
0x1800479f7  mov     rax, [r10]
0x1800479fa  test    rax, rax
0x1800479fd  jz      short loc_180047A07
0x1800479ff  mov     rcx, [rax]
0x180047a02  test    rcx, rcx
0x180047a05  jnz     short loc_180047A22
0x180047a07  cmp     [rbp+10h], r14d
0x180047a0b  jz      loc_180047BC0
0x180047a11  mov     rax, [rbx]
0x180047a14  mov     rcx, rbx
0x180047a17  mov     rax, [rax+30h]
0x180047a1b  call    _guard_dispatch_icall
0x180047a20  jmp     short loc_180047A78
0x180047a22  mov     rax, [rcx+58h]
0x180047a26  test    rax, rax
0x180047a29  jz      short loc_180047A07
0x180047a2b  mov     edx, [rbp+20h]
0x180047a2e  mov     rcx, r10
0x180047a31  mov     r8d, [rbx+r9*4+298h]
0x180047a39  mov     dword ptr [rsp+88h+var_58], edx
0x180047a3d  mov     edx, [rbx+0FCh]
0x180047a43  mov     dword ptr [rsp+88h+var_60], edx
0x180047a47  mov     rdx, rdi
0x180047a4a  mov     dword ptr [rsp+88h+var_68], r9d
0x180047a4f  mov     r9d, [rbx+100h]
0x180047a56  call    _guard_dispatch_icall
0x180047a5b  mov     esi, eax
0x180047a5d  test    eax, eax
0x180047a5f  jns     short loc_180047A07
0x180047a61  mov     rcx, [rbx]
0x180047a64  mov     rax, [rcx+30h]
0x180047a68  mov     rcx, rbx
0x180047a6b  call    _guard_dispatch_icall
0x180047a70  mov     rcx, rbx; this
0x180047a73  call    ?RedispatchPendingRuns@CKsDevice@@QEAAXXZ; CKsDevice::RedispatchPendingRuns(void)
0x180047a78  test    esi, esi
0x180047a7a  js      loc_180047C76
0x180047a80  mov     rax, [rdi+0B8h]
0x180047a87  lea     rcx, ?CompleteSystemPowerIrp@CKsDevice@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAV1@@Z; CKsDevice::CompleteSystemPowerIrp(_DEVICE_OBJECT *,_IRP *,CKsDevice *)
0x180047a8e  mov     rdx, rdi; Irp
0x180047a91  or      [rax+3], r13b
0x180047a95  mov     rax, [rdi+0B8h]
0x180047a9c  movups  xmm0, xmmword ptr [rax]
0x180047a9f  movups  xmmword ptr [rax-48h], xmm0
0x180047aa3  movups  xmm1, xmmword ptr [rax+10h]
0x180047aa7  movups  xmmword ptr [rax-38h], xmm1
0x180047aab  movups  xmm0, xmmword ptr [rax+20h]
0x180047aaf  movups  xmmword ptr [rax-28h], xmm0
0x180047ab3  movsd   xmm1, qword ptr [rax+30h]
0x180047ab8  movsd   qword ptr [rax-18h], xmm1
0x180047abd  mov     [rax-45h], r14b
0x180047ac1  mov     rax, [rdi+0B8h]
0x180047ac8  mov     [rax-10h], rcx
0x180047acc  mov     [rax-8], rbx
0x180047ad0  mov     byte ptr [rax-45h], 0E0h
0x180047ad4  mov     rcx, [rbx+0F0h]; DeviceObject
0x180047adb  call    cs:__imp_PoCallDriver
0x180047ae2  nop     dword ptr [rax+rax+00h]
0x180047ae7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180047aee  jnz     short loc_180047B37
0x180047af0  mov     eax, 103h
0x180047af5  add     rsp, 48h
0x180047af9  pop     r15
0x180047afb  pop     r14
0x180047afd  pop     r13
0x180047aff  pop     r12
0x180047b01  pop     rdi
0x180047b02  pop     rsi
0x180047b03  pop     rbp
0x180047b04  pop     rbx
0x180047b05  retn
0x180047b07  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b0e  cmp     [rcx+48h], r14w
0x180047b13  jz      loc_18004797C
0x180047b19  mov     rcx, [rcx+40h]
0x180047b1d  mov     r9d, 5Dh ; ']'
0x180047b23  mov     r8d, r13d
0x180047b26  mov     [rsp+88h+var_68], r12
0x180047b2b  mov     dl, 5
0x180047b2d  call    WPP_RECORDER_SF_
0x180047b32  jmp     loc_18004797C
0x180047b37  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b3e  cmp     [rcx+48h], r14w
0x180047b43  jz      short loc_180047AF0
0x180047b45  mov     rcx, [rcx+40h]
0x180047b49  mov     r9d, 62h ; 'b'
0x180047b4f  mov     r8d, r13d
0x180047b52  mov     [rsp+88h+var_68], r12
0x180047b57  mov     dl, 5
0x180047b59  call    WPP_RECORDER_SF_
0x180047b5e  jmp     short loc_180047AF0
0x180047b60  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b67  cmp     [rcx+48h], r14w
0x180047b6c  jz      loc_1800479D0
0x180047b72  mov     rcx, [rcx+40h]
0x180047b76  mov     r9d, 5Eh ; '^'
0x180047b7c  mov     r8d, r13d
0x180047b7f  mov     [rsp+88h+var_68], r12
0x180047b84  mov     dl, 5
0x180047b86  call    WPP_RECORDER_SF_
0x180047b8b  jmp     loc_1800479D0
0x180047b90  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b97  cmp     [rcx+48h], r14w
0x180047b9c  jz      loc_18004798F
0x180047ba2  mov     rcx, [rcx+40h]
0x180047ba6  mov     r9d, 61h ; 'a'
0x180047bac  mov     r8d, r13d
0x180047baf  mov     [rsp+88h+var_68], r12
0x180047bb4  mov     dl, 5
0x180047bb6  call    WPP_RECORDER_SF_
0x180047bbb  jmp     loc_18004798F
0x180047bc0  cmp     dword ptr [rbp+18h], 6
0x180047bc4  jnz     loc_180047A11
0x180047bca  mov     [rbx+311h], r14b
0x180047bd1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180047bd8  jz      loc_180047A11
0x180047bde  mov     rcx, cs:WPP_GLOBAL_Control
0x180047be5  cmp     [rcx+48h], r14w
0x180047bea  jz      loc_180047A11
0x180047bf0  mov     rax, [rbx+0E0h]
0x180047bf7  mov     r9d, 60h ; '`'
0x180047bfd  mov     rcx, [rcx+40h]
0x180047c01  mov     dl, 5
0x180047c03  mov     [rsp+88h+var_58], rdi
0x180047c08  mov     [rsp+88h+var_60], rax
0x180047c0d  mov     [rsp+88h+var_68], r12
0x180047c12  call    WPP_RECORDER_SF_qq
0x180047c17  jmp     loc_180047A11
0x180047c1c  mov     eax, [rbx+300h]
0x180047c22  test    eax, eax
0x180047c24  jz      loc_1800479ED
0x180047c2a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180047c31  jz      short loc_180047C6C
0x180047c33  mov     rcx, cs:WPP_GLOBAL_Control
0x180047c3a  cmp     [rcx+48h], r14w
0x180047c3f  jz      short loc_180047C6C
0x180047c41  mov     rcx, [rcx+40h]
0x180047c45  mov     r9d, 5Fh ; '_'
0x180047c4b  mov     [rsp+88h+var_50], eax
0x180047c4f  mov     dl, 5
0x180047c51  mov     rax, [rbx+0E0h]
0x180047c58  mov     [rsp+88h+var_58], rdi
0x180047c5d  mov     [rsp+88h+var_60], rax
0x180047c62  mov     [rsp+88h+var_68], r12
0x180047c67  call    WPP_RECORDER_SF_qqd
0x180047c6c  mov     esi, 0C0000001h
0x180047c71  jmp     loc_180047A61
0x180047c76  mov     rcx, rdi; Irp
0x180047c79  mov     [rdi+30h], esi
0x180047c7c  call    cs:__imp_PoStartNextPowerIrp
0x180047c83  nop     dword ptr [rax+rax+00h]
0x180047c88  xor     edx, edx; PriorityBoost
0x180047c8a  mov     rcx, rdi; Irp
0x180047c8d  call    cs:__imp_IofCompleteRequest
0x180047c94  nop     dword ptr [rax+rax+00h]
0x180047c99  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180047ca0  jz      short loc_180047CC9
0x180047ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x180047ca9  cmp     [rcx+48h], r14w
0x180047cae  jz      short loc_180047CC9
0x180047cb0  mov     rcx, [rcx+40h]
0x180047cb4  mov     r9d, 63h ; 'c'
0x180047cba  mov     r8d, r13d
0x180047cbd  mov     [rsp+88h+var_68], r12
0x180047cc2  mov     dl, 5
0x180047cc4  call    WPP_RECORDER_SF_
0x180047cc9  mov     eax, esi
0x180047ccb  jmp     loc_180047AF5
```
