# SpeechInfo::GetSpeechHandler(void)

- ea: `0x180082a18`
- end: `0x180082cd8`
- name: `?GetSpeechHandler@SpeechInfo@@CAAEAU_SPEECH_PREFERENCES_2@@XZ`
- size: `704`
- prototype: `struct _SPEECH_PREFERENCES_2 *(void)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180082850`
- `0x180082a00`
- `0x180082ce0`

## callees

- `0x180008dc0`
- `0x180009448`
- `0x180014f2c`
- `0x180016748`
- `0x180016db0`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18002a690`
- `0x180082454`
- `0x180082a18`
- `0x180082d08`
- `0x180082e1c`
- `0x180083508`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180082af7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180082af7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180082b45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180082b59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180082b45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180082b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082cbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082cbd`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180082c23`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180082c23`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180082b1a`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180082b1a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180082bba`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180082bba`

## string_xrefs

- `0x180082b4e`: `WindowsCreateStringReference`
- `0x180082af0`: `api-ms-win-core-winrt-string-l1-1-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct _SPEECH_PREFERENCES_2 *__fastcall SpeechInfo::GetSpeechHandler(__int64 a1, __int64 a2, unsigned __int16 a3)
{
  __int64 v3; // rbx
  int v4; // eax
  __int64 v5; // rdi
  int v6; // esi
  char v7; // r15
  int v8; // ebx
  HMODULE Library; // rax
  __int64 v10; // rdx
  const int *v11; // rcx
  int v12; // eax
  FARPROC ProcAddress; // r14
  FARPROC v14; // rax
  __int64 SpeechServicesPrivacySettingValue; // rax
  __int64 v16; // rcx
  __int64 SpeechServicesEnabledSettingValue; // rax
  bool *v18; // r8
  const unsigned __int16 *v19; // rdx
  signed int LastError; // eax
  int v22; // edx
  unsigned int v23; // r8d
  bool v24; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v25[7]; // [rsp+31h] [rbp-48h] BYREF
  __int64 v26; // [rsp+38h] [rbp-41h] BYREF
  int v27; // [rsp+40h] [rbp-39h]
  __int64 v28; // [rsp+48h] [rbp-31h] BYREF
  const int *v29; // [rsp+50h] [rbp-29h] BYREF
  HMODULE hModule; // [rsp+58h] [rbp-21h]
  __int64 v31; // [rsp+60h] [rbp-19h] BYREF
  __int128 v32; // [rsp+68h] [rbp-11h]
  char *v33[4]; // [rsp+78h] [rbp-1h] BYREF

  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + *(unsigned int *)&tls_index);
  v4 = *(_DWORD *)(v3 + 528);
  v5 = v3 + 536;
  v6 = -1;
  if ( (v4 & 1) == 0 )
  {
    *(_DWORD *)(v3 + 528) = v4 | 1;
    *(_OWORD *)v5 = 0;
    *(_QWORD *)(v3 + 552) = 0;
    *(_QWORD *)(v3 + 560) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)v5, L"#", 1u);
    *(_DWORD *)(v3 + 568) = -1;
    *(_DWORD *)(v3 + 572) = -1;
    _tlregdtor(SpeechInfo::GetSpeechHandler_::_2_::_dynamic_atexit_destructor_for__result__);
  }
  if ( *(_BYTE *)(v3 + 310) )
    return (struct _SPEECH_PREFERENCES_2 *)v5;
  *(_BYTE *)(v3 + 310) = 1;
  if ( !IsWindowsVersionOrGreater(0xAu, 0, a3) )
  {
LABEL_24:
    SpeechServicesEnabledSettingValue = SpeechInfo::GetSpeechServicesEnabledSettingValue(v33);
    std::wstring::operator=(v5, SpeechServicesEnabledSettingValue);
    std::wstring::~wstring(v33);
    v25[0] = 0;
    v24 = 0;
    if ( (int)SpeechPlatform::Settings::GetUserAcceptedPrivacyPolicy((SpeechPlatform::Settings *)v25, &v24, v18) >= 0 )
      v6 = v24;
    *(_DWORD *)(v5 + 32) = v6;
    *(_DWORD *)(v5 + 36) = CSpeechInfoV2::GetHKLMSettingValueForAllowInputPersonalization(
                             L"Software\\Microsoft\\PolicyManager\\Current\\Device\\Privacy",
                             v19);
    return (struct _SPEECH_PREFERENCES_2 *)v5;
  }
  v7 = 0;
  v26 = 0;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v8 = -2147221008;
  v27 = -2147221008;
  Library = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  v11 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v29 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = Library;
  if ( Library )
  {
    v12 = RoInitialize(1);
    if ( v12 < 0 )
    {
      if ( v12 == -2147417850 )
      {
LABEL_10:
        ProcAddress = GetProcAddress(hModule, "WindowsGetStringRawBuffer");
        v14 = GetProcAddress(hModule, "WindowsCreateStringReference");
        if ( v14
          && ProcAddress
          && ((int (__fastcall *)(const unsigned __int16 *, __int64, __int64 *, __int64 *))v14)(
               L"Windows.Media.Speech.UserSpeechPreferences",
               42,
               &v31,
               &v28) >= 0
          && (int)RoGetActivationFactory(v28, &GUID_32a96485_c187_4e95_b34e_d8a3be92e73a, &v26) >= 0
          && v26 )
        {
          SpeechServicesPrivacySettingValue = CSpeechInfoV2::GetSpeechServicesPrivacySettingValue(v33, v26);
          std::wstring::operator=(v5, SpeechServicesPrivacySettingValue);
          std::wstring::~wstring(v33);
          *(_DWORD *)(v5 + 32) = 100;
          *(_DWORD *)(v5 + 36) = 100;
          v7 = 1;
        }
        goto LABEL_16;
      }
    }
    else
    {
      v8 = v12;
      v27 = v12;
    }
    if ( v12 < 0 )
      goto LABEL_16;
    goto LABEL_10;
  }
