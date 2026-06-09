# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1801bcce8`
- end: `0x1801bcd9c`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `180`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, BYTE *lpData, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180252cfc`

## callees

- `0x1801bcce8`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1801bcd78`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1801bcd78`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCreateKeyExW` at `0x1801bcd44`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCreateKeyExW` at `0x1801bcd44`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801bcd8e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801bcd8e`

## string_xrefs

- `0x1801bcd10`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x1801bcd61`: `LastUnsafeExtensionReportTime`

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
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF

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
0x1801bcce8  mov     r11, rsp
0x1801bcceb  mov     [r11+20h], r9d
0x1801bccef  mov     [r11+18h], r8
0x1801bccf3  mov     [r11+10h], rdx
0x1801bccf7  mov     [r11+8], rcx
0x1801bccfb  push    rbx
0x1801bccfc  sub     rsp, 60h
0x1801bcd00  mov     qword ptr [r11-28h], 0
0x1801bcd08  lea     rax, [r11-18h]
0x1801bcd0c  mov     [r11-30h], rax
0x1801bcd10  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Internet Explorer"...
0x1801bcd17  mov     qword ptr [r11-38h], 0
0x1801bcd1f  xor     r9d, r9d; lpClass
0x1801bcd22  mov     [rsp+68h+samDesired], 2; samDesired
0x1801bcd2a  xor     r8d, r8d; Reserved
0x1801bcd2d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1801bcd34  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1801bcd3c  mov     qword ptr [r11-18h], 0
0x1801bcd44  call    cs:__imp_RegCreateKeyExW
0x1801bcd4a  mov     ebx, eax
0x1801bcd4c  test    eax, eax
0x1801bcd4e  jnz     short loc_1801BCD94
0x1801bcd50  mov     rax, [rsp+68h+lpData]
0x1801bcd58  lea     r9d, [rbx+3]; dwType
0x1801bcd5c  mov     rcx, [rsp+68h+hKey]; hKey
0x1801bcd61  lea     rdx, ValueName; "LastUnsafeExtensionReportTime"
0x1801bcd68  mov     [rsp+68h+samDesired], 8; cbData
0x1801bcd70  xor     r8d, r8d; Reserved
0x1801bcd73  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x1801bcd78  call    cs:__imp_RegSetValueExW
0x1801bcd7e  mov     rcx, [rsp+68h+hKey]; hKey
0x1801bcd83  mov     ebx, eax
0x1801bcd85  cmp     rcx, 0FFFFFFFF80000001h
0x1801bcd8c  jz      short loc_1801BCD94
0x1801bcd8e  call    cs:__imp_RegCloseKey
0x1801bcd94  mov     eax, ebx
0x1801bcd96  add     rsp, 60h
0x1801bcd9a  pop     rbx
0x1801bcd9b  retn
```
