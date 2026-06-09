# CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)

- ea: `0x180079550`
- end: `0x180079618`
- name: `?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z`
- size: `200`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, LPBYTE lpData, unsigned int *)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007a878`
- `0x18007ac3c`
- `0x18007b444`
- `0x18007ba00`
- `0x18007bdec`
- `0x18007c678`
- `0x18008fb10`
- `0x1800a52bc`
- `0x1800a5d54`
- `0x1800b02fc`
- `0x1800b6c60`
- `0x1800d7f14`

## callees

- `0x180079550`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079600`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079600`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079589`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079589`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800795d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800795d1`

## pseudocode

```c
__int64 __fastcall CommonUtil::GetDwordFromRegistry(
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        LPBYTE lpData,
        unsigned int *a4)
{
  LSTATUS v6; // eax
  signed int v7; // ebx
  LSTATUS v8; // eax
  DWORD cbData; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    cbData = 4;
    Type = 0;
    v8 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    if ( v7 >= 0 && Type != 4 )
      v7 = -2147418113;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180079550  mov     r11, rsp
0x180079553  mov     [r11+8], rbx
0x180079557  mov     [r11+10h], rsi
0x18007955b  push    rdi
0x18007955c  sub     rsp, 40h
0x180079560  mov     rsi, rdx
0x180079563  mov     qword ptr [r11-10h], 0
0x18007956b  mov     rdx, rcx; lpSubKey
0x18007956e  lea     rax, [r11-10h]
0x180079572  mov     rdi, r8
0x180079575  mov     [r11-28h], rax
0x180079579  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180079580  mov     r9d, 20019h; samDesired
0x180079586  xor     r8d, r8d; ulOptions
0x180079589  call    cs:__imp_RegOpenKeyExW
0x18007958f  mov     ebx, eax
0x180079591  test    eax, eax
0x180079593  jle     short loc_18007959E
0x180079595  movzx   ebx, ax
0x180079598  or      ebx, 80070000h
0x18007959e  test    ebx, ebx
0x1800795a0  js      short loc_1800795F6
0x1800795a2  mov     rcx, [rsp+48h+hKey]; hKey
0x1800795a7  lea     rax, [rsp+48h+cbData]
0x1800795ac  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800795b1  lea     r9, [rsp+48h+Type]; lpType
0x1800795b6  xor     r8d, r8d; lpReserved
0x1800795b9  mov     [rsp+48h+lpData], rdi; lpData
0x1800795be  mov     rdx, rsi; lpValueName
0x1800795c1  mov     [rsp+48h+cbData], 4
0x1800795c9  mov     [rsp+48h+Type], 0
0x1800795d1  call    cs:__imp_RegQueryValueExW
0x1800795d7  mov     ebx, eax
0x1800795d9  test    eax, eax
0x1800795db  jle     short loc_1800795E6
0x1800795dd  movzx   ebx, ax
0x1800795e0  or      ebx, 80070000h
0x1800795e6  test    ebx, ebx
0x1800795e8  js      short loc_1800795F6
0x1800795ea  cmp     [rsp+48h+Type], 4
0x1800795ef  jz      short loc_1800795F6
0x1800795f1  mov     ebx, 8000FFFFh
0x1800795f6  mov     rcx, [rsp+48h+hKey]; hKey
0x1800795fb  test    rcx, rcx
0x1800795fe  jz      short loc_180079606
0x180079600  call    cs:__imp_RegCloseKey
0x180079606  mov     rsi, [rsp+48h+arg_8]
0x18007960b  mov     eax, ebx
0x18007960d  mov     rbx, [rsp+48h+arg_0]
0x180079612  add     rsp, 40h
0x180079616  pop     rdi
0x180079617  retn
```
