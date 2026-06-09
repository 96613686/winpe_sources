# I8xReinitializeHardware

- ea: `0x14001e950`
- end: `0x14001ed92`
- name: `I8xReinitializeHardware`
- size: `1090`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004530`
- `0x140007b10`
- `0x140008e80`
- `0x14000b72c`
- `0x14000b8a8`
- `0x140017008`
- `0x14001b924`
- `0x14001ce6c`
- `0x14001e950`
- `0x14001eda0`
- `0x14001eea0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001ed79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ed79`
- `ntoskrnl!IofCompleteRequest` at `0x14001ec8c`
- `ntoskrnl!IofCompleteRequest` at `0x14001ed2f`
- `ntoskrnl!IofCompleteRequest` at `0x14001ec8c`
- `ntoskrnl!IofCompleteRequest` at `0x14001ed2f`
- `ntoskrnl!PoSetPowerState` at `0x14001ebc2`
- `ntoskrnl!PoSetPowerState` at `0x14001ecff`
- `ntoskrnl!PoSetPowerState` at `0x14001ebc2`
- `ntoskrnl!PoSetPowerState` at `0x14001ecff`
- `ntoskrnl!IoFreeWorkItem` at `0x14001ed68`
- `ntoskrnl!IoFreeWorkItem` at `0x14001ed68`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001ec7b`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001ed1e`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001ec7b`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001ed1e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001ecad`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001ed4d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001ecad`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001ed4d`

## pseudocode

```c
void __fastcall I8xReinitializeHardware(PDEVICE_OBJECT DeviceObject, PIO_WORKITEM *Context)
{
  int v3; // edi
  int v4; // esi
  IRP *v5; // r15
  IRP *v6; // rbp
  PDRIVER_CONTROL DeviceRoutine; // r12
  unsigned int v8; // ebx
  int v9; // edx
  __int64 v10; // rcx
  int v11; // edx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  PDRIVER_CONTROL v13; // rcx
  PDRIVER_CONTROL v14; // rax
  struct _IO_STACK_LOCATION *v15; // rdx
  char *DeviceContext; // [rsp+30h] [rbp-48h]
  int v17; // [rsp+88h] [rbp+10h] BYREF
  int v18; // [rsp+90h] [rbp+18h] BYREF
  PDRIVER_CONTROL v19; // [rsp+98h] [rbp+20h]

  v3 = -1073741823;
  v4 = -1073741823;
  v5 = (IRP *)Context[2];
  v6 = (IRP *)Context[1];
  DeviceRoutine = WPP_MAIN_CB.Queue.Wcb.DeviceRoutine;
  v18 = -1073741823;
  v17 = -1073741823;
  DeviceContext = (char *)WPP_MAIN_CB.Queue.Wcb.DeviceContext;
  v19 = WPP_MAIN_CB.Queue.Wcb.DeviceRoutine;
  if ( v5
    || (v8 = 0, (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) != 0)
    && WPP_MAIN_CB.Queue.Wcb.DeviceContext
    && *((_DWORD *)WPP_MAIN_CB.Queue.Wcb.DeviceContext + 20) == 1 )
  {
    v8 = 0x10000;
  }
  if ( v6
    || (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 2) != 0
    && WPP_MAIN_CB.Queue.Wcb.DeviceRoutine
    && *((_DWORD *)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine + 20) == 1 )
  {
    v8 |= 0x20000u;
  }
  if ( *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters || (unsigned __int8)I8xSanityCheckResources() )
  {
    I8xToggleInterrupts(0);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        22,
        32,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
    I8xInitializeHardware(&v18, &v17, v8);
    v3 = v18;
    if ( (int)(v18 + 0x80000000) < 0 || v18 == -1073741667 )
    {
      v4 = v17;
      goto LABEL_26;
    }
    v4 = v17;
  }
  else
  {
    if ( (v8 & 0x10000) != 0 )
      I8xManuallyRemoveDevice(DeviceContext);
    if ( (v8 & 0x20000) != 0 )
      I8xManuallyRemoveDevice(DeviceRoutine);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      17,
      33,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
      v3);
LABEL_26:
  if ( ((v4 + 0x80000000) & 0x80000000) == 0
    && v4 != -1073741667
    && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      17,
      34,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
      v4);
  }
  if ( ((v3 + 0x80000000) & 0x80000000) != 0
    || v3 == -1073741667
    || ((v4 + 0x80000000) & 0x80000000) != 0
    || v4 == -1073741667 )
  {
    LOBYTE(v10) = 1;
    I8xToggleInterrupts(v10);
  }
  if ( v4 >= 0 || v4 == -1073741667 || v4 == -1073741643 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        14,
        35,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
        v4);
    if ( v6 )
    {
      CurrentStackLocation = v6->Tail.Overlay.CurrentStackLocation;
      v13 = v19;
      *((_DWORD *)v19 + 20) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
      *((_DWORD *)v13 + 22) = 0;
      PoSetPowerState(
        *(PDEVICE_OBJECT *)v13,
        CurrentStackLocation->Parameters.Power.Type,
        CurrentStackLocation->Parameters.Power.State);
    }
    v14 = v19;
    if ( !*((_WORD *)v19 + 269) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          14,
          36,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
        v14 = v19;
      }
      I8xMouseConnectInterruptAndEnable(v14, 0);
      v14 = v19;
    }
    if ( v4 != -1073741643 && v4 != -1073741667 )
    {
      if ( *((_BYTE *)v14 + 1108) )
      {
        I8xMouseEnableTransmission(v14);
      }
      else
      {
        *((_WORD *)v14 + 506) = -1;
        *((_WORD *)v14 + 280) = 0;
        I8xResetMouse(v14);
      }
    }
    v4 = 0;
  }
  if ( v6 )
  {
    v6->IoStatus.Status = v4;
    v6->IoStatus.Information = 0;
    PoStartNextPowerIrp(v6);
    IofCompleteRequest(v6, 0);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)v19 + 40), v6, 0x20u);
  }
  if ( (int)(v3 + 0x80000000) < 0 || v3 == -1073741667 )
  {
    if ( v5 )
    {
      v15 = v5->Tail.Overlay.CurrentStackLocation;
      *((_DWORD *)DeviceContext + 20) = v15->Parameters.Read.ByteOffset.LowPart;
      *((_DWORD *)DeviceContext + 22) = 0;
      PoSetPowerState(*(PDEVICE_OBJECT *)DeviceContext, v15->Parameters.Power.Type, v15->Parameters.Power.State);
    }
    v3 = 0;
  }
  if ( v5 )
  {
    v5->IoStatus.Status = v3;
    v5->IoStatus.Information = 0;
    PoStartNextPowerIrp(v5);
    IofCompleteRequest(v5, 0);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceContext + 40), v5, 0x20u);
  }
  I8xSetPowerFlag(0x10000000, 0);
  IoFreeWorkItem(*Context);
  ExFreePoolWithTag(Context, 0);
}

