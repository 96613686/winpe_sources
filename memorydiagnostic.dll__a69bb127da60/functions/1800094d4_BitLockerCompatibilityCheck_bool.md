# BitLockerCompatibilityCheck(bool &)

- ea: `0x1800094d4`
- end: `0x180009e8b`
- name: `?BitLockerCompatibilityCheck@@YAJAEA_N@Z`
- size: `2487`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a6d4`

## callees

- `0x180001008`
- `0x180002e50`
- `0x180003e0c`
- `0x180005ef0`
- `0x180005fa4`
- `0x180007818`
- `0x1800094d4`
- `0x18000dcdc`
- `0x18000e310`
- `0x18000e7ec`
- `0x1800109b4`
- `0x1800109d4`
- `0x1800158a0`
- `0x180023010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180009567`
- `KERNEL32!FreeLibrary` at `0x1800095e7`
- `KERNEL32!FreeLibrary` at `0x180009667`
- `KERNEL32!FreeLibrary` at `0x180009710`
- `KERNEL32!FreeLibrary` at `0x1800098e5`
- `KERNEL32!FreeLibrary` at `0x1800099b6`
- `KERNEL32!FreeLibrary` at `0x180009a7e`
- `KERNEL32!FreeLibrary` at `0x180009b6c`
- `KERNEL32!FreeLibrary` at `0x180009c34`
- `KERNEL32!FreeLibrary` at `0x180009d3c`
- `KERNEL32!FreeLibrary` at `0x180009db0`
- `KERNEL32!FreeLibrary` at `0x180009567`
- `KERNEL32!FreeLibrary` at `0x1800095e7`
- `KERNEL32!FreeLibrary` at `0x180009667`
- `KERNEL32!FreeLibrary` at `0x180009710`
- `KERNEL32!FreeLibrary` at `0x1800098e5`
- `KERNEL32!FreeLibrary` at `0x1800099b6`
- `KERNEL32!FreeLibrary` at `0x180009a7e`
- `KERNEL32!FreeLibrary` at `0x180009b6c`
- `KERNEL32!FreeLibrary` at `0x180009c34`
- `KERNEL32!FreeLibrary` at `0x180009d3c`
- `KERNEL32!FreeLibrary` at `0x180009db0`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800096d2`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800097ec`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800096d2`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800097ec`
- `KERNEL32!GetProcAddress` at `0x18000953a`
- `KERNEL32!GetProcAddress` at `0x1800095b8`
- `KERNEL32!GetProcAddress` at `0x18000963a`
- `KERNEL32!GetProcAddress` at `0x18000953a`
- `KERNEL32!GetProcAddress` at `0x1800095b8`
- `KERNEL32!GetProcAddress` at `0x18000963a`
- `KERNEL32!LoadLibraryW` at `0x180009519`
- `KERNEL32!LoadLibraryW` at `0x180009519`

## string_xrefs

- `0x180009512`: `fveapi.dll`
- `0x180009e2c`: `BitLockerCompatibilityCheck_FveApiNotFound`
- `0x180009530`: `FveOpenVolumeW`
- `0x180009a29`: `BitLockerCompatibilityCheck_PrimaryVolumeNotProtected`
- `0x180009ade`: `BitLockerCompatibilityCheck_PrimaryVolumeProtected`
- `0x180009bdf`: `BitLockerCompatibilityCheck_SecureBootBound`
- `0x180009ca1`: `BitLockerCompatibilityCheck_SecureBootBindingPossible`
- `0x180009cea`: `BitLockerCompatibilityCheck_SecureBootNotBound`

## pseudocode

```c
__int64 __fastcall BitLockerCompatibilityCheck(bool *a1)
{
  HMODULE LibraryW; // rax
  unsigned int v3; // r8d
  const char *v4; // r9
  HMODULE v5; // rbx
  const char *v6; // r9
  FARPROC ProcAddress; // r12
  unsigned int v8; // r15d
  const char *v9; // rcx
  const char *v10; // r8
  char v11; // di
  const char *v13; // r9
  unsigned int v14; // r15d
  const char *v15; // rcx
  const char *v16; // r8
  char v17; // di
  const char *v18; // r9
  FARPROC v19; // r13
  unsigned int LastError; // r15d
  const char *v21; // rcx
  const char *v22; // r8
  char v23; // di
  UINT SystemWindowsDirectoryW; // eax
  UINT v25; // r15d
  const char *v26; // rcx
  const char *v27; // r8
  char v28; // di
  __int64 v29; // rcx
  unsigned __int64 v30; // rdx
  _WORD *v31; // rdi
  __int64 i; // rcx
  WCHAR *v33; // rcx
  UINT v34; // eax
  __int64 v35; // rdx
  char **v36; // rcx
  int v37; // eax
  unsigned int v38; // r15d
  const char *v39; // rcx
  const char *v40; // r8
  char v41; // di
  int v42; // eax
  unsigned int v43; // r15d
  const char *v44; // rcx
  const char *v45; // r8
  char v46; // di
  const struct _tlgProvider_t *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  unsigned int v51; // ecx
  const char *v52; // rcx
  const char *v53; // r8
  char v54; // di
  int v55; // eax
  unsigned int v56; // r15d
  const char *v57; // rcx
  const char *v58; // r8
  char v59; // di
  const struct _tlgProvider_t *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  const char *v64; // rcx
  const char *v65; // r8
  char v66; // di
  const struct _tlgProvider_t *v67; // rax
  __int64 v68; // r8
  __int64 v69; // r9
  const struct _tlgProvider_t *v70; // rax
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // r9
  const char *v74; // rcx
  const char *v75; // r8
  char v76; // di
  const char *v77; // rcx
  const char *v78; // r8
  char v79; // di
  const struct _tlgProvider_t *v80; // rax
  __int64 v81; // r8
  __int64 v82; // r9
  int v83; // [rsp+20h] [rbp-D8h]
  bool v84; // [rsp+30h] [rbp-C8h] BYREF
  int v85; // [rsp+34h] [rbp-C4h] BYREF
  int v86[2]; // [rsp+38h] [rbp-C0h] BYREF
  void *v87; // [rsp+40h] [rbp-B8h] BYREF
  _QWORD v88[3]; // [rsp+48h] [rbp-B0h] BYREF
  char v89; // [rsp+60h] [rbp-98h]
  LPWSTR lpBuffer[2]; // [rsp+68h] [rbp-90h] BYREF
  UINT uSize[2]; // [rsp+78h] [rbp-80h]
  unsigned __int64 v92; // [rsp+80h] [rbp-78h]
  char *v93[4]; // [rsp+88h] [rbp-70h] BYREF
  __int128 v94; // [rsp+A8h] [rbp-50h] BYREF
  __int128 v95; // [rsp+B8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  *a1 = 0;
  v88[2] = a1;
  v89 = 1;
  LibraryW = LoadLibraryW(L"fveapi.dll");
  v5 = LibraryW;
  v88[1] = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "FveOpenVolumeW");
    if ( ProcAddress )
    {
      v88[0] = GetProcAddress(v5, "FveCloseVolume");
      if ( v88[0] )
      {
        v19 = GetProcAddress(v5, "FveGetSecureBootBindingState");
        if ( v19 )
        {
          *(_OWORD *)lpBuffer = 0;
          *(_QWORD *)uSize = 0;
          v92 = 7;
          LOWORD(lpBuffer[0]) = 0;
          SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
          v25 = SystemWindowsDirectoryW;
          if ( SystemWindowsDirectoryW )
          {
            v29 = *(_QWORD *)uSize;
            if ( (unsigned __int64)SystemWindowsDirectoryW > *(_QWORD *)uSize )
            {
              v30 = SystemWindowsDirectoryW - *(_QWORD *)uSize;
              if ( v30 > v92 - *(_QWORD *)uSize )
              {
                std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpBuffer);
              }
              else
              {
                *(_QWORD *)uSize = SystemWindowsDirectoryW;
                v31 = (_WORD *)lpBuffer + v29;
                if ( v30 )
                {
                  for ( i = SystemWindowsDirectoryW - v29; i; --i )
                    *v31++ = 0;
                }
                *((_WORD *)lpBuffer + SystemWindowsDirectoryW) = 0;
              }
            }
            else
            {
              *(_QWORD *)uSize = SystemWindowsDirectoryW;
              *((_WORD *)lpBuffer + SystemWindowsDirectoryW) = 0;
            }
            v33 = (WCHAR *)lpBuffer;
            if ( v92 > 7 )
              v33 = lpBuffer[0];
            v34 = GetSystemWindowsDirectoryW(v33, uSize[0]);
            if ( v34 && v34 <= v25 )
            {
              v94 = 0;
              v95 = 0;
              std::wstring::_Construct<1,unsigned short const *>(&v94);
              std::operator+<unsigned short>(v93, v35, &v94);
              std::wstring::~wstring((char **)&v94);
              v87 = (void *)-1LL;
              v36 = v93;
              if ( v93[3] > (char *)7 )
                v36 = (char **)v93[0];
              v37 = ((__int64 (__fastcall *)(char **, _QWORD, void **))ProcAddress)(v36, 0, &v87);
              v38 = v37;
              if ( v37 >= 0 )
              {
                *(_QWORD *)&v94 = v88;
                *((_QWORD *)&v94 + 1) = &v87;
                LOBYTE(v95) = 1;
                v84 = 0;
                v42 = IsTpmProtectedVolume(v5, v87, &v84);
                v43 = v42;
                if ( v42 >= 0 )
                {
                  v47 = TlgHelper::Provider();
                  v51 = *(_DWORD *)v47;
                  if ( v84 )
                  {
                    if ( v51 > 4 )
                    {
                      v48 = *((_QWORD *)v47 + 3);
                      if ( (*((_QWORD *)v47 + 2) & 2) != 0 && (*((_QWORD *)v47 + 3) & 2LL) == *((_QWORD *)v47 + 3) )
                      {
                        *(_QWORD *)v86 = L"BitLockerCompatibilityCheck_PrimaryVolumeProtected";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                          (__int64)v47,
                          (__int64)byte_180029A45,
                          v49,
                          v50,
                          (int **)v86);
                      }
                    }
                    v85 = -1;
                    v55 = ((__int64 (__fastcall *)(int *, __int64))v19)(&v85, v48);
                    v56 = v55;
                    if ( v55 >= 0 )
                    {
                      if ( v85 == 3 )
                      {
                        v60 = TlgHelper::Provider();
                        if ( *(_DWORD *)v60 > 4u )
                        {
                          v61 = *((_QWORD *)v60 + 3);
                          if ( (*((_QWORD *)v60 + 2) & 2) != 0 && (*((_QWORD *)v60 + 3) & 2LL) == *((_QWORD *)v60 + 3) )
                          {
                            *(_QWORD *)v86 = L"BitLockerCompatibilityCheck_SecureBootBound";
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                              (__int64)v60,
                              (__int64)&dword_180029C8C,
                              v62,
                              v63,
                              (int **)v86);
                          }
                        }
                        *a1 = 1;
                        ((void (__fastcall *)(void *, __int64))v88[0])(v87, v61);
                        std::wstring::~wstring(v93);
                        std::wstring::~wstring((char **)lpBuffer);
                        FreeLibrary(v5);
                        if ( !*a1 )
                        {
                          _InterlockedExchange(&g_aomdPromptResult, 7);
                          v64 = "AOMDPromptResult::CheckBitLockerFailed";
                          v65 = "AOMDPromptResult::CheckBitLockerFailed";
                          v66 = 65;
                          do
                          {
                            ++v64;
                            if ( v66 == 58 )
                              v65 = v64;
                            v66 = *v64;
                          }
                          while ( *v64 );
                          tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                            v64,
                            7,
                            v65);
                        }
                        return 0;
                      }
                      else
                      {
                        if ( v85 == 2 )
                        {
                          v67 = TlgHelper::Provider();
                          if ( *(_DWORD *)v67 > 3u
                            && (*((_QWORD *)v67 + 2) & 2) != 0
                            && (*((_QWORD *)v67 + 3) & 2LL) == *((_QWORD *)v67 + 3) )
                          {
                            *(_QWORD *)v86 = L"BitLockerCompatibilityCheck_SecureBootBindingPossible";
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                              (__int64)v67,
                              (__int64)&byte_18002A29F,
                              v68,
                              v69,
                              (int **)v86);
                          }
                        }
                        v70 = TlgHelper::Provider();
                        if ( *(_DWORD *)v70 > 3u )
                        {
                          v71 = *((_QWORD *)v70 + 3);
                          if ( (*((_QWORD *)v70 + 2) & 2) != 0 && (*((_QWORD *)v70 + 3) & 2LL) == *((_QWORD *)v70 + 3) )
                          {
                            *(_QWORD *)v86 = L"BitLockerCompatibilityCheck_SecureBootNotBound";
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                              (__int64)v70,
                              (__int64)&dword_18002A1F4,
                              v72,
                              v73,
                              (int **)v86);
                          }
                        }
                        ((void (__fastcall *)(void *, __int64))v88[0])(v87, v71);
                        std::wstring::~wstring(v93);
                        std::wstring::~wstring((char **)lpBuffer);
                        FreeLibrary(v5);
                        if ( !*a1 )
                        {
                          _InterlockedExchange(&g_aomdPromptResult, 7);
                          v74 = "AOMDPromptResult::CheckBitLockerFailed";
                          v75 = "AOMDPromptResult::CheckBitLockerFailed";
                          v76 = 65;
                          do
                          {
                            ++v74;
                            if ( v76 == 58 )
                              v75 = v74;
                            v76 = *v74;
                          }
                          while ( *v74 );
                          tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                            v74,
                            7,
                            v75);
                        }
                        return 0;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x4FA,
                        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                        (const char *)(unsigned int)v55,
                        v83);
                      ((void (__fastcall *)(void *))v88[0])(v87);
                      std::wstring::~wstring(v93);
                      std::wstring::~wstring((char **)lpBuffer);
                      FreeLibrary(v5);
                      if ( !*a1 )
                      {
                        _InterlockedExchange(&g_aomdPromptResult, 7);
                        v57 = "AOMDPromptResult::CheckBitLockerFailed";
                        v58 = "AOMDPromptResult::CheckBitLockerFailed";
                        v59 = 65;
                        do
                        {
                          ++v57;
                          if ( v59 == 58 )
                            v58 = v57;
                          v59 = *v57;
                        }
                        while ( *v57 );
                        tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                          v57,
                          7,
                          v58);
                      }
                      return v56;
                    }
                  }
                  else
                  {
                    if ( v51 > 4 )
                    {
                      v48 = *((_QWORD *)v47 + 3);
                      if ( (*((_QWORD *)v47 + 2) & 2) != 0 && (*((_QWORD *)v47 + 3) & 2LL) == *((_QWORD *)v47 + 3) )
                      {
                        *(_QWORD *)v86 = L"BitLockerCompatibilityCheck_PrimaryVolumeNotProtected";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                          (__int64)v47,
                          (__int64)byte_18002A303,
                          v49,
                          v50,
                          (int **)v86);
                      }
                    }
                    *a1 = 1;
                    ((void (__fastcall *)(void *, __int64))v88[0])(v87, v48);
                    std::wstring::~wstring(v93);
                    std::wstring::~wstring((char **)lpBuffer);
                    FreeLibrary(v5);
                    if ( !*a1 )
                    {
                      _InterlockedExchange(&g_aomdPromptResult, 7);
                      v52 = "AOMDPromptResult::CheckBitLockerFailed";
                      v53 = "AOMDPromptResult::CheckBitLockerFailed";
                      v54 = 65;
                      do
                      {
                        ++v52;
                        if ( v54 == 58 )
                          v53 = v52;
                        v54 = *v52;
                      }
                      while ( *v52 );
                      tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                        v52,
                        7,
                        v53);
                    }
                    return 0;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x4ED,
                    (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                    (const char *)(unsigned int)v42,
                    v83);
                  ((void (__fastcall *)(void *))v88[0])(v87);
                  std::wstring::~wstring(v93);
                  std::wstring::~wstring((char **)lpBuffer);
                  FreeLibrary(v5);
                  if ( !*a1 )
                  {
                    _InterlockedExchange(&g_aomdPromptResult, 7);
                    v44 = "AOMDPromptResult::CheckBitLockerFailed";
                    v45 = "AOMDPromptResult::CheckBitLockerFailed";
                    v46 = 65;
                    do
                    {
                      ++v44;
                      if ( v46 == 58 )
                        v45 = v44;
                      v46 = *v44;
                    }
                    while ( *v44 );
                    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                      v44,
                      7,
                      v45);
                  }
                  return v43;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x4E6,
                  (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                  (const char *)(unsigned int)v37,
                  v83);
                std::wstring::~wstring(v93);
                std::wstring::~wstring((char **)lpBuffer);
                FreeLibrary(v5);
                if ( !*a1 )
                {
                  _InterlockedExchange(&g_aomdPromptResult, 7);
                  v39 = "AOMDPromptResult::CheckBitLockerFailed";
                  v40 = "AOMDPromptResult::CheckBitLockerFailed";
                  v41 = 65;
                  do
                  {
                    ++v39;
                    if ( v41 == 58 )
                      v40 = v39;
                    v41 = *v39;
                  }
                  while ( *v39 );
                  tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                    v39,
                    7,
                    v40);
                }
                return v38;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x4E1,
                (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                (const char *)0x8000FFFFLL,
                v83);
              std::wstring::~wstring((char **)lpBuffer);
              FreeLibrary(v5);
              if ( !*a1 )
              {
                _InterlockedExchange(&g_aomdPromptResult, 7);
                v77 = "AOMDPromptResult::CheckBitLockerFailed";
                v78 = "AOMDPromptResult::CheckBitLockerFailed";
                v79 = 65;
                do
                {
                  ++v77;
                  if ( v79 == 58 )
                    v78 = v77;
                  v79 = *v77;
                }
                while ( *v77 );
                tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                  v77,
                  7,
                  v78);
              }
              return 2147549183LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4DD,
              (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
              (const char *)0x8000FFFFLL,
              v83);
            std::wstring::~wstring((char **)lpBuffer);
            FreeLibrary(v5);
            if ( !*a1 )
            {
              _InterlockedExchange(&g_aomdPromptResult, 7);
              v26 = "AOMDPromptResult::CheckBitLockerFailed";
              v27 = "AOMDPromptResult::CheckBitLockerFailed";
              v28 = 65;
              do
              {
                ++v26;
                if ( v28 == 58 )
                  v27 = v26;
                v28 = *v26;
              }
              while ( *v26 );
              tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                v26,
                7,
                v27);
            }
            return 2147549183LL;
          }
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x4D8,
                        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                        v18);
          FreeLibrary(v5);
          if ( !*a1 )
          {
            _InterlockedExchange(&g_aomdPromptResult, 7);
            v21 = "AOMDPromptResult::CheckBitLockerFailed";
            v22 = "AOMDPromptResult::CheckBitLockerFailed";
            v23 = 65;
            do
            {
              ++v21;
              if ( v23 == 58 )
                v22 = v21;
              v23 = *v21;
            }
            while ( *v21 );
            tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
              v21,
              7,
              v22);
          }
          return LastError;
        }
      }
      else
      {
        v14 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x4D5,
                (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                v13);
        FreeLibrary(v5);
        if ( !*a1 )
        {
          _InterlockedExchange(&g_aomdPromptResult, 7);
          v15 = "AOMDPromptResult::CheckBitLockerFailed";
          v16 = "AOMDPromptResult::CheckBitLockerFailed";
          v17 = 65;
          do
          {
            ++v15;
            if ( v17 == 58 )
              v16 = v15;
            v17 = *v15;
          }
          while ( *v15 );
          tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
            v15,
            7,
            v16);
        }
        return v14;
      }
    }
    else
    {
      v8 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x4D2,
             (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
             v6);
      FreeLibrary(v5);
      if ( !*a1 )
      {
        _InterlockedExchange(&g_aomdPromptResult, 7);
        v9 = "AOMDPromptResult::CheckBitLockerFailed";
        v10 = "AOMDPromptResult::CheckBitLockerFailed";
        v11 = 65;
        do
        {
          ++v9;
          if ( v11 == 58 )
            v10 = v9;
          v11 = *v9;
        }
        while ( *v9 );
        tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
          v9,
          7,
          v10);
      }
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x4C8, v3, v4);
    v80 = TlgHelper::Provider();
    if ( *(_DWORD *)v80 > 4u && (*((_QWORD *)v80 + 2) & 2) != 0 && (*((_QWORD *)v80 + 3) & 2LL) == *((_QWORD *)v80 + 3) )
    {
      *(_QWORD *)v86 = L"BitLockerCompatibilityCheck_FveApiNotFound";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v80,
        (__int64)byte_18002A079,
        v81,
        v82,
        (int **)v86);
    }
    *a1 = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x1800094d4  mov     [rsp+arg_8], rbx
