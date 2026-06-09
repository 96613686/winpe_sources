# CRootFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x18000b6e0`
- end: `0x18000b826`
- name: `?GetUIObjectOf@CRootFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `326`
- prototype: `int(CRootFolder *__hidden this, HWND, unsigned int, const struct _ITEMID_CHILD *const *, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000b6e0`
- `0x18000b82c`
- `0x18000b9cc`

## import_xrefs

- `SHELL32!SHCreateDataObject` at `0x18000b73c`
- `SHELL32!SHCreateDataObject` at `0x18000b73c`
- `SHELL32!AssocCreateForClasses` at `0x18000b812`
- `SHELL32!AssocCreateForClasses` at `0x18000b812`

## pseudocode

```c
HRESULT __fastcall CRootFolder::GetUIObjectOf(
        LPCITEMIDLIST *this,
        HWND a2,
        UINT a3,
        LPCITEMIDLIST *a4,
        struct _GUID *riid,
        unsigned int *a6,
        void **a7)
{
  __int64 v7; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int *ppv; // [rsp+28h] [rbp-50h]
  ASSOCIATIONELEMENT rgClasses; // [rsp+50h] [rbp-28h] BYREF

  *a7 = 0;
  v7 = *(_QWORD *)&IID_IDataObject.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IDataObject.Data1 == *(_QWORD *)&riid->Data1 )
    v7 = *(_QWORD *)IID_IDataObject.Data4 - *(_QWORD *)riid->Data4;
  if ( !v7 )
    return SHCreateDataObject(this[7], a3, a4, 0, riid, a7);
  v9 = *(_QWORD *)&IID_IContextMenu.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IContextMenu.Data1 == *(_QWORD *)&riid->Data1 )
    v9 = *(_QWORD *)IID_IContextMenu.Data4 - *(_QWORD *)riid->Data4;
  if ( !v9 )
    return CscMenu_CreateDefaultContextMenu(
             a2,
             (struct IShellFolder *)((unsigned __int64)this & -(__int64)(this != (LPCITEMIDLIST *)16)),
             (const struct _ITEMIDLIST_ABSOLUTE *)this[7],
             (struct CCscFolderBase *)(this - 2),
             a3,
             (const struct _ITEMID_CHILD *const *)a4,
             L"open",
             riid,
             a7);
  v10 = *(_QWORD *)&IID_IExtractIconW.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IExtractIconW.Data1 == *(_QWORD *)&riid->Data1 )
    v10 = *(_QWORD *)IID_IExtractIconW.Data4 - *(_QWORD *)riid->Data4;
  if ( !v10 )
    return CRootFolder::_GetUIObjectOf_ExtractIcon(
             (CRootFolder *)this,
             a2,
             a3,
             (const struct _ITEMID_CHILD *const *)a4,
             riid,
             ppv,
             a7);
  v11 = *(_QWORD *)&IID_IQueryAssociations.Data1 - *(_QWORD *)&riid->Data1;
  if ( *(_QWORD *)&IID_IQueryAssociations.Data1 == *(_QWORD *)&riid->Data1 )
    v11 = *(_QWORD *)IID_IQueryAssociations.Data4 - *(_QWORD *)riid->Data4;
  if ( v11 )
    return -2147467259;
  rgClasses.ac = ASSOCCLASS_FOLDER;
  *(_OWORD *)&rgClasses.hkClass = 0;
  return AssocCreateForClasses(&rgClasses, 1u, riid, a7);
}

