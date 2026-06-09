# VfClearVerifierSettings

- ea: `0x140633cf8`
- end: `0x140634105`
- name: `VfClearVerifierSettings`
- size: `1037`
- prototype: `NTSTATUS()`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140bc1800`
- `0x140c4ec48`

## callees

- `0x1403f2d50`
- `0x140529430`
- `0x140633cf8`
- `0x1406daa70`
- `0x1406daad0`
- `0x1406db490`
- `0x1406dc470`
- `0x1406dc6b0`

## string_xrefs

- `0x140633ee6`: `Driver Verifier: Failed to delete XdvVerifierOptions key value with status: 0x%x\n`
- `0x140633f1c`: `Driver Verifier: Failed to delete VrfPersistThroughUpgrade key value with status: 0x%x\n`
- `0x140633e71`: `Driver Verifier: Failed to delete VerifyDrivers key value with status: 0x%x\n`
- `0x140633ea7`: `Driver Verifier: Failed to delete VerifierRandomTargets key value with status: 0x%x\n`
- `0x140633e05`: `Driver Verifier: Failed to delete VerifyDriverLevel key value with status: 0x%x\n`
- `0x140633e3b`: `Driver Verifier: Failed to delete RuleClasses key value with status: 0x%x\n`
- `0x1406340bd`: `Driver Verifier: Clearing Verifier options from Registry for preventing recursive crash.\n`
- `0x14063409f`: `Driver Verifier: Failed to delete DifPluginConfigData key value with status: 0x%x\n`
- `0x1406340e6`: `Driver Verifier: Failed to open Memory Management key with status: 0x%x\n Registry updates aborted!`
- `0x1406340cd`: `Driver Verifier: Failed to set VerifierOptionFlags key value with status: 0x%x\n Registry updates aborted!`
- `0x140634033`: `Driver Verifier: Failed to delete VerifierTipSparseness key value with status: 0x%x\n`
- `0x140634075`: `DifPluginConfigData`
- `0x140634069`: `Driver Verifier: Failed to delete VerifierLwspPoolTags key value with status: 0x%x\n`
- `0x140633fc7`: `Driver Verifier: Failed to delete VerifierTipLimitNumerator key value with status: 0x%x\n`
- `0x140633ffd`: `Driver Verifier: Failed to delete VerifierTipLimitDenominator key value with status: 0x%x\n`
- `0x140633f52`: `Driver Verifier: Failed to delete VerifierTriageContext key value with status: 0x%x\n`
- `0x140633f91`: `Driver Verifier: Failed to delete VerifyDriversSuppress key value with status: 0x%x\n`

## pseudocode

```c
NTSTATUS VfClearVerifierSettings()
{
  unsigned int v0; // eax
  PVOID *Reserved; // rax
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
  Reserved = (PVOID *)&VfPersistentStateRoot;
  ObjectAttributes.Length = 48;
  if ( !HIDWORD(WheapPfaLock.KernelStack) )
    Reserved = PspActiveProcessLock.SchedulerApc.Reserved;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)Reserved;
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
0x140633cf8  mov     [rsp-8+arg_10], rbx
0x140633cfd  mov     [rsp-8+arg_18], rdi
0x140633d02  push    rbp
0x140633d03  mov     rbp, rsp
0x140633d06  sub     rsp, 70h
0x140633d0a  xor     eax, eax
0x140633d0c  mov     [rbp+KeyHandle], 0
0x140633d14  mov     dword ptr [rbp+ObjectAttributes+4], eax
0x140633d17  xorps   xmm0, xmm0
0x140633d1a  mov     dword ptr [rbp+ObjectAttributes+1Ch], eax
0x140633d1d  mov     eax, cs:VfOptionFlags
0x140633d23  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140633d27  test    al, 20h
0x140633d29  jz      short loc_140633D30
0x140633d2b  and     eax, 0FFFFFFCFh
0x140633d2e  jmp     short loc_140633D40
0x140633d30  bt      eax, 0Ah
0x140633d34  jnb     short loc_140633D3D
0x140633d36  and     eax, 0FFFFFBC7h
0x140633d3b  jmp     short loc_140633D40
0x140633d3d  and     eax, 0FFFFFFE7h
0x140633d40  cmp     dword ptr cs:WheapPfaLock.KernelStack+4, 0
0x140633d47  lea     rcx, PspActiveProcessLock.___u58+20h
0x140633d4e  mov     [rbp+arg_0], eax
0x140633d51  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140633d55  lea     rax, VfPersistentStateRoot
0x140633d5c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140633d63  cmovz   rax, rcx
0x140633d67  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140633d6f  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140633d73  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140633d77  mov     edx, 0F003Fh; DesiredAccess
0x140633d7c  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140633d83  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140633d88  call    ZwOpenKey
0x140633d8d  test    eax, eax
0x140633d8f  js      loc_1406340E4
0x140633d95  lea     rdx, aVerifieroption_0; "VerifierOptions"
0x140633d9c  lea     rcx, [rbp+DestinationString]; DestinationString
0x140633da0  call    RtlInitUnicodeString
0x140633da5  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140633da9  lea     rax, [rbp+arg_0]
0x140633dad  mov     r9d, 4; Type
0x140633db3  lea     rdx, [rbp+DestinationString]; ValueName
0x140633db7  mov     [rsp+70h+DataSize], r9d; DataSize
0x140633dbc  xor     r8d, r8d; TitleIndex
0x140633dbf  mov     [rsp+70h+Data], rax; Data
0x140633dc4  call    ZwSetValueKey
0x140633dc9  test    eax, eax
0x140633dcb  js      loc_1406340CB
0x140633dd1  lea     rdx, aVerifydriverle_0; "VerifyDriverLevel"
0x140633dd8  lea     rcx, [rbp+DestinationString]; DestinationString
0x140633ddc  call    RtlInitUnicodeString
0x140633de1  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140633de5  lea     rdx, [rbp+DestinationString]; ValueName
0x140633de9  call    ZwDeleteValueKey
0x140633dee  mov     edi, 80000000h
0x140633df3  mov     ebx, 0C0000034h
0x140633df8  lea     ecx, [rax+rdi]
0x140633dfb  test    edi, ecx
0x140633dfd  jnz     short loc_140633E11
0x140633dff  cmp     eax, ebx
0x140633e01  jz      short loc_140633E11
0x140633e03  mov     edx, eax
0x140633e05  lea     rcx, aDriverVerifier_20; "Driver Verifier: Failed to delete Verif"...
0x140633e0c  call    VfUtilDbgPrint
0x140633e11  lea     rdx, aVerifiersettin_0; "VerifierSettingState"
0x140633e18  lea     rcx, [rbp+DestinationString]; DestinationString
0x140633e1c  call    RtlInitUnicodeString
0x140633e21  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140633e25  lea     rdx, [rbp+DestinationString]; ValueName
0x140633e29  call    ZwDeleteValueKey
0x140633e2e  lea     ecx, [rax+rdi]
0x140633e31  test    edi, ecx
0x140633e33  jnz     short loc_140633E47
0x140633e35  cmp     eax, ebx
0x140633e37  jz      short loc_140633E47
0x140633e39  mov     edx, eax
0x140633e3b  lea     rcx, aDriverVerifier_13; "Driver Verifier: Failed to delete RuleC"...
0x140633e42  call    VfUtilDbgPrint
0x140633e47  lea     rdx, aVerifydrivers_0; "VerifyDrivers"
0x140633e4e  lea     rcx, [rbp+DestinationString]; DestinationString
0x140633e52  call    RtlInitUnicodeString
0x140633e57  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140633e5b  lea     rdx, [rbp+DestinationString]; ValueName
0x140633e5f  call    ZwDeleteValueKey
0x140633e64  lea     ecx, [rax+rdi]
0x140633e67  test    edi, ecx
0x140633e69  jnz     short loc_140633E7D
0x140633e6b  cmp     eax, ebx
0x140633e6d  jz      short loc_140633E7D
0x140633e6f  mov     edx, eax
0x140633e71  lea     rcx, aDriverVerifier_6; "Driver Verifier: Failed to delete Verif"...
0x140633e78  call    VfUtilDbgPrint
0x140633e7d  lea     rdx, aVerifierrandom_0; "VerifierRandomTargets"
0x140633e84  lea     rcx, [rbp+DestinationString]; DestinationString
0x140633e88  call    RtlInitUnicodeString
0x140633e8d  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140633e91  lea     rdx, [rbp+DestinationString]; ValueName
0x140633e95  call    ZwDeleteValueKey
0x140633e9a  lea     ecx, [rax+rdi]
0x140633e9d  test    edi, ecx
0x140633e9f  jnz     short loc_140633EB3
0x140633ea1  cmp     eax, ebx
0x140633ea3  jz      short loc_140633EB3
0x140633ea5  mov     edx, eax
0x140633ea7  lea     rcx, aDriverVerifier_19; "Driver Verifier: Failed to delete Verif"...
0x140633eae  call    VfUtilDbgPrint
0x140633eb3  cmp     cs:VfFlightOptions, 0
0x140633eba  jz      short loc_140633EF2
0x140633ebc  lea     rdx, aXdvverifieropt_0; "XdvVerifierOptions"
0x140633ec3  lea     rcx, [rbp+DestinationString]; DestinationString
0x140633ec7  call    RtlInitUnicodeString
0x140633ecc  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140633ed0  lea     rdx, [rbp+DestinationString]; ValueName
0x140633ed4  call    ZwDeleteValueKey
0x140633ed9  lea     ecx, [rax+rdi]
0x140633edc  test    edi, ecx
0x140633ede  jnz     short loc_140633EF2
0x140633ee0  cmp     eax, ebx
0x140633ee2  jz      short loc_140633EF2
0x140633ee4  mov     edx, eax
0x140633ee6  lea     rcx, aDriverVerifier_14; "Driver Verifier: Failed to delete XdvVe"...
0x140633eed  call    VfUtilDbgPrint
0x140633ef2  lea     rdx, aVrfpersistthro; "VrfPersistThroughUpgrade"
0x140633ef9  lea     rcx, [rbp+DestinationString]; DestinationString
0x140633efd  call    RtlInitUnicodeString
0x140633f02  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140633f06  lea     rdx, [rbp+DestinationString]; ValueName
0x140633f0a  call    ZwDeleteValueKey
0x140633f0f  lea     ecx, [rax+rdi]
0x140633f12  test    edi, ecx
0x140633f14  jnz     short loc_140633F28
0x140633f16  cmp     eax, ebx
0x140633f18  jz      short loc_140633F28
0x140633f1a  mov     edx, eax
0x140633f1c  lea     rcx, aDriverVerifier_10; "Driver Verifier: Failed to delete VrfPe"...
0x140633f23  call    VfUtilDbgPrint
0x140633f28  lea     rdx, aVerifiertriage; "VerifierTriageContext"
0x140633f2f  lea     rcx, [rbp+DestinationString]; DestinationString
0x140633f33  call    RtlInitUnicodeString
0x140633f38  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140633f3c  lea     rdx, [rbp+DestinationString]; ValueName
0x140633f40  call    ZwDeleteValueKey
0x140633f45  lea     ecx, [rax+rdi]
0x140633f48  test    edi, ecx
0x140633f4a  jnz     short loc_140633F5E
0x140633f4c  cmp     eax, ebx
0x140633f4e  jz      short loc_140633F5E
0x140633f50  mov     edx, eax
0x140633f52  lea     rcx, aDriverVerifier_2; "Driver Verifier: Failed to delete Verif"...
0x140633f59  call    VfUtilDbgPrint
0x140633f5e  cmp     cs:VfXdvSuppressDriversBufferLength, 0FFFFFFFFh
0x140633f65  jz      short loc_140633F9D
0x140633f67  lea     rdx, aVerifydriverss_0; "VerifyDriversSuppress"
0x140633f6e  lea     rcx, [rbp+DestinationString]; DestinationString
0x140633f72  call    RtlInitUnicodeString
0x140633f77  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140633f7b  lea     rdx, [rbp+DestinationString]; ValueName
0x140633f7f  call    ZwDeleteValueKey
0x140633f84  lea     ecx, [rax+rdi]
0x140633f87  test    edi, ecx
0x140633f89  jnz     short loc_140633F9D
0x140633f8b  cmp     eax, ebx
0x140633f8d  jz      short loc_140633F9D
0x140633f8f  mov     edx, eax
0x140633f91  lea     rcx, aDriverVerifier_16; "Driver Verifier: Failed to delete Verif"...
0x140633f98  call    VfUtilDbgPrint
0x140633f9d  lea     rdx, aVerifiertiplim_0; "VerifierTipLimitNumerator"
0x140633fa4  lea     rcx, [rbp+DestinationString]; DestinationString
0x140633fa8  call    RtlInitUnicodeString
0x140633fad  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140633fb1  lea     rdx, [rbp+DestinationString]; ValueName
0x140633fb5  call    ZwDeleteValueKey
0x140633fba  lea     ecx, [rax+rdi]
0x140633fbd  test    edi, ecx
0x140633fbf  jnz     short loc_140633FD3
0x140633fc1  cmp     eax, ebx
0x140633fc3  jz      short loc_140633FD3
0x140633fc5  mov     edx, eax
0x140633fc7  lea     rcx, aDriverVerifier_12; "Driver Verifier: Failed to delete Verif"...
0x140633fce  call    VfUtilDbgPrint
0x140633fd3  lea     rdx, aVerifiertiplim_1; "VerifierTipLimitDenominator"
0x140633fda  lea     rcx, [rbp+DestinationString]; DestinationString
0x140633fde  call    RtlInitUnicodeString
0x140633fe3  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140633fe7  lea     rdx, [rbp+DestinationString]; ValueName
0x140633feb  call    ZwDeleteValueKey
0x140633ff0  lea     ecx, [rax+rdi]
0x140633ff3  test    edi, ecx
0x140633ff5  jnz     short loc_140634009
0x140633ff7  cmp     eax, ebx
0x140633ff9  jz      short loc_140634009
0x140633ffb  mov     edx, eax
0x140633ffd  lea     rcx, aDriverVerifier_11; "Driver Verifier: Failed to delete Verif"...
0x140634004  call    VfUtilDbgPrint
0x140634009  lea     rdx, aVerifiertipspa_0; "VerifierTipSparseness"
0x140634010  lea     rcx, [rbp+DestinationString]; DestinationString
0x140634014  call    RtlInitUnicodeString
0x140634019  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14063401d  lea     rdx, [rbp+DestinationString]; ValueName
0x140634021  call    ZwDeleteValueKey
0x140634026  lea     ecx, [rax+rdi]
0x140634029  test    edi, ecx
0x14063402b  jnz     short loc_14063403F
0x14063402d  cmp     eax, ebx
0x14063402f  jz      short loc_14063403F
0x140634031  mov     edx, eax
0x140634033  lea     rcx, aDriverVerifier; "Driver Verifier: Failed to delete Verif"...
0x14063403a  call    VfUtilDbgPrint
0x14063403f  lea     rdx, aVerifierlwsppo; "VerifierLwspPoolTags"
0x140634046  lea     rcx, [rbp+DestinationString]; DestinationString
0x14063404a  call    RtlInitUnicodeString
0x14063404f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140634053  lea     rdx, [rbp+DestinationString]; ValueName
0x140634057  call    ZwDeleteValueKey
0x14063405c  lea     ecx, [rax+rdi]
0x14063405f  test    edi, ecx
0x140634061  jnz     short loc_140634075
0x140634063  cmp     eax, ebx
0x140634065  jz      short loc_140634075
0x140634067  mov     edx, eax
0x140634069  lea     rcx, aDriverVerifier_23; "Driver Verifier: Failed to delete Verif"...
0x140634070  call    VfUtilDbgPrint
0x140634075  lea     rdx, aDifpluginconfi_0; "DifPluginConfigData"
0x14063407c  lea     rcx, [rbp+DestinationString]; DestinationString
0x140634080  call    RtlInitUnicodeString
0x140634085  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140634089  lea     rdx, [rbp+DestinationString]; ValueName
0x14063408d  call    ZwDeleteValueKey
0x140634092  lea     ecx, [rax+rdi]
0x140634095  test    edi, ecx
0x140634097  jnz     short loc_1406340AB
0x140634099  cmp     eax, ebx
0x14063409b  jz      short loc_1406340AB
0x14063409d  mov     edx, eax
0x14063409f  lea     rcx, aDriverVerifier_21; "Driver Verifier: Failed to delete DifPl"...
0x1406340a6  call    VfUtilDbgPrint
0x1406340ab  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1406340af  call    ZwFlushKey
0x1406340b4  cmp     cs:VfClearanceFlag, 0
0x1406340bb  jz      short loc_1406340D9
0x1406340bd  lea     rcx, aDriverVerifier_17; "Driver Verifier: Clearing Verifier opti"...
0x1406340c4  call    VfUtilDbgPrint
0x1406340c9  jmp     short loc_1406340D9
0x1406340cb  mov     edx, eax
0x1406340cd  lea     rcx, aDriverVerifier_7; "Driver Verifier: Failed to set Verifier"...
0x1406340d4  call    VfUtilDbgPrint
0x1406340d9  mov     rcx, [rbp+KeyHandle]; Handle
0x1406340dd  call    ZwClose
0x1406340e2  jmp     short loc_1406340F2
0x1406340e4  mov     edx, eax
0x1406340e6  lea     rcx, aDriverVerifier_15; "Driver Verifier: Failed to open Memory "...
0x1406340ed  call    VfUtilDbgPrint
0x1406340f2  lea     r11, [rsp+70h+var_s0]
0x1406340f7  mov     rbx, [r11+20h]
0x1406340fb  mov     rdi, [r11+28h]
0x1406340ff  mov     rsp, r11
0x140634102  pop     rbp
0x140634103  retn
```
