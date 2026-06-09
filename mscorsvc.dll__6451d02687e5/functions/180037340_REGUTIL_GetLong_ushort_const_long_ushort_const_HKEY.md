# REGUTIL::GetLong(ushort const *,long,ushort const *,HKEY__ *)

- ea: `0x180037340`
- end: `0x1800373de`
- name: `?GetLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, int, const unsigned __int16 *, HKEY)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800039ac`
- `0x1800046c4`
- `0x180004cac`
- `0x1800050b4`
- `0x180016794`
- `0x18001b1e4`
- `0x18001b57c`

## callees

- `0x180037340`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800373ce`
- `ADVAPI32!RegCloseKey` at `0x1800373ce`
- `ADVAPI32!RegQueryValueExW` at `0x1800373b3`
- `ADVAPI32!RegQueryValueExW` at `0x1800373b3`
- `ADVAPI32!RegOpenKeyExW` at `0x180037371`
- `ADVAPI32!RegOpenKeyExW` at `0x180037371`

## pseudocode

```c
__int64 __fastcall REGUTIL::GetLong(LPCWSTR lpValueName, DWORD a2, const unsigned __int16 *a3, HKEY a4)
{
  DWORD cbData; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF
  const unsigned __int16 *Data; // [rsp+60h] [rbp+18h] BYREF

  Data = a3;
  Type = a2;
  if ( RegOpenKeyExW(a4, &psz, 0, 0x20019u, &hKey) )
    return 0;
  Type = 4;
  cbData = 4;
  if ( RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
    LODWORD(Data) = 0;
  RegCloseKey(hKey);
  return (unsigned int)Data;
}

```

## disassembly

```asm
0x180037340  mov     [rsp+Data], r8
0x180037345  mov     [rsp+Type], edx
0x180037349  push    rbx
0x18003734a  sub     rsp, 40h
0x18003734e  mov     rbx, rcx
0x180037351  lea     rdx, psz; lpSubKey
0x180037358  mov     rax, r9
0x18003735b  lea     rcx, [rsp+48h+hKey]
0x180037360  mov     [rsp+48h+phkResult], rcx; phkResult
0x180037365  mov     r9d, 20019h; samDesired
0x18003736b  mov     rcx, rax; hKey
0x18003736e  xor     r8d, r8d; ulOptions
0x180037371  call    cs:__imp_RegOpenKeyExW
0x180037377  test    eax, eax
0x180037379  jz      short loc_18003737F
0x18003737b  xor     eax, eax
0x18003737d  jmp     short loc_1800373D8
0x18003737f  mov     rcx, [rsp+48h+hKey]; hKey
0x180037384  lea     rax, [rsp+48h+cbData]
0x180037389  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18003738e  lea     r9, [rsp+48h+Type]; lpType
0x180037393  lea     rax, [rsp+48h+Data]
0x180037398  mov     [rsp+48h+Type], 4
0x1800373a0  xor     r8d, r8d; lpReserved
0x1800373a3  mov     [rsp+48h+phkResult], rax; lpData
0x1800373a8  mov     rdx, rbx; lpValueName
0x1800373ab  mov     [rsp+48h+cbData], 4
0x1800373b3  call    cs:__imp_RegQueryValueExW
0x1800373b9  test    eax, eax
0x1800373bb  jnz     short loc_1800373C4
0x1800373bd  cmp     [rsp+48h+Type], 4
0x1800373c2  jz      short loc_1800373C9
0x1800373c4  and     dword ptr [rsp+48h+Data], 0
0x1800373c9  mov     rcx, [rsp+48h+hKey]; hKey
0x1800373ce  call    cs:__imp_RegCloseKey
0x1800373d4  mov     eax, dword ptr [rsp+48h+Data]
0x1800373d8  add     rsp, 40h
0x1800373dc  pop     rbx
0x1800373dd  retn
```
