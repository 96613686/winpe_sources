# IsPerfCountersEnabledOnPlatform(PlatformEnum)

- ea: `0x18001181c`
- end: `0x1800118e5`
- name: `?IsPerfCountersEnabledOnPlatform@@YAHW4PlatformEnum@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000af80`

## callees

- `0x18001181c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800118d7`
- `ADVAPI32!RegCloseKey` at `0x1800118d7`
- `ADVAPI32!RegGetValueW` at `0x1800118b8`
- `ADVAPI32!RegGetValueW` at `0x1800118b8`
- `ADVAPI32!RegOpenKeyExW` at `0x180011871`
- `ADVAPI32!RegOpenKeyExW` at `0x180011871`

## pseudocode

```c
__int64 __fastcall IsPerfCountersEnabledOnPlatform(int a1)
{
  REGSAM v1; // r9d
  unsigned int v2; // ebx
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  __int16 pvData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+68h] [rbp+20h] BYREF

  hkey = 0;
  pcbData = 0;
  v1 = 131097;
  pvData = 0;
  if ( a1 != 1 )
    v1 = (a1 != 0 ? 256 : 512) | 0x20019;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\ODBC\\ODBCINST.INI\\ODBC Connection Pooling", 0, v1, &hkey) )
  {
    v2 = 0;
  }
  else
  {
    pcbData = 4;
    v2 = 0;
    if ( !RegGetValueW(hkey, 0, L"PerfMon", 2u, 0, &pvData, &pcbData) )
      LOBYTE(v2) = pvData == 49;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v2;
}

```

## disassembly

```asm
0x18001181c  push    rbx
0x18001181e  sub     rsp, 40h
0x180011822  xor     eax, eax
0x180011824  mov     [rsp+48h+hkey], 0
0x18001182d  mov     [rsp+48h+arg_8], 0
0x180011835  mov     r9d, 20019h
0x18001183b  mov     [rsp+48h+arg_10], ax
0x180011840  cmp     ecx, 1
0x180011843  jz      short loc_180011856
0x180011845  neg     ecx
0x180011847  sbb     eax, eax
0x180011849  and     eax, 0FFFFFF00h
0x18001184e  add     eax, 200h
0x180011853  or      r9d, eax; samDesired
0x180011856  lea     rax, [rsp+48h+hkey]
0x18001185b  xor     r8d, r8d; ulOptions
0x18001185e  lea     rdx, aSoftwareOdbcOd_2; "SOFTWARE\\ODBC\\ODBCINST.INI\\ODBC Conn"...
0x180011865  mov     [rsp+48h+phkResult], rax; phkResult
0x18001186a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011871  call    cs:__imp_RegOpenKeyExW
0x180011877  test    eax, eax
0x180011879  jz      short loc_18001187F
0x18001187b  xor     ebx, ebx
0x18001187d  jmp     short loc_1800118CD
0x18001187f  mov     rcx, [rsp+48h+hkey]; hkey
0x180011884  lea     rax, [rsp+48h+arg_8]
0x180011889  mov     [rsp+48h+pcbData], rax; pcbData
0x18001188e  lea     r8, Value; "PerfMon"
0x180011895  lea     rax, [rsp+48h+arg_10]
0x18001189a  mov     [rsp+48h+arg_8], 4
0x1800118a2  mov     [rsp+48h+pvData], rax; pvData
0x1800118a7  mov     r9d, 2; dwFlags
0x1800118ad  xor     edx, edx; lpSubKey
0x1800118af  mov     [rsp+48h+phkResult], 0; pdwType
0x1800118b8  call    cs:__imp_RegGetValueW
0x1800118be  xor     ebx, ebx
0x1800118c0  test    eax, eax
0x1800118c2  jnz     short loc_1800118CD
0x1800118c4  cmp     [rsp+48h+arg_10], 31h ; '1'
0x1800118ca  setz    bl
0x1800118cd  mov     rcx, [rsp+48h+hkey]; hKey
0x1800118d2  test    rcx, rcx
0x1800118d5  jz      short loc_1800118DD
0x1800118d7  call    cs:__imp_RegCloseKey
0x1800118dd  mov     eax, ebx
0x1800118df  add     rsp, 40h
0x1800118e3  pop     rbx
0x1800118e4  retn
```
