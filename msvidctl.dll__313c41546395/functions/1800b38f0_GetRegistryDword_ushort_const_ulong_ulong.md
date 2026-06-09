# GetRegistryDword(ushort const *,ulong *,ulong)

- ea: `0x1800b38f0`
- end: `0x1800b399d`
- name: `?GetRegistryDword@@YAHPEBGPEAKK@Z`
- size: `173`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, LPBYTE lpData, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b2fe0`
- `0x1800b3270`

## callees

- `0x1800b38f0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800b3968`
- `ADVAPI32!RegQueryValueExW` at `0x1800b3968`
- `ADVAPI32!RegOpenKeyExW` at `0x1800b3931`
- `ADVAPI32!RegOpenKeyExW` at `0x1800b3931`
- `ADVAPI32!RegCloseKey` at `0x1800b3979`
- `ADVAPI32!RegCloseKey` at `0x1800b3983`
- `ADVAPI32!RegCloseKey` at `0x1800b3979`
- `ADVAPI32!RegCloseKey` at `0x1800b3983`

## pseudocode

```c
_BOOL8 __fastcall GetRegistryDword(LPCWSTR lpValueName, LPBYTE lpData, int a3)
{
  LSTATUS v6; // esi
  LSTATUS v7; // eax
  HKEY v8; // rcx
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  *(_DWORD *)lpData = a3;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Multimedia\\DVD", 0, 1u, &hKey);
  if ( !v6 )
  {
    Type = 0;
    cbData = 4;
    v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
    v8 = hKey;
    if ( v7 )
    {
      *(_DWORD *)lpData = a3;
      RegCloseKey(v8);
      return 0;
    }
    RegCloseKey(hKey);
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x1800b38f0  mov     r11, rsp
0x1800b38f3  mov     [r11+8], rbx
0x1800b38f7  push    rbp
0x1800b38f8  push    rsi
0x1800b38f9  push    rdi
0x1800b38fa  sub     rsp, 30h
0x1800b38fe  mov     [rdx], r8d
0x1800b3901  lea     rax, [r11+20h]
0x1800b3905  mov     edi, r8d
0x1800b3908  mov     [r11-28h], rax
0x1800b390c  mov     rbx, rdx
0x1800b390f  mov     qword ptr [r11+20h], 0
0x1800b3917  mov     rbp, rcx
0x1800b391a  lea     rdx, SubKey; "Software\\Microsoft\\Multimedia\\DVD"
0x1800b3921  xor     r8d, r8d; ulOptions
0x1800b3924  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b392b  mov     r9d, 1; samDesired
0x1800b3931  call    cs:__imp_RegOpenKeyExW
0x1800b3937  mov     esi, eax
0x1800b3939  test    eax, eax
0x1800b393b  jnz     short loc_1800B3989
0x1800b393d  mov     rcx, [rsp+48h+hKey]; hKey
0x1800b3942  lea     r9, [rsp+48h+Type]; lpType
0x1800b3947  mov     [rsp+48h+Type], eax
0x1800b394b  xor     r8d, r8d; lpReserved
0x1800b394e  lea     rax, [rsp+48h+cbData]
0x1800b3953  mov     [rsp+48h+cbData], 4
0x1800b395b  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800b3960  mov     rdx, rbp; lpValueName
0x1800b3963  mov     [rsp+48h+lpData], rbx; lpData
0x1800b3968  call    cs:__imp_RegQueryValueExW
0x1800b396e  mov     rcx, [rsp+48h+hKey]; hKey
0x1800b3973  test    eax, eax
0x1800b3975  jz      short loc_1800B3983
0x1800b3977  mov     [rbx], edi
0x1800b3979  call    cs:__imp_RegCloseKey
0x1800b397f  xor     eax, eax
0x1800b3981  jmp     short loc_1800B3990
0x1800b3983  call    cs:__imp_RegCloseKey
0x1800b3989  xor     eax, eax
0x1800b398b  test    esi, esi
0x1800b398d  setz    al
0x1800b3990  mov     rbx, [rsp+48h+arg_0]
0x1800b3995  add     rsp, 30h
0x1800b3999  pop     rdi
0x1800b399a  pop     rsi
0x1800b399b  pop     rbp
0x1800b399c  retn
```
