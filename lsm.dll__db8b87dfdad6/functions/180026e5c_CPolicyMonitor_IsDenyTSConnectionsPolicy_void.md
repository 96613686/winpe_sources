# CPolicyMonitor::IsDenyTSConnectionsPolicy(void)

- ea: `0x180026e5c`
- end: `0x180027028`
- name: `?IsDenyTSConnectionsPolicy@CPolicyMonitor@@AEAAHXZ`
- size: `460`
- prototype: `__int64 __fastcall(CPolicyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180051464`

## callees

- `0x1800074c0`
- `0x180026e5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026eb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026f2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026eb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026f2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026eea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026f6e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026fac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026eea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026f6e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026fac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002700d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027015`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002700d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027015`

## string_xrefs

- `0x180026e93`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x180026fd8`: `Unable to open REG_CONTROL_TSERVER key`

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
0x180026e5c  mov     qword ptr [rsp-18h+cbData], rcx
0x180026e61  push    rbp
0x180026e62  push    rbx
0x180026e63  push    rdi
0x180026e64  mov     rbp, rsp
0x180026e67  sub     rsp, 40h
0x180026e6b  lea     rax, [rbp+hKey]
0x180026e6f  mov     [rbp+Type], 0
0x180026e76  mov     edi, 1
0x180026e7b  mov     [rsp+40h+phkResult], rax; phkResult
0x180026e80  mov     r9d, 20019h; samDesired
0x180026e86  mov     [rbp+Data], edi
0x180026e89  xor     r8d, r8d; ulOptions
0x180026e8c  mov     [rbp+cbData], 4
0x180026e93  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180026e9a  mov     [rbp+hKey], 0
0x180026ea2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026ea9  mov     [rbp+var_10], 0
0x180026eb1  call    cs:__imp_RegOpenKeyExW
0x180026eb7  mov     rcx, [rbp+hKey]; hKey
0x180026ebb  mov     ebx, eax
0x180026ebd  test    rcx, rcx
0x180026ec0  jz      loc_180026FEB
0x180026ec6  test    eax, eax
0x180026ec8  jnz     short loc_180026F0A
0x180026eca  lea     rax, [rbp+cbData]
0x180026ece  xor     r8d, r8d; lpReserved
0x180026ed1  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180026ed6  lea     r9, [rbp+Type]; lpType
0x180026eda  lea     rax, [rbp+Data]
0x180026ede  lea     rdx, aFdenytsconnect; "fDenyTSConnections"
0x180026ee5  mov     [rsp+40h+phkResult], rax; lpData
0x180026eea  call    cs:__imp_RegQueryValueExW
0x180026ef0  mov     ebx, eax
0x180026ef2  test    eax, eax
0x180026ef4  jz      loc_180026FB8
0x180026efa  cmp     eax, 2
0x180026efd  jz      short loc_180026F0A
0x180026eff  cmp     eax, 3FAh
0x180026f04  jnz     loc_180026FB8
0x180026f0a  lea     rax, [rbp+var_10]
0x180026f0e  mov     r9d, 20019h; samDesired
0x180026f14  xor     r8d, r8d; ulOptions
0x180026f17  mov     [rsp+40h+phkResult], rax; phkResult
0x180026f1c  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180026f23  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026f2a  call    cs:__imp_RegOpenKeyExW
0x180026f30  mov     rcx, [rbp+var_10]; hKey
0x180026f34  mov     ebx, eax
0x180026f36  test    rcx, rcx
0x180026f39  jz      loc_180026FD8
0x180026f3f  test    eax, eax
0x180026f41  jnz     loc_180026FD8
0x180026f47  lea     rax, [rbp+cbData]
0x180026f4b  mov     [rbp+cbData], 4
0x180026f52  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180026f57  lea     r9, [rbp+Type]; lpType
0x180026f5b  lea     rax, [rbp+Data]
0x180026f5f  xor     r8d, r8d; lpReserved
0x180026f62  lea     rdx, aFdenytsconnect; "fDenyTSConnections"
0x180026f69  mov     [rsp+40h+phkResult], rax; lpData
0x180026f6e  call    cs:__imp_RegQueryValueExW
0x180026f74  mov     ebx, eax
0x180026f76  test    eax, eax
0x180026f78  jz      short loc_180026FF5
0x180026f7a  mov     rcx, [rbp+var_10]; hKey
0x180026f7e  lea     rax, [rbp+cbData]
0x180026f82  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180026f87  lea     r9, [rbp+Type]; lpType
0x180026f8b  lea     rax, [rbp+arg_18]
0x180026f8f  mov     [rbp+arg_18], 0
0x180026f96  xor     r8d, r8d; lpReserved
0x180026f99  mov     [rsp+40h+phkResult], rax; lpData
0x180026f9e  lea     rdx, aStartrcm; "StartRCM"
0x180026fa5  mov     [rbp+cbData], 4
0x180026fac  call    cs:__imp_RegQueryValueExW
0x180026fb2  mov     ebx, eax
0x180026fb4  test    eax, eax
0x180026fb6  jz      short loc_180027000
0x180026fb8  mov     rcx, [rbp+hKey]; hKey
0x180026fbc  test    rcx, rcx
0x180026fbf  jnz     short loc_18002700D
0x180026fc1  mov     rcx, [rbp+var_10]; hKey
0x180026fc5  test    rcx, rcx
0x180026fc8  jnz     short loc_180027015
0x180026fca  test    ebx, ebx
0x180026fcc  jz      short loc_18002701D
0x180026fce  mov     eax, edi
0x180026fd0  add     rsp, 40h
0x180026fd4  pop     rdi
0x180026fd5  pop     rbx
0x180026fd6  pop     rbp
0x180026fd7  retn
0x180026fd8  lea     rdx, aUnableToOpenRe; "Unable to open REG_CONTROL_TSERVER key"
0x180026fdf  mov     ecx, 4; int
0x180026fe4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180026fe9  jmp     short loc_180026FB8
0x180026feb  cmp     eax, 2
0x180026fee  jnz     short loc_180026FC1
0x180026ff0  jmp     loc_180026F0A
0x180026ff5  cmp     [rbp+Data], 0
0x180026ff9  jz      short loc_180026FB8
0x180026ffb  jmp     loc_180026F7A
0x180027000  xor     eax, eax
0x180027002  cmp     [rbp+arg_18], eax
0x180027005  setz    al
0x180027008  mov     [rbp+Data], eax
0x18002700b  jmp     short loc_180026FB8
0x18002700d  call    cs:__imp_RegCloseKey
0x180027013  jmp     short loc_180026FC1
0x180027015  call    cs:__imp_RegCloseKey
0x18002701b  jmp     short loc_180026FCA
0x18002701d  xor     edi, edi
0x18002701f  cmp     [rbp+Data], edi
0x180027022  setnz   dil
0x180027026  jmp     short loc_180026FCE
```
