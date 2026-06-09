# IsRegistryOverrideSet

- ea: `0x14000a8d4`
- end: `0x14000aa8a`
- name: `IsRegistryOverrideSet`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000a8b0`

## callees

- `0x14000a8d4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000a922`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a939`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a922`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a939`
- `ntoskrnl!ZwOpenKey` at `0x14000a978`
- `ntoskrnl!ZwOpenKey` at `0x14000a978`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a9ae`
- `ntoskrnl!ZwQueryValueKey` at `0x14000aa1d`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a9ae`
- `ntoskrnl!ZwQueryValueKey` at `0x14000aa1d`
- `ntoskrnl!ZwClose` at `0x14000aa68`
- `ntoskrnl!ZwClose` at `0x14000aa68`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa53`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa53`
- `ntoskrnl!ExAllocatePool2` at `0x14000a9e1`
- `ntoskrnl!ExAllocatePool2` at `0x14000a9e1`

## string_xrefs

- `0x14000a90b`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\EFS\Overrides`

## pseudocode

```c
__int64 __fastcall IsRegistryOverrideSet(__int64 a1, bool *a2)
{
  NTSTATUS v3; // ebx
  _DWORD *Pool2; // rdi
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+20h] BYREF
  int v10; // [rsp+A4h] [rbp+24h]
  void *KeyHandle; // [rsp+A8h] [rbp+28h] BYREF

  v10 = HIDWORD(a1);
  KeyHandle = 0;
  *a2 = 0;
  ResultLength = 0;
  DestinationString = 0;
  ValueName = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\EFS\\Overrides");
  RtlInitUnicodeString(&ValueName, L"NoCryptoOffload");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v3 >= 0 )
  {
    v3 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( (int)(v3 + 0x80000000) < 0 || v3 == -1073741789 )
    {
      Pool2 = (_DWORD *)ExAllocatePool2(256, ResultLength, 1163154260);
      if ( Pool2 )
      {
        v3 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Pool2, ResultLength, &ResultLength);
        if ( v3 >= 0 )
        {
          if ( Pool2[1] == 4 && Pool2[2] == 4 )
            *a2 = Pool2[3] != 0;
          else
            v3 = -1073741788;
        }
        ExFreePoolWithTag(Pool2, 0x45545354u);
      }
      else
      {
        v3 = -1073741670;
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000a8d4  mov     [rsp-18h+arg_10], rbx
0x14000a8d9  mov     qword ptr [rsp-18h+arg_0], rcx
0x14000a8de  push    rbp
0x14000a8df  push    rsi
0x14000a8e0  push    rdi
0x14000a8e1  mov     rbp, rsp
0x14000a8e4  sub     rsp, 80h
0x14000a8eb  xorps   xmm0, xmm0
0x14000a8ee  mov     [rbp+KeyHandle], 0
0x14000a8f6  xor     eax, eax
0x14000a8f8  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a8fc  mov     [rdx], al
0x14000a8fe  mov     rsi, rdx
0x14000a901  xorps   xmm1, xmm1
0x14000a904  mov     [rbp+arg_0], eax
0x14000a907  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000a90b  lea     rdx, SourceString; "\\Registry\\Machine\\Software\\Microsof"...
0x14000a912  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000a916  movups  xmmword ptr [rbp+ValueName.Length], xmm1
0x14000a91a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000a91e  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000a922  call    cs:__imp_RtlInitUnicodeString
0x14000a929  nop     dword ptr [rax+rax+00h]
0x14000a92e  lea     rdx, aNocryptooffloa; "NoCryptoOffload"
0x14000a935  lea     rcx, [rbp+ValueName]; DestinationString
0x14000a939  call    cs:__imp_RtlInitUnicodeString
0x14000a940  nop     dword ptr [rax+rax+00h]
0x14000a945  lea     rax, [rbp+DestinationString]
0x14000a949  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000a950  xorps   xmm0, xmm0
0x14000a953  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000a957  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000a95b  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000a963  mov     edx, 20019h; DesiredAccess
0x14000a968  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14000a96f  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000a973  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000a978  call    cs:__imp_ZwOpenKey
0x14000a97f  nop     dword ptr [rax+rax+00h]
0x14000a984  mov     ebx, eax
0x14000a986  test    eax, eax
0x14000a988  js      loc_14000AA5F
0x14000a98e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000a992  lea     rax, [rbp+arg_0]
0x14000a996  xor     r9d, r9d; KeyValueInformation
0x14000a999  mov     [rsp+80h+ResultLength], rax; ResultLength
0x14000a99e  lea     rdx, [rbp+ValueName]; ValueName
0x14000a9a2  mov     [rsp+80h+Length], 0; Length
0x14000a9aa  lea     r8d, [r9+2]; KeyValueInformationClass
0x14000a9ae  call    cs:__imp_ZwQueryValueKey
0x14000a9b5  nop     dword ptr [rax+rax+00h]
0x14000a9ba  mov     ecx, 80000000h
0x14000a9bf  mov     ebx, eax
0x14000a9c1  add     eax, ecx
0x14000a9c3  test    ecx, eax
0x14000a9c5  jnz     short loc_14000A9D3
0x14000a9c7  cmp     ebx, 0C0000023h
0x14000a9cd  jnz     loc_14000AA5F
0x14000a9d3  mov     edx, [rbp+arg_0]
0x14000a9d6  mov     ecx, 100h
0x14000a9db  mov     r8d, 45545354h
0x14000a9e1  call    cs:__imp_ExAllocatePool2
0x14000a9e8  nop     dword ptr [rax+rax+00h]
0x14000a9ed  mov     rdi, rax
0x14000a9f0  test    rax, rax
0x14000a9f3  jnz     short loc_14000A9FC
0x14000a9f5  mov     ebx, 0C000009Ah
0x14000a9fa  jmp     short loc_14000AA5F
0x14000a9fc  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000aa00  lea     rax, [rbp+arg_0]
0x14000aa04  mov     [rsp+80h+ResultLength], rax; ResultLength
0x14000aa09  lea     rdx, [rbp+ValueName]; ValueName
0x14000aa0d  mov     eax, [rbp+arg_0]
0x14000aa10  mov     r9, rdi; KeyValueInformation
0x14000aa13  mov     r8d, 2; KeyValueInformationClass
0x14000aa19  mov     [rsp+80h+Length], eax; Length
0x14000aa1d  call    cs:__imp_ZwQueryValueKey
0x14000aa24  nop     dword ptr [rax+rax+00h]
0x14000aa29  mov     ebx, eax
0x14000aa2b  test    eax, eax
0x14000aa2d  js      short loc_14000AA4B
0x14000aa2f  cmp     dword ptr [rdi+4], 4
0x14000aa33  jnz     short loc_14000AA46
0x14000aa35  cmp     dword ptr [rdi+8], 4
0x14000aa39  jnz     short loc_14000AA46
0x14000aa3b  cmp     dword ptr [rdi+0Ch], 0
0x14000aa3f  setnz   al
0x14000aa42  mov     [rsi], al
0x14000aa44  jmp     short loc_14000AA4B
0x14000aa46  mov     ebx, 0C0000024h
0x14000aa4b  mov     edx, 45545354h; Tag
0x14000aa50  mov     rcx, rdi; P
0x14000aa53  call    cs:__imp_ExFreePoolWithTag
0x14000aa5a  nop     dword ptr [rax+rax+00h]
0x14000aa5f  mov     rcx, [rbp+KeyHandle]; Handle
0x14000aa63  test    rcx, rcx
0x14000aa66  jz      short loc_14000AA74
0x14000aa68  call    cs:__imp_ZwClose
0x14000aa6f  nop     dword ptr [rax+rax+00h]
0x14000aa74  mov     eax, ebx
0x14000aa76  mov     rbx, [rsp+80h+arg_10]
0x14000aa7e  add     rsp, 80h
0x14000aa85  pop     rdi
0x14000aa86  pop     rsi
0x14000aa87  pop     rbp
0x14000aa88  retn
```
