# COfflineFilesSyncItem::_UpgradeAlreadyPerformed(void)

- ea: `0x18002aeb0`
- end: `0x18002af32`
- name: `?_UpgradeAlreadyPerformed@COfflineFilesSyncItem@@AEAAHXZ`
- size: `130`
- prototype: `__int64 __fastcall(COfflineFilesSyncItem *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ae30`

## callees

- `0x18002aeb0`
- `0x18003c460`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002aee1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002aee1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002af1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002af1f`

## string_xrefs

- `0x18002aed3`: `Software\Classes\Local Settings\Software\Microsoft\Windows\CurrentVersion\NetCache\SyncItemLog`

## pseudocode

```c
__int64 __fastcall COfflineFilesSyncItem::_UpgradeAlreadyPerformed(COfflineFilesSyncItem *this)
{
  unsigned int v1; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\NetCache\\SyncItemLog",
         0,
         0x20019u,
         &hKey) )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b2d92626087837896213d3e9ecbf6039_Traceguids);
    }
    RegCloseKey(hKey);
    return 1;
  }
  return v1;
}

```

## disassembly

```asm
0x18002aeb0  mov     r11, rsp
0x18002aeb3  mov     [r11+8], rcx
0x18002aeb7  push    rbx
0x18002aeb8  sub     rsp, 30h
0x18002aebc  lea     rax, [r11+8]
0x18002aec0  xor     ebx, ebx
0x18002aec2  mov     r9d, 20019h; samDesired
0x18002aec8  mov     [r11+8], rbx
0x18002aecc  xor     r8d, r8d; ulOptions
0x18002aecf  mov     [r11-18h], rax
0x18002aed3  lea     rdx, ?s_szRootKeyName_Vista_Win7@COfflineFilesSyncItem@@0QBGB; "Software\\Classes\\Local Settings\\Soft"...
0x18002aeda  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002aee1  call    cs:__imp_RegOpenKeyExW
0x18002aee7  test    eax, eax
0x18002aee9  jz      short loc_18002AF2A
0x18002aeeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aef2  lea     rax, WPP_GLOBAL_Control
0x18002aef9  cmp     rcx, rax
0x18002aefc  jz      short loc_18002AF1A
0x18002aefe  test    dword ptr [rcx+1Ch], 100000h
0x18002af05  jz      short loc_18002AF1A
0x18002af07  mov     rcx, [rcx+10h]
0x18002af0b  lea     edx, [rbx+0Bh]
0x18002af0e  lea     r8, WPP_b2d92626087837896213d3e9ecbf6039_Traceguids
0x18002af15  call    WPP_SF_
0x18002af1a  mov     rcx, [rsp+38h+hKey]; hKey
0x18002af1f  call    cs:__imp_RegCloseKey
0x18002af25  mov     ebx, 1
0x18002af2a  mov     eax, ebx
0x18002af2c  add     rsp, 30h
0x18002af30  pop     rbx
0x18002af31  retn
```
