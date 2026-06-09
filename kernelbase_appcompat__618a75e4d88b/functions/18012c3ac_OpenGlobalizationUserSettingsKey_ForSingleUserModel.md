# OpenGlobalizationUserSettingsKey_ForSingleUserModel

- ea: `0x18012c3ac`
- end: `0x18012c64d`
- name: `OpenGlobalizationUserSettingsKey_ForSingleUserModel`
- size: `673`
- prototype: `__int64 __fastcall(ACCESS_MASK DesiredAccess, PHANDLE KeyHandle)`
- caller_count: `16`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cd50`
- `0x180022a60`
- `0x180023c10`
- `0x180024ed0`
- `0x180027400`
- `0x180028630`
- `0x180029ec0`
- `0x18002a790`
- `0x18002aabc`
- `0x18002ad10`
- `0x18002b12c`
- `0x18002b780`
- `0x18002bea0`
- `0x180046ac0`
- `0x180048f20`
- `0x18004a820`

## callees

- `0x18002d7e0`
- `0x18011115c`
- `0x18012c3ac`
- `0x18012f834`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18012c3e7`
- `ntdll!RtlInitUnicodeString` at `0x18012c44d`
- `ntdll!RtlInitUnicodeString` at `0x18012c48c`
- `ntdll!RtlInitUnicodeString` at `0x18012c546`
- `ntdll!RtlInitUnicodeString` at `0x18012c3e7`
- `ntdll!RtlInitUnicodeString` at `0x18012c44d`
- `ntdll!RtlInitUnicodeString` at `0x18012c48c`
- `ntdll!RtlInitUnicodeString` at `0x18012c546`
- `ntdll!RtlCopyUnicodeString` at `0x18012c591`
- `ntdll!RtlCopyUnicodeString` at `0x18012c5f6`
- `ntdll!RtlCopyUnicodeString` at `0x18012c591`
- `ntdll!RtlCopyUnicodeString` at `0x18012c5f6`
- `ntdll!ZwQueryValueKey` at `0x18012c4bb`
- `ntdll!ZwQueryValueKey` at `0x18012c513`
- `ntdll!ZwQueryValueKey` at `0x18012c4bb`
- `ntdll!ZwQueryValueKey` at `0x18012c513`
- `ntdll!ZwClose` at `0x18012c626`
- `ntdll!ZwClose` at `0x18012c626`
- `ntdll!ZwOpenKey` at `0x18012c423`
- `ntdll!ZwOpenKey` at `0x18012c423`

## string_xrefs

