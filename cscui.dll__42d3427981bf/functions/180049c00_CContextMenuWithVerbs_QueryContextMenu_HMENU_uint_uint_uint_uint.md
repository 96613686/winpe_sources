# CContextMenuWithVerbs::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x180049c00`
- end: `0x180049e90`
- name: `?QueryContextMenu@CContextMenuWithVerbs@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `656`
- prototype: `__int64 __usercall@<rax>(CContextMenuWithVerbs *__hidden this@<rcx>, HMENU@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000c1dc`
- `0x18000d740`
- `0x180048a40`
- `0x180049854`
- `0x180049910`
- `0x180049940`
- `0x180049c00`
- `0x18004c636`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x180049e13`
- `SHLWAPI!__imp_StrCmpICW` at `0x180049e13`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180049c8e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180049ced`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180049e1f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180049c8e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180049ced`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180049e1f`
- `USER32!GetMenuItemInfoW` at `0x180049da9`
- `USER32!GetMenuItemInfoW` at `0x180049da9`
- `USER32!GetMenuItemCount` at `0x180049d60`
- `USER32!GetMenuItemCount` at `0x180049d60`
- `USER32!DeleteMenu` at `0x180049e4f`
- `USER32!DeleteMenu` at `0x180049e4f`

## pseudocode

```c
__int64 __fastcall CContextMenuWithVerbs::QueryContextMenu(
        CContextMenuWithVerbs *this,
        HMENU a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  HMENU v7; // r15
  const WCHAR *v9; // rbx
  unsigned int v10; // esi
  unsigned __int64 v11; // rax
  void *v12; // rax
  void *v13; // r12
  const WCHAR *v14; // rbx
  const WCHAR **v15; // r14
  unsigned int v16; // r13d
  int MenuItemCount; // r12d
  signed int v18; // ebx
  unsigned int v19; // r13d
  const WCHAR *v20; // rsi
  BOOL v21; // eax
  int v22; // r14d
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-CCh]
  HMENU v26; // [rsp+38h] [rbp-C8h]
  struct tagMENUITEMINFOW mii; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszStr1[80]; // [rsp+90h] [rbp-70h] BYREF

  v25 = a4;
  v7 = a2;
  v26 = a2;
  v24 = 0;
  if ( *((_QWORD *)this + 17)
    && (*(int (__fastcall **)(char *, __int64, int *))(*((_QWORD *)this + 4) + 40LL))((char *)this + 32, 512, &v24) >= 0
    && (v24 & 0x200) != 0 )
  {
    v9 = (const WCHAR *)*((_QWORD *)this + 17);
    v10 = 0;
    while ( *v9 )
    {
      ++v10;
      v9 += lstrlenW(v9) + 1;
    }
    v11 = 8LL * (int)v10;
    if ( !is_mul_ok((int)v10, 8u) )
      v11 = -1;
    v12 = operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
    v13 = v12;
    if ( v12 )
    {
      v14 = (const WCHAR *)*((_QWORD *)this + 17);
      v15 = (const WCHAR **)v12;
      if ( *v14 )
      {
        do
        {
          *v15++ = v14;
          v14 += lstrlenW(v14) + 1;
        }
        while ( *v14 );
        v7 = v26;
      }
      (*(void (__fastcall **)(char *, void *, _QWORD))(*((_QWORD *)this + 5) + 24LL))((char *)this + 40, v13, v10);
      operator delete(v13);
    }
  }
  LODWORD(v26) = CContextMenuForwarder::QueryContextMenu(this, v7, a3, v25, a5, a6);
  v16 = (unsigned int)v26;
  if ( (int)v26 >= 0 )
  {
    MenuItemCount = GetMenuItemCount(v7);
    v18 = 0;
    if ( MenuItemCount > 0 )
    {
      v19 = v25;
      do
      {
        memset_0(&mii, 0, sizeof(mii));
        mii.cbSize = 80;
        mii.fMask = 18;
        if ( GetMenuItemInfoW(v7, v18, 1024, &mii) && IsValidCommandItem(&mii, v19) && !IsDefViewPlaceholder(v7, v18) )
        {
          if ( ContextMenu_GetCommandStringVerb(*((struct IContextMenu **)this + 10), mii.wID - v19, pszStr1, 80) >= 0
            && (v20 = (const WCHAR *)*((_QWORD *)this + 17), v21 = 0, *v20) )
          {
            while ( !v21 )
            {
              v22 = StrCmpICW(pszStr1, v20);
              v20 += lstrlenW(v20) + 1;
              v21 = v22 == 0;
              if ( !*v20 )
              {
                if ( !v22 )
                  break;
                goto LABEL_25;
              }
            }
          }
          else
          {
LABEL_25:
            DeleteMenu(v7, v18--, 0x400u);
          }
        }
        ++v18;
      }
      while ( v18 < MenuItemCount );
      return (unsigned int)v26;
    }
  }
  return v16;
}

