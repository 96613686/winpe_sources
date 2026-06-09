# UserNLSInfo::CollectSpeechInputLanguage(void)

- ea: `0x18008ab60`
- end: `0x18008b1c0`
- name: `?CollectSpeechInputLanguage@UserNLSInfo@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `1632`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008dc0`
- `0x180009f08`
- `0x180014f2c`
- `0x1800157b8`
- `0x180016748`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18002a690`
- `0x18008ab60`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008ac0f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008ac0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008ad05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008ad19`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008ad05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008ad19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b13e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b18c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b1a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b13e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b18c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b1a6`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008acd4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008ad93`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008ae9e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008af62`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008afcd`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008b03c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008b0a2`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008acd4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008ad93`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008ae9e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008af62`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008afcd`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008b03c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18008b0a2`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18008ac73`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18008ac73`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008ade5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008ade5`

## string_xrefs

- `0x18008ad0e`: `WindowsCreateStringReference`
- `0x18008ac08`: `api-ms-win-core-winrt-string-l1-1-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall UserNLSInfo::CollectSpeechInputLanguage(__int64 a1, __int64 a2, unsigned __int16 a3)
{
  int v4; // ebx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  FARPROC ProcAddress; // r15
  FARPROC v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int ActivationFactory; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdi
  int (__fastcall *v21)(__int64, __int64 *); // rsi
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rcx
  _WORD *v28; // rax
  __int64 v29; // r8
  unsigned __int64 v30; // rdx
  void **v31; // rsi
  __int64 v32; // rdi
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  signed int v40; // eax
  int v41; // edx
  unsigned int v42; // r8d
  signed int LastError; // eax
  int v44; // edx
  unsigned int v45; // r8d
  signed int v46; // eax
  int v47; // edx
  unsigned int v48; // r8d
  signed int v49; // eax
  int v50; // edx
  unsigned int v51; // r8d
  signed int v52; // eax
  int v53; // edx
  unsigned int v54; // r8d
  signed int v55; // eax
  int v56; // edx
  unsigned int v57; // r8d
  signed int v58; // eax
  int v59; // edx
  unsigned int v60; // r8d
  __int64 v61; // [rsp+30h] [rbp-69h] BYREF
  __int64 v62; // [rsp+38h] [rbp-61h] BYREF
  const int *v63; // [rsp+40h] [rbp-59h] BYREF
  HMODULE hModule; // [rsp+48h] [rbp-51h]
  int v65; // [rsp+50h] [rbp-49h]
  __int64 v66; // [rsp+58h] [rbp-41h] BYREF
  __int64 v67; // [rsp+60h] [rbp-39h] BYREF
  __int64 v68; // [rsp+70h] [rbp-29h] BYREF
  __int128 v69; // [rsp+78h] [rbp-21h]
  void *v70[2]; // [rsp+88h] [rbp-11h] BYREF
  __int128 v71; // [rsp+98h] [rbp-1h]

  v66 = a2;
  if ( !IsWindowsVersionOrGreater(0xAu, 0, a3) )
  {
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)a2, L"#", 1u);
    return a2;
  }
  *(_OWORD *)v70 = 0;
  v71 = 0u;
  std::wstring::_Construct<1,unsigned short const *>((char **)v70, L"#", 1u);
  v66 = 0;
  v62 = 0;
  v61 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v4 = -2147221008;
  v65 = -2147221008;
  v63 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  if ( hModule )
  {
    v6 = RoInitialize(1);
    if ( v6 < 0 )
    {
      if ( v6 == -2147417850 )
        goto LABEL_19;
    }
    else
    {
      v4 = v6;
      v65 = v6;
    }
    if ( v6 < 0 )
    {
      *(_OWORD *)a2 = *(_OWORD *)v70;
      *(_OWORD *)(a2 + 16) = v71;
      *(_QWORD *)&v71 = 0;
      *((_QWORD *)&v71 + 1) = 7;
      LOWORD(v70[0]) = 0;
      v63 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( hModule )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v63) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v44, v45);
          __debugbreak();
        }
        hModule = 0;
      }
      if ( v4 >= 0 )
        RoUninitialize(v8, v7);
      v9 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      goto LABEL_83;
    }
LABEL_19:
    ProcAddress = GetProcAddress(hModule, "WindowsGetStringRawBuffer");
    v11 = GetProcAddress(hModule, "WindowsCreateStringReference");
    if ( v11 && ProcAddress )
    {
      if ( ((int (__fastcall *)(const unsigned __int16 *, __int64, __int64 *, __int64 *))v11)(
             L"Windows.Media.SpeechRecognition.SpeechRecognizer",
             48,
             &v68,
             &v67) >= 0 )
      {
        ActivationFactory = RoGetActivationFactory(v67, &GUID_87a35eac_a7dc_4b0b_bcc9_24f47c0b7ebf, &v61);
        v20 = v61;
        if ( ActivationFactory >= 0 && v61 )
        {
          v21 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 48LL);
          v22 = v62;
          if ( v62 )
          {
            v62 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
          if ( v21(v20, &v62) >= 0 && (v24 = v62) != 0 )
          {
            if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v62 + 48LL))(v62, &v66) >= 0 )
            {
              v28 = (_WORD *)((__int64 (__fastcall *)(__int64, _QWORD))ProcAddress)(v66, 0);
              v30 = -1;
              do
                ++v30;
              while ( v28[v30] );
              if ( v30 > *((_QWORD *)&v71 + 1) )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  (char **)v70,
                  v30,
                  v29,
                  v28);
              }
              else
              {
                v31 = v70;
                if ( *((_QWORD *)&v71 + 1) > 7u )
                  v31 = (void **)v70[0];
                *(_QWORD *)&v71 = v30;
                v32 = 2 * v30;
                memmove_0(v31, v28, 2 * v30);
                *(_WORD *)((char *)v31 + v32) = 0;
              }
              *(_OWORD *)a2 = *(_OWORD *)v70;
              *(_OWORD *)(a2 + 16) = v71;
              *(_QWORD *)&v71 = 0;
              *((_QWORD *)&v71 + 1) = 7;
              LOWORD(v70[0]) = 0;
              v63 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
              if ( hModule )
              {
                if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v63) )
                {
                  v52 = GetLastError();
                  if ( v52 > 0 )
                    v52 = (unsigned __int16)v52 | 0x80070000;
                  Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v52, v53, v54);
                  __debugbreak();
                }
                hModule = 0;
              }
              if ( v4 >= 0 )
                RoUninitialize(v34, v33);
              v35 = v61;
              if ( v61 )
              {
                v61 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
              }
            }
            else
            {
              *(_OWORD *)a2 = *(_OWORD *)v70;
              *(_OWORD *)(a2 + 16) = v71;
              *(_QWORD *)&v71 = 0;
              *((_QWORD *)&v71 + 1) = 7;
              LOWORD(v70[0]) = 0;
              v63 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
              if ( hModule )
              {
                if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v63) )
                {
                  v49 = GetLastError();
                  if ( v49 > 0 )
                    v49 = (unsigned __int16)v49 | 0x80070000;
                  Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v49, v50, v51);
                  __debugbreak();
                }
                hModule = 0;
              }
              if ( v4 >= 0 )
                RoUninitialize(v26, v25);
              v27 = v61;
              if ( v61 )
              {
                v61 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
              }
            }
          }
          else
          {
            *(_OWORD *)a2 = *(_OWORD *)v70;
            *(_OWORD *)(a2 + 16) = v71;
            *(_QWORD *)&v71 = 0;
            *((_QWORD *)&v71 + 1) = 7;
            LOWORD(v70[0]) = 0;
            v63 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
            if ( hModule )
            {
              if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v63) )
              {
                v55 = GetLastError();
                if ( v55 > 0 )
                  v55 = (unsigned __int16)v55 | 0x80070000;
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v55, v56, v57);
                __debugbreak();
              }
              hModule = 0;
            }
            if ( v4 >= 0 )
              RoUninitialize(v24, v23);
            v36 = v61;
            if ( v61 )
            {
              v61 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            }
          }
        }
        else
        {
          *(_OWORD *)a2 = *(_OWORD *)v70;
          *(_OWORD *)(a2 + 16) = v71;
          *(_QWORD *)&v71 = 0;
          *((_QWORD *)&v71 + 1) = 7;
          LOWORD(v70[0]) = 0;
          v63 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
          if ( hModule )
          {
            if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v63) )
            {
              v58 = GetLastError();
              if ( v58 > 0 )
                v58 = (unsigned __int16)v58 | 0x80070000;
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v58, v59, v60);
              JUMPOUT(0x18008B1BFLL);
            }
            hModule = 0;
            v20 = v61;
          }
          if ( v4 >= 0 )
          {
            RoUninitialize(v19, v18);
            v20 = v61;
          }
          if ( v20 )
          {
            v61 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
        }
      }
      else
      {
        *(_OWORD *)a2 = *(_OWORD *)v70;
        *(_OWORD *)(a2 + 16) = v71;
        *(_QWORD *)&v71 = 0;
        *((_QWORD *)&v71 + 1) = 7;
        LOWORD(v70[0]) = 0;
        v63 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
        if ( hModule )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v63) )
          {
            v46 = GetLastError();
            if ( v46 > 0 )
              v46 = (unsigned __int16)v46 | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v46, v47, v48);
            __debugbreak();
          }
          hModule = 0;
        }
        if ( v4 >= 0 )
          RoUninitialize(v15, v14);
        v16 = v61;
        if ( v61 )
        {
          v61 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
      }
    }
    else
    {
      *(_OWORD *)a2 = *(_OWORD *)v70;
      *(_OWORD *)(a2 + 16) = v71;
      *(_QWORD *)&v71 = 0;
      *((_QWORD *)&v71 + 1) = 7;
      LOWORD(v70[0]) = 0;
      v63 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( hModule )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v63) )
        {
          v40 = GetLastError();
          if ( v40 > 0 )
            v40 = (unsigned __int16)v40 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v40, v41, v42);
          __debugbreak();
        }
        hModule = 0;
      }
      if ( v4 >= 0 )
        RoUninitialize(v13, v12);
      v37 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
    }
    goto LABEL_83;
  }
  *(_OWORD *)a2 = *(_OWORD *)v70;
  *(_OWORD *)(a2 + 16) = v71;
  *(_QWORD *)&v71 = 0;
  *((_QWORD *)&v71 + 1) = 7;
  LOWORD(v70[0]) = 0;
  v63 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v5 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
LABEL_83:
  v38 = v62;
  if ( v62 )
  {
    v62 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  std::wstring::~wstring((char **)v70);
  return a2;
}

```

