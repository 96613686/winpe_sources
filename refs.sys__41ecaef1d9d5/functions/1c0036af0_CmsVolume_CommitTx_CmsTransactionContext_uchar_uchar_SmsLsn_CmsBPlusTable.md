# CmsVolume::CommitTx(CmsTransactionContext *,uchar,uchar,_SmsLsn *,CmsBPlusTable * *)

- ea: `0x1c0036af0`
- end: `0x1c0036ca6`
- name: `?CommitTx@CmsVolume@@QEAAJPEAVCmsTransactionContext@@EEPEAU_SmsLsn@@PEAPEAVCmsBPlusTable@@@Z`
- size: `438`
- prototype: `__int64 __usercall@<rax>(CmsVolume *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, struct _SmsLsn *, struct CmsBPlusTable **)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1c0011660`
- `0x1c00224d0`
- `0x1c0036440`

## callees

- `0x1c0012080`
- `0x1c0032e3c`
- `0x1c0034450`
- `0x1c00363b4`
- `0x1c0036af0`
- `0x1c0039984`
- `0x1c0041630`
- `0x1c006af80`
- `0x1c00e0800`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c008008f`
- `ntoskrnl!KeInitializeEvent` at `0x1c008008f`
- `ntoskrnl!KeSetEvent` at `0x1c008012d`
- `ntoskrnl!KeSetEvent` at `0x1c008012d`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c00800a1`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c00800b7`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c00800cd`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c00800e3`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c00800f9`

## pseudocode

```c

```
