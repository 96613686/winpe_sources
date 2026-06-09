# HHUrlSecurityManager::InternalSecurityManager::ReadRegistryData(void)

- ea: `0x18006ac20`
- end: `0x18006aea4`
- name: `?ReadRegistryData@InternalSecurityManager@HHUrlSecurityManager@@AEAAXXZ`
- size: `644`
- prototype: `void __fastcall(HHUrlSecurityManager::InternalSecurityManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017ca0`
- `0x180017ce0`
- `0x18002e7b4`
- `0x180037594`

## callees

- `0x18006ab30`
- `0x18006ac20`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18006ae8d`
- `ADVAPI32!RegCloseKey` at `0x18006ae8d`
- `ADVAPI32!RegQueryValueExA` at `0x18006accc`
- `ADVAPI32!RegQueryValueExA` at `0x18006ad13`
- `ADVAPI32!RegQueryValueExA` at `0x18006ad5a`
- `ADVAPI32!RegQueryValueExA` at `0x18006ada1`
- `ADVAPI32!RegQueryValueExA` at `0x18006ade8`
- `ADVAPI32!RegQueryValueExA` at `0x18006ae2f`
- `ADVAPI32!RegQueryValueExA` at `0x18006ae76`
- `ADVAPI32!RegQueryValueExA` at `0x18006accc`
- `ADVAPI32!RegQueryValueExA` at `0x18006ad13`
- `ADVAPI32!RegQueryValueExA` at `0x18006ad5a`
- `ADVAPI32!RegQueryValueExA` at `0x18006ada1`
- `ADVAPI32!RegQueryValueExA` at `0x18006ade8`
- `ADVAPI32!RegQueryValueExA` at `0x18006ae2f`
- `ADVAPI32!RegQueryValueExA` at `0x18006ae76`
- `ADVAPI32!RegOpenKeyExA` at `0x18006ac4c`
- `ADVAPI32!RegOpenKeyExA` at `0x18006ac4c`

## string_xrefs

- `0x18006ac80`: `ProtocolAllowList`

## pseudocode

```c
void __fastcall HHUrlSecurityManager::InternalSecurityManager::ReadRegistryData(
        HHUrlSecurityManager::InternalSecurityManager *this)
{
  HHUrlSecurityManager::InternalSecurityManager *v1; // rcx
  HHUrlSecurityManager::InternalSecurityManager *v2; // rcx
  HHUrlSecurityManager::InternalSecurityManager *cbData; // [rsp+40h] [rbp+8h] BYREF

  cbData = this;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "SOFTWARE\\Microsoft\\HTMLHelp\\1.x\\HHRestrictions\\",
          0,
          0x20019u,
          &HHUrlSecurityManager::m_secMan)
    && HHUrlSecurityManager::m_secMan )
  {
    HHUrlSecurityManager::InternalSecurityManager::ReadListData(
      v1,
      (struct HHUrlSecurityManager::InternalSecurityManager::List *)(&HHUrlSecurityManager::m_secMan + 1),
      "UrlAllowList");
    HHUrlSecurityManager::InternalSecurityManager::ReadListData(
      v2,
      (struct HHUrlSecurityManager::InternalSecurityManager::List *)&qword_18008C2B8,
      "ProtocolAllowList");
    if ( !HHUrlSecurityManager::m_secMan
      || (LODWORD(cbData) = 4,
          RegQueryValueExA(HHUrlSecurityManager::m_secMan, "MaxAllowedZone", 0, 0, &dword_18008C2C8, (LPDWORD)&cbData)) )
    {
      *(_DWORD *)&dword_18008C2C8 = 0;
    }
    if ( !HHUrlSecurityManager::m_secMan
      || (LODWORD(cbData) = 4,
          RegQueryValueExA(
            HHUrlSecurityManager::m_secMan,
            "SafeModeDetectionSetting",
            0,
            0,
            &dword_18008C2CC,
            (LPDWORD)&cbData)) )
    {
      *(_DWORD *)&dword_18008C2CC = 0;
    }
    if ( !HHUrlSecurityManager::m_secMan
      || (LODWORD(cbData) = 4,
          RegQueryValueExA(
            HHUrlSecurityManager::m_secMan,
            "EnableFrameNavigationInSafeMode",
            0,
            0,
            &dword_18008C2D0,
            (LPDWORD)&cbData)) )
    {
      *(_DWORD *)&dword_18008C2D0 = 0;
    }
    if ( !HHUrlSecurityManager::m_secMan
      || (LODWORD(cbData) = 4,
          RegQueryValueExA(
            HHUrlSecurityManager::m_secMan,
            "EnableWindowNavigationInSafeMode",
            0,
            0,
            &dword_18008C2D4,
            (LPDWORD)&cbData)) )
    {
      *(_DWORD *)&dword_18008C2D4 = 0;
    }
    if ( !HHUrlSecurityManager::m_secMan
      || (LODWORD(cbData) = 4,
          RegQueryValueExA(HHUrlSecurityManager::m_secMan, "DisableJumpToUrl", 0, 0, &dword_18008C2D8, (LPDWORD)&cbData)) )
    {
      *(_DWORD *)&dword_18008C2D8 = 0;
    }
    if ( !HHUrlSecurityManager::m_secMan
      || (LODWORD(cbData) = 4,
          RegQueryValueExA(
            HHUrlSecurityManager::m_secMan,
            "EnableNonInteractiveUser",
            0,
            0,
            &dword_18008C2DC,
            (LPDWORD)&cbData)) )
    {
      *(_DWORD *)&dword_18008C2DC = 0;
    }
    if ( !HHUrlSecurityManager::m_secMan
      || (LODWORD(cbData) = 4,
          RegQueryValueExA(
            HHUrlSecurityManager::m_secMan,
            "OverrideLMZLinHHContainer",
            0,
            0,
            &dword_18008C2E0,
            (LPDWORD)&cbData)) )
    {
      *(_DWORD *)&dword_18008C2E0 = 0;
    }
    RegCloseKey(HHUrlSecurityManager::m_secMan);
    HHUrlSecurityManager::m_secMan = 0;
  }
}

