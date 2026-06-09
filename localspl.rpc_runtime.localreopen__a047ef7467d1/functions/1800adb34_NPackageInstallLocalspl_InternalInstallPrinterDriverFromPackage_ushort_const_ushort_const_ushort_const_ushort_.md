# NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage(ushort const *,ushort const *,ushort const *,ushort const *,ulong,_INISPOOLER *)

- ea: `0x1800adb34`
- end: `0x1800b7a91`
- name: `?InternalInstallPrinterDriverFromPackage@NPackageInstallLocalspl@@YAJPEBG000KPEAU_INISPOOLER@@@Z`
- size: `40797`
- prototype: `int(NPackageInstallLocalspl *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct _INISPOOLER *)`
- caller_count: `6`
- callee_count: `44`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180069484`
- `0x1800ac384`
- `0x1800b8fd8`
- `0x1800baec4`
- `0x1800bcc0c`
- `0x1800bcf3c`

## callees

- `0x180008520`
- `0x180008560`
- `0x180009630`
- `0x180011f00`
- `0x180014448`
- `0x1800146e8`
- `0x180015e28`
- `0x180018868`
- `0x18001fb10`
- `0x180020690`
- `0x180023880`
- `0x18002e454`
- `0x18002ff50`
- `0x180033468`
- `0x18003df98`
- `0x18003e394`
- `0x18003e3c0`
- `0x18003e984`
- `0x18003ea2c`
- `0x180042e68`
- `0x180043740`
- `0x180046650`
- `0x180046a20`
- `0x180047318`
- `0x180047330`
- `0x18004ef4c`
- `0x180072888`
- `0x180072ed4`
- `0x180075ce8`
- `0x1800ab194`
- `0x1800ab290`
- `0x1800abe08`
- `0x1800adb34`
- `0x1800b7a98`
- `0x1800b7c9c`
- `0x1800b81d0`
- `0x1800ba1bc`
- `0x1800bdf84`
- `0x1800c1b18`
- `0x1800ca0fc`
- `0x1800ca5c8`
- `0x1800ccbd8`
- `0x1800cd2ac`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b71cb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b71e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b71cb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b71e3`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800b714d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800b714d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800addc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ae09d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ae146`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ae21a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b1453`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b56cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800addc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ae09d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ae146`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ae21a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b1453`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b56cf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800add8d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800adef6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800add8d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800adef6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800b13f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800b5690`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800b13f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800b5690`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ade96`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b7a38`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ade96`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b7a38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aeaa7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aeb63`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aee9e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800afe4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b06e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b0822`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b08a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b0954`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b0c3f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b119b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b173d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b17e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b1872`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b1931`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b29d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b3601`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b36b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b383f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4126`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b49aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4aed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4b85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4c39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4f4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b53a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b5980`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b5a32`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b5ac5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b5b7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b6bd3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aeaa7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aeb63`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aee9e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800afe4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b06e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b0822`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b08a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b0954`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b0c3f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b119b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b173d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b17e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b1872`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b1931`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b29d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b3601`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b36b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b383f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4126`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b49aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4aed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4b85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4c39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4f4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b53a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b5980`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b5a32`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b5ac5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b5b7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b6bd3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aea8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aeb54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aee8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800afe3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800affb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b06d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0716`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0751`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0787`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b07bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b07e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0811`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b088f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0945`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0a01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0a37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0a6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0a92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0c2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0f32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b118a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b172b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b17d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b185c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b1920`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b19d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b19fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b1a2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b1a49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b1b3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b1b69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b1b97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b1bb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b29bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b2b6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b2ba5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b2bdb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b2c11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b2c36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b2c59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b2c7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b2cb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b2ced`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b2d23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b2d48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b2d6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3545`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3570`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3590`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b35ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b35ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b36a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b382c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3a2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3a58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3a71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3a8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4115`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4294`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4998`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b49e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4a1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4a52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4a88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4aad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4adc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4b71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4c26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4ceb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4d21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4d57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4d7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4f3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5249`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5396`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b596e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5a1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5aaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5b65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5c1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5c55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5c8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5cb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5daa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5de0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5e16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b5e3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b6bba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b6d8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b6dc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b6df2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b6e20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b6e3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b6e5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b6e77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b6ea1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b6ec2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b6ee3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b6efb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b6f1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aea8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aeb54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aee8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800afe3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800affb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b06d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0716`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0751`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b0787`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b07bd`

## string_xrefs

- `0x1800add86`: `setupapi.dll`
- `0x1800b13e7`: `ntdll.dll`
- `0x1800b5684`: `ntdll.dll`
- `0x1800adeef`: `ntprint.dll`
- `0x1800adcb1`: `InternalInstallPrinterDriverFromPackage`
- `0x1800adf9e`: `InternalInstallPrinterDriverFromPackage`
- `0x1800ae074`: `InternalInstallPrinterDriverFromPackage`
- `0x1800ae116`: `InternalInstallPrinterDriverFromPackage`
- `0x1800ae1c3`: `InternalInstallPrinterDriverFromPackage`
- `0x1800ae297`: `InternalInstallPrinterDriverFromPackage`
- `0x1800ae3bc`: `InternalInstallPrinterDriverFromPackage`
- `0x1800ae4a4`: `InternalInstallPrinterDriverFromPackage`
- `0x1800ae8cf`: `InternalInstallPrinterDriverFromPackage`
- `0x1800b77cc`: `InternalInstallPrinterDriverFromPackage`
- `0x1800b785f`: `InternalInstallPrinterDriverFromPackage`
- `0x1800b7930`: `InternalInstallPrinterDriverFromPackage`
- `0x1800adc44`: `Installing %ws printer driver with pszServer=%ws, pszInfPath=%ws, pszEnvironment=%ws, dwFlags=%d.`
- `0x1800adf44`: `Invalid INF path passed into InstallPrinterDriverFromPackage: %ws`
- `0x1800ae433`: `Incorrect parameters passed to InstallPrinterDriverFromPackage:`
- `0x1800adc4b`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800adf4b`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800adfd5`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800ae01a`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800ae43a`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800ae460`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800ae52f`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800ae585`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800ae686`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800ae73a`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800ae791`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800ae90c`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800b7172`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800b718d`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800b720d`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800b72b9`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800b7319`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800b7375`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800b7528`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800b76f1`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800b7752`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800b77f9`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800b78ae`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800b7a5f`: `NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage`
- `0x1800ae06d`: `LoadLibrary(ntprint.dll) failed`
- `0x1800ae093`: `PSetupParseInfAndCommitFileQueue`
- `0x1800ae10f`: `GetProcAddress(pfnPSetupParseInfAndCommitFileQueue) failed`
- `0x1800ae13c`: `PSetupInstallICMProfiles`
- `0x1800adfce`: `Failed to load ntprint.dll, hr: 0x%x`
- `0x1800adff8`: `Failed to impersonate printer client, hr: 0x%x`
- `0x1800ae006`: `Failed to revert to Spooler service for loading ntprint.dll, hr: 0x%x`
- `0x1800ae613`: `Failed to copy driver name (device description) information!`
- `0x1800ae622`: `printscan\print\spooler\localspl\packageinstall.cxx`
- `0x1800ae65f`: `printscan\print\spooler\localspl\packageinstall.cxx`
- `0x1800ae1bc`: `GetProcAddress(pfnPSetupInstallICMProfiles) failed`
- `0x1800ae8c8`: `pfnPSetupParseInfAndCommitFileQueue failed`
- `0x1800b716b`: `Expecting full DriverStore path for driver: %ws`
- `0x1800ae650`: `Failed to copy driver package INF information!`
- `0x1800ae733`: `Parsing INF and committing files`
- `0x1800ae78a`: `Parsing INF and committing files failed: hr: 0x%x`
- `0x1800b736e`: `Base driver '%ws' is already installed (referenced by driver '%ws')`
- `0x1800b76ea`: `Installing color profiles`
- `0x1800b774b`: `Successfully installed color profiles.`
- `0x1800b77c5`: `pfnPSetupInstallICMProfiles succeeded`
- `0x1800b72b2`: `Performing legacy install for v%u driver: hr: 0x%x`
- `0x1800b78a7`: `Error installing color profiles: hr: 0x%x`
- `0x1800b7929`: `pfnPSetupInstallICMProfiles failed (profiles listed in additional info)`
- `0x1800b77f2`: `Successfully installed the %ws printer driver.`
- `0x1800b7a58`: `Error installing the %ws printer driver: hr: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage(
        NPackageInstallLocalspl *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        struct _SETUP_CONTEXT *a6)
{
  unsigned __int16 *v8; // r12
  unsigned int v9; // r15d
  HMODULE v10; // r13
  unsigned int v11; // ebx
  int ProcessorArchitectureFromEnvironmentString; // eax
  __int64 v13; // r14
  const unsigned __int16 *v14; // r8
  unsigned int DriverValidationPolicyLevel; // edi
  int v16; // eax
  int v17; // edx
  unsigned int v18; // eax
  unsigned int v19; // edx
  NCoreLibrary *v20; // rcx
  HMODULE Library; // rdi
  int LastErrorAsFailHRNoBreak; // eax
  NCoreLibrary *v23; // rcx
  FARPROC ProcAddress; // rdi
  NCoreLibrary *v25; // rcx
  int v26; // edi
  unsigned __int16 *v27; // rax
  int v28; // esi
  NCoreLibrary *v29; // rcx
  NCoreLibrary *v30; // rcx
  int v31; // edi
  DWORD LastError; // eax
  int v33; // eax
  NCoreLibrary *v34; // rcx
  unsigned int v35; // eax
  unsigned __int16 *v36; // rdx
  DWORD v37; // eax
  NCoreLibrary *v38; // rcx
  DWORD v39; // eax
  NCoreLibrary *v40; // rcx
  void *v41; // rdi
  DWORD v42; // eax
  NCoreLibrary *v43; // rcx
  void *v44; // rsi
  DWORD v45; // eax
  DWORD v46; // eax
  const char *v47; // r9
  unsigned int v48; // eax
  unsigned int v49; // eax
  __int64 v50; // rcx
  unsigned __int16 *v51; // rbx
  int v52; // eax
  struct SplLogType *v53; // rax
  __int64 v54; // r10
  DWORD v55; // r9d
  const unsigned __int16 *v56; // r8
  int v57; // edx
  const unsigned __int16 *v58; // rax
  struct SplLogType *v59; // rax
  __int64 v60; // r10
  struct _INISPOOLER *v61; // r8
  HLOCAL v62; // rax
  HANDLE ProcessHeap; // rax
  _OWORD *v64; // rax
  void *v65; // rbx
  int v66; // r14d
  HANDLE v67; // rax
  _QWORD *v68; // rax
  void *v69; // r9
  int v70; // eax
  unsigned int v71; // r11d
  int v72; // eax
  unsigned int v73; // r11d
  int v74; // r10d
  int v75; // eax
  unsigned int v76; // r11d
  int v77; // r10d
  int v78; // eax
  size_t v79; // rdx
  int v80; // r10d
  unsigned int v81; // r11d
  int v82; // eax
  unsigned int v83; // r11d
  int v84; // eax
  unsigned int v85; // r11d
  int v86; // r10d
  int v87; // eax
  int v88; // r10d
  unsigned int v89; // ebx
  HANDLE v90; // rax
  void *v91; // rax
  _DWORD *v92; // r10
  __int64 v93; // r11
  unsigned int v94; // ecx
  int v95; // eax
  int v96; // eax
  unsigned int *v97; // r10
  __int64 v98; // r11
  void *v99; // r9
  __int64 v100; // r10
  void *v101; // r9
  _DWORD *v102; // r10
  size_t v103; // r8
  int v104; // eax
  unsigned int *v105; // r10
  __int64 v106; // r11
  void *v107; // r9
  __int64 v108; // r10
  void *v109; // r9
  const void *v110; // r9
  _DWORD *v111; // r10
  size_t v112; // r8
  int v113; // r10d
  unsigned int *v114; // rax
  size_t v115; // rdx
  void *v116; // r9
  void *v117; // r9
  unsigned int v118; // r10d
  __int64 v119; // r11
  unsigned int *v120; // r10
  __int64 v121; // r11
  void *v122; // r9
  __int64 v123; // r10
  void *v124; // r9
  unsigned int v125; // r9d
  unsigned int *v126; // r10
  int v127; // eax
  unsigned int *v128; // r10
  __int64 v129; // r11
  void *v130; // r9
  __int64 v131; // r10
  void *v132; // r9
  _DWORD *v133; // r10
  int v134; // r10d
  unsigned int *v135; // rax
  unsigned int v136; // r11d
  void *v137; // r9
  void *v138; // r9
  unsigned int v139; // r10d
  __int64 v140; // rcx
  unsigned int v141; // r9d
  unsigned int v142; // r11d
  unsigned int v143; // r11d
  unsigned int v144; // r11d
  unsigned int v145; // r11d
  unsigned __int64 v146; // rdx
  unsigned int v147; // r9d
  int v148; // r14d
  unsigned int v149; // eax
  unsigned int v150; // ebx
  HANDLE v151; // rax
  _DWORD *v152; // rax
  void *v153; // rcx
  unsigned int v154; // r9d
  void *v155; // r10
  int v156; // r11d
  size_t v157; // rcx
  void *v158; // rdi
  HANDLE v159; // rax
  unsigned __int8 *v160; // r14
  unsigned __int64 v161; // rdi
  void *v162; // rdx
  unsigned __int8 v163; // al
  unsigned __int64 v164; // rcx
  unsigned __int8 *v165; // r11
  unsigned __int64 v166; // rdx
  int v167; // r9d
  unsigned int v168; // r10d
  unsigned int v169; // edi
  int v170; // eax
  int v171; // r10d
  int v172; // ecx
  int v173; // r8d
  unsigned int v174; // ebx
  _BYTE *v175; // r11
  char v176; // r14
  unsigned int v177; // r9d
  int v178; // r8d
  int v179; // r12d
  unsigned __int8 *v180; // rsi
  _BYTE *v181; // r14
  int v182; // r15d
  int v183; // eax
  SIZE_T v184; // r13
  int v185; // ebx
  int v186; // r11d
  int v187; // edx
  int v188; // r9d
  int v189; // r10d
  int v190; // r8d
  int v191; // r9d
  unsigned int v192; // edx
  int v193; // r8d
  int v194; // ecx
  int v195; // edx
  int v196; // r9d
  int v197; // edx
  unsigned int v198; // r8d
  unsigned int v199; // r9d
  int v200; // edx
  int v201; // r8d
  int v202; // r9d
  int v203; // edx
  int v204; // r8d
  int v205; // r10d
  int v206; // edx
  int v207; // r9d
  unsigned int v208; // r8d
  int v209; // edx
  HANDLE v210; // rax
  _DWORD *v211; // rax
  int v212; // r14d
  void *v213; // rbx
  void *v214; // rax
  HANDLE v215; // rax
  _QWORD *v216; // rax
  HANDLE v217; // rax
  HANDLE v218; // rax
  HANDLE v219; // rax
  HANDLE v220; // rax
  unsigned int *v221; // r11
  unsigned int v222; // ebx
  HANDLE v223; // rax
  void *v224; // rcx
  void *v225; // rax
  _DWORD *v226; // r14
  HANDLE v227; // rax
  _OWORD *v228; // rcx
  _DWORD *v229; // rax
  HANDLE v230; // rax
  _QWORD *v231; // rax
  _QWORD *v232; // rax
  HANDLE v233; // rax
  HANDLE v234; // rax
  HANDLE v235; // rax
  HANDLE v236; // rax
  LPVOID v237; // rcx
  unsigned int v238; // r10d
  int v239; // r14d
  __int64 v240; // r11
  unsigned int v241; // r10d
  __int64 v242; // r11
  void *v243; // r11
  unsigned int v244; // ebx
  HANDLE v245; // rax
  _DWORD *v246; // rax
  void *v247; // rcx
  void *v248; // r9
  void *v249; // r10
  const void **v250; // r11
  const void **v251; // r9
  LPVOID v252; // rcx
  unsigned int *v253; // r10
  LPVOID v254; // rcx
  unsigned int *v255; // r9
  void *v256; // rax
  HANDLE v257; // rax
  int v258; // eax
  __int64 v259; // rcx
  void *v260; // r9
  __int64 v261; // r10
  void *v262; // r11
  size_t v263; // r14
  unsigned int v264; // r9d
  unsigned int v265; // ebx
  __int64 v266; // r10
  size_t v267; // rcx
  unsigned int v268; // ebx
  HANDLE v269; // rax
  void *v270; // r11
  unsigned int v271; // r11d
  int v272; // r9d
  unsigned int v273; // r10d
  unsigned int v274; // r10d
  unsigned int v275; // r10d
  unsigned int v276; // r11d
  signed int v277; // eax
  FARPROC v278; // rax
  int v279; // eax
  unsigned int v280; // r10d
  size_t v281; // rbx
  unsigned __int64 v282; // rdx
  unsigned int v283; // r9d
  int v284; // r14d
  int v285; // r10d
  __int64 v286; // r9
  int v287; // r10d
  size_t v288; // rbx
  unsigned int v289; // r9d
  int v290; // r10d
  __int64 v291; // r9
  int v292; // r10d
  unsigned int v293; // ebx
  unsigned int v294; // r9d
  int v295; // r10d
  int v296; // r10d
  SIZE_T v297; // r14
  HANDLE v298; // rax
  _DWORD *v299; // rcx
  HANDLE v300; // rax
  void *v301; // rcx
  HANDLE v302; // rax
  void *v303; // rcx
  size_t v304; // rax
  unsigned int v305; // r14d
  HANDLE v306; // rax
  void *v307; // rcx
  _QWORD *v308; // rbx
  HANDLE v309; // rax
  HANDLE v310; // rax
  HANDLE v311; // rax
  HANDLE v312; // rax
  unsigned int *v313; // r8
  _QWORD *v314; // rbx
  HANDLE v315; // rax
  HANDLE v316; // rax
  HANDLE v317; // rax
  HANDLE v318; // rax
  unsigned __int64 v319; // r14
  void *v320; // rcx
  unsigned __int8 v321; // al
  int v322; // r9d
  unsigned int v323; // r8d
  int v324; // edi
  unsigned __int8 *v325; // rax
  int v326; // ebx
  unsigned int v327; // edx
  int v328; // ecx
  int v329; // r10d
  unsigned int v330; // r11d
  _BYTE *v331; // rax
  char v332; // r14
  int v333; // r10d
  unsigned int v334; // r11d
  unsigned __int8 *v335; // rdi
  _BYTE *v336; // rax
  SIZE_T v337; // r15
  int v338; // r13d
  int v339; // r12d
  int v340; // r14d
  int v341; // esi
  int v342; // edx
  unsigned int v343; // r8d
  int v344; // r9d
  unsigned int v345; // edx
  int v346; // r8d
  int v347; // r9d
  unsigned int v348; // edx
  int v349; // r8d
  int v350; // r10d
  int v351; // r11d
  unsigned int v352; // r9d
  int v353; // r8d
  unsigned int v354; // r9d
  int v355; // edx
  int v356; // r8d
  int v357; // r9d
  int v358; // edx
  unsigned int v359; // r8d
  int v360; // r9d
  int v361; // edx
  int v362; // r8d
  unsigned int v363; // r9d
  int v364; // edx
  unsigned __int64 i; // rcx
  int v366; // r14d
  void *v367; // r9
  void *v368; // r10
  unsigned int v369; // r11d
  __int64 v370; // r11
  unsigned int v371; // r11d
  size_t v372; // rcx
  __int64 v373; // r11
  void *v374; // r10
  void *v375; // r9
  size_t v376; // rax
  unsigned int *v377; // rcx
  unsigned int v378; // r11d
  void *v379; // r13
  void *v380; // r9
  void *v381; // r10
  int v382; // eax
  void *v383; // rcx
  unsigned int v384; // edx
  HANDLE v385; // rax
  HANDLE v386; // rax
  _QWORD *v387; // rax
  HANDLE v388; // rax
  HANDLE v389; // rax
  HANDLE v390; // rax
  HANDLE v391; // rax
  HANDLE v392; // rax
  HANDLE v393; // rax
  _QWORD *v394; // rax
  HANDLE v395; // rax
  HANDLE v396; // rax
  HANDLE v397; // rax
  HANDLE v398; // rax
  HANDLE v399; // rax
  _DWORD *v400; // rcx
  __int64 v401; // r11
  int *v402; // r14
  _DWORD *v403; // r14
  void *v404; // r9
  void *v405; // r10
  __int64 v406; // r11
  SIZE_T *v407; // rax
  _DWORD *v408; // r14
  void *v409; // r9
  void *v410; // r10
  __int64 v411; // r11
  _DWORD *v412; // rax
  _DWORD *v413; // r14
  __int64 v414; // r11
  _DWORD *v415; // rcx
  void *v416; // r9
  void *v417; // r10
  __int64 v418; // r11
  _DWORD *v419; // rax
  size_t v420; // r14
  unsigned int v421; // r9d
  int v422; // r9d
  unsigned int v423; // r11d
  int *v424; // rax
  HANDLE v425; // rax
  HANDLE v426; // rax
  HANDLE v427; // rax
  HANDLE v428; // rax
  HANDLE v429; // rax
  _OWORD *v430; // rcx
  void *v431; // rdi
  void *v432; // rsi
  HANDLE v433; // rax
  _QWORD *v434; // rax
  void *v435; // r9
  unsigned int v436; // r10d
  int v437; // eax
  unsigned int v438; // r10d
  int v439; // r11d
  int v440; // eax
  unsigned int v441; // r10d
  int v442; // r11d
  int v443; // eax
  int v444; // r11d
  unsigned int v445; // esi
  HANDLE v446; // rax
  void *v447; // rax
  SIZE_T v448; // rsi
  __int64 v449; // r10
  void *v450; // r11
  int v451; // edx
  void *v452; // rbx
  HANDLE v453; // rax
  void *v454; // rbx
  HANDLE v455; // rax
  HANDLE v456; // rax
  HANDLE v457; // rax
  unsigned int *v458; // rax
  __int64 v459; // r10
  void *v460; // r9
  void *v461; // r9
  const void *v462; // r11
  size_t v463; // r8
  int v464; // ecx
  unsigned int *v465; // rax
  __int64 v466; // r10
  void *v467; // r9
  void *v468; // r9
  const void *v469; // r9
  size_t v470; // r8
  int v471; // eax
  unsigned int *v472; // rcx
  unsigned int v473; // r10d
  void *v474; // r9
  void *v475; // r9
  __int64 v476; // rcx
  unsigned int v477; // r9d
  unsigned __int64 v478; // rdx
  int v479; // r8d
  LPVOID v480; // r9
  unsigned int v481; // r10d
  unsigned int v482; // eax
  unsigned int v483; // esi
  HANDLE v484; // rax
  _DWORD *v485; // rax
  SIZE_T v486; // rbx
  void *v487; // rcx
  void *v488; // r9
  unsigned int v489; // r10d
  void *v490; // r11
  LPVOID v491; // rcx
  HANDLE v492; // rax
  int v493; // r8d
  void *v494; // r8
  unsigned __int8 v495; // al
  unsigned __int64 v496; // rcx
  unsigned __int64 v497; // rdx
  int v498; // r11d
  unsigned int v499; // r8d
  unsigned __int8 *v500; // rax
  int v501; // r14d
  int v502; // edi
  unsigned int v503; // r9d
  unsigned int v504; // ecx
  int v505; // r10d
  unsigned int v506; // esi
  _BYTE *v507; // rax
  char v508; // dl
  unsigned int v509; // r9d
  int v510; // r12d
  unsigned __int8 *v511; // r15
  _BYTE *v512; // rax
  SIZE_T v513; // r14
  int v514; // ebx
  int v515; // r13d
  int v516; // esi
  int v517; // r11d
  int v518; // r10d
  int v519; // r8d
  int v520; // r10d
  int v521; // r9d
  int v522; // r8d
  unsigned int v523; // edx
  int v524; // r9d
  int v525; // ecx
  int v526; // edx
  int v527; // r8d
  int v528; // r9d
  int v529; // edx
  unsigned int v530; // r8d
  unsigned int v531; // r9d
  int v532; // edx
  int v533; // r8d
  int v534; // r9d
  int v535; // edx
  int v536; // r8d
  int v537; // r9d
  int v538; // r10d
  int v539; // r8d
  unsigned int v540; // edx
  int v541; // r9d
  HANDLE v542; // rax
  _DWORD *v543; // rax
  SIZE_T v544; // rsi
  void *v545; // rdi
  void *v546; // rax
  HANDLE v547; // rax
  _QWORD *v548; // rax
  HANDLE v549; // rax
  HANDLE v550; // rax
  HANDLE v551; // rax
  HANDLE v552; // rax
  unsigned int *v553; // rdx
  unsigned int v554; // edi
  HANDLE v555; // rax
  void *v556; // r9
  void *v557; // rax
  HANDLE v558; // rax
  _OWORD *v559; // rcx
  _DWORD *v560; // rax
  HANDLE v561; // rax
  _QWORD *v562; // rax
  _QWORD *v563; // rax
  HANDLE v564; // rax
  HANDLE v565; // rax
  HANDLE v566; // rax
  HANDLE v567; // rax
  LPVOID v568; // rcx
  unsigned int v569; // r9d
  unsigned int v570; // r9d
  __int64 v571; // r10
  void *v572; // r10
  unsigned int v573; // edi
  HANDLE v574; // rax
  _DWORD *v575; // rax
  void *v576; // rcx
  void *v577; // r9
  void *v578; // r10
  const void **v579; // r11
  const void **v580; // r9
  LPVOID v581; // rcx
  unsigned int *v582; // r10
  LPVOID v583; // rcx
  unsigned int *v584; // r9
  int v585; // eax
  HANDLE v586; // rax
  int v587; // eax
  __int64 v588; // rcx
  __int64 v589; // r9
  void *v590; // r10
  void *v591; // r11
  int v592; // edx
  unsigned int v593; // edi
  HANDLE v594; // rax
  _DWORD *v595; // rdi
  unsigned int v596; // r10d
  unsigned int v597; // edi
  __int64 v598; // r9
  LPVOID v599; // rcx
  unsigned int v600; // r11d
  int v601; // r10d
  unsigned int v602; // r9d
  unsigned int v603; // r9d
  unsigned int v604; // r9d
  unsigned int v605; // r11d
  int v606; // eax
  bool v607; // sf
  FARPROC v608; // rax
  unsigned int v609; // r10d
  int v610; // eax
  unsigned __int64 v611; // rdx
  unsigned int v612; // r9d
  int v613; // r10d
  SIZE_T v614; // r11
  unsigned int v615; // r11d
  __int64 v616; // r9
  int v617; // r10d
  unsigned int v618; // r9d
  int v619; // r10d
  SIZE_T v620; // r11
  unsigned int v621; // r11d
  __int64 v622; // r9
  int v623; // r10d
  unsigned int v624; // r9d
  int v625; // r10d
  unsigned int v626; // r11d
  int v627; // r10d
  int v628; // r11d
  HANDLE v629; // rax
  SIZE_T *v630; // rcx
  void *v631; // rdi
  HANDLE v632; // rax
  void *v633; // rcx
  HANDLE v634; // rax
  void *v635; // rcx
  SIZE_T v636; // rax
  HANDLE v637; // rax
  void *v638; // rcx
  _QWORD *v639; // rax
  HANDLE v640; // rax
  HANDLE v641; // rax
  HANDLE v642; // rax
  HANDLE v643; // rax
  SIZE_T *v644; // r8
  HANDLE v645; // rax
  HANDLE v646; // rax
  HANDLE v647; // rax
  HANDLE v648; // rax
  void *v649; // rcx
  unsigned __int8 v650; // al
  unsigned __int64 v651; // r9
  unsigned int v652; // r8d
  unsigned int v653; // eax
  unsigned __int8 *v654; // r15
  int v655; // ebx
  int v656; // r14d
  unsigned int v657; // edx
  _BYTE *v658; // r11
  unsigned int v659; // r10d
  int v660; // ecx
  int v661; // edi
  unsigned int v662; // eax
  char v663; // r9
  int v664; // r10d
  int v665; // r11d
  unsigned int v666; // eax
  unsigned __int8 *v667; // r15
  _BYTE *v668; // r13
  int v669; // r12d
  SIZE_T v670; // r14
  int v671; // esi
  int v672; // edi
  int v673; // edx
  unsigned int v674; // r8d
  int v675; // r9d
  unsigned int v676; // edx
  int v677; // r8d
  int v678; // r9d
  unsigned int v679; // edx
  int v680; // r8d
  int v681; // r10d
  int v682; // r11d
  unsigned int v683; // r9d
  int v684; // r8d
  unsigned int v685; // r9d
  int v686; // r10d
  int v687; // r11d
  int v688; // edx
  int v689; // r8d
  unsigned int v690; // r9d
  int v691; // edx
  int v692; // r10d
  int v693; // r8d
  unsigned int v694; // r9d
  int v695; // edx
  unsigned __int64 j; // rcx
  void *v697; // rdi
  void *v698; // rbx
  int v699; // eax
  void *v700; // rsi
  unsigned int v701; // r9d
  void *v702; // r10
  void *v703; // r11
  __int64 v704; // r9
  unsigned int v705; // r9d
  void *v706; // rcx
  __int64 v707; // r9
  void *v708; // r11
  void *v709; // r10
  unsigned int *v710; // rcx
  unsigned int v711; // r9d
  void *v712; // r12
  SIZE_T v713; // r13
  void *v714; // rdi
  void *v715; // r10
  void *v716; // r11
  LPVOID v717; // rax
  void *v718; // rsi
  HANDLE v719; // rax
  SIZE_T v720; // rdi
  int v721; // ecx
  HANDLE v722; // rax
  _QWORD *v723; // rsi
  HANDLE v724; // rax
  HANDLE v725; // rax
  HANDLE v726; // rax
  HANDLE v727; // rax
  void *v728; // rsi
  HANDLE v729; // rax
  HANDLE v730; // rax
  _QWORD *v731; // rdi
  void *v732; // rsi
  HANDLE v733; // rax
  void *v734; // rsi
  HANDLE v735; // rax
  void *v736; // rsi
  HANDLE v737; // rax
  HANDLE v738; // rax
  void *v739; // rdi
  HANDLE v740; // rax
  unsigned int v741; // edi
  size_t v742; // rcx
  _DWORD *v743; // r9
  __int64 v744; // r10
  int *v745; // rdx
  LPVOID v746; // rcx
  unsigned int v747; // r11d
  int v748; // r9d
  wchar_t *v749; // rax
  struct _INISPOOLER *v750; // r8
  wchar_t *v751; // r14
  struct SplLogType *v752; // rax
  __int64 v753; // r10
  struct _INIENVIRONMENT *IniKey; // rax
  struct _INIDRIVER *DriverInEnvironment; // rax
  __int64 v756; // rcx
  __int64 v757; // rcx
  int ClassDriverFromWU; // eax
  struct SplLogType *v759; // rax
  __int64 v760; // r10
  __int64 v761; // r11
  struct SplLogType *v762; // rax
  __int64 v763; // r10
  __int64 v764; // r11
  int *v765; // rcx
  struct _INISPOOLER *v766; // r8
  NCoreLibrary *v767; // rcx
  signed int v768; // edi
  DWORD v769; // r8d
  int v770; // edx
  const unsigned __int16 *v771; // rcx
  unsigned __int16 *v772; // rbx
  int v773; // edx
  const unsigned __int16 *v774; // rcx
  DWORD v775; // r8d
  int v776; // edx
  const unsigned __int16 *v777; // rcx
  HMODULE v778; // rdi
  unsigned __int64 v779; // rdx
  struct SplLogType *v780; // rax
  __int64 v781; // r10
  __int64 v782; // r11
  unsigned int v784; // [rsp+20h] [rbp-CB8h]
  char *v785; // [rsp+28h] [rbp-CB0h]
  unsigned __int16 *v786; // [rsp+28h] [rbp-CB0h]
  char *v787; // [rsp+28h] [rbp-CB0h]
  const unsigned __int16 *v788; // [rsp+38h] [rbp-CA0h]
  unsigned int v789; // [rsp+50h] [rbp-C88h]
  unsigned int v790; // [rsp+58h] [rbp-C80h]
  unsigned int v791; // [rsp+58h] [rbp-C80h]
  void *v792; // [rsp+60h] [rbp-C78h]
  LPVOID v793; // [rsp+60h] [rbp-C78h]
  void *Src; // [rsp+68h] [rbp-C70h]
  unsigned __int8 *Srca; // [rsp+68h] [rbp-C70h]
  LPVOID v796; // [rsp+70h] [rbp-C68h]
  SIZE_T v797; // [rsp+78h] [rbp-C60h]
  SIZE_T v798; // [rsp+80h] [rbp-C58h] BYREF
  unsigned int v799; // [rsp+88h] [rbp-C50h] BYREF
  SIZE_T dwBytes; // [rsp+90h] [rbp-C48h] BYREF
  LPVOID v801; // [rsp+98h] [rbp-C40h]
  LPVOID v802; // [rsp+A0h] [rbp-C38h]
  size_t Size; // [rsp+A8h] [rbp-C30h] BYREF
  LPVOID v804; // [rsp+B0h] [rbp-C28h]
  SIZE_T v805; // [rsp+B8h] [rbp-C20h] BYREF
  size_t v806; // [rsp+C0h] [rbp-C18h]
  size_t v807; // [rsp+C8h] [rbp-C10h] BYREF
  LPVOID v808; // [rsp+D0h] [rbp-C08h] BYREF
  unsigned int v809; // [rsp+D8h] [rbp-C00h]
  SIZE_T v810; // [rsp+E0h] [rbp-BF8h] BYREF
  LPVOID v811; // [rsp+E8h] [rbp-BF0h]
  LPVOID v812; // [rsp+F0h] [rbp-BE8h] BYREF
  SIZE_T v813; // [rsp+F8h] [rbp-BE0h] BYREF
  LPVOID v814; // [rsp+100h] [rbp-BD8h] BYREF
  LPVOID v815; // [rsp+108h] [rbp-BD0h] BYREF
  LPVOID v816; // [rsp+110h] [rbp-BC8h]
  SIZE_T v817; // [rsp+118h] [rbp-BC0h]
  LPVOID lpMem; // [rsp+120h] [rbp-BB8h] BYREF
  LPVOID v819; // [rsp+128h] [rbp-BB0h]
  char v820; // [rsp+130h] [rbp-BA8h]
  SIZE_T v821; // [rsp+138h] [rbp-BA0h]
  unsigned int *v822; // [rsp+140h] [rbp-B98h] BYREF
  SIZE_T v823; // [rsp+148h] [rbp-B90h] BYREF
  SIZE_T v824; // [rsp+150h] [rbp-B88h] BYREF
  size_t v825[2]; // [rsp+158h] [rbp-B80h] BYREF
  struct _SELECTED_DRV_INFO *v826; // [rsp+168h] [rbp-B70h] BYREF
  size_t v827; // [rsp+170h] [rbp-B68h]
  SIZE_T v828; // [rsp+178h] [rbp-B60h] BYREF
  size_t v829[2]; // [rsp+180h] [rbp-B58h] BYREF
  LPVOID v830; // [rsp+190h] [rbp-B48h]
  size_t pcchLength; // [rsp+198h] [rbp-B40h] BYREF
  LPVOID v832; // [rsp+1A0h] [rbp-B38h]
  unsigned __int16 *v833; // [rsp+1A8h] [rbp-B30h]
  unsigned __int16 *v834; // [rsp+1B0h] [rbp-B28h]
  unsigned int v835; // [rsp+1B8h] [rbp-B20h] BYREF
  unsigned int v836; // [rsp+1BCh] [rbp-B1Ch] BYREF
  _BYTE v837[12]; // [rsp+1C4h] [rbp-B14h] BYREF
  HMODULE hLibModule; // [rsp+1D0h] [rbp-B08h] BYREF
  struct _SETUP_CONTEXT *v839; // [rsp+1D8h] [rbp-B00h]
  HMODULE v840; // [rsp+1E0h] [rbp-AF8h] BYREF
  unsigned int v841; // [rsp+1E8h] [rbp-AF0h] BYREF
  unsigned int v842; // [rsp+1ECh] [rbp-AECh] BYREF
  unsigned int v843; // [rsp+1F0h] [rbp-AE8h] BYREF
  int v844; // [rsp+1F4h] [rbp-AE4h]
  unsigned int v845; // [rsp+1F8h] [rbp-AE0h] BYREF
  int v846; // [rsp+1FCh] [rbp-ADCh]
  int v847; // [rsp+200h] [rbp-AD8h]
  unsigned __int16 *v848; // [rsp+208h] [rbp-AD0h]
  struct _PSETUP_LOCAL_DATA *v849[2]; // [rsp+210h] [rbp-AC8h] BYREF
  unsigned __int16 *v850; // [rsp+220h] [rbp-AB8h]
  HMODULE v851; // [rsp+228h] [rbp-AB0h] BYREF
  HMODULE hModule; // [rsp+230h] [rbp-AA8h] BYREF
  HANDLE hToken; // [rsp+240h] [rbp-A98h]
  HMODULE phModule; // [rsp+248h] [rbp-A90h] BYREF
  __int128 v855; // [rsp+250h] [rbp-A88h] BYREF
  __int128 v856; // [rsp+260h] [rbp-A78h]
  __int128 v857; // [rsp+270h] [rbp-A68h] BYREF
  __int128 v858; // [rsp+280h] [rbp-A58h]
  int v859; // [rsp+298h] [rbp-A40h] BYREF
  __int64 v860; // [rsp+2A0h] [rbp-A38h]
  int v861; // [rsp+2A8h] [rbp-A30h]
  _QWORD v862[2]; // [rsp+2B0h] [rbp-A28h] BYREF
  int v863; // [rsp+2C0h] [rbp-A18h]
  int v864; // [rsp+2C8h] [rbp-A10h] BYREF
  __int64 v865; // [rsp+2D0h] [rbp-A08h]
  int v866; // [rsp+2D8h] [rbp-A00h]
  int v867; // [rsp+2E0h] [rbp-9F8h] BYREF
  __int64 v868; // [rsp+2E8h] [rbp-9F0h]
  int v869; // [rsp+2F0h] [rbp-9E8h]
  int v870; // [rsp+2F8h] [rbp-9E0h] BYREF
  __int64 v871; // [rsp+300h] [rbp-9D8h]
  int v872; // [rsp+308h] [rbp-9D0h]
  int v873; // [rsp+310h] [rbp-9C8h] BYREF
  __int64 v874; // [rsp+318h] [rbp-9C0h]
  int v875; // [rsp+320h] [rbp-9B8h]
  int v876; // [rsp+328h] [rbp-9B0h] BYREF
  __int64 v877; // [rsp+330h] [rbp-9A8h]
  int v878; // [rsp+338h] [rbp-9A0h]
  int v879; // [rsp+340h] [rbp-998h] BYREF
  __int64 v880; // [rsp+348h] [rbp-990h]
  int v881; // [rsp+350h] [rbp-988h]
  unsigned __int16 *v882[5]; // [rsp+3B0h] [rbp-928h] BYREF
  int v883; // [rsp+3DCh] [rbp-8FCh]
  unsigned __int16 *v884; // [rsp+3E0h] [rbp-8F8h]
  unsigned __int16 *v885; // [rsp+3E8h] [rbp-8F0h]
  unsigned __int16 *v886; // [rsp+3F0h] [rbp-8E8h]
  _BYTE v887[24]; // [rsp+400h] [rbp-8D8h] BYREF
  unsigned __int16 *v888; // [rsp+418h] [rbp-8C0h]
  struct _PSETUP_LOCAL_DATA *v889; // [rsp+420h] [rbp-8B8h]
  __int64 v890; // [rsp+438h] [rbp-8A0h]
  unsigned __int16 *v891; // [rsp+440h] [rbp-898h]
  char v892[24]; // [rsp+450h] [rbp-888h] BYREF
  char v893[24]; // [rsp+468h] [rbp-870h] BYREF
  char v894[24]; // [rsp+480h] [rbp-858h] BYREF
  char v895[24]; // [rsp+498h] [rbp-840h] BYREF
  char v896[24]; // [rsp+4B0h] [rbp-828h] BYREF
  char v897[24]; // [rsp+4C8h] [rbp-810h] BYREF
  char v898[24]; // [rsp+4E0h] [rbp-7F8h] BYREF
  char v899[24]; // [rsp+4F8h] [rbp-7E0h] BYREF
  char v900[24]; // [rsp+510h] [rbp-7C8h] BYREF
  char v901[24]; // [rsp+528h] [rbp-7B0h] BYREF
  char v902[24]; // [rsp+540h] [rbp-798h] BYREF
  char v903[24]; // [rsp+558h] [rbp-780h] BYREF
  char v904[24]; // [rsp+570h] [rbp-768h] BYREF
  char v905[24]; // [rsp+588h] [rbp-750h] BYREF
  char v906[24]; // [rsp+5A0h] [rbp-738h] BYREF
  char v907[24]; // [rsp+5B8h] [rbp-720h] BYREF
  char v908[24]; // [rsp+5D0h] [rbp-708h] BYREF
  char v909[24]; // [rsp+5E8h] [rbp-6F0h] BYREF
  _DWORD v910[2]; // [rsp+600h] [rbp-6D8h] BYREF
  __int64 v911; // [rsp+608h] [rbp-6D0h]
  __int16 v912; // [rsp+610h] [rbp-6C8h]
  __int64 v913; // [rsp+612h] [rbp-6C6h]
  __int16 v914; // [rsp+61Ah] [rbp-6BEh]
  _BYTE v915[32]; // [rsp+620h] [rbp-6B8h] BYREF
  _BYTE v916[32]; // [rsp+640h] [rbp-698h] BYREF
  _BYTE v917[4]; // [rsp+660h] [rbp-678h] BYREF
  unsigned __int16 v918[260]; // [rsp+664h] [rbp-674h] BYREF
  int v919; // [rsp+86Ch] [rbp-46Ch]
  unsigned __int16 v920[264]; // [rsp+870h] [rbp-468h] BYREF
  _BYTE v921[528]; // [rsp+A80h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+CD8h] [rbp+0h]

  v833 = a4;
  v834 = a3;
  v8 = a2;
  v848 = (unsigned __int16 *)this;
  v828 = (SIZE_T)this;
  v814 = a2;
  v823 = (SIZE_T)a3;
  pcchLength = (size_t)a4;
  v839 = a6;
  v9 = 0;
  v10 = 0;
  v807 = 0;
  v826 = 0;
  hToken = 0;
  LODWORD(v813) = 196624;
  LODWORD(v798) = 196624;
  LOWORD(v805) = -1;
  memset_0(v921, 0, 0x208u);
  if ( !a3 || !a4 || !a6 )
  {
    LODWORD(v13) = -2147024809;
    LODWORD(dwBytes) = -2147024809;
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
      L"Incorrect parameters passed to InstallPrinterDriverFromPackage:");
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
      L"pszDriverName=%ws, pszEnvironment=%ws, pIniSpooler=%p",
      a3,
      a4,
      v839);
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"InternalInstallPrinterDriverFromPackage",
      L"Invalid parameter",
      0,
      v8,
      a3,
      0,
      a4,
      0,
      0,
      0x57u,
      0x80070057);
    v11 = (unsigned int)a5 & 0xFBFFFFFF;
    goto LABEL_59;
  }
  v11 = (unsigned int)a5 & 0xFBFFFFFF;
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
    L"Installing %ws printer driver with pszServer=%ws, pszInfPath=%ws, pszEnvironment=%ws, dwFlags=%d.",
    a3,
    v848,
    v8,
    v833,
    (unsigned int)a5 & 0xFBFFFFFF);
  ProcessorArchitectureFromEnvironmentString = GetProcessorArchitectureFromEnvironmentString(v833, &v805);
  LODWORD(v13) = ProcessorArchitectureFromEnvironmentString;
  LODWORD(dwBytes) = ProcessorArchitectureFromEnvironmentString;
  if ( ProcessorArchitectureFromEnvironmentString < 0 )
  {
    v790 = ProcessorArchitectureFromEnvironmentString;
    v789 = 87;
    v788 = v833;
    v786 = a3;
    v14 = L"GetProcessorArchitectureFromEnvironmentString failed";
LABEL_6:
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"InternalInstallPrinterDriverFromPackage",
      v14,
      0,
      v8,
      v786,
      0,
      v788,
      0,
      0,
      v789,
      v790);
