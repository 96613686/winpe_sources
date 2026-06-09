# PiiSafeShellitemParsingNameHelpers::GetDriveTypeFromPath(ushort const *)

- ea: `0x180043bf8`
- end: `0x180043cb7`
- name: `?GetDriveTypeFromPath@PiiSafeShellitemParsingNameHelpers@@YAIPEBG@Z`
- size: `191`
- prototype: `unsigned int __fastcall(PiiSafeShellitemParsingNameHelpers *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x180043b40`

## callees

- `0x180013220`
- `0x1800254e0`
- `0x180026394`
- `0x180043bf8`
- `0x1800514a8`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180043c7d`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180043c7d`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180043c88`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180043c88`
- `SHLWAPI!PathStripToRootW` at `0x180043c5c`
- `SHLWAPI!PathStripToRootW` at `0x180043c5c`

## pseudocode

```c
__int64 __fastcall PiiSafeShellitemParsingNameHelpers::GetDriveTypeFromPath(
        PiiSafeShellitemParsingNameHelpers *this,
        const unsigned __int16 *a2)
{
  unsigned int v3; // edi
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  v3 = 0;
  if ( this )
  {
    if ( *(_WORD *)this )
    {
      memset_0(pszPath, 0, 0x208u);
      if ( (int)StringCchCopyW(pszPath, 0x104u, (const unsigned __int16 *)this) >= 0 )
      {
        if ( PathStripToRootW(pszPath) )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60851339>::GetImpl'::`2'::impl) )
            PathCchAddBackslash(pszPath, 0x104u);
          return GetDriveTypeW(pszPath);
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180043bf8  mov     [rsp+arg_8], rbx
0x180043bfd  mov     [rsp+arg_10], rsi
0x180043c02  push    rdi
0x180043c03  sub     rsp, 240h
0x180043c0a  mov     rax, cs:__security_cookie
0x180043c11  xor     rax, rsp
0x180043c14  mov     [rsp+248h+var_18], rax
0x180043c1c  xor     esi, esi
0x180043c1e  mov     rbx, rcx
0x180043c21  mov     edi, esi
0x180043c23  test    rcx, rcx
0x180043c26  jz      short loc_180043C90
0x180043c28  cmp     [rcx], si
0x180043c2b  jz      short loc_180043C90
0x180043c2d  xor     edx, edx; Val
0x180043c2f  lea     rcx, [rsp+248h+pszPath]; void *
0x180043c34  mov     r8d, 208h; Size
0x180043c3a  call    memset_0
0x180043c3f  mov     r8, rbx; unsigned __int16 *
0x180043c42  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x180043c47  mov     ebx, 104h
0x180043c4c  mov     edx, ebx; unsigned __int64
0x180043c4e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180043c53  test    eax, eax
0x180043c55  js      short loc_180043C90
0x180043c57  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180043c5c  call    cs:__imp_PathStripToRootW
0x180043c62  test    eax, eax
0x180043c64  jz      short loc_180043C90
0x180043c66  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60851339@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339> `wil::Feature<__WilFeatureTraits_Feature_60851339>::GetImpl(void)'::`2'::impl
0x180043c6d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339>::__private_IsEnabled(void)
0x180043c72  test    al, al
0x180043c74  jz      short loc_180043C83
0x180043c76  mov     edx, ebx; cchPath
0x180043c78  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180043c7d  call    cs:__imp_PathCchAddBackslash
0x180043c83  lea     rcx, [rsp+248h+pszPath]; lpRootPathName
0x180043c88  call    cs:__imp_GetDriveTypeW
0x180043c8e  mov     edi, eax
0x180043c90  mov     eax, edi
0x180043c92  mov     rcx, [rsp+248h+var_18]
0x180043c9a  xor     rcx, rsp; StackCookie
0x180043c9d  call    __security_check_cookie
0x180043ca2  lea     r11, [rsp+248h+var_8]
0x180043caa  mov     rbx, [r11+18h]
0x180043cae  mov     rsi, [r11+20h]
0x180043cb2  mov     rsp, r11
0x180043cb5  pop     rdi
0x180043cb6  retn
```
