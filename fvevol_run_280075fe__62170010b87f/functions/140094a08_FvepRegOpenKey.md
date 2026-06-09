# FvepRegOpenKey

- ea: `0x140094a08`
- end: `0x14009502c`
- name: `FvepRegOpenKey`
- size: `1572`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14005c7e8`
- `0x14005ca10`
- `0x14005cc74`
- `0x14005cd38`
- `0x14005d0dc`
- `0x14005d390`
- `0x140094888`

## callees

- `0x140007ce8`
- `0x14005cf34`
- `0x140094a08`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140094c45`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140094c79`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140094c45`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140094c79`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140094c5a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140094c8f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140094cbd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140094cf9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140094c5a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140094c8f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140094cbd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140094cf9`
- `ntoskrnl!RtlStringFromGUID` at `0x140094cda`
- `ntoskrnl!RtlStringFromGUID` at `0x140094cda`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140094fc3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140094fc3`
- `ntoskrnl!ZwOpenKey` at `0x140094b27`
- `ntoskrnl!ZwOpenKey` at `0x140094d51`
- `ntoskrnl!ZwOpenKey` at `0x140094b27`
- `ntoskrnl!ZwOpenKey` at `0x140094d51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094fd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094fef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095005`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009501b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094fd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094fef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095005`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009501b`
- `ntoskrnl!ZwClose` at `0x140094eb3`
- `ntoskrnl!ZwClose` at `0x140094fa9`
- `ntoskrnl!ZwClose` at `0x140094eb3`
- `ntoskrnl!ZwClose` at `0x140094fa9`
- `ntoskrnl!ExAllocatePool2` at `0x140094be6`
- `ntoskrnl!ExAllocatePool2` at `0x140094bff`
- `ntoskrnl!ExAllocatePool2` at `0x140094df9`
- `ntoskrnl!ExAllocatePool2` at `0x140094be6`
- `ntoskrnl!ExAllocatePool2` at `0x140094bff`
- `ntoskrnl!ExAllocatePool2` at `0x140094df9`
- `ntoskrnl!ZwQueryValueKey` at `0x140094b72`
- `ntoskrnl!ZwQueryValueKey` at `0x140094e3b`
- `ntoskrnl!ZwQueryValueKey` at `0x140094b72`
- `ntoskrnl!ZwQueryValueKey` at `0x140094e3b`
- `ntoskrnl!ZwCreateKey` at `0x140094f33`
- `ntoskrnl!ZwCreateKey` at `0x140094f8c`
- `ntoskrnl!ZwCreateKey` at `0x140094f33`
- `ntoskrnl!ZwCreateKey` at `0x140094f8c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094aa2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094ab9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094ad1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094ae8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094b48`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094aa2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094ab9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094ad1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094ae8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094b48`

## string_xrefs

