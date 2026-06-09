# wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)

- ea: `0x18000dd1c`
- end: `0x18000dd33`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `LSTATUS __fastcall(HKEY *)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000dd10`
- `0x18000df4c`
- `0x18000e2d0`
- `0x18000e354`
- `0x18000eccc`
- `0x18000f0ec`
- `0x18000f860`
- `0x18000faf0`
- `0x18000ffa0`
- `0x180010770`

## callees

- `0x18000dd1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd28`

## pseudocode

```c
LSTATUS __fastcall wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(
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
0x18000dd1c  sub     rsp, 28h
0x18000dd20  mov     rcx, [rcx]; hKey
0x18000dd23  test    rcx, rcx
0x18000dd26  jz      short loc_18000DD2E
0x18000dd28  call    cs:__imp_RegCloseKey
0x18000dd2e  add     rsp, 28h
0x18000dd32  retn
```
