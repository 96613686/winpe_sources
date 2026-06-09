# Microsoft::HostGuardian::Client::Plugin::HgsClientData::SetShsValuesFromRegistry(void)

- ea: `0x1800065c0`
- end: `0x1800068e6`
- name: `?SetShsValuesFromRegistry@HgsClientData@Plugin@Client@HostGuardian@Microsoft@@AEAAXXZ`
- size: `806`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::Plugin::HgsClientData *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006060`

## callees

- `0x180001520`
- `0x180005ad8`
- `0x180005d20`
- `0x180005e18`
- `0x180006260`
- `0x1800062ec`
- `0x18000642c`
- `0x1800065c0`
- `0x180006b00`
- `0x180006ce8`
- `0x1800085ec`
- `0x1800087e0`
- `0x1800088cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800066f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800066f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006670`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006670`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006698`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006698`

## string_xrefs

- `0x1800065eb`: `RemoteAttestationService`
- `0x18000660f`: `KdsService`
- `0x1800068a6`: `Failed to read the fallback service URL settings because the number of URL's found was %d.`
- `0x180006680`: `Failed to call RegOpenKeyEx. subKey: %ws. Error code:0X%08X`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::HgsClientData::SetShsValuesFromRegistry(
        Microsoft::HostGuardian::Client::Plugin::HgsClientData *this,
        __int64 a2,
        __int64 a3)
{
  __int64 RegistryKeyForString; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rax
  unsigned int v8; // eax
  HKEY v9; // rdx
  const wchar_t *v10; // r9
  int v11; // ebx
  Microsoft::HostGuardian::Client::Plugin::RegistryUtilities *v12; // rcx
  __int64 RegistryKeyForQword; // rax
  const wchar_t *v14; // r9
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  unsigned __int64 v21; // r9
  unsigned __int64 v22; // r9
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // r14
  __int64 v25; // rsi
  __int64 v26; // r8
  BYTE Data[8]; // [rsp+30h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-11h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-9h] BYREF
  __int64 v30; // [rsp+48h] [rbp-1h] BYREF
  __int64 v31; // [rsp+50h] [rbp+7h]
  _BYTE v32[32]; // [rsp+60h] [rbp+17h] BYREF

  RegistryKeyForString = Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString(
                           v32,
                           a2,
                           a3,
                           L"RemoteAttestationService");
  std::wstring::operator=(this, RegistryKeyForString);
  std::wstring::~wstring(v32);
  v7 = Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString(v32, v5, v6, L"KdsService");
  std::wstring::operator=((char *)this + 32, v7);
  std::wstring::~wstring(v32);
  Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForMultiString(&v30);
  *(_DWORD *)Data = 0;
  hKey = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\HgsClient", 0, 0x20019u, &hKey);
  if ( v8 )
  {
    Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(
      (wchar_t *)L"Failed to call RegOpenKeyEx. subKey: %ws. Error code:0X%08X",
      L"SOFTWARE\\Microsoft\\HgsClient",
      v8);
LABEL_3:
    v11 = *(_DWORD *)Data;
    goto LABEL_4;
  }
  cbData = 4;
  v16 = RegQueryValueExW(hKey, L"MaxRetries", 0, 0, Data, &cbData);
  if ( !v16 )
    goto LABEL_3;
  Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(
    (wchar_t *)L"Failed to call RegQueryValueEx. subKey: %ws. valueName: %ws. Error code:0X%08X",
    L"SOFTWARE\\Microsoft\\HgsClient",
    L"MaxRetries",
    v16);
  v11 = 0;
  *(_DWORD *)Data = 0;
LABEL_4:
  v12 = (Microsoft::HostGuardian::Client::Plugin::RegistryUtilities *)hKey;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v11 )
    *((_DWORD *)this + 29) = v11;
  RegistryKeyForQword = Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForQword(
                          v12,
                          v9,
                          L"RequestTimeout",
                          v10);
  if ( RegistryKeyForQword > 0 )
    v15 = RegistryKeyForQword / 1000;
  else
    v15 = 0;
  *((_DWORD *)this + 31) = v15;
  v17 = Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForQword(
          (Microsoft::HostGuardian::Client::Plugin::RegistryUtilities *)RegistryKeyForQword,
          (HKEY)v15,
          L"OperationTimeout",
          v14);
  if ( v17 > 0 )
    v18 = v17 / 1000;
  else
    LODWORD(v18) = 0;
  *((_DWORD *)this + 30) = v18;
  v19 = v31;
  v20 = v30;
  if ( v30 == v31 )
  {
    Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(
      (wchar_t *)L"Failed to read the fallback service URL settings because the number of URL's found was %d.",
      0);
    goto LABEL_35;
  }
  v21 = (v31 - v30) >> 5;
  if ( (v21 & 1) != 0 )
  {
    Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(
      (wchar_t *)L"Failed to read the fallback service URL settings because the number of URL's found was %d.",
      (const wchar_t *)((v31 - v30) >> 5));
    goto LABEL_35;
  }
  v22 = v21 >> 1;
  hKey = (HKEY)v22;
  if ( v22 > (__int64)(*((_QWORD *)this + 10) - *((_QWORD *)this + 8)) >> 5 )
  {
    if ( v22 > 0x7FFFFFFFFFFFFFFLL )
      goto LABEL_36;
    std::vector<std::wstring>::_Reallocate<0>((char *)this + 64, &hKey);
    v19 = v31;
    v20 = v30;
  }
  v23 = (unsigned __int64)((v19 - v20) >> 5) >> 1;
  hKey = (HKEY)v23;
  if ( v23 <= (__int64)(*((_QWORD *)this + 13) - *((_QWORD *)this + 11)) >> 5 )
    goto LABEL_25;
  if ( v23 > 0x7FFFFFFFFFFFFFFLL )