```

## disassembly

```asm
0x14001e950  mov     rax, rsp
0x14001e953  push    rdi
0x14001e954  push    r13
0x14001e956  push    r14
0x14001e958  push    r15
0x14001e95a  sub     rsp, 58h
0x14001e95e  mov     r14, rdx
0x14001e961  mov     [rax+8], rbx
0x14001e965  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+20h
0x14001e96c  mov     edi, 0C0000001h
0x14001e971  mov     [rax-28h], rbp
0x14001e975  xor     r13d, r13d
0x14001e978  mov     [rax-30h], rsi
0x14001e97c  mov     esi, edi
0x14001e97e  mov     r15, [r14+10h]
0x14001e982  mov     rbp, [r14+8]
0x14001e986  mov     [rax-38h], r12
0x14001e98a  mov     r12, qword ptr cs:WPP_MAIN_CB.Queue+18h
0x14001e991  mov     [rax+18h], edi
0x14001e994  mov     [rax+10h], edi
0x14001e997  mov     [rsp+78h+arg_18], r12
0x14001e99f  mov     [rsp+78h+var_48], rdx
0x14001e9a4  test    r15, r15
0x14001e9a7  jnz     short loc_14001E9C5
0x14001e9a9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001e9b0  mov     ebx, r13d
0x14001e9b3  mov     ecx, [rax]
0x14001e9b5  test    cl, 1
0x14001e9b8  jz      short loc_14001E9CA
0x14001e9ba  test    rdx, rdx
0x14001e9bd  jz      short loc_14001E9CA
0x14001e9bf  cmp     dword ptr [rdx+50h], 1
0x14001e9c3  jnz     short loc_14001E9CA
0x14001e9c5  mov     ebx, 10000h
0x14001e9ca  test    rbp, rbp
0x14001e9cd  jnz     short loc_14001E9EA
0x14001e9cf  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001e9d6  mov     ecx, [rax]
0x14001e9d8  test    cl, 2
0x14001e9db  jz      short loc_14001E9EE
0x14001e9dd  test    r12, r12
0x14001e9e0  jz      short loc_14001E9EE
0x14001e9e2  cmp     dword ptr [r12+50h], 1
0x14001e9e8  jnz     short loc_14001E9EE
0x14001e9ea  bts     ebx, 11h
0x14001e9ee  cmp     qword ptr cs:WPP_MAIN_CB.Queue+28h, 0
0x14001e9f6  jnz     short loc_14001EA2D
0x14001e9f8  call    I8xSanityCheckResources
0x14001e9fd  test    al, al
0x14001e9ff  jnz     short loc_14001EA2D
0x14001ea01  bt      ebx, 10h
0x14001ea05  jnb     short loc_14001EA11
0x14001ea07  mov     rcx, [rsp+78h+var_48]
0x14001ea0c  call    I8xManuallyRemoveDevice
0x14001ea11  bt      ebx, 11h
0x14001ea15  jnb     short loc_14001EA1F
0x14001ea17  mov     rcx, r12
0x14001ea1a  call    I8xManuallyRemoveDevice
0x14001ea1f  lea     r12, WPP_RECORDER_INITIALIZED
0x14001ea26  mov     ebx, 80000000h
0x14001ea2b  jmp     short loc_14001EAA6
0x14001ea2d  xor     ecx, ecx
0x14001ea2f  call    I8xToggleInterrupts
0x14001ea34  lea     r12, WPP_RECORDER_INITIALIZED
0x14001ea3b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001ea42  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001ea49  jz      short loc_14001EA6C
0x14001ea4b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ea52  mov     r9d, 20h ; ' '
0x14001ea58  mov     r8d, 16h
0x14001ea5e  mov     [rsp+78h+var_58], rax
0x14001ea63  mov     rcx, [rcx+40h]
0x14001ea67  call    WPP_RECORDER_SF_
0x14001ea6c  mov     r8d, ebx
0x14001ea6f  lea     rdx, [rsp+78h+arg_8]
0x14001ea77  lea     rcx, [rsp+78h+arg_10]
0x14001ea7f  call    I8xInitializeHardware
0x14001ea84  mov     edi, [rsp+78h+arg_10]
0x14001ea8b  mov     ebx, 80000000h
0x14001ea90  lea     eax, [rdi+rbx]
0x14001ea93  test    ebx, eax
0x14001ea95  jnz     short loc_14001EADD
0x14001ea97  cmp     edi, 0C000009Dh
0x14001ea9d  jz      short loc_14001EADD
0x14001ea9f  mov     esi, [rsp+78h+arg_8]
0x14001eaa6  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001eaad  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001eab4  jz      short loc_14001EAE4
0x14001eab6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eabd  mov     r9d, 21h ; '!'
0x14001eac3  mov     [rsp+78h+var_50], edi
0x14001eac7  mov     r8d, 11h
0x14001eacd  mov     [rsp+78h+var_58], rax
0x14001ead2  mov     rcx, [rcx+40h]
0x14001ead6  call    WPP_RECORDER_SF_D
0x14001eadb  jmp     short loc_14001EAE4
0x14001eadd  mov     esi, [rsp+78h+arg_8]
0x14001eae4  lea     eax, [rsi+rbx]
0x14001eae7  test    ebx, eax
0x14001eae9  jnz     short loc_14001EB28
0x14001eaeb  cmp     esi, 0C000009Dh
0x14001eaf1  jz      short loc_14001EB28
0x14001eaf3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001eafa  jz      short loc_14001EB28
0x14001eafc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb03  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001eb0a  mov     r9d, 22h ; '"'
0x14001eb10  mov     [rsp+78h+var_50], esi
0x14001eb14  mov     r8d, 11h
0x14001eb1a  mov     [rsp+78h+var_58], rax
0x14001eb1f  mov     rcx, [rcx+40h]
0x14001eb23  call    WPP_RECORDER_SF_D
0x14001eb28  lea     eax, [rdi+rbx]
0x14001eb2b  test    ebx, eax
0x14001eb2d  jnz     short loc_14001EB46
0x14001eb2f  cmp     edi, 0C000009Dh
0x14001eb35  jz      short loc_14001EB46
0x14001eb37  lea     eax, [rsi+rbx]
0x14001eb3a  test    ebx, eax
0x14001eb3c  jnz     short loc_14001EB46
0x14001eb3e  cmp     esi, 0C000009Dh
0x14001eb44  jnz     short loc_14001EB4D
0x14001eb46  mov     cl, 1
0x14001eb48  call    I8xToggleInterrupts
0x14001eb4d  test    esi, esi
0x14001eb4f  jns     short loc_14001EB65
0x14001eb51  cmp     esi, 0C000009Dh
0x14001eb57  jz      short loc_14001EB65
0x14001eb59  cmp     esi, 0C00000B5h
0x14001eb5f  jnz     loc_14001EC67
0x14001eb65  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001eb6c  jz      short loc_14001EB9A
0x14001eb6e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb75  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001eb7c  mov     r9d, 23h ; '#'
0x14001eb82  mov     [rsp+78h+var_50], esi
0x14001eb86  mov     r8d, 0Eh
0x14001eb8c  mov     [rsp+78h+var_58], rax
0x14001eb91  mov     rcx, [rcx+40h]
0x14001eb95  call    WPP_RECORDER_SF_D
0x14001eb9a  test    rbp, rbp
0x14001eb9d  jz      short loc_14001EBCE
0x14001eb9f  mov     rdx, [rbp+0B8h]
0x14001eba6  mov     rcx, [rsp+78h+arg_18]
0x14001ebae  mov     eax, [rdx+18h]
0x14001ebb1  mov     [rcx+50h], eax
0x14001ebb4  mov     [rcx+58h], r13d
0x14001ebb8  mov     r8d, [rdx+18h]; State
0x14001ebbc  mov     edx, [rdx+10h]; Type
0x14001ebbf  mov     rcx, [rcx]; DeviceObject
0x14001ebc2  call    cs:__imp_PoSetPowerState
0x14001ebc9  nop     dword ptr [rax+rax+00h]
0x14001ebce  mov     rax, [rsp+78h+arg_18]
0x14001ebd6  cmp     word ptr [rax+21Ah], 0
0x14001ebde  jnz     short loc_14001EC2B
0x14001ebe0  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001ebe7  jz      short loc_14001EC19
0x14001ebe9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ebf0  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001ebf7  mov     r9d, 24h ; '$'
0x14001ebfd  mov     [rsp+78h+var_58], rax
0x14001ec02  mov     r8d, 0Eh
0x14001ec08  mov     rcx, [rcx+40h]
0x14001ec0c  call    WPP_RECORDER_SF_
0x14001ec11  mov     rax, [rsp+78h+arg_18]
0x14001ec19  xor     edx, edx
0x14001ec1b  mov     rcx, rax
0x14001ec1e  call    I8xMouseConnectInterruptAndEnable
0x14001ec23  mov     rax, [rsp+78h+arg_18]
0x14001ec2b  cmp     esi, 0C00000B5h
0x14001ec31  jz      short loc_14001EC64
0x14001ec33  cmp     esi, 0C000009Dh
0x14001ec39  jz      short loc_14001EC64
0x14001ec3b  cmp     byte ptr [rax+454h], 0
0x14001ec42  mov     rcx, rax
0x14001ec45  jz      short loc_14001EC4E
0x14001ec47  call    I8xMouseEnableTransmission
0x14001ec4c  jmp     short loc_14001EC64
0x14001ec4e  mov     word ptr [rax+3F4h], 0FFFFh
0x14001ec57  mov     [rax+230h], r13w
0x14001ec5f  call    I8xResetMouse
0x14001ec64  mov     esi, r13d
0x14001ec67  mov     r12, [rsp+78h+var_38]
0x14001ec6c  test    rbp, rbp
0x14001ec6f  jz      short loc_14001ECB9
0x14001ec71  mov     rcx, rbp; Irp
0x14001ec74  mov     [rbp+30h], esi
0x14001ec77  mov     [rbp+38h], r13
0x14001ec7b  call    cs:__imp_PoStartNextPowerIrp
0x14001ec82  nop     dword ptr [rax+rax+00h]
0x14001ec87  xor     edx, edx; PriorityBoost
0x14001ec89  mov     rcx, rbp; Irp
0x14001ec8c  call    cs:__imp_IofCompleteRequest
0x14001ec93  nop     dword ptr [rax+rax+00h]
0x14001ec98  mov     rcx, [rsp+78h+arg_18]
0x14001eca0  mov     r8d, 20h ; ' '; RemlockSize
0x14001eca6  add     rcx, 28h ; '('; RemoveLock
0x14001ecaa  mov     rdx, rbp; Tag
0x14001ecad  call    cs:__imp_IoReleaseRemoveLockEx
0x14001ecb4  nop     dword ptr [rax+rax+00h]
0x14001ecb9  mov     rsi, [rsp+78h+var_30]
0x14001ecbe  lea     eax, [rdi+rbx]
0x14001ecc1  mov     rbp, [rsp+78h+var_28]
0x14001ecc6  test    ebx, eax
0x14001ecc8  mov     rbx, [rsp+78h+arg_0]
0x14001ecd0  jnz     short loc_14001ECDA
0x14001ecd2  cmp     edi, 0C000009Dh
0x14001ecd8  jnz     short loc_14001ED0E
0x14001ecda  test    r15, r15
0x14001ecdd  jz      short loc_14001ED0B
0x14001ecdf  mov     rdx, [r15+0B8h]
0x14001ece6  mov     rcx, [rsp+78h+var_48]
0x14001eceb  mov     eax, [rdx+18h]
0x14001ecee  mov     [rcx+50h], eax
0x14001ecf1  mov     [rcx+58h], r13d
0x14001ecf5  mov     r8d, [rdx+18h]; State
0x14001ecf9  mov     edx, [rdx+10h]; Type
0x14001ecfc  mov     rcx, [rcx]; DeviceObject
0x14001ecff  call    cs:__imp_PoSetPowerState
0x14001ed06  nop     dword ptr [rax+rax+00h]
0x14001ed0b  mov     edi, r13d
0x14001ed0e  test    r15, r15
0x14001ed11  jz      short loc_14001ED59
0x14001ed13  mov     rcx, r15; Irp
0x14001ed16  mov     [r15+30h], edi
0x14001ed1a  mov     [r15+38h], r13
0x14001ed1e  call    cs:__imp_PoStartNextPowerIrp
0x14001ed25  nop     dword ptr [rax+rax+00h]
0x14001ed2a  xor     edx, edx; PriorityBoost
0x14001ed2c  mov     rcx, r15; Irp
0x14001ed2f  call    cs:__imp_IofCompleteRequest
0x14001ed36  nop     dword ptr [rax+rax+00h]
0x14001ed3b  mov     rcx, [rsp+78h+var_48]
0x14001ed40  mov     r8d, 20h ; ' '; RemlockSize
0x14001ed46  add     rcx, 28h ; '('; RemoveLock
0x14001ed4a  mov     rdx, r15; Tag
0x14001ed4d  call    cs:__imp_IoReleaseRemoveLockEx
0x14001ed54  nop     dword ptr [rax+rax+00h]
0x14001ed59  xor     edx, edx
0x14001ed5b  mov     ecx, 10000000h
0x14001ed60  call    I8xSetPowerFlag
0x14001ed65  mov     rcx, [r14]; IoWorkItem
0x14001ed68  call    cs:__imp_IoFreeWorkItem
0x14001ed6f  nop     dword ptr [rax+rax+00h]
0x14001ed74  xor     edx, edx; Tag
0x14001ed76  mov     rcx, r14; P
0x14001ed79  call    cs:__imp_ExFreePoolWithTag
0x14001ed80  nop     dword ptr [rax+rax+00h]
0x14001ed85  add     rsp, 58h
0x14001ed89  pop     r15
0x14001ed8b  pop     r14
0x14001ed8d  pop     r13
0x14001ed8f  pop     rdi
0x14001ed90  retn
```