LABEL_59:
    v809 = v11;
    goto LABEL_60;
  }
  DriverValidationPolicyLevel = GetDriverValidationPolicyLevel();
  if ( (unsigned int)IsTestSigningEnabled() || DriverValidationPolicyLevel > 3 )
  {
    v809 = (unsigned int)a5 & 0xFBFFFFFF;
    if ( !v8 )
      goto LABEL_30;
  }
  else
  {
    if ( !v8 )
    {
      LODWORD(v13) = -2146762748;
      v17 = -2146762748;
      LODWORD(dwBytes) = -2146762748;
      goto LABEL_14;
    }
    v16 = ValidateDriver(DriverValidationPolicyLevel, v8);
    LODWORD(v13) = v16;
    LODWORD(dwBytes) = v16;
    if ( v16 < 0 )
    {
      v17 = v16;
LABEL_14:
      v18 = WIN32_FROM_HRESULT(v17);
      v790 = v19;
      v789 = v18;
      v788 = v833;
      v786 = v834;
      v14 = L"ValidateDriver failed";
      goto LABEL_6;
    }
    v809 = (unsigned int)a5 & 0xFBFFFFFF;
  }
  if ( !(unsigned int)IsInInfDir(v8) )
  {
    if ( (unsigned int)IsInfInDriverStore(v8) )
      goto LABEL_30;
    LODWORD(v13) = -2147024809;
    LODWORD(dwBytes) = -2147024809;
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
      L"Invalid INF path passed into InstallPrinterDriverFromPackage: %ws",
      v8);
LABEL_37:
    LastError = GetLastError();
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"InternalInstallPrinterDriverFromPackage",
      L"IsInfInDriverStore failed",
      0,
      v8,
      v834,
      0,
      v833,
      0,
      0,
      LastError,
      v13);
LABEL_60:
    v808 = 0;
    v815 = 0;
    goto LABEL_61;
  }
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0);
  hLibModule = Library;
  if ( Library
    || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v20),
        LODWORD(v13) = LastErrorAsFailHRNoBreak,
        LODWORD(dwBytes) = LastErrorAsFailHRNoBreak,
        LastErrorAsFailHRNoBreak >= 0) )
  {
    ProcAddress = GetProcAddress(Library, "SetupGetInfDriverStoreLocationW");
    if ( ProcAddress
      || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v23),
          LODWORD(v13) = LastErrorAsFailHRNoBreak,
          LODWORD(dwBytes) = LastErrorAsFailHRNoBreak,
          LastErrorAsFailHRNoBreak >= 0) )
    {
      v911 = 0;
      v913 = 0;
      v914 = 0;
      v910[0] = 28;
      v910[1] = 2;
      v912 = v805;
      if ( ((unsigned int (__fastcall *)(unsigned __int16 *, _DWORD *, _QWORD, _BYTE *, int, _QWORD))ProcAddress)(
             v8,
             v910,
             0,
             v921,
             260,
             0) )
      {
        LODWORD(v13) = 0;
        LODWORD(dwBytes) = 0;
        v26 = 0;
        goto LABEL_25;
      }
      LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v25);
      LODWORD(v13) = LastErrorAsFailHRNoBreak;
      LODWORD(dwBytes) = LastErrorAsFailHRNoBreak;
    }
  }
  v26 = LastErrorAsFailHRNoBreak;
LABEL_25:
  v27 = (unsigned __int16 *)v921;
  if ( v26 < 0 )
    v27 = v8;
  v8 = v27;
  if ( hLibModule )
    FreeLibrary(hLibModule);
  v814 = v8;
  if ( v26 < 0 )
    goto LABEL_37;
LABEL_30:
  v28 = (4 * (((unsigned __int8)a5 & 1) == 0) + 4) | 0x70010;
  if ( ((unsigned int)a5 & 0x8000000) == 0 )
    v28 = (4 * (((unsigned __int8)a5 & 1) == 0) + 4) | 0x30010;
  LODWORD(v813) = v28;
  hLibModule = (HMODULE)RevertToPrinterSelf();
  if ( !hLibModule )
  {
    v35 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v29);
    v36 = L"Failed to revert to Spooler service for loading ntprint.dll, hr: 0x%x";
    goto LABEL_43;
  }
  v10 = LoadLibraryExW(L"ntprint.dll", 0, 0x800u);
  v807 = (size_t)v10;
  if ( v10 )
  {
    v31 = 0;
    LODWORD(v13) = 0;
    LODWORD(dwBytes) = 0;
  }
  else
  {
    v33 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v30);
    v31 = v33;
    LODWORD(v13) = v33;
    LODWORD(dwBytes) = v33;
    if ( v33 < 0 )
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
        L"Failed to load ntprint.dll, hr: 0x%x",
        (unsigned int)v33);
  }
  if ( !ImpersonatePrinterClient(hLibModule) )
  {
    v35 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v34);
    v36 = L"Failed to impersonate printer client, hr: 0x%x";
LABEL_43:
    LODWORD(v13) = v35;
    LODWORD(dwBytes) = v35;
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
      v36,
      v35);
    v31 = v13;
  }
  if ( v31 < 0 )
  {
    v37 = GetLastError();
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"InternalInstallPrinterDriverFromPackage",
      L"LoadLibrary(ntprint.dll) failed",
      0,
      v8,
      v834,
      0,
      v833,
      0,
      0,
      v37,
      v13);
    LODWORD(v798) = v28;
    goto LABEL_60;
  }
  v808 = GetProcAddress(v10, "PSetupParseInfAndCommitFileQueue");
  v815 = v808;
  if ( !v808 )
  {
    LODWORD(v13) = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v38);
    LODWORD(dwBytes) = v13;
    if ( (int)v13 < 0 )
    {
      v39 = GetLastError();
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"InternalInstallPrinterDriverFromPackage",
        L"GetProcAddress(pfnPSetupParseInfAndCommitFileQueue) failed",
        0,
        v8,
        v834,
        0,
        v833,
        0,
        0,
        v39,
        v13);
      LODWORD(v813) = v28;
      LODWORD(v798) = v28;
LABEL_61:
      v41 = 0;
      v796 = 0;
      v819 = 0;
      goto LABEL_62;
    }
  }
  v41 = GetProcAddress(v10, "PSetupInstallICMProfiles");
  v796 = v41;
  v819 = v41;
  if ( !v41 )
  {
    LODWORD(v13) = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v40);
    LODWORD(dwBytes) = v13;
    if ( (int)v13 < 0 )
    {
      v42 = GetLastError();
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"InternalInstallPrinterDriverFromPackage",
        L"GetProcAddress(pfnPSetupInstallICMProfiles) failed",
        0,
        v8,
        v834,
        0,
        v833,
        0,
        0,
        v42,
        v13);
      v807 = (size_t)v10;
      LODWORD(v813) = v28;
      LODWORD(v798) = v28;
      v814 = v8;
      v809 = (unsigned int)a5 & 0xFBFFFFFF;
LABEL_62:
      v44 = 0;
      goto LABEL_63;
    }
  }
  v44 = GetProcAddress(v10, "PSetupDestroySelectedDriverInfo");
  v797 = (SIZE_T)v44;
  v816 = v44;
  if ( !v44 )
  {
    LODWORD(v13) = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v43);
    LODWORD(dwBytes) = v13;
    if ( (int)v13 < 0 )
    {
      v45 = GetLastError();
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"InternalInstallPrinterDriverFromPackage",
        L"GetProcAddress(pfnPSetupDestroySelectedDriverInfo) failed",
        0,
        v8,
        v834,
        0,
        v833,
        0,
        0,
        v45,
        v13);
      v815 = v808;
      v807 = (size_t)v10;
      LODWORD(v798) = v813;
      v814 = v8;
      v809 = (unsigned int)a5 & 0xFBFFFFFF;
      goto LABEL_65;
    }
  }
  v796 = v41;
  v797 = (SIZE_T)v44;
  hToken = RevertToPrinterSelf();
  if ( !hToken )
  {
    LODWORD(v13) = -2147418113;
    LODWORD(dwBytes) = -2147418113;
    v46 = GetLastError();
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"InternalInstallPrinterDriverFromPackage",
      L"RevertToPrinterSelf failed",
      0,
      v8,
      v834,
      0,
      v833,
      0,
      0,
      v46,
      0x8000FFFF);
    v796 = v41;
    v819 = v41;
    v815 = v808;
    v807 = (size_t)v10;
    LODWORD(v798) = v813;
    v814 = v8;
    v809 = (unsigned int)a5 & 0xFBFFFFFF;
LABEL_63:
    v797 = (SIZE_T)v44;
    goto LABEL_64;
  }
  LODWORD(v13) = 0;
  LODWORD(dwBytes) = 0;
  v819 = v41;
  v815 = v808;
  v807 = (size_t)v10;
  LODWORD(v798) = v813;
  v814 = v8;
  v809 = (unsigned int)a5 & 0xFBFFFFFF;
LABEL_64:
  v816 = v44;
