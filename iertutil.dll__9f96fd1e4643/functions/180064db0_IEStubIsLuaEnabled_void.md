# IEStubIsLuaEnabled(void)

- ea: `0x180064db0`
- end: `0x180064e7a`
- name: `?IEStubIsLuaEnabled@@YAHXZ`
- size: `202`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180064c0c`
- `0x180064f64`

## callees

- `0x180064db0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180064dfa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180064dfa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064e32`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064e32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064e5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064e5f`

## pseudocode

```c
__int64 IEStubIsLuaEnabled(void)
{
  LSTATUS v0; // eax
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  cbData = 0;
  Data = 0;
  if ( !dword_18029A158 )
  {
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
            0,
            0x20019u,
            &hKey) )
    {
      cbData = 4;
      v0 = RegQueryValueExW(hKey, L"EnableLUA", 0, 0, (LPBYTE)&Data, &cbData);
      if ( v0 )
      {
        if ( v0 == 2 )
          dword_18029A13C = 1;
      }
      else
      {
        dword_18029A13C = Data != 0;
      }
      RegCloseKey(hKey);
    }
    dword_18029A158 = 1;
  }
  return (unsigned int)dword_18029A13C;
}

```

## disassembly

```asm
0x180064db0  mov     rax, rsp
0x180064db3  sub     rsp, 38h
0x180064db7  cmp     cs:dword_18029A158, 0
0x180064dbe  mov     qword ptr [rax+18h], 0
0x180064dc6  mov     dword ptr [rax+8], 0
0x180064dcd  mov     dword ptr [rax+10h], 0
0x180064dd4  jnz     loc_180064E6F
0x180064dda  lea     rax, [rax+18h]
0x180064dde  mov     r9d, 20019h; samDesired
0x180064de4  xor     r8d, r8d; ulOptions
0x180064de7  mov     [rsp+38h+phkResult], rax; phkResult
0x180064dec  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180064df3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180064dfa  call    cs:__imp_RegOpenKeyExW
0x180064e00  test    eax, eax
0x180064e02  jnz     short loc_180064E65
0x180064e04  mov     rcx, [rsp+38h+hKey]; hKey
0x180064e09  lea     rax, [rsp+38h+cbData]
0x180064e0e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180064e13  lea     rdx, aEnablelua; "EnableLUA"
0x180064e1a  lea     rax, [rsp+38h+Data]
0x180064e1f  mov     [rsp+38h+cbData], 4
0x180064e27  xor     r9d, r9d; lpType
0x180064e2a  mov     [rsp+38h+phkResult], rax; lpData
0x180064e2f  xor     r8d, r8d; lpReserved
0x180064e32  call    cs:__imp_RegQueryValueExW
0x180064e38  test    eax, eax
0x180064e3a  jnz     short loc_180064E4B
0x180064e3c  cmp     [rsp+38h+Data], eax
0x180064e40  setnz   al
0x180064e43  mov     cs:dword_18029A13C, eax
0x180064e49  jmp     short loc_180064E5A
0x180064e4b  cmp     eax, 2
0x180064e4e  jnz     short loc_180064E5A
0x180064e50  mov     cs:dword_18029A13C, 1
0x180064e5a  mov     rcx, [rsp+38h+hKey]; hKey
0x180064e5f  call    cs:__imp_RegCloseKey
0x180064e65  mov     cs:dword_18029A158, 1
0x180064e6f  mov     eax, cs:dword_18029A13C
0x180064e75  add     rsp, 38h
0x180064e79  retn
```
