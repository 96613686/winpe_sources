# MPInitializeEx

- ea: `0x140037c40`
- end: `0x14003801b`
- name: `MPInitializeEx`
- size: `987`
- prototype: `__int64 __fastcall(NDIS_HANDLE NdisMiniportHandle)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x14000a290`
- `0x14000c488`
- `0x14000c930`
- `0x1400161f0`
- `0x140016700`
- `0x140037c40`

## import_xrefs

- `NDIS!NdisOpenConfigurationEx` at `0x140037d82`
- `NDIS!NdisOpenConfigurationEx` at `0x140037f64`
- `NDIS!NdisOpenConfigurationEx` at `0x140037d82`
- `NDIS!NdisOpenConfigurationEx` at `0x140037f64`
- `NDIS!NdisReadNetworkAddress` at `0x140037f8b`
- `NDIS!NdisReadNetworkAddress` at `0x140037f8b`
- `NDIS!NdisMSetMiniportAttributes` at `0x140037e88`
- `NDIS!NdisMSetMiniportAttributes` at `0x140037f42`
- `NDIS!NdisMSetMiniportAttributes` at `0x140037e88`
- `NDIS!NdisMSetMiniportAttributes` at `0x140037f42`
- `NDIS!NdisCloseConfiguration` at `0x140037e20`
- `NDIS!NdisCloseConfiguration` at `0x140037e47`
- `NDIS!NdisCloseConfiguration` at `0x140037f9c`
- `NDIS!NdisCloseConfiguration` at `0x140037e20`
- `NDIS!NdisCloseConfiguration` at `0x140037e47`
- `NDIS!NdisCloseConfiguration` at `0x140037f9c`
- `NDIS!NdisReadConfiguration` at `0x140037e09`
- `NDIS!NdisReadConfiguration` at `0x140037e09`

## pseudocode

