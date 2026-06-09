# CreateAgentAccountInSAM(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180132620`
- end: `0x18013294b`
- name: `?CreateAgentAccountInSAM@@YA?AUSidHelper@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `811`
- prototype: `SidHelper *__fastcall(SidHelper *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x1801331f4`

## callees

- `0x180130280`
- `0x180131c84`
- `0x180132620`
- `0x180134170`
- `0x180135188`
- `0x1801351e0`
- `0x180135344`

## import_xrefs

- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrOpenAlias` at `0x180132855`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrOpenAlias` at `0x180132855`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCreateUserInDomain` at `0x180132689`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCreateUserInDomain` at `0x180132689`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrSetInformationUser` at `0x180132765`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrSetInformationUser` at `0x180132765`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamISetPasswordForeignUser2` at `0x1801326f9`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamISetPasswordForeignUser2` at `0x1801326f9`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x1801328bf`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x1801328bf`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCloseHandle` at `0x1801328a1`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCloseHandle` at `0x1801328d1`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCloseHandle` at `0x1801328a1`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCloseHandle` at `0x1801328d1`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrAddMemberToAlias` at `0x180132884`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrAddMemberToAlias` at `0x180132884`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrQueryInformationUser` at `0x180132738`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrQueryInformationUser` at `0x180132738`

## pseudocode

```c

```
