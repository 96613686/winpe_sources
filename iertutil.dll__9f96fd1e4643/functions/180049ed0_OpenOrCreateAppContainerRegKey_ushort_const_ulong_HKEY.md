# OpenOrCreateAppContainerRegKey(ushort const *,ulong,HKEY__ * *)

- ea: `0x180049ed0`
- end: `0x180049f5f`
- name: `?OpenOrCreateAppContainerRegKey@@YAJPEBGKPEAPEAUHKEY__@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180054c50`

## callees

- `0x180049ed0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049f4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049f4e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180049f31`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180049f31`
- `USERENV!GetAppContainerRegistryLocation` at `0x180049ef1`
- `USERENV!GetAppContainerRegistryLocation` at `0x180049ef1`

## pseudocode

```c
__int64 __fastcall OpenOrCreateAppContainerRegKey(LPCWSTR lpSubKey, REGSAM samDesired, PHKEY phkResult)
{
  signed int AppContainerRegistryLocation; // ebx
  LSTATUS Key; // eax
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF

  hKey = 0;
  AppContainerRegistryLocation = GetAppContainerRegistryLocation(samDesired, &hKey);
  if ( AppContainerRegistryLocation >= 0 )
  {
    Key = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, samDesired, 0, phkResult, 0);
    AppContainerRegistryLocation = Key;
    if ( Key > 0 )
      AppContainerRegistryLocation = (unsigned __int16)Key | 0x80070000;
    RegCloseKey(hKey);
  }
  return (unsigned int)AppContainerRegistryLocation;
}

```

## disassembly

```asm
0x180049ed0  mov     rax, rsp
0x180049ed3  push    rbx
0x180049ed4  push    rbp
0x180049ed5  push    rsi
0x180049ed6  push    rdi
0x180049ed7  sub     rsp, 58h
0x180049edb  mov     edi, edx
0x180049edd  mov     qword ptr [rax+20h], 0
0x180049ee5  mov     rbp, rcx
0x180049ee8  lea     rdx, [rax+20h]
0x180049eec  mov     ecx, edi
0x180049eee  mov     rsi, r8
0x180049ef1  call    cs:__imp_GetAppContainerRegistryLocation
0x180049ef7  mov     ebx, eax
0x180049ef9  test    eax, eax
0x180049efb  js      short loc_180049F54
0x180049efd  mov     rcx, [rsp+78h+hKey]; hKey
0x180049f05  xor     r9d, r9d; lpClass
0x180049f08  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180049f11  xor     r8d, r8d; Reserved
0x180049f14  mov     [rsp+78h+phkResult], rsi; phkResult
0x180049f19  mov     rdx, rbp; lpSubKey
0x180049f1c  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180049f25  mov     [rsp+78h+samDesired], edi; samDesired
0x180049f29  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180049f31  call    cs:__imp_RegCreateKeyExW
0x180049f37  mov     ebx, eax
0x180049f39  test    eax, eax
0x180049f3b  jle     short loc_180049F46
0x180049f3d  movzx   ebx, ax
0x180049f40  or      ebx, 80070000h
0x180049f46  mov     rcx, [rsp+78h+hKey]; hKey
0x180049f4e  call    cs:__imp_RegCloseKey
0x180049f54  mov     eax, ebx
0x180049f56  add     rsp, 58h
0x180049f5a  pop     rdi
0x180049f5b  pop     rsi
0x180049f5c  pop     rbp
0x180049f5d  pop     rbx
0x180049f5e  retn
```
