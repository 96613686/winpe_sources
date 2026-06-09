# CSharingPropertyPage::_ShowSharingWizard(HWND__ *,ushort const *)

- ea: `0x180062f84`
- end: `0x18006307e`
- name: `?_ShowSharingWizard@CSharingPropertyPage@@IEAAXPEAUHWND__@@PEBG@Z`
- size: `250`
- prototype: `void(CSharingPropertyPage *__hidden this, HWND, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180062788`

## callees

- `0x180062f84`
- `0x180071e2c`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006300c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006300c`
- `SHELL32!SHParseDisplayName` at `0x180062fb6`
- `SHELL32!SHParseDisplayName` at `0x180062fb6`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x180062fd9`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x180062fd9`
- `SHELL32!__imp_ILFree` at `0x18006306d`
- `SHELL32!__imp_ILFree` at `0x18006306d`

## pseudocode

```c
void __fastcall CSharingPropertyPage::_ShowSharingWizard(
        CSharingPropertyPage *this,
        HWND a2,
        const unsigned __int16 *a3)
{
  LPVOID ppv; // [rsp+30h] [rbp-10h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-8h] BYREF
  CSharingPropertyPage *v6; // [rsp+50h] [rbp+10h] BYREF
  IShellItemArray *ppsiItemArray; // [rsp+68h] [rbp+28h] BYREF

  v6 = this;
  ppidl = 0;
  if ( SHParseDisplayName(a3, 0, &ppidl, 0, 0) >= 0 )
  {
    ppsiItemArray = 0;
    if ( SHCreateShellItemArrayFromIDLists(1u, (LPCITEMIDLIST *)&ppidl, &ppsiItemArray) >= 0 )
    {
      ppv = 0;
      if ( CoCreateInstance(&CLSID_SharingConfigurationManager, 0, 1u, &GUID_14aa4ab8_abe3_4a07_a290_1d5dccdd2fc2, &ppv) >= 0 )
      {
        LODWORD(v6) = 0;
        if ( (*(int (__fastcall **)(LPVOID, IShellItemArray *, CSharingPropertyPage **))(*(_QWORD *)ppv + 88LL))(
               ppv,
               ppsiItemArray,
               &v6) >= 0 )
          ShowModalSharingWizard(a2, ppsiItemArray, (unsigned int)v6);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      ((void (__fastcall *)(IShellItemArray *))ppsiItemArray->lpVtbl->Release)(ppsiItemArray);
    }
    ILFree(ppidl);
  }
}

```

## disassembly

```asm
0x180062f84  mov     [rsp-8+arg_8], rbx
0x180062f89  mov     [rsp-8+arg_0], rcx
0x180062f8e  push    rbp
0x180062f8f  mov     rbp, rsp
0x180062f92  sub     rsp, 40h
0x180062f96  mov     rcx, r8; pszName
0x180062f99  mov     [rbp+ppidl], 0
0x180062fa1  mov     rbx, rdx
0x180062fa4  mov     [rsp+40h+psfgaoOut], 0; psfgaoOut
0x180062fad  lea     r8, [rbp+ppidl]; ppidl
0x180062fb1  xor     edx, edx; pbc
0x180062fb3  xor     r9d, r9d; sfgaoIn
0x180062fb6  call    cs:__imp_SHParseDisplayName
0x180062fbc  test    eax, eax
0x180062fbe  js      loc_180063073
0x180062fc4  lea     r8, [rbp+ppsiItemArray]; ppsiItemArray
0x180062fc8  mov     [rbp+ppsiItemArray], 0
0x180062fd0  lea     rdx, [rbp+ppidl]; rgpidl
0x180062fd4  mov     ecx, 1; cidl
0x180062fd9  call    cs:__imp_SHCreateShellItemArrayFromIDLists
0x180062fdf  test    eax, eax
0x180062fe1  js      loc_180063069
0x180062fe7  xor     edx, edx; pUnkOuter
0x180062fe9  mov     [rbp+ppv], 0
0x180062ff1  lea     rax, [rbp+ppv]
0x180062ff5  lea     r9, _GUID_14aa4ab8_abe3_4a07_a290_1d5dccdd2fc2; riid
0x180062ffc  mov     [rsp+40h+psfgaoOut], rax; ppv
0x180063001  lea     rcx, CLSID_SharingConfigurationManager; rclsid
0x180063008  lea     r8d, [rdx+1]; dwClsContext
0x18006300c  call    cs:__imp_CoCreateInstance
0x180063012  test    eax, eax
0x180063014  js      short loc_180063059
0x180063016  mov     rcx, [rbp+ppv]
0x18006301a  lea     r8, [rbp+arg_0]
0x18006301e  mov     rdx, [rbp+ppsiItemArray]
0x180063022  mov     dword ptr [rbp+arg_0], 0
0x180063029  mov     rax, [rcx]
0x18006302c  mov     rax, [rax+58h]
0x180063030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063035  test    eax, eax
0x180063037  js      short loc_180063049
0x180063039  mov     r8d, dword ptr [rbp+arg_0]
0x18006303d  mov     rcx, rbx
0x180063040  mov     rdx, [rbp+ppsiItemArray]
0x180063044  call    ?ShowModalSharingWizard@@YAJPEAUHWND__@@PEAUIShellItemArray@@W4SHARE_MODE@@@Z; ShowModalSharingWizard(HWND__ *,IShellItemArray *,SHARE_MODE)
0x180063049  mov     rcx, [rbp+ppv]
0x18006304d  mov     rax, [rcx]
0x180063050  mov     rax, [rax+10h]
0x180063054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063059  mov     rcx, [rbp+ppsiItemArray]
0x18006305d  mov     rax, [rcx]
0x180063060  mov     rax, [rax+10h]
0x180063064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063069  mov     rcx, [rbp+ppidl]; pidl
0x18006306d  call    cs:__imp_ILFree
0x180063073  mov     rbx, [rsp+40h+arg_8]
0x180063078  add     rsp, 40h
0x18006307c  pop     rbp
0x18006307d  retn
```
