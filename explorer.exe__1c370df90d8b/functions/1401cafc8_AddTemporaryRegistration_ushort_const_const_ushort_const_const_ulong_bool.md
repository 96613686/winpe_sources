# AddTemporaryRegistration(ushort const * const,ushort const * const,ulong,bool)

- ea: `0x1401cafc8`
- end: `0x1401cb2b7`
- name: `?AddTemporaryRegistration@@YAJQEBG0K_N@Z`
- size: `751`
- prototype: `__int64 __fastcall(const unsigned __int16 *const, const unsigned __int16 *const, unsigned int, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c754`

## callees

- `0x1400158a4`
- `0x140077f58`
- `0x1400936ec`
- `0x1400954e0`
- `0x1401040e0`
- `0x1401cafc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401cb08e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401cb08e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cb0c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cb123`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cb191`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cb1fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cb26b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cb28a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cb0c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cb123`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cb191`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cb1fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cb26b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cb28a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1401cb157`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1401cb1c4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1401cb231`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1401cb157`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1401cb1c4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1401cb231`

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
0x1401cafc8  mov     [rsp-8+arg_0], rbx
0x1401cafcd  mov     [rsp-8+arg_8], rdi
0x1401cafd2  push    rbp
0x1401cafd3  lea     rbp, [rsp-190h]
0x1401cafdb  sub     rsp, 290h
0x1401cafe2  mov     rax, cs:__security_cookie
0x1401cafe9  xor     rax, rsp
0x1401cafec  mov     [rbp+190h+var_10], rax
0x1401caff3  mov     edi, r8d
0x1401caff6  lea     rax, aWindowsImmersi_0; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x1401caffd  mov     qword ptr [rsp+290h+dwOptions], rax; int
0x1401cb002  lea     r9, aSoftwareMicros_85; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1401cb009  lea     r8, aSS; "%s\\%s"
0x1401cb010  mov     edx, 104h; unsigned __int64
0x1401cb015  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x1401cb01a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401cb01f  mov     ebx, eax
0x1401cb021  test    eax, eax
0x1401cb023  jns     short loc_1401CB047
0x1401cb025  mov     rcx, [rbp+198h]; this
0x1401cb02c  mov     r9d, eax; char *
0x1401cb02f  lea     r8, aShellLibPcsett; "shell\\lib\\pcsettingssearch\\pcsetting"...
0x1401cb036  mov     edx, 18Dh; void *
0x1401cb03b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401cb040  mov     eax, ebx
0x1401cb042  jmp     loc_1401CB293
0x1401cb047  mov     [rsp+290h+hKey], 0
0x1401cb050  mov     [rsp+290h+lpdwDisposition], 0; lpdwDisposition
0x1401cb059  lea     rax, [rsp+290h+hKey]
0x1401cb05e  mov     [rsp+290h+phkResult], rax; phkResult
0x1401cb063  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1401cb06c  mov     [rsp+290h+samDesired], 2; samDesired
0x1401cb074  mov     [rsp+290h+dwOptions], 0; int
0x1401cb07c  xor     r9d, r9d; lpClass
0x1401cb07f  xor     r8d, r8d; Reserved
0x1401cb082  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1401cb087  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401cb08e  call    cs:__imp_RegCreateKeyExW
0x1401cb094  test    eax, eax
0x1401cb096  jz      short loc_1401CB0D4
0x1401cb098  mov     rcx, [rbp+198h]; this
0x1401cb09f  mov     r9d, eax; char *
0x1401cb0a2  lea     r8, aShellLibPcsett; "shell\\lib\\pcsettingssearch\\pcsetting"...
0x1401cb0a9  mov     edx, 199h; void *
0x1401cb0ae  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1401cb0b3  mov     ebx, eax
0x1401cb0b5  mov     rcx, [rsp+290h+hKey]; hKey
0x1401cb0ba  mov     [rsp+290h+hKey], 0
0x1401cb0c3  test    rcx, rcx
0x1401cb0c6  jz      short loc_1401CB0CF
0x1401cb0c8  call    cs:__imp_RegCloseKey
0x1401cb0ce  nop
0x1401cb0cf  jmp     loc_1401CB040
0x1401cb0d4  lea     r9, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x1401cb0db  lea     r8, aPackagemoniker; "PackageMoniker"
0x1401cb0e2  xor     edx, edx; unsigned __int16 *
0x1401cb0e4  mov     rcx, [rsp+290h+hKey]; HKEY
0x1401cb0e9  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1401cb0ee  mov     ebx, eax
0x1401cb0f0  test    eax, eax
0x1401cb0f2  jns     short loc_1401CB12F
0x1401cb0f4  mov     rcx, [rbp+198h]; this
0x1401cb0fb  mov     r9d, eax; char *
0x1401cb0fe  lea     r8, aShellLibPcsett; "shell\\lib\\pcsettingssearch\\pcsetting"...
0x1401cb105  mov     edx, 19Eh; void *
0x1401cb10a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401cb10f  nop
0x1401cb110  mov     rcx, [rsp+290h+hKey]; hKey
0x1401cb115  mov     [rsp+290h+hKey], 0
0x1401cb11e  test    rcx, rcx
0x1401cb121  jz      short loc_1401CB12A
0x1401cb123  call    cs:__imp_RegCloseKey
0x1401cb129  nop
0x1401cb12a  jmp     loc_1401CB040
0x1401cb12f  mov     [rsp+290h+Data], edi
0x1401cb133  mov     ebx, 4
0x1401cb138  mov     [rsp+290h+samDesired], ebx; cbData
0x1401cb13c  lea     rax, [rsp+290h+Data]
0x1401cb141  mov     qword ptr [rsp+290h+dwOptions], rax; unsigned int
0x1401cb146  mov     r9d, ebx; dwType
0x1401cb149  lea     r8, aCapabilities; "Capabilities"
0x1401cb150  xor     edx, edx; lpSubKey
0x1401cb152  mov     rcx, [rsp+290h+hKey]; hKey
0x1401cb157  call    cs:__imp_RegSetKeyValueW
0x1401cb15d  test    eax, eax
0x1401cb15f  jz      short loc_1401CB19D
0x1401cb161  mov     rcx, [rbp+198h]; this
0x1401cb168  mov     r9d, eax; char *
0x1401cb16b  lea     r8, aShellLibPcsett; "shell\\lib\\pcsettingssearch\\pcsetting"...
0x1401cb172  mov     edx, 1A7h; void *
0x1401cb177  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1401cb17c  mov     ebx, eax
0x1401cb17e  mov     rcx, [rsp+290h+hKey]; hKey
0x1401cb183  mov     [rsp+290h+hKey], 0
0x1401cb18c  test    rcx, rcx
0x1401cb18f  jz      short loc_1401CB198
0x1401cb191  call    cs:__imp_RegCloseKey
0x1401cb197  nop
0x1401cb198  jmp     loc_1401CB040
0x1401cb19d  mov     [rsp+290h+var_234], 10000000h
0x1401cb1a5  mov     [rsp+290h+samDesired], ebx; cbData
0x1401cb1a9  lea     rax, [rsp+290h+var_234]
0x1401cb1ae  mov     qword ptr [rsp+290h+dwOptions], rax; unsigned int
0x1401cb1b3  mov     r9d, ebx; dwType
0x1401cb1b6  lea     r8, aApplicationtyp; "ApplicationType"
0x1401cb1bd  xor     edx, edx; lpSubKey
0x1401cb1bf  mov     rcx, [rsp+290h+hKey]; hKey
0x1401cb1c4  call    cs:__imp_RegSetKeyValueW
0x1401cb1ca  test    eax, eax
0x1401cb1cc  jz      short loc_1401CB20A
0x1401cb1ce  mov     rcx, [rbp+198h]; this
0x1401cb1d5  mov     r9d, eax; char *
0x1401cb1d8  lea     r8, aShellLibPcsett; "shell\\lib\\pcsettingssearch\\pcsetting"...
0x1401cb1df  mov     edx, 1B0h; void *
0x1401cb1e4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1401cb1e9  mov     ebx, eax
0x1401cb1eb  mov     rcx, [rsp+290h+hKey]; hKey
0x1401cb1f0  mov     [rsp+290h+hKey], 0
0x1401cb1f9  test    rcx, rcx
0x1401cb1fc  jz      short loc_1401CB205
0x1401cb1fe  call    cs:__imp_RegCloseKey
0x1401cb204  nop
0x1401cb205  jmp     loc_1401CB040
0x1401cb20a  mov     [rsp+290h+var_230], 0
0x1401cb212  mov     [rsp+290h+samDesired], ebx; cbData
0x1401cb216  lea     rax, [rsp+290h+var_230]
0x1401cb21b  mov     qword ptr [rsp+290h+dwOptions], rax; unsigned int
0x1401cb220  mov     r9d, ebx; dwType
0x1401cb223  lea     r8, aRegistrationty; "RegistrationType"
0x1401cb22a  xor     edx, edx; lpSubKey
0x1401cb22c  mov     rcx, [rsp+290h+hKey]; hKey
0x1401cb231  call    cs:__imp_RegSetKeyValueW
0x1401cb237  test    eax, eax
0x1401cb239  jz      short loc_1401CB277
0x1401cb23b  mov     rcx, [rbp+198h]; this
0x1401cb242  mov     r9d, eax; char *
0x1401cb245  lea     r8, aShellLibPcsett; "shell\\lib\\pcsettingssearch\\pcsetting"...
0x1401cb24c  mov     edx, 1BCh; void *
0x1401cb251  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1401cb256  mov     ebx, eax
0x1401cb258  mov     rcx, [rsp+290h+hKey]; hKey
0x1401cb25d  mov     [rsp+290h+hKey], 0
0x1401cb266  test    rcx, rcx
0x1401cb269  jz      short loc_1401CB272
0x1401cb26b  call    cs:__imp_RegCloseKey
0x1401cb271  nop
0x1401cb272  jmp     loc_1401CB040
0x1401cb277  mov     rcx, [rsp+290h+hKey]; hKey
0x1401cb27c  mov     [rsp+290h+hKey], 0
0x1401cb285  test    rcx, rcx
0x1401cb288  jz      short loc_1401CB291
0x1401cb28a  call    cs:__imp_RegCloseKey
0x1401cb290  nop
0x1401cb291  xor     eax, eax
0x1401cb293  mov     rcx, [rbp+190h+var_10]
0x1401cb29a  xor     rcx, rsp; StackCookie
0x1401cb29d  call    __security_check_cookie
0x1401cb2a2  lea     r11, [rsp+290h+var_s0]
0x1401cb2aa  mov     rbx, [r11+10h]
0x1401cb2ae  mov     rdi, [r11+18h]
0x1401cb2b2  mov     rsp, r11
0x1401cb2b5  pop     rbp
0x1401cb2b6  retn
```