```

## disassembly

```asm
0x18006ac20  mov     [rsp+cbData], rcx
0x18006ac25  sub     rsp, 38h
0x18006ac29  lea     rax, ?m_secMan@HHUrlSecurityManager@@0VInternalSecurityManager@1@A; HHUrlSecurityManager::InternalSecurityManager HHUrlSecurityManager::m_secMan
0x18006ac30  mov     r9d, 20019h; samDesired
0x18006ac36  xor     r8d, r8d; ulOptions
0x18006ac39  mov     [rsp+38h+phkResult], rax; phkResult
0x18006ac3e  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\HTMLHelp\\1.x\\HHR"...
0x18006ac45  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006ac4c  call    cs:__imp_RegOpenKeyExA
0x18006ac52  test    eax, eax
0x18006ac54  jnz     loc_18006AE9F
0x18006ac5a  cmp     qword ptr cs:?m_secMan@HHUrlSecurityManager@@0VInternalSecurityManager@1@A, 0; HHUrlSecurityManager::InternalSecurityManager HHUrlSecurityManager::m_secMan
0x18006ac62  jz      loc_18006AE9F
0x18006ac68  lea     r8, aUrlallowlist; "UrlAllowList"
0x18006ac6f  mov     [rsp+38h+var_8], rbx
0x18006ac74  lea     rdx, ?m_secMan@HHUrlSecurityManager@@0VInternalSecurityManager@1@A+8; struct HHUrlSecurityManager::InternalSecurityManager::List *
0x18006ac7b  call    ?ReadListData@InternalSecurityManager@HHUrlSecurityManager@@AEAAXPEAUList@12@PEBD@Z; HHUrlSecurityManager::InternalSecurityManager::ReadListData(HHUrlSecurityManager::InternalSecurityManager::List *,char const *)
0x18006ac80  lea     r8, aProtocolallowl; "ProtocolAllowList"
0x18006ac87  lea     rdx, qword_18008C2B8; struct HHUrlSecurityManager::InternalSecurityManager::List *
0x18006ac8e  call    ?ReadListData@InternalSecurityManager@HHUrlSecurityManager@@AEAAXPEAUList@12@PEBD@Z; HHUrlSecurityManager::InternalSecurityManager::ReadListData(HHUrlSecurityManager::InternalSecurityManager::List *,char const *)
0x18006ac93  mov     rcx, qword ptr cs:?m_secMan@HHUrlSecurityManager@@0VInternalSecurityManager@1@A; hKey
0x18006ac9a  xor     ebx, ebx
0x18006ac9c  test    rcx, rcx
0x18006ac9f  jz      short loc_18006ACD6
0x18006aca1  lea     rax, [rsp+38h+cbData]
0x18006aca6  mov     dword ptr [rsp+38h+cbData], 4
0x18006acae  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18006acb3  lea     rdx, aMaxallowedzone; "MaxAllowedZone"
0x18006acba  lea     rax, dword_18008C2C8
0x18006acc1  xor     r9d, r9d; lpType
0x18006acc4  xor     r8d, r8d; lpReserved
0x18006acc7  mov     [rsp+38h+phkResult], rax; lpData
0x18006accc  call    cs:__imp_RegQueryValueExA
0x18006acd2  test    eax, eax
0x18006acd4  jz      short loc_18006ACDC
0x18006acd6  mov     cs:dword_18008C2C8, ebx
0x18006acdc  mov     rcx, qword ptr cs:?m_secMan@HHUrlSecurityManager@@0VInternalSecurityManager@1@A; hKey
0x18006ace3  test    rcx, rcx
0x18006ace6  jz      short loc_18006AD1D
0x18006ace8  lea     rax, [rsp+38h+cbData]
0x18006aced  mov     dword ptr [rsp+38h+cbData], 4
0x18006acf5  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18006acfa  lea     rdx, aSafemodedetect_0; "SafeModeDetectionSetting"
0x18006ad01  lea     rax, dword_18008C2CC
0x18006ad08  xor     r9d, r9d; lpType
0x18006ad0b  xor     r8d, r8d; lpReserved
0x18006ad0e  mov     [rsp+38h+phkResult], rax; lpData
0x18006ad13  call    cs:__imp_RegQueryValueExA
0x18006ad19  test    eax, eax
0x18006ad1b  jz      short loc_18006AD23
0x18006ad1d  mov     cs:dword_18008C2CC, ebx
0x18006ad23  mov     rcx, qword ptr cs:?m_secMan@HHUrlSecurityManager@@0VInternalSecurityManager@1@A; hKey
0x18006ad2a  test    rcx, rcx
0x18006ad2d  jz      short loc_18006AD64
0x18006ad2f  lea     rax, [rsp+38h+cbData]
0x18006ad34  mov     dword ptr [rsp+38h+cbData], 4
0x18006ad3c  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18006ad41  lea     rdx, aEnableframenav; "EnableFrameNavigationInSafeMode"
0x18006ad48  lea     rax, dword_18008C2D0
0x18006ad4f  xor     r9d, r9d; lpType
0x18006ad52  xor     r8d, r8d; lpReserved
0x18006ad55  mov     [rsp+38h+phkResult], rax; lpData
0x18006ad5a  call    cs:__imp_RegQueryValueExA
0x18006ad60  test    eax, eax
0x18006ad62  jz      short loc_18006AD6A
0x18006ad64  mov     cs:dword_18008C2D0, ebx
0x18006ad6a  mov     rcx, qword ptr cs:?m_secMan@HHUrlSecurityManager@@0VInternalSecurityManager@1@A; hKey
0x18006ad71  test    rcx, rcx
0x18006ad74  jz      short loc_18006ADAB
0x18006ad76  lea     rax, [rsp+38h+cbData]
0x18006ad7b  mov     dword ptr [rsp+38h+cbData], 4
0x18006ad83  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18006ad88  lea     rdx, aEnablewindowna; "EnableWindowNavigationInSafeMode"
0x18006ad8f  lea     rax, dword_18008C2D4
0x18006ad96  xor     r9d, r9d; lpType
0x18006ad99  xor     r8d, r8d; lpReserved
0x18006ad9c  mov     [rsp+38h+phkResult], rax; lpData
0x18006ada1  call    cs:__imp_RegQueryValueExA
0x18006ada7  test    eax, eax
0x18006ada9  jz      short loc_18006ADB1
0x18006adab  mov     cs:dword_18008C2D4, ebx
0x18006adb1  mov     rcx, qword ptr cs:?m_secMan@HHUrlSecurityManager@@0VInternalSecurityManager@1@A; hKey
0x18006adb8  test    rcx, rcx
0x18006adbb  jz      short loc_18006ADF2
0x18006adbd  lea     rax, [rsp+38h+cbData]
0x18006adc2  mov     dword ptr [rsp+38h+cbData], 4
0x18006adca  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18006adcf  lea     rdx, aDisablejumptou; "DisableJumpToUrl"
0x18006add6  lea     rax, dword_18008C2D8
0x18006addd  xor     r9d, r9d; lpType
0x18006ade0  xor     r8d, r8d; lpReserved
0x18006ade3  mov     [rsp+38h+phkResult], rax; lpData
0x18006ade8  call    cs:__imp_RegQueryValueExA
0x18006adee  test    eax, eax
0x18006adf0  jz      short loc_18006ADF8
0x18006adf2  mov     cs:dword_18008C2D8, ebx
0x18006adf8  mov     rcx, qword ptr cs:?m_secMan@HHUrlSecurityManager@@0VInternalSecurityManager@1@A; hKey
0x18006adff  test    rcx, rcx
0x18006ae02  jz      short loc_18006AE39
0x18006ae04  lea     rax, [rsp+38h+cbData]
0x18006ae09  mov     dword ptr [rsp+38h+cbData], 4
0x18006ae11  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18006ae16  lea     rdx, aEnablenoninter; "EnableNonInteractiveUser"
0x18006ae1d  lea     rax, dword_18008C2DC
0x18006ae24  xor     r9d, r9d; lpType
0x18006ae27  xor     r8d, r8d; lpReserved
0x18006ae2a  mov     [rsp+38h+phkResult], rax; lpData
0x18006ae2f  call    cs:__imp_RegQueryValueExA
0x18006ae35  test    eax, eax
0x18006ae37  jz      short loc_18006AE3F
0x18006ae39  mov     cs:dword_18008C2DC, ebx
0x18006ae3f  mov     rcx, qword ptr cs:?m_secMan@HHUrlSecurityManager@@0VInternalSecurityManager@1@A; hKey
0x18006ae46  test    rcx, rcx
0x18006ae49  jz      short loc_18006AE80
0x18006ae4b  lea     rax, [rsp+38h+cbData]
0x18006ae50  mov     dword ptr [rsp+38h+cbData], 4
0x18006ae58  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18006ae5d  lea     rdx, aOverridelmzlin; "OverrideLMZLinHHContainer"
0x18006ae64  lea     rax, dword_18008C2E0
0x18006ae6b  xor     r9d, r9d; lpType
0x18006ae6e  xor     r8d, r8d; lpReserved
0x18006ae71  mov     [rsp+38h+phkResult], rax; lpData
0x18006ae76  call    cs:__imp_RegQueryValueExA
0x18006ae7c  test    eax, eax
0x18006ae7e  jz      short loc_18006AE86
0x18006ae80  mov     cs:dword_18008C2E0, ebx
0x18006ae86  mov     rcx, qword ptr cs:?m_secMan@HHUrlSecurityManager@@0VInternalSecurityManager@1@A; hKey
0x18006ae8d  call    cs:__imp_RegCloseKey
0x18006ae93  mov     qword ptr cs:?m_secMan@HHUrlSecurityManager@@0VInternalSecurityManager@1@A, rbx; HHUrlSecurityManager::InternalSecurityManager HHUrlSecurityManager::m_secMan
0x18006ae9a  mov     rbx, [rsp+38h+var_8]
0x18006ae9f  add     rsp, 38h
0x18006aea3  retn
```
