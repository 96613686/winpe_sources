# NgcRegController::AsyncNgcRegResponseCallback(NgcHttpRequest *,STRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT *,long)

- ea: `0x18007e020`
- end: `0x18007e6ff`
- name: `?AsyncNgcRegResponseCallback@NgcRegController@@SAXPEAVNgcHttpRequest@@PEAUSTRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT@@J@Z`
- size: `1759`
- prototype: `void __fastcall(struct NgcHttpRequest *, struct STRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT *, int HresultFromResponse)`
- caller_count: `0`
- callee_count: `35`
- tags: `registry_config`

## callees

- `0x1800012a4`
- `0x180002110`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x18000fc20`
- `0x18001c02c`
- `0x1800204f0`
- `0x18002b9b4`
- `0x18003d520`
- `0x18003e830`
- `0x180040e88`
- `0x180042f60`
- `0x180043ef8`
- `0x180044300`
- `0x180044d30`
- `0x180046540`
- `0x180051650`
- `0x180055174`
- `0x180055210`
- `0x18007dfe8`
- `0x18007e020`
- `0x18007f178`
- `0x180080100`
- `0x1800805d0`
- `0x180080624`
- `0x180080674`
- `0x1800813fc`
- `0x180081450`
- `0x180084530`
- `0x180084600`
- `0x1800846cc`
- `0x180084728`
- `0x180084f30`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18007e487`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18007e487`
- `RPCRT4!UuidIsNil` at `0x18007e202`
- `RPCRT4!UuidIsNil` at `0x18007e202`
- `RPCRT4!RpcStringFreeW` at `0x18007e283`
- `RPCRT4!RpcStringFreeW` at `0x18007e283`
- `RPCRT4!UuidToStringW` at `0x18007e222`
- `RPCRT4!UuidToStringW` at `0x18007e222`

## string_xrefs

- `0x18007e26e`: `%s: CopyStringSafeW failed with error code: 0x%08x`
- `0x18007e2fc`: `%s: Cannot save registration result into registry. NgcRegController::SaveStatus failed with error code: 0x%08x.`
- `0x18007e2c2`: `%s: NgcRegController::NgcPrimeCachedLogonInLsa failed with error code: 0x%08x. Ignore and proceed.`
- `0x18007e5e2`: `%s: NgcRegController::NgcRemoveRegistration failed with error code: 0x%08x. UserEmail = "%s", TenantId = "%s", IdpDomain = "%s".`

## pseudocode

```c

```
