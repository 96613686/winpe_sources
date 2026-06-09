# TeredoResetConfigByService

- ea: `0x18000486c`
- end: `0x180004af6`
- name: `TeredoResetConfigByService`
- size: `650`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180004660`
- `0x1800331b0`
- `0x180069810`

## callees

- `0x18000486c`
- `0x18000d7b0`
- `0x1800190e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000491d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004984`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004a54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000491d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004984`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004a54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004add`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004add`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048a3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049df`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004aaf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049df`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004aaf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800049b6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180004a86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800049b6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180004a86`

## string_xrefs

- `0x180004893`: `System\CurrentControlSet\Services\iphlpsvc\Teredo`
- `0x1800048b8`: `System\CurrentControlSet\Services\iphlpsvc\Teredo`
- `0x180004916`: `TeredoConfigBySvc`
- `0x180004a45`: `TeredoConfigBySvc`
- `0x180004a7a`: `TeredoConfigBySvc`
- `0x1800048d3`: `Failed to open Teredo key 0x%x`
- `0x1800048bf`: `Unable to open key %s. Error %u`
- `0x180004ac2`: `Failed to reset ConfigBySvc 0x%x`

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
0x18000486c  push    rbp
0x18000486e  push    rbx
0x18000486f  push    rsi
0x180004870  push    r15
0x180004872  mov     rbp, rsp
0x180004875  sub     rsp, 48h
0x180004879  lea     rax, [rbp+hKey]
0x18000487d  mov     [rbp+hKey], 0FFFFFFFFFFFFFFFFh
0x180004885  mov     r9d, 2001Fh; samDesired
0x18000488b  mov     [rsp+48h+phkResult], rax; phkResult
0x180004890  xor     r8d, r8d; ulOptions
0x180004893  lea     rdx, aSystemCurrentc_17; "System\\CurrentControlSet\\Services\\ip"...
0x18000489a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800048a1  xor     esi, esi
0x1800048a3  call    cs:__imp_RegOpenKeyExW
0x1800048aa  nop     dword ptr [rax+rax+00h]
0x1800048af  mov     ebx, eax
0x1800048b1  test    eax, eax
0x1800048b3  jz      short loc_1800048DF
0x1800048b5  mov     r9d, eax
0x1800048b8  lea     r8, aSystemCurrentc_17; "System\\CurrentControlSet\\Services\\ip"...
0x1800048bf  lea     rdx, aUnableToOpenKe; "Unable to open key %s. Error %u"
0x1800048c6  mov     ecx, 100000h
0x1800048cb  call    EventWrite0
0x1800048d0  mov     r8d, ebx
0x1800048d3  lea     rdx, aFailedToOpenTe; "Failed to open Teredo key 0x%x"
0x1800048da  jmp     loc_180004AC9
0x1800048df  mov     rcx, [rbp+hKey]; hKey
0x1800048e3  mov     [rbp+Type], esi
0x1800048e6  mov     [rbp+Data], esi
0x1800048e9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800048ed  jz      loc_180004AD3
0x1800048f3  lea     rax, [rbp+cbData]
0x1800048f7  mov     r15d, 4
0x1800048fd  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180004902  lea     r9, [rbp+Type]; lpType
0x180004906  lea     rax, [rbp+Data]
0x18000490a  mov     [rbp+cbData], r15d
0x18000490e  xor     r8d, r8d; lpReserved
0x180004911  mov     [rsp+48h+phkResult], rax; lpData
0x180004916  lea     rdx, aTeredoconfigby; "TeredoConfigBySvc"
0x18000491d  call    cs:__imp_RegQueryValueExW
0x180004924  nop     dword ptr [rax+rax+00h]
0x180004929  test    eax, eax
0x18000492b  jnz     loc_180004AD3
0x180004931  cmp     [rbp+Type], r15d
0x180004935  jnz     loc_180004AD3
0x18000493b  mov     eax, [rbp+Data]
0x18000493e  test    eax, eax
0x180004940  jz      loc_180004AD3
0x180004946  mov     rbx, [rbp+hKey]
0x18000494a  mov     [rbp+cbData], esi
0x18000494d  mov     [rbp+Type], esi
0x180004950  mov     [rbp+Data], esi
0x180004953  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180004957  jz      loc_180004A05
0x18000495d  lea     rax, [rbp+arg_18]
0x180004961  mov     [rbp+arg_18], r15d
0x180004965  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000496a  lea     r9, [rbp+Type]; lpType
0x18000496e  lea     rax, [rbp+Data]
0x180004972  xor     r8d, r8d; lpReserved
0x180004975  lea     rdx, aType; "Type"
0x18000497c  mov     [rsp+48h+phkResult], rax; lpData
0x180004981  mov     rcx, rbx; hKey
0x180004984  call    cs:__imp_RegQueryValueExW
0x18000498b  nop     dword ptr [rax+rax+00h]
0x180004990  test    eax, eax
0x180004992  jz      short loc_180004998
0x180004994  xor     eax, eax
0x180004996  jmp     short loc_1800049A1
0x180004998  cmp     [rbp+Type], r15d
0x18000499c  jnz     short loc_180004994
0x18000499e  mov     eax, [rbp+Data]
0x1800049a1  mov     ecx, [rbp+cbData]
0x1800049a4  cmp     ecx, eax
0x1800049a6  jz      short loc_180004A05
0x1800049a8  test    ecx, ecx
0x1800049aa  lea     rdx, aType; "Type"
0x1800049b1  mov     rcx, rbx; hKey
0x1800049b4  jnz     short loc_1800049CB
0x1800049b6  call    cs:__imp_RegDeleteValueW
0x1800049bd  nop     dword ptr [rax+rax+00h]
0x1800049c2  cmp     eax, 2
0x1800049c5  jnz     short loc_1800049EB
0x1800049c7  xor     eax, eax
0x1800049c9  jmp     short loc_1800049EB
0x1800049cb  lea     rax, [rbp+cbData]
0x1800049cf  mov     dword ptr [rsp+48h+lpcbData], r15d; cbData
0x1800049d4  mov     r9d, r15d; dwType
0x1800049d7  mov     [rsp+48h+phkResult], rax; lpData
0x1800049dc  xor     r8d, r8d; Reserved
0x1800049df  call    cs:__imp_RegSetValueExW
0x1800049e6  nop     dword ptr [rax+rax+00h]
0x1800049eb  test    eax, eax
0x1800049ed  jz      short loc_180004A05
0x1800049ef  mov     r8d, eax
0x1800049f2  lea     rdx, aFailedToResetT; "Failed to reset Teredo type 0x%x"
0x1800049f9  mov     ecx, 100000h
0x1800049fe  call    EventWriteError0
0x180004a03  jmp     short loc_180004A0A
0x180004a05  mov     esi, 1
0x180004a0a  mov     rbx, [rbp+hKey]
0x180004a0e  mov     [rbp+cbData], 0
0x180004a15  mov     [rbp+Type], 0
0x180004a1c  mov     [rbp+Data], 0
0x180004a23  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180004a27  jz      loc_180004AD3
0x180004a2d  lea     rax, [rbp+arg_18]
0x180004a31  mov     [rbp+arg_18], r15d
0x180004a35  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180004a3a  lea     r9, [rbp+Type]; lpType
0x180004a3e  lea     rax, [rbp+Data]
0x180004a42  xor     r8d, r8d; lpReserved
0x180004a45  lea     rdx, aTeredoconfigby; "TeredoConfigBySvc"
0x180004a4c  mov     [rsp+48h+phkResult], rax; lpData
0x180004a51  mov     rcx, rbx; hKey
0x180004a54  call    cs:__imp_RegQueryValueExW
0x180004a5b  nop     dword ptr [rax+rax+00h]
0x180004a60  test    eax, eax
0x180004a62  jz      short loc_180004A68
0x180004a64  xor     eax, eax
0x180004a66  jmp     short loc_180004A71
0x180004a68  cmp     [rbp+Type], r15d
0x180004a6c  jnz     short loc_180004A64
0x180004a6e  mov     eax, [rbp+Data]
0x180004a71  mov     ecx, [rbp+cbData]
0x180004a74  cmp     ecx, eax
0x180004a76  jz      short loc_180004AD3
0x180004a78  test    ecx, ecx
0x180004a7a  lea     rdx, aTeredoconfigby; "TeredoConfigBySvc"
0x180004a81  mov     rcx, rbx; hKey
0x180004a84  jnz     short loc_180004A9B
0x180004a86  call    cs:__imp_RegDeleteValueW
0x180004a8d  nop     dword ptr [rax+rax+00h]
0x180004a92  cmp     eax, 2
0x180004a95  jnz     short loc_180004ABB
0x180004a97  xor     eax, eax
0x180004a99  jmp     short loc_180004ABB
0x180004a9b  lea     rax, [rbp+cbData]
0x180004a9f  mov     dword ptr [rsp+48h+lpcbData], r15d; cbData
0x180004aa4  mov     r9d, r15d; dwType
0x180004aa7  mov     [rsp+48h+phkResult], rax; lpData
0x180004aac  xor     r8d, r8d; Reserved
0x180004aaf  call    cs:__imp_RegSetValueExW
0x180004ab6  nop     dword ptr [rax+rax+00h]
0x180004abb  test    eax, eax
0x180004abd  jz      short loc_180004AD3
0x180004abf  mov     r8d, eax
0x180004ac2  lea     rdx, aFailedToResetC; "Failed to reset ConfigBySvc 0x%x"
0x180004ac9  mov     ecx, 100000h
0x180004ace  call    EventWriteError0
0x180004ad3  mov     rcx, [rbp+hKey]; hKey
0x180004ad7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004adb  jz      short loc_180004AE9
0x180004add  call    cs:__imp_RegCloseKey
0x180004ae4  nop     dword ptr [rax+rax+00h]
0x180004ae9  mov     eax, esi
0x180004aeb  add     rsp, 48h
0x180004aef  pop     r15
0x180004af1  pop     rsi
0x180004af2  pop     rbx
0x180004af3  pop     rbp
0x180004af4  retn
```
