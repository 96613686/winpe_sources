# DllMain_Sni(HINSTANCE__ *,ulong,void *)

- ea: `0x100412c0c`
- end: `0x100412dbb`
- name: `?DllMain_Sni@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `431`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x100545a0c`
- `0x100545dd4`

## callees

- `0x100412c0c`
- `0x100413d10`
- `0x10043a324`
- `0x10043a480`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x100412cb2`
- `KERNEL32!SetLastError` at `0x100412d1f`
- `KERNEL32!SetLastError` at `0x100412cb2`
- `KERNEL32!SetLastError` at `0x100412d1f`

## pseudocode

```c

```
