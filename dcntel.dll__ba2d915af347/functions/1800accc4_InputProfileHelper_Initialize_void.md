# InputProfileHelper::Initialize(void)

- ea: `0x1800accc4`
- end: `0x1800acfd0`
- name: `?Initialize@InputProfileHelper@@QEAAJXZ`
- size: `780`
- prototype: `__int64 __fastcall(InputProfileHelper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ad150`

## callees

- `0x180008dc0`
- `0x1800097d0`
- `0x180013708`
- `0x18001daf0`
- `0x18001dcc8`
- `0x1800accc4`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800acd7b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800acd7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800acda3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800acda3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800acf18`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800acf31`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800acf18`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800acf31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acfaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acfaa`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800ace51`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800ace51`

## string_xrefs

- `0x1800acd99`: `WindowsCreateStringReference`
- `0x1800acd74`: `api-ms-win-core-winrt-string-l1-1-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall InputProfileHelper::Initialize(InputProfileHelper *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  HMODULE Library; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  FARPROC ProcAddress; // r10
  signed int ActivationFactory; // edi
  __int64 v9; // rcx
  const unsigned __int16 *v10; // rax
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, char *); // r15
  _QWORD *v15; // r14
  __int64 v16; // rdx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, InputProfileHelper *); // r15
  __int64 v19; // rdx
  BOOL v20; // eax
  unsigned int v21; // r8d
  const char *v22; // r9
  wil::details::in1diag3 *v23; // rcx
  __int64 v24; // rcx
  signed int LastError; // eax
  int v27; // edx
  unsigned int v28; // r8d
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
  int v30; // [rsp+38h] [rbp-31h] BYREF
  __int64 v31; // [rsp+40h] [rbp-29h] BYREF
  const int *v32; // [rsp+48h] [rbp-21h] BYREF
  HMODULE v33; // [rsp+50h] [rbp-19h]
  _QWORD *v34; // [rsp+58h] [rbp-11h]
  __int128 v35; // [rsp+60h] [rbp-9h] BYREF
  __int64 v36; // [rsp+70h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v29 = 0;
  v30 = 0;
  v35 = 0;
  v36 = 0;
  v31 = 0;
  v2 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( v2 )
  {
    *v2 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager *,Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs *>::`vftable';
    *((_DWORD *)v2 + 3) = 1;
    *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager *,Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs *>>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v3[2] = this;
    *v3 = off_180194928;
  }
  else
  {
    v3 = 0;
  }
  v34 = v3;
  Library = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  v32 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v33 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WindowsCreateStringReference");
    if ( ProcAddress )
    {
      v9 = 0x7FFFFFFF;
      v10 = L"Windows.UI.Internal.Text.Core.CoreKeyboardInputProfileManager";
      do
      {
        if ( !*v10 )
          break;
        ++v10;
        --v9;
      }
      while ( v9 );
      ActivationFactory = v9 == 0 ? 0x80070057 : 0;
      v5 = 0x7FFFFFFF - v9;
      v6 = (0x7FFFFFFF - v9) & -(__int64)(v9 != 0);
      if ( v9 )
      {
        ActivationFactory = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, __int128 *, __int64 *))ProcAddress)(
                              L"Windows.UI.Internal.Text.Core.CoreKeyboardInputProfileManager",
                              (unsigned int)v6,
                              &v35,
                              &v31);
        if ( ActivationFactory >= 0 )
        {
          v11 = v31;
          v12 = v29;
          if ( v29 )
          {
            v29 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          }
          ActivationFactory = RoGetActivationFactory(v11, &GUID_d0380bbe_201e_4a70_8eff_bb52f7996cae, &v29);
          if ( ActivationFactory >= 0 )
          {
            v13 = v29;
            v14 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v29 + 48LL);
            v15 = (_QWORD *)((char *)this + 8);
            v16 = *((_QWORD *)this + 1);
            if ( v16 )
            {
              *v15 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
            }
            ActivationFactory = v14(v13, (char *)this + 8);
            if ( ActivationFactory >= 0 )
            {
              v17 = *v15;
              v18 = *(__int64 (__fastcall **)(__int64, InputProfileHelper *))(*(_QWORD *)*v15 + 160LL);
              v19 = *(_QWORD *)this;
              if ( *(_QWORD *)this )
              {
                *(_QWORD *)this = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              }
              ActivationFactory = v18(v17, this);
              if ( ActivationFactory >= 0 )
              {
                ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)this + 56LL))(
                                      *(_QWORD *)this,
                                      &v30);
                if ( ActivationFactory >= 0 )
                {
                  (*(void (__fastcall **)(_QWORD, _QWORD *, char *))(*(_QWORD *)*v15 + 64LL))(
                    *v15,
                    v3,
                    (char *)this + 24);
                  if ( v30 )
                  {
                    v20 = SetEvent(*((HANDLE *)this + 2));
                    v23 = retaddr;
                    if ( !v20 )
                      goto LABEL_39;
                    SetEvent(KeyboardWinRTClient::s_hInit);
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      ActivationFactory = -2147467263;
    }
  }
  else
  {
    ActivationFactory = 126;
  }
  v32 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( !v33 )
    goto LABEL_31;
  if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v32) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v27, v28);
