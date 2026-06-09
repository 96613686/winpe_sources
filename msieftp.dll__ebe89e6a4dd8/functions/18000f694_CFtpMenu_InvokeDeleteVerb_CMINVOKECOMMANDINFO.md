# CFtpMenu::_InvokeDeleteVerb(_CMINVOKECOMMANDINFO *)

- ea: `0x18000f694`
- end: `0x18000f9eb`
- name: `?_InvokeDeleteVerb@CFtpMenu@@IEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `855`
- prototype: `__int64 __fastcall(CFtpMenu *__hidden this, struct _CMINVOKECOMMANDINFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e4c0`

## callees

- `0x180002240`
- `0x18000f694`
- `0x180011ae8`
- `0x18001e1cc`
- `0x18001fa30`
- `0x18001fc24`
- `0x180023340`
- `0x180023ce4`
- `0x180024134`
- `0x180025bac`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x18000f748`
- `SHELL32!__imp_ILClone` at `0x18000f748`
- `SHELL32!__imp_ILFree` at `0x18000f975`
- `SHELL32!__imp_ILFree` at `0x18000f975`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000f81a`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000f81a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000f865`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000f865`
- `USER32!SetCursor` at `0x18000f7f6`
- `USER32!SetCursor` at `0x18000f980`
- `USER32!SetCursor` at `0x18000f7f6`
- `USER32!SetCursor` at `0x18000f980`
- `USER32!LoadCursorW` at `0x18000f7ed`
- `USER32!LoadCursorW` at `0x18000f7ed`

## pseudocode

```c
__int64 __fastcall CFtpMenu::_InvokeDeleteVerb(
        CFtpMenu *this,
        struct _CMINVOKECOMMANDINFO *a2,
        __int64 a3,
        unsigned int a4)
{
  HWND v4; // r12
  unsigned int v7; // ebx
  HWND hwnd; // rcx
  unsigned int v9; // eax
  unsigned int v10; // eax
  HWND *CStatusBarFromDefViewSite; // r13
  struct IProgressDialog *Instance; // rsi
  ITEMIDLIST *v13; // rax
  struct CFtpFolder *v14; // rdx
  const struct _ITEMIDLIST *v15; // r14
  HWND v16; // rcx
  __int64 v17; // r8
  CFtpSite *v18; // rcx
  HCURSOR CursorW; // rax
  IUnknown *v20; // rcx
  HWND v21; // rdx
  int v22; // edx
  unsigned int v23; // r9d
  const struct _ITEMIDLIST *v24; // rdx
  __int64 v25; // rdx
  struct GLOBALTIMEOUTINFO **v26; // rcx
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  unsigned int v29; // [rsp+28h] [rbp-D8h]
  unsigned int v30; // [rsp+30h] [rbp-D0h]
  unsigned int v31; // [rsp+30h] [rbp-D0h]
  HWND phwnd; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST pidl; // [rsp+48h] [rbp-B8h]
  HCURSOR hCursor; // [rsp+50h] [rbp-B0h]
  _QWORD v35[4]; // [rsp+60h] [rbp-A0h] BYREF
  HWND v36; // [rsp+80h] [rbp-80h]
  HWND *v37; // [rsp+88h] [rbp-78h]
  struct IProgressDialog *v38; // [rsp+90h] [rbp-70h]
  __int64 v39; // [rsp+98h] [rbp-68h]
  __int64 v40; // [rsp+A0h] [rbp-60h]
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF

  v4 = 0;
  v7 = 0;
  if ( *((_QWORD *)this + 6) )
  {
    if ( (*((_BYTE *)this + 24) & 0x20) == 0 )
    {
      v7 = -2147024891;
      DisplayWininetError(a2->hwnd, (int)a2, -2147024891, a4, 0x199u, v28, v30, 0);
      return v7;
    }
    if ( (a2->fMask & 0x400) == 0 )
    {
      hwnd = a2->hwnd;
      if ( !hwnd )
        hwnd = (HWND)*((_QWORD *)this + 7);
      v9 = FtpConfirmDeleteDialog(hwnd, *((struct CFtpPidlList **)this + 4), *((struct CFtpFolder **)this + 5)) - 2;
      if ( !v9 )
        return (unsigned int)-2147023673;
      v10 = v9 - 4;
      if ( v10 )
      {
        if ( v10 == 1 )
          return 1;
        return (unsigned int)-2147023673;
      }
    }
    CStatusBarFromDefViewSite = (HWND *)GetCStatusBarFromDefViewSite(*((struct IUnknown **)this + 2));
    Instance = CProgressDialog_CreateInstance(0x4Cu);
    v13 = ILClone(*(LPCITEMIDLIST *)(*((_QWORD *)this + 6) + 48LL));
    v14 = (struct CFtpFolder *)*((_QWORD *)this + 5);
    v15 = v13;
    v16 = a2->hwnd;
    pidl = v13;
    v35[0] = v13;
    v35[1] = v14;
    v35[2] = *((_QWORD *)v14 + 16);
    v35[3] = a2;
    if ( v16 )
      v36 = v16;
    else
      v36 = (HWND)*((_QWORD *)this + 7);
    v17 = *((_QWORD *)this + 6);
    v37 = CStatusBarFromDefViewSite;
    v38 = Instance;
    v39 = 0;
    v40 = 0;
    v18 = *(CFtpSite **)(v17 + 16);
    phwnd = 0;
    if ( v18 )
    {
      CFtpSite::GetHint(
        v18,
        0,
        *(const struct _ITEMIDLIST **)(v17 + 40),
        0,
        (void **)&phwnd,
        *((struct IUnknown **)this + 2),
        v14);
      v4 = phwnd;
      if ( phwnd )
      {
        CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
        hCursor = SetCursor(CursorW);
        if ( Instance )
        {
          v20 = (IUnknown *)*((_QWORD *)this + 2);
          phwnd = 0;
          IUnknown_GetWindow(v20, &phwnd);
          v21 = phwnd;
          if ( !phwnd )
          {
            v21 = (HWND)*((_QWORD *)this + 7);
            phwnd = v21;
          }
          ((void (__fastcall *)(struct IProgressDialog *, HWND, _QWORD, __int64, _QWORD))Instance->lpVtbl->SetAnimation)(
            Instance,
            v21,
            0,
            2,
            0);
          if ( LoadStringW(g_hinst, 0x121u, Buffer, 260) )
            ((void (__fastcall *)(struct IProgressDialog *, __int64, WCHAR *))Instance->lpVtbl[1].StartProgressDialog)(
              Instance,
              2,
              Buffer);
        }
        v7 = CFtpPidlList::RecursiveEnum(
               *((CFtpPidlList **)this + 4),
               v15,
               (int (*)(void *, void *, const struct _ITEMIDLIST *, int *, void *))DeleteItemCB,
               v4,
               v35);
        if ( Instance )
          ((void (__fastcall *)(struct IProgressDialog *, __int64))Instance->lpVtbl[1].SetTitle)(Instance, 1);
        LODWORD(v40) = 1;
        if ( v7 != -2147023673 )
        {
          v24 = pidl;
          *(_DWORD *)(*((_QWORD *)this + 4) + 28LL) = 0;
          v7 = CFtpPidlList::RecursiveEnum(
                 *((CFtpPidlList **)this + 4),
                 v24,
                 (int (*)(void *, void *, const struct _ITEMIDLIST *, int *, void *))DeleteItemCB,
                 v4,
                 v35);
        }
        if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023673 )
        {
          DisplayWininetError(a2->hwnd, v22, v7, v23, 0x199u, v29, v31, Instance);
          v7 = -2147023673;
        }
        if ( CStatusBarFromDefViewSite )
          CStatusBar::SetStatusMessage(CStatusBarFromDefViewSite, 0x40u, 0);
        if ( Instance )
        {
          ((void (__fastcall *)(struct IProgressDialog *))Instance->lpVtbl->HasUserCancelled)(Instance);
          ((void (__fastcall *)(struct IProgressDialog *))Instance->lpVtbl->SetTitle)(Instance);
        }
        ILFree(pidl);
        SetCursor(hCursor);
      }
    }
    v25 = *((_QWORD *)this + 6);
    v26 = *(struct GLOBALTIMEOUTINFO ***)(v25 + 16);
    if ( v26 )
      CFtpSite::ReleaseHint(v26, *(const struct _ITEMIDLIST **)(v25 + 40), (struct GLOBALTIMEOUTINFO *)v4);
  }
  return v7;
}

