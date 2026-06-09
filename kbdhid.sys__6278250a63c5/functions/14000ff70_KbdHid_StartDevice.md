# KbdHid_StartDevice

- ea: `0x14000ff70`
- end: `0x140010504`
- name: `KbdHid_StartDevice`
- size: `1428`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000f930`

## callees

- `0x140003e30`
- `0x140004f80`
- `0x1400052a0`
- `0x140005a0c`
- `0x140007130`
- `0x140007540`
- `0x14000ff70`
- `0x140010510`

## import_xrefs

- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140010383`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140010383`
- `ntoskrnl!IoFreeMdl` at `0x14001048f`
- `ntoskrnl!IoFreeMdl` at `0x14001048f`
- `ntoskrnl!IofCallDriver` at `0x1400103e0`
- `ntoskrnl!IofCallDriver` at `0x1400103e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010476`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400104a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400104bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010476`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400104a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400104bc`
- `ntoskrnl!ZwClose` at `0x1400101a4`
- `ntoskrnl!ZwClose` at `0x1400101a4`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400102bb`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400102bb`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400100d5`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400100d5`
- `ntoskrnl!IoAllocateIrp` at `0x14001031e`
- `ntoskrnl!IoAllocateIrp` at `0x14001031e`
- `ntoskrnl!ExAllocatePool2` at `0x140010059`
- `ntoskrnl!ExAllocatePool2` at `0x140010229`
- `ntoskrnl!ExAllocatePool2` at `0x140010059`
- `ntoskrnl!ExAllocatePool2` at `0x140010229`
- `ntoskrnl!IoAllocateMdl` at `0x1400102db`
- `ntoskrnl!IoAllocateMdl` at `0x1400102db`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010301`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010301`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140010407`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140010407`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400103c9`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400103c9`
- `HIDPARSE!HidP_GetCaps` at `0x1400100a1`
- `HIDPARSE!HidP_GetCaps` at `0x1400100a1`
- `HIDPARSE!HidP_MaxUsageListLength` at `0x1400101ba`
- `HIDPARSE!HidP_MaxUsageListLength` at `0x1400101ba`

## pseudocode

```c
__int64 __fastcall KbdHid_StartDevice(char *Context)
{
  __int64 *v2; // rdx
  NTSTATUS Caps; // ebx
  void *Pool2; // rdi
  struct _DEVICE_OBJECT *v5; // rcx
  ULONG v6; // eax
  ULONG v7; // ebx
  unsigned int v8; // r14d
  unsigned __int64 v9; // r15
  __int64 v10; // rax
  __int64 v11; // r12
  __int128 v12; // xmm1
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rax
  struct _MDL *Mdl; // rax
  __int64 v18; // rcx
  PIRP Irp; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  IRP *v21; // rbx
  struct _IO_STACK_LOCATION *v22; // rax
  NTSTATUS v23; // r14d
  struct _MDL *v24; // rcx
  void *DeviceRegKey; // [rsp+48h] [rbp-31h] BYREF
  __int64 v27; // [rsp+50h] [rbp-29h]
  int v28; // [rsp+58h] [rbp-21h]
  _HIDP_CAPS Capabilities; // [rsp+60h] [rbp-19h] BYREF

  memset(&Capabilities, 0, sizeof(Capabilities));
  v27 = 0;
  DeviceRegKey = 0;
  v28 = 0;
  v2 = WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      5,
      17,
      (__int64)WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids);
  LoadKeyboardUsageMappingList(Context, v2);
  Caps = KbdHid_CallHidClass(Context, 721320);
  if ( Caps >= 0 )
  {
    Pool2 = (void *)ExAllocatePool2(64, (unsigned int)v27, 1214538315);
    if ( !Pool2 )
      return (unsigned int)-1073741670;
    Caps = KbdHid_CallHidClass(Context, 721299);
    if ( Caps < 0 || (Caps = HidP_GetCaps((PHIDP_PREPARSED_DATA)Pool2, &Capabilities), Caps < 0) )
    {
LABEL_42:
      ExFreePoolWithTag(Pool2, 0);
      return (unsigned int)Caps;
    }
    v5 = (struct _DEVICE_OBJECT *)*((_QWORD *)Context + 2);
    *((_WORD *)Context + 144) = Capabilities.NumberInputDataIndices;
    if ( IoOpenDeviceRegistryKey(v5, 1u, 0x1F0000u, &DeviceRegKey) >= 0 )
    {
      if ( (int)KbdHid_QueryDeviceKey(DeviceRegKey) >= 0 )
      {
        Context[280] = 0;
        *((_DWORD *)Context + 86) = 0;
      }
      if ( (int)KbdHid_QueryDeviceKey(DeviceRegKey) >= 0 )
      {
        Context[281] = 0;
        *((_DWORD *)Context + 87) = 0;
      }
      if ( (int)KbdHid_QueryDeviceKey(DeviceRegKey) >= 0 )
        *((_WORD *)Context + 144) = 0;
      if ( (int)KbdHid_QueryDeviceKey(DeviceRegKey) >= 0 )
        *((_WORD *)Context + 142) = 0;
      if ( (int)KbdHid_QueryDeviceKey(DeviceRegKey) >= 0 )
        *((_WORD *)Context + 143) = 0;
      ZwClose(DeviceRegKey);
    }
    v6 = HidP_MaxUsageListLength(HidP_Input, 7u, (PHIDP_PREPARSED_DATA)Pool2);
    v7 = v6;
    if ( v6 > 0x3FFFFFFF
      || (v8 = (Capabilities.InputReportByteLength + 7) & 0xFFFFFFF8,
          v9 = (4 * v6 + 7) & 0xFFFFFFF8,
          ((unsigned __int64)~v8 - 152) / 6 < v9) )
    {
      Caps = -1073741823;
      goto LABEL_42;
    }
    v10 = ExAllocatePool2(64, v8 + 2 * ((_DWORD)v9 + 2 * ((_DWORD)v9 + 38)), 1214538315);
    *((_QWORD *)Context + 14) = v10;
    v11 = v10;
    if ( !v10 )
    {
      Caps = -1073741670;
      goto LABEL_42;
    }
    *(_QWORD *)v10 = Pool2;
    *(_OWORD *)(v10 + 8) = *(_OWORD *)&Capabilities.Usage;
    *(_OWORD *)(v10 + 24) = *(_OWORD *)&Capabilities.Reserved[3];
    *(_OWORD *)(v10 + 40) = *(_OWORD *)&Capabilities.Reserved[11];
    v12 = *(_OWORD *)&Capabilities.NumberInputValueCaps;
    *(_QWORD *)(v10 + 80) = v10 + 152;
    *(_OWORD *)(v10 + 56) = v12;
    *(_DWORD *)(v10 + 72) = v7;
    v13 = v8 + v10 + 152;
    *(_QWORD *)(v10 + 120) = v13;
    *(_QWORD *)(v10 + 88) = v13 + v9;
    v14 = v9 + v13 + v9;
    *(_QWORD *)(v11 + 96) = v14;
    v15 = v9 + v14;
    *(_QWORD *)(v11 + 128) = v15;
    v16 = v9 + v15;
    *(_QWORD *)(v11 + 104) = v16;
    *(_QWORD *)(v11 + 112) = v9 + v16;
    KeInitializeSpinLock((PKSPIN_LOCK)(v11 + 136));
    Mdl = IoAllocateMdl(*(PVOID *)(v11 + 80), Capabilities.InputReportByteLength, 0, 0, 0);
    *(_QWORD *)(v11 + 144) = Mdl;
    if ( !Mdl )
    {
      Caps = -1073741670;
LABEL_38:
      ExFreePoolWithTag(Pool2, 0);
      v24 = *(struct _MDL **)(v11 + 144);
      if ( v24 )
        IoFreeMdl(v24);
      ExFreePoolWithTag((PVOID)v11, 0);
      *((_QWORD *)Context + 14) = 0;
      return (unsigned int)Caps;
    }
    MmBuildMdlForNonPagedPool(Mdl);
    v18 = *((_QWORD *)Context + 1);
    *((_QWORD *)Context + 100) = 0;
    Irp = IoAllocateIrp(*(_BYTE *)(v18 + 76), 0);
    *((_QWORD *)Context + 99) = Irp;
    if ( !Irp )
    {
      Caps = -1073741670;
      goto LABEL_38;
    }
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].MajorFunction = 14;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 721511;
    CurrentStackLocation[-1].Parameters.Create.Options = 0;
    CurrentStackLocation[-1].Parameters.Read.Length = 0;
    v21 = (IRP *)*((_QWORD *)Context + 99);
    if ( IoSetCompletionRoutineEx(
           *(PDEVICE_OBJECT *)Context,
           v21,
           KbdHid_PresenceNotificationCompleted,
           Context,
           1u,
           1u,
           1u) < 0 )
    {
      v22 = v21->Tail.Overlay.CurrentStackLocation;
      v22[-1].CompletionRoutine = KbdHid_PresenceNotificationCompleted;
      v22[-1].Context = Context;
      v22[-1].Control = -32;
    }
    IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(Context + 152), *((PVOID *)Context + 99), File, 1u, 0x20u);
    v23 = IofCallDriver(*((PDEVICE_OBJECT *)Context + 1), *((PIRP *)Context + 99));
    if ( v23 < 0 )
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 152), *((PVOID *)Context + 99), 0x20u);
    Caps = 0;
    if ( v23 != 259 )
      Caps = v23;
    if ( Caps < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qd(
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          4,
          18,
          (__int64)WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids,
          *(_QWORD *)Context,
          Caps);
      goto LABEL_38;
    }
  }
  return (unsigned int)Caps;
}

