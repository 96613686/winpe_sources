# PackageSid::FamilyMonikerStringToSid(Common::COMMON_STRING const *,void * *)

- ea: `0x18000d1c8`
- end: `0x18000d479`
- name: `?FamilyMonikerStringToSid@PackageSid@@SAJPEBUCOMMON_STRING@Common@@PEAPEAX@Z`
- size: `689`
- prototype: `static int(const struct Common::COMMON_STRING *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000dff0`

## callees

- `0x18000cda0`
- `0x18000d1c8`
- `0x18000d480`
- `0x18000d53c`
- `0x18000d6b0`
- `0x18000d8a8`
- `0x180058da8`
- `0x180194eb9`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18000d287`
- `ntdll!RtlFreeUnicodeString` at `0x18000d2cd`
- `ntdll!RtlFreeUnicodeString` at `0x18000d448`
- `ntdll!RtlFreeUnicodeString` at `0x18000d464`
- `ntdll!RtlFreeUnicodeString` at `0x18000d287`
- `ntdll!RtlFreeUnicodeString` at `0x18000d2cd`
- `ntdll!RtlFreeUnicodeString` at `0x18000d448`
- `ntdll!RtlFreeUnicodeString` at `0x18000d464`
- `ntdll!RtlInitUnicodeString` at `0x18000d217`
- `ntdll!RtlInitUnicodeString` at `0x18000d217`
- `ntdll!RtlDowncaseUnicodeString` at `0x18000d22e`
- `ntdll!RtlDowncaseUnicodeString` at `0x18000d22e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000d426`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000d426`

## string_xrefs

- `0x18000d266`: `onecore\base\appmodel\package\packagesid.cpp`
- `0x18000d2b2`: `onecore\base\appmodel\package\packagesid.cpp`
- `0x18000d331`: `onecore\base\appmodel\common\cryptoprovider.cpp`

## pseudocode

```c

```
