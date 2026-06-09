# GetRegistryBytes(ushort const *,uchar *,ulong *)

- ea: `0x1800b37b0`
- end: `0x1800b3843`
- name: `?GetRegistryBytes@@YAHPEBGPEAEPEAK@Z`
- size: `147`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, LPBYTE lpData, LPDWORD lpcbData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b3270`
- `0x1800b436c`

## callees

- `0x1800b37b0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800b381c`
- `ADVAPI32!RegQueryValueExW` at `0x1800b381c`
- `ADVAPI32!RegOpenKeyExW` at `0x1800b37ec`
- `ADVAPI32!RegOpenKeyExW` at `0x1800b37ec`
- `ADVAPI32!RegCloseKey` at `0x1800b382d`
- `ADVAPI32!RegCloseKey` at `0x1800b382d`

## pseudocode

```c
_BOOL8 __fastcall GetRegistryBytes(LPCWSTR lpValueName, LPBYTE lpData, LPDWORD lpcbData)
{
  LSTATUS v6; // edi
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  DWORD Type; // [rsp+88h] [rbp+20h] BYREF

  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Multimedia\\DVD", 0, 1u, &hKey);
  if ( !v6 )
  {
    Type = 0;
    if ( RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, lpcbData) )
      *lpcbData = 0;
    RegCloseKey(hKey);
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x1800b37b0  push    rbx
0x1800b37b2  push    rbp
0x1800b37b3  push    rsi
0x1800b37b4  push    rdi
0x1800b37b5  sub     rsp, 48h
0x1800b37b9  mov     rbx, r8
0x1800b37bc  mov     [rsp+68h+hKey], 0
0x1800b37c5  mov     rsi, rdx
0x1800b37c8  lea     rax, [rsp+68h+hKey]
0x1800b37cd  mov     rbp, rcx
0x1800b37d0  mov     [rsp+68h+phkResult], rax; phkResult
0x1800b37d5  xor     r8d, r8d; ulOptions
0x1800b37d8  lea     rdx, SubKey; "Software\\Microsoft\\Multimedia\\DVD"
0x1800b37df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b37e6  mov     r9d, 1; samDesired
0x1800b37ec  call    cs:__imp_RegOpenKeyExW
0x1800b37f2  mov     edi, eax
0x1800b37f4  test    eax, eax
0x1800b37f6  jnz     short loc_1800B3833
0x1800b37f8  mov     rcx, [rsp+68h+hKey]; hKey
0x1800b37fd  lea     r9, [rsp+68h+Type]; lpType
0x1800b3805  mov     [rsp+68h+lpcbData], rbx; lpcbData
0x1800b380a  xor     r8d, r8d; lpReserved
0x1800b380d  mov     rdx, rbp; lpValueName
0x1800b3810  mov     [rsp+68h+phkResult], rsi; lpData
0x1800b3815  mov     [rsp+68h+Type], eax
0x1800b381c  call    cs:__imp_RegQueryValueExW
0x1800b3822  test    eax, eax
0x1800b3824  jz      short loc_1800B3828
0x1800b3826  mov     [rbx], edi
0x1800b3828  mov     rcx, [rsp+68h+hKey]; hKey
0x1800b382d  call    cs:__imp_RegCloseKey
0x1800b3833  xor     eax, eax
0x1800b3835  test    edi, edi
0x1800b3837  setz    al
0x1800b383a  add     rsp, 48h
0x1800b383e  pop     rdi
0x1800b383f  pop     rsi
0x1800b3840  pop     rbp
0x1800b3841  pop     rbx
0x1800b3842  retn
```