- `0x18012c436`: `\Registry\Machine\System\CurrentControlSet\Control\CommonGlobUserSettings\`

## pseudocode

```c
__int64 __fastcall OpenGlobalizationUserSettingsKey_ForSingleUserModel(ACCESS_MASK DesiredAccess, PHANDLE KeyHandle)
{
  NTSTATUS v4; // ebx
  NTSTATUS v5; // eax
  WCHAR *v6; // rdi
  HANDLE v7; // rax
  UNICODE_STRING SourceString; // [rsp+38h] [rbp-31h] BYREF
  UNICODE_STRING v10; // [rsp+48h] [rbp-21h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-1h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+Fh] BYREF
  ULONG ResultLength; // [rsp+E0h] [rbp+77h] BYREF
  HANDLE KeyHandlea; // [rsp+E8h] [rbp+7Fh]

  if ( dword_1803A7174 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, &word_1803A68C0);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return (unsigned int)ZwOpenKey(KeyHandle, DesiredAccess, &ObjectAttributes);
  }
  KeyHandlea = 0;
  v10 = 0;
  RtlInitUnicodeString(&v10, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CommonGlobUserSettings\\");
  v4 = OpenRegistryKey(DesiredAccess);
  if ( v4 >= 0 )
  {
    ResultLength = 0;
    ValueName = 0;
    RtlInitUnicodeString(&ValueName, L"RedirectedKey");
    v5 = ZwQueryValueKey(KeyHandlea, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( !ResultLength || v5 != -1073741789 && v5 != -2147483643 )
    {
      *(_QWORD *)&DestinationString.Length = 11141120;
      DestinationString.Buffer = &word_1803A68C0;
      if ( v10.Length <= 0xAAu )
      {
        RtlCopyUnicodeString(&DestinationString, &v10);
        dword_1803A7174 = 1;
      }
      v4 = 0;
      *KeyHandle = KeyHandlea;
      KeyHandlea = 0;
      goto LABEL_21;
    }
    v6 = (WCHAR *)wil::details::heap_allocator::allocate(ResultLength);
    if ( v6 )
    {
      v4 = ZwQueryValueKey(KeyHandlea, &ValueName, KeyValuePartialInformation, v6, ResultLength, &ResultLength);
      if ( v4 >= 0 )
      {
        if ( *((_DWORD *)v6 + 1) != 1 )
        {
          v7 = KeyHandlea;
          KeyHandlea = 0;
LABEL_15:
          *KeyHandle = v7;
          goto LABEL_16;
        }
        SourceString = 0;
        RtlInitUnicodeString(&SourceString, v6 + 6);
        v4 = OpenRegistryKey(DesiredAccess);
        if ( v4 >= 0 )
        {
          *(_QWORD *)&DestinationString.Length = 11141120;
          DestinationString.Buffer = &word_1803A68C0;
          if ( SourceString.Length <= 0xAAu )
          {
            RtlCopyUnicodeString(&DestinationString, &SourceString);
            dword_1803A7174 = 1;
          }
          v7 = 0;
          goto LABEL_15;
        }
      }
LABEL_16:
      FreeEnvironmentStringsW(v6);
      goto LABEL_21;
    }
    v4 = -1073741801;
  }
LABEL_21:
  if ( KeyHandlea )
    ZwClose(KeyHandlea);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18012c3ac  mov     [rsp-8+arg_0], rbx
0x18012c3b1  mov     [rsp-8+arg_8], rsi
0x18012c3b6  push    rbp
0x18012c3b7  push    rdi
0x18012c3b8  push    r14
0x18012c3ba  lea     rbp, [rsp-47h]
0x18012c3bf  sub     rsp, 0B0h
0x18012c3c6  cmp     cs:dword_1803A7174, 0
0x18012c3cd  mov     rsi, rdx
0x18012c3d0  mov     r14d, ecx
0x18012c3d3  xorps   xmm0, xmm0
0x18012c3d6  jz      short loc_18012C436
0x18012c3d8  lea     rdx, word_1803A68C0; SourceString
0x18012c3df  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18012c3e3  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18012c3e7  call    cs:__imp_RtlInitUnicodeString
0x18012c3ee  nop     dword ptr [rax+rax+00h]
0x18012c3f3  xor     eax, eax
0x18012c3f5  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18012c3fd  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18012c401  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18012c405  lea     rax, [rbp+57h+DestinationString]
0x18012c409  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18012c411  xorps   xmm0, xmm0
0x18012c414  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18012c418  mov     edx, r14d; DesiredAccess
0x18012c41b  mov     rcx, rsi; KeyHandle
0x18012c41e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18012c423  call    cs:__imp_ZwOpenKey
0x18012c42a  nop     dword ptr [rax+rax+00h]
0x18012c42f  mov     ebx, eax
0x18012c431  jmp     loc_18012C632
0x18012c436  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x18012c43d  mov     [rbp+57h+KeyHandle], 0
0x18012c445  lea     rcx, [rbp+57h+var_78]; DestinationString
0x18012c449  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x18012c44d  call    cs:__imp_RtlInitUnicodeString
0x18012c454  nop     dword ptr [rax+rax+00h]
0x18012c459  lea     r8, [rbp+57h+KeyHandle]
0x18012c45d  mov     ecx, r14d; DesiredAccess
0x18012c460  lea     rdx, [rbp+57h+var_78]
0x18012c464  call    OpenRegistryKey
0x18012c469  mov     ebx, eax
0x18012c46b  test    eax, eax
0x18012c46d  js      loc_18012C61D
0x18012c473  xorps   xmm0, xmm0
0x18012c476  mov     [rbp+57h+arg_10], 0
0x18012c47d  lea     rdx, aRedirectedkey; "RedirectedKey"
0x18012c484  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x18012c488  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x18012c48c  call    cs:__imp_RtlInitUnicodeString
0x18012c493  nop     dword ptr [rax+rax+00h]
0x18012c498  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18012c49c  lea     rax, [rbp+57h+arg_10]
0x18012c4a0  xor     r9d, r9d; KeyValueInformation
0x18012c4a3  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x18012c4a8  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18012c4ac  mov     [rsp+0C0h+Length], 0; Length
0x18012c4b4  lea     ebx, [r9+2]
0x18012c4b8  mov     r8d, ebx; KeyValueInformationClass
0x18012c4bb  call    cs:__imp_ZwQueryValueKey
0x18012c4c2  nop     dword ptr [rax+rax+00h]
0x18012c4c7  mov     ecx, [rbp+57h+arg_10]; unsigned __int64
0x18012c4ca  test    ecx, ecx
0x18012c4cc  jz      loc_18012C5CD
0x18012c4d2  cmp     eax, 0C0000023h
0x18012c4d7  jz      short loc_18012C4E4
0x18012c4d9  cmp     eax, 80000005h
0x18012c4de  jnz     loc_18012C5CD
0x18012c4e4  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18012c4e9  mov     rdi, rax
0x18012c4ec  test    rax, rax
0x18012c4ef  jz      loc_18012C5C6
0x18012c4f5  mov     ecx, [rbp+57h+arg_10]
0x18012c4f8  lea     rax, [rbp+57h+arg_10]
0x18012c4fc  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x18012c501  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18012c505  mov     [rsp+0C0h+Length], ecx; Length
0x18012c509  mov     r9, rdi; KeyValueInformation
0x18012c50c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18012c510  mov     r8d, ebx; KeyValueInformationClass
0x18012c513  call    cs:__imp_ZwQueryValueKey
0x18012c51a  nop     dword ptr [rax+rax+00h]
0x18012c51f  mov     ebx, eax
0x18012c521  test    eax, eax
0x18012c523  js      loc_18012C5BC
0x18012c529  cmp     dword ptr [rdi+4], 1
0x18012c52d  jnz     short loc_18012C5AD
0x18012c52f  xorps   xmm0, xmm0
0x18012c532  mov     [rbp+57h+var_90], 0
0x18012c53a  lea     rdx, [rdi+0Ch]; SourceString
0x18012c53e  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x18012c542  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x18012c546  call    cs:__imp_RtlInitUnicodeString
0x18012c54d  nop     dword ptr [rax+rax+00h]
0x18012c552  lea     r8, [rbp+57h+var_90]
0x18012c556  mov     ecx, r14d; DesiredAccess
0x18012c559  lea     rdx, [rbp+57h+SourceString]
0x18012c55d  call    OpenRegistryKey
0x18012c562  mov     ebx, eax
0x18012c564  test    eax, eax
0x18012c566  js      short loc_18012C5BC
0x18012c568  mov     eax, 0AAh
0x18012c56d  lea     rdx, word_1803A68C0
0x18012c574  xorps   xmm0, xmm0
0x18012c577  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18012c57b  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x18012c57f  mov     [rbp+57h+DestinationString.Buffer], rdx
0x18012c583  cmp     ax, [rbp+57h+SourceString.Length]
0x18012c587  jb      short loc_18012C5A7
0x18012c589  lea     rdx, [rbp+57h+SourceString]; SourceString
0x18012c58d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18012c591  call    cs:__imp_RtlCopyUnicodeString
0x18012c598  nop     dword ptr [rax+rax+00h]
0x18012c59d  mov     cs:dword_1803A7174, 1
0x18012c5a7  mov     rax, [rbp+57h+var_90]
0x18012c5ab  jmp     short loc_18012C5B9
0x18012c5ad  mov     rax, [rbp+57h+KeyHandle]
0x18012c5b1  mov     [rbp+57h+KeyHandle], 0
0x18012c5b9  mov     [rsi], rax
0x18012c5bc  mov     rcx, rdi; penv
0x18012c5bf  call    FreeEnvironmentStringsW
0x18012c5c4  jmp     short loc_18012C61D
0x18012c5c6  mov     ebx, 0C0000017h
0x18012c5cb  jmp     short loc_18012C61D
0x18012c5cd  mov     eax, 0AAh
0x18012c5d2  lea     rdx, word_1803A68C0
0x18012c5d9  xorps   xmm0, xmm0
0x18012c5dc  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18012c5e0  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x18012c5e4  mov     [rbp+57h+DestinationString.Buffer], rdx
0x18012c5e8  cmp     ax, [rbp+57h+var_78.Length]
0x18012c5ec  jb      short loc_18012C60C
0x18012c5ee  lea     rdx, [rbp+57h+var_78]; SourceString
0x18012c5f2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18012c5f6  call    cs:__imp_RtlCopyUnicodeString
0x18012c5fd  nop     dword ptr [rax+rax+00h]
0x18012c602  mov     cs:dword_1803A7174, 1
0x18012c60c  mov     rax, [rbp+57h+KeyHandle]
0x18012c610  xor     ebx, ebx
0x18012c612  mov     [rsi], rax
0x18012c615  mov     [rbp+57h+KeyHandle], 0
0x18012c61d  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18012c621  test    rcx, rcx
0x18012c624  jz      short loc_18012C632
0x18012c626  call    cs:__imp_ZwClose
0x18012c62d  nop     dword ptr [rax+rax+00h]
0x18012c632  lea     r11, [rsp+0C0h+var_10]
0x18012c63a  mov     eax, ebx
0x18012c63c  mov     rbx, [r11+20h]
0x18012c640  mov     rsi, [r11+28h]
0x18012c644  mov     rsp, r11
0x18012c647  pop     r14
0x18012c649  pop     rdi
0x18012c64a  pop     rbp
0x18012c64b  retn
```
