# Internal_GetPrevInstallLanguage

- ea: `0x1800649c4`
- end: `0x180064bb2`
- name: `Internal_GetPrevInstallLanguage`
- size: `494`
- prototype: `__int64 __fastcall(PVOID MemoryPointer)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180064bb8`

## callees

- `0x18005b8ac`
- `0x1800649c4`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlSizeHeap` at `0x180064a64`
- `ntdll!RtlSizeHeap` at `0x180064a64`
- `ntdll!NtQueryValueKey` at `0x180064afb`
- `ntdll!NtQueryValueKey` at `0x180064b59`
- `ntdll!NtQueryValueKey` at `0x180064afb`
- `ntdll!NtQueryValueKey` at `0x180064b59`
- `ntdll!NtOpenKey` at `0x180064ab6`
- `ntdll!NtOpenKey` at `0x180064ab6`
- `ntdll!NtClose` at `0x180064b7f`
- `ntdll!NtClose` at `0x180064b7f`
- `ntdll!RtlInitUnicodeString` at `0x180064a43`
- `ntdll!RtlInitUnicodeString` at `0x180064ad2`
- `ntdll!RtlInitUnicodeString` at `0x180064b30`
- `ntdll!RtlInitUnicodeString` at `0x180064a43`
- `ntdll!RtlInitUnicodeString` at `0x180064ad2`
- `ntdll!RtlInitUnicodeString` at `0x180064b30`

## string_xrefs

- `0x180064a2a`: `\Registry\Machine\System\CurrentControlSet\Control\NLS\Language`
- `0x180064ac6`: `PreviousInstallLanguage`
- `0x180064b1c`: `InstallLanguage`

## pseudocode

```c
__int64 __fastcall Internal_GetPrevInstallLanguage(PVOID MemoryPointer, unsigned int a2)
{
  NTSTATUS v4; // ebx
  NTSTATUS v5; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE KeyValueInformation[192]; // [rsp+90h] [rbp-70h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(KeyValueInformation, 0, 0xBAu);
  ValueName = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\NLS\\Language");
  if ( !MemoryPointer || RtlSizeHeap(NtCurrentPeb()->ProcessHeap, 0, MemoryPointer) - 172 > 0xFFFFFFFFFFFFFF52uLL )
    return 3221225485LL;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v4 >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"PreviousInstallLanguage");
    v5 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0xBAu, &ResultLength);
    v4 = v5;
    if ( v5 >= 0
      || v5 == -1073741772
      && (memset_0(KeyValueInformation, 0, 0xBAu),
          ResultLength = 0,
          RtlInitUnicodeString(&ValueName, L"InstallLanguage"),
          v4 = NtQueryValueKey(
                 KeyHandle,
                 &ValueName,
                 KeyValuePartialInformation,
                 KeyValueInformation,
                 0xBAu,
                 &ResultLength),
          v4 >= 0) )
    {
      v4 = CopyLangDataFromReg(a2, MemoryPointer, KeyValueInformation);
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800649c4  mov     [rsp-8+arg_8], rbx
0x1800649c9  mov     [rsp-8+arg_10], rsi
0x1800649ce  push    rbp
0x1800649cf  push    rdi
0x1800649d0  push    r15
0x1800649d2  lea     rbp, [rsp-60h]
0x1800649d7  sub     rsp, 160h
0x1800649de  mov     rax, cs:__security_cookie
0x1800649e5  xor     rax, rsp
0x1800649e8  mov     [rbp+70h+var_20], rax
0x1800649ec  xorps   xmm0, xmm0
0x1800649ef  mov     [rsp+170h+KeyHandle], 0
0x1800649f8  mov     esi, edx
0x1800649fa  mov     [rsp+170h+var_140], 0
0x180064a02  mov     rdi, rcx
0x180064a05  mov     r15d, 0BAh
0x180064a0b  mov     r8d, r15d; Size
0x180064a0e  lea     rcx, [rbp+70h+KeyValueInformation]; void *
0x180064a12  xor     edx, edx; Val
0x180064a14  movups  xmmword ptr [rsp+170h+ObjectAttributes.Length], xmm0
0x180064a19  movups  xmmword ptr [rsp+170h+ObjectAttributes.ObjectName], xmm0
0x180064a1e  movups  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x180064a22  call    memset_0
0x180064a27  xorps   xmm0, xmm0
0x180064a2a  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x180064a31  xorps   xmm1, xmm1
0x180064a34  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180064a39  movups  xmmword ptr [rsp+170h+ValueName.Length], xmm0
0x180064a3e  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm1
0x180064a43  call    cs:__imp_RtlInitUnicodeString
0x180064a49  test    rdi, rdi
0x180064a4c  jz      loc_180064B89
0x180064a52  mov     rcx, gs:60h
0x180064a5b  mov     r8, rdi; MemoryPointer
0x180064a5e  xor     edx, edx; Flags
0x180064a60  mov     rcx, [rcx+30h]; HeapHandle
0x180064a64  call    cs:__imp_RtlSizeHeap
0x180064a6a  add     rax, 0FFFFFFFFFFFFFF54h
0x180064a70  cmp     rax, 0FFFFFFFFFFFFFF52h
0x180064a76  ja      loc_180064B89
0x180064a7c  lea     rax, [rsp+170h+DestinationString]
0x180064a81  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x180064a89  xorps   xmm0, xmm0
0x180064a8c  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x180064a91  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x180064a96  mov     [rsp+170h+ObjectAttributes.RootDirectory], 0
0x180064a9f  mov     edx, 20019h; DesiredAccess
0x180064aa4  mov     [rsp+170h+ObjectAttributes.Attributes], 40h ; '@'
0x180064aac  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180064ab1  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x180064ab6  call    cs:__imp_NtOpenKey
0x180064abc  mov     ebx, eax
0x180064abe  test    eax, eax
0x180064ac0  js      loc_180064B75
0x180064ac6  lea     rdx, aPreviousinstal; "PreviousInstallLanguage"
0x180064acd  lea     rcx, [rsp+170h+ValueName]; DestinationString
0x180064ad2  call    cs:__imp_RtlInitUnicodeString
0x180064ad8  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180064add  lea     rax, [rsp+170h+var_140]
0x180064ae2  mov     [rsp+170h+ResultLength], rax; ResultLength
0x180064ae7  lea     r9, [rbp+70h+KeyValueInformation]; KeyValueInformation
0x180064aeb  mov     r8d, 2; KeyValueInformationClass
0x180064af1  mov     [rsp+170h+Length], r15d; Length
0x180064af6  lea     rdx, [rsp+170h+ValueName]; ValueName
0x180064afb  call    cs:__imp_NtQueryValueKey
0x180064b01  mov     ebx, eax
0x180064b03  test    eax, eax
0x180064b05  jns     short loc_180064B65
0x180064b07  cmp     eax, 0C0000034h
0x180064b0c  jnz     short loc_180064B75
0x180064b0e  mov     r8d, r15d; Size
0x180064b11  lea     rcx, [rbp+70h+KeyValueInformation]; void *
0x180064b15  xor     edx, edx; Val
0x180064b17  call    memset_0
0x180064b1c  lea     rdx, aInstalllanguag; "InstallLanguage"
0x180064b23  mov     [rsp+170h+var_140], 0
0x180064b2b  lea     rcx, [rsp+170h+ValueName]; DestinationString
0x180064b30  call    cs:__imp_RtlInitUnicodeString
0x180064b36  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180064b3b  lea     rax, [rsp+170h+var_140]
0x180064b40  mov     [rsp+170h+ResultLength], rax; ResultLength
0x180064b45  lea     r9, [rbp+70h+KeyValueInformation]; KeyValueInformation
0x180064b49  mov     r8d, 2; KeyValueInformationClass
0x180064b4f  mov     [rsp+170h+Length], r15d; Length
0x180064b54  lea     rdx, [rsp+170h+ValueName]; ValueName
0x180064b59  call    cs:__imp_NtQueryValueKey
0x180064b5f  mov     ebx, eax
0x180064b61  test    eax, eax
0x180064b63  js      short loc_180064B75
0x180064b65  lea     r8, [rbp+70h+KeyValueInformation]
0x180064b69  mov     rdx, rdi
0x180064b6c  mov     ecx, esi
0x180064b6e  call    CopyLangDataFromReg
0x180064b73  mov     ebx, eax
0x180064b75  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x180064b7a  test    rcx, rcx
0x180064b7d  jz      short loc_180064B85
0x180064b7f  call    cs:__imp_NtClose
0x180064b85  mov     eax, ebx
0x180064b87  jmp     short loc_180064B8E
0x180064b89  mov     eax, 0C000000Dh
0x180064b8e  mov     rcx, [rbp+70h+var_20]
0x180064b92  xor     rcx, rsp; StackCookie
0x180064b95  call    __security_check_cookie
0x180064b9a  lea     r11, [rsp+170h+var_10]
0x180064ba2  mov     rbx, [r11+28h]
0x180064ba6  mov     rsi, [r11+30h]
0x180064baa  mov     rsp, r11
0x180064bad  pop     r15
0x180064baf  pop     rdi
0x180064bb0  pop     rbp
0x180064bb1  retn
```