LABEL_65:
  if ( (_WORD)v805 == 12 && v8 && !(unsigned __int8)IsServerSKU() )
  {
    try
    {
      LocalSpoolerTelemetry::WriteDbgTraceInfo(
        "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
        L"Checking if ARM64 is supported in driver package: %ws",
        v8);
      std::wstring::wstring(v915, v8);
      LOBYTE(v805) = PrintCore::DriverHelpers::IsArchitectureSupportedByDriver(v915);
      std::wstring::_Tidy_deallocate(v915);
      if ( !(_BYTE)v805 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
          L"ARM64 is not supported in driver package: %ws",
          v8);
        std::wstring::wstring(v916, v8);
        LOBYTE(v805) = PrintCore::DriverHelpers::IsMicrosoftDriverPackage(v916);
        std::wstring::_Tidy_deallocate(v916);
        if ( (_BYTE)v805 )
        {
          LocalSpoolerTelemetry::WriteDbgTraceInfo(
            "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
            L"Driver package is a Microsoft driver package, not firing a WNF notification");
        }
        else
        {
          memset_0(v917, 0, 0x418u);
          v919 = 1;
          v48 = StringCchCopyW(v918, 0x104u, v834);
          wil::details::in1diag3::Throw_IfFailedMsg(
            retaddr,
            (void *)0x28FB,
            (unsigned int)"printscan\\print\\spooler\\localspl\\packageinstall.cxx",
            (const char *)v48,
            (int)"Failed to copy driver name (device description) information!",
            v785);
          v49 = StringCchCopyW(v920, 0x104u, v8);
          wil::details::in1diag3::Throw_IfFailedMsg(
            retaddr,
            (void *)0x28FC,
            (unsigned int)"printscan\\print\\spooler\\localspl\\packageinstall.cxx",
            (const char *)v49,
            (int)"Failed to copy driver package INF information!",
            v787);
          wil::wnf_publish<_DriverNoNativeArchitectureSupportData>(v50, v917);
        }
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x2905,
        (unsigned int)"printscan\\print\\spooler\\localspl\\packageinstall.cxx",
        v47);
      v9 = 0;
      LODWORD(v13) = dwBytes;
      v10 = (HMODULE)v807;
      v808 = v815;
      v41 = v819;
      v796 = v819;
      v44 = v816;
      v797 = (SIZE_T)v816;
      LODWORD(v813) = v798;
      v848 = (unsigned __int16 *)v828;
      v8 = (unsigned __int16 *)v814;
      v834 = (unsigned __int16 *)v823;
      v833 = (unsigned __int16 *)pcchLength;
      v11 = v809;
    }
  }
  v820 = 0;
  if ( (int)v13 >= 0 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
      L"Parsing INF and committing files");
    v784 = v11;
    v51 = v834;
    v52 = ((__int64 (__fastcall *)(_QWORD, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, struct _SELECTED_DRV_INFO **))v808)(
            0,
            v8,
            v834,
            v833,
            v784,
            &v826);
    LODWORD(v13) = v52;
    if ( v52 < 0 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
        L"Parsing INF and committing files failed: hr: 0x%x",
        (unsigned int)v52);
      if ( (_DWORD)v13 == -2147021875 )
      {
        v820 = 1;
        v859 = -2147021875;
        v860 = 4;
        v861 = 0;
        v862[0] = L"-";
        v862[1] = 4;
        v863 = 1;
        SplLogType::SplLogType((SplLogType *)v901, v8);
        v53 = SplLogType::SplLogType((SplLogType *)v908, v834);
        SplLogEvent2(&SETUP_INSTALL_V4_PRINTER_DRIVER_FAILED, v53, v54, v862, &v859, 0);
      }
      else
      {
        v55 = GetLastError();
        if ( v826 && *((_DWORD *)v826 + 43) )
          v56 = (const unsigned __int16 *)*((_QWORD *)v826 + 28);
        else
          v56 = 0;
        if ( v826 )
          v57 = *((_DWORD *)v826 + 43);
        else
          v57 = 0;
        if ( v826 )
          v58 = (const unsigned __int16 *)*((_QWORD *)v826 + 23);
        else
          v58 = 0;
        SplLogPrinterSetupCoreDriverEvent(
          &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
          L"InternalInstallPrinterDriverFromPackage",
          L"pfnPSetupParseInfAndCommitFileQueue failed",
          0,
          v8,
          v51,
          v58,
          v833,
          v57,
          v56,
          v55,
          v13);
      }
    }
    if ( (int)v13 >= 0 && *((_DWORD *)v826 + 24) > 4u )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
        L"v%u drivers are not supported");
      LODWORD(v13) = -2147021882;
      v820 = 1;
      v867 = *((_DWORD *)v826 + 24);
      v868 = 4;
      v869 = 0;
      SplLogType::SplLogType((SplLogType *)v909, *(const unsigned __int16 **)v826);
      v59 = SplLogType::SplLogType((SplLogType *)v892, *((const unsigned __int16 **)v826 + 1));
      SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_UNSUPPORTED_VERSION, v59, v60, &v867, 0);
    }
  }
  memset_0(v882, 0, 0x50u);
  if ( (int)v13 >= 0 )
  {
    v883 = v813;
    v882[4] = (unsigned __int16 *)v826;
    v885 = v834;
    v886 = v833;
    v884 = v8;
    v882[3] = v848;
    if ( *((_DWORD *)v826 + 24) < 4u )
    {
      v847 = 0;
      v851 = 0;
      LODWORD(v804) = 0;
      v840 = 0;
      v62 = LocalAlloc(0x40u, 4u);
      SP<unsigned char,SP_HLOCAL<unsigned char>>::operator=(&v840, v62);
      hLibModule = v840;
      if ( !v840 )
      {
        v66 = -2147024882;
LABEL_629:
        SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v840);
        if ( v66 >= 0 )
        {
          v44 = (void *)v797;
          if ( (_DWORD)v804 == 4 )
          {
            v66 = 0;
            v847 = *(_DWORD *)v851;
            goto LABEL_1005;
          }
        }
        else
        {
          if ( v66 == -805306316 )
          {
            v66 = -1073418222;
LABEL_1002:
            v44 = (void *)v797;
            goto LABEL_1005;
          }
          if ( v66 == -805306139 || v66 == -1073425151 )
          {
            v66 = -1073418201;
            goto LABEL_1002;
          }
          v44 = (void *)v797;
          if ( v66 == -805306306 )
          {
            v66 = -1073418200;
LABEL_1005:
            SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v851);
            LODWORD(dwBytes) = v66;
            LocalSpoolerTelemetry::GetWindowsInfoResult<long &>(&dwBytes);
            v749 = wcsrchr(*(const wchar_t **)v826, 0x5Cu);
            v821 = (SIZE_T)v749;
            if ( !v749 )
            {
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
                L"Expecting full DriverStore path for driver: %ws",
                *(_QWORD *)v826);
              LocalSpoolerTelemetry::WriteDbgTraceInfo(
                "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
                L"Driver Name passed along via RPC: %ws",
                v834);
              v749 = (wchar_t *)v821;
            }
            if ( v847
              && v66 >= 0
              && (!v749
               || (v751 = v749 + 1, (unsigned int)_o__wcsicmp(v749 + 1, L"prnms003.inf"))
               && (unsigned int)_o__wcsicmp(v751, L"ntprint.inf")) )
            {
              LODWORD(v13) = -2147021882;
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
                L"v%u drivers are not supported on Windows S: hr: 0x%x",
                *((unsigned int *)v826 + 24),
                2147945414LL);
              v864 = *((_DWORD *)v826 + 24);
              v865 = 4;
              v866 = 0;
              SplLogType::SplLogType((SplLogType *)v893, *(const unsigned __int16 **)v826);
              v752 = SplLogType::SplLogType((SplLogType *)v894, *((const unsigned __int16 **)v826 + 1));
              SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_UNSUPPORTED_VERSION, v752, v753, &v864, 0);
            }
            else
            {
              v13 = (unsigned int)NPackageInstallLocalspl::LegacyInstallPrinterDriverFromPackage(v882, v839, v750);
              LocalSpoolerTelemetry::WriteDbgTraceInfo(
                "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
                L"Performing legacy install for v%u driver: hr: 0x%x",
                *((unsigned int *)v826 + 24),
                v13);
            }
            goto LABEL_1033;
          }
          if ( v66 != -2147024774 )
            goto LABEL_1005;
        }
        v66 = -1073418210;
        goto LABEL_1005;
      }
      v846 = 0;
      v844 = 0;
      *(_OWORD *)v825 = 0;
      v808 = 0;
      ProcessHeap = GetProcessHeap();
      v64 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
      v65 = v64;
      Src = v64;
      if ( !v64 )
      {
        v792 = 0;
        v66 = -1073741801;
        LODWORD(v798) = -1073741801;
        Src = 0;
LABEL_588:
        LODWORD(v805) = -805306345;
        v809 = -1;
        goto LABEL_589;
      }
      v796 = v41;
      v797 = (SIZE_T)v44;
      *v64 = xmmword_18013E190;
      v64[1] = xmmword_18013E1A0;
      v64[2] = xmmword_18013E1B0;
      v64[3] = xmmword_18013E1C0;
      v64[4] = xmmword_18013E1D0;
      v64[5] = xmmword_18013E1E0;
      v64[6] = xmmword_18013E1F0;
      v64[7] = xmmword_18013E200;
      v64[8] = xmmword_18013E210;
      v64[9] = xmmword_18013E220;
      v67 = GetProcessHeap();
      v68 = HeapAlloc(v67, 8u, 8u);
      v792 = v68;
      if ( !v68 )
      {
        v66 = -1073741801;
        LODWORD(v798) = -1073741801;
        v792 = 0;
        goto LABEL_588;
      }
      *v68 = qword_18013E0D0;
      v828 = __rdtsc();
      LODWORD(dwBytes) = 0;
      LODWORD(Size) = 0;
      v66 = RtlUIntAdd(4, 4, &Size);
      LODWORD(v798) = v66;
      if ( v66 < 0 )
        goto LABEL_585;
      v70 = RtlUIntAdd(0, (unsigned int)Size, &dwBytes);
      v66 = v70 | 0x10000000;
      LODWORD(v798) = v70 | 0x10000000;
      if ( v70 < 0 )
        goto LABEL_585;
      LODWORD(Size) = 0;
      v66 = RtlUIntAdd(v71, 160, &Size);
      LODWORD(v798) = v66;
      if ( v66 < 0 )
        goto LABEL_585;
      v72 = RtlUIntAdd((unsigned int)dwBytes, (unsigned int)Size, &dwBytes);
      v66 = v74 | v72;
      LODWORD(v798) = v74 | v72;
      if ( (v74 | v72) < 0 )
        goto LABEL_585;
      LODWORD(Size) = 0;
      v66 = RtlUIntAdd(v73, v73 + 4, &Size);
      LODWORD(v798) = v66;
      if ( v66 < 0 )
        goto LABEL_585;
      v75 = RtlUIntAdd((unsigned int)dwBytes, (unsigned int)Size, &dwBytes);
      v66 = v77 | v75;
      LODWORD(v798) = v77 | v75;
      if ( (v77 | v75) < 0
        || (LODWORD(Size) = 0, v66 = RtlUIntAdd(v76, v76 + 4, &Size), LODWORD(v798) = v66, v66 < 0)
        || (v78 = RtlUIntAdd((unsigned int)dwBytes, (unsigned int)Size, &dwBytes),
            v66 = v80 | v78,
            LODWORD(v798) = v80 | v78,
            (v80 | v78) < 0) )
      {
LABEL_585:
        v792 = v69;
        goto LABEL_586;
      }
      pcchLength = 0;
      if ( StringCchLengthW(L"Microsoft-Reserved-24C26ACC-DE62-4303-88AD-6CD4F1447F18", v79, &pcchLength) < 0 )
      {
        v66 = -1073741762;
LABEL_220:
        LODWORD(v798) = v66;
LABEL_586:
        Src = v65;
        goto LABEL_587;
      }
      LODWORD(Size) = 0;
      v66 = RtlUIntAdd(v81, (unsigned int)(2 * (pcchLength + 1)), &Size);
      LODWORD(v798) = v66;
      if ( v66 < 0 )
        goto LABEL_586;
      v82 = RtlUIntAdd((unsigned int)dwBytes, (unsigned int)Size, &dwBytes);
      v66 = v82 | 0x10000000;
      LODWORD(v798) = v82 | 0x10000000;
      if ( v82 < 0 )
        goto LABEL_586;
      LODWORD(Size) = 0;
      v66 = RtlUIntAdd(v83, v83, &Size);
      LODWORD(v798) = v66;
      if ( v66 < 0 )
        goto LABEL_586;
      v84 = RtlUIntAdd((unsigned int)dwBytes, (unsigned int)Size, &dwBytes);
      v66 = v86 | v84;
      LODWORD(v798) = v86 | v84;
      if ( (v86 | v84) < 0 )
        goto LABEL_586;
      LODWORD(Size) = 0;
      v66 = RtlUIntAdd(v85, v85, &Size);
      LODWORD(v798) = v66;
      if ( v66 < 0 )
        goto LABEL_586;
      v87 = RtlUIntAdd((unsigned int)dwBytes, (unsigned int)Size, &dwBytes);
      v66 = v88 | v87;
      LODWORD(v798) = v88 | v87;
      if ( (v88 | v87) < 0 )
        goto LABEL_586;
      HIDWORD(v825[0]) = dwBytes;
      v89 = dwBytes;
      v90 = GetProcessHeap();
      v91 = HeapAlloc(v90, 8u, v89);
      if ( !v91 )
      {
        v66 = -1073741801;
        LODWORD(v798) = -1073741801;
LABEL_587:
        v796 = v41;
        v797 = (SIZE_T)v44;
        goto LABEL_588;
      }
      LODWORD(v813) = 0;
      v825[1] = (size_t)v91;
      LODWORD(v825[0]) = 0;
      LODWORD(v822) = 0;
      v821 = 0;
      lpMem = v91;
      LODWORD(v806) = 8;
      v65 = Src;
      LODWORD(Size) = 160;
      v797 = (SIZE_T)v44;
      v796 = v41;
      v66 = RtlULongLongAdd(v91, 4, &v822);
      LODWORD(v798) = v66;
      if ( v66 < 0 )
        goto LABEL_122;
      if ( (unsigned __int64)(v92 + 2) > v825[1] + HIDWORD(v825[0]) )
        goto LABEL_137;
      *v92 = v93;
      *v822 = 0;
      v94 = Size;
      v95 = ++LODWORD(v825[0]);
      LODWORD(v822) = 0;
      v821 = 0;
      if ( Src )
      {
        if ( !(_DWORD)Size )
          goto LABEL_120;
      }
      else if ( (_DWORD)Size )
      {
LABEL_120:
        v66 = -1073741811;
LABEL_121:
        LODWORD(v798) = v66;
        goto LABEL_122;
      }
      v97 = (unsigned int *)v825[1];
      if ( v825[1] )
      {
        lpMem = (LPVOID)v825[1];
        LODWORD(dwBytes) = 0;
        if ( v95 )
        {
          do
          {
            LODWORD(v810) = 0;
            v66 = RtlUIntAdd((unsigned int)v93, *v97, &v810);
            LODWORD(v798) = v66;
            if ( v66 < 0 )
              goto LABEL_122;
            v796 = v41;
            v797 = (SIZE_T)v44;
            Src = v65;
            v792 = v99;
            v66 = RtlULongLongAdd(v100, (unsigned int)v810, &lpMem);
            LODWORD(v798) = v66;
            if ( v66 < 0 )
              goto LABEL_122;
            LODWORD(dwBytes) = dwBytes + 1;
            v792 = v101;
            Src = v65;
            v797 = (SIZE_T)v44;
            v796 = v41;
            v97 = (unsigned int *)lpMem;
          }
          while ( (unsigned int)dwBytes < LODWORD(v825[0]) );
        }
        v66 = RtlULongLongAdd(v97, v93, &v822);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        v103 = (unsigned int)Size;
        if ( (unsigned __int64)v102 + (unsigned int)Size + 4 > v825[1] + HIDWORD(v825[0]) )
          goto LABEL_137;
        *v102 = Size;
        if ( v65 )
        {
          memcpy_0(v822, v65, v103);
          v98 = 4;
        }
      }
      else
      {
        LODWORD(Size) = 0;
        v66 = RtlUIntAdd((unsigned int)v93, v94, &Size);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        v66 = RtlUIntAdd(HIDWORD(v825[0]), (unsigned int)Size, (char *)v825 + 4);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
      }
      v104 = ++LODWORD(v825[0]);
      LODWORD(v822) = 0;
      v821 = 0;
      if ( v792 )
      {
        if ( !(_DWORD)v806 )
          goto LABEL_120;
      }
      else if ( (_DWORD)v806 )
      {
        goto LABEL_120;
      }
      v105 = (unsigned int *)v825[1];
      if ( v825[1] )
      {
        lpMem = (LPVOID)v825[1];
        LODWORD(v810) = 0;
        if ( v104 )
        {
          do
          {
            LODWORD(Size) = 0;
            v66 = RtlUIntAdd((unsigned int)v98, *v105, &Size);
            LODWORD(v798) = v66;
            if ( v66 < 0 )
              goto LABEL_122;
            v796 = v41;
            v797 = (SIZE_T)v44;
            Src = v65;
            v792 = v107;
            v66 = RtlULongLongAdd(v108, (unsigned int)Size, &lpMem);
            LODWORD(v798) = v66;
            if ( v66 < 0 )
              goto LABEL_122;
            LODWORD(v810) = v810 + 1;
            v792 = v109;
            Src = v65;
            v797 = (SIZE_T)v44;
            v796 = v41;
            v105 = (unsigned int *)lpMem;
          }
          while ( (unsigned int)v810 < LODWORD(v825[0]) );
        }
        v66 = RtlULongLongAdd(v105, v98, &v822);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        v112 = (unsigned int)v806;
        if ( (unsigned __int64)v111 + (unsigned int)v806 + 4 > v825[1] + HIDWORD(v825[0]) )
          goto LABEL_137;
        *v111 = v806;
        if ( v110 )
        {
          memcpy_0(v822, v110, v112);
          v106 = 4;
        }
      }
      else
      {
        LODWORD(Size) = 0;
        v66 = RtlUIntAdd((unsigned int)v98, (unsigned int)v806, &Size);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        v66 = RtlUIntAdd(HIDWORD(v825[0]), (unsigned int)Size, (char *)v825 + 4);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
      }
      v113 = ++LODWORD(v825[0]);
      LODWORD(v822) = 0;
      v821 = 0;
      v114 = (unsigned int *)v825[1];
      v807 = v825[1];
      if ( v825[1] )
      {
        lpMem = (LPVOID)v825[1];
        LODWORD(v810) = 0;
        if ( v113 )
        {
          do
          {
            LODWORD(Size) = 0;
            v66 = RtlUIntAdd((unsigned int)v106, *v114, &Size);
            LODWORD(v798) = v66;
            if ( v66 < 0 )
              goto LABEL_122;
            v796 = v41;
            v797 = (SIZE_T)v44;
            Src = v65;
            v792 = v116;
            v66 = RtlULongLongAdd(v807, (unsigned int)Size, &lpMem);
            LODWORD(v798) = v66;
            if ( v66 < 0 )
              goto LABEL_122;
            LODWORD(v810) = v810 + 1;
            v792 = v117;
            Src = v65;
            v797 = (SIZE_T)v44;
            v796 = v41;
            v114 = (unsigned int *)lpMem;
            v807 = (size_t)lpMem;
          }
          while ( (unsigned int)v810 < v118 );
        }
        v66 = RtlULongLongAdd(v114, v106, &v822);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        if ( v807 + 12 > v825[1] + HIDWORD(v825[0]) )
          goto LABEL_137;
        *(_DWORD *)v807 = 8;
        *(_QWORD *)v822 = v828;
      }
      else
      {
        LODWORD(Size) = 0;
        v66 = RtlUIntAdd((unsigned int)v106, 8, &Size);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        v66 = RtlUIntAdd(HIDWORD(v825[0]), (unsigned int)Size, (char *)v825 + 4);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
      }
      ++LODWORD(v825[0]);
      v807 = 0;
      if ( StringCchLengthW(L"Microsoft-Reserved-24C26ACC-DE62-4303-88AD-6CD4F1447F18", v115, &v807) < 0 )
      {
        v66 = -1073741762;
        goto LABEL_121;
      }
      v66 = RtlULongLongAdd(v807, 1, &v807);
      LODWORD(v798) = v66;
      if ( v66 < 0 )
        goto LABEL_122;
      v799 = 2 * v807;
      LODWORD(v822) = 0;
      v821 = 0;
      if ( !(2 * (_DWORD)v807) )
        goto LABEL_120;
      v120 = (unsigned int *)v825[1];
      if ( v825[1] )
      {
        lpMem = (LPVOID)v825[1];
        LODWORD(v810) = 0;
        if ( !LODWORD(v825[0]) )
          goto LABEL_180;
        do
        {
          LODWORD(Size) = 0;
          v66 = RtlUIntAdd((unsigned int)v119, *v120, &Size);
          LODWORD(v798) = v66;
          if ( v66 < 0 )
            goto LABEL_122;
          v796 = v41;
          v797 = (SIZE_T)v44;
          Src = v65;
          v792 = v122;
          v66 = RtlULongLongAdd(v123, (unsigned int)Size, &lpMem);
          LODWORD(v798) = v66;
          if ( v66 < 0 )
          {
            v792 = v124;
            Src = v65;
            v797 = (SIZE_T)v44;
            v796 = v41;
            goto LABEL_122;
          }
          LODWORD(v810) = v810 + 1;
          v120 = (unsigned int *)lpMem;
        }
        while ( (unsigned int)v810 < LODWORD(v825[0]) );
        v792 = v124;
        Src = v65;
        v797 = (SIZE_T)v44;
        v796 = v41;
LABEL_180:
        v66 = RtlULongLongAdd(v120, v119, &v822);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        if ( (unsigned __int64)v126 + v125 + 4 <= v825[1] + HIDWORD(v825[0]) )
        {
          *v126 = v125;
          memcpy_0(v822, L"Microsoft-Reserved-24C26ACC-DE62-4303-88AD-6CD4F1447F18", v125);
          v121 = 4;
          goto LABEL_183;
        }
        goto LABEL_137;
      }
      LODWORD(Size) = 0;
      v66 = RtlUIntAdd((unsigned int)v119, (unsigned int)(2 * v807), &Size);
      LODWORD(v798) = v66;
      if ( v66 < 0 )
        goto LABEL_122;
      v66 = RtlUIntAdd(HIDWORD(v825[0]), (unsigned int)Size, (char *)v825 + 4);
      LODWORD(v798) = v66;
      if ( v66 < 0 )
        goto LABEL_122;