- `0x140094aae`: `\Registry\Machine\System\CurrentControlSet\Control\FVEAutoUnlock`
- `0x140094a8e`: `\Registry\Machine\`

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
0x140094a08  mov     rax, rsp
0x140094a0b  mov     [rax+20h], r9
0x140094a0f  mov     [rax+10h], edx
0x140094a12  mov     [rax+8], rcx
0x140094a16  push    rbp
0x140094a17  push    rbx
0x140094a18  push    rsi
0x140094a19  push    rdi
0x140094a1a  push    r12
0x140094a1c  push    r13
0x140094a1e  push    r14
0x140094a20  push    r15
0x140094a22  lea     rbp, [rax-58h]
0x140094a26  sub     rsp, 118h
0x140094a2d  xorps   xmm0, xmm0
0x140094a30  xor     edi, edi
0x140094a32  xorps   xmm1, xmm1
0x140094a35  mov     qword ptr [rsp+150h+Source.Length], rdi
0x140094a3a  mov     r15d, r8d
0x140094a3d  mov     [rbp+50h+var_B0], rdi
0x140094a41  and     r15d, 1
0x140094a45  mov     [rsp+150h+var_110], edi
0x140094a49  mov     r14d, edi
0x140094a4c  movups  xmmword ptr [rbp+50h+GuidString.Length], xmm0
0x140094a50  movups  xmmword ptr [rsp+150h+Source.Buffer], xmm1
0x140094a55  movups  xmmword ptr [rbp+50h+Destination.Length], xmm0
0x140094a59  movups  xmmword ptr [rsp+150h+var_F8.Buffer], xmm1
0x140094a5e  movups  xmmword ptr [rsp+150h+ObjectAttributes+8], xmm0
0x140094a63  movups  xmmword ptr [rbp+50h+ObjectAttributes+18h], xmm0
0x140094a67  movups  xmmword ptr [rbp+50h+ObjectAttributes+28h], xmm0
0x140094a6b  movups  xmmword ptr [rbp+50h+var_58.Length], xmm0
0x140094a6f  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm1
0x140094a73  movups  xmmword ptr [rbp+50h+var_68.Length], xmm0
0x140094a77  movups  xmmword ptr [rbp+50h+ValueName.Length], xmm1
0x140094a7b  test    r8b, 2
0x140094a7f  jnz     loc_140094DC7
0x140094a85  test    r15d, r15d
0x140094a88  jz      loc_140094DD0
0x140094a8e  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\"
0x140094a95  mov     r12, rdi
0x140094a98  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140094a9c  mov     r13, rdi
0x140094a9f  mov     rsi, rdi
0x140094aa2  call    cs:__imp_RtlInitUnicodeString
0x140094aa9  nop     dword ptr [rax+rax+00h]
0x140094aae  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x140094ab5  lea     rcx, [rbp+50h+var_68]; DestinationString
0x140094ab9  call    cs:__imp_RtlInitUnicodeString
0x140094ac0  nop     dword ptr [rax+rax+00h]
0x140094ac5  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\FVE"...
0x140094acc  lea     rcx, [rsp+150h+Source.Buffer]; DestinationString
0x140094ad1  call    cs:__imp_RtlInitUnicodeString
0x140094ad8  nop     dword ptr [rax+rax+00h]
0x140094add  lea     rdx, Source; "\\"
0x140094ae4  lea     rcx, [rbp+50h+var_58]; DestinationString
0x140094ae8  call    cs:__imp_RtlInitUnicodeString
0x140094aef  nop     dword ptr [rax+rax+00h]
0x140094af4  lea     rax, [rbp+50h+var_68]
0x140094af8  mov     dword ptr [rsp+150h+ObjectAttributes+8], 30h ; '0'
0x140094b00  xorps   xmm0, xmm0
0x140094b03  mov     qword ptr [rbp+50h+ObjectAttributes+18h], rax
0x140094b07  lea     r8, [rsp+150h+ObjectAttributes+8]; ObjectAttributes
0x140094b0c  mov     qword ptr [rsp+150h+ObjectAttributes+10h], rdi
0x140094b11  mov     edx, 20019h; DesiredAccess
0x140094b16  mov     dword ptr [rbp+50h+ObjectAttributes+20h], 240h
0x140094b1d  lea     rcx, [rsp+150h+Source]; KeyHandle
0x140094b22  movdqu  xmmword ptr [rbp+50h+ObjectAttributes+28h], xmm0
0x140094b27  call    cs:__imp_ZwOpenKey
0x140094b2e  nop     dword ptr [rax+rax+00h]
0x140094b33  mov     ebx, eax
0x140094b35  test    eax, eax
0x140094b37  js      loc_140094DD7
0x140094b3d  lea     rdx, aDriverautounlo; "DriverAutoUnlockRedirectionKey"
0x140094b44  lea     rcx, [rbp+50h+ValueName]; DestinationString
0x140094b48  call    cs:__imp_RtlInitUnicodeString
0x140094b4f  nop     dword ptr [rax+rax+00h]
0x140094b54  mov     rcx, qword ptr [rsp+150h+Source.Length]; KeyHandle
0x140094b59  lea     rax, [rsp+150h+var_110]
0x140094b5e  xor     r9d, r9d; KeyValueInformation
0x140094b61  mov     [rsp+150h+ResultLength], rax; ResultLength
0x140094b66  lea     rdx, [rbp+50h+ValueName]; ValueName
0x140094b6a  mov     [rsp+150h+Length], edi; Length
0x140094b6e  lea     r8d, [r9+2]; KeyValueInformationClass
0x140094b72  call    cs:__imp_ZwQueryValueKey
0x140094b79  nop     dword ptr [rax+rax+00h]
0x140094b7e  mov     ebx, eax
0x140094b80  cmp     eax, 0C0000034h
0x140094b85  jz      loc_140094DDE
0x140094b8b  cmp     eax, 80000005h
0x140094b90  jz      loc_140094DEA
0x140094b96  cmp     eax, 0C0000023h
0x140094b9b  jz      loc_140094DEA
0x140094ba1  xor     r15d, r15d
0x140094ba4  test    eax, eax
0x140094ba6  js      loc_140094D6C
0x140094bac  mov     ebx, 0C0000001h
0x140094bb1  jmp     loc_140094D6C
0x140094bb6  mov     rcx, qword ptr [rsp+150h+Source.Length]; Handle
0x140094bbb  test    rcx, rcx
0x140094bbe  jnz     loc_140094EB3
0x140094bc4  mov     eax, 88h
0x140094bc9  add     di, ax
0x140094bcc  cmp     di, ax
0x140094bcf  jb      loc_140094D61
0x140094bd5  movzx   ebx, di
0x140094bd8  lea     ecx, [rax+78h]
0x140094bdb  mov     r12d, 30455646h
0x140094be1  mov     edx, ebx
0x140094be3  mov     r8d, r12d
0x140094be6  call    cs:__imp_ExAllocatePool2
0x140094bed  nop     dword ptr [rax+rax+00h]
0x140094bf2  mov     r8d, r12d
0x140094bf5  mov     edx, ebx
0x140094bf7  mov     ecx, 100h
0x140094bfc  mov     r13, rax
0x140094bff  call    cs:__imp_ExAllocatePool2
0x140094c06  nop     dword ptr [rax+rax+00h]
0x140094c0b  mov     r12, rax
0x140094c0e  xor     eax, eax
0x140094c10  test    r13, r13
0x140094c13  jz      loc_140094F9D
0x140094c19  test    r12, r12
0x140094c1c  jz      loc_140094F9D
0x140094c22  lea     rdx, [rbp+50h+DestinationString]; SourceString
0x140094c26  mov     [rbp+50h+Destination.Buffer], r12
0x140094c2a  lea     rcx, [rbp+50h+Destination]; DestinationString
0x140094c2e  mov     [rbp+50h+Destination.MaximumLength], di
0x140094c32  mov     [rbp+50h+Destination.Length], di
0x140094c36  mov     qword ptr [rsp+150h+ObjectAttributes], r13
0x140094c3b  mov     word ptr [rsp+150h+var_F8.Buffer+2], di
0x140094c40  mov     word ptr [rsp+150h+var_F8.Buffer], di
0x140094c45  call    cs:__imp_RtlCopyUnicodeString
0x140094c4c  nop     dword ptr [rax+rax+00h]
0x140094c51  lea     rdx, [rsp+150h+Source.Buffer]; Source
0x140094c56  lea     rcx, [rbp+50h+Destination]; Destination
0x140094c5a  call    cs:__imp_RtlAppendUnicodeStringToString
0x140094c61  nop     dword ptr [rax+rax+00h]
0x140094c66  mov     ebx, eax
0x140094c68  test    eax, eax
0x140094c6a  js      loc_140094DC2
0x140094c70  lea     rdx, [rbp+50h+DestinationString]; SourceString
0x140094c74  lea     rcx, [rsp+150h+var_F8.Buffer]; DestinationString
0x140094c79  call    cs:__imp_RtlCopyUnicodeString
0x140094c80  nop     dword ptr [rax+rax+00h]
0x140094c85  lea     rdx, [rsp+150h+Source.Buffer]; Source
0x140094c8a  lea     rcx, [rsp+150h+var_F8.Buffer]; Destination
0x140094c8f  call    cs:__imp_RtlAppendUnicodeStringToString
0x140094c96  nop     dword ptr [rax+rax+00h]
0x140094c9b  mov     ebx, eax
0x140094c9d  test    eax, eax
0x140094c9f  js      loc_140094DC2
0x140094ca5  mov     rdi, [rbp+50h+Guid]
0x140094ca9  xor     ebx, ebx
0x140094cab  test    rdi, rdi
0x140094cae  jz      loc_140094ECE
0x140094cb4  lea     rdx, [rbp+50h+var_58]; Source
0x140094cb8  lea     rcx, [rsp+150h+var_F8.Buffer]; Destination
0x140094cbd  call    cs:__imp_RtlAppendUnicodeStringToString
0x140094cc4  nop     dword ptr [rax+rax+00h]
0x140094cc9  mov     ebx, eax
0x140094ccb  test    eax, eax
0x140094ccd  js      loc_140094DC2
0x140094cd3  lea     rdx, [rbp+50h+GuidString]; GuidString
0x140094cd7  mov     rcx, rdi; Guid
0x140094cda  call    cs:__imp_RtlStringFromGUID
0x140094ce1  nop     dword ptr [rax+rax+00h]
0x140094ce6  mov     ebx, eax
0x140094ce8  test    eax, eax
0x140094cea  js      loc_140094DC2
0x140094cf0  lea     rdx, [rbp+50h+GuidString]; Source
0x140094cf4  lea     rcx, [rsp+150h+var_F8.Buffer]; Destination
0x140094cf9  call    cs:__imp_RtlAppendUnicodeStringToString
0x140094d00  nop     dword ptr [rax+rax+00h]
0x140094d05  mov     ebx, eax
0x140094d07  test    eax, eax
0x140094d09  js      loc_140094DC2
0x140094d0f  mov     edi, 1
0x140094d14  test    r15d, r15d
0x140094d17  jz      loc_140094ED5
0x140094d1d  mov     edx, [rbp+50h+DesiredAccess]; DesiredAccess
0x140094d20  lea     rax, [rsp+150h+var_F8.Buffer]
0x140094d25  mov     rcx, [rbp+50h+KeyHandle]; KeyHandle
0x140094d29  lea     r8, [rsp+150h+ObjectAttributes+8]; ObjectAttributes
0x140094d2e  xor     r15d, r15d
0x140094d31  mov     qword ptr [rbp+50h+ObjectAttributes+18h], rax
0x140094d35  xorps   xmm0, xmm0
0x140094d38  mov     qword ptr [rsp+150h+ObjectAttributes+10h], r15
0x140094d3d  movdqu  xmmword ptr [rbp+50h+ObjectAttributes+28h], xmm0
0x140094d42  mov     dword ptr [rsp+150h+ObjectAttributes+8], 30h ; '0'
0x140094d4a  mov     dword ptr [rbp+50h+ObjectAttributes+20h], 240h
0x140094d51  call    cs:__imp_ZwOpenKey
0x140094d58  nop     dword ptr [rax+rax+00h]
0x140094d5d  mov     ebx, eax
0x140094d5f  jmp     short loc_140094D6C
0x140094d61  mov     ebx, 0C0000095h
0x140094d66  mov     edi, r12d
0x140094d69  xor     r15d, r15d
0x140094d6c  mov     rcx, qword ptr [rsp+150h+Source.Length]; Handle
0x140094d71  test    rcx, rcx
0x140094d74  jnz     loc_140094FA9
0x140094d7a  test    edi, edi
0x140094d7c  jnz     loc_140094FBF
0x140094d82  mov     edi, 30455646h
0x140094d87  test    r14, r14
0x140094d8a  jnz     loc_140094FD4
0x140094d90  test    rsi, rsi
0x140094d93  jnz     loc_140094FEA
0x140094d99  test    r13, r13
0x140094d9c  jnz     loc_140095000
0x140094da2  test    r12, r12
0x140094da5  jnz     loc_140095016
0x140094dab  mov     eax, ebx
0x140094dad  add     rsp, 118h
0x140094db4  pop     r15
0x140094db6  pop     r14
0x140094db8  pop     r13
0x140094dba  pop     r12
0x140094dbc  pop     rdi
0x140094dbd  pop     rsi
0x140094dbe  pop     rbx
0x140094dbf  pop     rbp
0x140094dc0  retn
0x140094dc2  mov     edi, r14d
0x140094dc5  jmp     short loc_140094D69
0x140094dc7  test    r15d, r15d
0x140094dca  jz      loc_140094A8E
0x140094dd0  mov     ebx, 0C000000Dh
0x140094dd5  jmp     short loc_140094DAB
0x140094dd7  cmp     eax, 0C0000034h
0x140094ddc  jnz     short loc_140094DC2
0x140094dde  movzx   edi, word ptr [rsp+150h+Source.Buffer]
0x140094de3  xor     ebx, ebx
0x140094de5  jmp     loc_140094BB6
0x140094dea  mov     edx, [rsp+150h+var_110]
0x140094dee  mov     ecx, 100h
0x140094df3  mov     r8d, 30455646h
0x140094df9  call    cs:__imp_ExAllocatePool2
0x140094e00  nop     dword ptr [rax+rax+00h]
0x140094e05  mov     rsi, rax
0x140094e08  test    rax, rax
0x140094e0b  jnz     short loc_140094E17
0x140094e0d  mov     ebx, 0C000009Ah
0x140094e12  jmp     loc_140094D69
0x140094e17  mov     rcx, qword ptr [rsp+150h+Source.Length]; KeyHandle
0x140094e1c  lea     rax, [rsp+150h+var_110]
0x140094e21  mov     [rsp+150h+ResultLength], rax; ResultLength
0x140094e26  lea     rdx, [rbp+50h+ValueName]; ValueName
0x140094e2a  mov     eax, [rsp+150h+var_110]
0x140094e2e  mov     r9, rsi; KeyValueInformation
0x140094e31  mov     r8d, 2; KeyValueInformationClass
0x140094e37  mov     [rsp+150h+Length], eax; Length
0x140094e3b  call    cs:__imp_ZwQueryValueKey
0x140094e42  nop     dword ptr [rax+rax+00h]
0x140094e47  mov     ebx, eax
0x140094e49  test    eax, eax
0x140094e4b  js      loc_140094DC2
0x140094e51  mov     ecx, [rsi+8]; ulOperand
0x140094e54  lea     rdx, [rsp+150h+Source.Buffer]; pusResult
0x140094e59  call    RtlULongToUShort
0x140094e5e  mov     ebx, eax
0x140094e60  test    eax, eax
0x140094e62  js      loc_140094DC2
0x140094e68  movzx   edi, word ptr [rsp+150h+Source.Buffer]
0x140094e6d  lea     rax, [rsi+0Ch]
0x140094e71  mov     ecx, 2
0x140094e76  mov     word ptr [rsp+150h+Source.Buffer+2], di
0x140094e7b  mov     qword ptr [rsp+150h+var_F8.Length], rax
0x140094e80  cmp     di, cx
0x140094e83  jb      loc_140094DE3
0x140094e89  xor     ebx, ebx
0x140094e8b  movzx   eax, di
0x140094e8e  shr     rax, 1
0x140094e91  cmp     [rsi+rax*2+0Ah], bx
0x140094e96  jnz     loc_140094BB6
0x140094e9c  mov     eax, 0FFFEh
0x140094ea1  add     di, ax
0x140094ea4  mov     word ptr [rsp+150h+Source.Buffer], di
0x140094ea9  cmp     di, cx
0x140094eac  jnb     short loc_140094E8B
0x140094eae  jmp     loc_140094BB6
0x140094eb3  call    cs:__imp_ZwClose
0x140094eba  nop     dword ptr [rax+rax+00h]
0x140094ebf  movzx   edi, word ptr [rsp+150h+Source.Buffer]
0x140094ec4  mov     qword ptr [rsp+150h+Source.Length], rbx
0x140094ec9  jmp     loc_140094BC4
0x140094ece  mov     edi, ebx
0x140094ed0  jmp     loc_140094D14
0x140094ed5  lea     rcx, [rbp+50h+var_B0]
0x140094ed9  call    FvepCreateSecurityDescriptor
0x140094ede  mov     r14, [rbp+50h+var_B0]
0x140094ee2  xor     r15d, r15d
0x140094ee5  mov     ebx, eax
0x140094ee7  test    eax, eax
0x140094ee9  js      loc_140094D6C
0x140094eef  lea     rax, [rbp+50h+Destination]
0x140094ef3  mov     [rsp+30h], r15; Disposition
0x140094ef8  mov     dword ptr [rsp+150h+ResultLength], r15d; CreateOptions
0x140094efd  lea     r8, [rsp+150h+ObjectAttributes+8]; ObjectAttributes
0x140094f02  xor     r9d, r9d; TitleIndex
0x140094f05  mov     qword ptr [rbp+50h+ObjectAttributes+18h], rax
  ... truncated ...
```
