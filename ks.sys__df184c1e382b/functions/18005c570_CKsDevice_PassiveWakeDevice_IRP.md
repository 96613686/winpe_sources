# CKsDevice::PassiveWakeDevice(_IRP *)

- ea: `0x18005c570`
- end: `0x18005c7b2`
- name: `?PassiveWakeDevice@CKsDevice@@CAXPEAU_IRP@@@Z`
- size: `578`
- prototype: `void __fastcall(struct _IRP *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18000c1dc`
- `0x18000c4c8`
- `0x18000c630`
- `0x180019cb0`
- `0x18005c570`
- `0x18005c7b8`
- `0x18005c83c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18005c688`
- `ntoskrnl!KeReleaseMutex` at `0x18005c688`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18005c6c5`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18005c6c5`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18005c70e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18005c70e`
- `ntoskrnl!PoSetPowerState` at `0x18005c6b6`
- `ntoskrnl!PoSetPowerState` at `0x18005c6b6`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005c64c`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005c64c`

## pseudocode

```c
void __fastcall CKsDevice::PassiveWakeDevice(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  IKsDevice *v3; // rdi
  CKsDevice *v4; // rbx
  int v5; // edx
  struct _KSDEVICE_HEADER_EX *DeviceHeader; // r13
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rax
  void (__fastcall *v8)(IKsDevice *, struct _IRP *, _QWORD, _QWORD); // rax
  int v9; // edx
  ULONG LowPart; // ebp
  CKsDevice *i; // rdi
  CKsDevice *v12; // rcx
  int v13; // edx
  PDEVICE_OBJECT DeviceObject; // [rsp+80h] [rbp+8h]

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  DeviceObject = CurrentStackLocation->DeviceObject;
  v3 = *(IKsDevice **)(*(_QWORD *)DeviceObject->DeviceExtension + 360LL);
  v4 = (CKsDevice *)&v3[-25];
  DeviceHeader = CKsDevice::GetDeviceHeaderEx((struct _DEVICE_OBJECT *)v3[3].__vftable);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      1,
      105,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  v4->AcquireDevice(v3 - 25);
  if ( v3->__vftable )
  {
    QueryInterface = v3->QueryInterface;
    if ( QueryInterface )
    {
      v8 = (void (__fastcall *)(IKsDevice *, struct _IRP *, _QWORD, _QWORD))*((_QWORD *)QueryInterface + 12);
      if ( v8 )
      {
        v8(v3, a1, CurrentStackLocation->Parameters.Read.ByteOffset.LowPart, LODWORD(v3[7].__vftable));
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(v9) = 5;
            WPP_RECORDER_SF_D(
              WPP_GLOBAL_Control->DeviceExtension,
              v9,
              1,
              106,
              (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
              LODWORD(v3[7].__vftable));
          }
        }
      }
    }
  }
  KeWaitForSingleObject(&v4->m_PowerNotifyMutex, Executive, 0, 0, 0);
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  LODWORD(v3[7].__vftable) = LowPart;
  for ( i = (CKsDevice *)v4->m_PowerNotifyList.Flink;
        i != (CKsDevice *)&v4->m_PowerNotifyList;
        i = (CKsDevice *)i->IKsDevice::IUnknown::__vftable )
  {
    (*((void (__fastcall **)(IKsThermalNotification_vtbl *))i->QueryInterface + 4))(i->IKsThermalNotification::IUnknown::__vftable);
  }
  KeReleaseMutex(&v4->m_PowerNotifyMutex, 0);
  v4->ReleaseDevice(v4);
  PoSetPowerState(DeviceObject, DevicePowerState, CurrentStackLocation->Parameters.Power.State);
  PoStartNextPowerIrp(a1);
  CKsDevice::CompleteIrp(v12, a1, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v13) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      1,
      107,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  if ( LowPart == 1 )
  {
    CKsDevice::RedispatchPendingCreates(v4);
    CKsDevice::RedispatchPendedIrps(v4, 0);
  }
  IoReleaseRemoveLockEx(&DeviceHeader->RemoveLock, a1, 0x20u);
}

