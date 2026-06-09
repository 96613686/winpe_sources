# CComClassInfo::InitializeLocalServer(int,HKEY__ *,bool,ushort)

- ea: `0x180114280`
- end: `0x1801147a0`
- name: `?InitializeLocalServer@CComClassInfo@@AEAAJHPEAUHKEY__@@_NG@Z`
- size: `1312`
- prototype: `__int64 __fastcall(CComClassInfo *this, int hKeyCLSID, HKEY supportsDarwinId, bool defaultArchitectureForView, unsigned __int16 fInSCM)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18010e818`

## callees

- `0x180062788`
- `0x180087534`
- `0x18008db2c`
- `0x1800e7048`
- `0x1800e740c`
- `0x180114280`
- `0x180140d6c`
- `0x18015ddc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011435e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180114772`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011435e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180114772`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180114787`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180114787`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801142c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801142c0`

## string_xrefs

- `0x18011446d`: `onecore\com\combase\catalog\class.cxx`
- `0x1801144ac`: `onecore\com\combase\catalog\class.cxx`
- `0x180114527`: `onecore\com\combase\catalog\class.cxx`
- `0x180114593`: `onecore\com\combase\catalog\class.cxx`
- `0x180114684`: `onecore\com\combase\catalog\class.cxx`
- `0x180114741`: `onecore\com\combase\catalog\class.cxx`
- `0x180114406`: `CLSID:%ws %!HRESULT!`
- `0x18011445e`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x1801144bb`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x18011452e`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x18011473a`: `CLSID:%ws FileNotFound on server architecture query, continuing on%ws %!HRESULT!`
- `0x1801146f7`: `CLSID:%ws Unable to determine server architecture, treating as fatal%ws %!HRESULT!`
- `0x180114581`: `CLSID:%ws Value:%!HRESULT!`
- `0x18011467d`: `CLSID:%ws Binary architecture doesn't match registry view architecture. Server:%ws %!HRESULT!`
- `0x1801142c8`: `CComClassInfo::InitializeLocalServer`

## pseudocode

