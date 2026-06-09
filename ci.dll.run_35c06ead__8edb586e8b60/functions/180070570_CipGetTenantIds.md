# CipGetTenantIds

- ea: `0x180070570`
- end: `0x18007091d`
- name: `CipGetTenantIds`
- size: `941`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180058048`

## callees

- `0x18002c0d0`
- `0x18002c500`
- `0x180070570`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800708d2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800708d2`
- `ntoskrnl!ExAllocatePool2` at `0x1800706cb`
- `ntoskrnl!ExAllocatePool2` at `0x1800706f7`
- `ntoskrnl!ExAllocatePool2` at `0x1800706cb`
- `ntoskrnl!ExAllocatePool2` at `0x1800706f7`
- `ntoskrnl!ZwQueryValueKey` at `0x180070835`
- `ntoskrnl!ZwQueryValueKey` at `0x180070835`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007071a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007071a`
- `ntoskrnl!ZwClose` at `0x180070891`
- `ntoskrnl!ZwClose` at `0x1800708c1`
- `ntoskrnl!ZwClose` at `0x1800708e3`
- `ntoskrnl!ZwClose` at `0x180070891`
- `ntoskrnl!ZwClose` at `0x1800708c1`
- `ntoskrnl!ZwClose` at `0x1800708e3`
- `ntoskrnl!ZwOpenKey` at `0x18007063f`
- `ntoskrnl!ZwOpenKey` at `0x1800707f9`
- `ntoskrnl!ZwOpenKey` at `0x18007063f`
- `ntoskrnl!ZwOpenKey` at `0x1800707f9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180070771`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180070771`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18007078f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800707ae`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18007078f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800707ae`
- `ntoskrnl!RtlGUIDFromString` at `0x180070876`
- `ntoskrnl!RtlGUIDFromString` at `0x180070876`
- `ntoskrnl!ZwEnumerateKey` at `0x180070671`
- `ntoskrnl!ZwEnumerateKey` at `0x180070755`
- `ntoskrnl!ZwEnumerateKey` at `0x180070671`
- `ntoskrnl!ZwEnumerateKey` at `0x180070755`

## string_xrefs

- `0x1800705a2`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\CI\Enrollments`

## pseudocode

```c
__int64 __fastcall CipGetTenantIds(GUID **a1, ULONG *a2)
{
  ULONG v4; // edi
  NTSTATUS appended; // ebx
  NTSTATUS v6; // eax
  USHORT MaximumLength; // ax
  GUID *Pool2; // r14
  ULONG i; // esi
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING Source; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+68h] [rbp-98h] BYREF
  UNICODE_STRING GuidString; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  _DWORD KeyInformation[136]; // [rsp+C0h] [rbp-40h] BYREF

  KeyHandle = 0;
  Source.Buffer = L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control\\CI\\Enrollments";
  Handle = 0;
  ValueName.Buffer = L"TenantID";
  *(_QWORD *)&Source.Length = 8650882;
  *(_QWORD *)&ValueName.Length = 1179664;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v4 = 0;
  Destination = 0;
  memset(KeyInformation, 0, sizeof(KeyInformation));
  *a2 = 0;
  ObjectAttributes.ObjectName = &Source;
  ResultLength = 0;
  *a1 = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  appended = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( appended >= 0 )
  {
    while ( 1 )
    {
      v6 = ZwEnumerateKey(KeyHandle, v4, KeyBasicInformation, KeyInformation, 0x220u, &ResultLength);
      appended = v6;
      if ( v6 == -2147483622 )
        break;
      if ( v6 < 0 )
        goto LABEL_24;
      MaximumLength = Destination.MaximumLength;
      if ( (unsigned __int16)(Source.Length + LOWORD(KeyInformation[3]) + 4) > Destination.MaximumLength )
        MaximumLength = Source.Length + LOWORD(KeyInformation[3]) + 4;
      ++v4;
      Destination.MaximumLength = MaximumLength;
    }
    if ( v4 )
    {
      Pool2 = (GUID *)ExAllocatePool2(258, 16LL * v4, 1668499779);
      if ( Pool2 )
      {
        Destination.Buffer = (PWSTR)ExAllocatePool2(258, Destination.MaximumLength, 1919109443);
        if ( Destination.Buffer )
        {
          for ( i = 0; i < v4; ++i )
          {
            appended = ZwEnumerateKey(KeyHandle, i, KeyBasicInformation, KeyInformation, 0x220u, &ResultLength);
            if ( appended < 0 )
              goto LABEL_12;
            appended = RtlAppendUnicodeStringToString(&Destination, &Source);
            if ( appended < 0 )
              goto LABEL_12;
            appended = RtlAppendUnicodeToString(&Destination, L"\\");
            if ( appended < 0 )
              goto LABEL_12;
            appended = RtlAppendUnicodeToString(&Destination, (PCWSTR)&KeyInformation[4]);
            if ( appended < 0 )
              goto LABEL_12;
            ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = &Destination;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 576;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            appended = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
            if ( appended < 0 )
              goto LABEL_12;
            appended = ZwQueryValueKey(
                         Handle,
                         &ValueName,
                         KeyValuePartialInformation,
                         KeyInformation,
                         0x220u,
                         &ResultLength);
            if ( appended < 0 )
              goto LABEL_12;
            GuidString.Length = KeyInformation[2];
            GuidString.MaximumLength = KeyInformation[2];
            *(_DWORD *)(&GuidString.MaximumLength + 1) = 0;
            GuidString.Buffer = (PWSTR)&KeyInformation[3];
            appended = RtlGUIDFromString(&GuidString, &Pool2[i]);
            if ( appended < 0 )
              goto LABEL_12;
            ZwClose(Handle);
            Destination.Length = 0;
            Handle = 0;
          }
          *a1 = Pool2;
          *a2 = v4;
        }
        else
        {
          appended = -1073741801;
LABEL_12:
          ExFreePoolWithTag(Pool2, 0x63734943u);
        }
      }
      else
      {
        appended = -1073741801;
      }
    }
  }
