# SetRMTag(ushort *)

- ea: `0x140014a40`
- end: `0x140014cf2`
- name: `?SetRMTag@@YAJPEAG@Z`
- size: `690`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1400143cc`

## callees

- `0x140001418`
- `0x140014a40`
- `0x1400156b4`
- `0x140019610`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140014ccb`
- `msvcrt!??3@YAXPEAX@Z` at `0x140014ccb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014bd7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014bd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014cb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014cb3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140014ad4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140014ad4`

## string_xrefs

- `0x140014b5e`: `RegCreateKeyExW failed creating SIUF_DATA_PATH`
- `0x140014c5d`: `Unexpected error opening SIUF_DATA_PATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetRMTag(BYTE *lpData)
{
  signed int StateSeparatedSiufRelativePath; // ebx
  const WCHAR *v3; // rdx
  LSTATUS v4; // eax
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rax
  LSTATUS v8; // eax
  int v9; // r8d
  int v10; // r9d
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
    StateSeparatedSiufRelativePath = GetStateSeparatedSiufRelativePath(lpData, lpSubKey);
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
        if ( (unsigned int)dword_140028000 > 2
          && (qword_140028010 & 0x400000000000LL) != 0
          && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
        {
          v15 = 0x1000000;
          v12 = 720;
          v16 = "SetRMTag";
          v17 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
          v13 = StateSeparatedSiufRelativePath;
          v18 = (__int64)"RegCreateKeyExW failed creating SIUF_DATA_PATH";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            0,
            (unsigned int)byte_1400237FD,
            v5,
            v6,
            (__int64)&v18,
            (__int64)&v13,
            (__int64)&v17,
            (__int64)&v16,
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
          if ( (unsigned int)dword_140028000 > 2
            && (qword_140028010 & 0x400000000000LL) != 0
            && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
          {
            v18 = 0x1000000;
            v13 = 739;
            v17 = "SetRMTag";
            v16 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufring\\siufring.cpp";
            v12 = StateSeparatedSiufRelativePath;
            v15 = (__int64)"Unexpected error opening SIUF_DATA_PATH";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              0,
              (unsigned int)byte_1400238B9,
              v9,
              v10,
              (__int64)&v15,
              (__int64)&v12,
              (__int64)&v16,
              (__int64)&v17,
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
0x140014a40  push    rbp
0x140014a42  push    rbx
0x140014a43  push    rsi
0x140014a44  push    rdi
0x140014a45  lea     rbp, [rsp-3Fh]
0x140014a4a  sub     rsp, 0B8h
0x140014a51  mov     rax, cs:__security_cookie
0x140014a58  xor     rax, rsp
0x140014a5b  mov     [rbp+57h+var_30], rax
0x140014a5f  mov     rdi, rcx
0x140014a62  xor     esi, esi
0x140014a64  mov     [rbp+57h+hKey], rsi
0x140014a68  mov     [rbp+57h+var_38], 7
0x140014a70  mov     [rbp+57h+var_40], rsi
0x140014a74  mov     word ptr [rbp+57h+lpSubKey], si
0x140014a78  test    rcx, rcx
0x140014a7b  jnz     short loc_140014A87
0x140014a7d  mov     ebx, 80004003h
0x140014a82  jmp     loc_140014CC0
0x140014a87  lea     rdx, [rbp+57h+lpSubKey]
0x140014a8b  call    ?GetStateSeparatedSiufRelativePath@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetStateSeparatedSiufRelativePath(ushort const *,std::wstring &)
0x140014a90  mov     ebx, eax
0x140014a92  test    eax, eax
0x140014a94  js      loc_140014CAA
0x140014a9a  lea     rdx, [rbp+57h+lpSubKey]
0x140014a9e  cmp     [rbp+57h+var_38], 8
0x140014aa3  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140014aa8  mov     [rsp+0D0h+lpdwDisposition], rsi; lpdwDisposition
0x140014aad  lea     rax, [rbp+57h+hKey]
0x140014ab1  mov     [rsp+0D0h+phkResult], rax; phkResult
0x140014ab6  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x140014abb  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x140014ac3  mov     [rsp+0D0h+dwOptions], esi; dwOptions
0x140014ac7  xor     r9d, r9d; lpClass
0x140014aca  xor     r8d, r8d; Reserved
0x140014acd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140014ad4  call    cs:__imp_RegCreateKeyExW
0x140014adb  nop     dword ptr [rax+rax+00h]
0x140014ae0  test    eax, eax
0x140014ae2  jz      loc_140014BA6
0x140014ae8  jg      short loc_140014AEE
0x140014aea  mov     ebx, eax
0x140014aec  jmp     short loc_140014AF7
0x140014aee  movzx   ebx, ax
0x140014af1  or      ebx, 80070000h
0x140014af7  mov     eax, cs:dword_140028000
0x140014afd  cmp     eax, 2
0x140014b00  jbe     loc_140014CAA
0x140014b06  mov     rdx, cs:qword_140028018
0x140014b0d  mov     rax, cs:qword_140028010
0x140014b14  mov     rcx, 400000000000h
0x140014b1e  test    rcx, rax
0x140014b21  jz      loc_140014CAA
0x140014b27  mov     rax, rdx
0x140014b2a  and     rax, rcx
0x140014b2d  cmp     rax, rdx
0x140014b30  jnz     loc_140014CAA
0x140014b36  mov     [rbp+57h+var_70], 1000000h
0x140014b3e  mov     [rbp+57h+var_80], 2D0h
0x140014b45  lea     rax, aSetrmtag; "SetRMTag"
0x140014b4c  mov     [rbp+57h+var_68], rax
0x140014b50  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140014b57  mov     [rbp+57h+var_60], rax
0x140014b5b  mov     [rbp+57h+var_7C], ebx
0x140014b5e  lea     rax, aRegcreatekeyex; "RegCreateKeyExW failed creating SIUF_DA"...
0x140014b65  mov     [rbp+57h+var_58], rax
0x140014b69  lea     rax, [rbp+57h+var_70]
0x140014b6d  mov     [rsp+0D0h+var_88], rax
0x140014b72  lea     rax, [rbp+57h+var_80]
0x140014b76  mov     [rsp+0D0h+lpdwDisposition], rax
0x140014b7b  lea     rax, [rbp+57h+var_68]
0x140014b7f  mov     [rsp+0D0h+phkResult], rax
0x140014b84  lea     rax, [rbp+57h+var_60]
0x140014b88  mov     [rsp+0D0h+lpSecurityAttributes], rax
0x140014b8d  lea     rax, [rbp+57h+var_7C]
0x140014b91  mov     qword ptr [rsp+0D0h+samDesired], rax
0x140014b96  lea     rax, [rbp+57h+var_58]
0x140014b9a  lea     rdx, byte_1400237FD
0x140014ba1  jmp     loc_140014CA0
0x140014ba6  or      rax, 0FFFFFFFFFFFFFFFFh
0x140014baa  inc     rax
0x140014bad  cmp     [rdi+rax*2], si
0x140014bb1  jnz     short loc_140014BAA
0x140014bb3  lea     eax, ds:2[rax*2]
0x140014bba  mov     [rsp+0D0h+samDesired], eax; cbData
0x140014bbe  mov     qword ptr [rsp+0D0h+dwOptions], rdi; lpData
0x140014bc3  mov     r9d, 1; dwType
0x140014bc9  xor     r8d, r8d; Reserved
0x140014bcc  lea     rdx, aRmtag; "RMTag"
0x140014bd3  mov     rcx, [rbp+57h+hKey]; hKey
0x140014bd7  call    cs:__imp_RegSetValueExW
0x140014bde  nop     dword ptr [rax+rax+00h]
0x140014be3  test    eax, eax
0x140014be5  jz      loc_140014CAA
0x140014beb  jg      short loc_140014BF1
0x140014bed  mov     ebx, eax
0x140014bef  jmp     short loc_140014BFA
0x140014bf1  movzx   ebx, ax
0x140014bf4  or      ebx, 80070000h
0x140014bfa  mov     eax, cs:dword_140028000
0x140014c00  cmp     eax, 2
0x140014c03  jbe     loc_140014CAA
0x140014c09  mov     rdx, cs:qword_140028018
0x140014c10  mov     rax, cs:qword_140028010
0x140014c17  mov     rcx, 400000000000h
0x140014c21  test    rcx, rax
0x140014c24  jz      loc_140014CAA
0x140014c2a  mov     rax, rdx
0x140014c2d  and     rax, rcx
0x140014c30  cmp     rax, rdx
0x140014c33  jnz     short loc_140014CAA
0x140014c35  mov     [rbp+57h+var_58], 1000000h
0x140014c3d  mov     [rbp+57h+var_7C], 2E3h
0x140014c44  lea     rax, aSetrmtag; "SetRMTag"
0x140014c4b  mov     [rbp+57h+var_60], rax
0x140014c4f  lea     rax, aOnecoreBaseDia_4; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140014c56  mov     [rbp+57h+var_68], rax
0x140014c5a  mov     [rbp+57h+var_80], ebx
0x140014c5d  lea     rax, aUnexpectedErro; "Unexpected error opening SIUF_DATA_PATH"
0x140014c64  mov     [rbp+57h+var_70], rax
0x140014c68  lea     rax, [rbp+57h+var_58]
0x140014c6c  mov     [rsp+0D0h+var_88], rax
0x140014c71  lea     rax, [rbp+57h+var_7C]
0x140014c75  mov     [rsp+0D0h+lpdwDisposition], rax
0x140014c7a  lea     rax, [rbp+57h+var_60]
0x140014c7e  mov     [rsp+0D0h+phkResult], rax
0x140014c83  lea     rax, [rbp+57h+var_68]
0x140014c87  mov     [rsp+0D0h+lpSecurityAttributes], rax
0x140014c8c  lea     rax, [rbp+57h+var_80]
0x140014c90  mov     qword ptr [rsp+0D0h+samDesired], rax
0x140014c95  lea     rax, [rbp+57h+var_70]
0x140014c99  lea     rdx, byte_1400238B9
0x140014ca0  mov     qword ptr [rsp+0D0h+dwOptions], rax
0x140014ca5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140014caa  mov     rcx, [rbp+57h+hKey]; hKey
0x140014cae  test    rcx, rcx
0x140014cb1  jz      short loc_140014CC0
0x140014cb3  call    cs:__imp_RegCloseKey
0x140014cba  nop     dword ptr [rax+rax+00h]
0x140014cbf  nop
0x140014cc0  cmp     [rbp+57h+var_38], 8
0x140014cc5  jb      short loc_140014CD7
0x140014cc7  mov     rcx, [rbp+57h+lpSubKey]
0x140014ccb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140014cd2  nop     dword ptr [rax+rax+00h]
0x140014cd7  mov     eax, ebx
0x140014cd9  mov     rcx, [rbp+57h+var_30]
0x140014cdd  xor     rcx, rsp; StackCookie
0x140014ce0  call    __security_check_cookie
0x140014ce5  add     rsp, 0B8h
0x140014cec  pop     rdi
0x140014ced  pop     rsi
0x140014cee  pop     rbx
0x140014cef  pop     rbp
0x140014cf0  retn
```
