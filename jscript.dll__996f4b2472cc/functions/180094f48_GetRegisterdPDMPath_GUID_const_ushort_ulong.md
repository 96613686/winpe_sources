# GetRegisterdPDMPath(_GUID const &,ushort *,ulong)

- ea: `0x180094f48`
- end: `0x18009507c`
- name: `?GetRegisterdPDMPath@@YAJAEBU_GUID@@PEAGK@Z`
- size: `308`
- prototype: `int(const struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180095084`

## callees

- `0x180043d14`
- `0x180094f48`
- `0x1800966e0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180095027`
- `ADVAPI32!RegCloseKey` at `0x180095027`
- `ADVAPI32!RegQueryValueExW` at `0x180095014`
- `ADVAPI32!RegQueryValueExW` at `0x180095014`
- `ADVAPI32!RegOpenKeyExW` at `0x180094fe6`
- `ADVAPI32!RegOpenKeyExW` at `0x180094fe6`
- `ole32!CoTaskMemFree` at `0x180095038`
- `ole32!CoTaskMemFree` at `0x180095038`
- `ole32!StringFromCLSID` at `0x180094f89`
- `ole32!StringFromCLSID` at `0x180094f89`

## string_xrefs

- `0x180094fa4`: `CLSID\%s\InProcServer32`

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
0x180094f48  mov     [rsp-8+arg_10], rbx
0x180094f4d  push    rbp
0x180094f4e  push    rsi
0x180094f4f  push    rdi
0x180094f50  lea     rbp, [rsp-170h]
0x180094f58  sub     rsp, 270h
0x180094f5f  mov     rax, cs:__security_cookie
0x180094f66  xor     rax, rsp
0x180094f69  mov     [rbp+180h+var_20], rax
0x180094f70  mov     rsi, rdx
0x180094f73  mov     [rsp+280h+cbData], 208h
0x180094f7b  lea     rdx, [rsp+280h+lpsz]; lplpsz
0x180094f80  mov     [rsp+280h+lpsz], 0
0x180094f89  call    cs:__imp_StringFromCLSID
0x180094f90  nop     dword ptr [rax+rax+00h]
0x180094f95  mov     ebx, eax
0x180094f97  test    eax, eax
0x180094f99  js      loc_180095057
0x180094f9f  mov     r9, [rsp+280h+lpsz]
0x180094fa4  lea     r8, aClsidSInprocse; "CLSID\\%s\\InProcServer32"
0x180094fab  mov     edx, 104h; unsigned __int64
0x180094fb0  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180094fb5  xor     edi, edi
0x180094fb7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180094fbc  mov     ebx, eax
0x180094fbe  test    eax, eax
0x180094fc0  js      short loc_180095033
0x180094fc2  lea     rax, [rsp+280h+hKey]
0x180094fc7  mov     [rsp+280h+hKey], rdi
0x180094fcc  mov     r9d, 20019h; samDesired
0x180094fd2  mov     [rsp+280h+phkResult], rax; phkResult
0x180094fd7  xor     r8d, r8d; ulOptions
0x180094fda  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180094fdf  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180094fe6  call    cs:__imp_RegOpenKeyExW
0x180094fed  nop     dword ptr [rax+rax+00h]
0x180094ff2  mov     edi, eax
0x180094ff4  test    eax, eax
0x180094ff6  jnz     short loc_180095033
0x180094ff8  mov     rcx, [rsp+280h+hKey]; hKey
0x180094ffd  lea     rax, [rsp+280h+cbData]
0x180095002  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180095007  xor     r9d, r9d; lpType
0x18009500a  xor     r8d, r8d; lpReserved
0x18009500d  mov     [rsp+280h+phkResult], rsi; lpData
0x180095012  xor     edx, edx; lpValueName
0x180095014  call    cs:__imp_RegQueryValueExW
0x18009501b  nop     dword ptr [rax+rax+00h]
0x180095020  mov     rcx, [rsp+280h+hKey]; hKey
0x180095025  mov     edi, eax
0x180095027  call    cs:__imp_RegCloseKey
0x18009502e  nop     dword ptr [rax+rax+00h]
0x180095033  mov     rcx, [rsp+280h+lpsz]; pv
0x180095038  call    cs:__imp_CoTaskMemFree
0x18009503f  nop     dword ptr [rax+rax+00h]
0x180095044  test    edi, edi
0x180095046  jz      short loc_180095057
0x180095048  jg      short loc_18009504E
0x18009504a  mov     ebx, edi
0x18009504c  jmp     short loc_180095057
0x18009504e  movzx   ebx, di
0x180095051  or      ebx, 80070000h
0x180095057  mov     eax, ebx
0x180095059  mov     rcx, [rbp+180h+var_20]
0x180095060  xor     rcx, rsp; StackCookie
0x180095063  call    __security_check_cookie
0x180095068  mov     rbx, [rsp+280h+arg_10]
0x180095070  add     rsp, 270h
0x180095077  pop     rdi
0x180095078  pop     rsi
0x180095079  pop     rbp
0x18009507a  retn
```