```c
__int64 __fastcall CComClassInfo::InitializeLocalServer(
        CComClassInfo *this,
        int hKeyCLSID,
        HKEY supportsDarwinId,
        bool defaultArchitectureForView,
        unsigned __int16 fInSCM)
{
  HRESULT file; // ebx
  bool v8; // sf
  int v9; // r14d
  int v10; // edx
  TraceLevel v11; // r9d
  wchar_t *v12; // rsi
  const wchar_t **p_m_pwszLocalServer; // rsi
  HRESULT RegistryStringValue; // eax
  CComClassInfo *v15; // rcx
  TraceLevel v16; // r9d
  int ExeArchitectureFromRegString; // eax
  wchar_t *v18; // r8
  HKEY__ *hKeyLocalServer; // [rsp+40h] [rbp-28h] BYREF
  wchar_t *pwszDarwinId; // [rsp+48h] [rbp-20h] BYREF
  wchar_t *pwszDarwinLocalServer; // [rsp+50h] [rbp-18h] BYREF

  hKeyLocalServer = 0;
  file = RegOpenKeyExW(supportsDarwinId, Com::Catalog::Constants::LocalServer32, 0, 0x20019u, &hKeyLocalServer);
  v8 = file < 0;
  if ( file )
  {
    if ( file > 0 )
    {
      file = (unsigned __int16)file | 0x80070000;
      v8 = file < 0;
    }
    if ( v8 )
    {
LABEL_17:
      if ( file != -2147024894 )
      {
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          ComTraceMessageT<unsigned short *,long>(
            "onecore\\com\\combase\\catalog\\class.cxx",
            "CComClassInfo::InitializeLocalServer",
            920,
            ERRORS,
            L"CLSID:%ws %!HRESULT!",
            this->m_wszClsidString,
            file);
        goto $Cleanup_6;
      }
LABEL_70:
      file = 0;
      goto $Cleanup_6;
    }
  }
  v9 = 0;
  if ( defaultArchitectureForView )
  {
    pwszDarwinId = 0;
    pwszDarwinLocalServer = 0;
    file = GetRegistryStringValue(hKeyLocalServer, 0, Com::Catalog::Constants::LocalServer32, 1u, &pwszDarwinId);
    if ( file < 0 )
    {
      if ( file != -2147024894 )
      {
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          ComTraceMessageT<unsigned short *,unsigned short const *,long>(
            "onecore\\com\\combase\\catalog\\class.cxx",
            "CComClassInfo::InitializeLocalServer",
            824,
            v11,
            L"CLSID:%ws Value:%ws %!HRESULT!",
            this->m_wszClsidString,
            Com::Catalog::Constants::LocalServer32,
            file);
        goto $Cleanup_6;
      }
    }
    else
    {
      v12 = pwszDarwinId;
      file = CComClassInfo::GetPathFromDarwinDescriptor(this, v10, pwszDarwinId, &pwszDarwinLocalServer);
      if ( v12 && v12 != g_wszEmptyString )
        HeapFree(g_hHeap, 0, v12);
      if ( file < 0 )
      {
        v9 = -2147467229;
        if ( file != -2147467229 )
        {
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
            ComTraceMessageT<unsigned short *,unsigned short *,long>(
              "onecore\\com\\combase\\catalog\\class.cxx",
              "CComClassInfo::InitializeLocalServer",
              805,
              ERRORS,
              L"CLSID:%ws Value:%ws %!HRESULT!",
              this->m_wszClsidString,
              0,
              file);
          goto $Cleanup_6;
        }
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          ComTraceMessageT<unsigned short *,unsigned short *,long>(
            "onecore\\com\\combase\\catalog\\class.cxx",
            "CComClassInfo::InitializeLocalServer",
            811,
            ERRORS,
            L"CLSID:%ws Value:%ws %!HRESULT!",
            this->m_wszClsidString,
            0,
            -2147467229);
      }
      else
      {
        this->m_pwszLocalServer = pwszDarwinLocalServer;
      }
    }
  }
  p_m_pwszLocalServer = (const wchar_t **)&this->m_pwszLocalServer;
  if ( !this->m_pwszLocalServer )
  {
    file = GetRegistryStringValue(hKeyLocalServer, 0, 0, 0, &this->m_pwszLocalServer);
    if ( file == -2147024894 )
    {
      file = v9;
      if ( v9 >= 0 )
        file = -2147024894;
      if ( file < 0 )
        goto LABEL_17;
    }
    else if ( file < 0 )
    {
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<unsigned short *,long>(
          "onecore\\com\\combase\\catalog\\class.cxx",
          "CComClassInfo::InitializeLocalServer",
          844,
          ERRORS,
          L"CLSID:%ws Value:%!HRESULT!",
          this->m_wszClsidString,
          file);
      goto $Cleanup_6;
    }
  }
  RegistryStringValue = GetRegistryStringValue(
                          hKeyLocalServer,
                          0,
                          Com::Catalog::Constants::ServerExecutable,
                          0,
                          &this->m_pwszServerExecutable);
  file = 0;
  if ( RegistryStringValue != -2147024894 )
    file = RegistryStringValue;
  if ( file >= 0 )
  {
    if ( !*p_m_pwszLocalServer )
      goto $Cleanup_6;
    ExeArchitectureFromRegString = CComClassInfo::GetExeArchitectureFromRegString(
                                     v15,
                                     *p_m_pwszLocalServer,
                                     &this->m_dwOutofprocServerBinaryArchitecture);
    file = ExeArchitectureFromRegString;
    if ( ExeArchitectureFromRegString >= 0 )
    {
      if ( fInSCM
        && this->m_dwOutofprocServerBinaryArchitecture != fInSCM
        && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(WARNING)) )
      {
        ComTraceMessageT<unsigned short *,unsigned short *,long>(
          "onecore\\com\\combase\\catalog\\class.cxx",
          "CComClassInfo::InitializeLocalServer",
          883,
          WARNING,
          L"CLSID:%ws Binary architecture doesn't match registry view architecture. Server:%ws %!HRESULT!",
          this->m_wszClsidString,
          (wchar_t *)*p_m_pwszLocalServer,
          file);
      }
      this->m_clsctx |= 4u;
      this->m_serverType = LocalServerType32;
      goto LABEL_70;
    }
    if ( (unsigned int)(ExeArchitectureFromRegString + 2147024894) <= 1 )
    {
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(WARNING) )
        ComTraceMessageT<unsigned short *,unsigned short *,long>(
          "onecore\\com\\combase\\catalog\\class.cxx",
          "CComClassInfo::InitializeLocalServer",
          890,
          WARNING,
          L"CLSID:%ws FileNotFound on server architecture query, continuing on%ws %!HRESULT!",
          this->m_wszClsidString,
          (wchar_t *)*p_m_pwszLocalServer,
          file);
      v18 = (wchar_t *)*p_m_pwszLocalServer;
      if ( *p_m_pwszLocalServer && v18 != g_wszEmptyString )
        HeapFree(g_hHeap, 0, v18);
      *p_m_pwszLocalServer = 0;
      goto LABEL_70;
    }
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(WARNING) )
      ComTraceMessageT<unsigned short *,unsigned short *,long>(
        "onecore\\com\\combase\\catalog\\class.cxx",
        "CComClassInfo::InitializeLocalServer",
        900,
        WARNING,
        L"CLSID:%ws Unable to determine server architecture, treating as fatal%ws %!HRESULT!",
        this->m_wszClsidString,
        (wchar_t *)*p_m_pwszLocalServer,
        file);
  }
  else if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
  {
    ComTraceMessageT<unsigned short *,unsigned short const *,long>(
      "onecore\\com\\combase\\catalog\\class.cxx",
      "CComClassInfo::InitializeLocalServer",
      863,
      v16,
      L"CLSID:%ws Value:%ws %!HRESULT!",
      this->m_wszClsidString,
      Com::Catalog::Constants::ServerExecutable,
      file);
  }
$Cleanup_6:
  if ( hKeyLocalServer )
    RegCloseKey(hKeyLocalServer);
  return (unsigned int)file;
}

```

