# Intl_SaveUISettingsToNtUserFile(HKEY__ *)

- ea: `0x180026304`
- end: `0x1800265b3`
- name: `?Intl_SaveUISettingsToNtUserFile@@YAXPEAUHKEY__@@@Z`
- size: `687`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000dce0`
- `0x180017cf0`
- `0x180022180`

## callees

- `0x18000f4d4`
- `0x18001319c`
- `0x180016e00`
- `0x180023524`
- `0x18002578c`
- `0x1800258c8`
- `0x180025d38`
- `0x180026304`
- `0x180026df0`
- `0x180028118`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002647b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026559`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002647b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026559`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800264d8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800264d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026564`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002656d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026564`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002656d`

## string_xrefs

- `0x1800264ce`: `LanguageConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Intl_SaveUISettingsToNtUserFile(HKEY hKey)
{
  __int64 v2; // rbx
  const unsigned __int16 *v3; // rcx
  HKEY NtUserHive; // rsi
  signed int v5; // ebx
  __int64 v6; // rcx
  WCHAR *v7; // rax
  unsigned __int16 *v8; // rax
  __int64 v9; // rdx
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // rdi
  __int64 v12; // rax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  int v15; // r9d
  unsigned __int64 cbData; // rdx
  const unsigned __int16 *v17; // rcx
  int lpData; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v19[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v22[42]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Data[352]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v24[352]; // [rsp+470h] [rbp+370h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+778h] [rbp+678h]

  hKeya = 0;
  v19[0] = 0;
  v2 = 700;
  memset_0(Data, 0, 0x2BCu);
  memset_0(v24, 0, 0x2BCu);
  dwDisposition = 0;
  wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v22,
    "Intl_SaveUISettingsToNtUserFile");
  v22[0] = &IntlCplTraceLoggingTelemetry::Intl_SaveUISettingsToNtUserFile::`vftable';
  IntlCplTraceLoggingTelemetry::Intl_SaveUISettingsToNtUserFile::StartActivity((IntlCplTraceLoggingTelemetry::Intl_SaveUISettingsToNtUserFile *)v22);
  NtUserHive = Intl_LoadNtUserHive(v3, L"Control Panel\\Desktop", v19);
  if ( NtUserHive )
  {
    v6 = 700;
    v7 = Data;
    do
    {
      *(_BYTE *)v7 = 0;
      v7 = (WCHAR *)((char *)v7 + 1);
      --v6;
    }
    while ( v6 );
    v8 = v24;
    do
    {
      *(_BYTE *)v8 = 0;
      v8 = (unsigned __int16 *)((char *)v8 + 1);
      --v2;
    }
    while ( v2 );
    if ( (unsigned int)Intl_GetUserUILanguage(hKey, Data, 350) )
    {
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( Data[v12] );
      v13 = RegSetValueExW(NtUserHive, L"PreferredUILanguages", 0, 7u, (const BYTE *)Data, 2 * v12 + 2);
      v5 = v13;
      if ( v13 > 0 )
        v5 = (unsigned __int16)v13 | 0x80070000;
      v10 = retaddr;
      if ( v5 >= 0 )
      {
        v14 = RegCreateKeyExW(NtUserHive, L"LanguageConfiguration", 0, 0, 0, 0x20006u, 0, &hKeya, &dwDisposition);
        v5 = v14;
        if ( v14 > 0 )
          v5 = (unsigned __int16)v14 | 0x80070000;
        v10 = retaddr;
        if ( v5 >= 0 )
        {
          cbData = Intl_GetUserUILangConfig(hKey, Data, v24, v15);
          do
            ++v11;
          while ( v24[v11] );
          if ( cbData > 2 * v11 )
            RegSetValueExW(hKeya, Data, 0, 7u, (const BYTE *)v24, cbData);
          RegCloseKey(hKeya);
          goto LABEL_25;
        }
        v9 = 3262;
      }
      else
      {
        v9 = 3245;
      }
    }
    else
    {
      v5 = -2147467259;
      v9 = 3226;
      v10 = retaddr;
    }
    wil::details::in1diag3::_Log_Hr(
      v10,
      (void *)v9,
      (unsigned int)"shell\\osshell\\cpls\\intl\\util.cpp",
      (const char *)(unsigned int)v5,
      lpData);
LABEL_25:
    RegCloseKey(NtUserHive);
    Intl_UnloadNtUserHive(v17, v19);
    goto LABEL_26;
  }
  v5 = -2147467259;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xC8D,
    (unsigned int)"shell\\osshell\\cpls\\intl\\util.cpp",
    (const char *)0x80004005LL,
    lpData);
LABEL_26:
  wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v22,
    (unsigned int)v5);
  IntlCplTraceLoggingTelemetry::Intl_SaveUISettingsToNtUserFile::~Intl_SaveUISettingsToNtUserFile((IntlCplTraceLoggingTelemetry::Intl_SaveUISettingsToNtUserFile *)v22);
}

