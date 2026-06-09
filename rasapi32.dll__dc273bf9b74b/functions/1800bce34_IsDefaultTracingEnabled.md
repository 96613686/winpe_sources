# IsDefaultTracingEnabled

- ea: `0x1800bce34`
- end: `0x1800bcec5`
- name: `IsDefaultTracingEnabled`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bbcf8`
- `0x1800bc148`

## callees

- `0x1800bce34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bce6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bce6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bceb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bceb7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bce9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bce9c`

## pseudocode

```c
__int64 IsDefaultTracingEnabled()
{
  unsigned int v0; // ebx
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v0 = 0;
  cbData = 4;
  hKey = 0;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Tracing", 0, 0x20019u, &hKey)
    && !RegQueryValueExW(hKey, L"DefaultTracing", 0, 0, (LPBYTE)&Data, &cbData) )
  {
    LOBYTE(v0) = Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x1800bce34  mov     rax, rsp
0x1800bce37  push    rbx
0x1800bce38  sub     rsp, 30h
0x1800bce3c  xor     ebx, ebx
0x1800bce3e  mov     dword ptr [rax+10h], 4
0x1800bce45  mov     [rax+18h], rbx
0x1800bce49  mov     r9d, 20019h; samDesired
0x1800bce4f  mov     [rax+8], ebx
0x1800bce52  lea     rax, [rax+18h]
0x1800bce56  xor     r8d, r8d; ulOptions
0x1800bce59  mov     [rsp+38h+phkResult], rax; phkResult
0x1800bce5e  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Tracing"
0x1800bce65  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bce6c  call    cs:__imp_RegOpenKeyExW
0x1800bce72  test    eax, eax
0x1800bce74  jnz     short loc_1800BCEAD
0x1800bce76  mov     rcx, [rsp+38h+hKey]; hKey
0x1800bce7b  lea     rax, [rsp+38h+cbData]
0x1800bce80  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800bce85  lea     rdx, aDefaulttracing; "DefaultTracing"
0x1800bce8c  lea     rax, [rsp+38h+Data]
0x1800bce91  xor     r9d, r9d; lpType
0x1800bce94  xor     r8d, r8d; lpReserved
0x1800bce97  mov     [rsp+38h+phkResult], rax; lpData
0x1800bce9c  call    cs:__imp_RegQueryValueExW
0x1800bcea2  test    eax, eax
0x1800bcea4  jnz     short loc_1800BCEAD
0x1800bcea6  cmp     [rsp+38h+Data], ebx
0x1800bceaa  setnz   bl
0x1800bcead  mov     rcx, [rsp+38h+hKey]; hKey
0x1800bceb2  test    rcx, rcx
0x1800bceb5  jz      short loc_1800BCEBD
0x1800bceb7  call    cs:__imp_RegCloseKey
0x1800bcebd  mov     eax, ebx
0x1800bcebf  add     rsp, 30h
0x1800bcec3  pop     rbx
0x1800bcec4  retn
```
