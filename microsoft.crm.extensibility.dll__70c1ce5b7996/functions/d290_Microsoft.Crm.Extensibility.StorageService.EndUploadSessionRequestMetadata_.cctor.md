# Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::.cctor

- ea: `0xd290`
- end: `0xd2a5`
- name: `Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::.cctor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0xd29a`: `commit`

## pseudocode

```c

```

## disassembly

```asm
0xd290  ldstr    aCancel// "cancel"
0xd295  stsfld   string Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::CANCEL_STATUS
0xd29a  ldstr    aCommit// "commit"
0xd29f  stsfld   string Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::COMMIT_STATUS
0xd2a4  ret
```
