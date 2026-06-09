# VfClearVerifierSettings

- ea: `0x1406397e8`
- end: `0x140639bf5`
- name: `VfClearVerifierSettings`
- size: `1037`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140bc4800`
- `0x140c53f38`

## callees

- `0x140403380`
- `0x140530500`
- `0x1406397e8`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406ddfe0`
- `0x1406defc0`
- `0x1406df200`

## string_xrefs

- `0x140639997`: `Driver Verifier: Failed to delete VerifierRandomTargets key value with status: 0x%x\n`
- `0x1406399d6`: `Driver Verifier: Failed to delete XdvVerifierOptions key value with status: 0x%x\n`
- `0x14063992b`: `Driver Verifier: Failed to delete RuleClasses key value with status: 0x%x\n`
- `0x140639961`: `Driver Verifier: Failed to delete VerifyDrivers key value with status: 0x%x\n`
- `0x1406398f5`: `Driver Verifier: Failed to delete VerifyDriverLevel key value with status: 0x%x\n`
- `0x140639b59`: `Driver Verifier: Failed to delete VerifierLwspPoolTags key value with status: 0x%x\n`
- `0x140639b65`: `DifPluginConfigData`
- `0x140639b8f`: `Driver Verifier: Failed to delete DifPluginConfigData key value with status: 0x%x\n`
- `0x140639aed`: `Driver Verifier: Failed to delete VerifierTipLimitDenominator key value with status: 0x%x\n`
- `0x140639b23`: `Driver Verifier: Failed to delete VerifierTipSparseness key value with status: 0x%x\n`
- `0x140639a81`: `Driver Verifier: Failed to delete VerifyDriversSuppress key value with status: 0x%x\n`
- `0x140639ab7`: `Driver Verifier: Failed to delete VerifierTipLimitNumerator key value with status: 0x%x\n`
- `0x140639a0c`: `Driver Verifier: Failed to delete VrfPersistThroughUpgrade key value with status: 0x%x\n`
- `0x140639a42`: `Driver Verifier: Failed to delete VerifierTriageContext key value with status: 0x%x\n`
- `0x140639bad`: `Driver Verifier: Clearing Verifier options from Registry for preventing recursive crash.\n`
- `0x140639bbd`: `Driver Verifier: Failed to set VerifierOptionFlags key value with status: 0x%x\n Registry updates aborted!`
- `0x140639bd6`: `Driver Verifier: Failed to open Memory Management key with status: 0x%x\n Registry updates aborted!`

## pseudocode

