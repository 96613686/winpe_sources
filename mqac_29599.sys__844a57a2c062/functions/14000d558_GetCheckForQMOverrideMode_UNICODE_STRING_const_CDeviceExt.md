# GetCheckForQMOverrideMode(_UNICODE_STRING const *,CDeviceExt *)

- ea: `0x14000d558`
- end: `0x14000d67c`
- name: `?GetCheckForQMOverrideMode@@YAXPEBU_UNICODE_STRING@@PEAUCDeviceExt@@@Z`
- size: `292`
- prototype: `void __fastcall(const struct _UNICODE_STRING *, struct CDeviceExt *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000cef8`

## callees

- `0x14000d558`
- `0x140024bb0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000d5e6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d5e6`
- `ntoskrnl!ZwOpenKey` at `0x14000d5c0`
- `ntoskrnl!ZwOpenKey` at `0x14000d5c0`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d61c`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d61c`
- `ntoskrnl!ZwClose` at `0x14000d62e`
- `ntoskrnl!ZwClose` at `0x14000d62e`

## pseudocode

```c
void __fastcall GetCheckForQMOverrideMode(const struct _UNICODE_STRING *a1, struct CDeviceExt *a2)
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
    RtlInitUnicodeString(&DestinationString, L"CheckQMProcess");
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
        *((_DWORD *)a2 + 247) = 1;
    }
  }
}

```

## disassembly

```asm
0x14000d558  mov     [rsp-8+arg_0], rbx
0x14000d55d  mov     [rsp-8+arg_10], rdi
0x14000d562  push    rbp
0x14000d563  lea     rbp, [rsp-57h]
0x14000d568  sub     rsp, 0A0h
0x14000d56f  mov     rax, cs:__security_cookie
0x14000d576  xor     rax, rsp
0x14000d579  mov     [rbp+57h+var_8], rax
0x14000d57d  mov     rdi, rdx
0x14000d580  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000d588  lea     rax, ?g_RegistryPath@@3U_UNICODE_STRING@@A; _UNICODE_STRING g_RegistryPath
0x14000d58f  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000d597  xorps   xmm0, xmm0
0x14000d59a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000d59e  mov     edx, 1; DesiredAccess
0x14000d5a3  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14000d5ab  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000d5af  mov     [rbp+57h+KeyHandle], 0
0x14000d5b7  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d5bb  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000d5c0  call    cs:__imp_ZwOpenKey
0x14000d5c7  nop     dword ptr [rax+rax+00h]
0x14000d5cc  test    eax, eax
0x14000d5ce  js      loc_14000D65A
0x14000d5d4  xorps   xmm0, xmm0
0x14000d5d7  lea     rdx, aCheckqmprocess; "CheckQMProcess"
0x14000d5de  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000d5e2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000d5e6  call    cs:__imp_RtlInitUnicodeString
0x14000d5ed  nop     dword ptr [rax+rax+00h]
0x14000d5f2  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d5f6  lea     rax, [rbp+57h+var_70]
0x14000d5fa  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x14000d5ff  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000d603  mov     r8d, 2; KeyValueInformationClass
0x14000d609  mov     [rsp+0A0h+Length], 14h; Length
0x14000d611  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14000d615  mov     [rbp+57h+var_70], 0
0x14000d61c  call    cs:__imp_ZwQueryValueKey
0x14000d623  nop     dword ptr [rax+rax+00h]
0x14000d628  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14000d62c  mov     ebx, eax
0x14000d62e  call    cs:__imp_ZwClose
0x14000d635  nop     dword ptr [rax+rax+00h]
0x14000d63a  test    ebx, ebx
0x14000d63c  js      short loc_14000D65A
0x14000d63e  cmp     [rbp+57h+var_1C], 4
0x14000d642  jnz     short loc_14000D65A
0x14000d644  cmp     [rbp+57h+var_18], 4
0x14000d648  jnz     short loc_14000D65A
0x14000d64a  cmp     [rbp+57h+var_14], 0
0x14000d64e  jz      short loc_14000D65A
0x14000d650  mov     dword ptr [rdi+3DCh], 1
0x14000d65a  mov     rcx, [rbp+57h+var_8]
0x14000d65e  xor     rcx, rsp; StackCookie
0x14000d661  call    __security_check_cookie
0x14000d666  lea     r11, [rsp+0A0h+var_s0]
0x14000d66e  mov     rbx, [r11+10h]
0x14000d672  mov     rdi, [r11+20h]
0x14000d676  mov     rsp, r11
0x14000d679  pop     rbp
0x14000d67a  retn
```
