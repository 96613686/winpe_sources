# NetFontLoader::NormalizeUrl(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18025394c`
- end: `0x180253aa3`
- name: `?NormalizeUrl@NetFontLoader@@SAJPEB_W0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(LPCWSTR lpszBaseUrl, LPCWSTR lpszUrl, LPWSTR lpszBuffer)`
- caller_count: `3`
- callee_count: `2`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180210060`
- `0x1802531b0`
- `0x180253470`

## callees

- `0x180124e28`
- `0x18025394c`

## import_xrefs

- `kernel32!GetLastError` at `0x1802539b6`
- `kernel32!GetLastError` at `0x180253a1e`
- `kernel32!GetLastError` at `0x180253a58`
- `kernel32!GetLastError` at `0x1802539b6`
- `kernel32!GetLastError` at `0x180253a1e`
- `kernel32!GetLastError` at `0x180253a58`
- `WININET!InternetCanonicalizeUrlW` at `0x180253a14`
- `WININET!InternetCanonicalizeUrlW` at `0x180253a4e`
- `WININET!InternetCanonicalizeUrlW` at `0x180253a14`
- `WININET!InternetCanonicalizeUrlW` at `0x180253a4e`
- `WININET!InternetCombineUrlW` at `0x1802539a8`
- `WININET!InternetCombineUrlW` at `0x1802539ef`
- `WININET!InternetCombineUrlW` at `0x1802539a8`
- `WININET!InternetCombineUrlW` at `0x1802539ef`

## pseudocode

```c
__int64 __fastcall NetFontLoader::NormalizeUrl(LPCWSTR lpszBaseUrl, LPCWSTR lpszUrl, LPWSTR lpszBuffer)
{
  LPWSTR v5; // rbx
  _QWORD *v6; // rdi
  WCHAR *v7; // r8
  WCHAR *v8; // r8
  BOOL v9; // eax
  WCHAR *v10; // rdx
  WCHAR *v11; // rdx
  signed int LastError; // eax
  unsigned int v13; // ecx
  DWORD dwBufferLength; // [rsp+50h] [rbp+8h] BYREF

  dwBufferLength = 256;
  v5 = lpszBuffer;
  std::wstring::resize(lpszBuffer, 256);
  if ( lpszBaseUrl && *lpszBaseUrl )
  {
    v6 = v5 + 12;
    if ( *((_QWORD *)v5 + 3) <= 7u )
      v7 = v5;
    else
      v7 = *(WCHAR **)v5;
    if ( InternetCombineUrlW(lpszBaseUrl, lpszUrl, v7, &dwBufferLength, 0) )
      goto LABEL_27;
    if ( GetLastError() == 122 )
    {
      std::wstring::resize(v5, dwBufferLength);
      if ( *v6 <= 7u )
        v8 = v5;
      else
        v8 = *(WCHAR **)v5;
      v9 = InternetCombineUrlW(lpszBaseUrl, lpszUrl, v8, &dwBufferLength, 0);
      goto LABEL_21;
    }
  }
  else
  {
    v6 = v5 + 12;
    if ( *((_QWORD *)v5 + 3) <= 7u )
      v10 = v5;
    else
      v10 = *(WCHAR **)v5;
    if ( InternetCanonicalizeUrlW(lpszUrl, v10, &dwBufferLength, 0) )
      goto LABEL_27;
    if ( GetLastError() == 122 )
    {
      std::wstring::resize(v5, dwBufferLength);
      if ( *v6 <= 7u )
        v11 = v5;
      else
        v11 = *(WCHAR **)v5;
      v9 = InternetCanonicalizeUrlW(lpszUrl, v11, &dwBufferLength, 0);
LABEL_21:
      if ( !v9 )
        goto LABEL_22;
LABEL_27:
      std::wstring::resize(v5, dwBufferLength);
      return 0;
    }
  }
LABEL_22:
  LastError = GetLastError();
  *((_QWORD *)v5 + 2) = 0;
  v13 = LastError;
  if ( *v6 > 7u )
    v5 = *(LPWSTR *)v5;
  *v5 = 0;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v13;
}

