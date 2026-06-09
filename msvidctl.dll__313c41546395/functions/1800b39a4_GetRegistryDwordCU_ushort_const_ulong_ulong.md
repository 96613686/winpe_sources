# GetRegistryDwordCU(ushort const *,ulong *,ulong)

- ea: `0x1800b39a4`
- end: `0x1800b3a50`
- name: `?GetRegistryDwordCU@@YAHPEBGPEAKK@Z`
- size: `172`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, LPBYTE lpData, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b40e0`
- `0x1800b4110`
- `0x1800b4140`

## callees

- `0x1800b39a4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800b3a1c`
- `ADVAPI32!RegQueryValueExW` at `0x1800b3a1c`
- `ADVAPI32!RegOpenKeyExW` at `0x1800b39e5`
- `ADVAPI32!RegOpenKeyExW` at `0x1800b39e5`
- `ADVAPI32!RegCloseKey` at `0x1800b3a31`
- `ADVAPI32!RegCloseKey` at `0x1800b3a3b`
- `ADVAPI32!RegCloseKey` at `0x1800b3a31`
- `ADVAPI32!RegCloseKey` at `0x1800b3a3b`

## pseudocode

```c
_BOOL8 __fastcall GetRegistryDwordCU(LPCWSTR lpValueName, LPBYTE lpData, DWORD a3)
{
  LSTATUS v5; // edi
  LSTATUS v6; // eax
  HKEY v7; // rcx
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  cbData = a3;
  *(_DWORD *)lpData = -1;
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Multimedia\\DVD", 0, 1u, &hKey);
  if ( !v5 )
  {
    Type = 0;
    cbData = 4;
    v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
    v7 = hKey;
    if ( v6 )
    {
      *(_DWORD *)lpData = -1;
      RegCloseKey(v7);
      return 0;
    }
    RegCloseKey(hKey);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x1800b39a4  mov     r11, rsp
0x1800b39a7  mov     [r11+18h], r8d
0x1800b39ab  push    rbx
0x1800b39ac  push    rsi
0x1800b39ad  push    rdi
0x1800b39ae  sub     rsp, 30h
0x1800b39b2  mov     rbx, rdx
0x1800b39b5  mov     dword ptr [rdx], 0FFFFFFFFh
0x1800b39bb  mov     rsi, rcx
0x1800b39be  mov     qword ptr [r11+20h], 0
0x1800b39c6  lea     rax, [r11+20h]
0x1800b39ca  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800b39d1  lea     rdx, SubKey; "Software\\Microsoft\\Multimedia\\DVD"
0x1800b39d8  mov     [r11-28h], rax
0x1800b39dc  mov     r9d, 1; samDesired
0x1800b39e2  xor     r8d, r8d; ulOptions
0x1800b39e5  call    cs:__imp_RegOpenKeyExW
0x1800b39eb  mov     edi, eax
0x1800b39ed  test    eax, eax
0x1800b39ef  jnz     short loc_1800B3A41
0x1800b39f1  mov     rcx, [rsp+48h+hKey]; hKey
0x1800b39f6  lea     r9, [rsp+48h+Type]; lpType
0x1800b39fb  mov     [rsp+48h+Type], eax
0x1800b39ff  xor     r8d, r8d; lpReserved
0x1800b3a02  lea     rax, [rsp+48h+cbData]
0x1800b3a07  mov     [rsp+48h+cbData], 4
0x1800b3a0f  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800b3a14  mov     rdx, rsi; lpValueName
0x1800b3a17  mov     [rsp+48h+lpData], rbx; lpData
0x1800b3a1c  call    cs:__imp_RegQueryValueExW
0x1800b3a22  mov     rcx, [rsp+48h+hKey]; hKey
0x1800b3a27  test    eax, eax
0x1800b3a29  jz      short loc_1800B3A3B
0x1800b3a2b  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800b3a31  call    cs:__imp_RegCloseKey
0x1800b3a37  xor     eax, eax
0x1800b3a39  jmp     short loc_1800B3A48
0x1800b3a3b  call    cs:__imp_RegCloseKey
0x1800b3a41  xor     eax, eax
0x1800b3a43  test    edi, edi
0x1800b3a45  setz    al
0x1800b3a48  add     rsp, 30h
0x1800b3a4c  pop     rdi
0x1800b3a4d  pop     rsi
0x1800b3a4e  pop     rbx
0x1800b3a4f  retn
```
