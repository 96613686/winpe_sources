# AccentColors::UpdateHistory(ulong,bool)

- ea: `0x1400fa99c`
- end: `0x1400faeaf`
- name: `?UpdateHistory@AccentColors@@SAJK_N@Z`
- size: `1299`
- prototype: `__int64 __fastcall(unsigned int, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400fa858`

## callees

- `0x140020580`
- `0x140047f0c`
- `0x14007bf4c`
- `0x1400869e4`
- `0x140086c88`
- `0x14009ac68`
- `0x1400fa99c`
- `0x1400faeb8`
- `0x1400faf6c`
- `0x14010e160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400fabf7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400fad41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400fae0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400fae5f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400fabf7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400fad41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400fae0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400fae5f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400faa43`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400fab17`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400faa43`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400fab17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400faaa1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400faaa1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400fabb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400fac76`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400fabb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400fac76`

## pseudocode

```c
__int64 __fastcall AccentColors::UpdateHistory(unsigned int a1)
{
  BOOL v2; // r12d
  HKEY *phkResult; // rax
  HKEY v4; // rcx
  LSTATUS Key; // eax
  signed int v6; // ebx
  __int64 v7; // rdx
  bool IsKnownColor; // si
  HKEY *v9; // rax
  HKEY v10; // rcx
  LSTATUS v11; // eax
  bool v12; // dl
  bool v13; // sf
  HKEY *v14; // rax
  HKEY v15; // rcx
  LSTATUS v16; // eax
  signed int v17; // edi
  int v18; // r15d
  LSTATUS v19; // eax
  bool v20; // sf
  int v21; // ebx
  LSTATUS v22; // eax
  __int64 v23; // rax
  int v24; // esi
  int v25; // ebx
  int v26; // eax
  int i; // edx
  int v28; // ebx
  int v29; // edi
  signed int v30; // edx
  int v31; // r8d
  int v32; // r9d
  LSTATUS v33; // eax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-E0h]
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v38[4]; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v40; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE v42[8]; // [rsp+70h] [rbp-90h] BYREF
  HKEY v43[2]; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v44[6]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ValueName[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  hKey = 0;
  v40 = 0;
  v2 = IsAutoColorizationEnabled();
  CCurrentColorUser::CCurrentColorUser(v43, 0x2001Fu);
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v4 = v43[0];
  if ( CCurrentColorUser::_overrideCurrentUser )
    v4 = CCurrentColorUser::_overrideCurrentUser;
  Key = RegCreateKeyExW(
          v4,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\History",
          0,
          0,
          0,
          0x2001Fu,
          0,
          phkResult,
          0);
  v6 = Key;
  if ( Key > 0 )
    v6 = (unsigned __int16)Key | 0x80070000;
  if ( v6 < 0 )
  {
    v7 = 365;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\lib\\occolorlib\\accentcolors.cpp",
      (const char *)(unsigned int)v6,
      dwOptions);
    goto LABEL_66;
  }
  IsKnownColor = 0;
  v9 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v40);
  v10 = v43[0];
  if ( CCurrentColorUser::_overrideCurrentUser )
    v10 = CCurrentColorUser::_overrideCurrentUser;
  v11 = RegOpenKeyExW(v10, L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\History\\Colors", 0, 0x2001Fu, v9);
  v13 = v11 < 0;
  if ( v11 > 0 )
    v13 = 1;
  if ( v13 )
  {
    IsKnownColor = AccentColors::_IsKnownColor(a1, v12);
    v14 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v40);
    v15 = v43[0];
    if ( CCurrentColorUser::_overrideCurrentUser )
      v15 = CCurrentColorUser::_overrideCurrentUser;
    v16 = RegCreateKeyExW(
            v15,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\History\\Colors",
            0,
            0,
            0,
            0x2001Fu,
            0,
            v14,
            0);
    v6 = v16;
    if ( v16 > 0 )
      v6 = (unsigned __int16)v16 | 0x80070000;
    if ( v6 < 0 )
    {
      v7 = 371;
      goto LABEL_18;
    }
  }
  if ( !AccentColors::_IsKnownColor(a1, v12) || IsKnownColor )
  {
    v17 = 0;
    v18 = 0;
    *(_DWORD *)Data = 0;
    if ( !IsKnownColor && a1 != 195948557 )
    {
      v44[0] = a1;
      v18 = 1;
    }
    cbData = 4;
    v19 = RegQueryValueExW(hKey, L"AutoColor", 0, 0, Data, &cbData);
    v20 = v19 < 0;
    if ( v19 > 0 )
      v20 = 1;
    if ( v20 )
    {
      *(_DWORD *)Data = v2;
      RegSetValueExW(hKey, L"AutoColor", 0, 4u, Data, 4u);
    }
    v21 = 0;
    while ( v21 < 5 )
    {
      if ( *(_DWORD *)Data == 1 && !v21 )
        goto LABEL_39;
      dwOptionsa[0] = v21;
      v17 = StringCchPrintfW(ValueName, 0x104u, L"%s%u", L"ColorHistory", *(_QWORD *)dwOptionsa);
      if ( v17 < 0 )
        goto LABEL_39;
      *(_DWORD *)v38 = 0;
      cbData = 4;
      v22 = RegQueryValueExW(v40, ValueName, 0, 0, v38, &cbData);
      v17 = v22;
      if ( v22 > 0 )
        v17 = (unsigned __int16)v22 | 0x80070000;
      if ( v17 < 0 )
      {
LABEL_39:
        ++v21;
        if ( v17 < 0 )
          break;
      }
      else
      {
        if ( ((a1 ^ *(_DWORD *)v38) & 0xFFFFFF) != 0 )
        {
          v23 = v18++;
          v44[v23] = *(_DWORD *)v38;
        }
        ++v21;
      }
    }
    v24 = 0;
    v25 = 0;
    do
    {
LABEL_41:
      if ( v25 >= v18 )
        break;
      dwOptionsa[0] = v24;
      v26 = StringCchPrintfW(ValueName, 0x104u, L"%s%u", L"ColorHistory", *(_QWORD *)dwOptionsa);
      if ( v26 >= 0 )
      {
        for ( i = 0; i < v25; ++i )
        {
          if ( ((v44[v25] ^ v44[i]) & 0xFFFFFF) == 0 )
          {
            ++v25;
            goto LABEL_41;
          }
        }
        v26 = RegSetValueExW(v40, ValueName, 0, 4u, (const BYTE *)&v44[v25], 4u);
        if ( v26 > 0 )
          v26 = (unsigned __int16)v26 | 0x80070000;
        ++v24;
      }
      ++v25;
    }
    while ( v26 >= 0 );
    v28 = 0;
    v29 = v24;
    do
    {
      if ( v29 >= 5 || v28 >= 5 )
        break;
      dwOptionsa[0] = v29;
      v30 = StringCchPrintfW(ValueName, 0x104u, L"%s%u", L"ColorHistory", *(_QWORD *)dwOptionsa);
      if ( v30 >= 0 )
      {
LABEL_56:
        if ( (unsigned int)v28 < 4 )
        {
          v31 = 0;
          v32 = *((_DWORD *)qword_1401FF9B0 + v28);
          *(_DWORD *)v38 = v32;
          while ( v31 < v24 )
          {
            if ( ((v44[v31] ^ v32) & 0xFFFFFF) == 0 )
            {
              ++v28;
              goto LABEL_56;
            }
            ++v31;
          }
          v33 = RegSetValueExW(v40, ValueName, 0, 4u, v38, 4u);
          v30 = v33;
          if ( v33 > 0 )
            v30 = (unsigned __int16)v33 | 0x80070000;
        }
      }
      ++v29;
      ++v28;
    }
    while ( v30 >= 0 );
  }
  *(_DWORD *)v42 = v2;
  RegSetValueExW(hKey, L"AutoColor", 0, 4u, v42, 4u);
  v6 = 0;
LABEL_66:
  CCurrentColorUser::~CCurrentColorUser((CCurrentColorUser *)v43);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v40);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400fa99c  push    rbp
0x1400fa99e  push    rbx
0x1400fa99f  push    rsi
0x1400fa9a0  push    rdi
0x1400fa9a1  push    r12
0x1400fa9a3  push    r14
0x1400fa9a5  push    r15
0x1400fa9a7  lea     rbp, [rsp-1C0h]
0x1400fa9af  sub     rsp, 2C0h
0x1400fa9b6  mov     rax, cs:__security_cookie
0x1400fa9bd  xor     rax, rsp
0x1400fa9c0  mov     [rbp+1F0h+var_40], rax
0x1400fa9c7  mov     r14d, ecx
0x1400fa9ca  mov     [rsp+2F0h+hKey], 0
0x1400fa9d3  mov     [rsp+2F0h+var_290], 0
0x1400fa9dc  call    ?IsAutoColorizationEnabled@@YA_NXZ; IsAutoColorizationEnabled(void)
0x1400fa9e1  mov     edi, 2001Fh
0x1400fa9e6  movzx   r12d, al
0x1400fa9ea  mov     edx, edi; samDesired
0x1400fa9ec  lea     rcx, [rsp+2F0h+var_278]; phkResult
0x1400fa9f1  call    ??0CCurrentColorUser@@QEAA@K@Z; CCurrentColorUser::CCurrentColorUser(ulong)
0x1400fa9f6  lea     rcx, [rsp+2F0h+hKey]
0x1400fa9fb  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1400faa00  mov     rdx, cs:?_overrideCurrentUser@CCurrentColorUser@@0PEAUHKEY__@@EA; HKEY__ * CCurrentColorUser::_overrideCurrentUser
0x1400faa07  mov     rcx, [rsp+2F0h+var_278]
0x1400faa0c  test    rdx, rdx
0x1400faa0f  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x1400faa18  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1400faa1d  cmovnz  rcx, rdx; hKey
0x1400faa21  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400faa2a  lea     rdx, aSoftwareMicros_80; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400faa31  xor     r9d, r9d; lpClass
0x1400faa34  mov     [rsp+2F0h+samDesired], edi; samDesired
0x1400faa38  xor     r8d, r8d; Reserved
0x1400faa3b  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x1400faa43  call    cs:__imp_RegCreateKeyExW
0x1400faa4a  nop     dword ptr [rax+rax+00h]
0x1400faa4f  mov     ebx, eax
0x1400faa51  mov     r15d, 80070000h
0x1400faa57  test    eax, eax
0x1400faa59  jle     short loc_1400FAA61
0x1400faa5b  movzx   ebx, ax
0x1400faa5e  or      ebx, r15d
0x1400faa61  test    ebx, ebx
0x1400faa63  jns     short loc_1400FAA6F
0x1400faa65  mov     edx, 16Dh
0x1400faa6a  jmp     loc_1400FAB38
0x1400faa6f  lea     rcx, [rsp+2F0h+var_290]
0x1400faa74  xor     sil, sil
0x1400faa77  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1400faa7c  mov     rdx, cs:?_overrideCurrentUser@CCurrentColorUser@@0PEAUHKEY__@@EA; HKEY__ * CCurrentColorUser::_overrideCurrentUser
0x1400faa83  mov     r9d, edi; samDesired
0x1400faa86  mov     rcx, [rsp+2F0h+var_278]
0x1400faa8b  test    rdx, rdx
0x1400faa8e  mov     qword ptr [rsp+2F0h+dwOptions], rax; phkResult
0x1400faa93  cmovnz  rcx, rdx; hKey
0x1400faa97  xor     r8d, r8d; ulOptions
0x1400faa9a  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400faaa1  call    cs:__imp_RegOpenKeyExW
0x1400faaa8  nop     dword ptr [rax+rax+00h]
0x1400faaad  test    eax, eax
0x1400faaaf  jle     short loc_1400FAAB9
0x1400faab1  movzx   eax, ax
0x1400faab4  or      eax, r15d
0x1400faab7  test    eax, eax
0x1400faab9  jns     loc_1400FAB53
0x1400faabf  mov     ecx, r14d; unsigned int
0x1400faac2  call    ?_IsKnownColor@AccentColors@@CA_NK_N@Z; AccentColors::_IsKnownColor(ulong,bool)
0x1400faac7  lea     rcx, [rsp+2F0h+var_290]
0x1400faacc  mov     sil, al
0x1400faacf  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1400faad4  mov     r8, cs:?_overrideCurrentUser@CCurrentColorUser@@0PEAUHKEY__@@EA; HKEY__ * CCurrentColorUser::_overrideCurrentUser
0x1400faadb  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400faae2  mov     rcx, [rsp+2F0h+var_278]
0x1400faae7  test    r8, r8
0x1400faaea  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x1400faaf3  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1400faaf8  cmovnz  rcx, r8; hKey
0x1400faafc  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400fab05  xor     r9d, r9d; lpClass
0x1400fab08  xor     r8d, r8d; Reserved
0x1400fab0b  mov     [rsp+2F0h+samDesired], edi; samDesired
0x1400fab0f  mov     [rsp+2F0h+dwOptions], 0; int
0x1400fab17  call    cs:__imp_RegCreateKeyExW
0x1400fab1e  nop     dword ptr [rax+rax+00h]
0x1400fab23  mov     ebx, eax
0x1400fab25  test    eax, eax
0x1400fab27  jle     short loc_1400FAB2F
0x1400fab29  movzx   ebx, ax
0x1400fab2c  or      ebx, r15d
0x1400fab2f  test    ebx, ebx
0x1400fab31  jns     short loc_1400FAB53
0x1400fab33  mov     edx, 173h; void *
0x1400fab38  mov     rcx, [rbp+1F8h]; this
0x1400fab3f  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\lib\\occolorlib\\acc"...
0x1400fab46  mov     r9d, ebx; char *
0x1400fab49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400fab4e  jmp     loc_1400FAE6D
0x1400fab53  mov     ecx, r14d; unsigned int
0x1400fab56  call    ?_IsKnownColor@AccentColors@@CA_NK_N@Z; AccentColors::_IsKnownColor(ulong,bool)
0x1400fab5b  mov     ebx, 4
0x1400fab60  test    al, al
0x1400fab62  jz      short loc_1400FAB6D
0x1400fab64  test    sil, sil
0x1400fab67  jz      loc_1400FAE3A
0x1400fab6d  xor     edi, edi
0x1400fab6f  xor     r15d, r15d
0x1400fab72  mov     dword ptr [rsp+2F0h+Data], edi
0x1400fab76  test    sil, sil
0x1400fab79  jnz     short loc_1400FAB8C
0x1400fab7b  cmp     r14d, 0BADF00Dh
0x1400fab82  jz      short loc_1400FAB8C
0x1400fab84  mov     [rbp+1F0h+var_268], r14d
0x1400fab88  lea     r15d, [rdi+1]
0x1400fab8c  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1400fab91  lea     rax, [rsp+2F0h+cbData]
0x1400fab96  mov     qword ptr [rsp+2F0h+samDesired], rax; lpcbData
0x1400fab9b  lea     rdx, aAutocolor; "AutoColor"
0x1400faba2  lea     rax, [rsp+2F0h+Data]
0x1400faba7  mov     [rsp+2F0h+cbData], ebx
0x1400fabab  xor     r9d, r9d; lpType
0x1400fabae  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1400fabb3  xor     r8d, r8d; lpReserved
0x1400fabb6  call    cs:__imp_RegQueryValueExW
0x1400fabbd  nop     dword ptr [rax+rax+00h]
0x1400fabc2  test    eax, eax
0x1400fabc4  jle     short loc_1400FABD0
0x1400fabc6  movzx   eax, ax
0x1400fabc9  or      eax, 80070000h
0x1400fabce  test    eax, eax
0x1400fabd0  jns     short loc_1400FAC03
0x1400fabd2  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1400fabd7  lea     rax, [rsp+2F0h+Data]
0x1400fabdc  mov     [rsp+2F0h+samDesired], ebx; cbData
0x1400fabe0  lea     rdx, aAutocolor; "AutoColor"
0x1400fabe7  mov     r9d, ebx; dwType
0x1400fabea  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1400fabef  xor     r8d, r8d; Reserved
0x1400fabf2  mov     dword ptr [rsp+2F0h+Data], r12d
0x1400fabf7  call    cs:__imp_RegSetValueExW
0x1400fabfe  nop     dword ptr [rax+rax+00h]
0x1400fac03  xor     ebx, ebx
0x1400fac05  cmp     ebx, 5
0x1400fac08  jge     loc_1400FACC2
0x1400fac0e  cmp     dword ptr [rsp+2F0h+Data], 1
0x1400fac13  jnz     short loc_1400FAC1D
0x1400fac15  test    ebx, ebx
0x1400fac17  jz      loc_1400FACB8
0x1400fac1d  lea     r9, aColorhistory; "ColorHistory"
0x1400fac24  mov     [rsp+2F0h+dwOptions], ebx
0x1400fac28  lea     r8, aSU; "%s%u"
0x1400fac2f  mov     edx, 104h; unsigned __int64
0x1400fac34  lea     rcx, [rbp+1F0h+ValueName]; unsigned __int16 *
0x1400fac38  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400fac3d  mov     edi, eax
0x1400fac3f  test    eax, eax
0x1400fac41  js      short loc_1400FACB8
0x1400fac43  mov     rcx, [rsp+2F0h+var_290]; hKey
0x1400fac48  lea     rax, [rsp+2F0h+cbData]
0x1400fac4d  mov     qword ptr [rsp+2F0h+samDesired], rax; lpcbData
0x1400fac52  lea     rdx, [rbp+1F0h+ValueName]; lpValueName
0x1400fac56  lea     rax, [rsp+2F0h+var_29C]
0x1400fac5b  mov     dword ptr [rsp+2F0h+var_29C], 0
0x1400fac63  xor     r9d, r9d; lpType
0x1400fac66  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1400fac6b  xor     r8d, r8d; lpReserved
0x1400fac6e  mov     [rsp+2F0h+cbData], 4
0x1400fac76  call    cs:__imp_RegQueryValueExW
0x1400fac7d  nop     dword ptr [rax+rax+00h]
0x1400fac82  mov     edi, eax
0x1400fac84  test    eax, eax
0x1400fac86  jle     short loc_1400FAC91
0x1400fac88  movzx   edi, ax
0x1400fac8b  or      edi, 80070000h
0x1400fac91  test    edi, edi
0x1400fac93  js      short loc_1400FACB8
0x1400fac95  mov     ecx, dword ptr [rsp+2F0h+var_29C]
0x1400fac99  mov     eax, ecx
0x1400fac9b  xor     eax, r14d
0x1400fac9e  test    eax, 0FFFFFFh
0x1400faca3  jnz     short loc_1400FACAC
0x1400faca5  inc     ebx
0x1400faca7  jmp     loc_1400FAC05
0x1400facac  movsxd  rax, r15d
0x1400facaf  inc     r15d
0x1400facb2  mov     [rbp+rax*4+1F0h+var_268], ecx
0x1400facb6  jmp     short loc_1400FACA5
0x1400facb8  inc     ebx
0x1400facba  test    edi, edi
0x1400facbc  jns     loc_1400FAC05
0x1400facc2  xor     esi, esi
0x1400facc4  xor     ebx, ebx
0x1400facc6  lea     r14d, [rsi+1]
0x1400facca  cmp     ebx, r15d
0x1400faccd  jge     loc_1400FAD67
0x1400facd3  lea     r9, aColorhistory; "ColorHistory"
0x1400facda  mov     [rsp+2F0h+dwOptions], esi
0x1400facde  lea     r8, aSU; "%s%u"
0x1400face5  mov     edx, 104h; unsigned __int64
0x1400facea  lea     rcx, [rbp+1F0h+ValueName]; unsigned __int16 *
0x1400facee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400facf3  test    eax, eax
0x1400facf5  js      short loc_1400FAD5C
0x1400facf7  movsxd  rax, ebx
0x1400facfa  lea     r8, [rbp+1F0h+var_268]
0x1400facfe  xor     edx, edx
0x1400fad00  lea     r8, [r8+rax*4]
0x1400fad04  cmp     edx, ebx
0x1400fad06  jge     short loc_1400FAD24
0x1400fad08  movsxd  rax, edx
0x1400fad0b  mov     ecx, [rbp+rax*4+1F0h+var_268]
0x1400fad0f  xor     ecx, [r8]
0x1400fad12  test    ecx, 0FFFFFFh
0x1400fad18  jz      short loc_1400FAD1F
0x1400fad1a  add     edx, r14d
0x1400fad1d  jmp     short loc_1400FAD04
0x1400fad1f  add     ebx, r14d
0x1400fad22  jmp     short loc_1400FACCA
0x1400fad24  mov     rcx, [rsp+2F0h+var_290]; hKey
0x1400fad29  lea     rdx, [rbp+1F0h+ValueName]; lpValueName
0x1400fad2d  mov     eax, 4
0x1400fad32  mov     [rsp+2F0h+samDesired], eax; cbData
0x1400fad36  mov     r9d, eax; dwType
0x1400fad39  mov     qword ptr [rsp+2F0h+dwOptions], r8; lpData
0x1400fad3e  xor     r8d, r8d; Reserved
0x1400fad41  call    cs:__imp_RegSetValueExW
0x1400fad48  nop     dword ptr [rax+rax+00h]
0x1400fad4d  test    eax, eax
0x1400fad4f  jle     short loc_1400FAD59
0x1400fad51  movzx   eax, ax
0x1400fad54  or      eax, 80070000h
0x1400fad59  add     esi, r14d
0x1400fad5c  add     ebx, r14d
0x1400fad5f  test    eax, eax
0x1400fad61  jns     loc_1400FACCA
0x1400fad67  xor     ebx, ebx
0x1400fad69  mov     edi, esi
0x1400fad6b  cmp     edi, 5
0x1400fad6e  jge     loc_1400FAE35
0x1400fad74  cmp     ebx, 5
0x1400fad77  jge     loc_1400FAE35
0x1400fad7d  lea     r9, aColorhistory; "ColorHistory"
0x1400fad84  mov     [rsp+2F0h+dwOptions], edi
0x1400fad88  lea     r8, aSU; "%s%u"
0x1400fad8f  mov     edx, 104h; unsigned __int64
0x1400fad94  lea     rcx, [rbp+1F0h+ValueName]; unsigned __int16 *
0x1400fad98  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400fad9d  mov     edx, eax
0x1400fad9f  test    eax, eax
0x1400fada1  js      loc_1400FAE27
0x1400fada7  mov     r10d, 4
0x1400fadad  cmp     ebx, 5
0x1400fadb0  jge     short loc_1400FAE27
0x1400fadb2  cmp     ebx, r10d
0x1400fadb5  jnb     short loc_1400FAE27
0x1400fadb7  movsxd  rcx, ebx
0x1400fadba  lea     r9, qword_1401FF9B0
0x1400fadc1  xor     r8d, r8d
0x1400fadc4  mov     r9d, [r9+rcx*4]
0x1400fadc8  mov     dword ptr [rsp+2F0h+var_29C], r9d
0x1400fadcd  cmp     r8d, esi
0x1400fadd0  jge     short loc_1400FADEE
0x1400fadd2  movsxd  rax, r8d
0x1400fadd5  mov     ecx, r9d
0x1400fadd8  xor     ecx, [rbp+rax*4+1F0h+var_268]
0x1400faddc  test    ecx, 0FFFFFFh
0x1400fade2  jz      short loc_1400FADE9
0x1400fade4  add     r8d, r14d
0x1400fade7  jmp     short loc_1400FADCD
0x1400fade9  add     ebx, r14d
0x1400fadec  jmp     short loc_1400FADAD
0x1400fadee  mov     rcx, [rsp+2F0h+var_290]; hKey
0x1400fadf3  lea     rax, [rsp+2F0h+var_29C]
0x1400fadf8  mov     [rsp+2F0h+samDesired], r10d; cbData
0x1400fadfd  lea     rdx, [rbp+1F0h+ValueName]; lpValueName
0x1400fae01  mov     r9d, r10d; dwType
0x1400fae04  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1400fae09  xor     r8d, r8d; Reserved
0x1400fae0c  call    cs:__imp_RegSetValueExW
0x1400fae13  nop     dword ptr [rax+rax+00h]
0x1400fae18  mov     edx, eax
0x1400fae1a  test    eax, eax
0x1400fae1c  jle     short loc_1400FAE27
0x1400fae1e  movzx   edx, ax
0x1400fae21  or      edx, 80070000h
0x1400fae27  add     edi, r14d
0x1400fae2a  add     ebx, r14d
0x1400fae2d  test    edx, edx
0x1400fae2f  jns     loc_1400FAD6B
0x1400fae35  mov     ebx, 4
0x1400fae3a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1400fae3f  lea     rax, [rsp+2F0h+var_280]
0x1400fae44  mov     [rsp+2F0h+samDesired], ebx; cbData
0x1400fae48  lea     rdx, aAutocolor; "AutoColor"
0x1400fae4f  mov     r9d, ebx; dwType
0x1400fae52  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1400fae57  xor     r8d, r8d; Reserved
0x1400fae5a  mov     dword ptr [rsp+2F0h+var_280], r12d
0x1400fae5f  call    cs:__imp_RegSetValueExW
0x1400fae66  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
