# FveAdBackupStatusCache::SetBackupTypeSpecificInformation(void)

- ea: `0x180022ea0`
- end: `0x180022fd0`
- name: `?SetBackupTypeSpecificInformation@FveAdBackupStatusCache@@MEBAJXZ`
- size: `304`
- prototype: `__int64 __fastcall(const BYTE *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800037a0`
- `0x180022ea0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180022f6b`
- `ADVAPI32!RegSetValueExW` at `0x180022f6b`
- `ADVAPI32!RegCreateKeyExW` at `0x180022ef7`
- `ADVAPI32!RegCreateKeyExW` at `0x180022ef7`
- `ADVAPI32!RegCloseKey` at `0x180022fb8`
- `ADVAPI32!RegCloseKey` at `0x180022fb8`

## pseudocode

```c
__int64 __fastcall FveAdBackupStatusCache::SetBackupTypeSpecificInformation(const BYTE *this)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceEncryption\\ADBackup",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( !v3 )
    goto LABEL_8;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v3);
  if ( (v3 & 0x80000000) == 0 )
  {
LABEL_8:
    v4 = RegSetValueExW(hKey, L"DomainGuid", 0, 3u, this + 8, 0x10u);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v3);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180022ea0  mov     r11, rsp
0x180022ea3  mov     [r11+8], rbx
0x180022ea7  mov     [r11+18h], rbp
0x180022eab  push    rdi
0x180022eac  sub     rsp, 50h
0x180022eb0  mov     qword ptr [r11-18h], 0
0x180022eb8  lea     rax, [r11+10h]
0x180022ebc  mov     [r11-20h], rax
0x180022ec0  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180022ec7  mov     qword ptr [r11-28h], 0
0x180022ecf  mov     rdi, rcx
0x180022ed2  mov     [rsp+58h+samDesired], 2; samDesired
0x180022eda  xor     r9d, r9d; lpClass
0x180022edd  xor     r8d, r8d; Reserved
0x180022ee0  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180022ee8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022eef  mov     qword ptr [r11+10h], 0
0x180022ef7  call    cs:__imp_RegCreateKeyExW
0x180022efd  mov     ebx, eax
0x180022eff  test    eax, eax
0x180022f01  jle     short loc_180022F0C
0x180022f03  movzx   ebx, ax
0x180022f06  or      ebx, 80070000h
0x180022f0c  lea     rbp, WPP_GLOBAL_Control
0x180022f13  test    ebx, ebx
0x180022f15  jz      short loc_180022F45
0x180022f17  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f1e  cmp     rcx, rbp
0x180022f21  jz      short loc_180022F41
0x180022f23  test    byte ptr [rcx+1Ch], 40h
0x180022f27  jz      short loc_180022F41
0x180022f29  mov     rcx, [rcx+10h]
0x180022f2d  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180022f34  mov     edx, 8Ah
0x180022f39  mov     r9d, ebx
0x180022f3c  call    WPP_SF_d
0x180022f41  test    ebx, ebx
0x180022f43  js      short loc_180022FAE
0x180022f45  mov     rcx, [rsp+58h+hKey]; hKey
0x180022f4a  lea     rax, [rdi+8]
0x180022f4e  mov     [rsp+58h+samDesired], 10h; cbData
0x180022f56  lea     rdx, aDomainguid; "DomainGuid"
0x180022f5d  mov     r9d, 3; dwType
0x180022f63  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180022f68  xor     r8d, r8d; Reserved
0x180022f6b  call    cs:__imp_RegSetValueExW
0x180022f71  mov     ebx, eax
0x180022f73  test    eax, eax
0x180022f75  jle     short loc_180022F80
0x180022f77  movzx   ebx, ax
0x180022f7a  or      ebx, 80070000h
0x180022f80  test    ebx, ebx
0x180022f82  jz      short loc_180022FAE
0x180022f84  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f8b  cmp     rcx, rbp
0x180022f8e  jz      short loc_180022FAE
0x180022f90  test    byte ptr [rcx+1Ch], 40h
0x180022f94  jz      short loc_180022FAE
0x180022f96  mov     rcx, [rcx+10h]
0x180022f9a  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180022fa1  mov     edx, 8Bh
0x180022fa6  mov     r9d, ebx
0x180022fa9  call    WPP_SF_d
0x180022fae  mov     rcx, [rsp+58h+hKey]; hKey
0x180022fb3  test    rcx, rcx
0x180022fb6  jz      short loc_180022FBE
0x180022fb8  call    cs:__imp_RegCloseKey
0x180022fbe  mov     rbp, [rsp+58h+arg_10]
0x180022fc3  mov     eax, ebx
0x180022fc5  mov     rbx, [rsp+58h+arg_0]
0x180022fca  add     rsp, 50h
0x180022fce  pop     rdi
0x180022fcf  retn
```
