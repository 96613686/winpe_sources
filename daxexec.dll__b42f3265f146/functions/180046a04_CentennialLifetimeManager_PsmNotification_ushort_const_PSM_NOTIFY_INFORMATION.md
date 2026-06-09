# CentennialLifetimeManager::PsmNotification(ushort const *,_PSM_NOTIFY_INFORMATION *)

- ea: `0x180046a04`
- end: `0x180047027`
- name: `?PsmNotification@CentennialLifetimeManager@@AEAAXPEBGPEAU_PSM_NOTIFY_INFORMATION@@@Z`
- size: `1571`
- prototype: `void __fastcall(ClmDataStore **this, unsigned __int16 *, struct _PSM_NOTIFY_INFORMATION *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b010`

## callees

- `0x1800016e4`
- `0x180004f70`
- `0x180011e9c`
- `0x180012fb8`
- `0x180013320`
- `0x180013510`
- `0x180014e74`
- `0x180014ebc`
- `0x1800164f8`
- `0x180016b98`
- `0x1800190e0`
- `0x18001f808`
- `0x180046a04`
- `0x180047888`
- `0x1800494ac`
- `0x18004abe8`
- `0x18006096c`
- `0x1800613ac`
- `0x180061c68`
- `0x180062484`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046d4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046d4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046d2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046ce4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046ce4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046d8c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046d8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046d3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046dc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046d3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046dc2`
- `api-ms-win-core-psm-plm-l1-2-0!PsmRegisterApplicationNotification2` at `0x180046aa0`
- `api-ms-win-core-psm-plm-l1-2-0!PsmRegisterApplicationNotification2` at `0x180046aa0`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180046bc3`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180046bc3`

## pseudocode

```c
void __fastcall CentennialLifetimeManager::PsmNotification(
        ClmDataStore **this,
        unsigned __int16 *a2,
        struct _PSM_NOTIFY_INFORMATION *a3)
{
  char v6; // r15
  ClmPackageData **v7; // rbx
  _DWORD *v8; // rcx
  int v9; // r9d
  char *v10; // rax
  __int64 v11; // rcx
  ClmPackageData *v12; // rdi
  WCHAR *v13; // rdi
  const WCHAR *v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  __int128 *v19; // rax
  const WCHAR *v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // r15d
  HKEY v23; // r12
  HKEY *v24; // rsi
  HKEY v25; // r14
  DWORD LastError; // edi
  unsigned int v27; // eax
  _DWORD *v28; // rcx
  int v29; // r9d
  ClmDataStore *v30; // rbx
  int v31; // r14d
  __int64 v32; // r12
  __int64 v33; // r8
  char *ApplicationData; // rax
  HKEY v35; // rcx
  ClmPackageData **v36; // rsi
  ClmPackageData *v37; // rdi
  char v38; // r14
  HKEY v39; // rdi
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  const char *v43; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-2D8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-2D8h]
  unsigned int phkResultb; // [rsp+20h] [rbp-2D8h]
  BYTE Data[8]; // [rsp+40h] [rbp-2B8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-2B0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+50h] [rbp-2A8h] BYREF
  ClmPackageData *v50; // [rsp+58h] [rbp-2A0h]
  HKEY *p_hKey; // [rsp+60h] [rbp-298h]
  HKEY v52; // [rsp+68h] [rbp-290h] BYREF
  char v53; // [rsp+70h] [rbp-288h]
  char v54; // [rsp+78h] [rbp-280h] BYREF
  char v55; // [rsp+80h] [rbp-278h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+88h] [rbp-270h] BYREF
  __int128 v57; // [rsp+98h] [rbp-260h]
  __int128 v58; // [rsp+A8h] [rbp-250h] BYREF
  __int128 v59; // [rsp+B8h] [rbp-240h]
  _QWORD v60[42]; // [rsp+D0h] [rbp-228h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+220h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]

  v6 = 0;
  *(_DWORD *)Data = 0;
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v60,
    "PsmNotification");
  v60[0] = &DesktopAppXProvider::PsmNotification::`vftable';
  DesktopAppXProvider::PsmNotification::StartActivity((DesktopAppXProvider::PsmNotification *)v60);
  try
  {
    v7 = 0;
    v50 = 0;
    if ( *(_DWORD *)a3 == 3 )
    {
      PsmRegisterApplicationNotification2(
        4,
        *((_QWORD *)a3 + 5),
        *((unsigned int *)a3 + 12),
        a2,
        CentennialLifetimeManager::s_PsmNotification,
        this);
      v8 = (_DWORD *)*((_QWORD *)DesktopAppXProvider::Instance() + 1);
      if ( *v8 > 5u )
      {
        *(_QWORD *)Data = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v8,
          (unsigned int)word_1800E63E2,
          0,
          v9,
          (__int64)Data);
      }
      v10 = (char *)ClmDataStore::AddApplication(this[40], *((_DWORD *)a3 + 12));
      v7 = 0;
      if ( &v54 != v10 )
      {
        v7 = *(ClmPackageData ***)v10;
        *(_QWORD *)v10 = 0;
      }
      v50 = (ClmPackageData *)v7;
      v11 = *(_QWORD *)Data;
      if ( *(_QWORD *)Data )
      {
        *(_QWORD *)Data = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      v12 = v7[18];
      *(_QWORD *)Data = v12;
      if ( v12 )
        (*(void (__fastcall **)(ClmPackageData *))(*(_QWORD *)v12 + 8LL))(v12);
      CentennialLifetimeManager::QueueStatechangeNotification(this, 1);
      if ( v12 )
        (*(void (__fastcall **)(ClmPackageData *))(*(_QWORD *)v12 + 16LL))(v12);
      packageFamilyNameLength = 65;
      v13 = (WCHAR *)v7[18];
      *(_QWORD *)Data = v13;
      if ( v13 )
        (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v13 + 8LL))(v13);
      v14 = v13 + 24;
      if ( *((_QWORD *)v13 + 9) > 7u )
        v14 = *(const WCHAR **)v14;
      v15 = PackageFamilyNameFromFullName(v14, &packageFamilyNameLength, packageFamilyName);
      if ( v15 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x36D,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
          (const char *)v15,
          phkResult);
      if ( v13 )
        (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v13 + 16LL))(v13);
      v58 = 0;
      v59 = 0;
      v16 = -1;
      do
        ++v16;
      while ( packageFamilyName[v16] );
      std::wstring::_Construct<1,unsigned short const *>(&v58, packageFamilyName, v16);
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v59) < 0x61 )
        std::_Xlen_string();
      v19 = &v58;
      if ( *((_QWORD *)&v59 + 1) > 7u )
        v19 = (__int128 *)v58;
      std::wstring::wstring(
        lpSubKey,
        v17,
        v18,
        L"SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\SystemAppData\\",
        97,
        v19,
        v59);
      hKey = 0;
      p_hKey = &hKey;
      v52 = 0;
      v53 = 1;
      v20 = (const WCHAR *)lpSubKey;
      if ( *((_QWORD *)&v57 + 1) > 7u )
        v20 = lpSubKey[0];
      v21 = RegOpenKeyExW(HKEY_CURRENT_USER, v20, 0, 0x20006u, &v52);
      v22 = v21;
      if ( v21 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x379,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
          (const char *)v21,
          phkResulta);
      if ( v53 )
      {
        v23 = v52;
        v24 = p_hKey;
        v25 = *p_hKey;
        if ( *p_hKey )
        {
          LastError = GetLastError();
          RegCloseKey(v25);
          SetLastError(LastError);
        }
        *v24 = v23;
      }
      if ( !v22 )
      {
        *(_DWORD *)Data = 1;
        v27 = RegSetValueExW(hKey, L"WasEverActivated", 0, 4u, Data, 4u);
        if ( v27 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x383,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
            (const char *)v27,
            phkResultb);
      }
      if ( hKey )
        RegCloseKey(hKey);
      std::wstring::~wstring(lpSubKey);
      std::wstring::~wstring(&v58);
      goto LABEL_62;
    }
    if ( *(_DWORD *)a3 != 4 )
    {
LABEL_62:
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v60, 0);
      if ( v7 )
        (*((void (__fastcall **)(ClmPackageData **))*v7 + 2))(v7);
      v60[0] = &DesktopAppXProvider::PsmNotification::`vftable';
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v60, v40, v41, v42);
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v60);
      return;
    }
    v28 = (_DWORD *)*((_QWORD *)DesktopAppXProvider::Instance() + 1);
    if ( *v28 > 5u )
    {
      hKey = (HKEY)a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v28,
        (unsigned int)&dword_1800E63B4,
        0,
        v29,
        (__int64)&hKey);
    }
    v30 = this[40];
    v31 = *((_DWORD *)a3 + 12);
    v32 = *((_QWORD *)a3 + 5);
    *(_OWORD *)lpSubKey = 0;
    v57 = 0;
    v33 = -1;
    do
      ++v33;
    while ( a2[v33] );
    std::wstring::_Construct<1,unsigned short const *>(lpSubKey, a2, v33);
    ApplicationData = (char *)ClmDataStore::GetApplicationData(
                                (_DWORD)v30,
                                (unsigned int)&hKey,
                                (unsigned int)lpSubKey,
                                v32,
                                v31);
    v7 = 0;
    if ( &v55 != ApplicationData )
    {
      v7 = *(ClmPackageData ***)ApplicationData;
      *(_QWORD *)ApplicationData = 0;
    }
    v50 = (ClmPackageData *)v7;
    v35 = hKey;
    if ( hKey )
    {
      hKey = 0;
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)v35 + 16LL))(v35);
    }
    std::wstring::~wstring(lpSubKey);
    ClmDataStore::RemoveApplication(this[40], a2, *((void **)a3 + 5), *((_DWORD *)a3 + 12));
    v36 = v7 + 18;
    if ( v7 )
    {
      v37 = *v36;
      if ( *v36 )
        (*(void (__fastcall **)(ClmPackageData *))(*(_QWORD *)v37 + 8LL))(*v36);
      v6 = 1;
      v38 = 1;
      if ( !ClmPackageData::HasApplications(v37) )
        goto LABEL_54;
    }
    else
    {
      v37 = v50;
    }
    v38 = 0;
