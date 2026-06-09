# Mso::OfficeWebServiceApi::ConfigService::GetConfigTokenInternal(MsoReserveTag,Mso::OfficeWebServiceApi::ConfigServiceTelemetryApi,Mso::OfficeWebServiceApi::ConfigToken::Token,Mso::OfficeWebServiceApi::FederationProviderConfiguration const &,wchar_t *,uint)

- ea: `0x180077894`
- end: `0x180077c37`
- name: `?GetConfigTokenInternal@ConfigService@OfficeWebServiceApi@Mso@@SA?AW4Flags@Status@23@VMsoReserveTag@@W4ConfigServiceTelemetryApi@23@W4Token@ConfigToken@23@AEBVFederationProviderConfiguration@23@PEA_WI@Z`
- size: `931`
- prototype: ``
- caller_count: `7`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180077500`
- `0x1800775dc`
- `0x180077734`
- `0x1800777d8`
- `0x180078d38`
- `0x180078f48`
- `0x180079174`

## callees

- `0x180003980`
- `0x18000adf0`
- `0x18000c2dc`
- `0x18000ffb0`
- `0x1800123d0`
- `0x18002cbe4`
- `0x18003e690`
- `0x180052cd0`
- `0x180052e28`
- `0x180056c50`
- `0x18007356c`
- `0x1800750c0`
- `0x180075104`
- `0x1800759c0`
- `0x180077894`
- `0x18007957c`
- `0x18007a298`
- `0x18007a5b0`
- `0x18007fdc0`
- `0x180091ef0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180077a66`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180077a66`

## string_xrefs

