# RegUtil::ReadStringValue(ushort const * const &,ushort const * const &,ushort *,ulong const &)

- ea: `0x18000d4b4`
- end: `0x18000d561`
- name: `?ReadStringValue@RegUtil@@CAJAEBQEBG0PEAGAEBK@Z`
- size: `173`
- prototype: `LSTATUS __fastcall(const WCHAR **, LPCWSTR *, BYTE *, const unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ed44`
- `0x18000fa50`

## callees

- `0x18000d4b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d52b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d52b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d549`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d549`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d4f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d4f6`

## pseudocode

```c
LSTATUS __fastcall RegUtil::ReadStringValue(const WCHAR **a1, LPCWSTR *a2, BYTE *a3, const unsigned int *a4)
{
  const WCHAR *v5; // rdx
  LSTATUS result; // eax
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF

  v5 = *a1;
  cbData = 2 * *a4;
  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v8 = 0;
    v9 = RegQueryValueExW(hKey, *a2, 0, 0, a3, &cbData);
    if ( v9 )
    {
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
      else
        v8 = v9;
    }
    RegCloseKey(hKey);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000d4b4  mov     r11, rsp
0x18000d4b7  mov     [r11+8], rbx
0x18000d4bb  mov     [r11+10h], rsi
0x18000d4bf  push    rdi
0x18000d4c0  sub     rsp, 40h
0x18000d4c4  mov     eax, [r9]
0x18000d4c7  mov     rsi, rdx
0x18000d4ca  mov     rdx, [rcx]; lpSubKey
0x18000d4cd  add     eax, eax
0x18000d4cf  mov     [rsp+48h+cbData], eax
0x18000d4d3  mov     rdi, r8
0x18000d4d6  lea     rax, [r11-18h]
0x18000d4da  mov     qword ptr [r11-18h], 0
0x18000d4e2  mov     r9d, 20019h; samDesired
0x18000d4e8  mov     [r11-28h], rax
0x18000d4ec  xor     r8d, r8d; ulOptions
0x18000d4ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d4f6  call    cs:__imp_RegOpenKeyExW
0x18000d4fc  test    eax, eax
0x18000d4fe  jz      short loc_18000D50C
0x18000d500  jle     short loc_18000D551
0x18000d502  movzx   eax, ax
0x18000d505  or      eax, 80070000h
0x18000d50a  jmp     short loc_18000D551
0x18000d50c  mov     rdx, [rsi]; lpValueName
0x18000d50f  lea     rax, [rsp+48h+cbData]
0x18000d514  mov     rcx, [rsp+48h+hKey]; hKey
0x18000d519  xor     r9d, r9d; lpType
0x18000d51c  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000d521  xor     r8d, r8d; lpReserved
0x18000d524  mov     [rsp+48h+lpData], rdi; lpData
0x18000d529  xor     ebx, ebx
0x18000d52b  call    cs:__imp_RegQueryValueExW
0x18000d531  test    eax, eax
0x18000d533  jz      short loc_18000D544
0x18000d535  jg      short loc_18000D53B
0x18000d537  mov     ebx, eax
0x18000d539  jmp     short loc_18000D544
0x18000d53b  movzx   ebx, ax
0x18000d53e  or      ebx, 80070000h
0x18000d544  mov     rcx, [rsp+48h+hKey]; hKey
0x18000d549  call    cs:__imp_RegCloseKey
0x18000d54f  mov     eax, ebx
0x18000d551  mov     rbx, [rsp+48h+arg_0]
0x18000d556  mov     rsi, [rsp+48h+arg_8]
0x18000d55b  add     rsp, 40h
0x18000d55f  pop     rdi
0x18000d560  retn
```
