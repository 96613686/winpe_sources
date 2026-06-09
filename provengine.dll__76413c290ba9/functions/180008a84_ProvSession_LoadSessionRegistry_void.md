# ProvSession::LoadSessionRegistry(void)

- ea: `0x180008a84`
- end: `0x180008e55`
- name: `?LoadSessionRegistry@ProvSession@@AEAAJXZ`
- size: `977`
- prototype: `__int64 __fastcall(ProvSession *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180008900`
- `0x1800097d0`

## callees

- `0x1800010c8`
- `0x1800011ac`
- `0x180008a84`
- `0x1800098dc`
- `0x180009900`
- `0x180009b84`
- `0x18000af20`
- `0x180033218`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008b44`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008d78`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008e0d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008b44`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008d78`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008e0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008bc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008bc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008c72`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008c72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008c2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008c2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e2d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180008cf0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180008cf0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d05`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProvSession::LoadSessionRegistry(ProvSession *this)
{
  signed int SzValue; // ebx
  __int64 v3; // rdx
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  char *v7; // rdi
  HKEY *v8; // r14
  HKEY v9; // r12
  HKEY v10; // r15
  DWORD LastError; // ebx
  LSTATUS Value; // eax
  const WCHAR *v13; // r8
  bool v14; // dl
  __int64 v15; // r9
  signed int v16; // eax
  void **v17; // rbx
  struct TraceLoggingCorrelationVector *v18; // rsi
  void *v19; // rcx
  char *v20; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v27; // [rsp+68h] [rbp-98h]
  _BYTE v28[32]; // [rsp+70h] [rbp-90h] BYREF
  DWORD *v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  CHAR MultiByteStr[144]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  if ( (unsigned int)dword_18005A000 > 4 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004E423, 0, 0, 2, v28);
  hKey = 0;
  v27 = 7;
  v26 = 0;
  LOWORD(lpSubKey[0]) = 0;
  SzValue = RegGetSzValue(*((HKEY *)this + 11), L"LastSession", lpSubKey);
  if ( SzValue < 0 )
  {
    v3 = 435;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
      (const char *)(unsigned int)SzValue,
      phkResult);
LABEL_6:
    if ( v27 >= 8 )
      operator delete((void *)lpSubKey[0]);
    v27 = 7;
    v26 = 0;
    LOWORD(lpSubKey[0]) = 0;
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)SzValue;
  }
  hKey = 0;
  v5 = (const WCHAR *)lpSubKey;
  if ( v27 >= 8 )
    v5 = lpSubKey[0];
  v6 = RegOpenKeyExW(*((HKEY *)this + 11), v5, 0, 0xFu, &hKey);
  if ( v6 )
  {
    SzValue = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x1BD,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
                (const char *)v6,
                phkResulta);
    goto LABEL_6;
  }
  v7 = (char *)this + 24;
  std::wstring::assign((void **)this + 3, (void **)lpSubKey, 0, 0xFFFFFFFFFFFFFFFFuLL);
  v8 = (HKEY *)((char *)this + 96);
  if ( (HKEY *)((char *)this + 96) != &hKey )
  {
    v9 = hKey;
    v10 = *v8;
    if ( *v8 )
    {
      LastError = GetLastError();
      RegCloseKey(v10);
      SetLastError(LastError);
    }
    *v8 = v9;
    hKey = 0;
  }
  cbData[0] = 4;
  Value = RegQueryValueExW(*v8, L"RebootCount", 0, 0, (LPBYTE)this + 16, cbData);
  SzValue = Value;
  if ( Value > 0 )
    SzValue = (unsigned __int16)Value | 0x80070000;
  if ( SzValue < 0 )
  {
    v3 = 452;
    goto LABEL_5;
  }
  SzValue = RegGetSzValue(*v8, L"BeginTime", (char *)this + 56);
  if ( SzValue < 0 )
  {
    v3 = 453;
    goto LABEL_5;
  }
  if ( *((_QWORD *)this + 6) < 8u )
    v13 = (const WCHAR *)((char *)this + 24);
  else
    v13 = *(const WCHAR **)v7;
  if ( WideCharToMultiByte(0, 0x400u, v13, -1, MultiByteStr, 129, 0, 0) )
  {
    v17 = (void **)((char *)this + 104);
    v18 = TraceLoggingCorrelationVector::Set(MultiByteStr, v14);
    v19 = *v17;
    if ( v18 != *v17 )
    {
      if ( v19 )
        operator delete(v19);
      *v17 = v18;
    }
  }
  else
  {
    if ( (unsigned int)dword_18005A000 > 3 )
    {
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      cbData[0] = v16;
      v29 = cbData;
      v30 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004E4F2, 0, 0, 3, v28);
    }
    v17 = (void **)((char *)this + 104);
  }
  if ( !*v17 && (unsigned int)dword_18005A000 > 3 )
  {
    if ( *((_QWORD *)v7 + 3) < 8u )
      v20 = v7;
    else
      v20 = *(char **)v7;
    *(_QWORD *)cbData = v20;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_18005A000,
      (__int64)byte_18004E44B,
      0,
      v15,
      (__int64 **)cbData);
  }
  if ( (unsigned int)dword_18005A000 > 4 )
  {
    if ( *((_QWORD *)v7 + 3) >= 8u )
      v7 = *(char **)v7;
    *(_QWORD *)cbData = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_18005A000,
      (__int64)&dword_18004E3C4,
      0,
      v15,
      (__int64 **)cbData);
  }
  if ( v27 >= 8 )
    operator delete((void *)lpSubKey[0]);
  v27 = 7;
  v26 = 0;
  LOWORD(lpSubKey[0]) = 0;
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180008a84  push    rbp
0x180008a86  push    rbx
0x180008a87  push    rsi
0x180008a88  push    rdi
0x180008a89  push    r12
0x180008a8b  push    r13
0x180008a8d  push    r14
0x180008a8f  push    r15
0x180008a91  lea     rbp, [rsp-48h]
0x180008a96  sub     rsp, 148h
0x180008a9d  mov     rax, cs:__security_cookie
0x180008aa4  xor     rax, rsp
0x180008aa7  mov     [rbp+80h+var_50], rax
0x180008aab  mov     rsi, rcx
0x180008aae  mov     eax, cs:dword_18005A000
0x180008ab4  cmp     eax, 4
0x180008ab7  jbe     short loc_180008AE4
0x180008ab9  lea     rax, [rsp+180h+var_110]
0x180008abe  mov     [rsp+180h+lpcbData], rax
0x180008ac3  mov     dword ptr [rsp+180h+phkResult], 2; int
0x180008acb  xor     r9d, r9d
0x180008ace  xor     r8d, r8d
0x180008ad1  lea     rdx, byte_18004E423
0x180008ad8  lea     rcx, dword_18005A000
0x180008adf  call    _tlgWriteTransfer_EventWriteTransfer
0x180008ae4  xor     r13d, r13d
0x180008ae7  mov     [rsp+180h+hKey], r13
0x180008aec  lea     r15d, [r13+7]
0x180008af0  mov     [rsp+180h+var_118], r15
0x180008af5  mov     [rsp+180h+var_120], r13
0x180008afa  mov     word ptr [rsp+180h+lpSubKey], r13w
0x180008b00  lea     r8, [rsp+180h+lpSubKey]; void *
0x180008b05  lea     rdx, aLastsession; "LastSession"
0x180008b0c  mov     rcx, [rsi+58h]; hKey
0x180008b10  call    ?RegGetSzValue@@YAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegGetSzValue(HKEY__ *,ushort const *,std::wstring &)
0x180008b15  mov     ebx, eax
0x180008b17  test    eax, eax
0x180008b19  jns     short loc_180008B71
0x180008b1b  mov     edx, 1B3h; void *
0x180008b20  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180008b27  mov     r9d, ebx; char *
0x180008b2a  mov     rcx, [rbp+88h]; this
0x180008b31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b36  nop
0x180008b37  cmp     [rsp+180h+var_118], 8
0x180008b3d  jb      short loc_180008B4A
0x180008b3f  mov     rcx, [rsp+180h+lpSubKey]
0x180008b44  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008b4a  mov     [rsp+180h+var_118], r15
0x180008b4f  mov     [rsp+180h+var_120], r13
0x180008b54  mov     word ptr [rsp+180h+lpSubKey], r13w
0x180008b5a  mov     rcx, [rsp+180h+hKey]; hKey
0x180008b5f  test    rcx, rcx
0x180008b62  jz      short loc_180008B6A
0x180008b64  call    cs:__imp_RegCloseKey
0x180008b6a  mov     eax, ebx
0x180008b6c  jmp     loc_180008E35
0x180008b71  mov     rdi, [rsp+180h+hKey]
0x180008b76  test    rdi, rdi
0x180008b79  jz      short loc_180008B94
0x180008b7b  call    cs:__imp_GetLastError
0x180008b81  mov     ebx, eax
0x180008b83  mov     rcx, rdi; hKey
0x180008b86  call    cs:__imp_RegCloseKey
0x180008b8c  mov     ecx, ebx; dwErrCode
0x180008b8e  call    cs:__imp_SetLastError
0x180008b94  mov     [rsp+180h+hKey], r13
0x180008b99  lea     rdx, [rsp+180h+lpSubKey]
0x180008b9e  cmp     [rsp+180h+var_118], 8
0x180008ba4  cmovnb  rdx, [rsp+180h+lpSubKey]; lpSubKey
0x180008baa  lea     rax, [rsp+180h+hKey]
0x180008baf  mov     [rsp+180h+phkResult], rax; unsigned int
0x180008bb4  mov     r9d, 0Fh; samDesired
0x180008bba  xor     r8d, r8d; ulOptions
0x180008bbd  mov     rcx, [rsi+58h]; hKey
0x180008bc1  call    cs:__imp_RegOpenKeyExW
0x180008bc7  test    eax, eax
0x180008bc9  jz      short loc_180008BED
0x180008bcb  mov     rcx, [rbp+88h]; this
0x180008bd2  mov     r9d, eax; char *
0x180008bd5  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180008bdc  mov     edx, 1BDh; void *
0x180008be1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180008be6  mov     ebx, eax
0x180008be8  jmp     loc_180008B37
0x180008bed  lea     rdi, [rsi+18h]
0x180008bf1  or      r9, 0FFFFFFFFFFFFFFFFh
0x180008bf5  xor     r8d, r8d
0x180008bf8  lea     rdx, [rsp+180h+lpSubKey]
0x180008bfd  mov     rcx, rdi; void *
0x180008c00  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180008c05  lea     r14, [rsi+60h]
0x180008c09  lea     rax, [rsp+180h+hKey]
0x180008c0e  cmp     r14, rax
0x180008c11  jz      short loc_180008C47
0x180008c13  mov     r12, [rsp+180h+hKey]
0x180008c18  mov     r15, [r14]
0x180008c1b  test    r15, r15
0x180008c1e  jz      short loc_180008C39
0x180008c20  call    cs:__imp_GetLastError
0x180008c26  mov     ebx, eax
0x180008c28  mov     rcx, r15; hKey
0x180008c2b  call    cs:__imp_RegCloseKey
0x180008c31  mov     ecx, ebx; dwErrCode
0x180008c33  call    cs:__imp_SetLastError
0x180008c39  mov     [r14], r12
0x180008c3c  mov     [rsp+180h+hKey], r13
0x180008c41  mov     r15d, 7
0x180008c47  mov     [rsp+180h+cbData], 4
0x180008c4f  lea     rax, [rsi+10h]
0x180008c53  lea     rcx, [rsp+180h+cbData]
0x180008c58  mov     [rsp+180h+lpcbData], rcx; lpcbData
0x180008c5d  mov     [rsp+180h+phkResult], rax; lpData
0x180008c62  xor     r9d, r9d; lpType
0x180008c65  xor     r8d, r8d; lpReserved
0x180008c68  lea     rdx, aRebootcount; "RebootCount"
0x180008c6f  mov     rcx, [r14]; hKey
0x180008c72  call    cs:__imp_RegQueryValueExW
0x180008c78  mov     ebx, eax
0x180008c7a  mov     r12d, 80070000h
0x180008c80  test    eax, eax
0x180008c82  jle     short loc_180008C8A
0x180008c84  movzx   ebx, ax
0x180008c87  or      ebx, r12d
0x180008c8a  test    ebx, ebx
0x180008c8c  jns     short loc_180008C98
0x180008c8e  mov     edx, 1C4h
0x180008c93  jmp     loc_180008B20
0x180008c98  lea     r8, [rsi+38h]; void *
0x180008c9c  lea     rdx, aBegintime; "BeginTime"
0x180008ca3  mov     rcx, [r14]; hKey
0x180008ca6  call    ?RegGetSzValue@@YAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegGetSzValue(HKEY__ *,ushort const *,std::wstring &)
0x180008cab  mov     ebx, eax
0x180008cad  test    eax, eax
0x180008caf  jns     short loc_180008CBB
0x180008cb1  mov     edx, 1C5h
0x180008cb6  jmp     loc_180008B20
0x180008cbb  cmp     qword ptr [rdi+18h], 8
0x180008cc0  jb      short loc_180008CC7
0x180008cc2  mov     r8, [rdi]
0x180008cc5  jmp     short loc_180008CCA
0x180008cc7  mov     r8, rdi; lpWideCharStr
0x180008cca  mov     [rsp+180h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180008ccf  mov     [rsp+180h+lpDefaultChar], r13; lpDefaultChar
0x180008cd4  mov     dword ptr [rsp+180h+lpcbData], 81h; cbMultiByte
0x180008cdc  lea     rax, [rbp+80h+MultiByteStr]
0x180008ce0  mov     [rsp+180h+phkResult], rax; lpMultiByteStr
0x180008ce5  or      r9d, 0FFFFFFFFh; cchWideChar
0x180008ce9  mov     edx, 400h; dwFlags
0x180008cee  xor     ecx, ecx; CodePage
0x180008cf0  call    cs:__imp_WideCharToMultiByte
0x180008cf6  test    eax, eax
0x180008cf8  jnz     short loc_180008D5B
0x180008cfa  mov     eax, cs:dword_18005A000
0x180008d00  cmp     eax, 3
0x180008d03  jbe     short loc_180008D55
0x180008d05  call    cs:__imp_GetLastError
0x180008d0b  test    eax, eax
0x180008d0d  jle     short loc_180008D15
0x180008d0f  movzx   eax, ax
0x180008d12  or      eax, r12d
0x180008d15  mov     [rsp+180h+cbData], eax
0x180008d19  lea     rax, [rsp+180h+cbData]
0x180008d1e  mov     [rbp+80h+var_F0], rax
0x180008d22  mov     [rbp+80h+var_E8], 4
0x180008d2a  lea     rax, [rsp+180h+var_110]
0x180008d2f  mov     [rsp+180h+lpcbData], rax
0x180008d34  mov     dword ptr [rsp+180h+phkResult], 3
0x180008d3c  xor     r9d, r9d
0x180008d3f  xor     r8d, r8d
0x180008d42  lea     rdx, word_18004E4F2
0x180008d49  lea     rcx, dword_18005A000
0x180008d50  call    _tlgWriteTransfer_EventWriteTransfer
0x180008d55  lea     rbx, [rsi+68h]
0x180008d59  jmp     short loc_180008D81
0x180008d5b  lea     rbx, [rsi+68h]
0x180008d5f  lea     rcx, [rbp+80h+MultiByteStr]; Source
0x180008d63  call    ?Set@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Set(char const *,bool)
0x180008d68  mov     rsi, rax
0x180008d6b  mov     rcx, [rbx]
0x180008d6e  cmp     rax, rcx
0x180008d71  jz      short loc_180008D81
0x180008d73  test    rcx, rcx
0x180008d76  jz      short loc_180008D7E
0x180008d78  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008d7e  mov     [rbx], rsi
0x180008d81  cmp     [rbx], r13
0x180008d84  jnz     short loc_180008DC5
0x180008d86  mov     eax, cs:dword_18005A000
0x180008d8c  cmp     eax, 3
0x180008d8f  jbe     short loc_180008DC5
0x180008d91  cmp     qword ptr [rdi+18h], 8
0x180008d96  jb      short loc_180008D9D
0x180008d98  mov     rax, [rdi]
0x180008d9b  jmp     short loc_180008DA0
0x180008d9d  mov     rax, rdi
0x180008da0  mov     qword ptr [rsp+180h+cbData], rax
0x180008da5  lea     rax, [rsp+180h+cbData]
0x180008daa  mov     [rsp+180h+phkResult], rax
0x180008daf  xor     r8d, r8d
0x180008db2  lea     rdx, byte_18004E44B
0x180008db9  lea     rcx, dword_18005A000
0x180008dc0  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180008dc5  mov     eax, cs:dword_18005A000
0x180008dcb  cmp     eax, 4
0x180008dce  jbe     short loc_180008E00
0x180008dd0  cmp     qword ptr [rdi+18h], 8
0x180008dd5  jb      short loc_180008DDA
0x180008dd7  mov     rdi, [rdi]
0x180008dda  mov     qword ptr [rsp+180h+cbData], rdi
0x180008ddf  lea     rax, [rsp+180h+cbData]
0x180008de4  mov     [rsp+180h+phkResult], rax
0x180008de9  xor     r8d, r8d
0x180008dec  lea     rdx, dword_18004E3C4
0x180008df3  lea     rcx, dword_18005A000
0x180008dfa  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180008dff  nop
0x180008e00  cmp     [rsp+180h+var_118], 8
0x180008e06  jb      short loc_180008E13
0x180008e08  mov     rcx, [rsp+180h+lpSubKey]
0x180008e0d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008e13  mov     [rsp+180h+var_118], r15
0x180008e18  mov     [rsp+180h+var_120], r13
0x180008e1d  mov     word ptr [rsp+180h+lpSubKey], r13w
0x180008e23  mov     rcx, [rsp+180h+hKey]; hKey
0x180008e28  test    rcx, rcx
0x180008e2b  jz      short loc_180008E33
0x180008e2d  call    cs:__imp_RegCloseKey
0x180008e33  xor     eax, eax
0x180008e35  mov     rcx, [rbp+80h+var_50]
0x180008e39  xor     rcx, rsp; StackCookie
0x180008e3c  call    __security_check_cookie
0x180008e41  add     rsp, 148h
0x180008e48  pop     r15
0x180008e4a  pop     r14
0x180008e4c  pop     r13
0x180008e4e  pop     r12
0x180008e50  pop     rdi
0x180008e51  pop     rsi
0x180008e52  pop     rbx
0x180008e53  pop     rbp
0x180008e54  retn
```
