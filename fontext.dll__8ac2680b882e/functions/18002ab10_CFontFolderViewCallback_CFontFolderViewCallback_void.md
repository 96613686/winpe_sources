# CFontFolderViewCallback::~CFontFolderViewCallback(void)

- ea: `0x18002ab10`
- end: `0x18002ab7a`
- name: `??1CFontFolderViewCallback@@AEAA@XZ`
- size: `106`
- prototype: `void __fastcall(CFontFolderViewCallback *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002af60`

## callees

- `0x18002ab10`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ab67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ab67`

## pseudocode

```c
void __fastcall CFontFolderViewCallback::~CFontFolderViewCallback(CFontFolderViewCallback *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CFontFolderViewCallback::`vftable'{for `IShellFolderViewCB'};
  *((_QWORD *)this + 1) = &CFontFolderViewCallback::`vftable'{for `IFolderViewSettings'};
  *((_QWORD *)this + 2) = &CFontFolderViewCallback::`vftable'{for `IObjectWithSite'};
  v2 = *((_QWORD *)this + 5);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 4);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  CoTaskMemFree(*((LPVOID *)this + 9));
  _InterlockedDecrement(&g_cRefCount);
}

```

## disassembly

```asm
0x18002ab10  push    rbx
0x18002ab12  sub     rsp, 20h
0x18002ab16  lea     rax, ??_7CFontFolderViewCallback@@6BIShellFolderViewCB@@@; const CFontFolderViewCallback::`vftable'{for `IShellFolderViewCB'}
0x18002ab1d  mov     rbx, rcx
0x18002ab20  mov     [rcx], rax
0x18002ab23  lea     rax, ??_7CFontFolderViewCallback@@6BIFolderViewSettings@@@; const CFontFolderViewCallback::`vftable'{for `IFolderViewSettings'}
0x18002ab2a  mov     [rcx+8], rax
0x18002ab2e  lea     rax, ??_7CFontFolderViewCallback@@6BIObjectWithSite@@@; const CFontFolderViewCallback::`vftable'{for `IObjectWithSite'}
0x18002ab35  mov     [rcx+10h], rax
0x18002ab39  mov     rcx, [rcx+28h]
0x18002ab3d  test    rcx, rcx
0x18002ab40  jz      short loc_18002AB4E
0x18002ab42  mov     rax, [rcx]
0x18002ab45  mov     rax, [rax+10h]
0x18002ab49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab4e  mov     rcx, [rbx+20h]
0x18002ab52  test    rcx, rcx
0x18002ab55  jz      short loc_18002AB63
0x18002ab57  mov     rax, [rcx]
0x18002ab5a  mov     rax, [rax+10h]
0x18002ab5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab63  mov     rcx, [rbx+48h]; pv
0x18002ab67  call    cs:__imp_CoTaskMemFree
0x18002ab6d  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x18002ab74  add     rsp, 20h
0x18002ab78  pop     rbx
0x18002ab79  retn
```