LABEL_24:
  if ( Handle )
    ZwClose(Handle);
  RtlFreeUnicodeString(&Destination);
  ZwClose(KeyHandle);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180070570  mov     [rsp-8+arg_10], rbx
0x180070575  mov     [rsp-8+arg_18], rsi
0x18007057a  push    rbp
0x18007057b  push    rdi
0x18007057c  push    r12
0x18007057e  push    r14
0x180070580  push    r15
0x180070582  lea     rbp, [rsp-1F0h]
0x18007058a  sub     rsp, 2F0h
0x180070591  mov     rax, cs:__security_cookie
0x180070598  xor     rax, rsp
0x18007059b  mov     [rbp+210h+var_30], rax
0x1800705a2  lea     rax, aRegistryMachin_10; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x1800705a9  mov     [rsp+310h+KeyHandle], 0
0x1800705b2  mov     [rsp+310h+Source.Buffer], rax
0x1800705b7  mov     r12, rdx
0x1800705ba  lea     rax, aTenantid; "TenantID"
0x1800705c1  mov     [rsp+310h+Handle], 0
0x1800705ca  mov     r15, rcx
0x1800705cd  mov     [rsp+310h+ValueName.Buffer], rax
0x1800705d2  xorps   xmm0, xmm0
0x1800705d5  mov     qword ptr [rsp+310h+Source.Length], 840082h
0x1800705de  mov     esi, 220h
0x1800705e3  mov     qword ptr [rsp+310h+ValueName.Length], 120010h
0x1800705ec  mov     r8d, esi; Size
0x1800705ef  mov     qword ptr [rbp+210h+ObjectAttributes.Length], 30h ; '0'
0x1800705f7  xor     edx, edx; Val
0x1800705f9  mov     qword ptr [rbp+210h+ObjectAttributes.Attributes], 240h
0x180070601  lea     rcx, [rbp+210h+KeyInformation]; void *
0x180070605  xor     edi, edi
0x180070607  movups  xmmword ptr [rsp+310h+Destination.Length], xmm0
0x18007060c  call    memset
0x180070611  lea     rax, [rsp+310h+Source]
0x180070616  mov     [r12], edi
0x18007061a  xorps   xmm0, xmm0
0x18007061d  mov     [rbp+210h+ObjectAttributes.ObjectName], rax
0x180070621  lea     r8, [rbp+210h+ObjectAttributes]; ObjectAttributes
0x180070625  mov     [rsp+310h+var_2E0], edi
0x180070629  mov     edx, 20019h; DesiredAccess
0x18007062e  mov     [r15], rdi
0x180070631  lea     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x180070636  mov     [rbp+210h+ObjectAttributes.RootDirectory], rdi
0x18007063a  movdqu  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007063f  call    cs:__imp_ZwOpenKey
0x180070646  nop     dword ptr [rax+rax+00h]
0x18007064b  mov     ebx, eax
0x18007064d  test    eax, eax
0x18007064f  js      loc_1800708B7
0x180070655  mov     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x18007065a  lea     rax, [rsp+310h+var_2E0]
0x18007065f  mov     [rsp+310h+ResultLength], rax; ResultLength
0x180070664  lea     r9, [rbp+210h+KeyInformation]; KeyInformation
0x180070668  xor     r8d, r8d; KeyInformationClass
0x18007066b  mov     [rsp+310h+Length], esi; Length
0x18007066f  mov     edx, edi; Index
0x180070671  call    cs:__imp_ZwEnumerateKey
0x180070678  nop     dword ptr [rax+rax+00h]
0x18007067d  mov     ebx, eax
0x18007067f  cmp     eax, 8000001Ah
0x180070684  jz      short loc_1800706B0
0x180070686  test    eax, eax
0x180070688  js      loc_1800708B7
0x18007068e  movzx   eax, [rsp+310h+Destination.MaximumLength]
0x180070693  movzx   ecx, [rbp+210h+var_244]
0x180070697  add     cx, 4
0x18007069b  add     cx, [rsp+310h+Source.Length]
0x1800706a0  cmp     cx, ax
0x1800706a3  cmova   ax, cx
0x1800706a7  inc     edi
0x1800706a9  mov     [rsp+310h+Destination.MaximumLength], ax
0x1800706ae  jmp     short loc_180070655
0x1800706b0  test    edi, edi
0x1800706b2  jz      loc_1800708B7
0x1800706b8  mov     edx, edi
0x1800706ba  mov     esi, 102h
0x1800706bf  shl     rdx, 4
0x1800706c3  mov     ecx, esi
0x1800706c5  mov     r8d, 63734943h
0x1800706cb  call    cs:__imp_ExAllocatePool2
0x1800706d2  nop     dword ptr [rax+rax+00h]
0x1800706d7  mov     r14, rax
0x1800706da  test    rax, rax
0x1800706dd  jnz     short loc_1800706E9
0x1800706df  mov     ebx, 0C0000017h
0x1800706e4  jmp     loc_1800708B7
0x1800706e9  movzx   edx, [rsp+310h+Destination.MaximumLength]
0x1800706ee  mov     r8d, 72634943h
0x1800706f4  mov     rcx, rsi
0x1800706f7  call    cs:__imp_ExAllocatePool2
0x1800706fe  nop     dword ptr [rax+rax+00h]
0x180070703  mov     [rsp+310h+Destination.Buffer], rax
0x180070708  test    rax, rax
0x18007070b  jnz     short loc_18007072B
0x18007070d  mov     ebx, 0C0000017h
0x180070712  mov     edx, 63734943h; Tag
0x180070717  mov     rcx, r14; P
0x18007071a  call    cs:__imp_ExFreePoolWithTag
0x180070721  nop     dword ptr [rax+rax+00h]
0x180070726  jmp     loc_1800708B7
0x18007072b  xor     esi, esi
0x18007072d  cmp     esi, edi
0x18007072f  jnb     loc_1800708B0
0x180070735  mov     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x18007073a  lea     rax, [rsp+310h+var_2E0]
0x18007073f  mov     [rsp+310h+ResultLength], rax; ResultLength
0x180070744  lea     r9, [rbp+210h+KeyInformation]; KeyInformation
0x180070748  xor     r8d, r8d; KeyInformationClass
0x18007074b  mov     [rsp+310h+Length], 220h; Length
0x180070753  mov     edx, esi; Index
0x180070755  call    cs:__imp_ZwEnumerateKey
0x18007075c  nop     dword ptr [rax+rax+00h]
0x180070761  mov     ebx, eax
0x180070763  test    eax, eax
0x180070765  js      short loc_180070712
0x180070767  lea     rdx, [rsp+310h+Source]; Source
0x18007076c  lea     rcx, [rsp+310h+Destination]; Destination
0x180070771  call    cs:__imp_RtlAppendUnicodeStringToString
0x180070778  nop     dword ptr [rax+rax+00h]
0x18007077d  mov     ebx, eax
0x18007077f  test    eax, eax
0x180070781  js      short loc_180070712
0x180070783  lea     rdx, asc_180033184; "\\"
0x18007078a  lea     rcx, [rsp+310h+Destination]; Destination
0x18007078f  call    cs:__imp_RtlAppendUnicodeToString
0x180070796  nop     dword ptr [rax+rax+00h]
0x18007079b  mov     ebx, eax
0x18007079d  test    eax, eax
0x18007079f  js      loc_180070712
0x1800707a5  lea     rdx, [rbp+210h+var_240]; Source
0x1800707a9  lea     rcx, [rsp+310h+Destination]; Destination
0x1800707ae  call    cs:__imp_RtlAppendUnicodeToString
0x1800707b5  nop     dword ptr [rax+rax+00h]
0x1800707ba  mov     ebx, eax
0x1800707bc  test    eax, eax
0x1800707be  js      loc_180070712
0x1800707c4  lea     rax, [rsp+310h+Destination]
0x1800707c9  mov     [rbp+210h+ObjectAttributes.Length], 30h ; '0'
0x1800707d0  xorps   xmm0, xmm0
0x1800707d3  mov     [rbp+210h+ObjectAttributes.ObjectName], rax
0x1800707d7  lea     r8, [rbp+210h+ObjectAttributes]; ObjectAttributes
0x1800707db  mov     [rbp+210h+ObjectAttributes.RootDirectory], 0
0x1800707e3  mov     edx, 20019h; DesiredAccess
0x1800707e8  mov     [rbp+210h+ObjectAttributes.Attributes], 240h
0x1800707ef  lea     rcx, [rsp+310h+Handle]; KeyHandle
0x1800707f4  movdqu  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800707f9  call    cs:__imp_ZwOpenKey
0x180070800  nop     dword ptr [rax+rax+00h]
0x180070805  mov     ebx, eax
0x180070807  test    eax, eax
0x180070809  js      loc_180070712
0x18007080f  mov     rcx, [rsp+310h+Handle]; KeyHandle
0x180070814  lea     rax, [rsp+310h+var_2E0]
0x180070819  mov     [rsp+310h+ResultLength], rax; ResultLength
0x18007081e  lea     r9, [rbp+210h+KeyInformation]; KeyValueInformation
0x180070822  mov     r8d, 2; KeyValueInformationClass
0x180070828  mov     [rsp+310h+Length], 220h; Length
0x180070830  lea     rdx, [rsp+310h+ValueName]; ValueName
0x180070835  call    cs:__imp_ZwQueryValueKey
0x18007083c  nop     dword ptr [rax+rax+00h]
0x180070841  mov     ebx, eax
0x180070843  test    eax, eax
0x180070845  js      loc_180070712
0x18007084b  mov     eax, [rbp+210h+var_248]
0x18007084e  lea     rcx, [rsp+310h+GuidString]; GuidString
0x180070853  mov     [rsp+310h+GuidString.Length], ax
0x180070858  mov     [rsp+310h+GuidString.MaximumLength], ax
0x18007085d  lea     rax, [rbp+210h+var_244]
0x180070861  mov     edx, esi
0x180070863  shl     rdx, 4
0x180070867  add     rdx, r14; Guid
0x18007086a  mov     dword ptr [rsp+310h+GuidString+4], 0
0x180070872  mov     [rbp+210h+GuidString.Buffer], rax
0x180070876  call    cs:__imp_RtlGUIDFromString
0x18007087d  nop     dword ptr [rax+rax+00h]
0x180070882  mov     ebx, eax
0x180070884  test    eax, eax
0x180070886  js      loc_180070712
0x18007088c  mov     rcx, [rsp+310h+Handle]; Handle
0x180070891  call    cs:__imp_ZwClose
0x180070898  nop     dword ptr [rax+rax+00h]
0x18007089d  xor     eax, eax
0x18007089f  mov     [rsp+310h+Destination.Length], ax
0x1800708a4  inc     esi
0x1800708a6  mov     [rsp+310h+Handle], rax
0x1800708ab  jmp     loc_18007072D
0x1800708b0  mov     [r15], r14
0x1800708b3  mov     [r12], edi
0x1800708b7  mov     rcx, [rsp+310h+Handle]; Handle
0x1800708bc  test    rcx, rcx
0x1800708bf  jz      short loc_1800708CD
0x1800708c1  call    cs:__imp_ZwClose
0x1800708c8  nop     dword ptr [rax+rax+00h]
0x1800708cd  lea     rcx, [rsp+310h+Destination]; UnicodeString
0x1800708d2  call    cs:__imp_RtlFreeUnicodeString
0x1800708d9  nop     dword ptr [rax+rax+00h]
0x1800708de  mov     rcx, [rsp+310h+KeyHandle]; Handle
0x1800708e3  call    cs:__imp_ZwClose
0x1800708ea  nop     dword ptr [rax+rax+00h]
0x1800708ef  mov     eax, ebx
0x1800708f1  mov     rcx, [rbp+210h+var_30]
0x1800708f8  xor     rcx, rsp; StackCookie
0x1800708fb  call    __security_check_cookie
0x180070900  lea     r11, [rsp+310h+var_20]
0x180070908  mov     rbx, [r11+40h]
0x18007090c  mov     rsi, [r11+48h]
0x180070910  mov     rsp, r11
0x180070913  pop     r15
0x180070915  pop     r14
0x180070917  pop     r12
0x180070919  pop     rdi
0x18007091a  pop     rbp
0x18007091b  retn
```
