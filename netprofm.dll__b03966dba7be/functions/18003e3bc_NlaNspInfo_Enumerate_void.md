# NlaNspInfo::Enumerate(void)

- ea: `0x18003e3bc`
- end: `0x18003e719`
- name: `?Enumerate@NlaNspInfo@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `861`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f888`

## callees

- `0x18000f388`
- `0x1800100d8`
- `0x180010100`
- `0x180010124`
- `0x1800120d0`
- `0x180012870`
- `0x180012f40`
- `0x18002b7c0`
- `0x18003a79c`
- `0x18003e2c0`
- `0x18003e2e4`
- `0x18003e3bc`
- `0x18003e720`

## import_xrefs

- `WS2_32!WSALookupServiceEnd` at `0x18003e6b9`
- `WS2_32!WSALookupServiceEnd` at `0x18003e6b9`
- `WS2_32!WSALookupServiceNextW` at `0x18003e694`
- `WS2_32!WSALookupServiceNextW` at `0x18003e694`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e6a3`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e6a3`

## string_xrefs

- `0x18003e409`: `~~~ NLA NSP Enumeration [WSALookupServiceBegin/WSALookupServiceNext] ~~~\n`
- `0x18003e6f8`: `WSALookupServiceNext`
- `0x18003e707`: `onecore\net\netprofiles\service\src\netshnlmplugin\nlansp.cpp`
- `0x18003e455`: `\nNetwork #%u\n  ServiceInstanceName (Network Name): %ws\n  Comment (optional): %ws\n  Query String: %ws\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NlaNspInfo::Enumerate(__int64 a1, __int64 a2)
{
  struct _WSAQuerySetW *v3; // r14
  unsigned int i; // r12d
  __int64 j; // r15
  BYTE *pBlobData; // rdi
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  wchar_t *v13; // r9
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  wchar_t *v17; // r8
  const wchar_t *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r10
  int v21; // eax
  unsigned int Error; // eax
  unsigned int v24[2]; // [rsp+20h] [rbp-59h]
  char *v25; // [rsp+28h] [rbp-51h]
  enum TUNNEL_TYPE v26; // [rsp+44h] [rbp-35h] BYREF
  unsigned int v27; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v28[32]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v29; // [rsp+70h] [rbp-9h]
  HANDLE *p_hLookup; // [rsp+78h] [rbp-1h]
  char v31; // [rsp+80h] [rbp+7h]
  HANDLE hLookup; // [rsp+88h] [rbp+Fh] BYREF
  DWORD dwBufferLength; // [rsp+90h] [rbp+17h] BYREF
  struct _WSAQuerySetW *v34; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v29 = a2;
  v3 = (struct _WSAQuerySetW *)operator new[](0x4000u);
  v34 = v3;
  std::wstring::wstring(a2, (__int64)L"~~~ NLA NSP Enumeration [WSALookupServiceBegin/WSALookupServiceNext] ~~~\n");
  hLookup = CreateNlaNspHandle();
  p_hLookup = &hLookup;
  v31 = 1;
  for ( i = 0; ; ++i )
  {
    memset_0(v3, 0, 0x4000u);
    dwBufferLength = 0x4000;
    if ( WSALookupServiceNextW(hLookup, 0xFF0u, &dwBufferLength, v3) == -1 )
      break;
    wil::str_printf<std::wstring>(
      (__int64)v28,
      (__int64)L"\n"
                "Network #%u\n"
                "  ServiceInstanceName (Network Name): %ws\n"
                "  Comment (optional): %ws\n"
                "  Query String: %ws\n",
      i,
      v3->lpszServiceInstanceName,
      v3->lpszComment,
      v3->lpszQueryString);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)v28);
    if ( v3->lpBlob )
    {
      for ( j = 0; ; j = (unsigned int)(v21 + j) )
      {
        pBlobData = v3->lpBlob->pBlobData;
        v7 = *(_DWORD *)&pBlobData[j];
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            v9 = v8 - 1;
            if ( v9 )
            {
              v10 = v9 - 1;
              if ( v10 )
              {
                if ( v10 == 1 )
                {
                  v24[0] = *(_DWORD *)&pBlobData[j + 20];
                  wil::str_printf<std::wstring>(
                    (__int64)v28,
                    (__int64)L"  - NLA_BLOB Data Type: NLA_ICS\n"
                              "      NLA_ICS Type: %u\n"
                              "      NLA_ICS Speed: %u\n"
                              "      NLA_ICS State: %u\n"
                              "      NLA_ICS Machine Name: %ws\n"
                              "      NLA_ICS Shared Adapter Name: %ws\n",
                    *(unsigned int *)&pBlobData[j + 16],
                    *(unsigned int *)&pBlobData[j + 12],
                    *(_QWORD *)v24,
                    &pBlobData[(unsigned int)j + 24],
                    &pBlobData[(unsigned int)j + 536]);
                }
                else
                {
                  wil::str_printf<std::wstring>((__int64)v28, (__int64)L"  - NLA_BLOB Data Type Unknown : %u\n");
                }
                std::wstring::append();
              }
              else
              {
                v11 = *(_DWORD *)&pBlobData[j + 16];
                if ( v11 )
                {
                  v12 = v11 - 1;
                  if ( v12 )
                    v13 = v12 == 1 ? L"NLA_INTERNET_YES" : L"(unknown NLA_INTERNET)";
                  else
                    v13 = L"NLA_INTERNET_NO";
                }
                else
                {
                  v13 = L"NLA_INTERNET_UNKNOWN";
                }
                v14 = *(_DWORD *)&pBlobData[j + 12];
                if ( v14 )
                {
                  v15 = v14 - 1;
                  if ( v15 )
                  {
                    v16 = v15 - 1;
                    if ( v16 )
                      v17 = v16 == 1 ? L"NLA_NETWORK_UNKNOWN" : L"(unknown NLA_CONNECTIVITY_TYPE)";
                    else
                      v17 = L"NLA_NETWORK_UNMANAGED";
                  }
                  else
                  {
                    v17 = L"NLA_NETWORK_MANAGED";
                  }
                }
                else
                {
                  v17 = L"NLA_NETWORK_AD_HOC";
                }
                wil::str_printf<std::wstring>(
                  (__int64)v28,
                  (__int64)L"  - NLA_BLOB Data Type: NLA_CONNECTIVITY\n"
                            "      NLA_CONNECTIVITY Type: %ws\n"
                            "      NLA_CONNECTIVITY Internet: %ws\n",
                  v17,
                  v13);
                std::wstring::append();
              }
            }
            else
            {
              wil::str_printf<std::wstring>(
                (__int64)v28,
                (__int64)L"  - NLA_BLOB Data Type: NLA_802_1X_LOCATION\n      NLA_802_1X_LOCATION Information: %hs\n",
                &pBlobData[(unsigned int)j + 12]);
              std::wstring::append();
            }
          }
          else
          {
            v27 = *(_DWORD *)&pBlobData[j + 12];
            v26 = TUNNEL_TYPE_NONE;
            v18 = ToString(&v27, &v26);
            v24[0] = *(_DWORD *)&pBlobData[j + 16];
            wil::str_printf<std::wstring>(
              (__int64)v28,
              (__int64)L"  - NLA_BLOB Data Type: NLA_INTERFACE\n"
                        "      NLA_INTERFACE Type: %u (%ws)\n"
                        "      NLA_INTERFACE Speed: %u\n"
                        "      NLA_INTERFACE Adapter Name: %hs\n",
              v19,
              v18,
              *(_QWORD *)v24,
              v20);
            std::wstring::append();
          }
          std::wstring::_Tidy_deallocate((__int64)v28);
        }
        else
        {
          std::wstring::append(a2, (__int64)L"  - NLA_BLOB Data Type: NLA_RAW_DATA\n");
        }
        v21 = *(_DWORD *)&pBlobData[j + 8];
        if ( !v21 )
          break;
      }
    }
  }
  Error = WSAGetLastError();
  if ( Error != 10110 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\nlansp.cpp",
      (const char *)Error,
      (unsigned int)"WSALookupServiceNext",
      v25);
  if ( !hLookup )
    WSALookupServiceEnd(0);
  std::unique_ptr<char>::~unique_ptr<char>((void **)&v34);
  return a2;
}

```

