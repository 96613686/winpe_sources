# CActiveUrl::IsUrlBlocked(ushort const *,int)

- ea: `0x180035af0`
- end: `0x180035cba`
- name: `?IsUrlBlocked@CActiveUrl@@UEAAJPEBGH@Z`
- size: `458`
- prototype: `__int64 __fastcall(CActiveUrl *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800055bc`
- `0x1800227b0`
- `0x180035af0`
- `0x1800cca00`
- `0x1800cca90`

## import_xrefs

- `SHLWAPI!StrCmpNIW` at `0x180035c1f`
- `SHLWAPI!StrCmpNIW` at `0x180035c3b`
- `SHLWAPI!StrCmpNIW` at `0x180035c86`
- `SHLWAPI!StrCmpNIW` at `0x180035c1f`
- `SHLWAPI!StrCmpNIW` at `0x180035c3b`
- `SHLWAPI!StrCmpNIW` at `0x180035c86`
- `KERNEL32!CompareStringW` at `0x180035b8a`
- `KERNEL32!CompareStringW` at `0x180035bb8`
- `KERNEL32!CompareStringW` at `0x180035be7`
- `KERNEL32!CompareStringW` at `0x180035b8a`
- `KERNEL32!CompareStringW` at `0x180035bb8`
- `KERNEL32!CompareStringW` at `0x180035be7`
- `urlmon!CoInternetParseUrl` at `0x180035c6c`
- `urlmon!CoInternetParseUrl` at `0x180035c6c`

## pseudocode