```c
NDIS_STATUS __fastcall MPInitializeEx(NDIS_HANDLE NdisMiniportHandle)
{
  NDIS_STATUS result; // eax
  __int64 MiniportCB; // rbx
  char v4; // al
  int Status; // [rsp+30h] [rbp-D0h] BYREF
  PVOID ConfigurationHandle; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int NetworkAddressLength; // [rsp+40h] [rbp-C0h] BYREF
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+48h] [rbp-B8h] BYREF
  _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING Keyword; // [rsp+68h] [rbp-98h] BYREF
  __int128 MiniportAttributes; // [rsp+78h] [rbp-88h] BYREF
  __int128 MiniportAttributes_16; // [rsp+88h] [rbp-78h]
  union _NDIS_MINIPORT_ADAPTER_ATTRIBUTES MiniportAttributes_40; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v14; // [rsp+180h] [rbp+80h] BYREF
  _DWORD v15[16]; // [rsp+190h] [rbp+90h] BYREF

  Status = 0;
  ConfigurationHandle = 0;
  NetworkAddressLength = 0;
  MiniportAttributes = 0;
  MiniportAttributes_16 = 0;
  memset(&MiniportAttributes_40, 0, sizeof(MiniportAttributes_40));
  v15[0] = 65793;
  v15[1] = 65797;
  v15[2] = 65811;
  v14 = 0;
  memset(&ConfigObject, 0, sizeof(ConfigObject));
  v15[3] = 67174661;
  v15[4] = 67174784;
  v15[5] = 67174786;
  v15[6] = 67174785;
  v15[7] = -33550335;
  v15[8] = -33550334;
  v15[9] = -33550333;
  v15[10] = -33550329;
  v15[11] = 65795;
  v15[12] = -50265856;
  v15[13] = -50265855;
  v15[14] = -50265854;
  v15[15] = 65804;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids);
  }
  ConfigObject.Header = (NDIS_OBJECT_HEADER)1573289;
  ConfigObject.NdisHandle = NdisMiniportHandle;
  result = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
  Status = result;
  if ( !result )
  {
    Keyword.Buffer = L"MiniportName";
    ParameterValue = 0;
    *(_QWORD *)&Keyword.Length = 1703960;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterString);
    if ( Status )
    {
      NdisCloseConfiguration(ConfigurationHandle);
    }
    else
    {
      MiniportCB = NdisWanAllocateMiniportCB((PCUNICODE_STRING)&ParameterValue->ParameterData);
      NdisCloseConfiguration(ConfigurationHandle);
      if ( !MiniportCB )
        return -1073741823;
      *(_DWORD *)(MiniportCB + 16) = 0;
      *(_QWORD *)(MiniportCB + 40) = NdisMiniportHandle;
      LODWORD(MiniportAttributes) = 2097566;
      *((_QWORD *)&MiniportAttributes + 1) = MiniportCB;
      *(_QWORD *)&MiniportAttributes_16 = 32;
      DWORD2(MiniportAttributes_16) = 0;
      Status = NdisMSetMiniportAttributes(NdisMiniportHandle, (PNDIS_MINIPORT_ADAPTER_ATTRIBUTES)&MiniportAttributes);
      if ( Status >= 0 )
      {
        MiniportAttributes_40.AddDeviceRegistrationAttributes.Flags = glMaxMTU;
        MiniportAttributes_40.Header = (NDIS_OBJECT_HEADER)14680479;
        memset(&MiniportAttributes_40.HardwareAssistAttributes.CurrentReceiveFilterCapabilities, 255, 32);
        MiniportAttributes_40.GeneralAttributes.LookaheadSize = glMRRU;
        MiniportAttributes_40.GeneralAttributes.PowerManagementCapabilities = (PNDIS_PNP_CAPABILITIES)&v14;
        MiniportAttributes_40.GeneralAttributes.SupportedOidList = v15;
        MiniportAttributes_40.AddDeviceRegistrationAttributes.MiniportAddDeviceContext = 0;
        *((_QWORD *)&MiniportAttributes_40.HardwareAssistAttributes + 7) = 1;
        v14 = 0u;
        *((_QWORD *)&MiniportAttributes_40.HardwareAssistAttributes + 10) = 0x180000007LL;
        MiniportAttributes_40.GeneralAttributes.MacAddressLength = 0;
        MiniportAttributes_40.GeneralAttributes.RecvScaleCapabilities = 0;
        *((_QWORD *)&MiniportAttributes_40.HardwareAssistAttributes + 21) = 3;
        MiniportAttributes_40.GeneralAttributes.ConnectionType = NET_IF_CONNECTION_DEDICATED;
        MiniportAttributes_40.GeneralAttributes.IfType = 6;
        MiniportAttributes_40.GeneralAttributes.IfConnectorPresent = 0;
        MiniportAttributes_40.GeneralAttributes.SupportedPauseFunctions = 0;
        MiniportAttributes_40.GeneralAttributes.SupportedOidListLength = 64;
        Status = NdisMSetMiniportAttributes(NdisMiniportHandle, &MiniportAttributes_40);
        if ( Status >= 0 )
        {
          Status = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
          if ( Status
            || (NdisReadNetworkAddress(&Status, (PVOID *)(MiniportCB + 120), &NetworkAddressLength, ConfigurationHandle),
                NdisCloseConfiguration(ConfigurationHandle),
                Status)
            || NetworkAddressLength != 6 )
          {
            v4 = MEMORY[0xFFFFF78000000321] ^ MEMORY[0xFFFFF78000000015];
            *(_BYTE *)(MiniportCB + 120) = (MEMORY[0xFFFFF78000000322] ^ MEMORY[0xFFFFF78000000016]) & 0xFE;
            *(_BYTE *)(MiniportCB + 121) = v4;
            *(_DWORD *)(MiniportCB + 122) = 1396789792;
          }
          _InterlockedIncrement((volatile signed __int32 *)(MiniportCB + 16));
          *(_DWORD *)(MiniportCB + 20) = 2;
          return 0;
        }
      }
      NdisWanFreeMiniportCB((PVOID)MiniportCB);
    }
    return Status;
  }
  return result;
}

```

## disassembly

