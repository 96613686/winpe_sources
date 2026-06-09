# GetConfigInfo

- ea: `0x180131cc8`
- end: `0x180131da8`
- name: `GetConfigInfo`
- size: `224`
- prototype: `__int64 __fastcall(LPBYTE lpData, LPBYTE)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180131a34`

## callees

- `0x180003d80`
- `0x180131cc8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180131d1d`
- `ADVAPI32!RegOpenKeyExW` at `0x180131d1d`
- `ADVAPI32!RegQueryValueExW` at `0x180131d50`
- `ADVAPI32!RegQueryValueExW` at `0x180131d7f`
- `ADVAPI32!RegQueryValueExW` at `0x180131d50`
- `ADVAPI32!RegQueryValueExW` at `0x180131d7f`
- `ADVAPI32!RegCloseKey` at `0x180131d8a`
- `ADVAPI32!RegCloseKey` at `0x180131d8a`

## string_xrefs

- `0x180131d12`: `SOFTWARE\Microsoft\DataAccess\MSOLEDBSQL`

## pseudocode

```c
LSTATUS __fastcall GetConfigInfo(LPBYTE lpData, LPBYTE a2)
{
  LSTATUS result; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  *(_DWORD *)lpData = 1;
  *(_DWORD *)a2 = g_SystemInfo.dwNumberOfProcessors + 1;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\DataAccess\\MSOLEDBSQL", 0, 0x20019u, &hKey);
  if ( !result )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"UseMPHeap", 0, 0, lpData, &cbData);
    cbData = 4;
    RegQueryValueExW(hKey, L"NumberOfCsPools", 0, 0, a2, &cbData);
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180131cc8  mov     r11, rsp
0x180131ccb  mov     [r11+18h], rbx
0x180131ccf  push    rdi
0x180131cd0  sub     rsp, 50h
0x180131cd4  mov     rax, cs:__security_cookie
0x180131cdb  xor     rax, rsp
0x180131cde  mov     [rsp+58h+var_18], rax
0x180131ce3  and     qword ptr [r11-28h], 0
0x180131ce8  mov     rdi, rdx
0x180131ceb  mov     dword ptr [rcx], 1
0x180131cf1  mov     rbx, rcx
0x180131cf4  mov     eax, cs:?g_SystemInfo@@3U_SYSTEM_INFO@@A.dwNumberOfProcessors; _SYSTEM_INFO g_SystemInfo ...
0x180131cfa  mov     r9d, 20019h; samDesired
0x180131d00  inc     eax
0x180131d02  xor     r8d, r8d; ulOptions
0x180131d05  mov     [rdx], eax
0x180131d07  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180131d0e  lea     rax, [r11-28h]
0x180131d12  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\DataAccess\\MSOLED"...
0x180131d19  mov     [r11-38h], rax
0x180131d1d  call    cs:__imp_RegOpenKeyExW
0x180131d23  test    eax, eax
0x180131d25  jnz     short loc_180131D90
0x180131d27  mov     rcx, [rsp+58h+hKey]; hKey
0x180131d2c  lea     rax, [rsp+58h+cbData]
0x180131d31  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180131d36  lea     rdx, aUsempheap; "UseMPHeap"
0x180131d3d  xor     r9d, r9d; lpType
0x180131d40  mov     [rsp+58h+lpData], rbx; lpData
0x180131d45  xor     r8d, r8d; lpReserved
0x180131d48  mov     [rsp+58h+cbData], 4
0x180131d50  call    cs:__imp_RegQueryValueExW
0x180131d56  mov     rcx, [rsp+58h+hKey]; hKey
0x180131d5b  lea     rax, [rsp+58h+cbData]
0x180131d60  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180131d65  lea     rdx, aNumberofcspool; "NumberOfCsPools"
0x180131d6c  xor     r9d, r9d; lpType
0x180131d6f  mov     [rsp+58h+lpData], rdi; lpData
0x180131d74  xor     r8d, r8d; lpReserved
0x180131d77  mov     [rsp+58h+cbData], 4
0x180131d7f  call    cs:__imp_RegQueryValueExW
0x180131d85  mov     rcx, [rsp+58h+hKey]; hKey
0x180131d8a  call    cs:__imp_RegCloseKey
0x180131d90  mov     rcx, [rsp+58h+var_18]
0x180131d95  xor     rcx, rsp; StackCookie
0x180131d98  call    __security_check_cookie
0x180131d9d  mov     rbx, [rsp+58h+arg_10]
0x180131da2  add     rsp, 50h
0x180131da6  pop     rdi
0x180131da7  retn
```
