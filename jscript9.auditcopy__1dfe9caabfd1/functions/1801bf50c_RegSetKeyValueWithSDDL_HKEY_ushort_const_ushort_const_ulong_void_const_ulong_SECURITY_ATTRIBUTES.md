# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1801bf50c`
- end: `0x1801bf5d3`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, __int64, BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802572fc`

## callees

- `0x1801bf50c`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1801bf5a2`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1801bf5a2`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCreateKeyExW` at `0x1801bf568`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCreateKeyExW` at `0x1801bf568`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801bf5be`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801bf5be`

## string_xrefs

- `0x1801bf534`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x1801bf58b`: `LastUnsafeExtensionReportTime`

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
0x1801bf50c  mov     r11, rsp
0x1801bf50f  mov     [r11+20h], r9d
0x1801bf513  mov     [r11+18h], r8
0x1801bf517  mov     [r11+10h], rdx
0x1801bf51b  mov     [r11+8], rcx
0x1801bf51f  push    rbx
0x1801bf520  sub     rsp, 60h
0x1801bf524  mov     qword ptr [r11-28h], 0
0x1801bf52c  lea     rax, [r11-18h]
0x1801bf530  mov     [r11-30h], rax
0x1801bf534  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Internet Explorer"...
0x1801bf53b  mov     qword ptr [r11-38h], 0
0x1801bf543  xor     r9d, r9d; lpClass
0x1801bf546  mov     [rsp+68h+samDesired], 2; samDesired
0x1801bf54e  xor     r8d, r8d; Reserved
0x1801bf551  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1801bf558  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1801bf560  mov     qword ptr [r11-18h], 0
0x1801bf568  call    cs:__imp_RegCreateKeyExW
0x1801bf56f  nop     dword ptr [rax+rax+00h]
0x1801bf574  mov     ebx, eax
0x1801bf576  test    eax, eax
0x1801bf578  jnz     short loc_1801BF5CA
0x1801bf57a  mov     rax, [rsp+68h+lpData]
0x1801bf582  lea     r9d, [rbx+3]; dwType
0x1801bf586  mov     rcx, [rsp+68h+hKey]; hKey
0x1801bf58b  lea     rdx, ValueName; "LastUnsafeExtensionReportTime"
0x1801bf592  mov     [rsp+68h+samDesired], 8; cbData
0x1801bf59a  xor     r8d, r8d; Reserved
0x1801bf59d  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x1801bf5a2  call    cs:__imp_RegSetValueExW
0x1801bf5a9  nop     dword ptr [rax+rax+00h]
0x1801bf5ae  mov     rcx, [rsp+68h+hKey]; hKey
0x1801bf5b3  mov     ebx, eax
0x1801bf5b5  cmp     rcx, 0FFFFFFFF80000001h
0x1801bf5bc  jz      short loc_1801BF5CA
0x1801bf5be  call    cs:__imp_RegCloseKey
0x1801bf5c5  nop     dword ptr [rax+rax+00h]
0x1801bf5ca  mov     eax, ebx
0x1801bf5cc  add     rsp, 60h
0x1801bf5d0  pop     rbx
0x1801bf5d1  retn
```