```c
NTSTATUS VfClearVerifierSettings()
{
  unsigned int v0; // eax
  UNICODE_STRING *v1; // rax
  NTSTATUS v2; // eax
  NTSTATUS v3; // eax
  NTSTATUS v4; // eax
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  NTSTATUS v13; // eax
  NTSTATUS v14; // eax
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  unsigned int Data; // [rsp+80h] [rbp+10h] BYREF
  HANDLE KeyHandle; // [rsp+88h] [rbp+18h] BYREF

  KeyHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  DestinationString = 0;
  if ( (VfOptionFlags & 0x20) != 0 )
  {
    v0 = VfOptionFlags & 0xFFFFFFCF;
  }
  else if ( (VfOptionFlags & 0x400) != 0 )
  {
    v0 = VfOptionFlags & 0xFFFFFBC7;
  }
  else
  {
    v0 = VfOptionFlags & 0xFFFFFFE7;
  }
  Data = v0;
  v1 = (UNICODE_STRING *)&VfPersistentStateRoot;
  ObjectAttributes.Length = 48;
  if ( !CmStateSeparationEnabled )
    v1 = &CmRegistryMachineSystemCurrentControlSetControlSessionManagerMemoryManagement;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = v1;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  if ( v2 < 0 )
    return VfUtilDbgPrint(
             "Driver Verifier: Failed to open Memory Management key with status: 0x%x\n Registry updates aborted!",
             v2);
  RtlInitUnicodeString(&DestinationString, L"VerifierOptions");
  v3 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &Data, 4u);
  if ( v3 < 0 )
  {
    VfUtilDbgPrint(
      "Driver Verifier: Failed to set VerifierOptionFlags key value with status: 0x%x\n Registry updates aborted!",
      v3);
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, L"VerifyDriverLevel");
    v4 = ZwDeleteValueKey(KeyHandle, &DestinationString);
    if ( (int)(v4 + 0x80000000) >= 0 && v4 != -1073741772 )
      VfUtilDbgPrint("Driver Verifier: Failed to delete VerifyDriverLevel key value with status: 0x%x\n", v4);
    RtlInitUnicodeString(&DestinationString, L"VerifierSettingState");
    v5 = ZwDeleteValueKey(KeyHandle, &DestinationString);
    if ( ((v5 + 0x80000000) & 0x80000000) == 0 && v5 != -1073741772 )
      VfUtilDbgPrint("Driver Verifier: Failed to delete RuleClasses key value with status: 0x%x\n", v5);
    RtlInitUnicodeString(&DestinationString, L"VerifyDrivers");
    v6 = ZwDeleteValueKey(KeyHandle, &DestinationString);
    if ( ((v6 + 0x80000000) & 0x80000000) == 0 && v6 != -1073741772 )
      VfUtilDbgPrint("Driver Verifier: Failed to delete VerifyDrivers key value with status: 0x%x\n", v6);
    RtlInitUnicodeString(&DestinationString, L"VerifierRandomTargets");
    v7 = ZwDeleteValueKey(KeyHandle, &DestinationString);
    if ( ((v7 + 0x80000000) & 0x80000000) == 0 && v7 != -1073741772 )
      VfUtilDbgPrint("Driver Verifier: Failed to delete VerifierRandomTargets key value with status: 0x%x\n", v7);
    if ( VfFlightOptions )
    {
      RtlInitUnicodeString(&DestinationString, L"XdvVerifierOptions");
      v8 = ZwDeleteValueKey(KeyHandle, &DestinationString);
      if ( ((v8 + 0x80000000) & 0x80000000) == 0 && v8 != -1073741772 )
        VfUtilDbgPrint("Driver Verifier: Failed to delete XdvVerifierOptions key value with status: 0x%x\n", v8);
    }
    RtlInitUnicodeString(&DestinationString, L"VrfPersistThroughUpgrade");
    v9 = ZwDeleteValueKey(KeyHandle, &DestinationString);
    if ( ((v9 + 0x80000000) & 0x80000000) == 0 && v9 != -1073741772 )
      VfUtilDbgPrint("Driver Verifier: Failed to delete VrfPersistThroughUpgrade key value with status: 0x%x\n", v9);
    RtlInitUnicodeString(&DestinationString, L"VerifierTriageContext");
    v10 = ZwDeleteValueKey(KeyHandle, &DestinationString);
    if ( ((v10 + 0x80000000) & 0x80000000) == 0 && v10 != -1073741772 )
      VfUtilDbgPrint("Driver Verifier: Failed to delete VerifierTriageContext key value with status: 0x%x\n", v10);
    if ( VfXdvSuppressDriversBufferLength != -1 )
    {
      RtlInitUnicodeString(&DestinationString, L"VerifyDriversSuppress");
      v11 = ZwDeleteValueKey(KeyHandle, &DestinationString);
      if ( ((v11 + 0x80000000) & 0x80000000) == 0 && v11 != -1073741772 )
        VfUtilDbgPrint("Driver Verifier: Failed to delete VerifyDriversSuppress key value with status: 0x%x\n", v11);
    }
    RtlInitUnicodeString(&DestinationString, L"VerifierTipLimitNumerator");
    v12 = ZwDeleteValueKey(KeyHandle, &DestinationString);
    if ( ((v12 + 0x80000000) & 0x80000000) == 0 && v12 != -1073741772 )
      VfUtilDbgPrint("Driver Verifier: Failed to delete VerifierTipLimitNumerator key value with status: 0x%x\n", v12);
    RtlInitUnicodeString(&DestinationString, L"VerifierTipLimitDenominator");
    v13 = ZwDeleteValueKey(KeyHandle, &DestinationString);
    if ( ((v13 + 0x80000000) & 0x80000000) == 0 && v13 != -1073741772 )
      VfUtilDbgPrint("Driver Verifier: Failed to delete VerifierTipLimitDenominator key value with status: 0x%x\n", v13);
    RtlInitUnicodeString(&DestinationString, L"VerifierTipSparseness");
    v14 = ZwDeleteValueKey(KeyHandle, &DestinationString);
    if ( ((v14 + 0x80000000) & 0x80000000) == 0 && v14 != -1073741772 )
      VfUtilDbgPrint("Driver Verifier: Failed to delete VerifierTipSparseness key value with status: 0x%x\n", v14);
    RtlInitUnicodeString(&DestinationString, L"VerifierLwspPoolTags");
    v15 = ZwDeleteValueKey(KeyHandle, &DestinationString);
    if ( ((v15 + 0x80000000) & 0x80000000) == 0 && v15 != -1073741772 )
      VfUtilDbgPrint("Driver Verifier: Failed to delete VerifierLwspPoolTags key value with status: 0x%x\n", v15);
    RtlInitUnicodeString(&DestinationString, L"DifPluginConfigData");
    v16 = ZwDeleteValueKey(KeyHandle, &DestinationString);
    if ( ((v16 + 0x80000000) & 0x80000000) == 0 && v16 != -1073741772 )
      VfUtilDbgPrint("Driver Verifier: Failed to delete DifPluginConfigData key value with status: 0x%x\n", v16);
    ZwFlushKey(KeyHandle);
    if ( VfClearanceFlag )
      VfUtilDbgPrint("Driver Verifier: Clearing Verifier options from Registry for preventing recursive crash.\n");
  }
  return ZwClose(KeyHandle);
}

```

