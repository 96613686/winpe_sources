# GetConfigParamLocalWEx

- ea: `0x180022ebc`
- end: `0x180022f85`
- name: `GetConfigParamLocalWEx`
- size: `201`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, LPBYTE lpData, DWORD, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180022f8c`
- `0x180023f6c`
- `0x180025100`

## callees

- `0x180022ebc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022f2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022f2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180022f03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180022f03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022f69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022f69`

## string_xrefs

- `0x180022ef5`: `System\CurrentControlSet\Services\NTDS\Parameters`

## pseudocode

```c
__int64 __fastcall GetConfigParamLocalWEx(LPCWSTR lpValueName, LPBYTE lpData, DWORD a3, __int64 a4)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF
  int v12; // [rsp+6Ch] [rbp+24h]

  v12 = HIDWORD(a4);
  cbData = a3;
  Type = 0;
  hKey = 0;
  v6 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\NTDS\\Parameters", 0, 0x2000000u, &hKey);
  if ( v6 )
  {
    return v6;
  }
  else
  {
    v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
    if ( !v7
      && (Type - 1 <= 1 || Type == 7)
      && cbData >= 2
      && *(_WORD *)&lpData[2 * ((unsigned __int64)cbData >> 1) - 2] )
    {
      v7 = 13;
    }
    RegCloseKey(hKey);
  }
  return v7;
}

```

## disassembly

```asm
0x180022ebc  mov     rax, rsp
0x180022ebf  mov     [rax+8], rbx
0x180022ec3  mov     [rax+10h], rsi
0x180022ec7  mov     [rax+20h], r9
0x180022ecb  mov     [rax+18h], r8d
0x180022ecf  push    rdi
0x180022ed0  sub     rsp, 40h
0x180022ed4  xor     esi, esi
0x180022ed6  mov     rdi, rdx
0x180022ed9  mov     [rax+20h], esi
0x180022edc  mov     rbx, rcx
0x180022edf  mov     [rax-18h], rsi
0x180022ee3  lea     rax, [rax-18h]
0x180022ee7  mov     r9d, 2000000h; samDesired
0x180022eed  mov     [rsp+48h+phkResult], rax; phkResult
0x180022ef2  xor     r8d, r8d; ulOptions
0x180022ef5  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\NT"...
0x180022efc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022f03  call    cs:__imp_RegOpenKeyExA
0x180022f09  test    eax, eax
0x180022f0b  jnz     short loc_180022F71
0x180022f0d  mov     rcx, [rsp+48h+hKey]; hKey
0x180022f12  lea     rax, [rsp+48h+cbData]
0x180022f17  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180022f1c  lea     r9, [rsp+48h+Type]; lpType
0x180022f21  xor     r8d, r8d; lpReserved
0x180022f24  mov     [rsp+48h+phkResult], rdi; lpData
0x180022f29  mov     rdx, rbx; lpValueName
0x180022f2c  call    cs:__imp_RegQueryValueExW
0x180022f32  mov     ebx, eax
0x180022f34  test    eax, eax
0x180022f36  jnz     short loc_180022F64
0x180022f38  mov     eax, [rsp+48h+Type]
0x180022f3c  lea     ecx, [rax-1]
0x180022f3f  cmp     ecx, 1
0x180022f42  jbe     short loc_180022F49
0x180022f44  cmp     eax, 7
0x180022f47  jnz     short loc_180022F64
0x180022f49  cmp     [rsp+48h+cbData], 2
0x180022f4e  jb      short loc_180022F64
0x180022f50  mov     eax, [rsp+48h+cbData]
0x180022f54  mov     ecx, 0Dh
0x180022f59  shr     rax, 1
0x180022f5c  cmp     [rdi+rax*2-2], si
0x180022f61  cmovnz  ebx, ecx
0x180022f64  mov     rcx, [rsp+48h+hKey]; hKey
0x180022f69  call    cs:__imp_RegCloseKey
0x180022f6f  jmp     short loc_180022F73
0x180022f71  mov     ebx, eax
0x180022f73  mov     rsi, [rsp+48h+arg_8]
0x180022f78  mov     eax, ebx
0x180022f7a  mov     rbx, [rsp+48h+arg_0]
0x180022f7f  add     rsp, 40h
0x180022f83  pop     rdi
0x180022f84  retn
```
