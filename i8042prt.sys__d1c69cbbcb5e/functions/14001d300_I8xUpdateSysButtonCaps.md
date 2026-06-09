# I8xUpdateSysButtonCaps

- ea: `0x14001d300`
- end: `0x14001d5e8`
- name: `I8xUpdateSysButtonCaps`
- size: `744`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140004530`
- `0x140007b10`
- `0x14000d128`
- `0x14000d708`
- `0x14001cf5c`
- `0x14001d300`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001d5cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d5cd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d46b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d46b`
- `ntoskrnl!IoFreeWorkItem` at `0x14001d5bc`
- `ntoskrnl!IoFreeWorkItem` at `0x14001d5bc`
- `ntoskrnl!ZwClose` at `0x14001d4b8`
- `ntoskrnl!ZwClose` at `0x14001d4b8`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001d349`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001d349`
- `ntoskrnl!ZwSetValueKey` at `0x14001d4a7`
- `ntoskrnl!ZwSetValueKey` at `0x14001d4a7`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14001d564`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14001d575`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14001d564`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14001d575`

## pseudocode

```c
void __fastcall I8xUpdateSysButtonCaps(PDEVICE_OBJECT DeviceObject, PIO_WORKITEM *Context)
{
  bool v2; // zf
  unsigned __int8 *DeviceExtension; // rdi
  int v5; // edx
  __int64 v6; // rdx
  int v7; // eax
  int v8; // edx
  IRP *PendedIrp; // rax
  __int64 DataSize; // [rsp+28h] [rbp-30h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HANDLE KeyHandle; // [rsp+68h] [rbp+10h] BYREF

  v2 = *((_DWORD *)Context + 2) == 0;
  DestinationString = 0;
  KeyHandle = 0;
  Data = 0;
  if ( !v2 )
  {
    DeviceExtension = (unsigned __int8 *)DeviceObject->DeviceExtension;
    if ( IoOpenDeviceRegistryKey(*((PDEVICE_OBJECT *)DeviceExtension + 4), 1u, 0x1F0000u, &KeyHandle) < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          25,
          31,
          (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
    }
    else
    {
      switch ( *((_DWORD *)Context + 2) )
      {
        case '^':
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v5,
              22,
              25,
              (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
          DeviceExtension[584] |= 1u;
          break;
        case '_':
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v5,
              22,
              26,
              (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
          DeviceExtension[584] |= 2u;
          break;
        case 'c':
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v5,
              22,
              27,
              (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
          DeviceExtension[584] |= 4u;
          break;
        default:
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_D(
              WPP_GLOBAL_Control->DeviceExtension,
              v5,
              25,
              28,
              (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids,
              *((_DWORD *)Context + 2),
              *(_QWORD *)&DestinationString.Length,
              DestinationString.Buffer);
          break;
      }
      RtlInitUnicodeString(&DestinationString, L"PowerCapabilities");
      Data = DeviceExtension[584];
      ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &Data, 4u);
      ZwClose(KeyHandle);
      if ( *((_QWORD *)DeviceExtension + 85) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            24,
            30,
            (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
        PendedIrp = (IRP *)I8xUpdateSysButtonCapsGetPendedIrp(DeviceExtension);
        if ( PendedIrp )
          I8xCompleteSysButtonIrp(PendedIrp);
        IoSetDeviceInterfaceState((PUNICODE_STRING)DeviceExtension + 42, 0);
        IoSetDeviceInterfaceState((PUNICODE_STRING)DeviceExtension + 42, 1u);
      }
      else
      {
        v7 = I8xRegisterDeviceInterface(*((_QWORD *)DeviceExtension + 4), v6, DeviceExtension + 672);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(DataSize) = v7;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            22,
            29,
            (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids,
            DataSize);
        }
      }
    }
  }
  IoFreeWorkItem(*Context);
  ExFreePoolWithTag(Context, 0);
}

```

## disassembly

