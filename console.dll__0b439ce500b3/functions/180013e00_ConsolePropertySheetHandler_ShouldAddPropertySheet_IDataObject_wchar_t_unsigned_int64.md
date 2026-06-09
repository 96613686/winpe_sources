# ConsolePropertySheetHandler::_ShouldAddPropertySheet(IDataObject *,wchar_t *,unsigned __int64)

- ea: `0x180013e00`
- end: `0x180013fd1`
- name: `?_ShouldAddPropertySheet@ConsolePropertySheetHandler@@AEAAJPEAUIDataObject@@PEA_W_K@Z`
- size: `465`
- prototype: `int(ConsolePropertySheetHandler *__hidden this, struct IDataObject *, wchar_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800137e0`

## callees

- `0x1800015b0`
- `0x180002088`
- `0x180004dcc`
- `0x180005e60`
- `0x1800132e4`
- `0x180013bec`
- `0x180013e00`
- `0x18001a010`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFileInfoW` at `0x180013f20`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFileInfoW` at `0x180013f20`
- `ext-ms-win-shell-shell32-l1-2-2!SHCreateShellItemArrayFromDataObject` at `0x180013e55`
- `ext-ms-win-shell-shell32-l1-2-2!SHCreateShellItemArrayFromDataObject` at `0x180013e55`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ConsolePropertySheetHandler::_ShouldAddPropertySheet(
        ConsolePropertySheetHandler *this,
        struct IDataObject *a2,
        wchar_t *a3)
{
  int ShellItemLinkTargetExpanded; // ebx
  void *v6; // rdi
  __int64 (__fastcall *v7)(void *, _QWORD, struct IShellItem **); // rbx
  const ITEMIDLIST *v8; // rcx
  struct IShellItemVtbl *lpVtbl; // rax
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  struct IShellItem *v12; // [rsp+38h] [rbp-C8h] BYREF
  void *ppv; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v14; // [rsp+48h] [rbp-B8h] BYREF
  SHFILEINFOW psfi; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+310h] [rbp+210h] BYREF

  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  ShellItemLinkTargetExpanded = SHCreateShellItemArrayFromDataObject(
                                  a2,
                                  &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                                  &ppv);
  if ( ShellItemLinkTargetExpanded >= 0 )
  {
    v11 = 0;
    ShellItemLinkTargetExpanded = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppv + 56LL))(ppv, &v11);
    if ( ShellItemLinkTargetExpanded >= 0 )
    {
      if ( v11 == 1 )
      {
        v12 = 0;
        v6 = ppv;
        v7 = *(__int64 (__fastcall **)(void *, _QWORD, struct IShellItem **))(*(_QWORD *)ppv + 64LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
        ShellItemLinkTargetExpanded = v7(v6, 0, &v12);
        if ( ShellItemLinkTargetExpanded >= 0 )
        {
          ShellItemLinkTargetExpanded = ConsolePropertySheetHandler::_GetShellItemLinkTargetExpanded(v8, v12, pszPath);
          if ( ShellItemLinkTargetExpanded >= 0 )
          {
            memset_0(&psfi, 0, sizeof(psfi));
            if ( (unsigned int)SHGetFileInfoW(pszPath, 0, &psfi, 0x2B8u, 0x2000u) == 17744 )
            {
              v14 = 0;
              lpVtbl = v12->lpVtbl;
              v14 = 0;
              ShellItemLinkTargetExpanded = ((__int64 (__fastcall *)(struct IShellItem *, __int64, wchar_t **))lpVtbl->GetDisplayName)(
                                              v12,
                                              2147844096LL,
                                              &v14);
              if ( ShellItemLinkTargetExpanded >= 0 )
                ShellItemLinkTargetExpanded = StringCchCopyW(a3, 0x104u, v14);
              wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>((void **)&v14);
            }
            else
            {
              ShellItemLinkTargetExpanded = -2147467259;
            }
          }
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
      }
      else
      {
        ShellItemLinkTargetExpanded = -2147467259;
      }
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)ShellItemLinkTargetExpanded;
}

```

## disassembly

```asm
0x180013e00  mov     [rsp-8+arg_0], rbx
0x180013e05  mov     [rsp-8+arg_18], rsi
0x180013e0a  push    rbp
0x180013e0b  push    rdi
0x180013e0c  push    r14
0x180013e0e  lea     rbp, [rsp-430h]
0x180013e16  sub     rsp, 530h
0x180013e1d  mov     rax, cs:__security_cookie
0x180013e24  xor     rax, rsp
0x180013e27  mov     [rbp+440h+var_20], rax
0x180013e2e  mov     rsi, r8
0x180013e31  mov     rbx, rdx
0x180013e34  xor     r14d, r14d
0x180013e37  mov     [rsp+540h+ppv], r14
0x180013e3c  lea     rcx, [rsp+540h+ppv]
0x180013e41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013e46  lea     r8, [rsp+540h+ppv]; ppv
0x180013e4b  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x180013e52  mov     rcx, rbx; pdo
0x180013e55  call    cs:__imp_SHCreateShellItemArrayFromDataObject
0x180013e5c  nop     dword ptr [rax+rax+00h]
0x180013e61  mov     ebx, eax
0x180013e63  test    eax, eax
0x180013e65  js      loc_180013F9D
0x180013e6b  mov     [rsp+540h+var_510], r14d
0x180013e70  mov     rcx, [rsp+540h+ppv]
0x180013e75  mov     rax, [rcx]
0x180013e78  lea     rdx, [rsp+540h+var_510]
0x180013e7d  mov     rax, [rax+38h]
0x180013e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e86  mov     ebx, eax
0x180013e88  test    eax, eax
0x180013e8a  js      loc_180013F9D
0x180013e90  cmp     [rsp+540h+var_510], 1
0x180013e95  jz      short loc_180013EA1
0x180013e97  mov     ebx, 80004005h
0x180013e9c  jmp     loc_180013F9D
0x180013ea1  mov     [rsp+540h+var_508], r14
0x180013ea6  mov     rdi, [rsp+540h+ppv]
0x180013eab  mov     rax, [rdi]
0x180013eae  mov     rbx, [rax+40h]
0x180013eb2  lea     rcx, [rsp+540h+var_508]
0x180013eb7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013ebc  lea     r8, [rsp+540h+var_508]
0x180013ec1  xor     edx, edx
0x180013ec3  mov     rcx, rdi
0x180013ec6  mov     rax, rbx
0x180013ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ece  mov     ebx, eax
0x180013ed0  test    eax, eax
0x180013ed2  js      loc_180013F92
0x180013ed8  lea     r8, [rbp+440h+pszPath]; wchar_t *
0x180013edf  mov     rdx, [rsp+540h+var_508]; struct IShellItem *
0x180013ee4  call    ?_GetShellItemLinkTargetExpanded@ConsolePropertySheetHandler@@AEAAJPEAUIShellItem@@PEA_W_K@Z; ConsolePropertySheetHandler::_GetShellItemLinkTargetExpanded(IShellItem *,wchar_t *,unsigned __int64)
0x180013ee9  mov     ebx, eax
0x180013eeb  test    eax, eax
0x180013eed  js      loc_180013F92
0x180013ef3  mov     ebx, 2B8h
0x180013ef8  mov     r8d, ebx; Size
0x180013efb  xor     edx, edx; Val
0x180013efd  lea     rcx, [rsp+540h+psfi]; void *
0x180013f02  call    memset_0
0x180013f07  mov     [rsp+540h+uFlags], 2000h; uFlags
0x180013f0f  mov     r9d, ebx; cbFileInfo
0x180013f12  lea     r8, [rsp+540h+psfi]; psfi
0x180013f17  xor     edx, edx; dwFileAttributes
0x180013f19  lea     rcx, [rbp+440h+pszPath]; pszPath
0x180013f20  call    cs:__imp_SHGetFileInfoW
0x180013f27  nop     dword ptr [rax+rax+00h]
0x180013f2c  mov     rcx, rax
0x180013f2f  shr     rcx, 10h
0x180013f33  test    cx, cx
0x180013f36  jnz     short loc_180013F8D
0x180013f38  mov     ecx, 4550h
0x180013f3d  cmp     ax, cx
0x180013f40  jnz     short loc_180013F8D
0x180013f42  mov     [rsp+540h+var_4F8], r14
0x180013f47  mov     rcx, [rsp+540h+var_508]
0x180013f4c  mov     rax, [rcx]
0x180013f4f  mov     [rsp+540h+var_4F8], r14
0x180013f54  lea     r8, [rsp+540h+var_4F8]
0x180013f59  mov     edx, 80058000h
0x180013f5e  mov     rax, [rax+28h]
0x180013f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f67  mov     ebx, eax
0x180013f69  test    eax, eax
0x180013f6b  js      short loc_180013F81
0x180013f6d  mov     r8, [rsp+540h+var_4F8]; wchar_t *
0x180013f72  mov     edx, 104h; unsigned __int64
0x180013f77  mov     rcx, rsi; wchar_t *
0x180013f7a  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180013f7f  mov     ebx, eax
0x180013f81  lea     rcx, [rsp+540h+var_4F8]
0x180013f86  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180013f8b  jmp     short loc_180013F92
0x180013f8d  mov     ebx, 80004005h
0x180013f92  lea     rcx, [rsp+540h+var_508]
0x180013f97  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013f9c  nop
0x180013f9d  lea     rcx, [rsp+540h+ppv]
0x180013fa2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013fa7  mov     eax, ebx
0x180013fa9  mov     rcx, [rbp+440h+var_20]
0x180013fb0  xor     rcx, rsp; StackCookie
0x180013fb3  call    __security_check_cookie
0x180013fb8  lea     r11, [rsp+540h+var_10]
0x180013fc0  mov     rbx, [r11+20h]
0x180013fc4  mov     rsi, [r11+38h]
0x180013fc8  mov     rsp, r11
0x180013fcb  pop     r14
0x180013fcd  pop     rdi
0x180013fce  pop     rbp
0x180013fcf  retn
```
