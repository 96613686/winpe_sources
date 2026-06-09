# GetPolicyState

- ea: `0x180043fb4`
- end: `0x1800440fc`
- name: `GetPolicyState`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043e44`

## callees

- `0x180043fb4`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x1800440a6`
- `ntdll!NtQueryValueKey` at `0x1800440a6`
- `ntdll!NtOpenKey` at `0x180044075`
- `ntdll!NtOpenKey` at `0x180044075`
- `ntdll!NtClose` at `0x1800440b8`
- `ntdll!NtClose` at `0x1800440b8`
- `ntdll!RtlInitUnicodeString` at `0x180044016`
- `ntdll!RtlInitUnicodeString` at `0x18004403a`
- `ntdll!RtlInitUnicodeString` at `0x180044016`
- `ntdll!RtlInitUnicodeString` at `0x18004403a`

## string_xrefs

- `0x180044022`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\WOW`
- `0x18004402b`: `\REGISTRY\MACHINE\Software\Policies\Microsoft\Windows\AppCompat`

## pseudocode

```c
__int64 __fastcall GetPolicyState(char a1)
{
  unsigned int v1; // edi
  const WCHAR *v2; // rdx
  const WCHAR *v4; // rdx
  NTSTATUS v5; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  struct _UNICODE_STRING v9; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp+37h] BYREF
  int v13; // [rsp+94h] [rbp+3Bh]
  int v14; // [rsp+9Ch] [rbp+43h]

  v1 = 0;
  v2 = L"VDMDisallowed";
  KeyHandle = 0;
  ResultLength = 0;
  if ( !a1 )
    v2 = L"DisallowedPolicyDefault";
  v9 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, v2);
  v4 = L"\\REGISTRY\\MACHINE\\Software\\Policies\\Microsoft\\Windows\\AppCompat";
  if ( !a1 )
    v4 = L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control\\WOW";
  RtlInitUnicodeString(&v9, v4);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v9;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    v5 = NtQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x14u,
           &ResultLength);
    NtClose(KeyHandle);
    if ( v5 >= 0 && v13 == 4 )
      return 2 - (unsigned int)(v14 != 0);
  }
  return v1;
}

```

## disassembly

```asm
0x180043fb4  mov     [rsp-8+arg_0], rbx
0x180043fb9  mov     [rsp-8+arg_8], rdi
0x180043fbe  push    rbp
0x180043fbf  lea     rbp, [rsp-57h]
0x180043fc4  sub     rsp, 0B0h
0x180043fcb  mov     rax, cs:__security_cookie
0x180043fd2  xor     rax, rsp
0x180043fd5  mov     [rbp+57h+var_8], rax
0x180043fd9  xorps   xmm0, xmm0
0x180043fdc  lea     rax, aDisallowedpoli; "DisallowedPolicyDefault"
0x180043fe3  xor     edi, edi
0x180043fe5  lea     rdx, aVdmdisallowed; "VDMDisallowed"
0x180043fec  test    cl, cl
0x180043fee  mov     [rbp+57h+KeyHandle], rdi
0x180043ff2  mov     bl, cl
0x180043ff4  mov     [rbp+57h+var_80], edi
0x180043ff7  xorps   xmm1, xmm1
0x180043ffa  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180043ffe  cmovz   rdx, rax; SourceString
0x180044002  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x180044006  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18004400a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18004400e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180044012  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180044016  call    cs:__imp_RtlInitUnicodeString
0x18004401d  nop     dword ptr [rax+rax+00h]
0x180044022  lea     rax, aRegistryMachin_26; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x180044029  test    bl, bl
0x18004402b  lea     rdx, aRegistryMachin_27; "\\REGISTRY\\MACHINE\\Software\\Policies"...
0x180044032  cmovz   rdx, rax; SourceString
0x180044036  lea     rcx, [rbp+57h+var_70]; DestinationString
0x18004403a  call    cs:__imp_RtlInitUnicodeString
0x180044041  nop     dword ptr [rax+rax+00h]
0x180044046  lea     rax, [rbp+57h+var_70]
0x18004404a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180044051  xorps   xmm0, xmm0
0x180044054  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180044058  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18004405c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180044060  mov     edx, 20019h; DesiredAccess
0x180044065  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18004406c  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180044070  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180044075  call    cs:__imp_NtOpenKey
0x18004407c  nop     dword ptr [rax+rax+00h]
0x180044081  test    eax, eax
0x180044083  js      short loc_1800440D8
0x180044085  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180044089  lea     rax, [rbp+57h+var_80]
0x18004408d  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x180044092  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180044096  lea     r8d, [rdi+2]; KeyValueInformationClass
0x18004409a  mov     [rsp+0B0h+Length], 14h; Length
0x1800440a2  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1800440a6  call    cs:__imp_NtQueryValueKey
0x1800440ad  nop     dword ptr [rax+rax+00h]
0x1800440b2  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800440b6  mov     ebx, eax
0x1800440b8  call    cs:__imp_NtClose
0x1800440bf  nop     dword ptr [rax+rax+00h]
0x1800440c4  test    ebx, ebx
0x1800440c6  js      short loc_1800440D8
0x1800440c8  cmp     [rbp+57h+var_1C], 4
0x1800440cc  jnz     short loc_1800440D8
0x1800440ce  mov     eax, [rbp+57h+var_14]
0x1800440d1  neg     eax
0x1800440d3  sbb     edi, edi
0x1800440d5  add     edi, 2
0x1800440d8  mov     eax, edi
0x1800440da  mov     rcx, [rbp+57h+var_8]
0x1800440de  xor     rcx, rsp; StackCookie
0x1800440e1  call    __security_check_cookie
0x1800440e6  lea     r11, [rsp+0B0h+var_s0]
0x1800440ee  mov     rbx, [r11+10h]
0x1800440f2  mov     rdi, [r11+18h]
0x1800440f6  mov     rsp, r11
0x1800440f9  pop     rbp
0x1800440fa  retn
```
