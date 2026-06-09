# ReadPayloadFromRegistry(ushort const *,ushort *,ulong)

- ea: `0x14000ac6c`
- end: `0x14000adb5`
- name: `?ReadPayloadFromRegistry@@YAHPEBGPEAGK@Z`
- size: `329`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPBYTE lpData, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140005bd4`

## callees

- `0x14000ac6c`
- `0x140019610`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000ace7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000ad17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000ace7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000ad17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000ad54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000ad54`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000acad`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000acad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ad73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ad88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ad73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ad88`

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
0x14000ac6c  mov     [rsp-8+arg_10], rbx
0x14000ac71  mov     [rsp-8+arg_18], rdi
0x14000ac76  push    rbp
0x14000ac77  mov     rbp, rsp
0x14000ac7a  sub     rsp, 60h
0x14000ac7e  mov     rax, cs:__security_cookie
0x14000ac85  xor     rax, rsp
0x14000ac88  mov     [rbp+var_8], rax
0x14000ac8c  mov     rdi, rdx
0x14000ac8f  mov     [rbp+hKey], 0
0x14000ac97  xorps   xmm0, xmm0
0x14000ac9a  mov     [rbp+var_20], 0
0x14000aca2  lea     rdx, [rbp+pclsid]; pclsid
0x14000aca6  mov     rbx, rcx
0x14000aca9  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x14000acad  call    cs:__imp_CLSIDFromString
0x14000acb4  nop     dword ptr [rax+rax+00h]
0x14000acb9  test    eax, eax
0x14000acbb  jns     short loc_14000ACC7
0x14000acbd  mov     eax, 5DD0119h
0x14000acc2  jmp     loc_14000AD96
0x14000acc7  lea     rax, [rbp+hKey]
0x14000accb  mov     r9d, 20019h; samDesired
0x14000acd1  xor     r8d, r8d; ulOptions
0x14000acd4  mov     [rsp+60h+phkResult], rax; phkResult
0x14000acd9  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Siuf\\Staging\\"
0x14000ace0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000ace7  call    cs:__imp_RegOpenKeyExW
0x14000acee  nop     dword ptr [rax+rax+00h]
0x14000acf3  test    eax, eax
0x14000acf5  jz      short loc_14000ACFE
0x14000acf7  mov     ebx, 5DD0116h
0x14000acfc  jmp     short loc_14000AD6A
0x14000acfe  mov     rcx, [rbp+hKey]; hKey
0x14000ad02  lea     rax, [rbp+var_20]
0x14000ad06  mov     r9d, 20019h; samDesired
0x14000ad0c  mov     [rsp+60h+phkResult], rax; phkResult
0x14000ad11  xor     r8d, r8d; ulOptions
0x14000ad14  mov     rdx, rbx; lpSubKey
0x14000ad17  call    cs:__imp_RegOpenKeyExW
0x14000ad1e  nop     dword ptr [rax+rax+00h]
0x14000ad23  test    eax, eax
0x14000ad25  jz      short loc_14000AD2E
0x14000ad27  mov     ebx, 5DD0117h
0x14000ad2c  jmp     short loc_14000AD6A
0x14000ad2e  mov     rcx, [rbp+var_20]; hKey
0x14000ad32  lea     rax, [rbp+cbData]
0x14000ad36  mov     [rsp+60h+lpcbData], rax; lpcbData
0x14000ad3b  xor     r9d, r9d; lpType
0x14000ad3e  xor     r8d, r8d; lpReserved
0x14000ad41  mov     [rsp+60h+phkResult], rdi; lpData
0x14000ad46  xor     edx, edx; lpValueName
0x14000ad48  mov     [rbp+cbData], 2710h
0x14000ad4f  mov     ebx, 5DD011h
0x14000ad54  call    cs:__imp_RegQueryValueExW
0x14000ad5b  nop     dword ptr [rax+rax+00h]
0x14000ad60  test    eax, eax
0x14000ad62  mov     ecx, 5DD0118h
0x14000ad67  cmovnz  ebx, ecx
0x14000ad6a  mov     rcx, [rbp+hKey]; hObject
0x14000ad6e  test    rcx, rcx
0x14000ad71  jz      short loc_14000AD7F
0x14000ad73  call    cs:__imp_CloseHandle
0x14000ad7a  nop     dword ptr [rax+rax+00h]
0x14000ad7f  mov     rcx, [rbp+var_20]; hObject
0x14000ad83  test    rcx, rcx
0x14000ad86  jz      short loc_14000AD94
0x14000ad88  call    cs:__imp_CloseHandle
0x14000ad8f  nop     dword ptr [rax+rax+00h]
0x14000ad94  mov     eax, ebx
0x14000ad96  mov     rcx, [rbp+var_8]
0x14000ad9a  xor     rcx, rsp; StackCookie
0x14000ad9d  call    __security_check_cookie
0x14000ada2  lea     r11, [rsp+60h+var_s0]
0x14000ada7  mov     rbx, [r11+20h]
0x14000adab  mov     rdi, [r11+28h]
0x14000adaf  mov     rsp, r11
0x14000adb2  pop     rbp
0x14000adb3  retn
```
