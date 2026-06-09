# CFtpFolder::_GetCachedPidlFromDisplayName(ushort const *,_ITEMIDLIST * *)

- ea: `0x1800182c4`
- end: `0x180018560`
- name: `?_GetCachedPidlFromDisplayName@CFtpFolder@@IEAAJPEBGPEAPEFAU_ITEMIDLIST@@@Z`
- size: `668`
- prototype: `__int64 __fastcall(CFtpFolder *__hidden this, PCWSTR pszStart, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800172a0`

## callees

- `0x180002240`
- `0x1800112d4`
- `0x180016b4c`
- `0x1800170bc`
- `0x18001812c`
- `0x1800182c4`
- `0x18001b91c`
- `0x18001bda4`
- `0x18001ca1c`
- `0x18001f950`
- `0x18001fdb0`
- `0x18002009c`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x180018440`
- `SHELL32!__imp_ILFindLastID` at `0x180018440`
- `SHELL32!__imp_ILRemoveLastID` at `0x180018498`
- `SHELL32!__imp_ILRemoveLastID` at `0x180018498`
- `SHELL32!__imp_ILCombine` at `0x1800184d1`
- `SHELL32!__imp_ILCombine` at `0x1800184d1`
- `SHELL32!__imp_ILFree` at `0x1800184dd`
- `SHELL32!__imp_ILFree` at `0x180018531`
- `SHELL32!__imp_ILFree` at `0x1800184dd`
- `SHELL32!__imp_ILFree` at `0x180018531`
- `SHLWAPI!StrChrW` at `0x18001839f`
- `SHLWAPI!StrChrW` at `0x18001839f`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x180018378`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x180018378`

## pseudocode

```c
__int64 __fastcall CFtpFolder::_GetCachedPidlFromDisplayName(
        struct IMalloc **this,
        PCWSTR pszStart,
        struct _ITEMIDLIST **a3)
{
  unsigned int v6; // ebx
  struct CFtpDir *FtpDir; // rax
  CFtpDir *v8; // rdi
  __int64 v9; // r14
  __int64 v10; // rax
  int v11; // eax
  struct _ITEMIDLIST *PidlFromWireName; // rax
  struct IMalloc *v13; // rbx
  unsigned int WireEncoding; // eax
  ITEMIDLIST *v15; // rdi
  const struct _ITEMIDLIST *ID; // rax
  struct IMalloc *v17; // r8
  CFtpSite *v18; // r12
  const char *pszPath; // r13
  struct CFtpDir *v20; // r14
  const ITEMIDLIST *v21; // rax
  const unsigned __int16 *v22; // r9
  ITEMIDLIST *v23; // rbx
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  CFtpDir *v26; // [rsp+48h] [rbp-B8h] BYREF
  char v27[272]; // [rsp+50h] [rbp-B0h] BYREF

