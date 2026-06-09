# ReadRegDword(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x180026aa0`
- end: `0x180026b4e`
- name: `?ReadRegDword@@YAKPEAUHKEY__@@PEBG1K@Z`
- size: `174`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180026aa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026ae3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026ae3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026b13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026b13`

## pseudocode

```c
__int64 __fastcall ReadRegDword(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, unsigned int a4)
{
  BYTE Data[4]; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData[3]; // [rsp+34h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+50h] [rbp+10h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF

  hKey = a1;
  *(_DWORD *)Data = 0;
  cbData[0] = 4;
  Type = 0;
  if ( !RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, a3, 0, &Type, Data, cbData) && Type == 4 )
      a4 = *(_DWORD *)Data;
    RegCloseKey(hKey);
  }
  return a4;
}

```

## disassembly

```asm
0x180026aa0  mov     r11, rsp
0x180026aa3  mov     [r11+10h], rbx
0x180026aa7  mov     [r11+18h], rdi
0x180026aab  mov     [r11+8], rcx
0x180026aaf  push    rbp
0x180026ab0  mov     rbp, rsp
0x180026ab3  sub     rsp, 40h
0x180026ab7  mov     ebx, r9d
0x180026aba  mov     dword ptr [rbp+Data], 0
0x180026ac1  mov     rdi, r8
0x180026ac4  mov     [rbp+cbData], 4
0x180026acb  lea     rax, [rbp+hKey]
0x180026acf  mov     [rbp+Type], 0
0x180026ad6  mov     r9d, 20019h; samDesired
0x180026adc  mov     [r11-28h], rax
0x180026ae0  xor     r8d, r8d; ulOptions
0x180026ae3  call    cs:__imp_RegOpenKeyExW
0x180026aea  nop     dword ptr [rax+rax+00h]
0x180026aef  test    eax, eax
0x180026af1  jnz     short loc_180026B3B
0x180026af3  mov     rcx, [rbp+hKey]; hKey
0x180026af7  lea     rax, [rbp+cbData]
0x180026afb  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180026b00  lea     r9, [rbp+Type]; lpType
0x180026b04  lea     rax, [rbp+Data]
0x180026b08  xor     r8d, r8d; lpReserved
0x180026b0b  mov     rdx, rdi; lpValueName
0x180026b0e  mov     [rsp+40h+lpData], rax; lpData
0x180026b13  call    cs:__imp_RegQueryValueExW
0x180026b1a  nop     dword ptr [rax+rax+00h]
0x180026b1f  test    eax, eax
0x180026b21  jnz     short loc_180026B2B
0x180026b23  cmp     [rbp+Type], 4
0x180026b27  cmovz   ebx, dword ptr [rbp+Data]
0x180026b2b  mov     rcx, [rbp+hKey]; hKey
0x180026b2f  call    cs:__imp_RegCloseKey
0x180026b36  nop     dword ptr [rax+rax+00h]
0x180026b3b  mov     rdi, [rsp+40h+arg_10]
0x180026b40  mov     eax, ebx
0x180026b42  mov     rbx, [rsp+40h+arg_8]
0x180026b47  add     rsp, 40h
0x180026b4b  pop     rbp
0x180026b4c  retn
```
