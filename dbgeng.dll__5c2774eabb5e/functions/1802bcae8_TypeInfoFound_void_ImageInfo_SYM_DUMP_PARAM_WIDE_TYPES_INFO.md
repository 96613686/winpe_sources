# TypeInfoFound(void *,ImageInfo *,_SYM_DUMP_PARAM_WIDE *,_TYPES_INFO *)

- ea: `0x1802bcae8`
- end: `0x1802bd70d`
- name: `?TypeInfoFound@@YAKPEAXPEAVImageInfo@@PEAU_SYM_DUMP_PARAM_WIDE@@PEAU_TYPES_INFO@@@Z`
- size: `3109`
- prototype: `unsigned int __fastcall(void *, struct ImageInfo *, struct _SYM_DUMP_PARAM_WIDE *, struct _TYPES_INFO *)`
- caller_count: `7`
- callee_count: `31`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801da770`
- `0x1801dc2c0`
- `0x1801dd4a0`
- `0x1802afad8`
- `0x1802b25cc`
- `0x1802bc8d4`
- `0x1802db088`

## callees

- `0x1800793cc`
- `0x18007c2dc`
- `0x180081918`
- `0x180085440`
- `0x18008b234`
- `0x18008e740`
- `0x180093c88`
- `0x1800986ec`
- `0x18009a324`
- `0x1800f0f40`
- `0x1800f2560`
- `0x180159910`
- `0x18016497c`
- `0x18019a094`
- `0x18019a800`
- `0x1801d7e30`
- `0x1802674c4`
- `0x180289d2c`
- `0x1802adc1c`
- `0x1802b1658`
- `0x1802b1848`
- `0x1802b2890`
- `0x1802b3b08`
- `0x1802bcae8`
- `0x1802bd714`
- `0x1802bd938`
- `0x1802da870`
- `0x1802da8c4`
- `0x1802de3c0`
- `0x1804da4c0`
- `0x1804da880`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802bd648`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802bd648`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802bccb6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802bd1c1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802bccb6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802bd1c1`
- `dbghelp!SymFromAddrW` at `0x1802bcdce`
- `dbghelp!SymFromAddrW` at `0x1802bcdce`
- `dbghelp!SymLoadModuleExW` at `0x1802bd4d5`
- `dbghelp!SymLoadModuleExW` at `0x1802bd4d5`
- `dbghelp!SymGetModuleInfoW64` at `0x1802bd43b`
- `dbghelp!SymGetModuleInfoW64` at `0x1802bd502`
- `dbghelp!SymGetModuleInfoW64` at `0x1802bd43b`
- `dbghelp!SymGetModuleInfoW64` at `0x1802bd502`

## string_xrefs

- `0x1802bccd2`: `ntdll`
- `0x1802bd67c`: `*************************************************************************\n***                                                                   ***\n***                                                                   ***\n***    Your debugger is not using the correct symbols                 ***\n***                                                                   ***\n***    In order for this command to work properly, your symbol path   ***\n***    must point to .pdb files that have full typ`
- `0x1802bd675`: `*************************************************************************\n***                                                                   ***\n***                                                                   ***\n***    Either you specified an unqualified symbol, or your debugger   ***\n***    doesn't have full symbol information.  Unqualified symbol      ***\n***    resolution is turned off by default. Please either specify a   ***\n***    fully qualified symbol module!symbolname, o`

## pseudocode

```c

```
