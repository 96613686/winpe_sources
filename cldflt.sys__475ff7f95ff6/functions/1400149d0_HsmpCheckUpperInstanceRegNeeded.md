# HsmpCheckUpperInstanceRegNeeded

- ea: `0x1400149d0`
- end: `0x140014b81`
- name: `HsmpCheckUpperInstanceRegNeeded`
- size: `433`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140087490`

## callees

- `0x1400149d0`
- `0x14001e1c0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140014a4d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140014a79`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140014a4d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140014a79`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140014a61`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140014a61`
- `ntoskrnl!ZwQueryValueKey` at `0x140014b0e`
- `ntoskrnl!ZwQueryValueKey` at `0x140014b0e`
- `ntoskrnl!ZwOpenKey` at `0x140014ac0`
- `ntoskrnl!ZwOpenKey` at `0x140014ac0`
- `ntoskrnl!ZwClose` at `0x140014b4e`
- `ntoskrnl!ZwClose` at `0x140014b4e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014add`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014add`

## string_xrefs

- `0x140014a0c`: `\Registry\Machine\System\CurrentControlSet\Services\`

## pseudocode

```c
__int64 __fastcall HsmpCheckUpperInstanceRegNeeded(PCUNICODE_STRING Source, bool *a2)
{
  NTSTATUS v4; // ebx
  NTSTATUS v5; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp-70h] BYREF
  char v13; // [rsp+A0h] [rbp-60h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  *(_QWORD *)&Destination.Length = 20971520;
  Destination.Buffer = (PWSTR)&v13;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  KeyValueInformation = 0;
  RtlAppendUnicodeToString(&Destination, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\");
  RtlAppendUnicodeStringToString(&Destination, Source);
  RtlAppendUnicodeToString(&Destination, L"\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v4 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"DoNotRegisterUpperInstance");
    v5 = ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x10u,
           &ResultLength);
    v4 = v5;
    if ( v5 == -1073741772 )
    {
      *a2 = 1;
      v4 = 0;
    }
    else if ( v5 >= 0 )
    {
      if ( DWORD1(KeyValueInformation) == 4 )
        *a2 = HIDWORD(KeyValueInformation) == 0;
      else
        v4 = -1073741788;
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400149d0  mov     [rsp-8+arg_10], rbx
0x1400149d5  mov     [rsp-8+arg_18], rdi
0x1400149da  push    rbp
0x1400149db  lea     rbp, [rsp-0F0h]
0x1400149e3  sub     rsp, 1F0h
0x1400149ea  mov     rax, cs:__security_cookie
0x1400149f1  xor     rax, rsp
0x1400149f4  mov     [rbp+0F0h+var_10], rax
0x1400149fb  xorps   xmm0, xmm0
0x1400149fe  xor     eax, eax
0x140014a00  mov     [rsp+1F0h+KeyHandle], rax
0x140014a05  mov     rdi, rdx
0x140014a08  mov     [rsp+1F0h+var_1C0], eax
0x140014a0c  lea     rdx, Source; "\\Registry\\Machine\\System\\CurrentCon"...
0x140014a13  movups  xmmword ptr [rsp+1F0h+Destination.Length], xmm0
0x140014a18  mov     eax, 140h
0x140014a1d  mov     rbx, rcx
0x140014a20  mov     [rsp+1F0h+Destination.MaximumLength], ax
0x140014a25  lea     rcx, [rsp+1F0h+Destination]; Destination
0x140014a2a  lea     rax, [rbp+0F0h+var_150]
0x140014a2e  xorps   xmm1, xmm1
0x140014a31  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.ObjectName], xmm0
0x140014a36  mov     [rsp+1F0h+Destination.Buffer], rax
0x140014a3b  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.Length], xmm0
0x140014a40  movups  xmmword ptr [rsp+1F0h+ObjectAttributes+1Ch], xmm0
0x140014a45  movups  xmmword ptr [rbp+0F0h+DestinationString.Length], xmm0
0x140014a49  movups  [rbp+0F0h+KeyValueInformation], xmm1
0x140014a4d  call    cs:__imp_RtlAppendUnicodeToString
0x140014a54  nop     dword ptr [rax+rax+00h]
0x140014a59  mov     rdx, rbx; Source
0x140014a5c  lea     rcx, [rsp+1F0h+Destination]; Destination
0x140014a61  call    cs:__imp_RtlAppendUnicodeStringToString
0x140014a68  nop     dword ptr [rax+rax+00h]
0x140014a6d  lea     rdx, aParameters; "\\Parameters"
0x140014a74  lea     rcx, [rsp+1F0h+Destination]; Destination
0x140014a79  call    cs:__imp_RtlAppendUnicodeToString
0x140014a80  nop     dword ptr [rax+rax+00h]
0x140014a85  lea     rax, [rsp+1F0h+Destination]
0x140014a8a  mov     [rsp+1F0h+ObjectAttributes.Length], 30h ; '0'
0x140014a92  xorps   xmm0, xmm0
0x140014a95  mov     [rsp+1F0h+ObjectAttributes.ObjectName], rax
0x140014a9a  lea     r8, [rsp+1F0h+ObjectAttributes]; ObjectAttributes
0x140014a9f  mov     [rsp+1F0h+ObjectAttributes.RootDirectory], 0
0x140014aa8  mov     edx, 20019h; DesiredAccess
0x140014aad  mov     [rsp+1F0h+ObjectAttributes.Attributes], 240h
0x140014ab5  lea     rcx, [rsp+1F0h+KeyHandle]; KeyHandle
0x140014aba  movdqu  xmmword ptr [rsp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140014ac0  call    cs:__imp_ZwOpenKey
0x140014ac7  nop     dword ptr [rax+rax+00h]
0x140014acc  mov     ebx, eax
0x140014ace  test    eax, eax
0x140014ad0  js      short loc_140014B44
0x140014ad2  lea     rdx, SourceString; "DoNotRegisterUpperInstance"
0x140014ad9  lea     rcx, [rbp+0F0h+DestinationString]; DestinationString
0x140014add  call    cs:__imp_RtlInitUnicodeString
0x140014ae4  nop     dword ptr [rax+rax+00h]
0x140014ae9  mov     rcx, [rsp+1F0h+KeyHandle]; KeyHandle
0x140014aee  lea     rax, [rsp+1F0h+var_1C0]
0x140014af3  mov     [rsp+1F0h+ResultLength], rax; ResultLength
0x140014af8  lea     r9, [rbp+0F0h+KeyValueInformation]; KeyValueInformation
0x140014afc  mov     r8d, 2; KeyValueInformationClass
0x140014b02  mov     [rsp+1F0h+Length], 10h; Length
0x140014b0a  lea     rdx, [rbp+0F0h+DestinationString]; ValueName
0x140014b0e  call    cs:__imp_ZwQueryValueKey
0x140014b15  nop     dword ptr [rax+rax+00h]
0x140014b1a  mov     ebx, eax
0x140014b1c  cmp     eax, 0C0000034h
0x140014b21  jnz     short loc_140014B2A
0x140014b23  mov     byte ptr [rdi], 1
0x140014b26  xor     ebx, ebx
0x140014b28  jmp     short loc_140014B44
0x140014b2a  test    eax, eax
0x140014b2c  js      short loc_140014B44
0x140014b2e  cmp     dword ptr [rbp+0F0h+KeyValueInformation+4], 4
0x140014b32  jz      short loc_140014B3B
0x140014b34  mov     ebx, 0C0000024h
0x140014b39  jmp     short loc_140014B44
0x140014b3b  cmp     dword ptr [rbp+0F0h+KeyValueInformation+0Ch], 0
0x140014b3f  setz    al
0x140014b42  mov     [rdi], al
0x140014b44  mov     rcx, [rsp+1F0h+KeyHandle]; Handle
0x140014b49  test    rcx, rcx
0x140014b4c  jz      short loc_140014B5A
0x140014b4e  call    cs:__imp_ZwClose
0x140014b55  nop     dword ptr [rax+rax+00h]
0x140014b5a  mov     eax, ebx
0x140014b5c  mov     rcx, [rbp+0F0h+var_10]
0x140014b63  xor     rcx, rsp; StackCookie
0x140014b66  call    __security_check_cookie
0x140014b6b  lea     r11, [rsp+1F0h+var_s0]
0x140014b73  mov     rbx, [r11+20h]
0x140014b77  mov     rdi, [r11+28h]
0x140014b7b  mov     rsp, r11
0x140014b7e  pop     rbp
0x140014b7f  retn
```
