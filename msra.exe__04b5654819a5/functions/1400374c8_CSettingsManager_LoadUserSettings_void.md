# CSettingsManager::LoadUserSettings(void)

- ea: `0x1400374c8`
- end: `0x1400376c2`
- name: `?LoadUserSettings@CSettingsManager@@QEAAJXZ`
- size: `506`
- prototype: `__int64 __fastcall(CSettingsManager *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400194c8`
- `0x14002cf20`
- `0x14002d118`
- `0x14002d684`
- `0x14002df5c`

## callees

- `0x140034ce4`
- `0x14003747c`
- `0x1400374c8`
- `0x1400376c8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140037689`
- `ADVAPI32!RegCloseKey` at `0x140037689`
- `ADVAPI32!RegOpenKeyExW` at `0x140037573`
- `ADVAPI32!RegOpenKeyExW` at `0x1400375ff`
- `ADVAPI32!RegOpenKeyExW` at `0x140037573`
- `ADVAPI32!RegOpenKeyExW` at `0x1400375ff`
- `ADVAPI32!RegQueryValueExW` at `0x14003765e`
- `ADVAPI32!RegQueryValueExW` at `0x14003765e`
- `KERNEL32!ReleaseMutex` at `0x1400376a6`
- `KERNEL32!ReleaseMutex` at `0x1400376a6`
- `KERNEL32!WaitForSingleObject` at `0x140037533`
- `KERNEL32!WaitForSingleObject` at `0x140037533`

## string_xrefs

- `0x140037511`: `base\diagnosis\ra\racommon\src\settingsmanager.cpp`
- `0x1400375ad`: `base\diagnosis\ra\racommon\src\settingsmanager.cpp`
- `0x1400375b4`: `CSettingsManager::WriteDefaultSettings`

## pseudocode

```c
__int64 __fastcall CSettingsManager::LoadUserSettings(BYTE *this)
{
  int v1; // ebp
  HANDLE v3; // rcx
  unsigned int v4; // ebx
  int i; // r8d
  CSettingsManager *v6; // rcx
  int v7; // r8d
  signed int v8; // eax
  CEventLogger *v9; // rcx
  CEventLogger *v10; // rcx
  CEventLogger *v11; // rcx
  __int64 v12; // rdi
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  v1 = 0;
  hKey = 0;
  cbData = 0;
  v3 = *(HANDLE *)this;
  Type = 4;
  if ( v3 )
  {
    if ( WaitForSingleObject(v3, 0x64u) == 258 )
    {
      v4 = -2147467259;
      goto LABEL_18;
    }
    v1 = 1;
    if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Remote Assistance", 0, 1u, &hKey) )
    {
      for ( i = 0; i < 5; i = v7 + 1 )
        CSettingsManager::LoadDefaultSetting(this, (unsigned int)i);
      v8 = CSettingsManager::SaveSettings(v6);
      v4 = v8;
      if ( v8 < 0 )
      {
        CEventLogger::LogError(
          v9,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\settingsmanager.cpp",
          0x37Fu,
          L"CSettingsManager::WriteDefaultSettings",
          v8);
        CEventLogger::LogError(
          v10,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\settingsmanager.cpp",
          0xA0u,
          L"CSettingsManager::LoadUserSettings",
          v4);
        goto LABEL_18;
      }
      if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Remote Assistance", 0, 1u, &hKey) )
      {
        v4 = -2147467259;
        CEventLogger::LogError(
          v11,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\settingsmanager.cpp",
          0xA9u,
          L"CSettingsManager::LoadUserSettings",
          0x80004005);
        goto LABEL_18;
      }
    }
    else
    {
      v4 = 0;
    }
    cbData = 4;
    v12 = 0;
    do
    {
      if ( RegQueryValueExW(hKey, (LPCWSTR)(&RA_SETTINGS_DWORD)[v12], 0, &Type, &this[4 * v12 + 8], &cbData) )
        CSettingsManager::LoadDefaultSetting(this, (unsigned int)v12);
      v12 = (unsigned int)(v12 + 1);
    }
    while ( (int)v12 < 5 );
  }
  else
  {
    v4 = -2147467261;
    CEventLogger::LogError(
      0,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\settingsmanager.cpp",
      0x8Bu,
      L"CSettingsManager::LoadUserSettings",
      0x80004003);
  }
LABEL_18:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v1 == 1 )
    ReleaseMutex(*(HANDLE *)this);
  return v4;
}

```

## disassembly

