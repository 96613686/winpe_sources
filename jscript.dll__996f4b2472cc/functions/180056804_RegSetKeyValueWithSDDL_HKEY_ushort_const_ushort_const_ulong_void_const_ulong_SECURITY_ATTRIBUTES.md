# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180056804`
- end: `0x1800568bf`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `187`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, BYTE *lpData, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180093e34`

## callees

- `0x180056804`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800568aa`
- `ADVAPI32!RegCloseKey` at `0x1800568aa`
- `ADVAPI32!RegSetValueExW` at `0x18005688e`
- `ADVAPI32!RegSetValueExW` at `0x18005688e`
- `ADVAPI32!RegCreateKeyExW` at `0x180056854`
- `ADVAPI32!RegCreateKeyExW` at `0x180056854`

## string_xrefs

- `0x180056820`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x180056877`: `LastUnsafeExtensionReportTime`

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
0x180056804  mov     r11, rsp
0x180056807  mov     [r11+18h], r8
0x18005680b  push    rbx
0x18005680c  sub     rsp, 50h
0x180056810  mov     qword ptr [r11-18h], 0
0x180056818  lea     rax, [r11+18h]
0x18005681c  mov     [r11-20h], rax
0x180056820  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Internet Explorer"...
0x180056827  mov     qword ptr [r11-28h], 0
0x18005682f  xor     r9d, r9d; lpClass
0x180056832  mov     [rsp+58h+samDesired], 2; samDesired
0x18005683a  xor     r8d, r8d; Reserved
0x18005683d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180056844  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18005684c  mov     qword ptr [r11+18h], 0
0x180056854  call    cs:__imp_RegCreateKeyExW
0x18005685b  nop     dword ptr [rax+rax+00h]
0x180056860  mov     ebx, eax
0x180056862  test    eax, eax
0x180056864  jnz     short loc_1800568B6
0x180056866  mov     rax, [rsp+58h+lpData]
0x18005686e  lea     r9d, [rbx+3]; dwType
0x180056872  mov     rcx, [rsp+58h+hKey]; hKey
0x180056877  lea     rdx, aLastunsafeexte; "LastUnsafeExtensionReportTime"
0x18005687e  mov     [rsp+58h+samDesired], 8; cbData
0x180056886  xor     r8d, r8d; Reserved
0x180056889  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18005688e  call    cs:__imp_RegSetValueExW
0x180056895  nop     dword ptr [rax+rax+00h]
0x18005689a  mov     rcx, [rsp+58h+hKey]; hKey
0x18005689f  mov     ebx, eax
0x1800568a1  cmp     rcx, 0FFFFFFFF80000001h
0x1800568a8  jz      short loc_1800568B6
0x1800568aa  call    cs:__imp_RegCloseKey
0x1800568b1  nop     dword ptr [rax+rax+00h]
0x1800568b6  mov     eax, ebx
0x1800568b8  add     rsp, 50h
0x1800568bc  pop     rbx
0x1800568bd  retn
```
