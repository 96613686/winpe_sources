# OpenGlobalizationUserSettingsKey_ForMua

- ea: `0x18002aabc`
- end: `0x18002ad01`
- name: `OpenGlobalizationUserSettingsKey_ForMua`
- size: `581`
- prototype: `__int64 __fastcall(ACCESS_MASK DesiredAccess, PSID Sid, PHANDLE KeyHandle)`
- caller_count: `16`
- callee_count: `5`
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
- `0x18002ad10`
- `0x18002b12c`
- `0x18002b780`
- `0x18002bea0`
- `0x180046ac0`
- `0x180048f20`
- `0x18004a820`
- `0x180147bf0`

## callees

- `0x18002aabc`
- `0x18002d7e0`
- `0x18011115c`
- `0x18012c3ac`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x180199ef7`
- `ntdll!RtlSubAuthoritySid` at `0x180199f11`
- `ntdll!RtlSubAuthoritySid` at `0x180199ef7`
- `ntdll!RtlSubAuthoritySid` at `0x180199f11`
- `ntdll!RtlFreeUnicodeString` at `0x18002ace1`
- `ntdll!RtlFreeUnicodeString` at `0x18002ace1`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002ab75`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002ab75`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002ac0b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002ac0b`
- `ntdll!RtlAppendUnicodeToString` at `0x18002abc9`
- `ntdll!RtlAppendUnicodeToString` at `0x18002abeb`
- `ntdll!RtlAppendUnicodeToString` at `0x18002abc9`
- `ntdll!RtlAppendUnicodeToString` at `0x18002abeb`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18002ab27`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18002ab27`
- `ntdll!RtlSubAuthorityCountSid` at `0x180199ed1`
- `ntdll!RtlSubAuthorityCountSid` at `0x180199ed1`
- `ntdll!ZwQueryInformationToken` at `0x180199eb5`
- `ntdll!ZwQueryInformationToken` at `0x180199eb5`
- `ntdll!ZwClose` at `0x18002ac6b`
- `ntdll!ZwClose` at `0x18002ac6b`
- `ntdll!ZwOpenKey` at `0x18002ac56`
- `ntdll!ZwOpenKey` at `0x18002ac89`
- `ntdll!ZwOpenKey` at `0x18002ac56`
- `ntdll!ZwOpenKey` at `0x18002ac89`

## string_xrefs

- `0x18002ab4c`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\International`
- `0x18002ab67`: `TargetNtPath`

## pseudocode

```c
__int64 __fastcall OpenGlobalizationUserSettingsKey_ForMua(
        ACCESS_MASK DesiredAccess,
        PSID Sid,
        PHANDLE KeyHandle,
        _DWORD *a4)
{
  PSID v6; // rbx
  PSID *v8; // rdi
  NTSTATUS PersistedStateLocation; // ebx
  USHORT v10; // bx
  WCHAR *v11; // rax
  WCHAR *v12; // rsi
  int v13; // r14d
  PUCHAR v15; // rax
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE KeyHandlea; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Source[264]; // [rsp+A0h] [rbp-60h] BYREF

  v6 = Sid;
  UnicodeString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( Sid )
  {
    v8 = 0;
  }
  else
  {
    v8 = (PSID *)wil::details::heap_allocator::allocate(0x54u);
    if ( !v8 )
      return (unsigned int)-1073741801;
    ResultLength = 0;
    PersistedStateLocation = ZwQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, v8, 0x54u, &ResultLength);
    if ( PersistedStateLocation < 0 )
      goto LABEL_19;
    v6 = *v8;
  }
  v15 = RtlSubAuthorityCountSid(v6);
  if ( *v15 < 2u || (v13 = 0, *v15 == 5) && *RtlSubAuthoritySid(v6, 0) == 21 && *RtlSubAuthoritySid(v6, 4u) == 503 )
  {
    *a4 = 0;
LABEL_28:
    PersistedStateLocation = OpenGlobalizationUserSettingsKey_ForSingleUserModel(DesiredAccess, KeyHandle);
    goto LABEL_13;
  }
  PersistedStateLocation = RtlConvertSidToUnicodeString(&UnicodeString, v6, 1u);
  if ( PersistedStateLocation >= 0 )
  {
    ResultLength = 0;
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"GlobalizationUserSettings",
                               L"TargetNtPath",
                               L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\International",
                               0,
                               Source,
                               520,
                               &ResultLength);
    if ( PersistedStateLocation >= 0 )
    {
      v10 = ResultLength + UnicodeString.Length + 4;
      v11 = (WCHAR *)wil::details::heap_allocator::allocate(v10);
      v12 = v11;
      if ( v11 )
      {
        *(_QWORD *)&Destination.Length = 0;
        Destination.MaximumLength = v10;
        Destination.Buffer = v11;
        PersistedStateLocation = RtlAppendUnicodeToString(&Destination, Source);
        if ( PersistedStateLocation >= 0 )
        {
          PersistedStateLocation = RtlAppendUnicodeToString(&Destination, L"\\");
          if ( PersistedStateLocation >= 0 )
          {
            PersistedStateLocation = RtlAppendUnicodeStringToString(&Destination, &UnicodeString);
            if ( PersistedStateLocation >= 0 )
            {
              ObjectAttributes.Length = 48;
              ObjectAttributes.ObjectName = &Destination;
              ObjectAttributes.RootDirectory = 0;
              ObjectAttributes.Attributes = 576;
              KeyHandlea = 0;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              if ( ZwOpenKey(&KeyHandlea, 0x20019u, &ObjectAttributes) < 0 )
              {
                v13 = 1;
                *a4 = 1;
              }
              else
              {
                ZwClose(KeyHandlea);
                *a4 = 2;
                PersistedStateLocation = ZwOpenKey(KeyHandle, DesiredAccess, &ObjectAttributes);
              }
            }
          }
        }
        FreeEnvironmentStringsW(v12);
      }
      else
      {
        PersistedStateLocation = -1073741801;
      }
    }
    RtlFreeUnicodeString(&UnicodeString);
  }
  if ( v13 )
    goto LABEL_28;