```c
__int64 __fastcall CActiveUrl::IsUrlBlocked(CActiveUrl *this, const unsigned __int16 *a2, int a3)
{
  unsigned int v5; // ebx
  DWORD pcchResult[4]; // [rsp+40h] [rbp-1088h] BYREF
  WCHAR pwzUrl[6]; // [rsp+50h] [rbp-1078h] BYREF
  WCHAR psz2[2082]; // [rsp+5Ch] [rbp-106Ch] BYREF

  pcchResult[0] = 2084;
  v5 = 1;
  if ( (a3 || *((_DWORD *)this + 24) && ((*((_DWORD *)this + 25) - 1) & 0xFFFFFFFD) != 0)
    && a2
    && *a2
    && !(unsigned int)IsMHTMLUrlW(a2)
    && CompareStringW(0x7Fu, 1u, a2, 4, L"cid:", 4) != 2
    && CompareStringW(0x7Fu, 1u, a2, -1, L"about:blank", -1) != 2 )
  {
    if ( CompareStringW(0x7Fu, 1u, a2, 6, L"res://", 6) != 2 || (int)StringCchCopyW(pwzUrl, 0x824u, a2) < 0 )
      goto LABEL_15;
    while ( !StrCmpNIW(L"%%", psz2, 1) || !StrCmpNIW(L"\\%%", psz2, 2) )
      CoInternetParseUrl(pwzUrl, PARSE_ENCODE_IS_UNESCAPE, 0, pwzUrl, 0x824u, pcchResult, 0);
    if ( !StrCmpNIW(L"\\\\", psz2, 2) )
    {
LABEL_15:
      *((_DWORD *)this + 26) = 1;
      return 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180035af0  mov     [rsp+arg_10], rbx
0x180035af5  push    rbp
0x180035af6  push    rsi
0x180035af7  push    rdi
0x180035af8  mov     eax, 10B0h
0x180035afd  call    _alloca_probe
0x180035b02  sub     rsp, rax
0x180035b05  mov     rax, cs:__security_cookie
0x180035b0c  xor     rax, rsp
0x180035b0f  mov     [rsp+10C8h+var_28], rax
0x180035b17  xor     ebp, ebp
0x180035b19  mov     [rsp+10C8h+pcchResult], 824h
0x180035b21  mov     rdi, rdx
0x180035b24  mov     rsi, rcx
0x180035b27  mov     ebx, 1
0x180035b2c  test    r8d, r8d
0x180035b2f  jnz     short loc_180035B4A
0x180035b31  cmp     [rcx+60h], ebp
0x180035b34  jz      loc_180035C95
0x180035b3a  mov     eax, [rcx+64h]
0x180035b3d  sub     eax, ebx
0x180035b3f  test    eax, 0FFFFFFFDh
0x180035b44  jz      loc_180035C95
0x180035b4a  test    rdi, rdi
0x180035b4d  jz      loc_180035C95
0x180035b53  cmp     [rdx], bp
0x180035b56  jz      loc_180035C95
0x180035b5c  mov     rcx, rdi; psz1
0x180035b5f  call    ?IsMHTMLUrlW@@YAHPEBG@Z; IsMHTMLUrlW(ushort const *)
0x180035b64  test    eax, eax
0x180035b66  jnz     loc_180035C95
0x180035b6c  lea     r9d, [rax+4]; cchCount1
0x180035b70  mov     r8, rdi; lpString1
0x180035b73  lea     rax, aCid_0; "cid:"
0x180035b7a  mov     [rsp+10C8h+cchCount2], r9d; cchCount2
0x180035b7f  lea     ecx, [r9+7Bh]; Locale
0x180035b83  mov     [rsp+10C8h+lpString2], rax; lpString2
0x180035b88  mov     edx, ebx; dwCmpFlags
0x180035b8a  call    cs:__imp_CompareStringW
0x180035b90  cmp     eax, 2
0x180035b93  jz      loc_180035C95
0x180035b99  or      r9d, 0FFFFFFFFh; cchCount1
0x180035b9d  lea     rax, aAboutBlank; "about:blank"
0x180035ba4  mov     [rsp+10C8h+cchCount2], r9d; cchCount2
0x180035ba9  mov     r8, rdi; lpString1
0x180035bac  mov     edx, ebx; dwCmpFlags
0x180035bae  mov     [rsp+10C8h+lpString2], rax; lpString2
0x180035bb3  mov     ecx, 7Fh; Locale
0x180035bb8  call    cs:__imp_CompareStringW
0x180035bbe  cmp     eax, 2
0x180035bc1  jz      loc_180035C95
0x180035bc7  mov     r9d, 6; cchCount1
0x180035bcd  lea     rax, aRes; "res://"
0x180035bd4  mov     [rsp+10C8h+cchCount2], r9d; cchCount2
0x180035bd9  mov     r8, rdi; lpString1
0x180035bdc  mov     edx, ebx; dwCmpFlags
0x180035bde  mov     [rsp+10C8h+lpString2], rax; lpString2
0x180035be3  lea     ecx, [r9+79h]; Locale
0x180035be7  call    cs:__imp_CompareStringW
0x180035bed  cmp     eax, 2
0x180035bf0  jnz     loc_180035C90
0x180035bf6  mov     r8, rdi; unsigned __int16 *
0x180035bf9  lea     rcx, [rsp+10C8h+pwzUrl]; unsigned __int16 *
0x180035bfe  mov     edx, 824h; unsigned __int64
0x180035c03  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035c08  test    eax, eax
0x180035c0a  js      loc_180035C90
0x180035c10  mov     r8d, ebx; nChar
0x180035c13  lea     rdx, [rsp+10C8h+psz2]; psz2
0x180035c18  lea     rcx, psz1; "%%"
0x180035c1f  call    cs:__imp_StrCmpNIW
0x180035c25  test    eax, eax
0x180035c27  jz      short loc_180035C45
0x180035c29  mov     r8d, 2; nChar
0x180035c2f  lea     rdx, [rsp+10C8h+psz2]; psz2
0x180035c34  lea     rcx, asc_1800DBC00; "\\%%"
0x180035c3b  call    cs:__imp_StrCmpNIW
0x180035c41  test    eax, eax
0x180035c43  jnz     short loc_180035C74
0x180035c45  xor     r8d, r8d; dwFlags
0x180035c48  mov     [rsp+10C8h+dwReserved], ebp; dwReserved
0x180035c4c  lea     rax, [rsp+10C8h+pcchResult]
0x180035c51  mov     qword ptr [rsp+10C8h+cchCount2], rax; pcchResult
0x180035c56  lea     r9, [rsp+10C8h+pwzUrl]; pszResult
0x180035c5b  lea     rcx, [rsp+10C8h+pwzUrl]; pwzUrl
0x180035c60  mov     dword ptr [rsp+10C8h+lpString2], 824h; cchResult
0x180035c68  lea     edx, [r8+7]; ParseAction
0x180035c6c  call    cs:__imp_CoInternetParseUrl
0x180035c72  jmp     short loc_180035C10
0x180035c74  mov     r8d, 2; nChar
0x180035c7a  lea     rdx, [rsp+10C8h+psz2]; psz2
0x180035c7f  lea     rcx, asc_1800D82C0; "\\\\"
0x180035c86  call    cs:__imp_StrCmpNIW
0x180035c8c  test    eax, eax
0x180035c8e  jnz     short loc_180035C95
0x180035c90  mov     [rsi+68h], ebx
0x180035c93  mov     ebx, ebp
0x180035c95  mov     eax, ebx
0x180035c97  mov     rcx, [rsp+10C8h+var_28]
0x180035c9f  xor     rcx, rsp; StackCookie
0x180035ca2  call    __security_check_cookie
0x180035ca7  mov     rbx, [rsp+10C8h+arg_10]
0x180035caf  add     rsp, 10B0h
0x180035cb6  pop     rdi
0x180035cb7  pop     rsi
0x180035cb8  pop     rbp
0x180035cb9  retn
```
