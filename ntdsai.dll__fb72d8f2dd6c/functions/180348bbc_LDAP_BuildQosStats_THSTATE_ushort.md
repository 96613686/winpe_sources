# LDAP_BuildQosStats(_THSTATE *,ushort * *)

- ea: `0x180348bbc`
- end: `0x180348d9f`
- name: `?LDAP_BuildQosStats@@YA?AW4_enum1@@PEAU_THSTATE@@PEAPEAG@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1803794f4`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18001e090`
- `0x180029fac`
- `0x1800ef5e0`
- `0x180348bbc`

## import_xrefs

- `NTDSATQ!AtqQosClassGetInfo` at `0x180348ca4`
- `NTDSATQ!AtqQosClassGetInfo` at `0x180348cbc`
- `NTDSATQ!AtqQosClassGetInfo` at `0x180348cd4`
- `NTDSATQ!AtqQosClassGetInfo` at `0x180348cec`
- `NTDSATQ!AtqQosClassGetInfo` at `0x180348ca4`
- `NTDSATQ!AtqQosClassGetInfo` at `0x180348cbc`
- `NTDSATQ!AtqQosClassGetInfo` at `0x180348cd4`
- `NTDSATQ!AtqQosClassGetInfo` at `0x180348cec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180348d6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180472cc8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180348d6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180472cc8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180348c0d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180348c0d`
- `ntdll!RtlStringFromGUID` at `0x180348c8f`
- `ntdll!RtlStringFromGUID` at `0x180348c8f`
- `ntdll!RtlFreeUnicodeString` at `0x180348d22`
- `ntdll!RtlFreeUnicodeString` at `0x180348d22`

## string_xrefs

- `0x180348d07`: `\n	<LdapQosClass QosId='%s' CpuGoal='%d' CpuUsed='%d' QueueDepth='%d' QueueDelay='%d'/>`

## pseudocode

```c

```