LABEL_13:
  if ( v8 )
LABEL_19:
    FreeEnvironmentStringsW((LPWCH)v8);
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x18002aabc  push    rbp
0x18002aabe  push    rbx
0x18002aabf  push    rsi
0x18002aac0  push    rdi
0x18002aac1  push    r12
0x18002aac3  push    r13
0x18002aac5  push    r14
0x18002aac7  push    r15
0x18002aac9  lea     rbp, [rsp-1C8h]
0x18002aad1  sub     rsp, 2C8h
0x18002aad8  mov     rax, cs:__security_cookie
0x18002aadf  xor     rax, rsp
0x18002aae2  mov     [rbp+200h+var_50], rax
0x18002aae9  xorps   xmm0, xmm0
0x18002aaec  xor     eax, eax
0x18002aaee  mov     r15, r9
0x18002aaf1  mov     r13, r8
0x18002aaf4  mov     rbx, rdx
0x18002aaf7  mov     r12d, ecx
0x18002aafa  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x18002aafe  movups  xmmword ptr [rbp+200h+ObjectAttributes+1Ch], xmm0
0x18002ab02  movups  xmmword ptr [rsp+300h+UnicodeString.Length], xmm0
0x18002ab07  movups  xmmword ptr [rsp+300h+ObjectAttributes.Length], xmm0
0x18002ab0c  test    rdx, rdx
0x18002ab0f  jz      loc_180199E7E
0x18002ab15  xor     edi, edi
0x18002ab17  jmp     loc_180199ECE
0x18002ab1c  mov     r8b, 1; AllocateDestinationString
0x18002ab1f  lea     rcx, [rsp+300h+UnicodeString]; UnicodeString
0x18002ab24  mov     rdx, rbx; Sid
0x18002ab27  call    cs:__imp_RtlConvertSidToUnicodeString
0x18002ab2e  nop     dword ptr [rax+rax+00h]
0x18002ab33  mov     ebx, eax
0x18002ab35  test    eax, eax
0x18002ab37  js      loc_18002ACED
0x18002ab3d  lea     rax, [rsp+300h+var_2C0]
0x18002ab42  mov     [rsp+300h+var_2C0], r14d
0x18002ab47  mov     [rsp+300h+var_2D0], rax
0x18002ab4c  lea     r8, aRegistryMachin_35; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18002ab53  lea     rax, [rbp+200h+Source]
0x18002ab57  mov     [rsp+300h+var_2D8], 208h
0x18002ab5f  xor     r9d, r9d
0x18002ab62  mov     [rsp+300h+ResultLength], rax
0x18002ab67  lea     rdx, aTargetntpath; "TargetNtPath"
0x18002ab6e  lea     rcx, aGlobalizationu; "GlobalizationUserSettings"
0x18002ab75  call    cs:__imp_RtlGetPersistedStateLocation
0x18002ab7c  nop     dword ptr [rax+rax+00h]
0x18002ab81  mov     ebx, eax
0x18002ab83  test    eax, eax
0x18002ab85  js      loc_18002ACDC
0x18002ab8b  movzx   eax, [rsp+300h+UnicodeString.Length]
0x18002ab90  add     ax, word ptr [rsp+300h+var_2C0]
0x18002ab95  add     ax, si
0x18002ab98  movzx   ebx, ax
0x18002ab9b  mov     ecx, ebx; unsigned __int64
0x18002ab9d  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18002aba2  mov     rsi, rax
0x18002aba5  test    rax, rax
0x18002aba8  jz      loc_18002ACD7
0x18002abae  xorps   xmm0, xmm0
0x18002abb1  lea     rdx, [rbp+200h+Source]; Source
0x18002abb5  movups  xmmword ptr [rsp+300h+Destination.Length], xmm0
0x18002abba  lea     rcx, [rsp+300h+Destination]; Destination
0x18002abbf  mov     [rsp+300h+Destination.MaximumLength], bx
0x18002abc4  mov     [rsp+300h+Destination.Buffer], rax
0x18002abc9  call    cs:__imp_RtlAppendUnicodeToString
0x18002abd0  nop     dword ptr [rax+rax+00h]
0x18002abd5  mov     ebx, eax
0x18002abd7  test    eax, eax
0x18002abd9  js      loc_18002AC97
0x18002abdf  lea     rdx, asc_18029DEC8; "\\"
0x18002abe6  lea     rcx, [rsp+300h+Destination]; Destination
0x18002abeb  call    cs:__imp_RtlAppendUnicodeToString
0x18002abf2  nop     dword ptr [rax+rax+00h]
0x18002abf7  mov     ebx, eax
0x18002abf9  test    eax, eax
0x18002abfb  js      loc_18002AC97
0x18002ac01  lea     rdx, [rsp+300h+UnicodeString]; Source
0x18002ac06  lea     rcx, [rsp+300h+Destination]; Destination
0x18002ac0b  call    cs:__imp_RtlAppendUnicodeStringToString
0x18002ac12  nop     dword ptr [rax+rax+00h]
0x18002ac17  mov     ebx, eax
0x18002ac19  test    eax, eax
0x18002ac1b  js      short loc_18002AC97
0x18002ac1d  lea     rax, [rsp+300h+Destination]
0x18002ac22  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x18002ac2a  xorps   xmm0, xmm0
0x18002ac2d  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x18002ac31  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x18002ac36  mov     [rsp+300h+ObjectAttributes.RootDirectory], r14
0x18002ac3b  mov     edx, 20019h; DesiredAccess
0x18002ac40  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x18002ac47  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x18002ac4c  mov     [rsp+300h+KeyHandle], r14
0x18002ac51  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002ac56  call    cs:__imp_ZwOpenKey
0x18002ac5d  nop     dword ptr [rax+rax+00h]
0x18002ac62  test    eax, eax
0x18002ac64  js      short loc_18002ACA1
0x18002ac66  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x18002ac6b  call    cs:__imp_ZwClose
0x18002ac72  nop     dword ptr [rax+rax+00h]
0x18002ac77  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x18002ac7c  mov     dword ptr [r15], 2
0x18002ac83  mov     edx, r12d; DesiredAccess
0x18002ac86  mov     rcx, r13; KeyHandle
0x18002ac89  call    cs:__imp_ZwOpenKey
0x18002ac90  nop     dword ptr [rax+rax+00h]
0x18002ac95  mov     ebx, eax
0x18002ac97  mov     rcx, rsi; penv
0x18002ac9a  call    FreeEnvironmentStringsW
0x18002ac9f  jmp     short loc_18002ACDC
0x18002aca1  mov     r14d, 1
0x18002aca7  mov     [r15], r14d
0x18002acaa  jmp     short loc_18002AC97
0x18002acac  test    rdi, rdi
0x18002acaf  jnz     short loc_18002ACF7
0x18002acb1  mov     eax, ebx
0x18002acb3  mov     rcx, [rbp+200h+var_50]
0x18002acba  xor     rcx, rsp; StackCookie
0x18002acbd  call    __security_check_cookie
0x18002acc2  add     rsp, 2C8h
0x18002acc9  pop     r15
0x18002accb  pop     r14
0x18002accd  pop     r13
0x18002accf  pop     r12
0x18002acd1  pop     rdi
0x18002acd2  pop     rsi
0x18002acd3  pop     rbx
0x18002acd4  pop     rbp
0x18002acd5  retn
0x18002acd7  mov     ebx, 0C0000017h
0x18002acdc  lea     rcx, [rsp+300h+UnicodeString]; UnicodeString
0x18002ace1  call    cs:__imp_RtlFreeUnicodeString
0x18002ace8  nop     dword ptr [rax+rax+00h]
0x18002aced  test    r14d, r14d
0x18002acf0  jz      short loc_18002ACAC
0x18002acf2  jmp     loc_180199F30
0x18002acf7  mov     rcx, rdi; penv
0x18002acfa  call    FreeEnvironmentStringsW
0x18002acff  jmp     short loc_18002ACB1
0x180199e7e  mov     ebx, 54h ; 'T'
0x180199e83  mov     ecx, ebx; unsigned __int64
0x180199e85  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180199e8a  mov     rdi, rax
0x180199e8d  test    rax, rax
0x180199e90  jz      loc_180199F42
0x180199e96  lea     rax, [rsp+300h+var_2C0]
0x180199e9b  mov     [rsp+300h+var_2C0], 0
0x180199ea3  mov     r9d, ebx; Length
0x180199ea6  mov     [rsp+300h+ResultLength], rax; ResultLength
0x180199eab  mov     r8, rdi; TokenInformation
0x180199eae  lea     edx, [rbx-53h]; TokenInformationClass
0x180199eb1  lea     rcx, [rbx-5Ah]; TokenHandle
0x180199eb5  call    cs:__imp_ZwQueryInformationToken
0x180199ebc  nop     dword ptr [rax+rax+00h]
0x180199ec1  mov     ebx, eax
0x180199ec3  test    eax, eax
0x180199ec5  js      loc_18002ACF7
0x180199ecb  mov     rbx, [rdi]
0x180199ece  mov     rcx, rbx; Sid
0x180199ed1  call    cs:__imp_RtlSubAuthorityCountSid
0x180199ed8  nop     dword ptr [rax+rax+00h]
0x180199edd  cmp     byte ptr [rax], 2
0x180199ee0  jb      short loc_180199F29
0x180199ee2  xor     r14d, r14d
0x180199ee5  cmp     byte ptr [rax], 5
0x180199ee8  lea     esi, [r14+4]
0x180199eec  jnz     loc_18002AB1C
0x180199ef2  xor     edx, edx; SubAuthority
0x180199ef4  mov     rcx, rbx; Sid
0x180199ef7  call    cs:__imp_RtlSubAuthoritySid
0x180199efe  nop     dword ptr [rax+rax+00h]
0x180199f03  cmp     dword ptr [rax], 15h
0x180199f06  jnz     loc_18002AB1C
0x180199f0c  mov     edx, esi; SubAuthority
0x180199f0e  mov     rcx, rbx; Sid
0x180199f11  call    cs:__imp_RtlSubAuthoritySid
0x180199f18  nop     dword ptr [rax+rax+00h]
0x180199f1d  cmp     dword ptr [rax], 1F7h
0x180199f23  jnz     loc_18002AB1C
0x180199f29  mov     dword ptr [r15], 0
0x180199f30  mov     rdx, r13; KeyHandle
0x180199f33  mov     ecx, r12d; DesiredAccess
0x180199f36  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x180199f3b  mov     ebx, eax
0x180199f3d  jmp     loc_18002ACAC
0x180199f42  mov     ebx, 0C0000017h
0x180199f47  jmp     loc_18002ACB1
```
