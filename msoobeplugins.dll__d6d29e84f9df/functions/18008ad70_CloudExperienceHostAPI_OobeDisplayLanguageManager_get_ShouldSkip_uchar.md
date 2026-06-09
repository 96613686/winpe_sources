# CloudExperienceHostAPI::OobeDisplayLanguageManager::get_ShouldSkip(uchar *)

- ea: `0x18008ad70`
- end: `0x18008afcb`
- name: `?get_ShouldSkip@OobeDisplayLanguageManager@CloudExperienceHostAPI@@UEAAJPEAE@Z`
- size: `603`
- prototype: `__int64 __fastcall(CloudExperienceHostAPI::OobeDisplayLanguageManager *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003470`
- `0x180004eb0`
- `0x180008b54`
- `0x180019140`
- `0x18001e9a4`
- `0x1800203d0`
- `0x1800230b0`
- `0x1800418d8`
- `0x18007f5c0`
- `0x180088950`
- `0x18008a464`
- `0x18008a5b4`
- `0x18008ad70`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008af77`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008af77`
- `ext-ms-win-resources-languageoverlay-l1-1-5!GetInstalledLanguagePackType` at `0x18008aee3`
- `ext-ms-win-resources-languageoverlay-l1-1-5!GetInstalledLanguagePackType` at `0x18008aee3`

## string_xrefs

