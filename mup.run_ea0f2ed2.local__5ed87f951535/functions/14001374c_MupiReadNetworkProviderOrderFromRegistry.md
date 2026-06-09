# MupiReadNetworkProviderOrderFromRegistry

- ea: `0x14001374c`
- end: `0x14001387e`
- name: `MupiReadNetworkProviderOrderFromRegistry`
- size: `306`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000f2a0`

## callees

- `0x1400054a0`
- `0x14001374c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400137aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013805`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400137aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013805`
- `ntoskrnl!ZwQueryValueKey` at `0x140013837`
- `ntoskrnl!ZwQueryValueKey` at `0x140013837`
- `ntoskrnl!ZwOpenKey` at `0x1400137ec`
- `ntoskrnl!ZwOpenKey` at `0x1400137ec`

## string_xrefs

- `0x14001379f`: `\Registry\Machine\System\CurrentControlSet\Control\Networkprovider\ProviderOrder`

## pseudocode

```c
__int64 __fastcall MupiReadNetworkProviderOrderFromRegistry(PCWSTR SourceString, _DWORD *a2)
{
  NTSTATUS v4; // ecx
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp+Fh] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+78h] [rbp+1Fh] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+88h] [rbp+2Fh] BYREF
  int v11; // [rsp+8Ch] [rbp+33h]
  int v12; // [rsp+90h] [rbp+37h]
  int v13; // [rsp+94h] [rbp+3Bh]

  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  ValueName = 0;
  if ( MupiNetworkProviderOrderKeyHandle
    || (RtlInitUnicodeString(
          &DestinationString,
          L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Networkprovider\\ProviderOrder"),
        ObjectAttributes.Length = 48,
        ObjectAttributes.ObjectName = &DestinationString,
        ObjectAttributes.RootDirectory = 0,
        ObjectAttributes.Attributes = 576,
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
        v4 = ZwOpenKey(&MupiNetworkProviderOrderKeyHandle, 0x10u, &ObjectAttributes),
        v4 >= 0) )
  {
    RtlInitUnicodeString(&ValueName, SourceString);
    v4 = ZwQueryValueKey(
           MupiNetworkProviderOrderKeyHandle,
           &ValueName,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x18u,
           &ResultLength);
    if ( v4 >= 0 && v11 == 4 && v12 == 4 )
      *a2 = v13;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001374c  mov     [rsp-8+arg_10], rbx
0x140013751  mov     [rsp-8+arg_18], rdi
0x140013756  push    rbp
0x140013757  lea     rbp, [rsp-57h]
0x14001375c  sub     rsp, 0B0h
0x140013763  mov     rax, cs:__security_cookie
0x14001376a  xor     rax, rsp
0x14001376d  mov     [rbp+57h+var_10], rax
0x140013771  xorps   xmm0, xmm0
0x140013774  xor     eax, eax
0x140013776  cmp     cs:MupiNetworkProviderOrderKeyHandle, rax
0x14001377d  xorps   xmm1, xmm1
0x140013780  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140013784  mov     rbx, rdx
0x140013787  mov     rdi, rcx
0x14001378a  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14001378e  mov     [rbp+57h+var_80], eax
0x140013791  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140013795  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140013799  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x14001379d  jnz     short loc_1400137FE
0x14001379f  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400137a6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400137aa  call    cs:__imp_RtlInitUnicodeString
0x1400137b1  nop     dword ptr [rax+rax+00h]
0x1400137b6  lea     rax, [rbp+57h+DestinationString]
0x1400137ba  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400137c1  xorps   xmm0, xmm0
0x1400137c4  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400137c8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400137cc  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400137d4  mov     edx, 10h; DesiredAccess
0x1400137d9  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400137e0  lea     rcx, MupiNetworkProviderOrderKeyHandle; KeyHandle
0x1400137e7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400137ec  call    cs:__imp_ZwOpenKey
0x1400137f3  nop     dword ptr [rax+rax+00h]
0x1400137f8  mov     ecx, eax
0x1400137fa  test    eax, eax
0x1400137fc  js      short loc_14001385A
0x1400137fe  mov     rdx, rdi; SourceString
0x140013801  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140013805  call    cs:__imp_RtlInitUnicodeString
0x14001380c  nop     dword ptr [rax+rax+00h]
0x140013811  mov     rcx, cs:MupiNetworkProviderOrderKeyHandle; KeyHandle
0x140013818  lea     rax, [rbp+57h+var_80]
0x14001381c  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x140013821  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140013825  mov     r8d, 2; KeyValueInformationClass
0x14001382b  mov     [rsp+0B0h+Length], 18h; Length
0x140013833  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140013837  call    cs:__imp_ZwQueryValueKey
0x14001383e  nop     dword ptr [rax+rax+00h]
0x140013843  mov     ecx, eax
0x140013845  test    eax, eax
0x140013847  js      short loc_14001385A
0x140013849  cmp     [rbp+57h+var_24], 4
0x14001384d  jnz     short loc_14001385A
0x14001384f  cmp     [rbp+57h+var_20], 4
0x140013853  jnz     short loc_14001385A
0x140013855  mov     eax, [rbp+57h+var_1C]
0x140013858  mov     [rbx], eax
0x14001385a  mov     eax, ecx
0x14001385c  mov     rcx, [rbp+57h+var_10]
0x140013860  xor     rcx, rsp; StackCookie
0x140013863  call    __security_check_cookie
0x140013868  lea     r11, [rsp+0B0h+var_s0]
0x140013870  mov     rbx, [r11+20h]
0x140013874  mov     rdi, [r11+28h]
0x140013878  mov     rsp, r11
0x14001387b  pop     rbp
0x14001387c  retn
```