LABEL_36:
    std::vector<enum AttestationResultType>::_Xlength();
  std::vector<std::wstring>::_Reallocate<0>((char *)this + 88, &hKey);
  v19 = v31;
  v20 = v30;
LABEL_25:
  v24 = 0;
  if ( (v19 - v20) >> 5 )
  {
    do
    {
      v25 = 32 * v24;
      v26 = 32 * v24 + v20;
      if ( *((_QWORD *)this + 9) == *((_QWORD *)this + 10) )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(
          (char *)this + 64,
          *((_QWORD *)this + 9),
          v26);
      }
      else
      {
        std::wstring::wstring(*((_QWORD *)this + 9), v26);
        *((_QWORD *)this + 9) += 32LL;
      }
      if ( *((_QWORD *)this + 12) == *((_QWORD *)this + 13) )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(
          (char *)this + 88,
          *((_QWORD *)this + 12),
          v25 + v30 + 32);
      }
      else
      {
        std::wstring::wstring(*((_QWORD *)this + 12), v25 + v30 + 32);
        *((_QWORD *)this + 12) += 32LL;
      }
      v24 += 2LL;
      v20 = v30;
    }
    while ( v24 < (v31 - v30) >> 5 );
  }
LABEL_35:
  std::vector<std::wstring>::~vector<std::wstring>(&v30);
}

