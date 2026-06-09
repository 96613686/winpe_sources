# TestClientForAccess

- ea: `0x180009ff0`
- end: `0x18000a044`
- name: `TestClientForAccess`
- size: `84`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800093a8`

## callees

- `0x180009ff0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a031`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a031`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a022`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a022`

## pseudocode

```c
__int64 TestClientForAccess()
{
  unsigned int v0; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v0 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib",
          0,
          0x20019u,
          &hKey) )
  {
    RegCloseKey(hKey);
    return 1;
  }
  return v0;
}

```

## disassembly

```asm
0x180009ff0  push    rbx
0x180009ff2  sub     rsp, 30h
0x180009ff6  lea     rax, [rsp+38h+hKey]
0x180009ffb  mov     [rsp+38h+hKey], 0
0x18000a004  mov     r9d, 20019h; samDesired
0x18000a00a  mov     [rsp+38h+phkResult], rax; phkResult
0x18000a00f  xor     r8d, r8d; ulOptions
0x18000a012  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000a019  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a020  xor     ebx, ebx
0x18000a022  call    cs:__imp_RegOpenKeyExW
0x18000a028  test    eax, eax
0x18000a02a  jnz     short loc_18000A03C
0x18000a02c  mov     rcx, [rsp+38h+hKey]; hKey
0x18000a031  call    cs:__imp_RegCloseKey
0x18000a037  mov     ebx, 1
0x18000a03c  mov     eax, ebx
0x18000a03e  add     rsp, 30h
0x18000a042  pop     rbx
0x18000a043  retn
```