## disassembly

```asm
0x1406397e8  mov     [rsp-8+arg_10], rbx
0x1406397ed  mov     [rsp-8+arg_18], rdi
0x1406397f2  push    rbp
0x1406397f3  mov     rbp, rsp
0x1406397f6  sub     rsp, 70h
0x1406397fa  xor     eax, eax
0x1406397fc  mov     [rbp+KeyHandle], 0
0x140639804  mov     dword ptr [rbp+ObjectAttributes+4], eax
0x140639807  xorps   xmm0, xmm0
0x14063980a  mov     dword ptr [rbp+ObjectAttributes+1Ch], eax
0x14063980d  mov     eax, cs:VfOptionFlags
0x140639813  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140639817  test    al, 20h
0x140639819  jz      short loc_140639820
0x14063981b  and     eax, 0FFFFFFCFh
0x14063981e  jmp     short loc_140639830
0x140639820  bt      eax, 0Ah
0x140639824  jnb     short loc_14063982D
0x140639826  and     eax, 0FFFFFBC7h
0x14063982b  jmp     short loc_140639830
0x14063982d  and     eax, 0FFFFFFE7h
0x140639830  cmp     cs:CmStateSeparationEnabled, 0
0x140639837  lea     rcx, CmRegistryMachineSystemCurrentControlSetControlSessionManagerMemoryManagement
0x14063983e  mov     [rbp+arg_0], eax
0x140639841  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140639845  lea     rax, VfPersistentStateRoot
0x14063984c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140639853  cmovz   rax, rcx
0x140639857  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14063985f  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140639863  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140639867  mov     edx, 0F003Fh; DesiredAccess
0x14063986c  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140639873  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140639878  call    ZwOpenKey
0x14063987d  test    eax, eax
0x14063987f  js      loc_140639BD4
0x140639885  lea     rdx, aVerifieroption_0; "VerifierOptions"
0x14063988c  lea     rcx, [rbp+DestinationString]; DestinationString
0x140639890  call    RtlInitUnicodeString
0x140639895  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140639899  lea     rax, [rbp+arg_0]
0x14063989d  mov     r9d, 4; Type
0x1406398a3  lea     rdx, [rbp+DestinationString]; ValueName
0x1406398a7  mov     [rsp+70h+DataSize], r9d; DataSize
0x1406398ac  xor     r8d, r8d; TitleIndex
0x1406398af  mov     [rsp+70h+Data], rax; Data
0x1406398b4  call    ZwSetValueKey
0x1406398b9  test    eax, eax
0x1406398bb  js      loc_140639BBB
0x1406398c1  lea     rdx, aVerifydriverle_0; "VerifyDriverLevel"
0x1406398c8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1406398cc  call    RtlInitUnicodeString
0x1406398d1  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1406398d5  lea     rdx, [rbp+DestinationString]; ValueName
0x1406398d9  call    ZwDeleteValueKey
0x1406398de  mov     edi, 80000000h
0x1406398e3  mov     ebx, 0C0000034h
0x1406398e8  lea     ecx, [rax+rdi]
0x1406398eb  test    edi, ecx
0x1406398ed  jnz     short loc_140639901
0x1406398ef  cmp     eax, ebx
0x1406398f1  jz      short loc_140639901
0x1406398f3  mov     edx, eax
0x1406398f5  lea     rcx, aDriverVerifier_20; "Driver Verifier: Failed to delete Verif"...
0x1406398fc  call    VfUtilDbgPrint
0x140639901  lea     rdx, aVerifiersettin_0; "VerifierSettingState"
0x140639908  lea     rcx, [rbp+DestinationString]; DestinationString
0x14063990c  call    RtlInitUnicodeString
0x140639911  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140639915  lea     rdx, [rbp+DestinationString]; ValueName
0x140639919  call    ZwDeleteValueKey
0x14063991e  lea     ecx, [rax+rdi]
0x140639921  test    edi, ecx
0x140639923  jnz     short loc_140639937
0x140639925  cmp     eax, ebx
0x140639927  jz      short loc_140639937
0x140639929  mov     edx, eax
0x14063992b  lea     rcx, aDriverVerifier_13; "Driver Verifier: Failed to delete RuleC"...
0x140639932  call    VfUtilDbgPrint
0x140639937  lea     rdx, aVerifydrivers_0; "VerifyDrivers"
0x14063993e  lea     rcx, [rbp+DestinationString]; DestinationString
0x140639942  call    RtlInitUnicodeString
0x140639947  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14063994b  lea     rdx, [rbp+DestinationString]; ValueName
0x14063994f  call    ZwDeleteValueKey
0x140639954  lea     ecx, [rax+rdi]
0x140639957  test    edi, ecx
0x140639959  jnz     short loc_14063996D
0x14063995b  cmp     eax, ebx
0x14063995d  jz      short loc_14063996D
0x14063995f  mov     edx, eax
0x140639961  lea     rcx, aDriverVerifier_6; "Driver Verifier: Failed to delete Verif"...
0x140639968  call    VfUtilDbgPrint
0x14063996d  lea     rdx, aVerifierrandom_0; "VerifierRandomTargets"
0x140639974  lea     rcx, [rbp+DestinationString]; DestinationString
0x140639978  call    RtlInitUnicodeString
0x14063997d  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140639981  lea     rdx, [rbp+DestinationString]; ValueName
0x140639985  call    ZwDeleteValueKey
0x14063998a  lea     ecx, [rax+rdi]
0x14063998d  test    edi, ecx
0x14063998f  jnz     short loc_1406399A3
0x140639991  cmp     eax, ebx
0x140639993  jz      short loc_1406399A3
0x140639995  mov     edx, eax
0x140639997  lea     rcx, aDriverVerifier_19; "Driver Verifier: Failed to delete Verif"...
0x14063999e  call    VfUtilDbgPrint
0x1406399a3  cmp     cs:VfFlightOptions, 0
0x1406399aa  jz      short loc_1406399E2
0x1406399ac  lea     rdx, aXdvverifieropt_0; "XdvVerifierOptions"
0x1406399b3  lea     rcx, [rbp+DestinationString]; DestinationString
0x1406399b7  call    RtlInitUnicodeString
0x1406399bc  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1406399c0  lea     rdx, [rbp+DestinationString]; ValueName
0x1406399c4  call    ZwDeleteValueKey
0x1406399c9  lea     ecx, [rax+rdi]
0x1406399cc  test    edi, ecx
0x1406399ce  jnz     short loc_1406399E2
0x1406399d0  cmp     eax, ebx
0x1406399d2  jz      short loc_1406399E2
0x1406399d4  mov     edx, eax
0x1406399d6  lea     rcx, aDriverVerifier_14; "Driver Verifier: Failed to delete XdvVe"...
0x1406399dd  call    VfUtilDbgPrint
0x1406399e2  lea     rdx, aVrfpersistthro; "VrfPersistThroughUpgrade"
0x1406399e9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1406399ed  call    RtlInitUnicodeString
0x1406399f2  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1406399f6  lea     rdx, [rbp+DestinationString]; ValueName
0x1406399fa  call    ZwDeleteValueKey
0x1406399ff  lea     ecx, [rax+rdi]
0x140639a02  test    edi, ecx
0x140639a04  jnz     short loc_140639A18
0x140639a06  cmp     eax, ebx
0x140639a08  jz      short loc_140639A18
0x140639a0a  mov     edx, eax
0x140639a0c  lea     rcx, aDriverVerifier_10; "Driver Verifier: Failed to delete VrfPe"...
0x140639a13  call    VfUtilDbgPrint
0x140639a18  lea     rdx, aVerifiertriage; "VerifierTriageContext"
0x140639a1f  lea     rcx, [rbp+DestinationString]; DestinationString
0x140639a23  call    RtlInitUnicodeString
0x140639a28  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140639a2c  lea     rdx, [rbp+DestinationString]; ValueName
0x140639a30  call    ZwDeleteValueKey
0x140639a35  lea     ecx, [rax+rdi]
0x140639a38  test    edi, ecx
0x140639a3a  jnz     short loc_140639A4E
0x140639a3c  cmp     eax, ebx
0x140639a3e  jz      short loc_140639A4E
0x140639a40  mov     edx, eax
0x140639a42  lea     rcx, aDriverVerifier_2; "Driver Verifier: Failed to delete Verif"...
0x140639a49  call    VfUtilDbgPrint
0x140639a4e  cmp     cs:VfXdvSuppressDriversBufferLength, 0FFFFFFFFh
0x140639a55  jz      short loc_140639A8D
0x140639a57  lea     rdx, aVerifydriverss_0; "VerifyDriversSuppress"
0x140639a5e  lea     rcx, [rbp+DestinationString]; DestinationString
0x140639a62  call    RtlInitUnicodeString
0x140639a67  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140639a6b  lea     rdx, [rbp+DestinationString]; ValueName
0x140639a6f  call    ZwDeleteValueKey
0x140639a74  lea     ecx, [rax+rdi]
0x140639a77  test    edi, ecx
0x140639a79  jnz     short loc_140639A8D
0x140639a7b  cmp     eax, ebx
0x140639a7d  jz      short loc_140639A8D
0x140639a7f  mov     edx, eax
0x140639a81  lea     rcx, aDriverVerifier_16; "Driver Verifier: Failed to delete Verif"...
0x140639a88  call    VfUtilDbgPrint
0x140639a8d  lea     rdx, aVerifiertiplim_0; "VerifierTipLimitNumerator"
0x140639a94  lea     rcx, [rbp+DestinationString]; DestinationString
0x140639a98  call    RtlInitUnicodeString
0x140639a9d  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140639aa1  lea     rdx, [rbp+DestinationString]; ValueName
0x140639aa5  call    ZwDeleteValueKey
0x140639aaa  lea     ecx, [rax+rdi]
0x140639aad  test    edi, ecx
0x140639aaf  jnz     short loc_140639AC3
0x140639ab1  cmp     eax, ebx
0x140639ab3  jz      short loc_140639AC3
0x140639ab5  mov     edx, eax
0x140639ab7  lea     rcx, aDriverVerifier_12; "Driver Verifier: Failed to delete Verif"...
0x140639abe  call    VfUtilDbgPrint
0x140639ac3  lea     rdx, aVerifiertiplim_1; "VerifierTipLimitDenominator"
0x140639aca  lea     rcx, [rbp+DestinationString]; DestinationString
0x140639ace  call    RtlInitUnicodeString
0x140639ad3  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140639ad7  lea     rdx, [rbp+DestinationString]; ValueName
0x140639adb  call    ZwDeleteValueKey
0x140639ae0  lea     ecx, [rax+rdi]
0x140639ae3  test    edi, ecx
0x140639ae5  jnz     short loc_140639AF9
0x140639ae7  cmp     eax, ebx
0x140639ae9  jz      short loc_140639AF9
0x140639aeb  mov     edx, eax
0x140639aed  lea     rcx, aDriverVerifier_11; "Driver Verifier: Failed to delete Verif"...
0x140639af4  call    VfUtilDbgPrint
0x140639af9  lea     rdx, aVerifiertipspa_0; "VerifierTipSparseness"
0x140639b00  lea     rcx, [rbp+DestinationString]; DestinationString
0x140639b04  call    RtlInitUnicodeString
0x140639b09  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140639b0d  lea     rdx, [rbp+DestinationString]; ValueName
0x140639b11  call    ZwDeleteValueKey
0x140639b16  lea     ecx, [rax+rdi]
0x140639b19  test    edi, ecx
0x140639b1b  jnz     short loc_140639B2F
0x140639b1d  cmp     eax, ebx
0x140639b1f  jz      short loc_140639B2F
0x140639b21  mov     edx, eax
0x140639b23  lea     rcx, aDriverVerifier; "Driver Verifier: Failed to delete Verif"...
0x140639b2a  call    VfUtilDbgPrint
0x140639b2f  lea     rdx, aVerifierlwsppo; "VerifierLwspPoolTags"
0x140639b36  lea     rcx, [rbp+DestinationString]; DestinationString
0x140639b3a  call    RtlInitUnicodeString
0x140639b3f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140639b43  lea     rdx, [rbp+DestinationString]; ValueName
0x140639b47  call    ZwDeleteValueKey
0x140639b4c  lea     ecx, [rax+rdi]
0x140639b4f  test    edi, ecx
0x140639b51  jnz     short loc_140639B65
0x140639b53  cmp     eax, ebx
0x140639b55  jz      short loc_140639B65
0x140639b57  mov     edx, eax
0x140639b59  lea     rcx, aDriverVerifier_23; "Driver Verifier: Failed to delete Verif"...
0x140639b60  call    VfUtilDbgPrint
0x140639b65  lea     rdx, aDifpluginconfi_0; "DifPluginConfigData"
0x140639b6c  lea     rcx, [rbp+DestinationString]; DestinationString
0x140639b70  call    RtlInitUnicodeString
0x140639b75  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140639b79  lea     rdx, [rbp+DestinationString]; ValueName
0x140639b7d  call    ZwDeleteValueKey
0x140639b82  lea     ecx, [rax+rdi]
0x140639b85  test    edi, ecx
0x140639b87  jnz     short loc_140639B9B
0x140639b89  cmp     eax, ebx
0x140639b8b  jz      short loc_140639B9B
0x140639b8d  mov     edx, eax
0x140639b8f  lea     rcx, aDriverVerifier_21; "Driver Verifier: Failed to delete DifPl"...
0x140639b96  call    VfUtilDbgPrint
0x140639b9b  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140639b9f  call    ZwFlushKey
0x140639ba4  cmp     cs:VfClearanceFlag, 0
0x140639bab  jz      short loc_140639BC9
0x140639bad  lea     rcx, aDriverVerifier_17; "Driver Verifier: Clearing Verifier opti"...
0x140639bb4  call    VfUtilDbgPrint
0x140639bb9  jmp     short loc_140639BC9
0x140639bbb  mov     edx, eax
0x140639bbd  lea     rcx, aDriverVerifier_7; "Driver Verifier: Failed to set Verifier"...
0x140639bc4  call    VfUtilDbgPrint
0x140639bc9  mov     rcx, [rbp+KeyHandle]; Handle
0x140639bcd  call    ZwClose
0x140639bd2  jmp     short loc_140639BE2
0x140639bd4  mov     edx, eax
0x140639bd6  lea     rcx, aDriverVerifier_15; "Driver Verifier: Failed to open Memory "...
0x140639bdd  call    VfUtilDbgPrint
0x140639be2  lea     r11, [rsp+70h+var_s0]
0x140639be7  mov     rbx, [r11+20h]
0x140639beb  mov     rdi, [r11+28h]
0x140639bef  mov     rsp, r11
0x140639bf2  pop     rbp
0x140639bf3  retn
```
