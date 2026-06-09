# CFontFamilyFolder::s_CreateInstance(_GUID const &,void * *,ushort const *,_ITEMIDLIST const *,_ITEMIDLIST const *)

- ea: `0x18001a8b4`
- end: `0x18001a9d8`
- name: `?s_CreateInstance@CFontFamilyFolder@@SAJAEBU_GUID@@PEAPEAXPEBGPEFBU_ITEMIDLIST@@3@Z`
- size: `292`
- prototype: `static int(const struct _GUID *, void **, const unsigned __int16 *, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014f20`

## callees

- `0x180006624`
- `0x18001424c`
- `0x180018dcc`
- `0x18001a8b4`
- `0x18001c0d0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a964`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a964`

## pseudocode

```c
__int64 __fastcall CFontFamilyFolder::s_CreateInstance(
        const struct _GUID *a1,
        void **a2,
        const unsigned __int16 *a3,
        const struct _ITEMIDLIST *a4,
        const struct _ITEMIDLIST *a5)
{
  int v9; // ebx
  CFontFolderBase *v10; // rax
  CFontFolderBase *v11; // rdi

  v9 = -2147024882;
  v10 = (CFontFolderBase *)DirectUI::HAllocAndZero((DirectUI *)0xC8, (unsigned __int64)a2);
  v11 = v10;
  if ( v10 )
  {
    CFontFolderBase::CFontFolderBase(v10);
    *((_QWORD *)v11 + 4) = &CFontFolderBase::`vftable'{for `IPersistFolder2'};
    *(_QWORD *)v11 = &CFontFamilyFolder::`vftable'{for `CAggregatedUnknown'};
    *((_QWORD *)v11 + 5) = &CFontFamilyFolder::`vftable'{for `IShellFolder2'};
    *((_QWORD *)v11 + 6) = &CFontFolderBase::`vftable'{for `IShellIconOverlay'};
    *((_QWORD *)v11 + 7) = &CFontFolderBase::`vftable'{for `IFrameLayoutDefinition'};
    *((_QWORD *)v11 + 8) = &CFontFolder::`vftable'{for `IControlPanelNavPaneProvider'};
    *((_QWORD *)v11 + 9) = &CFontFolderBase::`vftable'{for `IExplorerPaneVisibility'};
    *((_QWORD *)v11 + 10) = &CFontFamilyFolder::`vftable'{for `IInfoPaneProvider'};
    *((_QWORD *)v11 + 11) = &CFontFolderBase::`vftable'{for `IFontFolderPrivate'};
    *((_QWORD *)v11 + 12) = &CFontFamilyFolder::`vftable'{for `CItemIDFactory<FID,156830041>'};
    CoTaskMemFree(*((LPVOID *)v11 + 14));
    *((_QWORD *)v11 + 14) = 0;
    v9 = SHILCombine(a4, a5, (struct _ITEMIDLIST **)v11 + 14);
    if ( v9 >= 0 )
    {
      v9 = StringCchCopyW((unsigned __int16 *)v11 + 68, 0x20u, a3);
      if ( v9 >= 0 )
        v9 = (**(__int64 (__fastcall ***)(CFontFolderBase *, const struct _GUID *, void **))v11)(v11, a1, a2);
    }
    (*(void (__fastcall **)(CFontFolderBase *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001a8b4  push    rbx
0x18001a8b6  push    rbp
0x18001a8b7  push    rsi
0x18001a8b8  push    rdi
0x18001a8b9  push    r14
0x18001a8bb  push    r15
0x18001a8bd  sub     rsp, 28h
0x18001a8c1  mov     r14, rcx
0x18001a8c4  mov     r15, r9
0x18001a8c7  mov     ecx, 0C8h; this
0x18001a8cc  mov     rsi, r8
0x18001a8cf  mov     rbp, rdx
0x18001a8d2  mov     ebx, 8007000Eh
0x18001a8d7  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18001a8dc  mov     rdi, rax
0x18001a8df  test    rax, rax
0x18001a8e2  jz      loc_18001A9C9
0x18001a8e8  mov     rcx, rax; this
0x18001a8eb  call    ??0CFontFolderBase@@IEAA@XZ; CFontFolderBase::CFontFolderBase(void)
0x18001a8f0  lea     rax, ??_7CFontFolderBase@@6BIPersistFolder2@@@; const CFontFolderBase::`vftable'{for `IPersistFolder2'}
0x18001a8f7  mov     [rdi+20h], rax
0x18001a8fb  lea     r10, ??_7CFontFamilyFolder@@6BCAggregatedUnknown@@@; const CFontFamilyFolder::`vftable'{for `CAggregatedUnknown'}
0x18001a902  lea     rax, ??_7CFontFamilyFolder@@6BIShellFolder2@@@; const CFontFamilyFolder::`vftable'{for `IShellFolder2'}
0x18001a909  mov     [rdi], r10
0x18001a90c  mov     [rdi+28h], rax
0x18001a910  lea     rbx, [rdi+70h]
0x18001a914  lea     rax, ??_7CFontFolderBase@@6BIShellIconOverlay@@@; const CFontFolderBase::`vftable'{for `IShellIconOverlay'}
0x18001a91b  mov     [rdi+30h], rax
0x18001a91f  lea     rax, ??_7CFontFolderBase@@6BIFrameLayoutDefinition@@@; const CFontFolderBase::`vftable'{for `IFrameLayoutDefinition'}
0x18001a926  mov     [rdi+38h], rax
0x18001a92a  lea     rax, ??_7CFontFolder@@6BIControlPanelNavPaneProvider@@@; const CFontFolder::`vftable'{for `IControlPanelNavPaneProvider'}
0x18001a931  mov     [rdi+40h], rax
0x18001a935  lea     rax, ??_7CFontFolderBase@@6BIExplorerPaneVisibility@@@; const CFontFolderBase::`vftable'{for `IExplorerPaneVisibility'}
0x18001a93c  mov     [rdi+48h], rax
0x18001a940  lea     rax, ??_7CFontFamilyFolder@@6BIInfoPaneProvider@@@; const CFontFamilyFolder::`vftable'{for `IInfoPaneProvider'}
0x18001a947  mov     [rdi+50h], rax
0x18001a94b  lea     rax, ??_7CFontFolderBase@@6BIFontFolderPrivate@@@; const CFontFolderBase::`vftable'{for `IFontFolderPrivate'}
0x18001a952  mov     [rdi+58h], rax
0x18001a956  lea     rax, ??_7CFontFamilyFolder@@6B?$CItemIDFactory@UFID@@$0JFJAJFJ@@@@; const CFontFamilyFolder::`vftable'{for `CItemIDFactory<FID,156830041>'}
0x18001a95d  mov     [rdi+60h], rax
0x18001a961  mov     rcx, [rbx]; pv
0x18001a964  call    cs:__imp_CoTaskMemFree
0x18001a96a  mov     rdx, [rsp+58h+arg_20]; struct _ITEMIDLIST *
0x18001a972  mov     r8, rbx; struct _ITEMIDLIST **
0x18001a975  mov     rcx, r15; struct _ITEMIDLIST *
0x18001a978  mov     qword ptr [rbx], 0
0x18001a97f  call    ?SHILCombine@@YAJPEFBU_ITEMIDLIST@@0PEAPEFAU1@@Z; SHILCombine(_ITEMIDLIST const *,_ITEMIDLIST const *,_ITEMIDLIST * *)
0x18001a984  mov     ebx, eax
0x18001a986  test    eax, eax
0x18001a988  js      short loc_18001A9BA
0x18001a98a  lea     rcx, [rdi+88h]; unsigned __int16 *
0x18001a991  mov     r8, rsi; unsigned __int16 *
0x18001a994  mov     edx, 20h ; ' '; unsigned __int64
0x18001a999  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a99e  mov     ebx, eax
0x18001a9a0  test    eax, eax
0x18001a9a2  js      short loc_18001A9BA
0x18001a9a4  mov     rax, [rdi]
0x18001a9a7  mov     r8, rbp
0x18001a9aa  mov     rdx, r14
0x18001a9ad  mov     rcx, rdi
0x18001a9b0  mov     rax, [rax]
0x18001a9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9b8  mov     ebx, eax
0x18001a9ba  mov     rax, [rdi]
0x18001a9bd  mov     rcx, rdi
0x18001a9c0  mov     rax, [rax+10h]
0x18001a9c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9c9  mov     eax, ebx
0x18001a9cb  add     rsp, 28h
0x18001a9cf  pop     r15
0x18001a9d1  pop     r14
0x18001a9d3  pop     rdi
0x18001a9d4  pop     rsi
0x18001a9d5  pop     rbp
0x18001a9d6  pop     rbx
0x18001a9d7  retn
```
