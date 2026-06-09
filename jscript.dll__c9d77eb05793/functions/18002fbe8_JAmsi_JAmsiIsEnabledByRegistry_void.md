# JAmsi::JAmsiIsEnabledByRegistry(void)

- ea: `0x18002fbe8`
- end: `0x18002fcbd`
- name: `?JAmsiIsEnabledByRegistry@JAmsi@@QEAA_NXZ`
- size: `213`
- prototype: `bool __fastcall(JAmsi *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f314`

## callees

- `0x18002fbe8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002fc8d`
- `ADVAPI32!RegCloseKey` at `0x18002fc8d`
- `ADVAPI32!RegQueryValueExW` at `0x18002fc81`
- `ADVAPI32!RegQueryValueExW` at `0x18002fc81`
- `ADVAPI32!RegOpenKeyExW` at `0x18002fc43`
- `ADVAPI32!RegOpenKeyExW` at `0x18002fc43`

## string_xrefs

- `0x18002fc7a`: `AmsiEnable`

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
0x18002fbe8  mov     qword ptr [rsp-10h+cbData], rcx
0x18002fbed  push    rbp
0x18002fbee  push    rbx
0x18002fbef  mov     rbp, rsp
0x18002fbf2  sub     rsp, 38h
0x18002fbf6  mov     eax, cs:?g_AmsiEnabled@@3HA; int g_AmsiEnabled
0x18002fbfc  mov     [rbp+Data], 0
0x18002fc03  mov     [rbp+Type], 0
0x18002fc0a  mov     [rbp+cbData], 0
0x18002fc11  mov     [rbp+hKey], 0
0x18002fc19  test    eax, eax
0x18002fc1b  jz      loc_18002FCB9
0x18002fc21  jg      short loc_18002FC4D
0x18002fc23  lea     rax, [rbp+hKey]
0x18002fc27  mov     r9d, 20019h; samDesired
0x18002fc2d  xor     r8d, r8d; ulOptions
0x18002fc30  mov     [rsp+38h+phkResult], rax; phkResult
0x18002fc35  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows Script\\Se"...
0x18002fc3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002fc43  call    cs:__imp_RegOpenKeyExW
0x18002fc49  test    eax, eax
0x18002fc4b  jz      short loc_18002FC56
0x18002fc4d  mov     al, 1
0x18002fc4f  add     rsp, 38h
0x18002fc53  pop     rbx
0x18002fc54  pop     rbp
0x18002fc55  retn
0x18002fc56  mov     rcx, [rbp+hKey]; hKey
0x18002fc5a  lea     rax, [rbp+cbData]
0x18002fc5e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002fc63  lea     r9, [rbp+Type]; lpType
0x18002fc67  lea     rax, [rbp+Data]
0x18002fc6b  mov     [rbp+cbData], 4
0x18002fc72  xor     r8d, r8d; lpReserved
0x18002fc75  mov     [rsp+38h+phkResult], rax; lpData
0x18002fc7a  lea     rdx, aAmsienable; "AmsiEnable"
0x18002fc81  call    cs:__imp_RegQueryValueExW
0x18002fc87  mov     rcx, [rbp+hKey]; hKey
0x18002fc8b  mov     ebx, eax
0x18002fc8d  call    cs:__imp_RegCloseKey
0x18002fc93  test    ebx, ebx
0x18002fc95  jnz     short loc_18002FC4D
0x18002fc97  cmp     [rbp+Type], 4
0x18002fc9b  jnz     short loc_18002FC4D
0x18002fc9d  mov     ecx, [rbp+Data]
0x18002fca0  xor     eax, eax
0x18002fca2  test    ecx, ecx
0x18002fca4  setnz   al
0x18002fca7  mov     cs:?g_AmsiEnabled@@3HA, eax; int g_AmsiEnabled
0x18002fcad  cmp     ecx, 1
0x18002fcb0  jz      short loc_18002FC4D
0x18002fcb2  test    ecx, ecx
0x18002fcb4  setnz   al
0x18002fcb7  jmp     short loc_18002FC4F
0x18002fcb9  xor     al, al
0x18002fcbb  jmp     short loc_18002FC4F
```