- `0x1800779cf`: `[ConfigService] GetConfigToken`
- `0x180077aeb`: `[ConfigService] GetConfigToken`
- `0x1800779a4`: `GetConfigToken failed to populate config service.`
- `0x180077acb`: `GetConfigToken failed to copy token.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Mso::OfficeWebServiceApi::ConfigService::GetConfigTokenInternal(
        unsigned int a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        wchar_t *Destination,
        unsigned int SizeInWords)
{
  __int64 v7; // rbx
  wchar_t *v8; // rdx
  unsigned int v9; // ebx
  int v10; // r9d
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 Value; // rax
  errno_t v14; // edi
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  const struct Mso::OfficeWebServiceApi::ConfigCachedFileInfo *v19; // rbx
  const char *v20; // [rsp+40h] [rbp-C0h] BYREF
  Mso::OfficeWebServiceApi::Token *v21[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v22[112]; // [rsp+60h] [rbp-A0h] BYREF
  void **v23; // [rsp+D0h] [rbp-30h] BYREF
  const char *v24; // [rsp+D8h] [rbp-28h]
  const wchar_t *v25; // [rsp+E0h] [rbp-20h]
  _BYTE v26[24]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v27; // [rsp+100h] [rbp+0h]
  __int64 v28; // [rsp+108h] [rbp+8h]
  _OWORD v29[2]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v30[3]; // [rsp+130h] [rbp+30h] BYREF
  __int16 v31; // [rsp+148h] [rbp+48h]
  __int128 v32; // [rsp+150h] [rbp+50h] BYREF
  __int64 v33; // [rsp+160h] [rbp+60h]
  __int64 v34; // [rsp+168h] [rbp+68h]
  _BYTE v35[304]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v36[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v37[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v38[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v39; // [rsp+300h] [rbp+200h]

  v7 = a3;
  Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::ConfigServiceTelemetryActivity(
    v35,
    a1,
    a2,
    a3,
    0,
    a4,
    a2 != 0);
  if ( (unsigned int)v7 < 0x14E && (_mm_lfence(), (v8 = off_180198E00[v7]) != 0) )
  {
    std::wstring::wstring(v29, v8);
  }
  else
  {
    v29[0] = 0;
    v29[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v29[0]) = 0;
  }
  if ( !SizeInWords )
    CrashWithRecovery(0x3632A3u, 0);
  *Destination = 0;
  if ( (unsigned int)v7 >= 0x14E )
  {
    v9 = sub_18007A298(509363935, v35, 2);
LABEL_20:
    std::wstring::~wstring(v29);
    Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::~ConfigServiceTelemetryActivity((Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity *)v35);
    return v9;
  }
  if ( !(unsigned __int8)Mso::OfficeWebServiceApi::ConfigService::PopulateForConfiguration(v35, a4, 650) )
  {
    v23 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
    v24 = "Message";
    v25 = L"GetConfigToken failed to populate config service.";
    *(_WORD *)v26 = 4;
    *(_OWORD *)&v26[8] = 0;
    v27 = 0;
    v28 = 7;
    *(_WORD *)&v26[8] = 0;
    v20 = "[ConfigService] GetConfigToken";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
      134567580,
      823,
      15,
      v10,
      (__int64)&v20,
      (__int64)&v23);
    std::wstring::~wstring(&v26[8]);
    v9 = 1;
    goto LABEL_20;
  }
  Mso::OfficeWebServiceApi::Service::FindTokenInMap(v21, v29, a4);
  if ( !v21[0] )
  {
    v11 = 1024;
    v12 = 509363934;
LABEL_19:
    v9 = sub_18007A298(v12, v35, v11);
    std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v21);
    goto LABEL_20;
  }
  Value = Mso::OfficeWebServiceApi::Token::GetValue(v21[0]);
  if ( *(_QWORD *)(Value + 24) > 7u )
    Value = *(_QWORD *)Value;
  v14 = wcsncpy_s(Destination, SizeInWords, (const wchar_t *)Value, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::~wstring(&v23);
  if ( v14 )
  {
    v23 = &Mso::Diagnostics::ClassifiedStructuredObject<int>::`vftable';
    v24 = "RetErr";
    LODWORD(v25) = v14;
    WORD2(v25) = 4;
    memset(v26, 0, sizeof(v26));
    v27 = 7;
    *(_WORD *)v26 = 0;
    v30[0] = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
    v30[1] = "Message";
    v30[2] = L"GetConfigToken failed to copy token.";
    v31 = 4;
    v32 = 0;
    v33 = 0;
    v34 = 7;
    LOWORD(v32) = 0;
    v20 = "[ConfigService] GetConfigToken";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<int>>(
      (unsigned int)L"GetConfigToken failed to copy token.",
      v15,
      v16,
      v17,
      (__int64)&v20,
      (__int64)v30,
      (__int64)&v23);
    std::wstring::~wstring(&v32);
    std::wstring::~wstring(v26);
    v11 = 0x800000;
    if ( v14 != 80 )
      v11 = 1;
    v12 = 509363933;
    goto LABEL_19;
  }
  Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::SetStatusFlags(v35, 509363932, 0);
  Mso::OfficeWebServiceApi::Service::GetCachedFileInfo((Mso::OfficeWebServiceApi::ConfigCachedFileInfo *)v22);
  if ( v22[96] )
  {
    v19 = (const struct Mso::OfficeWebServiceApi::ConfigCachedFileInfo *)std::optional<Mso::OfficeWebServiceApi::ConfigCachedFileInfo>::operator->(v22);
    if ( v39 )
    {
      std::wstring::operator=(v36, v19);
      std::wstring::operator=(v37, (char *)v19 + 32);
      std::wstring::operator=(v38, (char *)v19 + 64);
    }
    else
    {
      Mso::OfficeWebServiceApi::ConfigCachedFileInfo::ConfigCachedFileInfo(
        (Mso::OfficeWebServiceApi::ConfigCachedFileInfo *)v36,
        v19);
      v39 = 1;
    }
  }
  std::_Optional_destruct_base<Mso::OfficeWebServiceApi::ConfigCachedFileInfo,0>::~_Optional_destruct_base<Mso::OfficeWebServiceApi::ConfigCachedFileInfo,0>(v22);
  std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v21);
  std::wstring::~wstring(v29);
  Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::~ConfigServiceTelemetryActivity((Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity *)v35);
  return 0;
}

