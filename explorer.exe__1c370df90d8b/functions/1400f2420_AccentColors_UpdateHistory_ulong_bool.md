# AccentColors::UpdateHistory(ulong,bool)

- ea: `0x1400f2420`
- end: `0x1400f28f8`
- name: `?UpdateHistory@AccentColors@@SAJK_N@Z`
- size: `1240`
- prototype: `__int64 __fastcall(unsigned int, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400f22e8`

## callees

- `0x1400158a4`
- `0x140076e00`
- `0x140078078`
- `0x140080a44`
- `0x140080e90`
- `0x1400954e0`
- `0x1400f2420`
- `0x1400f2900`
- `0x1400f29b4`
- `0x1401040e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400f24c7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400f258f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400f24c7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400f258f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400f251f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400f251f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400f2628`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400f26dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400f2628`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400f26dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400f2663`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400f27a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400f2862`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400f28af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400f2663`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400f27a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400f2862`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400f28af`

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
          v32 = *((_DWORD *)qword_1402020F0 + v28);
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
0x1400f2420  push    rbp
0x1400f2422  push    rbx
0x1400f2423  push    rsi
0x1400f2424  push    rdi
0x1400f2425  push    r12
0x1400f2427  push    r14
0x1400f2429  push    r15
0x1400f242b  lea     rbp, [rsp-1C0h]
0x1400f2433  sub     rsp, 2C0h
0x1400f243a  mov     rax, cs:__security_cookie
0x1400f2441  xor     rax, rsp
0x1400f2444  mov     [rbp+1F0h+var_40], rax
0x1400f244b  mov     r14d, ecx
0x1400f244e  mov     [rsp+2F0h+hKey], 0
0x1400f2457  mov     [rsp+2F0h+var_290], 0
0x1400f2460  call    ?IsAutoColorizationEnabled@@YA_NXZ; IsAutoColorizationEnabled(void)
0x1400f2465  mov     edi, 2001Fh
0x1400f246a  movzx   r12d, al
0x1400f246e  mov     edx, edi; samDesired
0x1400f2470  lea     rcx, [rsp+2F0h+var_278]; phkResult
0x1400f2475  call    ??0CCurrentColorUser@@QEAA@K@Z; CCurrentColorUser::CCurrentColorUser(ulong)
0x1400f247a  lea     rcx, [rsp+2F0h+hKey]
0x1400f247f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1400f2484  mov     rdx, cs:?_overrideCurrentUser@CCurrentColorUser@@0PEAUHKEY__@@EA; HKEY__ * CCurrentColorUser::_overrideCurrentUser
0x1400f248b  mov     rcx, [rsp+2F0h+var_278]
0x1400f2490  test    rdx, rdx
0x1400f2493  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x1400f249c  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1400f24a1  cmovnz  rcx, rdx; hKey
0x1400f24a5  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400f24ae  lea     rdx, aSoftwareMicros_80; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400f24b5  xor     r9d, r9d; lpClass
0x1400f24b8  mov     [rsp+2F0h+samDesired], edi; samDesired
0x1400f24bc  xor     r8d, r8d; Reserved
0x1400f24bf  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x1400f24c7  call    cs:__imp_RegCreateKeyExW
0x1400f24cd  mov     ebx, eax
0x1400f24cf  mov     r15d, 80070000h
0x1400f24d5  test    eax, eax
0x1400f24d7  jle     short loc_1400F24DF
0x1400f24d9  movzx   ebx, ax
0x1400f24dc  or      ebx, r15d
0x1400f24df  test    ebx, ebx
0x1400f24e1  jns     short loc_1400F24ED
0x1400f24e3  mov     edx, 16Dh
0x1400f24e8  jmp     loc_1400F25AA
0x1400f24ed  lea     rcx, [rsp+2F0h+var_290]
0x1400f24f2  xor     sil, sil
0x1400f24f5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1400f24fa  mov     rdx, cs:?_overrideCurrentUser@CCurrentColorUser@@0PEAUHKEY__@@EA; HKEY__ * CCurrentColorUser::_overrideCurrentUser
0x1400f2501  mov     r9d, edi; samDesired
0x1400f2504  mov     rcx, [rsp+2F0h+var_278]
0x1400f2509  test    rdx, rdx
0x1400f250c  mov     qword ptr [rsp+2F0h+dwOptions], rax; phkResult
0x1400f2511  cmovnz  rcx, rdx; hKey
0x1400f2515  xor     r8d, r8d; ulOptions
0x1400f2518  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400f251f  call    cs:__imp_RegOpenKeyExW
0x1400f2525  test    eax, eax
0x1400f2527  jle     short loc_1400F2531
0x1400f2529  movzx   eax, ax
0x1400f252c  or      eax, r15d
0x1400f252f  test    eax, eax
0x1400f2531  jns     loc_1400F25C5
0x1400f2537  mov     ecx, r14d; unsigned int
0x1400f253a  call    ?_IsKnownColor@AccentColors@@CA_NK_N@Z; AccentColors::_IsKnownColor(ulong,bool)
0x1400f253f  lea     rcx, [rsp+2F0h+var_290]
0x1400f2544  mov     sil, al
0x1400f2547  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1400f254c  mov     r8, cs:?_overrideCurrentUser@CCurrentColorUser@@0PEAUHKEY__@@EA; HKEY__ * CCurrentColorUser::_overrideCurrentUser
0x1400f2553  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400f255a  mov     rcx, [rsp+2F0h+var_278]
0x1400f255f  test    r8, r8
0x1400f2562  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x1400f256b  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1400f2570  cmovnz  rcx, r8; hKey
0x1400f2574  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400f257d  xor     r9d, r9d; lpClass
0x1400f2580  xor     r8d, r8d; Reserved
0x1400f2583  mov     [rsp+2F0h+samDesired], edi; samDesired
0x1400f2587  mov     [rsp+2F0h+dwOptions], 0; int
0x1400f258f  call    cs:__imp_RegCreateKeyExW
0x1400f2595  mov     ebx, eax
0x1400f2597  test    eax, eax
0x1400f2599  jle     short loc_1400F25A1
0x1400f259b  movzx   ebx, ax
0x1400f259e  or      ebx, r15d
0x1400f25a1  test    ebx, ebx
0x1400f25a3  jns     short loc_1400F25C5
0x1400f25a5  mov     edx, 173h; void *
0x1400f25aa  mov     rcx, [rbp+1F8h]; this
0x1400f25b1  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\lib\\occolorlib\\acc"...
0x1400f25b8  mov     r9d, ebx; char *
0x1400f25bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400f25c0  jmp     loc_1400F28B7
0x1400f25c5  mov     ecx, r14d; unsigned int
0x1400f25c8  call    ?_IsKnownColor@AccentColors@@CA_NK_N@Z; AccentColors::_IsKnownColor(ulong,bool)
0x1400f25cd  mov     ebx, 4
0x1400f25d2  test    al, al
0x1400f25d4  jz      short loc_1400F25DF
0x1400f25d6  test    sil, sil
0x1400f25d9  jz      loc_1400F288A
0x1400f25df  xor     edi, edi
0x1400f25e1  xor     r15d, r15d
0x1400f25e4  mov     dword ptr [rsp+2F0h+Data], edi
0x1400f25e8  test    sil, sil
0x1400f25eb  jnz     short loc_1400F25FE
0x1400f25ed  cmp     r14d, 0BADF00Dh
0x1400f25f4  jz      short loc_1400F25FE
0x1400f25f6  mov     [rbp+1F0h+var_268], r14d
0x1400f25fa  lea     r15d, [rdi+1]
0x1400f25fe  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1400f2603  lea     rax, [rsp+2F0h+cbData]
0x1400f2608  mov     qword ptr [rsp+2F0h+samDesired], rax; lpcbData
0x1400f260d  lea     rdx, aAutocolor; "AutoColor"
0x1400f2614  lea     rax, [rsp+2F0h+Data]
0x1400f2619  mov     [rsp+2F0h+cbData], ebx
0x1400f261d  xor     r9d, r9d; lpType
0x1400f2620  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1400f2625  xor     r8d, r8d; lpReserved
0x1400f2628  call    cs:__imp_RegQueryValueExW
0x1400f262e  test    eax, eax
0x1400f2630  jle     short loc_1400F263C
0x1400f2632  movzx   eax, ax
0x1400f2635  or      eax, 80070000h
0x1400f263a  test    eax, eax
0x1400f263c  jns     short loc_1400F2669
0x1400f263e  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1400f2643  lea     rax, [rsp+2F0h+Data]
0x1400f2648  mov     [rsp+2F0h+samDesired], ebx; cbData
0x1400f264c  lea     rdx, aAutocolor; "AutoColor"
0x1400f2653  mov     r9d, ebx; dwType
0x1400f2656  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1400f265b  xor     r8d, r8d; Reserved
0x1400f265e  mov     dword ptr [rsp+2F0h+Data], r12d
0x1400f2663  call    cs:__imp_RegSetValueExW
0x1400f2669  xor     ebx, ebx
0x1400f266b  cmp     ebx, 5
0x1400f266e  jge     loc_1400F2722
0x1400f2674  cmp     dword ptr [rsp+2F0h+Data], 1
0x1400f2679  jnz     short loc_1400F2683
0x1400f267b  test    ebx, ebx
0x1400f267d  jz      loc_1400F2718
0x1400f2683  lea     r9, aColorhistory; "ColorHistory"
0x1400f268a  mov     [rsp+2F0h+dwOptions], ebx
0x1400f268e  lea     r8, aSU; "%s%u"
0x1400f2695  mov     edx, 104h; unsigned __int64
0x1400f269a  lea     rcx, [rbp+1F0h+ValueName]; unsigned __int16 *
0x1400f269e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400f26a3  mov     edi, eax
0x1400f26a5  test    eax, eax
0x1400f26a7  js      short loc_1400F2718
0x1400f26a9  mov     rcx, [rsp+2F0h+var_290]; hKey
0x1400f26ae  lea     rax, [rsp+2F0h+cbData]
0x1400f26b3  mov     qword ptr [rsp+2F0h+samDesired], rax; lpcbData
0x1400f26b8  lea     rdx, [rbp+1F0h+ValueName]; lpValueName
0x1400f26bc  lea     rax, [rsp+2F0h+var_29C]
0x1400f26c1  mov     dword ptr [rsp+2F0h+var_29C], 0
0x1400f26c9  xor     r9d, r9d; lpType
0x1400f26cc  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1400f26d1  xor     r8d, r8d; lpReserved
0x1400f26d4  mov     [rsp+2F0h+cbData], 4
0x1400f26dc  call    cs:__imp_RegQueryValueExW
0x1400f26e2  mov     edi, eax
0x1400f26e4  test    eax, eax
0x1400f26e6  jle     short loc_1400F26F1
0x1400f26e8  movzx   edi, ax
0x1400f26eb  or      edi, 80070000h
0x1400f26f1  test    edi, edi
0x1400f26f3  js      short loc_1400F2718
0x1400f26f5  mov     ecx, dword ptr [rsp+2F0h+var_29C]
0x1400f26f9  mov     eax, ecx
0x1400f26fb  xor     eax, r14d
0x1400f26fe  test    eax, 0FFFFFFh
0x1400f2703  jnz     short loc_1400F270C
0x1400f2705  inc     ebx
0x1400f2707  jmp     loc_1400F266B
0x1400f270c  movsxd  rax, r15d
0x1400f270f  inc     r15d
0x1400f2712  mov     [rbp+rax*4+1F0h+var_268], ecx
0x1400f2716  jmp     short loc_1400F2705
0x1400f2718  inc     ebx
0x1400f271a  test    edi, edi
0x1400f271c  jns     loc_1400F266B
0x1400f2722  xor     esi, esi
0x1400f2724  xor     ebx, ebx
0x1400f2726  lea     r14d, [rsi+1]
0x1400f272a  cmp     ebx, r15d
0x1400f272d  jge     loc_1400F27C1
0x1400f2733  lea     r9, aColorhistory; "ColorHistory"
0x1400f273a  mov     [rsp+2F0h+dwOptions], esi
0x1400f273e  lea     r8, aSU; "%s%u"
0x1400f2745  mov     edx, 104h; unsigned __int64
0x1400f274a  lea     rcx, [rbp+1F0h+ValueName]; unsigned __int16 *
0x1400f274e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400f2753  test    eax, eax
0x1400f2755  js      short loc_1400F27B6
0x1400f2757  movsxd  rax, ebx
0x1400f275a  lea     r8, [rbp+1F0h+var_268]
0x1400f275e  xor     edx, edx
0x1400f2760  lea     r8, [r8+rax*4]
0x1400f2764  cmp     edx, ebx
0x1400f2766  jge     short loc_1400F2784
0x1400f2768  movsxd  rax, edx
0x1400f276b  mov     ecx, [rbp+rax*4+1F0h+var_268]
0x1400f276f  xor     ecx, [r8]
0x1400f2772  test    ecx, 0FFFFFFh
0x1400f2778  jz      short loc_1400F277F
0x1400f277a  add     edx, r14d
0x1400f277d  jmp     short loc_1400F2764
0x1400f277f  add     ebx, r14d
0x1400f2782  jmp     short loc_1400F272A
0x1400f2784  mov     rcx, [rsp+2F0h+var_290]; hKey
0x1400f2789  lea     rdx, [rbp+1F0h+ValueName]; lpValueName
0x1400f278d  mov     eax, 4
0x1400f2792  mov     [rsp+2F0h+samDesired], eax; cbData
0x1400f2796  mov     r9d, eax; dwType
0x1400f2799  mov     qword ptr [rsp+2F0h+dwOptions], r8; lpData
0x1400f279e  xor     r8d, r8d; Reserved
0x1400f27a1  call    cs:__imp_RegSetValueExW
0x1400f27a7  test    eax, eax
0x1400f27a9  jle     short loc_1400F27B3
0x1400f27ab  movzx   eax, ax
0x1400f27ae  or      eax, 80070000h
0x1400f27b3  add     esi, r14d
0x1400f27b6  add     ebx, r14d
0x1400f27b9  test    eax, eax
0x1400f27bb  jns     loc_1400F272A
0x1400f27c1  xor     ebx, ebx
0x1400f27c3  mov     edi, esi
0x1400f27c5  cmp     edi, 5
0x1400f27c8  jge     loc_1400F2885
0x1400f27ce  cmp     ebx, 5
0x1400f27d1  jge     loc_1400F2885
0x1400f27d7  lea     r9, aColorhistory; "ColorHistory"
0x1400f27de  mov     [rsp+2F0h+dwOptions], edi
0x1400f27e2  lea     r8, aSU; "%s%u"
0x1400f27e9  mov     edx, 104h; unsigned __int64
0x1400f27ee  lea     rcx, [rbp+1F0h+ValueName]; unsigned __int16 *
0x1400f27f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400f27f7  mov     edx, eax
0x1400f27f9  test    eax, eax
0x1400f27fb  js      short loc_1400F2877
0x1400f27fd  mov     r10d, 4
0x1400f2803  cmp     ebx, 5
0x1400f2806  jge     short loc_1400F2877
0x1400f2808  cmp     ebx, r10d
0x1400f280b  jnb     short loc_1400F2877
0x1400f280d  movsxd  rcx, ebx
0x1400f2810  lea     r9, qword_1402020F0
0x1400f2817  xor     r8d, r8d
0x1400f281a  mov     r9d, [r9+rcx*4]
0x1400f281e  mov     dword ptr [rsp+2F0h+var_29C], r9d
0x1400f2823  cmp     r8d, esi
0x1400f2826  jge     short loc_1400F2844
0x1400f2828  movsxd  rax, r8d
0x1400f282b  mov     ecx, r9d
0x1400f282e  xor     ecx, [rbp+rax*4+1F0h+var_268]
0x1400f2832  test    ecx, 0FFFFFFh
0x1400f2838  jz      short loc_1400F283F
0x1400f283a  add     r8d, r14d
0x1400f283d  jmp     short loc_1400F2823
0x1400f283f  add     ebx, r14d
0x1400f2842  jmp     short loc_1400F2803
0x1400f2844  mov     rcx, [rsp+2F0h+var_290]; hKey
0x1400f2849  lea     rax, [rsp+2F0h+var_29C]
0x1400f284e  mov     [rsp+2F0h+samDesired], r10d; cbData
0x1400f2853  lea     rdx, [rbp+1F0h+ValueName]; lpValueName
0x1400f2857  mov     r9d, r10d; dwType
0x1400f285a  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1400f285f  xor     r8d, r8d; Reserved
0x1400f2862  call    cs:__imp_RegSetValueExW
0x1400f2868  mov     edx, eax
0x1400f286a  test    eax, eax
0x1400f286c  jle     short loc_1400F2877
0x1400f286e  movzx   edx, ax
0x1400f2871  or      edx, 80070000h
0x1400f2877  add     edi, r14d
0x1400f287a  add     ebx, r14d
0x1400f287d  test    edx, edx
0x1400f287f  jns     loc_1400F27C5
0x1400f2885  mov     ebx, 4
0x1400f288a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1400f288f  lea     rax, [rsp+2F0h+var_280]
0x1400f2894  mov     [rsp+2F0h+samDesired], ebx; cbData
0x1400f2898  lea     rdx, aAutocolor; "AutoColor"
0x1400f289f  mov     r9d, ebx; dwType
0x1400f28a2  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1400f28a7  xor     r8d, r8d; Reserved
0x1400f28aa  mov     dword ptr [rsp+2F0h+var_280], r12d
0x1400f28af  call    cs:__imp_RegSetValueExW
0x1400f28b5  xor     ebx, ebx
0x1400f28b7  lea     rcx, [rsp+2F0h+var_278]; this
0x1400f28bc  call    ??1CCurrentColorUser@@QEAA@XZ; CCurrentColorUser::~CCurrentColorUser(void)
0x1400f28c1  lea     rcx, [rsp+2F0h+var_290]
0x1400f28c6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400f28cb  lea     rcx, [rsp+2F0h+hKey]
0x1400f28d0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400f28d5  mov     eax, ebx
0x1400f28d7  mov     rcx, [rbp+1F0h+var_40]
  ... truncated ...
```
