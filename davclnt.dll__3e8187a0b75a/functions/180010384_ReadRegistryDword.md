# ReadRegistryDword

- ea: `0x180010384`
- end: `0x18001041b`
- name: `ReadRegistryDword`
- size: `151`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, LPBYTE lpData, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010424`
- `0x18001068c`

## callees

- `0x180010384`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800103c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800103c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010403`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010403`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800103f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800103f3`

## pseudocode

```c
__int64 __fastcall ReadRegistryDword(LPCWSTR lpValueName, LPBYTE lpData, LPCWSTR lpSubKey)
{
  unsigned int v5; // ebx
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF

  v5 = 0;
  hKey = 0;
  Type = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    LOBYTE(v5) = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData) == 0;
    RegCloseKey(hKey);
  }
  return v5;
}

```

## disassembly

```asm
0x180010384  mov     r11, rsp
0x180010387  mov     [r11+8], rbx
0x18001038b  mov     [r11+10h], rsi
0x18001038f  push    rdi
0x180010390  sub     rsp, 40h
0x180010394  mov     rsi, rcx
0x180010397  mov     rax, r8
0x18001039a  lea     rcx, [r11-10h]
0x18001039e  mov     rdi, rdx
0x1800103a1  mov     [r11-28h], rcx
0x1800103a5  xor     ebx, ebx
0x1800103a7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800103ae  mov     [r11-10h], rbx
0x1800103b2  mov     r9d, 20019h; samDesired
0x1800103b8  mov     [rsp+48h+Type], ebx
0x1800103bc  xor     r8d, r8d; ulOptions
0x1800103bf  mov     rdx, rax; lpSubKey
0x1800103c2  call    cs:__imp_RegOpenKeyExW
0x1800103c8  test    eax, eax
0x1800103ca  jnz     short loc_180010409
0x1800103cc  mov     rcx, [rsp+48h+hKey]; hKey
0x1800103d1  lea     rax, [rsp+48h+cbData]
0x1800103d6  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800103db  lea     r9, [rsp+48h+Type]; lpType
0x1800103e0  xor     r8d, r8d; lpReserved
0x1800103e3  mov     [rsp+48h+lpData], rdi; lpData
0x1800103e8  mov     rdx, rsi; lpValueName
0x1800103eb  mov     [rsp+48h+cbData], 4
0x1800103f3  call    cs:__imp_RegQueryValueExW
0x1800103f9  mov     rcx, [rsp+48h+hKey]; hKey
0x1800103fe  test    eax, eax
0x180010400  setz    bl
0x180010403  call    cs:__imp_RegCloseKey
0x180010409  mov     rsi, [rsp+48h+arg_8]
0x18001040e  mov     eax, ebx
0x180010410  mov     rbx, [rsp+48h+arg_0]
0x180010415  add     rsp, 40h
0x180010419  pop     rdi
0x18001041a  retn
```
