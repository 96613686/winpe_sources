# wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)

- ea: `0x180008250`
- end: `0x180008267`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `LSTATUS __fastcall(HKEY *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008228`
- `0x18000832c`
- `0x180008908`
- `0x180008b80`

## callees

- `0x180008250`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000825c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000825c`

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
0x180008250  sub     rsp, 28h
0x180008254  mov     rcx, [rcx]; hKey
0x180008257  test    rcx, rcx
0x18000825a  jz      short loc_180008262
0x18000825c  call    cs:__imp_RegCloseKey
0x180008262  add     rsp, 28h
0x180008266  retn
```
