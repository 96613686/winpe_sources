# CMediaServerFolder::_GetAbsoluteParsingName(_ITEMID_CHILD const *,ushort * *)

- ea: `0x180020228`
- end: `0x1800202f2`
- name: `?_GetAbsoluteParsingName@CMediaServerFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAPEAG@Z`
- size: `202`
- prototype: `int(CMediaServerFolder *__hidden this, const struct _ITEMID_CHILD *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180020410`

## callees

- `0x18000ab48`
- `0x18000dd80`
- `0x180011930`
- `0x180020228`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHGetNameFromIDList` at `0x180020262`
- `api-ms-win-shell-namespace-l1-1-0!SHGetNameFromIDList` at `0x180020262`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800202a5`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800202a5`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800202b9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800202b9`

## pseudocode

```c
__int64 __fastcall CMediaServerFolder::_GetAbsoluteParsingName(
        CMediaServerFolder *this,
        const struct _ITEMID_CHILD *a2,
        unsigned __int16 **a3)
{
  const ITEMIDLIST *v3; // rcx
  CMediaServerFolder *v6; // rcx
  HRESULT String; // ebx
  PCWSTR pszMore; // [rsp+20h] [rbp-248h] BYREF
  PWSTR ppszName; // [rsp+28h] [rbp-240h] BYREF
  WCHAR pszPathOut[264]; // [rsp+30h] [rbp-238h] BYREF

  v3 = (const ITEMIDLIST *)*((_QWORD *)this + 14);
  ppszName = 0;
  String = SHGetNameFromIDList(v3, SIGDN_DESKTOPABSOLUTEPARSING, &ppszName);
  if ( String >= 0 )
  {
    pszMore = 0;
    String = CMediaServerFolder::_GetString(v6, a2, &PKEY_ParsingName, (unsigned __int16 **)&pszMore);
    if ( String >= 0 )
    {
      String = PathCchCombine(pszPathOut, 0x104u, ppszName, pszMore);
      if ( String >= 0 )
        String = SHStrDupW(pszPathOut, a3);
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pszMore);
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppszName);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180020228  push    rbx
0x18002022a  push    rsi
0x18002022b  push    rdi
0x18002022c  sub     rsp, 250h
0x180020233  mov     rax, cs:__security_cookie
0x18002023a  xor     rax, rsp
0x18002023d  mov     [rsp+268h+var_28], rax
0x180020245  mov     rcx, [rcx+70h]; pidl
0x180020249  mov     rdi, r8
0x18002024c  mov     rsi, rdx
0x18002024f  mov     [rsp+268h+ppszName], 0
0x180020258  lea     r8, [rsp+268h+ppszName]; ppszName
0x18002025d  mov     edx, 80028000h; sigdnName
0x180020262  call    cs:__imp_SHGetNameFromIDList
0x180020268  mov     ebx, eax
0x18002026a  test    eax, eax
0x18002026c  js      short loc_1800202CB
0x18002026e  lea     r9, [rsp+268h+pszMore]; unsigned __int16 **
0x180020273  mov     [rsp+268h+pszMore], 0
0x18002027c  lea     r8, PKEY_ParsingName; struct _tagpropertykey *
0x180020283  mov     rdx, rsi; struct _ITEMID_CHILD *
0x180020286  call    ?_GetString@CMediaServerFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CMediaServerFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x18002028b  mov     ebx, eax
0x18002028d  test    eax, eax
0x18002028f  js      short loc_1800202C1
0x180020291  mov     r9, [rsp+268h+pszMore]; pszMore
0x180020296  lea     rcx, [rsp+268h+pszPathOut]; pszPathOut
0x18002029b  mov     r8, [rsp+268h+ppszName]; pszPathIn
0x1800202a0  mov     edx, 104h; cchPathOut
0x1800202a5  call    cs:__imp_PathCchCombine
0x1800202ab  mov     ebx, eax
0x1800202ad  test    eax, eax
0x1800202af  js      short loc_1800202C1
0x1800202b1  mov     rdx, rdi; ppwsz
0x1800202b4  lea     rcx, [rsp+268h+pszPathOut]; psz
0x1800202b9  call    cs:__imp_SHStrDupW
0x1800202bf  mov     ebx, eax
0x1800202c1  lea     rcx, [rsp+268h+pszMore]
0x1800202c6  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800202cb  lea     rcx, [rsp+268h+ppszName]
0x1800202d0  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800202d5  mov     eax, ebx
0x1800202d7  mov     rcx, [rsp+268h+var_28]
0x1800202df  xor     rcx, rsp; StackCookie
0x1800202e2  call    __security_check_cookie
0x1800202e7  add     rsp, 250h
0x1800202ee  pop     rdi
0x1800202ef  pop     rsi
0x1800202f0  pop     rbx
0x1800202f1  retn
```
