# ReadRegistrySettings

- ea: `0x14000dca0`
- end: `0x14000e27f`
- name: `ReadRegistrySettings`
- size: `1503`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14000d5e0`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x14000dca0`

## import_xrefs

- `NDIS!NdisReadConfiguration` at `0x14000de7b`
- `NDIS!NdisReadConfiguration` at `0x14000def7`
- `NDIS!NdisReadConfiguration` at `0x14000df9d`
- `NDIS!NdisReadConfiguration` at `0x14000e047`
- `NDIS!NdisReadConfiguration` at `0x14000e0ea`
- `NDIS!NdisReadConfiguration` at `0x14000e199`
- `NDIS!NdisReadConfiguration` at `0x14000de7b`
- `NDIS!NdisReadConfiguration` at `0x14000def7`
- `NDIS!NdisReadConfiguration` at `0x14000df9d`
- `NDIS!NdisReadConfiguration` at `0x14000e047`
- `NDIS!NdisReadConfiguration` at `0x14000e0ea`
- `NDIS!NdisReadConfiguration` at `0x14000e199`
- `NDIS!NdisCloseConfiguration` at `0x14000e228`
- `NDIS!NdisCloseConfiguration` at `0x14000e228`
- `NDIS!NdisOpenConfigurationEx` at `0x14000dd2e`
- `NDIS!NdisOpenConfigurationEx` at `0x14000dd2e`

## string_xrefs

- `0x14000e0c2`: `fAcceptAnyService`

## pseudocode

