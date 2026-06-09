# AccessRegistryInt(ushort const *,ushort const *,int)

- ea: `0x180009940`
- end: `0x1800099d7`
- name: `?AccessRegistryInt@@YAHPEBG0H@Z`
- size: `151`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, int)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008330`
- `0x180009724`
- `0x180009848`
- `0x18001649c`
- `0x1800166c0`
- `0x1800300ac`
- `0x180040418`
- `0x180060600`

## callees

- `0x180009940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800099c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800099c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009984`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009984`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800099b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800099b2`

## pseudocode

```c
__int64 __fastcall AccessRegistryInt(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int a3)
{
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF

  cbData = 4;
  Data = 0;
  Type = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData) )
      a3 = Data;
    RegCloseKey(hKey);
  }
  return a3;
}

```

## disassembly

```asm
0x180009940  mov     [rsp+arg_0], rbx
0x180009945  push    rdi
0x180009946  sub     rsp, 40h
0x18000994a  xor     eax, eax
0x18000994c  mov     [rsp+48h+cbData], 4
0x180009954  mov     [rsp+48h+Data], eax
0x180009958  mov     rdi, rdx
0x18000995b  mov     [rsp+48h+Type], eax
0x18000995f  mov     ebx, r8d
0x180009962  mov     [rsp+48h+hKey], rax
0x180009967  mov     rdx, rcx; lpSubKey
0x18000996a  lea     rax, [rsp+48h+hKey]
0x18000996f  mov     r9d, 20019h; samDesired
0x180009975  xor     r8d, r8d; ulOptions
0x180009978  mov     [rsp+48h+phkResult], rax; phkResult
0x18000997d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009984  call    cs:__imp_RegOpenKeyExW
0x18000998a  test    eax, eax
0x18000998c  jnz     short loc_1800099CA
0x18000998e  mov     rcx, [rsp+48h+hKey]; hKey
0x180009993  lea     rax, [rsp+48h+cbData]
0x180009998  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000999d  lea     r9, [rsp+48h+Type]; lpType
0x1800099a2  lea     rax, [rsp+48h+Data]
0x1800099a7  xor     r8d, r8d; lpReserved
0x1800099aa  mov     rdx, rdi; lpValueName
0x1800099ad  mov     [rsp+48h+phkResult], rax; lpData
0x1800099b2  call    cs:__imp_RegQueryValueExW
0x1800099b8  mov     rcx, [rsp+48h+hKey]; hKey
0x1800099bd  test    eax, eax
0x1800099bf  cmovz   ebx, [rsp+48h+Data]
0x1800099c4  call    cs:__imp_RegCloseKey
0x1800099ca  mov     eax, ebx
0x1800099cc  mov     rbx, [rsp+48h+arg_0]
0x1800099d1  add     rsp, 40h
0x1800099d5  pop     rdi
0x1800099d6  retn
```
