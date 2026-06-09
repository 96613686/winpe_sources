# CKnownFoldersFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x1800096d0`
- end: `0x1800098cf`
- name: `?GetUIObjectOf@CKnownFoldersFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `511`
- prototype: `int(CKnownFoldersFolder *__hidden this, HWND, unsigned int, const struct _ITEMID_CHILD *const *, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800096d0`
- `0x1800098d8`
- `0x1800099e4`

## import_xrefs

- `SHELL32!SHCreateDataObject` at `0x180009729`
- `SHELL32!SHCreateDataObject` at `0x180009729`
- `SHELL32!AssocCreateForClasses` at `0x1800098bf`
- `SHELL32!AssocCreateForClasses` at `0x1800098bf`

## pseudocode

```c
__int64 __fastcall CKnownFoldersFolder::GetUIObjectOf(
        LPCITEMIDLIST *this,
        HWND a2,
        UINT a3,
        LPCITEMIDLIST *a4,
        const struct _GUID *riid,
        unsigned int *a6,
        struct IShellFolder *a7)
{
  __int64 v8; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned int v19; // ecx
  __int64 v20; // rax
  void **ppv; // [rsp+28h] [rbp-40h]
  ASSOCIATIONELEMENT rgClasses; // [rsp+40h] [rbp-28h] BYREF

  a7->lpVtbl = 0;
  v8 = *(_QWORD *)&IID_IDataObject.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IDataObject.Data1 == *(_QWORD *)&riid->Data1 )
    v8 = *(_QWORD *)IID_IDataObject.Data4 - *(_QWORD *)riid->Data4;
  if ( !v8 )
    return (unsigned int)SHCreateDataObject(this[6], a3, a4, 0, riid, (void **)&a7->lpVtbl);
  v10 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
    v10 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
  if ( !v10 )
    return (unsigned int)CKnownFoldersFolder::_GetUIObjectOf_ContextMenu(
                           (CKnownFoldersFolder *)(this - 2),
                           a2,
                           a3,
                           (const struct _ITEMID_CHILD *const *)a4,
                           riid,
                           (LPITEMIDLIST)ppv,
                           a7);
  v11 = *(_QWORD *)&IID_IQueryAssociations.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IQueryAssociations.Data1 == *(_QWORD *)&riid->Data1 )
    v11 = *(_QWORD *)IID_IQueryAssociations.Data4 - *(_QWORD *)riid->Data4;
  if ( !v11 )
    goto LABEL_37;
  v12 = *(_QWORD *)&IID_IAssociationArray.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IAssociationArray.Data1 == *(_QWORD *)&riid->Data1 )
    v12 = *(_QWORD *)IID_IAssociationArray.Data4 - *(_QWORD *)riid->Data4;
  if ( !v12 )
  {
LABEL_37:
    rgClasses.ac = ASSOCCLASS_FOLDER;
    *(_OWORD *)&rgClasses.hkClass = 0;
    return (unsigned int)AssocCreateForClasses(&rgClasses, 1u, riid, (void **)&a7->lpVtbl);
  }
  v13 = *(_QWORD *)&IID_IExtractIconA.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IExtractIconA.Data1 == *(_QWORD *)&riid->Data1 )
    v13 = *(_QWORD *)IID_IExtractIconA.Data4 - *(_QWORD *)riid->Data4;
  if ( !v13 )
    return (unsigned int)CKnownFoldersFolder::_GetUIObjectOf_DelegateToShell(
                           (CKnownFoldersFolder *)(this - 2),
                           a2,
                           (unsigned int)riid,
                           (const struct _ITEMID_CHILD *const *)a4,
                           riid,
                           a6,
                           (void **)&a7->lpVtbl);
  v14 = *(_QWORD *)&IID_IExtractIconW.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IExtractIconW.Data1 == *(_QWORD *)&riid->Data1 )
    v14 = *(_QWORD *)IID_IExtractIconW.Data4 - *(_QWORD *)riid->Data4;
  if ( !v14 )
    return (unsigned int)CKnownFoldersFolder::_GetUIObjectOf_DelegateToShell(
                           (CKnownFoldersFolder *)(this - 2),
                           a2,
                           (unsigned int)riid,
                           (const struct _ITEMID_CHILD *const *)a4,
                           riid,
                           a6,
                           (void **)&a7->lpVtbl);
  v15 = *(_QWORD *)&IID_IExtractImage.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IExtractImage.Data1 == *(_QWORD *)&riid->Data1 )
    v15 = *(_QWORD *)IID_IExtractImage.Data4 - *(_QWORD *)riid->Data4;
  if ( !v15 )
    return (unsigned int)CKnownFoldersFolder::_GetUIObjectOf_DelegateToShell(
                           (CKnownFoldersFolder *)(this - 2),
                           a2,
                           (unsigned int)riid,
                           (const struct _ITEMID_CHILD *const *)a4,
                           riid,
                           a6,
                           (void **)&a7->lpVtbl);
  v16 = *(_QWORD *)&IID_IExtractImage2.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IExtractImage2.Data1 == *(_QWORD *)&riid->Data1 )
    v16 = *(_QWORD *)IID_IExtractImage2.Data4 - *(_QWORD *)riid->Data4;
  if ( !v16 )
    return (unsigned int)CKnownFoldersFolder::_GetUIObjectOf_DelegateToShell(
                           (CKnownFoldersFolder *)(this - 2),
                           a2,
                           (unsigned int)riid,
                           (const struct _ITEMID_CHILD *const *)a4,
                           riid,
                           a6,
                           (void **)&a7->lpVtbl);
  v17 = *(_QWORD *)&IID_IThumbnailProvider.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IThumbnailProvider.Data1 == *(_QWORD *)&riid->Data1 )
    v17 = *(_QWORD *)IID_IThumbnailProvider.Data4 - *(_QWORD *)riid->Data4;
  if ( !v17 )
    return (unsigned int)CKnownFoldersFolder::_GetUIObjectOf_DelegateToShell(
                           (CKnownFoldersFolder *)(this - 2),
                           a2,
                           (unsigned int)riid,
                           (const struct _ITEMID_CHILD *const *)a4,
                           riid,
                           a6,
                           (void **)&a7->lpVtbl);
  v18 = *(_QWORD *)&IID_ICustomIconManager.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_ICustomIconManager.Data1 == *(_QWORD *)&riid->Data1 )
    v18 = *(_QWORD *)IID_ICustomIconManager.Data4 - *(_QWORD *)riid->Data4;
  if ( !v18 )
    return (unsigned int)CKnownFoldersFolder::_GetUIObjectOf_DelegateToShell(
                           (CKnownFoldersFolder *)(this - 2),
                           a2,
                           (unsigned int)riid,
                           (const struct _ITEMID_CHILD *const *)a4,
                           riid,
                           a6,
                           (void **)&a7->lpVtbl);
  v19 = -2147467259;
  v20 = *(_QWORD *)&IID_IQueryInfo.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IQueryInfo.Data1 == *(_QWORD *)&riid->Data1 )
    v20 = *(_QWORD *)IID_IQueryInfo.Data4 - *(_QWORD *)riid->Data4;
  if ( !v20 )
    return (unsigned int)CKnownFoldersFolder::_GetUIObjectOf_DelegateToShell(
                           (CKnownFoldersFolder *)(this - 2),
                           a2,
                           (unsigned int)riid,
                           (const struct _ITEMID_CHILD *const *)a4,
                           riid,
                           a6,
                           (void **)&a7->lpVtbl);
  return v19;
}

