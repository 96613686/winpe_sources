# GetRegisterdPDMPath(_GUID const &,ushort *,ulong)

- ea: `0x180256910`
- end: `0x180256a5c`
- name: `?GetRegisterdPDMPath@@YAJAEBU_GUID@@PEAGK@Z`
- size: `332`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180256a64`
- `0x180256d08`

## callees

- `0x1801a2a90`
- `0x180256910`
- `0x1803481f0`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180256a07`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180256a07`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1802569c6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1802569c6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1802569f4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1802569f4`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromCLSID` at `0x180256969`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromCLSID` at `0x180256969`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180256a18`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180256a18`

## string_xrefs

- `0x180256984`: `CLSID\%s\InProcServer32`

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
0x180256910  mov     rax, rsp
0x180256913  mov     [rax+20h], rbx
0x180256917  mov     [rax+18h], r8d
0x18025691b  mov     [rax+10h], rdx
0x18025691f  mov     [rax+8], rcx
0x180256923  push    rbp
0x180256924  push    rsi
0x180256925  push    rdi
0x180256926  lea     rbp, [rax-188h]
0x18025692d  sub     rsp, 270h
0x180256934  mov     rax, cs:__security_cookie
0x18025693b  xor     rax, rsp
0x18025693e  mov     [rbp+180h+var_20], rax
0x180256945  mov     rcx, [rbp+180h+rclsid]; rclsid
0x18025694c  lea     rdx, [rsp+280h+lpsz]; lplpsz
0x180256951  mov     rsi, [rbp+180h+lpData]
0x180256958  mov     [rsp+280h+cbData], 208h
0x180256960  mov     [rsp+280h+lpsz], 0
0x180256969  call    cs:__imp_StringFromCLSID
0x180256970  nop     dword ptr [rax+rax+00h]
0x180256975  mov     ebx, eax
0x180256977  test    eax, eax
0x180256979  js      loc_180256A37
0x18025697f  mov     r9, [rsp+280h+lpsz]
0x180256984  lea     r8, aClsidSInprocse; "CLSID\\%s\\InProcServer32"
0x18025698b  mov     edx, 104h; unsigned __int64
0x180256990  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180256995  xor     edi, edi
0x180256997  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18025699c  mov     ebx, eax
0x18025699e  test    eax, eax
0x1802569a0  js      short loc_180256A13
0x1802569a2  lea     rax, [rsp+280h+hKey]
0x1802569a7  mov     [rsp+280h+hKey], rdi
0x1802569ac  mov     r9d, 20019h; samDesired
0x1802569b2  mov     [rsp+280h+phkResult], rax; phkResult
0x1802569b7  xor     r8d, r8d; ulOptions
0x1802569ba  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x1802569bf  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1802569c6  call    cs:__imp_RegOpenKeyExW
0x1802569cd  nop     dword ptr [rax+rax+00h]
0x1802569d2  mov     edi, eax
0x1802569d4  test    eax, eax
0x1802569d6  jnz     short loc_180256A13
0x1802569d8  mov     rcx, [rsp+280h+hKey]; hKey
0x1802569dd  lea     rax, [rsp+280h+cbData]
0x1802569e2  mov     [rsp+280h+lpcbData], rax; lpcbData
0x1802569e7  xor     r9d, r9d; lpType
0x1802569ea  xor     r8d, r8d; lpReserved
0x1802569ed  mov     [rsp+280h+phkResult], rsi; lpData
0x1802569f2  xor     edx, edx; lpValueName
0x1802569f4  call    cs:__imp_RegQueryValueExW
0x1802569fb  nop     dword ptr [rax+rax+00h]
0x180256a00  mov     rcx, [rsp+280h+hKey]; hKey
0x180256a05  mov     edi, eax
0x180256a07  call    cs:__imp_RegCloseKey
0x180256a0e  nop     dword ptr [rax+rax+00h]
0x180256a13  mov     rcx, [rsp+280h+lpsz]; pv
0x180256a18  call    cs:__imp_CoTaskMemFree
0x180256a1f  nop     dword ptr [rax+rax+00h]
0x180256a24  test    edi, edi
0x180256a26  jz      short loc_180256A37
0x180256a28  jg      short loc_180256A2E
0x180256a2a  mov     ebx, edi
0x180256a2c  jmp     short loc_180256A37
0x180256a2e  movzx   ebx, di
0x180256a31  or      ebx, 80070000h
0x180256a37  mov     eax, ebx
0x180256a39  mov     rcx, [rbp+180h+var_20]
0x180256a40  xor     rcx, rsp; StackCookie
0x180256a43  call    __security_check_cookie
0x180256a48  mov     rbx, [rsp+280h+arg_18]
0x180256a50  add     rsp, 270h
0x180256a57  pop     rdi
0x180256a58  pop     rsi
0x180256a59  pop     rbp
0x180256a5a  retn
```
