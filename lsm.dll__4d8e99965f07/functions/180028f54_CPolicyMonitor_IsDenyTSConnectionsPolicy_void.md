# CPolicyMonitor::IsDenyTSConnectionsPolicy(void)

- ea: `0x180028f54`
- end: `0x18002914f`
- name: `?IsDenyTSConnectionsPolicy@CPolicyMonitor@@AEAAHXZ`
- size: `507`
- prototype: `__int64 __fastcall(CPolicyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180054be4`

## callees

- `0x1800077a0`
- `0x180028f54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028fa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002902e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028fa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002902e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028fe8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029078`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800290c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028fe8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029078`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800290c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029128`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029136`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029128`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029136`

## string_xrefs

- `0x180028f8b`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x1800290f3`: `Unable to open REG_CONTROL_TSERVER key`

## pseudocode

```c
__int64 __fastcall CPolicyMonitor::IsDenyTSConnectionsPolicy(CPolicyMonitor *this)
{
  unsigned int v1; // edi
  LSTATUS v2; // eax
  LSTATUS v3; // ebx
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  int v10; // [rsp+64h] [rbp+24h]
  BOOL Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  int v13; // [rsp+78h] [rbp+38h] BYREF

  v10 = HIDWORD(this);
  Type = 0;
  v1 = 1;
  Data = 1;
  cbData = 4;
  hKey = 0;
  phkResult = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
         0,
         0x20019u,
         &hKey);
  v3 = v2;
  if ( !hKey )
  {
    if ( v2 != 2 )
      goto LABEL_13;
    goto LABEL_6;
  }
  if ( v2
    || (v4 = RegQueryValueExW(hKey, L"fDenyTSConnections", 0, &Type, (LPBYTE)&Data, &cbData), (v3 = v4) != 0)
    && (v4 == 2 || v4 == 1018) )
  {
LABEL_6:
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Terminal Server",
           0,
           0x20019u,
           &phkResult);
    v3 = v5;
    if ( !phkResult || v5 )
    {
      _DbgPrintMessage(4, "Unable to open REG_CONTROL_TSERVER key");
    }
    else
    {
      cbData = 4;
      v3 = RegQueryValueExW(phkResult, L"fDenyTSConnections", 0, &Type, (LPBYTE)&Data, &cbData);
      if ( v3 || Data )
      {
        v13 = 0;
        cbData = 4;
        v3 = RegQueryValueExW(phkResult, L"StartRCM", 0, &Type, (LPBYTE)&v13, &cbData);
        if ( !v3 )
          Data = v13 == 0;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
LABEL_13:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( !v3 )
    return Data;
  return v1;
}

```

## disassembly