```

## disassembly

```asm
0x18000b6e0  mov     [rsp+arg_0], rbx
0x18000b6e5  push    rdi
0x18000b6e6  sub     rsp, 70h
0x18000b6ea  mov     r10, [rsp+78h+arg_20]
0x18000b6f2  mov     r11, r9
0x18000b6f5  mov     r9, [rsp+78h+arg_30]; ppv
0x18000b6fd  mov     ebx, r8d
0x18000b700  mov     rdi, rdx
0x18000b703  mov     qword ptr [r9], 0
0x18000b70a  mov     rax, qword ptr cs:IID_IDataObject.Data1
0x18000b711  sub     rax, [r10]
0x18000b714  jnz     short loc_18000B721
0x18000b716  mov     rax, qword ptr cs:IID_IDataObject.Data4
0x18000b71d  sub     rax, [r10+8]
0x18000b721  test    rax, rax
0x18000b724  jnz     short loc_18000B747
0x18000b726  mov     rcx, [rcx+38h]; pidlFolder
0x18000b72a  mov     r8, r11; apidl
0x18000b72d  mov     [rsp+78h+ppv], r9; ppv
0x18000b732  mov     edx, ebx; cidl
0x18000b734  xor     r9d, r9d; pdtInner
0x18000b737  mov     [rsp+78h+riid], r10; riid
0x18000b73c  call    cs:__imp_SHCreateDataObject
0x18000b742  jmp     loc_18000B818
0x18000b747  mov     rax, qword ptr cs:IID_IContextMenu.Data1
0x18000b74e  sub     rax, [r10]
0x18000b751  jnz     short loc_18000B75E
0x18000b753  mov     rax, qword ptr cs:IID_IContextMenu.Data4
0x18000b75a  sub     rax, [r10+8]
0x18000b75e  test    rax, rax
0x18000b761  jnz     short loc_18000B7A1
0x18000b763  mov     r8, [rcx+38h]; struct _ITEMIDLIST_ABSOLUTE *
0x18000b767  lea     rax, [rcx-10h]
0x18000b76b  mov     [rsp+78h+var_38], r9; ppv
0x18000b770  neg     rax
0x18000b773  mov     [rsp+78h+var_40], r10; riid
0x18000b778  lea     rax, aOpen_0; "open"
0x18000b77f  mov     [rsp+78h+var_48], rax; unsigned __int16 *
0x18000b784  lea     r9, [rcx-10h]; struct CCscFolderBase *
0x18000b788  sbb     rdx, rdx
0x18000b78b  mov     [rsp+78h+ppv], r11; struct _ITEMID_CHILD **
0x18000b790  and     rdx, rcx; struct IShellFolder *
0x18000b793  mov     dword ptr [rsp+78h+riid], ebx; unsigned int
0x18000b797  mov     rcx, rdi; HWND
0x18000b79a  call    ?CscMenu_CreateDefaultContextMenu@@YAJPEAUHWND__@@PEAUIShellFolder@@PEBU_ITEMIDLIST_ABSOLUTE@@PEAVCCscFolderBase@@IPEBQEFBU_ITEMID_CHILD@@PEBGAEBU_GUID@@PEAPEAX@Z; CscMenu_CreateDefaultContextMenu(HWND__ *,IShellFolder *,_ITEMIDLIST_ABSOLUTE const *,CCscFolderBase *,uint,_ITEMID_CHILD const * const *,ushort const *,_GUID const &,void * *)
0x18000b79f  jmp     short loc_18000B818
0x18000b7a1  mov     rax, qword ptr cs:IID_IExtractIconW.Data1
0x18000b7a8  sub     rax, [r10]
0x18000b7ab  jnz     short loc_18000B7B8
0x18000b7ad  mov     rax, qword ptr cs:IID_IExtractIconW.Data4
0x18000b7b4  sub     rax, [r10+8]
0x18000b7b8  test    rax, rax
0x18000b7bb  jnz     short loc_18000B7D1
0x18000b7bd  mov     [rsp+78h+var_48], r9; void **
0x18000b7c2  mov     r9, r11; struct _ITEMID_CHILD **
0x18000b7c5  mov     [rsp+78h+riid], r10; struct _GUID *
0x18000b7ca  call    ?_GetUIObjectOf_ExtractIcon@CRootFolder@@AEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z; CRootFolder::_GetUIObjectOf_ExtractIcon(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)
0x18000b7cf  jmp     short loc_18000B818
0x18000b7d1  mov     rax, qword ptr cs:IID_IQueryAssociations.Data1
0x18000b7d8  sub     rax, [r10]
0x18000b7db  jnz     short loc_18000B7E8
0x18000b7dd  mov     rax, qword ptr cs:IID_IQueryAssociations.Data4
0x18000b7e4  sub     rax, [r10+8]
0x18000b7e8  test    rax, rax
0x18000b7eb  jz      short loc_18000B7F4
0x18000b7ed  mov     eax, 80004005h
0x18000b7f2  jmp     short loc_18000B818
0x18000b7f4  xorps   xmm0, xmm0
0x18000b7f7  mov     [rsp+78h+rgClasses.ac], 8
0x18000b7ff  mov     r8, r10; riid
0x18000b802  lea     rcx, [rsp+78h+rgClasses]; rgClasses
0x18000b807  mov     edx, 1; cClasses
0x18000b80c  movdqu  xmmword ptr [rsp+78h+rgClasses.hkClass], xmm0
0x18000b812  call    cs:__imp_AssocCreateForClasses
0x18000b818  mov     rbx, [rsp+78h+arg_0]
0x18000b820  add     rsp, 70h
0x18000b824  pop     rdi
0x18000b825  retn
```
