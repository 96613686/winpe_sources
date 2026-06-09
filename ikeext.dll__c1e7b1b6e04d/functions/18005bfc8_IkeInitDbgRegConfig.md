# IkeInitDbgRegConfig

- ea: `0x18005bfc8`
- end: `0x18005c0b7`
- name: `IkeInitDbgRegConfig`
- size: `239`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18005f7e0`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x180050850`
- `0x18005bfc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c08f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c08f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005c06a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005c06a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c019`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c019`

## string_xrefs

- `0x18005c00b`: `SYSTEM\CurrentControlSet\Services\IKEEXT\Parameters`
- `0x18005c026`: `RegOpenKeyExW`
- `0x18005c095`: `IkeInitDbgRegConfig`

## pseudocode

```c
__int64 IkeInitDbgRegConfig()
{
  unsigned int v0; // eax
  __int64 v1; // rcx
  __int64 v2; // rbx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-20h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-1Ch] BYREF

  hKey = 0;
  cbData = 4;
  *(_DWORD *)Data = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\IKEEXT\\Parameters", 0, 1u, &hKey);
  if ( v0 )
  {
    v2 = WfpReportSysErrorAsWinError(v1, "RegOpenKeyExW", v0, 1);
  }
  else
  {
    cbData = 4;
    v2 = 0;
    if ( !RegQueryValueExW(hKey, L"TestFlags", 0, 0, Data, &cbData) )
      LODWORD(gIkeExtGlobals[85].DebugInfo) = *(_DWORD *)Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return IkeReturnError(v2, "IkeInitDbgRegConfig");
}

```

## disassembly

```asm
0x18005bfc8  push    rbx
0x18005bfca  sub     rsp, 50h
0x18005bfce  mov     rax, cs:__security_cookie
0x18005bfd5  xor     rax, rsp
0x18005bfd8  mov     [rsp+58h+var_18], rax
0x18005bfdd  lea     rax, [rsp+58h+hKey]
0x18005bfe2  mov     [rsp+58h+hKey], 0
0x18005bfeb  mov     ebx, 1
0x18005bff0  mov     [rsp+58h+cbData], 4
0x18005bff8  mov     r9d, ebx; samDesired
0x18005bffb  mov     dword ptr [rsp+58h+Data], 0
0x18005c003  xor     r8d, r8d; ulOptions
0x18005c006  mov     [rsp+58h+phkResult], rax; phkResult
0x18005c00b  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\IK"...
0x18005c012  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005c019  call    cs:__imp_RegOpenKeyExW
0x18005c01f  test    eax, eax
0x18005c021  jz      short loc_18005C03A
0x18005c023  mov     r9d, ebx
0x18005c026  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18005c02d  mov     r8d, eax
0x18005c030  call    WfpReportSysErrorAsWinError
0x18005c035  mov     rbx, rax
0x18005c038  jmp     short loc_18005C085
0x18005c03a  mov     rcx, [rsp+58h+hKey]; hKey
0x18005c03f  lea     rax, [rsp+58h+cbData]
0x18005c044  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18005c049  lea     rdx, aTestflags; "TestFlags"
0x18005c050  lea     rax, [rsp+58h+Data]
0x18005c055  mov     [rsp+58h+cbData], 4
0x18005c05d  xor     r9d, r9d; lpType
0x18005c060  mov     [rsp+58h+phkResult], rax; lpData
0x18005c065  xor     r8d, r8d; lpReserved
0x18005c068  xor     ebx, ebx
0x18005c06a  call    cs:__imp_RegQueryValueExW
0x18005c070  test    eax, eax
0x18005c072  jnz     short loc_18005C085
0x18005c074  mov     rax, cs:gIkeExtGlobals
0x18005c07b  mov     ecx, dword ptr [rsp+58h+Data]
0x18005c07f  mov     [rax+0D48h], ecx
0x18005c085  mov     rcx, [rsp+58h+hKey]; hKey
0x18005c08a  test    rcx, rcx
0x18005c08d  jz      short loc_18005C095
0x18005c08f  call    cs:__imp_RegCloseKey
0x18005c095  lea     rdx, aIkeinitdbgregc; "IkeInitDbgRegConfig"
0x18005c09c  mov     rcx, rbx
0x18005c09f  call    IkeReturnError
0x18005c0a4  mov     rcx, [rsp+58h+var_18]
0x18005c0a9  xor     rcx, rsp; StackCookie
0x18005c0ac  call    __security_check_cookie
0x18005c0b1  add     rsp, 50h
0x18005c0b5  pop     rbx
0x18005c0b6  retn
```