```

## disassembly

```asm
0x180026304  push    rbp
0x180026306  push    rbx
0x180026307  push    rsi
0x180026308  push    rdi
0x180026309  push    r14
0x18002630b  push    r15
0x18002630d  lea     rbp, [rsp-648h]
0x180026315  sub     rsp, 748h
0x18002631c  mov     rax, cs:__security_cookie
0x180026323  xor     rax, rsp
0x180026326  mov     [rbp+670h+var_40], rax
0x18002632d  mov     r14, rcx
0x180026330  xor     r15d, r15d
0x180026333  mov     [rsp+770h+hKey], r15
0x180026338  mov     [rsp+770h+var_720], r15b
0x18002633d  mov     ebx, 2BCh
0x180026342  mov     r8d, ebx; Size
0x180026345  xor     edx, edx; Val
0x180026347  lea     rcx, [rbp+670h+Data]; void *
0x18002634e  call    memset_0
0x180026353  mov     r8d, ebx; Size
0x180026356  xor     edx, edx; Val
0x180026358  lea     rcx, [rbp+670h+var_300]; void *
0x18002635f  call    memset_0
0x180026364  mov     [rsp+770h+dwDisposition], r15d
0x180026369  lea     rdx, aIntlSaveuisett; "Intl_SaveUISettingsToNtUserFile"
0x180026370  lea     rcx, [rsp+770h+var_710]
0x180026375  call    ??0?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002637a  lea     rax, ??_7Intl_SaveUISettingsToNtUserFile@IntlCplTraceLoggingTelemetry@@6B@; const IntlCplTraceLoggingTelemetry::Intl_SaveUISettingsToNtUserFile::`vftable'
0x180026381  mov     [rsp+770h+var_710], rax
0x180026386  lea     rcx, [rsp+770h+var_710]; this
0x18002638b  call    ?StartActivity@Intl_SaveUISettingsToNtUserFile@IntlCplTraceLoggingTelemetry@@QEAAXXZ; IntlCplTraceLoggingTelemetry::Intl_SaveUISettingsToNtUserFile::StartActivity(void)
0x180026390  nop
0x180026391  lea     r8, [rsp+770h+var_720]; unsigned __int8 *
0x180026396  lea     rdx, ?c_szCPanelDesktop@@3QBGB; "Control Panel\\Desktop"
0x18002639d  call    ?Intl_LoadNtUserHive@@YAPEAUHKEY__@@PEBG0PEAE@Z; Intl_LoadNtUserHive(ushort const *,ushort const *,uchar *)
0x1800263a2  mov     rsi, rax
0x1800263a5  mov     rcx, [rbp+678h]; this
0x1800263ac  test    rax, rax
0x1800263af  jnz     short loc_1800263CF
0x1800263b1  mov     ebx, 80004005h
0x1800263b6  mov     r9d, ebx; char *
0x1800263b9  lea     r8, aShellOsshellCp_1; "shell\\osshell\\cpls\\intl\\util.cpp"
0x1800263c0  mov     edx, 0C8Dh; void *
0x1800263c5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800263ca  jmp     loc_18002657D
0x1800263cf  mov     rcx, rbx
0x1800263d2  lea     rax, [rbp+670h+Data]
0x1800263d9  mov     [rax], r15b
0x1800263dc  inc     rax
0x1800263df  sub     rcx, 1
0x1800263e3  jnz     short loc_1800263D9
0x1800263e5  lea     rax, [rbp+670h+var_300]
0x1800263ec  mov     [rax], r15b
0x1800263ef  inc     rax
0x1800263f2  sub     rbx, 1
0x1800263f6  jnz     short loc_1800263EC
0x1800263f8  mov     rdi, [rbp+678h]
0x1800263ff  mov     r8d, 15Eh; int
0x180026405  lea     rdx, [rbp+670h+Data]; unsigned __int16 *
0x18002640c  mov     rcx, r14; hKey
0x18002640f  call    ?Intl_GetUserUILanguage@@YAHPEAUHKEY__@@PEAGH@Z; Intl_GetUserUILanguage(HKEY__ *,ushort *,int)
0x180026414  test    eax, eax
0x180026416  jnz     short loc_180026439
0x180026418  mov     ebx, 80004005h
0x18002641d  mov     edx, 0C9Ah; void *
0x180026422  mov     rcx, rdi; this
0x180026425  mov     r9d, ebx; char *
0x180026428  lea     r8, aShellOsshellCp_1; "shell\\osshell\\cpls\\intl\\util.cpp"
0x18002642f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026434  jmp     loc_18002656A
0x180026439  lea     rcx, [rbp+670h+Data]
0x180026440  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180026444  mov     rax, rdi
0x180026447  inc     rax
0x18002644a  cmp     [rcx+rax*2], r15w
0x18002644f  jnz     short loc_180026447
0x180026451  lea     eax, ds:2[rax*2]
0x180026458  mov     [rsp+770h+cbData], eax; cbData
0x18002645c  lea     rax, [rbp+670h+Data]
0x180026463  mov     [rsp+770h+lpData], rax; lpData
0x180026468  mov     r9d, 7; dwType
0x18002646e  xor     r8d, r8d; Reserved
0x180026471  lea     rdx, ?c_szUIPreferredLang@@3QBGB; "PreferredUILanguages"
0x180026478  mov     rcx, rsi; hKey
0x18002647b  call    cs:__imp_RegSetValueExW
0x180026481  mov     ebx, eax
0x180026483  test    eax, eax
0x180026485  jle     short loc_180026490
0x180026487  movzx   ebx, ax
0x18002648a  or      ebx, 80070000h
0x180026490  mov     rcx, [rbp+678h]
0x180026497  test    ebx, ebx
0x180026499  jns     short loc_1800264A2
0x18002649b  mov     edx, 0CADh
0x1800264a0  jmp     short loc_180026425
0x1800264a2  lea     rax, [rsp+770h+dwDisposition]
0x1800264a7  mov     [rsp+770h+lpdwDisposition], rax; lpdwDisposition
0x1800264ac  lea     rax, [rsp+770h+hKey]
0x1800264b1  mov     [rsp+770h+phkResult], rax; phkResult
0x1800264b6  mov     [rsp+770h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800264bb  mov     [rsp+770h+cbData], 20006h; samDesired
0x1800264c3  mov     dword ptr [rsp+770h+lpData], r15d; dwOptions
0x1800264c8  xor     r9d, r9d; lpClass
0x1800264cb  xor     r8d, r8d; Reserved
0x1800264ce  lea     rdx, ?c_szUILanguageConfigSubkey@@3QBGB; "LanguageConfiguration"
0x1800264d5  mov     rcx, rsi; hKey
0x1800264d8  call    cs:__imp_RegCreateKeyExW
0x1800264de  mov     ebx, eax
0x1800264e0  test    eax, eax
0x1800264e2  jle     short loc_1800264ED
0x1800264e4  movzx   ebx, ax
0x1800264e7  or      ebx, 80070000h
0x1800264ed  mov     rcx, [rbp+678h]
0x1800264f4  test    ebx, ebx
0x1800264f6  jns     short loc_180026502
0x1800264f8  mov     edx, 0CBEh
0x1800264fd  jmp     loc_180026425
0x180026502  lea     r8, [rbp+670h+var_300]; Destination
0x180026509  lea     rdx, [rbp+670h+Data]; lpValueName
0x180026510  mov     rcx, r14; hKey
0x180026513  call    ?Intl_GetUserUILangConfig@@YAKPEAUHKEY__@@PEAG1H@Z; Intl_GetUserUILangConfig(HKEY__ *,ushort *,ushort *,int)
0x180026518  mov     edx, eax
0x18002651a  lea     rax, [rbp+670h+var_300]
0x180026521  inc     rdi
0x180026524  cmp     [rax+rdi*2], r15w
0x180026529  jnz     short loc_180026521
0x18002652b  lea     rcx, [rdi+rdi]
0x18002652f  cmp     rdx, rcx
0x180026532  jbe     short loc_18002655F
0x180026534  mov     [rsp+770h+cbData], edx; cbData
0x180026538  lea     rax, [rbp+670h+var_300]
0x18002653f  mov     [rsp+770h+lpData], rax; lpData
0x180026544  mov     r9d, 7; dwType
0x18002654a  xor     r8d, r8d; Reserved
0x18002654d  lea     rdx, [rbp+670h+Data]; lpValueName
0x180026554  mov     rcx, [rsp+770h+hKey]; hKey
0x180026559  call    cs:__imp_RegSetValueExW
0x18002655f  mov     rcx, [rsp+770h+hKey]; hKey
0x180026564  call    cs:__imp_RegCloseKey
0x18002656a  mov     rcx, rsi; hKey
0x18002656d  call    cs:__imp_RegCloseKey
0x180026573  lea     rdx, [rsp+770h+var_720]; unsigned __int8 *
0x180026578  call    ?Intl_UnloadNtUserHive@@YAXPEBGPEAE@Z; Intl_UnloadNtUserHive(ushort const *,uchar *)
0x18002657d  mov     edx, ebx
0x18002657f  lea     rcx, [rsp+770h+var_710]
0x180026584  call    ?Stop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180026589  nop
0x18002658a  lea     rcx, [rsp+770h+var_710]; this
0x18002658f  call    ??1Intl_SaveUISettingsToNtUserFile@IntlCplTraceLoggingTelemetry@@QEAA@XZ; IntlCplTraceLoggingTelemetry::Intl_SaveUISettingsToNtUserFile::~Intl_SaveUISettingsToNtUserFile(void)
0x180026594  mov     rcx, [rbp+670h+var_40]
0x18002659b  xor     rcx, rsp; StackCookie
0x18002659e  call    __security_check_cookie
0x1800265a3  add     rsp, 748h
0x1800265aa  pop     r15
0x1800265ac  pop     r14
0x1800265ae  pop     rdi
0x1800265af  pop     rsi
0x1800265b0  pop     rbx
0x1800265b1  pop     rbp
0x1800265b2  retn
```
