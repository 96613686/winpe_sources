# GetRegistrySettings

- ea: `0x14001e3c0`
- end: `0x14001eb7a`
- name: `GetRegistrySettings`
- size: `1978`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14001ddf0`

## callees

- `0x140001b70`
- `0x14001d940`
- `0x14001dbc8`
- `0x14001dc40`
- `0x14001e3c0`

## import_xrefs

- `NDIS!NdisOpenConfigurationEx` at `0x14001e403`
- `NDIS!NdisOpenConfigurationEx` at `0x14001e403`
- `NDIS!NdisCloseConfiguration` at `0x14001eb46`
- `NDIS!NdisCloseConfiguration` at `0x14001eb46`
- `NDIS!NdisReadConfiguration` at `0x14001e457`
- `NDIS!NdisReadConfiguration` at `0x14001e4b0`
- `NDIS!NdisReadConfiguration` at `0x14001e50e`
- `NDIS!NdisReadConfiguration` at `0x14001e57c`
- `NDIS!NdisReadConfiguration` at `0x14001e5d4`
- `NDIS!NdisReadConfiguration` at `0x14001e626`
- `NDIS!NdisReadConfiguration` at `0x14001e678`
- `NDIS!NdisReadConfiguration` at `0x14001e6da`
- `NDIS!NdisReadConfiguration` at `0x14001e73a`
- `NDIS!NdisReadConfiguration` at `0x14001e791`
- `NDIS!NdisReadConfiguration` at `0x14001e7e6`
- `NDIS!NdisReadConfiguration` at `0x14001e839`
- `NDIS!NdisReadConfiguration` at `0x14001e88e`
- `NDIS!NdisReadConfiguration` at `0x14001e94c`
- `NDIS!NdisReadConfiguration` at `0x14001e9ad`
- `NDIS!NdisReadConfiguration` at `0x14001ea03`
- `NDIS!NdisReadConfiguration` at `0x14001ea59`
- `NDIS!NdisReadConfiguration` at `0x14001eab4`
- `NDIS!NdisReadConfiguration` at `0x14001eb0d`
- `NDIS!NdisReadConfiguration` at `0x14001e457`
- `NDIS!NdisReadConfiguration` at `0x14001e4b0`
- `NDIS!NdisReadConfiguration` at `0x14001e50e`
- `NDIS!NdisReadConfiguration` at `0x14001e57c`
- `NDIS!NdisReadConfiguration` at `0x14001e5d4`
- `NDIS!NdisReadConfiguration` at `0x14001e626`
- `NDIS!NdisReadConfiguration` at `0x14001e678`
- `NDIS!NdisReadConfiguration` at `0x14001e6da`
- `NDIS!NdisReadConfiguration` at `0x14001e73a`
- `NDIS!NdisReadConfiguration` at `0x14001e791`
- `NDIS!NdisReadConfiguration` at `0x14001e7e6`
- `NDIS!NdisReadConfiguration` at `0x14001e839`
- `NDIS!NdisReadConfiguration` at `0x14001e88e`
- `NDIS!NdisReadConfiguration` at `0x14001e94c`
- `NDIS!NdisReadConfiguration` at `0x14001e9ad`
- `NDIS!NdisReadConfiguration` at `0x14001ea03`
- `NDIS!NdisReadConfiguration` at `0x14001ea59`
- `NDIS!NdisReadConfiguration` at `0x14001eab4`
- `NDIS!NdisReadConfiguration` at `0x14001eb0d`

## string_xrefs

- `0x14001e81e`: `LookasideDepth`

## pseudocode

```c
NDIS_STATUS __fastcall GetRegistrySettings(
        void *a1,
        _WORD *a2,
        ULONG *a3,
        ULONG *a4,
        ULONG *a5,
        ULONG *a6,
        ULONG *a7,
        ULONG *a8,
        ULONG *a9,
        USHORT *a10,
        USHORT *a11,
        USHORT *a12,
        ULONG *a13,
        USHORT *a14,
        __int64 *a15,
        __int64 *a16,
        bool *a17,
        bool *a18,
        ULONG *a19,
        bool *a20,
        __int64 *a21)
{
  NDIS_STATUS result; // eax
  PVOID v25; // r8
  ULONG IntegerData; // eax
  unsigned int v27; // edi
  unsigned int *v28; // rbx
  ULONG v29; // ecx
  ULONG v30; // ecx
  ULONG *v31; // rax
  USHORT v32; // bx
  ULONG v33; // ecx
  ULONG v34; // ecx
  ULONG v35; // ecx
  USHORT Length; // cx
  ULONG v37; // eax
  USHORT v38; // cx
  USHORT v39; // cx
  ULONG v40; // ecx
  __int64 v41; // rax
  __int64 FullHostNameFromRegistry; // rax
  char **v43; // rbx
  char *v44; // rax
  __int64 v45; // rcx
  bool v46; // cl
  bool v47; // cl
  ULONG *v48; // rdx
  ULONG v49; // ecx
  bool v50; // cl
  __int64 v51; // rcx
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+30h] [rbp-40h] BYREF
  PVOID ConfigurationHandle; // [rsp+38h] [rbp-38h] BYREF
  UNICODE_STRING Keyword; // [rsp+40h] [rbp-30h] BYREF
  _NDIS_CONFIGURATION_OBJECT ConfigObject; // [rsp+50h] [rbp-20h] BYREF
  int Status; // [rsp+A0h] [rbp+30h] BYREF

  ConfigObject.NdisHandle = a1;
  Status = 0;
  ConfigurationHandle = 0;
  *(_QWORD *)&ConfigObject.Flags = 0;
  ParameterValue = 0;
  *(_QWORD *)&ConfigObject.Header.Type = 1573289;
  result = NdisOpenConfigurationEx(&ConfigObject, &ConfigurationHandle);
  Status = result;
  if ( !result )
  {
    v25 = ConfigurationHandle;
    Keyword.Buffer = L"VpnMediaType";
    *a2 = 1;
    *(_QWORD *)&Keyword.Length = 1703960;
    NdisReadConfiguration(&Status, &ParameterValue, v25, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      *a3 = 2;
      Status = 0;
    }
    else
    {
      IntegerData = ParameterValue->ParameterData.IntegerData;
      *a3 = IntegerData;
      if ( IntegerData - 1 > 1 )
        goto LABEL_32;
    }
    Keyword.Buffer = L"MaxSendTimeoutMs";
    *(_QWORD *)&Keyword.Length = 2228256;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    v27 = 0x7FFFFFFF;
    v28 = a5;
    if ( Status )
    {
      *a5 = 10000;
      Status = 0;
    }
    else
    {
      v29 = ParameterValue->ParameterData.IntegerData;
      *a5 = v29;
      if ( !v29 )
        *v28 = 0x7FFFFFFF;
    }
    Keyword.Buffer = L"InitialSendTimeoutMs";
    *(_QWORD *)&Keyword.Length = 2752552;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      Status = 0;
      *a6 = 1000;
    }
    else
    {
      v30 = ParameterValue->ParameterData.IntegerData;
      v31 = a6;
      *a6 = v30;
      if ( v30 )
        v27 = v30;
      else
        *v31 = 0x7FFFFFFF;
      if ( v27 > *v28 )
        *v31 = *v28;
    }
    Keyword.Buffer = L"MaxRetransmits";
    *(_QWORD *)&Keyword.Length = 1966108;
    v32 = 30;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      Status = 0;
      v33 = 5;
    }
    else
    {
      v33 = ParameterValue->ParameterData.IntegerData;
    }
    *a7 = v33;
    Keyword.Buffer = L"HelloMs";
    *(_QWORD *)&Keyword.Length = 1048590;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      Status = 0;
      v34 = 40000;
    }
    else
    {
      v34 = ParameterValue->ParameterData.IntegerData;
    }
    *a8 = v34;
    Keyword.Buffer = L"MaxAckDelayMs";
    *(_QWORD *)&Keyword.Length = 1835034;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      Status = 0;
      v35 = 500;
    }
    else
    {
      v35 = ParameterValue->ParameterData.IntegerData;
    }
    *a9 = v35;
    Keyword.Buffer = L"MaxOutOfOrder";
    *(_QWORD *)&Keyword.Length = 1835034;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      Status = 0;
      *a10 = 100;
    }
    else
    {
      Length = ParameterValue->ParameterData.StringData.Length;
      *a10 = Length;
      if ( Length > 0x4000u )
        goto LABEL_32;
    }
    Keyword.Buffer = L"OutgoingRole";
    *(_QWORD *)&Keyword.Length = 1703960;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      *a4 = 2;
      Status = 0;
    }
    else
    {
      v37 = ParameterValue->ParameterData.IntegerData;
      *a4 = v37;
      if ( v37 - 1 > 1 )
      {
LABEL_32:
        Status = -1073676267;
LABEL_77:
        NdisCloseConfiguration(ConfigurationHandle);
        return Status;
      }
    }
    Keyword.Buffer = L"ControlReceiveWindow";
    *(_QWORD *)&Keyword.Length = 2752552;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      Status = 0;
      v38 = 8;
    }
    else
    {
      v38 = ParameterValue->ParameterData.StringData.Length;
    }
    *a11 = v38;
    Keyword.Buffer = L"PayloadReceiveWindow";
    *(_QWORD *)&Keyword.Length = 2752552;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      Status = 0;
      v39 = 0;
    }
    else
    {
      v39 = ParameterValue->ParameterData.StringData.Length;
    }
    *a12 = v39;
    Keyword.Buffer = L"PayloadSendWindow";
    *(_QWORD *)&Keyword.Length = 2359330;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
    {
      Status = 0;
      v40 = 16;
    }
    else
    {
      v40 = ParameterValue->ParameterData.IntegerData;
    }
    *a13 = v40;
    Keyword.Buffer = L"LookasideDepth";
    *(_QWORD *)&Keyword.Length = 1966108;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
    if ( Status )
      Status = 0;
    else
      v32 = ParameterValue->ParameterData.StringData.Length;
    *a14 = v32;
    Keyword.Buffer = L"HostName";
    *(_QWORD *)&Keyword.Length = 1179664;
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterString);
    if ( Status )
    {
      FullHostNameFromRegistry = GetFullHostNameFromRegistry();
      v43 = (char **)a15;
      *a15 = FullHostNameFromRegistry;
      if ( FullHostNameFromRegistry )
        goto LABEL_55;
      v44 = (char *)ALLOC_NONPAGED(6, 1767125580);
      if ( v44 )
      {
        strcpy(v44, "NONE");
        v44[5] = 0;
      }
      *v43 = v44;
      if ( v44 )
      {
LABEL_55:
        Status = 0;
        goto LABEL_56;
      }
    }
    else
    {
      v41 = StrDupUnicodeToAscii(
              ParameterValue->ParameterData.StringData.Buffer,
              ParameterValue->ParameterData.StringData.Length);
      *a15 = v41;
      if ( v41 )
      {
        if ( Status )
          goto LABEL_77;
LABEL_56:
        Keyword.Buffer = L"Password";
        *(_QWORD *)&Keyword.Length = 1179664;
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterString);
        if ( Status )
        {
          Status = 0;
          v45 = 0;
        }
        else
        {
          v45 = StrDupUnicodeToAscii(
                  ParameterValue->ParameterData.StringData.Buffer,
                  ParameterValue->ParameterData.StringData.Length);
        }
        *a16 = v45;
        Keyword.Buffer = L"IgnoreFramingMismatch";
        *(_QWORD *)&Keyword.Length = 2883626;
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
        if ( Status )
        {
          Status = 0;
          v46 = 1;
        }
        else
        {
          v46 = ParameterValue->ParameterData.IntegerData != 0;
        }
        *a17 = v46;
        Keyword.Buffer = L"ExclusiveTunnels";
        *(_QWORD *)&Keyword.Length = 2228256;
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
        if ( Status )
        {
          Status = 0;
          v47 = 0;
        }
        else
        {
          v47 = ParameterValue->ParameterData.IntegerData != 0;
        }
        *a18 = v47;
        Keyword.Buffer = L"UseExistingRoutes";
        *(_QWORD *)&Keyword.Length = 2359330;
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
        v48 = a19;
        if ( Status )
        {
          Status = 0;
        }
        else
        {
          v49 = ParameterValue->ParameterData.IntegerData;
          *a19 = v49;
          if ( v49 <= 2 )
            goto LABEL_70;
        }
        *v48 = 2;
LABEL_70:
        Keyword.Buffer = L"DisableUdpChecksums";
        *(_QWORD *)&Keyword.Length = 2621478;
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
        if ( Status )
        {
          Status = 0;
          v50 = 1;
        }
        else
        {
          v50 = ParameterValue->ParameterData.IntegerData != 0;
        }
        *a20 = v50;
        Keyword.Buffer = L"DriverDesc";
        *(_QWORD *)&Keyword.Length = 1441812;
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterString);
        if ( Status )
        {
          Status = 0;
          v51 = 0;
        }
        else
        {
          v51 = StrDupNdisString(&ParameterValue->ParameterData);
        }
        *a21 = v51;
        goto LABEL_77;
      }
    }
    Status = -1073741670;
    goto LABEL_77;
  }
  return result;
}

