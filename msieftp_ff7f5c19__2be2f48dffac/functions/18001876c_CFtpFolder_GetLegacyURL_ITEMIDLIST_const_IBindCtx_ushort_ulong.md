# CFtpFolder::_GetLegacyURL(_ITEMIDLIST const *,IBindCtx *,ushort *,ulong)

- ea: `0x18001876c`
- end: `0x18001896b`
- name: `?_GetLegacyURL@CFtpFolder@@IEAAJPEFBU_ITEMIDLIST@@PEAUIBindCtx@@PEAGK@Z`
- size: `511`
- prototype: `int(CFtpFolder *__hidden this, const struct _ITEMIDLIST *, struct IBindCtx *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018568`
- `0x180018ee4`

## callees

- `0x180002240`
- `0x180006b40`
- `0x18001876c`
- `0x18001bda4`
- `0x18001cd5c`
- `0x18001d6bc`
- `0x18001fdb0`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x18001888f`
- `SHELL32!__imp_ILClone` at `0x18001888f`
- `SHELL32!__imp_ILCombine` at `0x180018843`
- `SHELL32!__imp_ILCombine` at `0x180018843`
- `SHELL32!__imp_ILFree` at `0x180018869`
- `SHELL32!__imp_ILFree` at `0x180018939`
- `SHELL32!__imp_ILFree` at `0x180018869`
- `SHELL32!__imp_ILFree` at `0x180018939`
- `SHLWAPI!UrlCombineW` at `0x180018930`
- `SHLWAPI!UrlCombineW` at `0x180018930`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180018912`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180018912`
- `SHLWAPI!__imp_ualstrcpynW` at `0x1800188f1`
- `SHLWAPI!__imp_ualstrcpynW` at `0x1800188f1`

## pseudocode

```c
__int64 __fastcall CFtpFolder::_GetLegacyURL(
        CFtpFolder *this,
        struct _ITEMIDLIST *a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4)
{
  struct IMalloc *v4; // r8
  unsigned __int16 *v6; // rdi
  int v7; // ebx
  int v8; // eax
  int v9; // esi
  struct _ITEMIDLIST *v10; // r12
  struct CFtpSite *v11; // r14
  const ITEMIDLIST *v12; // r13
  struct _ITEMIDLIST *i; // rdi
  USHORT cb; // bx
  const ITEMIDLIST *v15; // rax
  ITEMIDLIST *v16; // r13
  __int64 v17; // rax
  PWSTR *v18; // r9
  DWORD pcchCombined; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v21; // [rsp+38h] [rbp-C8h]
  struct CFtpSite *v22; // [rsp+40h] [rbp-C0h] BYREF
  struct _ITEMIDLIST *v23; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszExt[264]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = (struct IMalloc *)*((_QWORD *)this + 16);
  v6 = a4;
  v21 = a4;
  v7 = 0;
  pcchCombined = 2084;
  v22 = 0;
  v8 = SiteCache_PidlLookup(a2, 0, v4, &v22);
  v23 = 0;
  v9 = v8;
  v10 = 0;
  if ( v8 >= 0 )
  {
    v11 = v22;
    if ( !v22 )
      goto LABEL_18;
    v12 = (const ITEMIDLIST *)*((_QWORD *)v22 + 13);
    if ( v12 )
    {
      for ( i = a2; i; i = (struct _ITEMIDLIST *)((char *)i + i->mkid.cb) )
      {
        if ( !i->mkid.cb )
          break;
        if ( (unsigned int)FtpID_IsServerItemID(i) )
          break;
      }
      if ( (unsigned int)FtpID_IsServerItemID(i) )
        i = (struct _ITEMIDLIST *)((char *)i + i->mkid.cb);
      if ( i )
      {
        cb = i->mkid.cb;
        i->mkid.cb = 0;
        v15 = ILCombine(a2, v12);
        i->mkid.cb = cb;
        v7 = 0;
        v16 = (ITEMIDLIST *)v15;
        if ( v15 )
        {
          FtpPidl_InsertVirtualRoot(v15, i, &v23);
          ILFree(v16);
          v10 = v23;
        }
      }
      else
      {
        v9 = -2147024882;
      }
      v6 = v21;
    }
    else
    {
      v9 = -2147467259;
    }
    (*(void (__fastcall **)(struct CFtpSite *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v9 >= 0 )
      goto LABEL_18;
  }
  v10 = ILClone(a2);
  if ( !v10 )
    v7 = v9;
  if ( v7 >= 0 )
  {
LABEL_18:
    v7 = UrlCreateFromPidl(v10, 0x8000u, v6, pcchCombined, 0xC0000000, 0);
    v17 = ILFindHiddenIDOn(a2);
    if ( v17 )
    {
      if ( *(_WORD *)(v17 + 8) == 2 )
        ualstrcpynW(pszExt, (PERCEIVED *)(v17 + 10), (PERCEIVEDFLAG *)0x104, v18);
      else
        SHAnsiToUnicode((PCSTR)(v17 + 10), pszExt, 260);
      UrlCombineW(v6, pszExt, v6, &pcchCombined, 0);
    }
    ILFree(v10);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001876c  mov     [rsp-8+arg_10], rbx
0x180018771  push    rbp
0x180018772  push    rsi
0x180018773  push    rdi
0x180018774  push    r12
0x180018776  push    r13
0x180018778  push    r14
0x18001877a  push    r15
0x18001877c  lea     rbp, [rsp-170h]
0x180018784  sub     rsp, 270h
0x18001878b  mov     rax, cs:__security_cookie
0x180018792  xor     rax, rsp
0x180018795  mov     [rbp+1A0h+var_40], rax
0x18001879c  mov     r8, [rcx+80h]; struct IMalloc *
0x1800187a3  mov     r15, rdx
0x1800187a6  mov     rdi, r9
0x1800187a9  mov     [rsp+2A0h+var_268], r9
0x1800187ae  xor     ebx, ebx
0x1800187b0  mov     [rsp+2A0h+pcchCombined], 824h
0x1800187b8  mov     rcx, r15; struct _ITEMIDLIST *
0x1800187bb  mov     [rsp+2A0h+var_260], rbx
0x1800187c0  lea     r9, [rsp+2A0h+var_260]; struct CFtpSite **
0x1800187c5  xor     edx, edx; int
0x1800187c7  call    ?SiteCache_PidlLookup@@YAJPEFBU_ITEMIDLIST@@HPEAUIMalloc@@PEAPEAVCFtpSite@@@Z; SiteCache_PidlLookup(_ITEMIDLIST const *,int,IMalloc *,CFtpSite * *)
0x1800187cc  mov     [rsp+2A0h+var_258], rbx
0x1800187d1  mov     esi, eax
0x1800187d3  mov     r12d, ebx
0x1800187d6  test    eax, eax
0x1800187d8  js      loc_18001888C
0x1800187de  mov     r14, [rsp+2A0h+var_260]
0x1800187e3  test    r14, r14
0x1800187e6  jz      loc_1800188A8
0x1800187ec  mov     r13, [r14+68h]
0x1800187f0  test    r13, r13
0x1800187f3  jz      loc_180018903
0x1800187f9  mov     rdi, r15
0x1800187fc  test    r15, r15
0x1800187ff  jz      short loc_18001881A
0x180018801  cmp     [rdi], bx
0x180018804  jz      short loc_18001881A
0x180018806  mov     rcx, rdi; struct _ITEMIDLIST *
0x180018809  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001880e  test    eax, eax
0x180018810  jnz     short loc_18001881A
0x180018812  movzx   eax, word ptr [rdi]
0x180018815  add     rdi, rax
0x180018818  jnz     short loc_180018801
0x18001881a  mov     rcx, rdi; struct _ITEMIDLIST *
0x18001881d  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x180018822  test    eax, eax
0x180018824  jz      short loc_18001882C
0x180018826  movzx   eax, word ptr [rdi]
0x180018829  add     rdi, rax
0x18001882c  test    rdi, rdi
0x18001882f  jz      loc_1800188F9
0x180018835  movzx   ebx, word ptr [rdi]
0x180018838  xor     eax, eax
0x18001883a  mov     rdx, r13; pidl2
0x18001883d  mov     [rdi], ax
0x180018840  mov     rcx, r15; pidl1
0x180018843  call    cs:__imp_ILCombine
0x180018849  mov     [rdi], bx
0x18001884c  xor     ebx, ebx
0x18001884e  mov     r13, rax
0x180018851  test    rax, rax
0x180018854  jz      short loc_180018874
0x180018856  lea     r8, [rsp+2A0h+var_258]; struct _ITEMIDLIST **
0x18001885b  mov     rdx, rdi; struct _ITEMIDLIST *
0x18001885e  mov     rcx, rax; pidl1
0x180018861  call    ?FtpPidl_InsertVirtualRoot@@YAJPEFBU_ITEMIDLIST@@0PEAPEFAU1@@Z; FtpPidl_InsertVirtualRoot(_ITEMIDLIST const *,_ITEMIDLIST const *,_ITEMIDLIST * *)
0x180018866  mov     rcx, r13; pidl
0x180018869  call    cs:__imp_ILFree
0x18001886f  mov     r12, [rsp+2A0h+var_258]
0x180018874  mov     rdi, [rsp+2A0h+var_268]
0x180018879  mov     rax, [r14]
0x18001887c  mov     rcx, r14
0x18001887f  mov     rax, [rax+10h]
0x180018883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018888  test    esi, esi
0x18001888a  jns     short loc_1800188A8
0x18001888c  mov     rcx, r15; pidl
0x18001888f  call    cs:__imp_ILClone
0x180018895  test    rax, rax
0x180018898  mov     r12, rax
0x18001889b  cmovz   ebx, esi
0x18001889e  test    ebx, ebx
0x1800188a0  js      loc_18001893F
0x1800188a6  xor     ebx, ebx
0x1800188a8  mov     r9d, [rsp+2A0h+pcchCombined]; unsigned int
0x1800188ad  mov     r8, rdi; unsigned __int16 *
0x1800188b0  mov     [rsp+2A0h+var_278], ebx; int
0x1800188b4  mov     edx, 8000h; unsigned int
0x1800188b9  mov     rcx, r12; struct _ITEMIDLIST *
0x1800188bc  mov     [rsp+2A0h+dwFlags], 0C0000000h; unsigned int
0x1800188c4  call    ?UrlCreateFromPidl@@YAJPEFBU_ITEMIDLIST@@KPEAGKKH@Z; UrlCreateFromPidl(_ITEMIDLIST const *,ulong,ushort *,ulong,ulong,int)
0x1800188c9  mov     rcx, r15
0x1800188cc  mov     ebx, eax
0x1800188ce  call    ?ILFindHiddenIDOn@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST@@W4IDLHID@@H@Z; ILFindHiddenIDOn(_ITEMIDLIST const *,IDLHID,int)
0x1800188d3  test    rax, rax
0x1800188d6  jz      short loc_180018936
0x1800188d8  cmp     word ptr [rax+8], 2
0x1800188dd  lea     rcx, [rax+0Ah]; pszSrc
0x1800188e1  mov     r8d, 104h; cwchBuf
0x1800188e7  jnz     short loc_18001890D
0x1800188e9  mov     rdx, rcx; ptype
0x1800188ec  lea     rcx, [rsp+2A0h+pszExt]; pszExt
0x1800188f1  call    cs:__imp_ualstrcpynW
0x1800188f7  jmp     short loc_180018918
0x1800188f9  mov     esi, 8007000Eh
0x1800188fe  jmp     loc_180018874
0x180018903  mov     esi, 80004005h
0x180018908  jmp     loc_180018879
0x18001890d  lea     rdx, [rsp+2A0h+pszExt]; pwszDst
0x180018912  call    cs:__imp_SHAnsiToUnicode
0x180018918  lea     r9, [rsp+2A0h+pcchCombined]; pcchCombined
0x18001891d  mov     [rsp+2A0h+dwFlags], 0; dwFlags
0x180018925  mov     r8, rdi; pszCombined
0x180018928  lea     rdx, [rsp+2A0h+pszExt]; pszRelative
0x18001892d  mov     rcx, rdi; pszBase
0x180018930  call    cs:__imp_UrlCombineW
0x180018936  mov     rcx, r12; pidl
0x180018939  call    cs:__imp_ILFree
0x18001893f  mov     eax, ebx
0x180018941  mov     rcx, [rbp+1A0h+var_40]
0x180018948  xor     rcx, rsp; StackCookie
0x18001894b  call    __security_check_cookie
0x180018950  mov     rbx, [rsp+2A0h+arg_10]
0x180018958  add     rsp, 270h
0x18001895f  pop     r15
0x180018961  pop     r14
0x180018963  pop     r13
0x180018965  pop     r12
0x180018967  pop     rdi
0x180018968  pop     rsi
0x180018969  pop     rbp
0x18001896a  retn
```