```c
__int64 __fastcall ReadRegistrySettings(__int64 a1)
{
  PVOID v2; // r8
  PNDIS_CONFIGURATION_PARAMETER v3; // rax
  ULONG IntegerData; // ecx
  ULONG v5; // edi
  ULONG v6; // ecx
  bool v7; // al
  ULONG v8; // edx
  UNICODE_STRING Keyword; // [rsp+30h] [rbp-30h] BYREF
  _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+40h] [rbp-20h] BYREF
  int Status; // [rsp+A0h] [rbp+40h] BYREF
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+A8h] [rbp+48h] BYREF
  PVOID ConfigurationHandle; // [rsp+B0h] [rbp+50h] BYREF

  Status = -1073741823;
  ConfigurationHandle = 0;
  ParameterValue = 0;
  memset(&ConfigObject, 0, sizeof(ConfigObject));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
  ConfigObject.NdisHandle = *(NDIS_HANDLE *)(a1 + 72);
  ConfigObject.Header = (NDIS_OBJECT_HEADER)1573289;
  Status = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
  if ( Status )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)Status;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
    }
    *(_BYTE *)(a1 + 152) = 1;
    Status = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
    }
    *(_DWORD *)(a1 + 672) = 3;
    Status = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
    }
    *(_DWORD *)(a1 + 676) = 1;
    Status = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
    }
    v2 = ConfigurationHandle;
    Keyword.Buffer = L"WanEndPoints";
    *(_DWORD *)(a1 + 680) = 1;
    Status = 0;
    *(_QWORD *)&Keyword.Length = 1703960;
    NdisReadConfiguration(&Status, &ParameterValue, v2, &Keyword, NdisParameterInteger);
    if ( !Status )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
      }
      v3 = ParameterValue;
      *(_DWORD *)(a1 + 676) = 1;
      *(_DWORD *)(a1 + 680) = v3->ParameterData.IntegerData;
    }
    Keyword.Buffer = L"MaxTimeouts";
    Status = 0;
    *(_QWORD *)&Keyword.Length = 1572886;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
      }
      Status = 0;
      IntegerData = 3;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
      }
      IntegerData = ParameterValue->ParameterData.IntegerData;
    }
    *(_DWORD *)(a1 + 688) = IntegerData;
    Keyword.Buffer = L"SendTimeout";
    *(_QWORD *)&Keyword.Length = 1572886;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    v5 = 5000;
    if ( Status )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
      }
      Status = 0;
      v6 = 5000;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
      }
      v6 = ParameterValue->ParameterData.IntegerData;
    }
    *(_DWORD *)(a1 + 692) = v6;
    Keyword.Buffer = L"RecvTimeout";
    *(_QWORD *)&Keyword.Length = 1572886;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
      }
      Status = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
      }
      v5 = ParameterValue->ParameterData.IntegerData;
    }
    *(_DWORD *)(a1 + 696) = v5;
    Keyword.Buffer = L"fAcceptAnyService";
    *(_QWORD *)&Keyword.Length = 2359330;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
      }
      Status = 0;
      v7 = 1;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
      }
      v7 = ParameterValue->ParameterData.IntegerData != 0;
    }
    *(_BYTE *)(a1 + 704) = v7;
    Keyword.Buffer = L"SendWindowSize";
    *(_QWORD *)&Keyword.Length = 1966108;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
      }
      Status = 0;
      v8 = 32;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
      }
      v8 = 32;
      if ( ParameterValue->ParameterData.IntegerData - 1 <= 0x1E )
        v8 = ParameterValue->ParameterData.IntegerData;
    }
    *(_DWORD *)(a1 + 700) = v8;
    NdisCloseConfiguration(ConfigurationHandle);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      49,
      WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids,
      (unsigned int)Status);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000dca0  mov     [rsp-38h+arg_18], rbx
0x14000dca5  push    rbp
0x14000dca6  push    rsi
0x14000dca7  push    rdi
0x14000dca8  push    r12
0x14000dcaa  push    r13
0x14000dcac  push    r14
0x14000dcae  push    r15
0x14000dcb0  mov     rbp, rsp
0x14000dcb3  sub     rsp, 60h
0x14000dcb7  xor     r15d, r15d
0x14000dcba  mov     [rbp+Status], 0C0000001h
0x14000dcc1  xor     eax, eax
0x14000dcc3  mov     [rbp+ConfigurationHandle], r15
0x14000dcc7  xorps   xmm0, xmm0
0x14000dcca  mov     qword ptr [rbp+ConfigObject.Flags], rax
0x14000dcce  mov     rbx, rcx
0x14000dcd1  mov     [rbp+ParameterValue], r15
0x14000dcd5  movups  xmmword ptr [rbp+ConfigObject.Header.Type], xmm0
0x14000dcd9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dce0  lea     r12, WPP_GLOBAL_Control
0x14000dce7  lea     r14d, [r15+3]
0x14000dceb  lea     r13, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x14000dcf2  lea     esi, [rax+1]
0x14000dcf5  cmp     rcx, r12
0x14000dcf8  jz      short loc_14000DD17
0x14000dcfa  mov     eax, [rcx+2Ch]
0x14000dcfd  test    sil, al
0x14000dd00  jz      short loc_14000DD17
0x14000dd02  cmp     [rcx+29h], r14b
0x14000dd06  jb      short loc_14000DD17
0x14000dd08  mov     rcx, [rcx+18h]
0x14000dd0c  lea     edx, [rsi+15h]
0x14000dd0f  mov     r8, r13
0x14000dd12  call    WPP_SF_
0x14000dd17  mov     rax, [rbx+48h]
0x14000dd1b  lea     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14000dd1f  lea     rcx, [rbp+ConfigObject]; ConfigObject
0x14000dd23  mov     [rbp+ConfigObject.NdisHandle], rax
0x14000dd27  mov     dword ptr [rbp+ConfigObject.Header.Type], 1801A9h
0x14000dd2e  call    cs:__imp_NdisOpenConfigurationEx
0x14000dd35  nop     dword ptr [rax+rax+00h]
0x14000dd3a  mov     [rbp+Status], eax
0x14000dd3d  test    eax, eax
0x14000dd3f  jz      short loc_14000DD7D
0x14000dd41  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dd48  cmp     rcx, r12
0x14000dd4b  jz      loc_14000E263
0x14000dd51  mov     eax, [rcx+2Ch]
0x14000dd54  test    sil, al
0x14000dd57  jz      loc_14000E234
0x14000dd5d  cmp     [rcx+29h], sil
0x14000dd61  jb      loc_14000E234
0x14000dd67  mov     rcx, [rcx+18h]
0x14000dd6b  mov     edx, 17h
0x14000dd70  mov     r8, r13
0x14000dd73  call    WPP_SF_
0x14000dd78  jmp     loc_14000E234
0x14000dd7d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dd84  cmp     rcx, r12
0x14000dd87  jz      short loc_14000DDA8
0x14000dd89  mov     eax, [rcx+2Ch]
0x14000dd8c  test    sil, al
0x14000dd8f  jz      short loc_14000DDA8
0x14000dd91  cmp     [rcx+29h], r14b
0x14000dd95  jb      short loc_14000DDA8
0x14000dd97  mov     rcx, [rcx+18h]
0x14000dd9b  mov     edx, 19h
0x14000dda0  mov     r8, r13
0x14000dda3  call    WPP_SF_
0x14000dda8  mov     [rbx+98h], sil
0x14000ddaf  mov     [rbp+Status], r15d
0x14000ddb3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ddba  cmp     rcx, r12
0x14000ddbd  jz      short loc_14000DDDE
0x14000ddbf  mov     eax, [rcx+2Ch]
0x14000ddc2  test    sil, al
0x14000ddc5  jz      short loc_14000DDDE
0x14000ddc7  cmp     [rcx+29h], r14b
0x14000ddcb  jb      short loc_14000DDDE
0x14000ddcd  mov     rcx, [rcx+18h]
0x14000ddd1  mov     edx, 21h ; '!'
0x14000ddd6  mov     r8, r13
0x14000ddd9  call    WPP_SF_
0x14000ddde  mov     [rbx+2A0h], r14d
0x14000dde5  mov     [rbp+Status], r15d
0x14000dde9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ddf0  cmp     rcx, r12
0x14000ddf3  jz      short loc_14000DE14
0x14000ddf5  mov     eax, [rcx+2Ch]
0x14000ddf8  test    sil, al
0x14000ddfb  jz      short loc_14000DE14
0x14000ddfd  cmp     [rcx+29h], r14b
0x14000de01  jb      short loc_14000DE14
0x14000de03  mov     rcx, [rcx+18h]
0x14000de07  mov     edx, 23h ; '#'
0x14000de0c  mov     r8, r13
0x14000de0f  call    WPP_SF_
0x14000de14  mov     [rbx+2A4h], esi
0x14000de1a  mov     [rbp+Status], r15d
0x14000de1e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de25  cmp     rcx, r12
0x14000de28  jz      short loc_14000DE49
0x14000de2a  mov     eax, [rcx+2Ch]
0x14000de2d  test    sil, al
0x14000de30  jz      short loc_14000DE49
0x14000de32  cmp     [rcx+29h], r14b
0x14000de36  jb      short loc_14000DE49
0x14000de38  mov     rcx, [rcx+18h]
0x14000de3c  mov     edx, 25h ; '%'
0x14000de41  mov     r8, r13
0x14000de44  call    WPP_SF_
0x14000de49  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14000de4d  lea     rax, aWanendpoints; "WanEndPoints"
0x14000de54  lea     r9, [rbp+Keyword]; Keyword
0x14000de58  mov     [rbp+Keyword.Buffer], rax
0x14000de5c  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14000de60  mov     [rbx+2A8h], esi
0x14000de66  lea     rcx, [rbp+Status]; Status
0x14000de6a  mov     [rbp+Status], r15d
0x14000de6e  mov     qword ptr [rbp+Keyword.Length], 1A0018h
0x14000de76  mov     [rsp+60h+ParameterType], r15d; ParameterType
0x14000de7b  call    cs:__imp_NdisReadConfiguration
0x14000de82  nop     dword ptr [rax+rax+00h]
0x14000de87  cmp     [rbp+Status], r15d
0x14000de8b  jnz     short loc_14000DECB
0x14000de8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de94  cmp     rcx, r12
0x14000de97  jz      short loc_14000DEB8
0x14000de99  mov     eax, [rcx+2Ch]
0x14000de9c  test    sil, al
0x14000de9f  jz      short loc_14000DEB8
0x14000dea1  cmp     [rcx+29h], r14b
0x14000dea5  jb      short loc_14000DEB8
0x14000dea7  mov     rcx, [rcx+18h]
0x14000deab  mov     edx, 26h ; '&'
0x14000deb0  mov     r8, r13
0x14000deb3  call    WPP_SF_
0x14000deb8  mov     rax, [rbp+ParameterValue]
0x14000debc  mov     [rbx+2A4h], esi
0x14000dec2  mov     ecx, [rax+8]
0x14000dec5  mov     [rbx+2A8h], ecx
0x14000decb  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14000decf  lea     rax, aMaxtimeouts; "MaxTimeouts"
0x14000ded6  lea     r9, [rbp+Keyword]; Keyword
0x14000deda  mov     [rbp+Keyword.Buffer], rax
0x14000dede  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14000dee2  mov     [rbp+Status], r15d
0x14000dee6  lea     rcx, [rbp+Status]; Status
0x14000deea  mov     qword ptr [rbp+Keyword.Length], 180016h
0x14000def2  mov     [rsp+60h+ParameterType], r15d; ParameterType
0x14000def7  call    cs:__imp_NdisReadConfiguration
0x14000defe  nop     dword ptr [rax+rax+00h]
0x14000df03  cmp     [rbp+Status], r15d
0x14000df07  jnz     short loc_14000DF3D
0x14000df09  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df10  cmp     rcx, r12
0x14000df13  jz      short loc_14000DF34
0x14000df15  mov     eax, [rcx+2Ch]
0x14000df18  test    sil, al
0x14000df1b  jz      short loc_14000DF34
0x14000df1d  cmp     [rcx+29h], r14b
0x14000df21  jb      short loc_14000DF34
0x14000df23  mov     rcx, [rcx+18h]
0x14000df27  mov     edx, 27h ; '''
0x14000df2c  mov     r8, r13
0x14000df2f  call    WPP_SF_
0x14000df34  mov     rax, [rbp+ParameterValue]
0x14000df38  mov     ecx, [rax+8]
0x14000df3b  jmp     short loc_14000DF6F
0x14000df3d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df44  cmp     rcx, r12
0x14000df47  jz      short loc_14000DF68
0x14000df49  mov     eax, [rcx+2Ch]
0x14000df4c  test    sil, al
0x14000df4f  jz      short loc_14000DF68
0x14000df51  cmp     [rcx+29h], r14b
0x14000df55  jb      short loc_14000DF68
0x14000df57  mov     rcx, [rcx+18h]
0x14000df5b  mov     edx, 28h ; '('
0x14000df60  mov     r8, r13
0x14000df63  call    WPP_SF_
0x14000df68  mov     [rbp+Status], r15d
0x14000df6c  mov     ecx, r14d
0x14000df6f  mov     [rbx+2B0h], ecx
0x14000df75  lea     rax, aSendtimeout; "SendTimeout"
0x14000df7c  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14000df80  lea     rcx, [rbp+Status]; Status
0x14000df84  lea     r9, [rbp+Keyword]; Keyword
0x14000df88  mov     [rbp+Keyword.Buffer], rax
0x14000df8c  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14000df90  mov     qword ptr [rbp+Keyword.Length], 180016h
0x14000df98  mov     [rsp+60h+ParameterType], r15d; ParameterType
0x14000df9d  call    cs:__imp_NdisReadConfiguration
0x14000dfa4  nop     dword ptr [rax+rax+00h]
0x14000dfa9  mov     edi, 1388h
0x14000dfae  cmp     [rbp+Status], r15d
0x14000dfb2  jnz     short loc_14000DFE8
0x14000dfb4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dfbb  cmp     rcx, r12
0x14000dfbe  jz      short loc_14000DFDF
0x14000dfc0  mov     eax, [rcx+2Ch]
0x14000dfc3  test    sil, al
0x14000dfc6  jz      short loc_14000DFDF
0x14000dfc8  cmp     [rcx+29h], r14b
0x14000dfcc  jb      short loc_14000DFDF
0x14000dfce  mov     rcx, [rcx+18h]
0x14000dfd2  mov     edx, 29h ; ')'
0x14000dfd7  mov     r8, r13
0x14000dfda  call    WPP_SF_
0x14000dfdf  mov     rax, [rbp+ParameterValue]
0x14000dfe3  mov     ecx, [rax+8]
0x14000dfe6  jmp     short loc_14000E019
0x14000dfe8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dfef  cmp     rcx, r12
0x14000dff2  jz      short loc_14000E013
0x14000dff4  mov     eax, [rcx+2Ch]
0x14000dff7  test    sil, al
0x14000dffa  jz      short loc_14000E013
0x14000dffc  cmp     [rcx+29h], r14b
0x14000e000  jb      short loc_14000E013
0x14000e002  mov     rcx, [rcx+18h]
0x14000e006  mov     edx, 2Ah ; '*'
0x14000e00b  mov     r8, r13
0x14000e00e  call    WPP_SF_
0x14000e013  mov     [rbp+Status], r15d
0x14000e017  mov     ecx, edi
0x14000e019  mov     [rbx+2B4h], ecx
0x14000e01f  lea     rax, aRecvtimeout; "RecvTimeout"
0x14000e026  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14000e02a  lea     rcx, [rbp+Status]; Status
0x14000e02e  lea     r9, [rbp+Keyword]; Keyword
0x14000e032  mov     [rbp+Keyword.Buffer], rax
0x14000e036  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14000e03a  mov     qword ptr [rbp+Keyword.Length], 180016h
0x14000e042  mov     [rsp+60h+ParameterType], r15d; ParameterType
0x14000e047  call    cs:__imp_NdisReadConfiguration
0x14000e04e  nop     dword ptr [rax+rax+00h]
0x14000e053  cmp     [rbp+Status], r15d
0x14000e057  jnz     short loc_14000E08D
0x14000e059  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e060  cmp     rcx, r12
0x14000e063  jz      short loc_14000E084
0x14000e065  mov     eax, [rcx+2Ch]
0x14000e068  test    sil, al
0x14000e06b  jz      short loc_14000E084
0x14000e06d  cmp     [rcx+29h], r14b
0x14000e071  jb      short loc_14000E084
0x14000e073  mov     rcx, [rcx+18h]
0x14000e077  mov     edx, 2Bh ; '+'
0x14000e07c  mov     r8, r13
0x14000e07f  call    WPP_SF_
0x14000e084  mov     rax, [rbp+ParameterValue]
0x14000e088  mov     edi, [rax+8]
0x14000e08b  jmp     short loc_14000E0BC
0x14000e08d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e094  cmp     rcx, r12
0x14000e097  jz      short loc_14000E0B8
0x14000e099  mov     eax, [rcx+2Ch]
0x14000e09c  test    sil, al
0x14000e09f  jz      short loc_14000E0B8
0x14000e0a1  cmp     [rcx+29h], r14b
0x14000e0a5  jb      short loc_14000E0B8
0x14000e0a7  mov     rcx, [rcx+18h]
0x14000e0ab  mov     edx, 2Ch ; ','
0x14000e0b0  mov     r8, r13
0x14000e0b3  call    WPP_SF_
0x14000e0b8  mov     [rbp+Status], r15d
0x14000e0bc  mov     [rbx+2B8h], edi
0x14000e0c2  lea     rax, aFacceptanyserv; "fAcceptAnyService"
0x14000e0c9  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14000e0cd  lea     r9, [rbp+Keyword]; Keyword
0x14000e0d1  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14000e0d5  mov     [rbp+Keyword.Buffer], rax
0x14000e0d9  lea     rcx, [rbp+Status]; Status
0x14000e0dd  mov     qword ptr [rbp+Keyword.Length], 240022h
0x14000e0e5  mov     [rsp+60h+ParameterType], r15d; ParameterType
0x14000e0ea  call    cs:__imp_NdisReadConfiguration
0x14000e0f1  nop     dword ptr [rax+rax+00h]
0x14000e0f6  cmp     [rbp+Status], r15d
0x14000e0fa  jnz     short loc_14000E134
0x14000e0fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e103  cmp     rcx, r12
0x14000e106  jz      short loc_14000E127
0x14000e108  mov     eax, [rcx+2Ch]
0x14000e10b  test    sil, al
0x14000e10e  jz      short loc_14000E127
0x14000e110  cmp     [rcx+29h], r14b
0x14000e114  jb      short loc_14000E127
0x14000e116  mov     rcx, [rcx+18h]
0x14000e11a  mov     edx, 2Dh ; '-'
0x14000e11f  mov     r8, r13
0x14000e122  call    WPP_SF_
0x14000e127  mov     rax, [rbp+ParameterValue]
0x14000e12b  cmp     [rax+8], r15d
0x14000e12f  setnbe  al
0x14000e132  jmp     short loc_14000E166
0x14000e134  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e13b  cmp     rcx, r12
0x14000e13e  jz      short loc_14000E15F
  ... truncated ...
```