```asm
0x140037c40  push    rbp
0x140037c42  push    rbx
0x140037c43  push    rsi
0x140037c44  push    rdi
0x140037c45  push    r12
0x140037c47  push    r13
0x140037c49  lea     rbp, [rsp-0E8h]
0x140037c51  sub     rsp, 1E8h
0x140037c58  mov     rax, cs:__security_cookie
0x140037c5f  xor     rax, rsp
0x140037c62  mov     [rbp+110h+var_40], rax
0x140037c69  xor     esi, esi
0x140037c6b  xorps   xmm0, xmm0
0x140037c6e  mov     rdi, rcx
0x140037c71  mov     [rsp+210h+Status], esi
0x140037c75  lea     rcx, [rbp+110h+MiniportAttributes+28h]; void *
0x140037c79  mov     [rsp+210h+ConfigurationHandle], rsi
0x140037c7e  xor     edx, edx; Val
0x140037c80  mov     [rsp+210h+NetworkAddressLength], esi
0x140037c84  mov     r8d, 0E0h; Size
0x140037c8a  movups  xmmword ptr [rsp+210h+MiniportAttributes], xmm0
0x140037c8f  movups  xmmword ptr [rbp+110h+MiniportAttributes+10h], xmm0
0x140037c93  call    memset
0x140037c98  xorps   xmm0, xmm0
0x140037c9b  mov     [rbp+110h+var_80], 10101h
0x140037ca5  xorps   xmm1, xmm1
0x140037ca8  mov     [rbp+110h+var_7C], 10105h
0x140037cb2  xor     eax, eax
0x140037cb4  mov     [rbp+110h+var_78], 10113h
0x140037cbe  movups  [rbp+110h+var_90], xmm0
0x140037cc5  mov     qword ptr [rsp+210h+ConfigObject.Flags], rax
0x140037cca  movups  xmmword ptr [rsp+210h+ConfigObject.Header.Type], xmm1
0x140037ccf  mov     [rbp+110h+var_74], 4010105h
0x140037cd9  mov     [rbp+110h+var_70], 4010180h
0x140037ce3  mov     [rbp+110h+var_6C], 4010182h
0x140037ced  mov     [rbp+110h+var_68], 4010181h
0x140037cf7  mov     [rbp+110h+var_64], 0FE001001h
0x140037d01  mov     [rbp+110h+var_60], 0FE001002h
0x140037d0b  mov     [rbp+110h+var_5C], 0FE001003h
0x140037d15  mov     [rbp+110h+var_58], 0FE001007h
0x140037d1f  mov     [rbp+110h+var_54], 10103h
0x140037d29  mov     [rbp+110h+var_50], 0FD010100h
0x140037d33  mov     [rbp+110h+var_4C], 0FD010101h
0x140037d3d  mov     [rbp+110h+var_48], 0FD010102h
0x140037d47  mov     [rbp+110h+var_44], 1010Ch
0x140037d51  mov     rcx, cs:WPP_GLOBAL_Control
0x140037d58  lea     rax, WPP_GLOBAL_Control
0x140037d5f  cmp     rcx, rax
0x140037d62  jz      short loc_140037D6B
0x140037d64  mov     eax, [rcx+2Ch]
0x140037d67  test    al, 2
0x140037d69  jnz     short loc_140037DB6
0x140037d6b  lea     rdx, [rsp+210h+ConfigurationHandle]; ConfigurationHandle
0x140037d70  mov     dword ptr [rsp+210h+ConfigObject.Header.Type], 1801A9h
0x140037d78  lea     rcx, [rsp+210h+ConfigObject]; ConfigObject
0x140037d7d  mov     [rsp+210h+ConfigObject.NdisHandle], rdi
0x140037d82  call    cs:__imp_NdisOpenConfigurationEx
0x140037d89  nop     dword ptr [rax+rax+00h]
0x140037d8e  mov     [rsp+210h+Status], eax
0x140037d92  test    eax, eax
0x140037d94  jz      short loc_140037DD3
0x140037d96  mov     rcx, [rbp+110h+var_40]
0x140037d9d  xor     rcx, rsp; StackCookie
0x140037da0  call    __security_check_cookie
0x140037da5  add     rsp, 1E8h
0x140037dac  pop     r13
0x140037dae  pop     r12
0x140037db0  pop     rdi
0x140037db1  pop     rsi
0x140037db2  pop     rbx
0x140037db3  pop     rbp
0x140037db4  retn
0x140037db6  cmp     byte ptr [rcx+29h], 5
0x140037dba  jb      short loc_140037D6B
0x140037dbc  mov     rcx, [rcx+18h]
0x140037dc0  lea     r8, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids
0x140037dc7  mov     edx, 11h
0x140037dcc  call    WPP_SF_
0x140037dd1  jmp     short loc_140037D6B
0x140037dd3  mov     r8, [rsp+210h+ConfigurationHandle]; ConfigurationHandle
0x140037dd8  lea     rax, aMiniportname; "MiniportName"
0x140037ddf  lea     r9, [rsp+210h+Keyword]; Keyword
0x140037de4  mov     [rsp+210h+Keyword.Buffer], rax
0x140037de9  lea     rdx, [rsp+210h+ParameterValue]; ParameterValue
0x140037dee  mov     [rsp+210h+ParameterValue], rsi
0x140037df3  lea     rcx, [rsp+210h+Status]; Status
0x140037df8  mov     qword ptr [rsp+210h+Keyword.Length], 1A0018h
0x140037e01  mov     [rsp+210h+ParameterType], 2; ParameterType
0x140037e09  call    cs:__imp_NdisReadConfiguration
0x140037e10  nop     dword ptr [rax+rax+00h]
0x140037e15  cmp     [rsp+210h+Status], esi
0x140037e19  jz      short loc_140037E31
0x140037e1b  mov     rcx, [rsp+210h+ConfigurationHandle]; ConfigurationHandle
0x140037e20  call    cs:__imp_NdisCloseConfiguration
0x140037e27  nop     dword ptr [rax+rax+00h]
0x140037e2c  jmp     loc_140038012
0x140037e31  mov     rcx, [rsp+210h+ParameterValue]
0x140037e36  add     rcx, 8; SourceString
0x140037e3a  call    NdisWanAllocateMiniportCB
0x140037e3f  mov     rcx, [rsp+210h+ConfigurationHandle]; ConfigurationHandle
0x140037e44  mov     rbx, rax
0x140037e47  call    cs:__imp_NdisCloseConfiguration
0x140037e4e  nop     dword ptr [rax+rax+00h]
0x140037e53  test    rbx, rbx
0x140037e56  jnz     short loc_140037E62
0x140037e58  mov     eax, 0C0000001h
0x140037e5d  jmp     loc_140037D96
0x140037e62  mov     [rbx+10h], esi
0x140037e65  mov     [rbx+28h], rdi
0x140037e69  mov     dword ptr [rsp+210h+MiniportAttributes], 20019Eh
0x140037e71  mov     qword ptr [rbp+110h+MiniportAttributes+8], rbx
0x140037e75  mov     qword ptr [rbp+110h+MiniportAttributes+10h], 20h ; ' '
0x140037e7d  mov     dword ptr [rbp+110h+MiniportAttributes+18h], esi
0x140037e80  lea     rdx, [rsp+210h+MiniportAttributes]; MiniportAttributes
0x140037e85  mov     rcx, rdi; NdisMiniportHandle
0x140037e88  call    cs:__imp_NdisMSetMiniportAttributes
0x140037e8f  nop     dword ptr [rax+rax+00h]
0x140037e94  mov     [rsp+210h+Status], eax
0x140037e98  test    eax, eax
0x140037e9a  js      loc_14003800A
0x140037ea0  mov     eax, cs:glMaxMTU
0x140037ea6  lea     rdx, [rbp+110h+MiniportAttributes+28h]; MiniportAttributes
0x140037eaa  mov     dword ptr [rbp+110h+MiniportAttributes+38h], eax
0x140037ead  mov     r13d, 6
0x140037eb3  or      rax, 0FFFFFFFFFFFFFFFFh
0x140037eb7  mov     dword ptr [rbp+110h+MiniportAttributes+28h], 0E0019Fh
0x140037ebe  mov     qword ptr [rbp+110h+MiniportAttributes+40h], rax
0x140037ec2  mov     rcx, rdi; NdisMiniportHandle
0x140037ec5  mov     qword ptr [rbp+110h+MiniportAttributes+50h], rax
0x140037ec9  mov     qword ptr [rbp+110h+MiniportAttributes+48h], rax
0x140037ecd  mov     qword ptr [rbp+110h+MiniportAttributes+58h], rax
0x140037ed1  mov     eax, cs:glMRRU
0x140037ed7  mov     dword ptr [rbp+110h+MiniportAttributes+68h], eax
0x140037eda  lea     rax, [rbp+110h+var_90]
0x140037ee1  mov     qword ptr [rbp+110h+MiniportAttributes+70h], rax
0x140037ee5  lea     rax, [rbp+110h+var_80]
0x140037eec  mov     [rbp+110h+var_A8], rax
0x140037ef0  mov     qword ptr [rbp+110h+MiniportAttributes+30h], rsi
0x140037ef4  mov     qword ptr [rbp+110h+MiniportAttributes+60h], 1
0x140037efc  mov     qword ptr [rbp+110h+var_90], rsi
0x140037f03  mov     qword ptr [rbp+110h+var_90+8], rsi
0x140037f0a  mov     dword ptr [rbp+110h+MiniportAttributes+78h], 80000007h
0x140037f11  mov     dword ptr [rbp+110h+MiniportAttributes+7Ch], 1
0x140037f18  mov     word ptr [rbp+110h+MiniportAttributes+84h], si
0x140037f1c  mov     qword ptr [rbp+110h+MiniportAttributes+0C8h], rsi
0x140037f20  mov     qword ptr [rbp+110h+MiniportAttributes+0D0h], 3
0x140037f28  mov     dword ptr [rbp+110h+MiniportAttributes+0D8h], 1
0x140037f2f  mov     word ptr [rbp+110h+MiniportAttributes+0DCh], r13w
0x140037f34  mov     byte ptr [rbp+110h+MiniportAttributes+0DEh], sil
0x140037f38  mov     [rbp+110h+var_B4], esi
0x140037f3b  mov     [rbp+110h+var_A0], 40h ; '@'
0x140037f42  call    cs:__imp_NdisMSetMiniportAttributes
0x140037f49  nop     dword ptr [rax+rax+00h]
0x140037f4e  mov     [rsp+210h+Status], eax
0x140037f52  test    eax, eax
0x140037f54  js      loc_14003800A
0x140037f5a  lea     rdx, [rsp+210h+ConfigurationHandle]; ConfigurationHandle
0x140037f5f  lea     rcx, [rsp+210h+ConfigObject]; ConfigObject
0x140037f64  call    cs:__imp_NdisOpenConfigurationEx
0x140037f6b  nop     dword ptr [rax+rax+00h]
0x140037f70  mov     [rsp+210h+Status], eax
0x140037f74  test    eax, eax
0x140037f76  jnz     short loc_140037FB5
0x140037f78  mov     r9, [rsp+210h+ConfigurationHandle]; ConfigurationHandle
0x140037f7d  lea     rdx, [rbx+78h]; NetworkAddress
0x140037f81  lea     r8, [rsp+210h+NetworkAddressLength]; NetworkAddressLength
0x140037f86  lea     rcx, [rsp+210h+Status]; Status
0x140037f8b  call    cs:__imp_NdisReadNetworkAddress
0x140037f92  nop     dword ptr [rax+rax+00h]
0x140037f97  mov     rcx, [rsp+210h+ConfigurationHandle]; ConfigurationHandle
0x140037f9c  call    cs:__imp_NdisCloseConfiguration
0x140037fa3  nop     dword ptr [rax+rax+00h]
0x140037fa8  cmp     [rsp+210h+Status], esi
0x140037fac  jnz     short loc_140037FB5
0x140037fae  cmp     [rsp+210h+NetworkAddressLength], r13d
0x140037fb3  jz      short loc_140037FF8
0x140037fb5  mov     rcx, 0FFFFF78000000320h
0x140037fbf  mov     rax, 0FFFFF78000000014h
0x140037fc9  mov     rcx, [rcx]
0x140037fcc  mov     rax, [rax]
0x140037fcf  mov     edx, ecx
0x140037fd1  mov     r8d, eax
0x140037fd4  shr     edx, 10h
0x140037fd7  shr     r8d, 10h
0x140037fdb  xor     r8b, dl
0x140037fde  shr     eax, 8
0x140037fe1  and     r8b, 0FEh
0x140037fe5  shr     ecx, 8
0x140037fe8  xor     al, cl
0x140037fea  mov     [rbx+78h], r8b
0x140037fee  mov     [rbx+79h], al
0x140037ff1  mov     dword ptr [rbx+7Ah], 53415220h
0x140037ff8  lock inc dword ptr [rbx+10h]
0x140037ffc  mov     dword ptr [rbx+14h], 2
0x140038003  xor     eax, eax
0x140038005  jmp     loc_140037D96
0x14003800a  mov     rcx, rbx; P
0x14003800d  call    NdisWanFreeMiniportCB
0x140038012  mov     eax, [rsp+210h+Status]
0x140038016  jmp     loc_140037D96
```
