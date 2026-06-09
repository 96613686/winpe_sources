# CanShareFolder

- ea: `0x18002aa40`
- end: `0x18002ab2f`
- name: `CanShareFolder`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18002aa40`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002aad6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002aad6`
- `SHELL32!SHParseDisplayName` at `0x18002aa71`
- `SHELL32!SHParseDisplayName` at `0x18002aa71`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x18002aaa5`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x18002aaa5`
- `SHELL32!__imp_ILFree` at `0x18002ab1c`
- `SHELL32!__imp_ILFree` at `0x18002ab1c`

## pseudocode

```c
__int64 __fastcall CanShareFolder(const WCHAR *a1)
{
  HRESULT v1; // ebx
  LPITEMIDLIST ppidl[2]; // [rsp+30h] [rbp-10h] BYREF
  SFGAOF psfgaoOut; // [rsp+58h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+20h] BYREF
  IShellItemArray *ppsiItemArray; // [rsp+68h] [rbp+28h] BYREF

  ppidl[0] = 0;
  psfgaoOut = 0;
  v1 = SHParseDisplayName(a1, 0, ppidl, 0x60400000u, &psfgaoOut);
  if ( v1 >= 0 )
  {
    v1 = 1;
    if ( psfgaoOut == 1610612736 )
    {
      ppsiItemArray = 0;
      v1 = SHCreateShellItemArrayFromIDLists(1u, (LPCITEMIDLIST *)ppidl, &ppsiItemArray);
      if ( v1 >= 0 )
      {
        ppv = 0;
        v1 = CoCreateInstance(
               &CLSID_SharingConfigurationManager,
               0,
               1u,
               &GUID_14aa4ab8_abe3_4a07_a290_1d5dccdd2fc2,
               &ppv);
        if ( v1 >= 0 )
        {
          v1 = (*(__int64 (__fastcall **)(LPVOID, IShellItemArray *))(*(_QWORD *)ppv + 24LL))(ppv, ppsiItemArray);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        ((void (__fastcall *)(IShellItemArray *))ppsiItemArray->lpVtbl->Release)(ppsiItemArray);
      }
    }
    ILFree(ppidl[0]);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18002aa40  mov     [rsp-8+arg_0], rbx
0x18002aa45  push    rbp
0x18002aa46  mov     rbp, rsp
0x18002aa49  sub     rsp, 40h
0x18002aa4d  lea     rax, [rbp+arg_8]
0x18002aa51  mov     [rbp+ppidl], 0
0x18002aa59  mov     r9d, 60400000h; sfgaoIn
0x18002aa5f  mov     [rsp+40h+psfgaoOut], rax; psfgaoOut
0x18002aa64  lea     r8, [rbp+ppidl]; ppidl
0x18002aa68  mov     [rbp+arg_8], 0
0x18002aa6f  xor     edx, edx; pbc
0x18002aa71  call    cs:__imp_SHParseDisplayName
0x18002aa77  mov     ebx, eax
0x18002aa79  test    eax, eax
0x18002aa7b  js      loc_18002AB22
0x18002aa81  cmp     [rbp+arg_8], 60000000h
0x18002aa88  mov     ebx, 1
0x18002aa8d  jnz     loc_18002AB18
0x18002aa93  lea     r8, [rbp+ppsiItemArray]; ppsiItemArray
0x18002aa97  mov     [rbp+ppsiItemArray], 0
0x18002aa9f  lea     rdx, [rbp+ppidl]; rgpidl
0x18002aaa3  mov     ecx, ebx; cidl
0x18002aaa5  call    cs:__imp_SHCreateShellItemArrayFromIDLists
0x18002aaab  mov     ebx, eax
0x18002aaad  test    eax, eax
0x18002aaaf  js      short loc_18002AB18
0x18002aab1  xor     edx, edx; pUnkOuter
0x18002aab3  mov     [rbp+ppv], 0
0x18002aabb  lea     rax, [rbp+ppv]
0x18002aabf  lea     r9, _GUID_14aa4ab8_abe3_4a07_a290_1d5dccdd2fc2; riid
0x18002aac6  mov     [rsp+40h+psfgaoOut], rax; ppv
0x18002aacb  lea     rcx, CLSID_SharingConfigurationManager; rclsid
0x18002aad2  lea     r8d, [rdx+1]; dwClsContext
0x18002aad6  call    cs:__imp_CoCreateInstance
0x18002aadc  mov     ebx, eax
0x18002aade  test    eax, eax
0x18002aae0  js      short loc_18002AB08
0x18002aae2  mov     rcx, [rbp+ppv]
0x18002aae6  mov     rdx, [rbp+ppsiItemArray]
0x18002aaea  mov     rax, [rcx]
0x18002aaed  mov     rax, [rax+18h]
0x18002aaf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aaf6  mov     rcx, [rbp+ppv]
0x18002aafa  mov     ebx, eax
0x18002aafc  mov     rax, [rcx]
0x18002aaff  mov     rax, [rax+10h]
0x18002ab03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab08  mov     rcx, [rbp+ppsiItemArray]
0x18002ab0c  mov     rax, [rcx]
0x18002ab0f  mov     rax, [rax+10h]
0x18002ab13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab18  mov     rcx, [rbp+ppidl]; pidl
0x18002ab1c  call    cs:__imp_ILFree
0x18002ab22  mov     eax, ebx
0x18002ab24  mov     rbx, [rsp+40h+arg_0]
0x18002ab29  add     rsp, 40h
0x18002ab2d  pop     rbp
0x18002ab2e  retn
```
