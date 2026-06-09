# wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)

- ea: `0x180021f10`
- end: `0x180021f67`
- name: `?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z`
- size: `87`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001f2b0`
- `0x18001fa9c`
- `0x180020f70`

## callees

- `0x18000a4d8`
- `0x180021e98`
- `0x180021f10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021f45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021f45`

## pseudocode

```c
LSTATUS __fastcall wil::reg::open_unique_key_nothrow(HKEY hKey, LPCWSTR lpSubKey, __int64 a3, unsigned int a4)
{
  HKEY *phkResult; // rbx
  REGSAM access_flags; // eax
  LSTATUS result; // eax

  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(a3);
  access_flags = wil::reg::reg_view_details::get_access_flags(a4);
  result = RegOpenKeyExW(hKey, lpSubKey, 0, access_flags, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180021f10  push    rbx
0x180021f12  push    rbp
0x180021f13  push    rsi
0x180021f14  push    rdi
0x180021f15  sub     rsp, 38h
0x180021f19  mov     rbp, rcx
0x180021f1c  mov     edi, r9d
0x180021f1f  mov     rcx, r8
0x180021f22  mov     rsi, rdx
0x180021f25  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180021f2a  mov     ecx, edi
0x180021f2c  mov     rbx, rax
0x180021f2f  call    ?get_access_flags@reg_view_details@reg@wil@@YAKW4key_access@23@@Z; wil::reg::reg_view_details::get_access_flags(wil::reg::key_access)
0x180021f34  mov     r9d, eax; samDesired
0x180021f37  mov     [rsp+58h+phkResult], rbx; phkResult
0x180021f3c  xor     r8d, r8d; ulOptions
0x180021f3f  mov     rdx, rsi; lpSubKey
0x180021f42  mov     rcx, rbp; hKey
0x180021f45  call    cs:__imp_RegOpenKeyExW
0x180021f4c  nop     dword ptr [rax+rax+00h]
0x180021f51  test    eax, eax
0x180021f53  jle     short loc_180021F5D
0x180021f55  movzx   eax, ax
0x180021f58  or      eax, 80070000h
0x180021f5d  add     rsp, 38h
0x180021f61  pop     rdi
0x180021f62  pop     rsi
0x180021f63  pop     rbp
0x180021f64  pop     rbx
0x180021f65  retn
```
