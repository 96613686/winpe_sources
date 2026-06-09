# PrintFriendlyDebugMessage(_EXCEPTION_POINTERS *,void *,int,char const *)

- ea: `0x1801881e0`
- end: `0x180188289`
- name: `?PrintFriendlyDebugMessage@@YAXPEAU_EXCEPTION_POINTERS@@PEAXHPEBD@Z`
- size: `169`
- prototype: `void __fastcall(_EXCEPTION_POINTERS *lpep, void *pvObject, int fFunc, const char *szPossibleCause)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180187ea8`
- `0x180187f60`
- `0x180188060`
- `0x1801b5e90`

## callees

- `0x1801881e0`

## import_xrefs

- `ntdll!DbgPrint` at `0x18018820c`
- `ntdll!DbgPrint` at `0x180188226`
- `ntdll!DbgPrint` at `0x18018823f`
- `ntdll!DbgPrint` at `0x18018824e`
- `ntdll!DbgPrint` at `0x18018825b`
- `ntdll!DbgPrint` at `0x18018826b`
- `ntdll!DbgPrint` at `0x180188278`
- `ntdll!DbgPrint` at `0x18018820c`
- `ntdll!DbgPrint` at `0x180188226`
- `ntdll!DbgPrint` at `0x18018823f`
- `ntdll!DbgPrint` at `0x18018824e`
- `ntdll!DbgPrint` at `0x18018825b`
- `ntdll!DbgPrint` at `0x18018826b`
- `ntdll!DbgPrint` at `0x180188278`

## string_xrefs

- `0x180188238`: `The object we attempted to call is at %p.\n`
- `0x180188247`: `The function we attempted to call is at %p.\n`

## pseudocode

```c

```
