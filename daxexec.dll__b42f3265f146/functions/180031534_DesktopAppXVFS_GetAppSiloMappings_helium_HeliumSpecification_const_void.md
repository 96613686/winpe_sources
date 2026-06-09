# DesktopAppXVFS::GetAppSiloMappings(helium::HeliumSpecification const &,void *)

- ea: `0x180031534`
- end: `0x18003220f`
- name: `?GetAppSiloMappings@DesktopAppXVFS@@YA?AV?$vector@UMapping@DesktopAppXVFS@@V?$allocator@UMapping@DesktopAppXVFS@@@std@@@std@@AEBVHeliumSpecification@helium@@PEAX@Z`
- size: `3291`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, char *)`
- caller_count: `1`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180030254`

## callees

- `0x180004f70`
- `0x18000b132`
- `0x180012f3c`
- `0x1800130e4`
- `0x180013510`
- `0x1800136dc`
- `0x180014e74`
- `0x1800210fc`
- `0x1800270fc`
- `0x18002bab4`
- `0x18002d4f0`
- `0x18002d56c`
- `0x18002e804`
- `0x18002ef14`
- `0x18002fd58`
- `0x180031534`
- `0x180037040`
- `0x18003e43c`
- `0x18003e52c`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800315bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031667`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003174a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800315bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031667`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003174a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032056`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031ff4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032095`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800320d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800320fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032122`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003214a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032172`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003219a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800321c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800321ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031ff4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032095`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800320d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800320fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032122`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003214a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032172`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003219a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800321c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800321ea`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800316ff`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800316ff`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180031605`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800316a3`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180031605`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800316a3`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180031730`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18003203b`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180031730`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18003203b`

## string_xrefs

