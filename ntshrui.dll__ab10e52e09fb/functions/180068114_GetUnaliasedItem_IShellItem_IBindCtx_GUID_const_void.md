# GetUnaliasedItem(IShellItem *,IBindCtx *,_GUID const &,void * *)

- ea: `0x180068114`
- end: `0x180068322`
- name: `?GetUnaliasedItem@@YAJPEAUIShellItem@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `526`
- prototype: `__int64 __fastcall(struct IShellItem *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180068878`

## callees

- `0x180067cf4`
- `0x180068114`
- `0x180073ec4`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800682f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800682f3`
- `SHELL32!SHCreateItemFromParsingName` at `0x180068279`
- `SHELL32!SHCreateItemFromParsingName` at `0x180068279`
- `SHELL32!__imp_ILFree` at `0x180068250`
- `SHELL32!__imp_ILFree` at `0x180068250`

## pseudocode

```c
__int64 __fastcall GetUnaliasedItem(struct IShellItem *a1, ITEMIDLIST *a2, struct IShellFolder2 *a3, void **a4)
{
  struct IShellItemVtbl *lpVtbl; // rax
  HRESULT ParentAndChildIDListFromItem; // ebx
  struct IShellItemVtbl *v8; // rax
  __int64 v9; // rdx
  int v10; // r8d
  PCWSTR pszPath[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v13; // [rsp+70h] [rbp+28h] BYREF
  LPITEMIDLIST pidl; // [rsp+78h] [rbp+30h] BYREF
  struct IShellFolder2 *v15; // [rsp+80h] [rbp+38h] BYREF
  IBindCtx *pbc; // [rsp+88h] [rbp+40h] BYREF

  v15 = a3;
  pidl = a2;
  *a4 = 0;
  lpVtbl = a1->lpVtbl;
  v13 = 0;
  if ( ((int (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, __int64 *))lpVtbl->BindToHandler)(
         a1,
         0,
         &BHID_SFObject,
         &GUID_7d903fca_d6f9_4810_8332_946c0177e247,
         &v13) < 0 )
    goto LABEL_5;
  v15 = 0;
  ParentAndChildIDListFromItem = (*(__int64 (__fastcall **)(__int64, struct IShellFolder2 **))(*(_QWORD *)v13 + 32LL))(
                                   v13,
                                   &v15);
  if ( ParentAndChildIDListFromItem >= 0 )
  {
    ParentAndChildIDListFromItem = ((__int64 (__fastcall *)(struct IShellFolder2 *, GUID *, void **))v15->lpVtbl->QueryInterface)(
                                     v15,
                                     &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                     a4);
    ((void (__fastcall *)(struct IShellFolder2 *))v15->lpVtbl->Release)(v15);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( ParentAndChildIDListFromItem < 0 )
  {
LABEL_5:
    v8 = a1->lpVtbl;
    pszPath[0] = 0;
    if ( ((int (__fastcall *)(struct IShellItem *, __int64, PCWSTR *))v8->GetDisplayName)(a1, 2147844096LL, pszPath) < 0 )
      return ((unsigned int (__fastcall *)(struct IShellItem *, GUID *, void **))a1->lpVtbl->QueryInterface)(
               a1,
               &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
               a4);
    pbc = 0;
    v15 = 0;
    pidl = 0;
    ParentAndChildIDListFromItem = GetParentAndChildIDListFromItem(a1, v9, &v15, &pidl);
    if ( ParentAndChildIDListFromItem >= 0 )
    {
      ParentAndChildIDListFromItem = GetParsingBindCtx(v15, (const struct _ITEMID_CHILD *)pidl, v10, &pbc);
      ((void (__fastcall *)(struct IShellFolder2 *))v15->lpVtbl->Release)(v15);
      ILFree(pidl);
      if ( ParentAndChildIDListFromItem >= 0 )
      {
        pidl = 0;
        ParentAndChildIDListFromItem = SHCreateItemFromParsingName(
                                         pszPath[0],
                                         pbc,
                                         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                         (void **)&pidl);
        if ( ParentAndChildIDListFromItem >= 0 )
        {
          LODWORD(v15) = 0;
          if ( (*(unsigned int (__fastcall **)(LPITEMIDLIST, struct IShellItem *, __int64, struct IShellFolder2 **))(*(_QWORD *)&pidl->mkid.cb + 56LL))(
                 pidl,
                 a1,
                 0x10000000,
                 &v15) )
          {
            ParentAndChildIDListFromItem = (**(__int64 (__fastcall ***)(LPITEMIDLIST, GUID *, void **))&pidl->mkid.cb)(
                                             pidl,
                                             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                             a4);
          }
          else
          {
            ParentAndChildIDListFromItem = -2147467259;
          }
          (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl);
        }
        ((void (__fastcall *)(IBindCtx *))pbc->lpVtbl->Release)(pbc);
      }
    }
    CoTaskMemFree((LPVOID)pszPath[0]);
    if ( ParentAndChildIDListFromItem < 0 )
      return ((unsigned int (__fastcall *)(struct IShellItem *, GUID *, void **))a1->lpVtbl->QueryInterface)(
               a1,
               &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
               a4);
  }
  return (unsigned int)ParentAndChildIDListFromItem;
}

```

## disassembly

```asm
0x180068114  mov     [rsp-20h+arg_10], r8
0x180068119  mov     [rsp-20h+pidl], rdx
0x18006811e  push    rbp
0x18006811f  push    rbx
0x180068120  push    rsi
0x180068121  push    rdi
0x180068122  mov     rbp, rsp
0x180068125  sub     rsp, 48h
0x180068129  mov     qword ptr [r9], 0
0x180068130  lea     r8, BHID_SFObject
0x180068137  mov     rax, [rcx]
0x18006813a  mov     rdi, rcx
0x18006813d  lea     rcx, [rbp+arg_0]
0x180068141  mov     [rbp+arg_0], 0
0x180068149  mov     rsi, r9
0x18006814c  mov     [rsp+48h+var_28], rcx
0x180068151  lea     r9, _GUID_7d903fca_d6f9_4810_8332_946c0177e247
0x180068158  xor     edx, edx
0x18006815a  mov     rax, [rax+18h]
0x18006815e  mov     rcx, rdi
0x180068161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068166  test    eax, eax
0x180068168  js      short loc_1800681CF
0x18006816a  mov     rcx, [rbp+arg_0]
0x18006816e  lea     rdx, [rbp+arg_10]
0x180068172  mov     [rbp+arg_10], 0
0x18006817a  mov     rax, [rcx]
0x18006817d  mov     rax, [rax+20h]
0x180068181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068186  mov     ebx, eax
0x180068188  test    eax, eax
0x18006818a  js      short loc_1800681B7
0x18006818c  mov     rcx, [rbp+arg_10]
0x180068190  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180068197  mov     r8, rsi
0x18006819a  mov     rax, [rcx]
0x18006819d  mov     rax, [rax]
0x1800681a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800681a5  mov     rcx, [rbp+arg_10]
0x1800681a9  mov     ebx, eax
0x1800681ab  mov     rax, [rcx]
0x1800681ae  mov     rax, [rax+10h]
0x1800681b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800681b7  mov     rcx, [rbp+arg_0]
0x1800681bb  mov     rax, [rcx]
0x1800681be  mov     rax, [rax+10h]
0x1800681c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800681c7  test    ebx, ebx
0x1800681c9  jns     loc_180068317
0x1800681cf  mov     rax, [rdi]
0x1800681d2  lea     r8, [rbp+pszPath]
0x1800681d6  mov     edx, 80058000h
0x1800681db  mov     [rbp+pszPath], 0
0x1800681e3  mov     rcx, rdi
0x1800681e6  mov     rax, [rax+28h]
0x1800681ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800681ef  test    eax, eax
0x1800681f1  js      loc_1800682FD
0x1800681f7  lea     r9, [rbp+pidl]
0x1800681fb  mov     [rbp+pbc], 0
0x180068203  lea     r8, [rbp+arg_10]
0x180068207  mov     [rbp+arg_10], 0
0x18006820f  mov     rcx, rdi
0x180068212  mov     [rbp+pidl], 0
0x18006821a  call    GetParentAndChildIDListFromItem
0x18006821f  mov     ebx, eax
0x180068221  test    eax, eax
0x180068223  js      loc_1800682EF
0x180068229  mov     rdx, [rbp+pidl]; struct _ITEMID_CHILD *
0x18006822d  lea     r9, [rbp+pbc]; struct IBindCtx **
0x180068231  mov     rcx, [rbp+arg_10]; struct IShellFolder2 *
0x180068235  call    ?GetParsingBindCtx@@YAJPEAUIShellFolder2@@PEFBU_ITEMID_CHILD@@HPEAPEAUIBindCtx@@@Z; GetParsingBindCtx(IShellFolder2 *,_ITEMID_CHILD const *,int,IBindCtx * *)
0x18006823a  mov     rcx, [rbp+arg_10]
0x18006823e  mov     ebx, eax
0x180068240  mov     rax, [rcx]
0x180068243  mov     rax, [rax+10h]
0x180068247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006824c  mov     rcx, [rbp+pidl]; pidl
0x180068250  call    cs:__imp_ILFree
0x180068256  test    ebx, ebx
0x180068258  js      loc_1800682EF
0x18006825e  mov     rdx, [rbp+pbc]; pbc
0x180068262  lea     r9, [rbp+pidl]; ppv
0x180068266  mov     rcx, [rbp+pszPath]; pszPath
0x18006826a  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180068271  mov     [rbp+pidl], 0
0x180068279  call    cs:__imp_SHCreateItemFromParsingName
0x18006827f  mov     ebx, eax
0x180068281  test    eax, eax
0x180068283  js      short loc_1800682DF
0x180068285  mov     rcx, [rbp+pidl]
0x180068289  lea     r9, [rbp+arg_10]
0x18006828d  mov     dword ptr [rbp+arg_10], 0
0x180068294  mov     r8d, 10000000h
0x18006829a  mov     rdx, rdi
0x18006829d  mov     rax, [rcx]
0x1800682a0  mov     rax, [rax+38h]
0x1800682a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800682a9  test    eax, eax
0x1800682ab  jnz     short loc_1800682B4
0x1800682ad  mov     ebx, 80004005h
0x1800682b2  jmp     short loc_1800682CF
0x1800682b4  mov     rcx, [rbp+pidl]
0x1800682b8  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1800682bf  mov     r8, rsi
0x1800682c2  mov     rax, [rcx]
0x1800682c5  mov     rax, [rax]
0x1800682c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800682cd  mov     ebx, eax
0x1800682cf  mov     rcx, [rbp+pidl]
0x1800682d3  mov     rax, [rcx]
0x1800682d6  mov     rax, [rax+10h]
0x1800682da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800682df  mov     rcx, [rbp+pbc]
0x1800682e3  mov     rax, [rcx]
0x1800682e6  mov     rax, [rax+10h]
0x1800682ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800682ef  mov     rcx, [rbp+pszPath]; pv
0x1800682f3  call    cs:__imp_CoTaskMemFree
0x1800682f9  test    ebx, ebx
0x1800682fb  jns     short loc_180068317
0x1800682fd  mov     rax, [rdi]
0x180068300  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180068307  mov     r8, rsi
0x18006830a  mov     rcx, rdi
0x18006830d  mov     rax, [rax]
0x180068310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068315  mov     ebx, eax
0x180068317  mov     eax, ebx
0x180068319  add     rsp, 48h
0x18006831d  pop     rdi
0x18006831e  pop     rsi
0x18006831f  pop     rbx
0x180068320  pop     rbp
0x180068321  retn
```
