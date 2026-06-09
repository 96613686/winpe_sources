# Intl_SetUILanguageForSystemAccts(HKEY__ *,ulong *)

- ea: `0x180026994`
- end: `0x180026c2d`
- name: `?Intl_SetUILanguageForSystemAccts@@YAXPEAUHKEY__@@PEAK@Z`
- size: `665`
- prototype: `void __fastcall(HKEY hKey, unsigned int *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dce0`
- `0x180017cf0`
- `0x180022180`

## callees

- `0x180003546`
- `0x18000f4d4`
- `0x18001319c`
- `0x180016e00`
- `0x180023550`
- `0x18002578c`
- `0x1800258c8`
- `0x180026994`
- `0x180026ce0`
- `0x1800281d8`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180026a80`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180026a80`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026bd9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026bd9`
- `KERNEL32!NotifyUILanguageChange` at `0x180026bb5`
- `KERNEL32!NotifyUILanguageChange` at `0x180026bb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Intl_SetUILanguageForSystemAccts(HKEY hKey, unsigned int *a2)
{
  __int64 v4; // rcx
  WCHAR *v5; // rax
  __int64 v6; // rcx
  WCHAR *v7; // rax
  const WCHAR *v8; // rdi
  wil::details::in1diag3 *v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  unsigned __int16 *v13; // rax
  __int64 v14; // rax
  int pdwStatusRtrn; // [rsp+20h] [rbp-E0h]
  DWORD v16; // [rsp+30h] [rbp-D0h] BYREF
  ULONG pcchLanguagesBuffer; // [rsp+34h] [rbp-CCh] BYREF
  ULONG pulNumLanguages; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v19[42]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pcwstrNewLanguage[352]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR pwszLanguagesBuffer[352]; // [rsp+450h] [rbp+350h] BYREF
  unsigned __int16 Src[352]; // [rsp+710h] [rbp+610h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A08h] [rbp+908h]

  memset_0(pcwstrNewLanguage, 0, 0x2BCu);
  memset_0(Src, 0, 0x2BCu);
  memset_0(pwszLanguagesBuffer, 0, 0x2BCu);
  pulNumLanguages = 1;
  wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v19,
    "Intl_SetUILanguageForSystemAccts");
  v19[0] = &IntlCplTraceLoggingTelemetry::Intl_SetUILanguageForSystemAccts::`vftable';
  IntlCplTraceLoggingTelemetry::Intl_SetUILanguageForSystemAccts::StartActivity((IntlCplTraceLoggingTelemetry::Intl_SetUILanguageForSystemAccts *)v19);
  v4 = 700;
  v5 = pcwstrNewLanguage;
  do
  {
    *(_BYTE *)v5 = 0;
    v5 = (WCHAR *)((char *)v5 + 1);
    --v4;
  }
  while ( v4 );
  v6 = 700;
  v7 = pwszLanguagesBuffer;
  do
  {
    *(_BYTE *)v7 = 0;
    v7 = (WCHAR *)((char *)v7 + 1);
    --v6;
  }
  while ( v6 );
  pcchLanguagesBuffer = 350;
  v8 = (const WCHAR *)((unsigned __int64)pwszLanguagesBuffer
                     & -(__int64)GetSystemPreferredUILanguages(
                                   0x408u,
                                   &pulNumLanguages,
                                   pwszLanguagesBuffer,
                                   &pcchLanguagesBuffer));
  v9 = retaddr;
  if ( !(unsigned int)Intl_GetUserUILanguage(hKey, pcwstrNewLanguage, 350) )
  {
    v10 = 3371;
LABEL_7:
    wil::details::in1diag3::_Log_Hr(
      v9,
      (void *)v10,
      (unsigned int)"shell\\osshell\\cpls\\intl\\util.cpp",
      (const char *)0x80004005LL,
      pdwStatusRtrn);
    v11 = 2147500037LL;
    goto LABEL_22;
  }
  v9 = retaddr;
  if ( (int)Intl_SetUserPreferredMUILanguage(pcwstrNewLanguage, 1, 1) < 0 )
  {
    v10 = 3378;
    goto LABEL_7;
  }
  v12 = 700;
  v13 = Src;
  do
  {
    *(_BYTE *)v13 = 0;
    v13 = (unsigned __int16 *)((char *)v13 + 1);
    --v12;
  }
  while ( v12 );
  if ( (unsigned int)Intl_GetUserUILangConfig(hKey, pcwstrNewLanguage, Src) )
  {
    v14 = -1;
    do
      ++v14;
    while ( pcwstrNewLanguage[v14] );
    memcpy_0(&pcwstrNewLanguage[(unsigned int)(v14 + 1)], Src, 700 - 2LL * (unsigned int)(v14 + 1));
    v9 = retaddr;
    if ( (int)Intl_SetUserPreferredMUILanguage(pcwstrNewLanguage, 0, 1) < 0 )
    {
      v10 = 3400;
      goto LABEL_7;
    }
  }
  v16 = 0;
  if ( NotifyUILanguageChange(1u, pcwstrNewLanguage, v8, 0, &v16)
    && a2
    && CompareStringOrdinal(pcwstrNewLanguage, -1, v8, -1, 0) != 2 )
  {
    *a2 = v16;
  }
  v11 = 0;
LABEL_22:
  wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v19, v11);
  IntlCplTraceLoggingTelemetry::Intl_SetUILanguageForSystemAccts::~Intl_SetUILanguageForSystemAccts((IntlCplTraceLoggingTelemetry::Intl_SetUILanguageForSystemAccts *)v19);
}

```

