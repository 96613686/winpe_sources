# CCabFolder::GetDisplayNameOf(_ITEMIDLIST const *,ulong,_STRRET *)

- ea: `0x18000e540`
- end: `0x18000e615`
- name: `?GetDisplayNameOf@CCabFolder@@UEAAJPEFBU_ITEMIDLIST@@KPEAU_STRRET@@@Z`
- size: `213`
- prototype: `int(CCabFolder *__hidden this, const struct _ITEMIDLIST *, unsigned int, struct _STRRET *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002620`
- `0x18000e540`
- `0x18000e674`
- `0x18000f3c4`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x18000e5ca`
- `SHLWAPI!PathAppendW` at `0x18000e5ca`
- `SHLWAPI!SHStrDupW` at `0x18000e5df`
- `SHLWAPI!SHStrDupW` at `0x18000e5df`
- `SHLWAPI!__imp_ualstrcpynW` at `0x18000e58d`
- `SHLWAPI!__imp_ualstrcpynW` at `0x18000e5b7`
- `SHLWAPI!__imp_ualstrcpynW` at `0x18000e58d`
- `SHLWAPI!__imp_ualstrcpynW` at `0x18000e5b7`

## pseudocode

```c
HRESULT __fastcall CCabFolder::GetDisplayNameOf(
        LPCITEMIDLIST *this,
        struct _ITEMIDLIST *a2,
        unsigned int a3,
        struct _STRRET *a4)
{
  PERCEIVED *v5; // rdi
  PWSTR *v6; // r9
  unsigned int *v8; // [rsp+20h] [rbp-458h]
  WCHAR pszExt[264]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR pszMore[264]; // [rsp+240h] [rbp-238h] BYREF

  if ( !a2 )
    return -2147024809;
  if ( (a3 & 0x8000) != 0 )
  {
    v5 = (PERCEIVED *)((char *)&a2[5].mkid.cb + 1);
    if ( (a3 & 1) != 0 )
    {
      ualstrcpynW(pszExt, (PERCEIVED *)((char *)&a2[5].mkid.cb + 1), (PERCEIVEDFLAG *)0x104, (PWSTR *)a3);
    }
    else
    {
      SHGetNameAndFlagsW(this[5], a3, pszExt, a3, v8);
      ualstrcpynW(pszMore, v5, (PERCEIVEDFLAG *)0x104, v6);
      PathAppendW(pszExt, pszMore);
    }
    a4->uType = 0;
    return SHStrDupW(pszExt, &a4->pOleStr);
  }
  else
  {
    CCabFolder::GetNameOf((struct _CABITEM *)a2, a4);
    return 0;
  }
}

```

## disassembly

```asm
0x18000e540  push    rbx
0x18000e542  push    rdi
0x18000e543  sub     rsp, 468h
0x18000e54a  mov     rax, cs:__security_cookie
0x18000e551  xor     rax, rsp
0x18000e554  mov     [rsp+478h+var_28], rax
0x18000e55c  mov     rbx, r9
0x18000e55f  mov     r9d, r8d; unsigned int
0x18000e562  mov     rax, rdx
0x18000e565  test    rdx, rdx
0x18000e568  jz      loc_18000E5F6
0x18000e56e  bt      r8d, 0Fh
0x18000e573  jnb     short loc_18000E5E7
0x18000e575  lea     rdi, [rdx+10h]
0x18000e579  test    r9b, 1
0x18000e57d  jz      short loc_18000E595
0x18000e57f  mov     r8d, 104h; pflag
0x18000e585  lea     rcx, [rsp+478h+pszExt]; pszExt
0x18000e58a  mov     rdx, rdi; ptype
0x18000e58d  call    cs:__imp_ualstrcpynW
0x18000e593  jmp     short loc_18000E5D0
0x18000e595  mov     rcx, [rcx+28h]; pidl
0x18000e599  lea     r8, [rsp+478h+pszExt]; unsigned __int16 *
0x18000e59e  mov     edx, r9d; unsigned int
0x18000e5a1  call    ?SHGetNameAndFlagsW@@YAJPEFBU_ITEMIDLIST@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST const *,ulong,ushort *,uint,ulong *)
0x18000e5a6  mov     r8d, 104h; pflag
0x18000e5ac  lea     rcx, [rsp+478h+pszMore]; pszExt
0x18000e5b4  mov     rdx, rdi; ptype
0x18000e5b7  call    cs:__imp_ualstrcpynW
0x18000e5bd  lea     rdx, [rsp+478h+pszMore]; pszMore
0x18000e5c5  lea     rcx, [rsp+478h+pszExt]; pszPath
0x18000e5ca  call    cs:__imp_PathAppendW
0x18000e5d0  lea     rdx, [rbx+8]; ppwsz
0x18000e5d4  mov     dword ptr [rbx], 0
0x18000e5da  lea     rcx, [rsp+478h+pszExt]; psz
0x18000e5df  call    cs:__imp_SHStrDupW
0x18000e5e5  jmp     short loc_18000E5FB
0x18000e5e7  mov     rdx, rbx; struct _STRRET *
0x18000e5ea  mov     rcx, rax; struct _CABITEM *
0x18000e5ed  call    ?GetNameOf@CCabFolder@@SAJPEFAU_CABITEM@@PEAU_STRRET@@@Z; CCabFolder::GetNameOf(_CABITEM *,_STRRET *)
0x18000e5f2  xor     eax, eax
0x18000e5f4  jmp     short loc_18000E5FB
0x18000e5f6  mov     eax, 80070057h
0x18000e5fb  mov     rcx, [rsp+478h+var_28]
0x18000e603  xor     rcx, rsp; StackCookie
0x18000e606  call    __security_check_cookie
0x18000e60b  add     rsp, 468h
0x18000e612  pop     rdi
0x18000e613  pop     rbx
0x18000e614  retn
```
