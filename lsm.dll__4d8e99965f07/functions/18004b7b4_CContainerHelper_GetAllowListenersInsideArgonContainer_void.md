# CContainerHelper::GetAllowListenersInsideArgonContainer(void)

- ea: `0x18004b7b4`
- end: `0x18004b95e`
- name: `?GetAllowListenersInsideArgonContainer@CContainerHelper@@CAKXZ`
- size: `426`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002bec4`
- `0x180031a40`

## callees

- `0x18004b7b4`
- `0x18004e850`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004b91e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004b91e`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18004b81f`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18004b81f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b7fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b8ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b7fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b8ad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b85e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b8f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b85e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b8f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b939`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b939`

## string_xrefs

- `0x18004b857`: `AllowListenersInsideArgonContainer`

## pseudocode

```c
__int64 CContainerHelper::GetAllowListenersInsideArgonContainer(void)
{
  int v0; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-50h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-4Ch] BYREF
  DWORD Type; // [rsp+38h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-40h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-38h] BYREF
  BYTE v7[16]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v8; // [rsp+60h] [rbp-20h]
  __int16 v9; // [rsp+70h] [rbp-10h]

  hKey = 0;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey) )
  {
    cbData = 0;
    Type = 0;
    phkResult = 0;
    if ( (unsigned int)RtlGetCurrentServiceSessionId() )
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"AllowListenersInsideArgonContainer", 0, &Type, Data, &cbData) || Type != 4 )
      {
        v0 = 0;
        *(_DWORD *)Data = 0;
      }
      else
      {
        v0 = *(_DWORD *)Data;
      }
      if ( v0 )
      {
        *(_DWORD *)Data = 0;
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                0,
                0x20019u,
                &phkResult) )
        {
          cbData = 34;
          v9 = 0;
          *(_OWORD *)v7 = 0;
          v8 = 0;
          if ( !RegQueryValueExW(phkResult, L"EditionID", 0, &Type, v7, &cbData)
            && Type == 1
            && !(unsigned int)_o__wcsnicmp(v7, L"ContainerOSPlus", 15) )
          {
            *(_DWORD *)Data = 1;
          }
        }
      }
    }
    RegCloseKey(hKey);
  }
  return *(unsigned int *)Data;
}

```

## disassembly

```asm
0x18004b7b4  push    rbp
0x18004b7b6  mov     rbp, rsp
0x18004b7b9  sub     rsp, 80h
0x18004b7c0  mov     rax, cs:__security_cookie
0x18004b7c7  xor     rax, rsp
0x18004b7ca  mov     [rbp+var_8], rax
0x18004b7ce  lea     rax, [rbp+hKey]
0x18004b7d2  mov     [rbp+hKey], 0
0x18004b7da  mov     r9d, 20019h; samDesired
0x18004b7e0  mov     [rsp+80h+phkResult], rax; phkResult
0x18004b7e5  xor     r8d, r8d; ulOptions
0x18004b7e8  mov     dword ptr [rbp+Data], 0
0x18004b7ef  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18004b7f6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004b7fd  call    cs:__imp_RegOpenKeyExW
0x18004b804  nop     dword ptr [rax+rax+00h]
0x18004b809  test    eax, eax
0x18004b80b  jnz     loc_18004B945
0x18004b811  mov     [rbp+cbData], eax
0x18004b814  mov     [rbp+Type], eax
0x18004b817  mov     [rbp+var_38], 0
0x18004b81f  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18004b826  nop     dword ptr [rax+rax+00h]
0x18004b82b  test    eax, eax
0x18004b82d  jz      loc_18004B935
0x18004b833  mov     rcx, [rbp+hKey]; hKey
0x18004b837  lea     rax, [rbp+cbData]
0x18004b83b  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18004b840  lea     r9, [rbp+Type]; lpType
0x18004b844  lea     rax, [rbp+Data]
0x18004b848  mov     [rbp+cbData], 4
0x18004b84f  xor     r8d, r8d; lpReserved
0x18004b852  mov     [rsp+80h+phkResult], rax; lpData
0x18004b857  lea     rdx, aAllowlisteners; "AllowListenersInsideArgonContainer"
0x18004b85e  call    cs:__imp_RegQueryValueExW
0x18004b865  nop     dword ptr [rax+rax+00h]
0x18004b86a  test    eax, eax
0x18004b86c  jnz     short loc_18004B879
0x18004b86e  cmp     [rbp+Type], 4
0x18004b872  jnz     short loc_18004B879
0x18004b874  mov     eax, dword ptr [rbp+Data]
0x18004b877  jmp     short loc_18004B87E
0x18004b879  xor     eax, eax
0x18004b87b  mov     dword ptr [rbp+Data], eax
0x18004b87e  test    eax, eax
0x18004b880  jz      loc_18004B935
0x18004b886  lea     rax, [rbp+var_38]
0x18004b88a  mov     dword ptr [rbp+Data], 0
0x18004b891  mov     r9d, 20019h; samDesired
0x18004b897  mov     [rsp+80h+phkResult], rax; phkResult
0x18004b89c  xor     r8d, r8d; ulOptions
0x18004b89f  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004b8a6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004b8ad  call    cs:__imp_RegOpenKeyExW
0x18004b8b4  nop     dword ptr [rax+rax+00h]
0x18004b8b9  test    eax, eax
0x18004b8bb  jnz     short loc_18004B935
0x18004b8bd  mov     rcx, [rbp+var_38]; hKey
0x18004b8c1  lea     r9, [rbp+Type]; lpType
0x18004b8c5  xor     eax, eax
0x18004b8c7  mov     [rbp+cbData], 22h ; '"'
0x18004b8ce  mov     [rbp+var_10], ax
0x18004b8d2  lea     rdx, aEditionid; "EditionID"
0x18004b8d9  xorps   xmm0, xmm0
0x18004b8dc  lea     rax, [rbp+cbData]
0x18004b8e0  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18004b8e5  xor     r8d, r8d; lpReserved
0x18004b8e8  lea     rax, [rbp+var_30]
0x18004b8ec  mov     [rsp+80h+phkResult], rax; lpData
0x18004b8f1  movups  xmmword ptr [rbp+var_30], xmm0
0x18004b8f5  movups  [rbp+var_20], xmm0
0x18004b8f9  call    cs:__imp_RegQueryValueExW
0x18004b900  nop     dword ptr [rax+rax+00h]
0x18004b905  test    eax, eax
0x18004b907  jnz     short loc_18004B935
0x18004b909  cmp     [rbp+Type], 1
0x18004b90d  jnz     short loc_18004B935
0x18004b90f  lea     r8d, [rax+0Fh]
0x18004b913  lea     rdx, aContainerosplu; "ContainerOSPlus"
0x18004b91a  lea     rcx, [rbp+var_30]
0x18004b91e  call    cs:__imp__o__wcsnicmp
0x18004b925  nop     dword ptr [rax+rax+00h]
0x18004b92a  test    eax, eax
0x18004b92c  jnz     short loc_18004B935
0x18004b92e  mov     dword ptr [rbp+Data], 1
0x18004b935  mov     rcx, [rbp+hKey]; hKey
0x18004b939  call    cs:__imp_RegCloseKey
0x18004b940  nop     dword ptr [rax+rax+00h]
0x18004b945  mov     eax, dword ptr [rbp+Data]
0x18004b948  mov     rcx, [rbp+var_8]
0x18004b94c  xor     rcx, rsp; StackCookie
0x18004b94f  call    __security_check_cookie
0x18004b954  add     rsp, 80h
0x18004b95b  pop     rbp
0x18004b95c  retn
```
