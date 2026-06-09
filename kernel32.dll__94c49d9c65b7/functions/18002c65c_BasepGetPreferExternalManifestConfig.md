# BasepGetPreferExternalManifestConfig

- ea: `0x18002c65c`
- end: `0x18002c7bf`
- name: `BasepGetPreferExternalManifestConfig`
- size: `355`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c408`
- `0x18002ce30`

## callees

- `0x18002c65c`
- `0x18007a840`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18002c733`
- `ntdll!NtQueryValueKey` at `0x18002c733`
- `ntdll!NtOpenKey` at `0x18002c6f3`
- `ntdll!NtOpenKey` at `0x18002c6f3`
- `ntdll!NtClose` at `0x18002c750`
- `ntdll!NtClose` at `0x18002c750`
- `ntdll!RtlInitUnicodeString` at `0x18002c6be`
- `ntdll!RtlInitUnicodeString` at `0x18002c70a`
- `ntdll!RtlInitUnicodeString` at `0x18002c6be`
- `ntdll!RtlInitUnicodeString` at `0x18002c70a`

## string_xrefs

- `0x18002c6b3`: `\Registry\MACHINE\Software\Microsoft\Windows\CurrentVersion\SideBySide`
- `0x18002c6ff`: `PreferExternalManifest`

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
  v3 = dword_1800B5310;
  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( dword_1800B5310 != -1 )
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
    v7 = _InterlockedCompareExchange(&dword_1800B5310, v3, -1);
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
0x18002c65c  mov     [rsp-8+arg_8], rbx
0x18002c661  mov     [rsp-8+arg_10], rdi
0x18002c666  push    rbp
0x18002c667  lea     rbp, [rsp-57h]
0x18002c66c  sub     rsp, 0A0h
0x18002c673  mov     rax, cs:__security_cookie
0x18002c67a  xor     rax, rsp
0x18002c67d  mov     [rbp+57h+var_8], rax
0x18002c681  xorps   xmm0, xmm0
0x18002c684  xor     eax, eax
0x18002c686  xor     ebx, ebx
0x18002c688  mov     [rcx], eax
0x18002c68a  mov     rdi, rcx
0x18002c68d  mov     [rbp+57h+var_70], ebx
0x18002c690  mov     ecx, cs:dword_1800B5310
0x18002c696  mov     [rbp+57h+KeyHandle], rax
0x18002c69a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002c69e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002c6a2  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002c6a6  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18002c6aa  cmp     ecx, 0FFFFFFFFh
0x18002c6ad  jnz     loc_18002C779
0x18002c6b3  lea     rdx, aRegistryMachin_9; "\\Registry\\MACHINE\\Software\\Microsof"...
0x18002c6ba  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002c6be  call    cs:__imp_RtlInitUnicodeString
0x18002c6c4  lea     rax, [rbp+57h+DestinationString]
0x18002c6c8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002c6cf  xorps   xmm0, xmm0
0x18002c6d2  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002c6d6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002c6da  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x18002c6de  mov     edx, 20019h; DesiredAccess
0x18002c6e3  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18002c6ea  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002c6ee  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002c6f3  call    cs:__imp_NtOpenKey
0x18002c6f9  mov     ebx, eax
0x18002c6fb  test    eax, eax
0x18002c6fd  js      short loc_18002C77D
0x18002c6ff  lea     rdx, aPreferexternal; "PreferExternalManifest"
0x18002c706  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002c70a  call    cs:__imp_RtlInitUnicodeString
0x18002c710  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002c714  lea     rax, [rbp+57h+var_70]
0x18002c718  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18002c71d  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18002c721  mov     r8d, 2; KeyValueInformationClass
0x18002c727  mov     [rsp+0A0h+Length], 14h; Length
0x18002c72f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18002c733  call    cs:__imp_NtQueryValueKey
0x18002c739  test    eax, eax
0x18002c73b  jns     short loc_18002C791
0x18002c73d  xor     ebx, ebx
0x18002c73f  cmp     eax, 0C0000034h
0x18002c744  cmovnz  ebx, eax
0x18002c747  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18002c74b  test    rcx, rcx
0x18002c74e  jz      short loc_18002C756
0x18002c750  call    cs:__imp_NtClose
0x18002c756  mov     eax, ebx
0x18002c758  mov     rcx, [rbp+57h+var_8]
0x18002c75c  xor     rcx, rsp; StackCookie
0x18002c75f  call    __security_check_cookie
0x18002c764  lea     r11, [rsp+0A0h+var_s0]
0x18002c76c  mov     rbx, [r11+18h]
0x18002c770  mov     rdi, [r11+20h]
0x18002c774  mov     rsp, r11
0x18002c777  pop     rbp
0x18002c778  retn
0x18002c779  mov     [rdi], ecx
0x18002c77b  jmp     short loc_18002C747
0x18002c77d  cmp     eax, 0C0000034h
0x18002c782  jnz     short loc_18002C788
0x18002c784  xor     ebx, ebx
0x18002c786  jmp     short loc_18002C747
0x18002c788  cmp     eax, 0C000003Ah
0x18002c78d  jnz     short loc_18002C747
0x18002c78f  jmp     short loc_18002C784
0x18002c791  cmp     [rbp+57h+var_1C], 4
0x18002c795  mov     ebx, eax
0x18002c797  jnz     short loc_18002C7A7
0x18002c799  cmp     [rbp+57h+var_18], 4
0x18002c79d  jnz     short loc_18002C7A7
0x18002c79f  mov     ecx, [rbp+57h+var_14]
0x18002c7a2  cmp     ecx, 0FFFFFFFFh
0x18002c7a5  jnz     short loc_18002C7AC
0x18002c7a7  mov     ecx, 1
0x18002c7ac  or      eax, 0FFFFFFFFh
0x18002c7af  lock cmpxchg cs:dword_1800B5310, ecx
0x18002c7b7  cmp     eax, 0FFFFFFFFh
0x18002c7ba  cmovnz  ecx, eax
0x18002c7bd  jmp     short loc_18002C779
```