```

## disassembly

```asm
0x180077894  mov     [rsp-8+arg_0], rbx
0x180077899  mov     [rsp-8+arg_8], rdi
0x18007789e  push    rbp
0x18007789f  push    r14
0x1800778a1  push    r15
0x1800778a3  lea     rbp, [rsp-220h]
0x1800778ab  sub     rsp, 320h
0x1800778b2  mov     rax, cs:__security_cookie
0x1800778b9  xor     rax, rsp
0x1800778bc  mov     [rbp+230h+var_20], rax
0x1800778c3  mov     rdi, r9
0x1800778c6  mov     ebx, r8d
0x1800778c9  mov     r14, [rbp+230h+Destination]
0x1800778d0  xor     r15d, r15d
0x1800778d3  test    edx, edx
0x1800778d5  setnz   al
0x1800778d8  mov     byte ptr [rsp+330h+var_300], al
0x1800778dc  mov     [rsp+330h+var_308], r9
0x1800778e1  mov     byte ptr [rsp+330h+var_310], r15b
0x1800778e6  mov     r9d, r8d
0x1800778e9  mov     r8d, edx
0x1800778ec  mov     edx, ecx
0x1800778ee  lea     rcx, [rbp+230h+var_1C0]
0x1800778f2  call    ??0ConfigServiceTelemetryActivity@OfficeWebServiceApi@Mso@@QEAA@IW4ConfigServiceTelemetryApi@12@I_NAEBVFederationProviderConfiguration@12@1@Z; Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::ConfigServiceTelemetryActivity(uint,Mso::OfficeWebServiceApi::ConfigServiceTelemetryApi,uint,bool,Mso::OfficeWebServiceApi::FederationProviderConfiguration const &,bool)
0x1800778f7  cmp     ebx, 14Eh
0x1800778fd  jnb     short loc_18007791E
0x1800778ff  nop
0x180077900  lfence
0x180077903  lea     rdx, off_180198E00; "LiveOAuthAppID"
0x18007790a  mov     rdx, [rdx+rbx*8]
0x18007790e  test    rdx, rdx
0x180077911  jz      short loc_18007791E
0x180077913  lea     rcx, [rbp+230h+var_220]
0x180077917  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18007791c  jmp     short loc_180077937
0x18007791e  xorps   xmm0, xmm0
0x180077921  movups  [rbp+230h+var_220], xmm0
0x180077925  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007792d  movdqu  [rbp+230h+var_210], xmm1
0x180077932  mov     word ptr [rbp+230h+var_220], r15w
0x180077937  cmp     dword ptr [rbp+230h+SizeInWords], r15d
0x18007793e  jnz     short loc_18007794D
0x180077940  xor     edx, edx; struct CrashContext *
0x180077942  mov     ecx, 3632A3h; unsigned int
0x180077947  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18007794d  mov     [r14], r15w
0x180077951  cmp     ebx, 14Eh
0x180077957  jb      short loc_180077974
0x180077959  mov     r8d, 2
0x18007795f  lea     rdx, [rbp+230h+var_1C0]
0x180077963  mov     ecx, 1E5C46DFh
0x180077968  call    sub_18007A298
0x18007796d  mov     ebx, eax
0x18007796f  jmp     loc_180077B56
0x180077974  mov     r8d, 28Ah
0x18007797a  mov     rdx, rdi
0x18007797d  lea     rcx, [rbp+230h+var_1C0]
0x180077981  call    ?PopulateForConfiguration@ConfigService@OfficeWebServiceApi@Mso@@SA_NAEAVIConfigServiceTelemetryActivity@23@AEBVFederationProviderConfiguration@23@W4URL@ConfigURL@23@@Z; Mso::OfficeWebServiceApi::ConfigService::PopulateForConfiguration(Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity &,Mso::OfficeWebServiceApi::FederationProviderConfiguration const &,Mso::OfficeWebServiceApi::ConfigURL::URL)
0x180077986  test    al, al
0x180077988  jnz     loc_180077A14
0x18007798e  lea     rcx, ??_7FirstScheme@Structured@Logging@Http@Mso@@6B@; const Mso::Http::Logging::Structured::FirstScheme::`vftable'
0x180077995  mov     [rbp+230h+var_260], rcx
0x180077999  lea     rcx, aMessage; "Message"
0x1800779a0  mov     [rbp+230h+var_258], rcx
0x1800779a4  lea     rax, aGetconfigtoken; "GetConfigToken failed to populate confi"...
0x1800779ab  mov     [rbp+230h+var_250], rax
0x1800779af  mov     eax, 4
0x1800779b4  mov     word ptr [rbp+230h+var_248], ax
0x1800779b8  xorps   xmm0, xmm0
0x1800779bb  movups  [rbp+230h+var_248+8], xmm0
0x1800779bf  mov     [rbp+230h+var_230], r15
0x1800779c3  lea     ebx, [rax+3]
0x1800779c6  mov     [rbp+230h+var_228], rbx
0x1800779ca  mov     word ptr [rbp+230h+var_248+8], r15w
0x1800779cf  lea     rax, aConfigserviceG_0; "[ConfigService] GetConfigToken"
0x1800779d6  mov     [rsp+330h+var_2F0], rax
0x1800779db  lea     rax, [rbp+230h+var_260]
0x1800779df  mov     [rsp+330h+var_308], rax
0x1800779e4  lea     rax, [rsp+330h+var_2F0]
0x1800779e9  mov     [rsp+330h+var_310], rax
0x1800779ee  mov     edx, 337h
0x1800779f3  mov     ecx, 805569Ch
0x1800779f8  lea     r8d, [rbx+8]
0x1800779fc  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&)
0x180077a01  lea     rcx, [rbp+230h+var_248+8]; void *
0x180077a05  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180077a0a  mov     ebx, 1
0x180077a0f  jmp     loc_180077B56
0x180077a14  mov     r8, rdi
0x180077a17  lea     rdx, [rbp+230h+var_220]
0x180077a1b  lea     rcx, [rsp+330h+var_2E8]
0x180077a20  call    ?FindTokenInMap@Service@OfficeWebServiceApi@Mso@@SA?AV?$shared_ptr@VToken@OfficeWebServiceApi@Mso@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@AEBVFederationProviderConfiguration@23@@Z; Mso::OfficeWebServiceApi::Service::FindTokenInMap(std::wstring const &,Mso::OfficeWebServiceApi::FederationProviderConfiguration const &)
0x180077a25  mov     rcx, [rsp+330h+var_2E8]; this
0x180077a2a  test    rcx, rcx
0x180077a2d  jnz     short loc_180077A3F
0x180077a2f  mov     r8d, 400h
0x180077a35  mov     ecx, 1E5C46DEh
0x180077a3a  jmp     loc_180077B41
0x180077a3f  lea     rdx, [rbp+230h+var_260]
0x180077a43  call    ?GetValue@Token@OfficeWebServiceApi@Mso@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::OfficeWebServiceApi::Token::GetValue(void)
0x180077a48  mov     ebx, 7
0x180077a4d  cmp     [rax+18h], rbx
0x180077a51  jbe     short loc_180077A56
0x180077a53  mov     rax, [rax]
0x180077a56  mov     edx, dword ptr [rbp+230h+SizeInWords]; SizeInWords
0x180077a5c  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180077a60  mov     r8, rax; Source
0x180077a63  mov     rcx, r14; Destination
0x180077a66  call    cs:__imp_wcsncpy_s
0x180077a6c  mov     edi, eax
0x180077a6e  lea     rcx, [rbp+230h+var_260]; void *
0x180077a72  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180077a77  test    edi, edi
0x180077a79  jz      loc_180077B6F
0x180077a7f  lea     rax, ??_7?$ClassifiedStructuredObject@H@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<int>::`vftable'
0x180077a86  mov     [rbp+230h+var_260], rax
0x180077a8a  lea     rax, aReterr; "RetErr"
0x180077a91  mov     [rbp+230h+var_258], rax
0x180077a95  mov     dword ptr [rbp+230h+var_250], edi
0x180077a98  mov     eax, 4
0x180077a9d  mov     word ptr [rbp+230h+var_250+4], ax
0x180077aa1  xorps   xmm0, xmm0
0x180077aa4  movups  [rbp+230h+var_248], xmm0
0x180077aa8  mov     [rbp+230h+var_238], r15
0x180077aac  mov     [rbp+230h+var_230], rbx
0x180077ab0  mov     word ptr [rbp+230h+var_248], r15w
0x180077ab5  lea     rcx, ??_7FirstScheme@Structured@Logging@Http@Mso@@6B@; const Mso::Http::Logging::Structured::FirstScheme::`vftable'
0x180077abc  mov     [rbp+230h+var_200], rcx
0x180077ac0  lea     rcx, aMessage; "Message"
0x180077ac7  mov     [rbp+230h+var_1F8], rcx
0x180077acb  lea     rcx, aGetconfigtoken_0; "GetConfigToken failed to copy token."
0x180077ad2  mov     [rbp+230h+var_1F0], rcx
0x180077ad6  mov     [rbp+230h+var_1E8], ax
0x180077ada  movups  [rbp+230h+var_1E0], xmm0
0x180077ade  mov     [rbp+230h+var_1D0], r15
0x180077ae2  mov     [rbp+230h+var_1C8], rbx
0x180077ae6  mov     word ptr [rbp+230h+var_1E0], r15w
0x180077aeb  lea     rax, aConfigserviceG_0; "[ConfigService] GetConfigToken"
0x180077af2  mov     [rsp+330h+var_2F0], rax
0x180077af7  lea     rax, [rbp+230h+var_260]
0x180077afb  mov     [rsp+330h+var_300], rax
0x180077b00  lea     rax, [rbp+230h+var_200]
0x180077b04  mov     [rsp+330h+var_308], rax
0x180077b09  lea     rax, [rsp+330h+var_2F0]
0x180077b0e  mov     [rsp+330h+var_310], rax
0x180077b13  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@U?$ClassifiedStructuredObject@H@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAU?$ClassifiedStructuredObject@H@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<int>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<int> &&)
0x180077b18  lea     rcx, [rbp+230h+var_1E0]; void *
0x180077b1c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180077b21  lea     rcx, [rbp+230h+var_248]; void *
0x180077b25  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180077b2a  mov     eax, 1
0x180077b2f  mov     r8d, 800000h
0x180077b35  cmp     edi, 50h ; 'P'
0x180077b38  cmovnz  r8d, eax
0x180077b3c  mov     ecx, 1E5C46DDh
0x180077b41  lea     rdx, [rbp+230h+var_1C0]
0x180077b45  call    sub_18007A298
0x180077b4a  mov     ebx, eax
0x180077b4c  lea     rcx, [rsp+330h+var_2E8]; void *
0x180077b51  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x180077b56  lea     rcx, [rbp+230h+var_220]; void *
0x180077b5a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180077b5f  lea     rcx, [rbp+230h+var_1C0]; this
0x180077b63  call    ??1ConfigServiceTelemetryActivity@OfficeWebServiceApi@Mso@@UEAA@XZ; Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::~ConfigServiceTelemetryActivity(void)
0x180077b68  mov     eax, ebx
0x180077b6a  jmp     loc_180077C0F
0x180077b6f  xor     r8d, r8d
0x180077b72  mov     edx, 1E5C46DCh
0x180077b77  lea     rcx, [rbp+230h+var_1C0]
0x180077b7b  call    ?SetStatusFlags@ConfigServiceTelemetryActivity@OfficeWebServiceApi@Mso@@UEAAXIW4Flags@Status@23@@Z; Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::SetStatusFlags(uint,Mso::OfficeWebServiceApi::Status::Flags)
0x180077b80  lea     rcx, [rsp+330h+var_2D0]; this
0x180077b85  call    ?GetCachedFileInfo@Service@OfficeWebServiceApi@Mso@@SA?AV?$optional@UConfigCachedFileInfo@OfficeWebServiceApi@Mso@@@std@@XZ; Mso::OfficeWebServiceApi::Service::GetCachedFileInfo(void)
0x180077b8a  cmp     [rbp+230h+var_270], r15b
0x180077b8e  jz      short loc_180077BE7
0x180077b90  lea     rcx, [rsp+330h+var_2D0]
0x180077b95  call    ??C?$optional@UConfigCachedFileInfo@OfficeWebServiceApi@Mso@@@std@@QEBAPEBUConfigCachedFileInfo@OfficeWebServiceApi@Mso@@XZ; std::optional<Mso::OfficeWebServiceApi::ConfigCachedFileInfo>::operator->(void)
0x180077b9a  mov     rbx, rax
0x180077b9d  mov     rdx, rax; struct Mso::OfficeWebServiceApi::ConfigCachedFileInfo *
0x180077ba0  lea     rcx, [rbp+230h+var_90]; this
0x180077ba7  cmp     [rbp+230h+var_30], r15b
0x180077bae  jz      short loc_180077BD7
0x180077bb0  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180077bb5  lea     rdx, [rbx+20h]
0x180077bb9  lea     rcx, [rbp+230h+var_70]
0x180077bc0  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180077bc5  lea     rdx, [rbx+40h]
0x180077bc9  lea     rcx, [rbp+230h+var_50]
0x180077bd0  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180077bd5  jmp     short loc_180077BE7
0x180077bd7  call    ??0ConfigCachedFileInfo@OfficeWebServiceApi@Mso@@QEAA@AEBU012@@Z; Mso::OfficeWebServiceApi::ConfigCachedFileInfo::ConfigCachedFileInfo(Mso::OfficeWebServiceApi::ConfigCachedFileInfo const &)
0x180077bdc  mov     eax, 1
0x180077be1  mov     [rbp+230h+var_30], al
0x180077be7  lea     rcx, [rsp+330h+var_2D0]
0x180077bec  call    ??1?$_Optional_destruct_base@UConfigCachedFileInfo@OfficeWebServiceApi@Mso@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Mso::OfficeWebServiceApi::ConfigCachedFileInfo,0>::~_Optional_destruct_base<Mso::OfficeWebServiceApi::ConfigCachedFileInfo,0>(void)
0x180077bf1  lea     rcx, [rsp+330h+var_2E8]; void *
0x180077bf6  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x180077bfb  lea     rcx, [rbp+230h+var_220]; void *
0x180077bff  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180077c04  lea     rcx, [rbp+230h+var_1C0]; this
0x180077c08  call    ??1ConfigServiceTelemetryActivity@OfficeWebServiceApi@Mso@@UEAA@XZ; Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::~ConfigServiceTelemetryActivity(void)
0x180077c0d  xor     eax, eax
0x180077c0f  mov     rcx, [rbp+230h+var_20]
0x180077c16  xor     rcx, rsp; StackCookie
0x180077c19  call    __security_check_cookie
0x180077c1e  lea     r11, [rsp+330h+var_10]
0x180077c26  mov     rbx, [r11+20h]
0x180077c2a  mov     rdi, [r11+28h]
0x180077c2e  mov     rsp, r11
0x180077c31  pop     r15
0x180077c33  pop     r14
0x180077c35  pop     rbp
0x180077c36  retn
```
