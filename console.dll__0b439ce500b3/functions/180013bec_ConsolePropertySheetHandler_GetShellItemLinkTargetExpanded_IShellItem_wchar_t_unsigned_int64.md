# ConsolePropertySheetHandler::_GetShellItemLinkTargetExpanded(IShellItem *,wchar_t *,unsigned __int64)

- ea: `0x180013bec`
- end: `0x180013cd9`
- name: `?_GetShellItemLinkTargetExpanded@ConsolePropertySheetHandler@@AEAAJPEAUIShellItem@@PEA_W_K@Z`
- size: `237`
- prototype: `int(ConsolePropertySheetHandler *__hidden this, struct IShellItem *, wchar_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013e00`

## callees

- `0x180004dcc`
- `0x180005e60`
- `0x1800132e4`
- `0x1800136d4`
- `0x180013bec`
- `0x18001a010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180013c61`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180013c61`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180013c4f`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180013c4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConsolePropertySheetHandler::_GetShellItemLinkTargetExpanded(
        const ITEMIDLIST *this,
        struct IShellItem *a2,
        wchar_t *a3)
{
  ConsolePropertySheetHandler *v5; // rcx
  HRESULT TargetIdList; // ebx
  __int64 v7; // rax
  LPCITEMIDLIST pidl; // [rsp+30h] [rbp+10h] BYREF
  void *ppv; // [rsp+48h] [rbp+28h] BYREF

  pidl = this;
  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  ppv = 0;
  pidl = 0;
  TargetIdList = ConsolePropertySheetHandler::GetTargetIdList(v5, a2, (struct _ITEMIDLIST **)&pidl);
  if ( TargetIdList >= 0 )
  {
    TargetIdList = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    ILFree((LPITEMIDLIST)pidl);
    if ( TargetIdList >= 0 )
    {
      pidl = 0;
      v7 = *(_QWORD *)ppv;
      pidl = 0;
      TargetIdList = (*(__int64 (__fastcall **)(void *, __int64, LPCITEMIDLIST *))(v7 + 40))(ppv, 2147844096LL, &pidl);
      if ( TargetIdList >= 0 )
        TargetIdList = StringCchCopyW(a3, 0x104u, &pidl->mkid.cb);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pidl);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)TargetIdList;
}

```

## disassembly

```asm
0x180013bec  mov     rax, rsp
0x180013bef  mov     [rax+10h], rbx
0x180013bf3  mov     [rax+18h], rdi
0x180013bf7  mov     [rax+20h], r9
0x180013bfb  mov     [rax+8], rcx
0x180013bff  push    rbp
0x180013c00  mov     rbp, rsp
0x180013c03  sub     rsp, 20h
0x180013c07  mov     rdi, r8
0x180013c0a  mov     rbx, rdx
0x180013c0d  mov     [rbp+ppv], 0
0x180013c15  lea     rcx, [rbp+ppv]
0x180013c19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013c1e  mov     [rbp+ppv], 0
0x180013c26  mov     [rbp+pidl], 0
0x180013c2e  lea     r8, [rbp+pidl]; struct _ITEMIDLIST **
0x180013c32  mov     rdx, rbx; struct IShellItem *
0x180013c35  call    ?GetTargetIdList@ConsolePropertySheetHandler@@AEAAJPEAUIShellItem@@PEAPEFAU_ITEMIDLIST@@@Z; ConsolePropertySheetHandler::GetTargetIdList(IShellItem *,_ITEMIDLIST * *)
0x180013c3a  mov     ebx, eax
0x180013c3c  test    eax, eax
0x180013c3e  js      short loc_180013CBD
0x180013c40  lea     r8, [rbp+ppv]; ppv
0x180013c44  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180013c4b  mov     rcx, [rbp+pidl]; pidl
0x180013c4f  call    cs:__imp_SHCreateItemFromIDList
0x180013c56  nop     dword ptr [rax+rax+00h]
0x180013c5b  mov     ebx, eax
0x180013c5d  mov     rcx, [rbp+pidl]; pidl
0x180013c61  call    cs:__imp_ILFree
0x180013c68  nop     dword ptr [rax+rax+00h]
0x180013c6d  test    ebx, ebx
0x180013c6f  js      short loc_180013CBD
0x180013c71  mov     [rbp+pidl], 0
0x180013c79  mov     rcx, [rbp+ppv]
0x180013c7d  mov     rax, [rcx]
0x180013c80  mov     [rbp+pidl], 0
0x180013c88  lea     r8, [rbp+pidl]
0x180013c8c  mov     edx, 80058000h
0x180013c91  mov     rax, [rax+28h]
0x180013c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c9a  mov     ebx, eax
0x180013c9c  test    eax, eax
0x180013c9e  js      short loc_180013CB3
0x180013ca0  mov     r8, [rbp+pidl]; wchar_t *
0x180013ca4  mov     edx, 104h; unsigned __int64
0x180013ca9  mov     rcx, rdi; wchar_t *
0x180013cac  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180013cb1  mov     ebx, eax
0x180013cb3  lea     rcx, [rbp+pidl]
0x180013cb7  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180013cbc  nop
0x180013cbd  lea     rcx, [rbp+ppv]
0x180013cc1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013cc6  mov     eax, ebx
0x180013cc8  mov     rbx, [rsp+20h+arg_8]
0x180013ccd  mov     rdi, [rsp+20h+arg_10]
0x180013cd2  add     rsp, 20h
0x180013cd6  pop     rbp
0x180013cd7  retn
```
