# GetAppShim(void)

- ea: `0x18006c430`
- end: `0x18006c554`
- name: `?GetAppShim@@YAKXZ`
- size: `292`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006c9a0`

## callees

- `0x1800388a0`
- `0x18006c430`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x18006c4d4`
- `KERNEL32!GetFullPathNameW` at `0x18006c4d4`
- `KERNEL32!GetModuleFileNameW` at `0x18006c4a5`
- `KERNEL32!GetModuleFileNameW` at `0x18006c4a5`
- `ADVAPI32!RegQueryValueExW` at `0x18006c51a`
- `ADVAPI32!RegQueryValueExW` at `0x18006c51a`
- `ADVAPI32!RegOpenKeyExW` at `0x18006c484`
- `ADVAPI32!RegOpenKeyExW` at `0x18006c484`
- `ADVAPI32!RegCloseKey` at `0x18006c52b`
- `ADVAPI32!RegCloseKey` at `0x18006c52b`

## string_xrefs

- `0x18006c476`: `software\Microsoft\DirectShow\Compat`

## pseudocode

```c
__int64 GetAppShim(void)
{
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR FilePart; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+260h] [rbp+160h] BYREF

  *(_DWORD *)Data = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"software\\Microsoft\\DirectShow\\Compat", 0, 0x20019u, &hKey) )
  {
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      FilePart = 0;
      if ( GetFullPathNameW(Filename, 0x104u, Buffer, &FilePart) )
      {
        Type = 0;
        cbData = 4;
        RegQueryValueExW(hKey, FilePart, 0, &Type, Data, &cbData);
      }
    }
    RegCloseKey(hKey);
  }
  return *(unsigned int *)Data;
}

```

## disassembly

```asm
0x18006c430  push    rbp
0x18006c432  lea     rbp, [rsp-380h]
0x18006c43a  sub     rsp, 480h
0x18006c441  mov     rax, cs:__security_cookie
0x18006c448  xor     rax, rsp
0x18006c44b  mov     [rbp+380h+var_10], rax
0x18006c452  lea     rax, [rsp+480h+hKey]
0x18006c457  mov     dword ptr [rsp+480h+Data], 0
0x18006c45f  mov     r9d, 20019h; samDesired
0x18006c465  mov     [rsp+480h+phkResult], rax; phkResult
0x18006c46a  xor     r8d, r8d; ulOptions
0x18006c46d  mov     [rsp+480h+hKey], 0
0x18006c476  lea     rdx, aSoftwareMicros_0; "software\\Microsoft\\DirectShow\\Compat"
0x18006c47d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006c484  call    cs:__imp_RegOpenKeyExW
0x18006c48b  nop     dword ptr [rax+rax+00h]
0x18006c490  test    eax, eax
0x18006c492  jnz     loc_18006C537
0x18006c498  mov     r8d, 104h; nSize
0x18006c49e  lea     rdx, [rsp+480h+Filename]; lpFilename
0x18006c4a3  xor     ecx, ecx; hModule
0x18006c4a5  call    cs:__imp_GetModuleFileNameW
0x18006c4ac  nop     dword ptr [rax+rax+00h]
0x18006c4b1  test    eax, eax
0x18006c4b3  jz      short loc_18006C526
0x18006c4b5  lea     r9, [rsp+480h+FilePart]; lpFilePart
0x18006c4ba  mov     [rsp+480h+FilePart], 0
0x18006c4c3  lea     r8, [rbp+380h+Buffer]; lpBuffer
0x18006c4ca  mov     edx, 104h; nBufferLength
0x18006c4cf  lea     rcx, [rsp+480h+Filename]; lpFileName
0x18006c4d4  call    cs:__imp_GetFullPathNameW
0x18006c4db  nop     dword ptr [rax+rax+00h]
0x18006c4e0  test    eax, eax
0x18006c4e2  jz      short loc_18006C526
0x18006c4e4  mov     rdx, [rsp+480h+FilePart]; lpValueName
0x18006c4e9  lea     rax, [rsp+480h+cbData]
0x18006c4ee  mov     rcx, [rsp+480h+hKey]; hKey
0x18006c4f3  lea     r9, [rsp+480h+Type]; lpType
0x18006c4f8  mov     [rsp+480h+lpcbData], rax; lpcbData
0x18006c4fd  xor     r8d, r8d; lpReserved
0x18006c500  lea     rax, [rsp+480h+Data]
0x18006c505  mov     [rsp+480h+Type], 0
0x18006c50d  mov     [rsp+480h+phkResult], rax; lpData
0x18006c512  mov     [rsp+480h+cbData], 4
0x18006c51a  call    cs:__imp_RegQueryValueExW
0x18006c521  nop     dword ptr [rax+rax+00h]
0x18006c526  mov     rcx, [rsp+480h+hKey]; hKey
0x18006c52b  call    cs:__imp_RegCloseKey
0x18006c532  nop     dword ptr [rax+rax+00h]
0x18006c537  mov     eax, dword ptr [rsp+480h+Data]
0x18006c53b  mov     rcx, [rbp+380h+var_10]
0x18006c542  xor     rcx, rsp; StackCookie
0x18006c545  call    __security_check_cookie
0x18006c54a  add     rsp, 480h
0x18006c551  pop     rbp
0x18006c552  retn
```
