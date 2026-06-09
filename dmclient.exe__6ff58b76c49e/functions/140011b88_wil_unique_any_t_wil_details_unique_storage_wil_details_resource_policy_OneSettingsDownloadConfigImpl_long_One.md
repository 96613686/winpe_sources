# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<OneSettingsDownloadConfigImpl *,long (*)(OneSettingsDownloadConfigImpl *),&OneSettingsFreeDownloadConfig(OneSettingsDownloadConfigImpl *),wistd::integral_constant<unsigned __int64,0>,OneSettingsDownloadConfigImpl *,OneSettingsDownloadConfigImpl *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<OneSettingsDownloadConfigImpl *,long (*)(OneSettingsDownloadConfigImpl *),&OneSettingsFreeDownloadConfig(OneSettingsDownloadConfigImpl *),wistd::integral_constant<unsigned __int64,0>,OneSettingsDownloadConfigImpl *,OneSettingsDownloadConfigImpl *,0,std::nullptr_t>>>(void)

- ea: `0x140011b88`
- end: `0x140011b9f`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUOneSettingsDownloadConfigImpl@@P6AJPEAU1@@Z$1?OneSettingsFreeDownloadConfig@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140018cd7`

## callees

- `0x140011b88`

## import_xrefs

- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x140011b94`
- `OneSettingsClient!OneSettingsFreeDownloadConfig` at `0x140011b94`

## pseudocode

```c
__int64 __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<OneSettingsDownloadConfigImpl *,long (*)(OneSettingsDownloadConfigImpl *),&long OneSettingsFreeDownloadConfig(OneSettingsDownloadConfigImpl *),wistd::integral_constant<unsigned __int64,0>,OneSettingsDownloadConfigImpl *,OneSettingsDownloadConfigImpl *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<OneSettingsDownloadConfigImpl *,long (*)(OneSettingsDownloadConfigImpl *),&long OneSettingsFreeDownloadConfig(OneSettingsDownloadConfigImpl *),wistd::integral_constant<unsigned __int64,0>,OneSettingsDownloadConfigImpl *,OneSettingsDownloadConfigImpl *,0,std::nullptr_t>>>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return OneSettingsFreeDownloadConfig(v1);
  return result;
}

```

## disassembly

```asm
0x140011b88  sub     rsp, 28h
0x140011b8c  mov     rcx, [rcx]
0x140011b8f  test    rcx, rcx
0x140011b92  jz      short loc_140011B9A
0x140011b94  call    cs:__imp_OneSettingsFreeDownloadConfig
0x140011b9a  add     rsp, 28h
0x140011b9e  retn
```