```

## disassembly

```asm
0x14001e3c0  mov     [rsp-28h+arg_18], rbx
0x14001e3c5  push    rbp
0x14001e3c6  push    rsi
0x14001e3c7  push    rdi
0x14001e3c8  push    r14
0x14001e3ca  push    r15
0x14001e3cc  mov     rbp, rsp
0x14001e3cf  sub     rsp, 70h
0x14001e3d3  xor     r14d, r14d
0x14001e3d6  mov     [rbp+ConfigObject.NdisHandle], rcx
0x14001e3da  mov     rdi, rdx
0x14001e3dd  mov     [rbp+Status], r14d
0x14001e3e1  lea     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e3e5  mov     [rbp+ConfigurationHandle], r14
0x14001e3e9  lea     rcx, [rbp+ConfigObject]; ConfigObject
0x14001e3ed  mov     qword ptr [rbp+ConfigObject.Flags], r14
0x14001e3f1  mov     [rbp+ParameterValue], r14
0x14001e3f5  mov     rsi, r9
0x14001e3f8  mov     rbx, r8
0x14001e3fb  mov     qword ptr [rbp+ConfigObject.Header.Type], 1801A9h
0x14001e403  call    cs:__imp_NdisOpenConfigurationEx
0x14001e40a  nop     dword ptr [rax+rax+00h]
0x14001e40f  mov     [rbp+Status], eax
0x14001e412  test    eax, eax
0x14001e414  jnz     loc_14001EB65
0x14001e41a  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e41e  lea     rax, aVpnmediatype; "VpnMediaType"
0x14001e425  mov     [rsp+70h+arg_8], r12
0x14001e42d  lea     r9, [rbp+Keyword]; Keyword
0x14001e431  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001e435  mov     [rbp+Keyword.Buffer], rax
0x14001e439  lea     rcx, [rbp+Status]; Status
0x14001e43d  mov     [rsp+70h+arg_10], r13
0x14001e445  mov     word ptr [rdi], 1
0x14001e44a  mov     qword ptr [rbp+Keyword.Length], 1A0018h
0x14001e452  mov     [rsp+70h+ParameterType], r14d; ParameterType
0x14001e457  call    cs:__imp_NdisReadConfiguration
0x14001e45e  nop     dword ptr [rax+rax+00h]
0x14001e463  cmp     [rbp+Status], r14d
0x14001e467  jnz     short loc_14001E47E
0x14001e469  mov     rax, [rbp+ParameterValue]
0x14001e46d  mov     eax, [rax+8]
0x14001e470  mov     [rbx], eax
0x14001e472  dec     eax
0x14001e474  cmp     eax, 1
0x14001e477  jbe     short loc_14001E488
0x14001e479  jmp     loc_14001E6FC
0x14001e47e  mov     dword ptr [rbx], 2
0x14001e484  mov     [rbp+Status], r14d
0x14001e488  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e48c  lea     rax, aMaxsendtimeout; "MaxSendTimeoutMs"
0x14001e493  lea     r9, [rbp+Keyword]; Keyword
0x14001e497  mov     [rbp+Keyword.Buffer], rax
0x14001e49b  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001e49f  mov     qword ptr [rbp+Keyword.Length], 220020h
0x14001e4a7  lea     rcx, [rbp+Status]; Status
0x14001e4ab  mov     [rsp+70h+ParameterType], r14d; ParameterType
0x14001e4b0  call    cs:__imp_NdisReadConfiguration
0x14001e4b7  nop     dword ptr [rax+rax+00h]
0x14001e4bc  mov     edi, 7FFFFFFFh
0x14001e4c1  mov     rbx, [rbp+arg_20]
0x14001e4c5  cmp     [rbp+Status], r14d
0x14001e4c9  jnz     short loc_14001E4DC
0x14001e4cb  mov     rax, [rbp+ParameterValue]
0x14001e4cf  mov     ecx, [rax+8]
0x14001e4d2  mov     [rbx], ecx
0x14001e4d4  test    ecx, ecx
0x14001e4d6  jnz     short loc_14001E4E6
0x14001e4d8  mov     [rbx], edi
0x14001e4da  jmp     short loc_14001E4E6
0x14001e4dc  mov     dword ptr [rbx], 2710h
0x14001e4e2  mov     [rbp+Status], r14d
0x14001e4e6  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e4ea  lea     rax, aInitialsendtim; "InitialSendTimeoutMs"
0x14001e4f1  lea     r9, [rbp+Keyword]; Keyword
0x14001e4f5  mov     [rbp+Keyword.Buffer], rax
0x14001e4f9  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001e4fd  mov     qword ptr [rbp+Keyword.Length], 2A0028h
0x14001e505  lea     rcx, [rbp+Status]; Status
0x14001e509  mov     [rsp+70h+ParameterType], r14d; ParameterType
0x14001e50e  call    cs:__imp_NdisReadConfiguration
0x14001e515  nop     dword ptr [rax+rax+00h]
0x14001e51a  cmp     [rbp+Status], r14d
0x14001e51e  jnz     short loc_14001E541
0x14001e520  mov     rax, [rbp+ParameterValue]
0x14001e524  mov     ecx, [rax+8]
0x14001e527  mov     rax, [rbp+arg_28]
0x14001e52b  mov     [rax], ecx
0x14001e52d  test    ecx, ecx
0x14001e52f  jnz     short loc_14001E535
0x14001e531  mov     [rax], edi
0x14001e533  jmp     short loc_14001E537
0x14001e535  mov     edi, ecx
0x14001e537  mov     ecx, [rbx]
0x14001e539  cmp     edi, ecx
0x14001e53b  jbe     short loc_14001E54F
0x14001e53d  mov     [rax], ecx
0x14001e53f  jmp     short loc_14001E54F
0x14001e541  mov     rax, [rbp+arg_28]
0x14001e545  mov     [rbp+Status], r14d
0x14001e549  mov     dword ptr [rax], 3E8h
0x14001e54f  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e553  lea     rax, aMaxretransmits; "MaxRetransmits"
0x14001e55a  lea     r9, [rbp+Keyword]; Keyword
0x14001e55e  mov     [rbp+Keyword.Buffer], rax
0x14001e562  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001e566  mov     qword ptr [rbp+Keyword.Length], 1E001Ch
0x14001e56e  lea     rcx, [rbp+Status]; Status
0x14001e572  mov     [rsp+70h+ParameterType], r14d; ParameterType
0x14001e577  mov     ebx, 1Eh
0x14001e57c  call    cs:__imp_NdisReadConfiguration
0x14001e583  nop     dword ptr [rax+rax+00h]
0x14001e588  cmp     [rbp+Status], r14d
0x14001e58c  jnz     short loc_14001E597
0x14001e58e  mov     rax, [rbp+ParameterValue]
0x14001e592  mov     ecx, [rax+8]
0x14001e595  jmp     short loc_14001E5A0
0x14001e597  mov     [rbp+Status], r14d
0x14001e59b  mov     ecx, 5
0x14001e5a0  mov     rax, [rbp+arg_30]
0x14001e5a4  lea     r9, [rbp+Keyword]; Keyword
0x14001e5a8  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001e5ac  mov     [rsp+70h+ParameterType], r14d; ParameterType
0x14001e5b1  mov     r13d, 10h
0x14001e5b7  mov     [rax], ecx
0x14001e5b9  lea     rax, aHelloms; "HelloMs"
0x14001e5c0  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e5c4  lea     rcx, [rbp+Status]; Status
0x14001e5c8  mov     [rbp+Keyword.Buffer], rax
0x14001e5cc  mov     qword ptr [rbp+Keyword.Length], 10000Eh
0x14001e5d4  call    cs:__imp_NdisReadConfiguration
0x14001e5db  nop     dword ptr [rax+rax+00h]
0x14001e5e0  cmp     [rbp+Status], r14d
0x14001e5e4  jnz     short loc_14001E5EF
0x14001e5e6  mov     rax, [rbp+ParameterValue]
0x14001e5ea  mov     ecx, [rax+8]
0x14001e5ed  jmp     short loc_14001E5F8
0x14001e5ef  mov     [rbp+Status], r14d
0x14001e5f3  mov     ecx, 9C40h
0x14001e5f8  mov     rax, [rbp+arg_38]
0x14001e5fc  lea     r9, [rbp+Keyword]; Keyword
0x14001e600  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001e604  mov     [rsp+70h+ParameterType], r14d; ParameterType
0x14001e609  mov     [rax], ecx
0x14001e60b  lea     rax, aMaxackdelayms; "MaxAckDelayMs"
0x14001e612  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e616  lea     rcx, [rbp+Status]; Status
0x14001e61a  mov     [rbp+Keyword.Buffer], rax
0x14001e61e  mov     qword ptr [rbp+Keyword.Length], 1C001Ah
0x14001e626  call    cs:__imp_NdisReadConfiguration
0x14001e62d  nop     dword ptr [rax+rax+00h]
0x14001e632  cmp     [rbp+Status], r14d
0x14001e636  jnz     short loc_14001E641
0x14001e638  mov     rax, [rbp+ParameterValue]
0x14001e63c  mov     ecx, [rax+8]
0x14001e63f  jmp     short loc_14001E64A
0x14001e641  mov     [rbp+Status], r14d
0x14001e645  mov     ecx, 1F4h
0x14001e64a  mov     rax, [rbp+arg_40]
0x14001e64e  lea     r9, [rbp+Keyword]; Keyword
0x14001e652  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001e656  mov     [rsp+70h+ParameterType], r14d; ParameterType
0x14001e65b  mov     [rax], ecx
0x14001e65d  lea     rax, aMaxoutoforder; "MaxOutOfOrder"
0x14001e664  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e668  lea     rcx, [rbp+Status]; Status
0x14001e66c  mov     [rbp+Keyword.Buffer], rax
0x14001e670  mov     qword ptr [rbp+Keyword.Length], 1C001Ah
0x14001e678  call    cs:__imp_NdisReadConfiguration
0x14001e67f  nop     dword ptr [rax+rax+00h]
0x14001e684  cmp     [rbp+Status], r14d
0x14001e688  jnz     short loc_14001E6A5
0x14001e68a  mov     rax, [rbp+ParameterValue]
0x14001e68e  movzx   ecx, word ptr [rax+8]
0x14001e692  mov     rax, [rbp+arg_48]
0x14001e696  mov     [rax], cx
0x14001e699  mov     eax, 4000h
0x14001e69e  cmp     cx, ax
0x14001e6a1  jbe     short loc_14001E6B2
0x14001e6a3  jmp     short loc_14001E6FC
0x14001e6a5  mov     rax, [rbp+arg_48]
0x14001e6a9  mov     [rbp+Status], r14d
0x14001e6ad  mov     word ptr [rax], 64h ; 'd'
0x14001e6b2  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e6b6  lea     rax, aOutgoingrole; "OutgoingRole"
0x14001e6bd  lea     r9, [rbp+Keyword]; Keyword
0x14001e6c1  mov     [rbp+Keyword.Buffer], rax
0x14001e6c5  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001e6c9  mov     qword ptr [rbp+Keyword.Length], 1A0018h
0x14001e6d1  lea     rcx, [rbp+Status]; Status
0x14001e6d5  mov     [rsp+70h+ParameterType], r14d; ParameterType
0x14001e6da  call    cs:__imp_NdisReadConfiguration
0x14001e6e1  nop     dword ptr [rax+rax+00h]
0x14001e6e6  cmp     [rbp+Status], r14d
0x14001e6ea  jnz     short loc_14001E708
0x14001e6ec  mov     rax, [rbp+ParameterValue]
0x14001e6f0  mov     eax, [rax+8]
0x14001e6f3  mov     [rsi], eax
0x14001e6f5  dec     eax
0x14001e6f7  cmp     eax, 1
0x14001e6fa  jbe     short loc_14001E712
0x14001e6fc  mov     [rbp+Status], 0C0010015h
0x14001e703  jmp     loc_14001EB42
0x14001e708  mov     dword ptr [rsi], 2
0x14001e70e  mov     [rbp+Status], r14d
0x14001e712  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e716  lea     rax, aControlreceive; "ControlReceiveWindow"
0x14001e71d  lea     r9, [rbp+Keyword]; Keyword
0x14001e721  mov     [rbp+Keyword.Buffer], rax
0x14001e725  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001e729  mov     qword ptr [rbp+Keyword.Length], 2A0028h
0x14001e731  lea     rcx, [rbp+Status]; Status
0x14001e735  mov     [rsp+70h+ParameterType], r14d; ParameterType
0x14001e73a  call    cs:__imp_NdisReadConfiguration
0x14001e741  nop     dword ptr [rax+rax+00h]
0x14001e746  cmp     [rbp+Status], r14d
0x14001e74a  jnz     short loc_14001E756
0x14001e74c  mov     rax, [rbp+ParameterValue]
0x14001e750  movzx   ecx, word ptr [rax+8]
0x14001e754  jmp     short loc_14001E75F
0x14001e756  mov     [rbp+Status], r14d
0x14001e75a  mov     ecx, 8
0x14001e75f  mov     rax, [rbp+arg_50]
0x14001e766  lea     r9, [rbp+Keyword]; Keyword
0x14001e76a  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001e76e  mov     [rsp+70h+ParameterType], r14d; ParameterType
0x14001e773  mov     [rax], cx
0x14001e776  lea     rax, aPayloadreceive; "PayloadReceiveWindow"
0x14001e77d  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e781  lea     rcx, [rbp+Status]; Status
0x14001e785  mov     [rbp+Keyword.Buffer], rax
0x14001e789  mov     qword ptr [rbp+Keyword.Length], 2A0028h
0x14001e791  call    cs:__imp_NdisReadConfiguration
0x14001e798  nop     dword ptr [rax+rax+00h]
0x14001e79d  cmp     [rbp+Status], r14d
0x14001e7a1  jnz     short loc_14001E7AD
0x14001e7a3  mov     rax, [rbp+ParameterValue]
0x14001e7a7  movzx   ecx, word ptr [rax+8]
0x14001e7ab  jmp     short loc_14001E7B4
0x14001e7ad  mov     [rbp+Status], r14d
0x14001e7b1  mov     ecx, r14d
0x14001e7b4  mov     rax, [rbp+arg_58]
0x14001e7bb  lea     r9, [rbp+Keyword]; Keyword
0x14001e7bf  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001e7c3  mov     [rsp+70h+ParameterType], r14d; ParameterType
0x14001e7c8  mov     [rax], cx
0x14001e7cb  lea     rax, aPayloadsendwin; "PayloadSendWindow"
0x14001e7d2  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e7d6  lea     rcx, [rbp+Status]; Status
0x14001e7da  mov     [rbp+Keyword.Buffer], rax
0x14001e7de  mov     qword ptr [rbp+Keyword.Length], 240022h
0x14001e7e6  call    cs:__imp_NdisReadConfiguration
0x14001e7ed  nop     dword ptr [rax+rax+00h]
0x14001e7f2  cmp     [rbp+Status], r14d
0x14001e7f6  jnz     short loc_14001E801
0x14001e7f8  mov     rax, [rbp+ParameterValue]
0x14001e7fc  mov     ecx, [rax+8]
0x14001e7ff  jmp     short loc_14001E808
0x14001e801  mov     [rbp+Status], r14d
0x14001e805  mov     ecx, r13d
0x14001e808  mov     rax, [rbp+arg_60]
0x14001e80f  lea     r9, [rbp+Keyword]; Keyword
0x14001e813  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001e817  mov     [rsp+70h+ParameterType], r14d; ParameterType
0x14001e81c  mov     [rax], ecx
0x14001e81e  lea     rax, aLookasidedepth; "LookasideDepth"
0x14001e825  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e829  lea     rcx, [rbp+Status]; Status
0x14001e82d  mov     [rbp+Keyword.Buffer], rax
0x14001e831  mov     qword ptr [rbp+Keyword.Length], 1E001Ch
0x14001e839  call    cs:__imp_NdisReadConfiguration
0x14001e840  nop     dword ptr [rax+rax+00h]
0x14001e845  cmp     [rbp+Status], r14d
0x14001e849  jnz     short loc_14001E855
0x14001e84b  mov     rax, [rbp+ParameterValue]
0x14001e84f  movzx   ebx, word ptr [rax+8]
0x14001e853  jmp     short loc_14001E859
0x14001e855  mov     [rbp+Status], r14d
0x14001e859  mov     rax, [rbp+arg_68]
0x14001e860  lea     r9, [rbp+Keyword]; Keyword
0x14001e864  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001e868  mov     [rsp+70h+ParameterType], 2; ParameterType
0x14001e870  lea     rcx, [rbp+Status]; Status
0x14001e874  mov     [rax], bx
0x14001e877  lea     rax, aHostname_0; "HostName"
0x14001e87e  mov     r8, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14001e882  mov     [rbp+Keyword.Buffer], rax
0x14001e886  mov     qword ptr [rbp+Keyword.Length], 120010h
0x14001e88e  call    cs:__imp_NdisReadConfiguration
0x14001e895  nop     dword ptr [rax+rax+00h]
0x14001e89a  cmp     [rbp+Status], r14d
0x14001e89e  jnz     short loc_14001E8CB
0x14001e8a0  mov     rcx, [rbp+ParameterValue]
0x14001e8a4  movzx   edx, word ptr [rcx+8]
0x14001e8a8  mov     rcx, [rcx+10h]
0x14001e8ac  call    StrDupUnicodeToAscii
0x14001e8b1  mov     rcx, [rbp+arg_70]
0x14001e8b8  mov     [rcx], rax
0x14001e8bb  test    rax, rax
0x14001e8be  jz      short loc_14001E911
  ... truncated ...
```
