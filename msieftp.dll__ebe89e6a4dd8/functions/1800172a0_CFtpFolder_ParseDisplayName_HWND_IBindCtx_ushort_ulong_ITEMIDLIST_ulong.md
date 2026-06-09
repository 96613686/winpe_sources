# CFtpFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST * *,ulong *)

- ea: `0x1800172a0`
- end: `0x180017502`
- name: `?ParseDisplayName@CFtpFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEFAU_ITEMIDLIST@@3@Z`
- size: `610`
- prototype: `__int64 __usercall@<rax>(CFtpFolder *__hidden this@<rcx>, HWND@<rdx>, struct IBindCtx *@<r8>, unsigned __int16 *@<r9>, unsigned int *, struct _ITEMIDLIST **, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002240`
- `0x180016b4c`
- `0x1800170bc`
- `0x1800172a0`
- `0x1800182c4`
- `0x18001b3ec`
- `0x18001b91c`
- `0x18001fdb0`
- `0x18002009c`
- `0x180026ff0`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180017476`
- `SHELL32!__imp_ILFree` at `0x180017476`
- `SHLWAPI!PathIsRelativeW` at `0x1800173a3`
- `SHLWAPI!PathIsRelativeW` at `0x1800173a3`
- `SHLWAPI!__imp_ParseURLW` at `0x180017390`
- `SHLWAPI!__imp_ParseURLW` at `0x180017390`

## pseudocode

```c
__int64 __fastcall CFtpFolder::ParseDisplayName(
        struct IMalloc **this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST **a6,
        unsigned int *a7)
{
  int CachedPidlFromDisplayName; // edi
  _WORD *v11; // rax
  _WORD *v12; // rdx
  struct IMalloc *v13; // rbx
  unsigned int WireEncoding; // eax
  struct IMalloc *v15; // r8
  const struct _ITEMIDLIST *v16; // rcx
  __int64 v17; // rbx
  struct CFtpDir *FtpDir; // rax
  struct CFtpDir *v20; // rbx
  __int64 v21; // rax
  unsigned int v22; // edx
  PARSEDURLW ppu; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v24[12]; // [rsp+68h] [rbp-18h] BYREF
  int v25; // [rsp+74h] [rbp-Ch]

  *a6 = 0;
  CachedPidlFromDisplayName = CFtpFolder::_GetCachedPidlFromDisplayName(this, a4, a6);
  if ( CachedPidlFromDisplayName >= 0 )
  {
LABEL_21:
    if ( a7 )
    {
      CachedPidlFromDisplayName = ((__int64 (__fastcall *)(struct IMalloc **, __int64, struct _ITEMIDLIST **, unsigned int *))(*this)[9].lpVtbl)(
                                    this,
                                    1,
                                    a6,
                                    a7);
      if ( CachedPidlFromDisplayName < 0 )
        ILFree(*a6);
    }
    return (unsigned int)CachedPidlFromDisplayName;
  }
  v11 = (_WORD *)((char *)this[6] + *((int *)this + 16));
  if ( v11 && *v11 )
  {
    if ( CachedPidlFromDisplayName != -2147024894 )
      goto LABEL_8;
    goto LABEL_5;
  }
  if ( CachedPidlFromDisplayName != -2147024894 )
  {
    v13 = this[16];
    WireEncoding = CFtpFolder::GetWireEncoding(this);
    CachedPidlFromDisplayName = CreateFtpPidlFromUrlEx(a4, WireEncoding, (int *)a5, (LPCITEMIDLIST *)a6, v13, 0, 0, 0);
    if ( CachedPidlFromDisplayName < 0 )
      return (unsigned int)CachedPidlFromDisplayName;
    v15 = this[16];
    v16 = *a6;
    *(_QWORD *)v24 = 0;
    CachedPidlFromDisplayName = SiteCache_PidlLookup(v16, 1, v15, (struct CFtpSite **)v24);
    if ( CachedPidlFromDisplayName < 0 )
      return (unsigned int)CachedPidlFromDisplayName;
    v17 = *(_QWORD *)v24;
    CFtpSite::UpdateHiddenPassword(*(CFtpSite **)v24, *a6);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    goto LABEL_21;
  }
LABEL_5:
  if ( !a3 )
    return (unsigned int)CachedPidlFromDisplayName;
  *(_DWORD *)v24 = 16;
  *(_QWORD *)&v24[4] = 0;
  v25 = 0;
  if ( ((int (__fastcall *)(struct IBindCtx *, _BYTE *))a3->lpVtbl->GetBindOptions)(a3, v24) < 0
    || (*(_WORD *)&v24[8] & 0x1000) == 0 )
  {
    return (unsigned int)CachedPidlFromDisplayName;
  }
LABEL_8:
  v12 = (_WORD *)((char *)this[6] + *((int *)this + 16));
  if ( v12
    && *v12
    && a4
    && (memset(&ppu, 0, sizeof(ppu)), ppu.cbSize = 40, ParseURLW(a4, &ppu) >= 0)
    && ppu.nScheme == 1
    || !PathIsRelativeW(a4) )
  {
    if ( *a6 )
      Pidl_Set(a6, 0);
    return (unsigned int)-2147467259;
  }
  FtpDir = CFtpFolder::GetFtpDir((CFtpFolder *)this);
  v20 = FtpDir;
  if ( !FtpDir )
    return (unsigned int)-2147024882;
  v21 = *((_QWORD *)FtpDir + 2);
  if ( v21 )
    v22 = *(_DWORD *)(v21 + 196);
  else
    v22 = 0;
  CachedPidlFromDisplayName = CreateFtpPidlFromDisplayPath(a4, v22, a5, a6, 0, 0);
  (*(void (__fastcall **)(struct CFtpDir *))(*(_QWORD *)v20 + 16LL))(v20);
  if ( CachedPidlFromDisplayName >= 0 )
    goto LABEL_21;
  return (unsigned int)CachedPidlFromDisplayName;
}

