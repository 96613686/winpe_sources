# CKsDevice::CompleteSystemPowerIrp(_DEVICE_OBJECT *,_IRP *,CKsDevice *)

- ea: `0x18000bb60`
- end: `0x18000c04f`
- name: `?CompleteSystemPowerIrp@CKsDevice@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAV1@@Z`
- size: `1263`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, struct CKsDevice *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18000bb60`
- `0x18000c630`
- `0x180013a88`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x18000bdaa`
- `ntoskrnl!KeClearEvent` at `0x18000bdaa`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18000bd1e`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18000bff1`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18000bd1e`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18000bff1`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18000bc06`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18000bcb0`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18000bc06`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18000bcb0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000beec`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000bf91`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000beec`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000bf91`
- `ntoskrnl!PoRequestPowerIrp` at `0x18000bc52`
- `ntoskrnl!PoRequestPowerIrp` at `0x18000bd02`
- `ntoskrnl!PoRequestPowerIrp` at `0x18000bc52`
- `ntoskrnl!PoRequestPowerIrp` at `0x18000bd02`

## pseudocode

```c
__int64 __fastcall CKsDevice::CompleteSystemPowerIrp(struct _DEVICE_OBJECT *a1, struct _IRP *a2, struct CKsDevice *a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  NTSTATUS Status; // edi
  char *DeviceExtension; // rbp
  __int64 *v8; // rdx
  __int64 LowPart; // rax
  POWER_STATE v10; // ebx
  struct _IO_REMOVE_LOCK *v11; // r15
  NTSTATUS v12; // eax
  int v13; // edx
  struct _DEVICE_OBJECT *PhysicalDeviceObject; // rcx
  NTSTATUS v15; // eax
  unsigned int v16; // ebx
  NTSTATUS v17; // eax
  char v18; // di
  PDEVICE_OBJECT v20; // rcx
  int v21; // r9d
  int v22; // edx
  int v23; // edx
  int v24; // edx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Status = a2->IoStatus.Status;
  DeviceExtension = (char *)a3->m_Ext.Public.FunctionalDeviceObject->DeviceExtension;
  v8 = WPP_50288c75019938eedd86f8b19427641e_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v8) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v8,
      1,
      121,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    v8 = WPP_50288c75019938eedd86f8b19427641e_Traceguids;
  }
  if ( Status < 0 )
  {
LABEL_46:
    a3->m_SxIrp = 0;
    PoStartNextPowerIrp(a2);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v24) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v24,
        1,
        131,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
        Status);
    }
    goto LABEL_19;
  }
  LowPart = (int)CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  v10.SystemState = (SYSTEM_POWER_STATE)a3->m_DeviceStateMap[LowPart];
  if ( v10.SystemState == a3->m_Ext.Public.DevicePowerState )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v8) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        1,
        130,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    goto LABEL_18;
  }
  v11 = (struct _IO_REMOVE_LOCK *)(DeviceExtension - 32);
  if ( (_DWORD)LowPart == 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v8) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        1,
        122,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    v12 = IoAcquireRemoveLockEx(v11, CKsDevice::FinalCompleteDevicePowerIrp, File, 1u, 0x20u);
    if ( !v12 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v13) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          1,
          123,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
          v10.SystemState);
      }
      v17 = PoRequestPowerIrp(
              a3->m_Ext.Public.PhysicalDeviceObject,
              CurrentStackLocation->MinorFunction,
              v10,
              CKsDevice::FinalCompleteDevicePowerIrp,
              a3,
              0);
      v18 = v17;
      if ( v17 < 0 )
      {
        IoReleaseRemoveLockEx(v11, CKsDevice::FinalCompleteDevicePowerIrp, 0x20u);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(v22) = 5;
            WPP_RECORDER_SF_DD(
              WPP_GLOBAL_Control->DeviceExtension,
              v22,
              1,
              124,
              (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
              v10.SystemState,
              v18);
          }
        }
      }
      goto LABEL_18;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = WPP_GLOBAL_Control;
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        v21 = 125;
        goto LABEL_32;
      }
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v8) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        1,
        126,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
        CurrentStackLocation->Parameters.Read.ByteOffset.LowPart);
    }
    v12 = IoAcquireRemoveLockEx(v11, CKsDevice::FinalCompleteDevicePowerIrp, File, 1u, 0x20u);
    if ( !v12 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v13) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          1,
          127,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
          v10.SystemState);
      }
      PhysicalDeviceObject = a3->m_Ext.Public.PhysicalDeviceObject;
      a3->m_SxIrp = a2;
      v15 = PoRequestPowerIrp(
              PhysicalDeviceObject,
              CurrentStackLocation->MinorFunction,
              v10,
              CKsDevice::FinalCompleteDevicePowerIrp,
              a3,
              0);
      LOBYTE(Status) = v15;
      if ( v15 >= 0 )
        return (unsigned int)-1073741802;
      IoReleaseRemoveLockEx(v11, CKsDevice::FinalCompleteDevicePowerIrp, 0x20u);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v23) = 5;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v23,
          1,
          128,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
          v10.SystemState,
          Status);
      }
      goto LABEL_46;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = WPP_GLOBAL_Control;
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        v21 = 129;
LABEL_32:
        LOBYTE(v13) = 5;
        WPP_RECORDER_SF_D(
          v20->DeviceExtension,
          v13,
          1,
          v21,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
          v12);
      }
    }
  }