  v6 = -2147467259;
  if ( !a3 )
    return v6;
  FtpDir = CFtpFolder::GetFtpDir((CFtpFolder *)this);
  v26 = FtpDir;
  v8 = FtpDir;
  if ( FtpDir )
  {
    v9 = *((_QWORD *)FtpDir + 3);
    if ( v9 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 8LL))(*((_QWORD *)FtpDir + 3));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *a3 = 0;
      v10 = *((_QWORD *)v8 + 2);
      if ( v10 )
        v11 = *(_DWORD *)(v10 + 196);
      else
        v11 = 0;
      SHUnicodeToAnsiCP(v11 != 0 ? 0xFDE9 : 0, pszStart, v27, 260);
      PidlFromWireName = (struct _ITEMIDLIST *)CFtpDir::GetPidlFromWireName(v8, v27);
      *a3 = PidlFromWireName;
      if ( PidlFromWireName )
      {
        v6 = 0;
      }
      else if ( !StrChrW(pszStart, 0x2Fu) )
      {
        v6 = -2147024894;
      }
      (*(void (__fastcall **)(CFtpDir *))(*(_QWORD *)v8 + 16LL))(v8);
      return v6;
    }
    (*(void (__fastcall **)(struct CFtpDir *))(*(_QWORD *)FtpDir + 16LL))(FtpDir);
    v26 = 0;
  }
  *a3 = 0;
  v13 = this[16];
  pidl = 0;
  WireEncoding = CFtpFolder::GetWireEncoding(this);
  v6 = CreateFtpPidlFromUrlEx(pszStart, WireEncoding, 0, &pidl, v13, 0, 0, 0);
  if ( (v6 & 0x80000000) == 0 )
  {
    v15 = (ITEMIDLIST *)pidl;
    if ( pidl
      && pidl->mkid.cb
      && (ID = ILFindLastID(pidl), !(unsigned int)FtpID_IsServerItemID(ID))
      && (v17 = this[16], pidl = 0, (int)SiteCache_PidlLookup(v15, 1, v17, (struct CFtpSite **)&pidl) >= 0) )
    {
      v18 = (CFtpSite *)pidl;
      CFtpSite::UpdateHiddenPassword((CFtpSite *)pidl, v15);
      pszPath = FtpPidl_GetLastItemWireName(v15);
      ILRemoveLastID(v15);
      CFtpSite::GetFtpDir(v18, v15, &v26);
      v20 = v26;
      if ( v26 )
      {
        v21 = CFtpDir::GetPidlFromWireName(v26, pszPath);
        v23 = (ITEMIDLIST *)v21;
        if ( v21 )
        {
          *a3 = ILCombine(v15, v21);
          ILFree(v23);
          v6 = 0;
        }
        else
        {
          v6 = CFtpFolder::_ForPopulateAndEnum((CFtpFolder *)this, v20, v15, v22, pszPath, a3);
        }
        (*(void (__fastcall **)(struct CFtpDir *))(*(_QWORD *)v20 + 16LL))(v20);
      }
      else
      {
        v6 = -2147467259;
      }
      (*(void (__fastcall **)(CFtpSite *))(*(_QWORD *)v18 + 16LL))(v18);
    }
    else
    {
      v6 = -2147467259;
    }
    ILFree(v15);
  }
  return v6;
}

