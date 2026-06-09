# SetDevicePasswordLessData(PasswordLessDataType,ulong)

- ea: `0x1800dacac`
- end: `0x1800dadf9`
- name: `?SetDevicePasswordLessData@@YAJW4PasswordLessDataType@@K@Z`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800db520`

## callees

- `0x1800a5e64`
- `0x1800dacac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dace3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dace3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dacd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dacd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dacdb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dad6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dadcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dade5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dacdb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dad6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dadcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dade5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800dad9d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800dad9d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800dad39`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800dad39`

## string_xrefs

- `0x1800dad4b`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800dadaf`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 SetDevicePasswordLessData()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  unsigned int v3; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-48h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-48h]
  int Data[6]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  Data[0] = 2;
  hKey = 0;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PasswordLess\\Device",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  if ( v0 )
  {
    v1 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x170,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)v0,
           dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    return v1;
  }
  v3 = RegSetValueExW(hKey, L"DevicePasswordLessBuildVersion", 0, 4u, (const BYTE *)Data, 4u);
  if ( v3 )
  {
    v1 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x178,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)v3,
           dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    return v1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800dacac  mov     rax, rsp
0x1800dacaf  mov     [rax+8], rbx
0x1800dacb3  push    rdi
0x1800dacb4  sub     rsp, 60h
0x1800dacb8  mov     dword ptr [rax-18h], 2
0x1800dacbf  mov     qword ptr [rax+18h], 0
0x1800dacc7  mov     rdi, [rax+18h]
0x1800daccb  test    rdi, rdi
0x1800dacce  jz      short loc_1800DACEA
0x1800dacd0  call    cs:__imp_GetLastError
0x1800dacd6  mov     ebx, eax
0x1800dacd8  mov     rcx, rdi; hKey
0x1800dacdb  call    cs:__imp_RegCloseKey
0x1800dace1  mov     ecx, ebx; dwErrCode
0x1800dace3  call    cs:__imp_SetLastError
0x1800dace9  nop
0x1800dacea  mov     [rsp+68h+hKey], 0
0x1800dacf6  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x1800dacff  lea     rax, [rsp+68h+hKey]
0x1800dad07  mov     [rsp+68h+phkResult], rax; phkResult
0x1800dad0c  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800dad15  mov     [rsp+68h+samDesired], 20006h; samDesired
0x1800dad1d  mov     [rsp+68h+dwOptions], 0; unsigned int
0x1800dad25  xor     r9d, r9d; lpClass
0x1800dad28  xor     r8d, r8d; Reserved
0x1800dad2b  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800dad32  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800dad39  call    cs:__imp_RegCreateKeyExW
0x1800dad3f  test    eax, eax
0x1800dad41  jz      short loc_1800DAD76
0x1800dad43  mov     rcx, [rsp+68h]; this
0x1800dad48  mov     r9d, eax; char *
0x1800dad4b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800dad52  mov     edx, 170h; void *
0x1800dad57  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800dad5c  mov     ebx, eax
0x1800dad5e  mov     rcx, [rsp+68h+hKey]; hKey
0x1800dad66  test    rcx, rcx
0x1800dad69  jz      short loc_1800DAD72
0x1800dad6b  call    cs:__imp_RegCloseKey
0x1800dad71  nop
0x1800dad72  mov     eax, ebx
0x1800dad74  jmp     short loc_1800DADEE
0x1800dad76  mov     r9d, 4; dwType
0x1800dad7c  mov     [rsp+68h+samDesired], r9d; cbData
0x1800dad81  lea     rax, [rsp+68h+Data]
0x1800dad86  mov     qword ptr [rsp+68h+dwOptions], rax; unsigned int
0x1800dad8b  xor     r8d, r8d; Reserved
0x1800dad8e  lea     rdx, aDevicepassword_0; "DevicePasswordLessBuildVersion"
0x1800dad95  mov     rcx, [rsp+68h+hKey]; hKey
0x1800dad9d  call    cs:__imp_RegSetValueExW
0x1800dada3  test    eax, eax
0x1800dada5  jz      short loc_1800DADD8
0x1800dada7  mov     rcx, [rsp+68h]; this
0x1800dadac  mov     r9d, eax; char *
0x1800dadaf  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800dadb6  mov     edx, 178h; void *
0x1800dadbb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800dadc0  mov     ebx, eax
0x1800dadc2  mov     rcx, [rsp+68h+hKey]; hKey
0x1800dadca  test    rcx, rcx
0x1800dadcd  jz      short loc_1800DADD6
0x1800dadcf  call    cs:__imp_RegCloseKey
0x1800dadd5  nop
0x1800dadd6  jmp     short loc_1800DAD72
0x1800dadd8  mov     rcx, [rsp+68h+hKey]; hKey
0x1800dade0  test    rcx, rcx
0x1800dade3  jz      short loc_1800DADEC
0x1800dade5  call    cs:__imp_RegCloseKey
0x1800dadeb  nop
0x1800dadec  xor     eax, eax
0x1800dadee  mov     rbx, [rsp+68h+arg_0]
0x1800dadf3  add     rsp, 60h
0x1800dadf7  pop     rdi
0x1800dadf8  retn
```