```

## disassembly

```asm
0x1800096d0  push    rbx
0x1800096d2  sub     rsp, 60h
0x1800096d6  mov     r11, r9
0x1800096d9  mov     r10d, r8d
0x1800096dc  mov     r9, [rsp+68h+arg_30]; ppv
0x1800096e4  mov     rbx, rcx
0x1800096e7  mov     r8, [rsp+68h+arg_20]; unsigned int
0x1800096ef  mov     qword ptr [r9], 0
0x1800096f6  mov     rax, qword ptr cs:IID_IDataObject.Data1
0x1800096fd  sub     rax, [r8]
0x180009700  jnz     short loc_18000970D
0x180009702  mov     rax, qword ptr cs:IID_IDataObject.Data4
0x180009709  sub     rax, [r8+8]
0x18000970d  test    rax, rax
0x180009710  jnz     short loc_180009734
0x180009712  mov     rcx, [rcx+30h]; pidlFolder
0x180009716  mov     edx, r10d; cidl
0x180009719  mov     [rsp+68h+ppv], r9; ppv
0x18000971e  xor     r9d, r9d; pdtInner
0x180009721  mov     [rsp+68h+riid], r8; riid
0x180009726  mov     r8, r11; apidl
0x180009729  call    cs:__imp_SHCreateDataObject
0x18000972f  jmp     loc_1800098C5
0x180009734  mov     rax, [r8]
0x180009737  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x18000973e  jnz     short loc_18000974B
0x180009740  mov     rax, [r8+8]
0x180009744  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x18000974b  test    rax, rax
0x18000974e  jnz     short loc_18000976E
0x180009750  mov     [rsp+68h+var_38], r9; struct IShellFolder *
0x180009755  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x180009759  mov     [rsp+68h+riid], r8; struct _GUID *
0x18000975e  mov     r9, r11; struct _ITEMID_CHILD **
0x180009761  mov     r8d, r10d; unsigned int
0x180009764  call    ?_GetUIObjectOf_ContextMenu@CKnownFoldersFolder@@AEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z; CKnownFoldersFolder::_GetUIObjectOf_ContextMenu(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)
0x180009769  jmp     loc_1800098C5
0x18000976e  mov     rax, qword ptr cs:IID_IQueryAssociations.Data1
0x180009775  sub     rax, [r8]
0x180009778  jnz     short loc_180009785
0x18000977a  mov     rax, qword ptr cs:IID_IQueryAssociations.Data4
0x180009781  sub     rax, [r8+8]
0x180009785  test    rax, rax
0x180009788  jz      loc_1800098A4
0x18000978e  mov     rax, qword ptr cs:IID_IAssociationArray.Data1
0x180009795  sub     rax, [r8]
0x180009798  jnz     short loc_1800097A5
0x18000979a  mov     rax, qword ptr cs:IID_IAssociationArray.Data4
0x1800097a1  sub     rax, [r8+8]
0x1800097a5  test    rax, rax
0x1800097a8  jz      loc_1800098A4
0x1800097ae  mov     rax, qword ptr cs:IID_IExtractIconA.Data1
0x1800097b5  sub     rax, [r8]
0x1800097b8  jnz     short loc_1800097C5
0x1800097ba  mov     rax, qword ptr cs:IID_IExtractIconA.Data4
0x1800097c1  sub     rax, [r8+8]
0x1800097c5  test    rax, rax
0x1800097c8  jz      loc_18000987F
0x1800097ce  mov     rax, qword ptr cs:IID_IExtractIconW.Data1
0x1800097d5  sub     rax, [r8]
0x1800097d8  jnz     short loc_1800097E5
0x1800097da  mov     rax, qword ptr cs:IID_IExtractIconW.Data4
0x1800097e1  sub     rax, [r8+8]
0x1800097e5  test    rax, rax
0x1800097e8  jz      loc_18000987F
0x1800097ee  mov     rax, qword ptr cs:IID_IExtractImage.Data1
0x1800097f5  sub     rax, [r8]
0x1800097f8  jnz     short loc_180009805
0x1800097fa  mov     rax, qword ptr cs:IID_IExtractImage.Data4
0x180009801  sub     rax, [r8+8]
0x180009805  test    rax, rax
0x180009808  jz      short loc_18000987F
0x18000980a  mov     rax, qword ptr cs:IID_IExtractImage2.Data1
0x180009811  sub     rax, [r8]
0x180009814  jnz     short loc_180009821
0x180009816  mov     rax, qword ptr cs:IID_IExtractImage2.Data4
0x18000981d  sub     rax, [r8+8]
0x180009821  test    rax, rax
0x180009824  jz      short loc_18000987F
0x180009826  mov     rax, qword ptr cs:IID_IThumbnailProvider.Data1
0x18000982d  sub     rax, [r8]
0x180009830  jnz     short loc_18000983D
0x180009832  mov     rax, qword ptr cs:IID_IThumbnailProvider.Data4
0x180009839  sub     rax, [r8+8]
0x18000983d  test    rax, rax
0x180009840  jz      short loc_18000987F
0x180009842  mov     rax, qword ptr cs:IID_ICustomIconManager.Data1
0x180009849  sub     rax, [r8]
0x18000984c  jnz     short loc_180009859
0x18000984e  mov     rax, qword ptr cs:IID_ICustomIconManager.Data4
0x180009855  sub     rax, [r8+8]
0x180009859  test    rax, rax
0x18000985c  jz      short loc_18000987F
0x18000985e  mov     rax, qword ptr cs:IID_IQueryInfo.Data1
0x180009865  mov     ecx, 80004005h
0x18000986a  sub     rax, [r8]
0x18000986d  jnz     short loc_18000987A
0x18000986f  mov     rax, qword ptr cs:IID_IQueryInfo.Data4
0x180009876  sub     rax, [r8+8]
0x18000987a  test    rax, rax
0x18000987d  jnz     short loc_1800098C7
0x18000987f  mov     rax, [rsp+68h+arg_28]
0x180009887  lea     rcx, [rbx-10h]; this
0x18000988b  mov     [rsp+68h+var_38], r9; void **
0x180009890  mov     r9, r11; struct _ITEMID_CHILD **
0x180009893  mov     [rsp+68h+ppv], rax; unsigned int *
0x180009898  mov     [rsp+68h+riid], r8; struct _GUID *
0x18000989d  call    ?_GetUIObjectOf_DelegateToShell@CKnownFoldersFolder@@AEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z; CKnownFoldersFolder::_GetUIObjectOf_DelegateToShell(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)
0x1800098a2  jmp     short loc_1800098C5
0x1800098a4  xorps   xmm0, xmm0
0x1800098a7  mov     [rsp+68h+rgClasses.ac], 8
0x1800098af  mov     edx, 1; cClasses
0x1800098b4  lea     rcx, [rsp+68h+rgClasses]; rgClasses
0x1800098b9  movdqu  xmmword ptr [rsp+68h+rgClasses.hkClass], xmm0
0x1800098bf  call    cs:__imp_AssocCreateForClasses
0x1800098c5  mov     ecx, eax
0x1800098c7  mov     eax, ecx
0x1800098c9  add     rsp, 60h
0x1800098cd  pop     rbx
0x1800098ce  retn
```
