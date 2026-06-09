# HsmpCheckUpperInstanceRegNeeded

- ea: `0x140014950`
- end: `0x140014b01`
- name: `HsmpCheckUpperInstanceRegNeeded`
- size: `433`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140087490`

## callees

- `0x140014950`
- `0x14001e140`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400149cd`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400149f9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400149cd`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400149f9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400149e1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400149e1`
- `ntoskrnl!ZwQueryValueKey` at `0x140014a8e`
- `ntoskrnl!ZwQueryValueKey` at `0x140014a8e`
- `ntoskrnl!ZwOpenKey` at `0x140014a40`
- `ntoskrnl!ZwOpenKey` at `0x140014a40`
- `ntoskrnl!ZwClose` at `0x140014ace`
- `ntoskrnl!ZwClose` at `0x140014ace`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014a5d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014a5d`

## string_xrefs

- `0x14001498c`: `\Registry\Machine\System\CurrentControlSet\Services\`

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
0x140014950  mov     [rsp-8+arg_10], rbx
0x140014955  mov     [rsp-8+arg_18], rdi
0x14001495a  push    rbp
0x14001495b  lea     rbp, [rsp-0F0h]
0x140014963  sub     rsp, 1F0h
0x14001496a  mov     rax, cs:__security_cookie
0x140014971  xor     rax, rsp
0x140014974  mov     [rbp+0F0h+var_10], rax
0x14001497b  xorps   xmm0, xmm0
0x14001497e  xor     eax, eax
0x140014980  mov     [rsp+1F0h+KeyHandle], rax
0x140014985  mov     rdi, rdx
0x140014988  mov     [rsp+1F0h+var_1C0], eax
0x14001498c  lea     rdx, Source; "\\Registry\\Machine\\System\\CurrentCon"...
0x140014993  movups  xmmword ptr [rsp+1F0h+Destination.Length], xmm0
0x140014998  mov     eax, 140h
0x14001499d  mov     rbx, rcx
0x1400149a0  mov     [rsp+1F0h+Destination.MaximumLength], ax
0x1400149a5  lea     rcx, [rsp+1F0h+Destination]; Destination
0x1400149aa  lea     rax, [rbp+0F0h+var_150]
0x1400149ae  xorps   xmm1, xmm1
0x1400149b1  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.ObjectName], xmm0
0x1400149b6  mov     [rsp+1F0h+Destination.Buffer], rax
0x1400149bb  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.Length], xmm0
0x1400149c0  movups  xmmword ptr [rsp+1F0h+ObjectAttributes+1Ch], xmm0
0x1400149c5  movups  xmmword ptr [rbp+0F0h+DestinationString.Length], xmm0
0x1400149c9  movups  [rbp+0F0h+KeyValueInformation], xmm1
0x1400149cd  call    cs:__imp_RtlAppendUnicodeToString
0x1400149d4  nop     dword ptr [rax+rax+00h]
0x1400149d9  mov     rdx, rbx; Source
0x1400149dc  lea     rcx, [rsp+1F0h+Destination]; Destination
0x1400149e1  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400149e8  nop     dword ptr [rax+rax+00h]
0x1400149ed  lea     rdx, aParameters; "\\Parameters"
0x1400149f4  lea     rcx, [rsp+1F0h+Destination]; Destination
0x1400149f9  call    cs:__imp_RtlAppendUnicodeToString
0x140014a00  nop     dword ptr [rax+rax+00h]
0x140014a05  lea     rax, [rsp+1F0h+Destination]
0x140014a0a  mov     [rsp+1F0h+ObjectAttributes.Length], 30h ; '0'
0x140014a12  xorps   xmm0, xmm0
0x140014a15  mov     [rsp+1F0h+ObjectAttributes.ObjectName], rax
0x140014a1a  lea     r8, [rsp+1F0h+ObjectAttributes]; ObjectAttributes
0x140014a1f  mov     [rsp+1F0h+ObjectAttributes.RootDirectory], 0
0x140014a28  mov     edx, 20019h; DesiredAccess
0x140014a2d  mov     [rsp+1F0h+ObjectAttributes.Attributes], 240h
0x140014a35  lea     rcx, [rsp+1F0h+KeyHandle]; KeyHandle
0x140014a3a  movdqu  xmmword ptr [rsp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140014a40  call    cs:__imp_ZwOpenKey
0x140014a47  nop     dword ptr [rax+rax+00h]
0x140014a4c  mov     ebx, eax
0x140014a4e  test    eax, eax
0x140014a50  js      short loc_140014AC4
0x140014a52  lea     rdx, SourceString; "DoNotRegisterUpperInstance"
0x140014a59  lea     rcx, [rbp+0F0h+DestinationString]; DestinationString
0x140014a5d  call    cs:__imp_RtlInitUnicodeString
0x140014a64  nop     dword ptr [rax+rax+00h]
0x140014a69  mov     rcx, [rsp+1F0h+KeyHandle]; KeyHandle
0x140014a6e  lea     rax, [rsp+1F0h+var_1C0]
0x140014a73  mov     [rsp+1F0h+ResultLength], rax; ResultLength
0x140014a78  lea     r9, [rbp+0F0h+KeyValueInformation]; KeyValueInformation
0x140014a7c  mov     r8d, 2; KeyValueInformationClass
0x140014a82  mov     [rsp+1F0h+Length], 10h; Length
0x140014a8a  lea     rdx, [rbp+0F0h+DestinationString]; ValueName
0x140014a8e  call    cs:__imp_ZwQueryValueKey
0x140014a95  nop     dword ptr [rax+rax+00h]
0x140014a9a  mov     ebx, eax
0x140014a9c  cmp     eax, 0C0000034h
0x140014aa1  jnz     short loc_140014AAA
0x140014aa3  mov     byte ptr [rdi], 1
0x140014aa6  xor     ebx, ebx
0x140014aa8  jmp     short loc_140014AC4
0x140014aaa  test    eax, eax
0x140014aac  js      short loc_140014AC4
0x140014aae  cmp     dword ptr [rbp+0F0h+KeyValueInformation+4], 4
0x140014ab2  jz      short loc_140014ABB
0x140014ab4  mov     ebx, 0C0000024h
0x140014ab9  jmp     short loc_140014AC4
0x140014abb  cmp     dword ptr [rbp+0F0h+KeyValueInformation+0Ch], 0
0x140014abf  setz    al
0x140014ac2  mov     [rdi], al
0x140014ac4  mov     rcx, [rsp+1F0h+KeyHandle]; Handle
0x140014ac9  test    rcx, rcx
0x140014acc  jz      short loc_140014ADA
0x140014ace  call    cs:__imp_ZwClose
0x140014ad5  nop     dword ptr [rax+rax+00h]
0x140014ada  mov     eax, ebx
0x140014adc  mov     rcx, [rbp+0F0h+var_10]
0x140014ae3  xor     rcx, rsp; StackCookie
0x140014ae6  call    __security_check_cookie
0x140014aeb  lea     r11, [rsp+1F0h+var_s0]
0x140014af3  mov     rbx, [r11+20h]
0x140014af7  mov     rdi, [r11+28h]
0x140014afb  mov     rsp, r11
0x140014afe  pop     rbp
0x140014aff  retn
```
