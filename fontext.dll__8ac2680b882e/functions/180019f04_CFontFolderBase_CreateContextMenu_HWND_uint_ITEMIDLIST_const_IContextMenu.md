# CFontFolderBase::_CreateContextMenu(HWND__ *,uint,_ITEMIDLIST const * *,IContextMenu * *)

- ea: `0x180019f04`
- end: `0x18001a0c1`
- name: `?_CreateContextMenu@CFontFolderBase@@AEAAJPEAUHWND__@@IPEAPEFBU_ITEMIDLIST@@PEAPEAUIContextMenu@@@Z`
- size: `445`
- prototype: `int(CFontFolderBase *__hidden this, HWND, unsigned int, const struct _ITEMIDLIST **, struct IContextMenu **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016950`

## callees

- `0x180010458`
- `0x180019f04`
- `0x18001c0d0`
- `0x180022948`
- `0x180022c58`
- `0x180032010`

## import_xrefs

- `SHELL32!SHCreateDefaultContextMenu` at `0x18001a064`
- `SHELL32!SHCreateDefaultContextMenu` at `0x18001a064`
- `SHELL32!SHGetSpecialFolderLocation` at `0x180019f7e`
- `SHELL32!SHGetSpecialFolderLocation` at `0x180019f7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a080`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a08f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a09e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a08f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a09e`

## pseudocode

```c
__int64 __fastcall CFontFolderBase::_CreateContextMenu(
        CFontFolderBase *this,
        HWND a2,
        UINT a3,
        const struct _ITEMIDLIST **a4,
        struct IContextMenu **ppv)
{
  void **v5; // r12
  unsigned __int64 v6; // r13
  HRESULT v10; // ebx
  const struct _ITEMIDLIST *v11; // rcx
  int IsFolder; // edi
  unsigned __int64 v13; // rdx
  CContextMenuCB *v14; // rax
  CContextMenuCB *v15; // rax
  CContextMenuCB *v16; // rdi
  HKEY v18; // [rsp+20h] [rbp-51h] BYREF
  _QWORD v19[3]; // [rsp+28h] [rbp-49h] BYREF
  DEFCONTEXTMENU pdcm; // [rsp+40h] [rbp-31h] BYREF
  LPITEMIDLIST ppidl; // [rsp+D0h] [rbp+5Fh] BYREF
  UINT v22; // [rsp+E0h] [rbp+6Fh]
  HKEY hKey; // [rsp+E8h] [rbp+77h] BYREF

