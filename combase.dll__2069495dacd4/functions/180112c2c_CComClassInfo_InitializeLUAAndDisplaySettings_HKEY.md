# CComClassInfo::InitializeLUAAndDisplaySettings(HKEY__ *)

- ea: `0x180112c2c`
- end: `0x1801131b8`
- name: `?InitializeLUAAndDisplaySettings@CComClassInfo@@AEAAJPEAUHKEY__@@@Z`
- size: `1420`
- prototype: `__int64 __fastcall(CComClassInfo *this, HKEY hKeyHKLMClasses)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180063d34`

## callees

- `0x180087534`
- `0x18008db2c`
- `0x1800e7048`
- `0x180112c2c`
- `0x180140d6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180112f10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180112f10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180112fd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180112fd3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180112d34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180112d34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180112e7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180113069`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801130f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180113114`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180112e7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180113069`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801130f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180113114`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180112f50`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180112f50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180112ca2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180112cde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180113010`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801130ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180112ca2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180112cde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180113010`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801130ca`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x180112c72`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x180113198`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x180112c72`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x180113198`

## string_xrefs

- `0x180112cf4`: `onecore\com\combase\catalog\class.cxx`
- `0x180113174`: `onecore\com\combase\catalog\class.cxx`
- `0x180113153`: `CLSID:%ws %!HRESULT!`
- `0x180112ce4`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x180112dd2`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x180112e64`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x180112fb6`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x180112ced`: `CComClassInfo::InitializeLUAAndDisplaySettings`
- `0x18011315f`: `CComClassInfo::InitializeLUAAndDisplaySettings`

## pseudocode

```c
__int64 __fastcall CComClassInfo::InitializeLUAAndDisplaySettings(CComClassInfo *this, HKEY hKeyHKLMClasses)
{
  bool v2; // zf
  LSTATUS v5; // eax
  HRESULT v6; // ebx
  REGSAM v7; // r9d
  LSTATUS v8; // eax
  TraceLevel v9; // r9d
  const wchar_t *v10; // rdx
  HRESULT v11; // edi
  LSTATUS v12; // eax
  TraceLevel v13; // r9d
  HRESULT file; // ebx
  int v15; // r8d
  HRESULT RegistryStringValue; // eax
  TraceLevel v17; // r9d
  wchar_t *v18; // rax
  wchar_t *v19; // rdi
  LSTATUS MUIStringW; // eax
  TraceLevel v21; // r9d
  unsigned int m_regView; // r9d
  LSTATUS v23; // eax
  wchar_t **p_m_pwszBinaryName; // rdi
  HRESULT v25; // eax
  HRESULT v26; // eax
  REGSAM v27; // r9d
  LSTATUS v28; // eax
  unsigned int dwSize; // [rsp+40h] [rbp-20h] BYREF
  HKEY__ *hKeyClsid; // [rsp+48h] [rbp-18h] BYREF
  HKEY__ *hKeyLUA; // [rsp+50h] [rbp-10h] BYREF
  HKEY__ *hKeyInprocServer32; // [rsp+A0h] [rbp+40h] BYREF
  int bResult; // [rsp+B0h] [rbp+50h] BYREF
  int v35; // [rsp+B8h] [rbp+58h]

  v2 = this->m_regView == 512;
  bResult = 0;
  hKeyClsid = 0;
  v35 = 0;
  if ( v2 )
    LOWORD(v35) = Wow64SetThreadDefaultGuestMachine(this->m_regWowArchitecture);
  v5 = RegOpenKeyExW(hKeyHKLMClasses, this->m_wszClsidString, 0, this->m_regView | 0x20019, &hKeyClsid);
  v6 = v5;
  if ( !v5 )
  {
    v7 = this->m_regView | 0x20019;
    hKeyLUA = 0;
    v8 = RegOpenKeyExW(hKeyClsid, L"Elevation", 0, v7, &hKeyLUA);
    v10 = L"CLSID:%ws Value:%ws %!HRESULT!";
    v11 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v11 = (unsigned __int16)v8 | 0x80070000;
      if ( v11 != -2147024894
        && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS)) )
      {
        ComTraceMessageT<unsigned short *,unsigned short const *,long>(
          "onecore\\com\\combase\\catalog\\class.cxx",
          "CComClassInfo::InitializeLUAAndDisplaySettings",
          461,
          v9,
          v10,
          this->m_wszClsidString,
          L"Elevation",
          v11);
      }
      goto LABEL_39;
    }
    LODWORD(hKeyInprocServer32) = 0;
    dwSize = 4;
    v12 = RegQueryValueExW(hKeyLUA, L"Enabled", 0, (LPDWORD)&hKeyInprocServer32, (LPBYTE)&bResult, &dwSize);
    file = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        file = (unsigned __int16)v12 | 0x80070000;
      if ( file != -2147024894
        && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS)) )
      {
        v15 = 436;
        goto LABEL_19;
      }
    }
    else
    {
      if ( (_DWORD)hKeyInprocServer32 == 4 )
      {
        v11 = 0;
        this->m_bLUAEnabled = bResult;
LABEL_23:
        if ( this->m_bLUAEnabled )
        {
          RegistryStringValue = GetRegistryStringValue(hKeyLUA, 0, L"IconReference", 0, &this->m_pwszIconReference);
          v11 = 0;
          if ( RegistryStringValue != -2147024894 )
            v11 = RegistryStringValue;
          if ( v11 < 0
            && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS)) )
          {
            ComTraceMessageT<unsigned short *,unsigned short const *,long>(
              "onecore\\com\\combase\\catalog\\class.cxx",
              "CComClassInfo::InitializeLUAAndDisplaySettings",
              450,
              v17,
              L"CLSID:%ws Value:%ws %!HRESULT!",
              this->m_wszClsidString,
              L"IconReference",
              v11);
          }
        }
