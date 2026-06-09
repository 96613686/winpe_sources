# IsThereNewManifest(void)

- ea: `0x14000fbf8`
- end: `0x14000ff1e`
- name: `?IsThereNewManifest@@YAHXZ`
- size: `806`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000c928`

## callees

- `0x140001418`
- `0x1400018e4`
- `0x14000deac`
- `0x14000dff4`
- `0x14000fbf8`
- `0x14001529c`
- `0x140019610`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000fd29`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000fd29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000fe1a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000fe1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000fef5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000fef5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000fdda`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000fdda`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000fcc4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000fd72`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000fcc4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000fd72`

## string_xrefs

- `0x14000fceb`: `Did not obtain the LastDownloadTime from WNF_TEL_ONESETTINGS_UPDATED`
- `0x14000fe7e`: `IsThereNewManifest`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 IsThereNewManifest(void)
{
  unsigned int v0; // ebx
  int LastDownloadTimeFromWnf; // edi
  const WCHAR *v2; // rdx
  LSTATUS ValueW; // ecx
  int v4; // r8d
  int v5; // r9d
  BOOL v6; // esi
  LSTATUS v7; // eax
  int v8; // ecx
  int v9; // r9d
  DWORD pcbData; // [rsp+50h] [rbp-39h] BYREF
  LSTATUS v12; // [rsp+54h] [rbp-35h] BYREF
  int v13; // [rsp+58h] [rbp-31h] BYREF
  DWORD pdwType; // [rsp+5Ch] [rbp-2Dh] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-21h] BYREF
  __int64 v17; // [rsp+70h] [rbp-19h] BYREF
  __int64 pvData; // [rsp+78h] [rbp-11h] BYREF
  const char *v19; // [rsp+80h] [rbp-9h] BYREF
  const char *v20; // [rsp+88h] [rbp-1h] BYREF
  const char *v21; // [rsp+90h] [rbp+7h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+98h] [rbp+Fh] BYREF
  unsigned __int64 v23; // [rsp+B0h] [rbp+27h]

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
    v23 = 7;
    lpSubKey[2] = 0;
    LOWORD(lpSubKey[0]) = 0;
    GetStateSeparatedDiagTrackRegistryPath(lpSubKey);
    std::wstring::operator+=(lpSubKey, L"\\SettingsRequests\\WINDOWS.SIUF");
    v2 = (const WCHAR *)lpSubKey;
    if ( v23 >= 8 )
      v2 = lpSubKey[0];
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v2, L"LastDownloadTime", 0x48u, &pdwType, Data, &pcbData);
    v6 = ValueW == 0;
    if ( (unsigned int)dword_140028000 > 5 )
    {
      v12 = ValueW;
      v13 = LastDownloadTimeFromWnf;
      v17 = (__int64)"Did not obtain the LastDownloadTime from WNF_TEL_ONESETTINGS_UPDATED";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        ValueW,
        (unsigned int)byte_140022B8D,
        v4,
        v5,
        (__int64)&v17,
        (__int64)&v13,
        (__int64)&v12);
    }
    if ( v23 >= 8 )
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
      if ( v8
        && (unsigned int)dword_140028000 > 2
        && (qword_140028010 & 0x400000000000LL) != 0
        && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v17 = 0x1000000;
        v13 = 659;
        v19 = "IsThereNewManifest";
        v20 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        v12 = v8;
        v21 = "Failed to record LastDownloadTime";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v8,
          (unsigned int)word_14002240A,
          0,
          v9,
          (__int64)&v21,
          (__int64)&v12,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)&v13,
          (__int64)&v17);
      }
      RegCloseKey(hKey);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x14000fbf8  push    rbp
