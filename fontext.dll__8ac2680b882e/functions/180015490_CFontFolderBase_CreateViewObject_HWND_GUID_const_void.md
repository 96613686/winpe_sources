# CFontFolderBase::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180015490`
- end: `0x1800156ba`
- name: `?CreateViewObject@CFontFolderBase@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `554`
- prototype: `int(CFontFolderBase *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800128fc`
- `0x180015490`
- `0x18001c0d0`
- `0x180032010`

## import_xrefs

- `SHELL32!__imp_SHCreateShellFolderView` at `0x18001559e`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x18001559e`
- `SHELL32!__imp_CDefFolderMenu_Create2` at `0x180015666`
- `SHELL32!__imp_CDefFolderMenu_Create2` at `0x180015666`

## pseudocode

```c
__int64 __fastcall CFontFolderBase::CreateViewObject(
        unsigned __int64 this,
        struct IShellFolderViewCB *a2,
        const struct _GUID *a3,
        IShellView **ppcm)
{
  __int64 v6; // rax
  IShellFolderViewCB *v7; // rax
  char *v8; // rdi
  IShellFolderViewCB *v9; // rbx
  void (__fastcall **v10)(char *, GUID *, IShellFolder **); // rax
  void (__fastcall *v11)(char *, GUID *, IShellFolder **); // rax
  unsigned int v12; // ebx
  __int64 v13; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  SFV_CREATE pcsfv; // [rsp+50h] [rbp-28h] BYREF

  *ppcm = 0;
  v6 = *(_QWORD *)&IID_IShellView.Data1 - *(_QWORD *)&a3->Data1;
  if ( *(_QWORD *)&IID_IShellView.Data1 == *(_QWORD *)&a3->Data1 )
    v6 = *(_QWORD *)IID_IShellView.Data4 - *(_QWORD *)a3->Data4;
  if ( !v6 )
  {
    v7 = (IShellFolderViewCB *)DirectUI::HAllocAndZero((DirectUI *)0x50, (unsigned __int64)a2);
    v8 = (char *)(this - 40);
    v9 = v7;
    if ( v7 )
    {
      LODWORD(v7[3].lpVtbl) = 1;
      v7->lpVtbl = (struct IShellFolderViewCBVtbl *)&CFontFolderViewCallback::`vftable'{for `IShellFolderViewCB'};
      v7[4].lpVtbl = (struct IShellFolderViewCBVtbl *)v8;
      v7[1].lpVtbl = (struct IShellFolderViewCBVtbl *)&CFontFolderViewCallback::`vftable'{for `IFolderViewSettings'};
      v7[2].lpVtbl = (struct IShellFolderViewCBVtbl *)&CFontFolderViewCallback::`vftable'{for `IObjectWithSite'};
      v7[5].lpVtbl = 0;
      v7[6].lpVtbl = 0;
      v7[7].lpVtbl = 0;
      LOBYTE(v7[8].lpVtbl) = 1;
      v7[9].lpVtbl = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
      _InterlockedIncrement(&g_cRefCount);
    }
    else
    {
      v9 = 0;
    }
    if ( v9 )
    {
      v10 = *(void (__fastcall ***)(char *, GUID *, IShellFolder **))v8;
      memset(&pcsfv.cbSize + 1, 0, 20);
      pcsfv.cbSize = 32;
      v11 = *v10;
      pcsfv.psfvcb = v9;
      v11(v8, &IID_IShellFolder, &pcsfv.pshf);
      v12 = SHCreateShellFolderView(&pcsfv, ppcm);
      if ( pcsfv.psfvcb )
        ((void (__fastcall *)(IShellFolderViewCB *))pcsfv.psfvcb->lpVtbl[2].MessageSFVCB)(pcsfv.psfvcb);
      if ( pcsfv.pshf )
        ((void (__fastcall *)(IShellFolder *))pcsfv.pshf->lpVtbl->Release)(pcsfv.pshf);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
    return v12;
  }
  v13 = *(_QWORD *)&IID_IDropTarget.Data1 - *(_QWORD *)&a3->Data1;
  if ( *(_QWORD *)&IID_IDropTarget.Data1 == *(_QWORD *)&a3->Data1 )
    v13 = *(_QWORD *)IID_IDropTarget.Data4 - *(_QWORD *)a3->Data4;
  if ( !v13 )
    return (unsigned int)CFontFolderDropTarget::CreateInstance((HWND)a2, a2, a3, (void **)ppcm);
  v15 = *(_QWORD *)&IID_IContextMenu.Data1 - *(_QWORD *)&a3->Data1;
  if ( *(_QWORD *)&IID_IContextMenu.Data1 == *(_QWORD *)&a3->Data1 )
    v15 = *(_QWORD *)IID_IContextMenu.Data4 - *(_QWORD *)a3->Data4;
  if ( !v15 )
    return (unsigned int)CDefFolderMenu_Create2(
                           0,
                           (HWND)a2,
                           0,
                           0,
                           (IShellFolder *)(this & -(__int64)(this != 40)),
                           CFontFolderBase::s_ViewContextMenuCB,
                           0,
                           0,
                           (IContextMenu **)ppcm);
  v12 = -2147467262;
  v16 = *(_QWORD *)&IID_IFrameLayoutDefinition.Data1 - *(_QWORD *)&a3->Data1;
  if ( *(_QWORD *)&IID_IFrameLayoutDefinition.Data1 == *(_QWORD *)&a3->Data1 )
    v16 = *(_QWORD *)IID_IFrameLayoutDefinition.Data4 - *(_QWORD *)a3->Data4;
  if ( !v16 )
    return (unsigned int)(**(__int64 (__fastcall ***)(char *, const struct _GUID *, IShellView **))(this - 40))(
                           (char *)(this - 40),
                           a3,
                           ppcm);
  return v12;
}