LABEL_18:
  PoStartNextPowerIrp(a2);
LABEL_19:
  v16 = 0;
  if ( CurrentStackLocation && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1 )
    KeClearEvent(&a3->m_BlockPoweredDownEvent);
  return v16;
}

```

## disassembly

```asm
0x18000bb60  push    rbx
0x18000bb62  push    rbp
0x18000bb63  push    rsi
0x18000bb64  push    rdi
0x18000bb65  push    r12
0x18000bb67  push    r13
0x18000bb69  push    r14
0x18000bb6b  push    r15
0x18000bb6d  sub     rsp, 48h
0x18000bb71  mov     rax, [r8+0E0h]
0x18000bb78  mov     rsi, r8
0x18000bb7b  mov     r13, [rdx+0B8h]
0x18000bb82  mov     r12, rdx
0x18000bb85  mov     edi, [rdx+30h]
0x18000bb88  mov     rbp, [rax+40h]
0x18000bb8c  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000bb93  xor     r14d, r14d
0x18000bb96  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000bb9d  lea     rdx, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18000bba4  jnz     loc_18000BD4D
0x18000bbaa  test    edi, edi
0x18000bbac  js      loc_18000BFE7
0x18000bbb2  movsxd  rax, dword ptr [r13+18h]
0x18000bbb6  mov     ebx, [rsi+rax*4+298h]
0x18000bbbd  cmp     ebx, [rsi+100h]
0x18000bbc3  jz      loc_18000BD6B
0x18000bbc9  lea     r15, [rbp-20h]
0x18000bbcd  cmp     eax, 1
0x18000bbd0  jz      loc_18000BC72
0x18000bbd6  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000bbdd  jnz     loc_18000BE0D
0x18000bbe3  mov     r14d, 20h ; ' '
0x18000bbe9  lea     rbp, ?FinalCompleteDevicePowerIrp@CKsDevice@@CAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAV1@PEAU_IO_STATUS_BLOCK@@@Z; CKsDevice::FinalCompleteDevicePowerIrp(_DEVICE_OBJECT *,uchar,_POWER_STATE,CKsDevice *,_IO_STATUS_BLOCK *)
0x18000bbf0  lea     r8, File; File
0x18000bbf7  mov     [rsp+88h+RemlockSize], r14d; RemlockSize
0x18000bbfc  mov     rdx, rbp; Tag
0x18000bbff  mov     rcx, r15; RemoveLock
0x18000bc02  lea     r9d, [r14-1Fh]; Line
0x18000bc06  call    cs:__imp_IoAcquireRemoveLockEx
0x18000bc0d  nop     dword ptr [rax+rax+00h]
0x18000bc12  xor     edi, edi
0x18000bc14  test    eax, eax
0x18000bc16  jnz     loc_18000BDB8
0x18000bc1c  lea     rax, WPP_RECORDER_INITIALIZED
0x18000bc23  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000bc2a  jnz     loc_18000BF4D
0x18000bc30  mov     rcx, [rsi+0E8h]; DeviceObject
0x18000bc37  mov     r9, rbp; CompletionFunction
0x18000bc3a  mov     [rsi+3C0h], r12
0x18000bc41  mov     r8d, ebx; PowerState
0x18000bc44  mov     dl, [r13+1]; MinorFunction
0x18000bc48  mov     [rsp+88h+Irp], rdi; Irp
0x18000bc4d  mov     qword ptr [rsp+88h+RemlockSize], rsi; Context
0x18000bc52  call    cs:__imp_PoRequestPowerIrp
0x18000bc59  nop     dword ptr [rax+rax+00h]
0x18000bc5e  mov     edi, eax
0x18000bc60  test    eax, eax
0x18000bc62  js      loc_18000BF88
0x18000bc68  mov     ebx, 0C0000016h
0x18000bc6d  jmp     loc_18000BD39
0x18000bc72  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000bc79  jz      short loc_18000BC8D
0x18000bc7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc82  cmp     [rcx+48h], r14w
0x18000bc87  jnz     loc_18000BE9A
0x18000bc8d  mov     r14d, 20h ; ' '
0x18000bc93  lea     rbp, ?FinalCompleteDevicePowerIrp@CKsDevice@@CAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAV1@PEAU_IO_STATUS_BLOCK@@@Z; CKsDevice::FinalCompleteDevicePowerIrp(_DEVICE_OBJECT *,uchar,_POWER_STATE,CKsDevice *,_IO_STATUS_BLOCK *)
0x18000bc9a  lea     r8, File; File
0x18000bca1  mov     [rsp+88h+RemlockSize], r14d; RemlockSize
0x18000bca6  mov     rdx, rbp; Tag
0x18000bca9  mov     rcx, r15; RemoveLock
0x18000bcac  lea     r9d, [r14-1Fh]; Line
0x18000bcb0  call    cs:__imp_IoAcquireRemoveLockEx
0x18000bcb7  nop     dword ptr [rax+rax+00h]
0x18000bcbc  xor     edi, edi
0x18000bcbe  test    eax, eax
0x18000bcc0  jnz     loc_18000BE42
0x18000bcc6  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000bccd  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000bcd4  jz      short loc_18000BCE7
0x18000bcd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcdd  cmp     [rcx+48h], di
0x18000bce1  jnz     loc_18000BEB9
0x18000bce7  mov     dl, [r13+1]; MinorFunction
0x18000bceb  mov     r9, rbp; CompletionFunction
0x18000bcee  mov     rcx, [rsi+0E8h]; DeviceObject
0x18000bcf5  mov     r8d, ebx; PowerState
0x18000bcf8  mov     [rsp+88h+Irp], rdi; Irp
0x18000bcfd  mov     qword ptr [rsp+88h+RemlockSize], rsi; Context
0x18000bd02  call    cs:__imp_PoRequestPowerIrp
0x18000bd09  nop     dword ptr [rax+rax+00h]
0x18000bd0e  mov     edi, eax
0x18000bd10  test    eax, eax
0x18000bd12  js      loc_18000BEE3
0x18000bd18  xor     r14d, r14d
0x18000bd1b  mov     rcx, r12; Irp
0x18000bd1e  call    cs:__imp_PoStartNextPowerIrp
0x18000bd25  nop     dword ptr [rax+rax+00h]
0x18000bd2a  mov     ebx, r14d
0x18000bd2d  test    r13, r13
0x18000bd30  jz      short loc_18000BD39
0x18000bd32  cmp     dword ptr [r13+18h], 1
0x18000bd37  jnz     short loc_18000BDA3
0x18000bd39  mov     eax, ebx
0x18000bd3b  add     rsp, 48h
0x18000bd3f  pop     r15
0x18000bd41  pop     r14
0x18000bd43  pop     r13
0x18000bd45  pop     r12
0x18000bd47  pop     rdi
0x18000bd48  pop     rsi
0x18000bd49  pop     rbp
0x18000bd4a  pop     rbx
0x18000bd4b  retn
0x18000bd4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd54  cmp     [rcx+48h], r14w
0x18000bd59  jnz     loc_18000BE74
0x18000bd5f  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000bd66  jmp     loc_18000BBAA
0x18000bd6b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000bd72  jz      short loc_18000BD1B
0x18000bd74  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd7b  cmp     [rcx+48h], r14w
0x18000bd80  jz      short loc_18000BD1B
0x18000bd82  mov     rcx, [rcx+40h]
0x18000bd86  mov     r9d, 82h
0x18000bd8c  mov     qword ptr [rsp+88h+RemlockSize], rdx
0x18000bd91  mov     r8d, 1
0x18000bd97  mov     dl, 5
0x18000bd99  call    WPP_RECORDER_SF_
0x18000bd9e  jmp     loc_18000BD1B
0x18000bda3  lea     rcx, [rsi+428h]; Event
0x18000bdaa  call    cs:__imp_KeClearEvent
0x18000bdb1  nop     dword ptr [rax+rax+00h]
0x18000bdb6  jmp     short loc_18000BD39
0x18000bdb8  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000bdbf  xor     r14d, r14d
0x18000bdc2  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000bdc9  jz      loc_18000BD1B
0x18000bdcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdd6  cmp     [rcx+48h], r14w
0x18000bddb  jz      loc_18000BD1B
0x18000bde1  mov     r9d, 81h
0x18000bde7  mov     rcx, [rcx+40h]
0x18000bdeb  mov     r8d, 1
0x18000bdf1  mov     dword ptr [rsp+88h+Irp], eax
0x18000bdf5  mov     dl, 5
0x18000bdf7  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18000bdfe  mov     qword ptr [rsp+88h+RemlockSize], rax
0x18000be03  call    WPP_RECORDER_SF_D
0x18000be08  jmp     loc_18000BD1B
0x18000be0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be14  cmp     [rcx+48h], r14w
0x18000be19  jz      loc_18000BBE3
0x18000be1f  mov     rcx, [rcx+40h]
0x18000be23  mov     r9d, 7Eh ; '~'
0x18000be29  mov     dword ptr [rsp+88h+Irp], eax
0x18000be2d  mov     qword ptr [rsp+88h+RemlockSize], rdx
0x18000be32  mov     dl, 5
0x18000be34  lea     r8d, [r9-7Dh]
0x18000be38  call    WPP_RECORDER_SF_D
0x18000be3d  jmp     loc_18000BBE3
0x18000be42  lea     rcx, WPP_RECORDER_INITIALIZED
0x18000be49  xor     r14d, r14d
0x18000be4c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18000be53  jz      loc_18000BD1B
0x18000be59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be60  cmp     [rcx+48h], r14w
0x18000be65  jz      loc_18000BD1B
0x18000be6b  lea     r9d, [r14+7Dh]
0x18000be6f  jmp     loc_18000BDE7
0x18000be74  mov     rcx, [rcx+40h]
0x18000be78  mov     r9d, 79h ; 'y'
0x18000be7e  mov     qword ptr [rsp+88h+RemlockSize], rdx
0x18000be83  mov     dl, 5
0x18000be85  lea     r8d, [r9-78h]
0x18000be89  call    WPP_RECORDER_SF_
0x18000be8e  lea     rdx, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18000be95  jmp     loc_18000BD5F
0x18000be9a  mov     rcx, [rcx+40h]
0x18000be9e  mov     r9d, 7Ah ; 'z'
0x18000bea4  mov     qword ptr [rsp+88h+RemlockSize], rdx
0x18000bea9  mov     dl, 5
0x18000beab  lea     r8d, [r9-79h]
0x18000beaf  call    WPP_RECORDER_SF_
0x18000beb4  jmp     loc_18000BC8D
0x18000beb9  mov     rcx, [rcx+40h]
0x18000bebd  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18000bec4  mov     r9d, 7Bh ; '{'
0x18000beca  mov     dword ptr [rsp+88h+Irp], ebx
0x18000bece  mov     dl, 5
0x18000bed0  mov     qword ptr [rsp+88h+RemlockSize], rax
0x18000bed5  lea     r8d, [r9-7Ah]
0x18000bed9  call    WPP_RECORDER_SF_D
0x18000bede  jmp     loc_18000BCE7
0x18000bee3  mov     r8d, r14d; RemlockSize
0x18000bee6  mov     rdx, rbp; Tag
0x18000bee9  mov     rcx, r15; RemoveLock
0x18000beec  call    cs:__imp_IoReleaseRemoveLockEx
0x18000bef3  nop     dword ptr [rax+rax+00h]
0x18000bef8  lea     rax, WPP_RECORDER_INITIALIZED
0x18000beff  xor     r14d, r14d
0x18000bf02  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000bf09  jz      loc_18000BD1B
0x18000bf0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf16  cmp     [rcx+48h], r14w
0x18000bf1b  jz      loc_18000BD1B
0x18000bf21  mov     rcx, [rcx+40h]
0x18000bf25  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18000bf2c  mov     [rsp+88h+var_58], edi
0x18000bf30  lea     r9d, [r14+7Ch]
0x18000bf34  mov     dword ptr [rsp+88h+Irp], ebx
0x18000bf38  lea     r8d, [r14+1]
0x18000bf3c  mov     dl, 5
0x18000bf3e  mov     qword ptr [rsp+88h+RemlockSize], rax
0x18000bf43  call    WPP_RECORDER_SF_DD
0x18000bf48  jmp     loc_18000BD1B
0x18000bf4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf54  cmp     [rcx+48h], di
0x18000bf58  jz      loc_18000BC30
0x18000bf5e  mov     rcx, [rcx+40h]
0x18000bf62  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18000bf69  mov     r9d, 7Fh
0x18000bf6f  mov     dword ptr [rsp+88h+Irp], ebx
0x18000bf73  mov     dl, 5
0x18000bf75  mov     qword ptr [rsp+88h+RemlockSize], rax
0x18000bf7a  lea     r8d, [r9-7Eh]
0x18000bf7e  call    WPP_RECORDER_SF_D
0x18000bf83  jmp     loc_18000BC30
0x18000bf88  mov     r8d, r14d; RemlockSize
0x18000bf8b  mov     rdx, rbp; Tag
0x18000bf8e  mov     rcx, r15; RemoveLock
0x18000bf91  call    cs:__imp_IoReleaseRemoveLockEx
0x18000bf98  nop     dword ptr [rax+rax+00h]
0x18000bf9d  lea     rax, WPP_RECORDER_INITIALIZED
0x18000bfa4  xor     r14d, r14d
0x18000bfa7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000bfae  jz      short loc_18000BFE7
0x18000bfb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bfb7  cmp     [rcx+48h], r14w
0x18000bfbc  jz      short loc_18000BFE7
0x18000bfbe  mov     rcx, [rcx+40h]
0x18000bfc2  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18000bfc9  mov     [rsp+88h+var_58], edi
0x18000bfcd  lea     r8d, [r14+1]
0x18000bfd1  mov     dword ptr [rsp+88h+Irp], ebx
0x18000bfd5  mov     r9d, 80h
0x18000bfdb  mov     dl, 5
0x18000bfdd  mov     qword ptr [rsp+88h+RemlockSize], rax
0x18000bfe2  call    WPP_RECORDER_SF_DD
0x18000bfe7  mov     rcx, r12; Irp
0x18000bfea  mov     [rsi+3C0h], r14
0x18000bff1  call    cs:__imp_PoStartNextPowerIrp
0x18000bff8  nop     dword ptr [rax+rax+00h]
0x18000bffd  lea     rax, WPP_RECORDER_INITIALIZED
0x18000c004  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000c00b  jz      loc_18000BD2A
0x18000c011  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c018  cmp     [rcx+48h], r14w
0x18000c01d  jz      loc_18000BD2A
0x18000c023  mov     rcx, [rcx+40h]
0x18000c027  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18000c02e  mov     r9d, 83h
0x18000c034  mov     dword ptr [rsp+88h+Irp], edi
0x18000c038  mov     r8d, 1
0x18000c03e  mov     qword ptr [rsp+88h+RemlockSize], rax
0x18000c043  mov     dl, 5
0x18000c045  call    WPP_RECORDER_SF_D
0x18000c04a  jmp     loc_18000BD2A
```
