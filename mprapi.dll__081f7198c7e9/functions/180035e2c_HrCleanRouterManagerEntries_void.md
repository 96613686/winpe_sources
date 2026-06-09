# HrCleanRouterManagerEntries(void)

- ea: `0x180035e2c`
- end: `0x180035f7b`
- name: `?HrCleanRouterManagerEntries@@YAJXZ`
- size: `335`
- prototype: `LSTATUS(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800356d0`

## callees

- `0x180035e2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035f6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035f6e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180035e92`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180035ede`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180035f2a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180035e92`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180035ede`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180035f2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035e5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035e5a`
- `rtutils!TracePrintfW` at `0x180035ec6`
- `rtutils!TracePrintfW` at `0x180035f12`
- `rtutils!TracePrintfW` at `0x180035f5e`
- `rtutils!TracePrintfW` at `0x180035ec6`
- `rtutils!TracePrintfW` at `0x180035f12`
- `rtutils!TracePrintfW` at `0x180035f5e`

## string_xrefs

- `0x180035e4c`: `System\CurrentControlSet\Services\RemoteAccess\RouterManagers`
- `0x180035eac`: `HrMprConfigTransportGetInfo: RegDeleteKey for Ip`
- `0x180035ef8`: `HrMprConfigTransportGetInfo: RegDeleteKey for Ipv6`
- `0x180035f44`: `HrMprConfigTransportGetInfo: RegDeleteKey for Ipx`

## pseudocode

```c
LSTATUS HrCleanRouterManagerEntries(void)
{
  LSTATUS result; // eax
  int v1; // eax
  bool v2; // sf
  const WCHAR *v3; // rdx
  int v4; // eax
  bool v5; // sf
  const WCHAR *v6; // rdx
  int v7; // eax
  bool v8; // sf
  const WCHAR *v9; // rdx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\RemoteAccess\\RouterManagers",
             0,
             0x2000000u,
             &hKey);
  if ( result != 2 )
  {
    if ( result )
    {
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    v1 = RegDeleteKeyExW(hKey, L"Ip", 0, 0);
    v2 = v1 < 0;
    if ( v1 > 0 )
    {
      v1 = (unsigned __int16)v1 | 0x80070000;
      v2 = v1 < 0;
    }
    v3 = L"%hs succeeded : hr = %08lx";
    if ( v2 )
      v3 = L"%hs failed : hr = %08lx";
    TracePrintfW(g_dwTraceHandle, v3, "HrMprConfigTransportGetInfo: RegDeleteKey for Ip", (unsigned int)v1);
    v4 = RegDeleteKeyExW(hKey, L"Ipv6", 0, 0);
    v5 = v4 < 0;
    if ( v4 > 0 )
    {
      v4 = (unsigned __int16)v4 | 0x80070000;
      v5 = v4 < 0;
    }
    v6 = L"%hs succeeded : hr = %08lx";
    if ( v5 )
      v6 = L"%hs failed : hr = %08lx";
    TracePrintfW(g_dwTraceHandle, v6, "HrMprConfigTransportGetInfo: RegDeleteKey for Ipv6", (unsigned int)v4);
    v7 = RegDeleteKeyExW(hKey, L"Ipx", 0, 0);
    v8 = v7 < 0;
    if ( v7 > 0 )
    {
      v7 = (unsigned __int16)v7 | 0x80070000;
      v8 = v7 < 0;
    }
    v9 = L"%hs succeeded : hr = %08lx";
    if ( v8 )
      v9 = L"%hs failed : hr = %08lx";
    TracePrintfW(g_dwTraceHandle, v9, "HrMprConfigTransportGetInfo: RegDeleteKey for Ipx", (unsigned int)v7);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180035e2c  sub     rsp, 38h
0x180035e30  lea     rax, [rsp+38h+hKey]
0x180035e35  mov     [rsp+38h+hKey], 0
0x180035e3e  mov     r9d, 2000000h; samDesired
0x180035e44  mov     [rsp+38h+phkResult], rax; phkResult
0x180035e49  xor     r8d, r8d; ulOptions
0x180035e4c  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Re"...
0x180035e53  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035e5a  call    cs:__imp_RegOpenKeyExW
0x180035e60  cmp     eax, 2
0x180035e63  jz      loc_180035F64
0x180035e69  test    eax, eax
0x180035e6b  jz      short loc_180035E80
0x180035e6d  jle     loc_180035F76
0x180035e73  movzx   eax, ax
0x180035e76  or      eax, 80070000h
0x180035e7b  jmp     loc_180035F76
0x180035e80  mov     rcx, [rsp+38h+hKey]; hKey
0x180035e85  lea     rdx, aIp; "Ip"
0x180035e8c  xor     r9d, r9d; Reserved
0x180035e8f  xor     r8d, r8d; samDesired
0x180035e92  call    cs:__imp_RegDeleteKeyExW
0x180035e98  test    eax, eax
0x180035e9a  jle     short loc_180035EA6
0x180035e9c  movzx   eax, ax
0x180035e9f  or      eax, 80070000h
0x180035ea4  test    eax, eax
0x180035ea6  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180035eac  lea     r8, aHrmprconfigtra; "HrMprConfigTransportGetInfo: RegDeleteK"...
0x180035eb3  mov     r9d, eax
0x180035eb6  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x180035ebd  jns     short loc_180035EC6
0x180035ebf  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x180035ec6  call    cs:__imp_TracePrintfW
0x180035ecc  mov     rcx, [rsp+38h+hKey]; hKey
0x180035ed1  lea     rdx, aIpv6; "Ipv6"
0x180035ed8  xor     r9d, r9d; Reserved
0x180035edb  xor     r8d, r8d; samDesired
0x180035ede  call    cs:__imp_RegDeleteKeyExW
0x180035ee4  test    eax, eax
0x180035ee6  jle     short loc_180035EF2
0x180035ee8  movzx   eax, ax
0x180035eeb  or      eax, 80070000h
0x180035ef0  test    eax, eax
0x180035ef2  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180035ef8  lea     r8, aHrmprconfigtra_3; "HrMprConfigTransportGetInfo: RegDeleteK"...
0x180035eff  mov     r9d, eax
0x180035f02  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x180035f09  jns     short loc_180035F12
0x180035f0b  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x180035f12  call    cs:__imp_TracePrintfW
0x180035f18  mov     rcx, [rsp+38h+hKey]; hKey
0x180035f1d  lea     rdx, aIpx; "Ipx"
0x180035f24  xor     r9d, r9d; Reserved
0x180035f27  xor     r8d, r8d; samDesired
0x180035f2a  call    cs:__imp_RegDeleteKeyExW
0x180035f30  test    eax, eax
0x180035f32  jle     short loc_180035F3E
0x180035f34  movzx   eax, ax
0x180035f37  or      eax, 80070000h
0x180035f3c  test    eax, eax
0x180035f3e  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180035f44  lea     r8, aHrmprconfigtra_0; "HrMprConfigTransportGetInfo: RegDeleteK"...
0x180035f4b  mov     r9d, eax
0x180035f4e  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x180035f55  jns     short loc_180035F5E
0x180035f57  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x180035f5e  call    cs:__imp_TracePrintfW
0x180035f64  mov     rcx, [rsp+38h+hKey]; hKey
0x180035f69  test    rcx, rcx
0x180035f6c  jz      short loc_180035F74
0x180035f6e  call    cs:__imp_RegCloseKey
0x180035f74  xor     eax, eax
0x180035f76  add     rsp, 38h
0x180035f7a  retn
```