```

## disassembly

```asm
0x1800172a0  mov     [rsp-38h+arg_8], rbx
0x1800172a5  push    rbp
0x1800172a6  push    rsi
0x1800172a7  push    rdi
0x1800172a8  push    r12
0x1800172aa  push    r13
0x1800172ac  push    r14
0x1800172ae  push    r15
0x1800172b0  mov     rbp, rsp
0x1800172b3  sub     rsp, 80h
0x1800172ba  mov     rax, cs:__security_cookie
0x1800172c1  xor     rax, rsp
0x1800172c4  mov     [rbp+var_8], rax
0x1800172c8  mov     rsi, [rbp+arg_28]
0x1800172cc  mov     rbx, r8
0x1800172cf  mov     r13, [rbp+arg_20]
0x1800172d3  mov     r8, rsi; struct _ITEMIDLIST **
0x1800172d6  mov     r12, [rbp+arg_30]
0x1800172da  mov     rdx, r9; pszStart
0x1800172dd  mov     r15, r9
0x1800172e0  mov     r14, rcx
0x1800172e3  mov     qword ptr [rsi], 0
0x1800172ea  call    ?_GetCachedPidlFromDisplayName@CFtpFolder@@IEAAJPEBGPEAPEFAU_ITEMIDLIST@@@Z; CFtpFolder::_GetCachedPidlFromDisplayName(ushort const *,_ITEMIDLIST * *)
0x1800172ef  mov     edi, eax
0x1800172f1  test    eax, eax
0x1800172f3  jns     loc_18001744E
0x1800172f9  movsxd  rax, dword ptr [r14+40h]
0x1800172fd  xor     ecx, ecx
0x1800172ff  add     rax, [r14+30h]
0x180017303  jz      loc_1800173CA
0x180017309  cmp     [rax], cx
0x18001730c  jz      loc_1800173CA
0x180017312  cmp     edi, 80070002h
0x180017318  jnz     short loc_18001735B
0x18001731a  test    rbx, rbx
0x18001731d  jz      loc_18001747C
0x180017323  xor     eax, eax
0x180017325  mov     dword ptr [rbp+var_18], 10h
0x18001732c  mov     qword ptr [rbp+var_18+4], rax
0x180017330  lea     rdx, [rbp+var_18]
0x180017334  mov     [rbp+var_C], eax
0x180017337  mov     rcx, rbx
0x18001733a  mov     rax, [rbx]
0x18001733d  mov     rax, [rax+38h]
0x180017341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017346  test    eax, eax
0x180017348  js      loc_18001747C
0x18001734e  test    dword ptr [rbp+var_18+8], 1000h
0x180017355  jz      loc_18001747C
0x18001735b  movsxd  rdx, dword ptr [r14+40h]
0x18001735f  xor     edi, edi
0x180017361  add     rdx, [r14+30h]
0x180017365  jz      short loc_1800173A0
0x180017367  cmp     [rdx], di
0x18001736a  jz      short loc_1800173A0
0x18001736c  test    r15, r15
0x18001736f  jz      short loc_1800173A0
0x180017371  xorps   xmm0, xmm0
0x180017374  lea     rdx, [rbp+ppu]; ppu
0x180017378  xor     eax, eax
0x18001737a  mov     rcx, r15; pcszURL
0x18001737d  movups  xmmword ptr [rbp+ppu.cbSize], xmm0
0x180017381  mov     [rbp+ppu.cbSize], 28h ; '('
0x180017388  movups  xmmword ptr [rbp+ppu.cchProtocol], xmm0
0x18001738c  mov     qword ptr [rbp+ppu.cchSuffix], rax
0x180017390  call    cs:__imp_ParseURLW
0x180017396  test    eax, eax
0x180017398  js      short loc_1800173A0
0x18001739a  cmp     [rbp+ppu.nScheme], 1
0x18001739e  jz      short loc_1800173B1
0x1800173a0  mov     rcx, r15; pszPath
0x1800173a3  call    cs:__imp_PathIsRelativeW
0x1800173a9  test    eax, eax
0x1800173ab  jnz     loc_1800174A5
0x1800173b1  cmp     [rsi], rdi
0x1800173b4  jz      short loc_1800173C0
0x1800173b6  xor     edx, edx
0x1800173b8  mov     rcx, rsi
0x1800173bb  call    Pidl_Set
0x1800173c0  mov     edi, 80004005h
0x1800173c5  jmp     loc_18001747C
0x1800173ca  cmp     edi, 80070002h
0x1800173d0  jz      loc_18001731A
0x1800173d6  mov     rbx, [r14+80h]
0x1800173dd  mov     rcx, r14
0x1800173e0  call    ?GetWireEncoding@CFtpFolder@@QEAA?AW4WIREENC@@XZ; CFtpFolder::GetWireEncoding(void)
0x1800173e5  xor     ecx, ecx
0x1800173e7  mov     r9, rsi
0x1800173ea  mov     [rsp+80h+var_48], ecx
0x1800173ee  mov     r8, r13
0x1800173f1  mov     [rsp+80h+var_50], ecx
0x1800173f5  mov     edx, eax
0x1800173f7  mov     [rsp+80h+var_58], ecx
0x1800173fb  mov     rcx, r15
0x1800173fe  mov     [rsp+80h+var_60], rbx
0x180017403  call    ?CreateFtpPidlFromUrlEx@@YAJPEBGW4WIREENC@@PEAKPEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@HHH@Z; CreateFtpPidlFromUrlEx(ushort const *,WIREENC,ulong *,_ITEMIDLIST * *,IMalloc *,int,int,int)
0x180017408  xor     ebx, ebx
0x18001740a  mov     edi, eax
0x18001740c  test    eax, eax
0x18001740e  js      short loc_18001747C
0x180017410  mov     r8, [r14+80h]; struct IMalloc *
0x180017417  lea     r9, [rbp+var_18]; struct CFtpSite **
0x18001741b  mov     rcx, [rsi]; struct _ITEMIDLIST *
0x18001741e  lea     edx, [rbx+1]; int
0x180017421  mov     qword ptr [rbp+var_18], rbx
0x180017425  call    ?SiteCache_PidlLookup@@YAJPEFBU_ITEMIDLIST@@HPEAUIMalloc@@PEAPEAVCFtpSite@@@Z; SiteCache_PidlLookup(_ITEMIDLIST const *,int,IMalloc *,CFtpSite * *)
0x18001742a  mov     edi, eax
0x18001742c  test    eax, eax
0x18001742e  js      short loc_18001747C
0x180017430  mov     rbx, qword ptr [rbp+var_18]
0x180017434  mov     rdx, [rsi]; struct _ITEMIDLIST *
0x180017437  mov     rcx, rbx; this
0x18001743a  call    ?UpdateHiddenPassword@CFtpSite@@QEAAJPEFAU_ITEMIDLIST@@@Z; CFtpSite::UpdateHiddenPassword(_ITEMIDLIST *)
0x18001743f  mov     rax, [rbx]
0x180017442  mov     rcx, rbx
0x180017445  mov     rax, [rax+10h]
0x180017449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001744e  test    r12, r12
0x180017451  jz      short loc_18001747C
0x180017453  mov     rax, [r14]
0x180017456  mov     r9, r12
0x180017459  mov     r8, rsi
0x18001745c  mov     edx, 1
0x180017461  mov     rcx, r14
0x180017464  mov     rax, [rax+48h]
0x180017468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001746d  mov     edi, eax
0x18001746f  test    eax, eax
0x180017471  jns     short loc_18001747C
0x180017473  mov     rcx, [rsi]; pidl
0x180017476  call    cs:__imp_ILFree
0x18001747c  mov     eax, edi
0x18001747e  mov     rcx, [rbp+var_8]
0x180017482  xor     rcx, rsp; StackCookie
0x180017485  call    __security_check_cookie
0x18001748a  mov     rbx, [rsp+80h+arg_8]
0x180017492  add     rsp, 80h
0x180017499  pop     r15
0x18001749b  pop     r14
0x18001749d  pop     r13
0x18001749f  pop     r12
0x1800174a1  pop     rdi
0x1800174a2  pop     rsi
0x1800174a3  pop     rbp
0x1800174a4  retn
0x1800174a5  mov     rcx, r14; this
0x1800174a8  call    ?GetFtpDir@CFtpFolder@@QEAAPEAVCFtpDir@@XZ; CFtpFolder::GetFtpDir(void)
0x1800174ad  mov     rbx, rax
0x1800174b0  test    rax, rax
0x1800174b3  jz      short loc_1800174F8
0x1800174b5  mov     rax, [rax+10h]
0x1800174b9  test    rax, rax
0x1800174bc  jz      short loc_1800174C6
0x1800174be  mov     edx, [rax+0C4h]
0x1800174c4  jmp     short loc_1800174C8
0x1800174c6  mov     edx, edi
0x1800174c8  mov     [rsp+80h+var_58], edi
0x1800174cc  mov     r9, rsi
0x1800174cf  mov     r8, r13
0x1800174d2  mov     dword ptr [rsp+80h+var_60], edi
0x1800174d6  mov     rcx, r15
0x1800174d9  call    ?CreateFtpPidlFromDisplayPath@@YAJPEBGW4WIREENC@@PEAKPEAPEFAU_ITEMIDLIST@@HH@Z; CreateFtpPidlFromDisplayPath(ushort const *,WIREENC,ulong *,_ITEMIDLIST * *,int,int)
0x1800174de  mov     edi, eax
0x1800174e0  mov     rcx, rbx
0x1800174e3  mov     rax, [rbx]
0x1800174e6  mov     rax, [rax+10h]
0x1800174ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174ef  test    edi, edi
0x1800174f1  js      short loc_18001747C
0x1800174f3  jmp     loc_18001744E
0x1800174f8  mov     edi, 8007000Eh
0x1800174fd  jmp     loc_18001747C
```