  v22 = a3;
  v5 = (void **)ppv;
  v6 = (unsigned __int64)this + 40;
  hKey = 0;
  v18 = 0;
  *ppv = 0;
  FID_GetClassKeys((struct IShellFolder *)(((unsigned __int64)this + 40) & -(__int64)(this != 0)), *a4, &v18, &hKey);
  ppidl = 0;
  v10 = SHGetSpecialFolderLocation(a2, 20, &ppidl);
  if ( v10 >= 0 )
  {
    v11 = *a4;
    v19[0] = v18;
    v19[1] = hKey;
    ppv = 0;
    IsFolder = FID_IsFolder(v11);
    v10 = -2147024882;
    v14 = (CContextMenuCB *)DirectUI::HAllocAndZero((DirectUI *)0x18, v13);
    if ( v14 )
    {
      v15 = CContextMenuCB::CContextMenuCB(v14, IsFolder);
      v16 = v15;
      if ( v15 )
      {
        v10 = (**(__int64 (__fastcall ***)(CContextMenuCB *, GUID *, struct IContextMenu ***))v15)(
                v15,
                &GUID_3409e930_5a39_11d1_83fa_00a0c90dc849,
                &ppv);
        (*(void (__fastcall **)(CContextMenuCB *))(*(_QWORD *)v16 + 16LL))(v16);
        if ( v10 >= 0 )
        {
          pdcm.pidlFolder = ppidl;
          pdcm.cidl = v22;
          *(&pdcm.cidl + 1) = 0;
          pdcm.punkAssociationInfo = 0;
          pdcm.psf = (IShellFolder *)(v6 & -(__int64)(this != 0));
          pdcm.pcmcb = (IContextMenuCB *)ppv;
          pdcm.aKeys = (const HKEY *)v19;
          *(_QWORD *)&pdcm.cKeys = 2;
          pdcm.hwnd = a2;
          pdcm.apidl = a4;
          v10 = SHCreateDefaultContextMenu(&pdcm, &IID_IContextMenu, v5);
          ((void (__fastcall *)(struct IContextMenu **))(*ppv)[2].lpVtbl)(ppv);
        }
      }
    }
    CoTaskMemFree(ppidl);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v18 )
    RegCloseKey(v18);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180019f04  mov     [rsp-8+arg_8], rbx
0x180019f09  mov     [rsp-8+arg_10], r8d
0x180019f0e  push    rbp
0x180019f0f  push    rsi
0x180019f10  push    rdi
0x180019f11  push    r12
0x180019f13  push    r13
0x180019f15  push    r14
0x180019f17  push    r15
0x180019f19  lea     rbp, [rsp-1Fh]
0x180019f1e  sub     rsp, 90h
0x180019f25  mov     r12, [rbp+4Fh+ppv]
0x180019f29  lea     r13, [rcx+28h]
0x180019f2d  mov     rax, rcx
0x180019f30  mov     [rbp+4Fh+hKey], 0
0x180019f38  mov     rsi, r9
0x180019f3b  mov     [rbp+4Fh+var_A0], 0
0x180019f43  mov     r14, rcx
0x180019f46  lea     r9, [rbp+4Fh+hKey]; HKEY *
0x180019f4a  neg     rax
0x180019f4d  mov     qword ptr [r12], 0
0x180019f55  mov     r15, rdx
0x180019f58  lea     r8, [rbp+4Fh+var_A0]; HKEY *
0x180019f5c  mov     rdx, [rsi]; struct _ITEMIDLIST *
0x180019f5f  sbb     rcx, rcx
0x180019f62  and     rcx, r13; struct IShellFolder *
0x180019f65  call    ?FID_GetClassKeys@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST@@PEAPEAUHKEY__@@2@Z; FID_GetClassKeys(IShellFolder *,_ITEMIDLIST const *,HKEY__ * *,HKEY__ * *)
0x180019f6a  lea     r8, [rbp+4Fh+ppidl]; ppidl
0x180019f6e  mov     [rbp+4Fh+ppidl], 0
0x180019f76  mov     edx, 14h; csidl
0x180019f7b  mov     rcx, r15; hwnd
0x180019f7e  call    cs:__imp_SHGetSpecialFolderLocation
0x180019f84  mov     ebx, eax
0x180019f86  test    eax, eax
0x180019f88  js      loc_18001A086
0x180019f8e  mov     rax, [rbp+4Fh+var_A0]
0x180019f92  mov     rcx, [rsi]; struct _ITEMIDLIST *
0x180019f95  mov     [rbp+4Fh+var_98], rax
0x180019f99  mov     rax, [rbp+4Fh+hKey]
0x180019f9d  mov     [rbp+4Fh+var_90], rax
0x180019fa1  mov     [rbp+4Fh+ppv], 0
0x180019fa9  call    ?FID_IsFolder@@YAHPEFBU_ITEMIDLIST@@@Z; FID_IsFolder(_ITEMIDLIST const *)
0x180019fae  mov     ecx, 18h; this
0x180019fb3  mov     edi, eax
0x180019fb5  mov     ebx, 8007000Eh
0x180019fba  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180019fbf  test    rax, rax
0x180019fc2  jz      loc_18001A07C
0x180019fc8  mov     edx, edi; int
0x180019fca  mov     rcx, rax; this
0x180019fcd  call    ??0CContextMenuCB@@AEAA@H@Z; CContextMenuCB::CContextMenuCB(int)
0x180019fd2  mov     rdi, rax
0x180019fd5  test    rax, rax
0x180019fd8  jz      loc_18001A07C
0x180019fde  mov     rcx, [rax]
0x180019fe1  lea     r8, [rbp+4Fh+ppv]
0x180019fe5  lea     rdx, _GUID_3409e930_5a39_11d1_83fa_00a0c90dc849
0x180019fec  mov     rax, [rcx]
0x180019fef  mov     rcx, rdi
0x180019ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ff7  mov     rcx, [rdi]
0x180019ffa  mov     ebx, eax
0x180019ffc  mov     rax, [rcx+10h]
0x18001a000  mov     rcx, rdi
0x18001a003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a008  test    ebx, ebx
0x18001a00a  js      short loc_18001A07C
0x18001a00c  mov     rax, [rbp+4Fh+ppidl]
0x18001a010  lea     rdx, IID_IContextMenu; riid
0x18001a017  mov     [rbp+4Fh+pdcm.pidlFolder], rax
0x18001a01b  lea     rcx, [rbp+4Fh+pdcm]; pdcm
0x18001a01f  mov     eax, [rbp+4Fh+arg_10]
0x18001a022  neg     r14
0x18001a025  mov     [rbp+4Fh+pdcm.cidl], eax
0x18001a028  mov     r8, r12; ppv
0x18001a02b  sbb     rax, rax
0x18001a02e  mov     dword ptr [rbp+4Fh+pdcm+24h], 0
0x18001a035  and     rax, r13
0x18001a038  mov     [rbp+4Fh+pdcm.punkAssociationInfo], 0
0x18001a040  mov     [rbp+4Fh+pdcm.psf], rax
0x18001a044  mov     rax, [rbp+4Fh+ppv]
0x18001a048  mov     [rbp+4Fh+pdcm.pcmcb], rax
0x18001a04c  lea     rax, [rbp+4Fh+var_98]
0x18001a050  mov     [rbp+4Fh+pdcm.aKeys], rax
0x18001a054  mov     qword ptr [rbp+4Fh+pdcm.cKeys], 2
0x18001a05c  mov     [rbp+4Fh+pdcm.hwnd], r15
0x18001a060  mov     [rbp+4Fh+pdcm.apidl], rsi
0x18001a064  call    cs:__imp_SHCreateDefaultContextMenu
0x18001a06a  mov     rcx, [rbp+4Fh+ppv]
0x18001a06e  mov     ebx, eax
0x18001a070  mov     rax, [rcx]
0x18001a073  mov     rax, [rax+10h]
0x18001a077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a07c  mov     rcx, [rbp+4Fh+ppidl]; pv
0x18001a080  call    cs:__imp_CoTaskMemFree
0x18001a086  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18001a08a  test    rcx, rcx
0x18001a08d  jz      short loc_18001A095
0x18001a08f  call    cs:__imp_RegCloseKey
0x18001a095  mov     rcx, [rbp+4Fh+var_A0]; hKey
0x18001a099  test    rcx, rcx
0x18001a09c  jz      short loc_18001A0A4
0x18001a09e  call    cs:__imp_RegCloseKey
0x18001a0a4  mov     eax, ebx
0x18001a0a6  mov     rbx, [rsp+0C0h+arg_8]
0x18001a0ae  add     rsp, 90h
0x18001a0b5  pop     r15
0x18001a0b7  pop     r14
0x18001a0b9  pop     r13
0x18001a0bb  pop     r12
0x18001a0bd  pop     rdi
0x18001a0be  pop     rsi
0x18001a0bf  pop     rbp
0x18001a0c0  retn
```
