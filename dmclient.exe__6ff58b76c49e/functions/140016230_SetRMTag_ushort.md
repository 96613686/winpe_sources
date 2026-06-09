# SetRMTag(ushort *)

- ea: `0x140016230`
- end: `0x1400164c9`
- name: `?SetRMTag@@YAJPEAG@Z`
- size: `665`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x140015aec`

## callees

- `0x140001414`
- `0x140016230`
- `0x14001785c`
- `0x1400187e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400164a9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400164a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400163c1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400163c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400162c4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400162c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016497`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016497`

## string_xrefs

- `0x140016348`: `RegCreateKeyExW failed creating SIUF_DATA_PATH`
- `0x140016441`: `Unexpected error opening SIUF_DATA_PATH`

## pseudocode

```c
__int64 __fastcall SetRMTag(BYTE *lpData)
{
  signed int StateSeparatedSiufRelativePath; // ebx
  const WCHAR *v3; // rdx
  LSTATUS v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rax
  LSTATUS v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  int v12; // [rsp+50h] [rbp-29h] BYREF
  int v13; // [rsp+54h] [rbp-25h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-21h] BYREF
  __int64 v15; // [rsp+60h] [rbp-19h] BYREF
  const char *v16; // [rsp+68h] [rbp-11h] BYREF
  const char *v17; // [rsp+70h] [rbp-9h] BYREF
  __int64 v18; // [rsp+78h] [rbp-1h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int64 v20; // [rsp+98h] [rbp+1Fh]

  hKey = 0;
  v20 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  if ( lpData )
  {
    StateSeparatedSiufRelativePath = GetStateSeparatedSiufRelativePath((__int64)lpData, lpSubKey);
    if ( StateSeparatedSiufRelativePath >= 0 )
    {
      v3 = (const WCHAR *)lpSubKey;
      if ( v20 >= 8 )
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
          v15 = 0x1000000;
          v12 = 720;
          v16 = "SetRMTag";
          v17 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
          v13 = StateSeparatedSiufRelativePath;
          v18 = (__int64)"RegCreateKeyExW failed creating SIUF_DATA_PATH";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            0x400000000000LL,
            (__int64)byte_1400227F5,
            v5,
            v6,
            (const unsigned __int16 **)&v18,
            (__int64)&v13,
            (const unsigned __int16 **)&v17,
            (const unsigned __int16 **)&v16,
            (__int64)&v12,
            (__int64)&v15);
        }
      }
      else
      {
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)&lpData[2 * v7] );
        v8 = RegSetValueExW(hKey, L"RMTag", 0, 1u, lpData, 2 * v7 + 2);
        if ( v8 )
        {
          StateSeparatedSiufRelativePath = v8 > 0 ? (unsigned __int16)v8 | 0x80070000 : v8;
          if ( (unsigned int)dword_140027000 > 2
            && (qword_140027010 & 0x400000000000LL) != 0
            && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
          {
            v18 = 0x1000000;
            v13 = 739;
            v17 = "SetRMTag";
            v16 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
            v12 = StateSeparatedSiufRelativePath;
            v15 = (__int64)"Unexpected error opening SIUF_DATA_PATH";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              0x400000000000LL,
              (__int64)byte_1400228B1,
              v9,
              v10,
              (const unsigned __int16 **)&v15,
              (__int64)&v12,
              (const unsigned __int16 **)&v16,
              (const unsigned __int16 **)&v17,
              (__int64)&v13,
              (__int64)&v18);
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
  if ( v20 >= 8 )
    operator delete((void *)lpSubKey[0]);
  return (unsigned int)StateSeparatedSiufRelativePath;
}

```

## disassembly

