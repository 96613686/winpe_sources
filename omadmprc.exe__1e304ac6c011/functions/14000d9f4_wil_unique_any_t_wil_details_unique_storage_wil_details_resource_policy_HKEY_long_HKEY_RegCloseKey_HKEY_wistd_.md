# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)

- ea: `0x14000d9f4`
- end: `0x14000da12`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140015c49`
- `0x140015c7f`
- `0x140015c91`
- `0x140015d33`
- `0x140015d45`
- `0x140015ed9`

## callees

- `0x14000d9f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000da00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000da00`

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
0x14000d9f4  sub     rsp, 28h
0x14000d9f8  mov     rcx, [rcx]; hKey
0x14000d9fb  test    rcx, rcx
0x14000d9fe  jz      short loc_14000DA0C
0x14000da00  call    cs:__imp_RegCloseKey
0x14000da07  nop     dword ptr [rax+rax+00h]
0x14000da0c  add     rsp, 28h
0x14000da10  retn
```
