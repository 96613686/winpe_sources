# FvepRegOpenKey

- ea: `0x140096ab8`
- end: `0x1400970dc`
- name: `FvepRegOpenKey`
- size: `1572`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14005e868`
- `0x14005ea90`
- `0x14005ecf4`
- `0x14005edb8`
- `0x14005f15c`
- `0x14005f410`
- `0x140096938`

## callees

- `0x140007da8`
- `0x14005efb4`
- `0x140096ab8`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140096cf5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140096d29`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140096cf5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140096d29`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140096d0a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140096d3f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140096d6d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140096da9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140096d0a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140096d3f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140096d6d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140096da9`
- `ntoskrnl!RtlStringFromGUID` at `0x140096d8a`
- `ntoskrnl!RtlStringFromGUID` at `0x140096d8a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140097073`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140097073`
- `ntoskrnl!ZwOpenKey` at `0x140096bd7`
- `ntoskrnl!ZwOpenKey` at `0x140096e01`
- `ntoskrnl!ZwOpenKey` at `0x140096bd7`
- `ntoskrnl!ZwOpenKey` at `0x140096e01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097089`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009709f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400970b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400970cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097089`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009709f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400970b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400970cb`
- `ntoskrnl!ZwClose` at `0x140096f63`
- `ntoskrnl!ZwClose` at `0x140097059`
- `ntoskrnl!ZwClose` at `0x140096f63`
- `ntoskrnl!ZwClose` at `0x140097059`
- `ntoskrnl!ExAllocatePool2` at `0x140096c96`
- `ntoskrnl!ExAllocatePool2` at `0x140096caf`
- `ntoskrnl!ExAllocatePool2` at `0x140096ea9`
- `ntoskrnl!ExAllocatePool2` at `0x140096c96`
- `ntoskrnl!ExAllocatePool2` at `0x140096caf`
- `ntoskrnl!ExAllocatePool2` at `0x140096ea9`
- `ntoskrnl!ZwQueryValueKey` at `0x140096c22`
- `ntoskrnl!ZwQueryValueKey` at `0x140096eeb`
- `ntoskrnl!ZwQueryValueKey` at `0x140096c22`
- `ntoskrnl!ZwQueryValueKey` at `0x140096eeb`
- `ntoskrnl!ZwCreateKey` at `0x140096fe3`
- `ntoskrnl!ZwCreateKey` at `0x14009703c`
- `ntoskrnl!ZwCreateKey` at `0x140096fe3`
- `ntoskrnl!ZwCreateKey` at `0x14009703c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140096b52`
- `ntoskrnl!RtlInitUnicodeString` at `0x140096b69`
- `ntoskrnl!RtlInitUnicodeString` at `0x140096b81`
- `ntoskrnl!RtlInitUnicodeString` at `0x140096b98`
- `ntoskrnl!RtlInitUnicodeString` at `0x140096bf8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140096b52`
- `ntoskrnl!RtlInitUnicodeString` at `0x140096b69`
- `ntoskrnl!RtlInitUnicodeString` at `0x140096b81`
- `ntoskrnl!RtlInitUnicodeString` at `0x140096b98`
- `ntoskrnl!RtlInitUnicodeString` at `0x140096bf8`

## string_xrefs

- `0x140096b5e`: `\Registry\Machine\System\CurrentControlSet\Control\FVEAutoUnlock`
- `0x140096b3e`: `\Registry\Machine\`

## pseudocode

```c
__int64 __fastcall FvepRegOpenKey(const GUID *a1, ACCESS_MASK a2, char a3, void **a4)
{
  int v4; // edi
  int v5; // r15d
  struct _ACL *v6; // r14
  wchar_t *v7; // r12
  wchar_t *v8; // r13
  __int64 Pool2; // rsi
  NTSTATUS v10; // eax
  NTSTATUS appended; // ebx
  NTSTATUS v12; // eax
  unsigned __int16 v13; // di
  NTSTATUS v14; // eax
  unsigned __int16 Length; // di
  int v17; // eax
  ULONG ResultLength[2]; // [rsp+48h] [rbp-C0h] BYREF
  void *Source; // [rsp+50h] [rbp-B8h] BYREF
  UNICODE_STRING Source_8; // [rsp+58h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v21; // [rsp+68h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes_8; // [rsp+78h] [rbp-90h] BYREF
  struct _ACL *v23; // [rsp+A8h] [rbp-60h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+B0h] [rbp-58h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+C0h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-38h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+E0h] [rbp-28h] BYREF
  struct _UNICODE_STRING v28; // [rsp+F0h] [rbp-18h] BYREF
  UNICODE_STRING v29; // [rsp+100h] [rbp-8h] BYREF

  v4 = 0;
  Source = 0;
  v23 = 0;
  v5 = a3 & 1;
  ResultLength[0] = 0;
  v6 = 0;
  GuidString = 0;
  Source_8 = 0;
  Destination = 0;
  v21 = 0;
  memset(&ObjectAttributes_8, 0, sizeof(ObjectAttributes_8));
  v29 = 0;
  DestinationString = 0;
  v28 = 0;
  ValueName = 0;
  if ( (a3 & 2) == 0 )
  {
    if ( (a3 & 1) != 0 )
      goto LABEL_3;
    return (unsigned int)-1073741811;
  }
  if ( (a3 & 1) != 0 )
    return (unsigned int)-1073741811;
LABEL_3:
  v7 = 0;
  v8 = 0;
  Pool2 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\");
  RtlInitUnicodeString(&v28, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FVEAutoUnlock");
  RtlInitUnicodeString(&Source_8, L"System\\CurrentControlSet\\Control\\FVEAutoUnlock");
  RtlInitUnicodeString(&v29, L"\\");
  ObjectAttributes_8.Length = 48;
  ObjectAttributes_8.ObjectName = &v28;
  ObjectAttributes_8.RootDirectory = 0;
  ObjectAttributes_8.Attributes = 576;
  *(_OWORD *)&ObjectAttributes_8.SecurityDescriptor = 0;
  v10 = ZwOpenKey(&Source, 0x20019u, &ObjectAttributes_8);
  appended = v10;
  if ( v10 < 0 )
  {
    if ( v10 != -1073741772 )
      goto LABEL_38;
    goto LABEL_42;
  }
  RtlInitUnicodeString(&ValueName, L"DriverAutoUnlockRedirectionKey");
  v12 = ZwQueryValueKey(Source, &ValueName, KeyValuePartialInformation, 0, 0, ResultLength);
  appended = v12;
  if ( v12 == -1073741772 )
  {
LABEL_42:
    Length = Source_8.Length;
    goto LABEL_9;
  }
  if ( v12 != -2147483643 && v12 != -1073741789 )
  {
    if ( v12 >= 0 )
      appended = -1073741823;
    goto LABEL_25;
  }
  Pool2 = ExAllocatePool2(256, ResultLength[0], 809850438);
  if ( !Pool2 )
  {
    appended = -1073741670;
    goto LABEL_25;
  }
  appended = ZwQueryValueKey(
               Source,
               &ValueName,
               KeyValuePartialInformation,
               (PVOID)Pool2,
               ResultLength[0],
               ResultLength);
  if ( appended < 0 )
    goto LABEL_38;
  appended = RtlULongToUShort(*(_DWORD *)(Pool2 + 8), &Source_8.Length);
  if ( appended < 0 )
    goto LABEL_38;
  Length = Source_8.Length;
  Source_8.MaximumLength = Source_8.Length;
  for ( Source_8.Buffer = (wchar_t *)(Pool2 + 12); Length >= 2u; Source_8.Length = Length )
  {
    if ( *(_WORD *)(Pool2 + 2 * ((unsigned __int64)Length >> 1) + 10) )
      break;
    Length -= 2;
  }
LABEL_9:
  if ( Source )
  {
    ZwClose(Source);
    Length = Source_8.Length;
    Source = 0;
  }
  v13 = Length + 136;
  if ( v13 < 0x88u )
  {
    appended = -1073741675;
    v4 = 0;
    goto LABEL_25;
  }
  v8 = (wchar_t *)ExAllocatePool2(256, v13, 809850438);
  v7 = (wchar_t *)ExAllocatePool2(256, v13, 809850438);
  if ( !v8 || !v7 )
  {
    appended = -1073741670;
    v4 = 0;
    goto LABEL_25;
  }
  Destination.Buffer = v7;
  Destination.MaximumLength = v13;
  Destination.Length = v13;
  v21.Buffer = v8;
  v21.MaximumLength = v13;
  v21.Length = v13;
  RtlCopyUnicodeString(&Destination, &DestinationString);
  appended = RtlAppendUnicodeStringToString(&Destination, &Source_8);
  if ( appended < 0 )
    goto LABEL_38;
  RtlCopyUnicodeString(&v21, &DestinationString);
  appended = RtlAppendUnicodeStringToString(&v21, &Source_8);
  if ( appended < 0 )
    goto LABEL_38;
  if ( !a1 )
  {
    v4 = 0;
    goto LABEL_21;
  }
  appended = RtlAppendUnicodeStringToString(&v21, &v29);
  if ( appended < 0
    || (appended = RtlStringFromGUID(a1, &GuidString), appended < 0)
    || (appended = RtlAppendUnicodeStringToString(&v21, &GuidString), appended < 0) )
  {
LABEL_38:
    v4 = 0;
    goto LABEL_25;
  }
  v4 = 1;
LABEL_21:
  if ( v5 )
  {
    ObjectAttributes_8.ObjectName = &v21;
    ObjectAttributes_8.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes_8.SecurityDescriptor = 0;
    ObjectAttributes_8.Length = 48;
    ObjectAttributes_8.Attributes = 576;
    v14 = ZwOpenKey(a4, a2, &ObjectAttributes_8);
  }
  else
  {
    v17 = FvepCreateSecurityDescriptor(&v23);
    v6 = v23;
    appended = v17;
    if ( v17 < 0 )
      goto LABEL_25;
    ObjectAttributes_8.ObjectName = &Destination;
    ObjectAttributes_8.Length = 48;
    ObjectAttributes_8.RootDirectory = 0;
    ObjectAttributes_8.Attributes = 576;
    ObjectAttributes_8.SecurityDescriptor = v23;
    ObjectAttributes_8.SecurityQualityOfService = 0;
    appended = ZwCreateKey(&Source, 4u, &ObjectAttributes_8, 0, 0, 0, 0);
    if ( appended < 0 )
      goto LABEL_25;
    ObjectAttributes_8.ObjectName = &v21;
    ObjectAttributes_8.Length = 48;
    ObjectAttributes_8.RootDirectory = 0;
    ObjectAttributes_8.Attributes = 576;
    ObjectAttributes_8.SecurityDescriptor = v6;
    ObjectAttributes_8.SecurityQualityOfService = 0;
    v14 = ZwCreateKey(a4, a2, &ObjectAttributes_8, 0, 0, 0, 0);
  }
  appended = v14;
LABEL_25:
  if ( Source )
  {
    ZwClose(Source);
    Source = 0;
  }
  if ( v4 )
    RtlFreeUnicodeString(&GuidString);
  if ( v6 )
    ExFreePoolWithTag(v6, 0x30455646u);
  if ( Pool2 )
    ExFreePoolWithTag((PVOID)Pool2, 0x30455646u);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x30455646u);
  if ( v7 )
    ExFreePoolWithTag(v7, 0x30455646u);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140096ab8  mov     rax, rsp
0x140096abb  mov     [rax+20h], r9
0x140096abf  mov     [rax+10h], edx
0x140096ac2  mov     [rax+8], rcx
0x140096ac6  push    rbp
0x140096ac7  push    rbx
0x140096ac8  push    rsi
0x140096ac9  push    rdi
0x140096aca  push    r12
0x140096acc  push    r13
0x140096ace  push    r14
0x140096ad0  push    r15
0x140096ad2  lea     rbp, [rax-58h]
0x140096ad6  sub     rsp, 118h
0x140096add  xorps   xmm0, xmm0
0x140096ae0  xor     edi, edi
0x140096ae2  xorps   xmm1, xmm1
0x140096ae5  mov     qword ptr [rsp+150h+Source.Length], rdi
0x140096aea  mov     r15d, r8d
0x140096aed  mov     [rbp+50h+var_B0], rdi
0x140096af1  and     r15d, 1
0x140096af5  mov     [rsp+150h+var_110], edi
0x140096af9  mov     r14d, edi
0x140096afc  movups  xmmword ptr [rbp+50h+GuidString.Length], xmm0
0x140096b00  movups  xmmword ptr [rsp+150h+Source.Buffer], xmm1
0x140096b05  movups  xmmword ptr [rbp+50h+Destination.Length], xmm0
0x140096b09  movups  xmmword ptr [rsp+150h+var_F8.Buffer], xmm1
0x140096b0e  movups  xmmword ptr [rsp+150h+ObjectAttributes+8], xmm0
0x140096b13  movups  xmmword ptr [rbp+50h+ObjectAttributes+18h], xmm0
0x140096b17  movups  xmmword ptr [rbp+50h+ObjectAttributes+28h], xmm0
0x140096b1b  movups  xmmword ptr [rbp+50h+var_58.Length], xmm0
0x140096b1f  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm1
0x140096b23  movups  xmmword ptr [rbp+50h+var_68.Length], xmm0
0x140096b27  movups  xmmword ptr [rbp+50h+ValueName.Length], xmm1
0x140096b2b  test    r8b, 2
0x140096b2f  jnz     loc_140096E77
0x140096b35  test    r15d, r15d
0x140096b38  jz      loc_140096E80
0x140096b3e  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\"
0x140096b45  mov     r12, rdi
0x140096b48  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140096b4c  mov     r13, rdi
0x140096b4f  mov     rsi, rdi
0x140096b52  call    cs:__imp_RtlInitUnicodeString
0x140096b59  nop     dword ptr [rax+rax+00h]
0x140096b5e  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x140096b65  lea     rcx, [rbp+50h+var_68]; DestinationString
0x140096b69  call    cs:__imp_RtlInitUnicodeString
0x140096b70  nop     dword ptr [rax+rax+00h]
0x140096b75  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\FVE"...
0x140096b7c  lea     rcx, [rsp+150h+Source.Buffer]; DestinationString
0x140096b81  call    cs:__imp_RtlInitUnicodeString
0x140096b88  nop     dword ptr [rax+rax+00h]
0x140096b8d  lea     rdx, Source; "\\"
0x140096b94  lea     rcx, [rbp+50h+var_58]; DestinationString
0x140096b98  call    cs:__imp_RtlInitUnicodeString
0x140096b9f  nop     dword ptr [rax+rax+00h]
0x140096ba4  lea     rax, [rbp+50h+var_68]
0x140096ba8  mov     dword ptr [rsp+150h+ObjectAttributes+8], 30h ; '0'
0x140096bb0  xorps   xmm0, xmm0
0x140096bb3  mov     qword ptr [rbp+50h+ObjectAttributes+18h], rax
0x140096bb7  lea     r8, [rsp+150h+ObjectAttributes+8]; ObjectAttributes
0x140096bbc  mov     qword ptr [rsp+150h+ObjectAttributes+10h], rdi
0x140096bc1  mov     edx, 20019h; DesiredAccess
0x140096bc6  mov     dword ptr [rbp+50h+ObjectAttributes+20h], 240h
0x140096bcd  lea     rcx, [rsp+150h+Source]; KeyHandle
0x140096bd2  movdqu  xmmword ptr [rbp+50h+ObjectAttributes+28h], xmm0
0x140096bd7  call    cs:__imp_ZwOpenKey
0x140096bde  nop     dword ptr [rax+rax+00h]
0x140096be3  mov     ebx, eax
0x140096be5  test    eax, eax
0x140096be7  js      loc_140096E87
0x140096bed  lea     rdx, aDriverautounlo; "DriverAutoUnlockRedirectionKey"
0x140096bf4  lea     rcx, [rbp+50h+ValueName]; DestinationString
0x140096bf8  call    cs:__imp_RtlInitUnicodeString
0x140096bff  nop     dword ptr [rax+rax+00h]
0x140096c04  mov     rcx, qword ptr [rsp+150h+Source.Length]; KeyHandle
0x140096c09  lea     rax, [rsp+150h+var_110]
0x140096c0e  xor     r9d, r9d; KeyValueInformation
0x140096c11  mov     [rsp+150h+ResultLength], rax; ResultLength
0x140096c16  lea     rdx, [rbp+50h+ValueName]; ValueName
0x140096c1a  mov     [rsp+150h+Length], edi; Length
0x140096c1e  lea     r8d, [r9+2]; KeyValueInformationClass
0x140096c22  call    cs:__imp_ZwQueryValueKey
0x140096c29  nop     dword ptr [rax+rax+00h]
0x140096c2e  mov     ebx, eax
0x140096c30  cmp     eax, 0C0000034h
0x140096c35  jz      loc_140096E8E
0x140096c3b  cmp     eax, 80000005h
0x140096c40  jz      loc_140096E9A
0x140096c46  cmp     eax, 0C0000023h
0x140096c4b  jz      loc_140096E9A
0x140096c51  xor     r15d, r15d
0x140096c54  test    eax, eax
0x140096c56  js      loc_140096E1C
0x140096c5c  mov     ebx, 0C0000001h
0x140096c61  jmp     loc_140096E1C
0x140096c66  mov     rcx, qword ptr [rsp+150h+Source.Length]; Handle
0x140096c6b  test    rcx, rcx
0x140096c6e  jnz     loc_140096F63
0x140096c74  mov     eax, 88h
0x140096c79  add     di, ax
0x140096c7c  cmp     di, ax
0x140096c7f  jb      loc_140096E11
0x140096c85  movzx   ebx, di
0x140096c88  lea     ecx, [rax+78h]
0x140096c8b  mov     r12d, 30455646h
0x140096c91  mov     edx, ebx
0x140096c93  mov     r8d, r12d
0x140096c96  call    cs:__imp_ExAllocatePool2
0x140096c9d  nop     dword ptr [rax+rax+00h]
0x140096ca2  mov     r8d, r12d
0x140096ca5  mov     edx, ebx
0x140096ca7  mov     ecx, 100h
0x140096cac  mov     r13, rax
0x140096caf  call    cs:__imp_ExAllocatePool2
0x140096cb6  nop     dword ptr [rax+rax+00h]
0x140096cbb  mov     r12, rax
0x140096cbe  xor     eax, eax
0x140096cc0  test    r13, r13
0x140096cc3  jz      loc_14009704D
0x140096cc9  test    r12, r12
0x140096ccc  jz      loc_14009704D
0x140096cd2  lea     rdx, [rbp+50h+DestinationString]; SourceString
0x140096cd6  mov     [rbp+50h+Destination.Buffer], r12
0x140096cda  lea     rcx, [rbp+50h+Destination]; DestinationString
0x140096cde  mov     [rbp+50h+Destination.MaximumLength], di
0x140096ce2  mov     [rbp+50h+Destination.Length], di
0x140096ce6  mov     qword ptr [rsp+150h+ObjectAttributes], r13
0x140096ceb  mov     word ptr [rsp+150h+var_F8.Buffer+2], di
0x140096cf0  mov     word ptr [rsp+150h+var_F8.Buffer], di
0x140096cf5  call    cs:__imp_RtlCopyUnicodeString
0x140096cfc  nop     dword ptr [rax+rax+00h]
0x140096d01  lea     rdx, [rsp+150h+Source.Buffer]; Source
0x140096d06  lea     rcx, [rbp+50h+Destination]; Destination
0x140096d0a  call    cs:__imp_RtlAppendUnicodeStringToString
0x140096d11  nop     dword ptr [rax+rax+00h]
0x140096d16  mov     ebx, eax
0x140096d18  test    eax, eax
0x140096d1a  js      loc_140096E72
0x140096d20  lea     rdx, [rbp+50h+DestinationString]; SourceString
0x140096d24  lea     rcx, [rsp+150h+var_F8.Buffer]; DestinationString
0x140096d29  call    cs:__imp_RtlCopyUnicodeString
0x140096d30  nop     dword ptr [rax+rax+00h]
0x140096d35  lea     rdx, [rsp+150h+Source.Buffer]; Source
0x140096d3a  lea     rcx, [rsp+150h+var_F8.Buffer]; Destination
0x140096d3f  call    cs:__imp_RtlAppendUnicodeStringToString
0x140096d46  nop     dword ptr [rax+rax+00h]
0x140096d4b  mov     ebx, eax
0x140096d4d  test    eax, eax
0x140096d4f  js      loc_140096E72
0x140096d55  mov     rdi, [rbp+50h+Guid]
0x140096d59  xor     ebx, ebx
0x140096d5b  test    rdi, rdi
0x140096d5e  jz      loc_140096F7E
0x140096d64  lea     rdx, [rbp+50h+var_58]; Source
0x140096d68  lea     rcx, [rsp+150h+var_F8.Buffer]; Destination
0x140096d6d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140096d74  nop     dword ptr [rax+rax+00h]
0x140096d79  mov     ebx, eax
0x140096d7b  test    eax, eax
0x140096d7d  js      loc_140096E72
0x140096d83  lea     rdx, [rbp+50h+GuidString]; GuidString
0x140096d87  mov     rcx, rdi; Guid
0x140096d8a  call    cs:__imp_RtlStringFromGUID
0x140096d91  nop     dword ptr [rax+rax+00h]
0x140096d96  mov     ebx, eax
0x140096d98  test    eax, eax
0x140096d9a  js      loc_140096E72
0x140096da0  lea     rdx, [rbp+50h+GuidString]; Source
0x140096da4  lea     rcx, [rsp+150h+var_F8.Buffer]; Destination
0x140096da9  call    cs:__imp_RtlAppendUnicodeStringToString
0x140096db0  nop     dword ptr [rax+rax+00h]
0x140096db5  mov     ebx, eax
0x140096db7  test    eax, eax
0x140096db9  js      loc_140096E72
0x140096dbf  mov     edi, 1
0x140096dc4  test    r15d, r15d
0x140096dc7  jz      loc_140096F85
0x140096dcd  mov     edx, [rbp+50h+DesiredAccess]; DesiredAccess
0x140096dd0  lea     rax, [rsp+150h+var_F8.Buffer]
0x140096dd5  mov     rcx, [rbp+50h+KeyHandle]; KeyHandle
0x140096dd9  lea     r8, [rsp+150h+ObjectAttributes+8]; ObjectAttributes
0x140096dde  xor     r15d, r15d
0x140096de1  mov     qword ptr [rbp+50h+ObjectAttributes+18h], rax
0x140096de5  xorps   xmm0, xmm0
0x140096de8  mov     qword ptr [rsp+150h+ObjectAttributes+10h], r15
0x140096ded  movdqu  xmmword ptr [rbp+50h+ObjectAttributes+28h], xmm0
0x140096df2  mov     dword ptr [rsp+150h+ObjectAttributes+8], 30h ; '0'
0x140096dfa  mov     dword ptr [rbp+50h+ObjectAttributes+20h], 240h
0x140096e01  call    cs:__imp_ZwOpenKey
0x140096e08  nop     dword ptr [rax+rax+00h]
0x140096e0d  mov     ebx, eax
0x140096e0f  jmp     short loc_140096E1C
0x140096e11  mov     ebx, 0C0000095h
0x140096e16  mov     edi, r12d
0x140096e19  xor     r15d, r15d
0x140096e1c  mov     rcx, qword ptr [rsp+150h+Source.Length]; Handle
0x140096e21  test    rcx, rcx
0x140096e24  jnz     loc_140097059
0x140096e2a  test    edi, edi
0x140096e2c  jnz     loc_14009706F
0x140096e32  mov     edi, 30455646h
0x140096e37  test    r14, r14
0x140096e3a  jnz     loc_140097084
0x140096e40  test    rsi, rsi
0x140096e43  jnz     loc_14009709A
0x140096e49  test    r13, r13
0x140096e4c  jnz     loc_1400970B0
0x140096e52  test    r12, r12
0x140096e55  jnz     loc_1400970C6
0x140096e5b  mov     eax, ebx
0x140096e5d  add     rsp, 118h
0x140096e64  pop     r15
0x140096e66  pop     r14
0x140096e68  pop     r13
0x140096e6a  pop     r12
0x140096e6c  pop     rdi
0x140096e6d  pop     rsi
0x140096e6e  pop     rbx
0x140096e6f  pop     rbp
0x140096e70  retn
0x140096e72  mov     edi, r14d
0x140096e75  jmp     short loc_140096E19
0x140096e77  test    r15d, r15d
0x140096e7a  jz      loc_140096B3E
0x140096e80  mov     ebx, 0C000000Dh
0x140096e85  jmp     short loc_140096E5B
0x140096e87  cmp     eax, 0C0000034h
0x140096e8c  jnz     short loc_140096E72
0x140096e8e  movzx   edi, word ptr [rsp+150h+Source.Buffer]
0x140096e93  xor     ebx, ebx
0x140096e95  jmp     loc_140096C66
0x140096e9a  mov     edx, [rsp+150h+var_110]
0x140096e9e  mov     ecx, 100h
0x140096ea3  mov     r8d, 30455646h
0x140096ea9  call    cs:__imp_ExAllocatePool2
0x140096eb0  nop     dword ptr [rax+rax+00h]
0x140096eb5  mov     rsi, rax
0x140096eb8  test    rax, rax
0x140096ebb  jnz     short loc_140096EC7
0x140096ebd  mov     ebx, 0C000009Ah
0x140096ec2  jmp     loc_140096E19
0x140096ec7  mov     rcx, qword ptr [rsp+150h+Source.Length]; KeyHandle
0x140096ecc  lea     rax, [rsp+150h+var_110]
0x140096ed1  mov     [rsp+150h+ResultLength], rax; ResultLength
0x140096ed6  lea     rdx, [rbp+50h+ValueName]; ValueName
0x140096eda  mov     eax, [rsp+150h+var_110]
0x140096ede  mov     r9, rsi; KeyValueInformation
0x140096ee1  mov     r8d, 2; KeyValueInformationClass
0x140096ee7  mov     [rsp+150h+Length], eax; Length
0x140096eeb  call    cs:__imp_ZwQueryValueKey
0x140096ef2  nop     dword ptr [rax+rax+00h]
0x140096ef7  mov     ebx, eax
0x140096ef9  test    eax, eax
0x140096efb  js      loc_140096E72
0x140096f01  mov     ecx, [rsi+8]; ulOperand
0x140096f04  lea     rdx, [rsp+150h+Source.Buffer]; pusResult
0x140096f09  call    RtlULongToUShort
0x140096f0e  mov     ebx, eax
0x140096f10  test    eax, eax
0x140096f12  js      loc_140096E72
0x140096f18  movzx   edi, word ptr [rsp+150h+Source.Buffer]
0x140096f1d  lea     rax, [rsi+0Ch]
0x140096f21  mov     ecx, 2
0x140096f26  mov     word ptr [rsp+150h+Source.Buffer+2], di
0x140096f2b  mov     qword ptr [rsp+150h+var_F8.Length], rax
0x140096f30  cmp     di, cx
0x140096f33  jb      loc_140096E93
0x140096f39  xor     ebx, ebx
0x140096f3b  movzx   eax, di
0x140096f3e  shr     rax, 1
0x140096f41  cmp     [rsi+rax*2+0Ah], bx
0x140096f46  jnz     loc_140096C66
0x140096f4c  mov     eax, 0FFFEh
0x140096f51  add     di, ax
0x140096f54  mov     word ptr [rsp+150h+Source.Buffer], di
0x140096f59  cmp     di, cx
0x140096f5c  jnb     short loc_140096F3B
0x140096f5e  jmp     loc_140096C66
0x140096f63  call    cs:__imp_ZwClose
0x140096f6a  nop     dword ptr [rax+rax+00h]
0x140096f6f  movzx   edi, word ptr [rsp+150h+Source.Buffer]
0x140096f74  mov     qword ptr [rsp+150h+Source.Length], rbx
0x140096f79  jmp     loc_140096C74
0x140096f7e  mov     edi, ebx
0x140096f80  jmp     loc_140096DC4
0x140096f85  lea     rcx, [rbp+50h+var_B0]
0x140096f89  call    FvepCreateSecurityDescriptor
0x140096f8e  mov     r14, [rbp+50h+var_B0]
0x140096f92  xor     r15d, r15d
0x140096f95  mov     ebx, eax
0x140096f97  test    eax, eax
0x140096f99  js      loc_140096E1C
0x140096f9f  lea     rax, [rbp+50h+Destination]
0x140096fa3  mov     [rsp+30h], r15; Disposition
0x140096fa8  mov     dword ptr [rsp+150h+ResultLength], r15d; CreateOptions
0x140096fad  lea     r8, [rsp+150h+ObjectAttributes+8]; ObjectAttributes
0x140096fb2  xor     r9d, r9d; TitleIndex
0x140096fb5  mov     qword ptr [rbp+50h+ObjectAttributes+18h], rax
  ... truncated ...
```
