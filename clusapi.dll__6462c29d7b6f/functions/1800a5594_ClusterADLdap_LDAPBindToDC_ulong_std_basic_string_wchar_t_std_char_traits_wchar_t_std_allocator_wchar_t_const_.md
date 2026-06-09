# ClusterADLdap::LDAPBindToDC(ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,wchar_t const *,wchar_t const *,std::function<void (bool,bool,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)>)

- ea: `0x1800a5594`
- end: `0x1800a5cb5`
- name: `?LDAPBindToDC@ClusterADLdap@@QEAAJKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0PEB_W1V?$function@$$A6AX_N0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z@3@@Z`
- size: `1825`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180072790`
- `0x180072f10`

## callees

- `0x180002f50`
- `0x18001cc2c`
- `0x18001ed18`
- `0x180028f30`
- `0x180029578`
- `0x180029978`
- `0x1800a3788`
- `0x1800a3890`
- `0x1800a39a0`
- `0x1800a400c`
- `0x1800a5594`
- `0x1800a76a4`
- `0x1800a7734`
- `0x1800b5010`

## import_xrefs

- `api-ms-win-security-activedirectoryclient-l1-1-0!DsMakePasswordCredentialsW` at `0x1800a5b24`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsMakePasswordCredentialsW` at `0x1800a5b24`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x1800a5b4a`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x1800a5c30`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x1800a5b4a`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x1800a5c30`
- `NTDSAPI!DsBindWithCredW` at `0x1800a5bca`
- `NTDSAPI!DsBindWithCredW` at `0x1800a5bca`
- `logoncli!DsGetDcNameW` at `0x1800a57dd`
- `logoncli!DsGetDcNameW` at `0x1800a58fa`
- `logoncli!DsGetDcNameW` at `0x1800a57dd`
- `logoncli!DsGetDcNameW` at `0x1800a58fa`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800a5663`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800a5663`
- `DSROLE!DsRoleFreeMemory` at `0x1800a568f`
- `DSROLE!DsRoleFreeMemory` at `0x1800a5704`
- `DSROLE!DsRoleFreeMemory` at `0x1800a5747`
- `DSROLE!DsRoleFreeMemory` at `0x1800a568f`
- `DSROLE!DsRoleFreeMemory` at `0x1800a5704`
- `DSROLE!DsRoleFreeMemory` at `0x1800a5747`

## string_xrefs

- `0x1800a5886`: `Attempting DsGetDcName`

## pseudocode

```c

```
