# OsReadConfig

- ea: `0x14001a7d8`
- end: `0x14001ac0a`
- name: `OsReadConfig`
- size: `1074`
- prototype: `__int64 __fastcall(NDIS_HANDLE ConfigurationHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001a290`

## callees

- `0x14001a7d8`
- `0x14001ac10`

## import_xrefs

- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14001abcf`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14001abcf`
- `NDIS!NdisReadConfiguration` at `0x14001a88c`
- `NDIS!NdisReadConfiguration` at `0x14001a8d9`
- `NDIS!NdisReadConfiguration` at `0x14001a924`
- `NDIS!NdisReadConfiguration` at `0x14001a96f`
- `NDIS!NdisReadConfiguration` at `0x14001a9ba`
- `NDIS!NdisReadConfiguration` at `0x14001aa06`
- `NDIS!NdisReadConfiguration` at `0x14001aa52`
- `NDIS!NdisReadConfiguration` at `0x14001aa8b`
- `NDIS!NdisReadConfiguration` at `0x14001aad6`
- `NDIS!NdisReadConfiguration` at `0x14001abac`
- `NDIS!NdisReadConfiguration` at `0x14001a88c`
- `NDIS!NdisReadConfiguration` at `0x14001a8d9`
- `NDIS!NdisReadConfiguration` at `0x14001a924`
- `NDIS!NdisReadConfiguration` at `0x14001a96f`
- `NDIS!NdisReadConfiguration` at `0x14001a9ba`
- `NDIS!NdisReadConfiguration` at `0x14001aa06`
- `NDIS!NdisReadConfiguration` at `0x14001aa52`
- `NDIS!NdisReadConfiguration` at `0x14001aa8b`
- `NDIS!NdisReadConfiguration` at `0x14001aad6`
- `NDIS!NdisReadConfiguration` at `0x14001abac`

## string_xrefs

- `0x14001a9d9`: `AuthenticateIncomingCalls`

## pseudocode