```

## disassembly

```asm
0x180015490  mov     [rsp+arg_0], rbx
0x180015495  mov     [rsp+arg_8], rsi
0x18001549a  push    rdi
0x18001549b  sub     rsp, 70h
0x18001549f  mov     qword ptr [r9], 0
0x1800154a6  mov     rsi, r9
0x1800154a9  mov     rax, qword ptr cs:IID_IShellView.Data1
0x1800154b0  mov     r10, r8
0x1800154b3  mov     rdi, rcx
0x1800154b6  sub     rax, [r8]
0x1800154b9  jnz     short loc_1800154C6
0x1800154bb  mov     rax, qword ptr cs:IID_IShellView.Data4
0x1800154c2  sub     rax, [r8+8]
0x1800154c6  test    rax, rax
0x1800154c9  jnz     loc_1800155E5
0x1800154cf  lea     ecx, [rax+50h]; this
0x1800154d2  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800154d7  add     rdi, 0FFFFFFFFFFFFFFD8h
0x1800154db  mov     rbx, rax
0x1800154de  test    rax, rax
0x1800154e1  jz      short loc_18001554A
0x1800154e3  lea     rax, ??_7CFontFolderViewCallback@@6BIShellFolderViewCB@@@; const CFontFolderViewCallback::`vftable'{for `IShellFolderViewCB'}
0x1800154ea  mov     dword ptr [rbx+18h], 1
0x1800154f1  mov     [rbx], rax
0x1800154f4  mov     rcx, rdi
0x1800154f7  lea     rax, ??_7CFontFolderViewCallback@@6BIFolderViewSettings@@@; const CFontFolderViewCallback::`vftable'{for `IFolderViewSettings'}
0x1800154fe  mov     [rbx+20h], rdi
0x180015502  mov     [rbx+8], rax
0x180015506  lea     rax, ??_7CFontFolderViewCallback@@6BIObjectWithSite@@@; const CFontFolderViewCallback::`vftable'{for `IObjectWithSite'}
0x18001550d  mov     [rbx+10h], rax
0x180015511  mov     qword ptr [rbx+28h], 0
0x180015519  mov     qword ptr [rbx+30h], 0
0x180015521  mov     qword ptr [rbx+38h], 0
0x180015529  mov     byte ptr [rbx+40h], 1
0x18001552d  mov     qword ptr [rbx+48h], 0
0x180015535  mov     rax, [rdi]
0x180015538  mov     rax, [rax+8]
0x18001553c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015541  lock inc cs:?g_cRefCount@@3JA; long g_cRefCount
0x180015548  jmp     short loc_18001554C
0x18001554a  xor     ebx, ebx
0x18001554c  test    rbx, rbx
0x18001554f  jz      loc_1800155DB
0x180015555  mov     rax, [rdi]
0x180015558  lea     r8, [rsp+78h+pcsfv.pshf]
0x18001555d  lea     rdx, IID_IShellFolder
0x180015564  mov     qword ptr [rsp+54h], 0
0x18001556d  mov     rcx, rdi
0x180015570  mov     dword ptr [rsp+78h+pcsfv.pshf+4], 0
0x180015578  mov     [rsp+78h+pcsfv.cbSize], 20h ; ' '
0x180015580  mov     rax, [rax]
0x180015583  mov     [rsp+78h+pcsfv.psvOuter], 0
0x18001558c  mov     [rsp+78h+pcsfv.psfvcb], rbx
0x180015591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015596  mov     rdx, rsi; ppsv
0x180015599  lea     rcx, [rsp+78h+pcsfv]; pcsfv
0x18001559e  call    cs:__imp_SHCreateShellFolderView
0x1800155a4  mov     rcx, [rsp+78h+pcsfv.psfvcb]
0x1800155a9  mov     ebx, eax
0x1800155ab  test    rcx, rcx
0x1800155ae  jz      short loc_1800155BC
0x1800155b0  mov     rdx, [rcx]
0x1800155b3  mov     rax, [rdx+10h]
0x1800155b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155bc  mov     rcx, [rsp+78h+pcsfv.pshf]
0x1800155c1  test    rcx, rcx
0x1800155c4  jz      loc_1800156A6
0x1800155ca  mov     rax, [rcx]
0x1800155cd  mov     rax, [rax+10h]
0x1800155d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155d6  jmp     loc_1800156A6
0x1800155db  mov     ebx, 8007000Eh
0x1800155e0  jmp     loc_1800156A6
0x1800155e5  mov     rax, qword ptr cs:IID_IDropTarget.Data1
0x1800155ec  sub     rax, [r8]
0x1800155ef  jnz     short loc_1800155FC
0x1800155f1  mov     rax, qword ptr cs:IID_IDropTarget.Data4
0x1800155f8  sub     rax, [r8+8]
0x1800155fc  test    rax, rax
0x1800155ff  jnz     short loc_18001560E
0x180015601  mov     rcx, rdx; HWND
0x180015604  call    ?CreateInstance@CFontFolderDropTarget@@SAJPEAUHWND__@@PEAUIShellFolderViewCB@@AEBU_GUID@@PEAPEAX@Z; CFontFolderDropTarget::CreateInstance(HWND__ *,IShellFolderViewCB *,_GUID const &,void * *)
0x180015609  jmp     loc_1800156A4
0x18001560e  mov     rax, qword ptr cs:IID_IContextMenu.Data1
0x180015615  sub     rax, [r8]
0x180015618  jnz     short loc_180015625
0x18001561a  mov     rax, qword ptr cs:IID_IContextMenu.Data4
0x180015621  sub     rax, [r8+8]
0x180015625  test    rax, rax
0x180015628  jnz     short loc_18001566E
0x18001562a  lea     rax, [rcx-28h]
0x18001562e  mov     [rsp+78h+ppcm], rsi; ppcm
0x180015633  neg     rax
0x180015636  mov     [rsp+78h+ahkeys], 0; ahkeys
0x18001563f  lea     rax, ?s_ViewContextMenuCB@CFontFolderBase@@CAJPEAUIShellFolder@@PEAUHWND__@@PEAUIDataObject@@I_K_J@Z; CFontFolderBase::s_ViewContextMenuCB(IShellFolder *,HWND__ *,IDataObject *,uint,unsigned __int64,__int64)
0x180015646  mov     [rsp+78h+nKeys], 0; nKeys
0x18001564e  sbb     rcx, rcx
0x180015651  mov     [rsp+78h+pfn], rax; pfn
0x180015656  and     rcx, rdi
0x180015659  xor     r9d, r9d; apidl
0x18001565c  mov     [rsp+78h+psf], rcx; psf
0x180015661  xor     r8d, r8d; cidl
0x180015664  xor     ecx, ecx; pidlFolder
0x180015666  call    cs:__imp_CDefFolderMenu_Create2
0x18001566c  jmp     short loc_1800156A4
0x18001566e  mov     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data1
0x180015675  mov     ebx, 80004002h
0x18001567a  sub     rax, [r8]
0x18001567d  jnz     short loc_18001568A
0x18001567f  mov     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data4
0x180015686  sub     rax, [r8+8]
0x18001568a  test    rax, rax
0x18001568d  jnz     short loc_1800156A6
0x18001568f  add     rcx, 0FFFFFFFFFFFFFFD8h
0x180015693  mov     r8, rsi
0x180015696  mov     rdx, r10
0x180015699  mov     rax, [rcx]
0x18001569c  mov     rax, [rax]
0x18001569f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156a4  mov     ebx, eax
0x1800156a6  lea     r11, [rsp+78h+var_8]
0x1800156ab  mov     eax, ebx
0x1800156ad  mov     rbx, [r11+10h]
0x1800156b1  mov     rsi, [r11+18h]
0x1800156b5  mov     rsp, r11
0x1800156b8  pop     rdi
0x1800156b9  retn
```
