# CSpeechInfoV2::GetSpeechHandler(void)

- ea: `0x1800cb8b8`
- end: `0x1800cbb78`
- name: `?GetSpeechHandler@CSpeechInfoV2@@CAAEAU_SPEECH_PREFERENCES@@XZ`
- size: `704`
- prototype: `struct _SPEECH_PREFERENCES *(void)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800cb880`
- `0x1800cb8a0`
- `0x1800cbb80`

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
- `0x180082d08`
- `0x180082e1c`
- `0x180083508`
- `0x1800cb8b8`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800cb997`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800cb997`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cb9e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cb9f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cb9e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cb9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cbb5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cbb5d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800cbac3`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800cbac3`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800cb9ba`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800cb9ba`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800cba5a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800cba5a`

## string_xrefs

- `0x1800cb9ee`: `WindowsCreateStringReference`
- `0x1800cb990`: `api-ms-win-core-winrt-string-l1-1-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct _SPEECH_PREFERENCES *__fastcall CSpeechInfoV2::GetSpeechHandler(__int64 a1, __int64 a2, unsigned __int16 a3)
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
  v4 = *(_DWORD *)(v3 + 944);
  v5 = v3 + 952;
  v6 = -1;
  if ( (v4 & 1) == 0 )
  {
    *(_DWORD *)(v3 + 944) = v4 | 1;
    *(_OWORD *)v5 = 0;
    *(_QWORD *)(v3 + 968) = 0;
    *(_QWORD *)(v3 + 976) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)v5, L"#", 1u);
    *(_DWORD *)(v3 + 984) = -1;
    *(_DWORD *)(v3 + 988) = -1;
    _tlregdtor(CSpeechInfoV2::GetSpeechHandler_::_2_::_dynamic_atexit_destructor_for__result__);
  }
  if ( *(_BYTE *)(v3 + 315) )
    return (struct _SPEECH_PREFERENCES *)v5;
  *(_BYTE *)(v3 + 315) = 1;
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
    return (struct _SPEECH_PREFERENCES *)v5;
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
      JUMPOUT(0x1800CBB77LL);
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
  return (struct _SPEECH_PREFERENCES *)v5;
}

