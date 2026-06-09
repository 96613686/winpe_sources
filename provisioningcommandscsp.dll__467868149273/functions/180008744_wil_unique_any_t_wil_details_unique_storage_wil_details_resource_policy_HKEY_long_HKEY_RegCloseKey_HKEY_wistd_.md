# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)

- ea: `0x180008744`
- end: `0x180008762`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000d7c8`
- `0x18000d7da`
- `0x18000d7ec`
- `0x18000d7fe`
- `0x18000da04`
- `0x18000dadc`
- `0x18000daee`
- `0x18000dba5`
- `0x18000dbb7`
- `0x18000dbdb`

## callees

- `0x180008744`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008750`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008750`

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
0x180008744  sub     rsp, 28h
0x180008748  mov     rcx, [rcx]; hKey
0x18000874b  test    rcx, rcx
0x18000874e  jz      short loc_18000875C
0x180008750  call    cs:__imp_RegCloseKey
0x180008757  nop     dword ptr [rax+rax+00h]
0x18000875c  add     rsp, 28h
0x180008760  retn
```
