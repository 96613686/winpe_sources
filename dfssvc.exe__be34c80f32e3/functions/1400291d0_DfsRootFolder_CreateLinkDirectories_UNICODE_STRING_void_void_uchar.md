# DfsRootFolder::CreateLinkDirectories(_UNICODE_STRING *,void *,void * *,uchar *)

- ea: `0x1400291d0`
- end: `0x1400293bd`
- name: `?CreateLinkDirectories@DfsRootFolder@@AEAAJPEAU_UNICODE_STRING@@PEAXPEAPEAXPEAE@Z`
- size: `493`
- prototype: `__int64 __usercall@<rax>(DfsRootFolder *__hidden this@<rcx>, struct _UNICODE_STRING *@<rdx>, void *@<r8>, void **@<r9>, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400296d8`
- `0x14002bdc8`

## callees

- `0x14000fd24`
- `0x140025d40`
- `0x1400291d0`
- `0x14002bcf4`
- `0x14002ec0c`
- `0x140058008`
- `0x140058078`
- `0x1400582e4`

## import_xrefs

- `ntdll!NtClose` at `0x14002928f`
- `ntdll!NtClose` at `0x14002931e`
- `ntdll!NtClose` at `0x14002933c`
- `ntdll!NtClose` at `0x14002928f`
- `ntdll!NtClose` at `0x14002931e`
- `ntdll!NtClose` at `0x14002933c`

## pseudocode

```c

```
