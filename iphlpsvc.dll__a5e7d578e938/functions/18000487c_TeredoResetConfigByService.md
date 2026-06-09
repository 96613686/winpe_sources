# TeredoResetConfigByService

- ea: `0x18000487c`
- end: `0x180004b06`
- name: `TeredoResetConfigByService`
- size: `650`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180004670`
- `0x1800331c0`
- `0x180069830`

## callees

- `0x18000487c`
- `0x18000d7c0`
- `0x1800190f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000492d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004994`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004a64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000492d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004994`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004a64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004aed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004aed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004abf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004abf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800049c6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180004a96`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800049c6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180004a96`

## string_xrefs

- `0x1800048a3`: `System\CurrentControlSet\Services\iphlpsvc\Teredo`
- `0x1800048c8`: `System\CurrentControlSet\Services\iphlpsvc\Teredo`
- `0x180004926`: `TeredoConfigBySvc`
- `0x180004a55`: `TeredoConfigBySvc`
- `0x180004a8a`: `TeredoConfigBySvc`
- `0x1800048e3`: `Failed to open Teredo key 0x%x`
- `0x1800048cf`: `Unable to open key %s. Error %u`
- `0x180004ad2`: `Failed to reset ConfigBySvc 0x%x`

## pseudocode

```c
__int64 TeredoResetConfigByService()
{
  unsigned int v0; // esi
  unsigned int v1; // eax
  unsigned int v2; // ebx
  HKEY v3; // rbx
  int v4; // eax
  unsigned int v5; // eax
  HKEY v6; // rbx
  int v7; // eax
  unsigned int v8; // eax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD Type; // [rsp+70h] [rbp+28h] BYREF
  int Data; // [rsp+78h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+38h] BYREF
  DWORD lpcbData; // [rsp+88h] [rbp+40h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v0 = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\iphlpsvc\\Teredo", 0, 0x2001Fu, &hKey);
  v2 = v1;
  if ( v1 )
  {
    EventWrite0(
      0x100000,
      L"Unable to open key %s. Error %u",
      L"System\\CurrentControlSet\\Services\\iphlpsvc\\Teredo",
      v1);
    EventWriteError0(0x100000, L"Failed to open Teredo key 0x%x", v2);
  }
  else
  {
    Type = 0;
    Data = 0;
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"TeredoConfigBySvc", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data )
      {
        v3 = hKey;
        cbData = 0;
        Type = 0;
        Data = 0;
        if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          goto LABEL_19;
        lpcbData = 4;
        if ( RegQueryValueExW(hKey, L"Type", 0, &Type, (LPBYTE)&Data, &lpcbData) || Type != 4 )
          v4 = 0;
        else
          v4 = Data;
        if ( cbData == v4 )
          goto LABEL_19;
        if ( cbData )
        {
          v5 = RegSetValueExW(v3, L"Type", 0, 4u, (const BYTE *)&cbData, 4u);
        }
        else
        {
          v5 = RegDeleteValueW(v3, L"Type");
          if ( v5 == 2 )
            v5 = 0;
        }
        if ( !v5 )
LABEL_19:
          v0 = 1;
        else
          EventWriteError0(0x100000, L"Failed to reset Teredo type 0x%x", v5);
        v6 = hKey;
        cbData = 0;
        Type = 0;
        Data = 0;
        if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        {
          lpcbData = 4;
          if ( RegQueryValueExW(hKey, L"TeredoConfigBySvc", 0, &Type, (LPBYTE)&Data, &lpcbData) || Type != 4 )
            v7 = 0;
          else
            v7 = Data;
          if ( cbData != v7 )
          {
            if ( cbData )
            {
              v8 = RegSetValueExW(v6, L"TeredoConfigBySvc", 0, 4u, (const BYTE *)&cbData, 4u);
            }
            else
            {
              v8 = RegDeleteValueW(v6, L"TeredoConfigBySvc");
              if ( v8 == 2 )
                v8 = 0;
            }
            if ( v8 )
              EventWriteError0(0x100000, L"Failed to reset ConfigBySvc 0x%x", v8);
          }
        }
      }
    }
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18000487c  push    rbp
0x18000487e  push    rbx
0x18000487f  push    rsi
0x180004880  push    r15
0x180004882  mov     rbp, rsp
0x180004885  sub     rsp, 48h
0x180004889  lea     rax, [rbp+hKey]
0x18000488d  mov     [rbp+hKey], 0FFFFFFFFFFFFFFFFh
0x180004895  mov     r9d, 2001Fh; samDesired
0x18000489b  mov     [rsp+48h+phkResult], rax; phkResult
0x1800048a0  xor     r8d, r8d; ulOptions
0x1800048a3  lea     rdx, aSystemCurrentc_17; "System\\CurrentControlSet\\Services\\ip"...
0x1800048aa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800048b1  xor     esi, esi
0x1800048b3  call    cs:__imp_RegOpenKeyExW
0x1800048ba  nop     dword ptr [rax+rax+00h]
0x1800048bf  mov     ebx, eax
0x1800048c1  test    eax, eax
0x1800048c3  jz      short loc_1800048EF
0x1800048c5  mov     r9d, eax
0x1800048c8  lea     r8, aSystemCurrentc_17; "System\\CurrentControlSet\\Services\\ip"...
0x1800048cf  lea     rdx, aUnableToOpenKe; "Unable to open key %s. Error %u"
0x1800048d6  mov     ecx, 100000h
0x1800048db  call    EventWrite0
0x1800048e0  mov     r8d, ebx
0x1800048e3  lea     rdx, aFailedToOpenTe; "Failed to open Teredo key 0x%x"
0x1800048ea  jmp     loc_180004AD9
0x1800048ef  mov     rcx, [rbp+hKey]; hKey
0x1800048f3  mov     [rbp+Type], esi
0x1800048f6  mov     [rbp+Data], esi
0x1800048f9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800048fd  jz      loc_180004AE3
0x180004903  lea     rax, [rbp+cbData]
0x180004907  mov     r15d, 4
0x18000490d  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180004912  lea     r9, [rbp+Type]; lpType
0x180004916  lea     rax, [rbp+Data]
0x18000491a  mov     [rbp+cbData], r15d
0x18000491e  xor     r8d, r8d; lpReserved
0x180004921  mov     [rsp+48h+phkResult], rax; lpData
0x180004926  lea     rdx, aTeredoconfigby; "TeredoConfigBySvc"
0x18000492d  call    cs:__imp_RegQueryValueExW
0x180004934  nop     dword ptr [rax+rax+00h]
0x180004939  test    eax, eax
0x18000493b  jnz     loc_180004AE3
0x180004941  cmp     [rbp+Type], r15d
0x180004945  jnz     loc_180004AE3
0x18000494b  mov     eax, [rbp+Data]
0x18000494e  test    eax, eax
0x180004950  jz      loc_180004AE3
0x180004956  mov     rbx, [rbp+hKey]
0x18000495a  mov     [rbp+cbData], esi
0x18000495d  mov     [rbp+Type], esi
0x180004960  mov     [rbp+Data], esi
0x180004963  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180004967  jz      loc_180004A15
0x18000496d  lea     rax, [rbp+arg_18]
0x180004971  mov     [rbp+arg_18], r15d
0x180004975  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000497a  lea     r9, [rbp+Type]; lpType
0x18000497e  lea     rax, [rbp+Data]
0x180004982  xor     r8d, r8d; lpReserved
0x180004985  lea     rdx, aType; "Type"
0x18000498c  mov     [rsp+48h+phkResult], rax; lpData
0x180004991  mov     rcx, rbx; hKey
0x180004994  call    cs:__imp_RegQueryValueExW
0x18000499b  nop     dword ptr [rax+rax+00h]
0x1800049a0  test    eax, eax
0x1800049a2  jz      short loc_1800049A8
0x1800049a4  xor     eax, eax
0x1800049a6  jmp     short loc_1800049B1
0x1800049a8  cmp     [rbp+Type], r15d
0x1800049ac  jnz     short loc_1800049A4
0x1800049ae  mov     eax, [rbp+Data]
0x1800049b1  mov     ecx, [rbp+cbData]
0x1800049b4  cmp     ecx, eax
0x1800049b6  jz      short loc_180004A15
0x1800049b8  test    ecx, ecx
0x1800049ba  lea     rdx, aType; "Type"
0x1800049c1  mov     rcx, rbx; hKey
0x1800049c4  jnz     short loc_1800049DB
0x1800049c6  call    cs:__imp_RegDeleteValueW
0x1800049cd  nop     dword ptr [rax+rax+00h]
0x1800049d2  cmp     eax, 2
0x1800049d5  jnz     short loc_1800049FB
0x1800049d7  xor     eax, eax
0x1800049d9  jmp     short loc_1800049FB
0x1800049db  lea     rax, [rbp+cbData]
0x1800049df  mov     dword ptr [rsp+48h+lpcbData], r15d; cbData
0x1800049e4  mov     r9d, r15d; dwType
0x1800049e7  mov     [rsp+48h+phkResult], rax; lpData
0x1800049ec  xor     r8d, r8d; Reserved
0x1800049ef  call    cs:__imp_RegSetValueExW
0x1800049f6  nop     dword ptr [rax+rax+00h]
0x1800049fb  test    eax, eax
0x1800049fd  jz      short loc_180004A15
0x1800049ff  mov     r8d, eax
0x180004a02  lea     rdx, aFailedToResetT; "Failed to reset Teredo type 0x%x"
0x180004a09  mov     ecx, 100000h
0x180004a0e  call    EventWriteError0
0x180004a13  jmp     short loc_180004A1A
0x180004a15  mov     esi, 1
0x180004a1a  mov     rbx, [rbp+hKey]
0x180004a1e  mov     [rbp+cbData], 0
0x180004a25  mov     [rbp+Type], 0
0x180004a2c  mov     [rbp+Data], 0
0x180004a33  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180004a37  jz      loc_180004AE3
0x180004a3d  lea     rax, [rbp+arg_18]
0x180004a41  mov     [rbp+arg_18], r15d
0x180004a45  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180004a4a  lea     r9, [rbp+Type]; lpType
0x180004a4e  lea     rax, [rbp+Data]
0x180004a52  xor     r8d, r8d; lpReserved
0x180004a55  lea     rdx, aTeredoconfigby; "TeredoConfigBySvc"
0x180004a5c  mov     [rsp+48h+phkResult], rax; lpData
0x180004a61  mov     rcx, rbx; hKey
0x180004a64  call    cs:__imp_RegQueryValueExW
0x180004a6b  nop     dword ptr [rax+rax+00h]
0x180004a70  test    eax, eax
0x180004a72  jz      short loc_180004A78
0x180004a74  xor     eax, eax
0x180004a76  jmp     short loc_180004A81
0x180004a78  cmp     [rbp+Type], r15d
0x180004a7c  jnz     short loc_180004A74
0x180004a7e  mov     eax, [rbp+Data]
0x180004a81  mov     ecx, [rbp+cbData]
0x180004a84  cmp     ecx, eax
0x180004a86  jz      short loc_180004AE3
0x180004a88  test    ecx, ecx
0x180004a8a  lea     rdx, aTeredoconfigby; "TeredoConfigBySvc"
0x180004a91  mov     rcx, rbx; hKey
0x180004a94  jnz     short loc_180004AAB
0x180004a96  call    cs:__imp_RegDeleteValueW
0x180004a9d  nop     dword ptr [rax+rax+00h]
0x180004aa2  cmp     eax, 2
0x180004aa5  jnz     short loc_180004ACB
0x180004aa7  xor     eax, eax
0x180004aa9  jmp     short loc_180004ACB
0x180004aab  lea     rax, [rbp+cbData]
0x180004aaf  mov     dword ptr [rsp+48h+lpcbData], r15d; cbData
0x180004ab4  mov     r9d, r15d; dwType
0x180004ab7  mov     [rsp+48h+phkResult], rax; lpData
0x180004abc  xor     r8d, r8d; Reserved
0x180004abf  call    cs:__imp_RegSetValueExW
0x180004ac6  nop     dword ptr [rax+rax+00h]
0x180004acb  test    eax, eax
0x180004acd  jz      short loc_180004AE3
0x180004acf  mov     r8d, eax
0x180004ad2  lea     rdx, aFailedToResetC; "Failed to reset ConfigBySvc 0x%x"
0x180004ad9  mov     ecx, 100000h
0x180004ade  call    EventWriteError0
0x180004ae3  mov     rcx, [rbp+hKey]; hKey
0x180004ae7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004aeb  jz      short loc_180004AF9
0x180004aed  call    cs:__imp_RegCloseKey
0x180004af4  nop     dword ptr [rax+rax+00h]
0x180004af9  mov     eax, esi
0x180004afb  add     rsp, 48h
0x180004aff  pop     r15
0x180004b01  pop     rsi
0x180004b02  pop     rbx
0x180004b03  pop     rbp
0x180004b04  retn
```