## disassembly

```asm
0x18008ab60  push    rbp
0x18008ab62  push    rbx
0x18008ab63  push    rsi
0x18008ab64  push    rdi
0x18008ab65  push    r12
0x18008ab67  push    r13
0x18008ab69  push    r14
0x18008ab6b  push    r15
0x18008ab6d  lea     rbp, [rsp-1Fh]
0x18008ab72  sub     rsp, 0B8h
0x18008ab79  mov     rax, cs:__security_cookie
0x18008ab80  xor     rax, rsp
0x18008ab83  mov     [rbp+57h+var_48], rax
0x18008ab87  mov     r14, rdx
0x18008ab8a  mov     [rbp+57h+var_98], rdx
0x18008ab8e  xor     r12d, r12d
0x18008ab91  xor     edx, edx; unsigned __int16
0x18008ab93  lea     ecx, [rdx+0Ah]; unsigned __int16
0x18008ab96  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x18008ab9b  xorps   xmm0, xmm0
0x18008ab9e  lea     r8d, [r12+1]
0x18008aba3  lea     rdx, asc_1801B4764; "#"
0x18008abaa  test    al, al
0x18008abac  jnz     short loc_18008ABC7
0x18008abae  movups  xmmword ptr [r14], xmm0
0x18008abb2  mov     [r14+10h], r12
0x18008abb6  mov     [r14+18h], r12
0x18008abba  mov     rcx, r14
0x18008abbd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008abc2  jmp     loc_18008B0E6
0x18008abc7  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18008abcb  mov     qword ptr [rbp+57h+var_58], r12
0x18008abcf  mov     qword ptr [rbp+57h+var_58+8], r12
0x18008abd3  lea     rcx, [rbp+57h+var_68]
0x18008abd7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008abdc  nop
0x18008abdd  mov     [rbp+57h+var_98], r12
0x18008abe1  mov     [rbp+57h+var_B8], r12
0x18008abe5  mov     [rbp+57h+var_C0], r12
0x18008abe9  mov     [rbp+57h+var_90], r12
0x18008abed  mov     [rbp+57h+var_80], r12
0x18008abf1  xorps   xmm0, xmm0
0x18008abf4  movups  [rbp+57h+var_78], xmm0
0x18008abf8  mov     ebx, 800401F0h
0x18008abfd  mov     [rbp+57h+var_A0], ebx
0x18008ac00  xor     edx, edx; hFile
0x18008ac02  mov     r8d, 800h; dwFlags
0x18008ac08  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x18008ac0f  call    cs:__imp_LoadLibraryExW
0x18008ac15  lea     r13, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18008ac1c  mov     [rbp+57h+var_B0], r13
0x18008ac20  mov     [rbp+57h+hModule], rax
0x18008ac24  test    rax, rax
0x18008ac27  jnz     short loc_18008AC6E
0x18008ac29  movups  xmm0, xmmword ptr [rbp+57h+var_68]
0x18008ac2d  movups  xmmword ptr [r14], xmm0
0x18008ac31  movups  xmm1, [rbp+57h+var_58]
0x18008ac35  movups  xmmword ptr [r14+10h], xmm1
0x18008ac3a  mov     qword ptr [rbp+57h+var_58], r12
0x18008ac3e  mov     qword ptr [rbp+57h+var_58+8], 7
0x18008ac46  mov     word ptr [rbp+57h+var_68], r12w
0x18008ac4b  mov     [rbp+57h+var_B0], r13
0x18008ac4f  mov     rcx, [rbp+57h+var_C0]
0x18008ac53  test    rcx, rcx
0x18008ac56  jz      short loc_18008AC69
0x18008ac58  mov     [rbp+57h+var_C0], r12
0x18008ac5c  mov     rax, [rcx]
0x18008ac5f  mov     rax, [rax+10h]
0x18008ac63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ac68  nop
0x18008ac69  jmp     loc_18008B0C3
0x18008ac6e  mov     ecx, 1
0x18008ac73  call    cs:__imp_RoInitialize
0x18008ac79  test    eax, eax
0x18008ac7b  js      short loc_18008AC84
0x18008ac7d  mov     ebx, eax
0x18008ac7f  mov     [rbp+57h+var_A0], eax
0x18008ac82  jmp     short loc_18008AC8B
0x18008ac84  cmp     eax, 80010106h
0x18008ac89  jz      short loc_18008ACFA
0x18008ac8b  test    eax, eax
0x18008ac8d  jns     short loc_18008ACFA
0x18008ac8f  movups  xmm0, xmmword ptr [rbp+57h+var_68]
0x18008ac93  movups  xmmword ptr [r14], xmm0
0x18008ac97  movups  xmm1, [rbp+57h+var_58]
0x18008ac9b  movups  xmmword ptr [r14+10h], xmm1
0x18008aca0  mov     qword ptr [rbp+57h+var_58], r12
0x18008aca4  mov     qword ptr [rbp+57h+var_58+8], 7
0x18008acac  mov     word ptr [rbp+57h+var_68], r12w
0x18008acb1  mov     [rbp+57h+var_B0], r13
0x18008acb5  cmp     [rbp+57h+hModule], r12
0x18008acb9  jz      short loc_18008ACD0
0x18008acbb  lea     rcx, [rbp+57h+var_B0]
0x18008acbf  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18008acc4  test    al, al
0x18008acc6  jz      loc_18008B124
0x18008accc  mov     [rbp+57h+hModule], r12
0x18008acd0  test    ebx, ebx
0x18008acd2  js      short loc_18008ACDB
0x18008acd4  call    cs:__imp_RoUninitialize
0x18008acda  nop
0x18008acdb  mov     rcx, [rbp+57h+var_C0]
0x18008acdf  test    rcx, rcx
0x18008ace2  jz      short loc_18008ACF5
0x18008ace4  mov     [rbp+57h+var_C0], r12
0x18008ace8  mov     rax, [rcx]
0x18008aceb  mov     rax, [rax+10h]
0x18008acef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008acf4  nop
0x18008acf5  jmp     loc_18008B0C3
0x18008acfa  lea     rdx, aWindowsgetstri; "WindowsGetStringRawBuffer"
0x18008ad01  mov     rcx, [rbp+57h+hModule]; hModule
0x18008ad05  call    cs:__imp_GetProcAddress
0x18008ad0b  mov     r15, rax
0x18008ad0e  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x18008ad15  mov     rcx, [rbp+57h+hModule]; hModule
0x18008ad19  call    cs:__imp_GetProcAddress
0x18008ad1f  test    rax, rax
0x18008ad22  jz      loc_18008B061
0x18008ad28  test    r15, r15
0x18008ad2b  jz      loc_18008B061
0x18008ad31  lea     r9, [rbp+57h+var_90]
0x18008ad35  lea     r8, [rbp+57h+var_80]
0x18008ad39  mov     edx, 30h ; '0'
0x18008ad3e  lea     rcx, ?RuntimeClass_Windows_Media_SpeechRecognition_SpeechRecognizer@@3QBGB; "Windows.Media.SpeechRecognition.SpeechR"...
0x18008ad45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ad4a  test    eax, eax
0x18008ad4c  jns     short loc_18008ADB9
0x18008ad4e  movups  xmm0, xmmword ptr [rbp+57h+var_68]
0x18008ad52  movups  xmmword ptr [r14], xmm0
0x18008ad56  movups  xmm1, [rbp+57h+var_58]
0x18008ad5a  movups  xmmword ptr [r14+10h], xmm1
0x18008ad5f  mov     qword ptr [rbp+57h+var_58], r12
0x18008ad63  mov     qword ptr [rbp+57h+var_58+8], 7
0x18008ad6b  mov     word ptr [rbp+57h+var_68], r12w
0x18008ad70  mov     [rbp+57h+var_B0], r13
0x18008ad74  cmp     [rbp+57h+hModule], r12
0x18008ad78  jz      short loc_18008AD8F
0x18008ad7a  lea     rcx, [rbp+57h+var_B0]
0x18008ad7e  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18008ad83  test    al, al
0x18008ad85  jz      loc_18008B13E
0x18008ad8b  mov     [rbp+57h+hModule], r12
0x18008ad8f  test    ebx, ebx
0x18008ad91  js      short loc_18008AD9A
0x18008ad93  call    cs:__imp_RoUninitialize
0x18008ad99  nop
0x18008ad9a  mov     rcx, [rbp+57h+var_C0]
0x18008ad9e  test    rcx, rcx
0x18008ada1  jz      short loc_18008ADB4
0x18008ada3  mov     [rbp+57h+var_C0], r12
0x18008ada7  mov     rax, [rcx]
0x18008adaa  mov     rax, [rax+10h]
0x18008adae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008adb3  nop
0x18008adb4  jmp     loc_18008B0C3
0x18008adb9  mov     rdi, [rbp+57h+var_90]
0x18008adbd  mov     rcx, [rbp+57h+var_C0]
0x18008adc1  test    rcx, rcx
0x18008adc4  jz      short loc_18008ADD7
0x18008adc6  mov     [rbp+57h+var_C0], r12
0x18008adca  mov     rax, [rcx]
0x18008adcd  mov     rax, [rax+10h]
0x18008add1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008add6  nop
0x18008add7  lea     r8, [rbp+57h+var_C0]
0x18008addb  lea     rdx, _GUID_87a35eac_a7dc_4b0b_bcc9_24f47c0b7ebf
0x18008ade2  mov     rcx, rdi
0x18008ade5  call    cs:__imp_RoGetActivationFactory
0x18008adeb  mov     rdi, [rbp+57h+var_C0]
0x18008adef  test    eax, eax
0x18008adf1  js      loc_18008AFF3
0x18008adf7  test    rdi, rdi
0x18008adfa  jz      loc_18008AFF3
0x18008ae00  mov     rax, [rdi]
0x18008ae03  mov     rsi, [rax+30h]
0x18008ae07  mov     rcx, [rbp+57h+var_B8]
0x18008ae0b  test    rcx, rcx
0x18008ae0e  jz      short loc_18008AE21
0x18008ae10  mov     [rbp+57h+var_B8], r12
0x18008ae14  mov     rdx, [rcx]
0x18008ae17  mov     rax, [rdx+10h]
0x18008ae1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ae20  nop
0x18008ae21  lea     rdx, [rbp+57h+var_B8]
0x18008ae25  mov     rcx, rdi
0x18008ae28  mov     rax, rsi
0x18008ae2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ae30  test    eax, eax
0x18008ae32  js      loc_18008AF88
0x18008ae38  mov     rcx, [rbp+57h+var_B8]
0x18008ae3c  test    rcx, rcx
0x18008ae3f  jz      loc_18008AF88
0x18008ae45  mov     rax, [rcx]
0x18008ae48  lea     rdx, [rbp+57h+var_98]
0x18008ae4c  mov     rax, [rax+30h]
0x18008ae50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ae55  test    eax, eax
0x18008ae57  jns     short loc_18008AEC4
0x18008ae59  movups  xmm0, xmmword ptr [rbp+57h+var_68]
0x18008ae5d  movups  xmmword ptr [r14], xmm0
0x18008ae61  movups  xmm1, [rbp+57h+var_58]
0x18008ae65  movups  xmmword ptr [r14+10h], xmm1
0x18008ae6a  mov     qword ptr [rbp+57h+var_58], r12
0x18008ae6e  mov     qword ptr [rbp+57h+var_58+8], 7
0x18008ae76  mov     word ptr [rbp+57h+var_68], r12w
0x18008ae7b  mov     [rbp+57h+var_B0], r13
0x18008ae7f  cmp     [rbp+57h+hModule], r12
0x18008ae83  jz      short loc_18008AE9A
0x18008ae85  lea     rcx, [rbp+57h+var_B0]
0x18008ae89  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18008ae8e  test    al, al
0x18008ae90  jz      loc_18008B158
0x18008ae96  mov     [rbp+57h+hModule], r12
0x18008ae9a  test    ebx, ebx
0x18008ae9c  js      short loc_18008AEA5
0x18008ae9e  call    cs:__imp_RoUninitialize
0x18008aea4  nop
0x18008aea5  mov     rcx, [rbp+57h+var_C0]
0x18008aea9  test    rcx, rcx
0x18008aeac  jz      short loc_18008AEBF
0x18008aeae  mov     [rbp+57h+var_C0], r12
0x18008aeb2  mov     rax, [rcx]
0x18008aeb5  mov     rax, [rax+10h]
0x18008aeb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008aebe  nop
0x18008aebf  jmp     loc_18008B0C3
0x18008aec4  xor     edx, edx
0x18008aec6  mov     rcx, [rbp+57h+var_98]
0x18008aeca  mov     rax, r15
0x18008aecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008aed2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008aed6  inc     rdx
0x18008aed9  cmp     [rax+rdx*2], r12w
0x18008aede  jnz     short loc_18008AED6
0x18008aee0  cmp     rdx, qword ptr [rbp+57h+var_58+8]
0x18008aee4  ja      short loc_18008AF11
0x18008aee6  lea     rsi, [rbp+57h+var_68]
0x18008aeea  cmp     qword ptr [rbp+57h+var_58+8], 7
0x18008aeef  cmova   rsi, [rbp+57h+var_68]
0x18008aef4  mov     qword ptr [rbp+57h+var_58], rdx
0x18008aef8  lea     rdi, [rdx+rdx]
0x18008aefc  mov     r8, rdi; Size
0x18008aeff  mov     rdx, rax; Src
0x18008af02  mov     rcx, rsi; void *
0x18008af05  call    memmove_0
0x18008af0a  mov     [rsi+rdi], r12w
0x18008af0f  jmp     short loc_18008AF1D
0x18008af11  mov     r9, rax
0x18008af14  lea     rcx, [rbp+57h+var_68]
0x18008af18  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18008af1d  movups  xmm0, xmmword ptr [rbp+57h+var_68]
0x18008af21  movups  xmmword ptr [r14], xmm0
0x18008af25  movups  xmm1, [rbp+57h+var_58]
0x18008af29  movups  xmmword ptr [r14+10h], xmm1
0x18008af2e  mov     qword ptr [rbp+57h+var_58], r12
0x18008af32  mov     qword ptr [rbp+57h+var_58+8], 7
0x18008af3a  mov     word ptr [rbp+57h+var_68], r12w
0x18008af3f  mov     [rbp+57h+var_B0], r13
0x18008af43  cmp     [rbp+57h+hModule], r12
0x18008af47  jz      short loc_18008AF5E
0x18008af49  lea     rcx, [rbp+57h+var_B0]
0x18008af4d  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18008af52  test    al, al
0x18008af54  jz      loc_18008B172
0x18008af5a  mov     [rbp+57h+hModule], r12
0x18008af5e  test    ebx, ebx
0x18008af60  js      short loc_18008AF69
0x18008af62  call    cs:__imp_RoUninitialize
0x18008af68  nop
0x18008af69  mov     rcx, [rbp+57h+var_C0]
0x18008af6d  test    rcx, rcx
0x18008af70  jz      short loc_18008AF83
0x18008af72  mov     [rbp+57h+var_C0], r12
0x18008af76  mov     rax, [rcx]
0x18008af79  mov     rax, [rax+10h]
0x18008af7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008af82  nop
0x18008af83  jmp     loc_18008B0C3
0x18008af88  movups  xmm0, xmmword ptr [rbp+57h+var_68]
0x18008af8c  movups  xmmword ptr [r14], xmm0
0x18008af90  movups  xmm1, [rbp+57h+var_58]
0x18008af94  movups  xmmword ptr [r14+10h], xmm1
0x18008af99  mov     qword ptr [rbp+57h+var_58], r12
0x18008af9d  mov     qword ptr [rbp+57h+var_58+8], 7
0x18008afa5  mov     word ptr [rbp+57h+var_68], r12w
0x18008afaa  mov     [rbp+57h+var_B0], r13
0x18008afae  cmp     [rbp+57h+hModule], r12
0x18008afb2  jz      short loc_18008AFC9
0x18008afb4  lea     rcx, [rbp+57h+var_B0]
0x18008afb8  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18008afbd  test    al, al
0x18008afbf  jz      loc_18008B18C
0x18008afc5  mov     [rbp+57h+hModule], r12
0x18008afc9  test    ebx, ebx
0x18008afcb  js      short loc_18008AFD4
0x18008afcd  call    cs:__imp_RoUninitialize
0x18008afd3  nop
0x18008afd4  mov     rcx, [rbp+57h+var_C0]
0x18008afd8  test    rcx, rcx
  ... truncated ...
```
