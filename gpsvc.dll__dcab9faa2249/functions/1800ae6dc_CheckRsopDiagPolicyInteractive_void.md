# CheckRsopDiagPolicyInteractive(void)

- ea: `0x1800ae6dc`
- end: `0x1800ae917`
- name: `?CheckRsopDiagPolicyInteractive@@YAHXZ`
- size: `571`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180071890`

## callees

- `0x180072a08`
- `0x1800ae6dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae7cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae82d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae891`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae8f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae902`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae7cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae82d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae891`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae8f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae902`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800ae73d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800ae73d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae78c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae7ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae852`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae8b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae78c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae7ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae852`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae8b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ae7c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ae823`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ae887`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ae8e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ae7c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ae823`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ae887`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ae8e9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ae767`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ae767`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800ae70b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800ae70b`

## string_xrefs

- `0x1800ae71d`: `CheckRsopDiagPolicyInteractive::CoImpersonateClient failed with 0x%x`
- `0x1800ae747`: `CheckRsopDiagPolicyInteractive:: couldn't access registry of interactive user.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 CheckRsopDiagPolicyInteractive(void)
{
  HRESULT v0; // eax
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  int Data; // [rsp+68h] [rbp+20h] BYREF
  DWORD Type; // [rsp+70h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+30h] BYREF

  phkResult = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  Data = 0;
  v0 = CoImpersonateClient();
  if ( v0 >= 0 )
  {
    if ( RegOpenCurrentUser(0x20019u, &phkResult) )
    {
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgRsop,
        2u,
        L"CheckRsopDiagPolicyInteractive:: couldn't access registry of interactive user.");
      phkResult = 0;
    }
  }
  else
  {
    CDebugWrapper::Msg(
      (CDebugWrapper *)dbgRsop,
      2u,
      L"CheckRsopDiagPolicyInteractive::CoImpersonateClient failed with 0x%x",
      (unsigned int)v0);
  }
  CoRevertToSelf();
  if ( phkResult
    && !RegOpenKeyExW(phkResult, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"DenyRsopToInteractiveUser", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
  }
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"DenyRsopToInteractiveUser", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
  }
  if ( phkResult && !RegOpenKeyExW(phkResult, L"Software\\Policies\\Microsoft\\Windows\\System", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"DenyRsopToInteractiveUser", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\System", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"DenyRsopToInteractiveUser", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return Data == 0;
}

```

## disassembly

```asm
0x1800ae6dc  push    rbp
0x1800ae6de  push    rdi
0x1800ae6df  mov     rbp, rsp
0x1800ae6e2  sub     rsp, 48h
0x1800ae6e6  mov     [rbp+phkResult], 0
0x1800ae6ee  mov     [rbp+hKey], 0
0x1800ae6f6  mov     [rbp+cbData], 0
0x1800ae6fd  mov     [rbp+Type], 0
0x1800ae704  mov     [rbp+Data], 0
0x1800ae70b  call    cs:__imp_CoImpersonateClient
0x1800ae711  mov     edi, 20019h
0x1800ae716  test    eax, eax
0x1800ae718  jns     short loc_1800AE737
0x1800ae71a  mov     r9d, eax
0x1800ae71d  lea     r8, aCheckrsopdiagp_0; "CheckRsopDiagPolicyInteractive::CoImper"...
0x1800ae724  mov     edx, 2; unsigned int
0x1800ae729  lea     rcx, ?dbgRsop@@3VCDebugWrapper@@A; this
0x1800ae730  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800ae735  jmp     short loc_1800AE767
0x1800ae737  lea     rdx, [rbp+phkResult]; phkResult
0x1800ae73b  mov     ecx, edi; samDesired
0x1800ae73d  call    cs:__imp_RegOpenCurrentUser
0x1800ae743  test    eax, eax
0x1800ae745  jz      short loc_1800AE767
0x1800ae747  lea     r8, aCheckrsopdiagp; "CheckRsopDiagPolicyInteractive:: couldn"...
0x1800ae74e  mov     edx, 2; unsigned int
0x1800ae753  lea     rcx, ?dbgRsop@@3VCDebugWrapper@@A; this
0x1800ae75a  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800ae75f  mov     [rbp+phkResult], 0
0x1800ae767  call    cs:__imp_CoRevertToSelf
0x1800ae76d  mov     rcx, [rbp+phkResult]; hKey
0x1800ae771  test    rcx, rcx
0x1800ae774  jz      short loc_1800AE7D1
0x1800ae776  lea     rax, [rbp+hKey]
0x1800ae77a  mov     r9d, edi; samDesired
0x1800ae77d  xor     r8d, r8d; ulOptions
0x1800ae780  mov     [rsp+48h+var_28], rax; phkResult
0x1800ae785  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800ae78c  call    cs:__imp_RegOpenKeyExW
0x1800ae792  test    eax, eax
0x1800ae794  jnz     short loc_1800AE7D1
0x1800ae796  mov     rcx, [rbp+hKey]; hKey
0x1800ae79a  lea     rax, [rbp+cbData]
0x1800ae79e  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800ae7a3  lea     r9, [rbp+Type]; lpType
0x1800ae7a7  lea     rax, [rbp+Data]
0x1800ae7ab  mov     [rbp+cbData], 4
0x1800ae7b2  xor     r8d, r8d; lpReserved
0x1800ae7b5  mov     [rsp+48h+var_28], rax; lpData
0x1800ae7ba  lea     rdx, aDenyrsoptointe; "DenyRsopToInteractiveUser"
0x1800ae7c1  call    cs:__imp_RegQueryValueExW
0x1800ae7c7  mov     rcx, [rbp+hKey]; hKey
0x1800ae7cb  call    cs:__imp_RegCloseKey
0x1800ae7d1  lea     rax, [rbp+hKey]
0x1800ae7d5  mov     r9d, edi; samDesired
0x1800ae7d8  xor     r8d, r8d; ulOptions
0x1800ae7db  mov     [rsp+48h+var_28], rax; phkResult
0x1800ae7e0  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800ae7e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ae7ee  call    cs:__imp_RegOpenKeyExW
0x1800ae7f4  test    eax, eax
0x1800ae7f6  jnz     short loc_1800AE833
0x1800ae7f8  mov     rcx, [rbp+hKey]; hKey
0x1800ae7fc  lea     rax, [rbp+cbData]
0x1800ae800  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800ae805  lea     r9, [rbp+Type]; lpType
0x1800ae809  lea     rax, [rbp+Data]
0x1800ae80d  mov     [rbp+cbData], 4
0x1800ae814  xor     r8d, r8d; lpReserved
0x1800ae817  mov     [rsp+48h+var_28], rax; lpData
0x1800ae81c  lea     rdx, aDenyrsoptointe; "DenyRsopToInteractiveUser"
0x1800ae823  call    cs:__imp_RegQueryValueExW
0x1800ae829  mov     rcx, [rbp+hKey]; hKey
0x1800ae82d  call    cs:__imp_RegCloseKey
0x1800ae833  mov     rcx, [rbp+phkResult]; hKey
0x1800ae837  test    rcx, rcx
0x1800ae83a  jz      short loc_1800AE897
0x1800ae83c  lea     rax, [rbp+hKey]
0x1800ae840  mov     r9d, edi; samDesired
0x1800ae843  xor     r8d, r8d; ulOptions
0x1800ae846  mov     [rsp+48h+var_28], rax; phkResult
0x1800ae84b  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1800ae852  call    cs:__imp_RegOpenKeyExW
0x1800ae858  test    eax, eax
0x1800ae85a  jnz     short loc_1800AE897
0x1800ae85c  mov     rcx, [rbp+hKey]; hKey
0x1800ae860  lea     rax, [rbp+cbData]
0x1800ae864  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800ae869  lea     r9, [rbp+Type]; lpType
0x1800ae86d  lea     rax, [rbp+Data]
0x1800ae871  mov     [rbp+cbData], 4
0x1800ae878  xor     r8d, r8d; lpReserved
0x1800ae87b  mov     [rsp+48h+var_28], rax; lpData
0x1800ae880  lea     rdx, aDenyrsoptointe; "DenyRsopToInteractiveUser"
0x1800ae887  call    cs:__imp_RegQueryValueExW
0x1800ae88d  mov     rcx, [rbp+hKey]; hKey
0x1800ae891  call    cs:__imp_RegCloseKey
0x1800ae897  lea     rax, [rbp+hKey]
0x1800ae89b  mov     r9d, edi; samDesired
0x1800ae89e  xor     r8d, r8d; ulOptions
0x1800ae8a1  mov     [rsp+48h+var_28], rax; phkResult
0x1800ae8a6  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1800ae8ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ae8b4  call    cs:__imp_RegOpenKeyExW
0x1800ae8ba  test    eax, eax
0x1800ae8bc  jnz     short loc_1800AE8F9
0x1800ae8be  mov     rcx, [rbp+hKey]; hKey
0x1800ae8c2  lea     rax, [rbp+cbData]
0x1800ae8c6  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800ae8cb  lea     r9, [rbp+Type]; lpType
0x1800ae8cf  lea     rax, [rbp+Data]
0x1800ae8d3  mov     [rbp+cbData], 4
0x1800ae8da  xor     r8d, r8d; lpReserved
0x1800ae8dd  mov     [rsp+48h+var_28], rax; lpData
0x1800ae8e2  lea     rdx, aDenyrsoptointe; "DenyRsopToInteractiveUser"
0x1800ae8e9  call    cs:__imp_RegQueryValueExW
0x1800ae8ef  mov     rcx, [rbp+hKey]; hKey
0x1800ae8f3  call    cs:__imp_RegCloseKey
0x1800ae8f9  mov     rcx, [rbp+phkResult]; hKey
0x1800ae8fd  test    rcx, rcx
0x1800ae900  jz      short loc_1800AE908
0x1800ae902  call    cs:__imp_RegCloseKey
0x1800ae908  xor     eax, eax
0x1800ae90a  cmp     [rbp+Data], eax
0x1800ae90d  setz    al
0x1800ae910  add     rsp, 48h
0x1800ae914  pop     rdi
0x1800ae915  pop     rbp
0x1800ae916  retn
```