```

## disassembly

```asm
0x18025394c  mov     [rsp+arg_8], rbx
0x180253951  mov     [rsp+arg_10], rbp
0x180253956  push    rsi
0x180253957  push    rdi
0x180253958  push    r14
0x18025395a  sub     rsp, 30h
0x18025395e  mov     rbp, rdx
0x180253961  mov     rsi, rcx
0x180253964  mov     edx, 100h
0x180253969  mov     rcx, r8
0x18025396c  mov     [rsp+48h+dwBufferLength], edx
0x180253970  mov     rbx, r8
0x180253973  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180253978  xor     r14d, r14d
0x18025397b  test    rsi, rsi
0x18025397e  jz      short loc_1802539F7
0x180253980  cmp     [rsi], r14w
0x180253984  jz      short loc_1802539F7
0x180253986  lea     rdi, [rbx+18h]
0x18025398a  cmp     qword ptr [rdi], 7
0x18025398e  jbe     short loc_180253995
0x180253990  mov     r8, [rbx]
0x180253993  jmp     short loc_180253998
0x180253995  mov     r8, rbx; lpszBuffer
0x180253998  lea     r9, [rsp+48h+dwBufferLength]; lpdwBufferLength
0x18025399d  mov     [rsp+48h+dwFlags], r14d; dwFlags
0x1802539a2  mov     rdx, rbp; lpszRelativeUrl
0x1802539a5  mov     rcx, rsi; lpszBaseUrl
0x1802539a8  call    cs:__imp_InternetCombineUrlW
0x1802539ae  test    eax, eax
0x1802539b0  jnz     loc_180253A82
0x1802539b6  call    cs:__imp_GetLastError
0x1802539bc  cmp     eax, 7Ah ; 'z'
0x1802539bf  jnz     loc_180253A58
0x1802539c5  mov     edx, [rsp+48h+dwBufferLength]
0x1802539c9  mov     rcx, rbx
0x1802539cc  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1802539d1  cmp     qword ptr [rdi], 7
0x1802539d5  jbe     short loc_1802539DC
0x1802539d7  mov     r8, [rbx]
0x1802539da  jmp     short loc_1802539DF
0x1802539dc  mov     r8, rbx; lpszBuffer
0x1802539df  lea     r9, [rsp+48h+dwBufferLength]; lpdwBufferLength
0x1802539e4  mov     [rsp+48h+dwFlags], r14d; dwFlags
0x1802539e9  mov     rdx, rbp; lpszRelativeUrl
0x1802539ec  mov     rcx, rsi; lpszBaseUrl
0x1802539ef  call    cs:__imp_InternetCombineUrlW
0x1802539f5  jmp     short loc_180253A54
0x1802539f7  lea     rdi, [rbx+18h]
0x1802539fb  cmp     qword ptr [rdi], 7
0x1802539ff  jbe     short loc_180253A06
0x180253a01  mov     rdx, [rbx]
0x180253a04  jmp     short loc_180253A09
0x180253a06  mov     rdx, rbx; lpszBuffer
0x180253a09  xor     r9d, r9d; dwFlags
0x180253a0c  lea     r8, [rsp+48h+dwBufferLength]; lpdwBufferLength
0x180253a11  mov     rcx, rbp; lpszUrl
0x180253a14  call    cs:__imp_InternetCanonicalizeUrlW
0x180253a1a  test    eax, eax
0x180253a1c  jnz     short loc_180253A82
0x180253a1e  call    cs:__imp_GetLastError
0x180253a24  cmp     eax, 7Ah ; 'z'
0x180253a27  jnz     short loc_180253A58
0x180253a29  mov     edx, [rsp+48h+dwBufferLength]
0x180253a2d  mov     rcx, rbx
0x180253a30  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180253a35  cmp     qword ptr [rdi], 7
0x180253a39  jbe     short loc_180253A40
0x180253a3b  mov     rdx, [rbx]
0x180253a3e  jmp     short loc_180253A43
0x180253a40  mov     rdx, rbx; lpszBuffer
0x180253a43  xor     r9d, r9d; dwFlags
0x180253a46  lea     r8, [rsp+48h+dwBufferLength]; lpdwBufferLength
0x180253a4b  mov     rcx, rbp; lpszUrl
0x180253a4e  call    cs:__imp_InternetCanonicalizeUrlW
0x180253a54  test    eax, eax
0x180253a56  jnz     short loc_180253A82
0x180253a58  call    cs:__imp_GetLastError
0x180253a5e  mov     [rbx+10h], r14
0x180253a62  mov     ecx, eax
0x180253a64  cmp     qword ptr [rdi], 7
0x180253a68  jbe     short loc_180253A6D
0x180253a6a  mov     rbx, [rbx]
0x180253a6d  mov     [rbx], r14w
0x180253a71  test    eax, eax
0x180253a73  jle     short loc_180253A7E
0x180253a75  movzx   ecx, ax
0x180253a78  or      ecx, 80070000h
0x180253a7e  mov     eax, ecx
0x180253a80  jmp     short loc_180253A90
0x180253a82  mov     edx, [rsp+48h+dwBufferLength]
0x180253a86  mov     rcx, rbx
0x180253a89  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180253a8e  xor     eax, eax
0x180253a90  mov     rbx, [rsp+48h+arg_8]
0x180253a95  mov     rbp, [rsp+48h+arg_10]
0x180253a9a  add     rsp, 30h
0x180253a9e  pop     r14
0x180253aa0  pop     rdi
0x180253aa1  pop     rsi
0x180253aa2  retn
```
