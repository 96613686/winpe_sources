# MoveBootpTable

- ea: `0x180090df4`
- end: `0x180090f8b`
- name: `MoveBootpTable`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010bb8`

## callees

- `0x180090df4`

## import_xrefs

- `ADVAPI32!RegOpenKeyW` at `0x180090e2c`
- `ADVAPI32!RegOpenKeyW` at `0x180090e4e`
- `ADVAPI32!RegOpenKeyW` at `0x180090e2c`
- `ADVAPI32!RegOpenKeyW` at `0x180090e4e`
- `ADVAPI32!RegCloseKey` at `0x180090e64`
- `ADVAPI32!RegCloseKey` at `0x180090f55`
- `ADVAPI32!RegCloseKey` at `0x180090f65`
- `ADVAPI32!RegCloseKey` at `0x180090e64`
- `ADVAPI32!RegCloseKey` at `0x180090f55`
- `ADVAPI32!RegCloseKey` at `0x180090f65`
- `ADVAPI32!RegQueryValueExW` at `0x180090e91`
- `ADVAPI32!RegQueryValueExW` at `0x180090ef6`
- `ADVAPI32!RegQueryValueExW` at `0x180090e91`
- `ADVAPI32!RegQueryValueExW` at `0x180090ef6`
- `ADVAPI32!RegSetValueExW` at `0x180090f26`
- `ADVAPI32!RegSetValueExW` at `0x180090f26`
- `ADVAPI32!RegDeleteValueW` at `0x180090f43`
- `ADVAPI32!RegDeleteValueW` at `0x180090f43`
- `KERNEL32!LocalAlloc` at `0x180090ebd`
- `KERNEL32!LocalAlloc` at `0x180090ebd`
- `KERNEL32!LocalFree` at `0x180090f74`
- `KERNEL32!LocalFree` at `0x180090f74`

## string_xrefs

- `0x180090e47`: `SYSTEM\CurrentControlSet\Services\DHCPServer\Parameters`
- `0x180090e25`: `SOFTWARE\Microsoft\DhcpServer\Configuration\GlobalOptionValues`

## pseudocode

```c
LSTATUS MoveBootpTable()
{
  BYTE *lpData; // rdi
  LSTATUS result; // eax
  LSTATUS v2; // ebx
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  lpData = 0;
  phkResult = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  result = RegOpenKeyW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\DhcpServer\\Configuration\\GlobalOptionValues",
             &phkResult);
  if ( !result )
  {
    v2 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\DHCPServer\\Parameters", &hKey);
    if ( v2 )
    {
      RegCloseKey(phkResult);
    }
    else
    {
      v2 = RegQueryValueExW(phkResult, L"BootFileTable", 0, &Type, 0, &cbData);
      if ( !v2 )
      {
        if ( Type == 7 )
        {
          lpData = (BYTE *)LocalAlloc(0x40u, cbData);
          if ( lpData )
          {
            v2 = RegQueryValueExW(phkResult, L"BootFileTable", 0, &Type, lpData, &cbData);
            if ( !v2 )
            {
              v2 = RegSetValueExW(hKey, L"BootFileTable", 0, 7u, lpData, cbData);
              if ( !v2 )
                v2 = RegDeleteValueW(phkResult, L"BootFileTable");
            }
          }
          else
          {
            v2 = 8;
          }
        }
        else
        {
          v2 = 87;
        }
      }
      RegCloseKey(phkResult);
      RegCloseKey(hKey);
      LocalFree(lpData);
    }
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x180090df4  push    rbp
0x180090df6  push    rbx
0x180090df7  push    rdi
0x180090df8  mov     rbp, rsp
0x180090dfb  sub     rsp, 30h
0x180090dff  xor     edi, edi
0x180090e01  mov     [rbp+phkResult], 0
0x180090e09  mov     rbx, 0FFFFFFFF80000002h
0x180090e10  mov     [rbp+hKey], 0
0x180090e18  mov     rcx, rbx; hKey
0x180090e1b  mov     [rbp+cbData], edi
0x180090e1e  lea     r8, [rbp+phkResult]; phkResult
0x180090e22  mov     [rbp+Type], edi
0x180090e25  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\DhcpServer\\Config"...
0x180090e2c  call    cs:__imp_RegOpenKeyW
0x180090e33  nop     dword ptr [rax+rax+00h]
0x180090e38  test    eax, eax
0x180090e3a  jnz     loc_180090F82
0x180090e40  lea     r8, [rbp+hKey]; phkResult
0x180090e44  mov     rcx, rbx; hKey
0x180090e47  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\DH"...
0x180090e4e  call    cs:__imp_RegOpenKeyW
0x180090e55  nop     dword ptr [rax+rax+00h]
0x180090e5a  mov     rcx, [rbp+phkResult]; hKey
0x180090e5e  mov     ebx, eax
0x180090e60  test    eax, eax
0x180090e62  jz      short loc_180090E75
0x180090e64  call    cs:__imp_RegCloseKey
0x180090e6b  nop     dword ptr [rax+rax+00h]
0x180090e70  jmp     loc_180090F80
0x180090e75  lea     rax, [rbp+cbData]
0x180090e79  xor     r8d, r8d; lpReserved
0x180090e7c  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180090e81  lea     r9, [rbp+Type]; lpType
0x180090e85  lea     rdx, aBootfiletable; "BootFileTable"
0x180090e8c  mov     [rsp+30h+lpData], rdi; lpData
0x180090e91  call    cs:__imp_RegQueryValueExW
0x180090e98  nop     dword ptr [rax+rax+00h]
0x180090e9d  mov     ebx, eax
0x180090e9f  test    eax, eax
0x180090ea1  jnz     loc_180090F51
0x180090ea7  cmp     [rbp+Type], 7
0x180090eab  jz      short loc_180090EB5
0x180090ead  lea     ebx, [rax+57h]
0x180090eb0  jmp     loc_180090F51
0x180090eb5  mov     edx, [rbp+cbData]; uBytes
0x180090eb8  mov     ecx, 40h ; '@'; uFlags
0x180090ebd  call    cs:__imp_LocalAlloc
0x180090ec4  nop     dword ptr [rax+rax+00h]
0x180090ec9  mov     rdi, rax
0x180090ecc  test    rax, rax
0x180090ecf  jnz     short loc_180090ED6
0x180090ed1  lea     ebx, [rax+8]
0x180090ed4  jmp     short loc_180090F51
0x180090ed6  mov     rcx, [rbp+phkResult]; hKey
0x180090eda  lea     rax, [rbp+cbData]
0x180090ede  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180090ee3  lea     r9, [rbp+Type]; lpType
0x180090ee7  xor     r8d, r8d; lpReserved
0x180090eea  mov     [rsp+30h+lpData], rdi; lpData
0x180090eef  lea     rdx, aBootfiletable; "BootFileTable"
0x180090ef6  call    cs:__imp_RegQueryValueExW
0x180090efd  nop     dword ptr [rax+rax+00h]
0x180090f02  mov     ebx, eax
0x180090f04  test    eax, eax
0x180090f06  jnz     short loc_180090F51
0x180090f08  mov     eax, [rbp+cbData]
0x180090f0b  lea     r9d, [rbx+7]; dwType
0x180090f0f  mov     rcx, [rbp+hKey]; hKey
0x180090f13  lea     rdx, aBootfiletable; "BootFileTable"
0x180090f1a  mov     dword ptr [rsp+30h+lpcbData], eax; cbData
0x180090f1e  xor     r8d, r8d; Reserved
0x180090f21  mov     [rsp+30h+lpData], rdi; lpData
0x180090f26  call    cs:__imp_RegSetValueExW
0x180090f2d  nop     dword ptr [rax+rax+00h]
0x180090f32  mov     ebx, eax
0x180090f34  test    eax, eax
0x180090f36  jnz     short loc_180090F51
0x180090f38  mov     rcx, [rbp+phkResult]; hKey
0x180090f3c  lea     rdx, aBootfiletable; "BootFileTable"
0x180090f43  call    cs:__imp_RegDeleteValueW
0x180090f4a  nop     dword ptr [rax+rax+00h]
0x180090f4f  mov     ebx, eax
0x180090f51  mov     rcx, [rbp+phkResult]; hKey
0x180090f55  call    cs:__imp_RegCloseKey
0x180090f5c  nop     dword ptr [rax+rax+00h]
0x180090f61  mov     rcx, [rbp+hKey]; hKey
0x180090f65  call    cs:__imp_RegCloseKey
0x180090f6c  nop     dword ptr [rax+rax+00h]
0x180090f71  mov     rcx, rdi; hMem
0x180090f74  call    cs:__imp_LocalFree
0x180090f7b  nop     dword ptr [rax+rax+00h]
0x180090f80  mov     eax, ebx
0x180090f82  add     rsp, 30h
0x180090f86  pop     rdi
0x180090f87  pop     rbx
0x180090f88  pop     rbp
0x180090f89  retn
```
