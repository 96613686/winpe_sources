# CipGetTenantIds

- ea: `0x18006efe0`
- end: `0x18006f38d`
- name: `CipGetTenantIds`
- size: `941`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180057408`

## callees

- `0x18002bef0`
- `0x18002c340`
- `0x18006efe0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18006f342`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006f342`
- `ntoskrnl!ExAllocatePool2` at `0x18006f13b`
- `ntoskrnl!ExAllocatePool2` at `0x18006f167`
- `ntoskrnl!ExAllocatePool2` at `0x18006f13b`
- `ntoskrnl!ExAllocatePool2` at `0x18006f167`
- `ntoskrnl!ZwQueryValueKey` at `0x18006f2a5`
- `ntoskrnl!ZwQueryValueKey` at `0x18006f2a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006f18a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006f18a`
- `ntoskrnl!ZwClose` at `0x18006f301`
- `ntoskrnl!ZwClose` at `0x18006f331`
- `ntoskrnl!ZwClose` at `0x18006f353`
- `ntoskrnl!ZwClose` at `0x18006f301`
- `ntoskrnl!ZwClose` at `0x18006f331`
- `ntoskrnl!ZwClose` at `0x18006f353`
- `ntoskrnl!ZwOpenKey` at `0x18006f0af`
- `ntoskrnl!ZwOpenKey` at `0x18006f269`
- `ntoskrnl!ZwOpenKey` at `0x18006f0af`
- `ntoskrnl!ZwOpenKey` at `0x18006f269`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18006f1e1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18006f1e1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18006f1ff`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18006f21e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18006f1ff`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18006f21e`
- `ntoskrnl!RtlGUIDFromString` at `0x18006f2e6`
- `ntoskrnl!RtlGUIDFromString` at `0x18006f2e6`
- `ntoskrnl!ZwEnumerateKey` at `0x18006f0e1`
- `ntoskrnl!ZwEnumerateKey` at `0x18006f1c5`
- `ntoskrnl!ZwEnumerateKey` at `0x18006f0e1`
- `ntoskrnl!ZwEnumerateKey` at `0x18006f1c5`

## string_xrefs

- `0x18006f012`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\CI\Enrollments`

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
0x18006efe0  mov     [rsp-8+arg_10], rbx
0x18006efe5  mov     [rsp-8+arg_18], rsi
0x18006efea  push    rbp
0x18006efeb  push    rdi
0x18006efec  push    r12
0x18006efee  push    r14
0x18006eff0  push    r15
0x18006eff2  lea     rbp, [rsp-1F0h]
0x18006effa  sub     rsp, 2F0h
0x18006f001  mov     rax, cs:__security_cookie
0x18006f008  xor     rax, rsp
0x18006f00b  mov     [rbp+210h+var_30], rax
0x18006f012  lea     rax, aRegistryMachin_10; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x18006f019  mov     [rsp+310h+KeyHandle], 0
0x18006f022  mov     [rsp+310h+Source.Buffer], rax
0x18006f027  mov     r12, rdx
0x18006f02a  lea     rax, aTenantid; "TenantID"
0x18006f031  mov     [rsp+310h+Handle], 0
0x18006f03a  mov     r15, rcx
0x18006f03d  mov     [rsp+310h+ValueName.Buffer], rax
0x18006f042  xorps   xmm0, xmm0
0x18006f045  mov     qword ptr [rsp+310h+Source.Length], 840082h
0x18006f04e  mov     esi, 220h
0x18006f053  mov     qword ptr [rsp+310h+ValueName.Length], 120010h
0x18006f05c  mov     r8d, esi; Size
0x18006f05f  mov     qword ptr [rbp+210h+ObjectAttributes.Length], 30h ; '0'
0x18006f067  xor     edx, edx; Val
0x18006f069  mov     qword ptr [rbp+210h+ObjectAttributes.Attributes], 240h
0x18006f071  lea     rcx, [rbp+210h+KeyInformation]; void *
0x18006f075  xor     edi, edi
0x18006f077  movups  xmmword ptr [rsp+310h+Destination.Length], xmm0
0x18006f07c  call    memset
0x18006f081  lea     rax, [rsp+310h+Source]
0x18006f086  mov     [r12], edi
0x18006f08a  xorps   xmm0, xmm0
0x18006f08d  mov     [rbp+210h+ObjectAttributes.ObjectName], rax
0x18006f091  lea     r8, [rbp+210h+ObjectAttributes]; ObjectAttributes
0x18006f095  mov     [rsp+310h+var_2E0], edi
0x18006f099  mov     edx, 20019h; DesiredAccess
0x18006f09e  mov     [r15], rdi
0x18006f0a1  lea     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x18006f0a6  mov     [rbp+210h+ObjectAttributes.RootDirectory], rdi
0x18006f0aa  movdqu  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006f0af  call    cs:__imp_ZwOpenKey
0x18006f0b6  nop     dword ptr [rax+rax+00h]
0x18006f0bb  mov     ebx, eax
0x18006f0bd  test    eax, eax
0x18006f0bf  js      loc_18006F327
0x18006f0c5  mov     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x18006f0ca  lea     rax, [rsp+310h+var_2E0]
0x18006f0cf  mov     [rsp+310h+ResultLength], rax; ResultLength
0x18006f0d4  lea     r9, [rbp+210h+KeyInformation]; KeyInformation
0x18006f0d8  xor     r8d, r8d; KeyInformationClass
0x18006f0db  mov     [rsp+310h+Length], esi; Length
0x18006f0df  mov     edx, edi; Index
0x18006f0e1  call    cs:__imp_ZwEnumerateKey
0x18006f0e8  nop     dword ptr [rax+rax+00h]
0x18006f0ed  mov     ebx, eax
0x18006f0ef  cmp     eax, 8000001Ah
0x18006f0f4  jz      short loc_18006F120
0x18006f0f6  test    eax, eax
0x18006f0f8  js      loc_18006F327
0x18006f0fe  movzx   eax, [rsp+310h+Destination.MaximumLength]
0x18006f103  movzx   ecx, [rbp+210h+var_244]
0x18006f107  add     cx, 4
0x18006f10b  add     cx, [rsp+310h+Source.Length]
0x18006f110  cmp     cx, ax
0x18006f113  cmova   ax, cx
0x18006f117  inc     edi
0x18006f119  mov     [rsp+310h+Destination.MaximumLength], ax
0x18006f11e  jmp     short loc_18006F0C5
0x18006f120  test    edi, edi
0x18006f122  jz      loc_18006F327
0x18006f128  mov     edx, edi
0x18006f12a  mov     esi, 102h
0x18006f12f  shl     rdx, 4
0x18006f133  mov     ecx, esi
0x18006f135  mov     r8d, 63734943h
0x18006f13b  call    cs:__imp_ExAllocatePool2
0x18006f142  nop     dword ptr [rax+rax+00h]
0x18006f147  mov     r14, rax
0x18006f14a  test    rax, rax
0x18006f14d  jnz     short loc_18006F159
0x18006f14f  mov     ebx, 0C0000017h
0x18006f154  jmp     loc_18006F327
0x18006f159  movzx   edx, [rsp+310h+Destination.MaximumLength]
0x18006f15e  mov     r8d, 72634943h
0x18006f164  mov     rcx, rsi
0x18006f167  call    cs:__imp_ExAllocatePool2
0x18006f16e  nop     dword ptr [rax+rax+00h]
0x18006f173  mov     [rsp+310h+Destination.Buffer], rax
0x18006f178  test    rax, rax
0x18006f17b  jnz     short loc_18006F19B
0x18006f17d  mov     ebx, 0C0000017h
0x18006f182  mov     edx, 63734943h; Tag
0x18006f187  mov     rcx, r14; P
0x18006f18a  call    cs:__imp_ExFreePoolWithTag
0x18006f191  nop     dword ptr [rax+rax+00h]
0x18006f196  jmp     loc_18006F327
0x18006f19b  xor     esi, esi
0x18006f19d  cmp     esi, edi
0x18006f19f  jnb     loc_18006F320
0x18006f1a5  mov     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x18006f1aa  lea     rax, [rsp+310h+var_2E0]
0x18006f1af  mov     [rsp+310h+ResultLength], rax; ResultLength
0x18006f1b4  lea     r9, [rbp+210h+KeyInformation]; KeyInformation
0x18006f1b8  xor     r8d, r8d; KeyInformationClass
0x18006f1bb  mov     [rsp+310h+Length], 220h; Length
0x18006f1c3  mov     edx, esi; Index
0x18006f1c5  call    cs:__imp_ZwEnumerateKey
0x18006f1cc  nop     dword ptr [rax+rax+00h]
0x18006f1d1  mov     ebx, eax
0x18006f1d3  test    eax, eax
0x18006f1d5  js      short loc_18006F182
0x18006f1d7  lea     rdx, [rsp+310h+Source]; Source
0x18006f1dc  lea     rcx, [rsp+310h+Destination]; Destination
0x18006f1e1  call    cs:__imp_RtlAppendUnicodeStringToString
0x18006f1e8  nop     dword ptr [rax+rax+00h]
0x18006f1ed  mov     ebx, eax
0x18006f1ef  test    eax, eax
0x18006f1f1  js      short loc_18006F182
0x18006f1f3  lea     rdx, asc_1800332C8; "\\"
0x18006f1fa  lea     rcx, [rsp+310h+Destination]; Destination
0x18006f1ff  call    cs:__imp_RtlAppendUnicodeToString
0x18006f206  nop     dword ptr [rax+rax+00h]
0x18006f20b  mov     ebx, eax
0x18006f20d  test    eax, eax
0x18006f20f  js      loc_18006F182
0x18006f215  lea     rdx, [rbp+210h+var_240]; Source
0x18006f219  lea     rcx, [rsp+310h+Destination]; Destination
0x18006f21e  call    cs:__imp_RtlAppendUnicodeToString
0x18006f225  nop     dword ptr [rax+rax+00h]
0x18006f22a  mov     ebx, eax
0x18006f22c  test    eax, eax
0x18006f22e  js      loc_18006F182
0x18006f234  lea     rax, [rsp+310h+Destination]
0x18006f239  mov     [rbp+210h+ObjectAttributes.Length], 30h ; '0'
0x18006f240  xorps   xmm0, xmm0
0x18006f243  mov     [rbp+210h+ObjectAttributes.ObjectName], rax
0x18006f247  lea     r8, [rbp+210h+ObjectAttributes]; ObjectAttributes
0x18006f24b  mov     [rbp+210h+ObjectAttributes.RootDirectory], 0
0x18006f253  mov     edx, 20019h; DesiredAccess
0x18006f258  mov     [rbp+210h+ObjectAttributes.Attributes], 240h
0x18006f25f  lea     rcx, [rsp+310h+Handle]; KeyHandle
0x18006f264  movdqu  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006f269  call    cs:__imp_ZwOpenKey
0x18006f270  nop     dword ptr [rax+rax+00h]
0x18006f275  mov     ebx, eax
0x18006f277  test    eax, eax
0x18006f279  js      loc_18006F182
0x18006f27f  mov     rcx, [rsp+310h+Handle]; KeyHandle
0x18006f284  lea     rax, [rsp+310h+var_2E0]
0x18006f289  mov     [rsp+310h+ResultLength], rax; ResultLength
0x18006f28e  lea     r9, [rbp+210h+KeyInformation]; KeyValueInformation
0x18006f292  mov     r8d, 2; KeyValueInformationClass
0x18006f298  mov     [rsp+310h+Length], 220h; Length
0x18006f2a0  lea     rdx, [rsp+310h+ValueName]; ValueName
0x18006f2a5  call    cs:__imp_ZwQueryValueKey
0x18006f2ac  nop     dword ptr [rax+rax+00h]
0x18006f2b1  mov     ebx, eax
0x18006f2b3  test    eax, eax
0x18006f2b5  js      loc_18006F182
0x18006f2bb  mov     eax, [rbp+210h+var_248]
0x18006f2be  lea     rcx, [rsp+310h+GuidString]; GuidString
0x18006f2c3  mov     [rsp+310h+GuidString.Length], ax
0x18006f2c8  mov     [rsp+310h+GuidString.MaximumLength], ax
0x18006f2cd  lea     rax, [rbp+210h+var_244]
0x18006f2d1  mov     edx, esi
0x18006f2d3  shl     rdx, 4
0x18006f2d7  add     rdx, r14; Guid
0x18006f2da  mov     dword ptr [rsp+310h+GuidString+4], 0
0x18006f2e2  mov     [rbp+210h+GuidString.Buffer], rax
0x18006f2e6  call    cs:__imp_RtlGUIDFromString
0x18006f2ed  nop     dword ptr [rax+rax+00h]
0x18006f2f2  mov     ebx, eax
0x18006f2f4  test    eax, eax
0x18006f2f6  js      loc_18006F182
0x18006f2fc  mov     rcx, [rsp+310h+Handle]; Handle
0x18006f301  call    cs:__imp_ZwClose
0x18006f308  nop     dword ptr [rax+rax+00h]
0x18006f30d  xor     eax, eax
0x18006f30f  mov     [rsp+310h+Destination.Length], ax
0x18006f314  inc     esi
0x18006f316  mov     [rsp+310h+Handle], rax
0x18006f31b  jmp     loc_18006F19D
0x18006f320  mov     [r15], r14
0x18006f323  mov     [r12], edi
0x18006f327  mov     rcx, [rsp+310h+Handle]; Handle
0x18006f32c  test    rcx, rcx
0x18006f32f  jz      short loc_18006F33D
0x18006f331  call    cs:__imp_ZwClose
0x18006f338  nop     dword ptr [rax+rax+00h]
0x18006f33d  lea     rcx, [rsp+310h+Destination]; UnicodeString
0x18006f342  call    cs:__imp_RtlFreeUnicodeString
0x18006f349  nop     dword ptr [rax+rax+00h]
0x18006f34e  mov     rcx, [rsp+310h+KeyHandle]; Handle
0x18006f353  call    cs:__imp_ZwClose
0x18006f35a  nop     dword ptr [rax+rax+00h]
0x18006f35f  mov     eax, ebx
0x18006f361  mov     rcx, [rbp+210h+var_30]
0x18006f368  xor     rcx, rsp; StackCookie
0x18006f36b  call    __security_check_cookie
0x18006f370  lea     r11, [rsp+310h+var_20]
0x18006f378  mov     rbx, [r11+40h]
0x18006f37c  mov     rsi, [r11+48h]
0x18006f380  mov     rsp, r11
0x18006f383  pop     r15
0x18006f385  pop     r14
0x18006f387  pop     r12
0x18006f389  pop     rdi
0x18006f38a  pop     rbp
0x18006f38b  retn
```