```asm
0x1400374c8  mov     rax, rsp
0x1400374cb  mov     [rax+20h], rbx
0x1400374cf  push    rbp
0x1400374d0  push    rsi
0x1400374d1  push    rdi
0x1400374d2  sub     rsp, 30h
0x1400374d6  xor     ebp, ebp
0x1400374d8  mov     qword ptr [rax+18h], 0
0x1400374e0  mov     rsi, rcx
0x1400374e3  mov     dword ptr [rax+8], 0
0x1400374ea  mov     rcx, [rcx]; this
0x1400374ed  lea     edi, [rbp+4]
0x1400374f0  mov     [rax+10h], edi
0x1400374f3  test    rcx, rcx
0x1400374f6  jnz     short loc_14003752E
0x1400374f8  mov     ebx, 80004003h
0x1400374fd  mov     dword ptr [rax-20h], 80004003h
0x140037504  mov     r9d, 8Bh; unsigned int
0x14003750a  lea     rax, aCsettingsmanag; "CSettingsManager::LoadUserSettings"
0x140037511  lea     r8, aBaseDiagnosisR_13; "base\\diagnosis\\ra\\racommon\\src\\set"...
0x140037518  mov     [rsp+48h+phkResult], rax; unsigned __int16 *
0x14003751d  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140037524  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140037529  jmp     loc_14003767F
0x14003752e  mov     edx, 64h ; 'd'; dwMilliseconds
0x140037533  call    cs:__imp_WaitForSingleObject
0x14003753a  nop     dword ptr [rax+rax+00h]
0x14003753f  cmp     eax, 102h
0x140037544  jnz     short loc_140037550
0x140037546  mov     ebx, 80004005h
0x14003754b  jmp     loc_14003767F
0x140037550  lea     rax, [rsp+48h+hKey]
0x140037555  mov     ebp, 1
0x14003755a  mov     r9d, ebp; samDesired
0x14003755d  mov     [rsp+48h+phkResult], rax; phkResult
0x140037562  xor     r8d, r8d; ulOptions
0x140037565  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Remote Assistance"
0x14003756c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140037573  call    cs:__imp_RegOpenKeyExW
0x14003757a  nop     dword ptr [rax+rax+00h]
0x14003757f  test    eax, eax
0x140037581  jz      loc_140037627
0x140037587  xor     r8d, r8d
0x14003758a  mov     edx, r8d
0x14003758d  mov     rcx, rsi
0x140037590  call    ?LoadDefaultSetting@CSettingsManager@@QEAAJW4_RASettingDWORD@@@Z; CSettingsManager::LoadDefaultSetting(_RASettingDWORD)
0x140037595  inc     r8d
0x140037598  cmp     r8d, 5
0x14003759c  jl      short loc_14003758A
0x14003759e  call    ?SaveSettings@CSettingsManager@@QEAAJXZ; CSettingsManager::SaveSettings(void)
0x1400375a3  mov     ebx, eax
0x1400375a5  test    eax, eax
0x1400375a7  jns     short loc_1400375E1
0x1400375a9  mov     dword ptr [rsp+48h+lpcbData], eax; unsigned int
0x1400375ad  lea     r8, aBaseDiagnosisR_13; "base\\diagnosis\\ra\\racommon\\src\\set"...
0x1400375b4  lea     rax, aCsettingsmanag_0; "CSettingsManager::WriteDefaultSettings"
0x1400375bb  mov     r9d, 37Fh; unsigned int
0x1400375c1  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400375c8  mov     [rsp+48h+phkResult], rax; unsigned __int16 *
0x1400375cd  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400375d2  mov     r9d, 0A0h
0x1400375d8  mov     dword ptr [rsp+48h+lpcbData], ebx
0x1400375dc  jmp     loc_14003750A
0x1400375e1  lea     rax, [rsp+48h+hKey]
0x1400375e6  mov     r9d, ebp; samDesired
0x1400375e9  xor     r8d, r8d; ulOptions
0x1400375ec  mov     [rsp+48h+phkResult], rax; phkResult
0x1400375f1  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Remote Assistance"
0x1400375f8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400375ff  call    cs:__imp_RegOpenKeyExW
0x140037606  nop     dword ptr [rax+rax+00h]
0x14003760b  test    eax, eax
0x14003760d  jz      short loc_140037629
0x14003760f  mov     ebx, 80004005h
0x140037614  mov     dword ptr [rsp+48h+lpcbData], 80004005h
0x14003761c  mov     r9d, 0A9h
0x140037622  jmp     loc_14003750A
0x140037627  xor     ebx, ebx
0x140037629  mov     [rsp+48h+cbData], edi
0x14003762d  xor     edi, edi
0x14003762f  lea     rcx, [rsp+48h+cbData]
0x140037634  xor     r8d, r8d; lpReserved
0x140037637  mov     [rsp+48h+lpcbData], rcx; lpcbData
0x14003763c  lea     r10, ?RA_SETTINGS_DWORD@@3PAPEBGA; ushort const * near * RA_SETTINGS_DWORD
0x140037643  mov     rcx, [rsp+48h+hKey]; hKey
0x140037648  lea     rax, [rsi+8]
0x14003764c  mov     rdx, [r10+rdi*8]; lpValueName
0x140037650  lea     rax, [rax+rdi*4]
0x140037654  lea     r9, [rsp+48h+Type]; lpType
0x140037659  mov     [rsp+48h+phkResult], rax; lpData
0x14003765e  call    cs:__imp_RegQueryValueExW
0x140037665  nop     dword ptr [rax+rax+00h]
0x14003766a  test    eax, eax
0x14003766c  jz      short loc_140037678
0x14003766e  mov     edx, edi
0x140037670  mov     rcx, rsi
0x140037673  call    ?LoadDefaultSetting@CSettingsManager@@QEAAJW4_RASettingDWORD@@@Z; CSettingsManager::LoadDefaultSetting(_RASettingDWORD)
0x140037678  inc     edi
0x14003767a  cmp     edi, 5
0x14003767d  jl      short loc_14003762F
0x14003767f  mov     rcx, [rsp+48h+hKey]; hKey
0x140037684  test    rcx, rcx
0x140037687  jz      short loc_14003769E
0x140037689  call    cs:__imp_RegCloseKey
0x140037690  nop     dword ptr [rax+rax+00h]
0x140037695  mov     [rsp+48h+hKey], 0
0x14003769e  cmp     ebp, 1
0x1400376a1  jnz     short loc_1400376B2
0x1400376a3  mov     rcx, [rsi]; hMutex
0x1400376a6  call    cs:__imp_ReleaseMutex
0x1400376ad  nop     dword ptr [rax+rax+00h]
0x1400376b2  mov     eax, ebx
0x1400376b4  mov     rbx, [rsp+48h+arg_18]
0x1400376b9  add     rsp, 30h
0x1400376bd  pop     rdi
0x1400376be  pop     rsi
0x1400376bf  pop     rbp
0x1400376c0  retn
```
