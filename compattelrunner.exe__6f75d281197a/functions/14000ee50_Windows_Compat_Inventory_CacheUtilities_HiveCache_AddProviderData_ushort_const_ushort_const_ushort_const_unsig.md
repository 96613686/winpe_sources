# Windows::Compat::Inventory::CacheUtilities::HiveCache::AddProviderData(ushort const *,ushort const *,ushort const *,unsigned __int64)

- ea: `0x14000ee50`
- end: `0x14000eebb`
- name: `?AddProviderData@HiveCache@CacheUtilities@Inventory@Compat@Windows@@UEAAJPEBG00_K@Z`
- size: `107`
- prototype: `int(Windows::Compat::Inventory::CacheUtilities::HiveCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000ee50`
- `0x140010098`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000eea0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000eea0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000ee93`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000ee93`

## pseudocode

```c
LSTATUS __fastcall Windows::Compat::Inventory::CacheUtilities::HiveCache::AddProviderData(
        Windows::Compat::Inventory::CacheUtilities::HiveCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int64 Data)
{
  LSTATUS result; // eax
  LSTATUS v7; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  result = Windows::Compat::Inventory::CacheUtilities::HiveCache::GetItemKey(this, a2, a3, &hKey);
  if ( result >= 0 )
  {
    v7 = RegSetValueExW(hKey, a4, 0, 0xBu, (const BYTE *)&Data, 8u);
    RegCloseKey(hKey);
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x14000ee50  push    rbx
0x14000ee52  sub     rsp, 40h
0x14000ee56  mov     rbx, r9
0x14000ee59  mov     [rsp+48h+hKey], 0
0x14000ee62  lea     r9, [rsp+48h+hKey]; HKEY *
0x14000ee67  call    ?GetItemKey@HiveCache@CacheUtilities@Inventory@Compat@Windows@@AEAAJPEBG0AEAPEAUHKEY__@@@Z; Windows::Compat::Inventory::CacheUtilities::HiveCache::GetItemKey(ushort const *,ushort const *,HKEY__ * &)
0x14000ee6c  test    eax, eax
0x14000ee6e  js      short loc_14000EEB5
0x14000ee70  mov     rcx, [rsp+48h+hKey]; hKey
0x14000ee75  lea     rax, [rsp+48h+Data]
0x14000ee7a  mov     [rsp+48h+cbData], 8; cbData
0x14000ee82  mov     r9d, 0Bh; dwType
0x14000ee88  xor     r8d, r8d; Reserved
0x14000ee8b  mov     [rsp+48h+lpData], rax; lpData
0x14000ee90  mov     rdx, rbx; lpValueName
0x14000ee93  call    cs:__imp_RegSetValueExW
0x14000ee99  mov     rcx, [rsp+48h+hKey]; hKey
0x14000ee9e  mov     ebx, eax
0x14000eea0  call    cs:__imp_RegCloseKey
0x14000eea6  test    ebx, ebx
0x14000eea8  jle     short loc_14000EEB3
0x14000eeaa  movzx   ebx, bx
0x14000eead  or      ebx, 80070000h
0x14000eeb3  mov     eax, ebx
0x14000eeb5  add     rsp, 40h
0x14000eeb9  pop     rbx
0x14000eeba  retn
```
