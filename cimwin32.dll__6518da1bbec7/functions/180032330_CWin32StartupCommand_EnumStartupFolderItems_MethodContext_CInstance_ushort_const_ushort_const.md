# CWin32StartupCommand::EnumStartupFolderItems(MethodContext *,CInstance *,ushort const *,ushort const *)

- ea: `0x180032330`
- end: `0x1800329a6`
- name: `?EnumStartupFolderItems@CWin32StartupCommand@@IEAAJPEAVMethodContext@@PEAVCInstance@@PEBG2@Z`
- size: `1654`
- prototype: `__int64 __fastcall(CWin32StartupCommand *__hidden this, struct MethodContext *, struct CInstance *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180031b4c`
- `0x1800d38f0`

## callees

- `0x180014c58`
- `0x180015c80`
- `0x180032224`
- `0x180032330`
- `0x1800329ac`
- `0x18003a82c`
- `0x18003d7b0`
- `0x18007c6d8`
- `0x1800fc902`
- `0x1800fc980`
- `0x1800fca40`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x1800324fa`
- `msvcrt!_wsplitpath_s` at `0x180032611`
- `msvcrt!_wsplitpath_s` at `0x1800324fa`
- `msvcrt!_wsplitpath_s` at `0x180032611`
- `msvcrt!_wmakepath_s` at `0x180032543`
- `msvcrt!_wmakepath_s` at `0x18003276d`
- `msvcrt!_wmakepath_s` at `0x180032543`
- `msvcrt!_wmakepath_s` at `0x18003276d`
- `msvcrt!_wcsicmp` at `0x180032694`
- `msvcrt!_wcsicmp` at `0x1800328db`
- `msvcrt!_wcsicmp` at `0x180032694`
- `msvcrt!_wcsicmp` at `0x1800328db`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180032897`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180032897`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180032554`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180032554`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180032906`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180032906`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180032380`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18003238c`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180032398`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800323a3`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800323ae`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800326d9`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800328a6`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180032380`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18003238c`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180032398`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800323a3`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800323ae`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800326d9`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800328a6`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180032443`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003246f`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800324c0`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003251a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003266a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800326fe`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180032747`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180032831`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800328c2`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800328cf`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180032443`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003246f`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800324c0`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003251a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003266a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800326fe`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180032747`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180032831`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800328c2`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800328cf`
- `framedynos!?CreateNewInstance@Provider@@IEAAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x1800325ab`
- `framedynos!?CreateNewInstance@Provider@@IEAAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x1800325ab`
- `framedynos!?Commit@CInstance@@QEAAJXZ` at `0x180032875`
- `framedynos!?Commit@CInstance@@QEAAJXZ` at `0x180032875`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800327c7`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x180032810`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800327c7`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x180032810`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800324ad`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800324ad`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800323bc`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800323bc`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180032941`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180032941`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18003245c`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18003245c`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x180032426`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x180032426`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x1800328f5`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x1800328f5`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032631`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032648`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18003265f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18003267d`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800326b5`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800326cd`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032711`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032731`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032844`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032866`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032631`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032648`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18003265f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18003267d`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800326b5`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800326cd`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032711`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032731`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032844`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032866`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180032793`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800327a5`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800327ee`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180032793`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800327a5`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800327ee`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800327b8`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180032801`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800327b8`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180032801`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x1800323fb`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180032414`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180032438`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x1800323fb`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180032414`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180032438`
- `framedynos!?GetLocalInstancePath@Provider@@IEAA_NPEBVCInstance@@AEAVCHString@@@Z` at `0x1800323d8`
- `framedynos!?GetLocalInstancePath@Provider@@IEAA_NPEBVCInstance@@AEAVCHString@@@Z` at `0x1800328b8`
- `framedynos!?GetLocalInstancePath@Provider@@IEAA_NPEBVCInstance@@AEAVCHString@@@Z` at `0x1800323d8`
- `framedynos!?GetLocalInstancePath@Provider@@IEAA_NPEBVCInstance@@AEAVCHString@@@Z` at `0x1800328b8`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x180032484`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x180032484`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003273c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800327d2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800327dd`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003281b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032826`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032850`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800328eb`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003291b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003294c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032957`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032963`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003296f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003297b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003273c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800327d2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800327dd`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003281b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032826`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032850`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800328eb`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003291b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003294c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032957`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032963`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003296f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003297b`

