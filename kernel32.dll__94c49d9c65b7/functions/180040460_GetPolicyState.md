# GetPolicyState

- ea: `0x180040460`
- end: `0x180040589`
- name: `GetPolicyState`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800402f0`

## callees

- `0x180040460`
- `0x18007a840`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180040540`
- `ntdll!NtQueryValueKey` at `0x180040540`
- `ntdll!NtOpenKey` at `0x180040515`
- `ntdll!NtOpenKey` at `0x180040515`
- `ntdll!NtClose` at `0x18004054c`
- `ntdll!NtClose` at `0x18004054c`
- `ntdll!RtlInitUnicodeString` at `0x1800404c2`
- `ntdll!RtlInitUnicodeString` at `0x1800404e0`
- `ntdll!RtlInitUnicodeString` at `0x1800404c2`
- `ntdll!RtlInitUnicodeString` at `0x1800404e0`

## string_xrefs

- `0x1800404c8`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\WOW`
- `0x1800404d1`: `\REGISTRY\MACHINE\Software\Policies\Microsoft\Windows\AppCompat`

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
0x180040460  mov     [rsp-8+arg_0], rbx
0x180040465  mov     [rsp-8+arg_8], rdi
0x18004046a  push    rbp
0x18004046b  lea     rbp, [rsp-57h]
0x180040470  sub     rsp, 0B0h
0x180040477  mov     rax, cs:__security_cookie
0x18004047e  xor     rax, rsp
0x180040481  mov     [rbp+57h+var_8], rax
0x180040485  xorps   xmm0, xmm0
0x180040488  lea     rax, aDisallowedpoli; "DisallowedPolicyDefault"
0x18004048f  xor     edi, edi
0x180040491  lea     rdx, aVdmdisallowed; "VDMDisallowed"
0x180040498  test    cl, cl
0x18004049a  mov     [rbp+57h+KeyHandle], rdi
0x18004049e  mov     bl, cl
0x1800404a0  mov     [rbp+57h+var_80], edi
0x1800404a3  xorps   xmm1, xmm1
0x1800404a6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800404aa  cmovz   rdx, rax; SourceString
0x1800404ae  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x1800404b2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1800404b6  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800404ba  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800404be  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800404c2  call    cs:__imp_RtlInitUnicodeString
0x1800404c8  lea     rax, aRegistryMachin_26; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x1800404cf  test    bl, bl
0x1800404d1  lea     rdx, aRegistryMachin_27; "\\REGISTRY\\MACHINE\\Software\\Policies"...
0x1800404d8  cmovz   rdx, rax; SourceString
0x1800404dc  lea     rcx, [rbp+57h+var_70]; DestinationString
0x1800404e0  call    cs:__imp_RtlInitUnicodeString
0x1800404e6  lea     rax, [rbp+57h+var_70]
0x1800404ea  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800404f1  xorps   xmm0, xmm0
0x1800404f4  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800404f8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800404fc  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180040500  mov     edx, 20019h; DesiredAccess
0x180040505  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18004050c  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180040510  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180040515  call    cs:__imp_NtOpenKey
0x18004051b  test    eax, eax
0x18004051d  js      short loc_180040566
0x18004051f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180040523  lea     rax, [rbp+57h+var_80]
0x180040527  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x18004052c  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180040530  lea     r8d, [rdi+2]; KeyValueInformationClass
0x180040534  mov     [rsp+0B0h+Length], 14h; Length
0x18004053c  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180040540  call    cs:__imp_NtQueryValueKey
0x180040546  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18004054a  mov     ebx, eax
0x18004054c  call    cs:__imp_NtClose
0x180040552  test    ebx, ebx
0x180040554  js      short loc_180040566
0x180040556  cmp     [rbp+57h+var_1C], 4
0x18004055a  jnz     short loc_180040566
0x18004055c  mov     eax, [rbp+57h+var_14]
0x18004055f  neg     eax
0x180040561  sbb     edi, edi
0x180040563  add     edi, 2
0x180040566  mov     eax, edi
0x180040568  mov     rcx, [rbp+57h+var_8]
0x18004056c  xor     rcx, rsp; StackCookie
0x18004056f  call    __security_check_cookie
0x180040574  lea     r11, [rsp+0B0h+var_s0]
0x18004057c  mov     rbx, [r11+10h]
0x180040580  mov     rdi, [r11+18h]
0x180040584  mov     rsp, r11
0x180040587  pop     rbp
0x180040588  retn
```
