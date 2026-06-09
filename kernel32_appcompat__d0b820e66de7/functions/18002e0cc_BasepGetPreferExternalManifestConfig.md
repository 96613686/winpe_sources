# BasepGetPreferExternalManifestConfig

- ea: `0x18002e0cc`
- end: `0x18002e252`
- name: `BasepGetPreferExternalManifestConfig`
- size: `390`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002de78`
- `0x18002e8e0`

## callees

- `0x18002e0cc`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18002e1b9`
- `ntdll!NtQueryValueKey` at `0x18002e1b9`
- `ntdll!NtOpenKey` at `0x18002e169`
- `ntdll!NtOpenKey` at `0x18002e169`
- `ntdll!NtClose` at `0x18002e1dc`
- `ntdll!NtClose` at `0x18002e1dc`
- `ntdll!RtlInitUnicodeString` at `0x18002e12e`
- `ntdll!RtlInitUnicodeString` at `0x18002e18a`
- `ntdll!RtlInitUnicodeString` at `0x18002e12e`
- `ntdll!RtlInitUnicodeString` at `0x18002e18a`

## string_xrefs

- `0x18002e123`: `\Registry\MACHINE\Software\Microsoft\Windows\CurrentVersion\SideBySide`
- `0x18002e17f`: `PreferExternalManifest`

## pseudocode

```c
__int64 __fastcall BasepGetPreferExternalManifestConfig(signed __int32 *a1)
{
  unsigned int v1; // ebx
  signed __int32 v3; // ecx
  NTSTATUS v4; // eax
  NTSTATUS v5; // eax
  signed __int32 v7; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+80h] [rbp+37h] BYREF
  int v13; // [rsp+84h] [rbp+3Bh]
  int v14; // [rsp+88h] [rbp+3Fh]
  signed __int32 v15; // [rsp+8Ch] [rbp+43h]

  v1 = 0;
  *a1 = 0;
  ResultLength = 0;
  v3 = dword_1800BD310;
  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( dword_1800BD310 != -1 )
    goto LABEL_9;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion\\SideBySide");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v1 = v4;
  if ( v4 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"PreferExternalManifest");
    v5 = NtQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x14u,
           &ResultLength);
    if ( v5 < 0 )
    {
      v1 = 0;
      if ( v5 != -1073741772 )
        v1 = v5;
      goto LABEL_6;
    }
    v1 = v5;
    if ( v13 != 4 || v14 != 4 || (v3 = v15, v15 == -1) )
      v3 = 1;
    v7 = _InterlockedCompareExchange(&dword_1800BD310, v3, -1);
    if ( v7 != -1 )
      v3 = v7;
LABEL_9:
    *a1 = v3;
    goto LABEL_6;
  }
  if ( v4 == -1073741772 || v4 == -1073741766 )
    v1 = 0;
LABEL_6:
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v1;
}

```

## disassembly

