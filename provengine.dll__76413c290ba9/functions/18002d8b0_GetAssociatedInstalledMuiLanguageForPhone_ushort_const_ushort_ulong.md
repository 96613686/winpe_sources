# GetAssociatedInstalledMuiLanguageForPhone(ushort const *,ushort *,ulong)

- ea: `0x18002d8b0`
- end: `0x18002db37`
- name: `?GetAssociatedInstalledMuiLanguageForPhone@@YAJPEBGPEAGK@Z`
- size: `647`
- prototype: `__int64 __fastcall(PCWSTR sourceString, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002ef84`

## callees

- `0x1800098dc`
- `0x18000a0f8`
- `0x18002d8b0`
- `0x18004371a`
- `0x180043750`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d9ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d9ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d955`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d99c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dad4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dae8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d955`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d99c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dad4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dae8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d948`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d948`
- `api-ms-win-core-localization-l1-2-0!GetUILanguageInfo` at `0x18002da9b`
- `api-ms-win-core-localization-l1-2-0!GetUILanguageInfo` at `0x18002da9b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d9cf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d9fb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d9cf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d9fb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d933`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d933`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x18002d96a`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x18002d96a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetAssociatedInstalledMuiLanguageForPhone(PCWSTR sourceString, unsigned __int16 *a2)
{
  __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  int MuiForm; // ebx
  __int64 v7; // rdx
  const WCHAR *StringRawBuffer; // rbx
  WCHAR *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  const WCHAR *v12; // r8
  WCHAR *v13; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  HSTRING v16; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pAttributes; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pwmszLanguage[88]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  if ( !sourceString )
  {
    v4 = 457;
LABEL_38:
    MuiForm = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    return (unsigned int)MuiForm;
  }
  if ( !*sourceString )
  {
    v4 = 458;
    goto LABEL_38;
  }
  if ( !a2 )
  {
    v4 = 459;
    goto LABEL_38;
  }
  v5 = -1;
  do
    ++v5;
  while ( sourceString[v5] );
  if ( v5 > 0xFFFFFFFF )
  {
    LODWORD(v5) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(sourceString, v5, &hstringHeader, &string);
  WindowsDeleteString(0);
  v16 = 0;
  MuiForm = Bcp47GetMuiForm(string, &v16);
  if ( MuiForm < 0 )
  {
    v7 = 467;
    goto LABEL_12;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v16, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"zh-HK", -1, 1) != 2 )
  {
    if ( CompareStringOrdinal(StringRawBuffer, -1, L"bn-IN", -1, 1) == 2 )
    {
      StringRawBuffer = L"bn-BD";
    }
    else if ( !StringRawBuffer )
    {
      goto LABEL_34;
    }
    if ( *StringRawBuffer )
      goto LABEL_20;
LABEL_34:
    if ( v16 )
      WindowsDeleteString(v16);
    return 2147943569LL;
  }
  StringRawBuffer = L"zh-TW";
LABEL_20:
  pAttributes = 0;
  memset_0(pwmszLanguage, 0, 0xAAu);
  v9 = pwmszLanguage;
  v10 = 85;
  v11 = 2147483646;
  v12 = StringRawBuffer;
  do
  {
    if ( !v11 )
      break;
    if ( !*v12 )
      break;
    *v9++ = *v12++;
    --v11;
    --v10;
  }
  while ( v10 );
  v13 = v9 - 1;
  if ( v10 )
    v13 = v9;
  *v13 = 0;
  if ( !v10 || !GetUILanguageInfo(8u, pwmszLanguage, 0, 0, &pAttributes) || (pAttributes & 0x20) == 0 )
    goto LABEL_34;
  MuiForm = StringCchCopyW(a2, 0x55u, StringRawBuffer);
  if ( MuiForm < 0 )
  {
    v7 = 502;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)(unsigned int)MuiForm,
      bIgnoreCase);
    if ( v16 )
      WindowsDeleteString(v16);
    return (unsigned int)MuiForm;
  }
  if ( v16 )
    WindowsDeleteString(v16);
  return 0;
}

