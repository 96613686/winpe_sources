# TryToInitializeCredVaultAPI(void)

- ea: `0x18004bd5c`
- end: `0x18004be27`
- name: `?TryToInitializeCredVaultAPI@@YAXXZ`
- size: `203`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004bcb0`

## callees

- `0x1800046c8`
- `0x18004bd5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004bd91`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004bda8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004bdbf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004bdd6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004bded`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004be04`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004be1b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004bd91`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004bda8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004bdbf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004bdd6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004bded`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004be04`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18004be1b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18004bd69`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18004bd69`

## string_xrefs

- `0x18004bd62`: `vaultcli.dll`
- `0x18004bd7b`: `[msdrm]+TryToInitializeCredVaultAPI: "vaultcli.dll" module found, so office mobile is calling us\n`
- `0x18004bd97`: `VaultOpenVault`

## pseudocode

```c
void TryToInitializeCredVaultAPI(void)
{
  HMODULE ModuleHandleW; // rbx

  ModuleHandleW = GetModuleHandleW(L"vaultcli.dll");
  if ( ModuleHandleW )
  {
    _RTLTRACE("[msdrm]+TryToInitializeCredVaultAPI: \"vaultcli.dll\" module found, so office mobile is calling us\n");
    g_pfnVaultEnumerateVaults = (unsigned int (*)(unsigned int, unsigned int *, struct _GUID **))GetProcAddress(
                                                                                                   ModuleHandleW,
                                                                                                   "VaultEnumerateVaults");
    g_pfnVaultOpenVault = (unsigned int (*)(struct _GUID *, unsigned int, void **))GetProcAddress(
                                                                                     ModuleHandleW,
                                                                                     "VaultOpenVault");
    g_pfnVaultCloseVault = (unsigned int (*)(void **))GetProcAddress(ModuleHandleW, "VaultCloseVault");
    g_pfnVaultGetItem = (unsigned int (*)(void *, struct _GUID *, struct _VAULT_ITEM_ELEMENT *, struct _VAULT_ITEM_ELEMENT *, struct _VAULT_ITEM_ELEMENT *, HWND, unsigned int, struct _VAULT_ITEM **))GetProcAddress(ModuleHandleW, "VaultGetItem");
    g_pfnVaultFindItems = (unsigned int (*)(void *, struct _GUID *, struct _VAULT_ITEM_ELEMENT *, HWND, unsigned int, unsigned int *, struct _VAULT_ITEM **))GetProcAddress(ModuleHandleW, "VaultFindItems");
    g_pfnVaultFree = (void (*)(void *))GetProcAddress(ModuleHandleW, "VaultFree");
    GetProcAddress(ModuleHandleW, "VaultEnumerateItems");
  }
}

```

## disassembly

```asm
0x18004bd5c  push    rbx
0x18004bd5e  sub     rsp, 20h
0x18004bd62  lea     rcx, ModuleName; "vaultcli.dll"
0x18004bd69  call    cs:__imp_GetModuleHandleW
0x18004bd6f  mov     rbx, rax
0x18004bd72  test    rax, rax
0x18004bd75  jz      loc_18004BE21
0x18004bd7b  lea     rcx, aMsdrmTrytoinit; "[msdrm]+TryToInitializeCredVaultAPI: \""...
0x18004bd82  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004bd87  lea     rdx, aVaultenumerate; "VaultEnumerateVaults"
0x18004bd8e  mov     rcx, rbx; hModule
0x18004bd91  call    cs:__imp_GetProcAddress
0x18004bd97  lea     rdx, aVaultopenvault; "VaultOpenVault"
0x18004bd9e  mov     rcx, rbx; hModule
0x18004bda1  mov     cs:?g_pfnVaultEnumerateVaults@@3P6AKKPEAKPEAPEAU_GUID@@@ZEA, rax; ulong (*g_pfnVaultEnumerateVaults)(ulong,ulong *,_GUID * *)
0x18004bda8  call    cs:__imp_GetProcAddress
0x18004bdae  lea     rdx, aVaultclosevaul; "VaultCloseVault"
0x18004bdb5  mov     rcx, rbx; hModule
0x18004bdb8  mov     cs:?g_pfnVaultOpenVault@@3P6AKPEAU_GUID@@KPEAPEAX@ZEA, rax; ulong (*g_pfnVaultOpenVault)(_GUID *,ulong,void * *)
0x18004bdbf  call    cs:__imp_GetProcAddress
0x18004bdc5  lea     rdx, aVaultgetitem; "VaultGetItem"
0x18004bdcc  mov     rcx, rbx; hModule
0x18004bdcf  mov     cs:?g_pfnVaultCloseVault@@3P6AKPEAPEAX@ZEA, rax; ulong (*g_pfnVaultCloseVault)(void * *)
0x18004bdd6  call    cs:__imp_GetProcAddress
0x18004bddc  lea     rdx, aVaultfinditems; "VaultFindItems"
0x18004bde3  mov     rcx, rbx; hModule
0x18004bde6  mov     cs:?g_pfnVaultGetItem@@3P6AKPEAXPEAU_GUID@@PEAU_VAULT_ITEM_ELEMENT@@22PEAUHWND__@@KPEAPEAU_VAULT_ITEM@@@ZEA, rax; ulong (*g_pfnVaultGetItem)(void *,_GUID *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *,HWND__ *,ulong,_VAULT_ITEM * *)
0x18004bded  call    cs:__imp_GetProcAddress
0x18004bdf3  lea     rdx, aVaultfree; "VaultFree"
0x18004bdfa  mov     rcx, rbx; hModule
0x18004bdfd  mov     cs:?g_pfnVaultFindItems@@3P6AKPEAXPEAU_GUID@@PEAU_VAULT_ITEM_ELEMENT@@PEAUHWND__@@KPEAKPEAPEAU_VAULT_ITEM@@@ZEA, rax; ulong (*g_pfnVaultFindItems)(void *,_GUID *,_VAULT_ITEM_ELEMENT *,HWND__ *,ulong,ulong *,_VAULT_ITEM * *)
0x18004be04  call    cs:__imp_GetProcAddress
0x18004be0a  lea     rdx, aVaultenumerate_0; "VaultEnumerateItems"
0x18004be11  mov     rcx, rbx; hModule
0x18004be14  mov     cs:?g_pfnVaultFree@@3P6AXPEAX@ZEA, rax; void (*g_pfnVaultFree)(void *)
0x18004be1b  call    cs:__imp_GetProcAddress
0x18004be21  add     rsp, 20h
0x18004be25  pop     rbx
0x18004be26  retn
```