LABEL_16:
  v29 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v29) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v22, v23);
      JUMPOUT(0x180082CD7LL);
    }
    hModule = 0;
  }
  if ( v8 >= 0 )
    RoUninitialize(v11, v10);
  v16 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( !v7 )
    goto LABEL_24;
  return (struct _SPEECH_PREFERENCES_2 *)v5;
}

```

## disassembly

```asm
0x180082a18  push    rbp
0x180082a1a  push    rbx
0x180082a1b  push    rsi
0x180082a1c  push    rdi
0x180082a1d  push    r12
0x180082a1f  push    r14
0x180082a21  push    r15
0x180082a23  lea     rbp, [rsp-27h]
0x180082a28  sub     rsp, 0A0h
0x180082a2f  mov     rax, cs:__security_cookie
0x180082a36  xor     rax, rsp
0x180082a39  mov     [rbp+57h+var_38], rax
0x180082a3d  mov     ecx, cs:_tls_index
0x180082a43  mov     rax, gs:58h
0x180082a4c  mov     rbx, [rax+rcx*8]
0x180082a50  mov     edx, 210h
0x180082a55  mov     eax, [rdx+rbx]
0x180082a58  mov     edi, 218h
0x180082a5d  add     rdi, rbx
0x180082a60  xor     r12d, r12d
0x180082a63  or      esi, 0FFFFFFFFh
0x180082a66  test    al, 1
0x180082a68  jnz     short loc_180082AA5
0x180082a6a  or      eax, 1
0x180082a6d  mov     [rdx+rbx], eax
0x180082a70  xorps   xmm0, xmm0
0x180082a73  movups  xmmword ptr [rdi], xmm0
0x180082a76  mov     [rdi+10h], r12
0x180082a7a  mov     [rdi+18h], r12
0x180082a7e  lea     r8d, [r12+1]
0x180082a83  lea     rdx, asc_1801B4764; "#"
0x180082a8a  mov     rcx, rdi
0x180082a8d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180082a92  mov     [rdi+20h], esi
0x180082a95  mov     [rdi+24h], esi
0x180082a98  lea     rcx, _SpeechInfo__GetSpeechHandler____2____dynamic_atexit_destructor_for__result__
0x180082a9f  call    __tlregdtor
0x180082aa4  nop
0x180082aa5  mov     eax, 136h
0x180082aaa  cmp     [rax+rbx], r12b
0x180082aae  jnz     loc_180082C9C
0x180082ab4  mov     byte ptr [rax+rbx], 1
0x180082ab8  xor     edx, edx; unsigned __int16
0x180082aba  lea     ecx, [rdx+0Ah]; unsigned __int16
0x180082abd  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x180082ac2  test    al, al
0x180082ac4  jz      loc_180082C49
0x180082aca  mov     r15b, r12b
0x180082acd  mov     [rbp+57h+var_98], r12
0x180082ad1  mov     [rbp+57h+var_88], r12
0x180082ad5  mov     [rbp+57h+var_70], r12
0x180082ad9  xorps   xmm0, xmm0
0x180082adc  movups  [rbp+57h+var_68], xmm0
0x180082ae0  mov     ebx, 800401F0h
0x180082ae5  mov     [rbp+57h+var_90], ebx
0x180082ae8  xor     edx, edx; hFile
0x180082aea  mov     r8d, 800h; dwFlags
0x180082af0  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x180082af7  call    cs:__imp_LoadLibraryExW
0x180082afd  lea     rcx, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180082b04  mov     [rbp+57h+var_80], rcx
0x180082b08  mov     [rbp+57h+hModule], rax
0x180082b0c  test    rax, rax
0x180082b0f  jz      loc_180082BF9
0x180082b15  mov     ecx, 1
0x180082b1a  call    cs:__imp_RoInitialize
0x180082b20  test    eax, eax
0x180082b22  js      short loc_180082B2B
0x180082b24  mov     ebx, eax
0x180082b26  mov     [rbp+57h+var_90], eax
0x180082b29  jmp     short loc_180082B32
0x180082b2b  cmp     eax, 80010106h
0x180082b30  jz      short loc_180082B3A
0x180082b32  test    eax, eax
0x180082b34  js      loc_180082BF9
0x180082b3a  lea     rdx, aWindowsgetstri; "WindowsGetStringRawBuffer"
0x180082b41  mov     rcx, [rbp+57h+hModule]; hModule
0x180082b45  call    cs:__imp_GetProcAddress
0x180082b4b  mov     r14, rax
0x180082b4e  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x180082b55  mov     rcx, [rbp+57h+hModule]; hModule
0x180082b59  call    cs:__imp_GetProcAddress
0x180082b5f  test    rax, rax
0x180082b62  jz      loc_180082BF9
0x180082b68  test    r14, r14
0x180082b6b  jz      loc_180082BF9
0x180082b71  lea     r9, [rbp+57h+var_88]
0x180082b75  lea     r8, [rbp+57h+var_70]
0x180082b79  mov     edx, 2Ah ; '*'
0x180082b7e  lea     rcx, ?RuntimeClass_Windows_Media_Speech_UserSpeechPreferences@@3QBGB; "Windows.Media.Speech.UserSpeechPreferen"...
0x180082b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b8a  test    eax, eax
0x180082b8c  js      short loc_180082BF9
0x180082b8e  mov     r14, [rbp+57h+var_88]
0x180082b92  mov     rcx, [rbp+57h+var_98]
0x180082b96  test    rcx, rcx
0x180082b99  jz      short loc_180082BAC
0x180082b9b  mov     [rbp+57h+var_98], r12
0x180082b9f  mov     rax, [rcx]
0x180082ba2  mov     rax, [rax+10h]
0x180082ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082bab  nop
0x180082bac  lea     r8, [rbp+57h+var_98]
0x180082bb0  lea     rdx, _GUID_32a96485_c187_4e95_b34e_d8a3be92e73a
0x180082bb7  mov     rcx, r14
0x180082bba  call    cs:__imp_RoGetActivationFactory
0x180082bc0  test    eax, eax
0x180082bc2  js      short loc_180082BF9
0x180082bc4  cmp     [rbp+57h+var_98], r12
0x180082bc8  jz      short loc_180082BF9
0x180082bca  mov     rdx, [rbp+57h+var_98]
0x180082bce  lea     rcx, [rbp+57h+var_58]
0x180082bd2  call    ?GetSpeechServicesPrivacySettingValue@CSpeechInfoV2@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIUserSpeechPreferencesStatics@Speech@Media@Windows@@@Z; CSpeechInfoV2::GetSpeechServicesPrivacySettingValue(Windows::Media::Speech::IUserSpeechPreferencesStatics *)
0x180082bd7  mov     rdx, rax
0x180082bda  mov     rcx, rdi
0x180082bdd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180082be2  lea     rcx, [rbp+57h+var_58]
0x180082be6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180082beb  mov     eax, 64h ; 'd'
0x180082bf0  mov     [rdi+20h], eax
0x180082bf3  mov     [rdi+24h], eax
0x180082bf6  mov     r15b, 1
0x180082bf9  lea     rax, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180082c00  mov     [rbp+57h+var_80], rax
0x180082c04  cmp     [rbp+57h+hModule], r12
0x180082c08  jz      short loc_180082C1F
0x180082c0a  lea     rcx, [rbp+57h+var_80]
0x180082c0e  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180082c13  test    al, al
0x180082c15  jz      loc_180082CBD
0x180082c1b  mov     [rbp+57h+hModule], r12
0x180082c1f  test    ebx, ebx
0x180082c21  js      short loc_180082C2A
0x180082c23  call    cs:__imp_RoUninitialize
0x180082c29  nop
0x180082c2a  mov     rcx, [rbp+57h+var_98]
0x180082c2e  test    rcx, rcx
0x180082c31  jz      short loc_180082C44
0x180082c33  mov     [rbp+57h+var_98], r12
0x180082c37  mov     rax, [rcx]
0x180082c3a  mov     rax, [rax+10h]
0x180082c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082c43  nop
0x180082c44  test    r15b, r15b
0x180082c47  jnz     short loc_180082C9C
0x180082c49  lea     rcx, [rbp+57h+var_58]
0x180082c4d  call    ?GetSpeechServicesEnabledSettingValue@SpeechInfo@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; SpeechInfo::GetSpeechServicesEnabledSettingValue(void)
0x180082c52  mov     rdx, rax
0x180082c55  mov     rcx, rdi
0x180082c58  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180082c5d  lea     rcx, [rbp+57h+var_58]
0x180082c61  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180082c66  mov     [rbp+57h+var_9F], r12b
0x180082c6a  mov     [rbp+57h+var_A0], r12b
0x180082c6e  lea     rdx, [rbp+57h+var_A0]; bool *
0x180082c72  lea     rcx, [rbp+57h+var_9F]; this
0x180082c76  call    ?GetUserAcceptedPrivacyPolicy@Settings@SpeechPlatform@@YAJPEA_N0@Z; SpeechPlatform::Settings::GetUserAcceptedPrivacyPolicy(bool *,bool *)
0x180082c7b  test    eax, eax
0x180082c7d  js      short loc_180082C8A
0x180082c7f  mov     esi, r12d
0x180082c82  cmp     [rbp+57h+var_A0], r12b
0x180082c86  setnz   sil
0x180082c8a  mov     [rdi+20h], esi
0x180082c8d  lea     rcx, aSoftwareMicros_54; "Software\\Microsoft\\PolicyManager\\Cur"...
0x180082c94  call    ?GetHKLMSettingValueForAllowInputPersonalization@CSpeechInfoV2@@CAHPEBG0@Z; CSpeechInfoV2::GetHKLMSettingValueForAllowInputPersonalization(ushort const *,ushort const *)
0x180082c99  mov     [rdi+24h], eax
0x180082c9c  mov     rax, rdi
0x180082c9f  mov     rcx, [rbp+57h+var_38]
0x180082ca3  xor     rcx, rsp; StackCookie
0x180082ca6  call    __security_check_cookie
0x180082cab  add     rsp, 0A0h
0x180082cb2  pop     r15
0x180082cb4  pop     r14
0x180082cb6  pop     r12
0x180082cb8  pop     rdi
0x180082cb9  pop     rsi
0x180082cba  pop     rbx
0x180082cbb  pop     rbp
0x180082cbc  retn
0x180082cbd  call    cs:__imp_GetLastError
0x180082cc3  nop
0x180082cc4  test    eax, eax
0x180082cc6  jle     short loc_180082CD0
0x180082cc8  movzx   eax, ax
0x180082ccb  or      eax, 80070000h
0x180082cd0  mov     ecx, eax; this
0x180082cd2  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
