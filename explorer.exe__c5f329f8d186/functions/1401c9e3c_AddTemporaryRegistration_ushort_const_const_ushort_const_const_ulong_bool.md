# AddTemporaryRegistration(ushort const * const,ushort const * const,ulong,bool)

- ea: `0x1401c9e3c`
- end: `0x1401ca168`
- name: `?AddTemporaryRegistration@@YAJQEBG0K_N@Z`
- size: `812`
- prototype: `__int64 __fastcall(const unsigned __int16 *const, const unsigned __int16 *const, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a9b0`

## callees

- `0x140020580`
- `0x14007c5d0`
- `0x140098dc4`
- `0x14009ac68`
- `0x14010e160`
- `0x1401c9e3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401c9f02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401c9f02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401c9f42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401c9fa3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401ca01d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401ca096`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401ca10f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401ca134`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401c9f42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401c9fa3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401ca01d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401ca096`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401ca10f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401ca134`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1401c9fdd`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1401ca056`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1401ca0cf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1401c9fdd`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1401ca056`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1401ca0cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AddTemporaryRegistration(const unsigned __int16 *const a1, const unsigned __int16 *const a2, int a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int v7; // eax
  HKEY v8; // rcx
  int v9; // eax
  HKEY v10; // rcx
  unsigned int v11; // eax
  HKEY v12; // rcx
  unsigned int v13; // eax
  HKEY v14; // rcx
  unsigned int v15; // eax
  HKEY v16; // rcx
  HKEY v17; // rcx
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int Data; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v24; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v25[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = StringCchPrintfW(
         SubKey,
         0x104u,
         L"%s\\%s",
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\Applications");
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18D,
      (unsigned int)"shell\\lib\\pcsettingssearch\\pcsettings.cpp",
      (const char *)(unsigned int)v4,
      (int)L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel");
    return v5;
  }
  hKey = 0;
  v7 = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 0, 2u, 0, &hKey, 0);
  if ( v7 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x199,
           (unsigned int)"shell\\lib\\pcsettingssearch\\pcsettings.cpp",
           (const char *)v7,
           dwOptions);
    v8 = hKey;
    hKey = 0;
    if ( v8 )
      RegCloseKey(v8);
    return v5;
  }
  v9 = SHRegSetString(hKey, 0, L"PackageMoniker", L"windows.immersivecontrolpanel_cw5n1h2txyewy");
  v5 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"shell\\lib\\pcsettingssearch\\pcsettings.cpp",
      (const char *)(unsigned int)v9,
      dwOptions);
    v10 = hKey;
    hKey = 0;
    if ( v10 )
      RegCloseKey(v10);
    return v5;
  }
  Data = a3;
  v11 = RegSetKeyValueW(hKey, 0, L"Capabilities", 4u, &Data, 4u);
  if ( v11 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1A7,
           (unsigned int)"shell\\lib\\pcsettingssearch\\pcsettings.cpp",
           (const char *)v11,
           dwOptionsa);
    v12 = hKey;
    hKey = 0;
    if ( v12 )
      RegCloseKey(v12);
    return v5;
  }
  v24 = 0x10000000;
  v13 = RegSetKeyValueW(hKey, 0, L"ApplicationType", 4u, &v24, 4u);
  if ( v13 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1B0,
           (unsigned int)"shell\\lib\\pcsettingssearch\\pcsettings.cpp",
           (const char *)v13,
           dwOptionsb);
    v14 = hKey;
    hKey = 0;
    if ( v14 )
      RegCloseKey(v14);
    return v5;
  }
  v25[0] = 0;
  v15 = RegSetKeyValueW(hKey, 0, L"RegistrationType", 4u, v25, 4u);
  if ( v15 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1BC,
           (unsigned int)"shell\\lib\\pcsettingssearch\\pcsettings.cpp",
           (const char *)v15,
           dwOptionsc);
    v16 = hKey;
    hKey = 0;
    if ( v16 )
      RegCloseKey(v16);
    return v5;
  }
  v17 = hKey;
  hKey = 0;
  if ( v17 )
    RegCloseKey(v17);
  return 0;
}

```

## disassembly