LABEL_183:
      v127 = ++LODWORD(v825[0]);
      LODWORD(v822) = 0;
      v821 = 0;
      v128 = (unsigned int *)v825[1];
      if ( v825[1] )
      {
        lpMem = (LPVOID)v825[1];
        LODWORD(v810) = 0;
        if ( v127 )
        {
          do
          {
            LODWORD(Size) = 0;
            v66 = RtlUIntAdd((unsigned int)v121, *v128, &Size);
            LODWORD(v798) = v66;
            if ( v66 < 0 )
              goto LABEL_122;
            v796 = v41;
            v797 = (SIZE_T)v44;
            Src = v65;
            v792 = v130;
            v66 = RtlULongLongAdd(v131, (unsigned int)Size, &lpMem);
            LODWORD(v798) = v66;
            if ( v66 < 0 )
              goto LABEL_122;
            LODWORD(v810) = v810 + 1;
            v792 = v132;
            Src = v65;
            v797 = (SIZE_T)v44;
            v796 = v41;
            v128 = (unsigned int *)lpMem;
          }
          while ( (unsigned int)v810 < LODWORD(v825[0]) );
        }
        v66 = RtlULongLongAdd(v128, v121, &v822);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        if ( (unsigned __int64)(v133 + 2) > v825[1] + HIDWORD(v825[0]) )
          goto LABEL_137;
        *v133 = v129;
        *v822 = 0;
      }
      else
      {
        LODWORD(Size) = 0;
        v66 = RtlUIntAdd((unsigned int)v121, (unsigned int)v121, &Size);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        v66 = RtlUIntAdd(HIDWORD(v825[0]), (unsigned int)Size, (char *)v825 + 4);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
      }
      v134 = ++LODWORD(v825[0]);
      LODWORD(v822) = 0;
      v821 = 0;
      v135 = (unsigned int *)v825[1];
      v807 = v825[1];
      if ( !v825[1] )
      {
        LODWORD(Size) = 0;
        v66 = RtlUIntAdd((unsigned int)v129, (unsigned int)v129, &Size);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        v66 = RtlUIntAdd(HIDWORD(v825[0]), (unsigned int)Size, (char *)v825 + 4);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
LABEL_206:
        ++LODWORD(v825[0]);
        LODWORD(Size) = 0;
        v66 = RtlUIntAdd(v136, v136, &Size);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        LODWORD(dwBytes) = Size;
        LODWORD(Size) = 0;
        v66 = RtlUIntAdd(v140, 8, &Size);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        v66 = RtlUIntAdd(v141, (unsigned int)Size, &dwBytes);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        LODWORD(Size) = 0;
        v66 = RtlUIntAdd(v142, v142, &Size);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        v66 = RtlUIntAdd((unsigned int)dwBytes, (unsigned int)Size, &dwBytes);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        LODWORD(Size) = 0;
        v66 = RtlUIntAdd(v143, v143, &Size);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        v66 = RtlUIntAdd((unsigned int)dwBytes, (unsigned int)Size, &dwBytes);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        LODWORD(Size) = 0;
        v66 = RtlUIntAdd(v144, v144, &Size);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        v66 = RtlUIntAdd((unsigned int)dwBytes, (unsigned int)Size, &dwBytes);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        LODWORD(Size) = 0;
        v66 = RtlUIntAdd(v145, v145, &Size);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        v66 = RtlUIntAdd((unsigned int)dwBytes, (unsigned int)Size, &dwBytes);
        LODWORD(v798) = v66;
        if ( v66 < 0 )
          goto LABEL_122;
        LODWORD(v806) = 0;
        v802 = 0;
        v823 = __rdtsc();
        v836 = 8;
        v148 = RtlUIntAdd(8, HIDWORD(v825[0]), &v836);
        if ( v148 < 0 )
        {
          Src = v65;
          v797 = (SIZE_T)v44;
          v796 = v41;
          v815 = v10;
          v819 = v8;
        }
        else
        {
          v149 = (v836 + 7) & 0xFFFFFFF8;
          if ( v149 < v836 )
          {
            v66 = -805306219;
            goto LABEL_220;
          }
          v836 = (v836 + 7) & 0xFFFFFFF8;
          v150 = v149;
          v151 = GetProcessHeap();
          v152 = HeapAlloc(v151, 8u, v150);
          lpMem = v152;
          if ( !v152 )
          {
            LODWORD(v805) = -805306345;
            v66 = -805306345;
            LODWORD(v798) = -805306345;
            v809 = -1;
            goto LABEL_511;
          }
          v819 = v8;
          v815 = v10;
          v796 = v41;
          v797 = (SIZE_T)v44;
          v65 = Src;
          v807 = (size_t)v152;
          *v152 = v825[0];
          v148 = RtlULongLongAdd(v152, 4, &v807);
          if ( v148 < 0 )
          {
            lpMem = v153;
          }
          else
          {
            v157 = v807;
            *(_DWORD *)v807 = HIDWORD(v825[0]);
            v148 = RtlULongLongAdd(v157, v154, &v807);
            if ( v148 >= 0 )
            {
              v158 = lpMem;
              *(_QWORD *)((char *)lpMem + v836 - 8) = v823;
              memcpy_0((void *)v807, (const void *)v825[1], HIDWORD(v825[0]));
              v802 = v158;
              v147 = v836;
              goto LABEL_229;
            }
          }
          v819 = v8;
          v815 = v10;
          v796 = v41;
          v797 = (SIZE_T)v44;
          v792 = v155;
          LODWORD(dwBytes) = v156;
          v159 = GetProcessHeap();
          HeapFree(v159, 0, lpMem);
          v147 = 0;
        }
LABEL_229:
        v801 = 0;
        lpMem = 0;
        v812 = 0;
        v811 = 0;
        v816 = 0;
        v66 = v148 | 0x10000000;
        LODWORD(v798) = v66;
        if ( v66 < 0 )
        {
          v809 = -1;
          goto LABEL_486;
        }
        v160 = (unsigned __int8 *)v802;
        if ( !v802 )
        {
          v66 = -805306355;
          LODWORD(v798) = -805306355;
          goto LABEL_588;
        }
        v161 = v147;
        v832 = (LPVOID)v147;
        if ( !v147 || (v823 = v147 + 8LL, v162 = NCoreLibrary::AllocMem((NCoreLibrary *)v823, v146), (v830 = v162) == 0) )
        {
          v66 = -805306367;
          LODWORD(v798) = -805306367;
          LODWORD(v805) = -805306345;
          v809 = -1;
          goto LABEL_488;
        }
        v814 = 0;
        v163 = 0;
        LOBYTE(v805) = 0;
        v164 = 0;
        if ( v161 )
        {
          do
            v163 ^= v160[v164++];
          while ( v164 < v161 );
          LOBYTE(v805) = v163;
        }
        v801 = (LPVOID)0xC81ECB17B1B54A58LL;
        v165 = v160;
        pcchLength = (size_t)v160;
        v807 = (size_t)v162;
        v166 = (unsigned __int64)v832;
        v167 = (unsigned __int8)v832 & 7;
        v168 = 0;
        LODWORD(v810) = 0;
        if ( ((unsigned __int8)v832 & 7) != 0 )
        {
          LODWORD(v798) = 0;
          v169 = 0;
          v170 = 0;
          do
          {
            v171 = *v165++;
            LODWORD(Size) = 8 * v169;
            if ( v169 >= 4 )
              v9 |= v171 << (56 - Size);
            else
              v170 |= v171 << (24 - Size);
            ++v169;
          }
          while ( (int)v169 < v167 );
          LODWORD(v810) = v170;
          LODWORD(v798) = v9;
          pcchLength = (size_t)v165;
          v802 = v160;
          Src = v65;
          v797 = (SIZE_T)v44;
          v815 = v10;
          v819 = v8;
          v163 = v805;
          v9 = 0;
          v166 = (unsigned __int64)v832;
          v168 = v810 ^ 0xB17A307A;
          v172 = v798 ^ 0x42F6B18D;
          LODWORD(Size) = v798 ^ 0x42F6B18D;
          v173 = v810 ^ 0xB17A307A;
          v174 = 0;
          if ( ((unsigned __int8)v832 & 7) != 0 )
          {
            v175 = (_BYTE *)v807;
            do
            {
              v824 = (SIZE_T)(v175 + 1);
              if ( v174 >= 4 )
              {
                v172 = __ROR4__(v172, 24);
                v176 = v172;
              }
              else
              {
                v173 = __ROR4__(v173, 24);
                v176 = v173;
              }
              *v175 = v176;
              ++v174;
              v175 = (_BYTE *)v824;
            }
            while ( (int)v174 < v167 );
            v807 = v824;
            v160 = (unsigned __int8 *)v802;
          }
          v809 = -1;
          if ( (unsigned int)v167 <= 4 )
          {
            LODWORD(Size) = 0;
            if ( (unsigned int)v167 < 4 )
              v168 = v168 >> (8 * (4 - v167)) << (8 * (4 - v167));
            v177 = Size;
          }
          else
          {
            v177 = (unsigned int)Size >> (8 * (8 - v167)) << (8 * (8 - v167));
          }
        }
        else
        {
          v809 = -1;
          v177 = -1;
          LODWORD(v798) = 0;
        }
        if ( v166 >> 3 )
        {
          v824 = 0;
          v178 = 19032;
          LODWORD(Size) = 19032;
          LODWORD(v817) = WORD1(v801);
          v179 = WORD2(v801);
          v799 = HIWORD(v801);
          v180 = (unsigned __int8 *)pcchLength;
          v181 = (_BYTE *)v807;
          v182 = v798;
          v183 = v810;
          v184 = v166 >> 3;
          do
          {
            v185 = v180[3] | ((v180[2] | (((*v180 << 8) | v180[1]) << 8)) << 8);
            v186 = v180[7] | ((v180[6] | ((v180[5] | (v180[4] << 8)) << 8)) << 8);
            v187 = v177 ^ v186;
            v180 += 8;
            v188 = v168 ^ v185 ^ HIDWORD(v801) ^ ((v177 ^ v186) - v178);
            v189 = v187 ^ (__ROR4__(v188, 7) + WORD1(v801) * __ROR4__(HIDWORD(v801) ^ v188, 15));
            v190 = v188 ^ (v179 * __ROR4__(v189 - 1313519016, 9) - __ROR4__(v189, 10));
            v191 = v189 ^ (__ROR4__(v190, 27) + HIWORD(v801) * __ROR4__(v179 ^ v190, 28));
            v192 = v190 ^ (HIDWORD(v801) - (v191 ^ 0xB1B54A58));
            v193 = v191 ^ (WORD1(v801) * (v192 - Size) - (v192 >> 6));
            v194 = v192 ^ (Size * (v179 ^ __ROR4__(v193, 15)));
            v195 = v193 ^ (v179 * (HIWORD(v801) + __ROR4__(~v194, 3)));
            v196 = v195
                 ^ (v817 * (v799 ^ v194 ^ (v195 - Size - HIDWORD(v801))))
                 ^ __ROR4__(v194 ^ (v195 - Size - HIDWORD(v801)), 10);
            v197 = v194 ^ (v195 - Size - HIDWORD(v801)) ^ __ROR4__(v196, 3) ^ (v179 * __ROR4__(Size ^ v196, 26));
            v198 = v196 ^ (Size * (__ROR4__(v197, 15) - HIWORD(v801)));
            v199 = v197
                 ^ (Size * (v799 ^ v198))
                 ^ ((v198 ^ (v198 >> 14)) >> 1)
                 ^ (Size * ((8 * (v198 - v179)) | ((unsigned __int64)(v198 - v179) >> 29)));
            v200 = v198 ^ (WORD1(v801) * (v199 - v179) - (v199 >> 13));
            v201 = v199 ^ __ROR4__(v200, 11) ^ (v179 * __ROR4__(-1313519016 - v200, 9));
            v202 = v200 ^ (v201 + 1313519016 - HIWORD(v801));
            v203 = v201 ^ (Size * (v202 ^ WORD1(v801)) - __ROR4__(v202, 7));
            v204 = v202 ^ (WORD1(v801) * __ROR4__(v203 ^ HIWORD(v801), 28) - __ROR4__(v203, 16));
            v205 = v203 ^ (__ROR4__(v204, 4) + v179 * __ROR4__(-1313519016 - v204, 10));
            v206 = v204 ^ __ROR4__(v205, 9) ^ (HIWORD(v801) * __ROR4__(v205 + 1313519016, 4));
            v207 = v205 ^ (Size * __ROR4__(v206 ^ HIDWORD(v801), 24) - __ROR4__(v206, 30));
            v208 = v206 ^ (WORD1(v801) * __ROR4__(HIDWORD(v801) - v207, 11) - __ROR4__(v207, 12));
            v209 = v207 ^ (v208 >> 8) ^ (v179 * (v208 ^ WORD1(v801)));
            v168 = v209 ^ v183;
            v177 = v209 ^ v208 ^ v182 ^ HIDWORD(v801) ^ 0xB1B54A58;
            v181[3] = v209 ^ v183;
            v181[7] = v177;
            v181[2] = __ROR4__(v209 ^ v183, 8);
            v181[6] = __ROR4__(v177, 8);
            v181[1] = __ROR4__(v209 ^ v183, 16);
            v181[5] = __ROR4__(v177, 16);
            *v181 = __ROR4__(v209 ^ v183, 24);
            v181[4] = __ROR4__(v177, 24);
            v183 = v185;
            v182 = v186;
            v181 += 8;
            ++v824;
            v178 = Size;
          }
          while ( v824 < v184 );
          v163 = v805;
          v9 = 0;
          v8 = (unsigned __int16 *)v819;
          v10 = (HMODULE)v815;
          v44 = (void *)v797;
          v160 = (unsigned __int8 *)v802;
          v166 = (unsigned __int64)v832;
        }
        *(_QWORD *)((char *)v830 + v166) = v163;
        v210 = GetProcessHeap();
        v211 = HeapAlloc(v210, 8u, 0x30u);
        v815 = v211;
        if ( v211 )
        {
          v222 = v823;
          *v211 = v823;
          v223 = GetProcessHeap();
          v224 = HeapAlloc(v223, 8u, v222);
          v213 = v796;
          v225 = Src;
          if ( v224 )
          {
            v802 = v160;
            v226 = v815;
            *((_QWORD *)v815 + 1) = v224;
            memcpy_0(v224, v830, (unsigned int)v823);
            v226[4] = 160;
            v227 = GetProcessHeap();
            v228 = HeapAlloc(v227, 8u, 0xA0u);
            v229 = v815;
            if ( v228 )
            {
              *((_QWORD *)v815 + 3) = v228;
              *v228 = xmmword_18013E0E0;
              v228[1] = xmmword_18013E0F0;
              v228[2] = xmmword_18013E100;
              v228[3] = xmmword_18013E110;
              v228[4] = xmmword_18013E120;
              v228[5] = xmmword_18013E130;
              v228[6] = xmmword_18013E140;
              v228[7] = xmmword_18013E150;
              v228[8] = xmmword_18013E160;
              v228[9] = xmmword_18013E170;
              v229[8] = 8;
              v230 = GetProcessHeap();
              v231 = HeapAlloc(v230, 8u, 8u);
              if ( v231 )
              {
                v237 = v815;
                *((_QWORD *)v815 + 5) = v231;
                *v231 = qword_18013E180;
                v212 = 0;
                v797 = (SIZE_T)v44;
                v214 = v237;
                v814 = 0;
LABEL_263:
                v801 = v214;
                v215 = GetProcessHeap();
                HeapFree(v215, 0, v830);
                v216 = v814;
                if ( v814 )
                {
                  v827 = *((_QWORD *)v814 + 1);
                  if ( v827 )
                  {
                    v217 = GetProcessHeap();
                    HeapFree(v217, 0, (LPVOID)v827);
                    v216 = v814;
                    *((_QWORD *)v814 + 1) = 0;
                  }
                  v827 = v216[3];
                  if ( v827 )
                  {
                    v218 = GetProcessHeap();
                    HeapFree(v218, 0, (LPVOID)v827);
                    v216 = v814;
                    *((_QWORD *)v814 + 3) = 0;
                  }
                  v827 = v216[5];
                  if ( v827 )
                  {
                    v219 = GetProcessHeap();
                    HeapFree(v219, 0, (LPVOID)v827);
                    *((_QWORD *)v814 + 5) = 0;
                  }
                  v220 = GetProcessHeap();
                  HeapFree(v220, 0, v814);
                  v221 = (unsigned int *)v801;
                }
                else
                {
                  v221 = (unsigned int *)v801;
                }
                v66 = v212 | 0x10000000;
                LODWORD(v798) = v66;
                if ( v66 < 0 )
                {
                  v797 = (SIZE_T)v44;
                  v796 = v213;
                  goto LABEL_486;
                }
                LODWORD(Size) = 0;
                LODWORD(v798) = 4;
                v239 = RtlUIntAdd(4, *v221, &v798);
                if ( v239 < 0
                  || (v239 = RtlUIntAdd((unsigned int)v798, v238, &v798), v239 < 0)
                  || (v823 = v240 + 16,
                      v239 = RtlUIntAdd((unsigned int)v798, *(unsigned int *)(v240 + 16), &v798),
                      v239 < 0)
                  || (v239 = RtlUIntAdd((unsigned int)v798, v241, &v798), v239 < 0)
                  || (pcchLength = v242 + 32,
                      v239 = RtlUIntAdd((unsigned int)v798, *(unsigned int *)(v242 + 32), &v798),
                      v239 < 0) )
                {
                  v797 = (SIZE_T)v44;
                  v796 = v213;
LABEL_305:
                  v66 = v239 | 0x10000000;
                  LODWORD(v798) = v66;
                  if ( v66 < 0 )
                    goto LABEL_486;
                  v841 = 8;
                  v258 = RtlUIntAdd(8, (unsigned int)dwBytes, &v841);
                  v66 = v258 | 0x10000000;
                  LODWORD(v798) = v258 | 0x10000000;
                  if ( v258 < 0 )
                    goto LABEL_486;
                  v259 = (v841 + 7) & 0xFFFFFFF8;
                  if ( (unsigned int)v259 < v841 )
                  {
                    v66 = -1073741675;
LABEL_348:
                    LODWORD(v798) = v66;
                    goto LABEL_486;
                  }
                  v843 = (v841 + 7) & 0xFFFFFFF8;
                  v66 = RtlUIntAdd(v259, 8, &v843);
                  LODWORD(v798) = v66;
                  if ( v66 < 0 )
                    goto LABEL_486;
                  v819 = v8;
                  v815 = v10;
                  v796 = v213;
                  v797 = (SIZE_T)v44;
                  Src = v260;
                  v792 = v262;
                  LODWORD(v810) = 0;
                  v263 = v825[1];
                  if ( !v825[1] )
                    goto LABEL_319;
                  v792 = v262;
                  Src = v260;
                  v797 = (SIZE_T)v44;
                  v796 = v213;
                  v815 = v10;
                  v819 = v8;
                  if ( LODWORD(v825[0]) <= 1 )
                    goto LABEL_319;
                  v807 = v825[1];
                  v799 = 0;
                  while ( 1 )
                  {
                    v66 = RtlULongLongAdd(v263, v261, &v807);
                    LODWORD(v798) = v66;
                    if ( v66 < 0 )
                      goto LABEL_486;
                    v66 = RtlULongLongAdd(v807, v264, &v807);
                    LODWORD(v798) = v66;
                    if ( v66 < 0 )
                      goto LABEL_486;
                    if ( ++v799 )
                      break;
                    v263 = v807;
                  }
                  v265 = *(_DWORD *)v807;
                  v66 = RtlULongLongAdd(v807, v261, &v807);
                  LODWORD(v798) = v66;
                  if ( v66 < 0 )
                    goto LABEL_486;
                  v267 = v825[1];
                  if ( !v825[1] || LODWORD(v825[0]) <= 2 )
                  {
LABEL_319:
                    v66 = -1073741811;
                    LODWORD(v798) = -1073741811;
                    goto LABEL_486;
                  }
                  v807 = v825[1];
                  do
                  {
                    v66 = RtlULongLongAdd(v267, v266, &v807);
                    LODWORD(v798) = v66;
                    if ( v66 < 0 )
                      goto LABEL_486;
                    v66 = RtlULongLongAdd(v807, v271, &v807);
                    LODWORD(v798) = v66;
                    if ( v66 < 0 )
                      goto LABEL_486;
                    v267 = v807;
                  }
                  while ( (unsigned int)(v272 + 1) < 2 );
                  v66 = RtlULongLongAdd(v807, v266, &v807);
                  LODWORD(v798) = v66;
                  if ( v66 < 0 )
                    goto LABEL_486;
                  LODWORD(v810) = 0;
                  LODWORD(dwBytes) = v273;
                  v66 = RtlUIntAdd(v273, v843, &dwBytes);
                  LODWORD(v798) = v66;
                  if ( v66 < 0 )
                    goto LABEL_486;
                  v66 = RtlUIntAdd((unsigned int)dwBytes, v274, &dwBytes);
                  LODWORD(v798) = v66;
                  if ( v66 < 0 )
                    goto LABEL_486;
                  v66 = RtlUIntAdd((unsigned int)dwBytes, v265, &dwBytes);
                  LODWORD(v798) = v66;
                  if ( v66 < 0 )
                    goto LABEL_486;
                  v66 = RtlUIntAdd((unsigned int)dwBytes, v275, &dwBytes);
                  LODWORD(v798) = v66;
                  if ( v66 < 0 )
                    goto LABEL_486;
                  v66 = RtlUIntAdd((unsigned int)dwBytes, v276, &dwBytes);
                  LODWORD(v798) = v66;
                  if ( v66 < 0 )
                    goto LABEL_486;
                  LODWORD(v810) = dwBytes;
                  if ( (unsigned int)dwBytes > 0x400000 )
                  {
                    v66 = -2147418113;
                    goto LABEL_348;
                  }
                  v268 = dwBytes;
                  v269 = GetProcessHeap();
                  v270 = HeapAlloc(v269, 8u, v268);
                  v812 = v270;
                  if ( !v270 )
                  {
                    LODWORD(v805) = -805306345;
                    v66 = -805306345;
                    LODWORD(v798) = -805306345;
                    v812 = 0;
                    goto LABEL_487;
                  }
                  v855 = 0;
                  v856 = 0;
                  phModule = 0;
                  if ( !lpMem )
                  {
                    v66 = -2147024809;
LABEL_353:
                    LODWORD(v798) = v66;
                    goto LABEL_354;
                  }
                  *(_QWORD *)&v855 = lpMem;
                  LODWORD(v856) = Size;
                  *((_QWORD *)&v855 + 1) = v270;
                  *(_QWORD *)((char *)&v856 + 4) = (unsigned int)v810;
                  if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                    && (v278 = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                  {
                    v279 = ((__int64 (__fastcall *)(__int64, __int128 *))v278)(134, &v855);
                    v66 = v279 | 0x10000000;
                    LODWORD(v798) = v279 | 0x10000000;
                    if ( v279 >= 0 )
                    {
                      v280 = DWORD1(v856);
                      goto LABEL_351;
                    }
                  }
                  else
                  {
                    v277 = GetLastError();
                    LODWORD(v798) = v277;
                    v66 = v277;
                    if ( v277 > 0 )
                    {
                      v66 = (unsigned __int16)v277 | 0x80070000;
                      LODWORD(v798) = v66;
                    }
                    if ( v66 >= 0 )
                    {
                      v66 = -2147467259;
                      LODWORD(v798) = -2147467259;
                      goto LABEL_342;
                    }
                  }
                  if ( v66 == -805306333 )
                  {
                    v66 = -2147024774;
                    goto LABEL_348;
                  }
                  if ( v66 >= 0 )
                  {
                    v280 = v810;
LABEL_351:
                    LODWORD(dwBytes) = 0;
                    v270 = v812;
                    v810 = (SIZE_T)v812;
                    if ( v280 < 4 )
                    {
LABEL_352:
                      v66 = -805306306;
                      goto LABEL_353;
                    }
                    v281 = *(unsigned int *)v812;
                    LODWORD(v817) = *(_DWORD *)v812;
                    v284 = RtlULongLongAdd(v812, 4, &v810);
                    if ( v284 < 0 )
                      goto LABEL_406;
                    v284 = RtlUIntAdd(0, v283, &dwBytes);
                    if ( v284 < 0 )
                      goto LABEL_406;
                    if ( v285 - (int)dwBytes < (unsigned int)v281 )
                      goto LABEL_352;
                    v823 = v810;
                    v827 = v281;
                    v284 = RtlULongLongAdd(v810, (unsigned int)v281, &v810);
                    if ( v284 < 0 )
                      goto LABEL_406;
                    v284 = RtlUIntAdd((unsigned int)dwBytes, (unsigned int)v281, &dwBytes);
                    if ( v284 < 0 )
                      goto LABEL_406;
                    if ( v287 - (int)dwBytes < (unsigned int)v286 )
                      goto LABEL_352;
                    v288 = *(unsigned int *)v810;
                    v799 = *(_DWORD *)v810;
                    v284 = RtlULongLongAdd(v810, v286, &v810);
                    if ( v284 < 0 )
                      goto LABEL_406;
                    v284 = RtlUIntAdd((unsigned int)dwBytes, v289, &dwBytes);
                    if ( v284 < 0 )
                      goto LABEL_406;
                    if ( v290 - (int)dwBytes < (unsigned int)v288 )
                      goto LABEL_352;
                    v824 = v810;
                    pcchLength = v288;
                    v284 = RtlULongLongAdd(v810, (unsigned int)v288, &v810);
                    if ( v284 < 0 )
                      goto LABEL_406;
                    v284 = RtlUIntAdd((unsigned int)dwBytes, (unsigned int)v288, &dwBytes);
                    if ( v284 < 0 )
                      goto LABEL_406;
                    if ( v292 - (int)dwBytes < (unsigned int)v291 )
                      goto LABEL_352;
                    v293 = *(_DWORD *)v810;
                    LODWORD(Size) = *(_DWORD *)v810;
                    v284 = RtlULongLongAdd(v810, v291, &v810);
                    if ( v284 < 0 )
                      goto LABEL_406;
                    v284 = RtlUIntAdd((unsigned int)dwBytes, v294, &dwBytes);
                    if ( v284 < 0 )
                      goto LABEL_406;
                    if ( v295 - (int)dwBytes < v293 )
                      goto LABEL_352;
                    v284 = RtlUIntAdd((unsigned int)dwBytes, v293, &dwBytes);
                    if ( v284 < 0 )
                    {
LABEL_406:
                      v812 = v270;
                      goto LABEL_407;
                    }
                    if ( v296 != (_DWORD)dwBytes )
                      goto LABEL_352;
                    v297 = (unsigned int)v817;
                    if ( v293 + (_DWORD)v817 + v799 + 12LL != v296 )
                      goto LABEL_352;
                    v298 = GetProcessHeap();
                    v299 = HeapAlloc(v298, 8u, 0x30u);
                    v811 = v299;
                    if ( !v299 )
                    {
                      v811 = 0;
                      goto LABEL_291;
                    }
                    v819 = v8;
                    v815 = v10;
                    v797 = (SIZE_T)v44;
                    v830 = 0;
                    if ( v823 )
                    {
                      *v299 = v297;
                      v300 = GetProcessHeap();
                      v301 = HeapAlloc(v300, 8u, v297);
                      if ( !v301 )
                      {
LABEL_386:
                        v284 = -1073741801;
                        v308 = v811;
                        v827 = *((_QWORD *)v811 + 1);
                        if ( v827 )
                        {
                          v309 = GetProcessHeap();
                          HeapFree(v309, 0, (LPVOID)v827);
                          v308[1] = 0;
                        }
                        v827 = v308[3];
                        if ( v827 )
                        {
                          v310 = GetProcessHeap();
                          HeapFree(v310, 0, (LPVOID)v827);
                          v308[3] = 0;
                        }
                        v827 = v308[5];
                        if ( v827 )
                        {
                          v311 = GetProcessHeap();
                          HeapFree(v311, 0, (LPVOID)v827);
                          v308[5] = 0;
                        }
                        v312 = GetProcessHeap();
                        HeapFree(v312, 0, v308);
                        v299 = 0;
                        goto LABEL_396;
                      }
                      *((_QWORD *)v811 + 1) = v301;
                      v284 = 0;
                      memcpy_0(v301, (const void *)v823, v827);
                      v299 = v811;
                    }
                    else
                    {
                      *v299 = 0;
                      *((_QWORD *)v299 + 1) = 0;
                      v284 = 0;
                    }
                    if ( v824 )
                    {
                      v299[4] = v799;
                      v302 = GetProcessHeap();
                      v303 = HeapAlloc(v302, 8u, pcchLength);
                      if ( !v303 )
                      {
LABEL_385:
                        v819 = v8;
                        v815 = v10;
                        v797 = (SIZE_T)v44;
                        goto LABEL_386;
                      }
                      *((_QWORD *)v811 + 3) = v303;
                      v284 = 0;
                      memcpy_0(v303, (const void *)v824, pcchLength);
                      v299 = v811;
                    }
                    else
                    {
                      v299[4] = 0;
                      *((_QWORD *)v299 + 3) = 0;
                    }
                    if ( v810 )
                    {
                      v304 = (unsigned int)Size;
                      v299[8] = Size;
                      v305 = v304;
                      v827 = v304;
                      v306 = GetProcessHeap();
                      v307 = HeapAlloc(v306, 8u, v305);
                      if ( !v307 )
                        goto LABEL_385;
                      *((_QWORD *)v811 + 5) = v307;
                      v284 = 0;
                      memcpy_0(v307, (const void *)v810, v827);
                      v299 = v811;
                    }
                    else
                    {
                      v299[8] = 0;
                      *((_QWORD *)v299 + 5) = 0;
                    }
                    v830 = v299;
                    v797 = (SIZE_T)v44;
                    v815 = v10;
                    v819 = v8;
LABEL_396:
                    if ( v284 >= 0 )
                    {
                      v313 = v299;
                      v811 = v299;
                      goto LABEL_408;
                    }
                    v313 = 0;
                    v811 = 0;
                    v314 = v830;
                    if ( !v830 )
                    {
LABEL_408:
                      v66 = v284 | 0x10000000;
                      LODWORD(v798) = v66;
                      if ( v66 >= 0 )
                      {
                        if ( !v313 || (pcchLength = *((_QWORD *)v313 + 1)) == 0 || !*v313 )
                        {
                          v66 = -805306355;
LABEL_482:
                          LODWORD(v798) = v66;
                          LODWORD(v805) = -805306345;
                          goto LABEL_487;
                        }
                        v319 = *v313 - 8LL;
                        v807 = v319;
                        v320 = NCoreLibrary::AllocMem((NCoreLibrary *)v319, v282);
                        v816 = v320;
                        if ( !v320 )
                        {
LABEL_440:
                          v816 = 0;
                          v66 = -805306367;
                          goto LABEL_482;
                        }
                        v321 = 0;
                        LOBYTE(v805) = 0;
                        Size = 0x7F1137FAB69605ELL;
                        v830 = (LPVOID)pcchLength;
                        v832 = v320;
                        v823 = v319 & 7;
                        v322 = 0;
                        v323 = 0;
                        LODWORD(v798) = 0;
                        if ( (v319 & 7) != 0 )
                        {
                          LODWORD(v810) = 0;
                          v324 = 0;
                          v325 = (unsigned __int8 *)v830;
                          v326 = 0;
                          do
                          {
                            LODWORD(dwBytes) = *v325++;
                            v799 = 8 * v324;
                            if ( (unsigned int)v324 >= 4 )
                            {
                              LODWORD(dwBytes) = (_DWORD)dwBytes << (56 - v799);
                              v326 |= dwBytes;
                            }
                            else
                            {
                              LODWORD(dwBytes) = (_DWORD)dwBytes << (24 - v799);
                              v9 |= dwBytes;
                            }
                            ++v324;
                          }
                          while ( v324 < (int)v823 );
                          LODWORD(v798) = v9;
                          LODWORD(v810) = v326;
                          v830 = v325;
                          v797 = (SIZE_T)v44;
                          v815 = v10;
                          v819 = v8;
                          v321 = v805;
                          v9 = 0;
                          v319 = v807;
                          v327 = v823;
                          v323 = v798 ^ 0x92F65A5;
                          v328 = v798 ^ 0x92F65A5;
                          v329 = v326 ^ 0x699A899C;
                          v330 = 0;
                          if ( (_DWORD)v823 )
                          {
                            v331 = v832;
                            do
                            {
                              v827 = (size_t)(v331 + 1);
                              if ( v330 >= 4 )
                              {
                                v329 = __ROR4__(v329, 24);
                                v332 = v329;
                              }
                              else
                              {
                                v328 = __ROR4__(v328, 24);
                                v332 = v328;
                              }
                              *v331 = v332;
                              ++v330;
                              v331 = (_BYTE *)v827;
                            }
                            while ( (int)v330 < (int)v327 );
                            v832 = (LPVOID)v827;
                            v321 = v805;
                            v319 = v807;
                          }
                          if ( v327 <= 4 )
                          {
                            v322 = 0;
                            if ( v327 < 4 )
                              v323 = v323 >> (8 * (4 - v327)) << (8 * (4 - v327));
                          }
                          else
                          {
                            v322 = (v326 ^ 0x699A899Cu) >> (8 * (8 - v327)) << (8 * (8 - v327));
                          }
                        }
                        else
                        {
                          LODWORD(v810) = -1;
                        }
                        if ( v319 >> 3 )
                        {
                          v823 = 0;
                          v333 = HIDWORD(Size);
                          v334 = WORD2(Size);
                          v799 = WORD2(Size);
                          LODWORD(dwBytes) = 24670;
                          v335 = (unsigned __int8 *)v830;
                          v336 = v832;
                          v337 = v319 >> 3;
                          v338 = v810;
                          v339 = v798;
                          do
                          {
                            v340 = v335[3] | ((v335[2] | (((*v335 << 8) | v335[1]) << 8)) << 8);
                            v341 = v335[7] | ((v335[6] | ((v335[5] | (v335[4] << 8)) << 8)) << 8);
                            v335 += 8;
                            v342 = v323 ^ v340;
                            v343 = v333 ^ v323 ^ v340 ^ v322 ^ v341 ^ 0xAB69605E;
                            v344 = v342 ^ (__ROR4__(v343, 22) + v334 * __ROR4__(v343 + 1419157410, 27));
                            v345 = v343 ^ (WORD1(Size) * __ROR4__(v333 + v344, 9) - __ROR4__(v344, 30));
                            v346 = v344 ^ (dwBytes * (v345 - v334) - (v345 >> 13));
                            v347 = v345 ^ (HIWORD(Size) * __ROR4__(v346 ^ WORD1(Size), 26) - __ROR4__(v346, 30));
                            v348 = v346 ^ (v333 - (v347 ^ 0xAB69605E));
                            v349 = v347 ^ (WORD1(Size) * (v334 ^ v348)) ^ __ROR4__(v348, 6);
                            v350 = v348 ^ (__ROR4__(v349, 30) + dwBytes * __ROR4__(v349 + v333, 15));
                            v351 = v349 ^ (HIWORD(Size) * __ROR4__(v350 + 1419157410, 14) - __ROR4__(v350, 24));
                            v352 = v350 ^ __ROR4__(v351, 10) ^ (v799 * __ROR4__(v351 ^ 0xAB69605E, 12));
                            v353 = v352
                                 ^ (HIWORD(Size)
                                  * (dwBytes
                                   + __ROR4__(~(v351 ^ (v352 >> 10) ^ (WORD1(Size) * (v352 ^ HIWORD(Size)))), 5)));
                            v354 = v351
                                 ^ (v352 >> 10)
                                 ^ (WORD1(Size) * (v352 ^ HIWORD(Size)))
                                 ^ (v353 - HIWORD(Size))
                                 ^ 0xAB69605E;
                            v334 = v799;
                            v355 = v353 ^ ((v354 >> 2) + v799 * __ROR4__(HIWORD(Size) ^ v354, 30));
                            v333 = HIDWORD(Size);
                            v356 = v354 ^ (__ROR4__(v355, 25) + WORD1(Size) * __ROR4__(v355 - HIDWORD(Size), 6));
                            v357 = v355 ^ (dwBytes * (v799 ^ v356) + __ROR4__(v356, 9));
                            v358 = v356 ^ (__ROR4__(v357, 25) + HIWORD(Size) * __ROR4__(v357 ^ WORD1(Size), 27));
                            v359 = v357 ^ v358 ^ HIDWORD(Size) ^ 0xAB69605E;
                            v360 = v358 ^ (v799 * (__ROR4__(v359, 3) - WORD1(Size)));
                            v361 = v359 ^ (dwBytes * __ROR4__(v360 - HIDWORD(Size), 1) - __ROR4__(v360, 6));
                            v362 = v360 ^ (__ROR4__(v361, 18) + HIWORD(Size) * __ROR4__(v361 - 1419157410, 29));
                            v363 = v361 ^ (v799 * __ROR4__(v362 - 1419157410, 17) - __ROR4__(v362, 14));
                            v364 = v362 ^ (v363 >> 3) ^ (WORD1(Size) * (dwBytes ^ v363));
                            v323 = v363 ^ v339 ^ __ROR4__(v364, 30) ^ (dwBytes * __ROR4__(HIDWORD(Size) ^ v364, 28));
                            v322 = v364 ^ v338;
                            v336[3] = v323;
                            v336[7] = v364 ^ v338;
                            v336[2] = __ROR4__(v323, 8);
                            v336[6] = __ROR4__(v364 ^ v338, 8);
                            v336[1] = __ROR4__(v323, 16);
                            v336[5] = __ROR4__(v364 ^ v338, 16);
                            *v336 = __ROR4__(v323, 24);
                            v336[4] = __ROR4__(v364 ^ v338, 24);
                            v339 = v340;
                            v338 = v341;
                            v336 += 8;
                            ++v823;
                          }
                          while ( v823 < v337 );
                          v321 = v805;
                          v9 = 0;
                          v8 = (unsigned __int16 *)v819;
                          v10 = (HMODULE)v815;
                          v44 = (void *)v797;
                          v319 = v807;
                        }
                        for ( i = 0; i < v319; ++i )
                          v321 ^= *((_BYTE *)v816 + i);
                        if ( v321 != *(_QWORD *)(v319 + pcchLength) )
                        {
                          MemoryFree(v816);
                          goto LABEL_440;
                        }
                        v797 = (SIZE_T)v44;
                        LODWORD(dwBytes) = 0;
                        v814 = v816;
                        if ( (unsigned int)v319 < 4 )
                        {
LABEL_442:
                          v366 = -1073741762;
LABEL_481:
                          v66 = v366 | 0x10000000;
                          goto LABEL_482;
                        }
                        v366 = RtlULongLongAdd(v816, 4, &v814);
                        if ( v366 < 0 )
                          goto LABEL_479;
                        v366 = RtlUIntAdd(0, v369, &dwBytes);
                        if ( v366 < 0 )
                          goto LABEL_479;
                        if ( (int)v807 - (int)dwBytes < (unsigned int)v370 )
                        {
LABEL_446:
                          v366 = -1073741762;
                          goto LABEL_479;
                        }
                        LODWORD(v810) = *(_DWORD *)v814;
                        v366 = RtlULongLongAdd(v814, v370, &v814);
                        if ( v366 < 0 )
                          goto LABEL_479;
                        v366 = RtlUIntAdd((unsigned int)dwBytes, v371, &dwBytes);
                        if ( v366 < 0 )
                          goto LABEL_479;
                        if ( (int)v807 - (int)dwBytes < (unsigned int)v810 )
                          goto LABEL_446;
                        v366 = RtlUIntAdd((unsigned int)dwBytes, (unsigned int)v810, &dwBytes);
                        if ( v366 < 0 )
                        {
LABEL_479:
                          v796 = v367;
                          Src = v368;
LABEL_480:
                          v797 = (SIZE_T)v44;
                          goto LABEL_481;
                        }
                        if ( (char *)v816 + (unsigned int)v807 < (char *)v814 + (unsigned int)v810
                          || (unsigned int)v807 + (_BYTE *)v816 - (_BYTE *)v814 - (unsigned __int64)(unsigned int)v810 >= 8 )
                        {
                          goto LABEL_446;
                        }
                        LODWORD(v817) = *(_DWORD *)v816;
                        v807 = 0;
                        v823 = 0;
                        pcchLength = 0;
                        LODWORD(Size) = 0;
                        if ( v814 )
                        {
                          v366 = RtlULongLongAdd(v814, (unsigned int)v810, &v807);
                          Src = v374;
                          v797 = (SIZE_T)v44;
                          v796 = v375;
                          if ( v366 < 0 )
                          {
LABEL_467:
                            v382 = v806;
LABEL_468:
                            if ( v366 < 0 || (_DWORD)v817 == v382 )
                              goto LABEL_481;
                            goto LABEL_442;
                          }
                          v805 = v372;
                          v376 = v807;
                          if ( v372 < v807 )
                          {
                            while ( 1 )
                            {
                              v366 = RtlULongLongAdd(v372, v373, &v823);
                              if ( v366 < 0 )
                                goto LABEL_467;
                              if ( v823 > v807 )
                                goto LABEL_466;
                              v799 = 0;
                              v366 = RtlUIntAdd(v378, *v377, &v799);
                              if ( v366 < 0 )
                                goto LABEL_481;
                              v850 = v8;
                              v827 = (size_t)v10;
                              v824 = (SIZE_T)v44;
                              v832 = v792;
                              v379 = v802;
                              v830 = v802;
                              v798 = (SIZE_T)v801;
                              dwBytes = (SIZE_T)v812;
                              v819 = v811;
                              v815 = v816;
                              v366 = RtlULongLongAdd(v805, v799, &pcchLength);
                              v816 = v815;
                              v811 = v819;
                              v812 = (LPVOID)dwBytes;
                              v801 = (LPVOID)v798;
                              v802 = v379;
                              Src = v381;
                              v797 = (SIZE_T)v44;
                              v796 = v380;
                              v10 = (HMODULE)v827;
                              v8 = v850;
                              if ( v366 < 0 )
                                goto LABEL_467;
                              v372 = pcchLength;
                              v805 = pcchLength;
                              Src = v381;
                              v796 = v380;
                              if ( pcchLength > v807 )
                              {
                                v366 = -1073741811;
                                v816 = v815;
                                v811 = v819;
                                v812 = (LPVOID)dwBytes;
                                v801 = (LPVOID)v798;
                                v802 = v830;
                                v792 = v832;
                                goto LABEL_480;
                              }
                              LODWORD(Size) = Size + 1;
                              v816 = v815;
                              v811 = v819;
                              v812 = (LPVOID)dwBytes;
                              v801 = (LPVOID)v798;
                              v802 = v830;
                              v792 = v832;
                              v44 = (void *)v824;
                              v797 = v824;
                              if ( pcchLength >= v807 )
                              {
                                v816 = v815;
                                v811 = v819;
                                v812 = (LPVOID)dwBytes;
                                v801 = (LPVOID)v798;
                                v802 = v830;
                                v792 = v832;
                                Src = v381;
                                v797 = v824;
                                v796 = v380;
                                v376 = v807;
                                goto LABEL_465;
                              }
                            }
                          }
                          v372 = v805;
LABEL_465:
                          if ( v372 != v376 )
                          {
LABEL_466:
                            v366 = -1073741811;
                            goto LABEL_481;
                          }
                        }
                        else
                        {
                          v366 = 0;
                          Src = v368;
                          v797 = (SIZE_T)v44;
                          v796 = v367;
                        }
                        v383 = 0;
                        v823 = 0;
                        v384 = v810;
                        if ( (_DWORD)v810 )
                        {
                          v385 = GetProcessHeap();
                          v383 = HeapAlloc(v385, 8u, (unsigned int)v810);
                          v823 = (SIZE_T)v383;
                          if ( !v383 )
                          {
                            v366 = -1073741801;
                            goto LABEL_481;
                          }
                          v366 = 0;
                          v384 = v810;
                        }
                        if ( v814 )
                          memcpy_0(v383, v814, v384);
                        v808 = (LPVOID)v823;
                        v382 = Size;
                        LODWORD(v806) = Size;
                        goto LABEL_468;
                      }
LABEL_486:
                      LODWORD(v805) = -805306345;
LABEL_487:
                      if ( !v802 )
                      {
LABEL_489:
                        v387 = v801;
                        if ( v801 )
                        {
                          v821 = *((_QWORD *)v801 + 1);
                          if ( v821 )
                          {
                            v388 = GetProcessHeap();
                            HeapFree(v388, 0, (LPVOID)v821);
                            v387 = v801;
                            *((_QWORD *)v801 + 1) = 0;
                          }
                          v821 = v387[3];
                          if ( v821 )
                          {
                            v389 = GetProcessHeap();
                            HeapFree(v389, 0, (LPVOID)v821);
                            v387 = v801;
                            *((_QWORD *)v801 + 3) = 0;
                          }
                          v821 = v387[5];
                          if ( v821 )
                          {
                            v390 = GetProcessHeap();
                            HeapFree(v390, 0, (LPVOID)v821);
                            *((_QWORD *)v801 + 5) = 0;
                          }
                          v391 = GetProcessHeap();
                          HeapFree(v391, 0, v801);
                        }
                        if ( lpMem )
                        {
                          v392 = GetProcessHeap();
                          HeapFree(v392, 0, lpMem);
                        }
                        if ( v812 )
                        {
                          v393 = GetProcessHeap();
                          HeapFree(v393, 0, v812);
                        }
                        v394 = v811;
                        if ( v811 )
                        {
                          v821 = *((_QWORD *)v811 + 1);
                          if ( v821 )
                          {
                            v395 = GetProcessHeap();
                            HeapFree(v395, 0, (LPVOID)v821);
                            v394 = v811;
                            *((_QWORD *)v811 + 1) = 0;
                          }
                          v821 = v394[3];
                          if ( v821 )
                          {
                            v396 = GetProcessHeap();
                            HeapFree(v396, 0, (LPVOID)v821);
                            v394 = v811;
                            *((_QWORD *)v811 + 3) = 0;
                          }
                          v821 = v394[5];
                          if ( v821 )
                          {
                            v397 = GetProcessHeap();
                            HeapFree(v397, 0, (LPVOID)v821);
                            *((_QWORD *)v811 + 5) = 0;
                          }
                          v398 = GetProcessHeap();
                          HeapFree(v398, 0, v811);
                        }
                        if ( v816 )
                        {
                          v399 = GetProcessHeap();
                          HeapFree(v399, 0, v816);
                        }
LABEL_511:
                        if ( v66 < 0 )
                          goto LABEL_589;
                        if ( !(_DWORD)v806 )
                          goto LABEL_513;
                        if ( !v808 )
                        {
                          v66 = -1073741811;
LABEL_566:
                          LODWORD(v798) = v66;
                          goto LABEL_589;
                        }
                        v823 = (SIZE_T)v808;
                        v66 = RtlULongLongAdd(v808, 4, &v823);
                        LODWORD(v798) = v66;
                        v797 = (SIZE_T)v44;
                        if ( v66 < 0 )
                        {
                          v808 = v400;
                          goto LABEL_589;
                        }
                        v402 = (int *)v823;
                        if ( !*v400 )
                          v402 = 0;
                        if ( *v400 != (_DWORD)v401 )
                        {
                          v66 = -1073741789;
                          LODWORD(v798) = -1073741789;
                          goto LABEL_589;
                        }
                        v808 = v400;
                        v66 = *v402;
                        LODWORD(v798) = v66;
                        if ( v66 == -805306333 )
                        {
                          LODWORD(v813) = -2147024774;
                        }
                        else
                        {
                          LODWORD(v813) = v66;
                          if ( v66 != -2147024774 && v66 < 0 )
                            goto LABEL_589;
                        }
                        v797 = (SIZE_T)v44;
                        v808 = v400;
                        if ( (_DWORD)v806 == 6 )
                        {
                          v403 = v400;
                          v807 = (size_t)v400;
                          v799 = 0;
                          while ( 1 )
                          {
                            LODWORD(v817) = *v403;
                            v66 = RtlULongLongAdd(v403, v401, &v807);
                            LODWORD(v798) = v66;
                            if ( v66 < 0 )
                              goto LABEL_589;
                            v66 = RtlULongLongAdd(v807, (unsigned int)v817, &v807);
                            LODWORD(v798) = v66;
                            if ( v66 < 0 )
                              goto LABEL_589;
                            if ( ++v799 )
                              break;
                            v403 = (_DWORD *)v807;
                          }
                          LODWORD(v817) = *(_DWORD *)v807;
                          v66 = RtlULongLongAdd(v807, v401, &v807);
                          LODWORD(v798) = v66;
                          if ( v66 < 0 )
                            goto LABEL_589;
                          v407 = (SIZE_T *)v807;
                          if ( !(_DWORD)v817 )
                            v407 = 0;
                          if ( (_DWORD)v817 != 8 )
                            goto LABEL_565;
                          Src = v405;
                          v797 = (SIZE_T)v44;
                          v796 = v404;
                          if ( !v808 )
                          {
LABEL_547:
                            v66 = -1073741811;
                            LODWORD(v798) = -1073741811;
                            goto LABEL_589;
                          }
                          v408 = v808;
                          v807 = (size_t)v808;
                          v799 = 0;
                          v821 = *v407;
                          while ( 1 )
                          {
                            LODWORD(v817) = *v408;
                            v66 = RtlULongLongAdd(v408, v406, &v807);
                            LODWORD(v798) = v66;
                            if ( v66 < 0 )
                              goto LABEL_589;
                            v66 = RtlULongLongAdd(v807, (unsigned int)v817, &v807);
                            LODWORD(v798) = v66;
                            if ( v66 < 0 )
                              goto LABEL_589;
                            if ( ++v799 >= 2 )
                              break;
                            v408 = (_DWORD *)v807;
                          }
                          LODWORD(v817) = *(_DWORD *)v807;
                          v66 = RtlULongLongAdd(v807, v406, &v807);
                          LODWORD(v798) = v66;
                          if ( v66 < 0 )
                            goto LABEL_589;
                          v412 = (_DWORD *)v807;
                          if ( !(_DWORD)v817 )
                            v412 = 0;
                          if ( (_DWORD)v817 != (_DWORD)v411 )
                            goto LABEL_565;
                          Src = v410;
                          v797 = (SIZE_T)v44;
                          v796 = v409;
                          if ( !v808 )
                            goto LABEL_547;
                          v413 = v808;
                          v807 = (size_t)v808;
                          v799 = 0;
                          LODWORD(v810) = *v412;
                          while ( 1 )
                          {
                            LODWORD(v817) = *v413;
                            v66 = RtlULongLongAdd(v413, v411, &v807);
                            LODWORD(v798) = v66;
                            if ( v66 < 0 )
                              goto LABEL_589;
                            v66 = RtlULongLongAdd(v807, (unsigned int)v817, &v807);
                            LODWORD(v798) = v66;
                            if ( v66 < 0 )
                              goto LABEL_589;
                            if ( ++v799 >= 3 )
                              break;
                            v413 = (_DWORD *)v807;
                          }
                          LODWORD(Size) = *(_DWORD *)v807;
                          v66 = RtlULongLongAdd(v807, v411, &v807);
                          LODWORD(v798) = v66;
                          if ( v66 < 0 )
                            goto LABEL_589;
                          v823 = (_DWORD)Size ? v807 : 0LL;
                          v415 = v808;
                          v807 = (size_t)v808;
                          v799 = 0;
                          do
                          {
                            LODWORD(v817) = *v415;
                            v66 = RtlULongLongAdd(v415, v414, &v807);
                            LODWORD(v798) = v66;
                            if ( v66 < 0 )
                              goto LABEL_589;
                            v66 = RtlULongLongAdd(v807, (unsigned int)v817, &v807);
                            LODWORD(v798) = v66;
                            if ( v66 < 0 )
                              goto LABEL_589;
                            ++v799;
                            v415 = (_DWORD *)v807;
                          }
                          while ( v799 < (unsigned int)v414 );
                          LODWORD(v817) = *(_DWORD *)v807;
                          v66 = RtlULongLongAdd(v807, v414, &v807);
                          LODWORD(v798) = v66;
                          if ( v66 < 0 )
                            goto LABEL_589;
                          v419 = (_DWORD *)v807;
                          if ( !(_DWORD)v817 )
                            v419 = 0;
                          if ( (_DWORD)v817 != (_DWORD)v418 )
                          {
LABEL_565:
                            v66 = -1073741789;
                            goto LABEL_566;
                          }
                          Src = v417;
                          v797 = (SIZE_T)v44;
                          v796 = v416;
                          if ( !v808 )
                          {
                            v66 = -1073741811;
                            LODWORD(v798) = -1073741811;
                            goto LABEL_589;
                          }
                          v420 = (size_t)v808;
                          v807 = (size_t)v808;
                          v799 = 0;
                          LODWORD(v817) = *v419;
                          while ( 1 )
                          {
                            v66 = RtlULongLongAdd(v420, v418, &v807);
                            LODWORD(v798) = v66;
                            if ( v66 < 0 )
                              goto LABEL_589;
                            v66 = RtlULongLongAdd(v807, v421, &v807);
                            LODWORD(v798) = v66;
                            if ( v66 < 0 )
                              goto LABEL_589;
                            if ( ++v799 >= 5 )
                              break;
                            v420 = v807;
                          }
                          v96 = RtlULongLongAdd(v807, v418, &v807);
                          v66 = v96;
                          LODWORD(v798) = v96;
                          if ( v96 < 0 )
                          {
LABEL_125:
                            LODWORD(v798) = v96;
                            goto LABEL_589;
                          }
                          v424 = (int *)v807;
                          if ( !v422 )
                            v424 = 0;
                          if ( v422 != v423 )
                          {
                            v66 = -1073741789;
                            goto LABEL_514;
                          }
                          if ( v828 == v821 )
                          {
                            v844 = *v424;
                            v846 = v810;
                            if ( (unsigned int)v817 > v423 || (unsigned int)Size > v423 )
                            {
                              v66 = -2147024774;
                              goto LABEL_514;
                            }
                            memcpy_0(hLibModule, (const void *)v823, (unsigned int)Size);
                            v96 = v813;
                            if ( (_DWORD)v813 )
                            {
                              v66 = v813;
                              goto LABEL_125;
                            }
LABEL_589:
                            v825[0] = 0;
                            v821 = v825[1];
                            if ( v825[1] )
                            {
                              v425 = GetProcessHeap();
                              HeapFree(v425, 0, (LPVOID)v821);
                              v825[1] = 0;
                            }
                            if ( v808 )
                            {
                              v426 = GetProcessHeap();
                              HeapFree(v426, 0, v808);
                            }
                            if ( Src )
                            {
                              v427 = GetProcessHeap();
                              HeapFree(v427, 0, Src);
                            }
                            if ( v792 )
                            {
                              v428 = GetProcessHeap();
                              HeapFree(v428, 0, v792);
                            }
                            if ( v66 < 0 )
                              goto LABEL_628;
                            if ( !v844 )
                            {
LABEL_627:
                              LODWORD(v804) = v846;
                              v840 = 0;
                              v851 = hLibModule;
LABEL_628:
                              v41 = v796;
                              goto LABEL_629;
                            }
                            *(_OWORD *)v829 = 0;
                            v807 = 0;
                            v429 = GetProcessHeap();
                            v430 = HeapAlloc(v429, 8u, 0xA0u);
                            v793 = v430;
                            if ( !v430 )
                            {
                              v431 = 0;
                              v432 = 0;
LABEL_619:
                              v829[0] = 0;
                              v452 = (void *)v829[1];
                              if ( v829[1] )
                              {
                                v453 = GetProcessHeap();
                                HeapFree(v453, 0, v452);
                                v829[1] = 0;
                              }
                              v454 = (void *)v807;
                              if ( v807 )
                              {
                                v455 = GetProcessHeap();
                                HeapFree(v455, 0, v454);
                              }
                              if ( v431 )
                              {
                                v456 = GetProcessHeap();
                                HeapFree(v456, 0, v431);
                              }
                              if ( v432 )
                              {
                                v457 = GetProcessHeap();
                                HeapFree(v457, 0, v432);
                              }
                              goto LABEL_627;
                            }
                            v797 = (SIZE_T)v44;
                            *v430 = xmmword_18013E190;
                            v430[1] = xmmword_18013E1A0;
                            v430[2] = xmmword_18013E1B0;
                            v430[3] = xmmword_18013E1C0;
                            v430[4] = xmmword_18013E1D0;
                            v430[5] = xmmword_18013E1E0;
                            v430[6] = xmmword_18013E1F0;
                            v430[7] = xmmword_18013E200;
                            v430[8] = xmmword_18013E210;
                            v430[9] = xmmword_18013E220;
                            v433 = GetProcessHeap();
                            v434 = HeapAlloc(v433, 8u, 8u);
                            v814 = v434;
                            if ( !v434 )
                            {
                              v432 = 0;
LABEL_618:
                              v431 = v793;
                              goto LABEL_619;
                            }
                            *v434 = qword_18013E0D0;
                            v821 = __rdtsc();
                            LODWORD(v813) = 0;
                            v799 = 0;
                            if ( (int)RtlUIntAdd(4, 4, &v799) < 0
                              || (int)RtlUIntAdd(0, v799, &v813) < 0
                              || (v799 = 0, (int)RtlUIntAdd(v436, 160, &v799) < 0)
                              || (v437 = RtlUIntAdd((unsigned int)v813, v799, &v813), (v439 | v437) < 0)
                              || (v799 = 0, (int)RtlUIntAdd(v438, v438 + 4, &v799) < 0)
                              || (v440 = RtlUIntAdd((unsigned int)v813, v799, &v813), (v442 | v440) < 0)
                              || (v799 = 0, (int)RtlUIntAdd(v441, v441 + 4, &v799) < 0)
                              || (v443 = RtlUIntAdd((unsigned int)v813, v799, &v813), (v444 | v443) < 0) )
                            {
                              v797 = (SIZE_T)v44;
                              goto LABEL_647;
                            }
                            HIDWORD(v829[0]) = v813;
                            v445 = v813;
                            v446 = GetProcessHeap();
                            v447 = HeapAlloc(v446, 8u, v445);
                            v808 = v447;
                            if ( !v447 )
                            {
                              v432 = v814;
                              goto LABEL_618;
                            }
                            v829[1] = (size_t)v447;
                            LODWORD(v829[0]) = 0;
                            *(_QWORD *)v837 = 0;
                            v824 = (SIZE_T)v447;
                            LODWORD(v810) = 8;
                            LODWORD(Size) = 160;
                            v448 = v797;
                            v804 = v814;
                            if ( (int)RtlULongLongAdd(v447, 4, &v837[4]) < 0
                              || (unsigned __int64)v808 + 8 > v829[1] + HIDWORD(v829[0]) )
                            {
LABEL_991:
                              v431 = v450;
                              goto LABEL_992;
                            }
                            *(_DWORD *)v808 = v449;
                            **(_DWORD **)&v837[4] = v449;
                            v451 = ++LODWORD(v829[0]);
                            *(_QWORD *)v837 = 0;
                            if ( v450 )
                            {
                              if ( !(_DWORD)Size )
                                goto LABEL_617;
                            }
                            else if ( (_DWORD)Size )
                            {
                              goto LABEL_617;
                            }
                            v458 = (unsigned int *)v829[1];
                            lpMem = (LPVOID)v829[1];
                            if ( v829[1] )
                            {
                              v824 = v829[1];
                              LODWORD(v806) = 0;
                              if ( v451 )
                              {
                                do
                                {
                                  v799 = 0;
                                  if ( (int)RtlUIntAdd((unsigned int)v449, *v458, &v799) < 0 )
                                    goto LABEL_617;
                                  v796 = v460;
                                  v797 = v448;
                                  if ( (int)RtlULongLongAdd(lpMem, v799, &v824) < 0 )
                                    goto LABEL_991;
                                  LODWORD(v806) = v806 + 1;
                                  v793 = v450;
                                  v797 = v448;
                                  v796 = v461;
                                  v458 = (unsigned int *)v824;
                                  lpMem = (LPVOID)v824;
                                }
                                while ( (unsigned int)v806 < LODWORD(v829[0]) );
                              }
                              if ( (int)RtlULongLongAdd(v458, v449, &v837[4]) < 0 )
                                goto LABEL_617;
                              v463 = (unsigned int)Size;
                              if ( (unsigned __int64)lpMem + (unsigned int)Size + 4 > v829[1] + HIDWORD(v829[0]) )
                                goto LABEL_617;
                              *(_DWORD *)lpMem = Size;
                              if ( v462 )
                              {
                                memcpy_0(*(void **)&v837[4], v462, v463);
                                v459 = 4;
                              }
                            }
                            else
                            {
                              v799 = 0;
                              if ( (int)RtlUIntAdd((unsigned int)v449, (unsigned int)Size, &v799) < 0
                                || (int)RtlUIntAdd(HIDWORD(v829[0]), v799, (char *)v829 + 4) < 0 )
                              {
                                goto LABEL_617;
                              }
                            }
                            v464 = ++LODWORD(v829[0]);
                            *(_QWORD *)v837 = 0;
                            v435 = v804;
                            if ( v804 )
                            {
                              if ( !(_DWORD)v810 )
                                goto LABEL_617;
                            }
                            else if ( (_DWORD)v810 )
                            {
LABEL_647:
                              v432 = v435;
                              goto LABEL_618;
                            }
                            v465 = (unsigned int *)v829[1];
                            lpMem = (LPVOID)v829[1];
                            if ( v829[1] )
                            {
                              v824 = v829[1];
                              LODWORD(Size) = 0;
                              if ( v464 )
                              {
                                do
                                {
                                  v799 = 0;
                                  if ( (int)RtlUIntAdd((unsigned int)v459, *v465, &v799) < 0 )
                                    goto LABEL_617;
                                  v796 = v467;
                                  v797 = v448;
                                  if ( (int)RtlULongLongAdd(lpMem, v799, &v824) < 0 )
                                    goto LABEL_991;
                                  LODWORD(Size) = Size + 1;
                                  v793 = v450;
                                  v797 = v448;
                                  v796 = v468;
                                  v465 = (unsigned int *)v824;
                                  lpMem = (LPVOID)v824;
                                }
                                while ( (unsigned int)Size < LODWORD(v829[0]) );
                              }
                              if ( (int)RtlULongLongAdd(v465, v459, &v837[4]) < 0 )
                                goto LABEL_617;
                              v470 = (unsigned int)v810;
                              if ( (unsigned __int64)lpMem + (unsigned int)v810 + 4 > v829[1] + HIDWORD(v829[0]) )
                                goto LABEL_617;
                              *(_DWORD *)lpMem = v810;
                              if ( v469 )
                              {
                                memcpy_0(*(void **)&v837[4], v469, v470);
                                v466 = 4;
                              }
                            }
                            else
                            {
                              v799 = 0;
                              if ( (int)RtlUIntAdd((unsigned int)v459, (unsigned int)v810, &v799) < 0 )
                                goto LABEL_647;
                              if ( (int)RtlUIntAdd(HIDWORD(v829[0]), v799, (char *)v829 + 4) < 0 )
                                goto LABEL_617;
                            }
                            v471 = ++LODWORD(v829[0]);
                            *(_QWORD *)v837 = 0;
                            v472 = (unsigned int *)v829[1];
                            lpMem = (LPVOID)v829[1];
                            if ( !v829[1] )
                            {
                              v799 = 0;
                              if ( (int)RtlUIntAdd((unsigned int)v466, 8, &v799) < 0
                                || (int)RtlUIntAdd(HIDWORD(v829[0]), v799, (char *)v829 + 4) < 0 )
                              {
                                goto LABEL_617;
                              }
LABEL_672:
                              ++LODWORD(v829[0]);
                              v799 = 0;
                              if ( (int)RtlUIntAdd(v473, v473, &v799) < 0 )
                                goto LABEL_617;
                              LODWORD(v810) = v799;
                              v799 = 0;
                              if ( (int)RtlUIntAdd(v476, 8, &v799) < 0 || (int)RtlUIntAdd(v477, v799, &v810) < 0 )
                                goto LABEL_617;
                              LODWORD(Size) = 0;
                              LODWORD(dwBytes) = v810;
                              Srca = 0;
                              v821 = __rdtsc();
                              v835 = 8;
                              v479 = RtlUIntAdd(8, HIDWORD(v829[0]), &v835);
                              if ( v479 < 0 )
                              {
                                v797 = v448;
                                v815 = v10;
                                v819 = v8;
                              }
                              else
                              {
                                v482 = (v835 + 7) & 0xFFFFFFF8;
                                if ( v482 < v835 )
                                {
                                  v797 = v448;
                                  goto LABEL_617;
                                }
                                v835 = (v835 + 7) & 0xFFFFFFF8;
                                v483 = v482;
                                v484 = GetProcessHeap();
                                v485 = HeapAlloc(v484, 8u, v483);
                                v814 = v485;
                                if ( !v485 )
                                {
                                  v486 = v797;
LABEL_973:
                                  if ( (v805 & 0x80000000) != 0LL )
                                    goto LABEL_617;
                                  v741 = Size;
                                  if ( (_DWORD)Size )
                                  {
                                    if ( v807 )
                                    {
                                      v828 = v807;
                                      v797 = v486;
                                      if ( (int)RtlULongLongAdd(v807, 4, &v828) < 0 )
                                      {
                                        v807 = (size_t)v743;
                                      }
                                      else
                                      {
                                        v745 = (int *)v828;
                                        if ( !*v743 )
                                          v745 = 0;
                                        if ( *v743 == (_DWORD)v744 )
                                        {
                                          v807 = (size_t)v743;
                                          if ( *v745 < 0 || v741 <= 1 )
                                          {
                                            v797 = v486;
                                            v807 = (size_t)v743;
                                            v431 = v793;
                                            v432 = v804;
                                            goto LABEL_619;
                                          }
                                          v746 = v743;
                                          v814 = v743;
                                          while ( (int)RtlULongLongAdd(v746, v744, &v814) >= 0
                                               && (int)RtlULongLongAdd(v814, v747, &v814) >= 0 )
                                          {
                                            v746 = v814;
                                            if ( v748 != -1 )
                                            {
                                              RtlULongLongAdd(v814, v744, &v814);
                                              goto LABEL_617;
                                            }
                                          }
                                        }
                                        else
                                        {
                                          v807 = v742;
                                        }
                                      }
                                    }
                                    goto LABEL_617;
                                  }
                                  v431 = v793;
LABEL_992:
                                  v432 = v804;
                                  goto LABEL_619;
                                }
                                v819 = v8;
                                v815 = v10;
                                v448 = v797;
                                lpMem = v485;
                                *v485 = v829[0];
                                LODWORD(v810) = RtlULongLongAdd(v485, 4, &lpMem);
                                if ( (v810 & 0x80000000) != 0LL )
                                {
                                  v814 = v487;
                                }
                                else
                                {
                                  v491 = lpMem;
                                  *(_DWORD *)lpMem = HIDWORD(v829[0]);
                                  LODWORD(v810) = RtlULongLongAdd(v491, v489, &lpMem);
                                  if ( (v810 & 0x80000000) == 0LL )
                                  {
                                    *(_QWORD *)((char *)v814 + v835 - 8) = v821;
                                    memcpy_0(lpMem, (const void *)v829[1], HIDWORD(v829[0]));
                                    v480 = v814;
                                    Srca = (unsigned __int8 *)v814;
                                    v481 = v835;
                                    v479 = v810;
                                    goto LABEL_686;
                                  }
                                }
                                v819 = v8;
                                v815 = v10;
                                v796 = v488;
                                v793 = v490;
                                v492 = GetProcessHeap();
                                HeapFree(v492, 0, v814);
                                v480 = 0;
                                v479 = v810;
                                v481 = 0;
                              }
LABEL_686:
                              v801 = 0;
                              pcchLength = 0;
                              v811 = 0;
                              v816 = 0;
                              v493 = v479 | 0x10000000;
                              if ( v493 < 0 )
                              {
                                LODWORD(v805) = v493;
                                goto LABEL_946;
                              }
                              if ( !v480 )
                                goto LABEL_617;
                              lpMem = (LPVOID)v481;
                              if ( !v481
                                || (v823 = v481 + 8LL,
                                    v494 = NCoreLibrary::AllocMem((NCoreLibrary *)v823, v478),
                                    (v832 = v494) == 0) )
                              {
                                LODWORD(v805) = -805306367;
                                v486 = v797;
                                v595 = 0;
                                v700 = Srca;
                                goto LABEL_950;
                              }
                              v814 = 0;
                              v495 = 0;
                              LOBYTE(v805) = 0;
                              v496 = 0;
                              v497 = (unsigned __int64)lpMem;
                              if ( lpMem )
                              {
                                do
                                  v495 ^= Srca[v496++];
                                while ( v496 < (unsigned __int64)lpMem );
                                LOBYTE(v805) = v495;
                              }
                              v801 = (LPVOID)0xC81ECB17B1B54A58LL;
                              v824 = (SIZE_T)Srca;
                              v830 = v494;
                              v498 = (unsigned __int8)lpMem & 7;
                              v499 = 0;
                              LODWORD(v806) = 0;
                              if ( ((unsigned __int8)lpMem & 7) != 0 )
                              {
                                LODWORD(v810) = 0;
                                v500 = Srca;
                                v501 = 0;
                                v502 = 0;
                                do
                                {
                                  LODWORD(v806) = *v500++;
                                  v799 = 8 * v9;
                                  if ( v9 >= 4 )
                                  {
                                    LODWORD(v806) = (_DWORD)v806 << (56 - v799);
                                    v501 |= v806;
                                  }
                                  else
                                  {
                                    LODWORD(v806) = (_DWORD)v806 << (24 - v799);
                                    v502 |= v806;
                                  }
                                  ++v9;
                                }
                                while ( (int)v9 < v498 );
                                LODWORD(v806) = v502;
                                LODWORD(v810) = v501;
                                v824 = (SIZE_T)v500;
                                v797 = v448;
                                v815 = v10;
                                v819 = v8;
                                v495 = v805;
                                v66 = v798;
                                v497 = (unsigned __int64)lpMem;
                                v499 = v502 ^ 0xB17A307A;
                                v503 = v810 ^ 0x42F6B18D;
                                v504 = v502 ^ 0xB17A307A;
                                v505 = v810 ^ 0x42F6B18D;
                                v506 = 0;
                                if ( ((unsigned __int8)lpMem & 7) != 0 )
                                {
                                  v507 = v830;
                                  do
                                  {
                                    v821 = (SIZE_T)(v507 + 1);
                                    if ( v506 >= 4 )
                                    {
                                      v505 = __ROR4__(v505, 24);
                                      v508 = v505;
                                    }
                                    else
                                    {
                                      v504 = __ROR4__(v504, 24);
                                      v508 = v504;
                                    }
                                    *v507 = v508;
                                    ++v506;
                                    v507 = (_BYTE *)v821;
                                  }
                                  while ( (int)v506 < v498 );
                                  v830 = (LPVOID)v821;
                                  v495 = v805;
                                  v497 = (unsigned __int64)lpMem;
                                }
                                if ( (unsigned int)v498 <= 4 )
                                {
                                  v509 = 0;
                                  if ( (unsigned int)v498 < 4 )
                                    v499 = v499 >> (8 * (4 - v498)) << (8 * (4 - v498));
                                }
                                else
                                {
                                  v509 = v503 >> (8 * (8 - v498)) << (8 * (8 - v498));
                                }
                              }
                              else
                              {
                                v509 = -1;
                                LODWORD(v810) = 0;
                              }
                              if ( v497 >> 3 )
                              {
                                v828 = 0;
                                LODWORD(v813) = 19032;
                                LODWORD(v817) = WORD1(v801);
                                v510 = WORD2(v801);
                                v511 = (unsigned __int8 *)v824;
                                v512 = v830;
                                v513 = v497 >> 3;
                                v514 = v810;
                                v515 = v806;
                                do
                                {
                                  v516 = v511[3] | ((v511[2] | ((v511[1] | (*v511 << 8)) << 8)) << 8);
                                  v517 = v511[7] | ((v511[6] | ((v511[5] | (v511[4] << 8)) << 8)) << 8);
                                  v511 += 8;
                                  v518 = v499 ^ v516 ^ ((v509 ^ v517) - v813);
                                  v519 = HIDWORD(v801) ^ v518;
                                  v520 = v509
                                       ^ v517
                                       ^ (__ROR4__(HIDWORD(v801) ^ v518, 7) + WORD1(v801) * __ROR4__(v518, 15));
                                  v521 = v519 ^ (v510 * __ROR4__(v520 - 1313519016, 9) - __ROR4__(v520, 10));
                                  v522 = v520 ^ (__ROR4__(v521, 27) + HIWORD(v801) * __ROR4__(v521 ^ v510, 28));
                                  v523 = v521 ^ (HIDWORD(v801) - (v522 ^ 0xB1B54A58));
                                  v524 = v522 ^ (WORD1(v801) * (v523 - v813) - (v523 >> 6));
                                  v525 = v523 ^ (v813 * (v510 ^ __ROR4__(v524, 15)));
                                  v526 = v524 ^ (v510 * (HIWORD(v801) + __ROR4__(~v525, 3)));
                                  v527 = v525 ^ (v526 - v813 - HIDWORD(v801));
                                  v528 = v526 ^ (v817 * (v527 ^ HIWORD(v801))) ^ __ROR4__(v527, 10);
                                  v529 = v527 ^ __ROR4__(v528, 3) ^ (v510 * __ROR4__(v528 ^ v813, 26));
                                  v530 = v528 ^ (v813 * (__ROR4__(v529, 15) - HIWORD(v801)));
                                  v531 = v529
                                       ^ (v813 * (v530 ^ HIWORD(v801)))
                                       ^ ((v530 ^ (v530 >> 14)) >> 1)
                                       ^ (v813 * ((8 * (v530 - v510)) | ((unsigned __int64)(v530 - v510) >> 29)));
                                  v532 = v530 ^ (WORD1(v801) * (v531 - v510) - (v531 >> 13));
                                  v533 = v531 ^ __ROR4__(v532, 11) ^ (v510 * __ROR4__(-1313519016 - v532, 9));
                                  v534 = v532 ^ (v533 - HIWORD(v801) + 1313519016);
                                  v535 = v533 ^ (v813 * (v534 ^ WORD1(v801)) - __ROR4__(v534, 7));
                                  v536 = v534 ^ (WORD1(v801) * __ROR4__(v535 ^ HIWORD(v801), 28) - __ROR4__(v535, 16));
                                  v537 = v535 ^ (__ROR4__(v536, 4) + v510 * __ROR4__(-1313519016 - v536, 10));
                                  v538 = v536 ^ __ROR4__(v537, 9) ^ (HIWORD(v801) * __ROR4__(v537 + 1313519016, 4));
                                  v539 = v537 ^ (v813 * __ROR4__(HIDWORD(v801) ^ v538, 24) - __ROR4__(v538, 30));
                                  v540 = v538 ^ (WORD1(v801) * __ROR4__(HIDWORD(v801) - v539, 11) - __ROR4__(v539, 12));
                                  v541 = v539 ^ (v540 >> 8) ^ (v510 * (v540 ^ WORD1(v801)));
                                  v499 = v515 ^ v541;
                                  v509 = v540 ^ v514 ^ HIDWORD(v801) ^ v541 ^ 0xB1B54A58;
                                  v512[3] = v499;
                                  v512[7] = v509;
                                  v512[2] = __ROR4__(v499, 8);
                                  v512[6] = __ROR4__(v509, 8);
                                  v512[1] = __ROR4__(v499, 16);
                                  v512[5] = __ROR4__(v509, 16);
                                  *v512 = __ROR4__(v499, 24);
                                  v512[4] = __ROR4__(v509, 24);
                                  v515 = v516;
                                  v514 = v517;
                                  v512 += 8;
                                  ++v828;
                                }
                                while ( v828 < v513 );
                                v495 = v805;
                                v66 = v798;
                                v8 = (unsigned __int16 *)v819;
                                v10 = (HMODULE)v815;
                                v497 = (unsigned __int64)lpMem;
                              }
                              *(_QWORD *)((char *)v832 + v497) = v495;
                              v542 = GetProcessHeap();
                              v543 = HeapAlloc(v542, 8u, 0x30u);
                              v808 = v543;
                              if ( v543 )
                              {
                                v554 = v823;
                                *v543 = v823;
                                v555 = GetProcessHeap();
                                v556 = HeapAlloc(v555, 8u, v554);
                                v544 = v797;
                                v545 = v796;
                                v557 = v793;
                                if ( v556 )
                                {
                                  *((_QWORD *)v808 + 1) = v556;
                                  memcpy_0(v556, v832, (unsigned int)v823);
                                  *((_DWORD *)v808 + 4) = 160;
                                  v558 = GetProcessHeap();
                                  v559 = HeapAlloc(v558, 8u, 0xA0u);
                                  v560 = v808;
                                  if ( v559 )
                                  {
                                    *((_QWORD *)v808 + 3) = v559;
                                    *v559 = xmmword_18013E0E0;
                                    v559[1] = xmmword_18013E0F0;
                                    v559[2] = xmmword_18013E100;
                                    v559[3] = xmmword_18013E110;
                                    v559[4] = xmmword_18013E120;
                                    v559[5] = xmmword_18013E130;
                                    v559[6] = xmmword_18013E140;
                                    v559[7] = xmmword_18013E150;
                                    v559[8] = xmmword_18013E160;
                                    v559[9] = xmmword_18013E170;
                                    v560[8] = 8;
                                    v561 = GetProcessHeap();
                                    v562 = HeapAlloc(v561, 8u, 8u);
                                    if ( v562 )
                                    {
                                      v568 = v808;
                                      *((_QWORD *)v808 + 5) = v562;
                                      *v562 = qword_18013E180;
                                      LODWORD(v806) = 0;
                                      v546 = v568;
                                      v814 = 0;
LABEL_718:
                                      v801 = v546;
                                      v547 = GetProcessHeap();
                                      HeapFree(v547, 0, v832);
                                      v548 = v814;
                                      if ( v814 )
                                      {
                                        v821 = *((_QWORD *)v814 + 1);
                                        if ( v821 )
                                        {
                                          v549 = GetProcessHeap();
                                          HeapFree(v549, 0, (LPVOID)v821);
                                          v548 = v814;
                                          *((_QWORD *)v814 + 1) = 0;
                                        }
                                        v821 = v548[3];
                                        if ( v821 )
                                        {
                                          v550 = GetProcessHeap();
                                          HeapFree(v550, 0, (LPVOID)v821);
                                          v548 = v814;
                                          *((_QWORD *)v814 + 3) = 0;
                                        }
                                        v821 = v548[5];
                                        if ( v821 )
                                        {
                                          v551 = GetProcessHeap();
                                          HeapFree(v551, 0, (LPVOID)v821);
                                          *((_QWORD *)v814 + 5) = 0;
                                        }
                                        v552 = GetProcessHeap();
                                        HeapFree(v552, 0, v814);
                                        v553 = (unsigned int *)v801;
                                      }
                                      else
                                      {
                                        v553 = (unsigned int *)v801;
                                      }
                                      if ( (v806 & 0x80000000) != 0LL )
                                      {
                                        v797 = v544;
                                        v796 = v545;
                                        LODWORD(v805) = v806 | 0x10000000;
                                        v486 = v544;
                                        v595 = 0;
LABEL_948:
                                        v700 = Srca;
LABEL_949:
                                        if ( !v700 )
                                        {
LABEL_951:
                                          v723 = v801;
                                          if ( v801 )
                                          {
                                            v821 = *((_QWORD *)v801 + 1);
                                            if ( v821 )
                                            {
                                              v724 = GetProcessHeap();
                                              HeapFree(v724, 0, (LPVOID)v821);
                                              v723[1] = 0;
                                            }
                                            v821 = v723[3];
                                            if ( v821 )
                                            {
                                              v725 = GetProcessHeap();
                                              HeapFree(v725, 0, (LPVOID)v821);
                                              v723[3] = 0;
                                            }
                                            v821 = v723[5];
                                            if ( v821 )
                                            {
                                              v726 = GetProcessHeap();
                                              HeapFree(v726, 0, (LPVOID)v821);
                                              v723[5] = 0;
                                            }
                                            v727 = GetProcessHeap();
                                            HeapFree(v727, 0, v723);
                                          }
                                          v728 = (void *)pcchLength;
                                          if ( pcchLength )
                                          {
                                            v729 = GetProcessHeap();
                                            HeapFree(v729, 0, v728);
                                          }
                                          if ( v595 )
                                          {
                                            v730 = GetProcessHeap();
                                            HeapFree(v730, 0, v595);
                                          }
                                          v731 = v811;
                                          if ( v811 )
                                          {
                                            v732 = (void *)*((_QWORD *)v811 + 1);
                                            if ( v732 )
                                            {
                                              v733 = GetProcessHeap();
                                              HeapFree(v733, 0, v732);
                                              v731[1] = 0;
                                            }
                                            v734 = (void *)v731[3];
                                            if ( v734 )
                                            {
                                              v735 = GetProcessHeap();
                                              HeapFree(v735, 0, v734);
                                              v731[3] = 0;
                                            }
                                            v736 = (void *)v731[5];
                                            if ( v736 )
                                            {
                                              v737 = GetProcessHeap();
                                              HeapFree(v737, 0, v736);
                                              v731[5] = 0;
                                            }
                                            v738 = GetProcessHeap();
                                            HeapFree(v738, 0, v731);
                                          }
                                          v739 = v816;
                                          if ( v816 )
                                          {
                                            v740 = GetProcessHeap();
                                            HeapFree(v740, 0, v739);
                                          }
                                          goto LABEL_973;
                                        }
LABEL_950:
                                        v722 = GetProcessHeap();
                                        HeapFree(v722, 0, v700);
                                        goto LABEL_951;
                                      }
                                      LODWORD(v806) = 0;
                                      LODWORD(v805) = 4;
                                      LODWORD(v813) = RtlUIntAdd(4, *v553, &v805);
                                      if ( (v813 & 0x80000000) != 0LL
                                        || (LODWORD(v813) = RtlUIntAdd((unsigned int)v805, v569, &v805),
                                            (v813 & 0x80000000) != 0LL)
                                        || (v828 = (SIZE_T)v801 + 16,
                                            LODWORD(v813) = RtlUIntAdd(
                                                              (unsigned int)v805,
                                                              *((unsigned int *)v801 + 4),
                                                              &v805),
                                            (v813 & 0x80000000) != 0LL)
                                        || (LODWORD(v813) = RtlUIntAdd((unsigned int)v805, v570, &v805),
                                            (v813 & 0x80000000) != 0LL)
                                        || (v823 = v571 + 32,
                                            LODWORD(v813) = RtlUIntAdd(
                                                              (unsigned int)v805,
                                                              *(unsigned int *)(v571 + 32),
                                                              &v805),
                                            (v813 & 0x80000000) != 0LL) )
                                      {
                                        v797 = v544;
                                        v796 = v545;
                                      }
                                      else
                                      {
                                        v801 = v572;
                                        v573 = v805;
                                        v574 = GetProcessHeap();
                                        v575 = HeapAlloc(v574, 8u, v573);
                                        v815 = v575;
                                        if ( !v575 )
                                        {
LABEL_746:
                                          LODWORD(v805) = -805306345;
LABEL_946:
                                          v595 = 0;
                                          goto LABEL_947;
                                        }
                                        v545 = v796;
                                        v797 = v544;
                                        v808 = v575;
                                        *v575 = *(_DWORD *)v801;
                                        LODWORD(v813) = RtlULongLongAdd(v575, 4, &v808);
                                        if ( (v813 & 0x80000000) != 0LL )
                                        {
                                          v801 = v579;
                                          v804 = v578;
                                          v793 = v577;
                                          v815 = v576;
                                        }
                                        else
                                        {
                                          memcpy_0(v808, v579[1], *(unsigned int *)v579);
                                          LODWORD(v813) = RtlULongLongAdd(v808, *(unsigned int *)v801, &v808);
                                          if ( (v813 & 0x80000000) != 0LL
                                            || (v581 = v808,
                                                *(_DWORD *)v808 = *(_DWORD *)v828,
                                                LODWORD(v813) = RtlULongLongAdd(v581, 4, &v808),
                                                (v813 & 0x80000000) != 0LL) )
                                          {
                                            v801 = v580;
                                          }
                                          else
                                          {
                                            memcpy_0(v808, v580[3], *v582);
                                            LODWORD(v813) = RtlULongLongAdd(v808, *(unsigned int *)v828, &v808);
                                            if ( (v813 & 0x80000000) == 0LL )
                                            {
                                              v583 = v808;
                                              *(_DWORD *)v808 = *(_DWORD *)v823;
                                              LODWORD(v813) = RtlULongLongAdd(v583, 4, &v808);
                                              if ( (v813 & 0x80000000) == 0LL )
                                              {
                                                memcpy_0(v808, *((const void **)v801 + 5), *v584);
                                                v585 = RtlULongLongAdd(v808, *(unsigned int *)v823, &v808);
                                                LODWORD(v813) = v585;
                                                if ( v585 >= 0 )
                                                {
                                                  pcchLength = (size_t)v815;
                                                  LODWORD(v806) = v805;
LABEL_759:
                                                  v587 = v585 | 0x10000000;
                                                  if ( v587 < 0 )
                                                    goto LABEL_763;
                                                  v842 = 8;
                                                  v587 = RtlUIntAdd(8, (unsigned int)dwBytes, &v842) | 0x10000000;
                                                  if ( v587 < 0 )
                                                    goto LABEL_763;
                                                  v588 = (v842 + 7) & 0xFFFFFFF8;
                                                  if ( (unsigned int)v588 < v842 )
                                                  {
                                                    v587 = -1073741675;
LABEL_763:
                                                    LODWORD(v805) = v587;
                                                    goto LABEL_946;
                                                  }
                                                  v845 = (v842 + 7) & 0xFFFFFFF8;
                                                  v587 = RtlUIntAdd(v588, 8, &v845);
                                                  if ( v587 < 0 )
                                                    goto LABEL_763;
                                                  v819 = v8;
                                                  v815 = v10;
                                                  v796 = v545;
                                                  v797 = v544;
                                                  v793 = v590;
                                                  v804 = v591;
                                                  LODWORD(v810) = 0;
                                                  v828 = v829[1];
                                                  if ( v829[1]
                                                    && (v804 = v591,
                                                        v793 = v590,
                                                        v797 = v544,
                                                        v796 = v545,
                                                        v815 = v10,
                                                        v819 = v8,
                                                        LODWORD(v829[0]) > 1) )
                                                  {
                                                    v814 = (LPVOID)v829[1];
                                                    v799 = 0;
                                                    while ( 1 )
                                                    {
                                                      v592 = RtlULongLongAdd(v828, v589, &v814);
                                                      if ( v592 < 0 )
                                                        goto LABEL_767;
                                                      v592 = RtlULongLongAdd(v814, v596, &v814);
                                                      if ( v592 < 0 )
                                                        goto LABEL_767;
                                                      if ( ++v799 )
                                                        break;
                                                      v828 = (SIZE_T)v814;
                                                    }
                                                    v597 = *(_DWORD *)v814;
                                                    v592 = RtlULongLongAdd(v814, v589, &v814);
                                                    if ( v592 >= 0 )
                                                    {
                                                      v599 = (LPVOID)v829[1];
                                                      if ( !v829[1] || LODWORD(v829[0]) <= 2 )
                                                      {
                                                        v587 = -1073741811;
                                                        goto LABEL_763;
                                                      }
                                                      v814 = (LPVOID)v829[1];
                                                      do
                                                      {
                                                        v587 = RtlULongLongAdd(v599, v598, &v814);
                                                        if ( v587 < 0 )
                                                          goto LABEL_763;
                                                        v587 = RtlULongLongAdd(v814, v600, &v814);
                                                        if ( v587 < 0 )
                                                          goto LABEL_763;
                                                        v599 = v814;
                                                      }
                                                      while ( (unsigned int)(v601 + 1) < 2 );
                                                      v587 = RtlULongLongAdd(v814, v598, &v814);
                                                      if ( v587 < 0 )
                                                        goto LABEL_763;
                                                      LODWORD(v810) = 0;
                                                      LODWORD(v813) = v602;
                                                      v587 = RtlUIntAdd(v602, v845, &v813);
                                                      if ( v587 < 0 )
                                                        goto LABEL_763;
                                                      v587 = RtlUIntAdd((unsigned int)v813, v603, &v813);
                                                      if ( v587 < 0 )
                                                        goto LABEL_763;
                                                      v587 = RtlUIntAdd((unsigned int)v813, v597, &v813);
                                                      if ( v587 < 0 )
                                                        goto LABEL_763;
                                                      v587 = RtlUIntAdd((unsigned int)v813, v604, &v813);
                                                      if ( v587 < 0 )
                                                        goto LABEL_763;
                                                      v587 = RtlUIntAdd((unsigned int)v813, v605, &v813);
                                                      if ( v587 < 0 )
                                                        goto LABEL_763;
                                                      LODWORD(v810) = v813;
                                                      if ( (unsigned int)v813 > 0x400000 )
                                                      {
                                                        v587 = -2147418113;
                                                        goto LABEL_763;
                                                      }
                                                      v593 = v813;
                                                      v594 = GetProcessHeap();
                                                      v595 = HeapAlloc(v594, 8u, v593);
                                                      v802 = v595;
                                                      if ( !v595 )
                                                        goto LABEL_746;
                                                      v857 = 0;
                                                      v858 = 0;
                                                      hModule = 0;
                                                      if ( !pcchLength )
                                                      {
                                                        LODWORD(v805) = -2147024809;
                                                        goto LABEL_947;
                                                      }
                                                      *(_QWORD *)&v857 = pcchLength;
                                                      LODWORD(v858) = v806;
                                                      *((_QWORD *)&v857 + 1) = v595;
                                                      *(_QWORD *)((char *)&v858 + 4) = (unsigned int)v810;
                                                      if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                                                        && (v608 = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                                                      {
                                                        v606 = ((__int64 (__fastcall *)(__int64, __int128 *))v608)(
                                                                 134,
                                                                 &v857)
                                                             | 0x10000000;
                                                        if ( v606 >= 0 )
                                                        {
                                                          v609 = DWORD1(v858);
                                                          goto LABEL_805;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v606 = GetLastError();
                                                        v607 = v606 < 0;
                                                        if ( v606 > 0 )
                                                        {
                                                          v606 = (unsigned __int16)v606 | 0x80070000;
                                                          v607 = v606 < 0;
                                                        }
                                                        if ( !v607 )
                                                        {
                                                          LODWORD(v805) = -2147467259;
                                                          goto LABEL_947;
                                                        }
                                                      }
                                                      if ( v606 == -805306333 )
                                                      {
                                                        LODWORD(v805) = -2147024774;
                                                        goto LABEL_947;
                                                      }
                                                      if ( v606 < 0 )
                                                      {
                                                        LODWORD(v805) = v606;
                                                        goto LABEL_947;
                                                      }
                                                      v609 = v810;
LABEL_805:
                                                      LODWORD(dwBytes) = 0;
                                                      v812 = v595;
                                                      if ( v609 < 4 )
                                                      {
LABEL_806:
                                                        LODWORD(v805) = -805306306;
                                                        goto LABEL_947;
                                                      }
                                                      v799 = *v595;
                                                      v610 = RtlULongLongAdd(v595, 4, &v812);
                                                      if ( v610 < 0 )
                                                        goto LABEL_858;
                                                      v610 = RtlUIntAdd(0, v612, &dwBytes);
                                                      if ( v610 < 0 )
                                                        goto LABEL_858;
                                                      if ( v613 - (int)dwBytes < (unsigned int)v614 )
                                                        goto LABEL_806;
                                                      v823 = (SIZE_T)v812;
                                                      v828 = v614;
                                                      v610 = RtlULongLongAdd(v812, (unsigned int)v614, &v812);
                                                      if ( v610 < 0 )
                                                        goto LABEL_858;
                                                      v610 = RtlUIntAdd((unsigned int)dwBytes, v615, &dwBytes);
                                                      if ( v610 < 0 )
                                                        goto LABEL_858;
                                                      if ( v617 - (int)dwBytes < (unsigned int)v616 )
                                                        goto LABEL_806;
                                                      LODWORD(v810) = *(_DWORD *)v812;
                                                      v610 = RtlULongLongAdd(v812, v616, &v812);
                                                      if ( v610 < 0 )
                                                        goto LABEL_858;
                                                      v610 = RtlUIntAdd((unsigned int)dwBytes, v618, &dwBytes);
                                                      if ( v610 < 0 )
                                                        goto LABEL_858;
                                                      if ( v619 - (int)dwBytes < (unsigned int)v620 )
                                                        goto LABEL_806;
                                                      v830 = v812;
                                                      v824 = v620;
                                                      v610 = RtlULongLongAdd(v812, (unsigned int)v620, &v812);
                                                      if ( v610 < 0 )
                                                        goto LABEL_858;
                                                      v610 = RtlUIntAdd((unsigned int)dwBytes, v621, &dwBytes);
                                                      if ( v610 < 0 )
                                                        goto LABEL_858;
                                                      if ( v623 - (int)dwBytes < (unsigned int)v622 )
                                                        goto LABEL_806;
                                                      LODWORD(v817) = *(_DWORD *)v812;
                                                      v610 = RtlULongLongAdd(v812, v622, &v812);
                                                      if ( v610 < 0 )
                                                        goto LABEL_858;
                                                      v610 = RtlUIntAdd((unsigned int)dwBytes, v624, &dwBytes);
                                                      if ( v610 < 0 )
                                                        goto LABEL_858;
                                                      if ( v625 - (int)dwBytes < v626 )
                                                        goto LABEL_806;
                                                      v610 = RtlUIntAdd((unsigned int)dwBytes, v626, &dwBytes);
                                                      if ( v610 < 0 )
                                                      {
LABEL_858:
                                                        v802 = v595;
                                                        v631 = v796;
                                                        goto LABEL_859;
                                                      }
                                                      if ( v627 != (_DWORD)dwBytes
                                                        || v628 + (unsigned int)v810 + v799 + 12LL != v627 )
                                                      {
                                                        goto LABEL_806;
                                                      }
                                                      v629 = GetProcessHeap();
                                                      v630 = (SIZE_T *)HeapAlloc(v629, 8u, 0x30u);
                                                      v808 = v630;
                                                      if ( !v630 )
                                                      {
                                                        v811 = 0;
                                                        LODWORD(v805) = -805306345;
LABEL_947:
                                                        v486 = v797;
                                                        goto LABEL_948;
                                                      }
                                                      v819 = v8;
                                                      v815 = v10;
                                                      v631 = v796;
                                                      v797 = v544;
                                                      v814 = 0;
                                                      if ( v823 )
                                                      {
                                                        *(_DWORD *)v630 = v799;
                                                        v632 = GetProcessHeap();
                                                        v633 = HeapAlloc(v632, 8u, v828);
                                                        if ( !v633 )
                                                        {
LABEL_838:
                                                          LODWORD(v813) = -1073741801;
                                                          v639 = v808;
                                                          v821 = *((_QWORD *)v808 + 1);
                                                          if ( v821 )
                                                          {
                                                            v640 = GetProcessHeap();
                                                            HeapFree(v640, 0, (LPVOID)v821);
                                                            v639 = v808;
                                                            *((_QWORD *)v808 + 1) = 0;
                                                          }
                                                          v821 = v639[3];
                                                          if ( v821 )
                                                          {
                                                            v641 = GetProcessHeap();
                                                            HeapFree(v641, 0, (LPVOID)v821);
                                                            v639 = v808;
                                                            *((_QWORD *)v808 + 3) = 0;
                                                          }
                                                          v821 = v639[5];
                                                          if ( v821 )
                                                          {
                                                            v642 = GetProcessHeap();
                                                            HeapFree(v642, 0, (LPVOID)v821);
                                                            *((_QWORD *)v808 + 5) = 0;
                                                          }
                                                          v643 = GetProcessHeap();
                                                          HeapFree(v643, 0, v808);
                                                          v630 = 0;
                                                          goto LABEL_848;
                                                        }
                                                        *((_QWORD *)v808 + 1) = v633;
                                                        LODWORD(v813) = 0;
                                                        memcpy_0(v633, (const void *)v823, v828);
                                                        v630 = (SIZE_T *)v808;
                                                      }
                                                      else
                                                      {
                                                        *(_DWORD *)v630 = 0;
                                                        v630[1] = 0;
                                                        LODWORD(v813) = 0;
                                                      }
                                                      if ( v830 )
                                                      {
                                                        *((_DWORD *)v630 + 4) = v810;
                                                        v634 = GetProcessHeap();
                                                        v635 = HeapAlloc(v634, 8u, v824);
                                                        if ( !v635 )
                                                        {
LABEL_837:
                                                          v819 = v8;
                                                          v815 = v10;
                                                          v797 = v544;
                                                          goto LABEL_838;
                                                        }
                                                        *((_QWORD *)v808 + 3) = v635;
                                                        LODWORD(v813) = 0;
                                                        memcpy_0(v635, v830, v824);
                                                        v630 = (SIZE_T *)v808;
                                                      }
                                                      else
                                                      {
                                                        *((_DWORD *)v630 + 4) = 0;
                                                        v630[3] = 0;
                                                      }
                                                      if ( v812 )
                                                      {
                                                        v636 = (unsigned int)v817;
                                                        *((_DWORD *)v630 + 8) = v817;
                                                        v828 = v636;
                                                        v637 = GetProcessHeap();
                                                        v638 = HeapAlloc(v637, 8u, v828);
                                                        if ( !v638 )
                                                          goto LABEL_837;
                                                        *((_QWORD *)v808 + 5) = v638;
                                                        LODWORD(v813) = 0;
                                                        memcpy_0(v638, v812, v828);
                                                        v630 = (SIZE_T *)v808;
                                                      }
                                                      else
                                                      {
                                                        *((_DWORD *)v630 + 8) = 0;
                                                        v630[5] = 0;
                                                      }
                                                      v814 = v630;
                                                      v797 = v544;
                                                      v815 = v10;
                                                      v819 = v8;
LABEL_848:
                                                      v610 = v813;
                                                      if ( (v813 & 0x80000000) == 0LL )
                                                      {
                                                        v644 = v630;
                                                        v811 = v630;
                                                        goto LABEL_860;
                                                      }
                                                      v644 = 0;
                                                      v811 = 0;
                                                      if ( !v630 )
                                                      {
LABEL_860:
                                                        LODWORD(v805) = v610 | 0x10000000;
                                                        if ( v610 >= 0 )
                                                        {
                                                          if ( v644 )
                                                          {
                                                            v823 = v644[1];
                                                            if ( v823 )
                                                            {
                                                              if ( *(_DWORD *)v644 )
                                                              {
                                                                v814 = (LPVOID)(*(unsigned int *)v644 - 8LL);
                                                                v649 = NCoreLibrary::AllocMem(
                                                                         (NCoreLibrary *)v814,
                                                                         v611);
                                                                v816 = v649;
                                                                if ( !v649 )
                                                                {
LABEL_892:
                                                                  LODWORD(v805) = -805306367;
                                                                  v816 = 0;
                                                                  goto LABEL_893;
                                                                }
                                                                v650 = 0;
                                                                LOBYTE(v805) = 0;
                                                                v808 = (LPVOID)0x7F1137FAB69605ELL;
                                                                v812 = (LPVOID)v823;
                                                                v824 = (SIZE_T)v649;
                                                                v651 = (unsigned __int64)v814;
                                                                v828 = (unsigned __int8)v814 & 7;
                                                                v652 = 0;
                                                                LODWORD(v810) = 0;
                                                                if ( ((unsigned __int8)v814 & 7) != 0 )
                                                                {
                                                                  v809 = 0;
                                                                  v653 = 0;
                                                                  v654 = (unsigned __int8 *)v812;
                                                                  v655 = 0;
                                                                  v656 = 0;
                                                                  do
                                                                  {
                                                                    LODWORD(v806) = *v654++;
                                                                    v799 = 8 * v655;
                                                                    if ( (unsigned int)v655 >= 4 )
                                                                    {
                                                                      LODWORD(v806) = (_DWORD)v806 << (56 - v799);
                                                                      v653 |= v806;
                                                                    }
                                                                    else
                                                                    {
                                                                      LODWORD(v806) = (_DWORD)v806 << (24 - v799);
                                                                      v656 |= v806;
                                                                    }
                                                                    ++v655;
                                                                  }
                                                                  while ( v655 < (int)v828 );
                                                                  LODWORD(v810) = v656;
                                                                  v809 = v653;
                                                                  v812 = v654;
                                                                  v797 = v544;
                                                                  v796 = v631;
                                                                  v815 = v10;
                                                                  v819 = v8;
                                                                  v650 = v805;
                                                                  v66 = v798;
                                                                  v651 = (unsigned __int64)v814;
                                                                  v657 = v828;
                                                                  v658 = (_BYTE *)v824;
                                                                  v652 = v810 ^ 0x92F65A5;
                                                                  v659 = v809 ^ 0x699A899C;
                                                                  v660 = v810 ^ 0x92F65A5;
                                                                  v661 = v809 ^ 0x699A899C;
                                                                  if ( (_DWORD)v828 )
                                                                  {
                                                                    v662 = 0;
                                                                    do
                                                                    {
                                                                      v821 = (SIZE_T)(v658 + 1);
                                                                      if ( v662 >= 4 )
                                                                      {
                                                                        v661 = __ROR4__(v661, 24);
                                                                        v663 = v661;
                                                                      }
                                                                      else
                                                                      {
                                                                        v660 = __ROR4__(v660, 24);
                                                                        v663 = v660;
                                                                      }
                                                                      *v658 = v663;
                                                                      ++v662;
                                                                      v658 = (_BYTE *)v821;
                                                                    }
                                                                    while ( (int)v662 < (int)v657 );
                                                                    v824 = v821;
                                                                    v650 = v805;
                                                                    v651 = (unsigned __int64)v814;
                                                                  }
                                                                  if ( v657 <= 4 )
                                                                  {
                                                                    v664 = 0;
                                                                    if ( v657 < 4 )
                                                                      v652 = v652 >> (8 * (4 - v657)) << (8 * (4 - v657));
                                                                  }
                                                                  else
                                                                  {
                                                                    v664 = v659 >> (8 * (8 - v657)) << (8 * (8 - v657));
                                                                  }
                                                                }
                                                                else
                                                                {
                                                                  v664 = 0;
                                                                }
                                                                if ( v651 >> 3 )
                                                                {
                                                                  v828 = 0;
                                                                  v665 = HIDWORD(v808);
                                                                  LODWORD(v806) = WORD2(v808);
                                                                  LODWORD(v813) = 24670;
                                                                  v666 = v809;
                                                                  v667 = (unsigned __int8 *)v812;
                                                                  v668 = (_BYTE *)v824;
                                                                  v669 = v810;
                                                                  v670 = v651 >> 3;
                                                                  do
                                                                  {
                                                                    v671 = v667[3]
                                                                         | ((v667[2] | (((*v667 << 8) | v667[1]) << 8)) << 8);
                                                                    v672 = v667[7]
                                                                         | ((v667[6] | ((v667[5] | (v667[4] << 8)) << 8)) << 8);
                                                                    v667 += 8;
                                                                    v673 = v652 ^ v671;
                                                                    v674 = v665 ^ v652 ^ v671 ^ v664 ^ v672 ^ 0xAB69605E;
                                                                    v675 = v673
                                                                         ^ (__ROR4__(v674, 22)
                                                                          + v806 * __ROR4__(v674 + 1419157410, 27));
                                                                    v676 = v674
                                                                         ^ (WORD1(v808) * __ROR4__(v665 + v675, 9)
                                                                          - __ROR4__(v675, 30));
                                                                    v677 = v675 ^ (v813 * (v676 - v806) - (v676 >> 13));
                                                                    v678 = v676
                                                                         ^ (HIWORD(v808)
                                                                          * __ROR4__(v677 ^ WORD1(v808), 26)
                                                                          - __ROR4__(v677, 30));
                                                                    v679 = v677 ^ (v665 - (v678 ^ 0xAB69605E));
                                                                    v680 = v678
                                                                         ^ (WORD1(v808) * (v806 ^ v679))
                                                                         ^ __ROR4__(v679, 6);
                                                                    v681 = v679
                                                                         ^ (__ROR4__(v680, 30)
                                                                          + v813 * __ROR4__(v680 + v665, 15));
                                                                    v682 = v680
                                                                         ^ (HIWORD(v808)
                                                                          * __ROR4__(v681 + 1419157410, 14)
                                                                          - __ROR4__(v681, 24));
                                                                    v683 = v681
                                                                         ^ __ROR4__(v682, 10)
                                                                         ^ (v806 * __ROR4__(v682 ^ 0xAB69605E, 12));
                                                                    v684 = v683
                                                                         ^ (HIWORD(v808)
                                                                          * (v813
                                                                           + __ROR4__(
                                                                               ~(v682
                                                                               ^ (v683 >> 10)
                                                                               ^ (WORD1(v808) * (v683 ^ HIWORD(v808)))),
                                                                               5)));
                                                                    v685 = v682
                                                                         ^ (v683 >> 10)
                                                                         ^ (WORD1(v808) * (v683 ^ HIWORD(v808)))
                                                                         ^ (v684 - HIWORD(v808))
                                                                         ^ 0xAB69605E;
                                                                    v686 = v684
                                                                         ^ ((v685 >> 2)
                                                                          + v806 * __ROR4__(v685 ^ HIWORD(v808), 30));
                                                                    v687 = v685
                                                                         ^ (__ROR4__(v686, 25)
                                                                          + WORD1(v808)
                                                                          * __ROR4__(v686 - HIDWORD(v808), 6));
                                                                    v688 = v686
                                                                         ^ (v813 * (v806 ^ v687) + __ROR4__(v687, 9));
                                                                    v689 = v687
                                                                         ^ (__ROR4__(v688, 25)
                                                                          + HIWORD(v808)
                                                                          * __ROR4__(v688 ^ WORD1(v808), 27));
                                                                    v665 = HIDWORD(v808);
                                                                    v690 = HIDWORD(v808) ^ v688 ^ v689 ^ 0xAB69605E;
                                                                    v691 = v689
                                                                         ^ (v806 * (__ROR4__(v690, 3) - WORD1(v808)));
                                                                    v692 = v690
                                                                         ^ (v813 * __ROR4__(v691 - HIDWORD(v808), 1)
                                                                          - __ROR4__(v691, 6));
                                                                    v693 = v691
                                                                         ^ (__ROR4__(v692, 18)
                                                                          + HIWORD(v808)
                                                                          * __ROR4__(v692 - 1419157410, 29));
                                                                    v694 = v692
                                                                         ^ (v806 * __ROR4__(v693 - 1419157410, 17)
                                                                          - __ROR4__(v693, 14));
                                                                    v695 = v693
                                                                         ^ (v694 >> 3)
                                                                         ^ (WORD1(v808) * (v813 ^ v694));
                                                                    v652 = v694
                                                                         ^ v669
                                                                         ^ __ROR4__(v695, 30)
                                                                         ^ (v813 * __ROR4__(HIDWORD(v808) ^ v695, 28));
                                                                    v664 = v695 ^ v666;
                                                                    v668[3] = v652;
                                                                    v668[7] = v695 ^ v666;
                                                                    v668[2] = __ROR4__(v652, 8);
                                                                    v668[6] = __ROR4__(v695 ^ v666, 8);
                                                                    v668[1] = __ROR4__(v652, 16);
                                                                    v668[5] = __ROR4__(v695 ^ v666, 16);
                                                                    *v668 = __ROR4__(v652, 24);
                                                                    v668[4] = __ROR4__(v695 ^ v666, 24);
                                                                    v669 = v671;
                                                                    v666 = v672;
                                                                    v668 += 8;
                                                                    ++v828;
                                                                  }
                                                                  while ( v828 < v670 );
                                                                  v650 = v805;
                                                                  v66 = v798;
                                                                  v8 = (unsigned __int16 *)v819;
                                                                  v10 = (HMODULE)v815;
                                                                  v544 = v797;
                                                                  v651 = (unsigned __int64)v814;
                                                                }
                                                                for ( j = 0; j < v651; ++j )
                                                                  v650 ^= *((_BYTE *)v816 + j);
                                                                if ( v650 != *(_QWORD *)(v651 + v823) )
                                                                {
                                                                  MemoryFree(v816);
                                                                  goto LABEL_892;
                                                                }
                                                                v697 = v796;
                                                                v797 = v544;
                                                                v698 = v802;
                                                                LODWORD(v813) = 0;
                                                                v808 = v816;
                                                                if ( (unsigned int)v814 < 4 )
                                                                {
                                                                  v699 = -1073741762;
                                                                  v486 = v544;
                                                                  v700 = Srca;
LABEL_940:
                                                                  v595 = v802;
LABEL_941:
                                                                  LODWORD(v805) = v699 | 0x10000000;
                                                                  goto LABEL_949;
                                                                }
                                                                v699 = RtlULongLongAdd(v816, 4, &v808);
                                                                if ( v699 < 0 )
                                                                  goto LABEL_938;
                                                                v699 = RtlUIntAdd(0, v701, &v813);
                                                                if ( v699 < 0 )
                                                                  goto LABEL_938;
                                                                if ( (int)v814 - (int)v813 >= (unsigned int)v704 )
                                                                {
                                                                  LODWORD(v810) = *(_DWORD *)v808;
                                                                  v699 = RtlULongLongAdd(v808, v704, &v808);
                                                                  if ( v699 < 0 )
                                                                    goto LABEL_938;
                                                                  v699 = RtlUIntAdd((unsigned int)v813, v705, &v813);
                                                                  if ( v699 < 0 )
                                                                    goto LABEL_938;
                                                                  if ( (int)v814 - (int)v813 >= (unsigned int)v810 )
                                                                  {
                                                                    v699 = RtlUIntAdd(
                                                                             (unsigned int)v813,
                                                                             (unsigned int)v810,
                                                                             &v813);
                                                                    if ( v699 < 0 )
                                                                      goto LABEL_938;
                                                                    v813 = (unsigned int)v810;
                                                                    v821 = (unsigned int)v814;
                                                                    if ( (char *)v816 + (unsigned int)v814 >= (char *)v808 + (unsigned int)v810
                                                                      && v821 + (_BYTE *)v816 - (_BYTE *)v808 - v813 < 8 )
                                                                    {
                                                                      LODWORD(v817) = *(_DWORD *)v816;
                                                                      v814 = 0;
                                                                      v828 = 0;
                                                                      v823 = 0;
                                                                      LODWORD(v806) = 0;
                                                                      if ( v808 )
                                                                      {
                                                                        v699 = RtlULongLongAdd(v808, v813, &v814);
                                                                        LODWORD(v805) = v699;
                                                                        v802 = v698;
                                                                        v804 = v708;
                                                                        v793 = v709;
                                                                        v797 = v544;
                                                                        if ( v699 < 0 )
                                                                        {
                                                                          v486 = v544;
LABEL_933:
                                                                          v700 = Srca;
                                                                          v595 = v802;
LABEL_934:
                                                                          v721 = Size;
                                                                          goto LABEL_935;
                                                                        }
                                                                        v819 = v706;
                                                                        if ( v706 < v814 )
                                                                        {
                                                                          while ( 1 )
                                                                          {
                                                                            v699 = RtlULongLongAdd(v706, v707, &v828);
                                                                            if ( v699 < 0 )
                                                                              break;
                                                                            if ( v828 > (unsigned __int64)v814 )
                                                                            {
                                                                              v699 = -1073741811;
LABEL_918:
                                                                              v486 = v797;
                                                                              goto LABEL_939;
                                                                            }
                                                                            v799 = 0;
                                                                            v699 = RtlUIntAdd(v711, *v710, &v799);
                                                                            if ( v699 < 0 )
                                                                              goto LABEL_918;
                                                                            v821 = (SIZE_T)v8;
                                                                            v802 = v10;
                                                                            v712 = v697;
                                                                            v812 = v697;
                                                                            v713 = v544;
                                                                            v840 = (HMODULE)v544;
                                                                            v700 = Srca;
                                                                            v832 = Srca;
                                                                            v815 = v801;
                                                                            v714 = v811;
                                                                            v824 = (SIZE_T)v811;
                                                                            lpMem = v816;
                                                                            v699 = RtlULongLongAdd(v819, v799, &v823);
                                                                            LODWORD(v805) = v699;
                                                                            v816 = lpMem;
                                                                            v811 = v714;
                                                                            v595 = v698;
                                                                            v801 = v815;
                                                                            v804 = v716;
                                                                            v793 = v715;
                                                                            v486 = v713;
                                                                            v797 = v713;
                                                                            v796 = v712;
                                                                            v10 = (HMODULE)v802;
                                                                            v8 = (unsigned __int16 *)v821;
                                                                            if ( v699 < 0 )
                                                                              goto LABEL_934;
                                                                            v706 = (void *)v823;
                                                                            v819 = (LPVOID)v823;
                                                                            v717 = v814;
                                                                            v804 = v716;
                                                                            v793 = v715;
                                                                            if ( v823 > (unsigned __int64)v814 )
                                                                            {
                                                                              v699 = -1073741811;
                                                                              v816 = lpMem;
                                                                              v811 = (LPVOID)v824;
                                                                              v801 = v815;
                                                                              v797 = v486;
                                                                              v796 = v812;
                                                                              goto LABEL_941;
                                                                            }
                                                                            LODWORD(v806) = v806 + 1;
                                                                            v816 = lpMem;
                                                                            v811 = (LPVOID)v824;
                                                                            v698 = v595;
                                                                            v802 = v595;
                                                                            v801 = v815;
                                                                            v544 = (SIZE_T)v840;
                                                                            v797 = (SIZE_T)v840;
                                                                            v697 = v812;
                                                                            v796 = v812;
                                                                            if ( v823 >= (unsigned __int64)v814 )
                                                                            {
                                                                              v816 = lpMem;
                                                                              v811 = (LPVOID)v824;
                                                                              v802 = v698;
                                                                              v801 = v815;
                                                                              Srca = (unsigned __int8 *)v832;
                                                                              v804 = v716;
                                                                              v793 = v715;
                                                                              v486 = (SIZE_T)v840;
                                                                              v797 = (SIZE_T)v840;
                                                                              v796 = v812;
                                                                              goto LABEL_920;
                                                                            }
                                                                          }
                                                                          v486 = v797;
                                                                          goto LABEL_933;
                                                                        }
                                                                        v486 = v544;
                                                                        v717 = v814;
LABEL_920:
                                                                        if ( v706 != v717 )
                                                                        {
                                                                          v699 = -1073741811;
LABEL_939:
                                                                          v700 = Srca;
                                                                          goto LABEL_940;
                                                                        }
                                                                      }
                                                                      else
                                                                      {
                                                                        LODWORD(v805) = 0;
                                                                        v802 = v698;
                                                                        v804 = v703;
                                                                        v793 = v702;
                                                                        v797 = v544;
                                                                        v486 = v544;
                                                                      }
                                                                      v718 = 0;
                                                                      if ( (_DWORD)v810 )
                                                                      {
                                                                        v719 = GetProcessHeap();
                                                                        v720 = v813;
                                                                        v718 = HeapAlloc(v719, 8u, v813);
                                                                        if ( !v718 )
                                                                        {
                                                                          v699 = -1073741801;
                                                                          goto LABEL_939;
                                                                        }
                                                                        LODWORD(v805) = 0;
                                                                      }
                                                                      else
                                                                      {
                                                                        v720 = v813;
                                                                      }
                                                                      if ( v808 )
                                                                        memcpy_0(v718, v808, v720);
                                                                      v807 = (size_t)v718;
                                                                      v721 = v806;
                                                                      LODWORD(Size) = v806;
                                                                      v699 = v805;
                                                                      v595 = v802;
                                                                      v700 = Srca;
LABEL_935:
                                                                      if ( v699 >= 0 && (_DWORD)v817 != v721 )
                                                                        v699 = -1073741762;
                                                                      goto LABEL_941;
                                                                    }
                                                                  }
                                                                }
                                                                v699 = -1073741762;
LABEL_938:
                                                                v802 = v698;
                                                                v793 = v702;
                                                                v804 = v703;
                                                                v486 = v544;
                                                                v797 = v544;
                                                                goto LABEL_939;
                                                              }
                                                            }
                                                          }
                                                          LODWORD(v805) = -805306355;
                                                        }
LABEL_893:
                                                        v595 = v802;
                                                        goto LABEL_947;
                                                      }
                                                      v821 = v630[1];
                                                      if ( v821 )
                                                      {
                                                        v645 = GetProcessHeap();
                                                        HeapFree(v645, 0, (LPVOID)v821);
                                                        v630 = (SIZE_T *)v814;
                                                        *((_QWORD *)v814 + 1) = 0;
                                                      }
                                                      v821 = v630[3];
                                                      if ( v821 )
                                                      {
                                                        v646 = GetProcessHeap();
                                                        HeapFree(v646, 0, (LPVOID)v821);
                                                        v630 = (SIZE_T *)v814;
                                                        *((_QWORD *)v814 + 3) = 0;
                                                      }
                                                      v821 = v630[5];
                                                      if ( v821 )
                                                      {
                                                        v647 = GetProcessHeap();
                                                        HeapFree(v647, 0, (LPVOID)v821);
                                                        *((_QWORD *)v814 + 5) = 0;
                                                      }
                                                      v648 = GetProcessHeap();
                                                      HeapFree(v648, 0, v814);
                                                      v811 = 0;
                                                      v610 = v813;
LABEL_859:
                                                      v644 = 0;
                                                      goto LABEL_860;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    v592 = -1073741811;
                                                  }
LABEL_767:
                                                  v587 = v592;
                                                  goto LABEL_763;
                                                }
                                              }
                                            }
                                          }
                                        }
                                        v797 = v544;
                                        v586 = GetProcessHeap();
                                        HeapFree(v586, 0, v815);
                                      }
                                      v585 = v813;
                                      goto LABEL_759;
                                    }
                                  }
                                  v557 = v793;
                                }
                                LODWORD(v806) = -1073741801;
                                v793 = v557;
                                v814 = 0;
                                v563 = v808;
                                v821 = *((_QWORD *)v808 + 1);
                                if ( v821 )
                                {
                                  v564 = GetProcessHeap();
                                  HeapFree(v564, 0, (LPVOID)v821);
                                  v563 = v808;
                                  *((_QWORD *)v808 + 1) = 0;
                                }
                                v821 = v563[3];
                                if ( v821 )
                                {
                                  v565 = GetProcessHeap();
                                  HeapFree(v565, 0, (LPVOID)v821);
                                  v563 = v808;
                                  *((_QWORD *)v808 + 3) = 0;
                                }
                                v821 = v563[5];
                                if ( v821 )
                                {
                                  v566 = GetProcessHeap();
                                  HeapFree(v566, 0, (LPVOID)v821);
                                  *((_QWORD *)v808 + 5) = 0;
                                }
                                v567 = GetProcessHeap();
                                HeapFree(v567, 0, v808);
                              }
                              else
                              {
                                LODWORD(v806) = -1073741801;
                                v544 = v797;
                                v545 = v796;
                              }
                              v546 = 0;
                              goto LABEL_718;
                            }
                            v824 = v829[1];
                            LODWORD(Size) = 0;
                            if ( v471 )
                            {
                              do
                              {
                                v799 = 0;
                                if ( (int)RtlUIntAdd((unsigned int)v466, *v472, &v799) < 0 )
                                  goto LABEL_617;
                                v796 = v474;
                                v797 = v448;
                                if ( (int)RtlULongLongAdd(lpMem, v799, &v824) < 0 )
                                  goto LABEL_991;
                                LODWORD(Size) = Size + 1;
                                v793 = v450;
                                v797 = v448;
                                v796 = v475;
                                v472 = (unsigned int *)v824;
                                lpMem = (LPVOID)v824;
                              }
                              while ( (unsigned int)Size < LODWORD(v829[0]) );
                            }
                            if ( (int)RtlULongLongAdd(v472, v466, &v837[4]) >= 0
                              && (unsigned __int64)lpMem + 12 <= v829[1] + HIDWORD(v829[0]) )
                            {
                              *(_DWORD *)lpMem = 8;
                              **(_QWORD **)&v837[4] = v821;
                              goto LABEL_672;
                            }
LABEL_617:
                            v432 = v804;
                            goto LABEL_618;
                          }
                        }
LABEL_513:
                        v66 = -1073425151;
LABEL_514:
                        LODWORD(v798) = v66;
                        goto LABEL_589;
                      }
LABEL_488:
                      v386 = GetProcessHeap();
                      HeapFree(v386, 0, v802);
                      goto LABEL_489;
                    }
                    v827 = *((_QWORD *)v830 + 1);
                    if ( v827 )
                    {
                      v315 = GetProcessHeap();
                      HeapFree(v315, 0, (LPVOID)v827);
                      v314[1] = 0;
                    }
                    v827 = v314[3];
                    if ( v827 )
                    {
                      v316 = GetProcessHeap();
                      HeapFree(v316, 0, (LPVOID)v827);
                      v314[3] = 0;
                    }
                    v827 = v314[5];
                    if ( v827 )
                    {
                      v317 = GetProcessHeap();
                      HeapFree(v317, 0, (LPVOID)v827);
                      v314[5] = 0;
                    }
                    v318 = GetProcessHeap();
                    HeapFree(v318, 0, v314);
                    v811 = 0;
LABEL_407:
                    v313 = 0;
                    goto LABEL_408;
                  }
LABEL_342:
                  v270 = v812;
LABEL_354:
                  v812 = v270;
                  goto LABEL_486;
                }
                v801 = v243;
                v244 = v798;
                v245 = GetProcessHeap();
                v246 = HeapAlloc(v245, 8u, v244);
                v819 = v246;
                if ( !v246 )
                {
LABEL_291:
                  LODWORD(v805) = -805306345;
                  v66 = -805306345;
                  LODWORD(v798) = -805306345;
                  goto LABEL_487;
                }
                v213 = v796;
                v797 = (SIZE_T)v44;
                v815 = v246;
                *v246 = *(_DWORD *)v801;
                v239 = RtlULongLongAdd(v246, 4, &v815);
                if ( v239 < 0 )
                {
                  v801 = v250;
                  v792 = v249;
                  Src = v248;
                  v819 = v247;
                }
                else
                {
                  memcpy_0(v815, v250[1], *(unsigned int *)v250);
                  v239 = RtlULongLongAdd(v815, *(unsigned int *)v801, &v815);
                  if ( v239 < 0
                    || (v252 = v815, *(_DWORD *)v815 = *(_DWORD *)v823, v239 = RtlULongLongAdd(v252, 4, &v815), v239 < 0) )
                  {
                    v801 = v251;
                  }
                  else
                  {
                    memcpy_0(v815, v251[3], *v253);
                    v239 = RtlULongLongAdd(v815, *(unsigned int *)v823, &v815);
                    if ( v239 < 0 )
                    {
                      v256 = v801;
                    }
                    else
                    {
                      v254 = v815;
                      *(_DWORD *)v815 = *(_DWORD *)pcchLength;
                      v239 = RtlULongLongAdd(v254, 4, &v815);
                      v256 = v801;
                      if ( v239 >= 0 )
                      {
                        memcpy_0(v815, *((const void **)v801 + 5), *v255);
                        v239 = RtlULongLongAdd(v815, *(unsigned int *)pcchLength, &v815);
                        if ( v239 >= 0 )
                        {
                          lpMem = v819;
                          LODWORD(Size) = v798;
                          goto LABEL_305;
                        }
                        goto LABEL_303;
                      }
                    }
                    v801 = v256;
                  }
                }
LABEL_303:
                v797 = (SIZE_T)v44;
                v257 = GetProcessHeap();
                HeapFree(v257, 0, v819);
                goto LABEL_305;
              }
            }
            v225 = Src;
          }
          v212 = -1073741801;
          v797 = (SIZE_T)v44;
          Src = v225;
          v814 = 0;
          v232 = v815;
          v827 = *((_QWORD *)v815 + 1);
          if ( v827 )
          {
            v233 = GetProcessHeap();
            HeapFree(v233, 0, (LPVOID)v827);
            v232 = v815;
            *((_QWORD *)v815 + 1) = 0;
          }
          v827 = v232[3];
          if ( v827 )
          {
            v234 = GetProcessHeap();
            HeapFree(v234, 0, (LPVOID)v827);
            v232 = v815;
            *((_QWORD *)v815 + 3) = 0;
          }
          v827 = v232[5];
          if ( v827 )
          {
            v235 = GetProcessHeap();
            HeapFree(v235, 0, (LPVOID)v827);
            *((_QWORD *)v815 + 5) = 0;
          }
          v236 = GetProcessHeap();
          HeapFree(v236, 0, v815);
        }
        else
        {
          v212 = -1073741801;
          v213 = v796;
        }
        v214 = 0;
        goto LABEL_263;
      }
      lpMem = (LPVOID)v825[1];
      LODWORD(v810) = 0;
      if ( v134 )
      {
        do
        {
          LODWORD(Size) = 0;
          v66 = RtlUIntAdd((unsigned int)v129, *v135, &Size);
          LODWORD(v798) = v66;
          if ( v66 < 0 )
            goto LABEL_122;
          v796 = v41;
          v797 = (SIZE_T)v44;
          Src = v65;
          v792 = v137;
          v66 = RtlULongLongAdd(v807, (unsigned int)Size, &lpMem);
          LODWORD(v798) = v66;
          if ( v66 < 0 )
            goto LABEL_122;
          LODWORD(v810) = v810 + 1;
          v792 = v138;
          Src = v65;
          v797 = (SIZE_T)v44;
          v796 = v41;
          v135 = (unsigned int *)lpMem;
          v807 = (size_t)lpMem;
        }
        while ( (unsigned int)v810 < v139 );
      }
      v66 = RtlULongLongAdd(v135, v129, &v822);
      LODWORD(v798) = v66;
      if ( v66 >= 0 )
      {
        if ( v807 + 8 <= v825[1] + HIDWORD(v825[0]) )
        {
          *(_DWORD *)v807 = v136;
          *v822 = v136;
          goto LABEL_206;
        }
LABEL_137:
        v66 = -1073741789;
        goto LABEL_121;
      }
LABEL_122:
      v809 = -1;
      LODWORD(v805) = -805306345;
      goto LABEL_589;
    }
    if ( *((_QWORD *)v826 + 14) )
    {
      EnterSplSem(0);
      IniKey = (struct _INIENVIRONMENT *)FindIniKey(*((_QWORD *)v839 + 6), szEnvironment, 0);
      v821 = (SIZE_T)IniKey;
      if ( !IniKey )
      {
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
          L"Could not find INIENVIRONMENT: '%ws'",
          szEnvironment);
        LODWORD(v13) = -2147418113;
        IniKey = (struct _INIENVIRONMENT *)v821;
      }
      if ( (int)v13 >= 0 )
      {
        DriverInEnvironment = FindDriverInEnvironment(*((const unsigned __int16 **)v826 + 14), IniKey);
        if ( DriverInEnvironment && (*((_BYTE *)DriverInEnvironment + 200) & 8) != 0 )
        {
          LocalSpoolerTelemetry::WriteDbgTraceInfo(
            "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
            L"Base driver '%ws' is already installed (referenced by driver '%ws')",
            *((_QWORD *)v826 + 14),
            *((_QWORD *)v826 + 1));
          LeaveSplSem(v757);
          goto LABEL_1033;
        }
        LeaveSplSem(v756);
        v849[0] = 0;
        ClassDriverFromWU = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, unsigned __int16 *, int, struct _PSETUP_LOCAL_DATA **))v808)(
                              0,
                              0,
                              *((_QWORD *)v826 + 14),
                              v833,
                              0x4000000,
                              v849);
        LODWORD(v13) = ClassDriverFromWU;
        if ( ClassDriverFromWU == -2147023099 )
        {
          ClassDriverFromWU = RetrieveClassDriverFromWU(v826, v849);
          LODWORD(v13) = ClassDriverFromWU;
          if ( ClassDriverFromWU == -2147023099 )
          {
            v820 = 1;
            v870 = -2147023099;
            v871 = 4;
            v872 = 0;
            SplLogType::SplLogType((SplLogType *)v895, *((const unsigned __int16 **)v826 + 14));
            SplLogType::SplLogType((SplLogType *)v896, *(const unsigned __int16 **)v826);
            v759 = SplLogType::SplLogType((SplLogType *)v897, *((const unsigned __int16 **)v826 + 1));
            SplLogEvent2(
              (const struct _EVENT_DESCRIPTOR *)SETUP_INSTALL_PRINTER_DRIVER_CLASS_DRIVER_UNAVAILABLE,
              v759,
              v760,
              v761,
              &v870,
              0);
            goto LABEL_1030;
          }
        }
        if ( ClassDriverFromWU >= 0 )
        {
          LocalSpoolerTelemetry::WriteDbgTraceInfo(
            "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
            L"Base driver '%ws' found in driver store (referenced by driver '%ws')",
            *((_QWORD *)v826 + 14),
            *((_QWORD *)v826 + 1));
          memset_0(v887, 0, 0x50u);
          v889 = v849[0];
          v890 = *((_QWORD *)v826 + 14);
          v891 = v833;
          v888 = v848;
          LODWORD(v13) = AddV4PrinterDriver((struct _SETUP_CONTEXT *)v887, v839);
          if ( (int)v13 >= 0 )
          {
            LODWORD(v13) = NPackageInstallLocalspl::AddPackageInfoToRegistry(
                             (NPackageInstallLocalspl *)v887,
                             v839,
                             v766);
            if ( (int)v13 >= 0 )
            {
LABEL_1030:
              if ( v849[0] && v44 )
                ((void (*)(void))v44)();
              goto LABEL_1033;
            }
          }
          v820 = 1;
          v876 = v13;
          v877 = 4;
          v878 = 0;
          SplLogType::SplLogType((SplLogType *)v907, *((const unsigned __int16 **)v826 + 14));
          SplLogType::SplLogType((SplLogType *)v902, *(const unsigned __int16 **)v826);
          v762 = SplLogType::SplLogType((SplLogType *)v903, *((const unsigned __int16 **)v826 + 1));
          v765 = &v876;
        }
        else
        {
          v820 = 1;
          v873 = v13;
          v874 = 4;
          v875 = 0;
          SplLogType::SplLogType((SplLogType *)v898, *((const unsigned __int16 **)v826 + 14));
          SplLogType::SplLogType((SplLogType *)v899, *(const unsigned __int16 **)v826);
          v762 = SplLogType::SplLogType((SplLogType *)v900, *((const unsigned __int16 **)v826 + 1));
          v765 = &v873;
        }
        SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_CLASS_DRIVER_FAILURE, v762, v763, v764, v765, 0);
        goto LABEL_1030;
      }
    }
  }
