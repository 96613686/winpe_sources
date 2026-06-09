# CacNx::Utils::GetRegKeyValue(ushort const *,ushort const *,ulong,ulong *,uchar *)

- ea: `0x180073984`
- end: `0x180073a31`
- name: `?GetRegKeyValue@Utils@CacNx@@SAJPEBG0KPEAKPEAE@Z`
- size: `173`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int *, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800694f0`
- `0x180069680`
- `0x18006b4f4`
- `0x180071600`

## callees

- `0x180073984`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800739fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800739fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800739ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800739ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073a19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073a19`

## pseudocode

```c
__int64 __fastcall CacNx::Utils::GetRegKeyValue(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        DWORD a3,
        unsigned int *a4,
        unsigned __int8 *lpData)
{
  unsigned int v7; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF

  Type = a3;
  hKey = 0;
  v7 = -2147467259;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Terminal Server", 0, 1u, &hKey) )
  {
    Type = 0;
    if ( !RegQueryValueExW(hKey, a2, 0, &Type, lpData, a4) && Type == 4 )
      v7 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180073984  mov     r11, rsp
0x180073987  mov     [r11+10h], rbx
0x18007398b  mov     [r11+20h], rsi
0x18007398f  mov     [r11+18h], r8d
0x180073993  mov     [r11+8], rcx
0x180073997  push    rdi
0x180073998  sub     rsp, 30h
0x18007399c  mov     rdi, r9
0x18007399f  mov     qword ptr [r11+8], 0
0x1800739a7  mov     rsi, rdx
0x1800739aa  lea     rax, [r11+8]
0x1800739ae  mov     r9d, 1; samDesired
0x1800739b4  mov     [r11-18h], rax
0x1800739b8  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Terminal Server"
0x1800739bf  xor     r8d, r8d; ulOptions
0x1800739c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800739c9  mov     ebx, 80004005h
0x1800739ce  call    cs:__imp_RegOpenKeyExW
0x1800739d4  test    eax, eax
0x1800739d6  jnz     short loc_180073A0F
0x1800739d8  mov     rcx, [rsp+38h+hKey]; hKey
0x1800739dd  lea     r9, [rsp+38h+Type]; lpType
0x1800739e2  mov     [rsp+38h+Type], eax
0x1800739e6  xor     r8d, r8d; lpReserved
0x1800739e9  mov     rax, [rsp+38h+arg_20]
0x1800739ee  mov     rdx, rsi; lpValueName
0x1800739f1  mov     [rsp+38h+lpcbData], rdi; lpcbData
0x1800739f6  mov     [rsp+38h+lpData], rax; lpData
0x1800739fb  call    cs:__imp_RegQueryValueExW
0x180073a01  test    eax, eax
0x180073a03  jnz     short loc_180073A0F
0x180073a05  xor     ecx, ecx
0x180073a07  cmp     [rsp+38h+Type], 4
0x180073a0c  cmovz   ebx, ecx
0x180073a0f  mov     rcx, [rsp+38h+hKey]; hKey
0x180073a14  test    rcx, rcx
0x180073a17  jz      short loc_180073A1F
0x180073a19  call    cs:__imp_RegCloseKey
0x180073a1f  mov     rsi, [rsp+38h+arg_18]
0x180073a24  mov     eax, ebx
0x180073a26  mov     rbx, [rsp+38h+arg_8]
0x180073a2b  add     rsp, 30h
0x180073a2f  pop     rdi
0x180073a30  retn
```