## disassembly

```asm
0x18003e3bc  mov     [rsp-8+arg_0], rbx
0x18003e3c1  mov     [rsp-8+arg_10], rsi
0x18003e3c6  push    rbp
0x18003e3c7  push    rdi
0x18003e3c8  push    r12
0x18003e3ca  push    r14
0x18003e3cc  push    r15
0x18003e3ce  lea     rbp, [rsp-37h]
0x18003e3d3  sub     rsp, 0B0h
0x18003e3da  mov     rax, cs:__security_cookie
0x18003e3e1  xor     rax, rsp
0x18003e3e4  mov     [rbp+57h+var_30], rax
0x18003e3e8  mov     rsi, rdx
0x18003e3eb  mov     [rbp+57h+var_60], rdx
0x18003e3ef  mov     [rbp+57h+var_90], 0
0x18003e3f6  mov     ebx, 4000h
0x18003e3fb  mov     ecx, ebx; unsigned __int64
0x18003e3fd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003e402  mov     r14, rax
0x18003e405  mov     [rbp+57h+var_38], rax
0x18003e409  lea     rdx, aNlaNspEnumerat; "~~~ NLA NSP Enumeration [WSALookupServi"...
0x18003e410  mov     rcx, rsi
0x18003e413  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003e418  mov     [rbp+57h+var_90], 1
0x18003e41f  call    ?CreateNlaNspHandle@@YAPEAXXZ; CreateNlaNspHandle(void)
0x18003e424  mov     [rbp+57h+hLookup], rax
0x18003e428  lea     rax, [rbp+57h+hLookup]
0x18003e42c  mov     [rbp+57h+var_58], rax
0x18003e430  mov     [rbp+57h+var_50], 1
0x18003e434  xor     r12d, r12d
0x18003e437  jmp     loc_18003E674
0x18003e43c  mov     rax, [r14+50h]
0x18003e440  mov     [rsp+0D0h+var_A8], rax; char *
0x18003e445  mov     rax, [r14+20h]
0x18003e449  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18003e44e  mov     r9, [r14+8]
0x18003e452  mov     r8d, r12d
0x18003e455  lea     rdx, aNetworkUServic; "\nNetwork #%u\n  ServiceInstanceName (N"...
0x18003e45c  lea     rcx, [rbp+57h+var_80]
0x18003e460  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003e465  nop
0x18003e466  mov     rdx, rax
0x18003e469  mov     rcx, rsi
0x18003e46c  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003e471  nop
0x18003e472  lea     rcx, [rbp+57h+var_80]
0x18003e476  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e47b  cmp     qword ptr [r14+70h], 0
0x18003e480  jz      loc_18003E671
0x18003e486  xor     r15d, r15d
0x18003e489  mov     rax, [r14+70h]
0x18003e48d  mov     ebx, r15d
0x18003e490  mov     rdi, [rax+8]
0x18003e494  mov     r8d, [rdi+r15]
0x18003e498  mov     ecx, r8d
0x18003e49b  test    r8d, r8d
0x18003e49e  jz      loc_18003E64C
0x18003e4a4  sub     ecx, 1
0x18003e4a7  jz      loc_18003E5EF
0x18003e4ad  sub     ecx, 1
0x18003e4b0  jz      loc_18003E5C9
0x18003e4b6  sub     ecx, 1
0x18003e4b9  jz      short loc_18003E532
0x18003e4bb  cmp     ecx, 1
0x18003e4be  jz      short loc_18003E4E2
0x18003e4c0  lea     rdx, aNlaBlobDataTyp_2; "  - NLA_BLOB Data Type Unknown : %u\n"
0x18003e4c7  lea     rcx, [rbp+57h+var_80]
0x18003e4cb  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003e4d0  nop
0x18003e4d1  mov     rdx, rax
0x18003e4d4  mov     rcx, rsi
0x18003e4d7  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003e4dc  nop
0x18003e4dd  jmp     loc_18003E641
0x18003e4e2  lea     rax, [rdi+218h]
0x18003e4e9  add     rax, rbx
0x18003e4ec  lea     rcx, [rdi+18h]
0x18003e4f0  add     rcx, rbx
0x18003e4f3  mov     [rsp+0D0h+var_A0], rax
0x18003e4f8  mov     [rsp+0D0h+var_A8], rcx
0x18003e4fd  mov     eax, [rdi+r15+14h]
0x18003e502  mov     [rsp+0D0h+var_B0], eax
0x18003e506  mov     r9d, [rdi+r15+0Ch]
0x18003e50b  mov     r8d, [rdi+r15+10h]
0x18003e510  lea     rdx, aNlaBlobDataTyp_3; "  - NLA_BLOB Data Type: NLA_ICS\n      "...
0x18003e517  lea     rcx, [rbp+57h+var_80]
0x18003e51b  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003e520  nop
0x18003e521  mov     rdx, rax
0x18003e524  mov     rcx, rsi
0x18003e527  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003e52c  nop
0x18003e52d  jmp     loc_18003E641
0x18003e532  mov     ecx, [rdi+r15+10h]
0x18003e537  test    ecx, ecx
0x18003e539  jz      short loc_18003E560
0x18003e53b  sub     ecx, 1
0x18003e53e  jz      short loc_18003E557
0x18003e540  cmp     ecx, 1
0x18003e543  jz      short loc_18003E54E
0x18003e545  lea     r9, aUnknownNlaInte; "(unknown NLA_INTERNET)"
0x18003e54c  jmp     short loc_18003E567
0x18003e54e  lea     r9, aNlaInternetYes; "NLA_INTERNET_YES"
0x18003e555  jmp     short loc_18003E567
0x18003e557  lea     r9, aNlaInternetNo; "NLA_INTERNET_NO"
0x18003e55e  jmp     short loc_18003E567
0x18003e560  lea     r9, aNlaInternetUnk; "NLA_INTERNET_UNKNOWN"
0x18003e567  mov     ecx, [rdi+r15+0Ch]
0x18003e56c  test    ecx, ecx
0x18003e56e  jz      short loc_18003E5A3
0x18003e570  sub     ecx, 1
0x18003e573  jz      short loc_18003E59A
0x18003e575  sub     ecx, 1
0x18003e578  jz      short loc_18003E591
0x18003e57a  cmp     ecx, 1
0x18003e57d  jz      short loc_18003E588
0x18003e57f  lea     r8, aUnknownNlaConn; "(unknown NLA_CONNECTIVITY_TYPE)"
0x18003e586  jmp     short loc_18003E5AA
0x18003e588  lea     r8, aNlaNetworkUnkn; "NLA_NETWORK_UNKNOWN"
0x18003e58f  jmp     short loc_18003E5AA
0x18003e591  lea     r8, aNlaNetworkUnma; "NLA_NETWORK_UNMANAGED"
0x18003e598  jmp     short loc_18003E5AA
0x18003e59a  lea     r8, aNlaNetworkMana; "NLA_NETWORK_MANAGED"
0x18003e5a1  jmp     short loc_18003E5AA
0x18003e5a3  lea     r8, aNlaNetworkAdHo; "NLA_NETWORK_AD_HOC"
0x18003e5aa  lea     rdx, aNlaBlobDataTyp_1; "  - NLA_BLOB Data Type: NLA_CONNECTIVIT"...
0x18003e5b1  lea     rcx, [rbp+57h+var_80]
0x18003e5b5  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003e5ba  nop
0x18003e5bb  mov     rdx, rax
0x18003e5be  mov     rcx, rsi
0x18003e5c1  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003e5c6  nop
0x18003e5c7  jmp     short loc_18003E641
0x18003e5c9  lea     r8, [rdi+0Ch]
0x18003e5cd  add     r8, rbx
0x18003e5d0  lea     rdx, aNlaBlobDataTyp_4; "  - NLA_BLOB Data Type: NLA_802_1X_LOCA"...
0x18003e5d7  lea     rcx, [rbp+57h+var_80]
0x18003e5db  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003e5e0  nop
0x18003e5e1  mov     rdx, rax
0x18003e5e4  mov     rcx, rsi
0x18003e5e7  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003e5ec  nop
0x18003e5ed  jmp     short loc_18003E641
0x18003e5ef  mov     r8d, [rdi+r15+0Ch]
0x18003e5f4  mov     [rbp+57h+var_88], r8d
0x18003e5f8  mov     [rbp+57h+var_8C], 0
0x18003e5ff  lea     r10, [rdi+14h]
0x18003e603  add     r10, rbx
0x18003e606  lea     rdx, [rbp+57h+var_8C]; enum TUNNEL_TYPE *
0x18003e60a  lea     rcx, [rbp+57h+var_88]; unsigned int *
0x18003e60e  call    ?ToString@@YAPEB_WAEBKAEBW4TUNNEL_TYPE@@@Z; ToString(ulong const &,TUNNEL_TYPE const &)
0x18003e613  mov     r9, rax
0x18003e616  mov     [rsp+0D0h+var_A8], r10
0x18003e61b  mov     eax, [rdi+r15+10h]
0x18003e620  mov     [rsp+0D0h+var_B0], eax
0x18003e624  lea     rdx, aNlaBlobDataTyp; "  - NLA_BLOB Data Type: NLA_INTERFACE\n"...
0x18003e62b  lea     rcx, [rbp+57h+var_80]
0x18003e62f  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003e634  nop
0x18003e635  mov     rdx, rax
0x18003e638  mov     rcx, rsi
0x18003e63b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003e640  nop
0x18003e641  lea     rcx, [rbp+57h+var_80]
0x18003e645  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e64a  jmp     short loc_18003E65B
0x18003e64c  lea     rdx, aNlaBlobDataTyp_0; "  - NLA_BLOB Data Type: NLA_RAW_DATA\n"
0x18003e653  mov     rcx, rsi
0x18003e656  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18003e65b  mov     eax, [rdi+r15+8]
0x18003e660  test    eax, eax
0x18003e662  jz      short loc_18003E66C
0x18003e664  add     r15d, eax
0x18003e667  jmp     loc_18003E489
0x18003e66c  mov     ebx, 4000h
0x18003e671  inc     r12d
0x18003e674  mov     r8, rbx; Size
0x18003e677  xor     edx, edx; Val
0x18003e679  mov     rcx, r14; void *
0x18003e67c  call    memset_0
0x18003e681  mov     [rbp+57h+dwBufferLength], ebx
0x18003e684  mov     r9, r14; lpqsResults
0x18003e687  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x18003e68b  mov     edx, 0FF0h; dwControlFlags
0x18003e690  mov     rcx, [rbp+57h+hLookup]; hLookup
0x18003e694  call    cs:__imp_WSALookupServiceNextW
0x18003e69a  cmp     eax, 0FFFFFFFFh
0x18003e69d  jnz     loc_18003E43C
0x18003e6a3  call    cs:__imp_WSAGetLastError
0x18003e6a9  cmp     eax, 277Eh
0x18003e6ae  jnz     short loc_18003E6F4
0x18003e6b0  mov     rcx, [rbp+57h+hLookup]; hLookup
0x18003e6b4  test    rcx, rcx
0x18003e6b7  jnz     short loc_18003E6C0
0x18003e6b9  call    cs:__imp_WSALookupServiceEnd
0x18003e6bf  nop
0x18003e6c0  lea     rcx, [rbp+57h+var_38]
0x18003e6c4  call    ??1?$unique_ptr@DU?$default_delete@D@std@@@std@@QEAA@XZ; std::unique_ptr<char>::~unique_ptr<char>(void)
0x18003e6c9  mov     rax, rsi
0x18003e6cc  mov     rcx, [rbp+57h+var_30]
0x18003e6d0  xor     rcx, rsp; StackCookie
0x18003e6d3  call    __security_check_cookie
0x18003e6d8  lea     r11, [rsp+0D0h+var_20]
0x18003e6e0  mov     rbx, [r11+30h]
0x18003e6e4  mov     rsi, [r11+40h]
0x18003e6e8  mov     rsp, r11
0x18003e6eb  pop     r15
0x18003e6ed  pop     r14
0x18003e6ef  pop     r12
0x18003e6f1  pop     rdi
0x18003e6f2  pop     rbp
0x18003e6f3  retn
0x18003e6f4  mov     rcx, [rbp+5Fh]; this
0x18003e6f8  lea     rdx, aWsalookupservi_2; "WSALookupServiceNext"
0x18003e6ff  mov     qword ptr [rsp+0D0h+var_B0], rdx; unsigned int
0x18003e704  mov     r9d, eax; char *
0x18003e707  lea     r8, aOnecoreNetNetp_8; "onecore\\net\\netprofiles\\service\\src"...
0x18003e70e  mov     edx, 66h ; 'f'; void *
0x18003e713  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
