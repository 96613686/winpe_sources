# IkeGetGwSvcIkeDllName

- ea: `0x180095060`
- end: `0x180095167`
- name: `IkeGetGwSvcIkeDllName`
- size: `263`
- prototype: `__int64 __fastcall(BYTE *pszDest)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180095274`

## callees

- `0x1800061ec`
- `0x18004aa3c`
- `0x180050850`
- `0x18005453c`
- `0x180095060`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095140`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095140`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800950fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800950fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800950c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800950c8`

## string_xrefs

- `0x1800950a4`: `SYSTEM\CurrentControlSet\Services\IKEEXT\Parameters`
- `0x1800950d2`: `RegOpenKeyExW`
- `0x180095081`: `IkeGetGwSvcIkeDllName`
- `0x180095148`: `IkeGetGwSvcIkeDllName`
- `0x180095122`: `azureike.dll`
- `0x1800950f7`: `GwSvcIkeDll`

## pseudocode

```c
__int64 __fastcall IkeGetGwSvcIkeDllName(BYTE *pszDest)
{
  unsigned int v2; // eax
  __int64 v3; // rcx
  const char *v4; // rdx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-20h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-1Ch] BYREF

  hKey = 0;
  Type = 1;
  cbData = 520;
  TraceLogHelper("IkeGetGwSvcIkeDllName", 1);
  *(_WORD *)pszDest = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\IKEEXT\\Parameters", 0, 0x20019u, &hKey);
  if ( v2 )
  {
    v4 = "RegOpenKeyExW";
  }
  else
  {
    v2 = RegQueryValueExW(hKey, L"GwSvcIkeDll", 0, &Type, pszDest, &cbData);
    if ( !v2 )
      goto LABEL_7;
    v4 = "RegQueryValueExW";
  }
  if ( WfpReportSysErrorAsWinError(v3, v4, v2, 1) )
    StringCchCopyW((STRSAFE_LPWSTR)pszDest, 0x104u, L"azureike.dll");
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  return TraceLogHelper("IkeGetGwSvcIkeDllName", 0);
}

```

## disassembly

```asm
0x180095060  push    rbx
0x180095062  sub     rsp, 50h
0x180095066  mov     rax, cs:__security_cookie
0x18009506d  xor     rax, rsp
0x180095070  mov     [rsp+58h+var_18], rax
0x180095075  mov     rbx, rcx
0x180095078  mov     [rsp+58h+hKey], 0
0x180095081  lea     rcx, aIkegetgwsvcike; "IkeGetGwSvcIkeDllName"
0x180095088  mov     [rsp+58h+Type], 1
0x180095090  mov     edx, 1
0x180095095  mov     [rsp+58h+cbData], 208h
0x18009509d  call    TraceLogHelper
0x1800950a2  xor     eax, eax
0x1800950a4  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\IK"...
0x1800950ab  mov     [rbx], ax
0x1800950ae  mov     r9d, 20019h; samDesired
0x1800950b4  lea     rax, [rsp+58h+hKey]
0x1800950b9  xor     r8d, r8d; ulOptions
0x1800950bc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800950c3  mov     [rsp+58h+phkResult], rax; phkResult
0x1800950c8  call    cs:__imp_RegOpenKeyExW
0x1800950ce  test    eax, eax
0x1800950d0  jz      short loc_1800950DB
0x1800950d2  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800950d9  jmp     short loc_18009510F
0x1800950db  mov     rcx, [rsp+58h+hKey]; hKey
0x1800950e0  lea     rax, [rsp+58h+cbData]
0x1800950e5  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800950ea  lea     r9, [rsp+58h+Type]; lpType
0x1800950ef  xor     r8d, r8d; lpReserved
0x1800950f2  mov     [rsp+58h+phkResult], rbx; lpData
0x1800950f7  lea     rdx, aGwsvcikedll; "GwSvcIkeDll"
0x1800950fe  call    cs:__imp_RegQueryValueExW
0x180095104  test    eax, eax
0x180095106  jz      short loc_180095136
0x180095108  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x18009510f  mov     r9d, 1
0x180095115  mov     r8d, eax
0x180095118  call    WfpReportSysErrorAsWinError
0x18009511d  test    rax, rax
0x180095120  jz      short loc_180095136
0x180095122  lea     r8, aAzureikeDll; "azureike.dll"
0x180095129  mov     edx, 104h; cchDest
0x18009512e  mov     rcx, rbx; pszDest
0x180095131  call    StringCchCopyW
0x180095136  mov     rcx, [rsp+58h+hKey]; hKey
0x18009513b  test    rcx, rcx
0x18009513e  jz      short loc_180095146
0x180095140  call    cs:__imp_RegCloseKey
0x180095146  xor     edx, edx
0x180095148  lea     rcx, aIkegetgwsvcike; "IkeGetGwSvcIkeDllName"
0x18009514f  call    TraceLogHelper
0x180095154  mov     rcx, [rsp+58h+var_18]
0x180095159  xor     rcx, rsp; StackCookie
0x18009515c  call    __security_check_cookie
0x180095161  add     rsp, 50h
0x180095165  pop     rbx
0x180095166  retn
```
