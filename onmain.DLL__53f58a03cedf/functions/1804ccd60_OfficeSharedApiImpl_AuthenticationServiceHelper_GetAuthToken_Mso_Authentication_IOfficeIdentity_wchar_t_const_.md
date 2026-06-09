# OfficeSharedApiImpl::AuthenticationServiceHelper::GetAuthToken(Mso::Authentication::IOfficeIdentity *,wchar_t const *,wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,bool,Mso::Telemetry::Activity *)

- ea: `0x1804ccd60`
- end: `0x1804cd55e`
- name: `?GetAuthToken@AuthenticationServiceHelper@OfficeSharedApiImpl@@YA?AUResult@12@PEAUIOfficeIdentity@Authentication@Mso@@PEB_W11AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAUActivity@Telemetry@6@@Z`
- size: `2046`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `registry_config, service_task`

## callers

- `0x1804c9f64`
- `0x180893100`
- `0x180f8c730`

## callees

- `0x18002da60`
- `0x1800499b0`
- `0x1800581b0`
- `0x180081214`
- `0x180094190`
- `0x1800e3a80`
- `0x1800e3b54`
- `0x1801171ec`
- `0x180197e0c`
- `0x1802e5190`
- `0x18046ab38`
- `0x1804ccc50`
- `0x1804ccd60`
- `0x1804cd560`
- `0x1804cd5a4`
- `0x1804ce218`
- `0x1804ce300`
- `0x1804ce5a4`
- `0x1804ce610`
- `0x1804ce7c0`
- `0x180a6e8b8`
- `0x180ad02c4`
- `0x180ad32e8`

## import_xrefs

- `Mso98Win32Client!__imp_?ShowUIAsync@SignIn@Mso@@YA?AV?$LegacyFuture@PEAUIOfficeIdentity@Authentication@Mso@@@2@AEBVRepromptContext@Authentication@2@AEBUUIExecutionContext@52@@Z` at `0x1804cd340`
- `Mso98Win32Client!__imp_?ShowUIAsync@SignIn@Mso@@YA?AV?$LegacyFuture@PEAUIOfficeIdentity@Authentication@Mso@@@2@AEBVRepromptContext@Authentication@2@AEBUUIExecutionContext@52@@Z` at `0x1804cd340`
- `Mso30Win32Client!__imp_?GetInstance@RepromptContextFactory@Authentication@Mso@@YA?AVRepromptContext@23@KAEBUIOfficeIdentity@23@AEBVServiceParams@23@@Z` at `0x1804cd2a7`
- `Mso30Win32Client!__imp_?GetInstance@RepromptContextFactory@Authentication@Mso@@YA?AVRepromptContext@23@KAEBUIOfficeIdentity@23@AEBVServiceParams@23@@Z` at `0x1804cd2a7`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1804ccfae`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1804cd09b`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1804cd15f`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1804cd43d`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1804ccfae`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1804cd09b`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1804cd15f`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1804cd43d`
- `Mso20Win32Client!__imp_?GetCurrentExecutionContext@ApplicationModel@Mso@@YA?AV?$TCntPtr@UIExecutionContext@ApplicationModel@Mso@@@2@XZ` at `0x1804cd2f5`
- `Mso20Win32Client!__imp_?GetCurrentExecutionContext@ApplicationModel@Mso@@YA?AV?$TCntPtr@UIExecutionContext@ApplicationModel@Mso@@@2@XZ` at `0x1804cd2f5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1804cd184`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1804cd236`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1804cd184`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1804cd236`
- `Mso20Win32Client!__imp_?EndNow@Activity@Telemetry@Mso@@QEAAXXZ` at `0x1804ccfa3`
- `Mso20Win32Client!__imp_?EndNow@Activity@Telemetry@Mso@@QEAAXXZ` at `0x1804cd432`
- `Mso20Win32Client!__imp_?EndNow@Activity@Telemetry@Mso@@QEAAXXZ` at `0x1804ccfa3`
- `Mso20Win32Client!__imp_?EndNow@Activity@Telemetry@Mso@@QEAAXXZ` at `0x1804cd432`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x1804ccddb`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x1804ccef2`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x1804ccddb`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x1804ccef2`

## string_xrefs

- `0x1804ccded`: `GetAuthToken`
- `0x1804ccf04`: `GetAuthTokenTicket`
- `0x1804cd37d`: `GetAuthTokenTicketRetry`

## pseudocode

```c

```
