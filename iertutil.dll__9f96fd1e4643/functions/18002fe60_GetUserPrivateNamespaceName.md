# GetUserPrivateNamespaceName

- ea: `0x18002fe60`
- end: `0x18003010c`
- name: `GetUserPrivateNamespaceName`
- size: `684`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002fcb0`
- `0x1800537e4`

## callees

- `0x180018410`
- `0x18001d0f0`
- `0x18002fe60`
- `0x180030114`
- `0x180031f00`
- `0x1800323f0`
- `0x18005d720`
- `0x18005e8e4`
- `0x180062624`
- `0x180083c10`
- `0x180085010`

## import_xrefs

- `msvcrt!wcsncat_s` at `0x18002feeb`
- `msvcrt!wcsncat_s` at `0x18002ff79`
- `msvcrt!wcsncat_s` at `0x18002ff95`
- `msvcrt!wcsncat_s` at `0x18002feeb`
- `msvcrt!wcsncat_s` at `0x18002ff79`
- `msvcrt!wcsncat_s` at `0x18002ff95`
- `msvcrt!wcscpy_s` at `0x18002febe`
- `msvcrt!wcscpy_s` at `0x18002febe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300e2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003008f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003008f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180030064`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180030064`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x180030034`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x180030034`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18003000b`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18003000b`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFullName` at `0x18002ffde`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFullName` at `0x18002ffde`

## pseudocode

```c
wchar_t *GetUserPrivateNamespaceName()
{
  LPWSTR v0; // rsi
  const unsigned __int16 *CurrentUserSidString; // rax
  __int64 v2; // rbx
  rsize_t v3; // rdi
  const wchar_t *v4; // rax
  const wchar_t *String; // rdi
  rsize_t v6; // r9
  __int64 v7; // rax
  unsigned int CurrentPackageFullName; // eax
  unsigned int v9; // r8d
  unsigned int v10; // eax
  unsigned int v11; // r8d
  int v12; // eax
  const char *v13; // r9
  struct IBrowsingEnvironment *CorrectBrowsingEnvironment; // rdi
  void (__fastcall *v15)(struct IBrowsingEnvironment *, wchar_t *, LPWSTR, __int64, _BYTE, void **); // rbx
  char Bool; // al
  __int64 v17; // r9
  unsigned int v19; // [rsp+20h] [rbp-E0h]
  UINT32 packageFullNameLength; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+44h] [rbp-BCh] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR packageFamilyName[64]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR packageFullName[128]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v0 = 0;
  StringSid = 0;
  if ( !Destination )
  {
    wcscpy_s(&Destination, 0x88u, L"IEUser_");
    CurrentUserSidString = GetCurrentUserSidString();
    v2 = -1;
    v3 = -1;
    do
      ++v3;
    while ( CurrentUserSidString[v3] );
    v4 = GetCurrentUserSidString();
    wcsncat_s(&Destination, 0x88u, v4, v3);
    if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2
      || (unsigned int)IEConfiguration_GetDWORD(268435501) == 7
      || (unsigned int)IEConfiguration_GetDWORD(268435501) == 4
      || (unsigned int)IEConfiguration_GetDWORD(268435501) == 8
      || !(unsigned int)IEConfiguration_GetDWORD(268435501)
      && (unsigned __int8)IEConfiguration_GetBool(536870915)
      && (unsigned __int8)IEConfiguration_GetBool(536870927) )
    {
      String = (const wchar_t *)IEConfiguration_GetString(268435499);
      wcsncat_s(&Destination, 0x88u, L"_", 1u);
      v6 = -1;
      do
        ++v6;
      while ( String[v6] );
      wcsncat_s(&Destination, 0x88u, String, v6);
      v7 = IEConfiguration_GetString(268435506);
      v0 = (LPWSTR)v7;
      if ( !v7 )
        goto LABEL_16;
      do
        ++v2;
      while ( *(_WORD *)(v7 + 2 * v2) );
      if ( !v2 )
      {
LABEL_16:
        packageFullNameLength = 127;
        packageFamilyNameLength = 64;
        Sid = 0;
        CurrentPackageFullName = GetCurrentPackageFullName(&packageFullNameLength, packageFullName);
        if ( CurrentPackageFullName )
          wil::details::in1diag3::_FailFast_Win32(retaddr, (void *)0x36, v9, (const char *)CurrentPackageFullName, v19);
        v10 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
        if ( v10 )
          wil::details::in1diag3::_FailFast_Win32(retaddr, (void *)0x38, v11, (const char *)v10, v19);
        v12 = DeriveAppContainerSidFromAppContainerName(packageFamilyName, &Sid);
        if ( v12 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x3A,
            (unsigned int)"onecoreuap\\inetcore\\iertutil\\privatenamespace.cpp",
            (const char *)(unsigned int)v12,
            v19);
        if ( !ConvertSidToStringSidW(Sid, &StringSid) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x3C,
            (unsigned int)"onecoreuap\\inetcore\\iertutil\\privatenamespace.cpp",
            v13);
        v0 = StringSid;
        FreeSid(Sid);
      }
    }
  }
  if ( !g_hUserPrivateNamespace )
  {
    CorrectBrowsingEnvironment = GetCorrectBrowsingEnvironment();
    v15 = *(void (__fastcall **)(struct IBrowsingEnvironment *, wchar_t *, LPWSTR, __int64, _BYTE, void **))(*(_QWORD *)CorrectBrowsingEnvironment + 96LL);
    Bool = IEConfiguration_GetBool(536870916);
    LOBYTE(v17) = 1;
    v15(CorrectBrowsingEnvironment, &Destination, v0, v17, Bool ^ 1, &g_hUserPrivateNamespace);
  }
  LocalFree(StringSid);
  return &Destination;
}

```