```asm
0x14001d300  mov     rax, rsp
0x14001d303  mov     [rax+18h], rbx
0x14001d307  push    rsi
0x14001d308  push    rdi
0x14001d309  push    r14
0x14001d30b  sub     rsp, 40h
0x14001d30f  cmp     dword ptr [rdx+8], 0
0x14001d313  xorps   xmm0, xmm0
0x14001d316  movups  xmmword ptr [rax-28h], xmm0
0x14001d31a  mov     r14, rdx
0x14001d31d  mov     qword ptr [rax+10h], 0
0x14001d325  mov     dword ptr [rax+8], 0
0x14001d32c  jz      loc_14001D5B9
0x14001d332  mov     rdi, [rcx+40h]
0x14001d336  lea     r9, [rax+10h]; DeviceRegKey
0x14001d33a  mov     edx, 1; DevInstKeyType
0x14001d33f  mov     r8d, 1F0000h; DesiredAccess
0x14001d345  mov     rcx, [rdi+20h]; DeviceObject
0x14001d349  call    cs:__imp_IoOpenDeviceRegistryKey
0x14001d350  nop     dword ptr [rax+rax+00h]
0x14001d355  test    eax, eax
0x14001d357  js      loc_14001D583
0x14001d35d  mov     ecx, [r14+8]
0x14001d361  lea     rsi, WPP_9a74d45702a83a61696de9b252942f2f_Traceguids
0x14001d368  mov     eax, ecx
0x14001d36a  sub     eax, 5Eh ; '^'
0x14001d36d  jz      loc_14001D429
0x14001d373  sub     eax, 1
0x14001d376  jz      short loc_14001D3F1
0x14001d378  cmp     eax, 4
0x14001d37b  jz      short loc_14001D3B9
0x14001d37d  lea     rbx, WPP_RECORDER_INITIALIZED
0x14001d384  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001d38b  jz      loc_14001D45F
0x14001d391  mov     dword ptr [rsp+58h+DataSize], ecx
0x14001d395  mov     r9d, 1Ch
0x14001d39b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d3a2  mov     [rsp+58h+Data], rsi
0x14001d3a7  lea     r8d, [r9-3]
0x14001d3ab  mov     rcx, [rcx+40h]
0x14001d3af  call    WPP_RECORDER_SF_D
0x14001d3b4  jmp     loc_14001D45F
0x14001d3b9  lea     rbx, WPP_RECORDER_INITIALIZED
0x14001d3c0  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001d3c7  jz      short loc_14001D3E8
0x14001d3c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d3d0  mov     r9d, 1Bh
0x14001d3d6  mov     [rsp+58h+Data], rsi
0x14001d3db  mov     rcx, [rcx+40h]
0x14001d3df  lea     r8d, [r9-5]
0x14001d3e3  call    WPP_RECORDER_SF_
0x14001d3e8  or      byte ptr [rdi+248h], 4
0x14001d3ef  jmp     short loc_14001D45F
0x14001d3f1  lea     rbx, WPP_RECORDER_INITIALIZED
0x14001d3f8  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001d3ff  jz      short loc_14001D420
0x14001d401  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d408  mov     r9d, 1Ah
0x14001d40e  mov     [rsp+58h+Data], rsi
0x14001d413  mov     rcx, [rcx+40h]
0x14001d417  lea     r8d, [r9-4]
0x14001d41b  call    WPP_RECORDER_SF_
0x14001d420  or      byte ptr [rdi+248h], 2
0x14001d427  jmp     short loc_14001D45F
0x14001d429  lea     rbx, WPP_RECORDER_INITIALIZED
0x14001d430  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001d437  jz      short loc_14001D458
0x14001d439  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d440  mov     r9d, 19h
0x14001d446  mov     [rsp+58h+Data], rsi
0x14001d44b  mov     rcx, [rcx+40h]
0x14001d44f  lea     r8d, [r9-3]
0x14001d453  call    WPP_RECORDER_SF_
0x14001d458  or      byte ptr [rdi+248h], 1
0x14001d45f  lea     rdx, aPowercapabilit; "PowerCapabilities"
0x14001d466  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14001d46b  call    cs:__imp_RtlInitUnicodeString
0x14001d472  nop     dword ptr [rax+rax+00h]
0x14001d477  movzx   eax, byte ptr [rdi+248h]
0x14001d47e  lea     rdx, [rsp+58h+DestinationString]; ValueName
0x14001d483  mov     rcx, [rsp+58h+KeyHandle]; KeyHandle
0x14001d488  mov     r9d, 4; Type
0x14001d48e  mov     [rsp+58h+arg_0], eax
0x14001d492  xor     r8d, r8d; TitleIndex
0x14001d495  lea     rax, [rsp+58h+arg_0]
0x14001d49a  mov     dword ptr [rsp+58h+DataSize], 4; DataSize
0x14001d4a2  mov     [rsp+58h+Data], rax; Data
0x14001d4a7  call    cs:__imp_ZwSetValueKey
0x14001d4ae  nop     dword ptr [rax+rax+00h]
0x14001d4b3  mov     rcx, [rsp+58h+KeyHandle]; Handle
0x14001d4b8  call    cs:__imp_ZwClose
0x14001d4bf  nop     dword ptr [rax+rax+00h]
0x14001d4c4  cmp     qword ptr [rdi+2A8h], 0
0x14001d4cc  jnz     short loc_14001D513
0x14001d4ce  mov     rcx, [rdi+20h]
0x14001d4d2  lea     r8, [rdi+2A0h]
0x14001d4d9  call    I8xRegisterDeviceInterface
0x14001d4de  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001d4e5  jz      loc_14001D5B9
0x14001d4eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d4f2  mov     r9d, 1Dh
0x14001d4f8  mov     dword ptr [rsp+58h+DataSize], eax
0x14001d4fc  mov     [rsp+58h+Data], rsi
0x14001d501  mov     rcx, [rcx+40h]
0x14001d505  lea     r8d, [r9-7]
0x14001d509  call    WPP_RECORDER_SF_D
0x14001d50e  jmp     loc_14001D5B9
0x14001d513  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001d51a  jz      short loc_14001D53B
0x14001d51c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d523  mov     r9d, 1Eh
0x14001d529  mov     [rsp+58h+Data], rsi
0x14001d52e  mov     rcx, [rcx+40h]
0x14001d532  lea     r8d, [r9-6]
0x14001d536  call    WPP_RECORDER_SF_
0x14001d53b  mov     rcx, rdi
0x14001d53e  call    I8xUpdateSysButtonCapsGetPendedIrp
0x14001d543  test    rax, rax
0x14001d546  jz      short loc_14001D558
0x14001d548  xor     edx, edx
0x14001d54a  mov     r8d, 0C000009Dh
0x14001d550  mov     rcx, rax; Irp
0x14001d553  call    I8xCompleteSysButtonIrp
0x14001d558  lea     rbx, [rdi+2A0h]
0x14001d55f  xor     edx, edx; Enable
0x14001d561  mov     rcx, rbx; SymbolicLinkName
0x14001d564  call    cs:__imp_IoSetDeviceInterfaceState
0x14001d56b  nop     dword ptr [rax+rax+00h]
0x14001d570  mov     dl, 1; Enable
0x14001d572  mov     rcx, rbx; SymbolicLinkName
0x14001d575  call    cs:__imp_IoSetDeviceInterfaceState
0x14001d57c  nop     dword ptr [rax+rax+00h]
0x14001d581  jmp     short loc_14001D5B9
0x14001d583  lea     rbx, WPP_RECORDER_INITIALIZED
0x14001d58a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001d591  jz      short loc_14001D5B9
0x14001d593  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d59a  lea     rsi, WPP_9a74d45702a83a61696de9b252942f2f_Traceguids
0x14001d5a1  mov     r9d, 1Fh
0x14001d5a7  mov     [rsp+58h+Data], rsi
0x14001d5ac  mov     rcx, [rcx+40h]
0x14001d5b0  lea     r8d, [r9-6]
0x14001d5b4  call    WPP_RECORDER_SF_
0x14001d5b9  mov     rcx, [r14]; IoWorkItem
0x14001d5bc  call    cs:__imp_IoFreeWorkItem
0x14001d5c3  nop     dword ptr [rax+rax+00h]
0x14001d5c8  xor     edx, edx; Tag
0x14001d5ca  mov     rcx, r14; P
0x14001d5cd  call    cs:__imp_ExFreePoolWithTag
0x14001d5d4  nop     dword ptr [rax+rax+00h]
0x14001d5d9  mov     rbx, [rsp+58h+arg_10]
0x14001d5de  add     rsp, 40h
0x14001d5e2  pop     r14
0x14001d5e4  pop     rdi
0x14001d5e5  pop     rsi
0x14001d5e6  retn
```
