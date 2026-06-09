# RassrvRegGetDwEx

- ea: `0x180021720`
- end: `0x1800217e8`
- name: `RassrvRegGetDwEx`
- size: `200`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180026f44`
- `0x180027698`
- `0x1800277d0`
- `0x1800283bc`
- `0x180028460`
- `0x1800286e8`
- `0x180029b5c`
- `0x180029c5c`
- `0x180029f24`

## callees

- `0x180021720`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800217cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800217cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021780`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021780`
- `KERNEL32!RegQueryValueExW` at `0x1800217ac`
- `KERNEL32!RegQueryValueExW` at `0x1800217ac`

## pseudocode

```c
__int64 __fastcall RassrvRegGetDwEx(_DWORD *a1, int a2, const WCHAR *a3, const WCHAR *a4, int Data)
{
  unsigned int v9; // ebx
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF

  Data = 0;
  hKey = 0;
  Type = 4;
  cbData = 4;
  if ( !a1 )
    return 87;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, &hKey);
  if ( !v9 )
  {
    v9 = RegQueryValueExW(hKey, a4, 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v9 )
    {
      v9 = 0;
      Data = a2;
    }
    else
    {
      a2 = Data;
    }
    *a1 = a2;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180021720  mov     [rsp-18h+arg_8], rbx
0x180021725  mov     [rsp-18h+arg_10], rsi
0x18002172a  push    rbp
0x18002172b  push    rdi
0x18002172c  push    r14
0x18002172e  mov     rbp, rsp
0x180021731  sub     rsp, 40h
0x180021735  mov     rsi, rcx
0x180021738  mov     [rbp+Data], 0
0x18002173f  mov     [rbp+hKey], 0
0x180021747  mov     ecx, 4
0x18002174c  mov     [rbp+Type], ecx
0x18002174f  mov     r14, r9
0x180021752  mov     [rbp+cbData], ecx
0x180021755  mov     rax, r8
0x180021758  mov     edi, edx
0x18002175a  test    rsi, rsi
0x18002175d  jnz     short loc_180021764
0x18002175f  lea     eax, [rcx+53h]
0x180021762  jmp     short loc_1800217D5
0x180021764  lea     rcx, [rbp+hKey]
0x180021768  mov     r9d, 20019h; samDesired
0x18002176e  mov     [rsp+40h+phkResult], rcx; phkResult
0x180021773  xor     r8d, r8d; ulOptions
0x180021776  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002177d  mov     rdx, rax; lpSubKey
0x180021780  call    cs:__imp_RegOpenKeyExW
0x180021786  mov     ebx, eax
0x180021788  test    eax, eax
0x18002178a  jnz     short loc_1800217C4
0x18002178c  mov     rcx, [rbp+hKey]; hKey
0x180021790  lea     rax, [rbp+cbData]
0x180021794  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180021799  lea     r9, [rbp+Type]; lpType
0x18002179d  lea     rax, [rbp+Data]
0x1800217a1  xor     r8d, r8d; lpReserved
0x1800217a4  mov     rdx, r14; lpValueName
0x1800217a7  mov     [rsp+40h+phkResult], rax; lpData
0x1800217ac  call    cs:__imp_RegQueryValueExW
0x1800217b2  mov     ebx, eax
0x1800217b4  test    eax, eax
0x1800217b6  jz      short loc_1800217BF
0x1800217b8  xor     ebx, ebx
0x1800217ba  mov     [rbp+Data], edi
0x1800217bd  jmp     short loc_1800217C2
0x1800217bf  mov     edi, [rbp+Data]
0x1800217c2  mov     [rsi], edi
0x1800217c4  mov     rcx, [rbp+hKey]; hKey
0x1800217c8  test    rcx, rcx
0x1800217cb  jz      short loc_1800217D3
0x1800217cd  call    cs:__imp_RegCloseKey
0x1800217d3  mov     eax, ebx
0x1800217d5  mov     rbx, [rsp+40h+arg_8]
0x1800217da  mov     rsi, [rsp+40h+arg_10]
0x1800217df  add     rsp, 40h
0x1800217e3  pop     r14
0x1800217e5  pop     rdi
0x1800217e6  pop     rbp
0x1800217e7  retn
```
