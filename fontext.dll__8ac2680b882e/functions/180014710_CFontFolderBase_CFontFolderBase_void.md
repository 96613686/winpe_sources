# CFontFolderBase::~CFontFolderBase(void)

- ea: `0x180014710`
- end: `0x1800147df`
- name: `??1CFontFolderBase@@MEAA@XZ`
- size: `207`
- prototype: `void __fastcall(CFontFolderBase *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014b80`

## callees

- `0x180014510`

## import_xrefs

- `SHLWAPI!__imp_SHWeakReleaseInterface` at `0x1800147af`
- `SHLWAPI!__imp_SHWeakReleaseInterface` at `0x1800147af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014796`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014796`

## pseudocode

```c
void __fastcall CFontFolderBase::~CFontFolderBase(CFontFolderBase *this)
{
  unsigned __int64 v1; // rdi

  v1 = (unsigned __int64)this + 40;
  *(_QWORD *)this = &CFontFolderBase::`vftable'{for `CAggregatedUnknown'};
  *((_QWORD *)this + 4) = &CFontFolderBase::`vftable'{for `IPersistFolder2'};
  *((_QWORD *)this + 5) = &CFontFolderBase::`vftable'{for `IShellFolder2'};
  *((_QWORD *)this + 6) = &CFontFolderBase::`vftable'{for `IShellIconOverlay'};
  *((_QWORD *)this + 7) = &CFontFolderBase::`vftable'{for `IFrameLayoutDefinition'};
  *((_QWORD *)this + 8) = &CFontFolder::`vftable'{for `IControlPanelNavPaneProvider'};
  *((_QWORD *)this + 9) = &CFontFolderBase::`vftable'{for `IExplorerPaneVisibility'};
  *((_QWORD *)this + 10) = &CFontFolder::`vftable'{for `IInfoPaneProvider'};
  *((_QWORD *)this + 11) = &CFontFolderBase::`vftable'{for `IFontFolderPrivate'};
  *((_QWORD *)this + 12) = &CFontFamilyFolder::`vftable'{for `CItemIDFactory<FID,156830041>'};
  CoTaskMemFree(*((LPVOID *)this + 14));
  SHWeakReleaseInterface(v1 & -(__int64)(this != 0), (char *)this + 128);
  _InterlockedDecrement(&g_cRefCount);
  CItemIDFactory<FID,156830041>::~CItemIDFactory<FID,156830041>((char *)this + 96);
  *(_QWORD *)this = &CAggregatedUnknown::`vftable';
}

```

## disassembly

```asm
0x180014710  mov     [rsp+arg_0], rbx
0x180014715  mov     [rsp+arg_8], rsi
0x18001471a  push    rdi
0x18001471b  sub     rsp, 20h
0x18001471f  lea     rdi, [rcx+28h]
0x180014723  mov     rsi, rcx
0x180014726  lea     rax, ??_7CFontFolderBase@@6BCAggregatedUnknown@@@; const CFontFolderBase::`vftable'{for `CAggregatedUnknown'}
0x18001472d  mov     [rcx], rax
0x180014730  lea     rax, ??_7CFontFolderBase@@6BIPersistFolder2@@@; const CFontFolderBase::`vftable'{for `IPersistFolder2'}
0x180014737  mov     [rcx+20h], rax
0x18001473b  lea     rax, ??_7CFontFolderBase@@6BIShellFolder2@@@; const CFontFolderBase::`vftable'{for `IShellFolder2'}
0x180014742  mov     [rdi], rax
0x180014745  lea     rax, ??_7CFontFolderBase@@6BIShellIconOverlay@@@; const CFontFolderBase::`vftable'{for `IShellIconOverlay'}
0x18001474c  mov     [rcx+30h], rax
0x180014750  lea     rax, ??_7CFontFolderBase@@6BIFrameLayoutDefinition@@@; const CFontFolderBase::`vftable'{for `IFrameLayoutDefinition'}
0x180014757  mov     [rcx+38h], rax
0x18001475b  lea     rax, ??_7CFontFolder@@6BIControlPanelNavPaneProvider@@@; const CFontFolder::`vftable'{for `IControlPanelNavPaneProvider'}
0x180014762  mov     [rcx+40h], rax
0x180014766  lea     rax, ??_7CFontFolderBase@@6BIExplorerPaneVisibility@@@; const CFontFolderBase::`vftable'{for `IExplorerPaneVisibility'}
0x18001476d  mov     [rcx+48h], rax
0x180014771  lea     rax, ??_7CFontFolder@@6BIInfoPaneProvider@@@; const CFontFolder::`vftable'{for `IInfoPaneProvider'}
0x180014778  mov     [rcx+50h], rax
0x18001477c  lea     rax, ??_7CFontFolderBase@@6BIFontFolderPrivate@@@; const CFontFolderBase::`vftable'{for `IFontFolderPrivate'}
0x180014783  mov     [rcx+58h], rax
0x180014787  lea     rax, ??_7CFontFamilyFolder@@6B?$CItemIDFactory@UFID@@$0JFJAJFJ@@@@; const CFontFamilyFolder::`vftable'{for `CItemIDFactory<FID,156830041>'}
0x18001478e  mov     [rcx+60h], rax
0x180014792  mov     rcx, [rcx+70h]; pv
0x180014796  call    cs:__imp_CoTaskMemFree
0x18001479c  mov     rax, rsi
0x18001479f  lea     rdx, [rsi+80h]
0x1800147a6  neg     rax
0x1800147a9  sbb     rcx, rcx
0x1800147ac  and     rcx, rdi
0x1800147af  call    cs:__imp_SHWeakReleaseInterface
0x1800147b5  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x1800147bc  lea     rcx, [rsi+60h]
0x1800147c0  call    ??1?$CItemIDFactory@UFID@@$0JFJAJFJ@@@MEAA@XZ; CItemIDFactory<FID,156830041>::~CItemIDFactory<FID,156830041>(void)
0x1800147c5  mov     rbx, [rsp+28h+arg_0]
0x1800147ca  lea     rax, ??_7CAggregatedUnknown@@6B@; const CAggregatedUnknown::`vftable'
0x1800147d1  mov     [rsi], rax
0x1800147d4  mov     rsi, [rsp+28h+arg_8]
0x1800147d9  add     rsp, 20h
0x1800147dd  pop     rdi
0x1800147de  retn
```
