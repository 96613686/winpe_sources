# GetRegisterdPDMPath(_GUID const &,ushort *,ulong)

- ea: `0x18059b7a4`
- end: `0x18059b8f0`
- name: `?GetRegisterdPDMPath@@YAJAEBU_GUID@@PEAGK@Z`
- size: `332`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18059b8f8`
- `0x18059bb9c`

## callees

- `0x18029e7f4`
- `0x18059b7a4`
- `0x1805a9e80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18059b89b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18059b89b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18059b888`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18059b888`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18059b85a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18059b85a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18059b8ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18059b8ac`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18059b7fd`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18059b7fd`

## string_xrefs

- `0x18059b818`: `CLSID\%s\InProcServer32`

## pseudocode

```c
__int64 __fastcall GetRegisterdPDMPath(const struct _GUID *a1, BYTE *a2)
{
  HRESULT v3; // ebx
  LSTATUS Value; // edi
  DWORD cbData[2]; // [rsp+38h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+58h] [rbp-B0h] BYREF

  cbData[0] = 520;
  lpsz = 0;
  v3 = StringFromCLSID(a1, &lpsz);
  if ( v3 >= 0 )
  {
    Value = 0;
    v3 = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%s\\InProcServer32", lpsz);
    if ( v3 >= 0 )
    {
      hKey = 0;
      Value = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey);
      if ( !Value )
      {
        Value = RegQueryValueExW(hKey, 0, 0, 0, a2, cbData);
        RegCloseKey(hKey);
      }
    }
    CoTaskMemFree(lpsz);
    if ( Value )
    {
      if ( Value > 0 )
        return (unsigned __int16)Value | 0x80070000;
      else
        return (unsigned int)Value;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18059b7a4  mov     rax, rsp
0x18059b7a7  mov     [rax+20h], rbx
0x18059b7ab  mov     [rax+18h], r8d
0x18059b7af  mov     [rax+10h], rdx
0x18059b7b3  mov     [rax+8], rcx
0x18059b7b7  push    rbp
0x18059b7b8  push    rsi
0x18059b7b9  push    rdi
0x18059b7ba  lea     rbp, [rax-188h]
0x18059b7c1  sub     rsp, 270h
0x18059b7c8  mov     rax, cs:__security_cookie
0x18059b7cf  xor     rax, rsp
0x18059b7d2  mov     [rbp+180h+var_20], rax
0x18059b7d9  mov     rcx, [rbp+180h+rclsid]; rclsid
0x18059b7e0  lea     rdx, [rsp+280h+lpsz]; lplpsz
0x18059b7e5  mov     rsi, [rbp+180h+lpData]
0x18059b7ec  mov     [rsp+280h+cbData], 208h
0x18059b7f4  mov     [rsp+280h+lpsz], 0
0x18059b7fd  call    cs:__imp_StringFromCLSID
0x18059b804  nop     dword ptr [rax+rax+00h]
0x18059b809  mov     ebx, eax
0x18059b80b  test    eax, eax
0x18059b80d  js      loc_18059B8CB
0x18059b813  mov     r9, [rsp+280h+lpsz]
0x18059b818  lea     r8, aClsidSInprocse; "CLSID\\%s\\InProcServer32"
0x18059b81f  mov     edx, 104h; unsigned __int64
0x18059b824  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x18059b829  xor     edi, edi
0x18059b82b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18059b830  mov     ebx, eax
0x18059b832  test    eax, eax
0x18059b834  js      short loc_18059B8A7
0x18059b836  lea     rax, [rsp+280h+hKey]
0x18059b83b  mov     [rsp+280h+hKey], rdi
0x18059b840  mov     r9d, 20019h; samDesired
0x18059b846  mov     [rsp+280h+phkResult], rax; phkResult
0x18059b84b  xor     r8d, r8d; ulOptions
0x18059b84e  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x18059b853  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18059b85a  call    cs:__imp_RegOpenKeyExW
0x18059b861  nop     dword ptr [rax+rax+00h]
0x18059b866  mov     edi, eax
0x18059b868  test    eax, eax
0x18059b86a  jnz     short loc_18059B8A7
0x18059b86c  mov     rcx, [rsp+280h+hKey]; hKey
0x18059b871  lea     rax, [rsp+280h+cbData]
0x18059b876  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18059b87b  xor     r9d, r9d; lpType
0x18059b87e  xor     r8d, r8d; lpReserved
0x18059b881  mov     [rsp+280h+phkResult], rsi; lpData
0x18059b886  xor     edx, edx; lpValueName
0x18059b888  call    cs:__imp_RegQueryValueExW
0x18059b88f  nop     dword ptr [rax+rax+00h]
0x18059b894  mov     rcx, [rsp+280h+hKey]; hKey
0x18059b899  mov     edi, eax
0x18059b89b  call    cs:__imp_RegCloseKey
0x18059b8a2  nop     dword ptr [rax+rax+00h]
0x18059b8a7  mov     rcx, [rsp+280h+lpsz]; pv
0x18059b8ac  call    cs:__imp_CoTaskMemFree
0x18059b8b3  nop     dword ptr [rax+rax+00h]
0x18059b8b8  test    edi, edi
0x18059b8ba  jz      short loc_18059B8CB
0x18059b8bc  jg      short loc_18059B8C2
0x18059b8be  mov     ebx, edi
0x18059b8c0  jmp     short loc_18059B8CB
0x18059b8c2  movzx   ebx, di
0x18059b8c5  or      ebx, 80070000h
0x18059b8cb  mov     eax, ebx
0x18059b8cd  mov     rcx, [rbp+180h+var_20]
0x18059b8d4  xor     rcx, rsp; StackCookie
0x18059b8d7  call    __security_check_cookie
0x18059b8dc  mov     rbx, [rsp+280h+arg_18]
0x18059b8e4  add     rsp, 270h
0x18059b8eb  pop     rdi
0x18059b8ec  pop     rsi
0x18059b8ed  pop     rbp
0x18059b8ee  retn
```
