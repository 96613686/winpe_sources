# GdiIsUMPDSandboxingEnabled

- ea: `0x180044ea0`
- end: `0x180045100`
- name: `GdiIsUMPDSandboxingEnabled`
- size: `608`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041b00`
- `0x180044e54`
- `0x180045d0c`
- `0x180046570`

## callees

- `0x180041ae0`
- `0x180044ea0`
- `0x180046968`
- `0x18007ac50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044ef0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044ef0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044ed5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044ed5`
- `ntdll!RtlQueryActivationContextApplicationSettings` at `0x1800450c0`
- `ntdll!RtlQueryActivationContextApplicationSettings` at `0x1800450c0`
- `ntdll!RtlInitUnicodeString` at `0x180044f49`
- `ntdll!RtlInitUnicodeString` at `0x180045044`
- `ntdll!RtlInitUnicodeString` at `0x180044f49`
- `ntdll!RtlInitUnicodeString` at `0x180045044`
- `ntdll!NtOpenKey` at `0x180044f7e`
- `ntdll!NtOpenKey` at `0x180044f7e`
- `ntdll!NtClose` at `0x18004508c`
- `ntdll!NtClose` at `0x18004508c`
- `ntdll!NtQueryValueKey` at `0x18004506d`
- `ntdll!NtQueryValueKey` at `0x18004506d`
- `win32u!NtGdiSetUMPDSandboxState` at `0x180045018`
- `win32u!NtGdiSetUMPDSandboxState` at `0x1800450ef`
- `win32u!NtGdiSetUMPDSandboxState` at `0x180045018`
- `win32u!NtGdiSetUMPDSandboxState` at `0x1800450ef`

## string_xrefs

- `0x180044f3e`: `\Registry\Machine\SOFTWARE\Policies\Microsoft\Windows NT\Printers`
- `0x1800450b0`: `http://schemas.microsoft.com/SMI/2011/WindowsSettings`

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
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+90h] [rbp+27h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+A0h] [rbp+37h] BYREF
  int v10; // [rsp+A4h] [rbp+3Bh]
  int v11; // [rsp+ACh] [rbp+43h]

  KeyHandle = 0;
  EnterCriticalSection(&semUMPD);
  *(_QWORD *)&ValueName.Length = &semUMPD;
  if ( !dword_1800FBB1C )
  {
    ResultLength = 0;
    DestinationString = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    if ( gbSplWow64 )
    {
      dword_1800FA470 = 0;
      dword_1800FBB1C = 1;
      NtGdiSetUMPDSandboxState(0);
      v0 = dword_1800FA470;
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
        dword_1800FA470 = 0;
      }
      NtClose(KeyHandle);
    }
    v2 = dword_1800FA470;
    if ( dword_1800FA470 )
    {
      if ( (unsigned int)IsAppContainer() )
      {
        v2 = 0;
        dword_1800FA470 = 0;
      }
      else
      {
        v2 = dword_1800FA470;
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
          dword_1800FA470 = 1;
          goto LABEL_9;
        }
        v2 = 0;
        dword_1800FA470 = 0;
      }
    }
    v3 = 1;
LABEL_9:
    g_bUMPDLegacyWindowParenting = v3;
    dword_1800FBB1C = 1;
    if ( v2 )
    {
      NtGdiSetUMPDSandboxState(v2);
      v2 = dword_1800FA470;
    }
    v0 = v2;
    goto LABEL_3;
  }
  v0 = dword_1800FA470;
LABEL_3:
  LeaveCriticalSection(&semUMPD);
  return v0;
}

