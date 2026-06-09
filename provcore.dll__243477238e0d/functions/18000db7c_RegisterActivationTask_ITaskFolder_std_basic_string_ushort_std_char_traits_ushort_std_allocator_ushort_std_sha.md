# RegisterActivationTask(ITaskFolder *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::shared_ptr<WcmCommon::Xml::Document> &,tagVARIANT,_TASK_LOGON_TYPE,tagVARIANT)

- ea: `0x18000db7c`
- end: `0x18000dd0d`
- name: `?RegisterActivationTask@@YAJPEAUITaskFolder@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$shared_ptr@VDocument@Xml@WcmCommon@@@3@UtagVARIANT@@W4_TASK_LOGON_TYPE@@3@Z`
- size: `401`
- prototype: `HRESULT __fastcall(ITaskFolder *RootFolder, std::wstring *Path, std::shared_ptr<WcmCommon::Xml::Document> *XmlDoc, tagVARIANT UserId, _TASK_LOGON_TYPE Sddl, tagVARIANT RootFolder)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bfe0`
- `0x180025e30`

## callees

- `0x180002790`
- `0x18000b1e4`
- `0x18000b2f4`
- `0x18000db7c`
- `0x180010c34`
- `0x180011844`
- `0x180011cfc`
- `0x180048f78`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000dbd4`
- `OLEAUT32!__imp_VariantInit` at `0x18000dbd4`
- `OLEAUT32!__imp_VariantClear` at `0x18000dccf`
- `OLEAUT32!__imp_VariantClear` at `0x18000dccf`

## pseudocode

```c

```
