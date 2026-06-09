# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x18001616c`
- end: `0x18001621e`
- name: `?create@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800538e8`

## callees

- `0x1800108cc`
- `0x18001616c`
- `0x180016224`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016206`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016206`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800161c9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800161c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(
        __int64 a1,
        HKEY a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5)
{
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  int common; // ebx
  HKEY hKey[3]; // [rsp+50h] [rbp-18h] BYREF

  hKey[0] = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
  Key = RegCreateKeyExW(a2, a3, 0, 0, 0, 0x10u, 0, phkResult, 0);
  common = Key;
  if ( Key > 0 )
    common = (unsigned __int16)Key | 0x80070000;
  if ( common >= 0 )
    common = wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
               a1,
               (__int64)hKey,
               1,
               a5);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return (unsigned int)common;
}

```

## disassembly

```asm
0x18001616c  mov     rax, rsp
0x18001616f  mov     [rax+8], rbx
0x180016173  mov     [rax+10h], rsi
0x180016177  push    rdi
0x180016178  sub     rsp, 60h
0x18001617c  mov     rbx, r8
0x18001617f  mov     rdi, rdx
0x180016182  mov     rsi, rcx
0x180016185  mov     qword ptr [rax-18h], 0
0x18001618d  lea     rcx, [rax-18h]
0x180016191  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180016196  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18001619f  mov     [rsp+68h+phkResult], rax; phkResult
0x1800161a4  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800161ad  mov     [rsp+68h+samDesired], 10h; samDesired
0x1800161b5  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1800161bd  xor     r9d, r9d; lpClass
0x1800161c0  xor     r8d, r8d; Reserved
0x1800161c3  mov     rdx, rbx; lpSubKey
0x1800161c6  mov     rcx, rdi; hKey
0x1800161c9  call    cs:__imp_RegCreateKeyExW
0x1800161cf  mov     ebx, eax
0x1800161d1  test    eax, eax
0x1800161d3  jle     short loc_1800161DE
0x1800161d5  movzx   ebx, ax
0x1800161d8  or      ebx, 80070000h
0x1800161de  test    ebx, ebx
0x1800161e0  js      short loc_1800161FC
0x1800161e2  mov     r9, [rsp+68h+arg_20]
0x1800161ea  mov     r8b, 1
0x1800161ed  lea     rdx, [rsp+68h+hKey]
0x1800161f2  mov     rcx, rsi
0x1800161f5  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800161fa  mov     ebx, eax
0x1800161fc  mov     rcx, [rsp+68h+hKey]; hKey
0x180016201  test    rcx, rcx
0x180016204  jz      short loc_18001620C
0x180016206  call    cs:__imp_RegCloseKey
0x18001620c  mov     eax, ebx
0x18001620e  mov     rbx, [rsp+68h+arg_0]
0x180016213  mov     rsi, [rsp+68h+arg_8]
0x180016218  add     rsp, 60h
0x18001621c  pop     rdi
0x18001621d  retn
```
