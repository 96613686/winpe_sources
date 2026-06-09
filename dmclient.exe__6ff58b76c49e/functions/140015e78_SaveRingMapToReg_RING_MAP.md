# SaveRingMapToReg(_RING_MAP *)

- ea: `0x140015e78`
- end: `0x140016123`
- name: `?SaveRingMapToReg@@YAJPEAU_RING_MAP@@@Z`
- size: `683`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x140015aec`

## callees

- `0x140001414`
- `0x140015e78`
- `0x14001785c`
- `0x1400187e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400160fa`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400160fa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140016012`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140016012`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140015f26`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140015f26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400160e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400160e8`

## string_xrefs

- `0x140015faa`: `RegCreateKeyExW failed creating SIUF_DATA_PATH`
- `0x140016092`: `RegSetValueEx failed for SIUF_REG_RING_MAP_VALUE_NAME`

## pseudocode

```c
__int64 __fastcall SaveRingMapToReg(BYTE *lpData)
{
  signed int StateSeparatedSiufRelativePath; // ebx
  const WCHAR *v3; // rdx
  LSTATUS v4; // eax
  int v5; // r8d
  int v6; // r9d
  LSTATUS v7; // eax
  int v8; // r8d
  int v9; // r9d
  int v11; // [rsp+50h] [rbp-9h] BYREF
  int v12; // [rsp+54h] [rbp-5h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-1h] BYREF
  __int64 v14; // [rsp+60h] [rbp+7h] BYREF
  const char *v15; // [rsp+68h] [rbp+Fh] BYREF
  const char *v16; // [rsp+70h] [rbp+17h] BYREF
  __int64 v17; // [rsp+78h] [rbp+1Fh] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+80h] [rbp+27h] BYREF
  unsigned __int64 v19; // [rsp+98h] [rbp+3Fh]

  hKey = 0;
  v19 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  if ( lpData )
  {
    StateSeparatedSiufRelativePath = GetStateSeparatedSiufRelativePath((__int64)lpData, lpSubKey);
    if ( StateSeparatedSiufRelativePath >= 0 )
    {
      v3 = (const WCHAR *)lpSubKey;
      if ( v19 >= 8 )
        v3 = lpSubKey[0];
      v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
      if ( v4 )
      {
        if ( v4 > 0 )
          StateSeparatedSiufRelativePath = (unsigned __int16)v4 | 0x80070000;
        else
          StateSeparatedSiufRelativePath = v4;
        if ( (unsigned int)dword_140027000 > 2
          && (qword_140027010 & 0x400000000000LL) != 0
          && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
        {
          v14 = 0x1000000;
          v11 = 234;
          v15 = "SaveRingMapToReg";
          v16 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
          v12 = StateSeparatedSiufRelativePath;
          v17 = (__int64)"RegCreateKeyExW failed creating SIUF_DATA_PATH";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            0,
            (unsigned int)byte_140022AE5,
            v5,
            v6,
            (__int64)&v17,
            (__int64)&v12,
            (__int64)&v16,
            (__int64)&v15,
            (__int64)&v11,
            (__int64)&v14);
        }
      }
      else
      {
        v7 = RegSetValueExW(hKey, L"RM", 0, 3u, lpData, *((_DWORD *)lpData + 1));
        if ( v7 )
        {
          StateSeparatedSiufRelativePath = v7 > 0 ? (unsigned __int16)v7 | 0x80070000 : v7;
          if ( (unsigned int)dword_140027000 > 2
            && (qword_140027010 & 0x400000000000LL) != 0
            && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
          {
            v17 = 0x1000000;
            v12 = 253;
            v16 = "SaveRingMapToReg";
            v15 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
            v11 = StateSeparatedSiufRelativePath;
            v14 = (__int64)"RegSetValueEx failed for SIUF_REG_RING_MAP_VALUE_NAME";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              0,
              (unsigned int)&byte_140022D77,
              v8,
              v9,
              (__int64)&v14,
              (__int64)&v11,
              (__int64)&v15,
              (__int64)&v16,
              (__int64)&v12,
              (__int64)&v17);
          }
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    StateSeparatedSiufRelativePath = -2147467261;
  }
  if ( v19 >= 8 )
    operator delete((void *)lpSubKey[0]);
  return (unsigned int)StateSeparatedSiufRelativePath;
}

```

## disassembly

```asm
0x140015e78  mov     [rsp-8+arg_8], rbx
0x140015e7d  mov     [rsp-8+arg_10], rdi
0x140015e82  push    rbp
0x140015e83  lea     rbp, [rsp-57h]
0x140015e88  sub     rsp, 0B0h
0x140015e8f  mov     rax, cs:__security_cookie
0x140015e96  xor     rax, rsp
0x140015e99  mov     [rbp+57h+var_10], rax
0x140015e9d  mov     rdi, rcx
0x140015ea0  mov     [rbp+57h+hKey], 0
0x140015ea8  mov     [rbp+57h+var_18], 7
0x140015eb0  mov     [rbp+57h+var_20], 0
0x140015eb8  xor     eax, eax
0x140015eba  mov     word ptr [rbp+57h+lpSubKey], ax
0x140015ebe  test    rcx, rcx
0x140015ec1  jnz     short loc_140015ECD
0x140015ec3  mov     ebx, 80004003h
0x140015ec8  jmp     loc_1400160EF
0x140015ecd  lea     rdx, [rbp+57h+lpSubKey]
0x140015ed1  call    ?GetStateSeparatedSiufRelativePath@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetStateSeparatedSiufRelativePath(ushort const *,std::wstring &)
0x140015ed6  mov     ebx, eax
0x140015ed8  test    eax, eax
0x140015eda  js      loc_1400160DF
0x140015ee0  lea     rdx, [rbp+57h+lpSubKey]
0x140015ee4  cmp     [rbp+57h+var_18], 8
0x140015ee9  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140015eee  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x140015ef7  lea     rax, [rbp+57h+hKey]
0x140015efb  mov     [rsp+0B0h+phkResult], rax; phkResult
0x140015f00  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140015f09  mov     [rsp+0B0h+samDesired], 0F003Fh; samDesired
0x140015f11  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x140015f19  xor     r9d, r9d; lpClass
0x140015f1c  xor     r8d, r8d; Reserved
0x140015f1f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140015f26  call    cs:__imp_RegCreateKeyExW
0x140015f2c  test    eax, eax
0x140015f2e  jz      loc_140015FF2
0x140015f34  jg      short loc_140015F3A
0x140015f36  mov     ebx, eax
0x140015f38  jmp     short loc_140015F43
0x140015f3a  movzx   ebx, ax
0x140015f3d  or      ebx, 80070000h
0x140015f43  mov     eax, cs:dword_140027000
0x140015f49  cmp     eax, 2
0x140015f4c  jbe     loc_1400160DF
0x140015f52  mov     rdx, cs:qword_140027018
0x140015f59  mov     rax, cs:qword_140027010
0x140015f60  mov     rcx, 400000000000h
0x140015f6a  test    rcx, rax
0x140015f6d  jz      loc_1400160DF
0x140015f73  mov     rax, rdx
0x140015f76  and     rax, rcx
0x140015f79  cmp     rax, rdx
0x140015f7c  jnz     loc_1400160DF
0x140015f82  mov     [rbp+57h+var_50], 1000000h
0x140015f8a  mov     [rbp+57h+var_60], 0EAh
0x140015f91  lea     rax, aSaveringmaptor; "SaveRingMapToReg"
0x140015f98  mov     [rbp+57h+var_48], rax
0x140015f9c  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140015fa3  mov     [rbp+57h+var_40], rax
0x140015fa7  mov     [rbp+57h+var_5C], ebx
0x140015faa  lea     rax, aRegcreatekeyex; "RegCreateKeyExW failed creating SIUF_DA"...
0x140015fb1  mov     [rbp+57h+var_38], rax
0x140015fb5  lea     rax, [rbp+57h+var_50]
0x140015fb9  mov     [rsp+0B0h+var_68], rax
0x140015fbe  lea     rax, [rbp+57h+var_60]
0x140015fc2  mov     [rsp+0B0h+lpdwDisposition], rax
0x140015fc7  lea     rax, [rbp+57h+var_48]
0x140015fcb  mov     [rsp+0B0h+phkResult], rax
0x140015fd0  lea     rax, [rbp+57h+var_40]
0x140015fd4  mov     [rsp+0B0h+lpSecurityAttributes], rax
0x140015fd9  lea     rax, [rbp+57h+var_5C]
0x140015fdd  mov     qword ptr [rsp+0B0h+samDesired], rax
0x140015fe2  lea     rax, [rbp+57h+var_38]
0x140015fe6  lea     rdx, byte_140022AE5
0x140015fed  jmp     loc_1400160D5
0x140015ff2  mov     eax, [rdi+4]
0x140015ff5  mov     [rsp+0B0h+samDesired], eax; cbData
0x140015ff9  mov     qword ptr [rsp+0B0h+dwOptions], rdi; lpData
0x140015ffe  mov     r9d, 3; dwType
0x140016004  xor     r8d, r8d; Reserved
0x140016007  lea     rdx, aRm; "RM"
0x14001600e  mov     rcx, [rbp+57h+hKey]; hKey
0x140016012  call    cs:__imp_RegSetValueExW
0x140016018  test    eax, eax
0x14001601a  jz      loc_1400160DF
0x140016020  jg      short loc_140016026
0x140016022  mov     ebx, eax
0x140016024  jmp     short loc_14001602F
0x140016026  movzx   ebx, ax
0x140016029  or      ebx, 80070000h
0x14001602f  mov     eax, cs:dword_140027000
0x140016035  cmp     eax, 2
0x140016038  jbe     loc_1400160DF
0x14001603e  mov     rdx, cs:qword_140027018
0x140016045  mov     rax, cs:qword_140027010
0x14001604c  mov     rcx, 400000000000h
0x140016056  test    rcx, rax
0x140016059  jz      loc_1400160DF
0x14001605f  mov     rax, rdx
0x140016062  and     rax, rcx
0x140016065  cmp     rax, rdx
0x140016068  jnz     short loc_1400160DF
0x14001606a  mov     [rbp+57h+var_38], 1000000h
0x140016072  mov     [rbp+57h+var_5C], 0FDh
0x140016079  lea     rax, aSaveringmaptor; "SaveRingMapToReg"
0x140016080  mov     [rbp+57h+var_40], rax
0x140016084  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14001608b  mov     [rbp+57h+var_48], rax
0x14001608f  mov     [rbp+57h+var_60], ebx
0x140016092  lea     rax, aRegsetvalueexF; "RegSetValueEx failed for SIUF_REG_RING_"...
0x140016099  mov     [rbp+57h+var_50], rax
0x14001609d  lea     rax, [rbp+57h+var_38]
0x1400160a1  mov     [rsp+0B0h+var_68], rax
0x1400160a6  lea     rax, [rbp+57h+var_5C]
0x1400160aa  mov     [rsp+0B0h+lpdwDisposition], rax
0x1400160af  lea     rax, [rbp+57h+var_40]
0x1400160b3  mov     [rsp+0B0h+phkResult], rax
0x1400160b8  lea     rax, [rbp+57h+var_48]
0x1400160bc  mov     [rsp+0B0h+lpSecurityAttributes], rax
0x1400160c1  lea     rax, [rbp+57h+var_60]
0x1400160c5  mov     qword ptr [rsp+0B0h+samDesired], rax
0x1400160ca  lea     rax, [rbp+57h+var_50]
0x1400160ce  lea     rdx, byte_140022D77
0x1400160d5  mov     qword ptr [rsp+0B0h+dwOptions], rax
0x1400160da  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400160df  mov     rcx, [rbp+57h+hKey]; hKey
0x1400160e3  test    rcx, rcx
0x1400160e6  jz      short loc_1400160EF
0x1400160e8  call    cs:__imp_RegCloseKey
0x1400160ee  nop
0x1400160ef  cmp     [rbp+57h+var_18], 8
0x1400160f4  jb      short loc_140016100
0x1400160f6  mov     rcx, [rbp+57h+lpSubKey]
0x1400160fa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140016100  mov     eax, ebx
0x140016102  mov     rcx, [rbp+57h+var_10]
0x140016106  xor     rcx, rsp; StackCookie
0x140016109  call    __security_check_cookie
0x14001610e  lea     r11, [rsp+0B0h+var_s0]
0x140016116  mov     rbx, [r11+18h]
0x14001611a  mov     rdi, [r11+20h]
0x14001611e  mov     rsp, r11
0x140016121  pop     rbp
0x140016122  retn
```
