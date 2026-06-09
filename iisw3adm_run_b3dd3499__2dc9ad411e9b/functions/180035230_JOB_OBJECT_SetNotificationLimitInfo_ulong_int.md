# JOB_OBJECT::SetNotificationLimitInfo(ulong,int)

- ea: `0x180035230`
- end: `0x180035430`
- name: `?SetNotificationLimitInfo@JOB_OBJECT@@QEAAJKH@Z`
- size: `512`
- prototype: `__int64 __fastcall(JOB_OBJECT *__hidden this, unsigned int, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800193e4`
- `0x1800346b4`
- `0x180034da4`
- `0x180035010`
- `0x180035578`

## callees

- `0x180005878`
- `0x180035230`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003528f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003538b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003528f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003538b`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18003537d`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18003537d`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x180035285`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x180035285`
- `iisutil!PuDbgPrintError` at `0x1800352d8`
- `iisutil!PuDbgPrintError` at `0x1800353d4`
- `iisutil!PuDbgPrintError` at `0x1800352d8`
- `iisutil!PuDbgPrintError` at `0x1800353d4`

## string_xrefs

- `0x1800352d1`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\job_object.cxx`
- `0x1800353cd`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\job_object.cxx`

## pseudocode

```c

```
