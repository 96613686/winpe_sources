# JAmsi::JAmsiIsEnabledByRegistry(void)

- ea: `0x180041c50`
- end: `0x180041d38`
- name: `?JAmsiIsEnabledByRegistry@JAmsi@@QEAA_NXZ`
- size: `232`
- prototype: `bool __fastcall(JAmsi *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180041358`

## callees

- `0x180041c50`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180041d02`
- `ADVAPI32!RegCloseKey` at `0x180041d02`
- `ADVAPI32!RegQueryValueExW` at `0x180041cf0`
- `ADVAPI32!RegQueryValueExW` at `0x180041cf0`
- `ADVAPI32!RegOpenKeyExW` at `0x180041cab`
- `ADVAPI32!RegOpenKeyExW` at `0x180041cab`

## string_xrefs

- `0x180041ce9`: `AmsiEnable`

## pseudocode

```c
bool __fastcall JAmsi::JAmsiIsEnabledByRegistry(JAmsi *this)
{
  LSTATUS v2; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  int v4; // [rsp+54h] [rbp+1Ch]
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v4 = HIDWORD(this);
  Data = 0;
  Type = 0;
  cbData = 0;
  hKey = 0;
  if ( !g_AmsiEnabled )
    return 0;
  if ( g_AmsiEnabled > 0 )
    return 1;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Script\\Settings", 0, 0x20019u, &hKey) )
    return 1;
  cbData = 4;
  v2 = RegQueryValueExW(hKey, L"AmsiEnable", 0, &Type, (LPBYTE)&Data, &cbData);
  RegCloseKey(hKey);
  if ( v2 )
    return 1;
  if ( Type != 4 )
    return 1;
  g_AmsiEnabled = Data != 0;
  if ( Data == 1 )
    return 1;
  return Data != 0;
}

```

## disassembly

```asm
0x180041c50  mov     qword ptr [rsp-10h+cbData], rcx
0x180041c55  push    rbp
0x180041c56  push    rbx
0x180041c57  mov     rbp, rsp
0x180041c5a  sub     rsp, 38h
0x180041c5e  mov     eax, cs:?g_AmsiEnabled@@3HA; int g_AmsiEnabled
0x180041c64  mov     [rbp+Data], 0
0x180041c6b  mov     [rbp+Type], 0
0x180041c72  mov     [rbp+cbData], 0
0x180041c79  mov     [rbp+hKey], 0
0x180041c81  test    eax, eax
0x180041c83  jz      loc_180041D34
0x180041c89  jg      short loc_180041CBB
0x180041c8b  lea     rax, [rbp+hKey]
0x180041c8f  mov     r9d, 20019h; samDesired
0x180041c95  xor     r8d, r8d; ulOptions
0x180041c98  mov     [rsp+38h+phkResult], rax; phkResult
0x180041c9d  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows Script\\Se"...
0x180041ca4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041cab  call    cs:__imp_RegOpenKeyExW
0x180041cb2  nop     dword ptr [rax+rax+00h]
0x180041cb7  test    eax, eax
0x180041cb9  jz      short loc_180041CC5
0x180041cbb  mov     al, 1
0x180041cbd  add     rsp, 38h
0x180041cc1  pop     rbx
0x180041cc2  pop     rbp
0x180041cc3  retn
0x180041cc5  mov     rcx, [rbp+hKey]; hKey
0x180041cc9  lea     rax, [rbp+cbData]
0x180041ccd  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180041cd2  lea     r9, [rbp+Type]; lpType
0x180041cd6  lea     rax, [rbp+Data]
0x180041cda  mov     [rbp+cbData], 4
0x180041ce1  xor     r8d, r8d; lpReserved
0x180041ce4  mov     [rsp+38h+phkResult], rax; lpData
0x180041ce9  lea     rdx, aAmsienable; "AmsiEnable"
0x180041cf0  call    cs:__imp_RegQueryValueExW
0x180041cf7  nop     dword ptr [rax+rax+00h]
0x180041cfc  mov     rcx, [rbp+hKey]; hKey
0x180041d00  mov     ebx, eax
0x180041d02  call    cs:__imp_RegCloseKey
0x180041d09  nop     dword ptr [rax+rax+00h]
0x180041d0e  test    ebx, ebx
0x180041d10  jnz     short loc_180041CBB
0x180041d12  cmp     [rbp+Type], 4
0x180041d16  jnz     short loc_180041CBB
0x180041d18  mov     ecx, [rbp+Data]
0x180041d1b  xor     eax, eax
0x180041d1d  test    ecx, ecx
0x180041d1f  setnz   al
0x180041d22  mov     cs:?g_AmsiEnabled@@3HA, eax; int g_AmsiEnabled
0x180041d28  cmp     ecx, 1
0x180041d2b  jz      short loc_180041CBB
0x180041d2d  test    ecx, ecx
0x180041d2f  setnz   al
0x180041d32  jmp     short loc_180041CBD
0x180041d34  xor     al, al
0x180041d36  jmp     short loc_180041CBD
```
