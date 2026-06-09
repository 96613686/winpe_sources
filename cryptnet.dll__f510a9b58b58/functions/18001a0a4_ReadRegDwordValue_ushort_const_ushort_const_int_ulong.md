# ReadRegDwordValue(ushort const *,ushort const *,int,ulong *)

- ea: `0x18001a0a4`
- end: `0x18001a16e`
- name: `?ReadRegDwordValue@@YAKPEBG0HPEAK@Z`
- size: `202`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, int, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180019b00`
- `0x18001a038`

## callees

- `0x18001a0a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a15d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a15d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a0fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a0fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a130`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a130`

## pseudocode

```c
__int64 __fastcall ReadRegDwordValue(LPCWSTR lpSubKey, LPCWSTR lpValueName, int a3, unsigned int *a4)
{
  unsigned int v6; // ebx
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-14h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+38h] BYREF

  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, (a3 != 0 ? 0x100 : 0) | 0x20019, &hKey);
  if ( !v6 )
  {
    cbData = 4;
    v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, Data, &cbData);
    if ( !v6 )
    {
      if ( Type == 4 && cbData == 4 )
        *a4 = *(_DWORD *)Data;
      else
        v6 = 13;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18001a0a4  push    rbp
0x18001a0a6  push    rbx
0x18001a0a7  push    rsi
0x18001a0a8  push    rdi
0x18001a0a9  mov     rbp, rsp
0x18001a0ac  sub     rsp, 48h
0x18001a0b0  mov     rdi, r9
0x18001a0b3  mov     [rbp+Type], 0
0x18001a0ba  neg     r8d
0x18001a0bd  mov     [rbp+cbData], 0
0x18001a0c4  mov     rsi, rdx
0x18001a0c7  mov     dword ptr [rbp+Data], 0
0x18001a0ce  sbb     r9d, r9d
0x18001a0d1  mov     [rbp+hKey], 0
0x18001a0d9  and     r9d, 100h
0x18001a0e0  lea     rax, [rbp+hKey]
0x18001a0e4  mov     rdx, rcx; lpSubKey
0x18001a0e7  mov     [rsp+48h+phkResult], rax; phkResult
0x18001a0ec  or      r9d, 20019h; samDesired
0x18001a0f3  xor     r8d, r8d; ulOptions
0x18001a0f6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a0fd  call    cs:__imp_RegOpenKeyExW
0x18001a103  mov     ebx, eax
0x18001a105  test    eax, eax
0x18001a107  jnz     short loc_18001A154
0x18001a109  mov     rcx, [rbp+hKey]; hKey
0x18001a10d  lea     rax, [rbp+cbData]
0x18001a111  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001a116  lea     r9, [rbp+Type]; lpType
0x18001a11a  lea     rax, [rbp+Data]
0x18001a11e  mov     [rbp+cbData], 4
0x18001a125  xor     r8d, r8d; lpReserved
0x18001a128  mov     [rsp+48h+phkResult], rax; lpData
0x18001a12d  mov     rdx, rsi; lpValueName
0x18001a130  call    cs:__imp_RegQueryValueExW
0x18001a136  mov     ebx, eax
0x18001a138  test    eax, eax
0x18001a13a  jnz     short loc_18001A154
0x18001a13c  cmp     [rbp+Type], 4
0x18001a140  jnz     short loc_18001A14F
0x18001a142  cmp     [rbp+cbData], 4
0x18001a146  jnz     short loc_18001A14F
0x18001a148  mov     eax, dword ptr [rbp+Data]
0x18001a14b  mov     [rdi], eax
0x18001a14d  jmp     short loc_18001A154
0x18001a14f  mov     ebx, 0Dh
0x18001a154  mov     rcx, [rbp+hKey]; hKey
0x18001a158  test    rcx, rcx
0x18001a15b  jz      short loc_18001A163
0x18001a15d  call    cs:__imp_RegCloseKey
0x18001a163  mov     eax, ebx
0x18001a165  add     rsp, 48h
0x18001a169  pop     rdi
0x18001a16a  pop     rsi
0x18001a16b  pop     rbx
0x18001a16c  pop     rbp
0x18001a16d  retn
```
