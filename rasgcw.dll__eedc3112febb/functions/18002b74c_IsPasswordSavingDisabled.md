# IsPasswordSavingDisabled

- ea: `0x18002b74c`
- end: `0x18002b82b`
- name: `IsPasswordSavingDisabled`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180012ed4`
- `0x1800195a4`

## callees

- `0x18002b74c`
- `0x18002bc68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b808`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b808`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b7c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b7c7`
- `KERNEL32!RegQueryValueExW` at `0x18002b7fc`
- `KERNEL32!RegQueryValueExW` at `0x18002b7fc`

## string_xrefs

- `0x18002b7ab`: `System\CurrentControlSet\Services\Rasman\Parameters`

## pseudocode

```c
_BOOL8 IsPasswordSavingDisabled()
{
  LSTATUS v0; // ebx
  _BOOL8 result; // rax
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids);
  }
  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  result = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\Rasman\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    v0 = RegQueryValueExW(hKey, L"DisableSavePassword", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
    if ( !v0 && Type == 4 && Data )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18002b74c  push    rbp
0x18002b74e  push    rbx
0x18002b74f  mov     rbp, rsp
0x18002b752  sub     rsp, 38h
0x18002b756  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b75d  lea     rax, WPP_GLOBAL_Control
0x18002b764  cmp     rcx, rax
0x18002b767  jz      short loc_18002B78A
0x18002b769  test    byte ptr [rcx+1Ch], 4
0x18002b76d  jz      short loc_18002B78A
0x18002b76f  cmp     byte ptr [rcx+19h], 6
0x18002b773  jb      short loc_18002B78A
0x18002b775  mov     rcx, [rcx+10h]
0x18002b779  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18002b780  mov     edx, 30h ; '0'
0x18002b785  call    WPP_SF_
0x18002b78a  lea     rax, [rbp+hKey]
0x18002b78e  mov     [rbp+hKey], 0
0x18002b796  mov     r9d, 20019h; samDesired
0x18002b79c  mov     [rsp+38h+phkResult], rax; phkResult
0x18002b7a1  xor     r8d, r8d; ulOptions
0x18002b7a4  mov     [rbp+Type], 0
0x18002b7ab  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ra"...
0x18002b7b2  mov     [rbp+Data], 0
0x18002b7b9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b7c0  mov     [rbp+cbData], 0
0x18002b7c7  call    cs:__imp_RegOpenKeyExW
0x18002b7cd  test    eax, eax
0x18002b7cf  jnz     short loc_18002B822
0x18002b7d1  mov     rcx, [rbp+hKey]; hKey
0x18002b7d5  lea     rax, [rbp+cbData]
0x18002b7d9  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002b7de  lea     r9, [rbp+Type]; lpType
0x18002b7e2  lea     rax, [rbp+Data]
0x18002b7e6  mov     [rbp+cbData], 4
0x18002b7ed  xor     r8d, r8d; lpReserved
0x18002b7f0  mov     [rsp+38h+phkResult], rax; lpData
0x18002b7f5  lea     rdx, aDisablesavepas; "DisableSavePassword"
0x18002b7fc  call    cs:__imp_RegQueryValueExW
0x18002b802  mov     rcx, [rbp+hKey]; hKey
0x18002b806  mov     ebx, eax
0x18002b808  call    cs:__imp_RegCloseKey
0x18002b80e  test    ebx, ebx
0x18002b810  jnz     short loc_18002B822
0x18002b812  cmp     [rbp+Type], 4
0x18002b816  jnz     short loc_18002B822
0x18002b818  cmp     [rbp+Data], ebx
0x18002b81b  jz      short loc_18002B822
0x18002b81d  lea     eax, [rbx+1]
0x18002b820  jmp     short loc_18002B824
0x18002b822  xor     eax, eax
0x18002b824  add     rsp, 38h
0x18002b828  pop     rbx
0x18002b829  pop     rbp
0x18002b82a  retn
```
