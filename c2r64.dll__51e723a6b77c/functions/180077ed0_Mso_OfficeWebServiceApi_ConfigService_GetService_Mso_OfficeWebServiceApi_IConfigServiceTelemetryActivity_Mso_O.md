# Mso::OfficeWebServiceApi::ConfigService::GetService(Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity &,Mso::OfficeWebServiceApi::ConfigURL::URL,Mso::OfficeWebServiceApi::FederationProviderConfiguration const &,bool)

- ea: `0x180077ed0`
- end: `0x180078224`
- name: `?GetService@ConfigService@OfficeWebServiceApi@Mso@@QEAA?AV?$shared_ptr@VService@OfficeWebServiceApi@Mso@@@std@@AEAVIConfigServiceTelemetryActivity@23@W4URL@ConfigURL@23@AEBVFederationProviderConfiguration@23@_N@Z`
- size: `852`
- prototype: `__int64 __usercall@<rax>(Mso::OfficeWebServiceApi::ConfigService *this@<rcx>, struct Mso::OfficeWebServiceApi::FederationProviderConfiguration *)`
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800782a4`
- `0x180078584`
- `0x18007957c`

## callees

- `0x18000adf0`
- `0x180011340`
- `0x18001149c`
- `0x180011b70`
- `0x180012580`
- `0x180013304`
- `0x18003e690`
- `0x180073600`
- `0x18007625c`
- `0x180076ee0`
- `0x180077d2c`
- `0x180077dbc`
- `0x180077ed0`
- `0x180078224`
- `0x180079698`
- `0x18007a64c`
- `0x180081078`
- `0x1800fbee0`
- `0x180136ca4`
- `0x180146090`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180078167`
- `KERNEL32!SetEvent` at `0x180078167`
- `KERNEL32!ResetEvent` at `0x180078134`
- `KERNEL32!ResetEvent` at `0x180078134`
- `KERNEL32!WaitForSingleObjectEx` at `0x18007819c`
- `KERNEL32!WaitForSingleObjectEx` at `0x18007819c`

## string_xrefs

- `0x180078084`: `[ConfigService] GetService`
- `0x180078063`: `ServiceStatus failed`

## pseudocode

```c

```