```c
void __fastcall OsReadConfig(NDIS_HANDLE ConfigurationHandle)
{
  unsigned int v2; // eax
  PNDIS_CONFIGURATION_PARAMETER v3; // [rsp+30h] [rbp-49h] BYREF
  UNICODE_STRING Keyword; // [rsp+38h] [rbp-41h] BYREF
  __int64 v5; // [rsp+48h] [rbp-31h]
  const wchar_t *v6; // [rsp+50h] [rbp-29h]
  UNICODE_STRING v7; // [rsp+58h] [rbp-21h] BYREF
  __int64 v8; // [rsp+68h] [rbp-11h]
  const wchar_t *v9; // [rsp+70h] [rbp-9h]
  UNICODE_STRING v10; // [rsp+78h] [rbp-1h] BYREF
  UNICODE_STRING v11; // [rsp+88h] [rbp+Fh] BYREF
  int Status; // [rsp+E8h] [rbp+6Fh] BYREF
  int v13; // [rsp+F0h] [rbp+77h] BYREF
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+F8h] [rbp+7Fh] BYREF

  *(_QWORD *)&v11.Length = 1703960;
  v13 = 0;
  v11.Buffer = L"TapiLineName";
  v3 = 0;
  v7.Buffer = L"ClientIpAddresses";
  *(_QWORD *)&v7.Length = 2359330;
  v6 = L"ClientIpMasks";
  v5 = 1835034;
  v10.Buffer = L"TrustedIpAddresses";
  *(_QWORD *)&v10.Length = 2490404;
  v9 = L"TrustedIpMasks";
  v8 = 1966108;
  Keyword.Buffer = L"TcpPortNumber";
  ParameterValue = 0;
  Status = 0;
  *(_QWORD *)&Keyword.Length = 1835034;
  NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
  if ( !Status )
    PptpControlPort = ParameterValue->ParameterData.StringData.Length;
  ParameterValue = 0;
  Keyword.Buffer = L"BaseCallId";
  Status = 0;
  *(_QWORD *)&Keyword.Length = 1441812;
  NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
  if ( !Status )
    PptpBaseCallId = ParameterValue->ParameterData.IntegerData;
  ParameterValue = 0;
  Keyword.Buffer = L"MaxTransmit";
  Status = 0;
  *(_QWORD *)&Keyword.Length = 1572886;
  NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
  if ( !Status )
    PptpMaxTransmit = ParameterValue->ParameterData.IntegerData;
  ParameterValue = 0;
  Keyword.Buffer = L"InactivityIdleSeconds";
  Status = 0;
  *(_QWORD *)&Keyword.Length = 2883626;
  NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
  if ( !Status )
    PptpEchoTimeout = ParameterValue->ParameterData.IntegerData;
  ParameterValue = 0;
  Keyword.Buffer = L"AlwaysEcho";
  Status = 0;
  *(_QWORD *)&Keyword.Length = 1441812;
  NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
  if ( !Status )
    PptpEchoAlways = ParameterValue->ParameterData.IntegerData != 0;
  ParameterValue = 0;
  Keyword.Buffer = L"AuthenticateIncomingCalls";
  Status = 0;
  *(_QWORD *)&Keyword.Length = 3407922;
  NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
  if ( !Status )
    PptpAuthenticateIncomingCalls = ParameterValue->ParameterData.IntegerData != 0;
  ParameterValue = 0;
  Keyword.Buffer = L"PptpTraceMask";
  Status = 0;
  *(_QWORD *)&Keyword.Length = 1835034;
  NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
  ParameterValue = 0;
  Keyword.Buffer = L"ValidateAddress";
  Status = 0;
  *(_QWORD *)&Keyword.Length = 2097182;
  NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
  if ( !Status )
    PptpValidateAddress = ParameterValue->ParameterData.IntegerData;
  ParameterValue = 0;
  Keyword.Buffer = L"MaxTunnelsPerIpAddress";
  Status = 0;
  *(_QWORD *)&Keyword.Length = 3014700;
  NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, &Keyword, NdisParameterInteger);
  if ( !Status )
    PptpMaxTunnelsPerIpAddress = ParameterValue->ParameterData.IntegerData;
  PptpWanEndpoints = 1;
  if ( (unsigned int)PptpMaxTunnelsPerIpAddress > 1 )
    PptpMaxTunnelsPerIpAddress = -1;
  if ( (unsigned int)(PptpBaseCallId + 1) > 0x10000 )
    PptpBaseCallId = 0xFFFF;
  v2 = PptpMaxTransmit;
  PptpClientSide = 0;
  if ( !PptpMaxTransmit )
  {
    v2 = 1;
    PptpMaxTransmit = 1;
  }
  if ( v2 > 0x400 )
    PptpMaxTransmit = 1024;
  if ( PptpAuthenticateIncomingCalls )
    g_ulAcceptClientAddresses = ReadClientAddressAndMaskList(ConfigurationHandle, &v7);
  g_ulTrustedClientAddresses = ReadClientAddressAndMaskList(ConfigurationHandle, &v10);
  NdisReadConfiguration(&v13, &v3, ConfigurationHandle, &v11, NdisParameterString);
  if ( !v13 )
  {
    RtlUnicodeStringToAnsiString(&TapiLineName, (PCUNICODE_STRING)&v3->ParameterData, 0);
    TapiLineName.Buffer[TapiLineName.MaximumLength - 1] = 0;
  }
}

```

## disassembly

