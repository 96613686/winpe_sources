# FtpPidl_GetFileInfo(_ITEMIDLIST const *,_SHFILEINFOW *,ulong)

- ea: `0x18001c5dc`
- end: `0x18001c752`
- name: `?FtpPidl_GetFileInfo@@YAJPEFBU_ITEMIDLIST@@PEAU_SHFILEINFOW@@K@Z`
- size: `374`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST *, SHFILEINFOW *psfi, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800108e4`
- `0x1800194e0`
- `0x18001c7e8`

## callees

- `0x180002240`
- `0x18001bda4`
- `0x18001c330`
- `0x18001c5dc`
- `0x18001d2dc`
- `0x1800217e4`

## import_xrefs

- `SHELL32!ExtractIconExW` at `0x18001c6b0`
- `SHELL32!ExtractIconExW` at `0x18001c6b0`
- `SHELL32!SHGetFileInfoW` at `0x18001c661`
- `SHELL32!SHGetFileInfoW` at `0x18001c71f`
- `SHELL32!SHGetFileInfoW` at `0x18001c661`
- `SHELL32!SHGetFileInfoW` at `0x18001c71f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001c6cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001c6cb`
- `USER32!DestroyIcon` at `0x18001c68b`
- `USER32!DestroyIcon` at `0x18001c68b`

## string_xrefs

- `0x18001c6a5`: `imageres.dll`

## pseudocode

```c
__int64 __fastcall FtpPidl_GetFileInfo(const struct _ITEMIDLIST *a1, SHFILEINFOW *psfi, int a3)
{
  WCHAR *szTypeName; // r14
  DWORD_PTR v7; // rax
  unsigned int v8; // ebx
  WCHAR pszPath[264]; // [rsp+30h] [rbp-248h] BYREF

  psfi->hIcon = 0;
  szTypeName = psfi->szTypeName;
  psfi->szDisplayName[0] = 0;
  psfi->szTypeName[0] = 0;
  *(_QWORD *)&psfi->iIcon = 0;
  if ( (unsigned int)FtpID_IsServerItemID(a1) )
  {
    FtpServerID_GetServer(a1, pszPath, 0x104u);
    v7 = SHGetFileInfoW(pszPath, 0x10u, psfi, 0x2B8u, a3 | 0x10u);
    if ( v7 )
    {
      v8 = v7 == 0 ? 0x80004005 : 0;
      if ( psfi->hIcon )
        DestroyIcon(psfi->hIcon);
      if ( (a3 & 0x100) != 0 )
        ExtractIconExW(L"imageres.dll", -73, 0, &psfi->hIcon, 1u);
      LoadStringW(g_hinst, 0x11Fu, szTypeName, 80);
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    v8 = -2147467259;
    if ( a1->mkid.cb >= 0x27u && (*(_DWORD *)&a1[2].mkid.cb & 0xFFFCFFC2) == 0 )
    {
      FtpItemID_GetDisplayName(a1, pszPath, 0x104u);
      UrlPathToFileNameW(pszPath);
      return SHGetFileInfoW(pszPath, *(_DWORD *)((_BYTE *)&a1[3].mkid.cb + 1) & 0xFFFFFFF9, psfi, 0x2B8u, a3 | 0x10u) == 0
           ? 0x80004005
           : 0;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18001c5dc  push    rbx
0x18001c5de  push    rbp
0x18001c5df  push    rsi
0x18001c5e0  push    rdi
0x18001c5e1  push    r14
0x18001c5e3  sub     rsp, 250h
0x18001c5ea  mov     rax, cs:__security_cookie
0x18001c5f1  xor     rax, rsp
0x18001c5f4  mov     [rsp+278h+var_38], rax
0x18001c5fc  xor     eax, eax
0x18001c5fe  mov     qword ptr [rdx], 0
0x18001c605  lea     r14, [rdx+218h]
0x18001c60c  mov     [rdx+10h], ax
0x18001c610  mov     [r14], ax
0x18001c614  mov     ebp, r8d
0x18001c617  mov     rdi, rdx
0x18001c61a  mov     qword ptr [rdx+8], 0
0x18001c622  mov     rsi, rcx
0x18001c625  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001c62a  test    eax, eax
0x18001c62c  jz      loc_18001C6D3
0x18001c632  mov     r8d, 104h; unsigned int
0x18001c638  lea     rdx, [rsp+278h+pszPath]; unsigned __int16 *
0x18001c63d  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001c640  call    ?FtpServerID_GetServer@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpServerID_GetServer(_ITEMIDLIST const *,ushort *,ulong)
0x18001c645  mov     eax, ebp
0x18001c647  lea     rcx, [rsp+278h+pszPath]; pszPath
0x18001c64c  or      eax, 10h
0x18001c64f  mov     r9d, 2B8h; cbFileInfo
0x18001c655  mov     r8, rdi; psfi
0x18001c658  mov     [rsp+278h+uFlags], eax; uFlags
0x18001c65c  mov     edx, 10h; dwFileAttributes
0x18001c661  call    cs:__imp_SHGetFileInfoW
0x18001c667  test    rax, rax
0x18001c66a  jnz     short loc_18001C676
0x18001c66c  mov     ebx, 80004005h
0x18001c671  jmp     loc_18001C732
0x18001c676  mov     rcx, [rdi]; hIcon
0x18001c679  neg     rax
0x18001c67c  sbb     ebx, ebx
0x18001c67e  not     ebx
0x18001c680  and     ebx, 80004005h
0x18001c686  test    rcx, rcx
0x18001c689  jz      short loc_18001C691
0x18001c68b  call    cs:__imp_DestroyIcon
0x18001c691  bt      ebp, 8
0x18001c695  jnb     short loc_18001C6B6
0x18001c697  xor     r8d, r8d; phiconLarge
0x18001c69a  mov     [rsp+278h+uFlags], 1; nIcons
0x18001c6a2  mov     r9, rdi; phiconSmall
0x18001c6a5  lea     rcx, szFile; "imageres.dll"
0x18001c6ac  lea     edx, [r8-49h]; nIconIndex
0x18001c6b0  call    cs:__imp_ExtractIconExW
0x18001c6b6  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18001c6bd  mov     r9d, 50h ; 'P'; cchBufferMax
0x18001c6c3  mov     r8, r14; lpBuffer
0x18001c6c6  mov     edx, 11Fh; uID
0x18001c6cb  call    cs:__imp_LoadStringW
0x18001c6d1  jmp     short loc_18001C732
0x18001c6d3  cmp     word ptr [rsi], 27h ; '''
0x18001c6d7  mov     ebx, 80004005h
0x18001c6dc  jb      short loc_18001C732
0x18001c6de  test    dword ptr [rsi+6], 0FFFCFFC2h
0x18001c6e5  jnz     short loc_18001C732
0x18001c6e7  mov     r8d, 104h; unsigned int
0x18001c6ed  lea     rdx, [rsp+278h+pszPath]; unsigned __int16 *
0x18001c6f2  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001c6f5  call    ?FtpItemID_GetDisplayName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpItemID_GetDisplayName(_ITEMIDLIST const *,ushort *,ulong)
0x18001c6fa  lea     rcx, [rsp+278h+pszPath]; unsigned __int16 *
0x18001c6ff  call    ?UrlPathToFileNameW@@YAJPEAG@Z; UrlPathToFileNameW(ushort *)
0x18001c704  mov     edx, [rsi+0Ah]
0x18001c707  lea     rcx, [rsp+278h+pszPath]; pszPath
0x18001c70c  or      ebp, 10h
0x18001c70f  and     edx, 0FFFFFFF9h; dwFileAttributes
0x18001c712  mov     r9d, 2B8h; cbFileInfo
0x18001c718  mov     [rsp+278h+uFlags], ebp; uFlags
0x18001c71c  mov     r8, rdi; psfi
0x18001c71f  call    cs:__imp_SHGetFileInfoW
0x18001c725  neg     rax
0x18001c728  sbb     ebx, ebx
0x18001c72a  not     ebx
0x18001c72c  and     ebx, 80004005h
0x18001c732  mov     eax, ebx
0x18001c734  mov     rcx, [rsp+278h+var_38]
0x18001c73c  xor     rcx, rsp; StackCookie
0x18001c73f  call    __security_check_cookie
0x18001c744  add     rsp, 250h
0x18001c74b  pop     r14
0x18001c74d  pop     rdi
0x18001c74e  pop     rsi
0x18001c74f  pop     rbp
0x18001c750  pop     rbx
0x18001c751  retn
```