```asm
0x18002e0cc  mov     [rsp-8+arg_8], rbx
0x18002e0d1  mov     [rsp-8+arg_10], rdi
0x18002e0d6  push    rbp
0x18002e0d7  lea     rbp, [rsp-57h]
0x18002e0dc  sub     rsp, 0A0h
0x18002e0e3  mov     rax, cs:__security_cookie
0x18002e0ea  xor     rax, rsp
0x18002e0ed  mov     [rbp+57h+var_8], rax
0x18002e0f1  xorps   xmm0, xmm0
0x18002e0f4  xor     eax, eax
0x18002e0f6  xor     ebx, ebx
0x18002e0f8  mov     [rcx], eax
0x18002e0fa  mov     rdi, rcx
0x18002e0fd  mov     [rbp+57h+var_70], ebx
0x18002e100  mov     ecx, cs:dword_1800BD310
0x18002e106  mov     [rbp+57h+KeyHandle], rax
0x18002e10a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002e10e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002e112  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002e116  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18002e11a  cmp     ecx, 0FFFFFFFFh
0x18002e11d  jnz     loc_18002E20C
0x18002e123  lea     rdx, aRegistryMachin_9; "\\Registry\\MACHINE\\Software\\Microsof"...
0x18002e12a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002e12e  call    cs:__imp_RtlInitUnicodeString
0x18002e135  nop     dword ptr [rax+rax+00h]
0x18002e13a  lea     rax, [rbp+57h+DestinationString]
0x18002e13e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002e145  xorps   xmm0, xmm0
0x18002e148  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002e14c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002e150  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x18002e154  mov     edx, 20019h; DesiredAccess
0x18002e159  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18002e160  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002e164  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002e169  call    cs:__imp_NtOpenKey
0x18002e170  nop     dword ptr [rax+rax+00h]
0x18002e175  mov     ebx, eax
0x18002e177  test    eax, eax
0x18002e179  js      loc_18002E210
0x18002e17f  lea     rdx, aPreferexternal; "PreferExternalManifest"
0x18002e186  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002e18a  call    cs:__imp_RtlInitUnicodeString
0x18002e191  nop     dword ptr [rax+rax+00h]
0x18002e196  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002e19a  lea     rax, [rbp+57h+var_70]
0x18002e19e  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18002e1a3  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18002e1a7  mov     r8d, 2; KeyValueInformationClass
0x18002e1ad  mov     [rsp+0A0h+Length], 14h; Length
0x18002e1b5  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18002e1b9  call    cs:__imp_NtQueryValueKey
0x18002e1c0  nop     dword ptr [rax+rax+00h]
0x18002e1c5  test    eax, eax
0x18002e1c7  jns     short loc_18002E224
0x18002e1c9  xor     ebx, ebx
0x18002e1cb  cmp     eax, 0C0000034h
0x18002e1d0  cmovnz  ebx, eax
0x18002e1d3  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18002e1d7  test    rcx, rcx
0x18002e1da  jz      short loc_18002E1E8
0x18002e1dc  call    cs:__imp_NtClose
0x18002e1e3  nop     dword ptr [rax+rax+00h]
0x18002e1e8  mov     eax, ebx
0x18002e1ea  mov     rcx, [rbp+57h+var_8]
0x18002e1ee  xor     rcx, rsp; StackCookie
0x18002e1f1  call    __security_check_cookie
0x18002e1f6  lea     r11, [rsp+0A0h+var_s0]
0x18002e1fe  mov     rbx, [r11+18h]
0x18002e202  mov     rdi, [r11+20h]
0x18002e206  mov     rsp, r11
0x18002e209  pop     rbp
0x18002e20a  retn
0x18002e20c  mov     [rdi], ecx
0x18002e20e  jmp     short loc_18002E1D3
0x18002e210  cmp     eax, 0C0000034h
0x18002e215  jnz     short loc_18002E21B
0x18002e217  xor     ebx, ebx
0x18002e219  jmp     short loc_18002E1D3
0x18002e21b  cmp     eax, 0C000003Ah
0x18002e220  jnz     short loc_18002E1D3
0x18002e222  jmp     short loc_18002E217
0x18002e224  cmp     [rbp+57h+var_1C], 4
0x18002e228  mov     ebx, eax
0x18002e22a  jnz     short loc_18002E23A
0x18002e22c  cmp     [rbp+57h+var_18], 4
0x18002e230  jnz     short loc_18002E23A
0x18002e232  mov     ecx, [rbp+57h+var_14]
0x18002e235  cmp     ecx, 0FFFFFFFFh
0x18002e238  jnz     short loc_18002E23F
0x18002e23a  mov     ecx, 1
0x18002e23f  or      eax, 0FFFFFFFFh
0x18002e242  lock cmpxchg cs:dword_1800BD310, ecx
0x18002e24a  cmp     eax, 0FFFFFFFFh
0x18002e24d  cmovnz  ecx, eax
0x18002e250  jmp     short loc_18002E20C
```
