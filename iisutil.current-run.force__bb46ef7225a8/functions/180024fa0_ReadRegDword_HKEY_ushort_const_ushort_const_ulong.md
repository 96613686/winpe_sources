# ReadRegDword(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x180024fa0`
- end: `0x18002503b`
- name: `?ReadRegDword@@YAKPEAUHKEY__@@PEBG1K@Z`
- size: `155`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180024fa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024fe3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024fe3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025023`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025023`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002500d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002500d`

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
0x180024fa0  mov     r11, rsp
0x180024fa3  mov     [r11+10h], rbx
0x180024fa7  mov     [r11+18h], rdi
0x180024fab  mov     [r11+8], rcx
0x180024faf  push    rbp
0x180024fb0  mov     rbp, rsp
0x180024fb3  sub     rsp, 40h
0x180024fb7  mov     ebx, r9d
0x180024fba  mov     dword ptr [rbp+Data], 0
0x180024fc1  mov     rdi, r8
0x180024fc4  mov     [rbp+cbData], 4
0x180024fcb  lea     rax, [rbp+hKey]
0x180024fcf  mov     [rbp+Type], 0
0x180024fd6  mov     r9d, 20019h; samDesired
0x180024fdc  mov     [r11-28h], rax
0x180024fe0  xor     r8d, r8d; ulOptions
0x180024fe3  call    cs:__imp_RegOpenKeyExW
0x180024fe9  test    eax, eax
0x180024feb  jnz     short loc_180025029
0x180024fed  mov     rcx, [rbp+hKey]; hKey
0x180024ff1  lea     rax, [rbp+cbData]
0x180024ff5  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180024ffa  lea     r9, [rbp+Type]; lpType
0x180024ffe  lea     rax, [rbp+Data]
0x180025002  xor     r8d, r8d; lpReserved
0x180025005  mov     rdx, rdi; lpValueName
0x180025008  mov     [rsp+40h+lpData], rax; lpData
0x18002500d  call    cs:__imp_RegQueryValueExW
0x180025013  test    eax, eax
0x180025015  jnz     short loc_18002501F
0x180025017  cmp     [rbp+Type], 4
0x18002501b  cmovz   ebx, dword ptr [rbp+Data]
0x18002501f  mov     rcx, [rbp+hKey]; hKey
0x180025023  call    cs:__imp_RegCloseKey
0x180025029  mov     rdi, [rsp+40h+arg_10]
0x18002502e  mov     eax, ebx
0x180025030  mov     rbx, [rsp+40h+arg_8]
0x180025035  add     rsp, 40h
0x180025039  pop     rbp
0x18002503a  retn
```
