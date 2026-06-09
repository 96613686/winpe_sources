# GetCheckForClearDriverPacket(_UNICODE_STRING const *,CDeviceExt *)

- ea: `0x14000d42c`
- end: `0x14000d550`
- name: `?GetCheckForClearDriverPacket@@YAXPEBU_UNICODE_STRING@@PEAUCDeviceExt@@@Z`
- size: `292`
- prototype: `void __fastcall(const struct _UNICODE_STRING *, struct CDeviceExt *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000cef8`

## callees

- `0x14000d42c`
- `0x140024bb0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000d4ba`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d4ba`
- `ntoskrnl!ZwOpenKey` at `0x14000d494`
- `ntoskrnl!ZwOpenKey` at `0x14000d494`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d4f0`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d4f0`
- `ntoskrnl!ZwClose` at `0x14000d502`
- `ntoskrnl!ZwClose` at `0x14000d502`

## pseudocode

```c
void __fastcall GetCheckForClearDriverPacket(const struct _UNICODE_STRING *a1, struct CDeviceExt *a2)
{
  NTSTATUS v3; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+80h] [rbp+37h] BYREF
  int v9; // [rsp+84h] [rbp+3Bh]
  int v10; // [rsp+88h] [rbp+3Fh]
  int v11; // [rsp+8Ch] [rbp+43h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &g_RegistryPath;
  ObjectAttributes.RootDirectory = 0;
  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"ClearDriverPacket");
    ResultLength = 0;
    v3 = ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x14u,
           &ResultLength);
    ZwClose(KeyHandle);
    if ( v3 >= 0 && v9 == 4 && v10 == 4 )
    {
      if ( v11 )
        *((_DWORD *)a2 + 248) = 1;
    }
  }
}

```

## disassembly

```asm
0x14000d42c  mov     [rsp-8+arg_0], rbx
0x14000d431  mov     [rsp-8+arg_10], rdi
0x14000d436  push    rbp
0x14000d437  lea     rbp, [rsp-57h]
0x14000d43c  sub     rsp, 0A0h
0x14000d443  mov     rax, cs:__security_cookie
0x14000d44a  xor     rax, rsp
0x14000d44d  mov     [rbp+57h+var_8], rax
0x14000d451  mov     rdi, rdx
0x14000d454  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000d45c  lea     rax, ?g_RegistryPath@@3U_UNICODE_STRING@@A; _UNICODE_STRING g_RegistryPath
0x14000d463  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000d46b  xorps   xmm0, xmm0
0x14000d46e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000d472  mov     edx, 1; DesiredAccess
0x14000d477  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14000d47f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000d483  mov     [rbp+57h+KeyHandle], 0
0x14000d48b  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d48f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000d494  call    cs:__imp_ZwOpenKey
0x14000d49b  nop     dword ptr [rax+rax+00h]
0x14000d4a0  test    eax, eax
0x14000d4a2  js      loc_14000D52E
0x14000d4a8  xorps   xmm0, xmm0
0x14000d4ab  lea     rdx, aCleardriverpac; "ClearDriverPacket"
0x14000d4b2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000d4b6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000d4ba  call    cs:__imp_RtlInitUnicodeString
0x14000d4c1  nop     dword ptr [rax+rax+00h]
0x14000d4c6  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d4ca  lea     rax, [rbp+57h+var_70]
0x14000d4ce  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x14000d4d3  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000d4d7  mov     r8d, 2; KeyValueInformationClass
0x14000d4dd  mov     [rsp+0A0h+Length], 14h; Length
0x14000d4e5  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14000d4e9  mov     [rbp+57h+var_70], 0
0x14000d4f0  call    cs:__imp_ZwQueryValueKey
0x14000d4f7  nop     dword ptr [rax+rax+00h]
0x14000d4fc  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14000d500  mov     ebx, eax
0x14000d502  call    cs:__imp_ZwClose
0x14000d509  nop     dword ptr [rax+rax+00h]
0x14000d50e  test    ebx, ebx
0x14000d510  js      short loc_14000D52E
0x14000d512  cmp     [rbp+57h+var_1C], 4
0x14000d516  jnz     short loc_14000D52E
0x14000d518  cmp     [rbp+57h+var_18], 4
0x14000d51c  jnz     short loc_14000D52E
0x14000d51e  cmp     [rbp+57h+var_14], 0
0x14000d522  jz      short loc_14000D52E
0x14000d524  mov     dword ptr [rdi+3E0h], 1
0x14000d52e  mov     rcx, [rbp+57h+var_8]
0x14000d532  xor     rcx, rsp; StackCookie
0x14000d535  call    __security_check_cookie
0x14000d53a  lea     r11, [rsp+0A0h+var_s0]
0x14000d542  mov     rbx, [r11+10h]
0x14000d546  mov     rdi, [r11+20h]
0x14000d54a  mov     rsp, r11
0x14000d54d  pop     rbp
0x14000d54e  retn
```