```asm
0x14001a7d8  mov     [rsp-8+arg_0], rbx
0x14001a7dd  push    rbp
0x14001a7de  push    rsi
0x14001a7df  push    rdi
0x14001a7e0  push    r12
0x14001a7e2  push    r13
0x14001a7e4  push    r14
0x14001a7e6  push    r15
0x14001a7e8  lea     rbp, [rsp-27h]
0x14001a7ed  sub     rsp, 0A0h
0x14001a7f4  xor     edi, edi
0x14001a7f6  mov     qword ptr [rbp+57h+var_48.Length], 1A0018h
0x14001a7fe  lea     rax, aTapilinename; "TapiLineName"
0x14001a805  mov     [rbp+57h+arg_10], edi
0x14001a808  mov     [rbp+57h+var_48.Buffer], rax
0x14001a80c  lea     r9, [rbp+57h+Keyword]; Keyword
0x14001a810  lea     rax, aClientipaddres; "ClientIpAddresses"
0x14001a817  mov     [rbp+57h+var_A0], rdi
0x14001a81b  mov     [rbp+57h+var_78.Buffer], rax
0x14001a81f  lea     rdx, [rbp+57h+ParameterValue]; ParameterValue
0x14001a823  lea     rax, aClientipmasks; "ClientIpMasks"
0x14001a82a  mov     qword ptr [rbp+57h+var_78.Length], 240022h
0x14001a832  mov     [rbp+57h+var_80], rax
0x14001a836  mov     rbx, rcx
0x14001a839  lea     rax, aTrustedipaddre; "TrustedIpAddresses"
0x14001a840  mov     [rbp+57h+var_88], 1C001Ah
0x14001a848  mov     [rbp+57h+var_58.Buffer], rax
0x14001a84c  mov     r8, rcx; ConfigurationHandle
0x14001a84f  lea     rax, aTrustedipmasks; "TrustedIpMasks"
0x14001a856  mov     qword ptr [rbp+57h+var_58.Length], 260024h
0x14001a85e  mov     [rbp+57h+var_60], rax
0x14001a862  lea     rcx, [rbp+57h+Status]; Status
0x14001a866  lea     rax, aTcpportnumber; "TcpPortNumber"
0x14001a86d  mov     [rbp+57h+var_68], 1E001Ch
0x14001a875  mov     [rbp+57h+Keyword.Buffer], rax
0x14001a879  mov     [rbp+57h+ParameterValue], rdi
0x14001a87d  mov     [rbp+57h+Status], edi
0x14001a880  mov     qword ptr [rbp+57h+Keyword.Length], 1C001Ah
0x14001a888  mov     [rsp+0D0h+ParameterType], edi; ParameterType
0x14001a88c  call    cs:__imp_NdisReadConfiguration
0x14001a893  nop     dword ptr [rax+rax+00h]
0x14001a898  cmp     [rbp+57h+Status], edi
0x14001a89b  jnz     short loc_14001A8AC
0x14001a89d  mov     rax, [rbp+57h+ParameterValue]
0x14001a8a1  movzx   ecx, word ptr [rax+8]
0x14001a8a5  mov     cs:PptpControlPort, cx
0x14001a8ac  lea     rax, aBasecallid; "BaseCallId"
0x14001a8b3  mov     [rbp+57h+ParameterValue], rdi
0x14001a8b7  lea     r9, [rbp+57h+Keyword]; Keyword
0x14001a8bb  mov     [rbp+57h+Keyword.Buffer], rax
0x14001a8bf  mov     r8, rbx; ConfigurationHandle
0x14001a8c2  mov     [rbp+57h+Status], edi
0x14001a8c5  lea     rdx, [rbp+57h+ParameterValue]; ParameterValue
0x14001a8c9  mov     qword ptr [rbp+57h+Keyword.Length], 160014h
0x14001a8d1  lea     rcx, [rbp+57h+Status]; Status
0x14001a8d5  mov     [rsp+0D0h+ParameterType], edi; ParameterType
0x14001a8d9  call    cs:__imp_NdisReadConfiguration
0x14001a8e0  nop     dword ptr [rax+rax+00h]
0x14001a8e5  cmp     [rbp+57h+Status], edi
0x14001a8e8  jnz     short loc_14001A8F7
0x14001a8ea  mov     rax, [rbp+57h+ParameterValue]
0x14001a8ee  mov     ecx, [rax+8]
0x14001a8f1  mov     cs:PptpBaseCallId, ecx
0x14001a8f7  lea     rax, aMaxtransmit; "MaxTransmit"
0x14001a8fe  mov     [rbp+57h+ParameterValue], rdi
0x14001a902  lea     r9, [rbp+57h+Keyword]; Keyword
0x14001a906  mov     [rbp+57h+Keyword.Buffer], rax
0x14001a90a  mov     r8, rbx; ConfigurationHandle
0x14001a90d  mov     [rbp+57h+Status], edi
0x14001a910  lea     rdx, [rbp+57h+ParameterValue]; ParameterValue
0x14001a914  mov     qword ptr [rbp+57h+Keyword.Length], 180016h
0x14001a91c  lea     rcx, [rbp+57h+Status]; Status
0x14001a920  mov     [rsp+0D0h+ParameterType], edi; ParameterType
0x14001a924  call    cs:__imp_NdisReadConfiguration
0x14001a92b  nop     dword ptr [rax+rax+00h]
0x14001a930  cmp     [rbp+57h+Status], edi
0x14001a933  jnz     short loc_14001A942
0x14001a935  mov     rax, [rbp+57h+ParameterValue]
0x14001a939  mov     ecx, [rax+8]
0x14001a93c  mov     cs:PptpMaxTransmit, ecx
0x14001a942  lea     rax, aInactivityidle; "InactivityIdleSeconds"
0x14001a949  mov     [rbp+57h+ParameterValue], rdi
0x14001a94d  lea     r9, [rbp+57h+Keyword]; Keyword
0x14001a951  mov     [rbp+57h+Keyword.Buffer], rax
0x14001a955  mov     r8, rbx; ConfigurationHandle
0x14001a958  mov     [rbp+57h+Status], edi
0x14001a95b  lea     rdx, [rbp+57h+ParameterValue]; ParameterValue
0x14001a95f  mov     qword ptr [rbp+57h+Keyword.Length], 2C002Ah
0x14001a967  lea     rcx, [rbp+57h+Status]; Status
0x14001a96b  mov     [rsp+0D0h+ParameterType], edi; ParameterType
0x14001a96f  call    cs:__imp_NdisReadConfiguration
0x14001a976  nop     dword ptr [rax+rax+00h]
0x14001a97b  cmp     [rbp+57h+Status], edi
0x14001a97e  jnz     short loc_14001A98D
0x14001a980  mov     rax, [rbp+57h+ParameterValue]
0x14001a984  mov     ecx, [rax+8]
0x14001a987  mov     cs:PptpEchoTimeout, ecx
0x14001a98d  lea     rax, aAlwaysecho; "AlwaysEcho"
0x14001a994  mov     [rbp+57h+ParameterValue], rdi
0x14001a998  lea     r9, [rbp+57h+Keyword]; Keyword
0x14001a99c  mov     [rbp+57h+Keyword.Buffer], rax
0x14001a9a0  mov     r8, rbx; ConfigurationHandle
0x14001a9a3  mov     [rbp+57h+Status], edi
0x14001a9a6  lea     rdx, [rbp+57h+ParameterValue]; ParameterValue
0x14001a9aa  mov     qword ptr [rbp+57h+Keyword.Length], 160014h
0x14001a9b2  lea     rcx, [rbp+57h+Status]; Status
0x14001a9b6  mov     [rsp+0D0h+ParameterType], edi; ParameterType
0x14001a9ba  call    cs:__imp_NdisReadConfiguration
0x14001a9c1  nop     dword ptr [rax+rax+00h]
0x14001a9c6  cmp     [rbp+57h+Status], edi
0x14001a9c9  jnz     short loc_14001A9D9
0x14001a9cb  mov     rax, [rbp+57h+ParameterValue]
0x14001a9cf  cmp     [rax+8], edi
0x14001a9d2  setnz   cs:PptpEchoAlways
0x14001a9d9  lea     rax, aAuthenticatein; "AuthenticateIncomingCalls"
0x14001a9e0  mov     [rbp+57h+ParameterValue], rdi
0x14001a9e4  lea     r9, [rbp+57h+Keyword]; Keyword
0x14001a9e8  mov     [rbp+57h+Keyword.Buffer], rax
0x14001a9ec  mov     r8, rbx; ConfigurationHandle
0x14001a9ef  mov     [rbp+57h+Status], edi
0x14001a9f2  lea     rdx, [rbp+57h+ParameterValue]; ParameterValue
0x14001a9f6  mov     qword ptr [rbp+57h+Keyword.Length], 340032h
0x14001a9fe  lea     rcx, [rbp+57h+Status]; Status
0x14001aa02  mov     [rsp+0D0h+ParameterType], edi; ParameterType
0x14001aa06  call    cs:__imp_NdisReadConfiguration
0x14001aa0d  nop     dword ptr [rax+rax+00h]
0x14001aa12  cmp     [rbp+57h+Status], edi
0x14001aa15  jnz     short loc_14001AA25
0x14001aa17  mov     rax, [rbp+57h+ParameterValue]
0x14001aa1b  cmp     [rax+8], edi
0x14001aa1e  setnz   cs:PptpAuthenticateIncomingCalls
0x14001aa25  lea     rax, aPptptracemask; "PptpTraceMask"
0x14001aa2c  mov     [rbp+57h+ParameterValue], rdi
0x14001aa30  lea     r9, [rbp+57h+Keyword]; Keyword
0x14001aa34  mov     [rbp+57h+Keyword.Buffer], rax
0x14001aa38  mov     r8, rbx; ConfigurationHandle
0x14001aa3b  mov     [rbp+57h+Status], edi
0x14001aa3e  lea     rdx, [rbp+57h+ParameterValue]; ParameterValue
0x14001aa42  mov     qword ptr [rbp+57h+Keyword.Length], 1C001Ah
0x14001aa4a  lea     rcx, [rbp+57h+Status]; Status
0x14001aa4e  mov     [rsp+0D0h+ParameterType], edi; ParameterType
0x14001aa52  call    cs:__imp_NdisReadConfiguration
0x14001aa59  nop     dword ptr [rax+rax+00h]
0x14001aa5e  lea     rax, aValidateaddres; "ValidateAddress"
0x14001aa65  mov     [rbp+57h+ParameterValue], rdi
0x14001aa69  lea     r9, [rbp+57h+Keyword]; Keyword
0x14001aa6d  mov     [rbp+57h+Keyword.Buffer], rax
0x14001aa71  mov     r8, rbx; ConfigurationHandle
0x14001aa74  mov     [rbp+57h+Status], edi
0x14001aa77  lea     rdx, [rbp+57h+ParameterValue]; ParameterValue
0x14001aa7b  mov     qword ptr [rbp+57h+Keyword.Length], 20001Eh
0x14001aa83  lea     rcx, [rbp+57h+Status]; Status
0x14001aa87  mov     [rsp+0D0h+ParameterType], edi; ParameterType
0x14001aa8b  call    cs:__imp_NdisReadConfiguration
0x14001aa92  nop     dword ptr [rax+rax+00h]
0x14001aa97  cmp     [rbp+57h+Status], edi
0x14001aa9a  jnz     short loc_14001AAA9
0x14001aa9c  mov     rax, [rbp+57h+ParameterValue]
0x14001aaa0  mov     ecx, [rax+8]
0x14001aaa3  mov     cs:PptpValidateAddress, ecx
0x14001aaa9  lea     rax, aMaxtunnelsperi; "MaxTunnelsPerIpAddress"
0x14001aab0  mov     [rbp+57h+ParameterValue], rdi
0x14001aab4  lea     r9, [rbp+57h+Keyword]; Keyword
0x14001aab8  mov     [rbp+57h+Keyword.Buffer], rax
0x14001aabc  mov     r8, rbx; ConfigurationHandle
0x14001aabf  mov     [rbp+57h+Status], edi
0x14001aac2  lea     rdx, [rbp+57h+ParameterValue]; ParameterValue
0x14001aac6  mov     qword ptr [rbp+57h+Keyword.Length], 2E002Ch
0x14001aace  lea     rcx, [rbp+57h+Status]; Status
0x14001aad2  mov     [rsp+0D0h+ParameterType], edi; ParameterType
0x14001aad6  call    cs:__imp_NdisReadConfiguration
0x14001aadd  nop     dword ptr [rax+rax+00h]
0x14001aae2  cmp     [rbp+57h+Status], edi
0x14001aae5  jnz     short loc_14001AAF4
0x14001aae7  mov     rax, [rbp+57h+ParameterValue]
0x14001aaeb  mov     ecx, [rax+8]
0x14001aaee  mov     cs:PptpMaxTunnelsPerIpAddress, ecx
0x14001aaf4  mov     ecx, 1
0x14001aaf9  cmp     cs:PptpMaxTunnelsPerIpAddress, ecx
0x14001aaff  mov     cs:PptpWanEndpoints, ecx
0x14001ab05  jbe     short loc_14001AB11
0x14001ab07  mov     cs:PptpMaxTunnelsPerIpAddress, 0FFFFFFFFh
0x14001ab11  mov     eax, cs:PptpBaseCallId
0x14001ab17  inc     eax
0x14001ab19  cmp     eax, 10000h
0x14001ab1e  jbe     short loc_14001AB2A
0x14001ab20  mov     cs:PptpBaseCallId, 0FFFFh
0x14001ab2a  mov     eax, cs:PptpMaxTransmit
0x14001ab30  mov     cs:PptpClientSide, dil
0x14001ab37  cmp     eax, ecx
0x14001ab39  jnb     short loc_14001AB43
0x14001ab3b  mov     eax, ecx
0x14001ab3d  mov     cs:PptpMaxTransmit, ecx
0x14001ab43  mov     ecx, 400h
0x14001ab48  cmp     eax, ecx
0x14001ab4a  jbe     short loc_14001AB52
0x14001ab4c  mov     cs:PptpMaxTransmit, ecx
0x14001ab52  cmp     cs:PptpAuthenticateIncomingCalls, dil
0x14001ab59  jz      short loc_14001AB78
0x14001ab5b  lea     r9, g_AcceptClientList
0x14001ab62  mov     rcx, rbx; ConfigurationHandle
0x14001ab65  lea     r8, [rbp+57h+var_88]
0x14001ab69  lea     rdx, [rbp+57h+var_78]; Keyword
0x14001ab6d  call    ReadClientAddressAndMaskList
0x14001ab72  mov     cs:g_ulAcceptClientAddresses, eax
0x14001ab78  lea     r9, g_TrustedClientList
0x14001ab7f  mov     rcx, rbx; ConfigurationHandle
0x14001ab82  lea     r8, [rbp+57h+var_68]
0x14001ab86  lea     rdx, [rbp+57h+var_58]; Keyword
0x14001ab8a  call    ReadClientAddressAndMaskList
0x14001ab8f  lea     r9, [rbp+57h+var_48]; Keyword
0x14001ab93  mov     cs:g_ulTrustedClientAddresses, eax
0x14001ab99  mov     r8, rbx; ConfigurationHandle
0x14001ab9c  mov     [rsp+0D0h+ParameterType], 2; ParameterType
0x14001aba4  lea     rdx, [rbp+57h+var_A0]; ParameterValue
0x14001aba8  lea     rcx, [rbp+57h+arg_10]; Status
0x14001abac  call    cs:__imp_NdisReadConfiguration
0x14001abb3  nop     dword ptr [rax+rax+00h]
0x14001abb8  cmp     [rbp+57h+arg_10], edi
0x14001abbb  jnz     short loc_14001ABEE
0x14001abbd  mov     rdx, [rbp+57h+var_A0]
0x14001abc1  lea     rcx, TapiLineName; DestinationString
0x14001abc8  add     rdx, 8; SourceString
0x14001abcc  xor     r8d, r8d; AllocateDestinationString
0x14001abcf  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14001abd6  nop     dword ptr [rax+rax+00h]
0x14001abdb  movzx   ecx, cs:TapiLineName.MaximumLength
0x14001abe2  mov     rax, cs:TapiLineName.Buffer
0x14001abe9  mov     [rcx+rax-1], dil
0x14001abee  mov     rbx, [rsp+0D0h+arg_0]
0x14001abf6  add     rsp, 0A0h
0x14001abfd  pop     r15
0x14001abff  pop     r14
0x14001ac01  pop     r13
0x14001ac03  pop     r12
0x14001ac05  pop     rdi
0x14001ac06  pop     rsi
0x14001ac07  pop     rbp
0x14001ac08  retn
```
