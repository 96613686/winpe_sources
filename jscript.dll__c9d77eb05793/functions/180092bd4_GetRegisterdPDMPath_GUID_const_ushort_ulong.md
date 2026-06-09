# GetRegisterdPDMPath(_GUID const &,ushort *,ulong)

- ea: `0x180092bd4`
- end: `0x180092ce9`
- name: `?GetRegisterdPDMPath@@YAJAEBU_GUID@@PEAGK@Z`
- size: `277`
- prototype: `int(const struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180092cf0`

## callees

- `0x180042ad8`
- `0x180092bd4`
- `0x1800942d0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180092ca1`
- `ADVAPI32!RegCloseKey` at `0x180092ca1`
- `ADVAPI32!RegQueryValueExW` at `0x180092c94`
- `ADVAPI32!RegQueryValueExW` at `0x180092c94`
- `ADVAPI32!RegOpenKeyExW` at `0x180092c6c`
- `ADVAPI32!RegOpenKeyExW` at `0x180092c6c`
- `ole32!CoTaskMemFree` at `0x180092cac`
- `ole32!CoTaskMemFree` at `0x180092cac`
- `ole32!StringFromCLSID` at `0x180092c15`
- `ole32!StringFromCLSID` at `0x180092c15`

## string_xrefs

- `0x180092c2a`: `CLSID\%s\InProcServer32`

## pseudocode

```c
__int64 __fastcall GetRegisterdPDMPath(const struct _GUID *a1, BYTE *a2)
{
  HRESULT v3; // ebx
  LSTATUS v4; // edi
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  LPOLESTR lpsz; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  cbData = 520;
  lpsz = 0;
  v3 = StringFromCLSID(a1, &lpsz);
  if ( v3 >= 0 )
  {
    v4 = 0;
    v3 = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%s\\InProcServer32", lpsz);
    if ( v3 >= 0 )
    {
      hKey = 0;
      v4 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey);
      if ( !v4 )
      {
        v4 = RegQueryValueExW(hKey, 0, 0, 0, a2, &cbData);
        RegCloseKey(hKey);
      }
    }
    CoTaskMemFree(lpsz);
    if ( v4 )
    {
      if ( v4 > 0 )
        return (unsigned __int16)v4 | 0x80070000;
      else
        return (unsigned int)v4;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180092bd4  mov     [rsp-8+arg_10], rbx
0x180092bd9  push    rbp
0x180092bda  push    rsi
0x180092bdb  push    rdi
0x180092bdc  lea     rbp, [rsp-170h]
0x180092be4  sub     rsp, 270h
0x180092beb  mov     rax, cs:__security_cookie
0x180092bf2  xor     rax, rsp
0x180092bf5  mov     [rbp+180h+var_20], rax
0x180092bfc  mov     rsi, rdx
0x180092bff  mov     [rsp+280h+cbData], 208h
0x180092c07  lea     rdx, [rsp+280h+lpsz]; lplpsz
0x180092c0c  mov     [rsp+280h+lpsz], 0
0x180092c15  call    cs:__imp_StringFromCLSID
0x180092c1b  mov     ebx, eax
0x180092c1d  test    eax, eax
0x180092c1f  js      loc_180092CC5
0x180092c25  mov     r9, [rsp+280h+lpsz]
0x180092c2a  lea     r8, aClsidSInprocse; "CLSID\\%s\\InProcServer32"
0x180092c31  mov     edx, 104h; unsigned __int64
0x180092c36  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180092c3b  xor     edi, edi
0x180092c3d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180092c42  mov     ebx, eax
0x180092c44  test    eax, eax
0x180092c46  js      short loc_180092CA7
0x180092c48  lea     rax, [rsp+280h+hKey]
0x180092c4d  mov     [rsp+280h+hKey], rdi
0x180092c52  mov     r9d, 20019h; samDesired
0x180092c58  mov     [rsp+280h+phkResult], rax; phkResult
0x180092c5d  xor     r8d, r8d; ulOptions
0x180092c60  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180092c65  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180092c6c  call    cs:__imp_RegOpenKeyExW
0x180092c72  mov     edi, eax
0x180092c74  test    eax, eax
0x180092c76  jnz     short loc_180092CA7
0x180092c78  mov     rcx, [rsp+280h+hKey]; hKey
0x180092c7d  lea     rax, [rsp+280h+cbData]
0x180092c82  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180092c87  xor     r9d, r9d; lpType
0x180092c8a  xor     r8d, r8d; lpReserved
0x180092c8d  mov     [rsp+280h+phkResult], rsi; lpData
0x180092c92  xor     edx, edx; lpValueName
0x180092c94  call    cs:__imp_RegQueryValueExW
0x180092c9a  mov     rcx, [rsp+280h+hKey]; hKey
0x180092c9f  mov     edi, eax
0x180092ca1  call    cs:__imp_RegCloseKey
0x180092ca7  mov     rcx, [rsp+280h+lpsz]; pv
0x180092cac  call    cs:__imp_CoTaskMemFree
0x180092cb2  test    edi, edi
0x180092cb4  jz      short loc_180092CC5
0x180092cb6  jg      short loc_180092CBC
0x180092cb8  mov     ebx, edi
0x180092cba  jmp     short loc_180092CC5
0x180092cbc  movzx   ebx, di
0x180092cbf  or      ebx, 80070000h
0x180092cc5  mov     eax, ebx
0x180092cc7  mov     rcx, [rbp+180h+var_20]
0x180092cce  xor     rcx, rsp; StackCookie
0x180092cd1  call    __security_check_cookie
0x180092cd6  mov     rbx, [rsp+280h+arg_10]
0x180092cde  add     rsp, 270h
0x180092ce5  pop     rdi
0x180092ce6  pop     rsi
0x180092ce7  pop     rbp
0x180092ce8  retn
```