LABEL_39:
    wil::details::in1diag3::_FailFast_GetLastError(v23, (void *)0xA01, v21, v22);
  }
  v33 = 0;
LABEL_31:
  if ( v3 )
    (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v3 + 16LL))(v3, v5, v6);
  v24 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v24 + 16LL))(v24, v5, v6);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800accc4  push    rbp
0x1800accc6  push    rbx
0x1800accc7  push    rsi
0x1800accc8  push    rdi
0x1800accc9  push    r12
0x1800acccb  push    r13
0x1800acccd  push    r14
0x1800acccf  push    r15
0x1800accd1  lea     rbp, [rsp-1Fh]
0x1800accd6  sub     rsp, 88h
0x1800accdd  mov     rax, cs:__security_cookie
0x1800acce4  xor     rax, rsp
0x1800acce7  mov     [rbp+57h+var_48], rax
0x1800acceb  mov     rsi, rcx
0x1800accee  xor     r12d, r12d
0x1800accf1  mov     [rbp+57h+var_90], r12
0x1800accf5  mov     [rbp+57h+var_88], r12d
0x1800accf9  xorps   xmm0, xmm0
0x1800accfc  xor     eax, eax
0x1800accfe  movups  [rbp+57h+var_60], xmm0
0x1800acd02  mov     [rbp+57h+var_50], rax
0x1800acd06  mov     [rbp+57h+var_80], r12
0x1800acd0a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800acd11  lea     ecx, [rax+18h]; unsigned __int64
0x1800acd14  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800acd19  mov     rbx, rax
0x1800acd1c  test    rax, rax
0x1800acd1f  jz      short loc_1800ACD65
0x1800acd21  lea     rax, ??_7?$ITypedEventHandler@PEAVCoreKeyboardInputProfileManager@Core@Text@Internal@UI@Windows@@PEAVCoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs@23456@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager *,Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs *>::`vftable'
0x1800acd28  mov     [rbx], rax
0x1800acd2b  mov     dword ptr [rbx+0Ch], 1
0x1800acd32  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVCoreKeyboardInputProfileManager@Core@Text@Internal@UI@Windows@@PEAVCoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs@23456@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager *,Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs *>>::`vftable'
0x1800acd39  mov     [rbx], rax
0x1800acd3c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800acd43  test    rcx, rcx
0x1800acd46  jz      short loc_1800ACD55
0x1800acd48  mov     rax, [rcx]
0x1800acd4b  mov     rax, [rax+8]
0x1800acd4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acd54  nop
0x1800acd55  mov     [rbx+10h], rsi
0x1800acd59  lea     rax, off_180194928
0x1800acd60  mov     [rbx], rax
0x1800acd63  jmp     short loc_1800ACD68
0x1800acd65  mov     rbx, r12
0x1800acd68  mov     [rbp+57h+var_68], rbx
0x1800acd6c  xor     edx, edx; hFile
0x1800acd6e  mov     r8d, 800h; dwFlags
0x1800acd74  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x1800acd7b  call    cs:__imp_LoadLibraryExW
0x1800acd81  lea     r13, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800acd88  mov     [rbp+57h+var_78], r13
0x1800acd8c  mov     [rbp+57h+var_70], rax
0x1800acd90  test    rax, rax
0x1800acd93  jz      loc_1800ACF39
0x1800acd99  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x1800acda0  mov     rcx, rax; hModule
0x1800acda3  call    cs:__imp_GetProcAddress
0x1800acda9  mov     r10, rax
0x1800acdac  test    rax, rax
0x1800acdaf  jnz     short loc_1800ACDBB
0x1800acdb1  mov     edi, 80004001h
0x1800acdb6  jmp     loc_1800ACF3E
0x1800acdbb  mov     edx, 7FFFFFFFh
0x1800acdc0  mov     ecx, edx
0x1800acdc2  lea     rax, ?RuntimeClass_Windows_UI_Internal_Text_Core_CoreKeyboardInputProfileManager@@3QBGB; "Windows.UI.Internal.Text.Core.CoreKeybo"...
0x1800acdc9  cmp     [rax], r12w
0x1800acdcd  jz      short loc_1800ACDD9
0x1800acdcf  add     rax, 2
0x1800acdd3  sub     rcx, 1
0x1800acdd7  jnz     short loc_1800ACDC9
0x1800acdd9  mov     rax, rcx
0x1800acddc  neg     rax
0x1800acddf  sbb     edi, edi
0x1800acde1  not     edi
0x1800acde3  and     edi, 80070057h
0x1800acde9  mov     rax, rcx
0x1800acdec  sub     rdx, rcx
0x1800acdef  neg     rax
0x1800acdf2  sbb     r8, r8
0x1800acdf5  and     r8, rdx
0x1800acdf8  test    rcx, rcx
0x1800acdfb  jz      loc_1800ACF3E
0x1800ace01  mov     edx, r8d
0x1800ace04  lea     r9, [rbp+57h+var_80]
0x1800ace08  lea     r8, [rbp+57h+var_60]
0x1800ace0c  lea     rcx, ?RuntimeClass_Windows_UI_Internal_Text_Core_CoreKeyboardInputProfileManager@@3QBGB; "Windows.UI.Internal.Text.Core.CoreKeybo"...
0x1800ace13  mov     rax, r10
0x1800ace16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace1b  mov     edi, eax
0x1800ace1d  test    eax, eax
0x1800ace1f  js      loc_1800ACF3E
0x1800ace25  mov     rdi, [rbp+57h+var_80]
0x1800ace29  mov     rcx, [rbp+57h+var_90]
0x1800ace2d  test    rcx, rcx
0x1800ace30  jz      short loc_1800ACE43
0x1800ace32  mov     [rbp+57h+var_90], r12
0x1800ace36  mov     rax, [rcx]
0x1800ace39  mov     rax, [rax+10h]
0x1800ace3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace42  nop
0x1800ace43  lea     r8, [rbp+57h+var_90]
0x1800ace47  lea     rdx, _GUID_d0380bbe_201e_4a70_8eff_bb52f7996cae
0x1800ace4e  mov     rcx, rdi
0x1800ace51  call    cs:__imp_RoGetActivationFactory
0x1800ace57  mov     edi, eax
0x1800ace59  test    eax, eax
0x1800ace5b  js      loc_1800ACF3E
0x1800ace61  mov     rdi, [rbp+57h+var_90]
0x1800ace65  mov     rax, [rdi]
0x1800ace68  mov     r15, [rax+30h]
0x1800ace6c  lea     r14, [rsi+8]
0x1800ace70  mov     rdx, [r14]
0x1800ace73  test    rdx, rdx
0x1800ace76  jz      short loc_1800ACE8B
0x1800ace78  mov     [r14], r12
0x1800ace7b  mov     rcx, [rdx]
0x1800ace7e  mov     rax, [rcx+10h]
0x1800ace82  mov     rcx, rdx
0x1800ace85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace8a  nop
0x1800ace8b  mov     rdx, r14
0x1800ace8e  mov     rcx, rdi
0x1800ace91  mov     rax, r15
0x1800ace94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace99  mov     edi, eax
0x1800ace9b  test    eax, eax
0x1800ace9d  js      loc_1800ACF3E
0x1800acea3  mov     rdi, [r14]
0x1800acea6  mov     rax, [rdi]
0x1800acea9  mov     r15, [rax+0A0h]
0x1800aceb0  mov     rdx, [rsi]
0x1800aceb3  test    rdx, rdx
0x1800aceb6  jz      short loc_1800ACECB
0x1800aceb8  mov     [rsi], r12
0x1800acebb  mov     rcx, [rdx]
0x1800acebe  mov     rax, [rcx+10h]
0x1800acec2  mov     rcx, rdx
0x1800acec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aceca  nop
0x1800acecb  mov     rdx, rsi
0x1800acece  mov     rcx, rdi
0x1800aced1  mov     rax, r15
0x1800aced4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aced9  mov     edi, eax
0x1800acedb  test    eax, eax
0x1800acedd  js      short loc_1800ACF3E
0x1800acedf  mov     rcx, [rsi]
0x1800acee2  mov     rax, [rcx]
0x1800acee5  lea     rdx, [rbp+57h+var_88]
0x1800acee9  mov     rax, [rax+38h]
0x1800aceed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acef2  mov     edi, eax
0x1800acef4  test    eax, eax
0x1800acef6  js      short loc_1800ACF3E
0x1800acef8  mov     rcx, [r14]
0x1800acefb  mov     rax, [rcx]
0x1800acefe  lea     r8, [rsi+18h]
0x1800acf02  mov     rdx, rbx
0x1800acf05  mov     rax, [rax+40h]
0x1800acf09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf0e  cmp     [rbp+57h+var_88], r12d
0x1800acf12  jbe     short loc_1800ACF3E
0x1800acf14  mov     rcx, [rsi+10h]; hEvent
0x1800acf18  call    cs:__imp_SetEvent
0x1800acf1e  mov     rcx, [rbp+5Fh]
0x1800acf22  test    eax, eax
0x1800acf24  jz      loc_1800ACFC5
0x1800acf2a  mov     rcx, cs:?s_hInit@KeyboardWinRTClient@@2PEAXEA; hEvent
0x1800acf31  call    cs:__imp_SetEvent
0x1800acf37  jmp     short loc_1800ACF3E
0x1800acf39  mov     edi, 7Eh ; '~'
0x1800acf3e  mov     [rbp+57h+var_78], r13
0x1800acf42  cmp     [rbp+57h+var_70], r12
0x1800acf46  jz      short loc_1800ACF59
0x1800acf48  lea     rcx, [rbp+57h+var_78]
0x1800acf4c  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800acf51  test    al, al
0x1800acf53  jz      short loc_1800ACFAA
0x1800acf55  mov     [rbp+57h+var_70], r12
0x1800acf59  test    rbx, rbx
0x1800acf5c  jz      short loc_1800ACF6E
0x1800acf5e  mov     rax, [rbx]
0x1800acf61  mov     rcx, rbx
0x1800acf64  mov     rax, [rax+10h]
0x1800acf68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf6d  nop
0x1800acf6e  mov     rcx, [rbp+57h+var_90]
0x1800acf72  test    rcx, rcx
0x1800acf75  jz      short loc_1800ACF88
0x1800acf77  mov     [rbp+57h+var_90], r12
0x1800acf7b  mov     rax, [rcx]
0x1800acf7e  mov     rax, [rax+10h]
0x1800acf82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf87  nop
0x1800acf88  mov     eax, edi
0x1800acf8a  mov     rcx, [rbp+57h+var_48]
0x1800acf8e  xor     rcx, rsp; StackCookie
0x1800acf91  call    __security_check_cookie
0x1800acf96  add     rsp, 88h
0x1800acf9d  pop     r15
0x1800acf9f  pop     r14
0x1800acfa1  pop     r13
0x1800acfa3  pop     r12
0x1800acfa5  pop     rdi
0x1800acfa6  pop     rsi
0x1800acfa7  pop     rbx
0x1800acfa8  pop     rbp
0x1800acfa9  retn
0x1800acfaa  call    cs:__imp_GetLastError
0x1800acfb0  nop
0x1800acfb1  test    eax, eax
0x1800acfb3  jle     short loc_1800ACFBD
0x1800acfb5  movzx   eax, ax
0x1800acfb8  or      eax, 80070000h
0x1800acfbd  mov     ecx, eax; this
0x1800acfbf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800acfc4  nop
0x1800acfc5  mov     edx, 0A01h; void *
0x1800acfca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
