# DXGPROCESS::GetByHandle(void *,ulong,bool,bool *,bool *,_KAPC_STATE *,DXGPROCESS * *)

- ea: `0x140356414`
- end: `0x14035675d`
- name: `?GetByHandle@DXGPROCESS@@KAJPEAXK_NPEA_N2PEAU_KAPC_STATE@@PEAPEAV1@@Z`
- size: `841`
- prototype: `__int64 __usercall@<rax>(HANDLE Handle@<rcx>, ACCESS_MASK DesiredAccess@<edx>, bool@<r8b>, bool *@<r9>, LUID PrivilegeValue, struct _KAPC_STATE *, struct DXGPROCESS **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14035622c`

## callees

- `0x140012380`
- `0x14001b890`
- `0x140356414`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140356545`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140356545`
- `ntoskrnl!PsGetCurrentProcess` at `0x14035657b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14035657b`
- `ntoskrnl!ObfDereferenceObject` at `0x1403565d0`
- `ntoskrnl!ObfDereferenceObject` at `0x1403565d0`
- `ntoskrnl!KeStackAttachProcess` at `0x140356616`
- `ntoskrnl!KeStackAttachProcess` at `0x140356616`
- `ntoskrnl!PsGetProcessSessionId` at `0x140356537`
- `ntoskrnl!PsGetProcessSessionId` at `0x140356537`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1403564de`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1403564de`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140356520`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140356520`
- `ntoskrnl!PsProcessType` at `0x1403564a8`
- `ntoskrnl!PsGetProcessExitProcessCalled` at `0x140356509`
- `ntoskrnl!PsGetProcessExitProcessCalled` at `0x140356509`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x1403565f6`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x1403565f6`
- `watchdog!WdLogSingleEntry2` at `0x140356592`
- `watchdog!WdLogSingleEntry2` at `0x140356592`
- `watchdog!WdLogSingleEntry3` at `0x1403566f1`
- `watchdog!WdLogSingleEntry3` at `0x1403566f1`
- `watchdog!WdLogSingleEntry0` at `0x140356451`
- `watchdog!WdLogSingleEntry0` at `0x140356690`
- `watchdog!WdLogSingleEntry0` at `0x140356711`
- `watchdog!WdLogSingleEntry0` at `0x140356451`
- `watchdog!WdLogSingleEntry0` at `0x140356690`
- `watchdog!WdLogSingleEntry0` at `0x140356711`
- `watchdog!WdLogSingleEntry5` at `0x140356673`
- `watchdog!WdLogSingleEntry5` at `0x140356673`
- `watchdog!WdLogSingleEntry1` at `0x1403565b2`
- `watchdog!WdLogSingleEntry1` at `0x140356643`
- `watchdog!WdLogSingleEntry1` at `0x1403565b2`
- `watchdog!WdLogSingleEntry1` at `0x140356643`

## pseudocode

```c

```