```

## disassembly

```asm
0x1800182c4  mov     [rsp-8+arg_18], rbx
0x1800182c9  push    rbp
0x1800182ca  push    rsi
0x1800182cb  push    rdi
0x1800182cc  push    r12
0x1800182ce  push    r13
0x1800182d0  push    r14
0x1800182d2  push    r15
0x1800182d4  lea     rbp, [rsp-70h]
0x1800182d9  sub     rsp, 170h
0x1800182e0  mov     rax, cs:__security_cookie
0x1800182e7  xor     rax, rsp
0x1800182ea  mov     [rbp+0A0h+var_40], rax
0x1800182ee  xor     r13d, r13d
0x1800182f1  mov     rsi, r8
0x1800182f4  mov     r12, rdx
0x1800182f7  mov     r15, rcx
0x1800182fa  mov     ebx, 80004005h
0x1800182ff  test    r8, r8
0x180018302  jz      loc_180018537
0x180018308  call    ?GetFtpDir@CFtpFolder@@QEAAPEAVCFtpDir@@XZ; CFtpFolder::GetFtpDir(void)
0x18001830d  mov     [rsp+1A0h+var_158], rax
0x180018312  mov     rdi, rax
0x180018315  test    rax, rax
0x180018318  jz      loc_1800183D8
0x18001831e  mov     r14, [rax+18h]
0x180018322  test    r14, r14
0x180018325  jz      loc_1800183C4
0x18001832b  mov     rax, [r14]
0x18001832e  mov     rcx, r14
0x180018331  mov     rax, [rax+8]
0x180018335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001833a  mov     rax, [r14]
0x18001833d  mov     rcx, r14
0x180018340  mov     rax, [rax+10h]
0x180018344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018349  mov     [rsi], r13
0x18001834c  mov     rax, [rdi+10h]
0x180018350  test    rax, rax
0x180018353  jz      short loc_18001835D
0x180018355  mov     eax, [rax+0C4h]
0x18001835b  jmp     short loc_180018360
0x18001835d  mov     eax, r13d
0x180018360  neg     eax
0x180018362  lea     r8, [rsp+1A0h+var_150]
0x180018367  mov     r9d, 104h
0x18001836d  mov     rdx, r12
0x180018370  sbb     ecx, ecx
0x180018372  and     ecx, 0FDE9h
0x180018378  call    cs:__imp_SHUnicodeToAnsiCP
0x18001837e  lea     rdx, [rsp+1A0h+var_150]; char *
0x180018383  mov     rcx, rdi; this
0x180018386  call    ?GetPidlFromWireName@CFtpDir@@QEAAPEFBU_ITEMIDLIST@@PEBD@Z; CFtpDir::GetPidlFromWireName(char const *)
0x18001838b  mov     [rsi], rax
0x18001838e  test    rax, rax
0x180018391  jz      short loc_180018398
0x180018393  mov     ebx, r13d
0x180018396  jmp     short loc_1800183B0
0x180018398  mov     dx, 2Fh ; '/'; wMatch
0x18001839c  mov     rcx, r12; pszStart
0x18001839f  call    cs:__imp_StrChrW
0x1800183a5  test    rax, rax
0x1800183a8  mov     ecx, 80070002h
0x1800183ad  cmovz   ebx, ecx
0x1800183b0  mov     rax, [rdi]
0x1800183b3  mov     rcx, rdi
0x1800183b6  mov     rax, [rax+10h]
0x1800183ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183bf  jmp     loc_180018537
0x1800183c4  mov     rax, [rax]
0x1800183c7  mov     rcx, rdi
0x1800183ca  mov     rax, [rax+10h]
0x1800183ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183d3  mov     [rsp+1A0h+var_158], r13
0x1800183d8  mov     rcx, rsi
0x1800183db  mov     rax, r13
0x1800183de  mov     [rcx], rax
0x1800183e1  mov     rcx, r15
0x1800183e4  mov     rbx, [r15+80h]
0x1800183eb  mov     [rsp+1A0h+pidl], r13
0x1800183f0  call    ?GetWireEncoding@CFtpFolder@@QEAA?AW4WIREENC@@XZ; CFtpFolder::GetWireEncoding(void)
0x1800183f5  mov     [rsp+1A0h+var_168], r13d
0x1800183fa  lea     r9, [rsp+1A0h+pidl]
0x1800183ff  mov     [rsp+1A0h+var_170], r13d
0x180018404  xor     r8d, r8d
0x180018407  mov     dword ptr [rsp+1A0h+var_178], r13d
0x18001840c  mov     edx, eax
0x18001840e  mov     rcx, r12
0x180018411  mov     [rsp+1A0h+pszPath], rbx
0x180018416  call    ?CreateFtpPidlFromUrlEx@@YAJPEBGW4WIREENC@@PEAKPEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@HHH@Z; CreateFtpPidlFromUrlEx(ushort const *,WIREENC,ulong *,_ITEMIDLIST * *,IMalloc *,int,int,int)
0x18001841b  mov     ebx, eax
0x18001841d  test    eax, eax
0x18001841f  js      loc_180018537
0x180018425  mov     rdi, [rsp+1A0h+pidl]
0x18001842a  test    rdi, rdi
0x18001842d  jz      loc_180018529
0x180018433  cmp     [rdi], r13w
0x180018437  jz      loc_180018529
0x18001843d  mov     rcx, rdi; pidl
0x180018440  call    cs:__imp_ILFindLastID
0x180018446  mov     rcx, rax; struct _ITEMIDLIST *
0x180018449  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001844e  test    eax, eax
0x180018450  jnz     loc_180018529
0x180018456  mov     r8, [r15+80h]; struct IMalloc *
0x18001845d  lea     r9, [rsp+1A0h+pidl]; struct CFtpSite **
0x180018462  lea     edx, [rax+1]; int
0x180018465  mov     [rsp+1A0h+pidl], r13
0x18001846a  mov     rcx, rdi; struct _ITEMIDLIST *
0x18001846d  call    ?SiteCache_PidlLookup@@YAJPEFBU_ITEMIDLIST@@HPEAUIMalloc@@PEAPEAVCFtpSite@@@Z; SiteCache_PidlLookup(_ITEMIDLIST const *,int,IMalloc *,CFtpSite * *)
0x180018472  test    eax, eax
0x180018474  js      loc_180018529
0x18001847a  mov     r12, [rsp+1A0h+pidl]
0x18001847f  mov     rdx, rdi; struct _ITEMIDLIST *
0x180018482  mov     rcx, r12; this
0x180018485  call    ?UpdateHiddenPassword@CFtpSite@@QEAAJPEFAU_ITEMIDLIST@@@Z; CFtpSite::UpdateHiddenPassword(_ITEMIDLIST *)
0x18001848a  mov     rcx, rdi; struct _ITEMIDLIST *
0x18001848d  call    ?FtpPidl_GetLastItemWireName@@YAPEBDPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetLastItemWireName(_ITEMIDLIST const *)
0x180018492  mov     rcx, rdi; pidl
0x180018495  mov     r13, rax
0x180018498  call    cs:__imp_ILRemoveLastID
0x18001849e  lea     r8, [rsp+1A0h+var_158]; struct CFtpDir **
0x1800184a3  mov     rdx, rdi; struct _ITEMIDLIST *
0x1800184a6  mov     rcx, r12; this
0x1800184a9  call    ?GetFtpDir@CFtpSite@@QEAAJPEFBU_ITEMIDLIST@@PEAPEAVCFtpDir@@@Z; CFtpSite::GetFtpDir(_ITEMIDLIST const *,CFtpDir * *)
0x1800184ae  mov     r14, [rsp+1A0h+var_158]
0x1800184b3  test    r14, r14
0x1800184b6  jz      short loc_180018512
0x1800184b8  mov     rdx, r13; char *
0x1800184bb  mov     rcx, r14; this
0x1800184be  call    ?GetPidlFromWireName@CFtpDir@@QEAAPEFBU_ITEMIDLIST@@PEBD@Z; CFtpDir::GetPidlFromWireName(char const *)
0x1800184c3  mov     rbx, rax
0x1800184c6  test    rax, rax
0x1800184c9  jz      short loc_1800184E7
0x1800184cb  mov     rdx, rax; pidl2
0x1800184ce  mov     rcx, rdi; pidl1
0x1800184d1  call    cs:__imp_ILCombine
0x1800184d7  mov     rcx, rbx; pidl
0x1800184da  mov     [rsi], rax
0x1800184dd  call    cs:__imp_ILFree
0x1800184e3  xor     ebx, ebx
0x1800184e5  jmp     short loc_180018501
0x1800184e7  mov     [rsp+1A0h+var_178], rsi; struct _ITEMIDLIST **
0x1800184ec  mov     r8, rdi; pidl1
0x1800184ef  mov     rdx, r14; struct CFtpDir *
0x1800184f2  mov     [rsp+1A0h+pszPath], r13; pszPath
0x1800184f7  mov     rcx, r15; this
0x1800184fa  call    ?_ForPopulateAndEnum@CFtpFolder@@IEAAJPEAVCFtpDir@@PEFBU_ITEMIDLIST@@PEBGPEBDPEAPEFAU3@@Z; CFtpFolder::_ForPopulateAndEnum(CFtpDir *,_ITEMIDLIST const *,ushort const *,char const *,_ITEMIDLIST * *)
0x1800184ff  mov     ebx, eax
0x180018501  mov     rax, [r14]
0x180018504  mov     rcx, r14
0x180018507  mov     rax, [rax+10h]
0x18001850b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018510  jmp     short loc_180018517
0x180018512  mov     ebx, 80004005h
0x180018517  mov     rax, [r12]
0x18001851b  mov     rcx, r12
0x18001851e  mov     rax, [rax+10h]
0x180018522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018527  jmp     short loc_18001852E
0x180018529  mov     ebx, 80004005h
0x18001852e  mov     rcx, rdi; pidl
0x180018531  call    cs:__imp_ILFree
0x180018537  mov     eax, ebx
0x180018539  mov     rcx, [rbp+0A0h+var_40]
0x18001853d  xor     rcx, rsp; StackCookie
0x180018540  call    __security_check_cookie
0x180018545  mov     rbx, [rsp+1A0h+arg_18]
0x18001854d  add     rsp, 170h
0x180018554  pop     r15
0x180018556  pop     r14
0x180018558  pop     r13
0x18001855a  pop     r12
0x18001855c  pop     rdi
0x18001855d  pop     rsi
0x18001855e  pop     rbp
0x18001855f  retn
```