```

## disassembly

```asm
0x180044ea0  mov     [rsp-8+arg_0], rbx
0x180044ea5  mov     [rsp-8+arg_8], rdi
0x180044eaa  push    rbp
0x180044eab  lea     rbp, [rsp-57h]
0x180044eb0  sub     rsp, 0C0h
0x180044eb7  mov     rax, cs:__security_cookie
0x180044ebe  xor     rax, rsp
0x180044ec1  mov     [rbp+57h+var_8], rax
0x180044ec5  lea     rdi, semUMPD
0x180044ecc  xor     ebx, ebx
0x180044ece  mov     rcx, rdi; lpCriticalSection
0x180044ed1  mov     [rbp+57h+KeyHandle], rbx
0x180044ed5  call    cs:__imp_EnterCriticalSection
0x180044edb  cmp     cs:dword_1800FBB1C, ebx
0x180044ee1  mov     qword ptr [rbp+57h+ValueName.Length], rdi
0x180044ee5  jz      short loc_180044F19
0x180044ee7  mov     ebx, cs:dword_1800FA470
0x180044eed  mov     rcx, rdi; lpCriticalSection
0x180044ef0  call    cs:__imp_LeaveCriticalSection
0x180044ef6  mov     eax, ebx
0x180044ef8  mov     rcx, [rbp+57h+var_8]
0x180044efc  xor     rcx, rsp; StackCookie
0x180044eff  call    __security_check_cookie
0x180044f04  lea     r11, [rsp+0C0h+var_s0]
0x180044f0c  mov     rbx, [r11+10h]
0x180044f10  mov     rdi, [r11+18h]
0x180044f14  mov     rsp, r11
0x180044f17  pop     rbp
0x180044f18  retn
0x180044f19  cmp     cs:?gbSplWow64@@3HA, ebx; int gbSplWow64
0x180044f1f  xorps   xmm1, xmm1
0x180044f22  xorps   xmm0, xmm0
0x180044f25  mov     [rbp+57h+var_80], ebx
0x180044f28  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180044f2c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x180044f30  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x180044f34  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x180044f38  jnz     loc_180045006
0x180044f3e  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\SOFTWARE\\Policies"...
0x180044f45  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180044f49  call    cs:__imp_RtlInitUnicodeString
0x180044f4f  lea     rax, [rbp+57h+DestinationString]
0x180044f53  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180044f5a  xorps   xmm0, xmm0
0x180044f5d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180044f61  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180044f65  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180044f69  mov     edx, 80000000h; DesiredAccess
0x180044f6e  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180044f75  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180044f79  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180044f7e  call    cs:__imp_NtOpenKey
0x180044f84  test    eax, eax
0x180044f86  jns     loc_180045032
0x180044f8c  mov     eax, cs:dword_1800FA470
0x180044f92  test    eax, eax
0x180044f94  jnz     short loc_180044FBA
0x180044f96  mov     ecx, 1
0x180044f9b  mov     cs:?g_bUMPDLegacyWindowParenting@@3HA, ecx; int g_bUMPDLegacyWindowParenting
0x180044fa1  mov     cs:dword_1800FBB1C, 1
0x180044fab  test    eax, eax
0x180044fad  jnz     loc_1800450ED
0x180044fb3  mov     ebx, eax
0x180044fb5  jmp     loc_180044EED
0x180044fba  call    ?IsAppContainer@@YAHXZ; IsAppContainer(void)
0x180044fbf  test    eax, eax
0x180044fc1  jz      short loc_180044FFE
0x180044fc3  mov     eax, ebx
0x180044fc5  mov     cs:dword_1800FA470, ebx
0x180044fcb  test    eax, eax
0x180044fcd  jz      short loc_180044F96
0x180044fcf  mov     rax, gs:60h
0x180044fd8  mov     rcx, 1000000000h
0x180044fe2  test    [rax+2D0h], rcx
0x180044fe9  jz      loc_180045097
0x180044fef  mov     eax, 1
0x180044ff4  mov     ecx, ebx
0x180044ff6  mov     cs:dword_1800FA470, eax
0x180044ffc  jmp     short loc_180044F9B
0x180044ffe  mov     eax, cs:dword_1800FA470
0x180045004  jmp     short loc_180044FCB
0x180045006  xor     ecx, ecx
0x180045008  mov     cs:dword_1800FA470, ebx
0x18004500e  mov     cs:dword_1800FBB1C, 1
0x180045018  call    cs:__imp_NtGdiSetUMPDSandboxState
0x18004501e  mov     ebx, cs:dword_1800FA470
0x180045024  lea     rcx, [rbp+57h+ValueName]
0x180045028  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18004502d  jmp     loc_180044EF6
0x180045032  xorps   xmm0, xmm0
0x180045035  lea     rdx, aApplicationdri; "ApplicationDriverIsolation"
0x18004503c  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180045040  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x180045044  call    cs:__imp_RtlInitUnicodeString
0x18004504a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18004504e  lea     rax, [rbp+57h+var_80]
0x180045052  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x180045057  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18004505b  mov     r8d, 2; KeyValueInformationClass
0x180045061  mov     [rsp+0C0h+Length], 14h; Length
0x180045069  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18004506d  call    cs:__imp_NtQueryValueKey
0x180045073  test    eax, eax
0x180045075  js      short loc_180045088
0x180045077  cmp     [rbp+57h+var_1C], 4
0x18004507b  jnz     short loc_180045088
0x18004507d  cmp     [rbp+57h+var_14], ebx
0x180045080  jnz     short loc_180045088
0x180045082  mov     cs:dword_1800FA470, ebx
0x180045088  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18004508c  call    cs:__imp_NtClose
0x180045092  jmp     loc_180044F8C
0x180045097  mov     [rsp+0C0h+var_90], rbx
0x18004509c  lea     rax, [rbp+57h+ValueName]
0x1800450a0  mov     [rsp+0C0h+ResultLength], 8
0x1800450a9  lea     r9, aPrinterdriveri; "printerDriverIsolation"
0x1800450b0  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/SMI/2011/W"...
0x1800450b7  mov     qword ptr [rsp+0C0h+Length], rax
0x1800450bc  xor     edx, edx
0x1800450be  xor     ecx, ecx
0x1800450c0  call    cs:__imp_RtlQueryActivationContextApplicationSettings
0x1800450c6  test    eax, eax
0x1800450c8  js      short loc_1800450E0
0x1800450ca  movzx   eax, [rbp+57h+ValueName.Length]
0x1800450ce  mov     ecx, 0FFDFh
0x1800450d3  sub     ax, 54h ; 'T'
0x1800450d7  test    cx, ax
0x1800450da  jz      loc_180044FEF
0x1800450e0  mov     eax, ebx
0x1800450e2  mov     cs:dword_1800FA470, ebx
0x1800450e8  jmp     loc_180044F96
0x1800450ed  mov     ecx, eax
0x1800450ef  call    cs:__imp_NtGdiSetUMPDSandboxState
0x1800450f5  mov     eax, cs:dword_1800FA470
0x1800450fb  jmp     loc_180044FB3
```
