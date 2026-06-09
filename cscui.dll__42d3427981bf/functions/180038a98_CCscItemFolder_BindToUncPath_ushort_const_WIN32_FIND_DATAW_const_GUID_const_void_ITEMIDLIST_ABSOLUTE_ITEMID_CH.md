# CCscItemFolder::_BindToUncPath(ushort const *,_WIN32_FIND_DATAW const *,_GUID const &,void * *,_ITEMIDLIST_ABSOLUTE * *,_ITEMID_CHILD const * *)

- ea: `0x180038a98`
- end: `0x180038b86`
- name: `?_BindToUncPath@CCscItemFolder@@AEAAJPEBGPEBU_WIN32_FIND_DATAW@@AEBU_GUID@@PEAPEAXPEAPEAU_ITEMIDLIST_ABSOLUTE@@PEAPEFBU_ITEMID_CHILD@@@Z`
- size: `238`
- prototype: `int(CCscItemFolder *__hidden this, const unsigned __int16 *, const struct _WIN32_FIND_DATAW *, const struct _GUID *, void **, struct _ITEMIDLIST_ABSOLUTE **, const struct _ITEMID_CHILD **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180038934`
- `0x18003990c`

## callees

- `0x180011cd0`
- `0x180038a98`
- `0x18004d010`

## import_xrefs

- `SHELL32!SHParseDisplayName` at `0x180038b17`
- `SHELL32!SHParseDisplayName` at `0x180038b17`
- `SHELL32!SHBindToFolderIDListParent` at `0x180038b65`
- `SHELL32!SHBindToFolderIDListParent` at `0x180038b65`
- `SHELL32!__imp_SHILCreateFromPath` at `0x180038b49`
- `SHELL32!__imp_SHILCreateFromPath` at `0x180038b49`

## pseudocode

```c
__int64 __fastcall CCscItemFolder::_BindToUncPath(
        IBindCtx *this,
        const unsigned __int16 *a2,
        const struct _WIN32_FIND_DATAW *a3,
        const struct _GUID *a4,
        void **ppv,
        LPITEMIDLIST *ppidl,
        LPCITEMIDLIST *ppidlLast)
{
  void **v7; // r14
  LPITEMIDLIST *v8; // rdi
  LPCITEMIDLIST *v10; // r15
  int v12; // ebx
  IBindCtx *pbc; // [rsp+60h] [rbp+8h] BYREF

  pbc = this;
  v7 = ppv;
  v8 = ppidl;
  v10 = ppidlLast;
  *ppv = 0;
  *v8 = 0;
  *v10 = 0;
  if ( a3 )
  {
    *v8 = 0;
    if ( *a2 )
    {
      pbc = 0;
      v12 = _CreateFileSysBindCtx((const struct _GUID *)this, a3, &pbc);
      if ( v12 >= 0 )
      {
        v12 = SHParseDisplayName(a2, pbc, v8, 0, 0);
        ((void (__fastcall *)(IBindCtx *))pbc->lpVtbl->Release)(pbc);
      }
    }
    else
    {
      v12 = -2147024809;
    }
  }
  else
  {
    LODWORD(pbc) = 0;
    v12 = SHILCreateFromPath(a2, v8, (DWORD *)&pbc);
  }
  if ( v12 >= 0 )
    return (unsigned int)SHBindToFolderIDListParent(0, *v8, a4, v7, v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180038a98  mov     r11, rsp
0x180038a9b  mov     [r11+10h], rbx
0x180038a9f  mov     [r11+18h], rbp
0x180038aa3  mov     [r11+8], rcx
0x180038aa7  push    rsi
0x180038aa8  push    rdi
0x180038aa9  push    r12
0x180038aab  push    r14
0x180038aad  push    r15
0x180038aaf  sub     rsp, 30h
0x180038ab3  mov     r14, [rsp+58h+ppv]
0x180038abb  xor     r12d, r12d
0x180038abe  mov     rdi, [rsp+58h+ppidl]
0x180038ac6  mov     rbp, r9
0x180038ac9  mov     r15, [rsp+58h+ppidlLast]
0x180038ad1  mov     rax, r8
0x180038ad4  mov     rsi, rdx
0x180038ad7  mov     [r14], r12
0x180038ada  mov     [rdi], r12
0x180038add  mov     [r15], r12
0x180038ae0  test    r8, r8
0x180038ae3  jz      short loc_180038B39
0x180038ae5  mov     [rdi], r12
0x180038ae8  cmp     [rdx], r12w
0x180038aec  jz      short loc_180038B32
0x180038aee  lea     r8, [r11+8]; struct IBindCtx **
0x180038af2  mov     [r11+8], r12
0x180038af6  mov     rdx, rax; struct _WIN32_FIND_DATAW *
0x180038af9  call    ?_CreateFileSysBindCtx@@YAJPEAUIBindCtx@@PEBU_WIN32_FIND_DATAW@@PEAPEAU1@@Z; _CreateFileSysBindCtx(IBindCtx *,_WIN32_FIND_DATAW const *,IBindCtx * *)
0x180038afe  mov     ebx, eax
0x180038b00  test    eax, eax
0x180038b02  js      short loc_180038B51
0x180038b04  mov     rdx, [rsp+58h+pbc]; pbc
0x180038b09  xor     r9d, r9d; sfgaoIn
0x180038b0c  mov     r8, rdi; ppidl
0x180038b0f  mov     [rsp+58h+psfgaoOut], r12; psfgaoOut
0x180038b14  mov     rcx, rsi; pszName
0x180038b17  call    cs:__imp_SHParseDisplayName
0x180038b1d  mov     rcx, [rsp+58h+pbc]
0x180038b22  mov     ebx, eax
0x180038b24  mov     rax, [rcx]
0x180038b27  mov     rax, [rax+10h]
0x180038b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b30  jmp     short loc_180038B51
0x180038b32  mov     ebx, 80070057h
0x180038b37  jmp     short loc_180038B51
0x180038b39  lea     r8, [rsp+58h+pbc]; rgfInOut
0x180038b3e  mov     dword ptr [rsp+58h+pbc], r12d
0x180038b43  mov     rdx, rdi; ppidl
0x180038b46  mov     rcx, rsi; pszPath
0x180038b49  call    cs:__imp_SHILCreateFromPath
0x180038b4f  mov     ebx, eax
0x180038b51  test    ebx, ebx
0x180038b53  js      short loc_180038B6D
0x180038b55  mov     rdx, [rdi]; pidl
0x180038b58  mov     r9, r14; ppv
0x180038b5b  mov     r8, rbp; riid
0x180038b5e  mov     [rsp+58h+psfgaoOut], r15; ppidlLast
0x180038b63  xor     ecx, ecx; psfRoot
0x180038b65  call    cs:__imp_SHBindToFolderIDListParent
0x180038b6b  mov     ebx, eax
0x180038b6d  mov     rbp, [rsp+58h+arg_10]
0x180038b72  mov     eax, ebx
0x180038b74  mov     rbx, [rsp+58h+arg_8]
0x180038b79  add     rsp, 30h
0x180038b7d  pop     r15
0x180038b7f  pop     r14
0x180038b81  pop     r12
0x180038b83  pop     rdi
0x180038b84  pop     rsi
0x180038b85  retn
```
