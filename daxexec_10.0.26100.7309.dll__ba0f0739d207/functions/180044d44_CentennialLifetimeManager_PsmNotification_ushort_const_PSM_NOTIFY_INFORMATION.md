# CentennialLifetimeManager::PsmNotification(ushort const *,_PSM_NOTIFY_INFORMATION *)

- ea: `0x180044d44`
- end: `0x180045331`
- name: `?PsmNotification@CentennialLifetimeManager@@AEAAXPEBGPEAU_PSM_NOTIFY_INFORMATION@@@Z`
- size: `1517`
- prototype: `void __fastcall(CentennialLifetimeManager *__hidden this, const unsigned __int16 *, struct _PSM_NOTIFY_INFORMATION *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x180049440`

## callees

- `0x1800016e0`
- `0x1800053a0`
- `0x18001031c`
- `0x180011300`
- `0x1800116b0`
- `0x180011820`
- `0x1800118c0`
- `0x180013100`
- `0x180013148`
- `0x1800148e8`
- `0x180014f4c`
- `0x18001748c`
- `0x18001ec94`
- `0x180044d44`
- `0x180045ba8`
- `0x180047804`
- `0x180048f40`
- `0x18005ee7c`
- `0x18005f89c`
- `0x1800601b4`
- `0x180060a88`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800450ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800450ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045026`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045026`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045098`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045098`
- `api-ms-win-core-psm-plm-l1-2-0!PsmRegisterApplicationNotification2` at `0x180044de0`
- `api-ms-win-core-psm-plm-l1-2-0!PsmRegisterApplicationNotification2` at `0x180044de0`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180044f01`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180044f01`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
  void **v17; // rax
  const WCHAR *v18; // rdx
  unsigned int v19; // eax
  char v20; // di
  unsigned int v21; // eax
  _DWORD *v22; // rcx
  int v23; // r9d
  ClmDataStore *v24; // rbx
  int v25; // r14d
  __int64 v26; // r12
  __int64 v27; // r8
  char *ApplicationData; // rax
  HKEY v29; // rcx
  ClmPackageData **v30; // rsi
  ClmPackageData *v31; // rdi
  char v32; // r14
  HKEY v33; // rdi
  const char *v34; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-2D8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-2D8h]
  unsigned int phkResultb; // [rsp+20h] [rbp-2D8h]
  BYTE Data[8]; // [rsp+40h] [rbp-2B8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-2B0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+50h] [rbp-2A8h] BYREF
  ClmPackageData *v41; // [rsp+58h] [rbp-2A0h]
  HKEY *p_hKey; // [rsp+60h] [rbp-298h] BYREF
  HKEY v43; // [rsp+68h] [rbp-290h] BYREF
  char v44; // [rsp+70h] [rbp-288h]
  char v45; // [rsp+78h] [rbp-280h] BYREF
  char v46; // [rsp+80h] [rbp-278h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+88h] [rbp-270h] BYREF
  __int128 v48; // [rsp+98h] [rbp-260h]
  void *Src[2]; // [rsp+A8h] [rbp-250h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-240h]
  unsigned __int64 v51; // [rsp+C0h] [rbp-238h]
  _QWORD v52[42]; // [rsp+D0h] [rbp-228h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+220h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]

  v6 = 0;
  *(_DWORD *)Data = 0;
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v52,
    "PsmNotification");
  v52[0] = &DesktopAppXProvider::PsmNotification::`vftable';
  DesktopAppXProvider::PsmNotification::StartActivity((DesktopAppXProvider::PsmNotification *)v52);
  try
  {
    v7 = 0;
    v41 = 0;
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
          (unsigned int)&unk_1800E4AAA,
          0,
          v9,
          (__int64)Data);
      }
      v10 = (char *)ClmDataStore::AddApplication(this[40], *((_DWORD *)a3 + 12));
      v7 = 0;
      if ( &v45 != v10 )
      {
        v7 = *(ClmPackageData ***)v10;
        *(_QWORD *)v10 = 0;
      }
      v41 = (ClmPackageData *)v7;
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
      *(_OWORD *)Src = 0;
      v50 = 0;
      v51 = 0;
      v16 = -1;
      do
        ++v16;
      while ( packageFamilyName[v16] );
      std::wstring::_Construct<1,unsigned short const *>(Src, packageFamilyName, v16);
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v50) < 0x61 )
        std::_Xlen_string();
      v17 = Src;
      if ( v51 > 7 )
        v17 = (void **)Src[0];
      std::wstring::wstring(lpSubKey, 97, v17, v50);
      hKey = 0;
      p_hKey = &hKey;
      v43 = 0;
      v44 = 1;
      v18 = (const WCHAR *)lpSubKey;
      if ( *((_QWORD *)&v48 + 1) > 7u )
        v18 = lpSubKey[0];
      v19 = RegOpenKeyExW(HKEY_CURRENT_USER, v18, 0, 0x20006u, &v43);
      if ( v19 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x379,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
          (const char *)v19,
          phkResulta);
        v20 = 0;
      }
      else
      {
        v20 = 1;
      }
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
      if ( v20 )
      {
        *(_DWORD *)Data = 1;
        v21 = RegSetValueExW(hKey, L"WasEverActivated", 0, 4u, Data, 4u);
        if ( v21 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x383,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
            (const char *)v21,
            phkResultb);
      }
      if ( hKey )
        RegCloseKey(hKey);
      std::wstring::~wstring(lpSubKey);
      std::wstring::~wstring(Src);
      goto LABEL_59;
    }
    if ( *(_DWORD *)a3 != 4 )
    {
LABEL_59:
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v52, 0);
      if ( v7 )
        (*((void (__fastcall **)(ClmPackageData **))*v7 + 2))(v7);
      v52[0] = &DesktopAppXProvider::PsmNotification::`vftable';
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v52);
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v52);
      return;
    }
    v22 = (_DWORD *)*((_QWORD *)DesktopAppXProvider::Instance() + 1);
    if ( *v22 > 5u )
    {
      hKey = (HKEY)a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v22,
        (unsigned int)&unk_1800E4A7C,
        0,
        v23,
        (__int64)&hKey);
    }
    v24 = this[40];
    v25 = *((_DWORD *)a3 + 12);
    v26 = *((_QWORD *)a3 + 5);
    *(_OWORD *)lpSubKey = 0;
    v48 = 0;
    v27 = -1;
    do
      ++v27;
    while ( a2[v27] );
    std::wstring::_Construct<1,unsigned short const *>(lpSubKey, a2, v27);
    ApplicationData = (char *)ClmDataStore::GetApplicationData(
                                (_DWORD)v24,
                                (unsigned int)&hKey,
                                (unsigned int)lpSubKey,
                                v26,
                                v25);
    v7 = 0;
    if ( &v46 != ApplicationData )
    {
      v7 = *(ClmPackageData ***)ApplicationData;
      *(_QWORD *)ApplicationData = 0;
    }
    v41 = (ClmPackageData *)v7;
    v29 = hKey;
    if ( hKey )
    {
      hKey = 0;
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)v29 + 16LL))(v29);
    }
    std::wstring::~wstring(lpSubKey);
    ClmDataStore::RemoveApplication(this[40], a2, *((void **)a3 + 5), *((_DWORD *)a3 + 12));
    v30 = v7 + 18;
    if ( v7 )
    {
      v31 = *v30;
      if ( *v30 )
        (*(void (__fastcall **)(ClmPackageData *))(*(_QWORD *)v31 + 8LL))(*v30);
      v6 = 1;
      v32 = 1;
      if ( !ClmPackageData::HasApplications(v31) )
        goto LABEL_51;
    }
    else
    {
      v31 = v41;
    }
    v32 = 0;
