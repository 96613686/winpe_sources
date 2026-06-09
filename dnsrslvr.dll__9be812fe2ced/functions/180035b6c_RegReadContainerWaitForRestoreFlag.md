# RegReadContainerWaitForRestoreFlag

- ea: `0x180035b6c`
- end: `0x180035c28`
- name: `RegReadContainerWaitForRestoreFlag`
- size: `188`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800495c0`

## callees

- `0x180035b6c`
- `0x180046ec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035c0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035c0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035bc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035bc0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035bf2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035bf2`

## pseudocode

```c
__int64 RegReadContainerWaitForRestoreFlag()
{
  unsigned int v0; // ebx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-1Ch] BYREF
  DWORD Type; // [rsp+40h] [rbp-18h] BYREF

  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 4;
  v0 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Containers", 0, 1u, &hKey)
    && !RegQueryValueExW(hKey, L"WaitForRestore", 0, &Type, Data, &cbData) )
  {
    LOBYTE(v0) = *(_DWORD *)Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180035b6c  push    rbx
0x180035b6e  sub     rsp, 50h
0x180035b72  mov     rax, cs:__security_cookie
0x180035b79  xor     rax, rsp
0x180035b7c  mov     [rsp+58h+var_10], rax
0x180035b81  mov     eax, 4
0x180035b86  mov     dword ptr [rsp+58h+Data], 0
0x180035b8e  mov     [rsp+58h+cbData], eax
0x180035b92  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180035b99  mov     [rsp+58h+Type], eax
0x180035b9d  xor     ebx, ebx
0x180035b9f  lea     rax, [rsp+58h+hKey]
0x180035ba4  mov     [rsp+58h+hKey], 0
0x180035bad  xor     r8d, r8d; ulOptions
0x180035bb0  mov     [rsp+58h+phkResult], rax; phkResult
0x180035bb5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035bbc  lea     r9d, [rbx+1]; samDesired
0x180035bc0  call    cs:__imp_RegOpenKeyExW
0x180035bc6  test    eax, eax
0x180035bc8  jnz     short loc_180035C03
0x180035bca  mov     rcx, [rsp+58h+hKey]; hKey
0x180035bcf  lea     rax, [rsp+58h+cbData]
0x180035bd4  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180035bd9  lea     r9, [rsp+58h+Type]; lpType
0x180035bde  lea     rax, [rsp+58h+Data]
0x180035be3  xor     r8d, r8d; lpReserved
0x180035be6  lea     rdx, aWaitforrestore; "WaitForRestore"
0x180035bed  mov     [rsp+58h+phkResult], rax; lpData
0x180035bf2  call    cs:__imp_RegQueryValueExW
0x180035bf8  test    eax, eax
0x180035bfa  jnz     short loc_180035C03
0x180035bfc  cmp     dword ptr [rsp+58h+Data], ebx
0x180035c00  setnz   bl
0x180035c03  mov     rcx, [rsp+58h+hKey]; hKey
0x180035c08  test    rcx, rcx
0x180035c0b  jz      short loc_180035C13
0x180035c0d  call    cs:__imp_RegCloseKey
0x180035c13  mov     eax, ebx
0x180035c15  mov     rcx, [rsp+58h+var_10]
0x180035c1a  xor     rcx, rsp; StackCookie
0x180035c1d  call    __security_check_cookie
0x180035c22  add     rsp, 50h
0x180035c26  pop     rbx
0x180035c27  retn
```
