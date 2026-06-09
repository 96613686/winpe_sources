# CKsDevice::PassiveWakeDevice(_IRP *)

- ea: `0x18005c3d0`
- end: `0x18005c612`
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
- `0x180019c60`
- `0x18005c3d0`
- `0x18005c618`
- `0x18005c69c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18005c4e8`
- `ntoskrnl!KeReleaseMutex` at `0x18005c4e8`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18005c525`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18005c525`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18005c56e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18005c56e`
- `ntoskrnl!PoSetPowerState` at `0x18005c516`
- `ntoskrnl!PoSetPowerState` at `0x18005c516`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005c4ac`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005c4ac`

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
0x18005c3d0  push    rbx
0x18005c3d2  push    rbp
0x18005c3d3  push    rsi
0x18005c3d4  push    rdi
0x18005c3d5  push    r12
0x18005c3d7  push    r13
0x18005c3d9  push    r14
0x18005c3db  push    r15
0x18005c3dd  sub     rsp, 38h
0x18005c3e1  mov     r15, [rcx+0B8h]
0x18005c3e8  mov     rsi, rcx
0x18005c3eb  mov     rax, [r15+28h]
0x18005c3ef  mov     [rsp+78h+DeviceObject], rax
0x18005c3f7  mov     rax, [rax+40h]
0x18005c3fb  mov     rdx, [rax]
0x18005c3fe  mov     rdi, [rdx+168h]
0x18005c405  mov     rcx, [rdi+18h]; struct _DEVICE_OBJECT *
0x18005c409  lea     rbx, [rdi-0C8h]
0x18005c410  call    ?GetDeviceHeaderEx@CKsDevice@@SAPEAU_KSDEVICE_HEADER_EX@@PEAU_DEVICE_OBJECT@@@Z; CKsDevice::GetDeviceHeaderEx(_DEVICE_OBJECT *)
0x18005c415  mov     r13, rax
0x18005c418  xor     ebp, ebp
0x18005c41a  lea     rax, WPP_RECORDER_INITIALIZED
0x18005c421  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005c428  lea     r12, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c42f  lea     r14d, [rbp+1]
0x18005c433  jnz     loc_18005C58C
0x18005c439  mov     rax, [rbx]
0x18005c43c  mov     rcx, rbx
0x18005c43f  mov     rax, [rax+28h]
0x18005c443  call    _guard_dispatch_icall
0x18005c448  mov     rax, [rdi]
0x18005c44b  test    rax, rax
0x18005c44e  jz      short loc_18005C495
0x18005c450  mov     rax, [rax]
0x18005c453  test    rax, rax
0x18005c456  jz      short loc_18005C495
0x18005c458  mov     rax, [rax+60h]
0x18005c45c  test    rax, rax
0x18005c45f  jz      short loc_18005C495
0x18005c461  mov     r9d, [rdi+38h]
0x18005c465  mov     rdx, rsi
0x18005c468  mov     r8d, [r15+18h]
0x18005c46c  mov     rcx, rdi
0x18005c46f  call    _guard_dispatch_icall
0x18005c474  lea     rax, WPP_RECORDER_INITIALIZED
0x18005c47b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005c482  jz      short loc_18005C495
0x18005c484  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c48b  cmp     [rcx+48h], bp
0x18005c48f  jnz     loc_18005C5ED
0x18005c495  lea     r12, [rbx+2C8h]
0x18005c49c  mov     [rsp+78h+Timeout], rbp; Timeout
0x18005c4a1  mov     rcx, r12; Object
0x18005c4a4  xor     r9d, r9d; Alertable
0x18005c4a7  xor     r8d, r8d; WaitMode
0x18005c4aa  xor     edx, edx; WaitReason
0x18005c4ac  call    cs:__imp_KeWaitForSingleObject
0x18005c4b3  nop     dword ptr [rax+rax+00h]
0x18005c4b8  mov     ebp, [r15+18h]
0x18005c4bc  lea     r14, [rbx+2B8h]
0x18005c4c3  mov     [rdi+38h], ebp
0x18005c4c6  mov     rdi, [r14]
0x18005c4c9  jmp     short loc_18005C4DE
0x18005c4cb  mov     rcx, [rdi+10h]
0x18005c4cf  mov     rax, [rcx]
0x18005c4d2  mov     rax, [rax+20h]
0x18005c4d6  call    _guard_dispatch_icall
0x18005c4db  mov     rdi, [rdi]
0x18005c4de  cmp     rdi, r14
0x18005c4e1  jnz     short loc_18005C4CB
0x18005c4e3  xor     edx, edx; Wait
0x18005c4e5  mov     rcx, r12; Mutex
0x18005c4e8  call    cs:__imp_KeReleaseMutex
0x18005c4ef  nop     dword ptr [rax+rax+00h]
0x18005c4f4  mov     rax, [rbx]
0x18005c4f7  mov     rcx, rbx
0x18005c4fa  mov     rax, [rax+30h]
0x18005c4fe  call    _guard_dispatch_icall
0x18005c503  mov     r8d, [r15+18h]; State
0x18005c507  mov     edi, 1
0x18005c50c  mov     rcx, [rsp+78h+DeviceObject]; DeviceObject
0x18005c514  mov     edx, edi; Type
0x18005c516  call    cs:__imp_PoSetPowerState
0x18005c51d  nop     dword ptr [rax+rax+00h]
0x18005c522  mov     rcx, rsi; Irp
0x18005c525  call    cs:__imp_PoStartNextPowerIrp
0x18005c52c  nop     dword ptr [rax+rax+00h]
0x18005c531  xor     r8d, r8d; int
0x18005c534  mov     rdx, rsi; struct _IRP *
0x18005c537  call    ?CompleteIrp@CKsDevice@@QEAAJPEAU_IRP@@J@Z; CKsDevice::CompleteIrp(_IRP *,long)
0x18005c53c  lea     rax, WPP_RECORDER_INITIALIZED
0x18005c543  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005c54a  jnz     short loc_18005C5BB
0x18005c54c  cmp     ebp, edi
0x18005c54e  jnz     short loc_18005C562
0x18005c550  mov     rcx, rbx; this
0x18005c553  call    ?RedispatchPendingCreates@CKsDevice@@QEAAXXZ; CKsDevice::RedispatchPendingCreates(void)
0x18005c558  xor     edx, edx; unsigned __int8
0x18005c55a  mov     rcx, rbx; this
0x18005c55d  call    ?RedispatchPendedIrps@CKsDevice@@AEAAXE@Z; CKsDevice::RedispatchPendedIrps(uchar)
0x18005c562  mov     r8d, 20h ; ' '; RemlockSize
0x18005c568  mov     rdx, rsi; Tag
0x18005c56b  mov     rcx, r13; RemoveLock
0x18005c56e  call    cs:__imp_IoReleaseRemoveLockEx
0x18005c575  nop     dword ptr [rax+rax+00h]
0x18005c57a  add     rsp, 38h
0x18005c57e  pop     r15
0x18005c580  pop     r14
0x18005c582  pop     r13
0x18005c584  pop     r12
0x18005c586  pop     rdi
0x18005c587  pop     rsi
0x18005c588  pop     rbp
0x18005c589  pop     rbx
0x18005c58a  retn
0x18005c58c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c593  cmp     [rcx+48h], bp
0x18005c597  jz      loc_18005C439
0x18005c59d  mov     rcx, [rcx+40h]
0x18005c5a1  mov     r9d, 69h ; 'i'
0x18005c5a7  mov     r8d, r14d
0x18005c5aa  mov     [rsp+78h+Timeout], r12
0x18005c5af  mov     dl, 5
0x18005c5b1  call    WPP_RECORDER_SF_
0x18005c5b6  jmp     loc_18005C439
0x18005c5bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c5c2  xor     eax, eax
0x18005c5c4  cmp     [rcx+48h], ax
0x18005c5c8  jz      short loc_18005C54C
0x18005c5ca  mov     rcx, [rcx+40h]
0x18005c5ce  lea     r9d, [rax+6Bh]
0x18005c5d2  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c5d9  mov     r8d, edi
0x18005c5dc  mov     dl, 5
0x18005c5de  mov     [rsp+78h+Timeout], rax
0x18005c5e3  call    WPP_RECORDER_SF_
0x18005c5e8  jmp     loc_18005C54C
0x18005c5ed  mov     eax, [rdi+38h]
0x18005c5f0  mov     r9d, 6Ah ; 'j'
0x18005c5f6  mov     rcx, [rcx+40h]
0x18005c5fa  mov     r8d, r14d
0x18005c5fd  mov     [rsp+78h+var_50], eax
0x18005c601  mov     dl, 5
0x18005c603  mov     [rsp+78h+Timeout], r12
0x18005c608  call    WPP_RECORDER_SF_D
0x18005c60d  jmp     loc_18005C495
```