```

## disassembly

```asm
0x18002d8b0  mov     [rsp-8+arg_10], rbx
0x18002d8b5  push    rbp
0x18002d8b6  push    rsi
0x18002d8b7  push    rdi
0x18002d8b8  push    r14
0x18002d8ba  push    r15
0x18002d8bc  lea     rbp, [rsp-20h]
0x18002d8c1  sub     rsp, 120h
0x18002d8c8  mov     rax, cs:__security_cookie
0x18002d8cf  xor     rax, rsp
0x18002d8d2  mov     [rbp+40h+var_30], rax
0x18002d8d6  xor     r14d, r14d
0x18002d8d9  mov     rsi, rdx
0x18002d8dc  mov     rdi, rcx
0x18002d8df  test    rcx, rcx
0x18002d8e2  jnz     short loc_18002D8EE
0x18002d8e4  mov     edx, 1C9h
0x18002d8e9  jmp     loc_18002DAFA
0x18002d8ee  cmp     [rcx], r14w
0x18002d8f2  jz      loc_18002DAF5
0x18002d8f8  test    rsi, rsi
0x18002d8fb  jnz     short loc_18002D907
0x18002d8fd  mov     edx, 1CBh
0x18002d902  jmp     loc_18002DAFA
0x18002d907  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002d90b  mov     rbx, r15
0x18002d90e  inc     rbx
0x18002d911  cmp     [rcx+rbx*2], r14w
0x18002d916  jnz     short loc_18002D90E
0x18002d918  mov     eax, 0FFFFFFFFh
0x18002d91d  cmp     rbx, rax
0x18002d920  jbe     short loc_18002D939
0x18002d922  xor     r9d, r9d; lpArguments
0x18002d925  xor     r8d, r8d; nNumberOfArguments
0x18002d928  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002d92d  mov     ebx, eax
0x18002d92f  lea     edx, [r9+1]; dwExceptionFlags
0x18002d933  call    cs:__imp_RaiseException
0x18002d939  lea     r9, [rsp+140h+string]; string
0x18002d93e  mov     edx, ebx; length
0x18002d940  lea     r8, [rsp+140h+hstringHeader]; hstringHeader
0x18002d945  mov     rcx, rdi; sourceString
0x18002d948  call    cs:__imp_WindowsCreateStringReference
0x18002d94e  xor     ecx, ecx; string
0x18002d950  mov     [rsp+140h+var_110], r14
0x18002d955  call    cs:__imp_WindowsDeleteString
0x18002d95b  mov     rcx, [rsp+140h+string]
0x18002d960  lea     rdx, [rsp+140h+var_110]
0x18002d965  mov     [rsp+140h+var_110], r14
0x18002d96a  call    cs:__imp_Bcp47GetMuiForm
0x18002d970  mov     ebx, eax
0x18002d972  test    eax, eax
0x18002d974  jns     short loc_18002D9A7
0x18002d976  mov     edx, 1D3h; void *
0x18002d97b  mov     rcx, [rbp+48h]; this
0x18002d97f  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002d986  mov     r9d, ebx; char *
0x18002d989  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d98e  mov     rcx, [rsp+140h+var_110]; string
0x18002d993  test    rcx, rcx
0x18002d996  jz      loc_18002DB12
0x18002d99c  call    cs:__imp_WindowsDeleteString
0x18002d9a2  jmp     loc_18002DB12
0x18002d9a7  mov     rcx, [rsp+140h+var_110]; string
0x18002d9ac  xor     edx, edx; length
0x18002d9ae  call    cs:__imp_WindowsGetStringRawBuffer
0x18002d9b4  mov     r9d, r15d; cchCount2
0x18002d9b7  mov     [rsp+140h+bIgnoreCase], 1; bIgnoreCase
0x18002d9bf  mov     rcx, rax; lpString1
0x18002d9c2  lea     r8, aZhHk; "zh-HK"
0x18002d9c9  mov     edx, r15d; cchCount1
0x18002d9cc  mov     rbx, rax
0x18002d9cf  call    cs:__imp_CompareStringOrdinal
0x18002d9d5  cmp     eax, 2
0x18002d9d8  jnz     short loc_18002D9E3
0x18002d9da  lea     rbx, aZhTw; "zh-TW"
0x18002d9e1  jmp     short loc_18002DA22
0x18002d9e3  mov     r9d, r15d; cchCount2
0x18002d9e6  mov     [rsp+140h+bIgnoreCase], 1; bIgnoreCase
0x18002d9ee  lea     r8, aBnIn; "bn-IN"
0x18002d9f5  mov     edx, r15d; cchCount1
0x18002d9f8  mov     rcx, rbx; lpString1
0x18002d9fb  call    cs:__imp_CompareStringOrdinal
0x18002da01  cmp     eax, 2
0x18002da04  jnz     short loc_18002DA0F
0x18002da06  lea     rbx, aBnBd; "bn-BD"
0x18002da0d  jmp     short loc_18002DA18
0x18002da0f  test    rbx, rbx
0x18002da12  jz      loc_18002DADE
0x18002da18  cmp     [rbx], r14w
0x18002da1c  jz      loc_18002DADE
0x18002da22  xor     edx, edx; Val
0x18002da24  mov     [rsp+140h+pAttributes], r14d
0x18002da29  mov     r8d, 0AAh; Size
0x18002da2f  lea     rcx, [rsp+140h+pwmszLanguage]; void *
0x18002da34  call    memset_0
0x18002da39  mov     edi, 55h ; 'U'
0x18002da3e  lea     rax, [rsp+140h+pwmszLanguage]
0x18002da43  mov     edx, edi
0x18002da45  mov     ecx, 7FFFFFFEh
0x18002da4a  mov     r8, rbx
0x18002da4d  test    rcx, rcx
0x18002da50  jz      short loc_18002DA71
0x18002da52  movzx   r9d, word ptr [r8]
0x18002da56  test    r9w, r9w
0x18002da5a  jz      short loc_18002DA71
0x18002da5c  mov     [rax], r9w
0x18002da60  add     r8, 2
0x18002da64  add     rax, 2
0x18002da68  dec     rcx
0x18002da6b  sub     rdx, 1
0x18002da6f  jnz     short loc_18002DA4D
0x18002da71  test    rdx, rdx
0x18002da74  lea     rcx, [rax-2]
0x18002da78  cmovnz  rcx, rax
0x18002da7c  mov     [rcx], r14w
0x18002da80  jz      short loc_18002DADE
0x18002da82  xor     r9d, r9d; pcchFallbackLanguages
0x18002da85  lea     rax, [rsp+140h+pAttributes]
0x18002da8a  xor     r8d, r8d; pwszFallbackLanguages
0x18002da8d  mov     qword ptr [rsp+140h+bIgnoreCase], rax; pAttributes
0x18002da92  lea     rdx, [rsp+140h+pwmszLanguage]; pwmszLanguage
0x18002da97  lea     ecx, [r9+8]; dwFlags
0x18002da9b  call    cs:__imp_GetUILanguageInfo
0x18002daa1  test    eax, eax
0x18002daa3  jz      short loc_18002DADE
0x18002daa5  test    byte ptr [rsp+140h+pAttributes], 20h
0x18002daaa  jz      short loc_18002DADE
0x18002daac  mov     r8, rbx; unsigned __int16 *
0x18002daaf  mov     rdx, rdi; unsigned __int64
0x18002dab2  mov     rcx, rsi; unsigned __int16 *
0x18002dab5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002daba  mov     ebx, eax
0x18002dabc  test    eax, eax
0x18002dabe  jns     short loc_18002DACA
0x18002dac0  mov     edx, 1F6h
0x18002dac5  jmp     loc_18002D97B
0x18002daca  mov     rcx, [rsp+140h+var_110]; string
0x18002dacf  test    rcx, rcx
0x18002dad2  jz      short loc_18002DADA
0x18002dad4  call    cs:__imp_WindowsDeleteString
0x18002dada  xor     eax, eax
0x18002dadc  jmp     short loc_18002DB14
0x18002dade  mov     rcx, [rsp+140h+var_110]; string
0x18002dae3  test    rcx, rcx
0x18002dae6  jz      short loc_18002DAEE
0x18002dae8  call    cs:__imp_WindowsDeleteString
0x18002daee  mov     eax, 80070491h
0x18002daf3  jmp     short loc_18002DB14
0x18002daf5  mov     edx, 1CAh; void *
0x18002dafa  mov     rcx, [rbp+48h]; this
0x18002dafe  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002db05  mov     ebx, 80070057h
0x18002db0a  mov     r9d, ebx; char *
0x18002db0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002db12  mov     eax, ebx
0x18002db14  mov     rcx, [rbp+40h+var_30]
0x18002db18  xor     rcx, rsp; StackCookie
0x18002db1b  call    __security_check_cookie
0x18002db20  mov     rbx, [rsp+140h+arg_10]
0x18002db28  add     rsp, 120h
0x18002db2f  pop     r15
0x18002db31  pop     r14
0x18002db33  pop     rdi
0x18002db34  pop     rsi
0x18002db35  pop     rbp
0x18002db36  retn
```
