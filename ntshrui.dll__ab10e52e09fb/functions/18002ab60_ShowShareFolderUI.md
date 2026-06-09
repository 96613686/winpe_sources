# ShowShareFolderUI

- ea: `0x18002ab60`
- end: `0x18002ac4c`
- name: `ShowShareFolderUI`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18002ab60`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002abeb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002abeb`
- `SHELL32!SHParseDisplayName` at `0x18002ab95`
- `SHELL32!SHParseDisplayName` at `0x18002ab95`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x18002abba`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x18002abba`
- `SHELL32!__imp_ILFree` at `0x18002ac34`
- `SHELL32!__imp_ILFree` at `0x18002ac34`

## pseudocode

```c
__int64 __fastcall ShowShareFolderUI(__int64 a1, const WCHAR *a2)
{
  HRESULT v3; // ebx
  LPITEMIDLIST ppidl[2]; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+20h] BYREF
  IShellItemArray *ppsiItemArray; // [rsp+68h] [rbp+28h] BYREF

  ppidl[0] = 0;
  v3 = SHParseDisplayName(a2, 0, ppidl, 0, 0);
  if ( v3 >= 0 )
  {
    ppsiItemArray = 0;
    v3 = SHCreateShellItemArrayFromIDLists(1u, (LPCITEMIDLIST *)ppidl, &ppsiItemArray);
    if ( v3 >= 0 )
    {
      ppv = 0;
      v3 = CoCreateInstance(&CLSID_SharingConfigurationManager, 0, 1u, &GUID_14aa4ab8_abe3_4a07_a290_1d5dccdd2fc2, &ppv);
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(LPVOID, __int64, IShellItemArray *))(*(_QWORD *)ppv + 32LL))(
               ppv,
               a1,
               ppsiItemArray);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      ((void (__fastcall *)(IShellItemArray *))ppsiItemArray->lpVtbl->Release)(ppsiItemArray);
    }
    ILFree(ppidl[0]);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002ab60  mov     [rsp-8+arg_0], rbx
0x18002ab65  mov     [rsp-8+arg_8], rdi
0x18002ab6a  push    rbp
0x18002ab6b  mov     rbp, rsp
0x18002ab6e  sub     rsp, 40h
0x18002ab72  mov     rax, rdx
0x18002ab75  mov     [rbp+ppidl], 0
0x18002ab7d  mov     rdi, rcx
0x18002ab80  mov     [rsp+40h+psfgaoOut], 0; psfgaoOut
0x18002ab89  mov     rcx, rax; pszName
0x18002ab8c  lea     r8, [rbp+ppidl]; ppidl
0x18002ab90  xor     r9d, r9d; sfgaoIn
0x18002ab93  xor     edx, edx; pbc
0x18002ab95  call    cs:__imp_SHParseDisplayName
0x18002ab9b  mov     ebx, eax
0x18002ab9d  test    eax, eax
0x18002ab9f  js      loc_18002AC3A
0x18002aba5  lea     r8, [rbp+ppsiItemArray]; ppsiItemArray
0x18002aba9  mov     [rbp+ppsiItemArray], 0
0x18002abb1  lea     rdx, [rbp+ppidl]; rgpidl
0x18002abb5  mov     ecx, 1; cidl
0x18002abba  call    cs:__imp_SHCreateShellItemArrayFromIDLists
0x18002abc0  mov     ebx, eax
0x18002abc2  test    eax, eax
0x18002abc4  js      short loc_18002AC30
0x18002abc6  xor     edx, edx; pUnkOuter
0x18002abc8  mov     [rbp+ppv], 0
0x18002abd0  lea     rax, [rbp+ppv]
0x18002abd4  lea     r9, _GUID_14aa4ab8_abe3_4a07_a290_1d5dccdd2fc2; riid
0x18002abdb  mov     [rsp+40h+psfgaoOut], rax; ppv
0x18002abe0  lea     rcx, CLSID_SharingConfigurationManager; rclsid
0x18002abe7  lea     r8d, [rdx+1]; dwClsContext
0x18002abeb  call    cs:__imp_CoCreateInstance
0x18002abf1  mov     ebx, eax
0x18002abf3  test    eax, eax
0x18002abf5  js      short loc_18002AC20
0x18002abf7  mov     rcx, [rbp+ppv]
0x18002abfb  mov     rdx, rdi
0x18002abfe  mov     r8, [rbp+ppsiItemArray]
0x18002ac02  mov     rax, [rcx]
0x18002ac05  mov     rax, [rax+20h]
0x18002ac09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac0e  mov     rcx, [rbp+ppv]
0x18002ac12  mov     ebx, eax
0x18002ac14  mov     rax, [rcx]
0x18002ac17  mov     rax, [rax+10h]
0x18002ac1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac20  mov     rcx, [rbp+ppsiItemArray]
0x18002ac24  mov     rax, [rcx]
0x18002ac27  mov     rax, [rax+10h]
0x18002ac2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac30  mov     rcx, [rbp+ppidl]; pidl
0x18002ac34  call    cs:__imp_ILFree
0x18002ac3a  mov     rdi, [rsp+40h+arg_8]
0x18002ac3f  mov     eax, ebx
0x18002ac41  mov     rbx, [rsp+40h+arg_0]
0x18002ac46  add     rsp, 40h
0x18002ac4a  pop     rbp
0x18002ac4b  retn
```
