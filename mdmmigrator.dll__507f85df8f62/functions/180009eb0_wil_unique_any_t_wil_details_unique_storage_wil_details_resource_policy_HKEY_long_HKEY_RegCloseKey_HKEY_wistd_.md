# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)

- ea: `0x180009eb0`
- end: `0x180009ec7`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `LSTATUS __fastcall(HKEY *)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001f42a`
- `0x18001f7c9`
- `0x18001f835`
- `0x18001f847`
- `0x18001f859`
- `0x18001f86b`
- `0x18001f87d`

## callees

- `0x180009eb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009ebc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009ebc`

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
0x180009eb0  sub     rsp, 28h
0x180009eb4  mov     rcx, [rcx]; hKey
0x180009eb7  test    rcx, rcx
0x180009eba  jz      short loc_180009EC2
0x180009ebc  call    cs:__imp_RegCloseKey
0x180009ec2  add     rsp, 28h
0x180009ec6  retn
```
