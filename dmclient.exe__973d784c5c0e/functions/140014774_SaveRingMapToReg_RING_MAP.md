# SaveRingMapToReg(_RING_MAP *)

- ea: `0x140014774`
- end: `0x140014a38`
- name: `?SaveRingMapToReg@@YAJPEAU_RING_MAP@@@Z`
- size: `708`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1400143cc`

## callees

- `0x140001418`
- `0x140014774`
- `0x1400156b4`
- `0x140019610`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140014a08`
- `msvcrt!??3@YAXPEAX@Z` at `0x140014a08`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014914`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014914`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400149f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400149f0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140014822`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140014822`

## string_xrefs

- `0x1400148ac`: `RegCreateKeyExW failed creating SIUF_DATA_PATH`
- `0x14001499a`: `RegSetValueEx failed for SIUF_REG_RING_MAP_VALUE_NAME`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    StateSeparatedSiufRelativePath = GetStateSeparatedSiufRelativePath(lpData, lpSubKey);
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
        if ( (unsigned int)dword_140028000 > 2
          && (qword_140028010 & 0x400000000000LL) != 0
          && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
        {
          v14 = 0x1000000;
          v11 = 234;
          v15 = "SaveRingMapToReg";
          v16 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
          v12 = StateSeparatedSiufRelativePath;
          v17 = (__int64)"RegCreateKeyExW failed creating SIUF_DATA_PATH";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            0,
            (unsigned int)byte_140023AED,
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
          if ( (unsigned int)dword_140028000 > 2
            && (qword_140028010 & 0x400000000000LL) != 0
            && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
          {
            v17 = 0x1000000;
            v12 = 253;
            v16 = "SaveRingMapToReg";
            v15 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
            v11 = StateSeparatedSiufRelativePath;
            v14 = (__int64)"RegSetValueEx failed for SIUF_REG_RING_MAP_VALUE_NAME";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              0,
              (unsigned int)&byte_140023D7F,
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
0x140014774  mov     [rsp-8+arg_8], rbx
0x140014779  mov     [rsp-8+arg_10], rdi
0x14001477e  push    rbp
0x14001477f  lea     rbp, [rsp-57h]
0x140014784  sub     rsp, 0B0h
0x14001478b  mov     rax, cs:__security_cookie
0x140014792  xor     rax, rsp
0x140014795  mov     [rbp+57h+var_10], rax
0x140014799  mov     rdi, rcx
0x14001479c  mov     [rbp+57h+hKey], 0
0x1400147a4  mov     [rbp+57h+var_18], 7
0x1400147ac  mov     [rbp+57h+var_20], 0
0x1400147b4  xor     eax, eax
0x1400147b6  mov     word ptr [rbp+57h+lpSubKey], ax
0x1400147ba  test    rcx, rcx
0x1400147bd  jnz     short loc_1400147C9
0x1400147bf  mov     ebx, 80004003h
0x1400147c4  jmp     loc_1400149FD
0x1400147c9  lea     rdx, [rbp+57h+lpSubKey]
0x1400147cd  call    ?GetStateSeparatedSiufRelativePath@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetStateSeparatedSiufRelativePath(ushort const *,std::wstring &)
0x1400147d2  mov     ebx, eax
0x1400147d4  test    eax, eax
0x1400147d6  js      loc_1400149E7
0x1400147dc  lea     rdx, [rbp+57h+lpSubKey]
0x1400147e0  cmp     [rbp+57h+var_18], 8
0x1400147e5  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1400147ea  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x1400147f3  lea     rax, [rbp+57h+hKey]
0x1400147f7  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1400147fc  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140014805  mov     [rsp+0B0h+samDesired], 0F003Fh; samDesired
0x14001480d  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x140014815  xor     r9d, r9d; lpClass
0x140014818  xor     r8d, r8d; Reserved
0x14001481b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140014822  call    cs:__imp_RegCreateKeyExW
0x140014829  nop     dword ptr [rax+rax+00h]
0x14001482e  test    eax, eax
0x140014830  jz      loc_1400148F4
0x140014836  jg      short loc_14001483C
0x140014838  mov     ebx, eax
0x14001483a  jmp     short loc_140014845
0x14001483c  movzx   ebx, ax
0x14001483f  or      ebx, 80070000h
0x140014845  mov     eax, cs:dword_140028000
0x14001484b  cmp     eax, 2
0x14001484e  jbe     loc_1400149E7
0x140014854  mov     rdx, cs:qword_140028018
0x14001485b  mov     rax, cs:qword_140028010
0x140014862  mov     rcx, 400000000000h
0x14001486c  test    rcx, rax
0x14001486f  jz      loc_1400149E7
0x140014875  mov     rax, rdx
0x140014878  and     rax, rcx
0x14001487b  cmp     rax, rdx
0x14001487e  jnz     loc_1400149E7
0x140014884  mov     [rbp+57h+var_50], 1000000h
0x14001488c  mov     [rbp+57h+var_60], 0EAh
0x140014893  lea     rax, aSaveringmaptor; "SaveRingMapToReg"
0x14001489a  mov     [rbp+57h+var_48], rax
0x14001489e  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400148a5  mov     [rbp+57h+var_40], rax
0x1400148a9  mov     [rbp+57h+var_5C], ebx
0x1400148ac  lea     rax, aRegcreatekeyex; "RegCreateKeyExW failed creating SIUF_DA"...
0x1400148b3  mov     [rbp+57h+var_38], rax
0x1400148b7  lea     rax, [rbp+57h+var_50]
0x1400148bb  mov     [rsp+0B0h+var_68], rax
0x1400148c0  lea     rax, [rbp+57h+var_60]
0x1400148c4  mov     [rsp+0B0h+lpdwDisposition], rax
0x1400148c9  lea     rax, [rbp+57h+var_48]
0x1400148cd  mov     [rsp+0B0h+phkResult], rax
0x1400148d2  lea     rax, [rbp+57h+var_40]
0x1400148d6  mov     [rsp+0B0h+lpSecurityAttributes], rax
0x1400148db  lea     rax, [rbp+57h+var_5C]
0x1400148df  mov     qword ptr [rsp+0B0h+samDesired], rax
0x1400148e4  lea     rax, [rbp+57h+var_38]
0x1400148e8  lea     rdx, byte_140023AED
0x1400148ef  jmp     loc_1400149DD
0x1400148f4  mov     eax, [rdi+4]
0x1400148f7  mov     [rsp+0B0h+samDesired], eax; cbData
0x1400148fb  mov     qword ptr [rsp+0B0h+dwOptions], rdi; lpData
0x140014900  mov     r9d, 3; dwType
0x140014906  xor     r8d, r8d; Reserved
0x140014909  lea     rdx, aRm; "RM"
0x140014910  mov     rcx, [rbp+57h+hKey]; hKey
0x140014914  call    cs:__imp_RegSetValueExW
0x14001491b  nop     dword ptr [rax+rax+00h]
0x140014920  test    eax, eax
0x140014922  jz      loc_1400149E7
0x140014928  jg      short loc_14001492E
0x14001492a  mov     ebx, eax
0x14001492c  jmp     short loc_140014937
0x14001492e  movzx   ebx, ax
0x140014931  or      ebx, 80070000h
0x140014937  mov     eax, cs:dword_140028000
0x14001493d  cmp     eax, 2
0x140014940  jbe     loc_1400149E7
0x140014946  mov     rdx, cs:qword_140028018
0x14001494d  mov     rax, cs:qword_140028010
0x140014954  mov     rcx, 400000000000h
0x14001495e  test    rcx, rax
0x140014961  jz      loc_1400149E7
0x140014967  mov     rax, rdx
0x14001496a  and     rax, rcx
0x14001496d  cmp     rax, rdx
0x140014970  jnz     short loc_1400149E7
0x140014972  mov     [rbp+57h+var_38], 1000000h
0x14001497a  mov     [rbp+57h+var_5C], 0FDh
0x140014981  lea     rax, aSaveringmaptor; "SaveRingMapToReg"
0x140014988  mov     [rbp+57h+var_40], rax
0x14001498c  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140014993  mov     [rbp+57h+var_48], rax
0x140014997  mov     [rbp+57h+var_60], ebx
0x14001499a  lea     rax, aRegsetvalueexF; "RegSetValueEx failed for SIUF_REG_RING_"...
0x1400149a1  mov     [rbp+57h+var_50], rax
0x1400149a5  lea     rax, [rbp+57h+var_38]
0x1400149a9  mov     [rsp+0B0h+var_68], rax
0x1400149ae  lea     rax, [rbp+57h+var_5C]
0x1400149b2  mov     [rsp+0B0h+lpdwDisposition], rax
0x1400149b7  lea     rax, [rbp+57h+var_40]
0x1400149bb  mov     [rsp+0B0h+phkResult], rax
0x1400149c0  lea     rax, [rbp+57h+var_48]
0x1400149c4  mov     [rsp+0B0h+lpSecurityAttributes], rax
0x1400149c9  lea     rax, [rbp+57h+var_60]
0x1400149cd  mov     qword ptr [rsp+0B0h+samDesired], rax
0x1400149d2  lea     rax, [rbp+57h+var_50]
0x1400149d6  lea     rdx, byte_140023D7F
0x1400149dd  mov     qword ptr [rsp+0B0h+dwOptions], rax
0x1400149e2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400149e7  mov     rcx, [rbp+57h+hKey]; hKey
0x1400149eb  test    rcx, rcx
0x1400149ee  jz      short loc_1400149FD
0x1400149f0  call    cs:__imp_RegCloseKey
0x1400149f7  nop     dword ptr [rax+rax+00h]
0x1400149fc  nop
0x1400149fd  cmp     [rbp+57h+var_18], 8
0x140014a02  jb      short loc_140014A14
0x140014a04  mov     rcx, [rbp+57h+lpSubKey]
0x140014a08  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140014a0f  nop     dword ptr [rax+rax+00h]
0x140014a14  mov     eax, ebx
0x140014a16  mov     rcx, [rbp+57h+var_10]
0x140014a1a  xor     rcx, rsp; StackCookie
0x140014a1d  call    __security_check_cookie
0x140014a22  lea     r11, [rsp+0B0h+var_s0]
0x140014a2a  mov     rbx, [r11+18h]
0x140014a2e  mov     rdi, [r11+20h]
0x140014a32  mov     rsp, r11
0x140014a35  pop     rbp
0x140014a36  retn
```
