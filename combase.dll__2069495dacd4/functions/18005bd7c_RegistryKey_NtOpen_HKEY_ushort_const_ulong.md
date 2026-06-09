# RegistryKey::NtOpen(HKEY__ *,ushort const *,ulong)

- ea: `0x18005bd7c`
- end: `0x18005bfb0`
- name: `?NtOpen@RegistryKey@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `564`
- prototype: `HRESULT __fastcall(RegistryKey *this, HKEY__ *hkeyAncestor, const wchar_t *pszSubKeyPath, unsigned int desiredAccess)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005b960`
- `0x180132e50`

## callees

- `0x18000833c`
- `0x18005b0a0`
- `0x18005bd7c`
- `0x1801999b0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18005bdf2`
- `ntdll!NtOpenKey` at `0x18005bdf2`
- `ntdll!NtQueryKey` at `0x18005be62`
- `ntdll!NtQueryKey` at `0x18005be62`
- `ntdll!RtlNtStatusToDosError` at `0x18005bdfa`
- `ntdll!RtlNtStatusToDosError` at `0x18005be6a`
- `ntdll!RtlNtStatusToDosError` at `0x18005bdfa`
- `ntdll!RtlNtStatusToDosError` at `0x18005be6a`
- `ntdll!RtlInitUnicodeString` at `0x18005bdba`
- `ntdll!RtlInitUnicodeString` at `0x18005bdba`

## string_xrefs

- `0x18005beb3`: `StaticNtOpen`
- `0x18005bf0e`: `StaticNtOpen`
- `0x18005bf59`: `StaticNtOpen`
- `0x18005be88`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005beef`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005bf3e`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005bf97`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005bec8`: `%hs failed with path:%.*ls %.*ls`
- `0x18005bf23`: `%hs failed with path: %.*ls queryHr: %x`
- `0x18005bf6e`: `%hs failed with path: %.*ls`

## pseudocode

```c
__int64 __fastcall RegistryKey::NtOpen(
        RegistryKey *this,
        HKEY__ *hkeyAncestor,
        const wchar_t *pszSubKeyPath,
        ACCESS_MASK desiredAccess)
{
  NTSTATUS v7; // eax
  signed int v8; // eax
  HRESULT v9; // edi
  NTSTATUS v11; // eax
  signed int v12; // eax
  HRESULT v13; // ebx
  _UNICODE_STRING subKeyPath; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int ResultLength; // [rsp+60h] [rbp-A0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  int KeyInformation; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v18[262]; // [rsp+A4h] [rbp-5Ch] BYREF
  void *retaddr; // [rsp+2E8h] [rbp+1E8h]

  subKeyPath = 0;
  RtlInitUnicodeString(&subKeyPath, pszSubKeyPath);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &subKeyPath;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = hkeyAncestor;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenKey((PHANDLE)&this->_hkey, desiredAccess, &ObjectAttributes);
  v8 = RtlNtStatusToDosError(v7);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 != -2147024894 && v9 < 0 )
  {
    if ( hkeyAncestor )
    {
      ResultLength = 516;
      v11 = NtQueryKey(hkeyAncestor, KeyNameInformation, &KeyInformation, 0x204u, &ResultLength);
      v12 = RtlNtStatusToDosError(v11);
      v13 = v12;
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
      if ( v13 < 0 )
      {
        if ( v13 != -2147024662 && v13 != -2147024774 )
          wil::details::in1diag3::_Log_Hr(retaddr, 0x7E1u, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v13);
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          0x214u,
          "onecore\\com\\combase\\inc\\RegistryKey.hpp",
          v9,
          "%hs failed with path: %.*ls queryHr: %x",
          "StaticNtOpen",
          subKeyPath.Length,
          subKeyPath.Buffer,
          v13);
      }
      else
      {
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          0x210u,
          "onecore\\com\\combase\\inc\\RegistryKey.hpp",
          v9,
          "%hs failed with path:%.*ls %.*ls",
          "StaticNtOpen",
          KeyInformation,
          v18,
          subKeyPath.Length,
          subKeyPath.Buffer);
      }
    }
    else
    {
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        0x200u,
        "onecore\\com\\combase\\inc\\RegistryKey.hpp",
        v9,
        "%hs failed with path: %.*ls",
        "StaticNtOpen",
        subKeyPath.Length,
        subKeyPath.Buffer);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005bd7c  push    rbp
