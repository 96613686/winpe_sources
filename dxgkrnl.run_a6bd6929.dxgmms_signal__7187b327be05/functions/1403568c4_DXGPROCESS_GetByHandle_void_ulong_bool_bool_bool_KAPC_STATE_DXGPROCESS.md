# DXGPROCESS::GetByHandle(void *,ulong,bool,bool *,bool *,_KAPC_STATE *,DXGPROCESS * *)

- ea: `0x1403568c4`
- end: `0x140356c0d`
- name: `?GetByHandle@DXGPROCESS@@KAJPEAXK_NPEA_N2PEAU_KAPC_STATE@@PEAPEAV1@@Z`
- size: `841`
- prototype: `__int64 __usercall@<rax>(HANDLE Handle@<rcx>, ACCESS_MASK DesiredAccess@<edx>, bool@<r8b>, bool *@<r9>, LUID PrivilegeValue, struct _KAPC_STATE *, struct DXGPROCESS **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1403566dc`

## callees

- `0x140012540`
- `0x14001b9c0`
- `0x1403568c4`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403569f5`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403569f5`
- `ntoskrnl!PsGetCurrentProcess` at `0x140356a2b`
- `ntoskrnl!PsGetCurrentProcess` at `0x140356a2b`
- `ntoskrnl!ObfDereferenceObject` at `0x140356a80`
- `ntoskrnl!ObfDereferenceObject` at `0x140356a80`
- `ntoskrnl!KeStackAttachProcess` at `0x140356ac6`
- `ntoskrnl!KeStackAttachProcess` at `0x140356ac6`
- `ntoskrnl!PsGetProcessSessionId` at `0x1403569e7`
- `ntoskrnl!PsGetProcessSessionId` at `0x1403569e7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14035698e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14035698e`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x1403569d0`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x1403569d0`
- `ntoskrnl!PsProcessType` at `0x140356958`
- `ntoskrnl!PsGetProcessExitProcessCalled` at `0x1403569b9`
- `ntoskrnl!PsGetProcessExitProcessCalled` at `0x1403569b9`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140356aa6`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140356aa6`
- `watchdog!WdLogSingleEntry2` at `0x140356a42`
- `watchdog!WdLogSingleEntry2` at `0x140356a42`
- `watchdog!WdLogSingleEntry3` at `0x140356ba1`
- `watchdog!WdLogSingleEntry3` at `0x140356ba1`
- `watchdog!WdLogSingleEntry0` at `0x140356901`
- `watchdog!WdLogSingleEntry0` at `0x140356b40`
- `watchdog!WdLogSingleEntry0` at `0x140356bc1`
- `watchdog!WdLogSingleEntry0` at `0x140356901`
- `watchdog!WdLogSingleEntry0` at `0x140356b40`
- `watchdog!WdLogSingleEntry0` at `0x140356bc1`
- `watchdog!WdLogSingleEntry5` at `0x140356b23`
- `watchdog!WdLogSingleEntry5` at `0x140356b23`
- `watchdog!WdLogSingleEntry1` at `0x140356a62`
- `watchdog!WdLogSingleEntry1` at `0x140356af3`
- `watchdog!WdLogSingleEntry1` at `0x140356a62`
- `watchdog!WdLogSingleEntry1` at `0x140356af3`

## pseudocode

```c

```
