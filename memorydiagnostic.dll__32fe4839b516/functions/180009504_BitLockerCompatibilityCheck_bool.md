# BitLockerCompatibilityCheck(bool &)

- ea: `0x180009504`
- end: `0x180009f85`
- name: `?BitLockerCompatibilityCheck@@YAJAEA_N@Z`
- size: `2689`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a7e4`

## callees

- `0x180001008`
- `0x1800026b0`
- `0x1800037bc`
- `0x180005c80`
- `0x180005e94`
- `0x180007858`
- `0x180009504`
- `0x18000e790`
- `0x18000eaec`
- `0x18000f144`
- `0x180011384`
- `0x1800113a4`
- `0x1800165dc`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800097a4`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180009900`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800097a4`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180009900`
- `KERNEL32!FreeLibrary` at `0x180009601`
- `KERNEL32!FreeLibrary` at `0x180009694`
- `KERNEL32!FreeLibrary` at `0x180009725`
- `KERNEL32!FreeLibrary` at `0x1800097ef`
- `KERNEL32!FreeLibrary` at `0x180009a0f`
- `KERNEL32!FreeLibrary` at `0x180009aeb`
- `KERNEL32!FreeLibrary` at `0x180009bba`
- `KERNEL32!FreeLibrary` at `0x180009cae`
- `KERNEL32!FreeLibrary` at `0x180009d7d`
- `KERNEL32!FreeLibrary` at `0x180009e85`
- `KERNEL32!FreeLibrary` at `0x180009f07`
- `KERNEL32!FreeLibrary` at `0x180009601`
- `KERNEL32!FreeLibrary` at `0x180009694`
- `KERNEL32!FreeLibrary` at `0x180009725`
- `KERNEL32!FreeLibrary` at `0x1800097ef`
- `KERNEL32!FreeLibrary` at `0x180009a0f`
- `KERNEL32!FreeLibrary` at `0x180009aeb`
- `KERNEL32!FreeLibrary` at `0x180009bba`
- `KERNEL32!FreeLibrary` at `0x180009cae`
- `KERNEL32!FreeLibrary` at `0x180009d7d`
- `KERNEL32!FreeLibrary` at `0x180009e85`
- `KERNEL32!FreeLibrary` at `0x180009f07`
- `KERNEL32!GetProcAddress` at `0x1800095ce`
- `KERNEL32!GetProcAddress` at `0x18000965f`
- `KERNEL32!GetProcAddress` at `0x1800096f2`
- `KERNEL32!GetProcAddress` at `0x1800095ce`
- `KERNEL32!GetProcAddress` at `0x18000965f`
- `KERNEL32!GetProcAddress` at `0x1800096f2`
- `KERNEL32!LoadLibraryW` at `0x180009549`
- `KERNEL32!LoadLibraryW` at `0x180009549`

## string_xrefs

- `0x180009542`: `fveapi.dll`
- `0x180009594`: `BitLockerCompatibilityCheck_FveApiNotFound`
- `0x1800095c4`: `FveOpenVolumeW`
- `0x180009b62`: `BitLockerCompatibilityCheck_PrimaryVolumeNotProtected`
- `0x180009c20`: `BitLockerCompatibilityCheck_PrimaryVolumeProtected`
- `0x180009d25`: `BitLockerCompatibilityCheck_SecureBootBound`
- `0x180009dee`: `BitLockerCompatibilityCheck_SecureBootBindingPossible`
- `0x180009e30`: `BitLockerCompatibilityCheck_SecureBootNotBound`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall BitLockerCompatibilityCheck(bool *a1)
{
  HMODULE LibraryW; // rax
  unsigned int v3; // r8d
  const char *v4; // r9
  HMODULE v5; // rbx
  const struct _tlgProvider_t *v6; // rax
  int v7; // r8d
  int v8; // r9d
  const char *v10; // r9
  FARPROC ProcAddress; // r12
  unsigned int v12; // r15d
  __int64 v13; // rcx
  const char *v14; // rdi
  const char *v15; // r8
  char v16; // r9
  const char *v17; // rax
  const char *v18; // r9
  unsigned int v19; // r15d
  __int64 v20; // rcx
  const char *v21; // rdi
  const char *v22; // r8
  char v23; // r9
  const char *v24; // rax
  const char *v25; // r9
  FARPROC v26; // r13
  unsigned int LastError; // r15d
  __int64 v28; // rcx
  const char *v29; // rdi
  const char *v30; // r8
  char v31; // r9
  const char *v32; // rax
  UINT SystemWindowsDirectoryW; // eax
  UINT v34; // r15d
  const char *v35; // rdi
  const char *v36; // r8
  char v37; // r9
  const char *v38; // rcx
  __int64 v39; // r8
  unsigned __int64 v40; // rdx
  _WORD *v41; // rdi
  __int64 i; // rcx
  WCHAR *v43; // rcx
  UINT v44; // eax
  __int64 v45; // rdx
  _QWORD *v46; // rcx
  int v47; // eax
  unsigned int v48; // r15d
  const char *v49; // rdi
  const char *v50; // r8
  char v51; // r9
  const char *v52; // rcx
  int v53; // eax
  unsigned int v54; // r15d
  const char *v55; // rdi
  const char *v56; // r8
  char v57; // r9
  const char *v58; // rcx
  const struct _tlgProvider_t *v59; // rax
  int v60; // r8d
  int v61; // r9d
  __int64 v62; // rcx
  const char *v63; // rdi
  const char *v64; // r8
  char v65; // r9
  const char *v66; // rax
  int v67; // eax
  unsigned int v68; // r15d
  const char *v69; // rdi
  const char *v70; // r8
  char v71; // r9
  const char *v72; // rcx
  const struct _tlgProvider_t *v73; // rax
  int v74; // r8d
  int v75; // r9d
  __int64 v76; // rcx
  const char *v77; // rdi
  const char *v78; // r8
  char v79; // r9
  const char *v80; // rax
  const struct _tlgProvider_t *v81; // rax
  int v82; // r8d
  int v83; // r9d
  const struct _tlgProvider_t *v84; // rax
  int v85; // r8d
  int v86; // r9d
  __int64 v87; // rcx
  const char *v88; // rdi
  const char *v89; // r8
  char v90; // r9
  const char *v91; // rax
  __int64 v92; // rcx
  const char *v93; // rdi
  const char *v94; // r8
  char v95; // r9
  const char *v96; // rax
  int v97; // [rsp+20h] [rbp-108h]
  bool v98; // [rsp+30h] [rbp-F8h] BYREF
  int v99; // [rsp+34h] [rbp-F4h] BYREF
  void *v100; // [rsp+38h] [rbp-F0h] BYREF
  FARPROC v101; // [rsp+40h] [rbp-E8h] BYREF
  int v102[2]; // [rsp+48h] [rbp-E0h] BYREF
  const wchar_t *v103; // [rsp+50h] [rbp-D8h] BYREF
  _QWORD v104[3]; // [rsp+58h] [rbp-D0h] BYREF
  char v105; // [rsp+70h] [rbp-B8h]
  FARPROC *v106; // [rsp+78h] [rbp-B0h]
  void **v107; // [rsp+80h] [rbp-A8h]
  char v108; // [rsp+88h] [rbp-A0h]
  LPWSTR lpBuffer[2]; // [rsp+90h] [rbp-98h] BYREF
  UINT uSize[2]; // [rsp+A0h] [rbp-88h]
  unsigned __int64 v111; // [rsp+A8h] [rbp-80h]
  _QWORD v112[4]; // [rsp+B0h] [rbp-78h] BYREF
  _OWORD v113[2]; // [rsp+D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  *a1 = 0;
  v104[2] = a1;
  v105 = 1;
  LibraryW = LoadLibraryW(L"fveapi.dll");
  v5 = LibraryW;
  v104[1] = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "FveOpenVolumeW");
    if ( ProcAddress )
    {
      v101 = GetProcAddress(v5, "FveCloseVolume");
      if ( v101 )
      {
        v26 = GetProcAddress(v5, "FveGetSecureBootBindingState");
        if ( v26 )
        {
          *(_OWORD *)lpBuffer = 0;
          *(_QWORD *)uSize = 0;
          v111 = 7;
          LOWORD(lpBuffer[0]) = 0;
          SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
          v34 = SystemWindowsDirectoryW;
          if ( SystemWindowsDirectoryW )
          {
            v39 = *(_QWORD *)uSize;
            if ( (unsigned __int64)SystemWindowsDirectoryW > *(_QWORD *)uSize )
            {
              v40 = SystemWindowsDirectoryW - *(_QWORD *)uSize;
              if ( v40 > v111 - *(_QWORD *)uSize )
              {
                std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpBuffer);
              }
              else
              {
                *(_QWORD *)uSize = SystemWindowsDirectoryW;
                v41 = (_WORD *)lpBuffer + v39;
                if ( v40 )
                {
                  for ( i = SystemWindowsDirectoryW - v39; i; --i )
                    *v41++ = 0;
                }
                *((_WORD *)lpBuffer + v40 + v39) = 0;
              }
            }
            else
            {
              *(_QWORD *)uSize = SystemWindowsDirectoryW;
              *((_WORD *)lpBuffer + SystemWindowsDirectoryW) = 0;
            }
            v43 = (WCHAR *)lpBuffer;
            if ( v111 > 7 )
              v43 = lpBuffer[0];
            v44 = GetSystemWindowsDirectoryW(v43, uSize[0]);
            if ( v44 && v44 <= v34 )
            {
              memset(v113, 0, sizeof(v113));
              std::wstring::_Construct<1,unsigned short const *>(v113);
              std::operator+<unsigned short>(v112, v45, v113);
              std::wstring::~wstring(v113);
              v100 = (void *)-1LL;
              v46 = v112;
              if ( v112[3] > 7u )
                v46 = (_QWORD *)v112[0];
              v47 = ((__int64 (__fastcall *)(_QWORD *, _QWORD, void **))ProcAddress)(v46, 0, &v100);
              v48 = v47;
              if ( v47 >= 0 )
              {
                v106 = &v101;
                v107 = &v100;
                v108 = 1;
                v98 = 0;
                v53 = IsTpmProtectedVolume(v5, v100, &v98);
                v54 = v53;
                if ( v53 >= 0 )
                {
                  v59 = TlgHelper::Provider();
                  if ( v98 )
                  {
                    if ( *(_DWORD *)v59 > 4u
                      && (*((_BYTE *)v59 + 16) & 2) != 0
                      && (*((_QWORD *)v59 + 3) & 2LL) == *((_QWORD *)v59 + 3) )
                    {
                      *(_QWORD *)v102 = L"BitLockerCompatibilityCheck_PrimaryVolumeProtected";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                        (_DWORD)v59,
                        (unsigned int)&unk_18002AB01,
                        v60,
                        v61,
                        (__int64)v102);
                    }
                    v99 = -1;
                    v67 = ((__int64 (__fastcall *)(int *))v26)(&v99);
                    v68 = v67;
                    if ( v67 >= 0 )
                    {
                      if ( v99 == 3 )
                      {
                        v73 = TlgHelper::Provider();
                        if ( *(_DWORD *)v73 > 4u
                          && (*((_BYTE *)v73 + 16) & 2) != 0
                          && (*((_QWORD *)v73 + 3) & 2LL) == *((_QWORD *)v73 + 3) )
                        {
                          v103 = L"BitLockerCompatibilityCheck_SecureBootBound";
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                            (_DWORD)v73,
                            (unsigned int)&unk_18002AB01,
                            v74,
                            v75,
                            (__int64)&v103);
                        }
                        *a1 = 1;
                        ((void (__fastcall *)(void *))v101)(v100);
                        std::wstring::~wstring(v112);
                        std::wstring::~wstring(lpBuffer);
                        FreeLibrary(v5);
                        if ( !*a1 )
                        {
                          _InterlockedExchange(&g_aomdPromptResult, 7);
                          v77 = "AOMDPromptResult::CheckBitLockerFailed";
                          v78 = "AOMDPromptResult::CheckBitLockerFailed";
                          v79 = 65;
                          do
                          {
                            v80 = ++v77;
                            if ( v79 != 58 )
                              v80 = v78;
                            v78 = v80;
                            v79 = *v77;
                          }
                          while ( *v77 );
                          tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                            v76,
                            7,
                            v80);
                        }
                        return 0;
                      }
                      else
                      {
                        if ( v99 == 2 )
                        {
                          v81 = TlgHelper::Provider();
                          if ( *(_DWORD *)v81 > 3u
                            && (*((_BYTE *)v81 + 16) & 2) != 0
                            && (*((_QWORD *)v81 + 3) & 2LL) == *((_QWORD *)v81 + 3) )
                          {
                            v103 = L"BitLockerCompatibilityCheck_SecureBootBindingPossible";
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                              (_DWORD)v81,
                              (unsigned int)&unk_18002AF55,
                              v82,
                              v83,
                              (__int64)&v103);
                          }
                        }
                        v84 = TlgHelper::Provider();
                        if ( *(_DWORD *)v84 > 3u
                          && (*((_BYTE *)v84 + 16) & 2) != 0
                          && (*((_QWORD *)v84 + 3) & 2LL) == *((_QWORD *)v84 + 3) )
                        {
                          v104[0] = L"BitLockerCompatibilityCheck_SecureBootNotBound";
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                            (_DWORD)v84,
                            (unsigned int)&unk_18002AF55,
                            v85,
                            v86,
                            (__int64)v104);
                        }
                        ((void (__fastcall *)(void *))v101)(v100);
                        std::wstring::~wstring(v112);
                        std::wstring::~wstring(lpBuffer);
                        FreeLibrary(v5);
                        if ( !*a1 )
                        {
                          _InterlockedExchange(&g_aomdPromptResult, 7);
                          v88 = "AOMDPromptResult::CheckBitLockerFailed";
                          v89 = "AOMDPromptResult::CheckBitLockerFailed";
                          v90 = 65;
                          do
                          {
                            v91 = ++v88;
                            if ( v90 != 58 )
                              v91 = v89;
                            v89 = v91;
                            v90 = *v88;
                          }
                          while ( *v88 );
                          tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                            v87,
                            7,
                            v91);
                        }
                        return 0;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x559,
                        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                        (const char *)(unsigned int)v67,
                        v97);
                      ((void (__fastcall *)(void *))v101)(v100);
                      std::wstring::~wstring(v112);
                      std::wstring::~wstring(lpBuffer);
                      FreeLibrary(v5);
                      if ( !*a1 )
                      {
                        _InterlockedExchange(&g_aomdPromptResult, 7);
                        v69 = "AOMDPromptResult::CheckBitLockerFailed";
                        v70 = "AOMDPromptResult::CheckBitLockerFailed";
                        v71 = 65;
                        do
                        {
                          v72 = ++v69;
                          if ( v71 != 58 )
                            v72 = v70;
                          v70 = v72;
                          v71 = *v69;
                        }
                        while ( *v69 );
                        tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                          v72,
                          7,
                          v72);
                      }
                      return v68;
                    }
                  }
                  else
                  {
                    if ( *(_DWORD *)v59 > 4u
                      && (*((_BYTE *)v59 + 16) & 2) != 0
                      && (*((_QWORD *)v59 + 3) & 2LL) == *((_QWORD *)v59 + 3) )
                    {
                      *(_QWORD *)v102 = L"BitLockerCompatibilityCheck_PrimaryVolumeNotProtected";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                        (_DWORD)v59,
                        (unsigned int)&unk_18002AB01,
                        v60,
                        v61,
                        (__int64)v102);
                    }
                    *a1 = 1;
                    ((void (__fastcall *)(void *))v101)(v100);
                    std::wstring::~wstring(v112);
                    std::wstring::~wstring(lpBuffer);
                    FreeLibrary(v5);
                    if ( !*a1 )
                    {
                      _InterlockedExchange(&g_aomdPromptResult, 7);
                      v63 = "AOMDPromptResult::CheckBitLockerFailed";
                      v64 = "AOMDPromptResult::CheckBitLockerFailed";
                      v65 = 65;
                      do
                      {
                        v66 = ++v63;
                        if ( v65 != 58 )
                          v66 = v64;
                        v64 = v66;
                        v65 = *v63;
                      }
                      while ( *v63 );
                      tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                        v62,
                        7,
                        v66);
                    }
                    return 0;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x54C,
                    (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                    (const char *)(unsigned int)v53,
                    v97);
                  ((void (__fastcall *)(void *))v101)(v100);
                  std::wstring::~wstring(v112);
                  std::wstring::~wstring(lpBuffer);
                  FreeLibrary(v5);
                  if ( !*a1 )
                  {
                    _InterlockedExchange(&g_aomdPromptResult, 7);
                    v55 = "AOMDPromptResult::CheckBitLockerFailed";
                    v56 = "AOMDPromptResult::CheckBitLockerFailed";
                    v57 = 65;
                    do
                    {
                      v58 = ++v55;
                      if ( v57 != 58 )
                        v58 = v56;
                      v56 = v58;
                      v57 = *v55;
                    }
                    while ( *v55 );
                    tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                      v58,
                      7,
                      v58);
                  }
                  return v54;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x545,
                  (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                  (const char *)(unsigned int)v47,
                  v97);
                std::wstring::~wstring(v112);
                std::wstring::~wstring(lpBuffer);
                FreeLibrary(v5);
                if ( !*a1 )
                {
                  _InterlockedExchange(&g_aomdPromptResult, 7);
                  v49 = "AOMDPromptResult::CheckBitLockerFailed";
                  v50 = "AOMDPromptResult::CheckBitLockerFailed";
                  v51 = 65;
                  do
                  {
                    v52 = ++v49;
                    if ( v51 != 58 )
                      v52 = v50;
                    v50 = v52;
                    v51 = *v49;
                  }
                  while ( *v49 );
                  tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                    v52,
                    7,
                    v52);
                }
                return v48;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x540,
                (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                (const char *)0x8000FFFFLL,
                v97);
              std::wstring::~wstring(lpBuffer);
              FreeLibrary(v5);
              if ( !*a1 )
              {
                _InterlockedExchange(&g_aomdPromptResult, 7);
                v93 = "AOMDPromptResult::CheckBitLockerFailed";
                v94 = "AOMDPromptResult::CheckBitLockerFailed";
                v95 = 65;
                do
                {
                  v96 = ++v93;
                  if ( v95 != 58 )
                    v96 = v94;
                  v94 = v96;
                  v95 = *v93;
                }
                while ( *v93 );
                tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                  v92,
                  7,
                  v96);
              }
              return 2147549183LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x53C,
              (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
              (const char *)0x8000FFFFLL,
              v97);
            std::wstring::~wstring(lpBuffer);
            FreeLibrary(v5);
            if ( !*a1 )
            {
              _InterlockedExchange(&g_aomdPromptResult, 7);
              v35 = "AOMDPromptResult::CheckBitLockerFailed";
              v36 = "AOMDPromptResult::CheckBitLockerFailed";
              v37 = 65;
              do
              {
                v38 = ++v35;
                if ( v37 != 58 )
                  v38 = v36;
                v36 = v38;
                v37 = *v35;
              }
              while ( *v35 );
              tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
                v38,
                7,
                v38);
            }
            return 2147549183LL;
          }
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x537,
                        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                        v25);
          FreeLibrary(v5);
          if ( !*a1 )
          {
            v28 = (unsigned int)_InterlockedExchange(&g_aomdPromptResult, 7);
            v29 = "AOMDPromptResult::CheckBitLockerFailed";
            v30 = "AOMDPromptResult::CheckBitLockerFailed";
            v31 = 65;
            do
            {
              v32 = ++v29;
              if ( v31 != 58 )
                v32 = v30;
              v30 = v32;
              v31 = *v29;
            }
            while ( *v29 );
            tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
              v28,
              7,
              v32);
          }
          return LastError;
        }
      }
      else
      {
        v19 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x534,
                (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                v18);
        FreeLibrary(v5);
        if ( !*a1 )
        {
          v20 = (unsigned int)_InterlockedExchange(&g_aomdPromptResult, 7);
          v21 = "AOMDPromptResult::CheckBitLockerFailed";
          v22 = "AOMDPromptResult::CheckBitLockerFailed";
          v23 = 65;
          do
          {
            v24 = ++v21;
            if ( v23 != 58 )
              v24 = v22;
            v22 = v24;
            v23 = *v21;
          }
          while ( *v21 );
          tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
            v20,
            7,
            v24);
        }
        return v19;
      }
    }
    else
    {
      v12 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x531,
              (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
              v10);
      FreeLibrary(v5);
      if ( !*a1 )
      {
        v13 = (unsigned int)_InterlockedExchange(&g_aomdPromptResult, 7);
        v14 = "AOMDPromptResult::CheckBitLockerFailed";
        v15 = "AOMDPromptResult::CheckBitLockerFailed";
        v16 = 65;
        do
        {
          v17 = ++v14;
          if ( v16 != 58 )
            v17 = v15;
          v15 = v17;
          v16 = *v14;
        }
        while ( *v14 );
        tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
          v13,
          7,
          v17);
      }
      return v12;
    }
  }
  else
  {
    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x527, v3, v4);
    v6 = TlgHelper::Provider();
    if ( *(_DWORD *)v6 > 4u && (*((_BYTE *)v6 + 16) & 2) != 0 && (*((_QWORD *)v6 + 3) & 2LL) == *((_QWORD *)v6 + 3) )
    {
      *(_QWORD *)v102 = L"BitLockerCompatibilityCheck_FveApiNotFound";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v6,
        (unsigned int)&unk_18002AB01,
        v7,
        v8,
        (__int64)v102);
    }
    *a1 = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x180009504  mov     [rsp+arg_8], rbx
0x180009509  mov     [rsp+arg_10], rsi
0x18000950e  push    rdi
0x18000950f  push    r12
0x180009511  push    r13
0x180009513  push    r14
0x180009515  push    r15
0x180009517  sub     rsp, 100h
0x18000951e  mov     rax, cs:__security_cookie
0x180009525  xor     rax, rsp
0x180009528  mov     [rsp+128h+var_38], rax
0x180009530  mov     r14, rcx
0x180009533  xor     edi, edi
0x180009535  mov     [rcx], dil
0x180009538  mov     [rsp+128h+var_C0], rcx
0x18000953d  mov     [rsp+128h+var_B8], 1
0x180009542  lea     rcx, LibFileName; "fveapi.dll"
0x180009549  call    cs:__imp_LoadLibraryW
0x180009550  nop     dword ptr [rax+rax+00h]
0x180009555  mov     rbx, rax
0x180009558  mov     [rsp+128h+var_C8], rax
0x18000955d  test    rax, rax
0x180009560  jnz     short loc_1800095C4
0x180009562  mov     rcx, [rsp+128h]; this
0x18000956a  mov     edx, 527h; void *
0x18000956f  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180009574  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180009579  cmp     dword ptr [rax], 4
0x18000957c  jbe     short loc_1800095B9
0x18000957e  lea     edi, [rbx+2]
0x180009581  test    [rax+10h], dil
0x180009585  jz      short loc_1800095B9
0x180009587  mov     rcx, [rax+18h]
0x18000958b  and     rcx, rdi
0x18000958e  cmp     rcx, [rax+18h]
0x180009592  jnz     short loc_1800095B9
0x180009594  lea     rcx, aBitlockercompa_2; "BitLockerCompatibilityCheck_FveApiNotFo"...
0x18000959b  mov     qword ptr [rsp+128h+var_E0], rcx
0x1800095a0  lea     rcx, [rsp+128h+var_E0]
0x1800095a5  mov     qword ptr [rsp+128h+var_108], rcx
0x1800095aa  lea     rdx, byte_18002AB01
0x1800095b1  mov     rcx, rax
0x1800095b4  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800095b9  mov     byte ptr [r14], 1
0x1800095bd  xor     eax, eax
0x1800095bf  jmp     loc_180009F57
0x1800095c4  lea     rdx, ProcName; "FveOpenVolumeW"
0x1800095cb  mov     rcx, rbx; hModule
0x1800095ce  call    cs:__imp_GetProcAddress
0x1800095d5  nop     dword ptr [rax+rax+00h]
0x1800095da  mov     r12, rax
0x1800095dd  test    rax, rax
0x1800095e0  jnz     short loc_180009655
0x1800095e2  mov     rcx, [rsp+128h]; this
0x1800095ea  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x1800095f1  mov     edx, 531h; void *
0x1800095f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800095fb  mov     r15d, eax
0x1800095fe  mov     rcx, rbx; hLibModule
0x180009601  call    cs:__imp_FreeLibrary
0x180009608  nop     dword ptr [rax+rax+00h]
0x18000960d  nop
0x18000960e  cmp     [r14], dil
0x180009611  jnz     short loc_18000964D
0x180009613  lea     esi, [r12+7]
0x180009618  mov     ecx, esi
0x18000961a  xchg    ecx, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180009620  lea     rdi, aAomdpromptresu_5; "AOMDPromptResult::CheckBitLockerFailed"
0x180009627  mov     r8, rdi
0x18000962a  mov     r9b, 41h ; 'A'
0x18000962d  inc     rdi
0x180009630  mov     rax, rdi
0x180009633  cmp     r9b, 3Ah ; ':'
0x180009637  cmovnz  rax, r8
0x18000963b  mov     r8, rax
0x18000963e  mov     r9b, [rdi]
0x180009641  test    r9b, r9b
0x180009644  jnz     short loc_18000962D
0x180009646  mov     edx, esi
0x180009648  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x18000964d  mov     eax, r15d
0x180009650  jmp     loc_180009F57
0x180009655  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x18000965c  mov     rcx, rbx; hModule
0x18000965f  call    cs:__imp_GetProcAddress
0x180009666  nop     dword ptr [rax+rax+00h]
0x18000966b  mov     [rsp+128h+var_E8], rax
0x180009670  test    rax, rax
0x180009673  jnz     short loc_1800096E8
0x180009675  mov     rcx, [rsp+128h]; this
0x18000967d  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x180009684  mov     edx, 534h; void *
0x180009689  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000968e  mov     r15d, eax
0x180009691  mov     rcx, rbx; hLibModule
0x180009694  call    cs:__imp_FreeLibrary
0x18000969b  nop     dword ptr [rax+rax+00h]
0x1800096a0  nop
0x1800096a1  cmp     [r14], dil
0x1800096a4  jnz     short loc_1800096E0
0x1800096a6  mov     esi, 7
0x1800096ab  mov     ecx, esi
0x1800096ad  xchg    ecx, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x1800096b3  lea     rdi, aAomdpromptresu_5; "AOMDPromptResult::CheckBitLockerFailed"
0x1800096ba  mov     r8, rdi
0x1800096bd  mov     r9b, 41h ; 'A'
0x1800096c0  inc     rdi
0x1800096c3  mov     rax, rdi
0x1800096c6  cmp     r9b, 3Ah ; ':'
0x1800096ca  cmovnz  rax, r8
0x1800096ce  mov     r8, rax
0x1800096d1  mov     r9b, [rdi]
0x1800096d4  test    r9b, r9b
0x1800096d7  jnz     short loc_1800096C0
0x1800096d9  mov     edx, esi
0x1800096db  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x1800096e0  mov     eax, r15d
0x1800096e3  jmp     loc_180009F57
0x1800096e8  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x1800096ef  mov     rcx, rbx; hModule
0x1800096f2  call    cs:__imp_GetProcAddress
0x1800096f9  nop     dword ptr [rax+rax+00h]
0x1800096fe  mov     r13, rax
0x180009701  test    rax, rax
0x180009704  jnz     short loc_180009778
0x180009706  mov     rcx, [rsp+128h]; this
0x18000970e  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x180009715  mov     edx, 537h; void *
0x18000971a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000971f  mov     r15d, eax
0x180009722  mov     rcx, rbx; hLibModule
0x180009725  call    cs:__imp_FreeLibrary
0x18000972c  nop     dword ptr [rax+rax+00h]
0x180009731  nop
0x180009732  cmp     [r14], dil
0x180009735  jnz     short loc_180009770
0x180009737  lea     esi, [r13+7]
0x18000973b  mov     ecx, esi
0x18000973d  xchg    ecx, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180009743  lea     rdi, aAomdpromptresu_5; "AOMDPromptResult::CheckBitLockerFailed"
0x18000974a  mov     r8, rdi
0x18000974d  mov     r9b, 41h ; 'A'
0x180009750  inc     rdi
0x180009753  mov     rax, rdi
0x180009756  cmp     r9b, 3Ah ; ':'
0x18000975a  cmovnz  rax, r8
0x18000975e  mov     r8, rax
0x180009761  mov     r9b, [rdi]
0x180009764  test    r9b, r9b
0x180009767  jnz     short loc_180009750
0x180009769  mov     edx, esi
0x18000976b  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180009770  mov     eax, r15d
0x180009773  jmp     loc_180009F57
0x180009778  xorps   xmm0, xmm0
0x18000977b  movups  xmmword ptr [rsp+128h+lpBuffer], xmm0
0x180009783  mov     qword ptr [rsp+128h+uSize], rdi
0x18000978b  mov     esi, 7
0x180009790  mov     [rsp+128h+var_80], rsi
0x180009798  mov     word ptr [rsp+128h+lpBuffer], di
0x1800097a0  xor     edx, edx; uSize
0x1800097a2  xor     ecx, ecx; lpBuffer
0x1800097a4  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800097ab  nop     dword ptr [rax+rax+00h]
0x1800097b0  mov     r15d, eax
0x1800097b3  test    eax, eax
0x1800097b5  jnz     loc_18000983E
0x1800097bb  mov     rcx, [rsp+128h]; this
0x1800097c3  mov     r15d, 8000FFFFh
0x1800097c9  mov     r9d, r15d; char *
0x1800097cc  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x1800097d3  mov     edx, 53Ch; void *
0x1800097d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097dd  nop
0x1800097de  lea     rcx, [rsp+128h+lpBuffer]
0x1800097e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800097eb  nop
0x1800097ec  mov     rcx, rbx; hLibModule
0x1800097ef  call    cs:__imp_FreeLibrary
0x1800097f6  nop     dword ptr [rax+rax+00h]
0x1800097fb  nop
0x1800097fc  cmp     [r14], dil
0x1800097ff  jnz     short loc_180009836
0x180009801  mov     eax, esi
0x180009803  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180009809  lea     rdi, aAomdpromptresu_5; "AOMDPromptResult::CheckBitLockerFailed"
0x180009810  mov     r8, rdi
0x180009813  mov     r9b, 41h ; 'A'
0x180009816  inc     rdi
0x180009819  mov     rcx, rdi
0x18000981c  cmp     r9b, 3Ah ; ':'
0x180009820  cmovnz  rcx, r8
0x180009824  mov     r8, rcx
0x180009827  mov     r9b, [rdi]
0x18000982a  test    r9b, r9b
0x18000982d  jnz     short loc_180009816
0x18000982f  mov     edx, esi
0x180009831  call    ?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)
0x180009836  mov     eax, r15d
0x180009839  jmp     loc_180009F57
0x18000983e  mov     rcx, r15
0x180009841  mov     r8, qword ptr [rsp+128h+uSize]
0x180009849  cmp     r15, r8
0x18000984c  ja      short loc_180009876
0x18000984e  lea     rax, [rsp+128h+lpBuffer]
0x180009856  cmp     [rsp+128h+var_80], rsi
0x18000985e  cmova   rax, [rsp+128h+lpBuffer]
0x180009867  mov     qword ptr [rsp+128h+uSize], rcx
0x18000986f  mov     [rax+r15*2], di
0x180009874  jmp     short loc_1800098E0
0x180009876  mov     rdx, rcx
0x180009879  sub     rdx, r8
0x18000987c  mov     rax, [rsp+128h+var_80]
0x180009884  sub     rax, r8
0x180009887  cmp     rdx, rax
0x18000988a  ja      short loc_1800098D0
0x18000988c  mov     qword ptr [rsp+128h+uSize], rcx
0x180009894  lea     r9, [rsp+128h+lpBuffer]
0x18000989c  cmp     [rsp+128h+var_80], rsi
0x1800098a4  cmova   r9, [rsp+128h+lpBuffer]
0x1800098ad  lea     rdi, [r9+r8*2]
0x1800098b1  xor     r10d, r10d
0x1800098b4  test    rdx, rdx
0x1800098b7  jz      short loc_1800098C3
0x1800098b9  movzx   eax, r10w
0x1800098bd  mov     rcx, rdx
0x1800098c0  rep stosw
0x1800098c3  lea     rax, [rdx+r8]
0x1800098c7  xor     edi, edi
0x1800098c9  mov     [r9+rax*2], di
0x1800098ce  jmp     short loc_1800098E0
0x1800098d0  mov     r9, rdx
0x1800098d3  lea     rcx, [rsp+128h+lpBuffer]; Src
0x1800098db  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x1800098e0  lea     rcx, [rsp+128h+lpBuffer]
0x1800098e8  cmp     [rsp+128h+var_80], rsi
0x1800098f0  cmova   rcx, [rsp+128h+lpBuffer]; lpBuffer
0x1800098f9  mov     edx, [rsp+128h+uSize]; uSize
0x180009900  call    cs:__imp_GetSystemWindowsDirectoryW
0x180009907  nop     dword ptr [rax+rax+00h]
0x18000990c  test    eax, eax
0x18000990e  jz      loc_180009ED3
0x180009914  cmp     eax, r15d
0x180009917  ja      loc_180009ED3
0x18000991d  xorps   xmm0, xmm0
0x180009920  movups  [rsp+128h+var_58], xmm0
0x180009928  xorps   xmm1, xmm1
0x18000992b  movdqu  [rsp+128h+var_48], xmm1
0x180009934  mov     edi, 2
0x180009939  mov     r8d, edi
0x18000993c  cmp     qword ptr [rsp+128h+uSize], rdi
0x180009944  cmovb   r8, qword ptr [rsp+128h+uSize]
0x18000994d  lea     rdx, [rsp+128h+lpBuffer]
0x180009955  cmp     [rsp+128h+var_80], rsi
0x18000995d  cmova   rdx, [rsp+128h+lpBuffer]
0x180009966  lea     rcx, [rsp+128h+var_58]
0x18000996e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180009973  nop
0x180009974  lea     r8, [rsp+128h+var_58]
0x18000997c  lea     rcx, [rsp+128h+var_78]
0x180009984  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x180009989  nop
0x18000998a  lea     rcx, [rsp+128h+var_58]
0x180009992  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009997  or      [rsp+128h+var_F0], 0FFFFFFFFFFFFFFFFh
0x18000999d  lea     rcx, [rsp+128h+var_78]
0x1800099a5  cmp     [rsp+128h+var_60], rsi
0x1800099ad  cmova   rcx, [rsp+128h+var_78]
0x1800099b6  lea     r8, [rsp+128h+var_F0]
0x1800099bb  xor     edx, edx
0x1800099bd  mov     rax, r12
0x1800099c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099c5  mov     r15d, eax
0x1800099c8  xor     r12d, r12d
0x1800099cb  test    eax, eax
0x1800099cd  jns     loc_180009A5E
0x1800099d3  mov     rcx, [rsp+128h]; this
0x1800099db  mov     r9d, eax; char *
0x1800099de  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x1800099e5  mov     edx, 545h; void *
0x1800099ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800099ef  nop
0x1800099f0  lea     rcx, [rsp+128h+var_78]
0x1800099f8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800099fd  nop
0x1800099fe  lea     rcx, [rsp+128h+lpBuffer]
0x180009a06  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009a0b  nop
0x180009a0c  mov     rcx, rbx; hLibModule
0x180009a0f  call    cs:__imp_FreeLibrary
0x180009a16  nop     dword ptr [rax+rax+00h]
0x180009a1b  nop
0x180009a1c  cmp     [r14], r12b
0x180009a1f  jnz     short loc_180009A56
0x180009a21  mov     eax, esi
0x180009a23  xchg    eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180009a29  lea     rdi, aAomdpromptresu_5; "AOMDPromptResult::CheckBitLockerFailed"
0x180009a30  mov     r8, rdi
0x180009a33  mov     r9b, 41h ; 'A'
0x180009a36  inc     rdi
  ... truncated ...
```