```

## disassembly

```asm
0x1800065c0  mov     [rsp-8+arg_8], rbx
0x1800065c5  mov     [rsp-8+arg_10], rsi
0x1800065ca  push    rbp
0x1800065cb  push    rdi
0x1800065cc  push    r14
0x1800065ce  lea     rbp, [rsp-47h]
0x1800065d3  sub     rsp, 90h
0x1800065da  mov     rax, cs:__security_cookie
0x1800065e1  xor     rax, rsp
0x1800065e4  mov     [rbp+57h+var_20], rax
0x1800065e8  mov     rdi, rcx
0x1800065eb  lea     r9, aRemoteattestat; "RemoteAttestationService"
0x1800065f2  lea     rcx, [rbp+57h+var_40]
0x1800065f6  call    ?QueryRegistryKeyForString@RegistryUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAUHKEY__@@PEB_W1@Z; Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString(HKEY__ * const,wchar_t const *,wchar_t const *)
0x1800065fb  mov     rdx, rax
0x1800065fe  mov     rcx, rdi
0x180006601  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180006606  lea     rcx, [rbp+57h+var_40]
0x18000660a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000660f  lea     r9, aKdsservice; "KdsService"
0x180006616  lea     rcx, [rbp+57h+var_40]
0x18000661a  call    ?QueryRegistryKeyForString@RegistryUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAUHKEY__@@PEB_W1@Z; Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString(HKEY__ * const,wchar_t const *,wchar_t const *)
0x18000661f  lea     rcx, [rdi+20h]
0x180006623  mov     rdx, rax
0x180006626  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000662b  lea     rcx, [rbp+57h+var_40]
0x18000662f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006634  lea     rcx, [rbp+57h+var_58]
0x180006638  call    ?QueryRegistryKeyForMultiString@RegistryUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAUHKEY__@@PEB_W1@Z; Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForMultiString(HKEY__ * const,wchar_t const *,wchar_t const *)
0x18000663d  nop
0x18000663e  mov     dword ptr [rbp+57h+Data], 0
0x180006645  mov     [rbp+57h+hKey], 0
0x18000664d  lea     rax, [rbp+57h+hKey]
0x180006651  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180006656  mov     r9d, 20019h; samDesired
0x18000665c  xor     r8d, r8d; ulOptions
0x18000665f  lea     rbx, aSoftwareMicros; "SOFTWARE\\Microsoft\\HgsClient"
0x180006666  mov     rdx, rbx; lpSubKey
0x180006669  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006670  call    cs:__imp_RegOpenKeyExW
0x180006676  test    eax, eax
0x180006678  jz      short loc_1800066C7
0x18000667a  mov     r8d, eax
0x18000667d  mov     rdx, rbx; wchar_t *
0x180006680  lea     rcx, aFailedToCallRe; "Failed to call RegOpenKeyEx. subKey: %w"...
0x180006687  call    ?TraceWarning@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(wchar_t const *,...)
0x18000668c  mov     ebx, dword ptr [rbp+57h+Data]
0x18000668f  mov     rcx, [rbp+57h+hKey]; hKey
0x180006693  test    rcx, rcx
0x180006696  jz      short loc_18000669E
0x180006698  call    cs:__imp_RegCloseKey
0x18000669e  test    ebx, ebx
0x1800066a0  jz      short loc_1800066A5
0x1800066a2  mov     [rdi+74h], ebx
0x1800066a5  lea     r8, aRequesttimeout; "RequestTimeout"
0x1800066ac  call    ?QueryRegistryKeyForQword@RegistryUtilities@Plugin@Client@HostGuardian@Microsoft@@YA_JQEAUHKEY__@@PEB_W1@Z; Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForQword(HKEY__ * const,wchar_t const *,wchar_t const *)
0x1800066b1  mov     rcx, rax; this
0x1800066b4  mov     rbx, 20C49BA5E353F7CFh
0x1800066be  test    rax, rax
0x1800066c1  jg      short loc_18000671E
0x1800066c3  xor     edx, edx
0x1800066c5  jmp     short loc_180006732
0x1800066c7  mov     [rbp+57h+cbData], 4
0x1800066ce  lea     rax, [rbp+57h+cbData]
0x1800066d2  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x1800066d7  lea     rax, [rbp+57h+Data]
0x1800066db  mov     [rsp+0A0h+phkResult], rax; lpData
0x1800066e0  xor     r9d, r9d; lpType
0x1800066e3  xor     r8d, r8d; lpReserved
0x1800066e6  lea     rdx, ValueName; "MaxRetries"
0x1800066ed  mov     rcx, [rbp+57h+hKey]; hKey
0x1800066f1  call    cs:__imp_RegQueryValueExW
0x1800066f7  test    eax, eax
0x1800066f9  jz      short loc_18000668C
0x1800066fb  mov     r9d, eax
0x1800066fe  lea     r8, ValueName; "MaxRetries"
0x180006705  mov     rdx, rbx; wchar_t *
0x180006708  lea     rcx, aFailedToCallRe_2; "Failed to call RegQueryValueEx. subKey:"...
0x18000670f  call    ?TraceWarning@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(wchar_t const *,...)
0x180006714  xor     ebx, ebx
0x180006716  mov     dword ptr [rbp+57h+Data], ebx
0x180006719  jmp     loc_18000668F
0x18000671e  mov     rax, rbx
0x180006721  imul    rcx
0x180006724  sar     rdx, 7
0x180006728  mov     rax, rdx
0x18000672b  shr     rax, 3Fh
0x18000672f  add     rdx, rax; HKEY
0x180006732  mov     [rdi+7Ch], edx
0x180006735  lea     r8, aOperationtimeo; "OperationTimeout"
0x18000673c  call    ?QueryRegistryKeyForQword@RegistryUtilities@Plugin@Client@HostGuardian@Microsoft@@YA_JQEAUHKEY__@@PEB_W1@Z; Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForQword(HKEY__ * const,wchar_t const *,wchar_t const *)
0x180006741  mov     rcx, rax
0x180006744  test    rax, rax
0x180006747  jg      short loc_18000674D
0x180006749  xor     edx, edx
0x18000674b  jmp     short loc_180006761
0x18000674d  mov     rax, rbx
0x180006750  imul    rcx
0x180006753  sar     rdx, 7
0x180006757  mov     rax, rdx
0x18000675a  shr     rax, 3Fh
0x18000675e  add     rdx, rax
0x180006761  mov     [rdi+78h], edx
0x180006764  mov     rcx, [rbp+57h+var_50]
0x180006768  mov     r8, [rbp+57h+var_58]
0x18000676c  cmp     r8, rcx
0x18000676f  jnz     short loc_180006778
0x180006771  xor     edx, edx
0x180006773  jmp     loc_1800068A6
0x180006778  mov     rdx, rcx
0x18000677b  sub     rdx, r8
0x18000677e  mov     r9, rdx
0x180006781  sar     r9, 5
0x180006785  test    r9b, 1
0x180006789  jnz     loc_1800068A2
0x18000678f  lea     rbx, [rdi+40h]
0x180006793  shr     r9, 1
0x180006796  mov     [rbp+57h+hKey], r9
0x18000679a  mov     rax, [rbx+10h]
0x18000679e  sub     rax, [rbx]
0x1800067a1  sar     rax, 5
0x1800067a5  mov     rsi, 7FFFFFFFFFFFFFFh
0x1800067af  cmp     r9, rax
0x1800067b2  jbe     short loc_1800067D1
0x1800067b4  cmp     r9, rsi
0x1800067b7  ja      loc_1800068E0
0x1800067bd  lea     rdx, [rbp+57h+hKey]
0x1800067c1  mov     rcx, rbx
0x1800067c4  call    ??$_Reallocate@$0A@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::wstring>::_Reallocate<0>(unsigned __int64 &)
0x1800067c9  mov     rcx, [rbp+57h+var_50]
0x1800067cd  mov     r8, [rbp+57h+var_58]
0x1800067d1  mov     rdx, rcx
0x1800067d4  sub     rdx, r8
0x1800067d7  sar     rdx, 5
0x1800067db  shr     rdx, 1
0x1800067de  mov     [rbp+57h+hKey], rdx
0x1800067e2  mov     rax, [rdi+68h]
0x1800067e6  sub     rax, [rdi+58h]
0x1800067ea  sar     rax, 5
0x1800067ee  cmp     rdx, rax
0x1800067f1  jbe     short loc_180006811
0x1800067f3  cmp     rdx, rsi
0x1800067f6  ja      loc_1800068E0
0x1800067fc  lea     rdx, [rbp+57h+hKey]
0x180006800  lea     rcx, [rdi+58h]
0x180006804  call    ??$_Reallocate@$0A@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::wstring>::_Reallocate<0>(unsigned __int64 &)
0x180006809  mov     rcx, [rbp+57h+var_50]
0x18000680d  mov     r8, [rbp+57h+var_58]
0x180006811  xor     r14d, r14d
0x180006814  sub     rcx, r8
0x180006817  sar     rcx, 5
0x18000681b  test    rcx, rcx
0x18000681e  jz      loc_1800068B3
0x180006824  mov     rsi, r14
0x180006827  shl     rsi, 5
0x18000682b  add     r8, rsi
0x18000682e  mov     rax, [rbx+8]
0x180006832  cmp     rax, [rbx+10h]
0x180006836  jz      short loc_18000684A
0x180006838  mov     rdx, r8
0x18000683b  mov     rcx, rax
0x18000683e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180006843  add     qword ptr [rbx+8], 20h ; ' '
0x180006848  jmp     short loc_180006855
0x18000684a  mov     rdx, rax
0x18000684d  mov     rcx, rbx
0x180006850  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180006855  mov     r8, [rbp+57h+var_58]
0x180006859  add     r8, 20h ; ' '
0x18000685d  add     r8, rsi
0x180006860  mov     rax, [rdi+60h]
0x180006864  cmp     rax, [rdi+68h]
0x180006868  jz      short loc_18000687C
0x18000686a  mov     rdx, r8
0x18000686d  mov     rcx, rax
0x180006870  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180006875  add     qword ptr [rdi+60h], 20h ; ' '
0x18000687a  jmp     short loc_180006888
0x18000687c  mov     rdx, rax
0x18000687f  lea     rcx, [rdi+58h]
0x180006883  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180006888  add     r14, 2
0x18000688c  mov     rax, [rbp+57h+var_50]
0x180006890  mov     r8, [rbp+57h+var_58]
0x180006894  sub     rax, r8
0x180006897  sar     rax, 5
0x18000689b  cmp     r14, rax
0x18000689e  jb      short loc_180006824
0x1800068a0  jmp     short loc_1800068B3
0x1800068a2  sar     rdx, 5; wchar_t *
0x1800068a6  lea     rcx, aFailedToReadTh; "Failed to read the fallback service URL"...
0x1800068ad  call    ?TraceWarning@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(wchar_t const *,...)
0x1800068b2  nop
0x1800068b3  lea     rcx, [rbp+57h+var_58]
0x1800068b7  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800068bc  mov     rcx, [rbp+57h+var_20]
0x1800068c0  xor     rcx, rsp; StackCookie
0x1800068c3  call    __security_check_cookie
0x1800068c8  lea     r11, [rsp+0A0h+var_10]
0x1800068d0  mov     rbx, [r11+28h]
0x1800068d4  mov     rsi, [r11+30h]
0x1800068d8  mov     rsp, r11
0x1800068db  pop     r14
0x1800068dd  pop     rdi
0x1800068de  pop     rbp
0x1800068df  retn
0x1800068e0  call    ?_Xlength@?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@CAXXZ; std::vector<AttestationResultType>::_Xlength(void)
```