LABEL_51:
    if ( (v6 & 1) != 0 && v31 )
      (*(void (__fastcall **)(ClmPackageData *))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v32 )
    {
      v33 = (HKEY)*v30;
      hKey = v33;
      if ( v33 )
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)v33 + 8LL))(v33);
      CentennialLifetimeManager::QueueStatechangeNotification(this, 8);
      if ( v33 )
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)v33 + 16LL))(v33);
    }
    goto LABEL_59;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x394,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
      v34);
  }
}

```

## disassembly

```asm
0x180044d44  push    rbx
0x180044d46  push    rsi
0x180044d47  push    rdi
0x180044d48  push    r12
0x180044d4a  push    r13
0x180044d4c  push    r14
0x180044d4e  push    r15
0x180044d50  sub     rsp, 2C0h
0x180044d57  mov     rax, cs:__security_cookie
0x180044d5e  xor     rax, rsp
0x180044d61  mov     [rsp+2F8h+var_48], rax
0x180044d69  mov     rsi, r8
0x180044d6c  mov     rdi, rdx
0x180044d6f  mov     r13, rcx
0x180044d72  xor     r12d, r12d
0x180044d75  mov     r15d, r12d
0x180044d78  mov     dword ptr [rsp+2F8h+Data], r12d
0x180044d7d  lea     rdx, aPsmnotificatio; "PsmNotification"
0x180044d84  lea     rcx, [rsp+2F8h+var_228]
0x180044d8c  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180044d91  lea     r14, ??_7PsmNotification@DesktopAppXProvider@@6B@; const DesktopAppXProvider::PsmNotification::`vftable'
0x180044d98  mov     [rsp+2F8h+var_228], r14
0x180044da0  lea     rcx, [rsp+2F8h+var_228]; this
0x180044da8  call    ?StartActivity@PsmNotification@DesktopAppXProvider@@QEAAXXZ; DesktopAppXProvider::PsmNotification::StartActivity(void)
0x180044dad  nop
0x180044dae  mov     ebx, r12d
0x180044db1  mov     [rsp+2F8h+var_2A0], rbx
0x180044db6  cmp     dword ptr [rsi], 3
0x180044db9  jnz     loc_1800450FA
0x180044dbf  mov     qword ptr [rsp+2F8h+cbData], r13
0x180044dc4  lea     rax, ?s_PsmNotification@CentennialLifetimeManager@@CAXPEBGPEAU_PSM_NOTIFY_INFORMATION@@PEAX@Z; CentennialLifetimeManager::s_PsmNotification(ushort const *,_PSM_NOTIFY_INFORMATION *,void *)
0x180044dcb  mov     [rsp+2F8h+phkResult], rax
0x180044dd0  mov     r9, rdi
0x180044dd3  mov     r8d, [rsi+30h]
0x180044dd7  mov     rdx, [rsi+28h]
0x180044ddb  lea     ecx, [r12+4]
0x180044de0  call    cs:__imp_PsmRegisterApplicationNotification2
0x180044de7  nop     dword ptr [rax+rax+00h]
0x180044dec  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x180044df1  mov     rcx, [rax+8]
0x180044df5  cmp     dword ptr [rcx], 5
0x180044df8  jbe     short loc_180044E18
0x180044dfa  mov     qword ptr [rsp+2F8h+Data], rdi
0x180044dff  lea     rax, [rsp+2F8h+Data]
0x180044e04  mov     [rsp+2F8h+phkResult], rax
0x180044e09  xor     r8d, r8d
0x180044e0c  lea     rdx, unk_1800E4AAA
0x180044e13  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180044e18  mov     eax, [rsi+30h]
0x180044e1b  mov     dword ptr [rsp+2F8h+phkResult], eax; unsigned int
0x180044e1f  mov     r9, [rsi+28h]
0x180044e23  mov     r8, rdi
0x180044e26  lea     rdx, [rsp+2F8h+Data]
0x180044e2b  mov     rcx, [r13+140h]; this
0x180044e32  call    ?AddApplication@ClmDataStore@@QEAA?AV?$ComPtr@VClmApplicationData@@@WRL@Microsoft@@PEBGPEAXK@Z; ClmDataStore::AddApplication(ushort const *,void *,ulong)
0x180044e37  mov     rbx, r12
0x180044e3a  lea     rcx, [rsp+2F8h+var_280]
0x180044e3f  cmp     rcx, rax
0x180044e42  jz      short loc_180044E4A
0x180044e44  mov     rbx, [rax]
0x180044e47  mov     [rax], r12
0x180044e4a  mov     [rsp+2F8h+var_2A0], rbx
0x180044e4f  mov     rcx, qword ptr [rsp+2F8h+Data]
0x180044e54  test    rcx, rcx
0x180044e57  jz      short loc_180044E6B
0x180044e59  mov     qword ptr [rsp+2F8h+Data], r12
0x180044e5e  mov     rax, [rcx]
0x180044e61  mov     rax, [rax+10h]
0x180044e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e6a  nop
0x180044e6b  mov     rdi, [rbx+90h]
0x180044e72  mov     qword ptr [rsp+2F8h+Data], rdi
0x180044e77  test    rdi, rdi
0x180044e7a  jz      short loc_180044E8C
0x180044e7c  mov     rax, [rdi]
0x180044e7f  mov     rcx, rdi
0x180044e82  mov     rax, [rax+8]
0x180044e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e8b  nop
0x180044e8c  lea     r8, [rdi+30h]
0x180044e90  cmp     qword ptr [r8+18h], 7
0x180044e95  jbe     short loc_180044E9A
0x180044e97  mov     r8, [r8]
0x180044e9a  mov     edx, 1
0x180044e9f  mov     rcx, r13
0x180044ea2  call    ?QueueStatechangeNotification@CentennialLifetimeManager@@AEAAXW4PLM_STATE_CHANGE@@PEBG@Z; CentennialLifetimeManager::QueueStatechangeNotification(PLM_STATE_CHANGE,ushort const *)
0x180044ea7  nop
0x180044ea8  test    rdi, rdi
0x180044eab  jz      short loc_180044EBD
0x180044ead  mov     rax, [rdi]
0x180044eb0  mov     rcx, rdi
0x180044eb3  mov     rax, [rax+10h]
0x180044eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ebc  nop
0x180044ebd  mov     [rsp+2F8h+packageFamilyNameLength], 41h ; 'A'
0x180044ec5  mov     rdi, [rbx+90h]
0x180044ecc  mov     qword ptr [rsp+2F8h+Data], rdi
0x180044ed1  test    rdi, rdi
0x180044ed4  jz      short loc_180044EE6
0x180044ed6  mov     rax, [rdi]
0x180044ed9  mov     rcx, rdi
0x180044edc  mov     rax, [rax+8]
0x180044ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ee5  nop
0x180044ee6  lea     rcx, [rdi+30h]
0x180044eea  cmp     qword ptr [rcx+18h], 7
0x180044eef  jbe     short loc_180044EF4
0x180044ef1  mov     rcx, [rcx]; packageFullName
0x180044ef4  lea     r8, [rsp+2F8h+packageFamilyName]; packageFamilyName
0x180044efc  lea     rdx, [rsp+2F8h+packageFamilyNameLength]; packageFamilyNameLength
0x180044f01  call    cs:__imp_PackageFamilyNameFromFullName
0x180044f08  nop     dword ptr [rax+rax+00h]
0x180044f0d  mov     rcx, [rsp+2F8h]; this
0x180044f15  test    eax, eax
0x180044f17  jnz     loc_180045315
0x180044f1d  test    rdi, rdi
0x180044f20  jz      short loc_180044F32
0x180044f22  mov     rax, [rdi]
0x180044f25  mov     rcx, rdi
0x180044f28  mov     rax, [rax+10h]
0x180044f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f31  nop
0x180044f32  xorps   xmm0, xmm0
0x180044f35  movups  xmmword ptr [rsp+2F8h+Src], xmm0
0x180044f3d  mov     [rsp+2F8h+var_240], r12
0x180044f45  mov     [rsp+2F8h+var_238], r12
0x180044f4d  lea     rax, [rsp+2F8h+packageFamilyName]
0x180044f55  or      r8, 0FFFFFFFFFFFFFFFFh
0x180044f59  inc     r8
0x180044f5c  cmp     [rax+r8*2], r12w
0x180044f61  jnz     short loc_180044F59
0x180044f63  lea     rdx, [rsp+2F8h+packageFamilyName]
0x180044f6b  lea     rcx, [rsp+2F8h+Src]
0x180044f73  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180044f78  nop
0x180044f79  mov     rax, 7FFFFFFFFFFFFFFEh
0x180044f83  mov     rcx, [rsp+2F8h+var_240]
0x180044f8b  sub     rax, rcx
0x180044f8e  cmp     rax, 61h ; 'a'
0x180044f92  jb      loc_18004532A
0x180044f98  lea     rax, [rsp+2F8h+Src]
0x180044fa0  cmp     [rsp+2F8h+var_238], 7
0x180044fa9  cmova   rax, [rsp+2F8h+Src]
0x180044fb2  mov     [rsp+2F8h+var_2C8], rcx; __int64
0x180044fb7  mov     qword ptr [rsp+2F8h+cbData], rax; Src
0x180044fbc  mov     [rsp+2F8h+phkResult], 61h ; 'a'; __int64
0x180044fc5  lea     r9, aSoftwareClasse_0; "SOFTWARE\\Classes\\Local Settings\\Soft"...
0x180044fcc  lea     rcx, [rsp+2F8h+lpSubKey]; void *
0x180044fd4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180044fd9  mov     [rsp+2F8h+hKey], r12
0x180044fde  lea     rax, [rsp+2F8h+hKey]
0x180044fe3  mov     [rsp+2F8h+var_298], rax
0x180044fe8  mov     [rsp+2F8h+var_290], r12
0x180044fed  mov     [rsp+2F8h+var_288], 1
0x180044ff2  lea     rdx, [rsp+2F8h+lpSubKey]
0x180044ffa  cmp     [rsp+2F8h+var_258], 7
0x180045003  cmova   rdx, [rsp+2F8h+lpSubKey]; lpSubKey
0x18004500c  lea     rax, [rsp+2F8h+var_290]
0x180045011  mov     [rsp+2F8h+phkResult], rax; unsigned int
0x180045016  mov     r9d, 20006h; samDesired
0x18004501c  xor     r8d, r8d; ulOptions
0x18004501f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180045026  call    cs:__imp_RegOpenKeyExW
0x18004502d  nop     dword ptr [rax+rax+00h]
0x180045032  mov     rcx, [rsp+2F8h]; this
0x18004503a  test    eax, eax
0x18004503c  jz      short loc_180045057
0x18004503e  mov     r9d, eax; char *
0x180045041  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\execmodel\\des"...
0x180045048  mov     edx, 379h; void *
0x18004504d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180045052  mov     dil, r12b
0x180045055  jmp     short loc_18004505A
0x180045057  mov     dil, 1
0x18004505a  lea     rcx, [rsp+2F8h+var_298]
0x18004505f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180045064  test    dil, dil
0x180045067  jz      short loc_1800450C4
0x180045069  mov     dword ptr [rsp+2F8h+Data], 1
0x180045071  mov     [rsp+2F8h+cbData], 4; cbData
0x180045079  lea     rax, [rsp+2F8h+Data]
0x18004507e  mov     [rsp+2F8h+phkResult], rax; unsigned int
0x180045083  mov     r9d, 4; dwType
0x180045089  xor     r8d, r8d; Reserved
0x18004508c  lea     rdx, ValueName; "WasEverActivated"
0x180045093  mov     rcx, [rsp+2F8h+hKey]; hKey
0x180045098  call    cs:__imp_RegSetValueExW
0x18004509f  nop     dword ptr [rax+rax+00h]
0x1800450a4  mov     rcx, [rsp+2F8h]; this
0x1800450ac  test    eax, eax
0x1800450ae  jz      short loc_1800450C4
0x1800450b0  mov     r9d, eax; char *
0x1800450b3  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800450ba  mov     edx, 383h; void *
0x1800450bf  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800450c4  mov     rcx, [rsp+2F8h+hKey]; hKey
0x1800450c9  test    rcx, rcx
0x1800450cc  jz      short loc_1800450DA
0x1800450ce  call    cs:__imp_RegCloseKey
0x1800450d5  nop     dword ptr [rax+rax+00h]
0x1800450da  lea     rcx, [rsp+2F8h+lpSubKey]; void *
0x1800450e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800450e7  nop
0x1800450e8  lea     rcx, [rsp+2F8h+Src]; void *
0x1800450f0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800450f5  jmp     loc_1800452A9
0x1800450fa  cmp     dword ptr [rsi], 4
0x1800450fd  jnz     loc_1800452A9
0x180045103  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x180045108  mov     rcx, [rax+8]
0x18004510c  cmp     dword ptr [rcx], 5
0x18004510f  jbe     short loc_18004512F
0x180045111  mov     [rsp+2F8h+hKey], rdi
0x180045116  lea     rax, [rsp+2F8h+hKey]
0x18004511b  mov     [rsp+2F8h+phkResult], rax
0x180045120  xor     r8d, r8d
0x180045123  lea     rdx, unk_1800E4A7C
0x18004512a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004512f  mov     rbx, [r13+140h]
0x180045136  mov     r14d, [rsi+30h]
0x18004513a  mov     r12, [rsi+28h]
0x18004513e  xorps   xmm0, xmm0
0x180045141  movups  xmmword ptr [rsp+2F8h+lpSubKey], xmm0
0x180045149  xorps   xmm1, xmm1
0x18004514c  movdqu  xmmword ptr [rsp+98h], xmm1
0x180045155  or      r8, 0FFFFFFFFFFFFFFFFh
0x180045159  xor     eax, eax
0x18004515b  inc     r8
0x18004515e  cmp     [rdi+r8*2], ax
0x180045163  jnz     short loc_18004515B
0x180045165  mov     rdx, rdi
0x180045168  lea     rcx, [rsp+2F8h+lpSubKey]
0x180045170  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180045175  nop
0x180045176  mov     dword ptr [rsp+2F8h+phkResult], r14d
0x18004517b  mov     r9, r12
0x18004517e  lea     r8, [rsp+2F8h+lpSubKey]
0x180045186  lea     rdx, [rsp+2F8h+hKey]
0x18004518b  mov     rcx, rbx
0x18004518e  call    ?GetApplicationData@ClmDataStore@@QEBA?AV?$ComPtr@VClmApplicationData@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAXK@Z; ClmDataStore::GetApplicationData(std::wstring const &,void * const,ulong)
0x180045193  xor     r12d, r12d
0x180045196  mov     ebx, r12d
0x180045199  lea     rcx, [rsp+2F8h+var_278]
0x1800451a1  cmp     rcx, rax
0x1800451a4  jz      short loc_1800451AC
0x1800451a6  mov     rbx, [rax]
0x1800451a9  mov     [rax], r12
0x1800451ac  mov     [rsp+2F8h+var_2A0], rbx
0x1800451b1  mov     rcx, [rsp+2F8h+hKey]
0x1800451b6  test    rcx, rcx
0x1800451b9  jz      short loc_1800451CD
0x1800451bb  mov     [rsp+2F8h+hKey], r12
0x1800451c0  mov     rax, [rcx]
0x1800451c3  mov     rax, [rax+10h]
0x1800451c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451cc  nop
0x1800451cd  lea     rcx, [rsp+2F8h+lpSubKey]; void *
0x1800451d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800451da  mov     r9d, [rsi+30h]; unsigned int
0x1800451de  mov     r8, [rsi+28h]; void *
0x1800451e2  mov     rdx, rdi; unsigned __int16 *
0x1800451e5  mov     rcx, [r13+140h]; this
0x1800451ec  call    ?RemoveApplication@ClmDataStore@@QEAAXPEBGPEAXK@Z; ClmDataStore::RemoveApplication(ushort const *,void *,ulong)
0x1800451f1  lea     rsi, [rbx+90h]
0x1800451f8  test    rbx, rbx
0x1800451fb  jnz     short loc_180045204
0x1800451fd  mov     rdi, [rsp+2F8h+var_2A0]
0x180045202  jmp     short loc_180045231
0x180045204  mov     rdi, [rsi]
0x180045207  test    rdi, rdi
0x18004520a  jz      short loc_18004521C
0x18004520c  mov     rax, [rdi]
0x18004520f  mov     rcx, rdi
0x180045212  mov     rax, [rax+8]
0x180045216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004521b  nop
0x18004521c  mov     r15d, 1
0x180045222  mov     rcx, rdi; this
0x180045225  call    ?HasApplications@ClmPackageData@@QEBA_NXZ; ClmPackageData::HasApplications(void)
0x18004522a  test    al, al
0x18004522c  mov     r14b, r15b
0x18004522f  jz      short loc_180045234
0x180045231  mov     r14b, r12b
0x180045234  test    r15b, 1
0x180045238  jz      short loc_18004524F
0x18004523a  test    rdi, rdi
0x18004523d  jz      short loc_18004524F
0x18004523f  mov     rax, [rdi]
0x180045242  mov     rcx, rdi
0x180045245  mov     rax, [rax+10h]
0x180045249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004524e  nop
0x18004524f  test    r14b, r14b
0x180045252  jz      short loc_1800452A2
0x180045254  mov     rdi, [rsi]
0x180045257  mov     [rsp+2F8h+hKey], rdi
0x18004525c  test    rdi, rdi
0x18004525f  jz      short loc_180045271
0x180045261  mov     rax, [rdi]
0x180045264  mov     rcx, rdi
  ... truncated ...
```
