# WriteToERMTracked(ushort const *,ushort const *,ushort const *,IConfigManager2URI *)

- ea: `0x180010dc0`
- end: `0x1800110a9`
- name: `?WriteToERMTracked@@YAJPEBG00PEAUIConfigManager2URI@@@Z`
- size: `745`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IConfigManager2URI *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010170`
- `0x180010610`
- `0x180010864`

## callees

- `0x1800022e0`
- `0x180006c98`
- `0x180010dc0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ea5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010fa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ea5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010fa6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010eb8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010fb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010eb8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010fb9`
- `OLEAUT32!__imp_SysFreeString` at `0x180010e7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180010fb1`
- `OLEAUT32!__imp_SysFreeString` at `0x180011069`
- `OLEAUT32!__imp_SysFreeString` at `0x180010e7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180010fb1`
- `OLEAUT32!__imp_SysFreeString` at `0x180011069`
- `OLEAUT32!__imp_SysStringLen` at `0x180010fe8`
- `OLEAUT32!__imp_SysStringLen` at `0x180010fe8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011016`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001104f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011016`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001104f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010e8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010eb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001107a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010e8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010eb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001107a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010f5e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010f5e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010f06`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010f06`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180010e1e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180010e1e`

## string_xrefs

- `0x180010f77`: `Path%d`

## pseudocode

```c
__int64 __fastcall WriteToERMTracked(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IConfigManager2URI *a4)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v7; // r9
  signed int v8; // ebx
  LSTATUS v10; // eax
  bool v11; // cc
  __int64 (__fastcall *v12)(struct IConfigManager2URI *, _QWORD, _QWORD, BSTR *); // rsi
  OLECHAR *v13; // rdi
  DWORD LastError; // ebx
  int v15; // edi
  UINT v16; // eax
  BYTE pvData[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbData; // [rsp+6Ch] [rbp-94h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  dwDisposition = 0;
  *(_DWORD *)pvData = 0;
  pcbData = 4;
  bstrString = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, a2);
  v7 = L"OSData\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
  if ( !IsStateSeparationEnabled )
    v7 = L"Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
  v8 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s\\%s", v7, L"B92E7305-9462-4B48-AE6D-57D9D09FD698", a2, L"default");
  if ( v8 < 0 )
    goto LABEL_4;
  hKey = 0;
  v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
  v8 = v10;
  v11 = v10 <= 0;
  if ( v10 )
    goto LABEL_10;
  if ( dwDisposition == 2 && RegGetValueW(hKey, 0, L"count", 0x18u, 0, pvData, &pcbData) )
    *(_DWORD *)pvData = 0;
  v8 = StringCchPrintfW(SubKey, 0x104u, L"Path%d");
  if ( v8 < 0 )
    goto LABEL_4;
  v12 = *(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, _QWORD, BSTR *))(*(_QWORD *)a4 + 64LL);
  v13 = bstrString;
  if ( bstrString )
  {
    LastError = GetLastError();
    SysFreeString(v13);
    SetLastError(LastError);
  }
  bstrString = 0;
  v15 = v12(a4, 0, 0, &bstrString);
  if ( v15 >= 0 )
  {
    v16 = SysStringLen(bstrString);
    v10 = RegSetValueExW(hKey, SubKey, 0, 1u, (const BYTE *)bstrString, 2 * v16 + 2);
    v8 = v10;
    v11 = v10 <= 0;
    if ( v10
      || (++*(_DWORD *)pvData, v10 = RegSetValueExW(hKey, L"count", 0, 4u, pvData, 4u), v8 = v10, v11 = v10 <= 0, v10) )
    {
LABEL_10:
      if ( !v11 )
        v8 = (unsigned __int16)v10 | 0x80070000;
LABEL_4:
      if ( bstrString )
        SysFreeString(bstrString);
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v8;
    }
  }
  if ( bstrString )
    SysFreeString(bstrString);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180010dc0  mov     [rsp-8+arg_0], rbx
