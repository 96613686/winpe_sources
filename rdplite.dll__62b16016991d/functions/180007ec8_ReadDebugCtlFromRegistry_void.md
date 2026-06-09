# ReadDebugCtlFromRegistry(void)

- ea: `0x180007ec8`
- end: `0x180007f77`
- name: `?ReadDebugCtlFromRegistry@@YAXXZ`
- size: `175`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800083d0`

## callees

- `0x180007db4`
- `0x180007ec8`
- `0x180008380`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007f37`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007f37`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180007ef0`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180007ef0`

## pseudocode

```c
void ReadDebugCtlFromRegistry(void)
{
  HKEY *v0; // rax
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  hkey = 0;
  v0 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
  if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\RdpLite", v0) )
  {
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"DebugCtrl", 0x10u, 0, &pvData, &pcbData) )
    {
      gDebugCtrl = pvData & 1;
      byte_18003C9ED = (pvData & 2) != 0;
      byte_18003C9EE = (pvData & 4) != 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
}

```

## disassembly

```asm
0x180007ec8  sub     rsp, 48h
0x180007ecc  lea     rcx, [rsp+48h+hkey]
0x180007ed1  mov     [rsp+48h+hkey], 0
0x180007eda  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180007edf  mov     r8, rax; phkResult
0x180007ee2  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x180007ee9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007ef0  call    cs:__imp_RegOpenKeyW
0x180007ef6  test    eax, eax
0x180007ef8  jnz     short loc_180007F68
0x180007efa  mov     rcx, [rsp+48h+hkey]; hkey
0x180007eff  lea     r8, Value; "DebugCtrl"
0x180007f06  mov     [rsp+48h+arg_0], eax
0x180007f0a  mov     r9d, 10h; dwFlags
0x180007f10  lea     rax, [rsp+48h+arg_8]
0x180007f15  mov     [rsp+48h+arg_8], 4
0x180007f1d  mov     [rsp+48h+pcbData], rax; pcbData
0x180007f22  xor     edx, edx; lpSubKey
0x180007f24  lea     rax, [rsp+48h+arg_0]
0x180007f29  mov     [rsp+48h+pvData], rax; pvData
0x180007f2e  mov     [rsp+48h+pdwType], 0; pdwType
0x180007f37  call    cs:__imp_RegGetValueW
0x180007f3d  test    eax, eax
0x180007f3f  jnz     short loc_180007F68
0x180007f41  mov     ecx, [rsp+48h+arg_0]
0x180007f45  mov     dl, 1
0x180007f47  mov     al, cl
0x180007f49  and     al, dl
0x180007f4b  mov     cs:?gDebugCtrl@@3URDPLITE_DEBUG_CTRL@@A, al; RDPLITE_DEBUG_CTRL gDebugCtrl
0x180007f51  mov     al, cl
0x180007f53  shr     al, 1
0x180007f55  and     al, dl
0x180007f57  shr     cl, 2
0x180007f5a  and     cl, dl
0x180007f5c  mov     cs:byte_18003C9ED, al
0x180007f62  mov     cs:byte_18003C9EE, cl
0x180007f68  lea     rcx, [rsp+48h+hkey]
0x180007f6d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180007f72  add     rsp, 48h
0x180007f76  retn
```