LABEL_1033:
  LODWORD(v804) = v13;
  if ( (int)v13 >= 0 )
  {
    if ( *((_DWORD *)v826 + 24) < 4u
      || (LODWORD(v13) = AddV4PrinterDriver((struct _SETUP_CONTEXT *)v882, v839), LODWORD(v804) = v13, (int)v13 >= 0) )
    {
      if ( *((_DWORD *)v826 + 24) < 4u
        || (LODWORD(v13) = NPackageInstallLocalspl::AddPackageInfoToRegistry((NPackageInstallLocalspl *)v882, v839, v61),
            (int)v13 >= 0) )
      {
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
          L"Installing color profiles");
        if ( ((unsigned int (__fastcall *)(unsigned __int16 *, _QWORD))v41)(v848, *((_QWORD *)v826 + 24)) )
        {
          v768 = 0;
          LODWORD(v13) = 0;
LABEL_1041:
          if ( *((_DWORD *)v826 + 24) < 4u )
          {
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
              L"Successfully installed color profiles.");
            v769 = GetLastError();
            v770 = *((_DWORD *)v826 + 43);
            if ( v770 )
              v771 = (const unsigned __int16 *)*((_QWORD *)v826 + 28);
            else
              v771 = 0;
            SplLogPrinterSetupCoreDriverEvent(
              &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED,
              L"InternalInstallPrinterDriverFromPackage",
              L"pfnPSetupInstallICMProfiles succeeded",
              0,
              v8,
              v834,
              *((const unsigned __int16 **)v826 + 23),
              v833,
              v770,
              v771,
              v769,
              v768);
          }
          v772 = v834;
          LocalSpoolerTelemetry::WriteDbgTraceInfo(
            "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
            L"Successfully installed the %ws printer driver.",
            v834);
          v773 = *((_DWORD *)v826 + 43);
          if ( v773 )
            v774 = (const unsigned __int16 *)*((_QWORD *)v826 + 28);
          else
            v774 = 0;
          SplLogPrinterSetupCoreDriverEvent(
            &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED,
            L"InternalInstallPrinterDriverFromPackage",
            0,
            0,
            v8,
            v772,
            *((const unsigned __int16 **)v826 + 23),
            v833,
            v773,
            v774,
            0,
            v13);
          goto LABEL_1060;
        }
        v768 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v767);
        LODWORD(v13) = v768;
        if ( v768 >= 0 )
          goto LABEL_1041;
        if ( *((_DWORD *)v826 + 24) < 4u )
        {
          hLibModule = 0;
          ConvertMultiToSingleSz(*((const unsigned __int16 **)v826 + 24), (unsigned __int16 **)&hLibModule);
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
            L"Error installing color profiles: hr: 0x%x",
            (unsigned int)v768);
          v775 = GetLastError();
          v776 = *((_DWORD *)v826 + 43);
          v777 = v776 ? (const unsigned __int16 *)*((_QWORD *)v826 + 28) : 0LL;
          v791 = v768;
          v778 = hLibModule;
          SplLogPrinterSetupCoreDriverEvent(
            &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
            L"InternalInstallPrinterDriverFromPackage",
            L"pfnPSetupInstallICMProfiles failed (profiles listed in additional info)",
            (const unsigned __int16 *)hLibModule,
            v8,
            v834,
            *((const unsigned __int16 **)v826 + 23),
            v833,
            v776,
            v777,
            v775,
            v791);
          if ( v778 )
            operator delete(v778, v779);
        }
      }
    }
  }
  if ( !v826 )
    goto LABEL_1063;
  if ( *((_DWORD *)v826 + 24) >= 4u && !v820 )
  {
    v879 = v13;
    v880 = 4;
    v881 = 0;
    SplLogType::SplLogType((SplLogType *)v904, *((const unsigned __int16 **)v826 + 14));
    SplLogType::SplLogType((SplLogType *)v905, *(const unsigned __int16 **)v826);
    v780 = SplLogType::SplLogType((SplLogType *)v906, v834);
    SplLogEvent2(&SETUP_INSTALL_V4_PRINTER_DRIVER_FAILED, v780, v781, v782, &v879, 0);
  }