```

## disassembly

```asm
0x180049c00  push    rbp
0x180049c02  push    rbx
0x180049c03  push    rsi
0x180049c04  push    rdi
0x180049c05  push    r12
0x180049c07  push    r13
0x180049c09  push    r14
0x180049c0b  push    r15
0x180049c0d  lea     rbp, [rsp-48h]
0x180049c12  sub     rsp, 148h
0x180049c19  mov     rax, cs:__security_cookie
0x180049c20  xor     rax, rsp
0x180049c23  mov     [rbp+80h+var_50], rax
0x180049c27  xor     r14d, r14d
0x180049c2a  mov     [rsp+180h+var_14C], r9d
0x180049c2f  mov     r13d, r8d
0x180049c32  mov     r15, rdx
0x180049c35  mov     rdi, rcx
0x180049c38  mov     [rsp+180h+var_148], rdx
0x180049c3d  mov     [rsp+180h+var_150], r14d
0x180049c42  cmp     [rcx+88h], r14
0x180049c49  jz      loc_180049D27
0x180049c4f  add     rcx, 20h ; ' '
0x180049c53  lea     r8, [rsp+180h+var_150]
0x180049c58  mov     ebx, 200h
0x180049c5d  mov     edx, ebx
0x180049c5f  mov     rax, [rcx]
0x180049c62  mov     rax, [rax+28h]
0x180049c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c6b  test    eax, eax
0x180049c6d  js      loc_180049D27
0x180049c73  test    [rsp+180h+var_150], ebx
0x180049c77  jz      loc_180049D27
0x180049c7d  mov     rbx, [rdi+88h]
0x180049c84  mov     esi, r14d
0x180049c87  jmp     short loc_180049C9C
0x180049c89  mov     rcx, rbx; lpString
0x180049c8c  inc     esi
0x180049c8e  call    cs:__imp_lstrlenW
0x180049c94  inc     eax
0x180049c96  cdqe
0x180049c98  lea     rbx, [rbx+rax*2]
0x180049c9c  cmp     [rbx], r14w
0x180049ca0  jnz     short loc_180049C89
0x180049ca2  movsxd  rcx, esi
0x180049ca5  mov     eax, 8
0x180049caa  mul     rcx
0x180049cad  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180049cb4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180049cbb  cmovb   rax, rcx
0x180049cbf  mov     rcx, rax; unsigned __int64
0x180049cc2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180049cc7  mov     r12, rax
0x180049cca  test    rax, rax
0x180049ccd  jz      short loc_180049D27
0x180049ccf  mov     rbx, [rdi+88h]
0x180049cd6  mov     r14, rax
0x180049cd9  xor     eax, eax
0x180049cdb  cmp     [rbx], ax
0x180049cde  jz      short loc_180049D06
0x180049ce0  xor     r15d, r15d
0x180049ce3  mov     [r14], rbx
0x180049ce6  mov     rcx, rbx; lpString
0x180049ce9  lea     r14, [r14+8]
0x180049ced  call    cs:__imp_lstrlenW
0x180049cf3  inc     eax
0x180049cf5  cdqe
0x180049cf7  lea     rbx, [rbx+rax*2]
0x180049cfb  cmp     [rbx], r15w
0x180049cff  jnz     short loc_180049CE3
0x180049d01  mov     r15, [rsp+180h+var_148]
0x180049d06  lea     rcx, [rdi+28h]
0x180049d0a  mov     r8d, esi
0x180049d0d  mov     rax, [rcx]
0x180049d10  mov     rdx, r12
0x180049d13  mov     rax, [rax+18h]
0x180049d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d1c  mov     rcx, r12; Block
0x180049d1f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180049d24  xor     r14d, r14d
0x180049d27  mov     eax, [rbp+80h+arg_28]
0x180049d2d  mov     r8d, r13d; unsigned int
0x180049d30  mov     r9d, [rsp+180h+var_14C]; unsigned int
0x180049d35  mov     rdx, r15; HMENU
0x180049d38  mov     [rsp+180h+var_158], eax; unsigned int
0x180049d3c  mov     rcx, rdi; this
0x180049d3f  mov     eax, [rbp+80h+arg_20]
0x180049d45  mov     [rsp+180h+var_160], eax; unsigned int
0x180049d49  call    ?QueryContextMenu@CContextMenuForwarder@@UEAAJPEAUHMENU__@@IIII@Z; CContextMenuForwarder::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)
0x180049d4e  mov     dword ptr [rsp+180h+var_148], eax
0x180049d52  mov     r13d, eax
0x180049d55  test    eax, eax
0x180049d57  js      loc_180049E6D
0x180049d5d  mov     rcx, r15; hMenu
0x180049d60  call    cs:__imp_GetMenuItemCount
0x180049d66  mov     r12d, eax
0x180049d69  mov     ebx, r14d
0x180049d6c  test    eax, eax
0x180049d6e  jle     loc_180049E6D
0x180049d74  mov     r13d, [rsp+180h+var_14C]
0x180049d79  xor     edx, edx; Val
0x180049d7b  lea     rcx, [rsp+180h+mii]; void *
0x180049d80  lea     r8d, [rdx+50h]; Size
0x180049d84  call    memset_0
0x180049d89  lea     r9, [rsp+180h+mii]; lpmii
0x180049d8e  mov     [rsp+180h+mii.cbSize], 50h ; 'P'
0x180049d96  mov     r8d, 400h; fByPosition
0x180049d9c  mov     [rsp+180h+mii.fMask], 12h
0x180049da4  mov     edx, ebx; item
0x180049da6  mov     rcx, r15; hmenu
0x180049da9  call    cs:__imp_GetMenuItemInfoW
0x180049daf  test    eax, eax
0x180049db1  jz      loc_180049E57
0x180049db7  mov     edx, r13d; unsigned int
0x180049dba  lea     rcx, [rsp+180h+mii]; struct tagMENUITEMINFOW *
0x180049dbf  call    ?IsValidCommandItem@@YA_NAEBUtagMENUITEMINFOW@@I@Z; IsValidCommandItem(tagMENUITEMINFOW const &,uint)
0x180049dc4  test    al, al
0x180049dc6  jz      loc_180049E57
0x180049dcc  mov     edx, ebx; item
0x180049dce  mov     rcx, r15; hmenu
0x180049dd1  call    ?IsDefViewPlaceholder@@YA_NPEAUHMENU__@@H@Z; IsDefViewPlaceholder(HMENU__ *,int)
0x180049dd6  test    al, al
0x180049dd8  jnz     short loc_180049E57
0x180049dda  mov     edx, [rsp+180h+mii.wID]
0x180049dde  lea     r8, [rbp+80h+pszStr1]; unsigned __int16 *
0x180049de2  mov     rcx, [rdi+50h]; struct IContextMenu *
0x180049de6  sub     edx, r13d; unsigned int
0x180049de9  mov     r9d, 50h ; 'P'; int
0x180049def  call    ?ContextMenu_GetCommandStringVerb@@YAJPEAUIContextMenu@@IPEAGH@Z; ContextMenu_GetCommandStringVerb(IContextMenu *,uint,ushort *,int)
0x180049df4  test    eax, eax
0x180049df6  js      short loc_180049E44
0x180049df8  mov     rsi, [rdi+88h]
0x180049dff  mov     eax, r14d
0x180049e02  cmp     [rsi], r14w
0x180049e06  jz      short loc_180049E44
0x180049e08  test    eax, eax
0x180049e0a  jnz     short loc_180049E57
0x180049e0c  mov     rdx, rsi; pszStr2
0x180049e0f  lea     rcx, [rbp+80h+pszStr1]; pszStr1
0x180049e13  call    cs:__imp_StrCmpICW
0x180049e19  mov     rcx, rsi; lpString
0x180049e1c  mov     r14d, eax
0x180049e1f  call    cs:__imp_lstrlenW
0x180049e25  movsxd  rcx, eax
0x180049e28  lea     rsi, [rsi+rcx*2]
0x180049e2c  xor     ecx, ecx
0x180049e2e  add     rsi, 2
0x180049e32  mov     eax, ecx
0x180049e34  test    r14d, r14d
0x180049e37  setz    al
0x180049e3a  cmp     [rsi], cx
0x180049e3d  jnz     short loc_180049E08
0x180049e3f  test    r14d, r14d
0x180049e42  jz      short loc_180049E57
0x180049e44  mov     r8d, 400h; uFlags
0x180049e4a  mov     edx, ebx; uPosition
0x180049e4c  mov     rcx, r15; hMenu
0x180049e4f  call    cs:__imp_DeleteMenu
0x180049e55  dec     ebx
0x180049e57  inc     ebx
0x180049e59  mov     r14d, 0
0x180049e5f  cmp     ebx, r12d
0x180049e62  jl      loc_180049D79
0x180049e68  mov     r13d, dword ptr [rsp+180h+var_148]
0x180049e6d  mov     eax, r13d
0x180049e70  mov     rcx, [rbp+80h+var_50]
0x180049e74  xor     rcx, rsp; StackCookie
0x180049e77  call    __security_check_cookie
0x180049e7c  add     rsp, 148h
0x180049e83  pop     r15
0x180049e85  pop     r14
0x180049e87  pop     r13
0x180049e89  pop     r12
0x180049e8b  pop     rdi
0x180049e8c  pop     rsi
0x180049e8d  pop     rbx
0x180049e8e  pop     rbp
0x180049e8f  retn
```
