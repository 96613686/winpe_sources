# CreateNewFolder(HWND__ *,CFtpFolder *,CFtpDir *,IUnknown *,int,tagPOINT)

- ea: `0x1800222ec`
- end: `0x1800224e7`
- name: `?CreateNewFolder@@YAJPEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpDir@@PEAUIUnknown@@HUtagPOINT@@@Z`
- size: `507`
- prototype: `__int64 __fastcall(HWND, struct CFtpFolder *, struct CFtpDir *this, struct IUnknown *, int, struct tagPOINT)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000e4c0`

## callees

- `0x180002240`
- `0x18001168c`
- `0x180016b4c`
- `0x18001bf54`
- `0x1800222ec`
- `0x1800226f0`
- `0x180024134`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180022487`
- `SHELL32!__imp_ILFree` at `0x180022487`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180022425`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180022425`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x1800223d1`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x1800223d1`

## pseudocode

```c
__int64 __fastcall CreateNewFolder(
        HWND a1,
        struct CFtpFolder *a2,
        struct CFtpDir *this,
        struct IUnknown *a4,
        int a5,
        struct tagPOINT a6)
{
  struct CFtpDir *v6; // rdi
  struct CFtpDir *v8; // rsi
  int NewFolderName; // ebx
  struct CFtpDir *FtpDir; // rax
  int v13; // eax
  int v14; // edx
  unsigned int v15; // r9d
  __int64 v16; // rax
  int v17; // ecx
  ITEMIDLIST *v18; // rsi
  __int64 v19; // rax
  unsigned int v21; // [rsp+28h] [rbp-D8h]
  unsigned int v22; // [rsp+30h] [rbp-D0h]
  void *ppvOut; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST pidl; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v25[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v26[272]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[264]; // [rsp+170h] [rbp+70h] BYREF

  v6 = 0;
  v8 = this;
  if ( !this )
  {
    NewFolderName = -2147467259;
    FtpDir = CFtpFolder::GetFtpDir(a2);
    v6 = FtpDir;
    if ( !FtpDir )
      return (unsigned int)NewFolderName;
    v8 = FtpDir;
  }
  NewFolderName = _CreateNewFolderName(pszPath, (unsigned int)a2, v8);
  if ( NewFolderName >= 0 )
  {
    v25[0] = pszPath;
    v25[1] = a2;
    v13 = CFtpDir::WithHint(
            v8,
            0,
            a1,
            (int (*)(void *, struct HINTPROCINFO *, void *, int *))CreateNewFolderCB,
            v25,
            a4,
            a2);
    NewFolderName = v13;
    if ( v13 < 0 )
    {
      DisplayWininetError(a1, v14, v13, v15, 0x19Cu, v21, v22, 0);
      NewFolderName = -2147023673;
    }
    else
    {
      v16 = *((_QWORD *)v8 + 2);
      pidl = 0;
      if ( v16 )
        v17 = *(_DWORD *)(v16 + 196);
      else
        v17 = 0;
      SHUnicodeToAnsiCP(v17 != 0 ? 0xFDE9 : 0, pszPath, v26, 260);
      if ( (int)FtpItemID_CreateFake(pszPath, v26, 1, 0, 0, &pidl) >= 0 )
      {
        ppvOut = 0;
        IUnknown_QueryService(a4, (const GUID *const)&SID_DefView, &IID_IShellView2, &ppvOut);
        v18 = pidl;
        if ( ppvOut )
        {
          v19 = *(_QWORD *)ppvOut;
          if ( a5 )
            (*(void (__fastcall **)(void *, LPITEMIDLIST, __int64, struct tagPOINT *))(v19 + 152))(
              ppvOut,
              pidl,
              131,
              &a6);
          else
            (*(void (__fastcall **)(void *, LPITEMIDLIST, __int64))(v19 + 112))(ppvOut, pidl, 3);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
        }
        ILFree(v18);
      }
    }
  }
  if ( v6 )
    (*(void (__fastcall **)(struct CFtpDir *))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)NewFolderName;
}

```

## disassembly

```asm
0x1800222ec  push    rbp
0x1800222ee  push    rbx
0x1800222ef  push    rsi
0x1800222f0  push    rdi
0x1800222f1  push    r12
0x1800222f3  push    r14
0x1800222f5  push    r15
0x1800222f7  lea     rbp, [rsp-290h]
0x1800222ff  sub     rsp, 390h
0x180022306  mov     rax, cs:__security_cookie
0x18002230d  xor     rax, rsp
0x180022310  mov     [rbp+2C0h+var_40], rax
0x180022317  xor     edi, edi
0x180022319  mov     r12, r9
0x18002231c  mov     rsi, r8
0x18002231f  mov     r14, rdx
0x180022322  mov     r15, rcx
0x180022325  test    r8, r8
0x180022328  jnz     short loc_180022346
0x18002232a  mov     rcx, rdx; this
0x18002232d  mov     ebx, 80004005h
0x180022332  call    ?GetFtpDir@CFtpFolder@@QEAAPEAVCFtpDir@@XZ; CFtpFolder::GetFtpDir(void)
0x180022337  mov     rdi, rax
0x18002233a  test    rax, rax
0x18002233d  jz      loc_1800224C4
0x180022343  mov     rsi, rax
0x180022346  mov     r8, rsi; struct CFtpDir *
0x180022349  lea     rcx, [rbp+2C0h+pszPath]; unsigned __int16 *
0x18002234d  call    ?_CreateNewFolderName@@YAJPEAGKPEAVCFtpDir@@@Z; _CreateNewFolderName(ushort *,ulong,CFtpDir *)
0x180022352  mov     ebx, eax
0x180022354  test    eax, eax
0x180022356  js      loc_1800224B0
0x18002235c  lea     rax, [rbp+2C0h+pszPath]
0x180022360  mov     [rsp+3C0h+var_390], r14; unsigned int
0x180022365  mov     [rsp+3C0h+var_370], rax
0x18002236a  lea     r9, ?CreateNewFolderCB@@YAJPEAXPEAUHINTPROCINFO@@0PEAH@Z; int (*)(void *, struct HINTPROCINFO *, void *, int *)
0x180022371  lea     rax, [rsp+3C0h+var_370]
0x180022376  mov     [rsp+3C0h+var_398], r12; unsigned int
0x18002237b  mov     r8, r15; HWND
0x18002237e  mov     [rsp+3C0h+var_3A0], rax; void *
0x180022383  xor     edx, edx; struct CStatusBar *
0x180022385  mov     [rsp+3C0h+var_368], r14
0x18002238a  mov     rcx, rsi; this
0x18002238d  call    ?WithHint@CFtpDir@@QEAAJPEAVCStatusBar@@PEAUHWND__@@P6AJPEAXPEAUHINTPROCINFO@@2PEAH@ZPEBXPEAUIUnknown@@PEAVCFtpFolder@@@Z; CFtpDir::WithHint(CStatusBar *,HWND__ *,long (*)(void *,HINTPROCINFO *,void *,int *),void const *,IUnknown *,CFtpFolder *)
0x180022392  mov     ebx, eax
0x180022394  test    eax, eax
0x180022396  js      loc_18002248F
0x18002239c  mov     rax, [rsi+10h]
0x1800223a0  mov     [rsp+3C0h+pidl], 0
0x1800223a9  test    rax, rax
0x1800223ac  jz      short loc_1800223B6
0x1800223ae  mov     ecx, [rax+0C4h]
0x1800223b4  jmp     short loc_1800223B8
0x1800223b6  xor     ecx, ecx
0x1800223b8  neg     ecx
0x1800223ba  lea     r8, [rsp+3C0h+var_360]
0x1800223bf  mov     r9d, 104h
0x1800223c5  lea     rdx, [rbp+2C0h+pszPath]
0x1800223c9  sbb     ecx, ecx
0x1800223cb  and     ecx, 0FDE9h
0x1800223d1  call    cs:__imp_SHUnicodeToAnsiCP
0x1800223d7  xor     r9d, r9d; int
0x1800223da  lea     rax, [rsp+3C0h+pidl]
0x1800223df  mov     [rsp+3C0h+var_398], rax; struct _ITEMIDLIST **
0x1800223e4  lea     rdx, [rsp+3C0h+var_360]; char *
0x1800223e9  lea     rcx, [rbp+2C0h+pszPath]; pszPath
0x1800223ed  mov     dword ptr [rsp+3C0h+var_3A0], 0; int
0x1800223f5  lea     r8d, [r9+1]; int
0x1800223f9  call    ?FtpItemID_CreateFake@@YAJPEBGPEBDHHHPEAPEFAU_ITEMIDLIST@@@Z; FtpItemID_CreateFake(ushort const *,char const *,int,int,int,_ITEMIDLIST * *)
0x1800223fe  test    eax, eax
0x180022400  js      loc_1800224B0
0x180022406  lea     r9, [rsp+3C0h+ppvOut]; ppvOut
0x18002240b  mov     [rsp+3C0h+ppvOut], 0
0x180022414  lea     r8, IID_IShellView2; riid
0x18002241b  mov     rcx, r12; punk
0x18002241e  lea     rdx, SID_DefView; guidService
0x180022425  call    cs:__imp_IUnknown_QueryService
0x18002242b  mov     rcx, [rsp+3C0h+ppvOut]
0x180022430  mov     rsi, [rsp+3C0h+pidl]
0x180022435  test    rcx, rcx
0x180022438  jz      short loc_180022484
0x18002243a  cmp     [rbp+2C0h+arg_20], 0
0x180022441  mov     rdx, rsi
0x180022444  mov     rax, [rcx]
0x180022447  jz      short loc_180022464
0x180022449  mov     rax, [rax+98h]
0x180022450  lea     r9, [rbp+2C0h+arg_28]
0x180022457  mov     r8d, 83h
0x18002245d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022462  jmp     short loc_180022473
0x180022464  mov     rax, [rax+70h]
0x180022468  mov     r8d, 3
0x18002246e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022473  mov     rcx, [rsp+3C0h+ppvOut]
0x180022478  mov     rax, [rcx]
0x18002247b  mov     rax, [rax+10h]
0x18002247f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022484  mov     rcx, rsi; pidl
0x180022487  call    cs:__imp_ILFree
0x18002248d  jmp     short loc_1800224B0
0x18002248f  mov     [rsp+3C0h+var_388], 0; struct IProgressDialog *
0x180022498  mov     r8d, eax; int
0x18002249b  mov     rcx, r15; HWND
0x18002249e  mov     dword ptr [rsp+3C0h+var_3A0], 19Ch; unsigned int
0x1800224a6  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x1800224ab  mov     ebx, 800704C7h
0x1800224b0  test    rdi, rdi
0x1800224b3  jz      short loc_1800224C4
0x1800224b5  mov     rax, [rdi]
0x1800224b8  mov     rcx, rdi
0x1800224bb  mov     rax, [rax+10h]
0x1800224bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224c4  mov     eax, ebx
0x1800224c6  mov     rcx, [rbp+2C0h+var_40]
0x1800224cd  xor     rcx, rsp; StackCookie
0x1800224d0  call    __security_check_cookie
0x1800224d5  add     rsp, 390h
0x1800224dc  pop     r15
0x1800224de  pop     r14
0x1800224e0  pop     r12
0x1800224e2  pop     rdi
0x1800224e3  pop     rsi
0x1800224e4  pop     rbx
0x1800224e5  pop     rbp
0x1800224e6  retn
```
