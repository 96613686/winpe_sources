# PcpCreateDevice

- ea: `0x14001e2dc`
- end: `0x14001e4d4`
- name: `PcpCreateDevice`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001f4b0`

## callees

- `0x14000eb54`
- `0x140013110`
- `0x140013600`
- `0x14001e2dc`
- `0x14001e4dc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001e369`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e381`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e369`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e381`
- `NDIS!NdisRegisterDeviceEx` at `0x14001e3df`
- `NDIS!NdisRegisterDeviceEx` at `0x14001e3df`
- `NDIS!NdisDeregisterDeviceEx` at `0x14001e48e`
- `NDIS!NdisDeregisterDeviceEx` at `0x14001e48e`

## pseudocode

```c
__int64 PcpCreateDevice()
{
  unsigned int v0; // eax
  int v1; // edi
  unsigned int v2; // ebx
  int v3; // eax
  _NDIS_DEVICE_OBJECT_ATTRIBUTES DeviceObjectAttributes; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v7; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v8[28]; // [rsp+80h] [rbp-80h] BYREF

  DestinationString = 0;
  v7 = 0;
  memset(v8, 0, sizeof(v8));
  v8[14] = PcpDispatch;
  v8[15] = PcpDispatch;
  v8[0] = PcpDispatch;
  v8[18] = PcpDispatch;
  v8[2] = PcpDispatch;
  v8[23] = PcpWmiDispatch;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Psched");
  RtlInitUnicodeString(&v7, L"\\DosDevices\\Psched");
  DeviceObjectAttributes.DeviceName = &DestinationString;
  *(_QWORD *)&DeviceObjectAttributes.Header.Type = 3670400;
  DeviceObjectAttributes.SymbolicName = &v7;
  memset(&DeviceObjectAttributes.ExtensionSize, 0, 24);
  DeviceObjectAttributes.MajorFunctions = (PDRIVER_DISPATCH *)v8;
  v0 = NdisRegisterDeviceEx(
         WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink,
         &DeviceObjectAttributes,
         (PDEVICE_OBJECT *)&WPP_MAIN_CB.Queue.ListEntry.Blink,
         (PNDIS_HANDLE)&WPP_MAIN_CB.DeviceType);
  v1 = v0;
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids, v0);
    }
    v2 = -1073741823;
    if ( v1 < 0 )
      return (unsigned int)v1;
  }
  else
  {
    LODWORD(WPP_MAIN_CB.Queue.ListEntry.Blink[3].Flink) |= 4u;
    v3 = PcpSetDeviceSecurityDescriptor();
    v2 = v3;
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids,
          (unsigned int)v3);
      }
      NdisDeregisterDeviceEx(*(NDIS_HANDLE *)&WPP_MAIN_CB.DeviceType);
      WPP_MAIN_CB.Queue.ListEntry.Blink = 0;
      *(_QWORD *)&WPP_MAIN_CB.DeviceType = 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14001e2dc  mov     [rsp-8+arg_0], rbx
0x14001e2e1  mov     [rsp-8+arg_8], rdi
0x14001e2e6  push    rbp
0x14001e2e7  lea     rbp, [rsp-70h]
0x14001e2ec  sub     rsp, 170h
0x14001e2f3  mov     rax, cs:__security_cookie
0x14001e2fa  xor     rax, rsp
0x14001e2fd  mov     [rbp+70h+var_10], rax
0x14001e301  xorps   xmm0, xmm0
0x14001e304  lea     rcx, [rbp+70h+var_F0]; void *
0x14001e308  xorps   xmm1, xmm1
0x14001e30b  xor     eax, eax
0x14001e30d  xor     edx, edx; Val
0x14001e30f  mov     dword ptr [rsp+170h+DeviceObjectAttributes.DeviceClassGuid], eax
0x14001e313  mov     r8d, 0E0h; Size
0x14001e319  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm0
0x14001e31e  movups  xmmword ptr [rsp+170h+var_108.Length], xmm1
0x14001e323  movups  xmmword ptr [rsp+170h+DeviceObjectAttributes.Header.Type], xmm0
0x14001e328  movups  xmmword ptr [rsp+170h+DeviceObjectAttributes.SymbolicName], xmm0
0x14001e32d  movups  xmmword ptr [rsp+170h+DeviceObjectAttributes.ExtensionSize], xmm0
0x14001e332  call    memset
0x14001e337  lea     rax, PcpDispatch
0x14001e33e  mov     [rbp+70h+var_80], rax
0x14001e342  lea     rdx, aDevicePsched; "\\Device\\Psched"
0x14001e349  mov     [rbp+70h+var_78], rax
0x14001e34d  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x14001e352  mov     [rbp+70h+var_F0], rax
0x14001e356  mov     [rbp+70h+var_60], rax
0x14001e35a  mov     [rbp+70h+var_E0], rax
0x14001e35e  lea     rax, PcpWmiDispatch
0x14001e365  mov     [rbp+70h+var_38], rax
0x14001e369  call    cs:__imp_RtlInitUnicodeString
0x14001e370  nop     dword ptr [rax+rax+00h]
0x14001e375  lea     rdx, aDosdevicesPsch; "\\DosDevices\\Psched"
0x14001e37c  lea     rcx, [rsp+170h+var_108]; DestinationString
0x14001e381  call    cs:__imp_RtlInitUnicodeString
0x14001e388  nop     dword ptr [rax+rax+00h]
0x14001e38d  mov     rcx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink; NdisHandle
0x14001e394  lea     rax, [rsp+170h+DestinationString]
0x14001e399  mov     [rsp+170h+DeviceObjectAttributes.DeviceName], rax
0x14001e39e  lea     r9, WPP_MAIN_CB.DeviceType; NdisDeviceHandle
0x14001e3a5  lea     rax, [rsp+170h+var_108]
0x14001e3aa  mov     qword ptr [rsp+170h+DeviceObjectAttributes.Header.Type], 380180h
0x14001e3b3  mov     [rsp+170h+DeviceObjectAttributes.SymbolicName], rax
0x14001e3b8  lea     r8, WPP_MAIN_CB.Queue+8; pDeviceObject
0x14001e3bf  lea     rax, [rbp+70h+var_F0]
0x14001e3c3  mov     qword ptr [rsp+170h+DeviceObjectAttributes.ExtensionSize], 0
0x14001e3cc  xorps   xmm0, xmm0
0x14001e3cf  mov     [rsp+170h+DeviceObjectAttributes.MajorFunctions], rax
0x14001e3d4  lea     rdx, [rsp+170h+DeviceObjectAttributes]; DeviceObjectAttributes
0x14001e3d9  movdqu  xmmword ptr [rsp+170h+DeviceObjectAttributes.DefaultSDDLString], xmm0
0x14001e3df  call    cs:__imp_NdisRegisterDeviceEx
0x14001e3e6  nop     dword ptr [rax+rax+00h]
0x14001e3eb  mov     edi, eax
0x14001e3ed  test    eax, eax
0x14001e3ef  jz      short loc_14001E437
0x14001e3f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e3f8  lea     rdx, WPP_GLOBAL_Control
0x14001e3ff  cmp     rcx, rdx
0x14001e402  jz      short loc_14001E42B
0x14001e404  cmp     byte ptr [rcx+29h], 2
0x14001e408  jb      short loc_14001E42B
0x14001e40a  test    dword ptr [rcx+2Ch], 800h
0x14001e411  jz      short loc_14001E42B
0x14001e413  mov     rcx, [rcx+18h]
0x14001e417  lea     r8, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids
0x14001e41e  mov     edx, 13h
0x14001e423  mov     r9d, eax
0x14001e426  call    WPP_SF_D
0x14001e42b  test    edi, edi
0x14001e42d  mov     ebx, 0C0000001h
0x14001e432  cmovs   ebx, edi
0x14001e435  jmp     short loc_14001E4B0
0x14001e437  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14001e43e  or      dword ptr [rax+30h], 4
0x14001e442  call    PcpSetDeviceSecurityDescriptor
0x14001e447  mov     ebx, eax
0x14001e449  test    eax, eax
0x14001e44b  jns     short loc_14001E4B0
0x14001e44d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e454  lea     rdx, WPP_GLOBAL_Control
0x14001e45b  cmp     rcx, rdx
0x14001e45e  jz      short loc_14001E487
0x14001e460  cmp     byte ptr [rcx+29h], 2
0x14001e464  jb      short loc_14001E487
0x14001e466  test    dword ptr [rcx+2Ch], 800h
0x14001e46d  jz      short loc_14001E487
0x14001e46f  mov     rcx, [rcx+18h]
0x14001e473  lea     r8, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids
0x14001e47a  mov     edx, 14h
0x14001e47f  mov     r9d, eax
0x14001e482  call    WPP_SF_D
0x14001e487  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceType; NdisDeviceHandle
0x14001e48e  call    cs:__imp_NdisDeregisterDeviceEx
0x14001e495  nop     dword ptr [rax+rax+00h]
0x14001e49a  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, 0
0x14001e4a5  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, 0
0x14001e4b0  mov     eax, ebx
0x14001e4b2  mov     rcx, [rbp+70h+var_10]
0x14001e4b6  xor     rcx, rsp; StackCookie
0x14001e4b9  call    __security_check_cookie
0x14001e4be  lea     r11, [rsp+170h+var_s0]
0x14001e4c6  mov     rbx, [r11+10h]
0x14001e4ca  mov     rdi, [r11+18h]
0x14001e4ce  mov     rsp, r11
0x14001e4d1  pop     rbp
0x14001e4d2  retn
```