0x18005bd7e  push    rbx
0x18005bd7f  push    rsi
0x18005bd80  push    rdi
0x18005bd81  lea     rbp, [rsp-1C8h]
0x18005bd89  sub     rsp, 2C8h
0x18005bd90  mov     rax, cs:__security_cookie
0x18005bd97  xor     rax, rsp
0x18005bd9a  mov     [rbp+1E0h+var_30], rax
0x18005bda1  mov     rsi, hkeyAncestor
0x18005bda4  mov     rbx, this
0x18005bda7  xorps   xmm0, xmm0
0x18005bdaa  lea     this, [rsp+2E0h+subKeyPath]; DestinationString
0x18005bdaf  mov     hkeyAncestor, pszSubKeyPath; SourceString
0x18005bdb2  mov     edi, desiredAccess
0x18005bdb5  movups  xmmword ptr [rsp+2E0h+subKeyPath.Length], xmm0
0x18005bdba  call    cs:__imp_RtlInitUnicodeString
0x18005bdc0  lea     rax, [rsp+2E0h+subKeyPath]
0x18005bdc5  mov     qword ptr [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x18005bdce  xorps   xmm0, xmm0
0x18005bdd1  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x18005bdd6  lea     pszSubKeyPath, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x18005bddb  mov     qword ptr [rbp+1E0h+ObjectAttributes.Attributes], 40h ; '@'
0x18005bde3  mov     edx, edi; DesiredAccess
0x18005bde5  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rsi
0x18005bdea  mov     this, rbx; KeyHandle
0x18005bded  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005bdf2  call    cs:__imp_NtOpenKey
0x18005bdf8  mov     ecx, eax; Status
0x18005bdfa  call    cs:__imp_RtlNtStatusToDosError
0x18005be00  mov     edi, eax
0x18005be02  test    eax, eax
0x18005be04  jle     short loc_18005BE0F
0x18005be06  movzx   edi, ax
0x18005be09  or      edi, 80070000h
0x18005be0f  cmp     edi, 80070002h
0x18005be15  jz      short loc_18005BE1B
0x18005be17  test    edi, edi
0x18005be19  js      short loc_18005BE38
0x18005be1b  mov     eax, edi
0x18005be1d  mov     this, [rbp+1E0h+var_30]
0x18005be24  xor     this, rsp; StackCookie
0x18005be27  call    __security_check_cookie
0x18005be2c  add     rsp, 2C8h
0x18005be33  pop     rdi
0x18005be34  pop     rsi
0x18005be35  pop     rbx
0x18005be36  pop     rbp
0x18005be37  retn
0x18005be38  test    rsi, rsi
0x18005be3b  jz      loc_18005BF39
0x18005be41  mov     desiredAccess, 204h; Length
0x18005be47  lea     rax, [rsp+2E0h+var_280]
0x18005be4c  lea     pszSubKeyPath, [rbp+1E0h+KeyInformation]; KeyInformation
0x18005be50  mov     [rsp+2E0h+var_280], desiredAccess
0x18005be55  mov     edx, 3; KeyInformationClass
0x18005be5a  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x18005be5f  mov     this, rsi; KeyHandle
0x18005be62  call    cs:__imp_NtQueryKey
0x18005be68  mov     ecx, eax; Status
0x18005be6a  call    cs:__imp_RtlNtStatusToDosError
0x18005be70  mov     ebx, eax
0x18005be72  test    eax, eax
0x18005be74  jle     short loc_18005BE7F
0x18005be76  movzx   ebx, ax
0x18005be79  or      ebx, 80070000h
0x18005be7f  test    ebx, ebx
0x18005be81  js      short loc_18005BEDE
0x18005be83  mov     rax, [rsp+2E0h+subKeyPath.Buffer]
0x18005be88  lea     pszSubKeyPath, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005be8f  movzx   edx, [rsp+2E0h+subKeyPath.Length]
0x18005be94  mov     desiredAccess, edi; hr
0x18005be97  mov     this, [rbp+1E8h]; callerReturnAddress
0x18005be9e  mov     [rsp+2E0h+var_298], rax
0x18005bea3  lea     rax, [rbp+1E0h+var_23C]
0x18005bea7  mov     [rsp+2E0h+var_2A0], edx
0x18005beab  mov     edx, [rbp+1E0h+KeyInformation]
0x18005beae  mov     [rsp+2E0h+var_2A8], rax
0x18005beb3  lea     rax, callerFunction; "StaticNtOpen"
0x18005beba  mov     [rsp+2E0h+var_2B0], edx
0x18005bebe  mov     edx, 210h; lineNumber
0x18005bec3  mov     [rsp+2E0h+var_2B8], rax
0x18005bec8  lea     rax, aHsFailedWithPa; "%hs failed with path:%.*ls %.*ls"
0x18005becf  mov     [rsp+2E0h+ResultLength], rax; formatString
0x18005bed4  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005bed9  jmp     loc_18005BE1B
0x18005bede  cmp     ebx, 800700EAh
0x18005bee4  jnz     loc_18005BF84
0x18005beea  mov     rax, [rsp+2E0h+subKeyPath.Buffer]
0x18005beef  lea     pszSubKeyPath, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005bef6  movzx   edx, [rsp+2E0h+subKeyPath.Length]
0x18005befb  mov     desiredAccess, edi; hr
0x18005befe  mov     this, [rbp+1E8h]; callerReturnAddress
0x18005bf05  mov     [rsp+2E0h+var_2A0], ebx
0x18005bf09  mov     [rsp+2E0h+var_2A8], rax
0x18005bf0e  lea     rax, callerFunction; "StaticNtOpen"
0x18005bf15  mov     [rsp+2E0h+var_2B0], edx
0x18005bf19  mov     edx, 214h; lineNumber
0x18005bf1e  mov     [rsp+2E0h+var_2B8], rax
0x18005bf23  lea     rax, aHsFailedWithPa_0; "%hs failed with path: %.*ls queryHr: %x"
0x18005bf2a  mov     [rsp+2E0h+ResultLength], rax; formatString
0x18005bf2f  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005bf34  jmp     loc_18005BE1B
0x18005bf39  mov     rax, [rsp+2E0h+subKeyPath.Buffer]
0x18005bf3e  lea     pszSubKeyPath, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005bf45  movzx   edx, [rsp+2E0h+subKeyPath.Length]
0x18005bf4a  mov     desiredAccess, edi; hr
0x18005bf4d  mov     this, [rbp+1E8h]; callerReturnAddress
0x18005bf54  mov     [rsp+2E0h+var_2A8], rax
0x18005bf59  lea     rax, callerFunction; "StaticNtOpen"
0x18005bf60  mov     [rsp+2E0h+var_2B0], edx
0x18005bf64  mov     edx, 200h; lineNumber
0x18005bf69  mov     [rsp+2E0h+var_2B8], rax
0x18005bf6e  lea     rax, aHsFailedWithPa_1; "%hs failed with path: %.*ls"
0x18005bf75  mov     [rsp+2E0h+ResultLength], rax; formatString
0x18005bf7a  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005bf7f  jmp     loc_18005BE1B
0x18005bf84  cmp     ebx, 8007007Ah
0x18005bf8a  jz      loc_18005BEEA
0x18005bf90  mov     this, [rbp+1E8h]; callerReturnAddress
0x18005bf97  lea     pszSubKeyPath, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005bf9e  mov     desiredAccess, ebx; hr
0x18005bfa1  mov     edx, 7E1h; lineNumber
0x18005bfa6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005bfab  jmp     loc_18005BEEA
```
