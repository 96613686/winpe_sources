# CFontFolderBase::GetUIObjectOf(HWND__ *,uint,_ITEMIDLIST const * *,_GUID const &,uint *,void * *)

- ea: `0x180016950`
- end: `0x180016b4a`
- name: `?GetUIObjectOf@CFontFolderBase@@UEAAJPEAUHWND__@@IPEAPEFBU_ITEMIDLIST@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `506`
- prototype: `int(CFontFolderBase *__hidden this, HWND, unsigned int, const struct _ITEMIDLIST **, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180016950`
- `0x180019f04`
- `0x18001a0c8`
- `0x18001c0d0`
- `0x180020a84`
- `0x180022c58`
- `0x180026be0`
- `0x180032010`

## import_xrefs

- `SHELL32!SHCreateDataObject` at `0x1800169e1`
- `SHELL32!SHCreateDataObject` at `0x1800169e1`
- `SHELL32!AssocCreateForClasses` at `0x180016b31`
- `SHELL32!AssocCreateForClasses` at `0x180016b31`

## pseudocode

```c
__int64 __fastcall CFontFolderBase::GetUIObjectOf(
        LPCITEMIDLIST *this,
        HWND a2,
        unsigned int a3,
        const struct _ITEMIDLIST **a4,
        const struct _GUID *riid,
        unsigned int *a6,
        IDataObject *pdtInner)
{
  void **ppv; // r15
  __int64 v12; // rax
  unsigned int v13; // edi
  IDataObject v14; // rax
  __int64 v15; // rax
  const struct _ITEMIDLIST *v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rax
  CFontThumbnail *v20; // rax
  CFontThumbnail *v21; // rax
  struct IDataObjectVtbl **v22; // rsi
  __int64 v23; // rax
  ASSOCIATIONELEMENT rgClasses; // [rsp+30h] [rbp-58h] BYREF

  ppv = (void **)&pdtInner->lpVtbl;
  pdtInner->lpVtbl = 0;
  v12 = *(_QWORD *)&IID_IDataObject.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IDataObject.Data1 == *(_QWORD *)&riid->Data1 )
    v12 = *(_QWORD *)IID_IDataObject.Data4 - *(_QWORD *)riid->Data4;
  if ( !v12 )
  {
    pdtInner = 0;
    v13 = CFontFolderBase::_CreateDataObject((CFontFolderBase *)(this - 5), a2, a3, a4, &pdtInner);
    if ( (v13 & 0x80000000) == 0 )
    {
      v13 = SHCreateDataObject(this[9], a3, a4, pdtInner, riid, ppv);
      v14.lpVtbl = pdtInner->lpVtbl;
LABEL_24:
      ((void (*)(void))v14.lpVtbl->Release)();
      return v13;
    }
    return v13;
  }
  v15 = *(_QWORD *)&IID_IContextMenu.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IContextMenu.Data1 == *(_QWORD *)&riid->Data1 )
    v15 = *(_QWORD *)IID_IContextMenu.Data4 - *(_QWORD *)riid->Data4;
  if ( !v15 )
    return (unsigned int)CFontFolderBase::_CreateContextMenu(
                           (CFontFolderBase *)(this - 5),
                           a2,
                           a3,
                           a4,
                           (struct IContextMenu **)ppv);
  v13 = -2147467262;
  if ( a3 != 1 )
    return v13;
  v17 = *a4;
  if ( !*a4 )
    return v13;
  v18 = *(_QWORD *)&IID_IExtractIconW.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IExtractIconW.Data1 == *(_QWORD *)&riid->Data1 )
    v18 = *(_QWORD *)IID_IExtractIconW.Data4 - *(_QWORD *)riid->Data4;
  if ( !v18 )
    return (unsigned int)CFontIcon::CreateInstance(*a4, riid, ppv);
  v19 = *(_QWORD *)&IID_IExtractImage.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IExtractImage.Data1 == *(_QWORD *)&riid->Data1 )
    v19 = *(_QWORD *)IID_IExtractImage.Data4 - *(_QWORD *)riid->Data4;
  if ( v19 )
  {
    v23 = *(_QWORD *)&IID_IQueryAssociations.Data1 - *(_QWORD *)&riid->Data1;
    if ( *(_QWORD *)&IID_IQueryAssociations.Data1 == *(_QWORD *)&riid->Data1 )
      v23 = *(_QWORD *)IID_IQueryAssociations.Data4 - *(_QWORD *)riid->Data4;
    if ( v23 )
      return v13;
    rgClasses.ac = 9 - ((unsigned int)FID_IsFolder(*a4) != 0);
    *(_OWORD *)&rgClasses.hkClass = 0;
    return (unsigned int)AssocCreateForClasses(&rgClasses, 1u, riid, ppv);
  }
  v13 = -2147024882;
  v20 = (CFontThumbnail *)DirectUI::HAllocAndZero((DirectUI *)0x470, (unsigned __int64)a2);
  if ( v20 )
  {
    v21 = CFontThumbnail::CFontThumbnail(v20, a2, v17);
    v22 = (struct IDataObjectVtbl **)v21;
    if ( v21 )
    {
      if ( *((_QWORD *)v21 + 4) )
        v13 = (**(__int64 (__fastcall ***)(CFontThumbnail *, const struct _GUID *, void **))v21)(v21, riid, ppv);
      v14.lpVtbl = *v22;
      goto LABEL_24;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180016950  push    rbx
0x180016952  push    rbp
0x180016953  push    rsi
0x180016954  push    rdi
0x180016955  push    r12
0x180016957  push    r14
0x180016959  push    r15
0x18001695b  sub     rsp, 50h
0x18001695f  mov     r15, [rsp+88h+pdtInner]
0x180016967  mov     r14, r9
0x18001696a  mov     rbx, [rsp+88h+arg_20]
0x180016972  mov     esi, r8d
0x180016975  mov     r12, rdx
0x180016978  mov     rbp, rcx
0x18001697b  mov     qword ptr [r15], 0
0x180016982  mov     rax, qword ptr cs:IID_IDataObject.Data1
0x180016989  sub     rax, [rbx]
0x18001698c  jnz     short loc_180016999
0x18001698e  mov     rax, qword ptr cs:IID_IDataObject.Data4
0x180016995  sub     rax, [rbx+8]
0x180016999  test    rax, rax
0x18001699c  jnz     short loc_1800169F9
0x18001699e  mov     [rsp+88h+pdtInner], rax
0x1800169a6  add     rcx, 0FFFFFFFFFFFFFFD8h; this
0x1800169aa  lea     rax, [rsp+88h+pdtInner]
0x1800169b2  mov     [rsp+88h+riid], rax; struct IDataObject **
0x1800169b7  call    ?_CreateDataObject@CFontFolderBase@@AEAAJPEAUHWND__@@IPEAPEFBU_ITEMIDLIST@@PEAPEAUIDataObject@@@Z; CFontFolderBase::_CreateDataObject(HWND__ *,uint,_ITEMIDLIST const * *,IDataObject * *)
0x1800169bc  mov     edi, eax
0x1800169be  test    eax, eax
0x1800169c0  js      loc_180016B39
0x1800169c6  mov     r9, [rsp+88h+pdtInner]; pdtInner
0x1800169ce  mov     r8, r14; apidl
0x1800169d1  mov     rcx, [rbp+48h]; pidlFolder
0x1800169d5  mov     edx, esi; cidl
0x1800169d7  mov     [rsp+88h+ppv], r15; ppv
0x1800169dc  mov     [rsp+88h+riid], rbx; riid
0x1800169e1  call    cs:__imp_SHCreateDataObject
0x1800169e7  mov     rcx, [rsp+88h+pdtInner]
0x1800169ef  mov     edi, eax
0x1800169f1  mov     rax, [rcx]
0x1800169f4  jmp     loc_180016ADE
0x1800169f9  mov     rax, qword ptr cs:IID_IContextMenu.Data1
0x180016a00  sub     rax, [rbx]
0x180016a03  jnz     short loc_180016A10
0x180016a05  mov     rax, qword ptr cs:IID_IContextMenu.Data4
0x180016a0c  sub     rax, [rbx+8]
0x180016a10  test    rax, rax
0x180016a13  jnz     short loc_180016A28
0x180016a15  add     rcx, 0FFFFFFFFFFFFFFD8h; this
0x180016a19  mov     [rsp+88h+riid], r15; struct IContextMenu **
0x180016a1e  call    ?_CreateContextMenu@CFontFolderBase@@AEAAJPEAUHWND__@@IPEAPEFBU_ITEMIDLIST@@PEAPEAUIContextMenu@@@Z; CFontFolderBase::_CreateContextMenu(HWND__ *,uint,_ITEMIDLIST const * *,IContextMenu * *)
0x180016a23  jmp     loc_180016B37
0x180016a28  mov     edi, 80004002h
0x180016a2d  cmp     esi, 1
0x180016a30  jnz     loc_180016B39
0x180016a36  mov     rsi, [r9]
0x180016a39  test    rsi, rsi
0x180016a3c  jz      loc_180016B39
0x180016a42  mov     rax, qword ptr cs:IID_IExtractIconW.Data1
0x180016a49  sub     rax, [rbx]
0x180016a4c  jnz     short loc_180016A59
0x180016a4e  mov     rax, qword ptr cs:IID_IExtractIconW.Data4
0x180016a55  sub     rax, [rbx+8]
0x180016a59  test    rax, rax
0x180016a5c  jnz     short loc_180016A71
0x180016a5e  mov     r8, r15; void **
0x180016a61  mov     rdx, rbx; struct _GUID *
0x180016a64  mov     rcx, rsi; pidl
0x180016a67  call    ?CreateInstance@CFontIcon@@SAJPEFBU_ITEMIDLIST@@AEBU_GUID@@PEAPEAX@Z; CFontIcon::CreateInstance(_ITEMIDLIST const *,_GUID const &,void * *)
0x180016a6c  jmp     loc_180016B37
0x180016a71  mov     rax, qword ptr cs:IID_IExtractImage.Data1
0x180016a78  sub     rax, [rbx]
0x180016a7b  jnz     short loc_180016A88
0x180016a7d  mov     rax, qword ptr cs:IID_IExtractImage.Data4
0x180016a84  sub     rax, [rbx+8]
0x180016a88  test    rax, rax
0x180016a8b  jnz     short loc_180016AE9
0x180016a8d  mov     ecx, 470h; this
0x180016a92  mov     edi, 8007000Eh
0x180016a97  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180016a9c  test    rax, rax
0x180016a9f  jz      loc_180016B39
0x180016aa5  mov     r8, rsi; struct _ITEMIDLIST *
0x180016aa8  mov     rdx, r12; HWND
0x180016aab  mov     rcx, rax; this
0x180016aae  call    ??0CFontThumbnail@@AEAA@PEAUHWND__@@PEFBU_ITEMIDLIST@@@Z; CFontThumbnail::CFontThumbnail(HWND__ *,_ITEMIDLIST const *)
0x180016ab3  mov     rsi, rax
0x180016ab6  test    rax, rax
0x180016ab9  jz      short loc_180016B39
0x180016abb  cmp     qword ptr [rax+20h], 0
0x180016ac0  jz      short loc_180016AD8
0x180016ac2  mov     rcx, [rax]
0x180016ac5  mov     r8, r15
0x180016ac8  mov     rdx, rbx
0x180016acb  mov     rax, [rcx]
0x180016ace  mov     rcx, rsi
0x180016ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ad6  mov     edi, eax
0x180016ad8  mov     rax, [rsi]
0x180016adb  mov     rcx, rsi
0x180016ade  mov     rax, [rax+10h]
0x180016ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ae7  jmp     short loc_180016B39
0x180016ae9  mov     rax, qword ptr cs:IID_IQueryAssociations.Data1
0x180016af0  sub     rax, [rbx]
0x180016af3  jnz     short loc_180016B00
0x180016af5  mov     rax, qword ptr cs:IID_IQueryAssociations.Data4
0x180016afc  sub     rax, [rbx+8]
0x180016b00  test    rax, rax
0x180016b03  jnz     short loc_180016B39
0x180016b05  mov     rcx, rsi; struct _ITEMIDLIST *
0x180016b08  call    ?FID_IsFolder@@YAHPEFBU_ITEMIDLIST@@@Z; FID_IsFolder(_ITEMIDLIST const *)
0x180016b0d  neg     eax
0x180016b0f  xorps   xmm0, xmm0
0x180016b12  mov     r9, r15; ppv
0x180016b15  mov     r8, rbx; riid
0x180016b18  sbb     ecx, ecx
0x180016b1a  mov     edx, 1; cClasses
0x180016b1f  add     ecx, 9
0x180016b22  mov     [rsp+88h+rgClasses.ac], ecx
0x180016b26  lea     rcx, [rsp+88h+rgClasses]; rgClasses
0x180016b2b  movdqu  xmmword ptr [rsp+88h+rgClasses.hkClass], xmm0
0x180016b31  call    cs:__imp_AssocCreateForClasses
0x180016b37  mov     edi, eax
0x180016b39  mov     eax, edi
0x180016b3b  add     rsp, 50h
0x180016b3f  pop     r15
0x180016b41  pop     r14
0x180016b43  pop     r12
0x180016b45  pop     rdi
0x180016b46  pop     rsi
0x180016b47  pop     rbp
0x180016b48  pop     rbx
0x180016b49  retn
```
