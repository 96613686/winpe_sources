# MoveBootpTable

- ea: `0x180090c38`
- end: `0x180090dc9`
- name: `MoveBootpTable`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800114a4`

## callees

- `0x180090c38`

## import_xrefs

- `ADVAPI32!RegOpenKeyW` at `0x180090c6a`
- `ADVAPI32!RegOpenKeyW` at `0x180090c8c`
- `ADVAPI32!RegOpenKeyW` at `0x180090c6a`
- `ADVAPI32!RegOpenKeyW` at `0x180090c8c`
- `ADVAPI32!RegCloseKey` at `0x180090ca2`
- `ADVAPI32!RegCloseKey` at `0x180090d93`
- `ADVAPI32!RegCloseKey` at `0x180090da3`
- `ADVAPI32!RegCloseKey` at `0x180090ca2`
- `ADVAPI32!RegCloseKey` at `0x180090d93`
- `ADVAPI32!RegCloseKey` at `0x180090da3`
- `ADVAPI32!RegQueryValueExW` at `0x180090ccf`
- `ADVAPI32!RegQueryValueExW` at `0x180090d34`
- `ADVAPI32!RegQueryValueExW` at `0x180090ccf`
- `ADVAPI32!RegQueryValueExW` at `0x180090d34`
- `ADVAPI32!RegSetValueExW` at `0x180090d64`
- `ADVAPI32!RegSetValueExW` at `0x180090d64`
- `ADVAPI32!RegDeleteValueW` at `0x180090d81`
- `ADVAPI32!RegDeleteValueW` at `0x180090d81`
- `KERNEL32!LocalAlloc` at `0x180090cfb`
- `KERNEL32!LocalAlloc` at `0x180090cfb`
- `KERNEL32!LocalFree` at `0x180090db2`
- `KERNEL32!LocalFree` at `0x180090db2`

## string_xrefs

- `0x180090c85`: `SYSTEM\CurrentControlSet\Services\DHCPServer\Parameters`
- `0x180090c51`: `SOFTWARE\Microsoft\DhcpServer\Configuration\GlobalOptionValues`

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

  phkResult = 0;
  hKey = 0;
  lpData = 0;
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
0x180090c38  push    rbp
0x180090c3a  push    rbx
0x180090c3b  push    rdi
0x180090c3c  mov     rbp, rsp
0x180090c3f  sub     rsp, 30h
0x180090c43  and     [rbp+phkResult], 0
0x180090c48  lea     r8, [rbp+phkResult]; phkResult
0x180090c4c  and     [rbp+hKey], 0
0x180090c51  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\DhcpServer\\Config"...
0x180090c58  xor     edi, edi
0x180090c5a  mov     rbx, 0FFFFFFFF80000002h
0x180090c61  and     [rbp+cbData], edi
0x180090c64  mov     rcx, rbx; hKey
0x180090c67  and     [rbp+Type], edi
0x180090c6a  call    cs:__imp_RegOpenKeyW
0x180090c71  nop     dword ptr [rax+rax+00h]
0x180090c76  test    eax, eax
0x180090c78  jnz     loc_180090DC0
0x180090c7e  lea     r8, [rbp+hKey]; phkResult
0x180090c82  mov     rcx, rbx; hKey
0x180090c85  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\DH"...
0x180090c8c  call    cs:__imp_RegOpenKeyW
0x180090c93  nop     dword ptr [rax+rax+00h]
0x180090c98  mov     rcx, [rbp+phkResult]; hKey
0x180090c9c  mov     ebx, eax
0x180090c9e  test    eax, eax
0x180090ca0  jz      short loc_180090CB3
0x180090ca2  call    cs:__imp_RegCloseKey
0x180090ca9  nop     dword ptr [rax+rax+00h]
0x180090cae  jmp     loc_180090DBE
0x180090cb3  lea     rax, [rbp+cbData]
0x180090cb7  xor     r8d, r8d; lpReserved
0x180090cba  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180090cbf  lea     r9, [rbp+Type]; lpType
0x180090cc3  and     [rsp+30h+lpData], rdi
0x180090cc8  lea     rdx, aBootfiletable; "BootFileTable"
0x180090ccf  call    cs:__imp_RegQueryValueExW
0x180090cd6  nop     dword ptr [rax+rax+00h]
0x180090cdb  mov     ebx, eax
0x180090cdd  test    eax, eax
0x180090cdf  jnz     loc_180090D8F
0x180090ce5  cmp     [rbp+Type], 7
0x180090ce9  jz      short loc_180090CF3
0x180090ceb  lea     ebx, [rax+57h]
0x180090cee  jmp     loc_180090D8F
0x180090cf3  mov     edx, [rbp+cbData]; uBytes
0x180090cf6  mov     ecx, 40h ; '@'; uFlags
0x180090cfb  call    cs:__imp_LocalAlloc
0x180090d02  nop     dword ptr [rax+rax+00h]
0x180090d07  mov     rdi, rax
0x180090d0a  test    rax, rax
0x180090d0d  jnz     short loc_180090D14
0x180090d0f  lea     ebx, [rax+8]
0x180090d12  jmp     short loc_180090D8F
0x180090d14  mov     rcx, [rbp+phkResult]; hKey
0x180090d18  lea     rax, [rbp+cbData]
0x180090d1c  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180090d21  lea     r9, [rbp+Type]; lpType
0x180090d25  xor     r8d, r8d; lpReserved
0x180090d28  mov     [rsp+30h+lpData], rdi; lpData
0x180090d2d  lea     rdx, aBootfiletable; "BootFileTable"
0x180090d34  call    cs:__imp_RegQueryValueExW
0x180090d3b  nop     dword ptr [rax+rax+00h]
0x180090d40  mov     ebx, eax
0x180090d42  test    eax, eax
0x180090d44  jnz     short loc_180090D8F
0x180090d46  mov     eax, [rbp+cbData]
0x180090d49  lea     r9d, [rbx+7]; dwType
0x180090d4d  mov     rcx, [rbp+hKey]; hKey
0x180090d51  lea     rdx, aBootfiletable; "BootFileTable"
0x180090d58  mov     dword ptr [rsp+30h+lpcbData], eax; cbData
0x180090d5c  xor     r8d, r8d; Reserved
0x180090d5f  mov     [rsp+30h+lpData], rdi; lpData
0x180090d64  call    cs:__imp_RegSetValueExW
0x180090d6b  nop     dword ptr [rax+rax+00h]
0x180090d70  mov     ebx, eax
0x180090d72  test    eax, eax
0x180090d74  jnz     short loc_180090D8F
0x180090d76  mov     rcx, [rbp+phkResult]; hKey
0x180090d7a  lea     rdx, aBootfiletable; "BootFileTable"
0x180090d81  call    cs:__imp_RegDeleteValueW
0x180090d88  nop     dword ptr [rax+rax+00h]
0x180090d8d  mov     ebx, eax
0x180090d8f  mov     rcx, [rbp+phkResult]; hKey
0x180090d93  call    cs:__imp_RegCloseKey
0x180090d9a  nop     dword ptr [rax+rax+00h]
0x180090d9f  mov     rcx, [rbp+hKey]; hKey
0x180090da3  call    cs:__imp_RegCloseKey
0x180090daa  nop     dword ptr [rax+rax+00h]
0x180090daf  mov     rcx, rdi; hMem
0x180090db2  call    cs:__imp_LocalFree
0x180090db9  nop     dword ptr [rax+rax+00h]
0x180090dbe  mov     eax, ebx
0x180090dc0  add     rsp, 30h
0x180090dc4  pop     rdi
0x180090dc5  pop     rbx
0x180090dc6  pop     rbp
0x180090dc7  retn
```
