# CopyClientString(ushort *,ulong,uchar,_UNICODE_STRING *)

- ea: `0x18004ad00`
- end: `0x18004b02a`
- name: `?CopyClientString@@YAJPEAGKEPEAU_UNICODE_STRING@@@Z`
- size: `810`
- prototype: `int(unsigned __int16 *, unsigned int, unsigned __int8, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180008d14`

## callees

- `0x180006c50`
- `0x180007700`
- `0x18002ee7c`
- `0x18002f014`
- `0x18004ad00`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlOemStringToUnicodeString` at `0x18004af7f`
- `ntdll!RtlOemStringToUnicodeString` at `0x18004af7f`

## pseudocode

```c

```