LABEL_54:
    if ( (v6 & 1) != 0 && v37 )
      (*(void (__fastcall **)(ClmPackageData *))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v38 )
    {
      v39 = (HKEY)*v36;
      hKey = v39;
      if ( v39 )
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)v39 + 8LL))(v39);
      CentennialLifetimeManager::QueueStatechangeNotification(this, 8);
      if ( v39 )
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)v39 + 16LL))(v39);
    }
    goto LABEL_62;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x394,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
      v43);
  }
}

```

## disassembly

```asm
0x180046a04  push    rbx
0x180046a06  push    rsi
0x180046a07  push    rdi
0x180046a08  push    r12
0x180046a0a  push    r13
0x180046a0c  push    r14
0x180046a0e  push    r15
0x180046a10  sub     rsp, 2C0h
0x180046a17  mov     rax, cs:__security_cookie
0x180046a1e  xor     rax, rsp
0x180046a21  mov     [rsp+2F8h+var_48], rax
0x180046a29  mov     rdi, r8
0x180046a2c  mov     rsi, rdx
0x180046a2f  mov     r13, rcx
0x180046a32  xor     r12d, r12d
0x180046a35  mov     r15d, r12d
0x180046a38  mov     dword ptr [rsp+2F8h+Data], r12d
0x180046a3d  lea     rdx, aPsmnotificatio; "PsmNotification"
0x180046a44  lea     rcx, [rsp+2F8h+var_228]
0x180046a4c  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180046a51  lea     rax, ??_7PsmNotification@DesktopAppXProvider@@6B@; const DesktopAppXProvider::PsmNotification::`vftable'
0x180046a58  mov     [rsp+2F8h+var_228], rax
0x180046a60  lea     rcx, [rsp+2F8h+var_228]; this
0x180046a68  call    ?StartActivity@PsmNotification@DesktopAppXProvider@@QEAAXXZ; DesktopAppXProvider::PsmNotification::StartActivity(void)
0x180046a6d  nop
0x180046a6e  mov     ebx, r12d
0x180046a71  mov     [rsp+2F8h+var_2A0], rbx
0x180046a76  cmp     dword ptr [rdi], 3
0x180046a79  jnz     loc_180046DEE
0x180046a7f  mov     qword ptr [rsp+2F8h+cbData], r13
0x180046a84  lea     rax, ?s_PsmNotification@CentennialLifetimeManager@@CAXPEBGPEAU_PSM_NOTIFY_INFORMATION@@PEAX@Z; CentennialLifetimeManager::s_PsmNotification(ushort const *,_PSM_NOTIFY_INFORMATION *,void *)
0x180046a8b  mov     [rsp+2F8h+phkResult], rax
0x180046a90  mov     r9, rsi
0x180046a93  mov     r8d, [rdi+30h]
0x180046a97  mov     rdx, [rdi+28h]
0x180046a9b  lea     ecx, [r12+4]
0x180046aa0  call    cs:__imp_PsmRegisterApplicationNotification2
0x180046aa7  nop     dword ptr [rax+rax+00h]
0x180046aac  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x180046ab1  mov     rcx, [rax+8]
0x180046ab5  mov     eax, [rcx]
0x180046ab7  cmp     eax, 5
0x180046aba  jbe     short loc_180046ADA
0x180046abc  mov     qword ptr [rsp+2F8h+Data], rsi
0x180046ac1  lea     rax, [rsp+2F8h+Data]
0x180046ac6  mov     [rsp+2F8h+phkResult], rax
0x180046acb  xor     r8d, r8d
0x180046ace  lea     rdx, word_1800E63E2
0x180046ad5  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180046ada  mov     eax, [rdi+30h]
0x180046add  mov     dword ptr [rsp+2F8h+phkResult], eax; unsigned int
0x180046ae1  mov     r9, [rdi+28h]
0x180046ae5  mov     r8, rsi
0x180046ae8  lea     rdx, [rsp+2F8h+Data]
0x180046aed  mov     rcx, [r13+140h]; this
0x180046af4  call    ?AddApplication@ClmDataStore@@QEAA?AV?$ComPtr@VClmApplicationData@@@WRL@Microsoft@@PEBGPEAXK@Z; ClmDataStore::AddApplication(ushort const *,void *,ulong)
0x180046af9  mov     rbx, r12
0x180046afc  lea     rcx, [rsp+2F8h+var_280]
0x180046b01  cmp     rcx, rax
0x180046b04  jz      short loc_180046B0C
0x180046b06  mov     rbx, [rax]
0x180046b09  mov     [rax], r12
0x180046b0c  mov     [rsp+2F8h+var_2A0], rbx
0x180046b11  mov     rcx, qword ptr [rsp+2F8h+Data]
0x180046b16  test    rcx, rcx
0x180046b19  jz      short loc_180046B2D
0x180046b1b  mov     qword ptr [rsp+2F8h+Data], r12
0x180046b20  mov     rax, [rcx]
0x180046b23  mov     rax, [rax+10h]
0x180046b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b2c  nop
0x180046b2d  mov     rdi, [rbx+90h]
0x180046b34  mov     qword ptr [rsp+2F8h+Data], rdi
0x180046b39  test    rdi, rdi
0x180046b3c  jz      short loc_180046B4E
0x180046b3e  mov     rax, [rdi]
0x180046b41  mov     rcx, rdi
0x180046b44  mov     rax, [rax+8]
0x180046b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b4d  nop
0x180046b4e  lea     r8, [rdi+30h]
0x180046b52  cmp     qword ptr [r8+18h], 7
0x180046b57  jbe     short loc_180046B5C
0x180046b59  mov     r8, [r8]
0x180046b5c  mov     edx, 1
0x180046b61  mov     rcx, r13
0x180046b64  call    ?QueueStatechangeNotification@CentennialLifetimeManager@@AEAAXW4PLM_STATE_CHANGE@@PEBG@Z; CentennialLifetimeManager::QueueStatechangeNotification(PLM_STATE_CHANGE,ushort const *)
0x180046b69  nop
0x180046b6a  test    rdi, rdi
0x180046b6d  jz      short loc_180046B7F
0x180046b6f  mov     rax, [rdi]
0x180046b72  mov     rcx, rdi
0x180046b75  mov     rax, [rax+10h]
0x180046b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b7e  nop
0x180046b7f  mov     [rsp+2F8h+packageFamilyNameLength], 41h ; 'A'
0x180046b87  mov     rdi, [rbx+90h]
0x180046b8e  mov     qword ptr [rsp+2F8h+Data], rdi
0x180046b93  test    rdi, rdi
0x180046b96  jz      short loc_180046BA8
0x180046b98  mov     rax, [rdi]
0x180046b9b  mov     rcx, rdi
0x180046b9e  mov     rax, [rax+8]
0x180046ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ba7  nop
0x180046ba8  lea     rcx, [rdi+30h]
0x180046bac  cmp     qword ptr [rcx+18h], 7
0x180046bb1  jbe     short loc_180046BB6
0x180046bb3  mov     rcx, [rcx]; packageFullName
0x180046bb6  lea     r8, [rsp+2F8h+packageFamilyName]; packageFamilyName
0x180046bbe  lea     rdx, [rsp+2F8h+packageFamilyNameLength]; packageFamilyNameLength
0x180046bc3  call    cs:__imp_PackageFamilyNameFromFullName
0x180046bca  nop     dword ptr [rax+rax+00h]
0x180046bcf  mov     rcx, [rsp+2F8h]; this
0x180046bd7  test    eax, eax
0x180046bd9  jnz     loc_18004700B
0x180046bdf  test    rdi, rdi
0x180046be2  jz      short loc_180046BF4
0x180046be4  mov     rax, [rdi]
0x180046be7  mov     rcx, rdi
0x180046bea  mov     rax, [rax+10h]
0x180046bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046bf3  nop
0x180046bf4  xorps   xmm0, xmm0
0x180046bf7  movups  [rsp+2F8h+var_250], xmm0
0x180046bff  xorps   xmm1, xmm1
0x180046c02  movdqu  [rsp+2F8h+var_240], xmm1
0x180046c0b  lea     rax, [rsp+2F8h+packageFamilyName]
0x180046c13  or      r8, 0FFFFFFFFFFFFFFFFh
0x180046c17  inc     r8
0x180046c1a  cmp     [rax+r8*2], r12w
0x180046c1f  jnz     short loc_180046C17
0x180046c21  lea     rdx, [rsp+2F8h+packageFamilyName]
0x180046c29  lea     rcx, [rsp+2F8h+var_250]
0x180046c31  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180046c36  nop
0x180046c37  mov     rcx, qword ptr [rsp+2F8h+var_240]
0x180046c3f  mov     rax, 7FFFFFFFFFFFFFFEh
0x180046c49  sub     rax, rcx
0x180046c4c  cmp     rax, 61h ; 'a'
0x180046c50  jb      loc_180047020
0x180046c56  lea     rax, [rsp+2F8h+var_250]
0x180046c5e  cmp     qword ptr [rsp+2F8h+var_240+8], 7
0x180046c67  cmova   rax, qword ptr [rsp+2F8h+var_250]
0x180046c70  mov     [rsp+2F8h+var_2C8], rcx
0x180046c75  mov     qword ptr [rsp+2F8h+cbData], rax
0x180046c7a  mov     [rsp+2F8h+phkResult], 61h ; 'a'
0x180046c83  lea     r9, aSoftwareClasse_0; "SOFTWARE\\Classes\\Local Settings\\Soft"...
0x180046c8a  lea     rcx, [rsp+2F8h+lpSubKey]
0x180046c92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180046c97  mov     [rsp+2F8h+hKey], r12
0x180046c9c  lea     rax, [rsp+2F8h+hKey]
0x180046ca1  mov     [rsp+2F8h+var_298], rax
0x180046ca6  mov     [rsp+2F8h+var_290], r12
0x180046cab  mov     [rsp+2F8h+var_288], 1
0x180046cb0  lea     rdx, [rsp+2F8h+lpSubKey]
0x180046cb8  cmp     [rsp+2F8h+var_258], 7
0x180046cc1  cmova   rdx, [rsp+2F8h+lpSubKey]; lpSubKey
0x180046cca  lea     rax, [rsp+2F8h+var_290]
0x180046ccf  mov     [rsp+2F8h+phkResult], rax; unsigned int
0x180046cd4  mov     r9d, 20006h; samDesired
0x180046cda  xor     r8d, r8d; ulOptions
0x180046cdd  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180046ce4  call    cs:__imp_RegOpenKeyExW
0x180046ceb  nop     dword ptr [rax+rax+00h]
0x180046cf0  mov     r15d, eax
0x180046cf3  mov     rcx, [rsp+2F8h]; this
0x180046cfb  test    eax, eax
0x180046cfd  jz      short loc_180046D13
0x180046cff  mov     r9d, eax; char *
0x180046d02  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\execmodel\\des"...
0x180046d09  mov     edx, 379h; void *
0x180046d0e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180046d13  cmp     [rsp+2F8h+var_288], r12b
0x180046d18  jz      short loc_180046D5A
0x180046d1a  mov     r12, [rsp+2F8h+var_290]
0x180046d1f  mov     rsi, [rsp+2F8h+var_298]
0x180046d24  mov     r14, [rsi]
0x180046d27  test    r14, r14
0x180046d2a  jz      short loc_180046D57
0x180046d2c  call    cs:__imp_GetLastError
0x180046d33  nop     dword ptr [rax+rax+00h]
0x180046d38  mov     edi, eax
0x180046d3a  mov     rcx, r14; hKey
0x180046d3d  call    cs:__imp_RegCloseKey
0x180046d44  nop     dword ptr [rax+rax+00h]
0x180046d49  mov     ecx, edi; dwErrCode
0x180046d4b  call    cs:__imp_SetLastError
0x180046d52  nop     dword ptr [rax+rax+00h]
0x180046d57  mov     [rsi], r12
0x180046d5a  test    r15d, r15d
0x180046d5d  jnz     short loc_180046DB8
0x180046d5f  mov     dword ptr [rsp+2F8h+Data], 1
0x180046d67  mov     [rsp+2F8h+cbData], 4; cbData
0x180046d6f  lea     rax, [rsp+2F8h+Data]
0x180046d74  mov     [rsp+2F8h+phkResult], rax; unsigned int
0x180046d79  lea     r9d, [r15+4]; dwType
0x180046d7d  xor     r8d, r8d; Reserved
0x180046d80  lea     rdx, ValueName; "WasEverActivated"
0x180046d87  mov     rcx, [rsp+2F8h+hKey]; hKey
0x180046d8c  call    cs:__imp_RegSetValueExW
0x180046d93  nop     dword ptr [rax+rax+00h]
0x180046d98  mov     rcx, [rsp+2F8h]; this
0x180046da0  test    eax, eax
0x180046da2  jz      short loc_180046DB8
0x180046da4  mov     r9d, eax; char *
0x180046da7  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\execmodel\\des"...
0x180046dae  mov     edx, 383h; void *
0x180046db3  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180046db8  mov     rcx, [rsp+2F8h+hKey]; hKey
0x180046dbd  test    rcx, rcx
0x180046dc0  jz      short loc_180046DCE
0x180046dc2  call    cs:__imp_RegCloseKey
0x180046dc9  nop     dword ptr [rax+rax+00h]
0x180046dce  lea     rcx, [rsp+2F8h+lpSubKey]; void *
0x180046dd6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180046ddb  nop
0x180046ddc  lea     rcx, [rsp+2F8h+var_250]; void *
0x180046de4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180046de9  jmp     loc_180046F98
0x180046dee  cmp     dword ptr [rdi], 4
0x180046df1  jnz     loc_180046F98
0x180046df7  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x180046dfc  mov     rcx, [rax+8]
0x180046e00  mov     eax, [rcx]
0x180046e02  cmp     eax, 5
0x180046e05  jbe     short loc_180046E25
0x180046e07  mov     [rsp+2F8h+hKey], rsi
0x180046e0c  lea     rax, [rsp+2F8h+hKey]
0x180046e11  mov     [rsp+2F8h+phkResult], rax
0x180046e16  xor     r8d, r8d
0x180046e19  lea     rdx, dword_1800E63B4
0x180046e20  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180046e25  mov     rbx, [r13+140h]
0x180046e2c  mov     r14d, [rdi+30h]
0x180046e30  mov     r12, [rdi+28h]
0x180046e34  xorps   xmm0, xmm0
0x180046e37  movups  xmmword ptr [rsp+2F8h+lpSubKey], xmm0
0x180046e3f  xorps   xmm1, xmm1
0x180046e42  movdqu  xmmword ptr [rsp+98h], xmm1
0x180046e4b  or      r8, 0FFFFFFFFFFFFFFFFh
0x180046e4f  xor     eax, eax
0x180046e51  inc     r8
0x180046e54  cmp     [rsi+r8*2], ax
0x180046e59  jnz     short loc_180046E51
0x180046e5b  mov     rdx, rsi
0x180046e5e  lea     rcx, [rsp+2F8h+lpSubKey]
0x180046e66  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180046e6b  nop
0x180046e6c  mov     dword ptr [rsp+2F8h+phkResult], r14d
0x180046e71  mov     r9, r12
0x180046e74  lea     r8, [rsp+2F8h+lpSubKey]
0x180046e7c  lea     rdx, [rsp+2F8h+hKey]
0x180046e81  mov     rcx, rbx
0x180046e84  call    ?GetApplicationData@ClmDataStore@@QEBA?AV?$ComPtr@VClmApplicationData@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAXK@Z; ClmDataStore::GetApplicationData(std::wstring const &,void * const,ulong)
0x180046e89  xor     r12d, r12d
0x180046e8c  mov     ebx, r12d
0x180046e8f  lea     rcx, [rsp+2F8h+var_278]
0x180046e97  cmp     rcx, rax
0x180046e9a  jz      short loc_180046EA2
0x180046e9c  mov     rbx, [rax]
0x180046e9f  mov     [rax], r12
0x180046ea2  mov     [rsp+2F8h+var_2A0], rbx
0x180046ea7  mov     rcx, [rsp+2F8h+hKey]
0x180046eac  test    rcx, rcx
0x180046eaf  jz      short loc_180046EC3
0x180046eb1  mov     [rsp+2F8h+hKey], r12
0x180046eb6  mov     rax, [rcx]
0x180046eb9  mov     rax, [rax+10h]
0x180046ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ec2  nop
0x180046ec3  lea     rcx, [rsp+2F8h+lpSubKey]; void *
0x180046ecb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180046ed0  mov     r9d, [rdi+30h]; unsigned int
0x180046ed4  mov     r8, [rdi+28h]; void *
0x180046ed8  mov     rdx, rsi; unsigned __int16 *
0x180046edb  mov     rcx, [r13+140h]; this
0x180046ee2  call    ?RemoveApplication@ClmDataStore@@QEAAXPEBGPEAXK@Z; ClmDataStore::RemoveApplication(ushort const *,void *,ulong)
0x180046ee7  lea     rsi, [rbx+90h]
0x180046eee  test    rbx, rbx
0x180046ef1  jnz     short loc_180046EFA
0x180046ef3  mov     rdi, [rsp+2F8h+var_2A0]
0x180046ef8  jmp     short loc_180046F27
0x180046efa  mov     rdi, [rsi]
0x180046efd  test    rdi, rdi
0x180046f00  jz      short loc_180046F12
0x180046f02  mov     rax, [rdi]
0x180046f05  mov     rcx, rdi
0x180046f08  mov     rax, [rax+8]
0x180046f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f11  nop
0x180046f12  mov     r15d, 1
0x180046f18  mov     rcx, rdi; this
0x180046f1b  call    ?HasApplications@ClmPackageData@@QEBA_NXZ; ClmPackageData::HasApplications(void)
0x180046f20  test    al, al
0x180046f22  mov     r14b, r15b
0x180046f25  jz      short loc_180046F2A
0x180046f27  mov     r14b, r12b
0x180046f2a  test    r15b, 1
0x180046f2e  jz      short loc_180046F45
  ... truncated ...
```
