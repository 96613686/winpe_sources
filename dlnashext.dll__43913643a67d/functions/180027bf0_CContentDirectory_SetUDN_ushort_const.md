# CContentDirectory::SetUDN(ushort const *)

- ea: `0x180027bf0`
- end: `0x180027d03`
- name: `?SetUDN@CContentDirectory@@UEAAJPEBG@Z`
- size: `275`
- prototype: `int(CContentDirectory *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000bb48`
- `0x18000bc18`
- `0x18000bca4`
- `0x180011930`
- `0x1800125c4`
- `0x180017650`
- `0x1800197c0`
- `0x180027bf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027cc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027cc9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180027c45`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180027c79`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180027c45`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180027c79`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180027cd8`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180027cd8`

## pseudocode

```c
HRESULT __fastcall CContentDirectory::SetUDN(LPVOID *this, const unsigned __int16 *a2)
{
  HRESULT result; // eax
  unsigned __int64 v5; // rax
  WCHAR psz[304]; // [rsp+20h] [rbp-278h] BYREF

  if ( !a2 )
    return -2147467261;
  memset_0(psz, 0, 0x258u);
  if ( StrStrIW(a2, L"uuid:") )
  {
    result = StringCchCopyW(psz, 0x12Cu, a2);
  }
  else
  {
    result = StringCchPrintfW(psz, 0x12Cu, L"uuid:%s", a2);
    if ( result < 0 )
      return result;
    if ( StrStrIW(a2, L"{") )
    {
      v5 = wcslen2(a2);
      result = StringCchCatNW(psz, 0x12Cu, a2 + 1, v5 - 1);
    }
    else
    {
      result = StringCchCatW(psz, 0x12Cu, a2);
    }
  }
  if ( result >= 0 )
  {
    CoTaskMemFree(this[1]);
    return SHStrDupW(psz, (LPWSTR *)this + 1);
  }
  return result;
}

```

## disassembly

```asm
0x180027bf0  mov     [rsp+arg_10], rbx
0x180027bf5  mov     [rsp+arg_18], rsi
0x180027bfa  push    rdi
0x180027bfb  sub     rsp, 290h
0x180027c02  mov     rax, cs:__security_cookie
0x180027c09  xor     rax, rsp
0x180027c0c  mov     [rsp+298h+var_18], rax
0x180027c14  mov     rbx, rdx
0x180027c17  mov     rsi, rcx
0x180027c1a  test    rdx, rdx
0x180027c1d  jnz     short loc_180027C29
0x180027c1f  mov     eax, 80004003h
0x180027c24  jmp     loc_180027CDE
0x180027c29  xor     edx, edx; Val
0x180027c2b  lea     rcx, [rsp+298h+psz]; void *
0x180027c30  mov     r8d, 258h; Size
0x180027c36  call    memset_0
0x180027c3b  lea     rdx, aUuid; "uuid:"
0x180027c42  mov     rcx, rbx; pszFirst
0x180027c45  call    cs:__imp_StrStrIW
0x180027c4b  lea     rcx, [rsp+298h+psz]; unsigned __int16 *
0x180027c50  test    rax, rax
0x180027c53  jnz     short loc_180027CB4
0x180027c55  mov     edi, 12Ch
0x180027c5a  lea     r8, aUuidS; "uuid:%s"
0x180027c61  mov     edx, edi; unsigned __int64
0x180027c63  mov     r9, rbx
0x180027c66  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027c6b  test    eax, eax
0x180027c6d  js      short loc_180027CDE
0x180027c6f  lea     rdx, asc_18003C670; "{"
0x180027c76  mov     rcx, rbx; pszFirst
0x180027c79  call    cs:__imp_StrStrIW
0x180027c7f  test    rax, rax
0x180027c82  jz      short loc_180027CA2
0x180027c84  mov     rcx, rbx; unsigned __int16 *
0x180027c87  call    ?wcslen2@@YA_KPEBG@Z; wcslen2(ushort const *)
0x180027c8c  lea     r8, [rbx+2]; unsigned __int16 *
0x180027c90  mov     edx, edi; unsigned __int64
0x180027c92  lea     rcx, [rsp+298h+psz]; unsigned __int16 *
0x180027c97  lea     r9, [rax-1]; unsigned __int64
0x180027c9b  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180027ca0  jmp     short loc_180027CC1
0x180027ca2  mov     r8, rbx; unsigned __int16 *
0x180027ca5  lea     rcx, [rsp+298h+psz]; unsigned __int16 *
0x180027caa  mov     rdx, rdi; unsigned __int64
0x180027cad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180027cb2  jmp     short loc_180027CC1
0x180027cb4  mov     r8, rbx; unsigned __int16 *
0x180027cb7  mov     edx, 12Ch; unsigned __int64
0x180027cbc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027cc1  test    eax, eax
0x180027cc3  js      short loc_180027CDE
0x180027cc5  mov     rcx, [rsi+8]; pv
0x180027cc9  call    cs:__imp_CoTaskMemFree
0x180027ccf  lea     rdx, [rsi+8]; ppwsz
0x180027cd3  lea     rcx, [rsp+298h+psz]; psz
0x180027cd8  call    cs:__imp_SHStrDupW
0x180027cde  mov     rcx, [rsp+298h+var_18]
0x180027ce6  xor     rcx, rsp; StackCookie
0x180027ce9  call    __security_check_cookie
0x180027cee  lea     r11, [rsp+298h+var_8]
0x180027cf6  mov     rbx, [r11+20h]
0x180027cfa  mov     rsi, [r11+28h]
0x180027cfe  mov     rsp, r11
0x180027d01  pop     rdi
0x180027d02  retn
```
