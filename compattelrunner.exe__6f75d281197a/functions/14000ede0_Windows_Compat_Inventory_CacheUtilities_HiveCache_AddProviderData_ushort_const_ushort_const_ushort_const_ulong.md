# Windows::Compat::Inventory::CacheUtilities::HiveCache::AddProviderData(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x14000ede0`
- end: `0x14000ee48`
- name: `?AddProviderData@HiveCache@CacheUtilities@Inventory@Compat@Windows@@UEAAJPEBG00K@Z`
- size: `104`
- prototype: `int(Windows::Compat::Inventory::CacheUtilities::HiveCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000ede0`
- `0x140010098`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ee2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ee2d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000ee20`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000ee20`

## pseudocode

```c
LSTATUS __fastcall Windows::Compat::Inventory::CacheUtilities::HiveCache::AddProviderData(
        Windows::Compat::Inventory::CacheUtilities::HiveCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int Data)
{
  LSTATUS result; // eax
  LSTATUS v7; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  result = Windows::Compat::Inventory::CacheUtilities::HiveCache::GetItemKey(this, a2, a3, &hKey);
  if ( result >= 0 )
  {
    v7 = RegSetValueExW(hKey, a4, 0, 4u, (const BYTE *)&Data, 4u);
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
0x14000ede0  push    rbx
0x14000ede2  sub     rsp, 40h
0x14000ede6  mov     rbx, r9
0x14000ede9  mov     [rsp+48h+hKey], 0
0x14000edf2  lea     r9, [rsp+48h+hKey]; HKEY *
0x14000edf7  call    ?GetItemKey@HiveCache@CacheUtilities@Inventory@Compat@Windows@@AEAAJPEBG0AEAPEAUHKEY__@@@Z; Windows::Compat::Inventory::CacheUtilities::HiveCache::GetItemKey(ushort const *,ushort const *,HKEY__ * &)
0x14000edfc  test    eax, eax
0x14000edfe  js      short loc_14000EE42
0x14000ee00  mov     rcx, [rsp+48h+hKey]; hKey
0x14000ee05  lea     rax, [rsp+48h+Data]
0x14000ee0a  mov     r9d, 4; dwType
0x14000ee10  xor     r8d, r8d; Reserved
0x14000ee13  mov     [rsp+48h+cbData], r9d; cbData
0x14000ee18  mov     rdx, rbx; lpValueName
0x14000ee1b  mov     [rsp+48h+lpData], rax; lpData
0x14000ee20  call    cs:__imp_RegSetValueExW
0x14000ee26  mov     rcx, [rsp+48h+hKey]; hKey
0x14000ee2b  mov     ebx, eax
0x14000ee2d  call    cs:__imp_RegCloseKey
0x14000ee33  test    ebx, ebx
0x14000ee35  jle     short loc_14000EE40
0x14000ee37  movzx   ebx, bx
0x14000ee3a  or      ebx, 80070000h
0x14000ee40  mov     eax, ebx
0x14000ee42  add     rsp, 40h
0x14000ee46  pop     rbx
0x14000ee47  retn
```
