# MupiReadNetworkProviderOrderFromRegistry

- ea: `0x14001379c`
- end: `0x1400138ce`
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
- `0x14001379c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400137fa`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013855`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400137fa`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013855`
- `ntoskrnl!ZwQueryValueKey` at `0x140013887`
- `ntoskrnl!ZwQueryValueKey` at `0x140013887`
- `ntoskrnl!ZwOpenKey` at `0x14001383c`
- `ntoskrnl!ZwOpenKey` at `0x14001383c`

## string_xrefs

- `0x1400137ef`: `\Registry\Machine\System\CurrentControlSet\Control\Networkprovider\ProviderOrder`

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
0x14001379c  mov     [rsp-8+arg_10], rbx
0x1400137a1  mov     [rsp-8+arg_18], rdi
0x1400137a6  push    rbp
0x1400137a7  lea     rbp, [rsp-57h]
0x1400137ac  sub     rsp, 0B0h
0x1400137b3  mov     rax, cs:__security_cookie
0x1400137ba  xor     rax, rsp
0x1400137bd  mov     [rbp+57h+var_10], rax
0x1400137c1  xorps   xmm0, xmm0
0x1400137c4  xor     eax, eax
0x1400137c6  cmp     cs:MupiNetworkProviderOrderKeyHandle, rax
0x1400137cd  xorps   xmm1, xmm1
0x1400137d0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400137d4  mov     rbx, rdx
0x1400137d7  mov     rdi, rcx
0x1400137da  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400137de  mov     [rbp+57h+var_80], eax
0x1400137e1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400137e5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400137e9  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1400137ed  jnz     short loc_14001384E
0x1400137ef  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400137f6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400137fa  call    cs:__imp_RtlInitUnicodeString
0x140013801  nop     dword ptr [rax+rax+00h]
0x140013806  lea     rax, [rbp+57h+DestinationString]
0x14001380a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140013811  xorps   xmm0, xmm0
0x140013814  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140013818  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001381c  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140013824  mov     edx, 10h; DesiredAccess
0x140013829  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140013830  lea     rcx, MupiNetworkProviderOrderKeyHandle; KeyHandle
0x140013837  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001383c  call    cs:__imp_ZwOpenKey
0x140013843  nop     dword ptr [rax+rax+00h]
0x140013848  mov     ecx, eax
0x14001384a  test    eax, eax
0x14001384c  js      short loc_1400138AA
0x14001384e  mov     rdx, rdi; SourceString
0x140013851  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140013855  call    cs:__imp_RtlInitUnicodeString
0x14001385c  nop     dword ptr [rax+rax+00h]
0x140013861  mov     rcx, cs:MupiNetworkProviderOrderKeyHandle; KeyHandle
0x140013868  lea     rax, [rbp+57h+var_80]
0x14001386c  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x140013871  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140013875  mov     r8d, 2; KeyValueInformationClass
0x14001387b  mov     [rsp+0B0h+Length], 18h; Length
0x140013883  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140013887  call    cs:__imp_ZwQueryValueKey
0x14001388e  nop     dword ptr [rax+rax+00h]
0x140013893  mov     ecx, eax
0x140013895  test    eax, eax
0x140013897  js      short loc_1400138AA
0x140013899  cmp     [rbp+57h+var_24], 4
0x14001389d  jnz     short loc_1400138AA
0x14001389f  cmp     [rbp+57h+var_20], 4
0x1400138a3  jnz     short loc_1400138AA
0x1400138a5  mov     eax, [rbp+57h+var_1C]
0x1400138a8  mov     [rbx], eax
0x1400138aa  mov     eax, ecx
0x1400138ac  mov     rcx, [rbp+57h+var_10]
0x1400138b0  xor     rcx, rsp; StackCookie
0x1400138b3  call    __security_check_cookie
0x1400138b8  lea     r11, [rsp+0B0h+var_s0]
0x1400138c0  mov     rbx, [r11+20h]
0x1400138c4  mov     rdi, [r11+28h]
0x1400138c8  mov     rsp, r11
0x1400138cb  pop     rbp
0x1400138cc  retn
```