## string_xrefs

- `0x18003283a`: `Command`
- `0x18003285c`: `Command`
- `0x180032401`: `Common Startup`
- `0x1800326ab`: `UserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CWin32StartupCommand::EnumStartupFolderItems(
        CWin32StartupCommand *this,
        struct MethodContext *a2,
        struct CInstance *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  Provider *v7; // rdi
  char *FirstFileW; // r14
  int v9; // esi
  __int64 v10; // rbx
  const unsigned __int16 *v11; // rax
  int CurrentKeyValue; // eax
  const unsigned __int16 *v13; // rax
  int v14; // ebx
  const wchar_t *v15; // rax
  const wchar_t *v16; // rax
  bool i; // zf
  CInstance *NewInstance; // rbx
  struct CInstance *v19; // rdi
  const unsigned __int16 *v20; // rax
  CInstance *v21; // rax
  CInstance *v22; // rdi
  const unsigned __int16 *v23; // rax
  CInstance *v24; // rax
  const wchar_t *v25; // rax
  CHString *v26; // rax
  __int64 v27; // rax
  CHString *v28; // rax
  __int64 v29; // rax
  const unsigned __int16 *v30; // rax
  const wchar_t *v31; // rdi
  const wchar_t *v32; // rax
  struct CInstance *v34; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v35[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v36[8]; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+68h] [rbp-98h]
  _BYTE v38[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[8]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v40[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v41[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v42[8]; // [rsp+90h] [rbp-70h] BYREF
  Provider *v43; // [rsp+98h] [rbp-68h]
  struct MethodContext *v44; // [rsp+A0h] [rbp-60h]
  _BYTE v45[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v46[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v47[8]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v48[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v49[8]; // [rsp+C8h] [rbp-38h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v51[608]; // [rsp+320h] [rbp+220h] BYREF
  wchar_t v52[520]; // [rsp+580h] [rbp+480h] BYREF
  unsigned __int16 v53[520]; // [rsp+990h] [rbp+890h] BYREF
  unsigned __int16 v54[528]; // [rsp+DA0h] [rbp+CA0h] BYREF
  wchar_t Drive[8]; // [rsp+11C0h] [rbp+10C0h] BYREF
  wchar_t Filename[520]; // [rsp+11D0h] [rbp+10D0h] BYREF
  wchar_t Dir[520]; // [rsp+15E0h] [rbp+14E0h] BYREF
  wchar_t Buffer[520]; // [rsp+19F0h] [rbp+18F0h] BYREF

  v44 = a2;
  v7 = this;
  v43 = this;
  CHString::CHString((CHString *)v39);
  CHString::CHString((CHString *)v38);
  CHString::CHString((CHString *)v36);
  CHString::CHString((CHString *)v49);
  CHString::CHString((CHString *)v42);
  CRegistry::CRegistry((CRegistry *)v51);
  FirstFileW = 0;
  v9 = 0;
  if ( a3 )
  {
    Provider::GetLocalInstancePath(v7, a3, (struct CHString *)v42);
    v9 = -2147217406;
  }
  if ( a5 )
  {
    v10 = -2147483645;
    CHString::operator=(v39, a4);
    CHString::operator+=(v39, L"\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders");
    CHString::operator=(v38, L"Startup");
  }
  else
  {
    v10 = -2147483646;
    CHString::operator=(v39, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders");
    CHString::operator=(v38, L"Common Startup");
  }
  v11 = (const unsigned __int16 *)CHString::operator unsigned short const *(v39);
  CurrentKeyValue = CRegistry::Open((CRegistry *)v51, (HKEY)v10, v11, 0x20019u);
  if ( CurrentKeyValue
    || (v13 = (const unsigned __int16 *)CHString::operator unsigned short const *(v38),
        (CurrentKeyValue = CRegistry::GetCurrentKeyValue((CRegistry *)v51, v13, (struct CHString *)v36)) != 0) )
  {
    v9 = WinErrorToWBEMhResult(CurrentKeyValue);
  }
  else
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    v14 = 1;
    if ( !CHString::GetLength((CHString *)v36) )
      goto LABEL_13;
    v15 = (const wchar_t *)CHString::operator unsigned short const *(v36);
    _wsplitpath_s(v15, Drive, 3u, Dir, 0x208u, 0, 0, 0, 0);
    if ( !Drive[0] || Dir[0] != 92 )
      goto LABEL_13;
    v16 = (const wchar_t *)CHString::operator unsigned short const *(v36);
    _wmakepath_s(Buffer, 0x208u, 0, v16, L"*.*", 0);
    FirstFileW = (char *)FindFirstFileW(Buffer, &FindFileData);
    for ( i = FirstFileW + 1 == 0; ; i = !FindNextFileW(FirstFileW, &FindFileData) )
    {
      v14 = i;
LABEL_13:
      if ( v14 )
        break;
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 && (FindFileData.dwFileAttributes & 2) == 0 )
      {
        memset_0(v52, 0, 0xC34u);
        v34 = 0;
        if ( a3 )
        {
          v37 = 0;
          NewInstance = a3;
          v34 = a3;
          _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_AddRef(&v34);
          v19 = a3;
        }
        else
        {
          NewInstance = Provider::CreateNewInstance(v7, v44);
          v34 = NewInstance;
          v37 = 1;
          v19 = NewInstance;
        }
        _wsplitpath_s(FindFileData.cFileName, 0, 0, 0, 0, Filename, 0x208u, 0, 0);
        if ( !v19 )
          _com_issue_error(-2147467261);
        CInstance::SetCharSplat(NewInstance, L"Name", Filename);
        CInstance::SetCharSplat(NewInstance, L"Description", Filename);
        CInstance::SetCharSplat(NewInstance, L"Caption", Filename);
        v20 = (const unsigned __int16 *)CHString::operator unsigned short const *(v38);
        CInstance::SetCharSplat(NewInstance, L"Location", v20);
        if ( a4 && _wcsicmp(a4, L".DEFAULT") )
        {
          v21 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v34);
          CInstance::SetCharSplat(v21, L"UserSID", a4);
        }
        if ( a5 )
        {
          CInstance::SetCharSplat(NewInstance, L"User", a5);
        }
        else
        {
          CHString::CHString((CHString *)v41);
          if ( GetAllUsersName((struct CHString *)v41) )
          {
            v22 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v34);
            v23 = (const unsigned __int16 *)CHString::operator unsigned short const *(v41);
            CInstance::SetCharSplat(v22, L"User", v23);
          }
          else
          {
            v24 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v34);
            CInstance::SetCharSplat(v24, L"User", L"Public");
          }
          CHString::~CHString((CHString *)v41);
        }
        v25 = (const wchar_t *)CHString::operator unsigned short const *(v36);
        _wmakepath_s(v52, 0x208u, 0, v25, FindFileData.cFileName, 0);
        if ( (int)GetIconInfo((struct CIconInfo *)v52) < 0 )
        {
          CInstance::SetCharSplat(NewInstance, L"Command", FindFileData.cFileName);
        }
        else
        {
          CHString::CHString((CHString *)v35, v53);
          v26 = CHString::CHString((CHString *)v46, L" ");
          v27 = operator+(v45, v35, v26);
          CHString::operator=(v35, v27);
          CHString::~CHString((CHString *)v45);
          CHString::~CHString((CHString *)v46);
          v28 = CHString::CHString((CHString *)v48, v54);
          v29 = operator+(v47, v35, v28);
          CHString::operator=(v35, v29);
          CHString::~CHString((CHString *)v47);
          CHString::~CHString((CHString *)v48);
          v30 = (const unsigned __int16 *)CHString::operator unsigned short const *(v35);
          CInstance::SetCharSplat(NewInstance, L"Command", v30);
          CHString::~CHString((CHString *)v35);
        }
        if ( v37 )
        {
          v9 = CInstance::Commit(NewInstance);
          if ( v9 < 0 )
            goto LABEL_34;
        }
        else
        {
          CHString::CHString((CHString *)v40);
          Provider::GetLocalInstancePath(v43, NewInstance, (struct CHString *)v40);
          v31 = (const wchar_t *)CHString::operator unsigned short const *(v42);
          v32 = (const wchar_t *)CHString::operator unsigned short const *(v40);
          if ( !_wcsicmp(v32, v31) )
          {
            v9 = 0;
            CHString::~CHString((CHString *)v40);
LABEL_34:
            _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v34);
            break;
          }
          CHString::~CHString((CHString *)v40);
        }
        CInstance::Release(NewInstance);
        v7 = v43;
      }
    }
    if ( FirstFileW )
      FindClose(FirstFileW);
  }
  CRegistry::~CRegistry((CRegistry *)v51);
  CHString::~CHString((CHString *)v42);
  CHString::~CHString((CHString *)v49);
  CHString::~CHString((CHString *)v36);
  CHString::~CHString((CHString *)v38);
  CHString::~CHString((CHString *)v39);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180032330  push    rbp
0x180032332  push    rbx
0x180032333  push    rsi
0x180032334  push    rdi
0x180032335  push    r12
0x180032337  push    r13
0x180032339  push    r14
0x18003233b  push    r15
0x18003233d  lea     rbp, [rsp-1D18h]
0x180032345  mov     eax, 1E18h
0x18003234a  call    _alloca_probe
0x18003234f  sub     rsp, rax
0x180032352  mov     rax, cs:__security_cookie
0x180032359  xor     rax, rsp
0x18003235c  mov     [rbp+1D50h+var_50], rax
0x180032363  mov     r12, r9
0x180032366  mov     r15, r8
0x180032369  mov     [rbp+1D50h+var_1DB0], rdx
0x18003236d  mov     rdi, rcx
0x180032370  mov     [rbp+1D50h+var_1DB8], rcx
0x180032374  mov     r13, [rbp+1D50h+arg_20]
0x18003237b  lea     rcx, [rsp+1E50h+var_1DD8]
0x180032380  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180032386  nop
0x180032387  lea     rcx, [rsp+1E50h+var_1DE0]
0x18003238c  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180032392  nop
0x180032393  lea     rcx, [rsp+1E50h+var_1DF0]
0x180032398  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18003239e  nop
0x18003239f  lea     rcx, [rbp+1D50h+var_1D88]
0x1800323a3  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800323a9  nop
0x1800323aa  lea     rcx, [rbp+1D50h+var_1DC0]
0x1800323ae  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800323b4  nop
0x1800323b5  lea     rcx, [rbp+1D50h+var_1B30]
0x1800323bc  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x1800323c2  nop
0x1800323c3  xor     r14d, r14d
0x1800323c6  mov     esi, r14d
0x1800323c9  test    r15, r15
0x1800323cc  jz      short loc_1800323E3
0x1800323ce  lea     r8, [rbp+1D50h+var_1DC0]
0x1800323d2  mov     rdx, r15
0x1800323d5  mov     rcx, rdi
0x1800323d8  call    cs:__imp_?GetLocalInstancePath@Provider@@IEAA_NPEBVCInstance@@AEAVCHString@@@Z; Provider::GetLocalInstancePath(CInstance const *,CHString &)
0x1800323de  mov     esi, 80041002h
0x1800323e3  lea     rcx, [rsp+1E50h+var_1DD8]
0x1800323e8  test    r13, r13
0x1800323eb  jnz     short loc_18003240A
0x1800323ed  mov     rbx, 0FFFFFFFF80000002h
0x1800323f4  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800323fb  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x180032401  lea     rdx, aCommonStartup; "Common Startup"
0x180032408  jmp     short loc_180032433
0x18003240a  mov     rbx, 0FFFFFFFF80000003h
0x180032411  mov     rdx, r12
0x180032414  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x18003241a  lea     rdx, aSoftwareMicros_1; "\\SOFTWARE\\Microsoft\\Windows\\Current"...
0x180032421  lea     rcx, [rsp+1E50h+var_1DD8]
0x180032426  call    cs:__imp_??YCHString@@QEAAAEBV0@PEBG@Z; CHString::operator+=(ushort const *)
0x18003242c  lea     rdx, aStartup; "Startup"
0x180032433  lea     rcx, [rsp+1E50h+var_1DE0]
0x180032438  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x18003243e  lea     rcx, [rsp+1E50h+var_1DD8]
0x180032443  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180032449  mov     r8, rax
0x18003244c  mov     r9d, 20019h
0x180032452  mov     rdx, rbx
0x180032455  lea     rcx, [rbp+1D50h+var_1B30]
0x18003245c  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x180032462  test    eax, eax
0x180032464  jnz     loc_180032931
0x18003246a  lea     rcx, [rsp+1E50h+var_1DE0]
0x18003246f  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180032475  mov     rdx, rax
0x180032478  lea     r8, [rsp+1E50h+var_1DF0]
0x18003247d  lea     rcx, [rbp+1D50h+var_1B30]
0x180032484  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x18003248a  test    eax, eax
0x18003248c  jnz     loc_180032931
0x180032492  xor     edx, edx; Val
0x180032494  mov     r8d, 250h; Size
0x18003249a  lea     rcx, [rbp+1D50h+FindFileData]; void *
0x18003249e  call    memset_0
0x1800324a3  mov     ebx, 1
0x1800324a8  lea     rcx, [rsp+1E50h+var_1DF0]
0x1800324ad  call    cs:__imp_?GetLength@CHString@@QEBAHXZ; CHString::GetLength(void)
0x1800324b3  test    eax, eax
0x1800324b5  jz      loc_180032568
0x1800324bb  lea     rcx, [rsp+1E50h+var_1DF0]
0x1800324c0  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800324c6  mov     rcx, rax; FullPath
0x1800324c9  xor     eax, eax
0x1800324cb  mov     [rsp+1E50h+ExtCount], rax; ExtCount
0x1800324d0  mov     [rsp+1E50h+Ext], rax; Ext
0x1800324d5  mov     [rsp+1E50h+FilenameCount], rax; FilenameCount
0x1800324da  mov     [rsp+1E50h+Filename], rax; Filename
0x1800324df  mov     [rsp+1E50h+DirCount], 208h; DirCount
0x1800324e8  lea     r9, [rbp+1D50h+Dir]; Dir
0x1800324ef  lea     r8d, [rbx+2]; DriveCount
0x1800324f3  lea     rdx, [rbp+1D50h+Drive]; Drive
0x1800324fa  call    cs:__imp__wsplitpath_s
0x180032500  xor     ecx, ecx
0x180032502  cmp     [rbp+1D50h+Drive], cx
0x180032509  jz      short loc_180032568
0x18003250b  cmp     [rbp+1D50h+Dir], 5Ch ; '\'
0x180032513  jnz     short loc_180032568
0x180032515  lea     rcx, [rsp+1E50h+var_1DF0]
0x18003251a  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180032520  mov     r9, rax; Dir
0x180032523  mov     [rsp+1E50h+Filename], r14; Ext
0x180032528  lea     rax, Filename; "*.*"
0x18003252f  mov     [rsp+1E50h+DirCount], rax; Filename
0x180032534  xor     r8d, r8d; Drive
0x180032537  mov     edx, 208h; BufferCount
0x18003253c  lea     rcx, [rbp+1D50h+Buffer]; Buffer
0x180032543  call    cs:__imp__wmakepath_s
0x180032549  lea     rdx, [rbp+1D50h+FindFileData]; lpFindFileData
0x18003254d  lea     rcx, [rbp+1D50h+Buffer]; lpFileName
0x180032554  call    cs:__imp_FindFirstFileW
0x18003255a  mov     r14, rax
0x18003255d  xor     ecx, ecx
0x18003255f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032563  mov     ebx, ecx
0x180032565  setz    bl
0x180032568  test    ebx, ebx
0x18003256a  jnz     loc_18003288B
0x180032570  test    byte ptr [rbp+1D50h+FindFileData.dwFileAttributes], 10h
0x180032574  jnz     loc_1800328FF
0x18003257a  test    byte ptr [rbp+1D50h+FindFileData.dwFileAttributes], 2
0x18003257e  jnz     loc_1800328FF
0x180032584  xor     edx, edx; Val
0x180032586  mov     r8d, 0C34h; Size
0x18003258c  lea     rcx, [rbp+1D50h+var_18D0]; void *
0x180032593  call    memset_0
0x180032598  xor     eax, eax
0x18003259a  mov     [rsp+1E50h+var_1E00], rax
0x18003259f  test    r15, r15
0x1800325a2  jnz     short loc_1800325C6
0x1800325a4  mov     rdx, [rbp+1D50h+var_1DB0]
0x1800325a8  mov     rcx, rdi
0x1800325ab  call    cs:__imp_?CreateNewInstance@Provider@@IEAAPEAVCInstance@@PEAVMethodContext@@@Z; Provider::CreateNewInstance(MethodContext *)
0x1800325b1  mov     rbx, rax
0x1800325b4  mov     [rsp+1E50h+var_1E00], rax
0x1800325b9  mov     [rsp+1E50h+var_1DE8], 1
0x1800325c1  mov     rdi, rax
0x1800325c4  jmp     short loc_1800325DF
0x1800325c6  mov     [rsp+1E50h+var_1DE8], eax
0x1800325ca  mov     rbx, r15
0x1800325cd  mov     [rsp+1E50h+var_1E00], rbx
0x1800325d2  lea     rcx, [rsp+1E50h+var_1E00]
0x1800325d7  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_AddRef(void)
0x1800325dc  mov     rdi, r15
0x1800325df  xor     ecx, ecx
0x1800325e1  mov     [rsp+1E50h+ExtCount], rcx; ExtCount
0x1800325e6  mov     [rsp+1E50h+Ext], rcx; Ext
0x1800325eb  mov     [rsp+1E50h+FilenameCount], 208h; FilenameCount
0x1800325f4  lea     rax, [rbp+1D50h+var_C80]
0x1800325fb  mov     [rsp+1E50h+Filename], rax; Filename
0x180032600  mov     [rsp+1E50h+DirCount], rcx; DirCount
0x180032605  xor     r9d, r9d; Dir
0x180032608  xor     r8d, r8d; DriveCount
0x18003260b  xor     edx, edx; Drive
0x18003260d  lea     rcx, [rbp+1D50h+FindFileData.cFileName]; FullPath
0x180032611  call    cs:__imp__wsplitpath_s
0x180032617  test    rdi, rdi
0x18003261a  jz      loc_180032926
0x180032620  lea     r8, [rbp+1D50h+var_C80]
0x180032627  lea     rdx, aName; "Name"
0x18003262e  mov     rcx, rbx
0x180032631  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180032637  lea     r8, [rbp+1D50h+var_C80]
0x18003263e  lea     rdx, aDescription; "Description"
0x180032645  mov     rcx, rbx
0x180032648  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18003264e  lea     r8, [rbp+1D50h+var_C80]
0x180032655  lea     rdx, aCaption; "Caption"
0x18003265c  mov     rcx, rbx
0x18003265f  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180032665  lea     rcx, [rsp+1E50h+var_1DE0]
0x18003266a  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180032670  mov     r8, rax
0x180032673  lea     rdx, aLocation; "Location"
0x18003267a  mov     rcx, rbx
0x18003267d  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180032683  xor     edi, edi
0x180032685  test    r12, r12
0x180032688  jz      short loc_1800326BB
0x18003268a  lea     rdx, aDefault; ".DEFAULT"
0x180032691  mov     rcx, r12; String1
0x180032694  call    cs:__imp__wcsicmp
0x18003269a  test    eax, eax
0x18003269c  jz      short loc_1800326BB
0x18003269e  lea     rcx, [rsp+1E50h+var_1E00]
0x1800326a3  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x1800326a8  mov     r8, r12
0x1800326ab  lea     rdx, aUsersid; "UserSID"
0x1800326b2  mov     rcx, rax
0x1800326b5  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800326bb  test    r13, r13
0x1800326be  jz      short loc_1800326D5
0x1800326c0  mov     r8, r13
0x1800326c3  lea     rdx, aUser; "User"
0x1800326ca  mov     rcx, rbx
0x1800326cd  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800326d3  jmp     short loc_180032742
0x1800326d5  lea     rcx, [rbp+1D50h+var_1DC8]
0x1800326d9  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800326df  nop
0x1800326e0  lea     rcx, [rbp+1D50h+var_1DC8]; struct CHString *
0x1800326e4  call    ?GetAllUsersName@@YA_NAEAVCHString@@@Z; GetAllUsersName(CHString &)
0x1800326e9  lea     rcx, [rsp+1E50h+var_1E00]
0x1800326ee  test    al, al
0x1800326f0  jz      short loc_18003271B
0x1800326f2  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x1800326f7  mov     rdi, rax
0x1800326fa  lea     rcx, [rbp+1D50h+var_1DC8]
0x1800326fe  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180032704  mov     r8, rax
0x180032707  lea     rdx, aUser; "User"
0x18003270e  mov     rcx, rdi
0x180032711  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180032717  xor     edi, edi
0x180032719  jmp     short loc_180032738
0x18003271b  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x180032720  lea     r8, aPublic_1; "Public"
0x180032727  lea     rdx, aUser; "User"
0x18003272e  mov     rcx, rax
0x180032731  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180032737  nop
0x180032738  lea     rcx, [rbp+1D50h+var_1DC8]
0x18003273c  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180032742  lea     rcx, [rsp+1E50h+var_1DF0]
0x180032747  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18003274d  mov     r9, rax; Dir
0x180032750  mov     [rsp+1E50h+Filename], rdi; Ext
0x180032755  lea     rax, [rbp+1D50h+FindFileData.cFileName]
0x180032759  mov     [rsp+1E50h+DirCount], rax; Filename
0x18003275e  xor     r8d, r8d; Drive
0x180032761  mov     edx, 208h; BufferCount
0x180032766  lea     rcx, [rbp+1D50h+var_18D0]; Buffer
0x18003276d  call    cs:__imp__wmakepath_s
0x180032773  lea     rcx, [rbp+1D50h+var_18D0]; lpParameter
0x18003277a  call    ?GetIconInfo@@YAJAEAVCIconInfo@@@Z; GetIconInfo(CIconInfo &)
0x18003277f  test    eax, eax
0x180032781  js      loc_180032858
0x180032787  lea     rdx, [rbp+1D50h+var_14C0]
0x18003278e  lea     rcx, [rsp+1E50h+var_1DF8]
0x180032793  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x180032799  nop
0x18003279a  lea     rdx, asc_18013DF28; " "
0x1800327a1  lea     rcx, [rbp+1D50h+var_1DA0]
0x1800327a5  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x1800327ab  nop
0x1800327ac  mov     r8, rax
0x1800327af  lea     rdx, [rsp+1E50h+var_1DF8]
0x1800327b4  lea     rcx, [rbp+1D50h+var_1DA8]
0x1800327b8  call    cs:__imp_??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x1800327be  nop
0x1800327bf  mov     rdx, rax
0x1800327c2  lea     rcx, [rsp+1E50h+var_1DF8]
0x1800327c7  call    cs:__imp_??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x1800327cd  nop
0x1800327ce  lea     rcx, [rbp+1D50h+var_1DA8]
0x1800327d2  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800327d8  nop
0x1800327d9  lea     rcx, [rbp+1D50h+var_1DA0]
0x1800327dd  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800327e3  lea     rdx, [rbp+1D50h+var_10B0]
0x1800327ea  lea     rcx, [rbp+1D50h+var_1D90]
0x1800327ee  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x1800327f4  nop
0x1800327f5  mov     r8, rax
0x1800327f8  lea     rdx, [rsp+1E50h+var_1DF8]
0x1800327fd  lea     rcx, [rbp+1D50h+var_1D98]
0x180032801  call    cs:__imp_??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x180032807  nop
0x180032808  mov     rdx, rax
0x18003280b  lea     rcx, [rsp+1E50h+var_1DF8]
0x180032810  call    cs:__imp_??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x180032816  nop
0x180032817  lea     rcx, [rbp+1D50h+var_1D98]
0x18003281b  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180032821  nop
0x180032822  lea     rcx, [rbp+1D50h+var_1D90]
0x180032826  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18003282c  lea     rcx, [rsp+1E50h+var_1DF8]
0x180032831  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180032837  mov     r8, rax
0x18003283a  lea     rdx, aCommand; "Command"
0x180032841  mov     rcx, rbx
0x180032844  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18003284a  nop
0x18003284b  lea     rcx, [rsp+1E50h+var_1DF8]
0x180032850  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180032856  jmp     short loc_18003286C
0x180032858  lea     r8, [rbp+1D50h+FindFileData.cFileName]
0x18003285c  lea     rdx, aCommand; "Command"
  ... truncated ...
```