## disassembly

```asm
0x18002fe60  push    rbp
0x18002fe62  push    rbx
0x18002fe63  push    rsi
0x18002fe64  push    rdi
0x18002fe65  push    r12
0x18002fe67  push    r14
0x18002fe69  push    r15
0x18002fe6b  lea     rbp, [rsp-0F0h]
0x18002fe73  sub     rsp, 1F0h
0x18002fe7a  mov     rax, cs:__security_cookie
0x18002fe81  xor     rax, rsp
0x18002fe84  mov     [rbp+120h+var_40], rax
0x18002fe8b  xor     r14d, r14d
0x18002fe8e  lea     r15, Destination
0x18002fe95  cmp     cs:Destination, r14w
0x18002fe9d  mov     esi, r14d
0x18002fea0  mov     [rsp+220h+StringSid], r14
0x18002fea5  jnz     loc_180030095
0x18002feab  mov     r12d, 88h
0x18002feb1  lea     r8, aIeuser; "IEUser_"
0x18002feb8  mov     edx, r12d; SizeInWords
0x18002febb  mov     rcx, r15; Destination
0x18002febe  call    cs:__imp_wcscpy_s
0x18002fec4  call    ?GetCurrentUserSidString@@YAPEBGXZ; GetCurrentUserSidString(void)
0x18002fec9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002fecd  mov     rdi, rbx
0x18002fed0  inc     rdi
0x18002fed3  cmp     [rax+rdi*2], r14w
0x18002fed8  jnz     short loc_18002FED0
0x18002feda  call    ?GetCurrentUserSidString@@YAPEBGXZ; GetCurrentUserSidString(void)
0x18002fedf  mov     r9, rdi; MaxCount
0x18002fee2  mov     r8, rax; Source
0x18002fee5  mov     rdx, r12; SizeInWords
0x18002fee8  mov     rcx, r15; Destination
0x18002feeb  call    cs:__imp_wcsncat_s
0x18002fef1  mov     edi, 1000002Dh
0x18002fef6  mov     ecx, edi
0x18002fef8  call    ?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18002fefd  cmp     eax, 2
0x18002ff00  jz      short loc_18002FF59
0x18002ff02  mov     ecx, edi
0x18002ff04  call    ?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18002ff09  cmp     eax, 7
0x18002ff0c  jz      short loc_18002FF59
0x18002ff0e  mov     ecx, edi
0x18002ff10  call    ?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18002ff15  cmp     eax, 4
0x18002ff18  jz      short loc_18002FF59
0x18002ff1a  mov     ecx, edi
0x18002ff1c  call    ?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18002ff21  cmp     eax, 8
0x18002ff24  jz      short loc_18002FF59
0x18002ff26  mov     ecx, edi
0x18002ff28  call    ?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18002ff2d  test    eax, eax
0x18002ff2f  jnz     loc_180030095
0x18002ff35  mov     ecx, 20000003h
0x18002ff3a  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18002ff3f  test    al, al
0x18002ff41  jz      loc_180030095
0x18002ff47  mov     ecx, 2000000Fh
0x18002ff4c  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18002ff51  test    al, al
0x18002ff53  jz      loc_180030095
0x18002ff59  mov     ecx, 1000002Bh
0x18002ff5e  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18002ff63  mov     r9d, 1; MaxCount
0x18002ff69  lea     r8, asc_180181E88; "_"
0x18002ff70  mov     rdx, r12; SizeInWords
0x18002ff73  mov     rcx, r15; Destination
0x18002ff76  mov     rdi, rax
0x18002ff79  call    cs:__imp_wcsncat_s
0x18002ff7f  mov     r9, rbx
0x18002ff82  inc     r9; MaxCount
0x18002ff85  cmp     [rdi+r9*2], r14w
0x18002ff8a  jnz     short loc_18002FF82
0x18002ff8c  mov     r8, rdi; Source
0x18002ff8f  mov     rdx, r12; SizeInWords
0x18002ff92  mov     rcx, r15; Destination
0x18002ff95  call    cs:__imp_wcsncat_s
0x18002ff9b  mov     ecx, 10000032h
0x18002ffa0  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18002ffa5  mov     rsi, rax
0x18002ffa8  test    rax, rax
0x18002ffab  jz      short loc_18002FFC0
0x18002ffad  inc     rbx
0x18002ffb0  cmp     [rax+rbx*2], r14w
0x18002ffb5  jnz     short loc_18002FFAD
0x18002ffb7  test    rbx, rbx
0x18002ffba  jnz     loc_180030095
0x18002ffc0  lea     rdx, [rbp+120h+packageFullName]; packageFullName
0x18002ffc4  mov     [rsp+220h+packageFullNameLength], 7Fh
0x18002ffcc  lea     rcx, [rsp+220h+packageFullNameLength]; packageFullNameLength
0x18002ffd1  mov     [rsp+220h+packageFamilyNameLength], 40h ; '@'
0x18002ffd9  mov     [rsp+220h+Sid], r14
0x18002ffde  call    cs:__imp_GetCurrentPackageFullName
0x18002ffe4  test    eax, eax
0x18002ffe6  jz      short loc_18002FFFD
0x18002ffe8  mov     rcx, [rbp+128h]; this
0x18002ffef  mov     r9d, eax; char *
0x18002fff2  mov     edx, 36h ; '6'; void *
0x18002fff7  call    ?_FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_FailFast_Win32(void *,uint,char const *,ulong)
0x18002fffd  lea     r8, [rsp+220h+packageFamilyName]; packageFamilyName
0x180030002  lea     rdx, [rsp+220h+packageFamilyNameLength]; packageFamilyNameLength
0x180030007  lea     rcx, [rbp+120h+packageFullName]; packageFullName
0x18003000b  call    cs:__imp_PackageFamilyNameFromFullName
0x180030011  test    eax, eax
0x180030013  jz      short loc_18003002A
0x180030015  mov     rcx, [rbp+128h]; this
0x18003001c  mov     r9d, eax; char *
0x18003001f  mov     edx, 38h ; '8'; void *
0x180030024  call    ?_FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_FailFast_Win32(void *,uint,char const *,ulong)
0x18003002a  lea     rdx, [rsp+220h+Sid]
0x18003002f  lea     rcx, [rsp+220h+packageFamilyName]
0x180030034  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x18003003a  test    eax, eax
0x18003003c  jns     short loc_18003005A
0x18003003e  mov     rcx, [rbp+128h]; this
0x180030045  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\iertutil\\private"...
0x18003004c  mov     r9d, eax; char *
0x18003004f  mov     edx, 3Ah ; ':'; void *
0x180030054  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18003005a  mov     rcx, [rsp+220h+Sid]; Sid
0x18003005f  lea     rdx, [rsp+220h+StringSid]; StringSid
0x180030064  call    cs:__imp_ConvertSidToStringSidW
0x18003006a  test    eax, eax
0x18003006c  jnz     short loc_180030085
0x18003006e  mov     rcx, [rbp+128h]; this
0x180030075  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\iertutil\\private"...
0x18003007c  lea     edx, [rax+3Ch]; void *
0x18003007f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180030085  mov     rcx, [rsp+220h+Sid]; pSid
0x18003008a  mov     rsi, [rsp+220h+StringSid]
0x18003008f  call    cs:__imp_FreeSid
0x180030095  cmp     cs:?g_hUserPrivateNamespace@@3PEAXEA, r14; void * g_hUserPrivateNamespace
0x18003009c  jnz     short loc_1800300DD
0x18003009e  call    ?GetCorrectBrowsingEnvironment@@YAPEAUIBrowsingEnvironment@@XZ; GetCorrectBrowsingEnvironment(void)
0x1800300a3  mov     rdi, rax
0x1800300a6  mov     rcx, [rax]
0x1800300a9  mov     rbx, [rcx+60h]
0x1800300ad  mov     ecx, 20000004h
0x1800300b2  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800300b7  xor     al, 1
0x1800300b9  lea     rcx, ?g_hUserPrivateNamespace@@3PEAXEA; void * g_hUserPrivateNamespace
0x1800300c0  mov     [rsp+220h+var_1F8], rcx
0x1800300c5  mov     r9b, 1
0x1800300c8  mov     [rsp+220h+var_200], al
0x1800300cc  mov     r8, rsi
0x1800300cf  mov     rax, rbx
0x1800300d2  mov     rdx, r15
0x1800300d5  mov     rcx, rdi
0x1800300d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300dd  mov     rcx, [rsp+220h+StringSid]; hMem
0x1800300e2  call    cs:__imp_LocalFree
0x1800300e8  mov     rax, r15
0x1800300eb  mov     rcx, [rbp+120h+var_40]
0x1800300f2  xor     rcx, rsp; StackCookie
0x1800300f5  call    __security_check_cookie
0x1800300fa  add     rsp, 1F0h
0x180030101  pop     r15
0x180030103  pop     r14
0x180030105  pop     r12
0x180030107  pop     rdi
0x180030108  pop     rsi
0x180030109  pop     rbx
0x18003010a  pop     rbp
0x18003010b  retn
```