- `0x18008ae69`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`
- `0x18008afa0`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeDisplayLanguageManager::get_ShouldSkip(
        CloudExperienceHostAPI::OobeDisplayLanguageManager *this,
        unsigned __int8 *a2)
{
  __int64 v4; // rbx
  unsigned int (__fastcall *v5)(unsigned int, unsigned __int16 *, unsigned int, const unsigned __int16 *); // r14
  unsigned int v6; // eax
  unsigned int v7; // esi
  unsigned int v9; // ebx
  unsigned int v10; // r8d
  const char *v11; // r9
  int v12; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned int v14; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+34h] [rbp-CCh] BYREF
  int v16; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String2[88]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String1[88]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  CloudExperienceHostCoreTelemetry::GlobalizationState<char const (&)[67]>("CloudExperienceHostAPI::OobeDisplayLanguageMa"
                                                                           "nager::get_ShouldSkip");
  v14 = 0;
  SHRegGetDWORD(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
    L"SetupDisplayedLanguageSelection",
    &v14);
  if ( v14 != 1 )
  {
    SHRegGetDWORD(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\MUI\\Settings", L"IntlOOBEUnattend", &v14);
    if ( (v14 & 1) == 0 )
    {
      v17 = L"CloudAssignedLanguage";
      v4 = *(_QWORD *)AutoPilotUtils::AutoPilotTryGetStringPolicy(&v18, &v17);
      Windows::Internal::String::~String((Windows::Internal::String *)&v18);
      if ( !v4 )
      {
        v5 = (unsigned int (__fastcall *)(unsigned int, unsigned __int16 *, unsigned int, const unsigned __int16 *))*((_QWORD *)this + 8);
        if ( !v5 )
          v5 = GetSupportedUILanguages;
        v6 = v5(0, 0, 0, (const unsigned __int16 *)1);
        v7 = v6;
        if ( v6 >= 2 )
        {
          if ( v6 == 2 && (unsigned __int8)IsGetInstalledLanguagePackTypePresent() )
          {
            GetSystemPreferredUILanguage(&v17);
            v16 = 0;
            v18 = 0;
            v15 = 0;
            if ( (int)GetInstalledLanguagePackType(v17, &v16, &v18, &v15) >= 0 && v15 && !v16 && v18 )
            {
              *a2 = 1;
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
              return 0;
            }
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
          }
          String2[0] = 0;
          v9 = 0;
          while ( 1 )
          {
            if ( ((unsigned int (__fastcall *)(_QWORD, WCHAR *, __int64))v5)(v9, String1, 85) )
            {
              if ( String2[0] && CompareStringOrdinal(String1, -1, String2, -1, 1) != 2 )
              {
                *a2 = 0;
                return 0;
              }
              v12 = StringCchCopyW(String2, 0x55u, String1);
              if ( v12 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x154,
                  (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
                  (const char *)(unsigned int)v12,
                  bIgnoreCase);
            }
            else
            {
              wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x14A, v10, v11);
            }
            if ( ++v9 >= v7 )
              goto LABEL_9;
          }
        }
        if ( !v6 )
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x118,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
            (const char *)0x8000FFFFLL,
            bIgnoreCase);
      }
    }
  }
LABEL_9:
  *a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x18008ad70  mov     [rsp-8+arg_10], rbx
0x18008ad75  push    rbp
0x18008ad76  push    rsi
0x18008ad77  push    rdi
0x18008ad78  push    r14
0x18008ad7a  push    r15
0x18008ad7c  lea     rbp, [rsp-0C0h]
0x18008ad84  sub     rsp, 1C0h
0x18008ad8b  mov     rax, cs:__security_cookie
0x18008ad92  xor     rax, rsp
0x18008ad95  mov     [rbp+0E0h+var_30], rax
0x18008ad9c  mov     rsi, rcx
0x18008ad9f  mov     rdi, rdx
0x18008ada2  lea     rcx, aCloudexperienc_11; "CloudExperienceHostAPI::OobeDisplayLang"...
0x18008ada9  call    ??$GlobalizationState@AEAY0ED@$$CBD@CloudExperienceHostCoreTelemetry@@SAXAEAY0ED@$$CBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState<char const (&)[67]>(char const (&)[67])
0x18008adae  mov     rbx, 0FFFFFFFF80000002h
0x18008adb5  lea     r9, [rsp+1E0h+var_1B0]; unsigned int *
0x18008adba  xor     r15d, r15d
0x18008adbd  lea     r8, aSetupdisplayed; "SetupDisplayedLanguageSelection"
0x18008adc4  mov     rcx, rbx; HKEY
0x18008adc7  mov     [rsp+1E0h+var_1B0], r15d
0x18008adcc  lea     rdx, aSoftwareMicros_19; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18008add3  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18008add8  cmp     [rsp+1E0h+var_1B0], 1
0x18008addd  jz      loc_18008AE80
0x18008ade3  lea     r9, [rsp+1E0h+var_1B0]; unsigned int *
0x18008ade8  mov     rcx, rbx; HKEY
0x18008adeb  lea     r8, aIntloobeunatte; "IntlOOBEUnattend"
0x18008adf2  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\MUI"...
0x18008adf9  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18008adfe  test    byte ptr [rsp+1E0h+var_1B0], 1
0x18008ae03  jnz     short loc_18008AE80
0x18008ae05  lea     rax, aCloudassignedl; "CloudAssignedLanguage"
0x18008ae0c  lea     rdx, [rsp+1E0h+var_1A0]
0x18008ae11  mov     [rsp+1E0h+var_1A0], rax
0x18008ae16  lea     rcx, [rsp+1E0h+var_198]
0x18008ae1b  call    ?AutoPilotTryGetStringPolicy@AutoPilotUtils@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBQEBG@Z; AutoPilotUtils::AutoPilotTryGetStringPolicy(ushort const * const &)
0x18008ae20  lea     rcx, [rsp+1E0h+var_198]; this
0x18008ae25  mov     rbx, [rax]
0x18008ae28  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18008ae2d  test    rbx, rbx
0x18008ae30  jnz     short loc_18008AE80
0x18008ae32  mov     r14, [rsi+40h]
0x18008ae36  lea     rax, GetSupportedUILanguages
0x18008ae3d  test    r14, r14
0x18008ae40  lea     r9d, [r15+1]
0x18008ae44  cmovz   r14, rax
0x18008ae48  xor     r8d, r8d
0x18008ae4b  mov     rax, r14
0x18008ae4e  xor     edx, edx
0x18008ae50  xor     ecx, ecx
0x18008ae52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ae57  mov     esi, eax
0x18008ae59  cmp     eax, 2
0x18008ae5c  jnb     short loc_18008AEAB
0x18008ae5e  test    eax, eax
0x18008ae60  jnz     short loc_18008AE80
0x18008ae62  mov     rcx, [rbp+0E8h]; this
0x18008ae69  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x18008ae70  mov     r9d, 8000FFFFh; char *
0x18008ae76  mov     edx, 118h; void *
0x18008ae7b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18008ae80  mov     byte ptr [rdi], 1
0x18008ae83  xor     eax, eax
0x18008ae85  mov     rcx, [rbp+0E0h+var_30]
0x18008ae8c  xor     rcx, rsp; StackCookie
0x18008ae8f  call    __security_check_cookie
0x18008ae94  mov     rbx, [rsp+1E0h+arg_10]
0x18008ae9c  add     rsp, 1C0h
0x18008aea3  pop     r15
0x18008aea5  pop     r14
0x18008aea7  pop     rdi
0x18008aea8  pop     rsi
0x18008aea9  pop     rbp
0x18008aeaa  retn
0x18008aeab  jnz     short loc_18008AF1E
0x18008aead  call    IsGetInstalledLanguagePackTypePresent
0x18008aeb2  test    al, al
0x18008aeb4  jz      short loc_18008AF1E
0x18008aeb6  lea     rcx, [rsp+1E0h+var_1A0]
0x18008aebb  call    ?GetSystemPreferredUILanguage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; GetSystemPreferredUILanguage(void)
0x18008aec0  mov     rcx, [rsp+1E0h+var_1A0]
0x18008aec5  lea     r9, [rsp+1E0h+var_1AC]
0x18008aeca  lea     r8, [rsp+1E0h+var_198]
0x18008aecf  mov     [rsp+1E0h+var_1A8], r15d
0x18008aed4  lea     rdx, [rsp+1E0h+var_1A8]
0x18008aed9  mov     [rsp+1E0h+var_198], r15d
0x18008aede  mov     [rsp+1E0h+var_1AC], r15d
0x18008aee3  call    cs:__imp_GetInstalledLanguagePackType
0x18008aee9  test    eax, eax
0x18008aeeb  js      short loc_18008AF14
0x18008aeed  cmp     [rsp+1E0h+var_1AC], r15d
0x18008aef2  jz      short loc_18008AF14
0x18008aef4  cmp     [rsp+1E0h+var_1A8], r15d
0x18008aef9  jnz     short loc_18008AF14
0x18008aefb  cmp     [rsp+1E0h+var_198], r15d
0x18008af00  jz      short loc_18008AF14
0x18008af02  lea     rcx, [rsp+1E0h+var_1A0]
0x18008af07  mov     byte ptr [rdi], 1
0x18008af0a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008af0f  jmp     loc_18008AE83
0x18008af14  lea     rcx, [rsp+1E0h+var_1A0]
0x18008af19  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008af1e  mov     [rsp+1E0h+String2], r15w
0x18008af24  mov     ebx, r15d
0x18008af27  mov     r9d, 1
0x18008af2d  lea     rdx, [rbp+0E0h+String1]
0x18008af31  mov     ecx, ebx
0x18008af33  mov     rax, r14
0x18008af36  lea     r8d, [r9+54h]
0x18008af3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008af3f  test    eax, eax
0x18008af41  jnz     short loc_18008AF56
0x18008af43  mov     rcx, [rbp+0E8h]; this
0x18008af4a  mov     edx, 14Ah; void *
0x18008af4f  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18008af54  jmp     short loc_18008AFB4
0x18008af56  cmp     [rsp+1E0h+String2], r15w
0x18008af5c  jz      short loc_18008AF82
0x18008af5e  or      eax, 0FFFFFFFFh
0x18008af61  mov     [rsp+1E0h+bIgnoreCase], 1; int
0x18008af69  mov     r9d, eax; cchCount2
0x18008af6c  lea     r8, [rsp+1E0h+String2]; lpString2
0x18008af71  mov     edx, eax; cchCount1
0x18008af73  lea     rcx, [rbp+0E0h+String1]; lpString1
0x18008af77  call    cs:__imp_CompareStringOrdinal
0x18008af7d  cmp     eax, 2
0x18008af80  jnz     short loc_18008AFC3
0x18008af82  lea     r8, [rbp+0E0h+String1]; unsigned __int16 *
0x18008af86  mov     edx, 55h ; 'U'; unsigned __int64
0x18008af8b  lea     rcx, [rsp+1E0h+String2]; unsigned __int16 *
0x18008af90  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008af95  test    eax, eax
0x18008af97  jns     short loc_18008AFB4
0x18008af99  mov     rcx, [rbp+0E8h]; this
0x18008afa0  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x18008afa7  mov     r9d, eax; char *
0x18008afaa  mov     edx, 154h; void *
0x18008afaf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008afb4  inc     ebx
0x18008afb6  cmp     ebx, esi
0x18008afb8  jb      loc_18008AF27
0x18008afbe  jmp     loc_18008AE80
0x18008afc3  mov     [rdi], r15b
0x18008afc6  jmp     loc_18008AE83
```
