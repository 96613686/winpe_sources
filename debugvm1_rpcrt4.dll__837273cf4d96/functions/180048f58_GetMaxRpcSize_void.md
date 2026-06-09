# GetMaxRpcSize(void)

- ea: `0x180048f58`
- end: `0x180048ff4`
- name: `?GetMaxRpcSize@@YAXXZ`
- size: `156`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002499c`

## callees

- `0x180048f58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180048f95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180048f95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048fe9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048fe9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180048fd0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180048fd0`

## pseudocode

```c
void GetMaxRpcSize(void)
{
  unsigned int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  hkey = 0;
  pvData = 0;
  pcbData = 4;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Rpc", 0, 0x20019u, &hkey) )
  {
    if ( !RegGetValueA(hkey, 0, "MaxRpcSize", 0x18u, 0, &pvData, &pcbData) )
      gMaxRpcSize = pvData;
    RegCloseKey(hkey);
  }
}

```

## disassembly

```asm
0x180048f58  mov     rax, rsp
0x180048f5b  sub     rsp, 48h
0x180048f5f  mov     qword ptr [rax+18h], 0
0x180048f67  mov     r9d, 20019h; samDesired
0x180048f6d  mov     dword ptr [rax+8], 0
0x180048f74  xor     r8d, r8d; ulOptions
0x180048f77  mov     dword ptr [rax+10h], 4
0x180048f7e  lea     rax, [rax+18h]
0x180048f82  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Rpc"
0x180048f89  mov     [rsp+48h+phkResult], rax; phkResult
0x180048f8e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180048f95  call    cs:__imp_RegOpenKeyExA
0x180048f9b  test    eax, eax
0x180048f9d  jnz     short loc_180048FEF
0x180048f9f  mov     rcx, [rsp+48h+hkey]; hkey
0x180048fa4  lea     rax, [rsp+48h+arg_8]
0x180048fa9  mov     [rsp+48h+pcbData], rax; pcbData
0x180048fae  lea     r8, Value; "MaxRpcSize"
0x180048fb5  lea     rax, [rsp+48h+arg_0]
0x180048fba  mov     r9d, 18h; dwFlags
0x180048fc0  mov     [rsp+48h+pvData], rax; pvData
0x180048fc5  xor     edx, edx; lpSubKey
0x180048fc7  mov     [rsp+48h+phkResult], 0; pdwType
0x180048fd0  call    cs:__imp_RegGetValueA
0x180048fd6  test    eax, eax
0x180048fd8  jnz     short loc_180048FE4
0x180048fda  mov     eax, [rsp+48h+arg_0]
0x180048fde  mov     cs:?gMaxRpcSize@@3KA, eax; ulong gMaxRpcSize
0x180048fe4  mov     rcx, [rsp+48h+hkey]; hKey
0x180048fe9  call    cs:__imp_RegCloseKey
0x180048fef  add     rsp, 48h
0x180048ff3  retn
```
