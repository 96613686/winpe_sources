# CMediaServerFolder::_GetAbsoluteFriendlyName(_ITEMID_CHILD const *,ushort * *)

- ea: `0x180020150`
- end: `0x180020221`
- name: `?_GetAbsoluteFriendlyName@CMediaServerFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAPEAG@Z`
- size: `209`
- prototype: `int(CMediaServerFolder *__hidden this, const struct _ITEMID_CHILD *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180020400`

## callees

- `0x18000ab48`
- `0x18000dd80`
- `0x180011930`
- `0x180020150`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHGetNameFromIDList` at `0x180020191`
- `api-ms-win-shell-namespace-l1-1-0!SHGetNameFromIDList` at `0x180020191`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800201d4`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800201d4`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800201e8`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800201e8`

## pseudocode

```c
__int64 __fastcall CMediaServerFolder::_GetAbsoluteFriendlyName(
        CMediaServerFolder *this,
        const struct _ITEMID_CHILD *a2,
        unsigned __int16 **a3)
{
  const ITEMIDLIST *v4; // rcx
  CMediaServerFolder *v6; // rcx
  HRESULT String; // ebx
  PCWSTR pszMore; // [rsp+20h] [rbp-448h] BYREF
  PWSTR ppszName; // [rsp+28h] [rbp-440h] BYREF
  WCHAR pszPathOut[520]; // [rsp+30h] [rbp-438h] BYREF

  *a3 = 0;
  v4 = (const ITEMIDLIST *)*((_QWORD *)this + 14);
  ppszName = 0;
  String = SHGetNameFromIDList(v4, SIGDN_DESKTOPABSOLUTEEDITING, &ppszName);
  if ( String >= 0 )
  {
    pszMore = 0;
    String = CMediaServerFolder::_GetString(v6, a2, &PKEY_DeviceDisplay_FriendlyName, (unsigned __int16 **)&pszMore);
    if ( String >= 0 )
    {
      String = PathCchCombine(pszPathOut, 0x208u, ppszName, pszMore);
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
0x180020150  push    rbx
0x180020152  push    rsi
0x180020153  push    rdi
0x180020154  sub     rsp, 450h
0x18002015b  mov     rax, cs:__security_cookie
0x180020162  xor     rax, rsp
0x180020165  mov     [rsp+468h+var_28], rax
0x18002016d  mov     qword ptr [r8], 0
0x180020174  mov     rdi, r8
0x180020177  mov     rcx, [rcx+70h]; pidl
0x18002017b  lea     r8, [rsp+468h+ppszName]; ppszName
0x180020180  mov     rsi, rdx
0x180020183  mov     [rsp+468h+ppszName], 0
0x18002018c  mov     edx, 8004C000h; sigdnName
0x180020191  call    cs:__imp_SHGetNameFromIDList
0x180020197  mov     ebx, eax
0x180020199  test    eax, eax
0x18002019b  js      short loc_1800201FA
0x18002019d  lea     r9, [rsp+468h+pszMore]; unsigned __int16 **
0x1800201a2  mov     [rsp+468h+pszMore], 0
0x1800201ab  lea     r8, PKEY_DeviceDisplay_FriendlyName; struct _tagpropertykey *
0x1800201b2  mov     rdx, rsi; struct _ITEMID_CHILD *
0x1800201b5  call    ?_GetString@CMediaServerFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CMediaServerFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x1800201ba  mov     ebx, eax
0x1800201bc  test    eax, eax
0x1800201be  js      short loc_1800201F0
0x1800201c0  mov     r9, [rsp+468h+pszMore]; pszMore
0x1800201c5  lea     rcx, [rsp+468h+pszPathOut]; pszPathOut
0x1800201ca  mov     r8, [rsp+468h+ppszName]; pszPathIn
0x1800201cf  mov     edx, 208h; cchPathOut
0x1800201d4  call    cs:__imp_PathCchCombine
0x1800201da  mov     ebx, eax
0x1800201dc  test    eax, eax
0x1800201de  js      short loc_1800201F0
0x1800201e0  mov     rdx, rdi; ppwsz
0x1800201e3  lea     rcx, [rsp+468h+pszPathOut]; psz
0x1800201e8  call    cs:__imp_SHStrDupW
0x1800201ee  mov     ebx, eax
0x1800201f0  lea     rcx, [rsp+468h+pszMore]
0x1800201f5  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800201fa  lea     rcx, [rsp+468h+ppszName]
0x1800201ff  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180020204  mov     eax, ebx
0x180020206  mov     rcx, [rsp+468h+var_28]
0x18002020e  xor     rcx, rsp; StackCookie
0x180020211  call    __security_check_cookie
0x180020216  add     rsp, 450h
0x18002021d  pop     rdi
0x18002021e  pop     rsi
0x18002021f  pop     rbx
0x180020220  retn
```
