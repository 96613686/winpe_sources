# PrivilegeTypeNames::.cctor

- ea: `0x77ca0`
- end: `0x77cf1`
- name: `PrivilegeTypeNames::.cctor`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## string_xrefs

- `0x77ca0`: `prvCreate`
- `0x77caa`: `prvRead`
- `0x77cb4`: `prvWrite`
- `0x77cbe`: `prvDelete`

## pseudocode

```c

```

## disassembly

```asm
0x77ca0  ldstr    aPrvcreate// "prvCreate"
0x77ca5  stsfld   string PrivilegeTypeNames::Create
0x77caa  ldstr    aPrvread// "prvRead"
0x77caf  stsfld   string PrivilegeTypeNames::Read
0x77cb4  ldstr    aPrvwrite// "prvWrite"
0x77cb9  stsfld   string PrivilegeTypeNames::Write
0x77cbe  ldstr    aPrvdelete// "prvDelete"
0x77cc3  stsfld   string PrivilegeTypeNames::Delete
0x77cc8  ldstr    aPrvassign// "prvAssign"
0x77ccd  stsfld   string PrivilegeTypeNames::Assign
0x77cd2  ldstr    aPrvshare// "prvShare"
0x77cd7  stsfld   string PrivilegeTypeNames::Share
0x77cdc  ldstr    aPrvappend// "prvAppend"
0x77ce1  stsfld   string PrivilegeTypeNames::Append
0x77ce6  ldstr    aPrvappendto// "prvAppendTo"
0x77ceb  stsfld   string PrivilegeTypeNames::AppendTo
0x77cf0  ret
```
