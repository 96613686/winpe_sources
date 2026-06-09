# PackageSid::FamilyMonikerStringToSid(Common::COMMON_STRING const *,void * *)

- ea: `0x1800681d0`
- end: `0x180068456`
- name: `?FamilyMonikerStringToSid@PackageSid@@SAJPEBUCOMMON_STRING@Common@@PEAPEAX@Z`
- size: `646`
- prototype: `static int(const struct Common::COMMON_STRING *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180067f80`

## callees

- `0x18004df24`
- `0x1800681d0`
- `0x18006845c`
- `0x180068518`
- `0x18006868c`
- `0x1800689c8`
- `0x1800689ec`
- `0x180188eb9`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180068283`
- `ntdll!RtlFreeUnicodeString` at `0x1800682c3`
- `ntdll!RtlFreeUnicodeString` at `0x180068431`
- `ntdll!RtlFreeUnicodeString` at `0x180068447`
- `ntdll!RtlFreeUnicodeString` at `0x180068283`
- `ntdll!RtlFreeUnicodeString` at `0x1800682c3`
- `ntdll!RtlFreeUnicodeString` at `0x180068431`
- `ntdll!RtlFreeUnicodeString` at `0x180068447`
- `ntdll!RtlInitUnicodeString` at `0x18006821f`
- `ntdll!RtlInitUnicodeString` at `0x18006821f`
- `ntdll!RtlDowncaseUnicodeString` at `0x180068230`
- `ntdll!RtlDowncaseUnicodeString` at `0x180068230`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180068415`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180068415`

## string_xrefs

- `0x180068320`: `onecore\base\appmodel\common\cryptoprovider.cpp`
- `0x180068262`: `onecore\base\appmodel\package\packagesid.cpp`
- `0x1800682a8`: `onecore\base\appmodel\package\packagesid.cpp`

## pseudocode

```c

```
