# ClearIsMeteredDetectedOption

- ea: `0x180010a80`
- end: `0x180010b13`
- name: `ClearIsMeteredDetectedOption`
- size: `147`
- prototype: `LSTATUS __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001e870`

## callees

- `0x180010a80`
- `0x18004d1a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010adf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010adf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010ab5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010ab5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180010acd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180010acd`

## pseudocode

```c
LSTATUS __fastcall ClearIsMeteredDetectedOption(__int64 a1)
{
  HKEY v1; // rcx
  LSTATUS result; // eax
  unsigned int v3; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  *(_DWORD *)(a1 + 580) = 0;
  v1 = *(HKEY *)(a1 + 728);
  hKey = 0;
  result = RegOpenKeyExW(v1, 0, 0, 0xFu, &hKey);
  v3 = result;
  if ( !result )
  {
    result = RegDeleteValueW(hKey, L"DhcpIsMeteredDetected");
    v3 = result;
  }
  if ( hKey )
    result = RegCloseKey(hKey);
  if ( v3 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      return WPP_SF_D(1025, 248, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180010a80  push    rbx
0x180010a82  sub     rsp, 30h
0x180010a86  mov     dword ptr [rcx+244h], 0
0x180010a90  lea     rax, [rsp+38h+hKey]
0x180010a95  mov     rcx, [rcx+2D8h]; hKey
0x180010a9c  mov     r9d, 0Fh; samDesired
0x180010aa2  xor     r8d, r8d; ulOptions
0x180010aa5  mov     [rsp+38h+phkResult], rax; phkResult
0x180010aaa  xor     edx, edx; lpSubKey
0x180010aac  mov     [rsp+38h+hKey], 0
0x180010ab5  call    cs:__imp_RegOpenKeyExW
0x180010abb  mov     ebx, eax
0x180010abd  test    eax, eax
0x180010abf  jnz     short loc_180010AD5
0x180010ac1  mov     rcx, [rsp+38h+hKey]; hKey
0x180010ac6  lea     rdx, aDhcpismeteredd; "DhcpIsMeteredDetected"
0x180010acd  call    cs:__imp_RegDeleteValueW
0x180010ad3  mov     ebx, eax
0x180010ad5  mov     rcx, [rsp+38h+hKey]; hKey
0x180010ada  test    rcx, rcx
0x180010add  jz      short loc_180010AE5
0x180010adf  call    cs:__imp_RegCloseKey
0x180010ae5  test    ebx, ebx
0x180010ae7  jnz     short loc_180010AEF
0x180010ae9  add     rsp, 30h
0x180010aed  pop     rbx
0x180010aee  retn
0x180010aef  test    byte ptr cs:xmmword_1800616A0, 2
0x180010af6  jz      short loc_180010AE9
0x180010af8  mov     edx, 0F8h
0x180010afd  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x180010b04  mov     ecx, 401h
0x180010b09  mov     r9d, ebx
0x180010b0c  call    WPP_SF_D
0x180010b11  jmp     short loc_180010AE9
```
