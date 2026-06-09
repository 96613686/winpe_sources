# CUserNLSInfo::CollectKeyboardInputLanguage(void)

- ea: `0x18008a370`
- end: `0x18008ab51`
- name: `?CollectKeyboardInputLanguage@CUserNLSInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `2017`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800088e0`
- `0x180008dc0`
- `0x180009260`
- `0x18000929c`
- `0x180009f08`
- `0x180014f2c`
- `0x1800157b8`
- `0x180016748`
- `0x180016db0`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18002b3e4`
- `0x18002b470`
- `0x180084978`
- `0x18008a370`
- `0x1800cd1fc`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008a4c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008a4e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008a4c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008a4e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a514`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a529`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a543`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a514`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a529`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aab5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aacf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aab5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aacf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab37`

## string_xrefs

- `0x18008a4df`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x18008a4bc`: `Bcp47Langs.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall CUserNLSInfo::CollectKeyboardInputLanguage(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rsi
  int v3; // r13d
  _QWORD *v4; // rbx
  HMODULE Library; // rax
  HMODULE v6; // rcx
  FARPROC ProcAddress; // rbx
  FARPROC v8; // rdi
  FARPROC v9; // rax
  __int64 (__fastcall *v10)(_QWORD, _QWORD); // r12
  _WORD *v11; // rax
  __int64 v12; // r8
  unsigned __int64 v13; // rdx
  void **v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // r8
  unsigned __int64 v17; // rdx
  void **v18; // rcx
  __int128 *p_Src; // rcx
  int (__fastcall *v20)(__int128 *, __int64, __int64 *); // rsi
  void **v21; // rdi
  char *v22; // rbx
  __int64 trivial_2; // rax
  unsigned __int64 v24; // r15
  unsigned __int64 v25; // r8
  void **v26; // rdx
  __int128 *v27; // rcx
  _WORD *v28; // rax
  __int64 v29; // r8
  unsigned __int64 v30; // rdx
  void **v31; // rdi
  __int64 v32; // rbx
  unsigned __int64 v33; // rdx
  void **v34; // rcx
  unsigned __int64 v35; // rbx
  __int128 *v36; // rcx
  signed int v38; // eax
  int v39; // edx
  unsigned int v40; // r8d
  signed int v41; // eax
  int v42; // edx
  unsigned int v43; // r8d
  signed int v44; // eax
  int v45; // edx
  unsigned int v46; // r8d
  signed int v47; // eax
  int v48; // edx
  unsigned int v49; // r8d
  signed int v50; // eax
  int v51; // edx
  unsigned int v52; // r8d
  signed int v53; // eax
  int v54; // edx
  unsigned int v55; // r8d
  signed int v56; // eax
  int v57; // edx
  unsigned int v58; // r8d
  signed int v59; // eax
  int v60; // edx
  unsigned int v61; // r8d
  signed int v62; // eax
  int v63; // edx
  unsigned int v64; // r8d
  signed int LastError; // eax
  int v66; // edx
  unsigned int v67; // r8d
  const int *v68; // [rsp+20h] [rbp-E0h] BYREF
  HMODULE hModule; // [rsp+28h] [rbp-D8h]
  const int *v70; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE v71; // [rsp+38h] [rbp-C8h]
  int v72; // [rsp+40h] [rbp-C0h]
  FARPROC v73; // [rsp+48h] [rbp-B8h]
  __int64 v74; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v75; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v76; // [rsp+60h] [rbp-A0h]
  _QWORD *v77; // [rsp+68h] [rbp-98h]
  __int128 Src; // [rsp+70h] [rbp-90h] BYREF
  __int128 v79; // [rsp+80h] [rbp-80h]
  void *v80[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v81; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v82; // [rsp+A8h] [rbp-58h]
  void *v83[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v84; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v85; // [rsp+C8h] [rbp-38h]
  __int128 v86; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v87; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v88; // [rsp+E8h] [rbp-18h]
  __int128 v89; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v90; // [rsp+100h] [rbp+0h]
  __int64 v91; // [rsp+108h] [rbp+8h]

  v2 = a2;
  v76 = a2;
  v77 = a2;
  v3 = 0;
  v72 = 0;
  if ( !SystemRequirements::IsWindowsCore() )
  {
    Src = 0;
    v79 = 0u;
    std::wstring::_Construct<1,unsigned short const *>((char **)&Src, L"#", 1u);
    v74 = 0;
    v75 = 0;
    v86 = 0;
    v87 = 0;
    v88 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v86, L"#", 1u);
    *(_OWORD *)v80 = 0;
    v81 = 0;
    v82 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)v80, L"#", 1u);
    *(_OWORD *)v83 = 0;
    v84 = 0;
    v85 = 7;
    LOWORD(v83[0]) = 0;
    v68 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    hModule = LoadLibraryExW(L"Bcp47Langs.dll", 0, 0x800u);
    Library = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
    v70 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    v71 = Library;
    v6 = hModule;
    if ( !hModule || !Library )
    {
      *(_OWORD *)v2 = Src;
      *((_OWORD *)v2 + 1) = v79;
      *(_QWORD *)&v79 = 0;
      *((_QWORD *)&v79 + 1) = 7;
      LOWORD(Src) = 0;
      v70 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( Library )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v70) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v66, v67);
          JUMPOUT(0x18008AB50LL);
        }
        v71 = 0;
        v6 = hModule;
      }
      v68 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( !v6 )
        goto LABEL_89;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v68) )
      {
        v38 = GetLastError();
        if ( v38 > 0 )
          v38 = (unsigned __int16)v38 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v38, v39, v40);
        __debugbreak();
      }
      goto LABEL_88;
    }
    ProcAddress = GetProcAddress(hModule, "GetUserLanguages");
    v8 = GetProcAddress(hModule, "GetUserLanguageInputMethods");
    v73 = v8;
    v9 = GetProcAddress(v71, "WindowsGetStringRawBuffer");
    v10 = (__int64 (__fastcall *)(_QWORD, _QWORD))v9;
    if ( !ProcAddress || !v9 || !v8 )
    {
      *(_OWORD *)v2 = Src;
      *((_OWORD *)v2 + 1) = v79;
      *(_QWORD *)&v79 = 0;
      *((_QWORD *)&v79 + 1) = 7;
      LOWORD(Src) = 0;
      v70 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( v71 )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v70) )
          goto LABEL_115;
        v71 = 0;
      }
      v68 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( !hModule )
        goto LABEL_89;
      if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v68) )
      {
LABEL_88:
        hModule = 0;
        goto LABEL_89;
      }
      v47 = GetLastError();
      if ( v47 > 0 )
        v47 = (unsigned __int16)v47 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v47, v48, v49);
      goto LABEL_103;
    }
    if ( ((int (__fastcall *)(__int64, __int64 *))ProcAddress)(59, &v74) < 0 )
    {
      *(_OWORD *)v2 = Src;
      *((_OWORD *)v2 + 1) = v79;
      *(_QWORD *)&v79 = 0;
      *((_QWORD *)&v79 + 1) = 7;
      LOWORD(Src) = 0;
      v70 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( !v71 )
        goto LABEL_12;
      if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v70) )
      {
        v71 = 0;
LABEL_12:
        v68 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
        if ( hModule )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v68) )
          {
            v41 = GetLastError();
            if ( v41 > 0 )
              v41 = (unsigned __int16)v41 | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v41, v42, v43);
            __debugbreak();
          }
          goto LABEL_88;
        }
LABEL_89:
        std::wstring::~wstring((char **)v83);
        std::wstring::~wstring((char **)v80);
        std::wstring::~wstring((char **)&v86);
        std::wstring::~wstring((char **)&Src);
        return v2;
      }
LABEL_103:
      v50 = GetLastError();
      if ( v50 > 0 )
        v50 = (unsigned __int16)v50 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v50, v51, v52);
      __debugbreak();
    }
    v11 = (_WORD *)v10(v74, 0);
    v13 = -1;
    do
      ++v13;
    while ( v11[v13] );
    if ( v13 > v82 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v80,
        v13,
        v12,
        v11);
    }
    else
    {
      v14 = v80;
      if ( v82 > 7 )
        v14 = (void **)v80[0];
      v81 = v13;
      v15 = 2 * v13;
      memmove_0(v14, v11, 2 * v13);
      *(_WORD *)((char *)v14 + v15) = 0;
    }
    v17 = v81;
    if ( !v81 )
    {
      *(_OWORD *)v2 = Src;
      *((_OWORD *)v2 + 1) = v79;
      *(_QWORD *)&v79 = 0;
      *((_QWORD *)&v79 + 1) = 7;
      LOWORD(Src) = 0;
      v70 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( v71 )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v70) )
        {
          v53 = GetLastError();
          if ( v53 > 0 )
            v53 = (unsigned __int16)v53 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v53, v54, v55);
          __debugbreak();
        }
        v71 = 0;
      }
      v68 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( !hModule )
        goto LABEL_89;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v68) )
      {
        v44 = GetLastError();
        if ( v44 > 0 )
          v44 = (unsigned __int16)v44 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v44, v45, v46);
        __debugbreak();
      }
      goto LABEL_88;
    }
    v18 = v80;
    if ( v81 >= v82 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v80);
    }
    else
    {
      ++v81;
      if ( v82 > 7 )
        v18 = (void **)v80[0];
      *(_DWORD *)((char *)v18 + 2 * v17) = 59;
    }
    p_Src = &Src;
    if ( *((_QWORD *)&v79 + 1) > 7u )
      p_Src = (__int128 *)Src;
    *(_QWORD *)&v79 = 0;
    *(_WORD *)p_Src = 0;
    v20 = (int (__fastcall *)(__int128 *, __int64, __int64 *))v73;
    while ( 1 )
    {
      v21 = v80;
      if ( v82 > 7 )
        v21 = (void **)v80[0];
      if ( !v81
        || (v22 = (char *)v21 + 2 * v81, trivial_2 = _std_find_trivial_2(v21, v22, 59), (char *)trivial_2 == v22) )
      {
        v24 = -1;
      }
      else
      {
        v24 = (trivial_2 - (__int64)v21) >> 1;
      }
      if ( v24 == -1 )
        break;
      v89 = 0;
      v90 = 0;
      v91 = 0;
      v25 = v81;
      if ( v81 >= v24 )
        v25 = v24;
      v26 = v80;
      if ( v82 > 7 )
        v26 = (void **)v80[0];
      std::wstring::_Construct<1,unsigned short const *>((char **)&v89, v26, v25);
      v3 |= 4u;
      std::wstring::operator=(&v86, &v89);
      std::wstring::~wstring((char **)&v89);
      v27 = &v86;
      if ( v88 > 7 )
        v27 = (__int128 *)v86;
      if ( v20(v27, 59, &v75) >= 0 )
      {
        v28 = (_WORD *)v10(v75, 0);
        v30 = -1;
        do
          ++v30;
        while ( v28[v30] );
        if ( v30 > v85 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            (char **)v83,
            v30,
            v29,
            v28);
        }
        else
        {
          v31 = v83;
          if ( v85 > 7 )
            v31 = (void **)v83[0];
          v84 = v30;
          v32 = 2 * v30;
          memmove_0(v31, v28, 2 * v30);
          *(_WORD *)((char *)v31 + v32) = 0;
        }
        if ( v84 )
        {
          std::wstring::append(&Src);
          std::wstring::append(&Src, L";");
        }
      }
      v33 = v81;
      if ( v81 >= v24 + 1 )
        v33 = v24 + 1;
      v34 = v80;
      if ( v82 > 7 )
        v34 = (void **)v80[0];
      v35 = v81 - v33;
      memmove_0(v34, (char *)v34 + 2 * v33, 2 * (v81 - v33) + 2);
      v81 = v35;
    }
    v2 = v76;
    if ( !(_QWORD)v79 )
    {
      v36 = &Src;
      if ( *((_QWORD *)&v79 + 1) )
      {
        if ( *((_QWORD *)&v79 + 1) > 7u )
          v36 = (__int128 *)Src;
        *(_QWORD *)&v79 = 1;
        *(_WORD *)v36 = asc_1801B4764[0];
        *((_WORD *)v36 + 1) = 0;
      }
      else
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)&Src,
          1u,
          v16,
          L"#");
      }
    }
    *(_OWORD *)v2 = Src;
    *((_OWORD *)v2 + 1) = v79;
    *(_QWORD *)&v79 = 0;
    *((_QWORD *)&v79 + 1) = 7;
    LOWORD(Src) = 0;
    v70 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v71 )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v70) )
      {
        v56 = GetLastError();
        if ( v56 > 0 )
          v56 = (unsigned __int16)v56 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v56, v57, v58);
LABEL_112:
        v59 = GetLastError();
        if ( v59 > 0 )
          v59 = (unsigned __int16)v59 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v59, v60, v61);
LABEL_115:
        v62 = GetLastError();
        if ( v62 > 0 )
          v62 = (unsigned __int16)v62 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v62, v63, v64);
        __debugbreak();
      }
      v71 = 0;
    }
    v68 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( !hModule )
      goto LABEL_89;
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v68) )
    {
      hModule = 0;
      goto LABEL_89;
    }
    goto LABEL_112;
  }
  *(_OWORD *)v2 = 0;
  v2[2] = 0;
  v2[3] = 7;
  *(_WORD *)v2 = 0;
  v72 = 2;
  v4 = operator new(8u);
  v76 = v4;
  *v4 = &KeyboardHelper::`vftable';
  v73 = (FARPROC)v4;
  ((void (__fastcall *)(_QWORD *, _QWORD *))KeyboardHelper::`vftable')(v4, v2);
  *v4 = &KeyboardHelper::`vftable';
  operator delete(v4);
  return v2;
}

