# wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)

- ea: `0x180021ac0`
- end: `0x180021b4e`
- name: `?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001f7b0`

## callees

- `0x18000a4d8`
- `0x180021ac0`
- `0x180021e98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021b2a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021b2a`

## pseudocode

```c
LSTATUS __fastcall wil::reg::create_unique_key_nothrow(__int64 a1, const WCHAR *a2, __int64 a3, DWORD a4)
{
  HKEY *v5; // rax
  HKEY *phkResult; // rbx
  REGSAM samDesired; // eax
  LSTATUS result; // eax
  DWORD dwDisposition; // [rsp+78h] [rbp+20h] BYREF

  dwDisposition = a4;
  v5 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(a3);
  dwDisposition = 0;
  phkResult = v5;
  *v5 = 0;
  samDesired = wil::reg::reg_view_details::get_access_flags(1);
  result = RegCreateKeyExW(HKEY_USERS, a2, 0, 0, 0, samDesired, 0, phkResult, &dwDisposition);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180021ac0  mov     [rsp+arg_0], rbx
0x180021ac5  mov     [rsp+dwDisposition], r9d
0x180021aca  push    rdi
0x180021acb  sub     rsp, 50h
0x180021acf  mov     rcx, r8
0x180021ad2  mov     rdi, rdx
0x180021ad5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180021ada  mov     ecx, 1
0x180021adf  mov     [rsp+58h+dwDisposition], 0
0x180021ae7  mov     rbx, rax
0x180021aea  mov     qword ptr [rax], 0
0x180021af1  call    ?get_access_flags@reg_view_details@reg@wil@@YAKW4key_access@23@@Z; wil::reg::reg_view_details::get_access_flags(wil::reg::key_access)
0x180021af6  lea     rcx, [rsp+58h+dwDisposition]
0x180021afb  xor     r9d, r9d; lpClass
0x180021afe  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x180021b03  xor     r8d, r8d; Reserved
0x180021b06  mov     [rsp+58h+phkResult], rbx; phkResult
0x180021b0b  mov     rdx, rdi; lpSubKey
0x180021b0e  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180021b17  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180021b1e  mov     [rsp+58h+samDesired], eax; samDesired
0x180021b22  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180021b2a  call    cs:__imp_RegCreateKeyExW
0x180021b31  nop     dword ptr [rax+rax+00h]
0x180021b36  test    eax, eax
0x180021b38  jle     short loc_180021B42
0x180021b3a  movzx   eax, ax
0x180021b3d  or      eax, 80070000h
0x180021b42  mov     rbx, [rsp+58h+arg_0]
0x180021b47  add     rsp, 50h
0x180021b4b  pop     rdi
0x180021b4c  retn
```
