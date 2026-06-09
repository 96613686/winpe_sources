# MRxSmbReadMiscellaneousRegistryParameters

- ea: `0x140032114`
- end: `0x14003279b`
- name: `MRxSmbReadMiscellaneousRegistryParameters`
- size: `1671`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003108c`
- `0x140032e60`

## callees

- `0x140016560`
- `0x140031834`
- `0x140031adc`
- `0x140032114`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400321ae`
- `ntoskrnl!ZwOpenKey` at `0x1400322ce`
- `ntoskrnl!ZwOpenKey` at `0x1400325e1`
- `ntoskrnl!ZwOpenKey` at `0x1400326fe`
- `ntoskrnl!ZwOpenKey` at `0x1400321ae`
- `ntoskrnl!ZwOpenKey` at `0x1400322ce`
- `ntoskrnl!ZwOpenKey` at `0x1400325e1`
- `ntoskrnl!ZwOpenKey` at `0x1400326fe`
- `ntoskrnl!ZwClose` at `0x140032270`
- `ntoskrnl!ZwClose` at `0x140032588`
- `ntoskrnl!ZwClose` at `0x1400326a3`
- `ntoskrnl!ZwClose` at `0x140032771`
- `ntoskrnl!ZwClose` at `0x140032270`
- `ntoskrnl!ZwClose` at `0x140032588`
- `ntoskrnl!ZwClose` at `0x1400326a3`
- `ntoskrnl!ZwClose` at `0x140032771`
- `ntoskrnl!ZwQueryValueKey` at `0x140032637`
- `ntoskrnl!ZwQueryValueKey` at `0x140032750`
- `ntoskrnl!ZwQueryValueKey` at `0x140032637`
- `ntoskrnl!ZwQueryValueKey` at `0x140032750`
- `ntoskrnl!ZwSetValueKey` at `0x140032692`
- `ntoskrnl!ZwSetValueKey` at `0x140032692`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003216b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003228c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003259f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032605`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003265f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400326bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003271e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003216b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003228c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003259f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032605`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003265f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400326bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003271e`

## string_xrefs

- `0x140032137`: `\Registry\Machine\System\CurrentControlSet\Services\MRxSmb\Parameters`
- `0x1400321cc`: `DeferredOpensEnabled`
- `0x140032251`: `InfoCacheLevel`
- `0x140032281`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Parameters`
- `0x1400322ec`: `RequireSecuritySignature`
- `0x140032319`: `EnableSecuritySignature`
- `0x140032444`: `MaxNumOfExchangesForPipelineReadWrite`
- `0x14003248c`: `EnableCachingOnWriteOnlyOpens`
- `0x1400324b0`: `DisableByteRangeLockingOnReadOnlyFiles`
- `0x140032501`: `NoDeleteOnClose`
- `0x140032536`: `RequireExtendedSecurity`
- `0x140032563`: `SMB1NATCompatibilityLevel`
- `0x140032594`: `\Registry\Machine\System\CurrentControlSet\Services\EventLog\System\mrxsmb`
- `0x140032650`: `%SystemRoot%\System32\kernel32.dll`
- `0x1400326af`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`

## pseudocode

```c
int MRxSmbReadMiscellaneousRegistryParameters()
{
  int result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v5; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v6; // [rsp+90h] [rbp-70h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v8; // [rsp+A4h] [rbp-5Ch]
  __int128 v9; // [rsp+ACh] [rbp-54h]

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  v5 = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\MRxSmb\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      MRxSmbDeferredOpensEnabled = ResultLength;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      MRxSmbOplocksDisabled = ResultLength;
    MRxSmbGetUlongRegistryParameter(KeyHandle);
    MRxSmbGetUlongRegistryParameter(KeyHandle);
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      MRxSmbInfoCacheLevel = ResultLength;
    ZwClose(KeyHandle);
  }
  IsTerminalServicesServer();
  RtlInitUnicodeString(&v5, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v5;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    MRxSmbSecuritySignaturesRequired = 0;
    MRxSmbGetUlongRegistryParameter(KeyHandle);
    MRxSmbSecuritySignaturesEnabled = (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0;
    MRxSmbExtendedSignaturesRequired = 0;
    MRxSmbGetUlongRegistryParameter(KeyHandle);
    MRxSmbExtendedSignaturesEnabled = MRxSmbSecuritySignaturesEnabled;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      MRxSmbExtendedSignaturesEnabled = ResultLength != 0;
    if ( MRxSmbExtendedSignaturesRequired )
    {
      MRxSmbSecuritySignaturesRequired = 1;
      MRxSmbExtendedSignaturesEnabled = 1;
    }
    if ( MRxSmbExtendedSignaturesEnabled )
      MRxSmbSecuritySignaturesEnabled = 1;
    if ( MRxSmbSecuritySignaturesRequired )
      MRxSmbSecuritySignaturesEnabled = 1;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      EnablePlainTextPassword = ResultLength;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      OffLineFileTimeoutInterval = ResultLength;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      ExtendedSessTimeoutInterval = ResultLength;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      MaxNumOfExchangesForPipelineReadWrite = ResultLength;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      Win9xSessionRestriction = ResultLength;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      MRxSmbEnableCachingOnWriteOnlyOpens = ResultLength;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      DisableByteRangeLockingOnReadOnlyFiles = ResultLength;
    MRxSmbEnableDownLevelLogOff = 0;
    MRxSmbGetUlongRegistryParameter(KeyHandle);
    MRxSmbNoDeleteOnClose = 0;
    MRxSmbGetUlongRegistryParameter(KeyHandle);
    MRxSmbRequireExtendedSecurity = 0;
    MRxSmbGetUlongRegistryParameter(KeyHandle);
    MRxSmbNATCompatibilityLevel = 0;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      MRxSmbNATCompatibilityLevel = ResultLength;
    ZwClose(KeyHandle);
  }
  RtlInitUnicodeString(&v5, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\EventLog\\System\\mrxsmb");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v5;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    ResultLength = 0;
    RtlInitUnicodeString(&DestinationString, L"ParameterMessageFile");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x40u,
           &ResultLength)
      || v8 != 2 )
    {
      v6 = 0;
      RtlInitUnicodeString(&v6, L"%SystemRoot%\\System32\\kernel32.dll");
      ZwSetValueKey(KeyHandle, &DestinationString, 0, 2u, v6.Buffer, v6.Length + 2);
    }
    ZwClose(KeyHandle);
  }
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    ResultLength = 0;
    RtlInitUnicodeString(&DestinationString, L"Guid");
    ZwQueryValueKey(
      KeyHandle,
      &DestinationString,
      KeyValuePartialInformation,
      KeyValueInformation,
      0x80u,
      &ResultLength);
    *(_OWORD *)(RdrConfigurationBlock + 68) = v9;
    return ZwClose(KeyHandle);
  }
  return result;
}

