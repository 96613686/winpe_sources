# CipGetTenantIds

- ea: `0x180070290`
- end: `0x18007063d`
- name: `CipGetTenantIds`
- size: `941`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180058120`

## callees

- `0x18002bf20`
- `0x18002c380`
- `0x180070290`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800705f2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800705f2`
- `ntoskrnl!ExAllocatePool2` at `0x1800703eb`
- `ntoskrnl!ExAllocatePool2` at `0x180070417`
- `ntoskrnl!ExAllocatePool2` at `0x1800703eb`
- `ntoskrnl!ExAllocatePool2` at `0x180070417`
- `ntoskrnl!ZwQueryValueKey` at `0x180070555`
- `ntoskrnl!ZwQueryValueKey` at `0x180070555`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007043a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007043a`
- `ntoskrnl!ZwClose` at `0x1800705b1`
- `ntoskrnl!ZwClose` at `0x1800705e1`
- `ntoskrnl!ZwClose` at `0x180070603`
- `ntoskrnl!ZwClose` at `0x1800705b1`
- `ntoskrnl!ZwClose` at `0x1800705e1`
- `ntoskrnl!ZwClose` at `0x180070603`
- `ntoskrnl!ZwOpenKey` at `0x18007035f`
- `ntoskrnl!ZwOpenKey` at `0x180070519`
- `ntoskrnl!ZwOpenKey` at `0x18007035f`
- `ntoskrnl!ZwOpenKey` at `0x180070519`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180070491`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180070491`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800704af`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800704ce`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800704af`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800704ce`
- `ntoskrnl!RtlGUIDFromString` at `0x180070596`
- `ntoskrnl!RtlGUIDFromString` at `0x180070596`
- `ntoskrnl!ZwEnumerateKey` at `0x180070391`
- `ntoskrnl!ZwEnumerateKey` at `0x180070475`
- `ntoskrnl!ZwEnumerateKey` at `0x180070391`
- `ntoskrnl!ZwEnumerateKey` at `0x180070475`

## string_xrefs

- `0x1800702c2`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\CI\Enrollments`

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
0x180070290  mov     [rsp-8+arg_10], rbx
0x180070295  mov     [rsp-8+arg_18], rsi
0x18007029a  push    rbp
0x18007029b  push    rdi
0x18007029c  push    r12
0x18007029e  push    r14
0x1800702a0  push    r15
0x1800702a2  lea     rbp, [rsp-1F0h]
0x1800702aa  sub     rsp, 2F0h
0x1800702b1  mov     rax, cs:__security_cookie
0x1800702b8  xor     rax, rsp
0x1800702bb  mov     [rbp+210h+var_30], rax
0x1800702c2  lea     rax, aRegistryMachin_10; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x1800702c9  mov     [rsp+310h+KeyHandle], 0
0x1800702d2  mov     [rsp+310h+Source.Buffer], rax
0x1800702d7  mov     r12, rdx
0x1800702da  lea     rax, aTenantid; "TenantID"
0x1800702e1  mov     [rsp+310h+Handle], 0
0x1800702ea  mov     r15, rcx
0x1800702ed  mov     [rsp+310h+ValueName.Buffer], rax
0x1800702f2  xorps   xmm0, xmm0
0x1800702f5  mov     qword ptr [rsp+310h+Source.Length], 840082h
0x1800702fe  mov     esi, 220h
0x180070303  mov     qword ptr [rsp+310h+ValueName.Length], 120010h
0x18007030c  mov     r8d, esi; Size
0x18007030f  mov     qword ptr [rbp+210h+ObjectAttributes.Length], 30h ; '0'
0x180070317  xor     edx, edx; Val
0x180070319  mov     qword ptr [rbp+210h+ObjectAttributes.Attributes], 240h
0x180070321  lea     rcx, [rbp+210h+KeyInformation]; void *
0x180070325  xor     edi, edi
0x180070327  movups  xmmword ptr [rsp+310h+Destination.Length], xmm0
0x18007032c  call    memset
0x180070331  lea     rax, [rsp+310h+Source]
0x180070336  mov     [r12], edi
0x18007033a  xorps   xmm0, xmm0
0x18007033d  mov     [rbp+210h+ObjectAttributes.ObjectName], rax
0x180070341  lea     r8, [rbp+210h+ObjectAttributes]; ObjectAttributes
0x180070345  mov     [rsp+310h+var_2E0], edi
0x180070349  mov     edx, 20019h; DesiredAccess
0x18007034e  mov     [r15], rdi
0x180070351  lea     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x180070356  mov     [rbp+210h+ObjectAttributes.RootDirectory], rdi
0x18007035a  movdqu  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007035f  call    cs:__imp_ZwOpenKey
0x180070366  nop     dword ptr [rax+rax+00h]
0x18007036b  mov     ebx, eax
0x18007036d  test    eax, eax
0x18007036f  js      loc_1800705D7
0x180070375  mov     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x18007037a  lea     rax, [rsp+310h+var_2E0]
0x18007037f  mov     [rsp+310h+ResultLength], rax; ResultLength
0x180070384  lea     r9, [rbp+210h+KeyInformation]; KeyInformation
0x180070388  xor     r8d, r8d; KeyInformationClass
0x18007038b  mov     [rsp+310h+Length], esi; Length
0x18007038f  mov     edx, edi; Index
0x180070391  call    cs:__imp_ZwEnumerateKey
0x180070398  nop     dword ptr [rax+rax+00h]
0x18007039d  mov     ebx, eax
0x18007039f  cmp     eax, 8000001Ah
0x1800703a4  jz      short loc_1800703D0
0x1800703a6  test    eax, eax
0x1800703a8  js      loc_1800705D7
0x1800703ae  movzx   eax, [rsp+310h+Destination.MaximumLength]
0x1800703b3  movzx   ecx, [rbp+210h+var_244]
0x1800703b7  add     cx, 4
0x1800703bb  add     cx, [rsp+310h+Source.Length]
0x1800703c0  cmp     cx, ax
0x1800703c3  cmova   ax, cx
0x1800703c7  inc     edi
0x1800703c9  mov     [rsp+310h+Destination.MaximumLength], ax
0x1800703ce  jmp     short loc_180070375
0x1800703d0  test    edi, edi
0x1800703d2  jz      loc_1800705D7
0x1800703d8  mov     edx, edi
0x1800703da  mov     esi, 102h
0x1800703df  shl     rdx, 4
0x1800703e3  mov     ecx, esi
0x1800703e5  mov     r8d, 63734943h
0x1800703eb  call    cs:__imp_ExAllocatePool2
0x1800703f2  nop     dword ptr [rax+rax+00h]
0x1800703f7  mov     r14, rax
0x1800703fa  test    rax, rax
0x1800703fd  jnz     short loc_180070409
0x1800703ff  mov     ebx, 0C0000017h
0x180070404  jmp     loc_1800705D7
0x180070409  movzx   edx, [rsp+310h+Destination.MaximumLength]
0x18007040e  mov     r8d, 72634943h
0x180070414  mov     rcx, rsi
0x180070417  call    cs:__imp_ExAllocatePool2
0x18007041e  nop     dword ptr [rax+rax+00h]
0x180070423  mov     [rsp+310h+Destination.Buffer], rax
0x180070428  test    rax, rax
0x18007042b  jnz     short loc_18007044B
0x18007042d  mov     ebx, 0C0000017h
0x180070432  mov     edx, 63734943h; Tag
0x180070437  mov     rcx, r14; P
0x18007043a  call    cs:__imp_ExFreePoolWithTag
0x180070441  nop     dword ptr [rax+rax+00h]
0x180070446  jmp     loc_1800705D7
0x18007044b  xor     esi, esi
0x18007044d  cmp     esi, edi
0x18007044f  jnb     loc_1800705D0
0x180070455  mov     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x18007045a  lea     rax, [rsp+310h+var_2E0]
0x18007045f  mov     [rsp+310h+ResultLength], rax; ResultLength
0x180070464  lea     r9, [rbp+210h+KeyInformation]; KeyInformation
0x180070468  xor     r8d, r8d; KeyInformationClass
0x18007046b  mov     [rsp+310h+Length], 220h; Length
0x180070473  mov     edx, esi; Index
0x180070475  call    cs:__imp_ZwEnumerateKey
0x18007047c  nop     dword ptr [rax+rax+00h]
0x180070481  mov     ebx, eax
0x180070483  test    eax, eax
0x180070485  js      short loc_180070432
0x180070487  lea     rdx, [rsp+310h+Source]; Source
0x18007048c  lea     rcx, [rsp+310h+Destination]; Destination
0x180070491  call    cs:__imp_RtlAppendUnicodeStringToString
0x180070498  nop     dword ptr [rax+rax+00h]
0x18007049d  mov     ebx, eax
0x18007049f  test    eax, eax
0x1800704a1  js      short loc_180070432
0x1800704a3  lea     rdx, asc_180033354; "\\"
0x1800704aa  lea     rcx, [rsp+310h+Destination]; Destination
0x1800704af  call    cs:__imp_RtlAppendUnicodeToString
0x1800704b6  nop     dword ptr [rax+rax+00h]
0x1800704bb  mov     ebx, eax
0x1800704bd  test    eax, eax
0x1800704bf  js      loc_180070432
0x1800704c5  lea     rdx, [rbp+210h+var_240]; Source
0x1800704c9  lea     rcx, [rsp+310h+Destination]; Destination
0x1800704ce  call    cs:__imp_RtlAppendUnicodeToString
0x1800704d5  nop     dword ptr [rax+rax+00h]
0x1800704da  mov     ebx, eax
0x1800704dc  test    eax, eax
0x1800704de  js      loc_180070432
0x1800704e4  lea     rax, [rsp+310h+Destination]
0x1800704e9  mov     [rbp+210h+ObjectAttributes.Length], 30h ; '0'
0x1800704f0  xorps   xmm0, xmm0
0x1800704f3  mov     [rbp+210h+ObjectAttributes.ObjectName], rax
0x1800704f7  lea     r8, [rbp+210h+ObjectAttributes]; ObjectAttributes
0x1800704fb  mov     [rbp+210h+ObjectAttributes.RootDirectory], 0
0x180070503  mov     edx, 20019h; DesiredAccess
0x180070508  mov     [rbp+210h+ObjectAttributes.Attributes], 240h
0x18007050f  lea     rcx, [rsp+310h+Handle]; KeyHandle
0x180070514  movdqu  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x180070519  call    cs:__imp_ZwOpenKey
0x180070520  nop     dword ptr [rax+rax+00h]
0x180070525  mov     ebx, eax
0x180070527  test    eax, eax
0x180070529  js      loc_180070432
0x18007052f  mov     rcx, [rsp+310h+Handle]; KeyHandle
0x180070534  lea     rax, [rsp+310h+var_2E0]
0x180070539  mov     [rsp+310h+ResultLength], rax; ResultLength
0x18007053e  lea     r9, [rbp+210h+KeyInformation]; KeyValueInformation
0x180070542  mov     r8d, 2; KeyValueInformationClass
0x180070548  mov     [rsp+310h+Length], 220h; Length
0x180070550  lea     rdx, [rsp+310h+ValueName]; ValueName
0x180070555  call    cs:__imp_ZwQueryValueKey
0x18007055c  nop     dword ptr [rax+rax+00h]
0x180070561  mov     ebx, eax
0x180070563  test    eax, eax
0x180070565  js      loc_180070432
0x18007056b  mov     eax, [rbp+210h+var_248]
0x18007056e  lea     rcx, [rsp+310h+GuidString]; GuidString
0x180070573  mov     [rsp+310h+GuidString.Length], ax
0x180070578  mov     [rsp+310h+GuidString.MaximumLength], ax
0x18007057d  lea     rax, [rbp+210h+var_244]
0x180070581  mov     edx, esi
0x180070583  shl     rdx, 4
0x180070587  add     rdx, r14; Guid
0x18007058a  mov     dword ptr [rsp+310h+GuidString+4], 0
0x180070592  mov     [rbp+210h+GuidString.Buffer], rax
0x180070596  call    cs:__imp_RtlGUIDFromString
0x18007059d  nop     dword ptr [rax+rax+00h]
0x1800705a2  mov     ebx, eax
0x1800705a4  test    eax, eax
0x1800705a6  js      loc_180070432
0x1800705ac  mov     rcx, [rsp+310h+Handle]; Handle
0x1800705b1  call    cs:__imp_ZwClose
0x1800705b8  nop     dword ptr [rax+rax+00h]
0x1800705bd  xor     eax, eax
0x1800705bf  mov     [rsp+310h+Destination.Length], ax
0x1800705c4  inc     esi
0x1800705c6  mov     [rsp+310h+Handle], rax
0x1800705cb  jmp     loc_18007044D
0x1800705d0  mov     [r15], r14
0x1800705d3  mov     [r12], edi
0x1800705d7  mov     rcx, [rsp+310h+Handle]; Handle
0x1800705dc  test    rcx, rcx
0x1800705df  jz      short loc_1800705ED
0x1800705e1  call    cs:__imp_ZwClose
0x1800705e8  nop     dword ptr [rax+rax+00h]
0x1800705ed  lea     rcx, [rsp+310h+Destination]; UnicodeString
0x1800705f2  call    cs:__imp_RtlFreeUnicodeString
0x1800705f9  nop     dword ptr [rax+rax+00h]
0x1800705fe  mov     rcx, [rsp+310h+KeyHandle]; Handle
0x180070603  call    cs:__imp_ZwClose
0x18007060a  nop     dword ptr [rax+rax+00h]
0x18007060f  mov     eax, ebx
0x180070611  mov     rcx, [rbp+210h+var_30]
0x180070618  xor     rcx, rsp; StackCookie
0x18007061b  call    __security_check_cookie
0x180070620  lea     r11, [rsp+310h+var_20]
0x180070628  mov     rbx, [r11+40h]
0x18007062c  mov     rsi, [r11+48h]
0x180070630  mov     rsp, r11
0x180070633  pop     r15
0x180070635  pop     r14
0x180070637  pop     r12
0x180070639  pop     rdi
0x18007063a  pop     rbp
0x18007063b  retn
```