0x180010dc5  mov     [rsp-8+arg_10], rsi
0x180010dca  push    rbp
0x180010dcb  push    rdi
0x180010dcc  push    r14
0x180010dce  lea     rbp, [rsp-190h]
0x180010dd6  sub     rsp, 290h
0x180010ddd  mov     rax, cs:__security_cookie
0x180010de4  xor     rax, rsp
0x180010de7  mov     [rbp+1A0h+var_20], rax
0x180010dee  mov     r14, r9
0x180010df1  mov     rbx, rdx
0x180010df4  mov     [rsp+2A0h+hKey], 0
0x180010dfd  mov     [rsp+2A0h+dwDisposition], 0
0x180010e05  mov     dword ptr [rsp+2A0h+pvData], 0
0x180010e0d  mov     [rsp+2A0h+pcbData], 4
0x180010e15  mov     [rsp+2A0h+bstrString], 0
0x180010e1e  call    cs:__imp_RtlIsStateSeparationEnabled
0x180010e24  lea     rcx, aSoftwareMicros_4; "Software\\Microsoft\\EnterpriseResource"...
0x180010e2b  lea     r9, aOsdataSoftware_2; "OSData\\Software\\Microsoft\\Enterprise"...
0x180010e32  test    al, al
0x180010e34  cmovz   r9, rcx
0x180010e38  lea     rax, aDefault; "default"
0x180010e3f  mov     [rsp+2A0h+lpSecurityAttributes], rax
0x180010e44  mov     qword ptr [rsp+2A0h+samDesired], rbx
0x180010e49  lea     rax, aB92e730594624b; "B92E7305-9462-4B48-AE6D-57D9D09FD698"
0x180010e50  mov     qword ptr [rsp+2A0h+dwOptions], rax
0x180010e55  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180010e5c  mov     esi, 104h
0x180010e61  mov     edx, esi; unsigned __int64
0x180010e63  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x180010e68  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010e6d  mov     ebx, eax
0x180010e6f  test    eax, eax
0x180010e71  jns     short loc_180010E9B
0x180010e73  mov     rcx, [rsp+2A0h+bstrString]; bstrString
0x180010e78  test    rcx, rcx
0x180010e7b  jz      short loc_180010E84
0x180010e7d  call    cs:__imp_SysFreeString
0x180010e83  nop
0x180010e84  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180010e89  test    rcx, rcx
0x180010e8c  jz      short loc_180010E94
0x180010e8e  call    cs:__imp_RegCloseKey
0x180010e94  mov     eax, ebx
0x180010e96  jmp     loc_180011082
0x180010e9b  mov     rdi, [rsp+2A0h+hKey]
0x180010ea0  test    rdi, rdi
0x180010ea3  jz      short loc_180010EBE
0x180010ea5  call    cs:__imp_GetLastError
0x180010eab  mov     ebx, eax
0x180010ead  mov     rcx, rdi; hKey
0x180010eb0  call    cs:__imp_RegCloseKey
0x180010eb6  mov     ecx, ebx; dwErrCode
0x180010eb8  call    cs:__imp_SetLastError
0x180010ebe  mov     [rsp+2A0h+hKey], 0
0x180010ec7  lea     rax, [rsp+2A0h+dwDisposition]
0x180010ecc  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x180010ed1  lea     rax, [rsp+2A0h+hKey]
0x180010ed6  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180010edb  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010ee4  mov     [rsp+2A0h+samDesired], 2001Fh; samDesired
0x180010eec  mov     [rsp+2A0h+dwOptions], 0; dwOptions
0x180010ef4  xor     r9d, r9d; lpClass
0x180010ef7  xor     r8d, r8d; Reserved
0x180010efa  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x180010eff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010f06  call    cs:__imp_RegCreateKeyExW
0x180010f0c  mov     ebx, eax
0x180010f0e  test    eax, eax
0x180010f10  jz      short loc_180010F26
0x180010f12  jle     loc_180010E73
0x180010f18  movzx   ebx, ax
0x180010f1b  or      ebx, 80070000h
0x180010f21  jmp     loc_180010E73
0x180010f26  cmp     [rsp+2A0h+dwDisposition], 2
0x180010f2b  jnz     short loc_180010F72
0x180010f2d  lea     rax, [rsp+2A0h+pcbData]
0x180010f32  mov     [rsp+2A0h+lpSecurityAttributes], rax; pcbData
0x180010f37  lea     rax, [rsp+2A0h+pvData]
0x180010f3c  mov     qword ptr [rsp+2A0h+samDesired], rax; pvData
0x180010f41  mov     qword ptr [rsp+2A0h+dwOptions], 0; pdwType
0x180010f4a  mov     r9d, 18h; dwFlags
0x180010f50  lea     r8, ValueName; "count"
0x180010f57  xor     edx, edx; lpSubKey
0x180010f59  mov     rcx, [rsp+2A0h+hKey]; hkey
0x180010f5e  call    cs:__imp_RegGetValueW
0x180010f64  test    eax, eax
0x180010f66  jz      short loc_180010F72
0x180010f68  xor     r9d, r9d
0x180010f6b  mov     dword ptr [rsp+2A0h+pvData], r9d
0x180010f70  jmp     short loc_180010F77
0x180010f72  mov     r9d, dword ptr [rsp+2A0h+pvData]
0x180010f77  lea     r8, aPathD; "Path%d"
0x180010f7e  mov     rdx, rsi; unsigned __int64
0x180010f81  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x180010f86  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010f8b  mov     ebx, eax
0x180010f8d  test    eax, eax
0x180010f8f  js      loc_180010E73
0x180010f95  mov     rax, [r14]
0x180010f98  mov     rsi, [rax+40h]
0x180010f9c  mov     rdi, [rsp+2A0h+bstrString]
0x180010fa1  test    rdi, rdi
0x180010fa4  jz      short loc_180010FBF
0x180010fa6  call    cs:__imp_GetLastError
0x180010fac  mov     ebx, eax
0x180010fae  mov     rcx, rdi; bstrString
0x180010fb1  call    cs:__imp_SysFreeString
0x180010fb7  mov     ecx, ebx; dwErrCode
0x180010fb9  call    cs:__imp_SetLastError
0x180010fbf  mov     [rsp+2A0h+bstrString], 0
0x180010fc8  lea     r9, [rsp+2A0h+bstrString]
0x180010fcd  xor     r8d, r8d
0x180010fd0  xor     edx, edx
0x180010fd2  mov     rcx, r14
0x180010fd5  mov     rax, rsi
0x180010fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fdd  mov     edi, eax
0x180010fdf  test    eax, eax
0x180010fe1  js      short loc_18001105F
0x180010fe3  mov     rcx, [rsp+2A0h+bstrString]; pbstr
0x180010fe8  call    cs:__imp_SysStringLen
0x180010fee  lea     eax, ds:2[rax*2]
0x180010ff5  mov     rdx, [rsp+2A0h+bstrString]
0x180010ffa  mov     [rsp+2A0h+samDesired], eax; cbData
0x180010ffe  mov     qword ptr [rsp+2A0h+dwOptions], rdx; lpData
0x180011003  mov     r9d, 1; dwType
0x180011009  xor     r8d, r8d; Reserved
0x18001100c  lea     rdx, [rsp+2A0h+SubKey]; lpValueName
0x180011011  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180011016  call    cs:__imp_RegSetValueExW
0x18001101c  mov     ebx, eax
0x18001101e  test    eax, eax
0x180011020  jnz     loc_180010F12
0x180011026  inc     dword ptr [rsp+2A0h+pvData]
0x18001102a  mov     [rsp+2A0h+samDesired], 4; cbData
0x180011032  lea     rax, [rsp+2A0h+pvData]
0x180011037  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18001103c  lea     r9d, [rbx+4]; dwType
0x180011040  xor     r8d, r8d; Reserved
0x180011043  lea     rdx, ValueName; "count"
0x18001104a  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001104f  call    cs:__imp_RegSetValueExW
0x180011055  mov     ebx, eax
0x180011057  test    eax, eax
0x180011059  jnz     loc_180010F12
0x18001105f  mov     rcx, [rsp+2A0h+bstrString]; bstrString
0x180011064  test    rcx, rcx
0x180011067  jz      short loc_180011070
0x180011069  call    cs:__imp_SysFreeString
0x18001106f  nop
0x180011070  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180011075  test    rcx, rcx
0x180011078  jz      short loc_180011080
0x18001107a  call    cs:__imp_RegCloseKey
0x180011080  mov     eax, edi
0x180011082  mov     rcx, [rbp+1A0h+var_20]
0x180011089  xor     rcx, rsp; StackCookie
0x18001108c  call    __security_check_cookie
0x180011091  lea     r11, [rsp+2A0h+var_10]
0x180011099  mov     rbx, [r11+20h]
0x18001109d  mov     rsi, [r11+30h]
0x1800110a1  mov     rsp, r11
0x1800110a4  pop     r14
0x1800110a6  pop     rdi
0x1800110a7  pop     rbp
0x1800110a8  retn
```
