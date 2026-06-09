# PuLoadDebugFlagsFromRegStr

- ea: `0x180014ab0`
- end: `0x180014b09`
- name: `PuLoadDebugFlagsFromRegStr`
- size: `89`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180014ab0`
- `0x18001f280`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180014ade`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180014ade`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014afb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014afb`

## pseudocode

```c
__int64 __fastcall PuLoadDebugFlagsFromRegStr(LPCSTR lpSubKey, unsigned int DebugFlagsFromReg)
{
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
  {
    DebugFlagsFromReg = PuLoadDebugFlagsFromReg(hKey, DebugFlagsFromReg);
    RegCloseKey(hKey);
  }
  return DebugFlagsFromReg;
}

```

## disassembly

```asm
0x180014ab0  push    rbx
0x180014ab2  sub     rsp, 30h
0x180014ab6  mov     ebx, edx
0x180014ab8  mov     [rsp+38h+hKey], 0
0x180014ac1  mov     rdx, rcx; lpSubKey
0x180014ac4  lea     rax, [rsp+38h+hKey]
0x180014ac9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014ad0  mov     [rsp+38h+phkResult], rax; phkResult
0x180014ad5  mov     r9d, 20019h; samDesired
0x180014adb  xor     r8d, r8d; ulOptions
0x180014ade  call    cs:__imp_RegOpenKeyExA
0x180014ae4  test    eax, eax
0x180014ae6  jnz     short loc_180014B01
0x180014ae8  mov     rcx, [rsp+38h+hKey]
0x180014aed  mov     edx, ebx
0x180014aef  call    PuLoadDebugFlagsFromReg
0x180014af4  mov     rcx, [rsp+38h+hKey]; hKey
0x180014af9  mov     ebx, eax
0x180014afb  call    cs:__imp_RegCloseKey
0x180014b01  mov     eax, ebx
0x180014b03  add     rsp, 30h
0x180014b07  pop     rbx
0x180014b08  retn
```
