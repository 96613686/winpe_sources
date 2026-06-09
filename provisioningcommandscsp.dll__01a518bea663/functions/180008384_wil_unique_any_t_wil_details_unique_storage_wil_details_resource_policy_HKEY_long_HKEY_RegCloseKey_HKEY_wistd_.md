# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)

- ea: `0x180008384`
- end: `0x18000839b`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `LSTATUS __fastcall(HKEY *)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000d0fc`
- `0x18000d10e`
- `0x18000d120`
- `0x18000d132`
- `0x18000d338`
- `0x18000d410`
- `0x18000d422`
- `0x18000d4d7`
- `0x18000d4e9`
- `0x18000d50d`

## callees

- `0x180008384`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008390`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008390`

## pseudocode

```c
LSTATUS __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(
        HKEY *a1)
{
  HKEY v1; // rcx
  LSTATUS result; // eax

  v1 = *a1;
  if ( v1 )
    return RegCloseKey(v1);
  return result;
}

```

## disassembly

```asm
0x180008384  sub     rsp, 28h
0x180008388  mov     rcx, [rcx]; hKey
0x18000838b  test    rcx, rcx
0x18000838e  jz      short loc_180008396
0x180008390  call    cs:__imp_RegCloseKey
0x180008396  add     rsp, 28h
0x18000839a  retn
```