## disassembly

```asm
0x180026994  mov     [rsp-8+arg_10], rbx
0x180026999  mov     [rsp-8+arg_18], rsi
0x18002699e  push    rbp
0x18002699f  push    rdi
0x1800269a0  push    r13
0x1800269a2  push    r14
0x1800269a4  push    r15
0x1800269a6  lea     rbp, [rsp-8E0h]
0x1800269ae  sub     rsp, 9E0h
0x1800269b5  mov     rax, cs:__security_cookie
0x1800269bc  xor     rax, rsp
0x1800269bf  mov     [rbp+900h+var_30], rax
0x1800269c6  mov     r14, rdx
0x1800269c9  mov     r15, rcx
0x1800269cc  mov     ebx, 2BCh
0x1800269d1  mov     r8d, ebx; Size
0x1800269d4  xor     edx, edx; Val
0x1800269d6  lea     rcx, [rbp+900h+pcwstrNewLanguage]; void *
0x1800269dd  call    memset_0
0x1800269e2  mov     r8d, ebx; Size
0x1800269e5  xor     edx, edx; Val
0x1800269e7  lea     rcx, [rbp+900h+Src]; void *
0x1800269ee  call    memset_0
0x1800269f3  mov     r8d, ebx; Size
0x1800269f6  xor     edx, edx; Val
0x1800269f8  lea     rcx, [rbp+900h+pwszLanguagesBuffer]; void *
0x1800269ff  call    memset_0
0x180026a04  mov     [rsp+0A00h+pulNumLanguages], 1
0x180026a0c  lea     rdx, aIntlSetuilangu; "Intl_SetUILanguageForSystemAccts"
0x180026a13  lea     rcx, [rsp+0A00h+var_9C0]
0x180026a18  call    ??0?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180026a1d  lea     rax, ??_7Intl_SetUILanguageForSystemAccts@IntlCplTraceLoggingTelemetry@@6B@; const IntlCplTraceLoggingTelemetry::Intl_SetUILanguageForSystemAccts::`vftable'
0x180026a24  mov     [rsp+0A00h+var_9C0], rax
0x180026a29  lea     rcx, [rsp+0A00h+var_9C0]; this
0x180026a2e  call    ?StartActivity@Intl_SetUILanguageForSystemAccts@IntlCplTraceLoggingTelemetry@@QEAAXXZ; IntlCplTraceLoggingTelemetry::Intl_SetUILanguageForSystemAccts::StartActivity(void)
0x180026a33  nop
0x180026a34  mov     ecx, ebx
0x180026a36  lea     rax, [rbp+900h+pcwstrNewLanguage]
0x180026a3d  xor     r13d, r13d
0x180026a40  mov     [rax], r13b
0x180026a43  inc     rax
0x180026a46  sub     rcx, 1
0x180026a4a  jnz     short loc_180026A40
0x180026a4c  mov     rcx, rbx
0x180026a4f  lea     rax, [rbp+900h+pwszLanguagesBuffer]
0x180026a56  mov     [rax], r13b
0x180026a59  inc     rax
0x180026a5c  sub     rcx, 1
0x180026a60  jnz     short loc_180026A56
0x180026a62  mov     [rsp+0A00h+pcchLanguagesBuffer], 15Eh
0x180026a6a  lea     r9, [rsp+0A00h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180026a6f  lea     r8, [rbp+900h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x180026a76  lea     rdx, [rsp+0A00h+pulNumLanguages]; pulNumLanguages
0x180026a7b  mov     ecx, 408h; dwFlags
0x180026a80  call    cs:__imp_GetSystemPreferredUILanguages
0x180026a86  neg     eax
0x180026a88  sbb     rdi, rdi
0x180026a8b  lea     rax, [rbp+900h+pwszLanguagesBuffer]
0x180026a92  and     rdi, rax
0x180026a95  mov     rsi, [rbp+908h]
0x180026a9c  mov     r8d, 15Eh; int
0x180026aa2  lea     rdx, [rbp+900h+pcwstrNewLanguage]; unsigned __int16 *
0x180026aa9  mov     rcx, r15; hKey
0x180026aac  call    ?Intl_GetUserUILanguage@@YAHPEAUHKEY__@@PEAGH@Z; Intl_GetUserUILanguage(HKEY__ *,ushort *,int)
0x180026ab1  test    eax, eax
0x180026ab3  jnz     short loc_180026AD8
0x180026ab5  mov     edx, 0D2Bh; void *
0x180026aba  mov     ebx, 80004005h
0x180026abf  mov     r9d, ebx; char *
0x180026ac2  lea     r8, aShellOsshellCp_1; "shell\\osshell\\cpls\\intl\\util.cpp"
0x180026ac9  mov     rcx, rsi; this
0x180026acc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026ad1  mov     edx, ebx
0x180026ad3  jmp     loc_180026BED
0x180026ad8  mov     rsi, [rbp+908h]
0x180026adf  mov     edx, 1; int
0x180026ae4  mov     r8d, edx; int
0x180026ae7  lea     rcx, [rbp+900h+pcwstrNewLanguage]; unsigned __int16 *
0x180026aee  call    ?Intl_SetUserPreferredMUILanguage@@YAJPEAGHH@Z; Intl_SetUserPreferredMUILanguage(ushort *,int,int)
0x180026af3  shr     eax, 1Fh
0x180026af6  test    al, al
0x180026af8  jz      short loc_180026B01
0x180026afa  mov     edx, 0D32h
0x180026aff  jmp     short loc_180026ABA
0x180026b01  mov     rdx, rbx
0x180026b04  lea     rax, [rbp+900h+Src]
0x180026b0b  mov     [rax], r13b
0x180026b0e  inc     rax
0x180026b11  sub     rdx, 1
0x180026b15  jnz     short loc_180026B0B
0x180026b17  lea     r8, [rbp+900h+Src]; Destination
0x180026b1e  lea     rdx, [rbp+900h+pcwstrNewLanguage]; lpValueName
0x180026b25  mov     rcx, r15; hKey
0x180026b28  call    ?Intl_GetUserUILangConfig@@YAKPEAUHKEY__@@PEAG1H@Z; Intl_GetUserUILangConfig(HKEY__ *,ushort *,ushort *,int)
0x180026b2d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180026b31  test    eax, eax
0x180026b33  jz      short loc_180026B95
0x180026b35  lea     rcx, [rbp+900h+pcwstrNewLanguage]
0x180026b3c  mov     rax, r15
0x180026b3f  inc     rax
0x180026b42  cmp     [rcx+rax*2], r13w
0x180026b47  jnz     short loc_180026B3F
0x180026b49  lea     ecx, [rax+1]
0x180026b4c  add     rcx, rcx
0x180026b4f  sub     rbx, rcx
0x180026b52  lea     rax, [rbp+900h+pcwstrNewLanguage]
0x180026b59  add     rcx, rax; void *
0x180026b5c  mov     r8, rbx; Size
0x180026b5f  lea     rdx, [rbp+900h+Src]; Src
0x180026b66  call    memcpy_0
0x180026b6b  mov     rsi, [rbp+908h]
0x180026b72  xor     edx, edx; int
0x180026b74  lea     r8d, [rdx+1]; int
0x180026b78  lea     rcx, [rbp+900h+pcwstrNewLanguage]; unsigned __int16 *
0x180026b7f  call    ?Intl_SetUserPreferredMUILanguage@@YAJPEAGHH@Z; Intl_SetUserPreferredMUILanguage(ushort *,int,int)
0x180026b84  shr     eax, 1Fh
0x180026b87  test    al, al
0x180026b89  jz      short loc_180026B95
0x180026b8b  mov     edx, 0D48h
0x180026b90  jmp     loc_180026ABA
0x180026b95  mov     [rsp+0A00h+var_9D0], r13d
0x180026b9a  lea     rax, [rsp+0A00h+var_9D0]
0x180026b9f  mov     qword ptr [rsp+0A00h+pdwStatusRtrn], rax; pdwStatusRtrn
0x180026ba4  xor     r9d, r9d; dwReserved
0x180026ba7  mov     r8, rdi; pcwstrPreviousLanguage
0x180026baa  lea     rdx, [rbp+900h+pcwstrNewLanguage]; pcwstrNewLanguage
0x180026bb1  lea     ecx, [r9+1]; dwFlags
0x180026bb5  call    cs:__imp_NotifyUILanguageChange
0x180026bbb  test    eax, eax
0x180026bbd  jz      short loc_180026BEB
0x180026bbf  test    r14, r14
0x180026bc2  jz      short loc_180026BEB
0x180026bc4  mov     [rsp+0A00h+pdwStatusRtrn], r13d; bIgnoreCase
0x180026bc9  mov     r9d, r15d; cchCount2
0x180026bcc  mov     r8, rdi; lpString2
0x180026bcf  mov     edx, r15d; cchCount1
0x180026bd2  lea     rcx, [rbp+900h+pcwstrNewLanguage]; lpString1
0x180026bd9  call    cs:__imp_CompareStringOrdinal
0x180026bdf  cmp     eax, 2
0x180026be2  jz      short loc_180026BEB
0x180026be4  mov     eax, [rsp+0A00h+var_9D0]
0x180026be8  mov     [r14], eax
0x180026beb  xor     edx, edx
0x180026bed  lea     rcx, [rsp+0A00h+var_9C0]
0x180026bf2  call    ?Stop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180026bf7  nop
0x180026bf8  lea     rcx, [rsp+0A00h+var_9C0]; this
0x180026bfd  call    ??1Intl_SetUILanguageForSystemAccts@IntlCplTraceLoggingTelemetry@@QEAA@XZ; IntlCplTraceLoggingTelemetry::Intl_SetUILanguageForSystemAccts::~Intl_SetUILanguageForSystemAccts(void)
0x180026c02  mov     rcx, [rbp+900h+var_30]
0x180026c09  xor     rcx, rsp; StackCookie
0x180026c0c  call    __security_check_cookie
0x180026c11  lea     r11, [rsp+0A00h+var_20]
0x180026c19  mov     rbx, [r11+40h]
0x180026c1d  mov     rsi, [r11+48h]
0x180026c21  mov     rsp, r11
0x180026c24  pop     r15
0x180026c26  pop     r14
0x180026c28  pop     r13
0x180026c2a  pop     rdi
0x180026c2b  pop     rbp
0x180026c2c  retn
```
