# COOBEExpeditedUpdateUSOCallback::ScanCompleted(ushort const *,long,IMoUsoUpdateCollection *)

- ea: `0x18007a840`
- end: `0x18007aa71`
- name: `?ScanCompleted@COOBEExpeditedUpdateUSOCallback@@UEAAJPEBGJPEAUIMoUsoUpdateCollection@@@Z`
- size: `561`
- prototype: `int(COOBEExpeditedUpdateUSOCallback *__hidden this, const unsigned __int16 *, int, struct IMoUsoUpdateCollection *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003470`
- `0x180008544`
- `0x18001ad08`
- `0x18001d004`
- `0x180040898`
- `0x18007a840`
- `0x18007cec4`
- `0x1800b8834`
- `0x1800bf784`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007a8b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007a9a2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007a8b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007a9a2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007a957`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007a957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a965`

## string_xrefs

- `0x18007a86f`: `ExpeditedUpdateTask USO scan complete - Provider: [%s], Result: [hr=0x%08X]`
- `0x18007a97d`: `ExpeditedUpdateTask USO WuProvider scan completed - Setting scan event, hr=0x%08X`
- `0x18007a93e`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdateusocallbacks.h`
- `0x18007aa2e`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdateusocallbacks.h`

## pseudocode

```c

```