## disassembly

```asm
0x180114280  push    rbp
0x180114282  push    rbx
0x180114283  push    rsi
0x180114284  push    rdi
0x180114285  push    r12
0x180114287  push    r13
0x180114289  push    r14
0x18011428b  push    r15
0x18011428d  mov     rbp, rsp
0x180114290  sub     rsp, 68h
0x180114294  mov     rdi, this
0x180114297  lea     rdx, ?LocalServer32@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18011429e  mov     rax, hKeyCLSID
0x1801142a1  lea     this, [rbp+hKeyLocalServer]
0x1801142a5  mov     [rsp+68h+phkResult], this; phkResult
0x1801142aa  mov     sil, supportsDarwinId
0x1801142ad  xor     r15d, r15d
0x1801142b0  mov     this, rax; hKey
0x1801142b3  mov     r9d, 20019h; samDesired
0x1801142b9  mov     [rbp+hKeyLocalServer], r15
0x1801142bd  xor     r8d, r8d; ulOptions
0x1801142c0  call    cs:__imp_RegOpenKeyExW
0x1801142c6  mov     ebx, eax
0x1801142c8  lea     r13, aCcomclassinfoI_4; "CComClassInfo::InitializeLocalServer"
0x1801142cf  mov     eax, 80070002h
0x1801142d4  test    ebx, ebx
0x1801142d6  jz      short loc_1801142EB
0x1801142d8  jle     short loc_1801142E5
0x1801142da  movzx   ebx, bx
0x1801142dd  or      ebx, 80070000h
0x1801142e3  test    ebx, ebx
0x1801142e5  js      loc_1801143BD
0x1801142eb  mov     r14d, r15d
0x1801142ee  mov     r12d, 1
0x1801142f4  test    sil, sil
0x1801142f7  jz      short loc_180114377
0x1801142f9  mov     this, [rbp+hKeyLocalServer]; hParent
0x1801142fd  lea     rax, [rbp+pwszDarwinId]
0x180114301  lea     rsi, ?LocalServer32@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::LocalServer32
0x180114308  mov     [rbp+pwszDarwinId], r15
0x18011430c  mov     hKeyCLSID, rsi; pwszValueName
0x18011430f  mov     [rbp+pwszDarwinLocalServer], r15
0x180114313  mov     r9d, r12d; dwQueryFlags
0x180114316  mov     [rsp+68h+phkResult], rax; ppwszValue
0x18011431b  xor     edx, edx; pwszSubKeyName
0x18011431d  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180114322  mov     ebx, eax
0x180114324  test    eax, eax
0x180114326  js      loc_1801144DA
0x18011432c  mov     rsi, [rbp+pwszDarwinId]
0x180114330  lea     r9, [rbp+pwszDarwinLocalServer]; fInScm
0x180114334  mov     hKeyCLSID, rsi; ppszPath
0x180114337  mov     this, rdi; this
0x18011433a  call    ?GetPathFromDarwinDescriptor@CComClassInfo@@AEAAJHPEAGPEAPEAG@Z; CComClassInfo::GetPathFromDarwinDescriptor(int,ushort *,ushort * *)
0x18011433f  mov     ebx, eax
0x180114341  test    rsi, rsi
0x180114344  jz      short loc_180114364
0x180114346  lea     rax, ?g_wszEmptyString@@3QBGB; ushort const near * const g_wszEmptyString
0x18011434d  cmp     rsi, rax
0x180114350  jz      short loc_180114364
0x180114352  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180114359  mov     hKeyCLSID, rsi; lpMem
0x18011435c  xor     edx, edx; dwFlags
0x18011435e  call    cs:__imp_HeapFree
0x180114364  test    ebx, ebx
0x180114366  js      loc_180114412
0x18011436c  mov     rax, [rbp+pwszDarwinLocalServer]
0x180114370  mov     [rdi+108h], rax
0x180114377  lea     rsi, [rdi+108h]
0x18011437e  cmp     [rsi], r15
0x180114381  jnz     loc_1801145A4
0x180114387  mov     this, [rbp+hKeyLocalServer]; hParent
0x18011438b  xor     r9d, r9d; dwQueryFlags
0x18011438e  xor     r8d, r8d; pwszValueName
0x180114391  mov     [rsp+68h+phkResult], rsi; ppwszValue
0x180114396  xor     edx, edx; pwszSubKeyName
0x180114398  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x18011439d  mov     ebx, eax
0x18011439f  mov     eax, 80070002h
0x1801143a4  cmp     ebx, eax
0x1801143a6  jnz     loc_180114544
0x1801143ac  test    r14d, r14d
0x1801143af  mov     ebx, r14d
0x1801143b2  cmovns  ebx, eax
0x1801143b5  test    ebx, ebx
0x1801143b7  jns     loc_1801145A4
0x1801143bd  cmp     ebx, eax
0x1801143bf  jz      loc_18011477B
0x1801143c5  test    ebx, ebx
0x1801143c7  jns     $Cleanup_6
0x1801143cd  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801143d3  test    eax, eax
0x1801143d5  jnz     short loc_1801143F3
0x1801143d7  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1801143de  jz      $Cleanup_6
0x1801143e4  xor     ecx, ecx; level
0x1801143e6  call    IsWppLevelEnabled
0x1801143eb  test    al, al
0x1801143ed  jz      $Cleanup_6
0x1801143f3  lea     rax, [rdi+70h]
0x1801143f7  mov     [rsp+68h+var_38], ebx
0x1801143fb  mov     [rsp+68h+var_40], rax
0x180114400  mov     r8d, 398h
0x180114406  lea     rax, aClsidWsHresult_0; "CLSID:%ws %!HRESULT!"
0x18011440d  jmp     loc_180114588
0x180114412  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180114418  mov     r14d, 80004023h
0x18011441e  cmp     ebx, r14d
0x180114421  jz      short loc_18011447E
0x180114423  test    eax, eax
0x180114425  jnz     short loc_180114443
0x180114427  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18011442e  jz      $Cleanup_6
0x180114434  xor     ecx, ecx; level
0x180114436  call    IsWppLevelEnabled
0x18011443b  test    al, al
0x18011443d  jz      $Cleanup_6
0x180114443  lea     rax, [rdi+70h]
0x180114447  mov     [rsp+68h+file], ebx; <args_2>
0x18011444b  mov     qword ptr [rsp+68h+var_38], r15; <args_1>
0x180114450  xor     r9d, r9d; level
0x180114453  mov     [rsp+68h+var_40], rax; <args_0>
0x180114458  mov     r8d, 325h; line
0x18011445e  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x180114465  mov     rdx, r13; function
0x180114468  mov     [rsp+68h+phkResult], rax; format
0x18011446d  lea     this, aOnecoreComComb_119; "onecore\\com\\combase\\catalog\\class.c"...
0x180114474  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x180114479  jmp     $Cleanup_6
0x18011447e  test    eax, eax
0x180114480  jnz     short loc_18011449E
0x180114482  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180114489  jz      loc_180114377
0x18011448f  xor     ecx, ecx; level
0x180114491  call    IsWppLevelEnabled
0x180114496  test    al, al
0x180114498  jz      loc_180114377
0x18011449e  mov     [rsp+68h+file], r14d; <args_2>
0x1801144a3  lea     rax, [rdi+70h]
0x1801144a7  mov     qword ptr [rsp+68h+var_38], r15; <args_1>
0x1801144ac  lea     this, aOnecoreComComb_119; "onecore\\com\\combase\\catalog\\class.c"...
0x1801144b3  mov     [rsp+68h+var_40], rax; <args_0>
0x1801144b8  xor     r9d, r9d; level
0x1801144bb  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x1801144c2  mov     r8d, 32Bh; line
0x1801144c8  mov     rdx, r13; function
0x1801144cb  mov     [rsp+68h+phkResult], rax; format
0x1801144d0  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x1801144d5  jmp     loc_180114377
0x1801144da  cmp     ebx, 80070002h
0x1801144e0  jz      loc_180114377
0x1801144e6  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801144ec  test    eax, eax
0x1801144ee  jnz     short loc_18011450C
0x1801144f0  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1801144f7  jz      $Cleanup_6
0x1801144fd  xor     ecx, ecx; level
0x1801144ff  call    IsWppLevelEnabled
0x180114504  test    al, al
0x180114506  jz      $Cleanup_6
0x18011450c  mov     [rsp+68h+file], ebx; file
0x180114510  mov     r8d, 338h; line
0x180114516  mov     qword ptr [rsp+68h+var_38], rsi; <args_2>
0x18011451b  lea     rax, [rdi+70h]
0x18011451f  mov     rdx, r13; function
0x180114522  mov     [rsp+68h+var_40], rax; <args_1>
0x180114527  lea     this, aOnecoreComComb_119; "onecore\\com\\combase\\catalog\\class.c"...
0x18011452e  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x180114535  mov     [rsp+68h+phkResult], rax; <args_0>
0x18011453a  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x18011453f  jmp     $Cleanup_6
0x180114544  test    ebx, ebx
0x180114546  jns     short loc_1801145A4
0x180114548  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011454e  test    eax, eax
0x180114550  jnz     short loc_18011456E
0x180114552  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180114559  jz      $Cleanup_6
0x18011455f  xor     ecx, ecx; level
0x180114561  call    IsWppLevelEnabled
0x180114566  test    al, al
0x180114568  jz      $Cleanup_6
0x18011456e  lea     rax, [rdi+70h]
0x180114572  mov     [rsp+68h+var_38], ebx; <args_1>
0x180114576  mov     [rsp+68h+var_40], rax; <args_0>
0x18011457b  mov     r8d, 34Ch; line
0x180114581  lea     rax, aClsidWsValueHr; "CLSID:%ws Value:%!HRESULT!"
0x180114588  xor     r9d, r9d; level
0x18011458b  mov     [rsp+68h+phkResult], rax; format
0x180114590  mov     rdx, r13; function
0x180114593  lea     this, aOnecoreComComb_119; "onecore\\com\\combase\\catalog\\class.c"...
0x18011459a  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x18011459f  jmp     $Cleanup_6
0x1801145a4  mov     this, [rbp+hKeyLocalServer]; hParent
0x1801145a8  lea     rax, [rdi+128h]
0x1801145af  lea     r14, ?ServerExecutable@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::ServerExecutable
0x1801145b6  mov     [rsp+68h+phkResult], rax; ppwszValue
0x1801145bb  mov     hKeyCLSID, r14; pwszValueName
0x1801145be  xor     r9d, r9d; dwQueryFlags
0x1801145c1  xor     edx, edx; pwszSubKeyName
0x1801145c3  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x1801145c8  cmp     eax, 80070002h
0x1801145cd  mov     ebx, r15d
0x1801145d0  cmovnz  ebx, eax
0x1801145d3  test    ebx, ebx
0x1801145d5  jns     short loc_180114611
0x1801145d7  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801145dd  test    eax, eax
0x1801145df  jnz     short loc_1801145FD
0x1801145e1  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1801145e8  jz      $Cleanup_6
0x1801145ee  xor     ecx, ecx; level
0x1801145f0  call    IsWppLevelEnabled
0x1801145f5  test    al, al
0x1801145f7  jz      $Cleanup_6
0x1801145fd  mov     [rsp+68h+file], ebx
0x180114601  mov     r8d, 35Fh
0x180114607  mov     qword ptr [rsp+68h+var_38], r14
0x18011460c  jmp     loc_18011451B
0x180114611  mov     rdx, [rsi]; pwszRegString
0x180114614  test    rdx, rdx
0x180114617  jz      $Cleanup_6
0x18011461d  lea     r14, [rdi+130h]
0x180114624  mov     hKeyCLSID, r14; pExeArchitecture
0x180114627  call    ?GetExeArchitectureFromRegString@CComClassInfo@@AEAAJPEBGPEAK@Z; CComClassInfo::GetExeArchitectureFromRegString(ushort const *,ulong *)
0x18011462c  mov     ebx, eax
0x18011462e  test    eax, eax
0x180114630  js      short loc_1801146A8
0x180114632  movzx   eax, [rbp+arg_20]
0x180114636  test    ax, ax
0x180114639  jz      short loc_180114698
0x18011463b  cmp     [r14], eax
0x18011463e  jz      short loc_180114698
0x180114640  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180114646  test    eax, eax
0x180114648  jnz     short loc_18011465F
0x18011464a  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180114651  jz      short loc_180114698
0x180114653  mov     ecx, r12d; level
0x180114656  call    IsWppLevelEnabled
0x18011465b  test    al, al
0x18011465d  jz      short loc_180114698
0x18011465f  mov     rax, [rsi]
0x180114662  lea     this, [rdi+70h]
0x180114666  mov     [rsp+68h+file], ebx; <args_2>
0x18011466a  mov     r9d, r12d; level
0x18011466d  mov     qword ptr [rsp+68h+var_38], rax; <args_1>
0x180114672  mov     r8d, 373h; line
0x180114678  mov     [rsp+68h+var_40], this; <args_0>
0x18011467d  lea     rax, aClsidWsBinaryA_0; "CLSID:%ws Binary architecture doesn't m"...
0x180114684  lea     this, aOnecoreComComb_119; "onecore\\com\\combase\\catalog\\class.c"...
0x18011468b  mov     [rsp+68h+phkResult], rax; format
0x180114690  mov     rdx, r13; function
0x180114693  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x180114698  or      dword ptr [rdi+0E0h], 4
0x18011469f  mov     [rdi+60h], r12d
0x1801146a3  jmp     loc_18011477B
0x1801146a8  add     eax, 7FF8FFFEh
0x1801146ad  cmp     eax, r12d
0x1801146b0  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801146b6  jbe     short loc_180114703
0x1801146b8  test    eax, eax
0x1801146ba  jnz     short loc_1801146D9
0x1801146bc  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1801146c3  jz      $Cleanup_6
0x1801146c9  mov     ecx, r12d; level
0x1801146cc  call    IsWppLevelEnabled
0x1801146d1  test    al, al
0x1801146d3  jz      $Cleanup_6
0x1801146d9  mov     rax, [rsi]
0x1801146dc  lea     this, [rdi+70h]
0x1801146e0  mov     [rsp+68h+file], ebx
0x1801146e4  mov     r9d, r12d
0x1801146e7  mov     qword ptr [rsp+68h+var_38], rax
0x1801146ec  mov     r8d, 384h
0x1801146f2  mov     [rsp+68h+var_40], this
0x1801146f7  lea     rax, aClsidWsUnableT; "CLSID:%ws Unable to determine server ar"...
0x1801146fe  jmp     loc_180114465
0x180114703  test    eax, eax
0x180114705  jnz     short loc_18011471C
0x180114707  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18011470e  jz      short loc_180114755
0x180114710  mov     ecx, r12d; level
0x180114713  call    IsWppLevelEnabled
0x180114718  test    al, al
0x18011471a  jz      short loc_180114755
0x18011471c  mov     rax, [rsi]
0x18011471f  lea     this, [rdi+70h]
0x180114723  mov     [rsp+68h+file], ebx; <args_2>
0x180114727  mov     r9d, r12d; level
0x18011472a  mov     qword ptr [rsp+68h+var_38], rax; <args_1>
0x18011472f  mov     r8d, 37Ah; line
0x180114735  mov     [rsp+68h+var_40], this; <args_0>
0x18011473a  lea     rax, aClsidWsFilenot; "CLSID:%ws FileNotFound on server archit"...
0x180114741  lea     this, aOnecoreComComb_119; "onecore\\com\\combase\\catalog\\class.c"...
0x180114748  mov     [rsp+68h+phkResult], rax; format
0x18011474d  mov     rdx, r13; function
0x180114750  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x180114755  mov     hKeyCLSID, [rsi]; lpMem
0x180114758  test    hKeyCLSID, hKeyCLSID
  ... truncated ...
```