0x14000fbfa  push    rbx
0x14000fbfb  push    rsi
0x14000fbfc  push    rdi
0x14000fbfd  push    r13
0x14000fbff  lea     rbp, [rsp-37h]
0x14000fc04  sub     rsp, 0C0h
0x14000fc0b  mov     rax, cs:__security_cookie
0x14000fc12  xor     rax, rsp
0x14000fc15  mov     [rbp+57h+var_28], rax
0x14000fc19  mov     ebx, 1
0x14000fc1e  mov     qword ptr [rbp+57h+Data], 0
0x14000fc26  mov     [rbp+57h+var_68], 0
0x14000fc2e  mov     [rbp+57h+var_84], 0Bh
0x14000fc35  mov     [rbp+57h+var_90], 0
0x14000fc3c  mov     [rbp+57h+hKey], 0
0x14000fc44  lea     rcx, [rbp+57h+Data]; unsigned __int64 *
0x14000fc48  call    ?GetLastDownloadTimeFromWnf@@YAJPEA_K@Z; GetLastDownloadTimeFromWnf(unsigned __int64 *)
0x14000fc4d  mov     edi, eax
0x14000fc4f  mov     r13, 0FFFFFFFF80000002h
0x14000fc56  test    eax, eax
0x14000fc58  jns     loc_14000FD37
0x14000fc5e  mov     [rbp+57h+var_30], 7
0x14000fc66  mov     [rbp+57h+var_38], 0
0x14000fc6e  xor     eax, eax
0x14000fc70  mov     word ptr [rbp+57h+lpSubKey], ax
0x14000fc74  lea     rcx, [rbp+57h+lpSubKey]; void *
0x14000fc78  call    ?GetStateSeparatedDiagTrackRegistryPath@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetStateSeparatedDiagTrackRegistryPath(std::wstring &)
0x14000fc7d  lea     rdx, aSettingsreques; "\\SettingsRequests\\WINDOWS.SIUF"
0x14000fc84  lea     rcx, [rbp+57h+lpSubKey]; Src
0x14000fc88  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x14000fc8d  lea     rdx, [rbp+57h+lpSubKey]
0x14000fc91  cmp     [rbp+57h+var_30], 8
0x14000fc96  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x14000fc9b  lea     rax, [rbp+57h+var_90]
0x14000fc9f  mov     [rsp+0E0h+pcbData], rax; pcbData
0x14000fca4  lea     rax, [rbp+57h+Data]
0x14000fca8  mov     [rsp+0E0h+pvData], rax; pvData
0x14000fcad  lea     rax, [rbp+57h+var_84]
0x14000fcb1  mov     [rsp+0E0h+pdwType], rax; pdwType
0x14000fcb6  lea     r9d, [rbx+47h]; dwFlags
0x14000fcba  lea     r8, ValueName; "LastDownloadTime"
0x14000fcc1  mov     rcx, r13; hkey
0x14000fcc4  call    cs:__imp_RegGetValueW
0x14000fccb  nop     dword ptr [rax+rax+00h]
0x14000fcd0  mov     ecx, eax
0x14000fcd2  xor     esi, esi
0x14000fcd4  test    eax, eax
0x14000fcd6  setz    sil
0x14000fcda  mov     eax, cs:dword_140028000
0x14000fce0  cmp     eax, 5
0x14000fce3  jbe     short loc_14000FD1E
0x14000fce5  mov     [rbp+57h+var_8C], ecx
0x14000fce8  mov     [rbp+57h+var_88], edi
0x14000fceb  lea     rax, aDidNotObtainTh; "Did not obtain the LastDownloadTime fro"...
0x14000fcf2  mov     [rbp+57h+var_70], rax
0x14000fcf6  lea     rax, [rbp+57h+var_8C]
0x14000fcfa  mov     [rsp+0E0h+pcbData], rax
0x14000fcff  lea     rax, [rbp+57h+var_88]
0x14000fd03  mov     [rsp+0E0h+pvData], rax
0x14000fd08  lea     rax, [rbp+57h+var_70]
0x14000fd0c  mov     [rsp+0E0h+pdwType], rax
0x14000fd11  lea     rdx, byte_140022B8D
0x14000fd18  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000fd1d  nop
0x14000fd1e  cmp     [rbp+57h+var_30], 8
0x14000fd23  jb      short loc_14000FD39
0x14000fd25  mov     rcx, [rbp+57h+lpSubKey]
0x14000fd29  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000fd30  nop     dword ptr [rax+rax+00h]
0x14000fd35  jmp     short loc_14000FD39
0x14000fd37  mov     esi, ebx
0x14000fd39  mov     [rbp+57h+var_90], 8
0x14000fd40  lea     rax, [rbp+57h+var_90]
0x14000fd44  mov     [rsp+0E0h+pcbData], rax; pcbData
0x14000fd49  lea     rax, [rbp+57h+var_68]
0x14000fd4d  mov     [rsp+0E0h+pvData], rax; pvData
0x14000fd52  lea     rax, [rbp+57h+var_84]
0x14000fd56  mov     [rsp+0E0h+pdwType], rax; pdwType
0x14000fd5b  mov     r9d, 48h ; 'H'; dwFlags
0x14000fd61  lea     r8, ValueName; "LastDownloadTime"
0x14000fd68  lea     rdx, SubKey; "Software\\Microsoft\\Siuf"
0x14000fd6f  mov     rcx, r13; hkey
0x14000fd72  call    cs:__imp_RegGetValueW
0x14000fd79  nop     dword ptr [rax+rax+00h]
0x14000fd7e  test    esi, esi
0x14000fd80  jz      loc_14000FF01
0x14000fd86  mov     r8, [rbp+57h+var_68]
0x14000fd8a  test    eax, eax
0x14000fd8c  jnz     short loc_14000FD95
0x14000fd8e  cmp     qword ptr [rbp+57h+Data], r8
0x14000fd92  cmovz   ebx, eax
0x14000fd95  cmp     qword ptr [rbp+57h+Data], r8
0x14000fd99  jz      loc_14000FF01
0x14000fd9f  mov     [rsp+0E0h+lpdwDisposition], 0; lpdwDisposition
0x14000fda8  lea     rax, [rbp+57h+hKey]
0x14000fdac  mov     [rsp+0E0h+phkResult], rax; phkResult
0x14000fdb1  mov     [rsp+0E0h+pcbData], 0; lpSecurityAttributes
0x14000fdba  mov     dword ptr [rsp+0E0h+pvData], 0F003Fh; samDesired
0x14000fdc2  mov     dword ptr [rsp+0E0h+pdwType], 0; dwOptions
0x14000fdca  xor     r9d, r9d; lpClass
0x14000fdcd  xor     r8d, r8d; Reserved
0x14000fdd0  lea     rdx, SubKey; "Software\\Microsoft\\Siuf"
0x14000fdd7  mov     rcx, r13; hKey
0x14000fdda  call    cs:__imp_RegCreateKeyExW
0x14000fde1  nop     dword ptr [rax+rax+00h]
0x14000fde6  test    eax, eax
0x14000fde8  jnz     loc_14000FF01
0x14000fdee  mov     [rbp+57h+var_90], 8
0x14000fdf5  mov     dword ptr [rsp+0E0h+pvData], 8; cbData
0x14000fdfd  lea     rax, [rbp+57h+Data]
0x14000fe01  mov     [rsp+0E0h+pdwType], rax; lpData
0x14000fe06  mov     r9d, 0Bh; dwType
0x14000fe0c  xor     r8d, r8d; Reserved
0x14000fe0f  lea     rdx, ValueName; "LastDownloadTime"
0x14000fe16  mov     rcx, [rbp+57h+hKey]; hKey
0x14000fe1a  call    cs:__imp_RegSetValueExW
0x14000fe21  nop     dword ptr [rax+rax+00h]
0x14000fe26  mov     ecx, eax
0x14000fe28  test    eax, eax
0x14000fe2a  jz      loc_14000FEF1
0x14000fe30  mov     eax, cs:dword_140028000
0x14000fe36  cmp     eax, 2
0x14000fe39  jbe     loc_14000FEF1
0x14000fe3f  mov     rdx, cs:qword_140028018
0x14000fe46  mov     rax, cs:qword_140028010
0x14000fe4d  mov     r8, 400000000000h
0x14000fe57  test    r8, rax
0x14000fe5a  jz      loc_14000FEF1
0x14000fe60  mov     rax, rdx
0x14000fe63  and     rax, r8
0x14000fe66  cmp     rax, rdx
0x14000fe69  jnz     loc_14000FEF1
0x14000fe6f  mov     [rbp+57h+var_70], 1000000h
0x14000fe77  mov     [rbp+57h+var_88], 293h
0x14000fe7e  lea     rax, aIstherenewmani; "IsThereNewManifest"
0x14000fe85  mov     [rbp+57h+var_60], rax
0x14000fe89  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000fe90  mov     [rbp+57h+var_58], rax
0x14000fe94  test    ecx, ecx
0x14000fe96  jle     short loc_14000FEA1
0x14000fe98  movzx   ecx, cx
0x14000fe9b  or      ecx, 80070000h
0x14000fea1  mov     [rbp+57h+var_8C], ecx
0x14000fea4  lea     rax, aFailedToRecord; "Failed to record LastDownloadTime"
0x14000feab  mov     [rbp+57h+var_50], rax
0x14000feaf  lea     rax, [rbp+57h+var_70]
0x14000feb3  mov     [rsp+0E0h+var_98], rax
0x14000feb8  lea     rax, [rbp+57h+var_88]
0x14000febc  mov     [rsp+0E0h+lpdwDisposition], rax
0x14000fec1  lea     rax, [rbp+57h+var_60]
0x14000fec5  mov     [rsp+0E0h+phkResult], rax
0x14000feca  lea     rax, [rbp+57h+var_58]
0x14000fece  mov     [rsp+0E0h+pcbData], rax
0x14000fed3  lea     rax, [rbp+57h+var_8C]
0x14000fed7  mov     [rsp+0E0h+pvData], rax
0x14000fedc  lea     rax, [rbp+57h+var_50]
0x14000fee0  mov     [rsp+0E0h+pdwType], rax
0x14000fee5  lea     rdx, word_14002240A
0x14000feec  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000fef1  mov     rcx, [rbp+57h+hKey]; hKey
0x14000fef5  call    cs:__imp_RegCloseKey
0x14000fefc  nop     dword ptr [rax+rax+00h]
0x14000ff01  mov     eax, ebx
0x14000ff03  mov     rcx, [rbp+57h+var_28]
0x14000ff07  xor     rcx, rsp; StackCookie
0x14000ff0a  call    __security_check_cookie
0x14000ff0f  add     rsp, 0C0h
0x14000ff16  pop     r13
0x14000ff18  pop     rdi
0x14000ff19  pop     rsi
0x14000ff1a  pop     rbx
0x14000ff1b  pop     rbp
0x14000ff1c  retn
```
