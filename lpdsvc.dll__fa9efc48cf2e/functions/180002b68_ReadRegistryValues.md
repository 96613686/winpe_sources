# ReadRegistryValues

- ea: `0x180002b68`
- end: `0x180002df5`
- name: `ReadRegistryValues`
- size: `653`
- prototype: `unsigned int()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000276c`

## callees

- `0x180002b68`
- `0x180002e7c`
- `0x180002ea4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180002de8`
- `ADVAPI32!RegCloseKey` at `0x180002de8`
- `ADVAPI32!RegQueryValueExA` at `0x180002c86`
- `ADVAPI32!RegQueryValueExA` at `0x180002cc5`
- `ADVAPI32!RegQueryValueExA` at `0x180002d04`
- `ADVAPI32!RegQueryValueExA` at `0x180002d45`
- `ADVAPI32!RegQueryValueExA` at `0x180002d86`
- `ADVAPI32!RegQueryValueExA` at `0x180002dcc`
- `ADVAPI32!RegQueryValueExA` at `0x180002c86`
- `ADVAPI32!RegQueryValueExA` at `0x180002cc5`
- `ADVAPI32!RegQueryValueExA` at `0x180002d04`
- `ADVAPI32!RegQueryValueExA` at `0x180002d45`
- `ADVAPI32!RegQueryValueExA` at `0x180002d86`
- `ADVAPI32!RegQueryValueExA` at `0x180002dcc`
- `ADVAPI32!RegOpenKeyExA` at `0x180002c19`
- `ADVAPI32!RegOpenKeyExA` at `0x180002c19`

## string_xrefs

- `0x180002be3`: `System\CurrentControlSet\Services\LPDSVC\PARAMETERS`

## pseudocode