LABEL_1060:
  if ( v826 && v44 )
  {
    ((void (*)(void))v44)();
    v826 = 0;
  }
LABEL_1063:
  if ( hToken )
    ImpersonatePrinterClient(hToken);
  if ( v10 )
    FreeLibrary(v10);
  if ( (int)v13 < 0 )
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage",
      L"Error installing the %ws printer driver: hr: 0x%x",
      v834,
      (unsigned int)v13);
  else
    LODWORD(v13) = (_DWORD)v804;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800adb34  push    rbx
0x1800adb36  push    rsi
0x1800adb37  push    rdi
0x1800adb38  push    r12
0x1800adb3a  push    r13
0x1800adb3c  push    r14
0x1800adb3e  push    r15
0x1800adb40  sub     rsp, 0CA0h
0x1800adb47  mov     rax, cs:__security_cookie
0x1800adb4e  xor     rax, rsp
0x1800adb51  mov     [rsp+0CD8h+var_48], rax
0x1800adb59  mov     rbx, r9
0x1800adb5c  mov     [rsp+0CD8h+var_B30], rbx
0x1800adb64  mov     rdi, r8
0x1800adb67  mov     [rsp+0CD8h+var_B28], r8
0x1800adb6f  mov     r12, rdx
0x1800adb72  mov     [rsp+0CD8h+var_AD0], rcx
0x1800adb7a  mov     [rsp+0CD8h+var_B60], rcx
0x1800adb82  mov     [rsp+0CD8h+var_BD8], rdx
0x1800adb8a  mov     [rsp+0CD8h+var_B90], r8
0x1800adb92  mov     [rsp+0CD8h+pcchLength], rbx
0x1800adb9a  mov     r14, qword ptr [rsp+0CD8h+arg_28]
0x1800adba2  mov     [rsp+0CD8h+var_B00], r14
0x1800adbaa  xor     r15d, r15d
0x1800adbad  mov     r13d, r15d
0x1800adbb0  mov     [rsp+0CD8h+var_C10], r15
0x1800adbb8  mov     [rsp+0CD8h+var_B70], r15
0x1800adbc0  mov     [rsp+0CD8h+hToken], r15
0x1800adbc8  mov     esi, 30010h
0x1800adbcd  mov     dword ptr [rsp+0CD8h+var_BE0], esi
0x1800adbd4  mov     dword ptr [rsp+0CD8h+var_C58], esi
0x1800adbdb  mov     eax, 0FFFFh
0x1800adbe0  mov     word ptr [rsp+0CD8h+var_C20], ax
0x1800adbe8  xor     edx, edx; Val
0x1800adbea  mov     r8d, 208h; Size
0x1800adbf0  lea     rcx, [rsp+0CD8h+var_258]; void *
0x1800adbf8  call    memset_0
0x1800adbfd  test    rdi, rdi
0x1800adc00  jz      loc_1800AE425
0x1800adc06  test    rbx, rbx
0x1800adc09  jz      loc_1800AE425
0x1800adc0f  test    r14, r14
0x1800adc12  jz      loc_1800AE425
0x1800adc18  mov     ebx, dword ptr [rsp+0CD8h+arg_20]
0x1800adc1f  btr     ebx, 1Ah
0x1800adc23  mov     dword ptr [rsp+0CD8h+var_CA8], ebx
0x1800adc27  mov     r14, [rsp+0CD8h+var_B30]
0x1800adc2f  mov     [rsp+0CD8h+var_CB0], r14
0x1800adc34  mov     [rsp+0CD8h+var_CB8], r12
0x1800adc39  mov     r9, [rsp+0CD8h+var_AD0]
0x1800adc41  mov     r8, rdi
0x1800adc44  lea     rdx, aInstallingWsPr; "Installing %ws printer driver with pszS"...
0x1800adc4b  lea     rcx, aNpackageinstal_11; "NPackageInstallLocalspl::InternalInstal"...
0x1800adc52  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800adc57  lea     rdx, [rsp+0CD8h+var_C20]
0x1800adc5f  mov     rcx, r14
0x1800adc62  call    GetProcessorArchitectureFromEnvironmentString
0x1800adc67  mov     r14d, eax
0x1800adc6a  mov     dword ptr [rsp+0CD8h+dwBytes], eax
0x1800adc71  test    eax, eax
0x1800adc73  jns     short loc_1800ADCC9
0x1800adc75  mov     [rsp+0CD8h+var_C80], eax; unsigned int
0x1800adc79  mov     [rsp+0CD8h+var_C88], 57h ; 'W'; unsigned int
0x1800adc81  mov     [rsp+0CD8h+var_C90], r15; unsigned __int16 *
0x1800adc86  mov     [rsp+0CD8h+var_C98], r15d; int
0x1800adc8b  mov     rax, [rsp+0CD8h+var_B30]
0x1800adc93  mov     [rsp+0CD8h+var_CA0], rax; unsigned __int16 *
0x1800adc98  mov     [rsp+0CD8h+var_CA8], r15; unsigned __int16 *
0x1800adc9d  mov     [rsp+0CD8h+var_CB0], rdi; unsigned __int16 *
0x1800adca2  lea     r8, aGetprocessorar; "GetProcessorArchitectureFromEnvironment"...
0x1800adca9  xor     r9d, r9d; unsigned __int16 *
0x1800adcac  mov     [rsp+0CD8h+var_CB8], r12; unsigned __int16 *
0x1800adcb1  lea     rdx, aInternalinstal; "InternalInstallPrinterDriverFromPackage"
0x1800adcb8  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x1800adcbf  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x1800adcc4  jmp     loc_1800AE4C2
0x1800adcc9  call    ?GetDriverValidationPolicyLevel@@YA?AW4_DRIVER_VALIDATION_LEVEL@@XZ; GetDriverValidationPolicyLevel(void)
0x1800adcce  mov     edi, eax
0x1800adcd0  call    ?IsTestSigningEnabled@@YAHXZ; IsTestSigningEnabled(void)
0x1800adcd5  test    eax, eax
0x1800adcd7  jnz     loc_1800ADD61
0x1800adcdd  cmp     edi, 3
0x1800adce0  ja      short loc_1800ADD61
0x1800adce2  test    r12, r12
0x1800adce5  jz      short loc_1800ADD0C
0x1800adce7  mov     rdx, r12
0x1800adcea  mov     ecx, edi
0x1800adcec  call    ?ValidateDriver@@YAJW4_DRIVER_VALIDATION_LEVEL@@PEBG@Z; ValidateDriver(_DRIVER_VALIDATION_LEVEL,ushort const *)
0x1800adcf1  mov     r14d, eax
0x1800adcf4  mov     dword ptr [rsp+0CD8h+dwBytes], eax
0x1800adcfb  test    eax, eax
0x1800adcfd  jns     short loc_1800ADD03
0x1800adcff  mov     edx, eax
0x1800add01  jmp     short loc_1800ADD1D
0x1800add03  mov     [rsp+0CD8h+var_C00], ebx
0x1800add0a  jmp     short loc_1800ADD71
0x1800add0c  mov     r14d, 800B0004h
0x1800add12  mov     edx, r14d
0x1800add15  mov     dword ptr [rsp+0CD8h+dwBytes], r14d
0x1800add1d  mov     ecx, edx; int
0x1800add1f  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800add24  mov     [rsp+0CD8h+var_C80], edx
0x1800add28  mov     [rsp+0CD8h+var_C88], eax
0x1800add2c  mov     [rsp+0CD8h+var_C90], r15
0x1800add31  mov     [rsp+0CD8h+var_C98], r15d
0x1800add36  mov     rax, [rsp+0CD8h+var_B30]
0x1800add3e  mov     [rsp+0CD8h+var_CA0], rax
0x1800add43  mov     [rsp+0CD8h+var_CA8], r15
0x1800add48  mov     rax, [rsp+0CD8h+var_B28]
0x1800add50  mov     [rsp+0CD8h+var_CB0], rax
0x1800add55  lea     r8, aValidatedriver_0; "ValidateDriver failed"
0x1800add5c  jmp     loc_1800ADCA9
0x1800add61  mov     [rsp+0CD8h+var_C00], ebx
0x1800add68  test    r12, r12
0x1800add6b  jz      loc_1800ADEAC
0x1800add71  mov     rcx, r12
0x1800add74  call    IsInInfDir
0x1800add79  test    eax, eax
0x1800add7b  jz      loc_1800ADF23
0x1800add81  xor     r8d, r8d; dwFlags
0x1800add84  xor     edx, edx; hFile
0x1800add86  lea     rcx, LibFileName; "setupapi.dll"
0x1800add8d  call    cs:__imp_LoadLibraryExW
0x1800add93  mov     rdi, rax
0x1800add96  mov     [rsp+0CD8h+hLibModule], rax
0x1800add9e  test    rax, rax
0x1800adda1  jnz     short loc_1800ADDBA
0x1800adda3  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800adda8  mov     r14d, eax
0x1800addab  mov     dword ptr [rsp+0CD8h+dwBytes], eax
0x1800addb2  test    eax, eax
0x1800addb4  js      loc_1800ADE76
0x1800addba  lea     rdx, aSetupgetinfdri_0; "SetupGetInfDriverStoreLocationW"
0x1800addc1  mov     rcx, rdi; hModule
0x1800addc4  call    cs:__imp_GetProcAddress
0x1800addca  mov     rdi, rax
0x1800addcd  test    rax, rax
0x1800addd0  jnz     short loc_1800ADDE9
0x1800addd2  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800addd7  mov     r14d, eax
0x1800addda  mov     dword ptr [rsp+0CD8h+dwBytes], eax
0x1800adde1  test    eax, eax
0x1800adde3  js      loc_1800ADE76
0x1800adde9  mov     [rsp+0CD8h+var_6D0], r15
0x1800addf1  mov     [rsp+0CD8h+var_6C6], r15
0x1800addf9  mov     [rsp+0CD8h+var_6BE], r15w
0x1800ade02  mov     [rsp+0CD8h+var_6D8], 1Ch
0x1800ade0d  mov     [rsp+0CD8h+var_6D4], 2
0x1800ade18  movzx   eax, word ptr [rsp+0CD8h+var_C20]
0x1800ade20  mov     [rsp+0CD8h+var_6C8], ax
0x1800ade28  mov     [rsp+0CD8h+var_CB0], r15
0x1800ade2d  mov     dword ptr [rsp+0CD8h+var_CB8], 104h
0x1800ade35  lea     r9, [rsp+0CD8h+var_258]
0x1800ade3d  xor     r8d, r8d
0x1800ade40  lea     rdx, [rsp+0CD8h+var_6D8]
0x1800ade48  mov     rcx, r12
0x1800ade4b  mov     rax, rdi
0x1800ade4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ade53  test    eax, eax
0x1800ade55  jz      short loc_1800ADE67
0x1800ade57  mov     r14d, r15d
0x1800ade5a  mov     dword ptr [rsp+0CD8h+dwBytes], r15d
0x1800ade62  mov     edi, r15d
0x1800ade65  jmp     short loc_1800ADE78
0x1800ade67  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800ade6c  mov     r14d, eax
0x1800ade6f  mov     dword ptr [rsp+0CD8h+dwBytes], eax
0x1800ade76  mov     edi, eax
0x1800ade78  lea     rax, [rsp+0CD8h+var_258]
0x1800ade80  test    edi, edi
0x1800ade82  cmovs   rax, r12
0x1800ade86  mov     r12, rax
0x1800ade89  mov     rcx, [rsp+0CD8h+hLibModule]; hLibModule
0x1800ade91  test    rcx, rcx
0x1800ade94  jz      short loc_1800ADE9C
0x1800ade96  call    cs:__imp_FreeLibrary
0x1800ade9c  mov     [rsp+0CD8h+var_BD8], r12
0x1800adea4  test    edi, edi
0x1800adea6  js      loc_1800ADF57
0x1800adeac  mov     eax, ebx
0x1800adeae  not     eax
0x1800adeb0  and     eax, 1
0x1800adeb3  lea     ecx, ds:4[rax*4]
0x1800adeba  or      ecx, esi
0x1800adebc  mov     esi, ecx
0x1800adebe  bts     esi, 12h
0x1800adec2  bt      ebx, 1Bh
0x1800adec6  cmovnb  esi, ecx
0x1800adec9  mov     dword ptr [rsp+0CD8h+var_BE0], esi
0x1800aded0  call    cs:__imp_RevertToPrinterSelf
0x1800aded6  mov     [rsp+0CD8h+hLibModule], rax
0x1800adede  test    rax, rax
0x1800adee1  jz      loc_1800AE001
0x1800adee7  xor     edx, edx; hFile
0x1800adee9  mov     r8d, 800h; dwFlags
0x1800adeef  lea     rcx, aNtprintDll; "ntprint.dll"
0x1800adef6  call    cs:__imp_LoadLibraryExW
0x1800adefc  mov     r13, rax
0x1800adeff  mov     [rsp+0CD8h+var_C10], rax
0x1800adf07  test    rax, rax
0x1800adf0a  jz      loc_1800ADFB6
0x1800adf10  mov     edi, r15d
0x1800adf13  mov     r14d, r15d
0x1800adf16  mov     dword ptr [rsp+0CD8h+dwBytes], r15d
0x1800adf1e  jmp     loc_1800ADFE1
0x1800adf23  mov     rcx, r12; Str
0x1800adf26  call    IsInfInDriverStore
0x1800adf2b  test    eax, eax
0x1800adf2d  jnz     loc_1800ADEAC
0x1800adf33  mov     r14d, 80070057h
0x1800adf39  mov     dword ptr [rsp+0CD8h+dwBytes], r14d
0x1800adf41  mov     r8, r12
0x1800adf44  lea     rdx, aInvalidInfPath; "Invalid INF path passed into InstallPri"...
0x1800adf4b  lea     rcx, aNpackageinstal_11; "NPackageInstallLocalspl::InternalInstal"...
0x1800adf52  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800adf57  call    cs:__imp_GetLastError
0x1800adf5d  mov     [rsp+0CD8h+var_C80], r14d; unsigned int
0x1800adf62  mov     [rsp+0CD8h+var_C88], eax; unsigned int
0x1800adf66  mov     [rsp+0CD8h+var_C90], r15; unsigned __int16 *
0x1800adf6b  mov     [rsp+0CD8h+var_C98], r15d; int
0x1800adf70  mov     rax, [rsp+0CD8h+var_B30]
0x1800adf78  mov     [rsp+0CD8h+var_CA0], rax; unsigned __int16 *
0x1800adf7d  mov     [rsp+0CD8h+var_CA8], r15; unsigned __int16 *
0x1800adf82  mov     rax, [rsp+0CD8h+var_B28]
0x1800adf8a  mov     [rsp+0CD8h+var_CB0], rax; unsigned __int16 *
0x1800adf8f  mov     [rsp+0CD8h+var_CB8], r12; unsigned __int16 *
0x1800adf94  xor     r9d, r9d; unsigned __int16 *
0x1800adf97  lea     r8, aIsinfindrivers; "IsInfInDriverStore failed"
0x1800adf9e  lea     rdx, aInternalinstal; "InternalInstallPrinterDriverFromPackage"
0x1800adfa5  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x1800adfac  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x1800adfb1  jmp     loc_1800AE4C9
0x1800adfb6  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800adfbb  mov     edi, eax
0x1800adfbd  mov     r14d, eax
0x1800adfc0  mov     dword ptr [rsp+0CD8h+dwBytes], eax
0x1800adfc7  test    eax, eax
0x1800adfc9  jns     short loc_1800ADFE1
0x1800adfcb  mov     r8d, eax
0x1800adfce  lea     rdx, aFailedToLoadNt; "Failed to load ntprint.dll, hr: 0x%x"
0x1800adfd5  lea     rcx, aNpackageinstal_11; "NPackageInstallLocalspl::InternalInstal"...
0x1800adfdc  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800adfe1  mov     rcx, [rsp+0CD8h+hLibModule]; hToken
0x1800adfe9  call    cs:__imp_ImpersonatePrinterClient
0x1800adfef  test    eax, eax
0x1800adff1  jnz     short loc_1800AE029
0x1800adff3  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800adff8  lea     rdx, aFailedToImpers_0; "Failed to impersonate printer client, h"...
0x1800adfff  jmp     short loc_1800AE00D
0x1800ae001  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800ae006  lea     rdx, aFailedToRevert_2; "Failed to revert to Spooler service for"...
0x1800ae00d  mov     r14d, eax
0x1800ae010  mov     dword ptr [rsp+0CD8h+dwBytes], eax
0x1800ae017  mov     r8d, eax
0x1800ae01a  lea     rcx, aNpackageinstal_11; "NPackageInstallLocalspl::InternalInstal"...
0x1800ae021  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800ae026  mov     edi, r14d
0x1800ae029  test    edi, edi
0x1800ae02b  jns     short loc_1800AE093
0x1800ae02d  call    cs:__imp_GetLastError
0x1800ae033  mov     [rsp+0CD8h+var_C80], r14d; unsigned int
0x1800ae038  mov     [rsp+0CD8h+var_C88], eax; unsigned int
0x1800ae03c  mov     [rsp+0CD8h+var_C90], r15; unsigned __int16 *
0x1800ae041  mov     [rsp+0CD8h+var_C98], r15d; int
0x1800ae046  mov     rax, [rsp+0CD8h+var_B30]
0x1800ae04e  mov     [rsp+0CD8h+var_CA0], rax; unsigned __int16 *
0x1800ae053  mov     [rsp+0CD8h+var_CA8], r15; unsigned __int16 *
0x1800ae058  mov     rax, [rsp+0CD8h+var_B28]
0x1800ae060  mov     [rsp+0CD8h+var_CB0], rax; unsigned __int16 *
0x1800ae065  mov     [rsp+0CD8h+var_CB8], r12; unsigned __int16 *
0x1800ae06a  xor     r9d, r9d; unsigned __int16 *
0x1800ae06d  lea     r8, aLoadlibraryNtp; "LoadLibrary(ntprint.dll) failed"
0x1800ae074  lea     rdx, aInternalinstal; "InternalInstallPrinterDriverFromPackage"
0x1800ae07b  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x1800ae082  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x1800ae087  mov     dword ptr [rsp+0CD8h+var_C58], esi
0x1800ae08e  jmp     loc_1800AE4C9
0x1800ae093  lea     rdx, aPsetupparseinf; "PSetupParseInfAndCommitFileQueue"
0x1800ae09a  mov     rcx, r13; hModule
0x1800ae09d  call    cs:__imp_GetProcAddress
0x1800ae0a3  mov     [rsp+0CD8h+var_C08], rax
0x1800ae0ab  mov     [rsp+0CD8h+var_BD0], rax
0x1800ae0b3  test    rax, rax
0x1800ae0b6  jnz     loc_1800AE13C
0x1800ae0bc  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800ae0c1  mov     r14d, eax
0x1800ae0c4  mov     dword ptr [rsp+0CD8h+dwBytes], eax
0x1800ae0cb  test    eax, eax
0x1800ae0cd  jns     short loc_1800AE13C
0x1800ae0cf  call    cs:__imp_GetLastError
0x1800ae0d5  mov     [rsp+0CD8h+var_C80], r14d; unsigned int
0x1800ae0da  mov     [rsp+0CD8h+var_C88], eax; unsigned int
0x1800ae0de  mov     [rsp+0CD8h+var_C90], r15; unsigned __int16 *
0x1800ae0e3  mov     [rsp+0CD8h+var_C98], r15d; int
0x1800ae0e8  mov     rax, [rsp+0CD8h+var_B30]
0x1800ae0f0  mov     [rsp+0CD8h+var_CA0], rax; unsigned __int16 *
0x1800ae0f5  mov     [rsp+0CD8h+var_CA8], r15; unsigned __int16 *
0x1800ae0fa  mov     rax, [rsp+0CD8h+var_B28]
0x1800ae102  mov     [rsp+0CD8h+var_CB0], rax; unsigned __int16 *
0x1800ae107  mov     [rsp+0CD8h+var_CB8], r12; unsigned __int16 *
  ... truncated ...
```
