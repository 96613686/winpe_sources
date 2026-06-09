# GdiIsUMPDSandboxingEnabled

- ea: `0x18003ec70`
- end: `0x18003ef0d`
- name: `GdiIsUMPDSandboxingEnabled`
- size: `669`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ec24`
- `0x18003fb74`
- `0x180040468`
- `0x1800410a4`

## callees

- `0x18003ec70`
- `0x180040898`
- `0x1800413f0`
- `0x18007f800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ecc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ecc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003eca5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003eca5`
- `ntdll!RtlQueryActivationContextApplicationSettings` at `0x18003eec1`
- `ntdll!RtlQueryActivationContextApplicationSettings` at `0x18003eec1`
- `ntdll!RtlInitUnicodeString` at `0x18003ed26`
- `ntdll!RtlInitUnicodeString` at `0x18003ee33`
- `ntdll!RtlInitUnicodeString` at `0x18003ed26`
- `ntdll!RtlInitUnicodeString` at `0x18003ee33`
- `ntdll!NtOpenKey` at `0x18003ed61`
- `ntdll!NtOpenKey` at `0x18003ed61`
- `ntdll!NtClose` at `0x18003ee87`
- `ntdll!NtClose` at `0x18003ee87`
- `ntdll!NtQueryValueKey` at `0x18003ee62`
- `ntdll!NtQueryValueKey` at `0x18003ee62`
- `win32u!NtGdiSetUMPDSandboxState` at `0x18003ee01`
- `win32u!NtGdiSetUMPDSandboxState` at `0x18003eef6`
- `win32u!NtGdiSetUMPDSandboxState` at `0x18003ee01`
- `win32u!NtGdiSetUMPDSandboxState` at `0x18003eef6`

## string_xrefs

- `0x18003ed1b`: `\Registry\Machine\SOFTWARE\Policies\Microsoft\Windows NT\Printers`
- `0x18003eeb1`: `http://schemas.microsoft.com/SMI/2011/WindowsSettings`

## pseudocode

```c
__int64 GdiIsUMPDSandboxingEnabled()
{
  unsigned int v0; // ebx
  unsigned int v2; // eax
  int v3; // ecx
  ULONG ResultLength; // [rsp+40h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+90h] [rbp+27h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+A0h] [rbp+37h] BYREF
  int v10; // [rsp+A4h] [rbp+3Bh]
  int v11; // [rsp+ACh] [rbp+43h]

  KeyHandle = 0;
  EnterCriticalSection(&semUMPD);
  *(_QWORD *)&ValueName.Length = &semUMPD;
  if ( !dword_1800FEBFC )
  {
    ResultLength = 0;
    DestinationString = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    if ( gbSplWow64 )
    {
      dword_1800FD570 = 0;
      dword_1800FEBFC = 1;
      NtGdiSetUMPDSandboxState(0);
      v0 = dword_1800FD570;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&ValueName);
      return v0;
    }
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\SOFTWARE\\Policies\\Microsoft\\Windows NT\\Printers");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes) >= 0 )
    {
      ValueName = 0;
      RtlInitUnicodeString(&ValueName, L"ApplicationDriverIsolation");
      if ( NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x14u, &ResultLength) >= 0
        && v10 == 4
        && !v11 )
      {
        dword_1800FD570 = 0;
      }
      NtClose(KeyHandle);
    }
    v2 = dword_1800FD570;
    if ( dword_1800FD570 )
    {
      if ( (unsigned int)IsAppContainer() )
      {
        v2 = 0;
        dword_1800FD570 = 0;
      }
      else
      {
        v2 = dword_1800FD570;
      }
      if ( v2 )
      {
        if ( (NtCurrentPeb()->AppCompatFlagsUser.QuadPart & 0x1000000000LL) != 0
          || (int)RtlQueryActivationContextApplicationSettings(
                    0,
                    0,
                    L"http://schemas.microsoft.com/SMI/2011/WindowsSettings",
                    L"printerDriverIsolation",
                    &ValueName,
                    8,
                    0) >= 0
          && ((ValueName.Length - 84) & 0xFFDF) == 0 )
        {
          v2 = 1;
          v3 = 0;
          dword_1800FD570 = 1;
          goto LABEL_9;
        }
        v2 = 0;
        dword_1800FD570 = 0;
      }
    }
    v3 = 1;
LABEL_9:
    g_bUMPDLegacyWindowParenting = v3;
    dword_1800FEBFC = 1;
    if ( v2 )
    {
      NtGdiSetUMPDSandboxState(v2);
      v2 = dword_1800FD570;
    }
    v0 = v2;
    goto LABEL_3;
  }
  v0 = dword_1800FD570;
LABEL_3:
  LeaveCriticalSection(&semUMPD);
  return v0;
}

```