LABEL_31:
        RegCloseKey(hKeyLUA);
LABEL_39:
        v6 = 0;
        if ( v11 != -2147024894 )
          v6 = v11;
        if ( v6 >= 0 && this->m_bLUAEnabled )
        {
          v18 = (wchar_t *)HeapAlloc(g_hHeap, 0, 0x200u);
          v19 = v18;
          if ( v18 )
          {
            MUIStringW = RegLoadMUIStringW(hKeyClsid, g_wszDisplayName, v18, 0x200u, 0, 1u, 0);
            if ( MUIStringW )
            {
              if ( MUIStringW > 0 )
                v6 = (unsigned __int16)MUIStringW | 0x80070000;
              else
                v6 = MUIStringW;
              if ( v6 != -2147024894
                && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS)) )
              {
                ComTraceMessageT<unsigned short *,unsigned short const *,long>(
                  "onecore\\com\\combase\\catalog\\class.cxx",
                  "CComClassInfo::InitializeLUAAndDisplaySettings",
                  481,
                  v21,
                  L"CLSID:%ws Value:%ws %!HRESULT!",
                  this->m_wszClsidString,
                  g_wszDisplayName,
                  v6);
              }
              HeapFree(g_hHeap, 0, v19);
            }
            else
            {
              this->m_pwszDisplayName = v19;
            }
            if ( v6 >= 0 )
            {
              m_regView = this->m_regView;
              hKeyInprocServer32 = 0;
              v23 = RegOpenKeyExW(
                      hKeyClsid,
                      Com::Catalog::Constants::LocalServer32,
                      0,
                      m_regView | 0x20019,
                      &hKeyInprocServer32);
              v6 = v23;
              if ( v23 )
              {
                if ( v23 > 0 )
                  v6 = (unsigned __int16)v23 | 0x80070000;
                p_m_pwszBinaryName = &this->m_pwszBinaryName;
              }
              else
              {
                p_m_pwszBinaryName = &this->m_pwszBinaryName;
                v25 = GetRegistryStringValue(
                        hKeyInprocServer32,
                        0,
                        Com::Catalog::Constants::ServerExecutable,
                        0,
                        &this->m_pwszBinaryName);
                if ( v25 != -2147024894 )
                  v6 = v25;
                if ( v6 >= 0 && !*p_m_pwszBinaryName )
                  v6 = GetRegistryStringValue(hKeyInprocServer32, 0, 0, 0, &this->m_pwszBinaryName);
                RegCloseKey(hKeyInprocServer32);
              }
              if ( (int)(v6 + 0x80000000) < 0 || v6 == -2147024894 )
              {
                v26 = 0;
                if ( v6 != -2147024894 )
                  v26 = v6;
                v6 = v26;
                if ( !*p_m_pwszBinaryName )
                {
                  v27 = this->m_regView | 0x20019;
                  hKeyInprocServer32 = 0;
                  v28 = RegOpenKeyExW(hKeyClsid, Com::Catalog::Constants::InprocServer32, 0, v27, &hKeyInprocServer32);
                  v6 = v28;
                  if ( v28 )
                  {
                    if ( v28 > 0 )
                      v6 = (unsigned __int16)v28 | 0x80070000;
                  }
                  else
                  {
                    v6 = GetRegistryStringValue(hKeyInprocServer32, 0, 0, 0, p_m_pwszBinaryName);
                    RegCloseKey(hKeyInprocServer32);
                  }
                  if ( v6 == -2147024894 )
                    v6 = 0;
                }
              }
            }
          }
          else
          {
            v6 = -2147024882;
          }
        }
        RegCloseKey(hKeyClsid);
        goto LABEL_86;
      }
      file = -2147221165;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      {
        v15 = 427;
LABEL_19:
        ComTraceMessageT<unsigned short *,unsigned short const *,long>(
          "onecore\\com\\combase\\catalog\\class.cxx",
          "CComClassInfo::InitializeLUAAndDisplaySettings",
          v15,
          v13,
          L"CLSID:%ws Value:%ws %!HRESULT!",
          this->m_wszClsidString,
          L"Enabled",
          file);
      }
    }
    v11 = 0;
    if ( file != -2147024894 )
      v11 = file;
    if ( v11 < 0 )
      goto LABEL_31;
    goto LABEL_23;
  }
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 != -2147024894
    && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS)) )
  {
    ComTraceMessageT<unsigned short *,long>(
      "onecore\\com\\combase\\catalog\\class.cxx",
      "CComClassInfo::InitializeLUAAndDisplaySettings",
      545,
      ERRORS,
      L"CLSID:%ws %!HRESULT!",
      this->m_wszClsidString,
      v6);
  }