```asm
0x140016230  push    rbp
0x140016232  push    rbx
0x140016233  push    rsi
0x140016234  push    rdi
0x140016235  lea     rbp, [rsp-3Fh]
0x14001623a  sub     rsp, 0B8h
0x140016241  mov     rax, cs:__security_cookie
0x140016248  xor     rax, rsp
0x14001624b  mov     [rbp+57h+var_30], rax
0x14001624f  mov     rdi, rcx
0x140016252  xor     esi, esi
0x140016254  mov     [rbp+57h+hKey], rsi
0x140016258  mov     [rbp+57h+var_38], 7
0x140016260  mov     [rbp+57h+var_40], rsi
0x140016264  mov     word ptr [rbp+57h+lpSubKey], si
0x140016268  test    rcx, rcx
0x14001626b  jnz     short loc_140016277
0x14001626d  mov     ebx, 80004003h
0x140016272  jmp     loc_14001649E
0x140016277  lea     rdx, [rbp+57h+lpSubKey]
0x14001627b  call    ?GetStateSeparatedSiufRelativePath@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetStateSeparatedSiufRelativePath(ushort const *,std::wstring &)
0x140016280  mov     ebx, eax
0x140016282  test    eax, eax
0x140016284  js      loc_14001648E
0x14001628a  lea     rdx, [rbp+57h+lpSubKey]
0x14001628e  cmp     [rbp+57h+var_38], 8
0x140016293  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140016298  mov     [rsp+0D0h+lpdwDisposition], rsi; lpdwDisposition
0x14001629d  lea     rax, [rbp+57h+hKey]
0x1400162a1  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1400162a6  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1400162ab  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x1400162b3  mov     [rsp+0D0h+dwOptions], esi; dwOptions
0x1400162b7  xor     r9d, r9d; lpClass
0x1400162ba  xor     r8d, r8d; Reserved
0x1400162bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400162c4  call    cs:__imp_RegCreateKeyExW
0x1400162ca  test    eax, eax
0x1400162cc  jz      loc_140016390
0x1400162d2  jg      short loc_1400162D8
0x1400162d4  mov     ebx, eax
0x1400162d6  jmp     short loc_1400162E1
0x1400162d8  movzx   ebx, ax
0x1400162db  or      ebx, 80070000h
0x1400162e1  mov     eax, cs:dword_140027000
0x1400162e7  cmp     eax, 2
0x1400162ea  jbe     loc_14001648E
0x1400162f0  mov     rdx, cs:qword_140027018
0x1400162f7  mov     rax, cs:qword_140027010
0x1400162fe  mov     rcx, 400000000000h
0x140016308  test    rcx, rax
0x14001630b  jz      loc_14001648E
0x140016311  mov     rax, rdx
0x140016314  and     rax, rcx
0x140016317  cmp     rax, rdx
0x14001631a  jnz     loc_14001648E
0x140016320  mov     [rbp+57h+var_70], 1000000h
0x140016328  mov     [rbp+57h+var_80], 2D0h
0x14001632f  lea     rax, aSetrmtag; "SetRMTag"
0x140016336  mov     [rbp+57h+var_68], rax
0x14001633a  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140016341  mov     [rbp+57h+var_60], rax
0x140016345  mov     [rbp+57h+var_7C], ebx
0x140016348  lea     rax, aRegcreatekeyex; "RegCreateKeyExW failed creating SIUF_DA"...
0x14001634f  mov     [rbp+57h+var_58], rax
0x140016353  lea     rax, [rbp+57h+var_70]
0x140016357  mov     [rsp+0D0h+var_88], rax
0x14001635c  lea     rax, [rbp+57h+var_80]
0x140016360  mov     [rsp+0D0h+lpdwDisposition], rax
0x140016365  lea     rax, [rbp+57h+var_68]
0x140016369  mov     [rsp+0D0h+phkResult], rax
0x14001636e  lea     rax, [rbp+57h+var_60]
0x140016372  mov     [rsp+0D0h+lpSecurityAttributes], rax
0x140016377  lea     rax, [rbp+57h+var_7C]
0x14001637b  mov     qword ptr [rsp+0D0h+samDesired], rax
0x140016380  lea     rax, [rbp+57h+var_58]
0x140016384  lea     rdx, byte_1400227F5
0x14001638b  jmp     loc_140016484
0x140016390  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016394  inc     rax
0x140016397  cmp     [rdi+rax*2], si
0x14001639b  jnz     short loc_140016394
0x14001639d  lea     eax, ds:2[rax*2]
0x1400163a4  mov     [rsp+0D0h+samDesired], eax; cbData
0x1400163a8  mov     qword ptr [rsp+0D0h+dwOptions], rdi; lpData
0x1400163ad  mov     r9d, 1; dwType
0x1400163b3  xor     r8d, r8d; Reserved
0x1400163b6  lea     rdx, aRmtag; "RMTag"
0x1400163bd  mov     rcx, [rbp+57h+hKey]; hKey
0x1400163c1  call    cs:__imp_RegSetValueExW
0x1400163c7  test    eax, eax
0x1400163c9  jz      loc_14001648E
0x1400163cf  jg      short loc_1400163D5
0x1400163d1  mov     ebx, eax
0x1400163d3  jmp     short loc_1400163DE
0x1400163d5  movzx   ebx, ax
0x1400163d8  or      ebx, 80070000h
0x1400163de  mov     eax, cs:dword_140027000
0x1400163e4  cmp     eax, 2
0x1400163e7  jbe     loc_14001648E
0x1400163ed  mov     rdx, cs:qword_140027018
0x1400163f4  mov     rax, cs:qword_140027010
0x1400163fb  mov     rcx, 400000000000h
0x140016405  test    rcx, rax
0x140016408  jz      loc_14001648E
0x14001640e  mov     rax, rdx
0x140016411  and     rax, rcx
0x140016414  cmp     rax, rdx
0x140016417  jnz     short loc_14001648E
0x140016419  mov     [rbp+57h+var_58], 1000000h
0x140016421  mov     [rbp+57h+var_7C], 2E3h
0x140016428  lea     rax, aSetrmtag; "SetRMTag"
0x14001642f  mov     [rbp+57h+var_60], rax
0x140016433  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14001643a  mov     [rbp+57h+var_68], rax
0x14001643e  mov     [rbp+57h+var_80], ebx
0x140016441  lea     rax, aUnexpectedErro; "Unexpected error opening SIUF_DATA_PATH"
0x140016448  mov     [rbp+57h+var_70], rax
0x14001644c  lea     rax, [rbp+57h+var_58]
0x140016450  mov     [rsp+0D0h+var_88], rax
0x140016455  lea     rax, [rbp+57h+var_7C]
0x140016459  mov     [rsp+0D0h+lpdwDisposition], rax
0x14001645e  lea     rax, [rbp+57h+var_60]
0x140016462  mov     [rsp+0D0h+phkResult], rax
0x140016467  lea     rax, [rbp+57h+var_68]
0x14001646b  mov     [rsp+0D0h+lpSecurityAttributes], rax
0x140016470  lea     rax, [rbp+57h+var_80]
0x140016474  mov     qword ptr [rsp+0D0h+samDesired], rax
0x140016479  lea     rax, [rbp+57h+var_70]
0x14001647d  lea     rdx, byte_1400228B1
0x140016484  mov     qword ptr [rsp+0D0h+dwOptions], rax
0x140016489  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14001648e  mov     rcx, [rbp+57h+hKey]; hKey
0x140016492  test    rcx, rcx
0x140016495  jz      short loc_14001649E
0x140016497  call    cs:__imp_RegCloseKey
0x14001649d  nop
0x14001649e  cmp     [rbp+57h+var_38], 8
0x1400164a3  jb      short loc_1400164AF
0x1400164a5  mov     rcx, [rbp+57h+lpSubKey]
0x1400164a9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400164af  mov     eax, ebx
0x1400164b1  mov     rcx, [rbp+57h+var_30]
0x1400164b5  xor     rcx, rsp; StackCookie
0x1400164b8  call    __security_check_cookie
0x1400164bd  add     rsp, 0B8h
0x1400164c4  pop     rdi
0x1400164c5  pop     rsi
0x1400164c6  pop     rbx
0x1400164c7  pop     rbp
0x1400164c8  retn
```
