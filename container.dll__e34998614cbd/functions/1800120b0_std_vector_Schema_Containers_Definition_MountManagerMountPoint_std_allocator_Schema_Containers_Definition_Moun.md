# std::vector<Schema::Containers::Definition::MountManagerMountPoint,std::allocator<Schema::Containers::Definition::MountManagerMountPoint>>::_Xlength(void)

- ea: `0x1800120b0`
- end: `0x1800120c8`
- name: `?_Xlength@?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@CAXXZ`
- size: `24`
- prototype: ``
- caller_count: `22`
- callee_count: `0`
- tags: `reparse_path`

## callers

- `0x18000cac4`
- `0x18001adac`
- `0x18001afe0`
- `0x18001b214`
- `0x18001b480`
- `0x18001b7e0`
- `0x18001b9bc`
- `0x18001bbc8`
- `0x18001be38`
- `0x18001c08c`
- `0x18001c314`
- `0x18001c574`
- `0x18001c7e4`
- `0x18001ca60`
- `0x18001cd4c`
- `0x18001cf94`
- `0x18001d1e0`
- `0x18001d894`
- `0x18001d9d0`
- `0x1800228a8`
- `0x180024078`
- `0x18002841c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800120bb`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800120bb`

## pseudocode

```c
void __noreturn std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x1800120b0  sub     rsp, 28h
0x1800120b4  lea     rcx, aVectorTooLong; "vector too long"
0x1800120bb  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
