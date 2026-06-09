# VersionUtils::ReadCurrentOSVersion(void)

- ea: `0x18006371c`
- end: `0x180063be4`
- name: `?ReadCurrentOSVersion@VersionUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `1224`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180063290`
- `0x180063630`
- `0x180063bf0`
- `0x180092028`

## callees

- `0x180003220`
- `0x1800109ac`
- `0x180015b6c`
- `0x180016698`
- `0x180019768`
- `0x180019890`
- `0x18001e820`
- `0x180060f58`
- `0x180060f7c`
- `0x180061c34`
- `0x18006371c`
- `0x180077728`
- `0x180077870`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063839`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063891`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800638ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063943`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063a1f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063839`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063891`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800638ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063943`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063a1f`

## string_xrefs

- `0x1800637c9`: `onecore\base\flighting\common\inc\VersionUtils.h`
- `0x18006384e`: `onecore\base\flighting\common\inc\VersionUtils.h`
- `0x1800638a6`: `onecore\base\flighting\common\inc\VersionUtils.h`
- `0x1800638ff`: `onecore\base\flighting\common\inc\VersionUtils.h`
- `0x180063958`: `onecore\base\flighting\common\inc\VersionUtils.h`
- `0x1800639d7`: `onecore\base\flighting\common\inc\VersionUtils.h`
- `0x180063a34`: `onecore\base\flighting\common\inc\VersionUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
HKEY __fastcall VersionUtils::ReadCurrentOSVersion(HKEY a1)
{
  __int64 v2; // r8
  int v3; // ecx
  char v4; // di
  char v5; // al
  unsigned int ValueW; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // r8
  int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  int pdwType; // [rsp+20h] [rbp-5E8h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-5E8h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-5E8h]
  unsigned int pdwTypec; // [rsp+20h] [rbp-5E8h]
  unsigned int pdwTyped; // [rsp+20h] [rbp-5E8h]
  unsigned int pdwTypee; // [rsp+20h] [rbp-5E8h]
  DWORD pcbData; // [rsp+40h] [rbp-5C8h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-5C0h] BYREF
  int v36; // [rsp+50h] [rbp-5B8h] BYREF
  int v37; // [rsp+54h] [rbp-5B4h] BYREF
  int v38; // [rsp+58h] [rbp-5B0h] BYREF
  int v39; // [rsp+5Ch] [rbp-5ACh] BYREF
  int pvData; // [rsp+60h] [rbp-5A8h] BYREF
  HKEY v41[3]; // [rsp+68h] [rbp-5A0h] BYREF
  _BYTE v42[32]; // [rsp+80h] [rbp-588h] BYREF
  _BYTE v43[32]; // [rsp+A0h] [rbp-568h] BYREF
  _BYTE v44[32]; // [rsp+C0h] [rbp-548h] BYREF
  _BYTE v45[32]; // [rsp+E0h] [rbp-528h] BYREF
  _BYTE v46[32]; // [rsp+100h] [rbp-508h] BYREF
  _BYTE v47[32]; // [rsp+120h] [rbp-4E8h] BYREF
  _BYTE v48[32]; // [rsp+140h] [rbp-4C8h] BYREF
  _BYTE v49[32]; // [rsp+160h] [rbp-4A8h] BYREF
  _BYTE v50[32]; // [rsp+180h] [rbp-488h] BYREF
  _BYTE v51[528]; // [rsp+1A0h] [rbp-468h] BYREF
  _BYTE v52[528]; // [rsp+3B0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+608h] [rbp+0h]

  v41[1] = a1;
  hkey = 0;
  RegPersistedKey::RegPersistedKey(
    (RegPersistedKey *)v51,
    L"FeatureManagement",
    L"SYSTEM\\Software\\Microsoft\\BuildLayers");
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0,
    v2);
  v3 = RegPersistedKey::RegOpenKeyW((RegPersistedKey *)v51, L"DesktopEditions", 0x20019u, &hkey);
  if ( (int)(v3 + 0x80000000) < 0 || v3 == -2147024894 )
  {
    v5 = 0;
    v4 = 1;
  }
  else
  {
    v4 = 1;
    v5 = 1;
  }
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
      (const char *)(unsigned int)v3,
      pdwType);
  if ( v3 >= 0 )
  {
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hkey, 0, L"MajorVersion", 0x10u, 0, &pvData, &pcbData);
    if ( ValueW )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
        (const char *)ValueW,
        pdwTypea);
    v39 = 0;
    pcbData = 4;
    v8 = RegGetValueW(hkey, 0, L"MinorVersion", 0x10u, 0, &v39, &pcbData);
    if ( v8 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
        (const char *)v8,
        pdwTypeb);
    v38 = 0;
    pcbData = 4;
    v9 = RegGetValueW(hkey, 0, L"BuildNumber", 0x10u, 0, &v38, &pcbData);
    if ( v9 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
        (const char *)v9,
        pdwTypec);
    v36 = 0;
    pcbData = 4;
    v10 = RegGetValueW(hkey, 0, L"BuildQfe", 0x10u, 0, &v36, &pcbData);
    if ( v10 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
        (const char *)v10,
        pdwTyped);
    v41[0] = 0;
    RegPersistedKey::RegPersistedKey(
      (RegPersistedKey *)v52,
      L"FeatureManagement",
      L"SYSTEM\\Software\\Microsoft\\ServicingLayers");
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      v41,
      0,
      v11);
    v12 = RegPersistedKey::RegOpenKeyW((RegPersistedKey *)v52, L"_EDITION_", 0x20019u, v41);
    if ( ((v12 + 0x80000000) & 0x80000000) != 0 || v12 == -2147024894 )
      v4 = 0;
    if ( v4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
        (const char *)(unsigned int)v12,
        pdwTyped);
    if ( v12 >= 0 )
    {
      v37 = 0;
      pcbData = 4;
      v13 = RegGetValueW(v41[0], 0, L"BuildQfe", 0x10u, 0, &v37, &pcbData);
      if ( v13 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecore\\base\\flighting\\common\\inc\\VersionUtils.h",
          (const char *)v13,
          pdwTypee);
      v36 = v37;
    }
    std::_Integral_to_string<unsigned short,unsigned long>(v45);
    std::_Integral_to_string<unsigned short,unsigned long>(v44);
    std::_Integral_to_string<unsigned short,unsigned long>(v43);
    std::_Integral_to_string<unsigned short,unsigned long>(v42);
    v14 = std::operator+<unsigned short>(v50, v42, L".");
    v15 = std::operator+<unsigned short>(v49, v14, v43);
    v16 = std::operator+<unsigned short>(v48, v15, L".");
    v17 = std::operator+<unsigned short>(v47, v16, v44);
    v18 = std::operator+<unsigned short>(v46, v17, L".");
    std::operator+<unsigned short>(a1, v18, v45);
    std::wstring::_Tidy_deallocate(v46, v19);
    std::wstring::_Tidy_deallocate(v47, v20);
    std::wstring::_Tidy_deallocate(v48, v21);
    std::wstring::_Tidy_deallocate(v49, v22);
    std::wstring::_Tidy_deallocate(v50, v23);
    std::wstring::_Tidy_deallocate(v42, v24);
    std::wstring::_Tidy_deallocate(v43, v25);
    std::wstring::_Tidy_deallocate(v44, v26);
    std::wstring::_Tidy_deallocate(v45, v27);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v41);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return a1;
  }
  else
  {
    std::wstring::wstring(a1);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return a1;
  }
}

