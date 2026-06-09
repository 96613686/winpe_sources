# Internal_GetPrevInstallLanguage

- ea: `0x18006b6a8`
- end: `0x18006b8c7`
- name: `Internal_GetPrevInstallLanguage`
- size: `543`
- prototype: `__int64 __fastcall(PVOID MemoryPointer)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006b8d0`

## callees

- `0x1800611d8`
- `0x18006b6a8`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlSizeHeap` at `0x18006b74e`
- `ntdll!RtlSizeHeap` at `0x18006b74e`
- `ntdll!NtQueryValueKey` at `0x18006b7f7`
- `ntdll!NtQueryValueKey` at `0x18006b861`
- `ntdll!NtQueryValueKey` at `0x18006b7f7`
- `ntdll!NtQueryValueKey` at `0x18006b861`
- `ntdll!NtOpenKey` at `0x18006b7a6`
- `ntdll!NtOpenKey` at `0x18006b7a6`
- `ntdll!NtClose` at `0x18006b88d`
- `ntdll!NtClose` at `0x18006b88d`
- `ntdll!RtlInitUnicodeString` at `0x18006b727`
- `ntdll!RtlInitUnicodeString` at `0x18006b7c8`
- `ntdll!RtlInitUnicodeString` at `0x18006b832`
- `ntdll!RtlInitUnicodeString` at `0x18006b727`
- `ntdll!RtlInitUnicodeString` at `0x18006b7c8`
- `ntdll!RtlInitUnicodeString` at `0x18006b832`

## string_xrefs

- `0x18006b70e`: `\Registry\Machine\System\CurrentControlSet\Control\NLS\Language`
- `0x18006b7bc`: `PreviousInstallLanguage`
- `0x18006b81e`: `InstallLanguage`

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
0x18006b6a8  mov     [rsp-8+arg_8], rbx
0x18006b6ad  mov     [rsp-8+arg_10], rsi
0x18006b6b2  push    rbp
0x18006b6b3  push    rdi
0x18006b6b4  push    r15
0x18006b6b6  lea     rbp, [rsp-60h]
0x18006b6bb  sub     rsp, 160h
0x18006b6c2  mov     rax, cs:__security_cookie
0x18006b6c9  xor     rax, rsp
0x18006b6cc  mov     [rbp+70h+var_20], rax
0x18006b6d0  xorps   xmm0, xmm0
0x18006b6d3  mov     [rsp+170h+KeyHandle], 0
0x18006b6dc  mov     esi, edx
0x18006b6de  mov     [rsp+170h+var_140], 0
0x18006b6e6  mov     rdi, rcx
0x18006b6e9  mov     r15d, 0BAh
0x18006b6ef  mov     r8d, r15d; Size
0x18006b6f2  lea     rcx, [rbp+70h+KeyValueInformation]; void *
0x18006b6f6  xor     edx, edx; Val
0x18006b6f8  movups  xmmword ptr [rsp+170h+ObjectAttributes.Length], xmm0
0x18006b6fd  movups  xmmword ptr [rsp+170h+ObjectAttributes.ObjectName], xmm0
0x18006b702  movups  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006b706  call    memset_0
0x18006b70b  xorps   xmm0, xmm0
0x18006b70e  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x18006b715  xorps   xmm1, xmm1
0x18006b718  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x18006b71d  movups  xmmword ptr [rsp+170h+ValueName.Length], xmm0
0x18006b722  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm1
0x18006b727  call    cs:__imp_RtlInitUnicodeString
0x18006b72e  nop     dword ptr [rax+rax+00h]
0x18006b733  test    rdi, rdi
0x18006b736  jz      loc_18006B89D
0x18006b73c  mov     rcx, gs:60h
0x18006b745  mov     r8, rdi; MemoryPointer
0x18006b748  xor     edx, edx; Flags
0x18006b74a  mov     rcx, [rcx+30h]; HeapHandle
0x18006b74e  call    cs:__imp_RtlSizeHeap
0x18006b755  nop     dword ptr [rax+rax+00h]
0x18006b75a  add     rax, 0FFFFFFFFFFFFFF54h
0x18006b760  cmp     rax, 0FFFFFFFFFFFFFF52h
0x18006b766  ja      loc_18006B89D
0x18006b76c  lea     rax, [rsp+170h+DestinationString]
0x18006b771  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x18006b779  xorps   xmm0, xmm0
0x18006b77c  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x18006b781  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x18006b786  mov     [rsp+170h+ObjectAttributes.RootDirectory], 0
0x18006b78f  mov     edx, 20019h; DesiredAccess
0x18006b794  mov     [rsp+170h+ObjectAttributes.Attributes], 40h ; '@'
0x18006b79c  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x18006b7a1  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006b7a6  call    cs:__imp_NtOpenKey
0x18006b7ad  nop     dword ptr [rax+rax+00h]
0x18006b7b2  mov     ebx, eax
0x18006b7b4  test    eax, eax
0x18006b7b6  js      loc_18006B883
0x18006b7bc  lea     rdx, aPreviousinstal; "PreviousInstallLanguage"
0x18006b7c3  lea     rcx, [rsp+170h+ValueName]; DestinationString
0x18006b7c8  call    cs:__imp_RtlInitUnicodeString
0x18006b7cf  nop     dword ptr [rax+rax+00h]
0x18006b7d4  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x18006b7d9  lea     rax, [rsp+170h+var_140]
0x18006b7de  mov     [rsp+170h+ResultLength], rax; ResultLength
0x18006b7e3  lea     r9, [rbp+70h+KeyValueInformation]; KeyValueInformation
0x18006b7e7  mov     r8d, 2; KeyValueInformationClass
0x18006b7ed  mov     [rsp+170h+Length], r15d; Length
0x18006b7f2  lea     rdx, [rsp+170h+ValueName]; ValueName
0x18006b7f7  call    cs:__imp_NtQueryValueKey
0x18006b7fe  nop     dword ptr [rax+rax+00h]
0x18006b803  mov     ebx, eax
0x18006b805  test    eax, eax
0x18006b807  jns     short loc_18006B873
0x18006b809  cmp     eax, 0C0000034h
0x18006b80e  jnz     short loc_18006B883
0x18006b810  mov     r8d, r15d; Size
0x18006b813  lea     rcx, [rbp+70h+KeyValueInformation]; void *
0x18006b817  xor     edx, edx; Val
0x18006b819  call    memset_0
0x18006b81e  lea     rdx, aInstalllanguag; "InstallLanguage"
0x18006b825  mov     [rsp+170h+var_140], 0
0x18006b82d  lea     rcx, [rsp+170h+ValueName]; DestinationString
0x18006b832  call    cs:__imp_RtlInitUnicodeString
0x18006b839  nop     dword ptr [rax+rax+00h]
0x18006b83e  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x18006b843  lea     rax, [rsp+170h+var_140]
0x18006b848  mov     [rsp+170h+ResultLength], rax; ResultLength
0x18006b84d  lea     r9, [rbp+70h+KeyValueInformation]; KeyValueInformation
0x18006b851  mov     r8d, 2; KeyValueInformationClass
0x18006b857  mov     [rsp+170h+Length], r15d; Length
0x18006b85c  lea     rdx, [rsp+170h+ValueName]; ValueName
0x18006b861  call    cs:__imp_NtQueryValueKey
0x18006b868  nop     dword ptr [rax+rax+00h]
0x18006b86d  mov     ebx, eax
0x18006b86f  test    eax, eax
0x18006b871  js      short loc_18006B883
0x18006b873  lea     r8, [rbp+70h+KeyValueInformation]
0x18006b877  mov     rdx, rdi
0x18006b87a  mov     ecx, esi
0x18006b87c  call    CopyLangDataFromReg
0x18006b881  mov     ebx, eax
0x18006b883  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x18006b888  test    rcx, rcx
0x18006b88b  jz      short loc_18006B899
0x18006b88d  call    cs:__imp_NtClose
0x18006b894  nop     dword ptr [rax+rax+00h]
0x18006b899  mov     eax, ebx
0x18006b89b  jmp     short loc_18006B8A2
0x18006b89d  mov     eax, 0C000000Dh
0x18006b8a2  mov     rcx, [rbp+70h+var_20]
0x18006b8a6  xor     rcx, rsp; StackCookie
0x18006b8a9  call    __security_check_cookie
0x18006b8ae  lea     r11, [rsp+170h+var_10]
0x18006b8b6  mov     rbx, [r11+28h]
0x18006b8ba  mov     rsi, [r11+30h]
0x18006b8be  mov     rsp, r11
0x18006b8c1  pop     r15
0x18006b8c3  pop     rdi
0x18006b8c4  pop     rbp
0x18006b8c5  retn
```
