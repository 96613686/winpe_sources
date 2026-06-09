# ExpSetPendingUILanguage

- ea: `0x140ab79c0`
- end: `0x140ab7fee`
- name: `ExpSetPendingUILanguage`
- size: `1582`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140ab79a0`

## callees

- `0x1402a2f90`
- `0x140387f20`
- `0x140403380`
- `0x1404cd20c`
- `0x1404d5240`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406dd640`
- `0x1406dd6c0`
- `0x1406dd780`
- `0x1406ddfe0`
- `0x1406def60`
- `0x1406defc0`
- `0x1406f6f80`
- `0x1406f7380`
- `0x140724e08`
- `0x140ab79c0`
- `0x140ac0f20`

## string_xrefs

- `0x140ab7b8c`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings`
- `0x140b774fc`: `Control Panel\Desktop\LanguageConfigurationPending`
- `0x140ab7b35`: `Control Panel\Desktop\MuiCached`
- `0x140b776ba`: `Control Panel\Desktop\MuiCached`
- `0x140b775a6`: `Control Panel\Desktop\LanguageConfiguration`
- `0x140b77944`: `*** MUI: Can't copy language name for LanguageConfig item %S\n`
- `0x140b777b0`: `*** MUI: Failed to delete value %S from MachineLanguageConfiguration!\n`
- `0x140ab7bee`: `MachineLanguageConfiguration`
- `0x140b7786f`: `MachineLanguageConfiguration`
- `0x140b7795e`: `*** MUI: Can't copy language name for LanguageConfig item %u\n`
- `0x140ab7c4a`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings\LanguageConfiguration`

## pseudocode

```c
__int64 ExpSetPendingUILanguage()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 result; // rax
  char v3; // r15
  char v4; // r12
  NTSTATUS v5; // ebx
  ULONG i; // edi
  struct _KTHREAD *CurrentThread; // rcx
  char *Teb; // rcx
  int v9; // ebx
  ULONG v10; // eax
  ULONG v11; // ebx
  NTSTATUS v12; // edi
  unsigned int v13; // r14d
  HANDLE v14; // rcx
  NTSTATUS v15; // [rsp+40h] [rbp-4A8h] BYREF
  ULONG ResultLength; // [rsp+44h] [rbp-4A4h] BYREF
  HANDLE v17; // [rsp+48h] [rbp-4A0h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-498h] BYREF
  HANDLE v19; // [rsp+58h] [rbp-490h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-488h] BYREF
  UNICODE_STRING DestinationString; // [rsp+90h] [rbp-458h] BYREF
  UNICODE_STRING ValueName; // [rsp+A0h] [rbp-448h] BYREF
  HANDLE v23; // [rsp+B0h] [rbp-438h] BYREF
  HANDLE v24; // [rsp+B8h] [rbp-430h] BYREF
  HANDLE KeyHandle; // [rsp+C0h] [rbp-428h] BYREF
  UNICODE_STRING v26; // [rsp+D0h] [rbp-418h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+E0h] [rbp-408h] BYREF
  int v28; // [rsp+E4h] [rbp-404h]
  ULONG DataSize; // [rsp+E8h] [rbp-400h]
  WCHAR Data[122]; // [rsp+ECh] [rbp-3FCh] BYREF
  WCHAR SourceString[88]; // [rsp+1E0h] [rbp-308h] BYREF
  _BYTE v32[4]; // [rsp+290h] [rbp-258h] BYREF
  int v33; // [rsp+294h] [rbp-254h]
  ULONG v34[2]; // [rsp+298h] [rbp-250h] BYREF
  unsigned int Size; // [rsp+2A0h] [rbp-248h]
  size_t Size_4; // [rsp+2A4h] [rbp-244h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  ValueName = 0;
  v26 = 0;
  v23 = 0;
  Handle = 0;
  memset_0(SourceString, 0, 0xAAu);
  ResultLength = 0;
  KeyHandle = 0;
  v24 = 0;
  v17 = 0;
  v19 = 0;
  result = OpenGlobalizationUserSettingsKey(v1, v0, &v23);
  if ( (int)result < 0 )
    return result;
  v3 = 1;
  v4 = 0;
  RtlInitUnicodeString(&DestinationString, L"Control Panel\\Desktop");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v23;
  ObjectAttributes.Attributes = 1600;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(&KeyHandle, 0x40000000u, &ObjectAttributes);
  v15 = v5;
  if ( v5 < 0 )
    goto LABEL_10;
  RtlInitUnicodeString(&ValueName, L"PreferredUILanguagesPending");
  if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x100u, &ResultLength) >= 0
    && DataSize >= 4
    && v28 == 7 )
  {
    RtlInitUnicodeString(&ValueName, L"PreferredUILanguages");
    if ( ZwSetValueKey(KeyHandle, &ValueName, 0, 7u, Data, DataSize) >= 0 )
    {
      v4 = 1;
      if ( DataSize + 12 < 0x100 )
      {
        Data[((unsigned __int64)DataSize >> 1) - 1] = 0;
        RtlInitUnicodeString(&ValueName, L"PreferredUILanguagesPending");
        ZwDeleteValueKey(KeyHandle, &ValueName);
        RtlInitUnicodeString(&v26, Data);
        RtlInitUnicodeString(&DestinationString, L"Control Panel\\Desktop\\LanguageConfigurationPending");
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = v23;
        ObjectAttributes.Attributes = 1600;
        ObjectAttributes.ObjectName = &DestinationString;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenKey(&v24, 0x40000000u, &ObjectAttributes) >= 0
          && ZwQueryValueKey(v24, &v26, KeyValuePartialInformation, v32, 0x210u, &ResultLength) >= 0
          && v33 == 7 )
        {
          RtlInitUnicodeString(&DestinationString, L"Control Panel\\Desktop\\LanguageConfiguration");
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = v23;
          ObjectAttributes.Attributes = 1600;
          ObjectAttributes.ObjectName = &DestinationString;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( ZwCreateKey(&Handle, 0x40000000u, &ObjectAttributes, 0, 0, 0, 0) >= 0 )
          {
            if ( ZwSetValueKey(Handle, &v26, 0, 7u, &v34[1], v34[0]) >= 0 )
              ZwDeleteValueKey(v24, &v26);
            ZwClose(Handle);
          }
        }
      }
    }
  }
  RtlInitUnicodeString(&DestinationString, L"Control Panel\\Desktop\\MuiCached");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v23;
  ObjectAttributes.Attributes = 1600;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ZwOpenKey(&v17, 0x40000000u, &ObjectAttributes);
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\Settings");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 1600;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&Handle, 0x80000000, &ObjectAttributes) < 0 )
  {
    if ( v17 )
    {
      RtlInitUnicodeString(&ValueName, L"MachinePreferredUILanguages");
      ZwDeleteValueKey(v17, &ValueName);
    }
LABEL_7:
    RtlInitUnicodeString(&DestinationString, L"MachineLanguageConfiguration");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = v17;
    ObjectAttributes.Attributes = 1600;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&v19, 0x40000000u, &ObjectAttributes) >= 0 )
    {
      v11 = 0;
      do
      {
        memset_0(KeyValueInformation, 0, 0x100u);
        v12 = ZwEnumerateValueKey(v19, v11, KeyValueBasicInformation, KeyValueInformation, 0xFEu, &ResultLength);
        if ( v12 >= 0 )
        {
          RtlInitUnicodeString(&ValueName, Data);
          if ( ZwDeleteValueKey(v19, &ValueName) < 0 )
          {
            DbgPrint("*** MUI: Failed to delete value %S from MachineLanguageConfiguration!\n", Data);
            ++v11;
          }
        }
      }
      while ( v12 >= 0 );
    }
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\Settings\\LanguageConfiguration");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 1600;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&Handle, 0x80000000, &ObjectAttributes) >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        memset_0(v32, 0, 0x210u);
        v5 = ZwEnumerateValueKey(Handle, i, KeyValueFullInformation, v32, 0x20Eu, &ResultLength);
        v15 = v5;
        if ( v5 >= 0 )
        {
          v13 = Size;
          if ( (unsigned __int64)Size + 24 <= 0x210 && v34[0] + v34[1] <= 0x210 && v33 == 7 && Size < 0xAA )
          {
            memset_0(SourceString, 0, 0xAAu);
            memmove(SourceString, &Size_4, v13);
            RtlInitUnicodeString(&ValueName, SourceString);
            v14 = v19;
            if ( !v19 )
            {
              RtlInitUnicodeString(&DestinationString, L"MachineLanguageConfiguration");
              ObjectAttributes.Length = 48;
              ObjectAttributes.RootDirectory = v17;
              ObjectAttributes.Attributes = 1600;
              ObjectAttributes.ObjectName = &DestinationString;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              v5 = ZwCreateKey(&v19, 0x40000000u, &ObjectAttributes, 0, 0, 1u, 0);
              v15 = v5;
              if ( v5 < 0 )
                goto LABEL_10;
              v3 = 0;
              v14 = v19;
            }
            v5 = ZwSetValueKey(v14, &ValueName, 0, 7u, &v32[v34[0]], v34[1]);
            v15 = v5;
            if ( v5 < 0 )
            {
              DbgPrint("*** MUI: Can't copy language name for LanguageConfig item %S\n", SourceString);
              v5 = 0;
              v15 = 0;
            }
          }
          else
          {
            DbgPrint("*** MUI: Can't copy language name for LanguageConfig item %u\n", i);
          }
        }
        if ( v5 < 0 )
          break;
      }
      ZwClose(Handle);
    }
    else
    {
      v5 = 0;
      v15 = 0;
    }
    goto LABEL_10;
  }
  RtlInitUnicodeString(&ValueName, L"PreferredUILanguages");
  if ( ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x100u, &ResultLength) < 0
    || DataSize < 4
    || v28 != 7 )
  {
    LOWORD(v15) = 0;
    DataSize = 0;
    v9 = NtQueryInstallUILanguage(&v15);
    if ( v9 >= 0 )
    {
      v10 = DownLevelLangIDToLanguageName((unsigned __int16)v15, Data, 128, 0);
      DataSize = v10;
      if ( !v10 )
      {
        v9 = -1073741823;
        goto LABEL_62;
      }
      DataSize = 2 * v10;
    }
    if ( v9 >= 0 )
      goto LABEL_29;
LABEL_62:
    DbgPrintEx(0xFFFFFFFF, 0, "sysinfo: Can't set MachinePreferredUILanguages due to error %d\n", v9);
    if ( v17 )
      ZwDeleteValueKey(v17, &ValueName);
    goto LABEL_32;
  }
