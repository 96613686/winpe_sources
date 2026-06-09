# ReadPayloadFromRegistry(ushort const *,ushort *,ulong)

- ea: `0x14000aa08`
- end: `0x14000ab2c`
- name: `?ReadPayloadFromRegistry@@YAHPEBGPEAGK@Z`
- size: `292`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPBYTE lpData)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140005b34`

## callees

- `0x14000aa08`
- `0x1400187e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000aade`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000aade`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000aa7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000aaa7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000aa7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000aaa7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000aa49`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000aa49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aaf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ab06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aaf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ab06`

## pseudocode

```c
__int64 __fastcall ReadPayloadFromRegistry(LPCWSTR lpSubKey, LPBYTE lpData)
{
  unsigned int v5; // ebx
  DWORD cbData; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-20h] BYREF
  GUID pclsid; // [rsp+48h] [rbp-18h] BYREF

  hKey = 0;
  phkResult = 0;
  pclsid = 0;
  if ( CLSIDFromString(lpSubKey, &pclsid) < 0 )
    return 98369817;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Siuf\\Staging\\", 0, 0x20019u, &hKey) )
  {
    v5 = 98369814;
  }
  else if ( RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult) )
  {
    v5 = 98369815;
  }
  else
  {
    cbData = 10000;
    v5 = 6148113;
    if ( RegQueryValueExW(phkResult, 0, 0, 0, lpData, &cbData) )
      v5 = 98369816;
  }
  if ( hKey )
    CloseHandle(hKey);
  if ( phkResult )
    CloseHandle(phkResult);
  return v5;
}

```

## disassembly

```asm
0x14000aa08  mov     [rsp-8+arg_10], rbx
0x14000aa0d  mov     [rsp-8+arg_18], rdi
0x14000aa12  push    rbp
0x14000aa13  mov     rbp, rsp
0x14000aa16  sub     rsp, 60h
0x14000aa1a  mov     rax, cs:__security_cookie
0x14000aa21  xor     rax, rsp
0x14000aa24  mov     [rbp+var_8], rax
0x14000aa28  mov     rdi, rdx
0x14000aa2b  mov     [rbp+hKey], 0
0x14000aa33  xorps   xmm0, xmm0
0x14000aa36  mov     [rbp+var_20], 0
0x14000aa3e  lea     rdx, [rbp+pclsid]; pclsid
0x14000aa42  mov     rbx, rcx
0x14000aa45  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x14000aa49  call    cs:__imp_CLSIDFromString
0x14000aa4f  test    eax, eax
0x14000aa51  jns     short loc_14000AA5D
0x14000aa53  mov     eax, 5DD0119h
0x14000aa58  jmp     loc_14000AB0E
0x14000aa5d  lea     rax, [rbp+hKey]
0x14000aa61  mov     r9d, 20019h; samDesired
0x14000aa67  xor     r8d, r8d; ulOptions
0x14000aa6a  mov     [rsp+60h+phkResult], rax; phkResult
0x14000aa6f  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Siuf\\Staging\\"
0x14000aa76  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000aa7d  call    cs:__imp_RegOpenKeyExW
0x14000aa83  test    eax, eax
0x14000aa85  jz      short loc_14000AA8E
0x14000aa87  mov     ebx, 5DD0116h
0x14000aa8c  jmp     short loc_14000AAEE
0x14000aa8e  mov     rcx, [rbp+hKey]; hKey
0x14000aa92  lea     rax, [rbp+var_20]
0x14000aa96  mov     r9d, 20019h; samDesired
0x14000aa9c  mov     [rsp+60h+phkResult], rax; phkResult
0x14000aaa1  xor     r8d, r8d; ulOptions
0x14000aaa4  mov     rdx, rbx; lpSubKey
0x14000aaa7  call    cs:__imp_RegOpenKeyExW
0x14000aaad  test    eax, eax
0x14000aaaf  jz      short loc_14000AAB8
0x14000aab1  mov     ebx, 5DD0117h
0x14000aab6  jmp     short loc_14000AAEE
0x14000aab8  mov     rcx, [rbp+var_20]; hKey
0x14000aabc  lea     rax, [rbp+cbData]
0x14000aac0  mov     [rsp+60h+lpcbData], rax; lpcbData
0x14000aac5  xor     r9d, r9d; lpType
0x14000aac8  xor     r8d, r8d; lpReserved
0x14000aacb  mov     [rsp+60h+phkResult], rdi; lpData
0x14000aad0  xor     edx, edx; lpValueName
0x14000aad2  mov     [rbp+cbData], 2710h
0x14000aad9  mov     ebx, 5DD011h
0x14000aade  call    cs:__imp_RegQueryValueExW
0x14000aae4  test    eax, eax
0x14000aae6  mov     ecx, 5DD0118h
0x14000aaeb  cmovnz  ebx, ecx
0x14000aaee  mov     rcx, [rbp+hKey]; hObject
0x14000aaf2  test    rcx, rcx
0x14000aaf5  jz      short loc_14000AAFD
0x14000aaf7  call    cs:__imp_CloseHandle
0x14000aafd  mov     rcx, [rbp+var_20]; hObject
0x14000ab01  test    rcx, rcx
0x14000ab04  jz      short loc_14000AB0C
0x14000ab06  call    cs:__imp_CloseHandle
0x14000ab0c  mov     eax, ebx
0x14000ab0e  mov     rcx, [rbp+var_8]
0x14000ab12  xor     rcx, rsp; StackCookie
0x14000ab15  call    __security_check_cookie
0x14000ab1a  lea     r11, [rsp+60h+var_s0]
0x14000ab1f  mov     rbx, [r11+20h]
0x14000ab23  mov     rdi, [r11+28h]
0x14000ab27  mov     rsp, r11
0x14000ab2a  pop     rbp
0x14000ab2b  retn
```
