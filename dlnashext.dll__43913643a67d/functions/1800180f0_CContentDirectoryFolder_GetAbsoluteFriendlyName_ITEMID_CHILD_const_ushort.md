# CContentDirectoryFolder::_GetAbsoluteFriendlyName(_ITEMID_CHILD const *,ushort * *)

- ea: `0x1800180f0`
- end: `0x1800181d4`
- name: `?_GetAbsoluteFriendlyName@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAPEAG@Z`
- size: `228`
- prototype: `__int64 __fastcall(CContentDirectoryFolder *__hidden this, const struct _ITEMID_CHILD *, LPWSTR *ppwsz)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800164d0`

## callees

- `0x1800082b4`
- `0x18000ab48`
- `0x180011930`
- `0x1800180f0`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHGetNameFromIDList` at `0x180018138`
- `api-ms-win-shell-namespace-l1-1-0!SHGetNameFromIDList` at `0x180018138`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001817e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001817e`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180018192`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180018192`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentDirectoryFolder::_GetAbsoluteFriendlyName(
        LPCITEMIDLIST *this,
        const struct _ITEMID_CHILD *a2,
        LPWSTR *ppwsz)
{
  HRESULT String; // ebx
  PCWSTR pszMore; // [rsp+20h] [rbp-448h] BYREF
  PWSTR ppszName; // [rsp+28h] [rbp-440h] BYREF
  WCHAR pszPathOut[520]; // [rsp+30h] [rbp-438h] BYREF

  *ppwsz = 0;
  ppszName = 0;
  String = SHGetNameFromIDList(this[11], SIGDN_DESKTOPABSOLUTEEDITING, &ppszName);
  if ( String >= 0 )
  {
    pszMore = 0;
    String = CContentDirectoryFolder::_GetString(
               (CContentDirectoryFolder *)this,
               a2,
               &PKEY_ItemName,
               (unsigned __int16 **)&pszMore);
    if ( String >= 0 )
    {
      String = PathCchCombine(pszPathOut, 0x208u, ppszName, pszMore);
      if ( String >= 0 )
        String = SHStrDupW(pszPathOut, ppwsz);
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pszMore);
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppszName);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800180f0  mov     [rsp+arg_18], rbx
0x1800180f5  push    rbp
0x1800180f6  push    rsi
0x1800180f7  push    rdi
0x1800180f8  sub     rsp, 450h
0x1800180ff  mov     rax, cs:__security_cookie
0x180018106  xor     rax, rsp
0x180018109  mov     [rsp+468h+var_28], rax
0x180018111  mov     rdi, r8
0x180018114  mov     rbp, rdx
0x180018117  mov     rsi, rcx
0x18001811a  mov     qword ptr [r8], 0
0x180018121  mov     [rsp+468h+ppszName], 0
0x18001812a  lea     r8, [rsp+468h+ppszName]; ppszName
0x18001812f  mov     edx, 8004C000h; sigdnName
0x180018134  mov     rcx, [rcx+58h]; pidl
0x180018138  call    cs:__imp_SHGetNameFromIDList
0x18001813e  mov     ebx, eax
0x180018140  test    eax, eax
0x180018142  js      short loc_1800181A5
0x180018144  mov     [rsp+468h+pszMore], 0
0x18001814d  lea     r9, [rsp+468h+pszMore]; unsigned __int16 **
0x180018152  lea     r8, PKEY_ItemName; struct _tagpropertykey *
0x180018159  mov     rdx, rbp; struct _ITEMID_CHILD *
0x18001815c  mov     rcx, rsi; this
0x18001815f  call    ?_GetString@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CContentDirectoryFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x180018164  mov     ebx, eax
0x180018166  test    eax, eax
0x180018168  js      short loc_18001819A
0x18001816a  mov     r9, [rsp+468h+pszMore]; pszMore
0x18001816f  mov     r8, [rsp+468h+ppszName]; pszPathIn
0x180018174  mov     edx, 208h; cchPathOut
0x180018179  lea     rcx, [rsp+468h+pszPathOut]; pszPathOut
0x18001817e  call    cs:__imp_PathCchCombine
0x180018184  mov     ebx, eax
0x180018186  test    eax, eax
0x180018188  js      short loc_18001819A
0x18001818a  mov     rdx, rdi; ppwsz
0x18001818d  lea     rcx, [rsp+468h+pszPathOut]; psz
0x180018192  call    cs:__imp_SHStrDupW
0x180018198  mov     ebx, eax
0x18001819a  lea     rcx, [rsp+468h+pszMore]
0x18001819f  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800181a4  nop
0x1800181a5  lea     rcx, [rsp+468h+ppszName]
0x1800181aa  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800181af  mov     eax, ebx
0x1800181b1  mov     rcx, [rsp+468h+var_28]
0x1800181b9  xor     rcx, rsp; StackCookie
0x1800181bc  call    __security_check_cookie
0x1800181c1  mov     rbx, [rsp+468h+arg_18]
0x1800181c9  add     rsp, 450h
0x1800181d0  pop     rdi
0x1800181d1  pop     rsi
0x1800181d2  pop     rbp
0x1800181d3  retn
```