LABEL_29:
  if ( v17 )
    goto LABEL_30;
  RtlInitUnicodeString(&DestinationString, L"Control Panel\\Desktop\\MuiCached");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v23;
  ObjectAttributes.Attributes = 1600;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwCreateKey(&v17, 0x40000000u, &ObjectAttributes, 0, 0, 1u, 0);
  v15 = v5;
  if ( v5 >= 0 )
  {
LABEL_30:
    RtlInitUnicodeString(&ValueName, L"MachinePreferredUILanguages");
    if ( ZwSetValueKey(v17, &ValueName, 0, 7u, Data, DataSize) < 0 )
      DbgPrintEx(0xFFFFFFFF, 0, "sysinfo: Can't set MachinePreferredUILanguages\n");
LABEL_32:
    ZwClose(Handle);
    goto LABEL_7;
  }
LABEL_10:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v24 )
  {
    if ( ZwEnumerateValueKey(v24, 0, KeyValueBasicInformation, 0, 0, &ResultLength) == -2147483622 )
      ZwDeleteKey(v24);
    ZwClose(v24);
  }
  if ( v17 )
  {
    if ( !v19 || v3 && ZwEnumerateValueKey(v19, 0, KeyValueBasicInformation, 0, 0, &ResultLength) == -2147483622 )
    {
      if ( v19 )
        ZwDeleteKey(v19);
      if ( ZwEnumerateValueKey(v17, 0, KeyValueBasicInformation, 0, 0, &ResultLength) == -2147483622 )
        ZwDeleteKey(v17);
    }
    ZwClose(v17);
  }
  if ( v19 )
    ZwClose(v19);
  if ( v23 )
    ZwClose(v23);
  if ( v4 == 1 )
  {
    CurrentThread = KeGetCurrentThread();
    if ( (CurrentThread->MiscFlags & 0x400) != 0 || CurrentThread->ApcStateIndex == 1 )
      Teb = 0;
    else
      Teb = (char *)CurrentThread->Teb;
    if ( Teb )
      RtlWriteULongToUser(Teb + 6120, 0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140ab79c0  push    rbx
0x140ab79c2  push    rdi
0x140ab79c3  push    r12
0x140ab79c5  push    r13
0x140ab79c7  push    r14
0x140ab79c9  push    r15
0x140ab79cb  sub     rsp, 4B8h
0x140ab79d2  mov     rax, cs:__security_cookie
0x140ab79d9  xor     rax, rsp
0x140ab79dc  mov     [rsp+4E8h+var_48], rax
0x140ab79e4  xor     eax, eax
0x140ab79e6  xorps   xmm0, xmm0
0x140ab79e9  movups  xmmword ptr [rsp+4E8h+ObjectAttributes.Length], xmm0
0x140ab79ee  movups  xmmword ptr [rsp+4E8h+ObjectAttributes.ObjectName], xmm0
0x140ab79f3  movups  xmmword ptr [rsp+4E8h+ObjectAttributes+1Ch], xmm0
0x140ab79f8  movups  xmmword ptr [rsp+4E8h+DestinationString.Length], xmm0
0x140ab7a00  xorps   xmm1, xmm1
0x140ab7a03  movups  xmmword ptr [rsp+4E8h+ValueName.Length], xmm1
0x140ab7a0b  movups  xmmword ptr [rsp+4E8h+var_418.Length], xmm0
0x140ab7a13  xor     r13d, r13d
0x140ab7a16  mov     [rsp+4E8h+var_438], r13
0x140ab7a1e  mov     [rsp+4E8h+Handle], r13
0x140ab7a23  xor     edx, edx; Val
0x140ab7a25  mov     r8d, 0AAh; Size
0x140ab7a2b  lea     rcx, [rsp+4E8h+SourceString]; void *
0x140ab7a33  call    memset_0
0x140ab7a38  mov     [rsp+4E8h+var_4A4], r13d
0x140ab7a3d  mov     [rsp+4E8h+KeyHandle], r13
0x140ab7a45  mov     [rsp+4E8h+var_430], r13
0x140ab7a4d  mov     [rsp+4E8h+var_4A0], r13
0x140ab7a52  mov     [rsp+4E8h+var_490], r13
0x140ab7a57  lea     r8, [rsp+4E8h+var_438]
0x140ab7a5f  call    OpenGlobalizationUserSettingsKey
0x140ab7a64  test    eax, eax
0x140ab7a66  js      loc_140AB7D05
0x140ab7a6c  mov     r15b, 1
0x140ab7a6f  mov     r12b, r13b
0x140ab7a72  lea     rdx, aControlPanelDe_2; "Control Panel\\Desktop"
0x140ab7a79  lea     rcx, [rsp+4E8h+DestinationString]; DestinationString
0x140ab7a81  call    RtlInitUnicodeString
0x140ab7a86  lea     r14d, [r13+30h]
0x140ab7a8a  mov     [rsp+4E8h+ObjectAttributes.Length], r14d
0x140ab7a8f  mov     rax, [rsp+4E8h+var_438]
0x140ab7a97  mov     [rsp+4E8h+ObjectAttributes.RootDirectory], rax
0x140ab7a9c  mov     edi, 640h
0x140ab7aa1  mov     [rsp+4E8h+ObjectAttributes.Attributes], edi
0x140ab7aa5  lea     rax, [rsp+4E8h+DestinationString]
0x140ab7aad  mov     [rsp+4E8h+ObjectAttributes.ObjectName], rax
0x140ab7ab2  xorps   xmm0, xmm0
0x140ab7ab5  movdqu  xmmword ptr [rsp+4E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140ab7abe  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x140ab7ac3  mov     edx, 40000000h; DesiredAccess
0x140ab7ac8  lea     rcx, [rsp+4E8h+KeyHandle]; KeyHandle
0x140ab7ad0  call    ZwOpenKey
0x140ab7ad5  mov     ebx, eax
0x140ab7ad7  mov     [rsp+4E8h+var_4A8], eax
0x140ab7adb  test    eax, eax
0x140ab7add  js      loc_140AB7CA8
0x140ab7ae3  lea     rdx, aPreferreduilan; "PreferredUILanguagesPending"
0x140ab7aea  lea     rcx, [rsp+4E8h+ValueName]; DestinationString
0x140ab7af2  call    RtlInitUnicodeString
0x140ab7af7  lea     rax, [rsp+4E8h+var_4A4]
0x140ab7afc  mov     [rsp+4E8h+ResultLength], rax; ResultLength
0x140ab7b01  mov     [rsp+4E8h+Length], 100h; Length
0x140ab7b09  lea     r9, [rsp+4E8h+KeyValueInformation]; KeyValueInformation
0x140ab7b11  lea     ebx, [r13+2]
0x140ab7b15  mov     r8d, ebx; KeyValueInformationClass
0x140ab7b18  lea     rdx, [rsp+4E8h+ValueName]; ValueName
0x140ab7b20  mov     rcx, [rsp+4E8h+KeyHandle]; KeyHandle
0x140ab7b28  call    ZwQueryValueKey
0x140ab7b2d  test    eax, eax
0x140ab7b2f  jns     loc_140B7742C
0x140ab7b35  lea     rdx, aControlPanelDe_0; "Control Panel\\Desktop\\MuiCached"
0x140ab7b3c  lea     rcx, [rsp+4E8h+DestinationString]; DestinationString
0x140ab7b44  call    RtlInitUnicodeString
0x140ab7b49  mov     [rsp+4E8h+ObjectAttributes.Length], r14d
0x140ab7b4e  mov     rax, [rsp+4E8h+var_438]
0x140ab7b56  mov     [rsp+4E8h+ObjectAttributes.RootDirectory], rax
0x140ab7b5b  mov     [rsp+4E8h+ObjectAttributes.Attributes], edi
0x140ab7b5f  lea     rax, [rsp+4E8h+DestinationString]
0x140ab7b67  mov     [rsp+4E8h+ObjectAttributes.ObjectName], rax
0x140ab7b6c  xorps   xmm0, xmm0
0x140ab7b6f  movdqu  xmmword ptr [rsp+4E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140ab7b78  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x140ab7b7d  mov     edx, 40000000h; DesiredAccess
0x140ab7b82  lea     rcx, [rsp+4E8h+var_4A0]; KeyHandle
0x140ab7b87  call    ZwOpenKey
0x140ab7b8c  lea     rdx, aRegistryMachin_88; "\\Registry\\Machine\\System\\CurrentCon"...
0x140ab7b93  lea     rcx, [rsp+4E8h+DestinationString]; DestinationString
0x140ab7b9b  call    RtlInitUnicodeString
0x140ab7ba0  mov     [rsp+4E8h+ObjectAttributes.Length], r14d
0x140ab7ba5  mov     [rsp+4E8h+ObjectAttributes.RootDirectory], r13
0x140ab7baa  mov     [rsp+4E8h+ObjectAttributes.Attributes], edi
0x140ab7bae  lea     rax, [rsp+4E8h+DestinationString]
0x140ab7bb6  mov     [rsp+4E8h+ObjectAttributes.ObjectName], rax
0x140ab7bbb  xorps   xmm0, xmm0
0x140ab7bbe  movdqu  xmmword ptr [rsp+4E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140ab7bc7  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x140ab7bcc  mov     edx, 80000000h; DesiredAccess
0x140ab7bd1  lea     rcx, [rsp+4E8h+Handle]; KeyHandle
0x140ab7bd6  call    ZwOpenKey
0x140ab7bdb  test    eax, eax
0x140ab7bdd  jns     loc_140AB7D9B
0x140ab7be3  cmp     [rsp+4E8h+var_4A0], r13
0x140ab7be8  jnz     loc_140AB7E9A
0x140ab7bee  lea     rdx, aMachinelanguag; "MachineLanguageConfiguration"
0x140ab7bf5  lea     rcx, [rsp+4E8h+DestinationString]; DestinationString
0x140ab7bfd  call    RtlInitUnicodeString
0x140ab7c02  mov     [rsp+4E8h+ObjectAttributes.Length], r14d
0x140ab7c07  mov     rax, [rsp+4E8h+var_4A0]
0x140ab7c0c  mov     [rsp+4E8h+ObjectAttributes.RootDirectory], rax
0x140ab7c11  mov     [rsp+4E8h+ObjectAttributes.Attributes], edi
0x140ab7c15  lea     rax, [rsp+4E8h+DestinationString]
0x140ab7c1d  mov     [rsp+4E8h+ObjectAttributes.ObjectName], rax
0x140ab7c22  xorps   xmm0, xmm0
0x140ab7c25  movdqu  xmmword ptr [rsp+4E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140ab7c2e  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x140ab7c33  mov     edx, 40000000h; DesiredAccess
0x140ab7c38  lea     rcx, [rsp+4E8h+var_490]; KeyHandle
0x140ab7c3d  call    ZwOpenKey
0x140ab7c42  test    eax, eax
0x140ab7c44  jns     loc_140AB7F31
0x140ab7c4a  lea     rdx, aRegistryMachin_247; "\\Registry\\Machine\\System\\CurrentCon"...
0x140ab7c51  lea     rcx, [rsp+4E8h+DestinationString]; DestinationString
0x140ab7c59  call    RtlInitUnicodeString
0x140ab7c5e  mov     [rsp+4E8h+ObjectAttributes.Length], r14d
0x140ab7c63  mov     [rsp+4E8h+ObjectAttributes.RootDirectory], r13
0x140ab7c68  mov     [rsp+4E8h+ObjectAttributes.Attributes], edi
0x140ab7c6c  lea     rax, [rsp+4E8h+DestinationString]
0x140ab7c74  mov     [rsp+4E8h+ObjectAttributes.ObjectName], rax
0x140ab7c79  xorps   xmm0, xmm0
0x140ab7c7c  movdqu  xmmword ptr [rsp+4E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140ab7c85  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x140ab7c8a  mov     edx, 80000000h; DesiredAccess
0x140ab7c8f  lea     rcx, [rsp+4E8h+Handle]; KeyHandle
0x140ab7c94  call    ZwOpenKey
0x140ab7c99  test    eax, eax
0x140ab7c9b  jns     loc_140AB7D28
0x140ab7ca1  mov     ebx, r13d
0x140ab7ca4  mov     [rsp+4E8h+var_4A8], ebx
0x140ab7ca8  mov     rcx, [rsp+4E8h+KeyHandle]; Handle
0x140ab7cb0  test    rcx, rcx
0x140ab7cb3  jnz     loc_140AB7F39
0x140ab7cb9  mov     rcx, [rsp+4E8h+var_430]; KeyHandle
0x140ab7cc1  test    rcx, rcx
0x140ab7cc4  jnz     loc_140AB7F43
0x140ab7cca  mov     edi, 8000001Ah
0x140ab7ccf  cmp     [rsp+4E8h+var_4A0], r13
0x140ab7cd4  jnz     loc_140AB7F7F
0x140ab7cda  mov     rcx, [rsp+4E8h+var_490]; Handle
0x140ab7cdf  test    rcx, rcx
0x140ab7ce2  jnz     loc_140AB7FBF
0x140ab7ce8  mov     rcx, [rsp+4E8h+var_438]; Handle
0x140ab7cf0  test    rcx, rcx
0x140ab7cf3  jnz     loc_140AB7D91
0x140ab7cf9  cmp     r12b, 1
0x140ab7cfd  jz      loc_140AB7E6B
0x140ab7d03  mov     eax, ebx
0x140ab7d05  mov     rcx, [rsp+4E8h+var_48]
0x140ab7d0d  xor     rcx, rsp; StackCookie
0x140ab7d10  call    __security_check_cookie
0x140ab7d15  add     rsp, 4B8h
0x140ab7d1c  pop     r15
0x140ab7d1e  pop     r14
0x140ab7d20  pop     r13
0x140ab7d22  pop     r12
0x140ab7d24  pop     rdi
0x140ab7d25  pop     rbx
0x140ab7d26  retn
0x140ab7d28  mov     edi, r13d
0x140ab7d2b  xor     edx, edx; Val
0x140ab7d2d  mov     r8d, 210h; Size
0x140ab7d33  lea     rcx, [rsp+4E8h+var_258]; void *
0x140ab7d3b  call    memset_0
0x140ab7d40  lea     rax, [rsp+4E8h+var_4A4]
0x140ab7d45  mov     [rsp+4E8h+ResultLength], rax; ResultLength
0x140ab7d4a  mov     [rsp+4E8h+Length], 20Eh; Length
0x140ab7d52  lea     r9, [rsp+4E8h+var_258]; KeyValueInformation
0x140ab7d5a  mov     r8d, 1; KeyValueInformationClass
0x140ab7d60  mov     edx, edi; Index
0x140ab7d62  mov     rcx, [rsp+4E8h+Handle]; KeyHandle
0x140ab7d67  call    ZwEnumerateValueKey
0x140ab7d6c  mov     ebx, eax
0x140ab7d6e  mov     [rsp+4E8h+var_4A8], eax
0x140ab7d72  test    eax, eax
0x140ab7d74  jns     loc_140B777D0
0x140ab7d7a  test    ebx, ebx
0x140ab7d7c  jns     short loc_140AB7D8D
0x140ab7d7e  mov     rcx, [rsp+4E8h+Handle]; Handle
0x140ab7d83  call    ZwClose
0x140ab7d88  jmp     loc_140AB7CA8
0x140ab7d8d  inc     edi
0x140ab7d8f  jmp     short loc_140AB7D2B
0x140ab7d91  call    ZwClose
0x140ab7d96  jmp     loc_140AB7CF9
0x140ab7d9b  lea     rdx, aPreferreduilan_1; "PreferredUILanguages"
0x140ab7da2  lea     rcx, [rsp+4E8h+ValueName]; DestinationString
0x140ab7daa  call    RtlInitUnicodeString
0x140ab7daf  lea     rax, [rsp+4E8h+var_4A4]
0x140ab7db4  mov     [rsp+4E8h+ResultLength], rax; ResultLength
0x140ab7db9  mov     [rsp+4E8h+Length], 100h; Length
0x140ab7dc1  lea     r9, [rsp+4E8h+KeyValueInformation]; KeyValueInformation
0x140ab7dc9  mov     r8d, ebx; KeyValueInformationClass
0x140ab7dcc  lea     rdx, [rsp+4E8h+ValueName]; ValueName
0x140ab7dd4  mov     rcx, [rsp+4E8h+Handle]; KeyHandle
0x140ab7dd9  call    ZwQueryValueKey
0x140ab7dde  test    eax, eax
0x140ab7de0  js      loc_140AB7EC5
0x140ab7de6  cmp     [rsp+4E8h+DataSize], 4
0x140ab7dee  jb      loc_140AB7EC5
0x140ab7df4  cmp     [rsp+4E8h+var_404], 7
0x140ab7dfc  jnz     loc_140AB7EC5
0x140ab7e02  cmp     [rsp+4E8h+var_4A0], r13
0x140ab7e07  jz      loc_140B776BA
0x140ab7e0d  lea     rdx, aMachinepreferr; "MachinePreferredUILanguages"
0x140ab7e14  lea     rcx, [rsp+4E8h+ValueName]; DestinationString
0x140ab7e1c  call    RtlInitUnicodeString
0x140ab7e21  mov     eax, [rsp+4E8h+DataSize]
0x140ab7e28  mov     dword ptr [rsp+4E8h+ResultLength], eax; DataSize
0x140ab7e2c  lea     rax, [rsp+4E8h+Data]
0x140ab7e34  mov     qword ptr [rsp+4E8h+Length], rax; Data
0x140ab7e39  mov     r9d, 7; Type
0x140ab7e3f  xor     r8d, r8d; TitleIndex
0x140ab7e42  lea     rdx, [rsp+4E8h+ValueName]; ValueName
0x140ab7e4a  mov     rcx, [rsp+4E8h+var_4A0]; KeyHandle
0x140ab7e4f  call    ZwSetValueKey
0x140ab7e54  test    eax, eax
0x140ab7e56  js      loc_140AB7F1B
0x140ab7e5c  mov     rcx, [rsp+4E8h+Handle]; Handle
0x140ab7e61  call    ZwClose
0x140ab7e66  jmp     loc_140AB7BEE
0x140ab7e6b  mov     rcx, gs:188h
0x140ab7e74  test    dword ptr [rcx+74h], 400h
0x140ab7e7b  jnz     short loc_140AB7E86
0x140ab7e7d  cmp     byte ptr [rcx+24Ah], 1
0x140ab7e84  jnz     short loc_140AB7E8E
0x140ab7e86  mov     rcx, r13
0x140ab7e89  jmp     loc_140AB7FC9
0x140ab7e8e  mov     rcx, [rcx+0F0h]
0x140ab7e95  jmp     loc_140AB7FC9
0x140ab7e9a  lea     rdx, aMachinepreferr; "MachinePreferredUILanguages"
0x140ab7ea1  lea     rcx, [rsp+4E8h+ValueName]; DestinationString
0x140ab7ea9  call    RtlInitUnicodeString
0x140ab7eae  lea     rdx, [rsp+4E8h+ValueName]; ValueName
0x140ab7eb6  mov     rcx, [rsp+4E8h+var_4A0]; KeyHandle
0x140ab7ebb  call    ZwDeleteValueKey
0x140ab7ec0  jmp     loc_140AB7BEE
0x140ab7ec5  mov     word ptr [rsp+4E8h+var_4A8], r13w
0x140ab7ecb  mov     [rsp+4E8h+DataSize], r13d
0x140ab7ed3  lea     rcx, [rsp+4E8h+var_4A8]
0x140ab7ed8  call    NtQueryInstallUILanguage
0x140ab7edd  mov     ebx, eax
0x140ab7edf  test    eax, eax
0x140ab7ee1  js      loc_140B7767D
0x140ab7ee7  xor     r9d, r9d
0x140ab7eea  mov     r8d, 80h
0x140ab7ef0  lea     rdx, [rsp+4E8h+Data]
0x140ab7ef8  movzx   ecx, word ptr [rsp+4E8h+var_4A8]
0x140ab7efd  call    DownLevelLangIDToLanguageName
0x140ab7f02  mov     [rsp+4E8h+DataSize], eax
0x140ab7f09  test    eax, eax
0x140ab7f0b  jnz     loc_140B77674
0x140ab7f11  mov     ebx, 0C0000001h
0x140ab7f16  jmp     loc_140B77685
0x140ab7f1b  lea     r8, aSysinfoCanTSet_0; "sysinfo: Can't set MachinePreferredUILa"...
0x140ab7f22  xor     edx, edx; Level
0x140ab7f24  or      ecx, 0FFFFFFFFh; ComponentId
0x140ab7f27  call    DbgPrintEx
0x140ab7f2c  jmp     loc_140AB7E5C
0x140ab7f31  mov     ebx, r13d
0x140ab7f34  jmp     loc_140B77739
0x140ab7f39  call    ZwClose
0x140ab7f3e  jmp     loc_140AB7CB9
0x140ab7f43  lea     rax, [rsp+4E8h+var_4A4]
0x140ab7f48  mov     [rsp+4E8h+ResultLength], rax; ResultLength
0x140ab7f4d  mov     [rsp+4E8h+Length], r13d; Length
0x140ab7f52  xor     r9d, r9d; KeyValueInformation
0x140ab7f55  xor     r8d, r8d; KeyValueInformationClass
0x140ab7f58  xor     edx, edx; Index
0x140ab7f5a  call    ZwEnumerateValueKey
0x140ab7f5f  mov     edi, 8000001Ah
0x140ab7f64  cmp     eax, edi
0x140ab7f66  jnz     loc_140B77970
0x140ab7f6c  mov     rcx, [rsp+4E8h+var_430]; KeyHandle
0x140ab7f74  call    ZwDeleteKey
0x140ab7f79  nop
0x140ab7f7a  jmp     loc_140B77970
0x140ab7f7f  mov     rcx, [rsp+4E8h+var_490]; KeyHandle
0x140ab7f84  test    rcx, rcx
0x140ab7f87  jz      loc_140B77983
0x140ab7f8d  test    r15b, r15b
0x140ab7f90  jz      loc_140B779C1
0x140ab7f96  lea     rax, [rsp+4E8h+var_4A4]
0x140ab7f9b  mov     [rsp+4E8h+ResultLength], rax; ResultLength
0x140ab7fa0  mov     [rsp+4E8h+Length], r13d; Length
0x140ab7fa5  xor     r9d, r9d; KeyValueInformation
0x140ab7fa8  xor     r8d, r8d; KeyValueInformationClass
0x140ab7fab  xor     edx, edx; Index
0x140ab7fad  call    ZwEnumerateValueKey
0x140ab7fb2  cmp     eax, edi
  ... truncated ...
```