## disassembly

```asm
0x18003ec70  mov     [rsp-8+arg_0], rbx
0x18003ec75  mov     [rsp-8+arg_8], rdi
0x18003ec7a  push    rbp
0x18003ec7b  lea     rbp, [rsp-57h]
0x18003ec80  sub     rsp, 0C0h
0x18003ec87  mov     rax, cs:__security_cookie
0x18003ec8e  xor     rax, rsp
0x18003ec91  mov     [rbp+57h+var_8], rax
0x18003ec95  lea     rdi, semUMPD
0x18003ec9c  xor     ebx, ebx
0x18003ec9e  mov     rcx, rdi; lpCriticalSection
0x18003eca1  mov     [rbp+57h+KeyHandle], rbx
0x18003eca5  call    cs:__imp_EnterCriticalSection
0x18003ecac  nop     dword ptr [rax+rax+00h]
0x18003ecb1  cmp     cs:dword_1800FEBFC, ebx
0x18003ecb7  mov     qword ptr [rbp+57h+ValueName.Length], rdi
0x18003ecbb  jz      short loc_18003ECF6
0x18003ecbd  mov     ebx, cs:dword_1800FD570
0x18003ecc3  mov     rcx, rdi; lpCriticalSection
0x18003ecc6  call    cs:__imp_LeaveCriticalSection
0x18003eccd  nop     dword ptr [rax+rax+00h]
0x18003ecd2  mov     eax, ebx
0x18003ecd4  mov     rcx, [rbp+57h+var_8]
0x18003ecd8  xor     rcx, rsp; StackCookie
0x18003ecdb  call    __security_check_cookie
0x18003ece0  lea     r11, [rsp+0C0h+var_s0]
0x18003ece8  mov     rbx, [r11+10h]
0x18003ecec  mov     rdi, [r11+18h]
0x18003ecf0  mov     rsp, r11
0x18003ecf3  pop     rbp
0x18003ecf4  retn
0x18003ecf6  cmp     cs:?gbSplWow64@@3HA, ebx; int gbSplWow64
0x18003ecfc  xorps   xmm1, xmm1
0x18003ecff  xorps   xmm0, xmm0
0x18003ed02  mov     [rbp+57h+var_80], ebx
0x18003ed05  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003ed09  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18003ed0d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18003ed11  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18003ed15  jnz     loc_18003EDEF
0x18003ed1b  lea     rdx, SourceString; "\\Registry\\Machine\\SOFTWARE\\Policies"...
0x18003ed22  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003ed26  call    cs:__imp_RtlInitUnicodeString
0x18003ed2d  nop     dword ptr [rax+rax+00h]
0x18003ed32  lea     rax, [rbp+57h+DestinationString]
0x18003ed36  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003ed3d  xorps   xmm0, xmm0
0x18003ed40  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003ed44  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003ed48  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x18003ed4c  mov     edx, 80000000h; DesiredAccess
0x18003ed51  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18003ed58  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18003ed5c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003ed61  call    cs:__imp_NtOpenKey
0x18003ed68  nop     dword ptr [rax+rax+00h]
0x18003ed6d  test    eax, eax
0x18003ed6f  jns     loc_18003EE21
0x18003ed75  mov     eax, cs:dword_1800FD570
0x18003ed7b  test    eax, eax
0x18003ed7d  jnz     short loc_18003EDA3
0x18003ed7f  mov     ecx, 1
0x18003ed84  mov     cs:?g_bUMPDLegacyWindowParenting@@3HA, ecx; int g_bUMPDLegacyWindowParenting
0x18003ed8a  mov     cs:dword_1800FEBFC, 1
0x18003ed94  test    eax, eax
0x18003ed96  jnz     loc_18003EEF4
0x18003ed9c  mov     ebx, eax
0x18003ed9e  jmp     loc_18003ECC3
0x18003eda3  call    ?IsAppContainer@@YAHXZ; IsAppContainer(void)
0x18003eda8  test    eax, eax
0x18003edaa  jz      short loc_18003EDE7
0x18003edac  mov     eax, ebx
0x18003edae  mov     cs:dword_1800FD570, ebx
0x18003edb4  test    eax, eax
0x18003edb6  jz      short loc_18003ED7F
0x18003edb8  mov     rax, gs:60h
0x18003edc1  mov     rcx, 1000000000h
0x18003edcb  test    [rax+2D0h], rcx
0x18003edd2  jz      loc_18003EE98
0x18003edd8  mov     eax, 1
0x18003eddd  mov     ecx, ebx
0x18003eddf  mov     cs:dword_1800FD570, eax
0x18003ede5  jmp     short loc_18003ED84
0x18003ede7  mov     eax, cs:dword_1800FD570
0x18003eded  jmp     short loc_18003EDB4
0x18003edef  xor     ecx, ecx
0x18003edf1  mov     cs:dword_1800FD570, ebx
0x18003edf7  mov     cs:dword_1800FEBFC, 1
0x18003ee01  call    cs:__imp_NtGdiSetUMPDSandboxState
0x18003ee08  nop     dword ptr [rax+rax+00h]
0x18003ee0d  mov     ebx, cs:dword_1800FD570
0x18003ee13  lea     rcx, [rbp+57h+ValueName]
0x18003ee17  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003ee1c  jmp     loc_18003ECD2
0x18003ee21  xorps   xmm0, xmm0
0x18003ee24  lea     rdx, aApplicationdri; "ApplicationDriverIsolation"
0x18003ee2b  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x18003ee2f  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x18003ee33  call    cs:__imp_RtlInitUnicodeString
0x18003ee3a  nop     dword ptr [rax+rax+00h]
0x18003ee3f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18003ee43  lea     rax, [rbp+57h+var_80]
0x18003ee47  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x18003ee4c  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18003ee50  mov     r8d, 2; KeyValueInformationClass
0x18003ee56  mov     [rsp+0C0h+Length], 14h; Length
0x18003ee5e  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18003ee62  call    cs:__imp_NtQueryValueKey
0x18003ee69  nop     dword ptr [rax+rax+00h]
0x18003ee6e  test    eax, eax
0x18003ee70  js      short loc_18003EE83
0x18003ee72  cmp     [rbp+57h+var_1C], 4
0x18003ee76  jnz     short loc_18003EE83
0x18003ee78  cmp     [rbp+57h+var_14], ebx
0x18003ee7b  jnz     short loc_18003EE83
0x18003ee7d  mov     cs:dword_1800FD570, ebx
0x18003ee83  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18003ee87  call    cs:__imp_NtClose
0x18003ee8e  nop     dword ptr [rax+rax+00h]
0x18003ee93  jmp     loc_18003ED75
0x18003ee98  mov     [rsp+0C0h+var_90], rbx
0x18003ee9d  lea     rax, [rbp+57h+ValueName]
0x18003eea1  mov     [rsp+0C0h+ResultLength], 8
0x18003eeaa  lea     r9, aPrinterdriveri; "printerDriverIsolation"
0x18003eeb1  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/SMI/2011/W"...
0x18003eeb8  mov     qword ptr [rsp+0C0h+Length], rax
0x18003eebd  xor     edx, edx
0x18003eebf  xor     ecx, ecx
0x18003eec1  call    cs:__imp_RtlQueryActivationContextApplicationSettings
0x18003eec8  nop     dword ptr [rax+rax+00h]
0x18003eecd  test    eax, eax
0x18003eecf  js      short loc_18003EEE7
0x18003eed1  movzx   eax, [rbp+57h+ValueName.Length]
0x18003eed5  mov     ecx, 0FFDFh
0x18003eeda  sub     ax, 54h ; 'T'
0x18003eede  test    cx, ax
0x18003eee1  jz      loc_18003EDD8
0x18003eee7  mov     eax, ebx
0x18003eee9  mov     cs:dword_1800FD570, ebx
0x18003eeef  jmp     loc_18003ED7F
0x18003eef4  mov     ecx, eax
0x18003eef6  call    cs:__imp_NtGdiSetUMPDSandboxState
0x18003eefd  nop     dword ptr [rax+rax+00h]
0x18003ef02  mov     eax, cs:dword_1800FD570
0x18003ef08  jmp     loc_18003ED9C
```