LABEL_86:
  if ( v6 == -2147024894 )
    v6 = 0;
  if ( this->m_regView == 512 )
    Wow64SetThreadDefaultGuestMachine((unsigned __int16)v35);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180112c2c  mov     [rsp-38h+arg_8], rbx
0x180112c31  push    rbp
0x180112c32  push    rsi
0x180112c33  push    rdi
0x180112c34  push    r12
0x180112c36  push    r13
0x180112c38  push    r14
0x180112c3a  push    r15
0x180112c3c  mov     rbp, rsp
0x180112c3f  sub     rsp, 60h
0x180112c43  cmp     dword ptr [this+0ECh], 200h
0x180112c4d  mov     rbx, hKeyHKLMClasses
0x180112c50  mov     rsi, this
0x180112c53  mov     [rbp+bResult], 0
0x180112c5a  mov     [rbp+hKeyClsid], 0
0x180112c62  mov     [rbp+arg_18], 0
0x180112c69  jnz     short loc_180112C7C
0x180112c6b  movzx   ecx, word ptr [this+0F0h]
0x180112c72  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x180112c78  mov     word ptr [rbp+arg_18], ax
0x180112c7c  mov     r9d, [rsi+0ECh]
0x180112c83  lea     rax, [rbp+hKeyClsid]
0x180112c87  lea     rdi, [rsi+70h]
0x180112c8b  mov     [rsp+60h+phkResult], rax; phkResult
0x180112c90  mov     r14d, 20019h
0x180112c96  mov     hKeyHKLMClasses, rdi; lpSubKey
0x180112c99  or      r9d, r14d; samDesired
0x180112c9c  xor     r8d, r8d; ulOptions
0x180112c9f  mov     this, rbx; hKey
0x180112ca2  call    cs:__imp_RegOpenKeyExW
0x180112ca8  mov     ebx, eax
0x180112caa  test    eax, eax
0x180112cac  jnz     loc_18011311C
0x180112cb2  mov     r9d, [rsi+0ECh]
0x180112cb9  lea     rax, [rbp+hKeyLUA]
0x180112cbd  mov     this, [rbp+hKeyClsid]; hKey
0x180112cc1  lea     rbx, aElevation; "Elevation"
0x180112cc8  or      r9d, r14d; samDesired
0x180112ccb  mov     [rbp+hKeyLUA], 0
0x180112cd3  mov     hKeyHKLMClasses, rbx; lpSubKey
0x180112cd6  mov     [rsp+60h+phkResult], rax; phkResult
0x180112cdb  xor     r8d, r8d; ulOptions
0x180112cde  call    cs:__imp_RegOpenKeyExW
0x180112ce4  lea     hKeyHKLMClasses, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x180112ceb  mov     edi, eax
0x180112ced  lea     r12, aCcomclassinfoI_2; "CComClassInfo::InitializeLUAAndDisplayS"...
0x180112cf4  lea     r13, aOnecoreComComb_119; "onecore\\com\\combase\\catalog\\class.c"...
0x180112cfb  test    eax, eax
0x180112cfd  jnz     loc_180112E84
0x180112d03  mov     this, [rbp+hKeyLUA]; hKey
0x180112d07  lea     rdi, aEnabled; "Enabled"
0x180112d0e  mov     dword ptr [rbp+hKeyInprocServer32], eax
0x180112d11  lea     r9, [rbp+hKeyInprocServer32]; lpType
0x180112d15  lea     rax, [rbp+dwSize]
0x180112d19  mov     [rbp+dwSize], 4
0x180112d20  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180112d25  xor     r8d, r8d; lpReserved
0x180112d28  lea     rax, [rbp+bResult]
0x180112d2c  mov     hKeyHKLMClasses, rdi; lpValueName
0x180112d2f  mov     [rsp+60h+phkResult], rax; lpData
0x180112d34  call    cs:__imp_RegQueryValueExW
0x180112d3a  mov     r15d, 80070000h
0x180112d40  mov     ebx, eax
0x180112d42  lea     r14d, [r15+2]
0x180112d46  test    eax, eax
0x180112d48  jnz     short loc_180112D8A
0x180112d4a  cmp     dword ptr [rbp+hKeyInprocServer32], 4
0x180112d4e  jnz     short loc_180112D60
0x180112d50  mov     eax, [rbp+bResult]
0x180112d53  xor     edi, edi
0x180112d55  mov     [rsi+134h], eax
0x180112d5b  jmp     loc_180112DF3
0x180112d60  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180112d66  mov     ebx, 80040153h
0x180112d6b  test    eax, eax
0x180112d6d  jnz     short loc_180112D82
0x180112d6f  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180112d75  jz      short loc_180112DE3
0x180112d77  xor     ecx, ecx; level
0x180112d79  call    IsWppLevelEnabled
0x180112d7e  test    al, al
0x180112d80  jz      short loc_180112DE3
0x180112d82  mov     r8d, 1ABh
0x180112d88  jmp     short loc_180112DBA
0x180112d8a  jle     short loc_180112D92
0x180112d8c  movzx   ebx, ax
0x180112d8f  or      ebx, r15d
0x180112d92  cmp     ebx, r14d
0x180112d95  jz      short loc_180112DE3
0x180112d97  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180112d9d  test    eax, eax
0x180112d9f  jnz     short loc_180112DB4
0x180112da1  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180112da7  jz      short loc_180112DE3
0x180112da9  xor     ecx, ecx; level
0x180112dab  call    IsWppLevelEnabled
0x180112db0  test    al, al
0x180112db2  jz      short loc_180112DE3
0x180112db4  mov     r8d, 1B4h; line
0x180112dba  mov     [rsp+60h+file], ebx; file
0x180112dbe  lea     rax, [rsi+70h]
0x180112dc2  mov     [rsp+60h+pszDirectory], rdi; <args_2>
0x180112dc7  mov     hKeyHKLMClasses, r12; function
0x180112dca  mov     [rsp+60h+lpcbData], rax; <args_1>
0x180112dcf  mov     this, r13; file
0x180112dd2  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x180112dd9  mov     [rsp+60h+phkResult], rax; <args_0>
0x180112dde  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x180112de3  xor     edi, edi
0x180112de5  cmp     ebx, r14d
0x180112de8  cmovnz  edi, ebx
0x180112deb  test    edi, edi
0x180112ded  js      loc_180112E78
0x180112df3  cmp     dword ptr [rsi+134h], 0
0x180112dfa  jz      short loc_180112E78
0x180112dfc  mov     this, [rbp+hKeyLUA]; hParent
0x180112e00  lea     rax, [rsi+150h]
0x180112e07  lea     rbx, aIconreference; "IconReference"
0x180112e0e  mov     [rsp+60h+phkResult], rax; ppwszValue
0x180112e13  mov     r8, rbx; pwszValueName
0x180112e16  xor     r9d, r9d; dwQueryFlags
0x180112e19  xor     edx, edx; pwszSubKeyName
0x180112e1b  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180112e20  xor     edi, edi
0x180112e22  cmp     eax, r14d
0x180112e25  cmovnz  edi, eax
0x180112e28  test    edi, edi
0x180112e2a  jns     short loc_180112E78
0x180112e2c  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180112e32  test    eax, eax
0x180112e34  jnz     short loc_180112E49
0x180112e36  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180112e3c  jz      short loc_180112E78
0x180112e3e  xor     ecx, ecx; level
0x180112e40  call    IsWppLevelEnabled
0x180112e45  test    al, al
0x180112e47  jz      short loc_180112E78
0x180112e49  mov     [rsp+60h+file], edi; file
0x180112e4d  lea     rax, [rsi+70h]
0x180112e51  mov     [rsp+60h+pszDirectory], rbx; <args_2>
0x180112e56  mov     r8d, 1C2h; line
0x180112e5c  mov     [rsp+60h+lpcbData], rax; <args_1>
0x180112e61  mov     hKeyHKLMClasses, r12; function
0x180112e64  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x180112e6b  mov     this, r13; file
0x180112e6e  mov     [rsp+60h+phkResult], rax; <args_0>
0x180112e73  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x180112e78  mov     this, [rbp+hKeyLUA]; hKey
0x180112e7c  call    cs:__imp_RegCloseKey
0x180112e82  jmp     short loc_180112EE4
0x180112e84  mov     r15d, 80070000h
0x180112e8a  test    eax, eax
0x180112e8c  jle     short loc_180112E94
0x180112e8e  movzx   edi, ax
0x180112e91  or      edi, r15d
0x180112e94  mov     r14d, 80070002h
0x180112e9a  cmp     edi, r14d
0x180112e9d  jz      short loc_180112EE4
0x180112e9f  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180112ea5  test    eax, eax
0x180112ea7  jnz     short loc_180112EBC
0x180112ea9  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180112eaf  jz      short loc_180112EE4
0x180112eb1  xor     ecx, ecx; level
0x180112eb3  call    IsWppLevelEnabled
0x180112eb8  test    al, al
0x180112eba  jz      short loc_180112EE4
0x180112ebc  mov     [rsp+60h+file], edi; file
0x180112ec0  lea     rax, [rsi+70h]
0x180112ec4  mov     [rsp+60h+pszDirectory], rbx; <args_2>
0x180112ec9  mov     r8d, 1CDh; line
0x180112ecf  mov     [rsp+60h+lpcbData], rax; <args_1>
0x180112ed4  mov     this, r13; file
0x180112ed7  mov     [rsp+60h+phkResult], hKeyHKLMClasses; <args_0>
0x180112edc  mov     hKeyHKLMClasses, r12; function
0x180112edf  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x180112ee4  xor     ebx, ebx
0x180112ee6  cmp     edi, r14d
0x180112ee9  cmovnz  ebx, edi
0x180112eec  test    ebx, ebx
0x180112eee  js      loc_180113110
0x180112ef4  cmp     dword ptr [rsi+134h], 0
0x180112efb  jz      loc_180113110
0x180112f01  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180112f08  xor     edx, edx; dwFlags
0x180112f0a  mov     r8d, 200h; dwBytes
0x180112f10  call    cs:__imp_HeapAlloc
0x180112f16  mov     rdi, rax
0x180112f19  test    rax, rax
0x180112f1c  jz      loc_18011310B
0x180112f22  mov     this, [rbp+hKeyClsid]; hKey
0x180112f26  lea     hKeyHKLMClasses, g_wszDisplayName; pszValue
0x180112f2d  mov     [rsp+60h+pszDirectory], 0; pszDirectory
0x180112f36  mov     r9d, 200h; cbOutBuf
0x180112f3c  mov     dword ptr [rsp+60h+lpcbData], 1; Flags
0x180112f44  mov     r8, rax; pszOutBuf
0x180112f47  mov     [rsp+60h+phkResult], 0; pcbData
0x180112f50  call    cs:__imp_RegLoadMUIStringW
0x180112f56  test    eax, eax
0x180112f58  jnz     short loc_180112F63
0x180112f5a  mov     [rsi+140h], rdi
0x180112f61  jmp     short loc_180112FD9
0x180112f63  jg      short loc_180112F69
0x180112f65  mov     ebx, eax
0x180112f67  jmp     short loc_180112F6F
0x180112f69  movzx   ebx, ax
0x180112f6c  or      ebx, r15d
0x180112f6f  cmp     ebx, r14d
0x180112f72  jz      short loc_180112FC7
0x180112f74  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180112f7a  test    eax, eax
0x180112f7c  jnz     short loc_180112F91
0x180112f7e  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180112f84  jz      short loc_180112FC7
0x180112f86  xor     ecx, ecx; level
0x180112f88  call    IsWppLevelEnabled
0x180112f8d  test    al, al
0x180112f8f  jz      short loc_180112FC7
0x180112f91  mov     [rsp+60h+file], ebx; file
0x180112f95  lea     rax, g_wszDisplayName
0x180112f9c  mov     [rsp+60h+pszDirectory], rax; <args_2>
0x180112fa1  mov     r8d, 1E1h; line
0x180112fa7  lea     rax, [rsi+70h]
0x180112fab  mov     hKeyHKLMClasses, r12; function
0x180112fae  mov     [rsp+60h+lpcbData], rax; <args_1>
0x180112fb3  mov     this, r13; file
0x180112fb6  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x180112fbd  mov     [rsp+60h+phkResult], rax; <args_0>
0x180112fc2  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x180112fc7  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180112fce  mov     r8, rdi; lpMem
0x180112fd1  xor     edx, edx; dwFlags
0x180112fd3  call    cs:__imp_HeapFree
0x180112fd9  test    ebx, ebx
0x180112fdb  js      loc_180113110
0x180112fe1  mov     r9d, [rsi+0ECh]
0x180112fe8  lea     rax, [rbp+hKeyInprocServer32]
0x180112fec  mov     this, [rbp+hKeyClsid]; hKey
0x180112ff0  lea     hKeyHKLMClasses, ?LocalServer32@Constants@Catalog@Com@@3QBGB; lpSubKey
0x180112ff7  mov     r12d, 20019h
0x180112ffd  mov     [rbp+hKeyInprocServer32], 0
0x180113005  or      r9d, r12d; samDesired
0x180113008  mov     [rsp+60h+phkResult], rax; phkResult
0x18011300d  xor     r8d, r8d; ulOptions
0x180113010  call    cs:__imp_RegOpenKeyExW
0x180113016  mov     ebx, eax
0x180113018  test    eax, eax
0x18011301a  jnz     short loc_180113071
0x18011301c  mov     this, [rbp+hKeyInprocServer32]; hParent
0x180113020  lea     rdi, [rsi+148h]
0x180113027  xor     r9d, r9d; dwQueryFlags
0x18011302a  mov     [rsp+60h+phkResult], rdi; ppwszValue
0x18011302f  lea     r8, ?ServerExecutable@Constants@Catalog@Com@@3QBGB; pwszValueName
0x180113036  xor     edx, edx; pwszSubKeyName
0x180113038  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x18011303d  cmp     eax, r14d
0x180113040  cmovnz  ebx, eax
0x180113043  test    ebx, ebx
0x180113045  js      short loc_180113065
0x180113047  cmp     qword ptr [rdi], 0
0x18011304b  jnz     short loc_180113065
0x18011304d  mov     this, [rbp+hKeyInprocServer32]; hParent
0x180113051  xor     r9d, r9d; dwQueryFlags
0x180113054  xor     r8d, r8d; pwszValueName
0x180113057  mov     [rsp+60h+phkResult], rdi; ppwszValue
0x18011305c  xor     edx, edx; pwszSubKeyName
0x18011305e  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180113063  mov     ebx, eax
0x180113065  mov     this, [rbp+hKeyInprocServer32]; hKey
0x180113069  call    cs:__imp_RegCloseKey
0x18011306f  jmp     short loc_180113080
0x180113071  jle     short loc_180113079
0x180113073  movzx   ebx, ax
0x180113076  or      ebx, r15d
0x180113079  lea     rdi, [rsi+148h]
0x180113080  mov     ecx, 80000000h
0x180113085  lea     eax, [rbx+this]
0x180113088  test    ecx, eax
0x18011308a  jnz     short loc_180113091
0x18011308c  cmp     ebx, r14d
0x18011308f  jnz     short loc_180113110
0x180113091  xor     eax, eax
0x180113093  cmp     ebx, r14d
0x180113096  cmovnz  eax, ebx
0x180113099  cmp     qword ptr [rdi], 0
0x18011309d  mov     ebx, eax
0x18011309f  jnz     short loc_180113110
0x1801130a1  mov     r9d, [rsi+0ECh]
0x1801130a8  lea     rax, [rbp+hKeyInprocServer32]
0x1801130ac  mov     this, [rbp+hKeyClsid]; hKey
0x1801130b0  lea     hKeyHKLMClasses, ?InprocServer32@Constants@Catalog@Com@@3QBGB; lpSubKey
0x1801130b7  or      r9d, r12d; samDesired
0x1801130ba  mov     [rbp+hKeyInprocServer32], 0
0x1801130c2  xor     r8d, r8d; ulOptions
0x1801130c5  mov     [rsp+60h+phkResult], rax; phkResult
0x1801130ca  call    cs:__imp_RegOpenKeyExW
0x1801130d0  mov     ebx, eax
0x1801130d2  test    eax, eax
0x1801130d4  jnz     short loc_1801130FA
0x1801130d6  mov     this, [rbp+hKeyInprocServer32]; hParent
  ... truncated ...
```