```

## disassembly

```asm
0x18006371c  push    rbx
0x18006371e  push    rsi
0x18006371f  push    rdi
0x180063720  push    r12
0x180063722  push    r14
0x180063724  push    r15
0x180063726  sub     rsp, 5D8h
0x18006372d  mov     rax, cs:__security_cookie
0x180063734  xor     rax, rsp
0x180063737  mov     [rsp+608h+var_48], rax
0x18006373f  mov     rbx, rcx
0x180063742  mov     [rsp+608h+var_598], rcx
0x180063747  xor     esi, esi
0x180063749  mov     [rsp+608h+hkey], rsi
0x18006374e  lea     r8, aSystemSoftware; "SYSTEM\\Software\\Microsoft\\BuildLayer"...
0x180063755  lea     rdx, aFeaturemanagem; "FeatureManagement"
0x18006375c  lea     rcx, [rsp+608h+var_468]; this
0x180063764  call    ??0RegPersistedKey@@QEAA@PEBG0@Z; RegPersistedKey::RegPersistedKey(ushort const *,ushort const *)
0x180063769  xor     edx, edx
0x18006376b  lea     rcx, [rsp+608h+hkey]
0x180063770  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180063775  lea     r9, [rsp+608h+hkey]; HKEY *
0x18006377a  mov     r8d, 20019h; unsigned int
0x180063780  lea     rdx, aDesktopedition; "DesktopEditions"
0x180063787  lea     rcx, [rsp+608h+var_468]; this
0x18006378f  call    ?RegOpenKeyW@RegPersistedKey@@QEAAJPEBGKPEAPEAUHKEY__@@@Z; RegPersistedKey::RegOpenKeyW(ushort const *,ulong,HKEY__ * *)
0x180063794  mov     ecx, eax
0x180063796  mov     r12d, 80000000h
0x18006379c  add     eax, r12d
0x18006379f  test    r12d, eax
0x1800637a2  jnz     short loc_1800637B4
0x1800637a4  cmp     ecx, 80070002h
0x1800637aa  jz      short loc_1800637B4
0x1800637ac  mov     dil, 1
0x1800637af  mov     al, dil
0x1800637b2  jmp     short loc_1800637BA
0x1800637b4  mov     al, sil
0x1800637b7  mov     dil, 1
0x1800637ba  mov     r10, [rsp+608h]
0x1800637c2  test    al, al
0x1800637c4  jz      short loc_1800637DD
0x1800637c6  mov     r9d, ecx; char *
0x1800637c9  lea     r8, aOnecoreBaseFli_35; "onecore\\base\\flighting\\common\\inc\\"...
0x1800637d0  mov     edx, 55h ; 'U'; void *
0x1800637d5  mov     rcx, r10; this
0x1800637d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800637dd  test    ecx, ecx
0x1800637df  jns     short loc_1800637FC
0x1800637e1  mov     rcx, rbx
0x1800637e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800637e9  nop
0x1800637ea  lea     rcx, [rsp+608h+hkey]
0x1800637ef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800637f4  mov     rax, rbx
0x1800637f7  jmp     loc_180063BC2
0x1800637fc  mov     [rsp+608h+var_5A8], esi
0x180063800  mov     r14d, 4
0x180063806  mov     [rsp+608h+var_5C8], r14d
0x18006380b  lea     rax, [rsp+608h+var_5C8]
0x180063810  mov     [rsp+608h+pcbData], rax; pcbData
0x180063815  lea     rax, [rsp+608h+var_5A8]
0x18006381a  mov     [rsp+608h+pvData], rax; pvData
0x18006381f  mov     [rsp+608h+pdwType], rsi; unsigned int
0x180063824  lea     r15d, [r14+0Ch]
0x180063828  mov     r9d, r15d; dwFlags
0x18006382b  lea     r8, Value; "MajorVersion"
0x180063832  xor     edx, edx; lpSubKey
0x180063834  mov     rcx, [rsp+608h+hkey]; hkey
0x180063839  call    cs:__imp_RegGetValueW
0x18006383f  mov     rcx, [rsp+608h]; this
0x180063847  test    eax, eax
0x180063849  jz      short loc_18006385E
0x18006384b  mov     r9d, eax; char *
0x18006384e  lea     r8, aOnecoreBaseFli_35; "onecore\\base\\flighting\\common\\inc\\"...
0x180063855  lea     edx, [r14+59h]; void *
0x180063859  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18006385e  mov     [rsp+608h+var_5AC], esi
0x180063862  mov     [rsp+608h+var_5C8], r14d
0x180063867  lea     rax, [rsp+608h+var_5C8]
0x18006386c  mov     [rsp+608h+pcbData], rax; pcbData
0x180063871  lea     rax, [rsp+608h+var_5AC]
0x180063876  mov     [rsp+608h+pvData], rax; pvData
0x18006387b  mov     [rsp+608h+pdwType], rsi; unsigned int
0x180063880  mov     r9d, r15d; dwFlags
0x180063883  lea     r8, aMinorversion; "MinorVersion"
0x18006388a  xor     edx, edx; lpSubKey
0x18006388c  mov     rcx, [rsp+608h+hkey]; hkey
0x180063891  call    cs:__imp_RegGetValueW
0x180063897  mov     rcx, [rsp+608h]; this
0x18006389f  test    eax, eax
0x1800638a1  jz      short loc_1800638B7
0x1800638a3  mov     r9d, eax; char *
0x1800638a6  lea     r8, aOnecoreBaseFli_35; "onecore\\base\\flighting\\common\\inc\\"...
0x1800638ad  mov     edx, 61h ; 'a'; void *
0x1800638b2  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800638b7  mov     [rsp+608h+var_5B0], esi
0x1800638bb  mov     [rsp+608h+var_5C8], r14d
0x1800638c0  lea     rax, [rsp+608h+var_5C8]
0x1800638c5  mov     [rsp+608h+pcbData], rax; pcbData
0x1800638ca  lea     rax, [rsp+608h+var_5B0]
0x1800638cf  mov     [rsp+608h+pvData], rax; pvData
0x1800638d4  mov     [rsp+608h+pdwType], rsi; unsigned int
0x1800638d9  mov     r9d, r15d; dwFlags
0x1800638dc  lea     r8, aBuildnumber; "BuildNumber"
0x1800638e3  xor     edx, edx; lpSubKey
0x1800638e5  mov     rcx, [rsp+608h+hkey]; hkey
0x1800638ea  call    cs:__imp_RegGetValueW
0x1800638f0  mov     rcx, [rsp+608h]; this
0x1800638f8  test    eax, eax
0x1800638fa  jz      short loc_180063910
0x1800638fc  mov     r9d, eax; char *
0x1800638ff  lea     r8, aOnecoreBaseFli_35; "onecore\\base\\flighting\\common\\inc\\"...
0x180063906  mov     edx, 65h ; 'e'; void *
0x18006390b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180063910  mov     [rsp+608h+var_5B8], esi
0x180063914  mov     [rsp+608h+var_5C8], r14d
0x180063919  lea     rax, [rsp+608h+var_5C8]
0x18006391e  mov     [rsp+608h+pcbData], rax; pcbData
0x180063923  lea     rax, [rsp+608h+var_5B8]
0x180063928  mov     [rsp+608h+pvData], rax; pvData
0x18006392d  mov     [rsp+608h+pdwType], rsi; int
0x180063932  mov     r9d, r15d; dwFlags
0x180063935  lea     r8, aBuildqfe; "BuildQfe"
0x18006393c  xor     edx, edx; lpSubKey
0x18006393e  mov     rcx, [rsp+608h+hkey]; hkey
0x180063943  call    cs:__imp_RegGetValueW
0x180063949  mov     rcx, [rsp+608h]; this
0x180063951  test    eax, eax
0x180063953  jz      short loc_180063969
0x180063955  mov     r9d, eax; char *
0x180063958  lea     r8, aOnecoreBaseFli_35; "onecore\\base\\flighting\\common\\inc\\"...
0x18006395f  mov     edx, 69h ; 'i'; void *
0x180063964  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180063969  mov     [rsp+608h+var_5A0], rsi
0x18006396e  lea     r8, aSystemSoftware_0; "SYSTEM\\Software\\Microsoft\\ServicingL"...
0x180063975  lea     rdx, aFeaturemanagem; "FeatureManagement"
0x18006397c  lea     rcx, [rsp+608h+var_258]; this
0x180063984  call    ??0RegPersistedKey@@QEAA@PEBG0@Z; RegPersistedKey::RegPersistedKey(ushort const *,ushort const *)
0x180063989  xor     edx, edx
0x18006398b  lea     rcx, [rsp+608h+var_5A0]
0x180063990  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180063995  lea     r9, [rsp+608h+var_5A0]; HKEY *
0x18006399a  mov     r8d, 20019h; unsigned int
0x1800639a0  lea     rdx, aEdition; "_EDITION_"
0x1800639a7  lea     rcx, [rsp+608h+var_258]; this
0x1800639af  call    ?RegOpenKeyW@RegPersistedKey@@QEAAJPEBGKPEAPEAUHKEY__@@@Z; RegPersistedKey::RegOpenKeyW(ushort const *,ulong,HKEY__ * *)
0x1800639b4  lea     ecx, [rax+r12]
0x1800639b8  test    r12d, ecx
0x1800639bb  jnz     short loc_1800639C4
0x1800639bd  cmp     eax, 80070002h
0x1800639c2  jnz     short loc_1800639C7
0x1800639c4  mov     dil, sil
0x1800639c7  mov     rcx, [rsp+608h]; this
0x1800639cf  test    dil, dil
0x1800639d2  jz      short loc_1800639E8
0x1800639d4  mov     r9d, eax; char *
0x1800639d7  lea     r8, aOnecoreBaseFli_35; "onecore\\base\\flighting\\common\\inc\\"...
0x1800639de  mov     edx, 6Fh ; 'o'; void *
0x1800639e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800639e8  test    eax, eax
0x1800639ea  js      short loc_180063A4F
0x1800639ec  mov     [rsp+608h+var_5B4], esi
0x1800639f0  mov     [rsp+608h+var_5C8], r14d
0x1800639f5  lea     rax, [rsp+608h+var_5C8]
0x1800639fa  mov     [rsp+608h+pcbData], rax; pcbData
0x1800639ff  lea     rax, [rsp+608h+var_5B4]
0x180063a04  mov     [rsp+608h+pvData], rax; pvData
0x180063a09  mov     [rsp+608h+pdwType], rsi; unsigned int
0x180063a0e  mov     r9d, r15d; dwFlags
0x180063a11  lea     r8, aBuildqfe; "BuildQfe"
0x180063a18  xor     edx, edx; lpSubKey
0x180063a1a  mov     rcx, [rsp+608h+var_5A0]; hkey
0x180063a1f  call    cs:__imp_RegGetValueW
0x180063a25  mov     rcx, [rsp+608h]; this
0x180063a2d  test    eax, eax
0x180063a2f  jz      short loc_180063A45
0x180063a31  mov     r9d, eax; char *
0x180063a34  lea     r8, aOnecoreBaseFli_35; "onecore\\base\\flighting\\common\\inc\\"...
0x180063a3b  mov     edx, 74h ; 't'; void *
0x180063a40  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180063a45  mov     edx, [rsp+608h+var_5B4]
0x180063a49  mov     [rsp+608h+var_5B8], edx
0x180063a4d  jmp     short loc_180063A53
0x180063a4f  mov     edx, [rsp+608h+var_5B8]
0x180063a53  lea     rcx, [rsp+608h+var_528]
0x180063a5b  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x180063a60  nop
0x180063a61  mov     edx, [rsp+608h+var_5B0]
0x180063a65  lea     rcx, [rsp+608h+var_548]
0x180063a6d  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x180063a72  nop
0x180063a73  mov     edx, [rsp+608h+var_5AC]
0x180063a77  lea     rcx, [rsp+608h+var_568]
0x180063a7f  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x180063a84  nop
0x180063a85  mov     edx, [rsp+608h+var_5A8]
0x180063a89  lea     rcx, [rsp+608h+var_588]
0x180063a91  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x180063a96  nop
0x180063a97  lea     rdi, Delimiter; "."
0x180063a9e  mov     r8, rdi
0x180063aa1  lea     rdx, [rsp+608h+var_588]
0x180063aa9  lea     rcx, [rsp+608h+var_488]
0x180063ab1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180063ab6  nop
0x180063ab7  lea     r8, [rsp+608h+var_568]
0x180063abf  mov     rdx, rax
0x180063ac2  lea     rcx, [rsp+608h+var_4A8]
0x180063aca  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180063acf  nop
0x180063ad0  mov     r8, rdi
0x180063ad3  mov     rdx, rax
0x180063ad6  lea     rcx, [rsp+608h+var_4C8]
0x180063ade  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180063ae3  nop
0x180063ae4  lea     r8, [rsp+608h+var_548]
0x180063aec  mov     rdx, rax
0x180063aef  lea     rcx, [rsp+608h+var_4E8]
0x180063af7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180063afc  nop
0x180063afd  mov     r8, rdi
0x180063b00  mov     rdx, rax
0x180063b03  lea     rcx, [rsp+608h+var_508]
0x180063b0b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180063b10  nop
0x180063b11  lea     r8, [rsp+608h+var_528]
0x180063b19  mov     rdx, rax
0x180063b1c  mov     rcx, rbx
0x180063b1f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180063b24  nop
0x180063b25  lea     rcx, [rsp+608h+var_508]
0x180063b2d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063b32  nop
0x180063b33  lea     rcx, [rsp+608h+var_4E8]
0x180063b3b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063b40  nop
0x180063b41  lea     rcx, [rsp+608h+var_4C8]
0x180063b49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063b4e  nop
0x180063b4f  lea     rcx, [rsp+608h+var_4A8]
0x180063b57  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063b5c  nop
0x180063b5d  lea     rcx, [rsp+608h+var_488]
0x180063b65  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063b6a  nop
0x180063b6b  lea     rcx, [rsp+608h+var_588]
0x180063b73  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063b78  nop
0x180063b79  lea     rcx, [rsp+608h+var_568]
0x180063b81  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063b86  nop
0x180063b87  lea     rcx, [rsp+608h+var_548]
0x180063b8f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063b94  nop
0x180063b95  lea     rcx, [rsp+608h+var_528]
0x180063b9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063ba2  nop
0x180063ba3  lea     rcx, [rsp+608h+var_5A0]
0x180063ba8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180063bad  nop
0x180063bae  lea     rcx, [rsp+608h+hkey]
0x180063bb3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180063bb8  mov     rax, rbx
0x180063bbb  jmp     short loc_180063BC2
0x180063bbd  mov     rax, [rsp+608h+var_598]
0x180063bc2  mov     rcx, [rsp+608h+var_48]
0x180063bca  xor     rcx, rsp; StackCookie
0x180063bcd  call    __security_check_cookie
0x180063bd2  add     rsp, 5D8h
0x180063bd9  pop     r15
0x180063bdb  pop     r14
0x180063bdd  pop     r12
0x180063bdf  pop     rdi
0x180063be0  pop     rsi
0x180063be1  pop     rbx
0x180063be2  retn
```