```

## disassembly

```asm
0x14000ff70  push    rbp
0x14000ff72  push    rbx
0x14000ff73  push    rsi
0x14000ff74  push    r13
0x14000ff76  lea     rbp, [rsp-3Fh]
0x14000ff7b  sub     rsp, 0B8h
0x14000ff82  mov     rax, cs:__security_cookie
0x14000ff89  xor     rax, rsp
0x14000ff8c  mov     [rbp+57h+var_30], rax
0x14000ff90  mov     rsi, rcx
0x14000ff93  xor     edx, edx; Val
0x14000ff95  lea     rcx, [rbp+57h+Capabilities]; void *
0x14000ff99  mov     r8d, 40h ; '@'; Size
0x14000ff9f  call    memset
0x14000ffa4  xor     eax, eax
0x14000ffa6  xor     r13d, r13d
0x14000ffa9  mov     [rbp+57h+var_80], rax
0x14000ffad  mov     [rbp+57h+DeviceRegKey], r13
0x14000ffb1  mov     [rbp+57h+var_90], r13d
0x14000ffb5  mov     [rbp+57h+var_78], eax
0x14000ffb8  lea     rax, WPP_RECORDER_INITIALIZED
0x14000ffbf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ffc6  lea     rdx, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x14000ffcd  jz      short loc_14000FFFB
0x14000ffcf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ffd6  cmp     [rcx+48h], r13w
0x14000ffdb  jz      short loc_14000FFFB
0x14000ffdd  mov     rcx, [rcx+40h]
0x14000ffe1  mov     r8d, 5
0x14000ffe7  mov     [rsp+0D0h+Irp], rdx
0x14000ffec  mov     r9d, 11h
0x14000fff2  movzx   edx, r8b
0x14000fff6  call    WPP_RECORDER_SF_
0x14000fffb  mov     [rsp+0D0h+arg_8], rdi
0x140010003  mov     rcx, rsi
0x140010006  mov     [rsp+0D0h+arg_10], r12
0x14001000e  mov     [rsp+0D0h+arg_18], r14
0x140010016  mov     [rsp+0D0h+var_20], r15
0x14001001e  call    LoadKeyboardUsageMappingList
0x140010023  lea     rax, [rbp+57h+var_80]
0x140010027  mov     dword ptr [rsp+0D0h+InvokeOnError], 0Ch
0x14001002f  mov     edx, 0B01A8h
0x140010034  mov     [rsp+0D0h+Irp], rax
0x140010039  mov     rcx, rsi
0x14001003c  call    KbdHid_CallHidClass
0x140010041  mov     ebx, eax
0x140010043  test    eax, eax
0x140010045  js      loc_1400104C8
0x14001004b  mov     edx, dword ptr [rbp+57h+var_80]
0x14001004e  mov     ecx, 40h ; '@'
0x140010053  mov     r8d, 4864624Bh
0x140010059  call    cs:__imp_ExAllocatePool2
0x140010060  nop     dword ptr [rax+rax+00h]
0x140010065  mov     rdi, rax
0x140010068  test    rax, rax
0x14001006b  jnz     short loc_140010077
0x14001006d  mov     ebx, 0C000009Ah
0x140010072  jmp     loc_1400104C8
0x140010077  mov     eax, dword ptr [rbp+57h+var_80]
0x14001007a  mov     edx, 0B0193h
0x14001007f  mov     dword ptr [rsp+0D0h+InvokeOnError], eax
0x140010083  mov     rcx, rsi
0x140010086  mov     [rsp+0D0h+Irp], rdi
0x14001008b  call    KbdHid_CallHidClass
0x140010090  mov     ebx, eax
0x140010092  test    eax, eax
0x140010094  js      loc_1400104B7
0x14001009a  lea     rdx, [rbp+57h+Capabilities]; Capabilities
0x14001009e  mov     rcx, rdi; PreparsedData
0x1400100a1  call    cs:__imp_HidP_GetCaps
0x1400100a8  nop     dword ptr [rax+rax+00h]
0x1400100ad  mov     ebx, eax
0x1400100af  test    eax, eax
0x1400100b1  js      loc_1400104B7
0x1400100b7  movzx   eax, [rbp+57h+Capabilities.NumberInputDataIndices]
0x1400100bb  lea     r9, [rbp+57h+DeviceRegKey]; DeviceRegKey
0x1400100bf  mov     rcx, [rsi+10h]; DeviceObject
0x1400100c3  mov     edx, 1; DevInstKeyType
0x1400100c8  mov     r8d, 1F0000h; DesiredAccess
0x1400100ce  mov     [rsi+120h], ax
0x1400100d5  call    cs:__imp_IoOpenDeviceRegistryKey
0x1400100dc  nop     dword ptr [rax+rax+00h]
0x1400100e1  test    eax, eax
0x1400100e3  js      loc_1400101B0
0x1400100e9  mov     rcx, [rbp+57h+DeviceRegKey]; KeyHandle
0x1400100ed  lea     r8, [rbp+57h+var_90]
0x1400100f1  lea     rdx, aKeyboardtypeov; "KeyboardTypeOverride"
0x1400100f8  call    KbdHid_QueryDeviceKey
0x1400100fd  test    eax, eax
0x1400100ff  js      short loc_140010110
0x140010101  mov     eax, [rbp+57h+var_90]
0x140010104  mov     [rsi+118h], al
0x14001010a  mov     [rsi+158h], eax
0x140010110  mov     rcx, [rbp+57h+DeviceRegKey]; KeyHandle
0x140010114  lea     r8, [rbp+57h+var_90]
0x140010118  lea     rdx, aKeyboardsubtyp; "KeyboardSubtypeOverride"
0x14001011f  call    KbdHid_QueryDeviceKey
0x140010124  test    eax, eax
0x140010126  js      short loc_140010137
0x140010128  mov     eax, [rbp+57h+var_90]
0x14001012b  mov     [rsi+119h], al
0x140010131  mov     [rsi+15Ch], eax
0x140010137  mov     rcx, [rbp+57h+DeviceRegKey]; KeyHandle
0x14001013b  lea     r8, [rbp+57h+var_90]
0x14001013f  lea     rdx, aKeyboardnumber_1; "KeyboardNumberTotalKeysOverride"
0x140010146  call    KbdHid_QueryDeviceKey
0x14001014b  test    eax, eax
0x14001014d  js      short loc_14001015A
0x14001014f  movzx   eax, word ptr [rbp+57h+var_90]
0x140010153  mov     [rsi+120h], ax
0x14001015a  mov     rcx, [rbp+57h+DeviceRegKey]; KeyHandle
0x14001015e  lea     r8, [rbp+57h+var_90]
0x140010162  lea     rdx, aKeyboardnumber; "KeyboardNumberFunctionKeysOverride"
0x140010169  call    KbdHid_QueryDeviceKey
0x14001016e  test    eax, eax
0x140010170  js      short loc_14001017D
0x140010172  movzx   eax, word ptr [rbp+57h+var_90]
0x140010176  mov     [rsi+11Ch], ax
0x14001017d  mov     rcx, [rbp+57h+DeviceRegKey]; KeyHandle
0x140010181  lea     r8, [rbp+57h+var_90]
0x140010185  lea     rdx, aKeyboardnumber_0; "KeyboardNumberIndicatorsOverride"
0x14001018c  call    KbdHid_QueryDeviceKey
0x140010191  test    eax, eax
0x140010193  js      short loc_1400101A0
0x140010195  movzx   eax, word ptr [rbp+57h+var_90]
0x140010199  mov     [rsi+11Eh], ax
0x1400101a0  mov     rcx, [rbp+57h+DeviceRegKey]; Handle
0x1400101a4  call    cs:__imp_ZwClose
0x1400101ab  nop     dword ptr [rax+rax+00h]
0x1400101b0  mov     edx, 7; UsagePage
0x1400101b5  mov     r8, rdi; PreparsedData
0x1400101b8  xor     ecx, ecx; ReportType
0x1400101ba  call    cs:__imp_HidP_MaxUsageListLength
0x1400101c1  nop     dword ptr [rax+rax+00h]
0x1400101c6  mov     ebx, eax
0x1400101c8  cmp     eax, 3FFFFFFFh
0x1400101cd  ja      loc_1400104B2
0x1400101d3  movzx   r14d, [rbp+57h+Capabilities.InputReportByteLength]
0x1400101d8  lea     r15d, ds:7[rax*4]
0x1400101e0  add     r14d, 7
0x1400101e4  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400101ee  and     r14d, 0FFFFFFF8h
0x1400101f2  and     r15d, 0FFFFFFF8h
0x1400101f6  mov     edx, r14d
0x1400101f9  not     edx
0x1400101fb  sub     rdx, 98h
0x140010202  mul     rdx
0x140010205  shr     rdx, 2
0x140010209  cmp     rdx, r15
0x14001020c  jb      loc_1400104B2
0x140010212  lea     eax, [r15+26h]
0x140010216  mov     ecx, 40h ; '@'
0x14001021b  lea     eax, [r15+rax*2]
0x14001021f  mov     r8d, 4864624Bh
0x140010225  lea     edx, [r14+rax*2]
0x140010229  call    cs:__imp_ExAllocatePool2
0x140010230  nop     dword ptr [rax+rax+00h]
0x140010235  mov     [rsi+70h], rax
0x140010239  mov     r12, rax
0x14001023c  test    rax, rax
0x14001023f  jnz     short loc_14001024B
0x140010241  mov     ebx, 0C000009Ah
0x140010246  jmp     loc_1400104B7
0x14001024b  mov     [rax], rdi
0x14001024e  lea     rcx, [rax+98h]
0x140010255  movaps  xmm0, xmmword ptr [rbp+57h+Capabilities.Usage]
0x140010259  movups  xmmword ptr [rax+8], xmm0
0x14001025d  movaps  xmm1, xmmword ptr [rbp+57h+Capabilities.Reserved+6]
0x140010261  movups  xmmword ptr [rax+18h], xmm1
0x140010265  movaps  xmm0, xmmword ptr [rbp+57h+Capabilities.Reserved+16h]
0x140010269  movups  xmmword ptr [rax+28h], xmm0
0x14001026d  movaps  xmm1, xmmword ptr [rbp+17h]
0x140010271  mov     [rax+50h], rcx
0x140010275  movups  xmmword ptr [rax+38h], xmm1
0x140010279  mov     [rax+48h], ebx
0x14001027c  mov     eax, r14d
0x14001027f  add     rcx, rax
0x140010282  mov     [r12+78h], rcx
0x140010287  lea     rax, [rcx+r15]
0x14001028b  mov     [r12+58h], rax
0x140010290  lea     rcx, [r12+88h]; SpinLock
0x140010298  add     rax, r15
0x14001029b  mov     [r12+60h], rax
0x1400102a0  add     rax, r15
0x1400102a3  mov     [r12+80h], rax
0x1400102ab  add     rax, r15
0x1400102ae  mov     [r12+68h], rax
0x1400102b3  add     rax, r15
0x1400102b6  mov     [r12+70h], rax
0x1400102bb  call    cs:__imp_KeInitializeSpinLock
0x1400102c2  nop     dword ptr [rax+rax+00h]
0x1400102c7  movzx   edx, [rbp+57h+Capabilities.InputReportByteLength]; Length
0x1400102cb  xor     r9d, r9d; ChargeQuota
0x1400102ce  mov     rcx, [r12+50h]; VirtualAddress
0x1400102d3  xor     r8d, r8d; SecondaryBuffer
0x1400102d6  mov     [rsp+0D0h+Irp], r13; Irp
0x1400102db  call    cs:__imp_IoAllocateMdl
0x1400102e2  nop     dword ptr [rax+rax+00h]
0x1400102e7  mov     [r12+90h], rax
0x1400102ef  test    rax, rax
0x1400102f2  jnz     short loc_1400102FE
0x1400102f4  mov     ebx, 0C000009Ah
0x1400102f9  jmp     loc_140010471
0x1400102fe  mov     rcx, rax; MemoryDescriptorList
0x140010301  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140010308  nop     dword ptr [rax+rax+00h]
0x14001030d  mov     rcx, [rsi+8]
0x140010311  xor     edx, edx; ChargeQuota
0x140010313  mov     [rsi+320h], r13
0x14001031a  movzx   ecx, byte ptr [rcx+4Ch]; StackSize
0x14001031e  call    cs:__imp_IoAllocateIrp
0x140010325  nop     dword ptr [rax+rax+00h]
0x14001032a  mov     [rsi+318h], rax
0x140010331  test    rax, rax
0x140010334  jnz     short loc_140010340
0x140010336  mov     ebx, 0C000009Ah
0x14001033b  jmp     loc_140010471
0x140010340  mov     rax, [rax+0B8h]
0x140010347  lea     r14, KbdHid_PresenceNotificationCompleted
0x14001034e  mov     [rsp+0D0h+InvokeOnCancel], 1; InvokeOnCancel
0x140010353  mov     r9, rsi; Context
0x140010356  mov     [rsp+0D0h+InvokeOnError], 1; InvokeOnError
0x14001035b  mov     r8, r14; CompletionRoutine
0x14001035e  mov     byte ptr [rsp+0D0h+Irp], 1; InvokeOnSuccess
0x140010363  mov     byte ptr [rax-48h], 0Eh
0x140010367  mov     dword ptr [rax-30h], 0B0267h
0x14001036e  mov     [rax-38h], r13d
0x140010372  mov     [rax-40h], r13d
0x140010376  mov     rbx, [rsi+318h]
0x14001037d  mov     rcx, [rsi]; DeviceObject
0x140010380  mov     rdx, rbx; Irp
0x140010383  call    cs:__imp_IoSetCompletionRoutineEx
0x14001038a  nop     dword ptr [rax+rax+00h]
0x14001038f  test    eax, eax
0x140010391  jns     short loc_1400103A6
0x140010393  mov     rax, [rbx+0B8h]
0x14001039a  mov     [rax-10h], r14
0x14001039e  mov     [rax-8], rsi
0x1400103a2  mov     byte ptr [rax-45h], 0E0h
0x1400103a6  mov     rdx, [rsi+318h]; Tag
0x1400103ad  lea     r8, File; File
0x1400103b4  mov     r9d, 1; Line
0x1400103ba  mov     dword ptr [rsp+0D0h+Irp], 20h ; ' '; RemlockSize
0x1400103c2  lea     rcx, [rsi+98h]; RemoveLock
0x1400103c9  call    cs:__imp_IoAcquireRemoveLockEx
0x1400103d0  nop     dword ptr [rax+rax+00h]
0x1400103d5  mov     rdx, [rsi+318h]; Irp
0x1400103dc  mov     rcx, [rsi+8]; DeviceObject
0x1400103e0  call    cs:__imp_IofCallDriver
0x1400103e7  nop     dword ptr [rax+rax+00h]
0x1400103ec  mov     r14d, eax
0x1400103ef  test    eax, eax
0x1400103f1  jns     short loc_140010413
0x1400103f3  mov     rdx, [rsi+318h]; Tag
0x1400103fa  lea     rcx, [rsi+98h]; RemoveLock
0x140010401  mov     r8d, 20h ; ' '; RemlockSize
0x140010407  call    cs:__imp_IoReleaseRemoveLockEx
0x14001040e  nop     dword ptr [rax+rax+00h]
0x140010413  cmp     r14d, 103h
0x14001041a  mov     ebx, r13d
0x14001041d  cmovnz  ebx, r14d
0x140010421  test    ebx, ebx
0x140010423  jns     loc_1400104C8
0x140010429  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140010430  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010437  jz      short loc_140010471
0x140010439  mov     rax, [rsi]
0x14001043c  mov     r8d, 4
0x140010442  mov     rcx, cs:WPP_GLOBAL_Control
0x140010449  mov     r9d, 12h
0x14001044f  mov     dword ptr [rsp+0D0h+InvokeOnCancel], ebx
0x140010453  movzx   edx, r8b
0x140010457  mov     qword ptr [rsp+0D0h+InvokeOnError], rax
0x14001045c  lea     rax, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x140010463  mov     [rsp+0D0h+Irp], rax
0x140010468  mov     rcx, [rcx+40h]
0x14001046c  call    WPP_RECORDER_SF_qd
0x140010471  xor     edx, edx; Tag
0x140010473  mov     rcx, rdi; P
0x140010476  call    cs:__imp_ExFreePoolWithTag
0x14001047d  nop     dword ptr [rax+rax+00h]
0x140010482  mov     rcx, [r12+90h]; Mdl
0x14001048a  test    rcx, rcx
0x14001048d  jz      short loc_14001049B
0x14001048f  call    cs:__imp_IoFreeMdl
0x140010496  nop     dword ptr [rax+rax+00h]
0x14001049b  xor     edx, edx; Tag
0x14001049d  mov     rcx, r12; P
0x1400104a0  call    cs:__imp_ExFreePoolWithTag
0x1400104a7  nop     dword ptr [rax+rax+00h]
0x1400104ac  mov     [rsi+70h], r13
0x1400104b0  jmp     short loc_1400104C8
0x1400104b2  mov     ebx, 0C0000001h
0x1400104b7  xor     edx, edx; Tag
0x1400104b9  mov     rcx, rdi; P
0x1400104bc  call    cs:__imp_ExFreePoolWithTag
0x1400104c3  nop     dword ptr [rax+rax+00h]
0x1400104c8  mov     r15, [rsp+0D0h+var_20]
0x1400104d0  mov     eax, ebx
0x1400104d2  mov     r14, [rsp+0D0h+arg_18]
  ... truncated ...
```
