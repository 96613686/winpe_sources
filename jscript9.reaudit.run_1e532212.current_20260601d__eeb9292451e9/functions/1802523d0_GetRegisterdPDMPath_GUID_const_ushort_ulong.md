# GetRegisterdPDMPath(_GUID const &,ushort *,ulong)

- ea: `0x1802523d0`
- end: `0x1802524fd`
- name: `?GetRegisterdPDMPath@@YAJAEBU_GUID@@PEAGK@Z`
- size: `301`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180252504`
- `0x180252784`

## callees

- `0x1801a071c`
- `0x1802523d0`
- `0x180341dd0`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1802524b5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1802524b5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180252480`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180252480`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1802524a8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1802524a8`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromCLSID` at `0x180252429`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromCLSID` at `0x180252429`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802524c0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802524c0`

## string_xrefs

- `0x18025243e`: `CLSID\%s\InProcServer32`

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
0x1802523d0  mov     rax, rsp
0x1802523d3  mov     [rax+20h], rbx
0x1802523d7  mov     [rax+18h], r8d
0x1802523db  mov     [rax+10h], rdx
0x1802523df  mov     [rax+8], rcx
0x1802523e3  push    rbp
0x1802523e4  push    rsi
0x1802523e5  push    rdi
0x1802523e6  lea     rbp, [rax-188h]
0x1802523ed  sub     rsp, 270h
0x1802523f4  mov     rax, cs:__security_cookie
0x1802523fb  xor     rax, rsp
0x1802523fe  mov     [rbp+180h+var_20], rax
0x180252405  mov     rcx, [rbp+180h+rclsid]; rclsid
0x18025240c  lea     rdx, [rsp+280h+lpsz]; lplpsz
0x180252411  mov     rsi, [rbp+180h+lpData]
0x180252418  mov     [rsp+280h+cbData], 208h
0x180252420  mov     [rsp+280h+lpsz], 0
0x180252429  call    cs:__imp_StringFromCLSID
0x18025242f  mov     ebx, eax
0x180252431  test    eax, eax
0x180252433  js      loc_1802524D9
0x180252439  mov     r9, [rsp+280h+lpsz]
0x18025243e  lea     r8, aClsidSInprocse; "CLSID\\%s\\InProcServer32"
0x180252445  mov     edx, 104h; unsigned __int64
0x18025244a  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x18025244f  xor     edi, edi
0x180252451  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180252456  mov     ebx, eax
0x180252458  test    eax, eax
0x18025245a  js      short loc_1802524BB
0x18025245c  lea     rax, [rsp+280h+hKey]
0x180252461  mov     [rsp+280h+hKey], rdi
0x180252466  mov     r9d, 20019h; samDesired
0x18025246c  mov     [rsp+280h+phkResult], rax; phkResult
0x180252471  xor     r8d, r8d; ulOptions
0x180252474  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180252479  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180252480  call    cs:__imp_RegOpenKeyExW
0x180252486  mov     edi, eax
0x180252488  test    eax, eax
0x18025248a  jnz     short loc_1802524BB
0x18025248c  mov     rcx, [rsp+280h+hKey]; hKey
0x180252491  lea     rax, [rsp+280h+cbData]
0x180252496  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18025249b  xor     r9d, r9d; lpType
0x18025249e  xor     r8d, r8d; lpReserved
0x1802524a1  mov     [rsp+280h+phkResult], rsi; lpData
0x1802524a6  xor     edx, edx; lpValueName
0x1802524a8  call    cs:__imp_RegQueryValueExW
0x1802524ae  mov     rcx, [rsp+280h+hKey]; hKey
0x1802524b3  mov     edi, eax
0x1802524b5  call    cs:__imp_RegCloseKey
0x1802524bb  mov     rcx, [rsp+280h+lpsz]; pv
0x1802524c0  call    cs:__imp_CoTaskMemFree
0x1802524c6  test    edi, edi
0x1802524c8  jz      short loc_1802524D9
0x1802524ca  jg      short loc_1802524D0
0x1802524cc  mov     ebx, edi
0x1802524ce  jmp     short loc_1802524D9
0x1802524d0  movzx   ebx, di
0x1802524d3  or      ebx, 80070000h
0x1802524d9  mov     eax, ebx
0x1802524db  mov     rcx, [rbp+180h+var_20]
0x1802524e2  xor     rcx, rsp; StackCookie
0x1802524e5  call    __security_check_cookie
0x1802524ea  mov     rbx, [rsp+280h+arg_18]
0x1802524f2  add     rsp, 270h
0x1802524f9  pop     rdi
0x1802524fa  pop     rsi
0x1802524fb  pop     rbp
0x1802524fc  retn
```
