# OpenProviderParametersKey

- ea: `0x18003439c`
- end: `0x180034429`
- name: `OpenProviderParametersKey`
- size: `141`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180030cdc`
- `0x180031918`
- `0x1800326d0`

## callees

- `0x18003439c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003440f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003440f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800343cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800343f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800343cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800343f7`

## pseudocode

```c
__int64 __fastcall OpenProviderParametersKey(HKEY a1, const WCHAR *a2, HKEY *a3)
{
  unsigned int v4; // ebx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  hKey = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  if ( !v4 )
    v4 = RegOpenKeyExW(hKey, L"Parameters\\WinSock", 0, 0x20019u, a3);
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x18003439c  mov     r11, rsp
0x18003439f  mov     [r11+8], rbx
0x1800343a3  push    rdi
0x1800343a4  sub     rsp, 30h
0x1800343a8  mov     rdi, r8
0x1800343ab  mov     qword ptr [r8], 0
0x1800343b2  lea     rax, [r11+18h]
0x1800343b6  mov     qword ptr [r11+18h], 0
0x1800343be  xor     r8d, r8d; ulOptions
0x1800343c1  mov     [r11-18h], rax
0x1800343c5  mov     r9d, 20019h; samDesired
0x1800343cb  call    cs:__imp_RegOpenKeyExW
0x1800343d2  nop     dword ptr [rax+rax+00h]
0x1800343d7  mov     ebx, eax
0x1800343d9  test    eax, eax
0x1800343db  jnz     short loc_180034405
0x1800343dd  mov     rcx, [rsp+38h+hKey]; hKey
0x1800343e2  lea     rdx, aParametersWins_0; "Parameters\\WinSock"
0x1800343e9  mov     r9d, 20019h; samDesired
0x1800343ef  mov     [rsp+38h+phkResult], rdi; phkResult
0x1800343f4  xor     r8d, r8d; ulOptions
0x1800343f7  call    cs:__imp_RegOpenKeyExW
0x1800343fe  nop     dword ptr [rax+rax+00h]
0x180034403  mov     ebx, eax
0x180034405  mov     rcx, [rsp+38h+hKey]; hKey
0x18003440a  test    rcx, rcx
0x18003440d  jz      short loc_18003441B
0x18003440f  call    cs:__imp_RegCloseKey
0x180034416  nop     dword ptr [rax+rax+00h]
0x18003441b  mov     eax, ebx
0x18003441d  mov     rbx, [rsp+38h+arg_0]
0x180034422  add     rsp, 30h
0x180034426  pop     rdi
0x180034427  retn
```