```asm
0x180028f54  mov     qword ptr [rsp-18h+cbData], rcx
0x180028f59  push    rbp
0x180028f5a  push    rbx
0x180028f5b  push    rdi
0x180028f5c  mov     rbp, rsp
0x180028f5f  sub     rsp, 40h
0x180028f63  lea     rax, [rbp+hKey]
0x180028f67  mov     [rbp+Type], 0
0x180028f6e  mov     edi, 1
0x180028f73  mov     [rsp+40h+phkResult], rax; phkResult
0x180028f78  mov     r9d, 20019h; samDesired
0x180028f7e  mov     [rbp+Data], edi
0x180028f81  xor     r8d, r8d; ulOptions
0x180028f84  mov     [rbp+cbData], 4
0x180028f8b  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180028f92  mov     [rbp+hKey], 0
0x180028f9a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028fa1  mov     [rbp+var_10], 0
0x180028fa9  call    cs:__imp_RegOpenKeyExW
0x180028fb0  nop     dword ptr [rax+rax+00h]
0x180028fb5  mov     rcx, [rbp+hKey]; hKey
0x180028fb9  mov     ebx, eax
0x180028fbb  test    rcx, rcx
0x180028fbe  jz      loc_180029106
0x180028fc4  test    eax, eax
0x180028fc6  jnz     short loc_18002900E
0x180028fc8  lea     rax, [rbp+cbData]
0x180028fcc  xor     r8d, r8d; lpReserved
0x180028fcf  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180028fd4  lea     r9, [rbp+Type]; lpType
0x180028fd8  lea     rax, [rbp+Data]
0x180028fdc  lea     rdx, aFdenytsconnect; "fDenyTSConnections"
0x180028fe3  mov     [rsp+40h+phkResult], rax; lpData
0x180028fe8  call    cs:__imp_RegQueryValueExW
0x180028fef  nop     dword ptr [rax+rax+00h]
0x180028ff4  mov     ebx, eax
0x180028ff6  test    eax, eax
0x180028ff8  jz      loc_1800290D2
0x180028ffe  cmp     eax, 2
0x180029001  jz      short loc_18002900E
0x180029003  cmp     eax, 3FAh
0x180029008  jnz     loc_1800290D2
0x18002900e  lea     rax, [rbp+var_10]
0x180029012  mov     r9d, 20019h; samDesired
0x180029018  xor     r8d, r8d; ulOptions
0x18002901b  mov     [rsp+40h+phkResult], rax; phkResult
0x180029020  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180029027  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002902e  call    cs:__imp_RegOpenKeyExW
0x180029035  nop     dword ptr [rax+rax+00h]
0x18002903a  mov     rcx, [rbp+var_10]; hKey
0x18002903e  mov     ebx, eax
0x180029040  test    rcx, rcx
0x180029043  jz      loc_1800290F3
0x180029049  test    eax, eax
0x18002904b  jnz     loc_1800290F3
0x180029051  lea     rax, [rbp+cbData]
0x180029055  mov     [rbp+cbData], 4
0x18002905c  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180029061  lea     r9, [rbp+Type]; lpType
0x180029065  lea     rax, [rbp+Data]
0x180029069  xor     r8d, r8d; lpReserved
0x18002906c  lea     rdx, aFdenytsconnect; "fDenyTSConnections"
0x180029073  mov     [rsp+40h+phkResult], rax; lpData
0x180029078  call    cs:__imp_RegQueryValueExW
0x18002907f  nop     dword ptr [rax+rax+00h]
0x180029084  mov     ebx, eax
0x180029086  test    eax, eax
0x180029088  jz      loc_180029110
0x18002908e  mov     rcx, [rbp+var_10]; hKey
0x180029092  lea     rax, [rbp+cbData]
0x180029096  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002909b  lea     r9, [rbp+Type]; lpType
0x18002909f  lea     rax, [rbp+arg_18]
0x1800290a3  mov     [rbp+arg_18], 0
0x1800290aa  xor     r8d, r8d; lpReserved
0x1800290ad  mov     [rsp+40h+phkResult], rax; lpData
0x1800290b2  lea     rdx, aStartrcm; "StartRCM"
0x1800290b9  mov     [rbp+cbData], 4
0x1800290c0  call    cs:__imp_RegQueryValueExW
0x1800290c7  nop     dword ptr [rax+rax+00h]
0x1800290cc  mov     ebx, eax
0x1800290ce  test    eax, eax
0x1800290d0  jz      short loc_18002911B
0x1800290d2  mov     rcx, [rbp+hKey]; hKey
0x1800290d6  test    rcx, rcx
0x1800290d9  jnz     short loc_180029128
0x1800290db  mov     rcx, [rbp+var_10]; hKey
0x1800290df  test    rcx, rcx
0x1800290e2  jnz     short loc_180029136
0x1800290e4  test    ebx, ebx
0x1800290e6  jz      short loc_180029144
0x1800290e8  mov     eax, edi
0x1800290ea  add     rsp, 40h
0x1800290ee  pop     rdi
0x1800290ef  pop     rbx
0x1800290f0  pop     rbp
0x1800290f1  retn
0x1800290f3  lea     rdx, aUnableToOpenRe; "Unable to open REG_CONTROL_TSERVER key"
0x1800290fa  mov     ecx, 4; int
0x1800290ff  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029104  jmp     short loc_1800290D2
0x180029106  cmp     eax, 2
0x180029109  jnz     short loc_1800290DB
0x18002910b  jmp     loc_18002900E
0x180029110  cmp     [rbp+Data], 0
0x180029114  jz      short loc_1800290D2
0x180029116  jmp     loc_18002908E
0x18002911b  xor     eax, eax
0x18002911d  cmp     [rbp+arg_18], eax
0x180029120  setz    al
0x180029123  mov     [rbp+Data], eax
0x180029126  jmp     short loc_1800290D2
0x180029128  call    cs:__imp_RegCloseKey
0x18002912f  nop     dword ptr [rax+rax+00h]
0x180029134  jmp     short loc_1800290DB
0x180029136  call    cs:__imp_RegCloseKey
0x18002913d  nop     dword ptr [rax+rax+00h]
0x180029142  jmp     short loc_1800290E4
0x180029144  xor     edi, edi
0x180029146  cmp     [rbp+Data], edi
0x180029149  setnz   dil
0x18002914d  jmp     short loc_1800290E8
```
