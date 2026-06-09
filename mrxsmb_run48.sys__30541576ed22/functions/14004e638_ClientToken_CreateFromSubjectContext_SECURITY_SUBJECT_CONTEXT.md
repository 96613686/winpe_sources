# ClientToken::CreateFromSubjectContext(_SECURITY_SUBJECT_CONTEXT *)

- ea: `0x14004e638`
- end: `0x14004e6e3`
- name: `?CreateFromSubjectContext@ClientToken@@SAPEAV1@PEAU_SECURITY_SUBJECT_CONTEXT@@@Z`
- size: `171`
- prototype: `struct ClientToken *__fastcall(struct _SECURITY_SUBJECT_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140087730`

## callees

- `0x14004e638`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004e699`
- `ntoskrnl!ExAllocatePool2` at `0x14004e699`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14004e657`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14004e677`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14004e657`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14004e677`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14004e6c4`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14004e6c4`

## pseudocode

```c

```