```c
unsigned int ReadRegistryValues()
{
  unsigned int result; // eax
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_e2a11bdbf6a53dd330d768a48b9244ec_Traceguids);
  dwMaxUsersGLB = 50;
  MaxQueueLength = 100;
  fJobRemovalEnabledGLB = 1;
  fAllowPrintResumeGLB = 1;
  fAlwaysRawGLB = 0;
  dwRecvTimeout = 60;
  result = RegOpenKeyExA(
             HKEY_LOCAL_MACHINE,
             "System\\CurrentControlSet\\Services\\LPDSVC\\PARAMETERS",
             0,
             0x20019u,
             &hKey);
  if ( result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      return WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_e2a11bdbf6a53dd330d768a48b9244ec_Traceguids, result);
  }
  else
  {
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "MaxConcurrentUsers", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      dwMaxUsersGLB = Data;
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "MaxQueueLength", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      MaxQueueLength = Data;
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "AllowJobRemoval", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && !Data )
      fJobRemovalEnabledGLB = 0;
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "AllowPrinterResume", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && !Data )
      fAllowPrintResumeGLB = 0;
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "SimulatePassThrough", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data == 1 )
      fAlwaysRawGLB = 1;
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "RecvTimeout", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      dwRecvTimeout = Data;
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180002b68  push    rbp
0x180002b6a  push    rdi
0x180002b6b  mov     rbp, rsp
0x180002b6e  sub     rsp, 38h
0x180002b72  mov     [rbp+hKey], 0
0x180002b7a  mov     [rbp+Type], 0
0x180002b81  mov     [rbp+Data], 0
0x180002b88  mov     [rbp+cbData], 0
0x180002b8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b96  lea     rdi, WPP_GLOBAL_Control
0x180002b9d  cmp     rcx, rdi
0x180002ba0  jz      short loc_180002BBD
0x180002ba2  test    byte ptr [rcx+1Ch], 1
0x180002ba6  jz      short loc_180002BBD
0x180002ba8  mov     rcx, [rcx+10h]
0x180002bac  lea     r8, WPP_e2a11bdbf6a53dd330d768a48b9244ec_Traceguids
0x180002bb3  mov     edx, 16h
0x180002bb8  call    WPP_SF_
0x180002bbd  lea     rax, [rbp+hKey]
0x180002bc1  mov     cs:dwMaxUsersGLB, 32h ; '2'
0x180002bcb  mov     r9d, 20019h; samDesired
0x180002bd1  mov     [rsp+38h+phkResult], rax; phkResult
0x180002bd6  xor     r8d, r8d; ulOptions
0x180002bd9  mov     cs:MaxQueueLength, 64h ; 'd'
0x180002be3  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\LP"...
0x180002bea  mov     cs:fJobRemovalEnabledGLB, 1
0x180002bf4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002bfb  mov     cs:fAllowPrintResumeGLB, 1
0x180002c05  mov     cs:fAlwaysRawGLB, 0
0x180002c0f  mov     cs:dwRecvTimeout, 3Ch ; '<'
0x180002c19  call    cs:__imp_RegOpenKeyExA
0x180002c1f  test    eax, eax
0x180002c21  jz      short loc_180002C5A
0x180002c23  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c2a  cmp     rcx, rdi
0x180002c2d  jz      loc_180002DEE
0x180002c33  test    byte ptr [rcx+1Ch], 1
0x180002c37  jz      loc_180002DEE
0x180002c3d  mov     rcx, [rcx+10h]
0x180002c41  lea     r8, WPP_e2a11bdbf6a53dd330d768a48b9244ec_Traceguids
0x180002c48  mov     edx, 17h
0x180002c4d  mov     r9d, eax
0x180002c50  call    WPP_SF_d
0x180002c55  jmp     loc_180002DEE
0x180002c5a  mov     rcx, [rbp+hKey]; hKey
0x180002c5e  lea     rax, [rbp+cbData]
0x180002c62  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180002c67  lea     r9, [rbp+Type]; lpType
0x180002c6b  lea     rax, [rbp+Data]
0x180002c6f  mov     edi, 4
0x180002c74  xor     r8d, r8d; lpReserved
0x180002c77  mov     [rsp+38h+phkResult], rax; lpData
0x180002c7c  lea     rdx, ValueName; "MaxConcurrentUsers"
0x180002c83  mov     [rbp+cbData], edi
0x180002c86  call    cs:__imp_RegQueryValueExA
0x180002c8c  test    eax, eax
0x180002c8e  jnz     short loc_180002C9E
0x180002c90  cmp     [rbp+Type], edi
0x180002c93  jnz     short loc_180002C9E
0x180002c95  mov     eax, [rbp+Data]
0x180002c98  mov     cs:dwMaxUsersGLB, eax
0x180002c9e  mov     rcx, [rbp+hKey]; hKey
0x180002ca2  lea     rax, [rbp+cbData]
0x180002ca6  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180002cab  lea     r9, [rbp+Type]; lpType
0x180002caf  lea     rax, [rbp+Data]
0x180002cb3  mov     [rbp+cbData], edi
0x180002cb6  xor     r8d, r8d; lpReserved
0x180002cb9  mov     [rsp+38h+phkResult], rax; lpData
0x180002cbe  lea     rdx, aMaxqueuelength; "MaxQueueLength"
0x180002cc5  call    cs:__imp_RegQueryValueExA
0x180002ccb  test    eax, eax
0x180002ccd  jnz     short loc_180002CDD
0x180002ccf  cmp     [rbp+Type], edi
0x180002cd2  jnz     short loc_180002CDD
0x180002cd4  mov     eax, [rbp+Data]
0x180002cd7  mov     cs:MaxQueueLength, eax
0x180002cdd  mov     rcx, [rbp+hKey]; hKey
0x180002ce1  lea     rax, [rbp+cbData]
0x180002ce5  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180002cea  lea     r9, [rbp+Type]; lpType
0x180002cee  lea     rax, [rbp+Data]
0x180002cf2  mov     [rbp+cbData], edi
0x180002cf5  xor     r8d, r8d; lpReserved
0x180002cf8  mov     [rsp+38h+phkResult], rax; lpData
0x180002cfd  lea     rdx, aAllowjobremova; "AllowJobRemoval"
0x180002d04  call    cs:__imp_RegQueryValueExA
0x180002d0a  test    eax, eax
0x180002d0c  jnz     short loc_180002D1E
0x180002d0e  cmp     [rbp+Type], edi
0x180002d11  jnz     short loc_180002D1E
0x180002d13  cmp     [rbp+Data], eax
0x180002d16  jnz     short loc_180002D1E
0x180002d18  mov     cs:fJobRemovalEnabledGLB, eax
0x180002d1e  mov     rcx, [rbp+hKey]; hKey
0x180002d22  lea     rax, [rbp+cbData]
0x180002d26  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180002d2b  lea     r9, [rbp+Type]; lpType
0x180002d2f  lea     rax, [rbp+Data]
0x180002d33  mov     [rbp+cbData], edi
0x180002d36  xor     r8d, r8d; lpReserved
0x180002d39  mov     [rsp+38h+phkResult], rax; lpData
0x180002d3e  lea     rdx, aAllowprinterre; "AllowPrinterResume"
0x180002d45  call    cs:__imp_RegQueryValueExA
0x180002d4b  test    eax, eax
0x180002d4d  jnz     short loc_180002D5F
0x180002d4f  cmp     [rbp+Type], edi
0x180002d52  jnz     short loc_180002D5F
0x180002d54  cmp     [rbp+Data], eax
0x180002d57  jnz     short loc_180002D5F
0x180002d59  mov     cs:fAllowPrintResumeGLB, eax
0x180002d5f  mov     rcx, [rbp+hKey]; hKey
0x180002d63  lea     rax, [rbp+cbData]
0x180002d67  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180002d6c  lea     r9, [rbp+Type]; lpType
0x180002d70  lea     rax, [rbp+Data]
0x180002d74  mov     [rbp+cbData], edi
0x180002d77  xor     r8d, r8d; lpReserved
0x180002d7a  mov     [rsp+38h+phkResult], rax; lpData
0x180002d7f  lea     rdx, aSimulatepassth; "SimulatePassThrough"
0x180002d86  call    cs:__imp_RegQueryValueExA
0x180002d8c  test    eax, eax
0x180002d8e  jnz     short loc_180002DA5
0x180002d90  cmp     [rbp+Type], edi
0x180002d93  jnz     short loc_180002DA5
0x180002d95  cmp     [rbp+Data], 1
0x180002d99  jnz     short loc_180002DA5
0x180002d9b  mov     cs:fAlwaysRawGLB, 1
0x180002da5  mov     rcx, [rbp+hKey]; hKey
0x180002da9  lea     rax, [rbp+cbData]
0x180002dad  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180002db2  lea     r9, [rbp+Type]; lpType
0x180002db6  lea     rax, [rbp+Data]
0x180002dba  mov     [rbp+cbData], edi
0x180002dbd  xor     r8d, r8d; lpReserved
0x180002dc0  mov     [rsp+38h+phkResult], rax; lpData
0x180002dc5  lea     rdx, aRecvtimeout; "RecvTimeout"
0x180002dcc  call    cs:__imp_RegQueryValueExA
0x180002dd2  test    eax, eax
0x180002dd4  jnz     short loc_180002DE4
0x180002dd6  cmp     [rbp+Type], edi
0x180002dd9  jnz     short loc_180002DE4
0x180002ddb  mov     eax, [rbp+Data]
0x180002dde  mov     cs:dwRecvTimeout, eax
0x180002de4  mov     rcx, [rbp+hKey]; hKey
0x180002de8  call    cs:__imp_RegCloseKey
0x180002dee  add     rsp, 38h
0x180002df2  pop     rdi
0x180002df3  pop     rbp
0x180002df4  retn
```