```

## disassembly

```asm
0x18008a370  push    rbp
0x18008a372  push    rbx
0x18008a373  push    rsi
0x18008a374  push    rdi
0x18008a375  push    r12
0x18008a377  push    r13
0x18008a379  push    r14
0x18008a37b  push    r15
0x18008a37d  lea     rbp, [rsp-28h]
0x18008a382  sub     rsp, 128h
0x18008a389  mov     rax, cs:__security_cookie
0x18008a390  xor     rax, rsp
0x18008a393  mov     [rbp+60h+var_50], rax
0x18008a397  mov     rsi, rdx
0x18008a39a  mov     [rsp+160h+var_100], rdx
0x18008a39f  mov     [rsp+160h+var_F8], rdx
0x18008a3a4  xor     r15d, r15d
0x18008a3a7  mov     r13d, r15d
0x18008a3aa  mov     [rsp+160h+var_120], r15d
0x18008a3af  call    ?IsWindowsCore@SystemRequirements@@SA_NXZ; SystemRequirements::IsWindowsCore(void)
0x18008a3b4  test    al, al
0x18008a3b6  jz      short loc_18008A425
0x18008a3b8  xorps   xmm0, xmm0
0x18008a3bb  movups  xmmword ptr [rsi], xmm0
0x18008a3be  mov     [rsi+10h], r15
0x18008a3c2  lea     r14d, [r15+7]
0x18008a3c6  mov     [rsi+18h], r14
0x18008a3ca  mov     [rsi], r15w
0x18008a3ce  mov     [rsp+160h+var_120], 2
0x18008a3d6  mov     [rsp+160h+var_118], r15
0x18008a3db  lea     r14d, [r15+8]
0x18008a3df  mov     ecx, r14d; Size
0x18008a3e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008a3e7  mov     rbx, rax
0x18008a3ea  mov     [rsp+160h+var_100], rax
0x18008a3ef  lea     rdi, ??_7KeyboardHelper@@6B@; const KeyboardHelper::`vftable'
0x18008a3f6  mov     [rax], rdi
0x18008a3f9  mov     [rsp+160h+var_118], rax
0x18008a3fe  mov     rdx, rsi
0x18008a401  mov     rcx, rax
0x18008a404  mov     rax, cs:??_7KeyboardHelper@@6B@; const KeyboardHelper::`vftable'
0x18008a40b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a410  nop
0x18008a411  mov     [rbx], rdi
0x18008a414  mov     edx, r14d
0x18008a417  mov     rcx, rbx; Block
0x18008a41a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008a41f  nop
0x18008a420  jmp     loc_18008AA29
0x18008a425  xorps   xmm0, xmm0
0x18008a428  movups  [rsp+160h+Src], xmm0
0x18008a42d  mov     qword ptr [rbp+60h+var_E0], r15
0x18008a431  mov     qword ptr [rbp+60h+var_E0+8], r15
0x18008a435  mov     ebx, 1
0x18008a43a  mov     r8d, ebx
0x18008a43d  lea     rdi, asc_1801B4764; "#"
0x18008a444  mov     rdx, rdi
0x18008a447  lea     rcx, [rsp+160h+Src]
0x18008a44c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008a451  nop
0x18008a452  mov     [rsp+160h+var_110], r15
0x18008a457  mov     [rsp+160h+var_108], r15
0x18008a45c  xorps   xmm0, xmm0
0x18008a45f  movups  [rbp+60h+var_90], xmm0
0x18008a463  mov     [rbp+60h+var_80], r15
0x18008a467  mov     [rbp+60h+var_78], r15
0x18008a46b  mov     r8d, ebx
0x18008a46e  mov     rdx, rdi
0x18008a471  lea     rcx, [rbp+60h+var_90]
0x18008a475  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008a47a  nop
0x18008a47b  xorps   xmm0, xmm0
0x18008a47e  movups  xmmword ptr [rbp+60h+var_D0], xmm0
0x18008a482  mov     [rbp+60h+var_C0], r15
0x18008a486  mov     [rbp+60h+var_B8], r15
0x18008a48a  mov     r8d, ebx
0x18008a48d  mov     rdx, rdi
0x18008a490  lea     rcx, [rbp+60h+var_D0]
0x18008a494  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008a499  nop
0x18008a49a  xorps   xmm0, xmm0
0x18008a49d  movups  xmmword ptr [rbp+60h+var_B0], xmm0
0x18008a4a1  mov     [rbp+60h+var_A0], r15
0x18008a4a5  lea     r14d, [rbx+6]
0x18008a4a9  mov     [rbp+60h+var_98], r14
0x18008a4ad  mov     word ptr [rbp+60h+var_B0], r15w
0x18008a4b2  mov     ebx, 800h
0x18008a4b7  mov     r8d, ebx; dwFlags
0x18008a4ba  xor     edx, edx; hFile
0x18008a4bc  lea     rcx, aBcp47langsDll; "Bcp47Langs.dll"
0x18008a4c3  call    cs:__imp_LoadLibraryExW
0x18008a4c9  lea     rdi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18008a4d0  mov     [rsp+160h+var_140], rdi
0x18008a4d5  mov     [rsp+160h+hModule], rax
0x18008a4da  mov     r8d, ebx; dwFlags
0x18008a4dd  xor     edx, edx; hFile
0x18008a4df  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x18008a4e6  call    cs:__imp_LoadLibraryExW
0x18008a4ec  mov     [rsp+160h+var_130], rdi
0x18008a4f1  mov     [rsp+160h+var_128], rax
0x18008a4f6  mov     rcx, [rsp+160h+hModule]; hModule
0x18008a4fb  test    rcx, rcx
0x18008a4fe  jz      loc_18008A9A0
0x18008a504  test    rax, rax
0x18008a507  jz      loc_18008A9A0
0x18008a50d  lea     rdx, aGetuserlanguag; "GetUserLanguages"
0x18008a514  call    cs:__imp_GetProcAddress
0x18008a51a  mov     rbx, rax
0x18008a51d  lea     rdx, aGetuserlanguag_0; "GetUserLanguageInputMethods"
0x18008a524  mov     rcx, [rsp+160h+hModule]; hModule
0x18008a529  call    cs:__imp_GetProcAddress
0x18008a52f  mov     rdi, rax
0x18008a532  mov     [rsp+160h+var_118], rax
0x18008a537  lea     rdx, aWindowsgetstri; "WindowsGetStringRawBuffer"
0x18008a53e  mov     rcx, [rsp+160h+var_128]; hModule
0x18008a543  call    cs:__imp_GetProcAddress
0x18008a549  mov     r12, rax
0x18008a54c  test    rbx, rbx
0x18008a54f  jz      loc_18008A938
0x18008a555  test    rax, rax
0x18008a558  jz      loc_18008A938
0x18008a55e  test    rdi, rdi
0x18008a561  jz      loc_18008A938
0x18008a567  lea     edi, [r14+34h]
0x18008a56b  mov     ecx, edi
0x18008a56d  lea     rdx, [rsp+160h+var_110]
0x18008a572  mov     rax, rbx
0x18008a575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a57a  test    eax, eax
0x18008a57c  jns     short loc_18008A5ED
0x18008a57e  movups  xmm0, [rsp+160h+Src]
0x18008a583  movups  xmmword ptr [rsi], xmm0
0x18008a586  movups  xmm1, [rbp+60h+var_E0]
0x18008a58a  movups  xmmword ptr [rsi+10h], xmm1
0x18008a58e  mov     qword ptr [rbp+60h+var_E0], r15
0x18008a592  mov     qword ptr [rbp+60h+var_E0+8], r14
0x18008a596  mov     word ptr [rsp+160h+Src], r15w
0x18008a59c  lea     rdi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18008a5a3  mov     [rsp+160h+var_130], rdi
0x18008a5a8  cmp     [rsp+160h+var_128], r15
0x18008a5ad  jz      short loc_18008A5C6
0x18008a5af  lea     rcx, [rsp+160h+var_130]
0x18008a5b4  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18008a5b9  test    al, al
0x18008a5bb  jz      loc_18008AAB5
0x18008a5c1  mov     [rsp+160h+var_128], r15
0x18008a5c6  mov     [rsp+160h+var_140], rdi
0x18008a5cb  cmp     [rsp+160h+hModule], r15
0x18008a5d0  jz      loc_18008AA01
0x18008a5d6  lea     rcx, [rsp+160h+var_140]
0x18008a5db  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18008a5e0  test    al, al
0x18008a5e2  jz      loc_18008AA67
0x18008a5e8  jmp     loc_18008A9FC
0x18008a5ed  xor     edx, edx
0x18008a5ef  mov     rcx, [rsp+160h+var_110]
0x18008a5f4  mov     rax, r12
0x18008a5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a5fc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008a600  inc     rdx
0x18008a603  cmp     [rax+rdx*2], r15w
0x18008a608  jnz     short loc_18008A600
0x18008a60a  cmp     rdx, [rbp+60h+var_B8]
0x18008a60e  ja      short loc_18008A63F
0x18008a610  lea     rdi, [rbp+60h+var_D0]
0x18008a614  cmp     [rbp+60h+var_B8], r14
0x18008a618  cmova   rdi, [rbp+60h+var_D0]
0x18008a61d  mov     [rbp+60h+var_C0], rdx
0x18008a621  lea     rbx, [rdx+rdx]
0x18008a625  mov     r8, rbx; Size
0x18008a628  mov     rdx, rax; Src
0x18008a62b  mov     rcx, rdi; void *
0x18008a62e  call    memmove_0
0x18008a633  mov     [rdi+rbx], r15w
0x18008a638  mov     edi, 3Bh ; ';'
0x18008a63d  jmp     short loc_18008A64B
0x18008a63f  mov     r9, rax
0x18008a642  lea     rcx, [rbp+60h+var_D0]
0x18008a646  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18008a64b  mov     rdx, [rbp+60h+var_C0]
0x18008a64f  test    rdx, rdx
0x18008a652  jnz     short loc_18008A6C3
0x18008a654  movups  xmm0, [rsp+160h+Src]
0x18008a659  movups  xmmword ptr [rsi], xmm0
0x18008a65c  movups  xmm1, [rbp+60h+var_E0]
0x18008a660  movups  xmmword ptr [rsi+10h], xmm1
0x18008a664  mov     qword ptr [rbp+60h+var_E0], r15
0x18008a668  mov     qword ptr [rbp+60h+var_E0+8], r14
0x18008a66c  mov     word ptr [rsp+160h+Src], r15w
0x18008a672  lea     rdi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18008a679  mov     [rsp+160h+var_130], rdi
0x18008a67e  cmp     [rsp+160h+var_128], r15
0x18008a683  jz      short loc_18008A69C
0x18008a685  lea     rcx, [rsp+160h+var_130]
0x18008a68a  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18008a68f  test    al, al
0x18008a691  jz      loc_18008AACF
0x18008a697  mov     [rsp+160h+var_128], r15
0x18008a69c  mov     [rsp+160h+var_140], rdi
0x18008a6a1  cmp     [rsp+160h+hModule], r15
0x18008a6a6  jz      loc_18008AA01
0x18008a6ac  lea     rcx, [rsp+160h+var_140]
0x18008a6b1  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18008a6b6  test    al, al
0x18008a6b8  jz      loc_18008AA81
0x18008a6be  jmp     loc_18008A9FC
0x18008a6c3  lea     rcx, [rbp+60h+var_D0]; Src
0x18008a6c7  cmp     rdx, [rbp+60h+var_B8]
0x18008a6cb  jnb     short loc_18008A6E7
0x18008a6cd  lea     rax, [rdx+1]
0x18008a6d1  mov     [rbp+60h+var_C0], rax
0x18008a6d5  cmp     [rbp+60h+var_B8], r14
0x18008a6d9  cmova   rcx, [rbp+60h+var_D0]
0x18008a6de  mov     dword ptr [rcx+rdx*2], 3Bh ; ';'
0x18008a6e5  jmp     short loc_18008A6EF
0x18008a6e7  mov     r9d, edi
0x18008a6ea  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18008a6ef  lea     rcx, [rsp+160h+Src]
0x18008a6f4  cmp     qword ptr [rbp+60h+var_E0+8], r14
0x18008a6f8  cmova   rcx, qword ptr [rsp+160h+Src]
0x18008a6fe  mov     qword ptr [rbp+60h+var_E0], r15
0x18008a702  mov     [rcx], r15w
0x18008a706  mov     rsi, [rsp+160h+var_118]
0x18008a70b  mov     rax, [rbp+60h+var_C0]
0x18008a70f  lea     rdi, [rbp+60h+var_D0]
0x18008a713  cmp     [rbp+60h+var_B8], r14
0x18008a717  cmova   rdi, [rbp+60h+var_D0]
0x18008a71c  test    rax, rax
0x18008a71f  jz      short loc_18008A746
0x18008a721  lea     rbx, [rdi+rax*2]
0x18008a725  mov     r8d, 3Bh ; ';'
0x18008a72b  mov     rdx, rbx
0x18008a72e  mov     rcx, rdi
0x18008a731  call    __std_find_trivial_2
0x18008a736  mov     r15, rax
0x18008a739  cmp     rax, rbx
0x18008a73c  jz      short loc_18008A746
0x18008a73e  sub     r15, rdi
0x18008a741  sar     r15, 1
0x18008a744  jmp     short loc_18008A74A
0x18008a746  or      r15, 0FFFFFFFFFFFFFFFFh
0x18008a74a  xor     ebx, ebx
0x18008a74c  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18008a750  jz      loc_18008A881
0x18008a756  xorps   xmm0, xmm0
0x18008a759  movups  [rbp+60h+var_70], xmm0
0x18008a75d  mov     [rbp+60h+var_60], rbx
0x18008a761  mov     [rbp+60h+var_58], rbx
0x18008a765  mov     r8, [rbp+60h+var_C0]
0x18008a769  cmp     r8, r15
0x18008a76c  cmovnb  r8, r15
0x18008a770  lea     rdx, [rbp+60h+var_D0]
0x18008a774  cmp     [rbp+60h+var_B8], r14
0x18008a778  cmova   rdx, [rbp+60h+var_D0]
0x18008a77d  lea     rcx, [rbp+60h+var_70]
0x18008a781  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008a786  or      r13d, 4
0x18008a78a  lea     rdx, [rbp+60h+var_70]
0x18008a78e  lea     rcx, [rbp+60h+var_90]
0x18008a792  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008a797  lea     rcx, [rbp+60h+var_70]
0x18008a79b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008a7a0  lea     rcx, [rbp+60h+var_90]
0x18008a7a4  cmp     [rbp+60h+var_78], r14
0x18008a7a8  cmova   rcx, qword ptr [rbp+60h+var_90]
0x18008a7ad  lea     edx, [rbx+3Bh]
0x18008a7b0  lea     r8, [rsp+160h+var_108]
0x18008a7b5  mov     rax, rsi
0x18008a7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a7bd  test    eax, eax
0x18008a7bf  js      loc_18008A845
0x18008a7c5  xor     edx, edx
0x18008a7c7  mov     rcx, [rsp+160h+var_108]
0x18008a7cc  mov     rax, r12
0x18008a7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a7d4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008a7d8  inc     rdx
0x18008a7db  cmp     [rax+rdx*2], bx
0x18008a7df  jnz     short loc_18008A7D8
0x18008a7e1  cmp     rdx, [rbp+60h+var_98]
0x18008a7e5  ja      short loc_18008A814
0x18008a7e7  lea     rdi, [rbp+60h+var_B0]
0x18008a7eb  cmp     [rbp+60h+var_98], r14
0x18008a7ef  cmova   rdi, [rbp+60h+var_B0]
0x18008a7f4  mov     [rbp+60h+var_A0], rdx
0x18008a7f8  lea     rbx, [rdx+rdx]
0x18008a7fc  mov     r8, rbx; Size
0x18008a7ff  mov     rdx, rax; Src
0x18008a802  mov     rcx, rdi; void *
0x18008a805  call    memmove_0
0x18008a80a  xor     eax, eax
0x18008a80c  mov     [rdi+rbx], ax
0x18008a810  xor     ebx, ebx
0x18008a812  jmp     short loc_18008A820
0x18008a814  mov     r9, rax
0x18008a817  lea     rcx, [rbp+60h+var_B0]
0x18008a81b  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18008a820  cmp     [rbp+60h+var_A0], rbx
0x18008a824  jz      short loc_18008A845
0x18008a826  lea     rdx, [rbp+60h+var_B0]
  ... truncated ...
```
