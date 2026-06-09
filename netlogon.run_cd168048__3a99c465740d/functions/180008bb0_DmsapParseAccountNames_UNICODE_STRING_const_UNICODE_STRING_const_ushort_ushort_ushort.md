# DmsapParseAccountNames(_UNICODE_STRING const *,_UNICODE_STRING const *,ushort * *,ushort * *,ushort * *)

- ea: `0x180008bb0`
- end: `0x180008eff`
- name: `?DmsapParseAccountNames@@YAJPEBU_UNICODE_STRING@@0PEAPEAG11@Z`
- size: `847`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, const struct _UNICODE_STRING *@<rdx>, unsigned __int16 **@<r8>, unsigned __int16 **@<r9>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18007a0a8`

## callees

- `0x180007518`
- `0x180008bb0`
- `0x180008f08`
- `0x18002c758`
- `0x18004f3e8`
- `0x18007a058`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008c85`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008d12`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008c85`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008d12`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008dee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008dee`
- `ntdll!RtlInitUnicodeString` at `0x180008cbe`
- `ntdll!RtlInitUnicodeString` at `0x180008d5d`
- `ntdll!RtlInitUnicodeString` at `0x180008cbe`
- `ntdll!RtlInitUnicodeString` at `0x180008d5d`

## string_xrefs

- `0x180008e2f`: `RtlStringCchCopyNW failed, 0x%x\n`

## pseudocode

```c

```
