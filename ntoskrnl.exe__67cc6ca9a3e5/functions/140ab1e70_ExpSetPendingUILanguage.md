# ExpSetPendingUILanguage

- ea: `0x140ab1e70`
- end: `0x140ab249e`
- name: `ExpSetPendingUILanguage`
- size: `1582`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140ab1e50`

## callees

- `0x14020f1c0`
- `0x14020fe90`
- `0x1403f2d50`
- `0x1404bd35c`
- `0x1404c5a90`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406daad0`
- `0x1406daaf0`
- `0x1406dab70`
- `0x1406dac30`
- `0x1406db490`
- `0x1406dc410`
- `0x1406dc470`
- `0x1406f4480`
- `0x1406f4880`
- `0x140720e18`
- `0x140ab1e70`
- `0x140abbd90`

## string_xrefs

- `0x140ab203c`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings`
- `0x140b750c6`: `Control Panel\Desktop\LanguageConfigurationPending`
- `0x140ab1fe5`: `Control Panel\Desktop\MuiCached`
- `0x140b75284`: `Control Panel\Desktop\MuiCached`
- `0x140b75170`: `Control Panel\Desktop\LanguageConfiguration`
- `0x140b7550e`: `*** MUI: Can't copy language name for LanguageConfig item %S\n`
- `0x140b7537a`: `*** MUI: Failed to delete value %S from MachineLanguageConfiguration!\n`
- `0x140ab209e`: `MachineLanguageConfiguration`
- `0x140b75439`: `MachineLanguageConfiguration`
- `0x140b75528`: `*** MUI: Can't copy language name for LanguageConfig item %u\n`
- `0x140ab20fa`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings\LanguageConfiguration`

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
  _DWORD *Teb; // rcx
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
      Teb = CurrentThread->Teb;
    if ( Teb )
      RtlWriteULongToUser(Teb + 1530, 0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140ab1e70  push    rbx
0x140ab1e72  push    rdi
0x140ab1e73  push    r12
0x140ab1e75  push    r13
0x140ab1e77  push    r14
0x140ab1e79  push    r15
0x140ab1e7b  sub     rsp, 4B8h
0x140ab1e82  mov     rax, cs:__security_cookie
0x140ab1e89  xor     rax, rsp
0x140ab1e8c  mov     [rsp+4E8h+var_48], rax
0x140ab1e94  xor     eax, eax
0x140ab1e96  xorps   xmm0, xmm0
0x140ab1e99  movups  xmmword ptr [rsp+4E8h+ObjectAttributes.Length], xmm0
0x140ab1e9e  movups  xmmword ptr [rsp+4E8h+ObjectAttributes.ObjectName], xmm0
0x140ab1ea3  movups  xmmword ptr [rsp+4E8h+ObjectAttributes+1Ch], xmm0
0x140ab1ea8  movups  xmmword ptr [rsp+4E8h+DestinationString.Length], xmm0
0x140ab1eb0  xorps   xmm1, xmm1
0x140ab1eb3  movups  xmmword ptr [rsp+4E8h+ValueName.Length], xmm1
0x140ab1ebb  movups  xmmword ptr [rsp+4E8h+var_418.Length], xmm0
0x140ab1ec3  xor     r13d, r13d
0x140ab1ec6  mov     [rsp+4E8h+var_438], r13
0x140ab1ece  mov     [rsp+4E8h+Handle], r13
0x140ab1ed3  xor     edx, edx; Val
0x140ab1ed5  mov     r8d, 0AAh; Size
0x140ab1edb  lea     rcx, [rsp+4E8h+SourceString]; void *
0x140ab1ee3  call    memset_0
0x140ab1ee8  mov     [rsp+4E8h+var_4A4], r13d
0x140ab1eed  mov     [rsp+4E8h+KeyHandle], r13
0x140ab1ef5  mov     [rsp+4E8h+var_430], r13
0x140ab1efd  mov     [rsp+4E8h+var_4A0], r13
0x140ab1f02  mov     [rsp+4E8h+var_490], r13
0x140ab1f07  lea     r8, [rsp+4E8h+var_438]
0x140ab1f0f  call    OpenGlobalizationUserSettingsKey
0x140ab1f14  test    eax, eax
0x140ab1f16  js      loc_140AB21B5
0x140ab1f1c  mov     r15b, 1
0x140ab1f1f  mov     r12b, r13b
0x140ab1f22  lea     rdx, aControlPanelDe_2; "Control Panel\\Desktop"
0x140ab1f29  lea     rcx, [rsp+4E8h+DestinationString]; DestinationString
0x140ab1f31  call    RtlInitUnicodeString
0x140ab1f36  lea     r14d, [r13+30h]
0x140ab1f3a  mov     [rsp+4E8h+ObjectAttributes.Length], r14d
0x140ab1f3f  mov     rax, [rsp+4E8h+var_438]
0x140ab1f47  mov     [rsp+4E8h+ObjectAttributes.RootDirectory], rax
0x140ab1f4c  mov     edi, 640h
0x140ab1f51  mov     [rsp+4E8h+ObjectAttributes.Attributes], edi
0x140ab1f55  lea     rax, [rsp+4E8h+DestinationString]
0x140ab1f5d  mov     [rsp+4E8h+ObjectAttributes.ObjectName], rax
0x140ab1f62  xorps   xmm0, xmm0
0x140ab1f65  movdqu  xmmword ptr [rsp+4E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140ab1f6e  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x140ab1f73  mov     edx, 40000000h; DesiredAccess
0x140ab1f78  lea     rcx, [rsp+4E8h+KeyHandle]; KeyHandle
0x140ab1f80  call    ZwOpenKey
0x140ab1f85  mov     ebx, eax
0x140ab1f87  mov     [rsp+4E8h+var_4A8], eax
0x140ab1f8b  test    eax, eax
0x140ab1f8d  js      loc_140AB2158
0x140ab1f93  lea     rdx, aPreferreduilan; "PreferredUILanguagesPending"
0x140ab1f9a  lea     rcx, [rsp+4E8h+ValueName]; DestinationString
0x140ab1fa2  call    RtlInitUnicodeString
0x140ab1fa7  lea     rax, [rsp+4E8h+var_4A4]
0x140ab1fac  mov     [rsp+4E8h+ResultLength], rax; ResultLength
0x140ab1fb1  mov     [rsp+4E8h+Length], 100h; Length
0x140ab1fb9  lea     r9, [rsp+4E8h+KeyValueInformation]; KeyValueInformation
0x140ab1fc1  lea     ebx, [r13+2]
0x140ab1fc5  mov     r8d, ebx; KeyValueInformationClass
0x140ab1fc8  lea     rdx, [rsp+4E8h+ValueName]; ValueName
0x140ab1fd0  mov     rcx, [rsp+4E8h+KeyHandle]; KeyHandle
0x140ab1fd8  call    ZwQueryValueKey
0x140ab1fdd  test    eax, eax
0x140ab1fdf  jns     loc_140B74FF6
0x140ab1fe5  lea     rdx, aControlPanelDe_0; "Control Panel\\Desktop\\MuiCached"
0x140ab1fec  lea     rcx, [rsp+4E8h+DestinationString]; DestinationString
0x140ab1ff4  call    RtlInitUnicodeString
0x140ab1ff9  mov     [rsp+4E8h+ObjectAttributes.Length], r14d
0x140ab1ffe  mov     rax, [rsp+4E8h+var_438]
0x140ab2006  mov     [rsp+4E8h+ObjectAttributes.RootDirectory], rax
0x140ab200b  mov     [rsp+4E8h+ObjectAttributes.Attributes], edi
0x140ab200f  lea     rax, [rsp+4E8h+DestinationString]
0x140ab2017  mov     [rsp+4E8h+ObjectAttributes.ObjectName], rax
0x140ab201c  xorps   xmm0, xmm0
0x140ab201f  movdqu  xmmword ptr [rsp+4E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140ab2028  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x140ab202d  mov     edx, 40000000h; DesiredAccess
0x140ab2032  lea     rcx, [rsp+4E8h+var_4A0]; KeyHandle
0x140ab2037  call    ZwOpenKey
0x140ab203c  lea     rdx, aRegistryMachin_88; "\\Registry\\Machine\\System\\CurrentCon"...
0x140ab2043  lea     rcx, [rsp+4E8h+DestinationString]; DestinationString
0x140ab204b  call    RtlInitUnicodeString
0x140ab2050  mov     [rsp+4E8h+ObjectAttributes.Length], r14d
0x140ab2055  mov     [rsp+4E8h+ObjectAttributes.RootDirectory], r13
0x140ab205a  mov     [rsp+4E8h+ObjectAttributes.Attributes], edi
0x140ab205e  lea     rax, [rsp+4E8h+DestinationString]
0x140ab2066  mov     [rsp+4E8h+ObjectAttributes.ObjectName], rax
0x140ab206b  xorps   xmm0, xmm0
0x140ab206e  movdqu  xmmword ptr [rsp+4E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140ab2077  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x140ab207c  mov     edx, 80000000h; DesiredAccess
0x140ab2081  lea     rcx, [rsp+4E8h+Handle]; KeyHandle
0x140ab2086  call    ZwOpenKey
0x140ab208b  test    eax, eax
0x140ab208d  jns     loc_140AB224B
0x140ab2093  cmp     [rsp+4E8h+var_4A0], r13
0x140ab2098  jnz     loc_140AB234A
0x140ab209e  lea     rdx, aMachinelanguag; "MachineLanguageConfiguration"
0x140ab20a5  lea     rcx, [rsp+4E8h+DestinationString]; DestinationString
0x140ab20ad  call    RtlInitUnicodeString
0x140ab20b2  mov     [rsp+4E8h+ObjectAttributes.Length], r14d
0x140ab20b7  mov     rax, [rsp+4E8h+var_4A0]
0x140ab20bc  mov     [rsp+4E8h+ObjectAttributes.RootDirectory], rax
0x140ab20c1  mov     [rsp+4E8h+ObjectAttributes.Attributes], edi
0x140ab20c5  lea     rax, [rsp+4E8h+DestinationString]
0x140ab20cd  mov     [rsp+4E8h+ObjectAttributes.ObjectName], rax
0x140ab20d2  xorps   xmm0, xmm0
0x140ab20d5  movdqu  xmmword ptr [rsp+4E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140ab20de  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x140ab20e3  mov     edx, 40000000h; DesiredAccess
0x140ab20e8  lea     rcx, [rsp+4E8h+var_490]; KeyHandle
0x140ab20ed  call    ZwOpenKey
0x140ab20f2  test    eax, eax
0x140ab20f4  jns     loc_140AB23E1
0x140ab20fa  lea     rdx, aRegistryMachin_248; "\\Registry\\Machine\\System\\CurrentCon"...
0x140ab2101  lea     rcx, [rsp+4E8h+DestinationString]; DestinationString
0x140ab2109  call    RtlInitUnicodeString
0x140ab210e  mov     [rsp+4E8h+ObjectAttributes.Length], r14d
0x140ab2113  mov     [rsp+4E8h+ObjectAttributes.RootDirectory], r13
0x140ab2118  mov     [rsp+4E8h+ObjectAttributes.Attributes], edi
0x140ab211c  lea     rax, [rsp+4E8h+DestinationString]
0x140ab2124  mov     [rsp+4E8h+ObjectAttributes.ObjectName], rax
0x140ab2129  xorps   xmm0, xmm0
0x140ab212c  movdqu  xmmword ptr [rsp+4E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140ab2135  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x140ab213a  mov     edx, 80000000h; DesiredAccess
0x140ab213f  lea     rcx, [rsp+4E8h+Handle]; KeyHandle
0x140ab2144  call    ZwOpenKey
0x140ab2149  test    eax, eax
0x140ab214b  jns     loc_140AB21D8
0x140ab2151  mov     ebx, r13d
0x140ab2154  mov     [rsp+4E8h+var_4A8], ebx
0x140ab2158  mov     rcx, [rsp+4E8h+KeyHandle]; Handle
0x140ab2160  test    rcx, rcx
0x140ab2163  jnz     loc_140AB23E9
0x140ab2169  mov     rcx, [rsp+4E8h+var_430]; KeyHandle
0x140ab2171  test    rcx, rcx
0x140ab2174  jnz     loc_140AB23F3
0x140ab217a  mov     edi, 8000001Ah
0x140ab217f  cmp     [rsp+4E8h+var_4A0], r13
0x140ab2184  jnz     loc_140AB242F
0x140ab218a  mov     rcx, [rsp+4E8h+var_490]; Handle
0x140ab218f  test    rcx, rcx
0x140ab2192  jnz     loc_140AB246F
0x140ab2198  mov     rcx, [rsp+4E8h+var_438]; Handle
0x140ab21a0  test    rcx, rcx
0x140ab21a3  jnz     loc_140AB2241
0x140ab21a9  cmp     r12b, 1
0x140ab21ad  jz      loc_140AB231B
0x140ab21b3  mov     eax, ebx
0x140ab21b5  mov     rcx, [rsp+4E8h+var_48]
0x140ab21bd  xor     rcx, rsp; StackCookie
0x140ab21c0  call    __security_check_cookie
0x140ab21c5  add     rsp, 4B8h
0x140ab21cc  pop     r15
0x140ab21ce  pop     r14
0x140ab21d0  pop     r13
0x140ab21d2  pop     r12
0x140ab21d4  pop     rdi
0x140ab21d5  pop     rbx
0x140ab21d6  retn
0x140ab21d8  mov     edi, r13d
0x140ab21db  xor     edx, edx; Val
0x140ab21dd  mov     r8d, 210h; Size
0x140ab21e3  lea     rcx, [rsp+4E8h+var_258]; void *
0x140ab21eb  call    memset_0
0x140ab21f0  lea     rax, [rsp+4E8h+var_4A4]
0x140ab21f5  mov     [rsp+4E8h+ResultLength], rax; ResultLength
0x140ab21fa  mov     [rsp+4E8h+Length], 20Eh; Length
0x140ab2202  lea     r9, [rsp+4E8h+var_258]; KeyValueInformation
0x140ab220a  mov     r8d, 1; KeyValueInformationClass
0x140ab2210  mov     edx, edi; Index
0x140ab2212  mov     rcx, [rsp+4E8h+Handle]; KeyHandle
0x140ab2217  call    ZwEnumerateValueKey
0x140ab221c  mov     ebx, eax
0x140ab221e  mov     [rsp+4E8h+var_4A8], eax
0x140ab2222  test    eax, eax
0x140ab2224  jns     loc_140B7539A
0x140ab222a  test    ebx, ebx
0x140ab222c  jns     short loc_140AB223D
0x140ab222e  mov     rcx, [rsp+4E8h+Handle]; Handle
0x140ab2233  call    ZwClose
0x140ab2238  jmp     loc_140AB2158
0x140ab223d  inc     edi
0x140ab223f  jmp     short loc_140AB21DB
0x140ab2241  call    ZwClose
0x140ab2246  jmp     loc_140AB21A9
0x140ab224b  lea     rdx, aPreferreduilan_1; "PreferredUILanguages"
0x140ab2252  lea     rcx, [rsp+4E8h+ValueName]; DestinationString
0x140ab225a  call    RtlInitUnicodeString
0x140ab225f  lea     rax, [rsp+4E8h+var_4A4]
0x140ab2264  mov     [rsp+4E8h+ResultLength], rax; ResultLength
0x140ab2269  mov     [rsp+4E8h+Length], 100h; Length
0x140ab2271  lea     r9, [rsp+4E8h+KeyValueInformation]; KeyValueInformation
0x140ab2279  mov     r8d, ebx; KeyValueInformationClass
0x140ab227c  lea     rdx, [rsp+4E8h+ValueName]; ValueName
0x140ab2284  mov     rcx, [rsp+4E8h+Handle]; KeyHandle
0x140ab2289  call    ZwQueryValueKey
0x140ab228e  test    eax, eax
0x140ab2290  js      loc_140AB2375
0x140ab2296  cmp     [rsp+4E8h+DataSize], 4
0x140ab229e  jb      loc_140AB2375
0x140ab22a4  cmp     [rsp+4E8h+var_404], 7
0x140ab22ac  jnz     loc_140AB2375
0x140ab22b2  cmp     [rsp+4E8h+var_4A0], r13
0x140ab22b7  jz      loc_140B75284
0x140ab22bd  lea     rdx, aMachinepreferr; "MachinePreferredUILanguages"
0x140ab22c4  lea     rcx, [rsp+4E8h+ValueName]; DestinationString
0x140ab22cc  call    RtlInitUnicodeString
0x140ab22d1  mov     eax, [rsp+4E8h+DataSize]
0x140ab22d8  mov     dword ptr [rsp+4E8h+ResultLength], eax; DataSize
0x140ab22dc  lea     rax, [rsp+4E8h+Data]
0x140ab22e4  mov     qword ptr [rsp+4E8h+Length], rax; Data
0x140ab22e9  mov     r9d, 7; Type
0x140ab22ef  xor     r8d, r8d; TitleIndex
0x140ab22f2  lea     rdx, [rsp+4E8h+ValueName]; ValueName
0x140ab22fa  mov     rcx, [rsp+4E8h+var_4A0]; KeyHandle
0x140ab22ff  call    ZwSetValueKey
0x140ab2304  test    eax, eax
0x140ab2306  js      loc_140AB23CB
0x140ab230c  mov     rcx, [rsp+4E8h+Handle]; Handle
0x140ab2311  call    ZwClose
0x140ab2316  jmp     loc_140AB209E
0x140ab231b  mov     rcx, gs:188h
0x140ab2324  test    dword ptr [rcx+74h], 400h
0x140ab232b  jnz     short loc_140AB2336
0x140ab232d  cmp     byte ptr [rcx+24Ah], 1
0x140ab2334  jnz     short loc_140AB233E
0x140ab2336  mov     rcx, r13
0x140ab2339  jmp     loc_140AB2479
0x140ab233e  mov     rcx, [rcx+0F0h]
0x140ab2345  jmp     loc_140AB2479
0x140ab234a  lea     rdx, aMachinepreferr; "MachinePreferredUILanguages"
0x140ab2351  lea     rcx, [rsp+4E8h+ValueName]; DestinationString
0x140ab2359  call    RtlInitUnicodeString
0x140ab235e  lea     rdx, [rsp+4E8h+ValueName]; ValueName
0x140ab2366  mov     rcx, [rsp+4E8h+var_4A0]; KeyHandle
0x140ab236b  call    ZwDeleteValueKey
0x140ab2370  jmp     loc_140AB209E
0x140ab2375  mov     word ptr [rsp+4E8h+var_4A8], r13w
0x140ab237b  mov     [rsp+4E8h+DataSize], r13d
0x140ab2383  lea     rcx, [rsp+4E8h+var_4A8]
0x140ab2388  call    NtQueryInstallUILanguage
0x140ab238d  mov     ebx, eax
0x140ab238f  test    eax, eax
0x140ab2391  js      loc_140B75247
0x140ab2397  xor     r9d, r9d
0x140ab239a  mov     r8d, 80h
0x140ab23a0  lea     rdx, [rsp+4E8h+Data]
0x140ab23a8  movzx   ecx, word ptr [rsp+4E8h+var_4A8]
0x140ab23ad  call    DownLevelLangIDToLanguageName
0x140ab23b2  mov     [rsp+4E8h+DataSize], eax
0x140ab23b9  test    eax, eax
0x140ab23bb  jnz     loc_140B7523E
0x140ab23c1  mov     ebx, 0C0000001h
0x140ab23c6  jmp     loc_140B7524F
0x140ab23cb  lea     r8, aSysinfoCanTSet_0; "sysinfo: Can't set MachinePreferredUILa"...
0x140ab23d2  xor     edx, edx; Level
0x140ab23d4  or      ecx, 0FFFFFFFFh; ComponentId
0x140ab23d7  call    DbgPrintEx
0x140ab23dc  jmp     loc_140AB230C
0x140ab23e1  mov     ebx, r13d
0x140ab23e4  jmp     loc_140B75303
0x140ab23e9  call    ZwClose
0x140ab23ee  jmp     loc_140AB2169
0x140ab23f3  lea     rax, [rsp+4E8h+var_4A4]
0x140ab23f8  mov     [rsp+4E8h+ResultLength], rax; ResultLength
0x140ab23fd  mov     [rsp+4E8h+Length], r13d; Length
0x140ab2402  xor     r9d, r9d; KeyValueInformation
0x140ab2405  xor     r8d, r8d; KeyValueInformationClass
0x140ab2408  xor     edx, edx; Index
0x140ab240a  call    ZwEnumerateValueKey
0x140ab240f  mov     edi, 8000001Ah
0x140ab2414  cmp     eax, edi
0x140ab2416  jnz     loc_140B7553A
0x140ab241c  mov     rcx, [rsp+4E8h+var_430]; KeyHandle
0x140ab2424  call    ZwDeleteKey
0x140ab2429  nop
0x140ab242a  jmp     loc_140B7553A
0x140ab242f  mov     rcx, [rsp+4E8h+var_490]; KeyHandle
0x140ab2434  test    rcx, rcx
0x140ab2437  jz      loc_140B7554D
0x140ab243d  test    r15b, r15b
0x140ab2440  jz      loc_140B7558B
0x140ab2446  lea     rax, [rsp+4E8h+var_4A4]
0x140ab244b  mov     [rsp+4E8h+ResultLength], rax; ResultLength
0x140ab2450  mov     [rsp+4E8h+Length], r13d; Length
0x140ab2455  xor     r9d, r9d; KeyValueInformation
0x140ab2458  xor     r8d, r8d; KeyValueInformationClass
0x140ab245b  xor     edx, edx; Index
0x140ab245d  call    ZwEnumerateValueKey
0x140ab2462  cmp     eax, edi
  ... truncated ...
```