```

## disassembly

```asm
0x18000f694  mov     [rsp-8+arg_10], rbx
0x18000f699  push    rbp
0x18000f69a  push    rsi
0x18000f69b  push    rdi
0x18000f69c  push    r12
0x18000f69e  push    r13
0x18000f6a0  push    r14
0x18000f6a2  push    r15
0x18000f6a4  lea     rbp, [rsp-1D0h]
0x18000f6ac  sub     rsp, 2D0h
0x18000f6b3  mov     rax, cs:__security_cookie
0x18000f6ba  xor     rax, rsp
0x18000f6bd  mov     [rbp+200h+var_40], rax
0x18000f6c4  xor     r12d, r12d
0x18000f6c7  mov     r15, rdx
0x18000f6ca  mov     rdi, rcx
0x18000f6cd  mov     ebx, r12d
0x18000f6d0  cmp     [rcx+30h], r12
0x18000f6d4  jz      loc_18000F9BF
0x18000f6da  test    byte ptr [rcx+18h], 20h
0x18000f6de  jz      loc_18000F9A1
0x18000f6e4  test    dword ptr [rdx+4], 400h
0x18000f6eb  jnz     short loc_18000F727
0x18000f6ed  mov     rcx, [rdx+8]
0x18000f6f1  test    rcx, rcx
0x18000f6f4  jnz     short loc_18000F6FA
0x18000f6f6  mov     rcx, [rdi+38h]; HWND
0x18000f6fa  mov     r8, [rdi+28h]; struct CFtpFolder *
0x18000f6fe  mov     rdx, [rdi+20h]; struct CFtpPidlList *
0x18000f702  call    ?FtpConfirmDeleteDialog@@YAIPEAUHWND__@@PEAVCFtpPidlList@@PEAVCFtpFolder@@@Z; FtpConfirmDeleteDialog(HWND__ *,CFtpPidlList *,CFtpFolder *)
0x18000f707  sub     eax, 2
0x18000f70a  jz      short loc_18000F71D
0x18000f70c  sub     eax, 4
0x18000f70f  jz      short loc_18000F727
0x18000f711  cmp     eax, 1
0x18000f714  jnz     short loc_18000F71D
0x18000f716  mov     ebx, eax
0x18000f718  jmp     loc_18000F9BF
0x18000f71d  mov     ebx, 800704C7h
0x18000f722  jmp     loc_18000F9BF
0x18000f727  mov     rcx, [rdi+10h]; struct IUnknown *
0x18000f72b  call    ?GetCStatusBarFromDefViewSite@@YAPEAVCStatusBar@@PEAUIUnknown@@@Z; GetCStatusBarFromDefViewSite(IUnknown *)
0x18000f730  mov     ecx, 4Ch ; 'L'; uID
0x18000f735  mov     r13, rax
0x18000f738  call    ?CProgressDialog_CreateInstance@@YAPEAUIProgressDialog@@II@Z; CProgressDialog_CreateInstance(uint,uint)
0x18000f73d  mov     rcx, [rdi+30h]
0x18000f741  mov     rsi, rax
0x18000f744  mov     rcx, [rcx+30h]; pidl
0x18000f748  call    cs:__imp_ILClone
0x18000f74e  mov     rdx, [rdi+28h]
0x18000f752  mov     r14, rax
0x18000f755  mov     rcx, [r15+8]
0x18000f759  mov     [rsp+300h+pidl], rax
0x18000f75e  mov     [rsp+300h+var_2A0], rax
0x18000f763  mov     [rsp+300h+var_298], rdx
0x18000f768  mov     rax, [rdx+80h]
0x18000f76f  mov     [rsp+300h+var_290], rax
0x18000f774  mov     [rsp+300h+var_288], r15
0x18000f779  test    rcx, rcx
0x18000f77c  jz      short loc_18000F784
0x18000f77e  mov     [rbp+200h+var_280], rcx
0x18000f782  jmp     short loc_18000F78C
0x18000f784  mov     rax, [rdi+38h]
0x18000f788  mov     [rbp+200h+var_280], rax
0x18000f78c  mov     r8, [rdi+30h]
0x18000f790  mov     [rbp+200h+var_278], r13
0x18000f794  mov     [rbp+200h+var_270], rsi
0x18000f798  mov     [rbp+200h+var_268], r12
0x18000f79c  mov     [rbp+200h+var_260], r12
0x18000f7a0  mov     rcx, [r8+10h]; this
0x18000f7a4  mov     [rsp+300h+phwnd], r12
0x18000f7a9  test    rcx, rcx
0x18000f7ac  jz      loc_18000F986
0x18000f7b2  mov     rax, [rdi+10h]
0x18000f7b6  xor     r9d, r9d; struct CStatusBar *
0x18000f7b9  mov     r8, [r8+28h]; struct _ITEMIDLIST *
0x18000f7bd  mov     [rsp+300h+var_2D0], rdx; unsigned int
0x18000f7c2  xor     edx, edx; HWND
0x18000f7c4  mov     [rsp+300h+var_2D8], rax; unsigned int
0x18000f7c9  lea     rax, [rsp+300h+phwnd]
0x18000f7ce  mov     [rsp+300h+var_2E0], rax; void **
0x18000f7d3  call    ?GetHint@CFtpSite@@QEAAJPEAUHWND__@@PEFBU_ITEMIDLIST@@PEAVCStatusBar@@PEAPEAXPEAUIUnknown@@PEAVCFtpFolder@@@Z; CFtpSite::GetHint(HWND__ *,_ITEMIDLIST const *,CStatusBar *,void * *,IUnknown *,CFtpFolder *)
0x18000f7d8  mov     r12, [rsp+300h+phwnd]
0x18000f7dd  test    r12, r12
0x18000f7e0  jz      loc_18000F986
0x18000f7e6  mov     edx, 7F02h; lpCursorName
0x18000f7eb  xor     ecx, ecx; hInstance
0x18000f7ed  call    cs:__imp_LoadCursorW
0x18000f7f3  mov     rcx, rax; hCursor
0x18000f7f6  call    cs:__imp_SetCursor
0x18000f7fc  xor     ebx, ebx
0x18000f7fe  mov     [rsp+300h+hCursor], rax
0x18000f803  test    rsi, rsi
0x18000f806  jz      loc_18000F88E
0x18000f80c  mov     rcx, [rdi+10h]; punk
0x18000f810  lea     rdx, [rsp+300h+phwnd]; phwnd
0x18000f815  mov     [rsp+300h+phwnd], rbx
0x18000f81a  call    cs:__imp_IUnknown_GetWindow
0x18000f820  mov     rdx, [rsp+300h+phwnd]
0x18000f825  test    rdx, rdx
0x18000f828  jnz     short loc_18000F833
0x18000f82a  mov     rdx, [rdi+38h]
0x18000f82e  mov     [rsp+300h+phwnd], rdx
0x18000f833  mov     rax, [rsi]
0x18000f836  mov     r9d, 2
0x18000f83c  xor     r8d, r8d
0x18000f83f  mov     [rsp+300h+var_2E0], rbx
0x18000f844  mov     rcx, rsi
0x18000f847  mov     rax, [rax+18h]
0x18000f84b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f850  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000f857  lea     r8, [rbp+200h+Buffer]; lpBuffer
0x18000f85b  mov     r9d, 104h; cchBufferMax
0x18000f861  lea     edx, [r9+1Dh]; uID
0x18000f865  call    cs:__imp_LoadStringW
0x18000f86b  test    eax, eax
0x18000f86d  jz      short loc_18000F88E
0x18000f86f  mov     rax, [rsi]
0x18000f872  lea     r8, [rbp+200h+Buffer]
0x18000f876  xor     r9d, r9d
0x18000f879  mov     [rsp+300h+var_2E0], rbx
0x18000f87e  mov     rcx, rsi
0x18000f881  mov     rax, [rax+50h]
0x18000f885  lea     edx, [r9+2]
0x18000f889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f88e  mov     rcx, [rdi+20h]; this
0x18000f892  lea     rax, [rsp+300h+var_2A0]
0x18000f897  mov     r9, r12; void *
0x18000f89a  mov     [rsp+300h+var_2E0], rax; void *
0x18000f89f  lea     r8, ?DeleteItemCB@@YAJPEAX0PEFBU_ITEMIDLIST@@PEAH0@Z; int (*)(void *, void *, const struct _ITEMIDLIST *, int *, void *)
0x18000f8a6  mov     rdx, r14; struct _ITEMIDLIST *
0x18000f8a9  call    ?RecursiveEnum@CFtpPidlList@@QEAAJPEFBU_ITEMIDLIST@@P6AJPEAX10PEAH1@Z11@Z; CFtpPidlList::RecursiveEnum(_ITEMIDLIST const *,long (*)(void *,void *,_ITEMIDLIST const *,int *,void *),void *,void *)
0x18000f8ae  mov     ebx, eax
0x18000f8b0  test    rsi, rsi
0x18000f8b3  jz      short loc_18000F8CB
0x18000f8b5  mov     rcx, [rsi]
0x18000f8b8  xor     r8d, r8d
0x18000f8bb  mov     rax, [rcx+60h]
0x18000f8bf  lea     edx, [r8+1]
0x18000f8c3  mov     rcx, rsi
0x18000f8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8cb  mov     r14d, 800704C7h
0x18000f8d1  mov     dword ptr [rbp+200h+var_260], 1
0x18000f8d8  cmp     ebx, r14d
0x18000f8db  jz      short loc_18000F90C
0x18000f8dd  mov     rax, [rdi+20h]
0x18000f8e1  lea     r8, ?DeleteItemCB@@YAJPEAX0PEFBU_ITEMIDLIST@@PEAH0@Z; int (*)(void *, void *, const struct _ITEMIDLIST *, int *, void *)
0x18000f8e8  mov     rdx, [rsp+300h+pidl]; struct _ITEMIDLIST *
0x18000f8ed  mov     r9, r12; void *
0x18000f8f0  mov     dword ptr [rax+1Ch], 0
0x18000f8f7  lea     rax, [rsp+300h+var_2A0]
0x18000f8fc  mov     rcx, [rdi+20h]; this
0x18000f900  mov     [rsp+300h+var_2E0], rax; void *
0x18000f905  call    ?RecursiveEnum@CFtpPidlList@@QEAAJPEFBU_ITEMIDLIST@@P6AJPEAX10PEAH1@Z11@Z; CFtpPidlList::RecursiveEnum(_ITEMIDLIST const *,long (*)(void *,void *,_ITEMIDLIST const *,int *,void *),void *,void *)
0x18000f90a  mov     ebx, eax
0x18000f90c  mov     ecx, 80000000h
0x18000f911  lea     eax, [rbx+rcx]
0x18000f914  test    ecx, eax
0x18000f916  jnz     short loc_18000F939
0x18000f918  cmp     ebx, r14d
0x18000f91b  jz      short loc_18000F939
0x18000f91d  mov     rcx, [r15+8]; HWND
0x18000f921  mov     r8d, ebx; int
0x18000f924  mov     [rsp+300h+var_2C8], rsi; struct IProgressDialog *
0x18000f929  mov     dword ptr [rsp+300h+var_2E0], 199h; unsigned int
0x18000f931  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x18000f936  mov     ebx, r14d
0x18000f939  test    r13, r13
0x18000f93c  jz      short loc_18000F94D
0x18000f93e  xor     r8d, r8d; unsigned __int16 *
0x18000f941  mov     rcx, r13; this
0x18000f944  lea     edx, [r8+40h]; unsigned int
0x18000f948  call    ?SetStatusMessage@CStatusBar@@QEAAXIPEBG@Z; CStatusBar::SetStatusMessage(uint,ushort const *)
0x18000f94d  test    rsi, rsi
0x18000f950  jz      short loc_18000F970
0x18000f952  mov     rax, [rsi]
0x18000f955  mov     rcx, rsi
0x18000f958  mov     rax, [rax+20h]
0x18000f95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f961  mov     rax, [rsi]
0x18000f964  mov     rcx, rsi
0x18000f967  mov     rax, [rax+10h]
0x18000f96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f970  mov     rcx, [rsp+300h+pidl]; pidl
0x18000f975  call    cs:__imp_ILFree
0x18000f97b  mov     rcx, [rsp+300h+hCursor]; hCursor
0x18000f980  call    cs:__imp_SetCursor
0x18000f986  mov     rdx, [rdi+30h]
0x18000f98a  mov     rcx, [rdx+10h]; this
0x18000f98e  test    rcx, rcx
0x18000f991  jz      short loc_18000F9BF
0x18000f993  mov     rdx, [rdx+28h]; struct _ITEMIDLIST *
0x18000f997  mov     r8, r12; void *
0x18000f99a  call    ?ReleaseHint@CFtpSite@@QEAAXPEFBU_ITEMIDLIST@@PEAX@Z; CFtpSite::ReleaseHint(_ITEMIDLIST const *,void *)
0x18000f99f  jmp     short loc_18000F9BF
0x18000f9a1  mov     rcx, [rdx+8]; HWND
0x18000f9a5  mov     ebx, 80070005h
0x18000f9aa  mov     r8d, ebx; int
0x18000f9ad  mov     [rsp+300h+var_2C8], r12; struct IProgressDialog *
0x18000f9b2  mov     dword ptr [rsp+300h+var_2E0], 199h; unsigned int
0x18000f9ba  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x18000f9bf  mov     eax, ebx
0x18000f9c1  mov     rcx, [rbp+200h+var_40]
0x18000f9c8  xor     rcx, rsp; StackCookie
0x18000f9cb  call    __security_check_cookie
0x18000f9d0  mov     rbx, [rsp+300h+arg_10]
0x18000f9d8  add     rsp, 2D0h
0x18000f9df  pop     r15
0x18000f9e1  pop     r14
0x18000f9e3  pop     r13
0x18000f9e5  pop     r12
0x18000f9e7  pop     rdi
0x18000f9e8  pop     rsi
0x18000f9e9  pop     rbp
0x18000f9ea  retn
```