```asm
0x1401c9e3c  mov     [rsp-8+arg_0], rbx
0x1401c9e41  mov     [rsp-8+arg_8], rdi
0x1401c9e46  push    rbp
0x1401c9e47  lea     rbp, [rsp-190h]
0x1401c9e4f  sub     rsp, 290h
0x1401c9e56  mov     rax, cs:__security_cookie
0x1401c9e5d  xor     rax, rsp
0x1401c9e60  mov     [rbp+190h+var_10], rax
0x1401c9e67  mov     edi, r8d
0x1401c9e6a  lea     rax, aWindowsImmersi_0; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x1401c9e71  mov     qword ptr [rsp+290h+dwOptions], rax; int
0x1401c9e76  lea     r9, aSoftwareMicros_85; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1401c9e7d  lea     r8, aSS; "%s\\%s"
0x1401c9e84  mov     edx, 104h; unsigned __int64
0x1401c9e89  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x1401c9e8e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401c9e93  mov     ebx, eax
0x1401c9e95  test    eax, eax
0x1401c9e97  jns     short loc_1401C9EBB
0x1401c9e99  mov     rcx, [rbp+198h]; this
0x1401c9ea0  mov     r9d, eax; char *
0x1401c9ea3  lea     r8, aShellLibPcsett; "shell\\lib\\pcsettingssearch\\pcsetting"...
0x1401c9eaa  mov     edx, 18Dh; void *
0x1401c9eaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401c9eb4  mov     eax, ebx
0x1401c9eb6  jmp     loc_1401CA143
0x1401c9ebb  mov     [rsp+290h+hKey], 0
0x1401c9ec4  mov     [rsp+290h+lpdwDisposition], 0; lpdwDisposition
0x1401c9ecd  lea     rax, [rsp+290h+hKey]
0x1401c9ed2  mov     [rsp+290h+phkResult], rax; phkResult
0x1401c9ed7  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1401c9ee0  mov     [rsp+290h+samDesired], 2; samDesired
0x1401c9ee8  mov     [rsp+290h+dwOptions], 0; int
0x1401c9ef0  xor     r9d, r9d; lpClass
0x1401c9ef3  xor     r8d, r8d; Reserved
0x1401c9ef6  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1401c9efb  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401c9f02  call    cs:__imp_RegCreateKeyExW
0x1401c9f09  nop     dword ptr [rax+rax+00h]
0x1401c9f0e  test    eax, eax
0x1401c9f10  jz      short loc_1401C9F54
0x1401c9f12  mov     rcx, [rbp+198h]; this
0x1401c9f19  mov     r9d, eax; char *
0x1401c9f1c  lea     r8, aShellLibPcsett; "shell\\lib\\pcsettingssearch\\pcsetting"...
0x1401c9f23  mov     edx, 199h; void *
0x1401c9f28  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1401c9f2d  mov     ebx, eax
0x1401c9f2f  mov     rcx, [rsp+290h+hKey]; hKey
0x1401c9f34  mov     [rsp+290h+hKey], 0
0x1401c9f3d  test    rcx, rcx
0x1401c9f40  jz      short loc_1401C9F4F
0x1401c9f42  call    cs:__imp_RegCloseKey
0x1401c9f49  nop     dword ptr [rax+rax+00h]
0x1401c9f4e  nop
0x1401c9f4f  jmp     loc_1401C9EB4
0x1401c9f54  lea     r9, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x1401c9f5b  lea     r8, aPackagemoniker; "PackageMoniker"
0x1401c9f62  xor     edx, edx; unsigned __int16 *
0x1401c9f64  mov     rcx, [rsp+290h+hKey]; HKEY
0x1401c9f69  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1401c9f6e  mov     ebx, eax
0x1401c9f70  test    eax, eax
0x1401c9f72  jns     short loc_1401C9FB5
0x1401c9f74  mov     rcx, [rbp+198h]; this
0x1401c9f7b  mov     r9d, eax; char *
0x1401c9f7e  lea     r8, aShellLibPcsett; "shell\\lib\\pcsettingssearch\\pcsetting"...
0x1401c9f85  mov     edx, 19Eh; void *
0x1401c9f8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401c9f8f  nop
0x1401c9f90  mov     rcx, [rsp+290h+hKey]; hKey
0x1401c9f95  mov     [rsp+290h+hKey], 0
0x1401c9f9e  test    rcx, rcx
0x1401c9fa1  jz      short loc_1401C9FB0
0x1401c9fa3  call    cs:__imp_RegCloseKey
0x1401c9faa  nop     dword ptr [rax+rax+00h]
0x1401c9faf  nop
0x1401c9fb0  jmp     loc_1401C9EB4
0x1401c9fb5  mov     [rsp+290h+Data], edi
0x1401c9fb9  mov     ebx, 4
0x1401c9fbe  mov     [rsp+290h+samDesired], ebx; cbData
0x1401c9fc2  lea     rax, [rsp+290h+Data]
0x1401c9fc7  mov     qword ptr [rsp+290h+dwOptions], rax; unsigned int
0x1401c9fcc  mov     r9d, ebx; dwType
0x1401c9fcf  lea     r8, aCapabilities; "Capabilities"
0x1401c9fd6  xor     edx, edx; lpSubKey
0x1401c9fd8  mov     rcx, [rsp+290h+hKey]; hKey
0x1401c9fdd  call    cs:__imp_RegSetKeyValueW
0x1401c9fe4  nop     dword ptr [rax+rax+00h]
0x1401c9fe9  test    eax, eax
0x1401c9feb  jz      short loc_1401CA02F
0x1401c9fed  mov     rcx, [rbp+198h]; this
0x1401c9ff4  mov     r9d, eax; char *
0x1401c9ff7  lea     r8, aShellLibPcsett; "shell\\lib\\pcsettingssearch\\pcsetting"...
0x1401c9ffe  mov     edx, 1A7h; void *
0x1401ca003  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1401ca008  mov     ebx, eax
0x1401ca00a  mov     rcx, [rsp+290h+hKey]; hKey
0x1401ca00f  mov     [rsp+290h+hKey], 0
0x1401ca018  test    rcx, rcx
0x1401ca01b  jz      short loc_1401CA02A
0x1401ca01d  call    cs:__imp_RegCloseKey
0x1401ca024  nop     dword ptr [rax+rax+00h]
0x1401ca029  nop
0x1401ca02a  jmp     loc_1401C9EB4
0x1401ca02f  mov     [rsp+290h+var_234], 10000000h
0x1401ca037  mov     [rsp+290h+samDesired], ebx; cbData
0x1401ca03b  lea     rax, [rsp+290h+var_234]
0x1401ca040  mov     qword ptr [rsp+290h+dwOptions], rax; unsigned int
0x1401ca045  mov     r9d, ebx; dwType
0x1401ca048  lea     r8, aApplicationtyp; "ApplicationType"
0x1401ca04f  xor     edx, edx; lpSubKey
0x1401ca051  mov     rcx, [rsp+290h+hKey]; hKey
0x1401ca056  call    cs:__imp_RegSetKeyValueW
0x1401ca05d  nop     dword ptr [rax+rax+00h]
0x1401ca062  test    eax, eax
0x1401ca064  jz      short loc_1401CA0A8
0x1401ca066  mov     rcx, [rbp+198h]; this
0x1401ca06d  mov     r9d, eax; char *
0x1401ca070  lea     r8, aShellLibPcsett; "shell\\lib\\pcsettingssearch\\pcsetting"...
0x1401ca077  mov     edx, 1B0h; void *
0x1401ca07c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1401ca081  mov     ebx, eax
0x1401ca083  mov     rcx, [rsp+290h+hKey]; hKey
0x1401ca088  mov     [rsp+290h+hKey], 0
0x1401ca091  test    rcx, rcx
0x1401ca094  jz      short loc_1401CA0A3
0x1401ca096  call    cs:__imp_RegCloseKey
0x1401ca09d  nop     dword ptr [rax+rax+00h]
0x1401ca0a2  nop
0x1401ca0a3  jmp     loc_1401C9EB4
0x1401ca0a8  mov     [rsp+290h+var_230], 0
0x1401ca0b0  mov     [rsp+290h+samDesired], ebx; cbData
0x1401ca0b4  lea     rax, [rsp+290h+var_230]
0x1401ca0b9  mov     qword ptr [rsp+290h+dwOptions], rax; unsigned int
0x1401ca0be  mov     r9d, ebx; dwType
0x1401ca0c1  lea     r8, aRegistrationty; "RegistrationType"
0x1401ca0c8  xor     edx, edx; lpSubKey
0x1401ca0ca  mov     rcx, [rsp+290h+hKey]; hKey
0x1401ca0cf  call    cs:__imp_RegSetKeyValueW
0x1401ca0d6  nop     dword ptr [rax+rax+00h]
0x1401ca0db  test    eax, eax
0x1401ca0dd  jz      short loc_1401CA121
0x1401ca0df  mov     rcx, [rbp+198h]; this
0x1401ca0e6  mov     r9d, eax; char *
0x1401ca0e9  lea     r8, aShellLibPcsett; "shell\\lib\\pcsettingssearch\\pcsetting"...
0x1401ca0f0  mov     edx, 1BCh; void *
0x1401ca0f5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1401ca0fa  mov     ebx, eax
0x1401ca0fc  mov     rcx, [rsp+290h+hKey]; hKey
0x1401ca101  mov     [rsp+290h+hKey], 0
0x1401ca10a  test    rcx, rcx
0x1401ca10d  jz      short loc_1401CA11C
0x1401ca10f  call    cs:__imp_RegCloseKey
0x1401ca116  nop     dword ptr [rax+rax+00h]
0x1401ca11b  nop
0x1401ca11c  jmp     loc_1401C9EB4
0x1401ca121  mov     rcx, [rsp+290h+hKey]; hKey
0x1401ca126  mov     [rsp+290h+hKey], 0
0x1401ca12f  test    rcx, rcx
0x1401ca132  jz      short loc_1401CA141
0x1401ca134  call    cs:__imp_RegCloseKey
0x1401ca13b  nop     dword ptr [rax+rax+00h]
0x1401ca140  nop
0x1401ca141  xor     eax, eax
0x1401ca143  mov     rcx, [rbp+190h+var_10]
0x1401ca14a  xor     rcx, rsp; StackCookie
0x1401ca14d  call    __security_check_cookie
0x1401ca152  lea     r11, [rsp+290h+var_s0]
0x1401ca15a  mov     rbx, [r11+10h]
0x1401ca15e  mov     rdi, [r11+18h]
0x1401ca162  mov     rsp, r11
0x1401ca165  pop     rbp
0x1401ca166  retn
```
