# CContainerHelper::GetAllowListenersInsideArgonContainer(void)

- ea: `0x1800485b8`
- end: `0x180048737`
- name: `?GetAllowListenersInsideArgonContainer@CContainerHelper@@CAKXZ`
- size: `383`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029f14`
- `0x18002fa00`

## callees

- `0x1800485b8`
- `0x18004b460`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180048704`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180048704`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18004861d`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18004861d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180048601`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004869f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180048601`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004869f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048656`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800486e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048656`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800486e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048719`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048719`

## string_xrefs

- `0x18004864f`: `AllowListenersInsideArgonContainer`

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
0x1800485b8  push    rbp
0x1800485ba  mov     rbp, rsp
0x1800485bd  sub     rsp, 80h
0x1800485c4  mov     rax, cs:__security_cookie
0x1800485cb  xor     rax, rsp
0x1800485ce  mov     [rbp+var_8], rax
0x1800485d2  lea     rax, [rbp+hKey]
0x1800485d6  mov     [rbp+hKey], 0
0x1800485de  mov     r9d, 20019h; samDesired
0x1800485e4  mov     [rsp+80h+phkResult], rax; phkResult
0x1800485e9  xor     r8d, r8d; ulOptions
0x1800485ec  mov     dword ptr [rbp+Data], 0
0x1800485f3  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x1800485fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180048601  call    cs:__imp_RegOpenKeyExW
0x180048607  test    eax, eax
0x180048609  jnz     loc_18004871F
0x18004860f  mov     [rbp+cbData], eax
0x180048612  mov     [rbp+Type], eax
0x180048615  mov     [rbp+var_38], 0
0x18004861d  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180048623  test    eax, eax
0x180048625  jz      loc_180048715
0x18004862b  mov     rcx, [rbp+hKey]; hKey
0x18004862f  lea     rax, [rbp+cbData]
0x180048633  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180048638  lea     r9, [rbp+Type]; lpType
0x18004863c  lea     rax, [rbp+Data]
0x180048640  mov     [rbp+cbData], 4
0x180048647  xor     r8d, r8d; lpReserved
0x18004864a  mov     [rsp+80h+phkResult], rax; lpData
0x18004864f  lea     rdx, aAllowlisteners; "AllowListenersInsideArgonContainer"
0x180048656  call    cs:__imp_RegQueryValueExW
0x18004865c  test    eax, eax
0x18004865e  jnz     short loc_18004866B
0x180048660  cmp     [rbp+Type], 4
0x180048664  jnz     short loc_18004866B
0x180048666  mov     eax, dword ptr [rbp+Data]
0x180048669  jmp     short loc_180048670
0x18004866b  xor     eax, eax
0x18004866d  mov     dword ptr [rbp+Data], eax
0x180048670  test    eax, eax
0x180048672  jz      loc_180048715
0x180048678  lea     rax, [rbp+var_38]
0x18004867c  mov     dword ptr [rbp+Data], 0
0x180048683  mov     r9d, 20019h; samDesired
0x180048689  mov     [rsp+80h+phkResult], rax; phkResult
0x18004868e  xor     r8d, r8d; ulOptions
0x180048691  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180048698  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004869f  call    cs:__imp_RegOpenKeyExW
0x1800486a5  test    eax, eax
0x1800486a7  jnz     short loc_180048715
0x1800486a9  mov     rcx, [rbp+var_38]; hKey
0x1800486ad  lea     r9, [rbp+Type]; lpType
0x1800486b1  xor     eax, eax
0x1800486b3  mov     [rbp+cbData], 22h ; '"'
0x1800486ba  mov     [rbp+var_10], ax
0x1800486be  lea     rdx, aEditionid; "EditionID"
0x1800486c5  xorps   xmm0, xmm0
0x1800486c8  lea     rax, [rbp+cbData]
0x1800486cc  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800486d1  xor     r8d, r8d; lpReserved
0x1800486d4  lea     rax, [rbp+var_30]
0x1800486d8  mov     [rsp+80h+phkResult], rax; lpData
0x1800486dd  movups  xmmword ptr [rbp+var_30], xmm0
0x1800486e1  movups  [rbp+var_20], xmm0
0x1800486e5  call    cs:__imp_RegQueryValueExW
0x1800486eb  test    eax, eax
0x1800486ed  jnz     short loc_180048715
0x1800486ef  cmp     [rbp+Type], 1
0x1800486f3  jnz     short loc_180048715
0x1800486f5  lea     r8d, [rax+0Fh]
0x1800486f9  lea     rdx, aContainerosplu; "ContainerOSPlus"
0x180048700  lea     rcx, [rbp+var_30]
0x180048704  call    cs:__imp__o__wcsnicmp
0x18004870a  test    eax, eax
0x18004870c  jnz     short loc_180048715
0x18004870e  mov     dword ptr [rbp+Data], 1
0x180048715  mov     rcx, [rbp+hKey]; hKey
0x180048719  call    cs:__imp_RegCloseKey
0x18004871f  mov     eax, dword ptr [rbp+Data]
0x180048722  mov     rcx, [rbp+var_8]
0x180048726  xor     rcx, rsp; StackCookie
0x180048729  call    __security_check_cookie
0x18004872e  add     rsp, 80h
0x180048735  pop     rbp
0x180048736  retn
```
