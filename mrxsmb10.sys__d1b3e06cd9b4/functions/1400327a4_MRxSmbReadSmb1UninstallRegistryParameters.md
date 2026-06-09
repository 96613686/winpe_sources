# MRxSmbReadSmb1UninstallRegistryParameters

- ea: `0x1400327a4`
- end: `0x140032890`
- name: `MRxSmbReadSmb1UninstallRegistryParameters`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140032e60`

## callees

- `0x140031adc`
- `0x1400327a4`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140032813`
- `ntoskrnl!ZwOpenKey` at `0x140032813`
- `ntoskrnl!ZwClose` at `0x14003287d`
- `ntoskrnl!ZwClose` at `0x14003287d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400327d4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400327d4`

## string_xrefs

- `0x1400327b0`: `\Registry\Machine\Software\Microsoft\SMB1Uninstall`
- `0x14003285c`: `UninstallSMB1LBDays`

## pseudocode

```c
int MRxSmbReadSmb1UninstallRegistryParameters()
{
  int result; // eax
  int UlongRegistryParameter; // eax
  int v2; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp+18h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Software\\Microsoft\\SMB1Uninstall");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      MRxSmbSMB1DeprecationEnabled = MRxSmbSMB1DeprecationEnabledByPolicy;
    else
      MRxSmbSMB1DeprecationEnabled = 0;
    UlongRegistryParameter = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v2 = 15;
    if ( UlongRegistryParameter >= 0 )
      v2 = 0;
    MRxSmbUninstallSMB1LBDays = v2;
    return ZwClose(KeyHandle);
  }
  return result;
}

```

## disassembly

```asm
0x1400327a4  push    rbp
0x1400327a6  mov     rbp, rsp
0x1400327a9  sub     rsp, 60h
0x1400327ad  xorps   xmm0, xmm0
0x1400327b0  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x1400327b7  xor     eax, eax
0x1400327b9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400327bd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400327c1  mov     [rbp+KeyHandle], rax
0x1400327c5  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400327c9  mov     [rbp+arg_0], eax
0x1400327cc  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400327d0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400327d4  call    cs:__imp_RtlInitUnicodeString
0x1400327db  nop     dword ptr [rax+rax+00h]
0x1400327e0  lea     rax, [rbp+DestinationString]
0x1400327e4  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400327eb  xorps   xmm0, xmm0
0x1400327ee  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400327f2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400327f6  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400327fe  mov     edx, 20019h; DesiredAccess
0x140032803  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14003280a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14003280e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140032813  call    cs:__imp_ZwOpenKey
0x14003281a  nop     dword ptr [rax+rax+00h]
0x14003281f  test    eax, eax
0x140032821  js      short loc_140032889
0x140032823  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140032827  lea     r8, [rbp+arg_0]
0x14003282b  lea     rdx, aEnabled; "Enabled"
0x140032832  call    MRxSmbGetUlongRegistryParameter
0x140032837  test    eax, eax
0x140032839  js      short loc_140032848
0x14003283b  cmp     [rbp+arg_0], 0
0x14003283f  setnz   cs:MRxSmbSMB1DeprecationEnabled
0x140032846  jmp     short loc_140032854
0x140032848  mov     al, cs:MRxSmbSMB1DeprecationEnabledByPolicy
0x14003284e  mov     cs:MRxSmbSMB1DeprecationEnabled, al
0x140032854  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140032858  lea     r8, [rbp+arg_0]
0x14003285c  lea     rdx, aUninstallsmb1l; "UninstallSMB1LBDays"
0x140032863  call    MRxSmbGetUlongRegistryParameter
0x140032868  test    eax, eax
0x14003286a  mov     ecx, 0Fh
0x14003286f  cmovns  ecx, [rbp+arg_0]
0x140032873  mov     cs:MRxSmbUninstallSMB1LBDays, ecx
0x140032879  mov     rcx, [rbp+KeyHandle]; Handle
0x14003287d  call    cs:__imp_ZwClose
0x140032884  nop     dword ptr [rax+rax+00h]
0x140032889  add     rsp, 60h
0x14003288d  pop     rbp
0x14003288e  retn
```