- `0x180031ec4`: `D3DSCache`
- `0x180031f25`: `D3DSCache`
- `0x180031f62`: `D3DSCache`
- `0x180031b7d`: `DXCache`
- `0x180031bf5`: `DXCache`
- `0x180031c46`: `DXCache`
- `0x180031d5b`: `DXCache`
- `0x180031dcf`: `DXCache`
- `0x180031e1c`: `DXCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall DesktopAppXVFS::GetAppSiloMappings(_QWORD *a1, __int64 a2, char *a3)
{
  char *v3; // r15
  char *v6; // r13
  int v7; // edi
  char *v8; // r12
  int v9; // edi
  _QWORD *v10; // rax
  void *v11; // rbx
  HANDLE v12; // rdi
  _QWORD *v13; // rax
  void *v14; // rdi
  const WCHAR *v15; // rcx
  DWORD NamedSecurityInfoW; // eax
  PSECURITY_DESCRIPTOR v17; // rsi
  __m128i si128; // xmm6
  __int64 StateFolderString; // rax
  _QWORD *v20; // rax
  __int64 v21; // rax
  _QWORD *v22; // rax
  __int64 v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // r8
  void **v26; // rdi
  __int64 v27; // rax
  __int64 v28; // r8
  _WORD *v29; // rdi
  __int64 v30; // rax
  __int64 v31; // r8
  _WORD *v32; // rdi
  __int64 v33; // rax
  __int64 v34; // rax
  _QWORD *v35; // rax
  __int64 v36; // r8
  void **v37; // rdi
  __int64 v38; // rax
  __int64 v39; // r8
  void **v40; // rdi
  __int64 v41; // rax
  const char *v43; // r9
  const char *v44; // r9
  const char *v45; // r9
  const char *v46; // r9
  const char *v47; // r9
  const char *v48; // r9
  const char *v49; // r9
  const char *v50; // r9
  const char *v51; // r9
  unsigned int ppsidGroup; // [rsp+28h] [rbp-E0h]
  int ppsidGroupa; // [rsp+28h] [rbp-E0h]
  int ppsidGroupb; // [rsp+28h] [rbp-E0h]
  int ppsidGroupc; // [rsp+28h] [rbp-E0h]
  int ppsidGroupd; // [rsp+28h] [rbp-E0h]
  int ppDacl; // [rsp+30h] [rbp-D8h]
  int ppDacla; // [rsp+30h] [rbp-D8h]
  int ppDaclb; // [rsp+30h] [rbp-D8h]
  int ppDaclc; // [rsp+30h] [rbp-D8h]
  int ppDacld; // [rsp+30h] [rbp-D8h]
  HANDLE v62; // [rsp+48h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B8h] BYREF
  int v64; // [rsp+58h] [rbp-B0h]
  __int128 v65; // [rsp+60h] [rbp-A8h] BYREF
  __m128i v66; // [rsp+70h] [rbp-98h]
  __int128 v67; // [rsp+80h] [rbp-88h] BYREF
  __m128i v68; // [rsp+90h] [rbp-78h]
  char *v69; // [rsp+A0h] [rbp-68h] BYREF
  PSECURITY_DESCRIPTOR hMem[3]; // [rsp+A8h] [rbp-60h] BYREF
  void *Src[2]; // [rsp+C0h] [rbp-48h] BYREF
  __m128i v72; // [rsp+D0h] [rbp-38h]
  __int128 v73; // [rsp+E0h] [rbp-28h] BYREF
  __m128i v74; // [rsp+F0h] [rbp-18h]
  __int128 v75; // [rsp+100h] [rbp-8h] BYREF
  __m128i v76; // [rsp+110h] [rbp+8h]
  __int128 v77; // [rsp+120h] [rbp+18h] BYREF
  __m128i v78; // [rsp+130h] [rbp+28h]
  _BYTE v79[32]; // [rsp+140h] [rbp+38h] BYREF
  LPCWSTR pObjectName[4]; // [rsp+160h] [rbp+58h] BYREF
  _BYTE v81[32]; // [rsp+180h] [rbp+78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F0h] [rbp+E8h]

  v3 = a3;
  hMem[1] = a1;
  v6 = 0;
  v7 = 0;
  v64 = 0;
  v8 = 0;
  v69 = 0;
  if ( !a3 )
  {
    wil::open_current_access_token(&hObject, 131080);
    v7 = 2;
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v69,
      &hObject);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v8 = v69;
    v3 = v69;
  }
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v9 = v7 | 1;
  v64 = v9;
  v10 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 16LL))(a2, &v75);
  if ( v10[3] > 7u )
    v10 = (_QWORD *)*v10;
  v11 = (void *)OpenStateExplicit(v3, v10);
  hMem[2] = v11;
  std::wstring::~wstring(&v75);
  v62 = 0;
  hMem[0] = 0;
  if ( v3 )
  {
    v12 = v3;
  }
  else
  {
    wil::open_current_access_token(&hObject, 131080);
    v64 = v9 | 4;
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v62,
      &hObject);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v6 = (char *)v62;
    v12 = v62;
  }
  v13 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 16LL))(a2, &v75);
  if ( v13[3] > 7u )
    v13 = (_QWORD *)*v13;
  v14 = (void *)OpenStateExplicit(v12, v13);
  hObject = v14;
  std::wstring::~wstring(&v75);
  GetStateFolderString(pObjectName);
  v15 = (const WCHAR *)pObjectName;
  if ( pObjectName[3] > (LPCWSTR)7 )
    v15 = pObjectName[0];
  NamedSecurityInfoW = GetNamedSecurityInfoW(v15, SE_FILE_OBJECT, 4u, 0, 0, 0, 0, hMem);
  if ( NamedSecurityInfoW )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x3FF,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      (const char *)NamedSecurityInfoW,
      ppsidGroup);
  v17 = hMem[0];
  std::wstring::~wstring(pObjectName);
  if ( v14 )
    CloseState(v14);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  *(_OWORD *)Src = 0;
  v72.m128i_i64[0] = 0;
  v72.m128i_i64[1] = 7;
  LOWORD(Src[0]) = 0;
  GetKnownFolderForUser<1>(v79, &FOLDERID_Profile, v3);
  AppendPath(v79);
  GetStateRootFolderString(v81);
  v73 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v74 = si128;
  LOWORD(v73) = 0;
  v77 = 0;
  v78 = si128;
  LOWORD(v77) = 0;
  StateFolderString = GetStateFolderString(&v75);
  std::wstring::operator=(&v73, StateFolderString);
  std::wstring::~wstring(&v75);
  AppendPath(&v73);
  v20 = (_QWORD *)std::wstring::wstring(&v75, &v73);
  if ( !DesktopAppXVFS::CreatePackageDirectory(v20, v17) )
  {
    LocalFree(v17);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x362,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      v44);
  }
  v21 = GetStateFolderString(&v75);
  std::wstring::operator=(&v73, v21);
  std::wstring::~wstring(&v75);
  AppendPath(&v73);
  v22 = (_QWORD *)std::wstring::wstring(&v75, &v73);
  if ( !DesktopAppXVFS::CreatePackageDirectory(v22, v17) )
  {
    LocalFree(v17);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x36C,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      v45);
  }
  v23 = GetStateFolderString(&v75);
  std::wstring::operator=(&v73, v23);
  std::wstring::~wstring(&v75);
  AppendPath(&v73);
  v24 = (_QWORD *)std::wstring::wstring(&v75, &v73);
  if ( !DesktopAppXVFS::CreatePackageDirectory(v24, v17) )
  {
    LocalFree(v17);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x376,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      v46);
  }
  std::wstring::operator=(&v77, v79);
  AppendPath(&v77);
  AppendPath(&v77);
  if ( v72.m128i_i64[1] < 5uLL )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      Src,
      5,
      v25,
      L"Local");
  }
  else
  {
    v26 = Src;
    if ( v72.m128i_i64[1] > 7uLL )
      v26 = (void **)Src[0];
    v72.m128i_i64[0] = 5;
    memmove_0(v26, L"Local", 0xAu);
    *((_WORD *)v26 + 5) = 0;
  }
  std::wstring::_Append<unsigned short>(Src);
  v27 = GetStateFolderString(&v75);
  std::wstring::operator=(&v73, v27);
  std::wstring::~wstring(&v75);
  AppendPath(&v73);
  AppendPath(&v73);
  v65 = v73;
  v66 = v74;
  v74 = si128;
  LOWORD(v73) = 0;
  v67 = v77;
  v68 = v78;
  v78 = si128;
  LOWORD(v77) = 0;
  v75 = *(_OWORD *)Src;
  v76 = v72;
  v72.m128i_i64[0] = 0;
  v72.m128i_i64[1] = 7;
  LOWORD(Src[0]) = 0;
  if ( !DesktopAppXVFS::BuildMapping(&v75, &v67, &v65, 0x25u, ppsidGroup, ppDacl, (__int64)v17, (__int64)a1) )
  {
    LocalFree(v17);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x389,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      v47);
  }
  std::wstring::operator=(&v77, v79);
  AppendPath(&v77);
  AppendPath(&v77);
  if ( v72.m128i_i64[1] < 8uLL )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      Src,
      8,
      v28,
      L"LocalLow");
  }
  else
  {
    v29 = Src[0];
    v72.m128i_i64[0] = 8;
    memmove_0(Src[0], L"LocalLow", 0x10u);
    v29[8] = 0;
  }
  std::wstring::_Append<unsigned short>(Src);
  v30 = GetStateFolderString(&v75);
  std::wstring::operator=(&v73, v30);
  std::wstring::~wstring(&v75);
  AppendPath(&v73);
  AppendPath(&v73);
  v75 = v73;
  v76 = v74;
  v74 = si128;
  LOWORD(v73) = 0;
  v67 = v77;
  v68 = v78;
  v78 = si128;
  LOWORD(v77) = 0;
  v65 = *(_OWORD *)Src;
  v66 = v72;
  v72.m128i_i64[0] = 0;
  v72.m128i_i64[1] = 7;
  LOWORD(Src[0]) = 0;
  if ( !DesktopAppXVFS::BuildMapping(&v65, &v67, &v75, 0x25u, ppsidGroupa, ppDacla, (__int64)v17, (__int64)a1) )
  {
    LocalFree(v17);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x39C,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      v48);
  }
  std::wstring::operator=(&v77, v79);
  AppendPath(&v77);
  AppendPath(&v77);
  AppendPath(&v77);
  if ( v72.m128i_i64[1] < 8uLL )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      Src,
      8,
      v31,
      L"LocalLow");
  }
  else
  {
    v32 = Src[0];
    v72.m128i_i64[0] = 8;
    memmove_0(Src[0], L"LocalLow", 0x10u);
    v32[8] = 0;
  }
  std::wstring::_Append<unsigned short>(Src);
  std::wstring::_Append<unsigned short>(Src);
  v33 = GetStateFolderString(&v75);
  std::wstring::operator=(&v73, v33);
  std::wstring::~wstring(&v75);
  AppendPath(&v73);
  AppendPath(&v73);
  AppendPath(&v73);
  v75 = v73;
  v76 = v74;
  v74 = si128;
  LOWORD(v73) = 0;
  v67 = v77;
  v68 = v78;
  v78 = si128;
  LOWORD(v77) = 0;
  v65 = *(_OWORD *)Src;
  v66 = v72;
  v72.m128i_i64[0] = 0;
  v72.m128i_i64[1] = 7;
  LOWORD(Src[0]) = 0;
  if ( !DesktopAppXVFS::BuildMapping(&v65, &v67, &v75, 0x25u, ppsidGroupb, ppDaclb, (__int64)v17, (__int64)a1) )
  {
    LocalFree(v17);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3B2,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      v49);
  }
  v34 = GetStateFolderString(&v75);
  std::wstring::operator=(&v73, v34);
  std::wstring::~wstring(&v75);
  AppendPath(&v73);
  AppendPath(&v73);
  v35 = (_QWORD *)std::wstring::wstring(&v75, &v73);
  if ( !DesktopAppXVFS::CreatePackageDirectory(v35, v17) )
  {
    LocalFree(v17);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3BD,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      v50);
  }
  std::wstring::operator=(&v77, v79);
  AppendPath(&v77);
  AppendPath(&v77);
  AppendPath(&v77);
  if ( v72.m128i_i64[1] < 5uLL )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      Src,
      5,
      v36,
      L"Local");
  }
  else
  {
    v37 = Src;
    if ( v72.m128i_i64[1] > 7uLL )
      v37 = (void **)Src[0];
    v72.m128i_i64[0] = 5;
    memmove_0(v37, L"Local", 0xAu);
    *((_WORD *)v37 + 5) = 0;
  }
  std::wstring::_Append<unsigned short>(Src);
  std::wstring::_Append<unsigned short>(Src);
  v38 = GetStateFolderString(&v75);
  std::wstring::operator=(&v73, v38);
  std::wstring::~wstring(&v75);
  AppendPath(&v73);
  AppendPath(&v73);
  AppendPath(&v73);
  v75 = v73;
  v76 = v74;
  v74 = si128;
  LOWORD(v73) = 0;
  v67 = v77;
  v68 = v78;
  v78 = si128;
  LOWORD(v77) = 0;
  v65 = *(_OWORD *)Src;
  v66 = v72;
  v72.m128i_i64[0] = 0;
  v72.m128i_i64[1] = 7;
  LOWORD(Src[0]) = 0;
  if ( !DesktopAppXVFS::BuildMapping(&v65, &v67, &v75, 0x25u, ppsidGroupc, ppDaclc, (__int64)v17, (__int64)a1) )
  {
    LocalFree(v17);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3D3,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      v51);
  }
  std::wstring::operator=(&v77, v79);
  AppendPath(&v77);
  AppendPath(&v77);
  if ( v72.m128i_i64[1] < 5uLL )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      Src,
      5,
      v39,
      L"Local");
  }
  else
  {
    v40 = Src;
    if ( v72.m128i_i64[1] > 7uLL )
      v40 = (void **)Src[0];
    v72.m128i_i64[0] = 5;
    memmove_0(v40, L"Local", 0xAu);
    *((_WORD *)v40 + 5) = 0;
  }
  std::wstring::_Append<unsigned short>(Src);
  v41 = GetStateFolderString(&v75);
  std::wstring::operator=(&v73, v41);
  std::wstring::~wstring(&v75);
  AppendPath(&v73);
  AppendPath(&v73);
  v75 = v73;
  v76 = v74;
  v74 = si128;
  LOWORD(v73) = 0;
  v67 = v77;
  v68 = v78;
  v78 = si128;
  LOWORD(v77) = 0;
  v65 = *(_OWORD *)Src;
  v66 = v72;
  v72.m128i_i64[0] = 0;
  v72.m128i_i64[1] = 7;
  LOWORD(Src[0]) = 0;
  if ( !DesktopAppXVFS::BuildMapping(&v65, &v67, &v75, 0x25u, ppsidGroupd, ppDacld, (__int64)v17, (__int64)a1) )
  {
    LocalFree(v17);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3E6,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\desktopappxvfs.cpp",
      v43);
  }
  LocalFree(v17);
  std::wstring::~wstring(&v77);
  std::wstring::~wstring(&v73);
  std::wstring::~wstring(v81);
  std::wstring::~wstring(v79);
  std::wstring::~wstring(Src);
  if ( v11 )
    CloseState(v11);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  return a1;
}

```