0x1800094d9  mov     [rsp+arg_10], rsi
0x1800094de  push    rdi
0x1800094df  push    r12
0x1800094e1  push    r13
0x1800094e3  push    r14
0x1800094e5  push    r15
0x1800094e7  sub     rsp, 0D0h
0x1800094ee  mov     rax, cs:__security_cookie
0x1800094f5  xor     rax, rsp
0x1800094f8  mov     [rsp+0F8h+var_30], rax
0x180009500  mov     r14, rcx
0x180009503  xor     edi, edi
0x180009505  mov     [rcx], dil
0x180009508  mov     [rsp+0F8h+var_A0], rcx
0x18000950d  mov     [rsp+0F8h+var_98], 1
0x180009512  lea     rcx, LibFileName; "fveapi.dll"
0x180009519  call    cs:__imp_LoadLibraryW
0x18000951f  mov     rbx, rax
0x180009522  mov     [rsp+0F8h+var_A8], rax
0x180009527  test    rax, rax
0x18000952a  jz      loc_180009DF1
0x180009530  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x180009537  mov     rcx, rax; hModule
0x18000953a  call    cs:__imp_GetProcAddress
0x180009540  mov     r12, rax
0x180009543  test    rax, rax
0x180009546  jnz     short loc_1800095AE
0x180009548  mov     rcx, [rsp+0F8h]; this
0x180009550  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x180009557  mov     edx, 4D2h; void *
0x18000955c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009561  mov     r15d, eax
0x180009564  mov     rcx, rbx; hLibModule
0x180009567  call    cs:__imp_FreeLibrary
0x18000956d  nop
0x18000956e  cmp     [r14], dil
0x180009571  jnz     short loc_1800095A6
0x180009573  lea     esi, [rdi+7]
0x180009576  mov     ecx, esi
0x180009578  xchg    ecx, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x18000957e  lea     rcx, aAomdpromptresu_5; "AOMDPromptResult::CheckBitLockerFailed"
0x180009585  mov     r8, rcx
0x180009588  mov     dil, 41h ; 'A'
0x18000958b  inc     rcx
0x18000958e  cmp     dil, 3Ah ; ':'
0x180009592  jnz     short loc_180009597
0x180009594  mov     r8, rcx
0x180009597  mov     dil, [rcx]
0x18000959a  test    dil, dil
0x18000959d  jnz     short loc_18000958B
0x18000959f  mov     edx, esi
0x1800095a1  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x1800095a6  mov     eax, r15d
0x1800095a9  jmp     loc_180009E5D
0x1800095ae  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x1800095b5  mov     rcx, rbx; hModule
0x1800095b8  call    cs:__imp_GetProcAddress
0x1800095be  mov     [rsp+0F8h+var_B0], rax
0x1800095c3  test    rax, rax
0x1800095c6  jnz     short loc_180009630
0x1800095c8  mov     rcx, [rsp+0F8h]; this
0x1800095d0  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x1800095d7  mov     edx, 4D5h; void *
0x1800095dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800095e1  mov     r15d, eax
0x1800095e4  mov     rcx, rbx; hLibModule
0x1800095e7  call    cs:__imp_FreeLibrary
0x1800095ed  nop
0x1800095ee  cmp     [r14], dil
0x1800095f1  jnz     short loc_180009628
0x1800095f3  mov     esi, 7
0x1800095f8  mov     ecx, esi
0x1800095fa  xchg    ecx, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180009600  lea     rcx, aAomdpromptresu_5; "AOMDPromptResult::CheckBitLockerFailed"
0x180009607  mov     r8, rcx
0x18000960a  mov     dil, 41h ; 'A'
0x18000960d  inc     rcx
0x180009610  cmp     dil, 3Ah ; ':'
0x180009614  jnz     short loc_180009619
0x180009616  mov     r8, rcx
0x180009619  mov     dil, [rcx]
0x18000961c  test    dil, dil
0x18000961f  jnz     short loc_18000960D
0x180009621  mov     edx, esi
0x180009623  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180009628  mov     eax, r15d
0x18000962b  jmp     loc_180009E5D
0x180009630  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x180009637  mov     rcx, rbx; hModule
0x18000963a  call    cs:__imp_GetProcAddress
0x180009640  mov     r13, rax
0x180009643  test    rax, rax
0x180009646  jnz     short loc_1800096AF
0x180009648  mov     rcx, [rsp+0F8h]; this
0x180009650  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x180009657  mov     edx, 4D8h; void *
0x18000965c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009661  mov     r15d, eax
0x180009664  mov     rcx, rbx; hLibModule
0x180009667  call    cs:__imp_FreeLibrary
0x18000966d  nop
0x18000966e  cmp     [r14], dil
0x180009671  jnz     short loc_1800096A7
0x180009673  lea     esi, [r13+7]
0x180009677  mov     ecx, esi
0x180009679  xchg    ecx, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x18000967f  lea     rcx, aAomdpromptresu_5; "AOMDPromptResult::CheckBitLockerFailed"
0x180009686  mov     r8, rcx
0x180009689  mov     dil, 41h ; 'A'
0x18000968c  inc     rcx
0x18000968f  cmp     dil, 3Ah ; ':'
0x180009693  jnz     short loc_180009698
0x180009695  mov     r8, rcx
0x180009698  mov     dil, [rcx]
0x18000969b  test    dil, dil
0x18000969e  jnz     short loc_18000968C
0x1800096a0  mov     edx, esi
0x1800096a2  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x1800096a7  mov     eax, r15d
0x1800096aa  jmp     loc_180009E5D
0x1800096af  xorps   xmm0, xmm0
0x1800096b2  movups  xmmword ptr [rsp+0F8h+lpBuffer], xmm0
0x1800096b7  mov     qword ptr [rsp+0F8h+uSize], rdi
0x1800096bc  mov     esi, 7
0x1800096c1  mov     [rsp+0F8h+var_78], rsi
0x1800096c9  mov     word ptr [rsp+0F8h+lpBuffer], di
0x1800096ce  xor     edx, edx; uSize
0x1800096d0  xor     ecx, ecx; lpBuffer
0x1800096d2  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800096d8  mov     r15d, eax
0x1800096db  test    eax, eax
0x1800096dd  jnz     short loc_180009754
0x1800096df  mov     rcx, [rsp+0F8h]; this
0x1800096e7  mov     r15d, 8000FFFFh
0x1800096ed  mov     r9d, r15d; char *
0x1800096f0  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x1800096f7  mov     edx, 4DDh; void *
0x1800096fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009701  nop
0x180009702  lea     rcx, [rsp+0F8h+lpBuffer]
0x180009707  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000970c  nop
0x18000970d  mov     rcx, rbx; hLibModule
0x180009710  call    cs:__imp_FreeLibrary
0x180009716  nop
0x180009717  cmp     [r14], dil
0x18000971a  jnz     short loc_18000974C
0x18000971c  mov     eax, esi
0x18000971e  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180009724  lea     rcx, aAomdpromptresu_5; "AOMDPromptResult::CheckBitLockerFailed"
0x18000972b  mov     r8, rcx
0x18000972e  mov     dil, 41h ; 'A'
0x180009731  inc     rcx
0x180009734  cmp     dil, 3Ah ; ':'
0x180009738  jnz     short loc_18000973D
0x18000973a  mov     r8, rcx
0x18000973d  mov     dil, [rcx]
0x180009740  test    dil, dil
0x180009743  jnz     short loc_180009731
0x180009745  mov     edx, esi
0x180009747  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x18000974c  mov     eax, r15d
0x18000974f  jmp     loc_180009E5D
0x180009754  mov     rcx, qword ptr [rsp+0F8h+uSize]
0x180009759  cmp     r15, rcx
0x18000975c  ja      short loc_18000977D
0x18000975e  mov     qword ptr [rsp+0F8h+uSize], r15
0x180009763  lea     rcx, [rsp+0F8h+lpBuffer]
0x180009768  cmp     [rsp+0F8h+var_78], rsi
0x180009770  cmova   rcx, [rsp+0F8h+lpBuffer]
0x180009776  mov     [rcx+r15*2], di
0x18000977b  jmp     short loc_1800097D5
0x18000977d  mov     rdx, r15
0x180009780  sub     rdx, rcx
0x180009783  mov     rax, [rsp+0F8h+var_78]
0x18000978b  sub     rax, rcx
0x18000978e  cmp     rdx, rax
0x180009791  ja      short loc_1800097C8
0x180009793  mov     qword ptr [rsp+0F8h+uSize], r15
0x180009798  lea     r9, [rsp+0F8h+lpBuffer]
0x18000979d  cmp     [rsp+0F8h+var_78], rsi
0x1800097a5  cmova   r9, [rsp+0F8h+lpBuffer]
0x1800097ab  lea     rdi, [r9+rcx*2]
0x1800097af  test    rdx, rdx
0x1800097b2  jz      short loc_1800097BF
0x1800097b4  xor     eax, eax
0x1800097b6  movzx   eax, ax
0x1800097b9  mov     rcx, rdx
0x1800097bc  rep stosw
0x1800097bf  xor     edi, edi
0x1800097c1  mov     [r9+r15*2], di
0x1800097c6  jmp     short loc_1800097D5
0x1800097c8  mov     r9, rdx
0x1800097cb  lea     rcx, [rsp+0F8h+lpBuffer]; Src
0x1800097d0  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x1800097d5  lea     rcx, [rsp+0F8h+lpBuffer]
0x1800097da  cmp     [rsp+0F8h+var_78], rsi
0x1800097e2  cmova   rcx, [rsp+0F8h+lpBuffer]; lpBuffer
0x1800097e8  mov     edx, [rsp+0F8h+uSize]; uSize
0x1800097ec  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800097f2  test    eax, eax
0x1800097f4  jz      loc_180009D7F
0x1800097fa  cmp     eax, r15d
0x1800097fd  ja      loc_180009D7F
0x180009803  xorps   xmm0, xmm0
0x180009806  movups  [rsp+0F8h+var_50], xmm0
0x18000980e  xorps   xmm1, xmm1
0x180009811  movdqu  [rsp+0F8h+var_40], xmm1
0x18000981a  mov     edi, 2
0x18000981f  mov     r8d, edi
0x180009822  cmp     qword ptr [rsp+0F8h+uSize], rdi
0x180009827  cmovb   r8, qword ptr [rsp+0F8h+uSize]
0x18000982d  lea     rdx, [rsp+0F8h+lpBuffer]
0x180009832  cmp     [rsp+0F8h+var_78], rsi
0x18000983a  cmova   rdx, [rsp+0F8h+lpBuffer]
0x180009840  lea     rcx, [rsp+0F8h+var_50]
0x180009848  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000984d  nop
0x18000984e  lea     r8, [rsp+0F8h+var_50]
0x180009856  lea     rcx, [rsp+0F8h+var_70]
0x18000985e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x180009863  nop
0x180009864  lea     rcx, [rsp+0F8h+var_50]
0x18000986c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009871  mov     [rsp+0F8h+var_B8], 0FFFFFFFFFFFFFFFFh
0x18000987a  lea     rcx, [rsp+0F8h+var_70]
0x180009882  cmp     [rsp+0F8h+var_58], rsi
0x18000988a  cmova   rcx, [rsp+0F8h+var_70]
0x180009893  lea     r8, [rsp+0F8h+var_B8]
0x180009898  xor     edx, edx
0x18000989a  mov     rax, r12
0x18000989d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098a2  mov     r15d, eax
0x1800098a5  xor     r12d, r12d
0x1800098a8  test    eax, eax
0x1800098aa  jns     short loc_180009929
0x1800098ac  mov     rcx, [rsp+0F8h]; this
0x1800098b4  mov     r9d, eax; char *
0x1800098b7  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x1800098be  mov     edx, 4E6h; void *
0x1800098c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800098c8  nop
0x1800098c9  lea     rcx, [rsp+0F8h+var_70]
0x1800098d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800098d6  nop
0x1800098d7  lea     rcx, [rsp+0F8h+lpBuffer]
0x1800098dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800098e1  nop
0x1800098e2  mov     rcx, rbx; hLibModule
0x1800098e5  call    cs:__imp_FreeLibrary
0x1800098eb  nop
0x1800098ec  cmp     [r14], r12b
0x1800098ef  jnz     short loc_180009921
0x1800098f1  mov     eax, esi
0x1800098f3  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x1800098f9  lea     rcx, aAomdpromptresu_5; "AOMDPromptResult::CheckBitLockerFailed"
0x180009900  mov     r8, rcx
0x180009903  mov     dil, 41h ; 'A'
0x180009906  inc     rcx
0x180009909  cmp     dil, 3Ah ; ':'
0x18000990d  jnz     short loc_180009912
0x18000990f  mov     r8, rcx
0x180009912  mov     dil, [rcx]
0x180009915  test    dil, dil
0x180009918  jnz     short loc_180009906
0x18000991a  mov     edx, esi
0x18000991c  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180009921  mov     eax, r15d
0x180009924  jmp     loc_180009E5D
0x180009929  lea     rax, [rsp+0F8h+var_B0]
0x18000992e  mov     qword ptr [rsp+0F8h+var_50], rax
0x180009936  lea     rax, [rsp+0F8h+var_B8]
0x18000993b  mov     qword ptr [rsp+0F8h+var_50+8], rax
0x180009943  mov     byte ptr [rsp+0F8h+var_40], 1
0x18000994b  mov     [rsp+0F8h+var_C8], r12b
0x180009950  lea     r8, [rsp+0F8h+var_C8]; bool *
0x180009955  mov     rdx, [rsp+0F8h+var_B8]; void *
0x18000995a  mov     rcx, rbx; HINSTANCE
0x18000995d  call    ?IsTpmProtectedVolume@@YAJPEAUHINSTANCE__@@PEAXPEA_N@Z; IsTpmProtectedVolume(HINSTANCE__ *,void *,bool *)
0x180009962  mov     r15d, eax
0x180009965  test    eax, eax
0x180009967  jns     loc_1800099FA
0x18000996d  mov     rcx, [rsp+0F8h]; this
0x180009975  mov     r9d, eax; char *
0x180009978  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000997f  mov     edx, 4EDh; void *
0x180009984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009989  nop
0x18000998a  mov     rcx, [rsp+0F8h+var_B8]
0x18000998f  mov     rax, [rsp+0F8h+var_B0]
0x180009994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009999  nop
0x18000999a  lea     rcx, [rsp+0F8h+var_70]
0x1800099a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800099a7  nop
0x1800099a8  lea     rcx, [rsp+0F8h+lpBuffer]
0x1800099ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800099b2  nop
0x1800099b3  mov     rcx, rbx; hLibModule
  ... truncated ...
```
