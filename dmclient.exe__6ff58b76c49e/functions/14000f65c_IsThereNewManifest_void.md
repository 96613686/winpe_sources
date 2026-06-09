# IsThereNewManifest(void)

- ea: `0x14000f65c`
- end: `0x14000f95d`
- name: `?IsThereNewManifest@@YAHXZ`
- size: `769`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000c47c`

## callees

- `0x140001414`
- `0x1400018cc`
- `0x14000d96c`
- `0x14000dab4`
- `0x14000f65c`
- `0x1400174d0`
- `0x1400187e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000f787`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000f787`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f866`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f866`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000f728`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000f7ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000f728`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000f7ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000f82c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000f82c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000f93b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000f93b`

## string_xrefs

- `0x14000f749`: `Did not obtain the LastDownloadTime from WNF_TEL_ONESETTINGS_UPDATED`
- `0x14000f8c4`: `IsThereNewManifest`

## pseudocode

```c
__int64 IsThereNewManifest(void)
{
  unsigned int v0; // ebx
  int LastDownloadTimeFromWnf; // edi
  const WCHAR *v2; // rdx
  unsigned int ValueW; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  BOOL v6; // esi
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  __int64 v9; // r9
  __int64 v10; // rcx
  DWORD pcbData; // [rsp+50h] [rbp-39h] BYREF
  int v13; // [rsp+54h] [rbp-35h] BYREF
  int v14; // [rsp+58h] [rbp-31h] BYREF
  DWORD pdwType; // [rsp+5Ch] [rbp-2Dh] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-21h] BYREF
  __int64 v18; // [rsp+70h] [rbp-19h] BYREF
  __int64 pvData; // [rsp+78h] [rbp-11h] BYREF
  const char *v20; // [rsp+80h] [rbp-9h] BYREF
  const char *v21; // [rsp+88h] [rbp-1h] BYREF
  const char *v22; // [rsp+90h] [rbp+7h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+98h] [rbp+Fh] BYREF
  unsigned __int64 v24; // [rsp+B0h] [rbp+27h]

  v0 = 1;
  *(_QWORD *)Data = 0;
  pvData = 0;
  pdwType = 11;
  pcbData = 0;
  hKey = 0;
  LastDownloadTimeFromWnf = GetLastDownloadTimeFromWnf((unsigned __int64 *)Data);
  if ( LastDownloadTimeFromWnf >= 0 )
  {
    v6 = 1;
  }
  else
  {
    v24 = 7;
    lpSubKey[2] = 0;
    LOWORD(lpSubKey[0]) = 0;
    GetStateSeparatedDiagTrackRegistryPath(lpSubKey);
    std::wstring::operator+=(lpSubKey, L"\\SettingsRequests\\WINDOWS.SIUF");
    v2 = (const WCHAR *)lpSubKey;
    if ( v24 >= 8 )
      v2 = lpSubKey[0];
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v2, L"LastDownloadTime", 0x48u, &pdwType, Data, &pcbData);
    v6 = ValueW == 0;
    if ( (unsigned int)dword_140027000 > 5 )
    {
      v13 = ValueW;
      v14 = LastDownloadTimeFromWnf;
      v18 = (__int64)"Did not obtain the LastDownloadTime from WNF_TEL_ONESETTINGS_UPDATED";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        ValueW,
        (__int64)byte_140021B85,
        v4,
        v5,
        (const unsigned __int16 **)&v18,
        (__int64)&v14,
        (__int64)&v13);
    }
    if ( v24 >= 8 )
      operator delete((void *)lpSubKey[0]);
  }
  pcbData = 8;
  v7 = RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Siuf",
         L"LastDownloadTime",
         0x48u,
         &pdwType,
         &pvData,
         &pcbData);
  if ( v6 )
  {
    if ( !v7 && *(_QWORD *)Data == pvData )
      v0 = 0;
    if ( *(_QWORD *)Data != pvData
      && !RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Siuf", 0, 0, 0, 0xF003Fu, 0, &hKey, 0) )
    {
      pcbData = 8;
      v8 = RegSetValueExW(hKey, L"LastDownloadTime", 0, 0xBu, Data, 8u);
      v10 = (unsigned int)v8;
      if ( v8
        && (unsigned int)dword_140027000 > 2
        && (qword_140027010 & 0x400000000000LL) != 0
        && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
      {
        v18 = 0x1000000;
        v14 = 659;
        v20 = "IsThereNewManifest";
        v21 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
        if ( v8 > 0 )
          v10 = (unsigned __int16)v8 | 0x80070000;
        v13 = v10;
        v22 = "Failed to record LastDownloadTime";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v10,
          (__int64)word_140021402,
          0x400000000000LL,
          v9,
          (const unsigned __int16 **)&v22,
          (__int64)&v13,
          (const unsigned __int16 **)&v21,
          (const unsigned __int16 **)&v20,
          (__int64)&v14,
          (__int64)&v18);
      }
      RegCloseKey(hKey);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x14000f65c  push    rbp
0x14000f65e  push    rbx
0x14000f65f  push    rsi
0x14000f660  push    rdi
0x14000f661  push    r13
0x14000f663  lea     rbp, [rsp-37h]
0x14000f668  sub     rsp, 0C0h
0x14000f66f  mov     rax, cs:__security_cookie
0x14000f676  xor     rax, rsp
0x14000f679  mov     [rbp+57h+var_28], rax
0x14000f67d  mov     ebx, 1
0x14000f682  mov     qword ptr [rbp+57h+Data], 0
0x14000f68a  mov     [rbp+57h+var_68], 0
0x14000f692  mov     [rbp+57h+var_84], 0Bh
0x14000f699  mov     [rbp+57h+var_90], 0
0x14000f6a0  mov     [rbp+57h+hKey], 0
0x14000f6a8  lea     rcx, [rbp+57h+Data]; unsigned __int64 *
0x14000f6ac  call    ?GetLastDownloadTimeFromWnf@@YAJPEA_K@Z; GetLastDownloadTimeFromWnf(unsigned __int64 *)
0x14000f6b1  mov     edi, eax
0x14000f6b3  mov     r13, 0FFFFFFFF80000002h
0x14000f6ba  test    eax, eax
0x14000f6bc  jns     loc_14000F78F
0x14000f6c2  mov     [rbp+57h+var_30], 7
0x14000f6ca  mov     [rbp+57h+var_38], 0
0x14000f6d2  xor     eax, eax
0x14000f6d4  mov     word ptr [rbp+57h+lpSubKey], ax
0x14000f6d8  lea     rcx, [rbp+57h+lpSubKey]; void *
0x14000f6dc  call    ?GetStateSeparatedDiagTrackRegistryPath@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetStateSeparatedDiagTrackRegistryPath(std::wstring &)
0x14000f6e1  lea     rdx, aSettingsreques; "\\SettingsRequests\\WINDOWS.SIUF"
0x14000f6e8  lea     rcx, [rbp+57h+lpSubKey]; Src
0x14000f6ec  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x14000f6f1  lea     rdx, [rbp+57h+lpSubKey]
0x14000f6f5  cmp     [rbp+57h+var_30], 8
0x14000f6fa  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x14000f6ff  lea     rax, [rbp+57h+var_90]
0x14000f703  mov     [rsp+0E0h+pcbData], rax; pcbData
0x14000f708  lea     rax, [rbp+57h+Data]
0x14000f70c  mov     [rsp+0E0h+pvData], rax; pvData
0x14000f711  lea     rax, [rbp+57h+var_84]
0x14000f715  mov     [rsp+0E0h+pdwType], rax; pdwType
0x14000f71a  lea     r9d, [rbx+47h]; dwFlags
0x14000f71e  lea     r8, ValueName; "LastDownloadTime"
0x14000f725  mov     rcx, r13; hkey
0x14000f728  call    cs:__imp_RegGetValueW
0x14000f72e  mov     ecx, eax
0x14000f730  xor     esi, esi
0x14000f732  test    eax, eax
0x14000f734  setz    sil
0x14000f738  mov     eax, cs:dword_140027000
0x14000f73e  cmp     eax, 5
0x14000f741  jbe     short loc_14000F77C
0x14000f743  mov     [rbp+57h+var_8C], ecx
0x14000f746  mov     [rbp+57h+var_88], edi
0x14000f749  lea     rax, aDidNotObtainTh; "Did not obtain the LastDownloadTime fro"...
0x14000f750  mov     [rbp+57h+var_70], rax
0x14000f754  lea     rax, [rbp+57h+var_8C]
0x14000f758  mov     [rsp+0E0h+pcbData], rax
0x14000f75d  lea     rax, [rbp+57h+var_88]
0x14000f761  mov     [rsp+0E0h+pvData], rax
0x14000f766  lea     rax, [rbp+57h+var_70]
0x14000f76a  mov     [rsp+0E0h+pdwType], rax
0x14000f76f  lea     rdx, byte_140021B85
0x14000f776  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000f77b  nop
0x14000f77c  cmp     [rbp+57h+var_30], 8
0x14000f781  jb      short loc_14000F791
0x14000f783  mov     rcx, [rbp+57h+lpSubKey]
0x14000f787  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000f78d  jmp     short loc_14000F791
0x14000f78f  mov     esi, ebx
0x14000f791  mov     [rbp+57h+var_90], 8
0x14000f798  lea     rax, [rbp+57h+var_90]
0x14000f79c  mov     [rsp+0E0h+pcbData], rax; pcbData
0x14000f7a1  lea     rax, [rbp+57h+var_68]
0x14000f7a5  mov     [rsp+0E0h+pvData], rax; pvData
0x14000f7aa  lea     rax, [rbp+57h+var_84]
0x14000f7ae  mov     [rsp+0E0h+pdwType], rax; pdwType
0x14000f7b3  mov     r9d, 48h ; 'H'; dwFlags
0x14000f7b9  lea     r8, ValueName; "LastDownloadTime"
0x14000f7c0  lea     rdx, SubKey; "Software\\Microsoft\\Siuf"
0x14000f7c7  mov     rcx, r13; hkey
0x14000f7ca  call    cs:__imp_RegGetValueW
0x14000f7d0  test    esi, esi
0x14000f7d2  jz      loc_14000F941
0x14000f7d8  mov     r8, [rbp+57h+var_68]
0x14000f7dc  test    eax, eax
0x14000f7de  jnz     short loc_14000F7E7
0x14000f7e0  cmp     qword ptr [rbp+57h+Data], r8
0x14000f7e4  cmovz   ebx, eax
0x14000f7e7  cmp     qword ptr [rbp+57h+Data], r8
0x14000f7eb  jz      loc_14000F941
0x14000f7f1  mov     [rsp+0E0h+lpdwDisposition], 0; lpdwDisposition
0x14000f7fa  lea     rax, [rbp+57h+hKey]
0x14000f7fe  mov     [rsp+0E0h+phkResult], rax; phkResult
0x14000f803  mov     [rsp+0E0h+pcbData], 0; lpSecurityAttributes
0x14000f80c  mov     dword ptr [rsp+0E0h+pvData], 0F003Fh; samDesired
0x14000f814  mov     dword ptr [rsp+0E0h+pdwType], 0; dwOptions
0x14000f81c  xor     r9d, r9d; lpClass
0x14000f81f  xor     r8d, r8d; Reserved
0x14000f822  lea     rdx, SubKey; "Software\\Microsoft\\Siuf"
0x14000f829  mov     rcx, r13; hKey
0x14000f82c  call    cs:__imp_RegCreateKeyExW
0x14000f832  test    eax, eax
0x14000f834  jnz     loc_14000F941
0x14000f83a  mov     [rbp+57h+var_90], 8
0x14000f841  mov     dword ptr [rsp+0E0h+pvData], 8; cbData
0x14000f849  lea     rax, [rbp+57h+Data]
0x14000f84d  mov     [rsp+0E0h+pdwType], rax; lpData
0x14000f852  mov     r9d, 0Bh; dwType
0x14000f858  xor     r8d, r8d; Reserved
0x14000f85b  lea     rdx, ValueName; "LastDownloadTime"
0x14000f862  mov     rcx, [rbp+57h+hKey]; hKey
0x14000f866  call    cs:__imp_RegSetValueExW
0x14000f86c  mov     ecx, eax
0x14000f86e  test    eax, eax
0x14000f870  jz      loc_14000F937
0x14000f876  mov     eax, cs:dword_140027000
0x14000f87c  cmp     eax, 2
0x14000f87f  jbe     loc_14000F937
0x14000f885  mov     rdx, cs:qword_140027018
0x14000f88c  mov     rax, cs:qword_140027010
0x14000f893  mov     r8, 400000000000h
0x14000f89d  test    r8, rax
0x14000f8a0  jz      loc_14000F937
0x14000f8a6  mov     rax, rdx
0x14000f8a9  and     rax, r8
0x14000f8ac  cmp     rax, rdx
0x14000f8af  jnz     loc_14000F937
0x14000f8b5  mov     [rbp+57h+var_70], 1000000h
0x14000f8bd  mov     [rbp+57h+var_88], 293h
0x14000f8c4  lea     rax, aIstherenewmani; "IsThereNewManifest"
0x14000f8cb  mov     [rbp+57h+var_60], rax
0x14000f8cf  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000f8d6  mov     [rbp+57h+var_58], rax
0x14000f8da  test    ecx, ecx
0x14000f8dc  jle     short loc_14000F8E7
0x14000f8de  movzx   ecx, cx
0x14000f8e1  or      ecx, 80070000h
0x14000f8e7  mov     [rbp+57h+var_8C], ecx
0x14000f8ea  lea     rax, aFailedToRecord; "Failed to record LastDownloadTime"
0x14000f8f1  mov     [rbp+57h+var_50], rax
0x14000f8f5  lea     rax, [rbp+57h+var_70]
0x14000f8f9  mov     [rsp+0E0h+var_98], rax
0x14000f8fe  lea     rax, [rbp+57h+var_88]
0x14000f902  mov     [rsp+0E0h+lpdwDisposition], rax
0x14000f907  lea     rax, [rbp+57h+var_60]
0x14000f90b  mov     [rsp+0E0h+phkResult], rax
0x14000f910  lea     rax, [rbp+57h+var_58]
0x14000f914  mov     [rsp+0E0h+pcbData], rax
0x14000f919  lea     rax, [rbp+57h+var_8C]
0x14000f91d  mov     [rsp+0E0h+pvData], rax
0x14000f922  lea     rax, [rbp+57h+var_50]
0x14000f926  mov     [rsp+0E0h+pdwType], rax
0x14000f92b  lea     rdx, word_140021402
0x14000f932  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000f937  mov     rcx, [rbp+57h+hKey]; hKey
0x14000f93b  call    cs:__imp_RegCloseKey
0x14000f941  mov     eax, ebx
0x14000f943  mov     rcx, [rbp+57h+var_28]
0x14000f947  xor     rcx, rsp; StackCookie
0x14000f94a  call    __security_check_cookie
0x14000f94f  add     rsp, 0C0h
0x14000f956  pop     r13
0x14000f958  pop     rdi
0x14000f959  pop     rsi
0x14000f95a  pop     rbx
0x14000f95b  pop     rbp
0x14000f95c  retn
```