```

## disassembly

```asm
0x18005c570  push    rbx
0x18005c572  push    rbp
0x18005c573  push    rsi
0x18005c574  push    rdi
0x18005c575  push    r12
0x18005c577  push    r13
0x18005c579  push    r14
0x18005c57b  push    r15
0x18005c57d  sub     rsp, 38h
0x18005c581  mov     r15, [rcx+0B8h]
0x18005c588  mov     rsi, rcx
0x18005c58b  mov     rax, [r15+28h]
0x18005c58f  mov     [rsp+78h+DeviceObject], rax
0x18005c597  mov     rax, [rax+40h]
0x18005c59b  mov     rdx, [rax]
0x18005c59e  mov     rdi, [rdx+168h]
0x18005c5a5  mov     rcx, [rdi+18h]; struct _DEVICE_OBJECT *
0x18005c5a9  lea     rbx, [rdi-0C8h]
0x18005c5b0  call    ?GetDeviceHeaderEx@CKsDevice@@SAPEAU_KSDEVICE_HEADER_EX@@PEAU_DEVICE_OBJECT@@@Z; CKsDevice::GetDeviceHeaderEx(_DEVICE_OBJECT *)
0x18005c5b5  mov     r13, rax
0x18005c5b8  xor     ebp, ebp
0x18005c5ba  lea     rax, WPP_RECORDER_INITIALIZED
0x18005c5c1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005c5c8  lea     r12, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c5cf  lea     r14d, [rbp+1]
0x18005c5d3  jnz     loc_18005C72C
0x18005c5d9  mov     rax, [rbx]
0x18005c5dc  mov     rcx, rbx
0x18005c5df  mov     rax, [rax+28h]
0x18005c5e3  call    _guard_dispatch_icall
0x18005c5e8  mov     rax, [rdi]
0x18005c5eb  test    rax, rax
0x18005c5ee  jz      short loc_18005C635
0x18005c5f0  mov     rax, [rax]
0x18005c5f3  test    rax, rax
0x18005c5f6  jz      short loc_18005C635
0x18005c5f8  mov     rax, [rax+60h]
0x18005c5fc  test    rax, rax
0x18005c5ff  jz      short loc_18005C635
0x18005c601  mov     r9d, [rdi+38h]
0x18005c605  mov     rdx, rsi
0x18005c608  mov     r8d, [r15+18h]
0x18005c60c  mov     rcx, rdi
0x18005c60f  call    _guard_dispatch_icall
0x18005c614  lea     rax, WPP_RECORDER_INITIALIZED
0x18005c61b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005c622  jz      short loc_18005C635
0x18005c624  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c62b  cmp     [rcx+48h], bp
0x18005c62f  jnz     loc_18005C78D
0x18005c635  lea     r12, [rbx+2C8h]
0x18005c63c  mov     [rsp+78h+Timeout], rbp; Timeout
0x18005c641  mov     rcx, r12; Object
0x18005c644  xor     r9d, r9d; Alertable
0x18005c647  xor     r8d, r8d; WaitMode
0x18005c64a  xor     edx, edx; WaitReason
0x18005c64c  call    cs:__imp_KeWaitForSingleObject
0x18005c653  nop     dword ptr [rax+rax+00h]
0x18005c658  mov     ebp, [r15+18h]
0x18005c65c  lea     r14, [rbx+2B8h]
0x18005c663  mov     [rdi+38h], ebp
0x18005c666  mov     rdi, [r14]
0x18005c669  jmp     short loc_18005C67E
0x18005c66b  mov     rcx, [rdi+10h]
0x18005c66f  mov     rax, [rcx]
0x18005c672  mov     rax, [rax+20h]
0x18005c676  call    _guard_dispatch_icall
0x18005c67b  mov     rdi, [rdi]
0x18005c67e  cmp     rdi, r14
0x18005c681  jnz     short loc_18005C66B
0x18005c683  xor     edx, edx; Wait
0x18005c685  mov     rcx, r12; Mutex
0x18005c688  call    cs:__imp_KeReleaseMutex
0x18005c68f  nop     dword ptr [rax+rax+00h]
0x18005c694  mov     rax, [rbx]
0x18005c697  mov     rcx, rbx
0x18005c69a  mov     rax, [rax+30h]
0x18005c69e  call    _guard_dispatch_icall
0x18005c6a3  mov     r8d, [r15+18h]; State
0x18005c6a7  mov     edi, 1
0x18005c6ac  mov     rcx, [rsp+78h+DeviceObject]; DeviceObject
0x18005c6b4  mov     edx, edi; Type
0x18005c6b6  call    cs:__imp_PoSetPowerState
0x18005c6bd  nop     dword ptr [rax+rax+00h]
0x18005c6c2  mov     rcx, rsi; Irp
0x18005c6c5  call    cs:__imp_PoStartNextPowerIrp
0x18005c6cc  nop     dword ptr [rax+rax+00h]
0x18005c6d1  xor     r8d, r8d; int
0x18005c6d4  mov     rdx, rsi; struct _IRP *
0x18005c6d7  call    ?CompleteIrp@CKsDevice@@QEAAJPEAU_IRP@@J@Z; CKsDevice::CompleteIrp(_IRP *,long)
0x18005c6dc  lea     rax, WPP_RECORDER_INITIALIZED
0x18005c6e3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005c6ea  jnz     short loc_18005C75B
0x18005c6ec  cmp     ebp, edi
0x18005c6ee  jnz     short loc_18005C702
0x18005c6f0  mov     rcx, rbx; this
0x18005c6f3  call    ?RedispatchPendingCreates@CKsDevice@@QEAAXXZ; CKsDevice::RedispatchPendingCreates(void)
0x18005c6f8  xor     edx, edx; unsigned __int8
0x18005c6fa  mov     rcx, rbx; this
0x18005c6fd  call    ?RedispatchPendedIrps@CKsDevice@@AEAAXE@Z; CKsDevice::RedispatchPendedIrps(uchar)
0x18005c702  mov     r8d, 20h ; ' '; RemlockSize
0x18005c708  mov     rdx, rsi; Tag
0x18005c70b  mov     rcx, r13; RemoveLock
0x18005c70e  call    cs:__imp_IoReleaseRemoveLockEx
0x18005c715  nop     dword ptr [rax+rax+00h]
0x18005c71a  add     rsp, 38h
0x18005c71e  pop     r15
0x18005c720  pop     r14
0x18005c722  pop     r13
0x18005c724  pop     r12
0x18005c726  pop     rdi
0x18005c727  pop     rsi
0x18005c728  pop     rbp
0x18005c729  pop     rbx
0x18005c72a  retn
0x18005c72c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c733  cmp     [rcx+48h], bp
0x18005c737  jz      loc_18005C5D9
0x18005c73d  mov     rcx, [rcx+40h]
0x18005c741  mov     r9d, 69h ; 'i'
0x18005c747  mov     r8d, r14d
0x18005c74a  mov     [rsp+78h+Timeout], r12
0x18005c74f  mov     dl, 5
0x18005c751  call    WPP_RECORDER_SF_
0x18005c756  jmp     loc_18005C5D9
0x18005c75b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c762  xor     eax, eax
0x18005c764  cmp     [rcx+48h], ax
0x18005c768  jz      short loc_18005C6EC
0x18005c76a  mov     rcx, [rcx+40h]
0x18005c76e  lea     r9d, [rax+6Bh]
0x18005c772  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c779  mov     r8d, edi
0x18005c77c  mov     dl, 5
0x18005c77e  mov     [rsp+78h+Timeout], rax
0x18005c783  call    WPP_RECORDER_SF_
0x18005c788  jmp     loc_18005C6EC
0x18005c78d  mov     eax, [rdi+38h]
0x18005c790  mov     r9d, 6Ah ; 'j'
0x18005c796  mov     rcx, [rcx+40h]
0x18005c79a  mov     r8d, r14d
0x18005c79d  mov     [rsp+78h+var_50], eax
0x18005c7a1  mov     dl, 5
0x18005c7a3  mov     [rsp+78h+Timeout], r12
0x18005c7a8  call    WPP_RECORDER_SF_D
0x18005c7ad  jmp     loc_18005C635
```