```

## disassembly

```asm
0x140032114  mov     [rsp-8+arg_0], rbx
0x140032119  push    rbp
0x14003211a  lea     rbp, [rsp-30h]
0x14003211f  sub     rsp, 130h
0x140032126  mov     rax, cs:__security_cookie
0x14003212d  xor     rax, rsp
0x140032130  mov     [rbp+30h+var_10], rax
0x140032134  xorps   xmm0, xmm0
0x140032137  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x14003213e  xorps   xmm1, xmm1
0x140032141  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x140032146  xor     ebx, ebx
0x140032148  xor     eax, eax
0x14003214a  movups  xmmword ptr [rsp+130h+ObjectAttributes.ObjectName], xmm0
0x14003214f  mov     [rsp+130h+KeyHandle], rbx
0x140032154  movups  xmmword ptr [rsp+130h+ObjectAttributes+1Ch], xmm0
0x140032159  mov     [rsp+130h+var_100], ebx
0x14003215d  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm0
0x140032162  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x140032167  movups  xmmword ptr [rbp+30h+var_B0.Length], xmm1
0x14003216b  call    cs:__imp_RtlInitUnicodeString
0x140032172  nop     dword ptr [rax+rax+00h]
0x140032177  lea     rax, [rsp+130h+DestinationString]
0x14003217c  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x140032184  xorps   xmm0, xmm0
0x140032187  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x14003218c  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x140032191  mov     [rsp+130h+ObjectAttributes.RootDirectory], rbx
0x140032196  mov     edx, 20019h; DesiredAccess
0x14003219b  mov     [rsp+130h+ObjectAttributes.Attributes], 240h
0x1400321a3  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1400321a8  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400321ae  call    cs:__imp_ZwOpenKey
0x1400321b5  nop     dword ptr [rax+rax+00h]
0x1400321ba  test    eax, eax
0x1400321bc  js      loc_14003227C
0x1400321c2  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1400321c7  lea     r8, [rsp+130h+var_100]
0x1400321cc  lea     rdx, aDeferredopense; "DeferredOpensEnabled"
0x1400321d3  call    MRxSmbGetUlongRegistryParameter
0x1400321d8  test    eax, eax
0x1400321da  js      short loc_1400321E6
0x1400321dc  mov     al, byte ptr [rsp+130h+var_100]
0x1400321e0  mov     cs:MRxSmbDeferredOpensEnabled, al
0x1400321e6  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1400321eb  lea     r8, [rsp+130h+var_100]
0x1400321f0  lea     rdx, aOplocksdisable; "OplocksDisabled"
0x1400321f7  call    MRxSmbGetUlongRegistryParameter
0x1400321fc  test    eax, eax
0x1400321fe  js      short loc_14003220A
0x140032200  mov     al, byte ptr [rsp+130h+var_100]
0x140032204  mov     cs:MRxSmbOplocksDisabled, al
0x14003220a  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14003220f  lea     r8, [rsp+130h+var_100]
0x140032214  lea     rdx, aDisableshadowl; "DisableShadowLoopback"
0x14003221b  call    MRxSmbGetUlongRegistryParameter
0x140032220  test    eax, eax
0x140032222  js      short loc_140032231
0x140032224  cmp     [rsp+130h+var_100], ebx
0x140032228  jz      short loc_140032231
0x14003222a  mov     cs:MRxSmbDisableShadowLoopback, 1
0x140032231  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x140032236  lea     r8, [rsp+130h+var_100]
0x14003223b  lea     rdx, aIgnorebindingo; "IgnoreBindingOrder"
0x140032242  call    MRxSmbGetUlongRegistryParameter
0x140032247  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14003224c  lea     r8, [rsp+130h+var_100]
0x140032251  lea     rdx, aInfocachelevel; "InfoCacheLevel"
0x140032258  call    MRxSmbGetUlongRegistryParameter
0x14003225d  test    eax, eax
0x14003225f  js      short loc_14003226B
0x140032261  mov     eax, [rsp+130h+var_100]
0x140032265  mov     cs:MRxSmbInfoCacheLevel, eax
0x14003226b  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x140032270  call    cs:__imp_ZwClose
0x140032277  nop     dword ptr [rax+rax+00h]
0x14003227c  call    IsTerminalServicesServer
0x140032281  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140032288  lea     rcx, [rbp+30h+var_B0]; DestinationString
0x14003228c  call    cs:__imp_RtlInitUnicodeString
0x140032293  nop     dword ptr [rax+rax+00h]
0x140032298  lea     rax, [rbp+30h+var_B0]
0x14003229c  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x1400322a4  xorps   xmm0, xmm0
0x1400322a7  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x1400322ac  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x1400322b1  mov     [rsp+130h+ObjectAttributes.RootDirectory], rbx
0x1400322b6  mov     edx, 20019h; DesiredAccess
0x1400322bb  mov     [rsp+130h+ObjectAttributes.Attributes], 240h
0x1400322c3  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1400322c8  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400322ce  call    cs:__imp_ZwOpenKey
0x1400322d5  nop     dword ptr [rax+rax+00h]
0x1400322da  test    eax, eax
0x1400322dc  js      loc_140032594
0x1400322e2  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1400322e7  lea     r8, [rsp+130h+var_100]
0x1400322ec  lea     rdx, aRequiresecurit; "RequireSecuritySignature"
0x1400322f3  mov     cs:MRxSmbSecuritySignaturesRequired, bl
0x1400322f9  call    MRxSmbGetUlongRegistryParameter
0x1400322fe  test    eax, eax
0x140032300  js      short loc_14003230F
0x140032302  cmp     [rsp+130h+var_100], ebx
0x140032306  jz      short loc_14003230F
0x140032308  mov     cs:MRxSmbSecuritySignaturesRequired, 1
0x14003230f  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x140032314  lea     r8, [rsp+130h+var_100]
0x140032319  lea     rdx, aEnablesecurity; "EnableSecuritySignature"
0x140032320  mov     cs:MRxSmbSecuritySignaturesEnabled, 1
0x140032327  call    MRxSmbGetUlongRegistryParameter
0x14003232c  test    eax, eax
0x14003232e  js      short loc_14003233C
0x140032330  cmp     [rsp+130h+var_100], ebx
0x140032334  jnz     short loc_14003233C
0x140032336  mov     cs:MRxSmbSecuritySignaturesEnabled, bl
0x14003233c  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x140032341  lea     r8, [rsp+130h+var_100]
0x140032346  lea     rdx, aRequireextende_0; "RequireExtendedSignature"
0x14003234d  mov     cs:MRxSmbExtendedSignaturesRequired, bl
0x140032353  call    MRxSmbGetUlongRegistryParameter
0x140032358  test    eax, eax
0x14003235a  js      short loc_140032369
0x14003235c  cmp     [rsp+130h+var_100], ebx
0x140032360  jz      short loc_140032369
0x140032362  mov     cs:MRxSmbExtendedSignaturesRequired, 1
0x140032369  mov     al, cs:MRxSmbSecuritySignaturesEnabled
0x14003236f  lea     r8, [rsp+130h+var_100]
0x140032374  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x140032379  lea     rdx, aEnableextended; "EnableExtendedSignature"
0x140032380  mov     cs:MRxSmbExtendedSignaturesEnabled, al
0x140032386  call    MRxSmbGetUlongRegistryParameter
0x14003238b  test    eax, eax
0x14003238d  js      short loc_14003239A
0x14003238f  cmp     [rsp+130h+var_100], ebx
0x140032393  setnz   cs:MRxSmbExtendedSignaturesEnabled
0x14003239a  cmp     cs:MRxSmbExtendedSignaturesRequired, bl
0x1400323a0  jz      short loc_1400323B0
0x1400323a2  mov     cs:MRxSmbSecuritySignaturesRequired, 1
0x1400323a9  mov     cs:MRxSmbExtendedSignaturesEnabled, 1
0x1400323b0  cmp     cs:MRxSmbExtendedSignaturesEnabled, bl
0x1400323b6  jz      short loc_1400323BF
0x1400323b8  mov     cs:MRxSmbSecuritySignaturesEnabled, 1
0x1400323bf  cmp     cs:MRxSmbSecuritySignaturesRequired, bl
0x1400323c5  jz      short loc_1400323CE
0x1400323c7  mov     cs:MRxSmbSecuritySignaturesEnabled, 1
0x1400323ce  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1400323d3  lea     r8, [rsp+130h+var_100]
0x1400323d8  lea     rdx, aEnableplaintex; "EnablePlainTextPassword"
0x1400323df  call    MRxSmbGetUlongRegistryParameter
0x1400323e4  test    eax, eax
0x1400323e6  js      short loc_1400323F2
0x1400323e8  mov     al, byte ptr [rsp+130h+var_100]
0x1400323ec  mov     cs:EnablePlainTextPassword, al
0x1400323f2  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1400323f7  lea     r8, [rsp+130h+var_100]
0x1400323fc  lea     rdx, aOfflinefiletim; "OffLineFileTimeoutIntervalInSeconds"
0x140032403  call    MRxSmbGetUlongRegistryParameter
0x140032408  test    eax, eax
0x14003240a  js      short loc_140032416
0x14003240c  mov     eax, [rsp+130h+var_100]
0x140032410  mov     cs:OffLineFileTimeoutInterval, eax
0x140032416  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14003241b  lea     r8, [rsp+130h+var_100]
0x140032420  lea     rdx, aExtendedsessti; "ExtendedSessTimeout"
0x140032427  call    MRxSmbGetUlongRegistryParameter
0x14003242c  test    eax, eax
0x14003242e  js      short loc_14003243A
0x140032430  mov     eax, [rsp+130h+var_100]
0x140032434  mov     cs:ExtendedSessTimeoutInterval, eax
0x14003243a  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14003243f  lea     r8, [rsp+130h+var_100]
0x140032444  lea     rdx, aMaxnumofexchan; "MaxNumOfExchangesForPipelineReadWrite"
0x14003244b  call    MRxSmbGetUlongRegistryParameter
0x140032450  test    eax, eax
0x140032452  js      short loc_14003245E
0x140032454  mov     eax, [rsp+130h+var_100]
0x140032458  mov     cs:MaxNumOfExchangesForPipelineReadWrite, eax
0x14003245e  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x140032463  lea     r8, [rsp+130h+var_100]
0x140032468  lea     rdx, aWin9xsessionre; "Win9xSessionRestriction"
0x14003246f  call    MRxSmbGetUlongRegistryParameter
0x140032474  test    eax, eax
0x140032476  js      short loc_140032482
0x140032478  mov     al, byte ptr [rsp+130h+var_100]
0x14003247c  mov     cs:Win9xSessionRestriction, al
0x140032482  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x140032487  lea     r8, [rsp+130h+var_100]
0x14003248c  lea     rdx, aEnablecachingo; "EnableCachingOnWriteOnlyOpens"
0x140032493  call    MRxSmbGetUlongRegistryParameter
0x140032498  test    eax, eax
0x14003249a  js      short loc_1400324A6
0x14003249c  mov     al, byte ptr [rsp+130h+var_100]
0x1400324a0  mov     cs:MRxSmbEnableCachingOnWriteOnlyOpens, al
0x1400324a6  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1400324ab  lea     r8, [rsp+130h+var_100]
0x1400324b0  lea     rdx, aDisablebyteran; "DisableByteRangeLockingOnReadOnlyFiles"
0x1400324b7  call    MRxSmbGetUlongRegistryParameter
0x1400324bc  test    eax, eax
0x1400324be  js      short loc_1400324CA
0x1400324c0  mov     al, byte ptr [rsp+130h+var_100]
0x1400324c4  mov     cs:DisableByteRangeLockingOnReadOnlyFiles, al
0x1400324ca  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1400324cf  lea     r8, [rsp+130h+var_100]
0x1400324d4  lea     rdx, aEnabledownleve; "EnableDownLevelLogOff"
0x1400324db  mov     cs:MRxSmbEnableDownLevelLogOff, bl
0x1400324e1  call    MRxSmbGetUlongRegistryParameter
0x1400324e6  test    eax, eax
0x1400324e8  js      short loc_1400324F7
0x1400324ea  cmp     [rsp+130h+var_100], ebx
0x1400324ee  jz      short loc_1400324F7
0x1400324f0  mov     cs:MRxSmbEnableDownLevelLogOff, 1
0x1400324f7  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1400324fc  lea     r8, [rsp+130h+var_100]
0x140032501  lea     rdx, aNodeleteonclos; "NoDeleteOnClose"
0x140032508  mov     cs:MRxSmbNoDeleteOnClose, bl
0x14003250e  call    MRxSmbGetUlongRegistryParameter
0x140032513  test    eax, eax
0x140032515  js      short loc_14003252C
0x140032517  cmp     [rsp+130h+var_100], ebx
0x14003251b  jz      short loc_14003252C
0x14003251d  cmp     cs:MRxSmbOplocksDisabled, bl
0x140032523  jz      short loc_14003252C
0x140032525  mov     cs:MRxSmbNoDeleteOnClose, 1
0x14003252c  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x140032531  lea     r8, [rsp+130h+var_100]
0x140032536  lea     rdx, aRequireextende; "RequireExtendedSecurity"
0x14003253d  mov     cs:MRxSmbRequireExtendedSecurity, bl
0x140032543  call    MRxSmbGetUlongRegistryParameter
0x140032548  test    eax, eax
0x14003254a  js      short loc_140032559
0x14003254c  cmp     [rsp+130h+var_100], ebx
0x140032550  jz      short loc_140032559
0x140032552  mov     cs:MRxSmbRequireExtendedSecurity, 1
0x140032559  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14003255e  lea     r8, [rsp+130h+var_100]
0x140032563  lea     rdx, aSmb1natcompati; "SMB1NATCompatibilityLevel"
0x14003256a  mov     cs:MRxSmbNATCompatibilityLevel, ebx
0x140032570  call    MRxSmbGetUlongRegistryParameter
0x140032575  test    eax, eax
0x140032577  js      short loc_140032583
0x140032579  mov     eax, [rsp+130h+var_100]
0x14003257d  mov     cs:MRxSmbNATCompatibilityLevel, eax
0x140032583  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x140032588  call    cs:__imp_ZwClose
0x14003258f  nop     dword ptr [rax+rax+00h]
0x140032594  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14003259b  lea     rcx, [rbp+30h+var_B0]; DestinationString
0x14003259f  call    cs:__imp_RtlInitUnicodeString
0x1400325a6  nop     dword ptr [rax+rax+00h]
0x1400325ab  lea     rax, [rbp+30h+var_B0]
0x1400325af  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x1400325b7  xorps   xmm0, xmm0
0x1400325ba  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x1400325bf  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x1400325c4  mov     [rsp+130h+ObjectAttributes.RootDirectory], rbx
0x1400325c9  mov     edx, 20019h; DesiredAccess
0x1400325ce  mov     [rsp+130h+ObjectAttributes.Attributes], 240h
0x1400325d6  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1400325db  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400325e1  call    cs:__imp_ZwOpenKey
0x1400325e8  nop     dword ptr [rax+rax+00h]
0x1400325ed  test    eax, eax
0x1400325ef  js      loc_1400326AF
0x1400325f5  lea     rdx, aParametermessa; "ParameterMessageFile"
0x1400325fc  mov     [rsp+130h+var_100], ebx
0x140032600  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x140032605  call    cs:__imp_RtlInitUnicodeString
0x14003260c  nop     dword ptr [rax+rax+00h]
0x140032611  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x140032616  lea     rax, [rsp+130h+var_100]
0x14003261b  mov     [rsp+130h+ResultLength], rax; ResultLength
0x140032620  lea     r9, [rbp+30h+KeyValueInformation]; KeyValueInformation
0x140032624  mov     r8d, 2; KeyValueInformationClass
0x14003262a  mov     [rsp+130h+Length], 40h ; '@'; Length
0x140032632  lea     rdx, [rsp+130h+DestinationString]; ValueName
0x140032637  call    cs:__imp_ZwQueryValueKey
0x14003263e  nop     dword ptr [rax+rax+00h]
0x140032643  test    eax, eax
0x140032645  jnz     short loc_14003264D
0x140032647  cmp     [rbp+30h+var_8C], 2
0x14003264b  jz      short loc_14003269E
0x14003264d  xorps   xmm0, xmm0
0x140032650  lea     rdx, aSystemrootSyst; "%SystemRoot%\\System32\\kernel32.dll"
0x140032657  lea     rcx, [rbp+30h+var_A0]; DestinationString
0x14003265b  movups  xmmword ptr [rbp+30h+var_A0.Length], xmm0
0x14003265f  call    cs:__imp_RtlInitUnicodeString
0x140032666  nop     dword ptr [rax+rax+00h]
0x14003266b  movzx   eax, [rbp+30h+var_A0.Length]
0x14003266f  lea     rdx, [rsp+130h+DestinationString]; ValueName
0x140032674  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x140032679  add     eax, 2
0x14003267c  mov     dword ptr [rsp+130h+ResultLength], eax; DataSize
0x140032680  mov     r9d, 2; Type
0x140032686  mov     rax, [rbp+30h+var_A0.Buffer]
0x14003268a  xor     r8d, r8d; TitleIndex
0x14003268d  mov     qword ptr [rsp+130h+Length], rax; Data
0x140032692  call    cs:__imp_ZwSetValueKey
0x140032699  nop     dword ptr [rax+rax+00h]
0x14003269e  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x1400326a3  call    cs:__imp_ZwClose
  ... truncated ...
```