## disassembly

```asm
0x180031534  mov     rax, rsp
0x180031537  mov     [rax+20h], rbx
0x18003153b  push    rbp
0x18003153c  push    rsi
0x18003153d  push    rdi
0x18003153e  push    r12
0x180031540  push    r13
0x180031542  push    r14
0x180031544  push    r15
0x180031546  lea     rbp, [rax-0E8h]
0x18003154d  sub     rsp, 1B0h
0x180031554  movaps  xmmword ptr [rax-48h], xmm6
0x180031558  mov     rax, cs:__security_cookie
0x18003155f  xor     rax, rsp
0x180031562  mov     [rbp+0E0h+var_48], rax
0x180031569  mov     r15, r8
0x18003156c  mov     rsi, rdx
0x18003156f  mov     r14, rcx
0x180031572  mov     [rbp+0E0h+var_138], rcx
0x180031576  xor     r13d, r13d
0x180031579  mov     edi, r13d
0x18003157c  mov     dword ptr [rsp+1E0h+var_190], r13d
0x180031581  mov     r12d, r13d
0x180031584  mov     [rbp+0E0h+var_148], r13
0x180031588  test    r8, r8
0x18003158b  jnz     short loc_1800315D0
0x18003158d  mov     edx, 20008h
0x180031592  lea     rcx, [rsp+1E0h+hObject]
0x180031597  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x18003159c  lea     edi, [r15+2]
0x1800315a0  lea     rdx, [rsp+1E0h+hObject]
0x1800315a5  lea     rcx, [rbp+0E0h+var_148]
0x1800315a9  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800315ae  mov     rcx, [rsp+1E0h+hObject]; hObject
0x1800315b3  lea     rax, [rcx-1]
0x1800315b7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800315bb  ja      short loc_1800315C9
0x1800315bd  call    cs:__imp_CloseHandle
0x1800315c4  nop     dword ptr [rax+rax+00h]
0x1800315c9  mov     r12, [rbp+0E0h+var_148]
0x1800315cd  mov     r15, r12
0x1800315d0  mov     [r14], r13
0x1800315d3  mov     [r14+8], r13
0x1800315d7  mov     [r14+10h], r13
0x1800315db  or      edi, 1
0x1800315de  mov     dword ptr [rsp+1E0h+var_190], edi
0x1800315e2  mov     rax, [rsi]
0x1800315e5  lea     rdx, [rbp+0E0h+var_E8]
0x1800315e9  mov     rcx, rsi
0x1800315ec  mov     rax, [rax+10h]
0x1800315f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315f5  cmp     qword ptr [rax+18h], 7
0x1800315fa  jbe     short loc_1800315FF
0x1800315fc  mov     rax, [rax]
0x1800315ff  mov     rdx, rax
0x180031602  mov     rcx, r15
0x180031605  call    cs:__imp_OpenStateExplicit
0x18003160c  nop     dword ptr [rax+rax+00h]
0x180031611  mov     rbx, rax
0x180031614  mov     [rbp+0E0h+var_130], rax
0x180031618  lea     rcx, [rbp+0E0h+var_E8]; void *
0x18003161c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180031621  mov     [rsp+1E0h+var_1A0], r13
0x180031626  mov     [rbp+0E0h+hMem], 0
0x18003162e  test    r15, r15
0x180031631  jnz     short loc_18003167D
0x180031633  mov     edx, 20008h
0x180031638  lea     rcx, [rsp+1E0h+hObject]
0x18003163d  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x180031642  or      edi, 4
0x180031645  mov     dword ptr [rsp+1E0h+var_190], edi
0x180031649  lea     rdx, [rsp+1E0h+hObject]
0x18003164e  lea     rcx, [rsp+1E0h+var_1A0]
0x180031653  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180031658  mov     rcx, [rsp+1E0h+hObject]; hObject
0x18003165d  lea     rax, [rcx-1]
0x180031661  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180031665  ja      short loc_180031673
0x180031667  call    cs:__imp_CloseHandle
0x18003166e  nop     dword ptr [rax+rax+00h]
0x180031673  mov     r13, [rsp+1E0h+var_1A0]
0x180031678  mov     rdi, r13
0x18003167b  jmp     short loc_180031680
0x18003167d  mov     rdi, r15
0x180031680  mov     rax, [rsi]
0x180031683  lea     rdx, [rbp+0E0h+var_E8]
0x180031687  mov     rcx, rsi
0x18003168a  mov     rax, [rax+10h]
0x18003168e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031693  cmp     qword ptr [rax+18h], 7
0x180031698  jbe     short loc_18003169D
0x18003169a  mov     rax, [rax]
0x18003169d  mov     rdx, rax
0x1800316a0  mov     rcx, rdi
0x1800316a3  call    cs:__imp_OpenStateExplicit
0x1800316aa  nop     dword ptr [rax+rax+00h]
0x1800316af  mov     rdi, rax
0x1800316b2  mov     [rsp+1E0h+hObject], rax
0x1800316b7  lea     rcx, [rbp+0E0h+var_E8]; void *
0x1800316bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800316c0  mov     rdx, rdi
0x1800316c3  lea     rcx, [rbp+0E0h+pObjectName]; Src
0x1800316c7  call    ?GetStateFolderString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXW4tag_STATE_PERSIST_ATTRIB@@@Z; GetStateFolderString(void *,tag_STATE_PERSIST_ATTRIB)
0x1800316cc  nop
0x1800316cd  lea     rcx, [rbp+0E0h+pObjectName]
0x1800316d1  cmp     [rbp+0E0h+var_70], 7
0x1800316d6  cmova   rcx, [rbp+0E0h+pObjectName]; pObjectName
0x1800316db  lea     rax, [rbp+0E0h+hMem]
0x1800316df  mov     [rsp+1E0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800316e4  xor     esi, esi
0x1800316e6  mov     [rsp+1E0h+ppSacl], rsi; ppSacl
0x1800316eb  mov     [rsp+1E0h+ppDacl], rsi; int
0x1800316f0  mov     [rsp+1E0h+ppsidGroup], rsi; unsigned int
0x1800316f5  xor     r9d, r9d; ppsidOwner
0x1800316f8  lea     edx, [rsi+1]; ObjectType
0x1800316fb  lea     r8d, [rsi+4]; SecurityInfo
0x1800316ff  call    cs:__imp_GetNamedSecurityInfoW
0x180031706  nop     dword ptr [rax+rax+00h]
0x18003170b  mov     rcx, [rbp+0E8h]; this
0x180031712  test    eax, eax
0x180031714  jnz     loc_1800320BA
0x18003171a  mov     rsi, [rbp+0E0h+hMem]
0x18003171e  lea     rcx, [rbp+0E0h+pObjectName]; void *
0x180031722  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180031727  nop
0x180031728  test    rdi, rdi
0x18003172b  jz      short loc_18003173D
0x18003172d  mov     rcx, rdi
0x180031730  call    cs:__imp_CloseState
0x180031737  nop     dword ptr [rax+rax+00h]
0x18003173c  nop
0x18003173d  lea     rax, [r13-1]
0x180031741  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180031745  ja      short loc_180031756
0x180031747  mov     rcx, r13; hObject
0x18003174a  call    cs:__imp_CloseHandle
0x180031751  nop     dword ptr [rax+rax+00h]
0x180031756  xorps   xmm0, xmm0
0x180031759  movups  xmmword ptr [rbp+0E0h+Src], xmm0
0x18003175d  xor     r13d, r13d
0x180031760  mov     qword ptr [rbp+0E0h+var_118], r13
0x180031764  lea     edi, [r13+7]
0x180031768  mov     qword ptr [rbp+0E0h+var_118+8], rdi
0x18003176c  mov     word ptr [rbp+0E0h+Src], r13w
0x180031771  mov     r8, r15
0x180031774  lea     rdx, FOLDERID_Profile
0x18003177b  lea     rcx, [rbp+0E0h+var_A8]
0x18003177f  call    ??$GetKnownFolderForUser@$00@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@PEAX@Z; GetKnownFolderForUser<1>(_GUID const &,void *)
0x180031784  nop
0x180031785  lea     rdx, aAppdata; "AppData"
0x18003178c  lea     rcx, [rbp+0E0h+var_A8]; Src
0x180031790  call    ?AppendPath@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; AppendPath(std::wstring &,ushort const *)
0x180031795  mov     rdx, rbx
0x180031798  lea     rcx, [rbp+0E0h+var_68]; Src
0x18003179c  call    ?GetStateRootFolderString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetStateRootFolderString(void *)
0x1800317a1  nop
0x1800317a2  xorps   xmm0, xmm0
0x1800317a5  movups  [rbp+0E0h+var_108], xmm0
0x1800317a9  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800317b1  movdqu  [rbp+0E0h+var_F8], xmm6
0x1800317b6  mov     word ptr [rbp+0E0h+var_108], r13w
0x1800317bb  movups  [rbp+0E0h+var_C8], xmm0
0x1800317bf  movdqu  [rbp+0E0h+var_B8], xmm6
0x1800317c4  mov     word ptr [rbp+0E0h+var_C8], r13w
0x1800317c9  mov     rdx, rbx
0x1800317cc  lea     rcx, [rbp+0E0h+var_E8]; Src
0x1800317d0  call    ?GetStateFolderString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXW4tag_STATE_PERSIST_ATTRIB@@@Z; GetStateFolderString(void *,tag_STATE_PERSIST_ATTRIB)
0x1800317d5  mov     rdx, rax
0x1800317d8  lea     rcx, [rbp+0E0h+var_108]
0x1800317dc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800317e1  lea     rcx, [rbp+0E0h+var_E8]; void *
0x1800317e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800317ea  lea     r15, aLocal; "Local"
0x1800317f1  mov     rdx, r15
0x1800317f4  lea     rcx, [rbp+0E0h+var_108]; Src
0x1800317f8  call    ?AppendPath@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; AppendPath(std::wstring &,ushort const *)
0x1800317fd  lea     rdx, [rbp+0E0h+var_108]
0x180031801  lea     rcx, [rbp+0E0h+var_E8]
0x180031805  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003180a  mov     rdx, rsi
0x18003180d  mov     rcx, rax
0x180031810  call    ?CreatePackageDirectory@DesktopAppXVFS@@YA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; DesktopAppXVFS::CreatePackageDirectory(std::wstring,void *)
0x180031815  test    al, al
0x180031817  jz      loc_1800320CF
0x18003181d  mov     rdx, rbx
0x180031820  lea     rcx, [rbp+0E0h+var_E8]; Src
0x180031824  call    ?GetStateFolderString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXW4tag_STATE_PERSIST_ATTRIB@@@Z; GetStateFolderString(void *,tag_STATE_PERSIST_ATTRIB)
0x180031829  mov     rdx, rax
0x18003182c  lea     rcx, [rbp+0E0h+var_108]
0x180031830  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180031835  lea     rcx, [rbp+0E0h+var_E8]; void *
0x180031839  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003183e  lea     rdx, aLocallow; "LocalLow"
0x180031845  lea     rcx, [rbp+0E0h+var_108]; Src
0x180031849  call    ?AppendPath@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; AppendPath(std::wstring &,ushort const *)
0x18003184e  lea     rdx, [rbp+0E0h+var_108]
0x180031852  lea     rcx, [rbp+0E0h+var_E8]
0x180031856  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003185b  mov     rdx, rsi
0x18003185e  mov     rcx, rax
0x180031861  call    ?CreatePackageDirectory@DesktopAppXVFS@@YA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; DesktopAppXVFS::CreatePackageDirectory(std::wstring,void *)
0x180031866  test    al, al
0x180031868  jz      loc_1800320F7
0x18003186e  mov     rdx, rbx
0x180031871  lea     rcx, [rbp+0E0h+var_E8]; Src
0x180031875  call    ?GetStateFolderString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXW4tag_STATE_PERSIST_ATTRIB@@@Z; GetStateFolderString(void *,tag_STATE_PERSIST_ATTRIB)
0x18003187a  mov     rdx, rax
0x18003187d  lea     rcx, [rbp+0E0h+var_108]
0x180031881  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180031886  lea     rcx, [rbp+0E0h+var_E8]; void *
0x18003188a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003188f  lea     rdx, aRoaming; "Roaming"
0x180031896  lea     rcx, [rbp+0E0h+var_108]; Src
0x18003189a  call    ?AppendPath@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; AppendPath(std::wstring &,ushort const *)
0x18003189f  lea     rdx, [rbp+0E0h+var_108]
0x1800318a3  lea     rcx, [rbp+0E0h+var_E8]
0x1800318a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800318ac  mov     rdx, rsi
0x1800318af  mov     rcx, rax
0x1800318b2  call    ?CreatePackageDirectory@DesktopAppXVFS@@YA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; DesktopAppXVFS::CreatePackageDirectory(std::wstring,void *)
0x1800318b7  test    al, al
0x1800318b9  jz      loc_18003211F
0x1800318bf  lea     rdx, [rbp+0E0h+var_A8]
0x1800318c3  lea     rcx, [rbp+0E0h+var_C8]
0x1800318c7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800318cc  mov     rdx, r15
0x1800318cf  lea     rcx, [rbp+0E0h+var_C8]; Src
0x1800318d3  call    ?AppendPath@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; AppendPath(std::wstring &,ushort const *)
0x1800318d8  lea     rdx, aPackages; "Packages"
0x1800318df  lea     rcx, [rbp+0E0h+var_C8]; Src
0x1800318e3  call    ?AppendPath@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; AppendPath(std::wstring &,ushort const *)
0x1800318e8  lea     eax, [rdi-2]
0x1800318eb  cmp     qword ptr [rbp+0E0h+var_118+8], rax
0x1800318ef  jb      short loc_18003191D
0x1800318f1  lea     rdi, [rbp+0E0h+Src]
0x1800318f5  cmp     qword ptr [rbp+0E0h+var_118+8], 7
0x1800318fa  cmova   rdi, [rbp+0E0h+Src]
0x1800318ff  mov     qword ptr [rbp+0E0h+var_118], rax
0x180031903  lea     r8d, [r13+0Ah]; Size
0x180031907  mov     rdx, r15; Src
0x18003190a  mov     rcx, rdi; void *
0x18003190d  call    memmove_0
0x180031912  mov     [rdi+0Ah], r13w
0x180031917  lea     edi, [r13+7]
0x18003191b  jmp     short loc_18003192C
0x18003191d  mov     r9, r15
0x180031920  mov     rdx, rax
0x180031923  lea     rcx, [rbp+0E0h+Src]
0x180031927  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18003192c  mov     r8d, 8
0x180031932  lea     rdx, aPackages; "Packages"
0x180031939  lea     rcx, [rbp+0E0h+Src]; Src
0x18003193d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180031942  mov     rdx, rbx
0x180031945  lea     rcx, [rbp+0E0h+var_E8]; Src
0x180031949  call    ?GetStateFolderString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXW4tag_STATE_PERSIST_ATTRIB@@@Z; GetStateFolderString(void *,tag_STATE_PERSIST_ATTRIB)
0x18003194e  mov     rdx, rax
0x180031951  lea     rcx, [rbp+0E0h+var_108]
0x180031955  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003195a  lea     rcx, [rbp+0E0h+var_E8]; void *
0x18003195e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180031963  mov     rdx, r15
0x180031966  lea     rcx, [rbp+0E0h+var_108]; Src
0x18003196a  call    ?AppendPath@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; AppendPath(std::wstring &,ushort const *)
0x18003196f  lea     rdx, aPackages; "Packages"
0x180031976  lea     rcx, [rbp+0E0h+var_108]; Src
0x18003197a  call    ?AppendPath@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; AppendPath(std::wstring &,ushort const *)
0x18003197f  movups  xmm0, [rbp+0E0h+var_108]
0x180031983  movups  [rsp+1E0h+var_190+8], xmm0
0x180031988  movups  xmm1, [rbp+0E0h+var_F8]
0x18003198c  movups  [rsp+1E0h+var_180+8], xmm1
0x180031991  movdqu  [rbp+0E0h+var_F8], xmm6
0x180031996  mov     word ptr [rbp+0E0h+var_108], r13w
0x18003199b  movups  xmm0, [rbp+0E0h+var_C8]
0x18003199f  movups  xmmword ptr [rsp+1E0h+var_170+8], xmm0
0x1800319a4  movups  xmm1, [rbp+0E0h+var_B8]
0x1800319a8  movups  [rbp+0E0h+var_158], xmm1
0x1800319ac  movdqu  [rbp+0E0h+var_B8], xmm6
0x1800319b1  mov     word ptr [rbp+0E0h+var_C8], r13w
0x1800319b6  movups  xmm0, xmmword ptr [rbp+0E0h+Src]
0x1800319ba  movups  [rbp+0E0h+var_E8], xmm0
0x1800319be  movups  xmm1, [rbp+0E0h+var_118]
0x1800319c2  movups  [rbp+0E0h+var_D8], xmm1
0x1800319c6  mov     qword ptr [rbp+0E0h+var_118], r13
0x1800319ca  mov     qword ptr [rbp+0E0h+var_118+8], rdi
0x1800319ce  mov     word ptr [rbp+0E0h+Src], r13w
0x1800319d3  mov     [rsp+1E0h+ppSecurityDescriptor], r14; __int64
0x1800319d8  mov     [rsp+1E0h+ppSacl], rsi; __int64
0x1800319dd  mov     r9d, 25h ; '%'
0x1800319e3  lea     r8, [rsp+1E0h+var_190+8]; void *
0x1800319e8  lea     rdx, [rsp+1E0h+var_170+8]; void *
0x1800319ed  lea     rcx, [rbp+0E0h+var_E8]; void *
0x1800319f1  call    ?BuildMapping@DesktopAppXVFS@@YA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4MappingFlags@1@I_NPEAXAEAV?$vector@UMapping@DesktopAppXVFS@@V?$allocator@UMapping@DesktopAppXVFS@@@std@@@3@@Z; DesktopAppXVFS::BuildMapping(std::wstring,std::wstring,std::wstring,DesktopAppXVFS::MappingFlags,uint,bool,void *,std::vector<DesktopAppXVFS::Mapping> &)
0x1800319f6  test    al, al
0x1800319f8  jz      loc_180032147
0x1800319fe  lea     rdx, [rbp+0E0h+var_A8]
0x180031a02  lea     rcx, [rbp+0E0h+var_C8]
0x180031a06  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180031a0b  lea     rdx, aLocallow; "LocalLow"
0x180031a12  lea     rcx, [rbp+0E0h+var_C8]; Src
  ... truncated ...
```
