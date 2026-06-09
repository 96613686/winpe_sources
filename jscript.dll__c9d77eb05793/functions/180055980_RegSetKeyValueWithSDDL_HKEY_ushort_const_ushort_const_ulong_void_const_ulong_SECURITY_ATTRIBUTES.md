# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180055980`
- end: `0x180055a28`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `168`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, BYTE *lpData, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180091c04`

## callees

- `0x180055980`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180055a1a`
- `ADVAPI32!RegCloseKey` at `0x180055a1a`
- `ADVAPI32!RegSetValueExW` at `0x180055a04`
- `ADVAPI32!RegSetValueExW` at `0x180055a04`
- `ADVAPI32!RegCreateKeyExW` at `0x1800559d0`
- `ADVAPI32!RegCreateKeyExW` at `0x1800559d0`

## string_xrefs

- `0x18005599c`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x1800559ed`: `LastUnsafeExtensionReportTime`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        BYTE *lpData)
{
  unsigned int v5; // ebx
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v5 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Internet Explorer\\LowRegistry",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  if ( !v5 )
  {
    v5 = RegSetValueExW(hKey, L"LastUnsafeExtensionReportTime", 0, 3u, lpData, 8u);
    if ( hKey != HKEY_CURRENT_USER )
      RegCloseKey(hKey);
  }
  return v5;
}

```

## disassembly

```asm
0x180055980  mov     r11, rsp
0x180055983  mov     [r11+18h], r8
0x180055987  push    rbx
0x180055988  sub     rsp, 50h
0x18005598c  mov     qword ptr [r11-18h], 0
0x180055994  lea     rax, [r11+18h]
0x180055998  mov     [r11-20h], rax
0x18005599c  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Internet Explorer"...
0x1800559a3  mov     qword ptr [r11-28h], 0
0x1800559ab  xor     r9d, r9d; lpClass
0x1800559ae  mov     [rsp+58h+samDesired], 2; samDesired
0x1800559b6  xor     r8d, r8d; Reserved
0x1800559b9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800559c0  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800559c8  mov     qword ptr [r11+18h], 0
0x1800559d0  call    cs:__imp_RegCreateKeyExW
0x1800559d6  mov     ebx, eax
0x1800559d8  test    eax, eax
0x1800559da  jnz     short loc_180055A20
0x1800559dc  mov     rax, [rsp+58h+lpData]
0x1800559e4  lea     r9d, [rbx+3]; dwType
0x1800559e8  mov     rcx, [rsp+58h+hKey]; hKey
0x1800559ed  lea     rdx, aLastunsafeexte; "LastUnsafeExtensionReportTime"
0x1800559f4  mov     [rsp+58h+samDesired], 8; cbData
0x1800559fc  xor     r8d, r8d; Reserved
0x1800559ff  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180055a04  call    cs:__imp_RegSetValueExW
0x180055a0a  mov     rcx, [rsp+58h+hKey]; hKey
0x180055a0f  mov     ebx, eax
0x180055a11  cmp     rcx, 0FFFFFFFF80000001h
0x180055a18  jz      short loc_180055A20
0x180055a1a  call    cs:__imp_RegCloseKey
0x180055a20  mov     eax, ebx
0x180055a22  add     rsp, 50h
0x180055a26  pop     rbx
0x180055a27  retn
```
