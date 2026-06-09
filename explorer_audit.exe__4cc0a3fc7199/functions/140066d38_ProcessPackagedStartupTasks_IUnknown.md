# ProcessPackagedStartupTasks(IUnknown *)

- ea: `0x140066d38`
- end: `0x14006700e`
- name: `?ProcessPackagedStartupTasks@@YAJPEAUIUnknown@@@Z`
- size: `726`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1401b4cbc`

## callees

- `0x14000c870`
- `0x140066d38`
- `0x140067014`
- `0x140067310`
- `0x1400954e0`
- `0x1401040e0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140066f6c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140066f6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140066da4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140066da4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140066dcd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140066dcd`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x140066d74`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x140066d74`
- `SHELL32!__imp_SHRestricted` at `0x140066d63`
- `SHELL32!__imp_SHRestricted` at `0x140066d63`

## string_xrefs

- `0x140066d9d`: `Windows.ApplicationModel.Internal.StartupTaskInternal`

## pseudocode

```c

```
