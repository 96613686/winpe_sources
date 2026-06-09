# PushApphelpp_Match(int *,_PUSHAPPHELP_PAYLOAD *,ITelecommandCache *,ushort const *,uint)

- ea: `0x1800b1b24`
- end: `0x1800b1f3e`
- name: `?PushApphelpp_Match@@YAKPEAHPEAU_PUSHAPPHELP_PAYLOAD@@PEAVITelecommandCache@@PEBGI@Z`
- size: `1050`
- prototype: `unsigned int(int *, struct _PUSHAPPHELP_PAYLOAD *, struct ITelecommandCache *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800b15f0`

## callees

- `0x180005180`
- `0x18000b6f0`
- `0x18000dcc0`
- `0x18000f6c4`
- `0x180012920`
- `0x18001b320`
- `0x18001e688`
- `0x18007a9cf`
- `0x1800b1b24`
- `0x1800ee46c`
- `0x1800f7010`

## import_xrefs

- `msvcrt!swscanf_s` at `0x1800b1e16`
- `msvcrt!swscanf_s` at `0x1800b1e68`
- `msvcrt!swscanf_s` at `0x1800b1eab`
- `msvcrt!swscanf_s` at `0x1800b1e16`
- `msvcrt!swscanf_s` at `0x1800b1e68`
- `msvcrt!swscanf_s` at `0x1800b1eab`
- `msvcrt!_wcsicmp` at `0x1800b1cfc`
- `msvcrt!_wcsicmp` at `0x1800b1d30`
- `msvcrt!_wcsicmp` at `0x1800b1cfc`
- `msvcrt!_wcsicmp` at `0x1800b1d30`

## string_xrefs

- `0x1800b1c46`: `Telecommand,Skipped,FileName not specified`
- `0x1800b1ba6`: `Failed to load telecommand cache [%d]`
- `0x1800b1c13`: `Failed to read telecommand parameters [%d]`
- `0x1800b1de4`: `FwLink`
- `0x1800b1c5f`: `No FileName parameter for PUSHAPPHELP Telecommand`
- `0x1800b1ec7`: `Skipped,FwLink not found`
- `0x1800b1e20`: `Bad FwLink: %S`

## pseudocode

```c

```