```

## disassembly

```asm
0x1800cb8b8  push    rbp
0x1800cb8ba  push    rbx
0x1800cb8bb  push    rsi
0x1800cb8bc  push    rdi
0x1800cb8bd  push    r12
0x1800cb8bf  push    r14
0x1800cb8c1  push    r15
0x1800cb8c3  lea     rbp, [rsp-27h]
0x1800cb8c8  sub     rsp, 0A0h
0x1800cb8cf  mov     rax, cs:__security_cookie
0x1800cb8d6  xor     rax, rsp
0x1800cb8d9  mov     [rbp+57h+var_38], rax
0x1800cb8dd  mov     ecx, cs:_tls_index
0x1800cb8e3  mov     rax, gs:58h
0x1800cb8ec  mov     rbx, [rax+rcx*8]
0x1800cb8f0  mov     edx, 3B0h
0x1800cb8f5  mov     eax, [rdx+rbx]
0x1800cb8f8  mov     edi, 3B8h
0x1800cb8fd  add     rdi, rbx
0x1800cb900  xor     r12d, r12d
0x1800cb903  or      esi, 0FFFFFFFFh
0x1800cb906  test    al, 1
0x1800cb908  jnz     short loc_1800CB945
0x1800cb90a  or      eax, 1
0x1800cb90d  mov     [rdx+rbx], eax
0x1800cb910  xorps   xmm0, xmm0
0x1800cb913  movups  xmmword ptr [rdi], xmm0
0x1800cb916  mov     [rdi+10h], r12
0x1800cb91a  mov     [rdi+18h], r12
0x1800cb91e  lea     r8d, [r12+1]
0x1800cb923  lea     rdx, asc_1801B4764; "#"
0x1800cb92a  mov     rcx, rdi
0x1800cb92d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800cb932  mov     [rdi+20h], esi
0x1800cb935  mov     [rdi+24h], esi
0x1800cb938  lea     rcx, _CSpeechInfoV2__GetSpeechHandler____2____dynamic_atexit_destructor_for__result__
0x1800cb93f  call    __tlregdtor
0x1800cb944  nop
0x1800cb945  mov     eax, 13Bh
0x1800cb94a  cmp     [rax+rbx], r12b
0x1800cb94e  jnz     loc_1800CBB3C
0x1800cb954  mov     byte ptr [rax+rbx], 1
0x1800cb958  xor     edx, edx; unsigned __int16
0x1800cb95a  lea     ecx, [rdx+0Ah]; unsigned __int16
0x1800cb95d  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800cb962  test    al, al
0x1800cb964  jz      loc_1800CBAE9
0x1800cb96a  mov     r15b, r12b
0x1800cb96d  mov     [rbp+57h+var_98], r12
0x1800cb971  mov     [rbp+57h+var_88], r12
0x1800cb975  mov     [rbp+57h+var_70], r12
0x1800cb979  xorps   xmm0, xmm0
0x1800cb97c  movups  [rbp+57h+var_68], xmm0
0x1800cb980  mov     ebx, 800401F0h
0x1800cb985  mov     [rbp+57h+var_90], ebx
0x1800cb988  xor     edx, edx; hFile
0x1800cb98a  mov     r8d, 800h; dwFlags
0x1800cb990  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x1800cb997  call    cs:__imp_LoadLibraryExW
0x1800cb99d  lea     rcx, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800cb9a4  mov     [rbp+57h+var_80], rcx
0x1800cb9a8  mov     [rbp+57h+hModule], rax
0x1800cb9ac  test    rax, rax
0x1800cb9af  jz      loc_1800CBA99
0x1800cb9b5  mov     ecx, 1
0x1800cb9ba  call    cs:__imp_RoInitialize
0x1800cb9c0  test    eax, eax
0x1800cb9c2  js      short loc_1800CB9CB
0x1800cb9c4  mov     ebx, eax
0x1800cb9c6  mov     [rbp+57h+var_90], eax
0x1800cb9c9  jmp     short loc_1800CB9D2
0x1800cb9cb  cmp     eax, 80010106h
0x1800cb9d0  jz      short loc_1800CB9DA
0x1800cb9d2  test    eax, eax
0x1800cb9d4  js      loc_1800CBA99
0x1800cb9da  lea     rdx, aWindowsgetstri; "WindowsGetStringRawBuffer"
0x1800cb9e1  mov     rcx, [rbp+57h+hModule]; hModule
0x1800cb9e5  call    cs:__imp_GetProcAddress
0x1800cb9eb  mov     r14, rax
0x1800cb9ee  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x1800cb9f5  mov     rcx, [rbp+57h+hModule]; hModule
0x1800cb9f9  call    cs:__imp_GetProcAddress
0x1800cb9ff  test    rax, rax
0x1800cba02  jz      loc_1800CBA99
0x1800cba08  test    r14, r14
0x1800cba0b  jz      loc_1800CBA99
0x1800cba11  lea     r9, [rbp+57h+var_88]
0x1800cba15  lea     r8, [rbp+57h+var_70]
0x1800cba19  mov     edx, 2Ah ; '*'
0x1800cba1e  lea     rcx, ?RuntimeClass_Windows_Media_Speech_UserSpeechPreferences@@3QBGB; "Windows.Media.Speech.UserSpeechPreferen"...
0x1800cba25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cba2a  test    eax, eax
0x1800cba2c  js      short loc_1800CBA99
0x1800cba2e  mov     r14, [rbp+57h+var_88]
0x1800cba32  mov     rcx, [rbp+57h+var_98]
0x1800cba36  test    rcx, rcx
0x1800cba39  jz      short loc_1800CBA4C
0x1800cba3b  mov     [rbp+57h+var_98], r12
0x1800cba3f  mov     rax, [rcx]
0x1800cba42  mov     rax, [rax+10h]
0x1800cba46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cba4b  nop
0x1800cba4c  lea     r8, [rbp+57h+var_98]
0x1800cba50  lea     rdx, _GUID_32a96485_c187_4e95_b34e_d8a3be92e73a
0x1800cba57  mov     rcx, r14
0x1800cba5a  call    cs:__imp_RoGetActivationFactory
0x1800cba60  test    eax, eax
0x1800cba62  js      short loc_1800CBA99
0x1800cba64  cmp     [rbp+57h+var_98], r12
0x1800cba68  jz      short loc_1800CBA99
0x1800cba6a  mov     rdx, [rbp+57h+var_98]
0x1800cba6e  lea     rcx, [rbp+57h+var_58]
0x1800cba72  call    ?GetSpeechServicesPrivacySettingValue@CSpeechInfoV2@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIUserSpeechPreferencesStatics@Speech@Media@Windows@@@Z; CSpeechInfoV2::GetSpeechServicesPrivacySettingValue(Windows::Media::Speech::IUserSpeechPreferencesStatics *)
0x1800cba77  mov     rdx, rax
0x1800cba7a  mov     rcx, rdi
0x1800cba7d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800cba82  lea     rcx, [rbp+57h+var_58]
0x1800cba86  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cba8b  mov     eax, 64h ; 'd'
0x1800cba90  mov     [rdi+20h], eax
0x1800cba93  mov     [rdi+24h], eax
0x1800cba96  mov     r15b, 1
0x1800cba99  lea     rax, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800cbaa0  mov     [rbp+57h+var_80], rax
0x1800cbaa4  cmp     [rbp+57h+hModule], r12
0x1800cbaa8  jz      short loc_1800CBABF
0x1800cbaaa  lea     rcx, [rbp+57h+var_80]
0x1800cbaae  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800cbab3  test    al, al
0x1800cbab5  jz      loc_1800CBB5D
0x1800cbabb  mov     [rbp+57h+hModule], r12
0x1800cbabf  test    ebx, ebx
0x1800cbac1  js      short loc_1800CBACA
0x1800cbac3  call    cs:__imp_RoUninitialize
0x1800cbac9  nop
0x1800cbaca  mov     rcx, [rbp+57h+var_98]
0x1800cbace  test    rcx, rcx
0x1800cbad1  jz      short loc_1800CBAE4
0x1800cbad3  mov     [rbp+57h+var_98], r12
0x1800cbad7  mov     rax, [rcx]
0x1800cbada  mov     rax, [rax+10h]
0x1800cbade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbae3  nop
0x1800cbae4  test    r15b, r15b
0x1800cbae7  jnz     short loc_1800CBB3C
0x1800cbae9  lea     rcx, [rbp+57h+var_58]
0x1800cbaed  call    ?GetSpeechServicesEnabledSettingValue@SpeechInfo@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; SpeechInfo::GetSpeechServicesEnabledSettingValue(void)
0x1800cbaf2  mov     rdx, rax
0x1800cbaf5  mov     rcx, rdi
0x1800cbaf8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800cbafd  lea     rcx, [rbp+57h+var_58]
0x1800cbb01  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cbb06  mov     [rbp+57h+var_9F], r12b
0x1800cbb0a  mov     [rbp+57h+var_A0], r12b
0x1800cbb0e  lea     rdx, [rbp+57h+var_A0]; bool *
0x1800cbb12  lea     rcx, [rbp+57h+var_9F]; this
0x1800cbb16  call    ?GetUserAcceptedPrivacyPolicy@Settings@SpeechPlatform@@YAJPEA_N0@Z; SpeechPlatform::Settings::GetUserAcceptedPrivacyPolicy(bool *,bool *)
0x1800cbb1b  test    eax, eax
0x1800cbb1d  js      short loc_1800CBB2A
0x1800cbb1f  mov     esi, r12d
0x1800cbb22  cmp     [rbp+57h+var_A0], r12b
0x1800cbb26  setnz   sil
0x1800cbb2a  mov     [rdi+20h], esi
0x1800cbb2d  lea     rcx, aSoftwareMicros_54; "Software\\Microsoft\\PolicyManager\\Cur"...
0x1800cbb34  call    ?GetHKLMSettingValueForAllowInputPersonalization@CSpeechInfoV2@@CAHPEBG0@Z; CSpeechInfoV2::GetHKLMSettingValueForAllowInputPersonalization(ushort const *,ushort const *)
0x1800cbb39  mov     [rdi+24h], eax
0x1800cbb3c  mov     rax, rdi
0x1800cbb3f  mov     rcx, [rbp+57h+var_38]
0x1800cbb43  xor     rcx, rsp; StackCookie
0x1800cbb46  call    __security_check_cookie
0x1800cbb4b  add     rsp, 0A0h
0x1800cbb52  pop     r15
0x1800cbb54  pop     r14
0x1800cbb56  pop     r12
0x1800cbb58  pop     rdi
0x1800cbb59  pop     rsi
0x1800cbb5a  pop     rbx
0x1800cbb5b  pop     rbp
0x1800cbb5c  retn
0x1800cbb5d  call    cs:__imp_GetLastError
0x1800cbb63  nop
0x1800cbb64  test    eax, eax
0x1800cbb66  jle     short loc_1800CBB70
0x1800cbb68  movzx   eax, ax
0x1800cbb6b  or      eax, 80070000h
0x1800cbb70  mov     ecx, eax; this
0x1800cbb72  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
