# JAmsi::JAmsiIsEnabledByRegistry(void)

- ea: `0x1802232ac`
- end: `0x18022337b`
- name: `?JAmsiIsEnabledByRegistry@JAmsi@@QEAA_NXZ`
- size: `207`
- prototype: `bool __fastcall(JAmsi *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180215be4`

## callees

- `0x1802232ac`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180223365`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180223365`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180223317`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180223317`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180223345`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180223345`

## string_xrefs

- `0x180223339`: `AmsiDisableJS9`

## pseudocode

```c
char __fastcall JAmsi::JAmsiIsEnabledByRegistry(JAmsi *this)
{
  char result; // al
  BYTE Data[4]; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+34h] [rbp-1Ch] BYREF
  DWORD cbData; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF

  result = JAmsi::g_AmsiEnabled;
  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 0;
  if ( JAmsi::g_AmsiEnabled )
  {
    if ( JAmsi::g_AmsiEnabled <= 0 )
    {
      JAmsi::g_AmsiEnabled = 1;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Script\\Settings", 0, 0x20019u, &hKey) )
      {
        if ( !RegQueryValueExW(hKey, L"AmsiDisableJS9", 0, &Type, Data, &cbData) && *(_DWORD *)Data == 1 && Type == 4 )
          JAmsi::g_AmsiEnabled = 0;
        RegCloseKey(hKey);
      }
      return JAmsi::g_AmsiEnabled != 0;
    }
    else
    {
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1802232ac  mov     [rsp-8+arg_0], rcx
0x1802232b1  push    rbp
0x1802232b2  mov     rbp, rsp
0x1802232b5  sub     rsp, 50h
0x1802232b9  mov     eax, cs:?g_AmsiEnabled@JAmsi@@0HA; int JAmsi::g_AmsiEnabled
0x1802232bf  mov     [rbp+hKey], 0
0x1802232c7  mov     dword ptr [rbp+Data], 0
0x1802232ce  mov     [rbp+cbData], 4
0x1802232d5  mov     [rbp+Type], 0
0x1802232dc  test    eax, eax
0x1802232de  jz      loc_180223375
0x1802232e4  jle     short loc_1802232ED
0x1802232e6  mov     al, 1
0x1802232e8  jmp     loc_180223375
0x1802232ed  lea     rax, [rbp+hKey]
0x1802232f1  mov     cs:?g_AmsiEnabled@JAmsi@@0HA, 1; int JAmsi::g_AmsiEnabled
0x1802232fb  mov     r9d, 20019h; samDesired
0x180223301  mov     [rsp+50h+phkResult], rax; phkResult
0x180223306  xor     r8d, r8d; ulOptions
0x180223309  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows Script\\Se"...
0x180223310  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180223317  call    cs:__imp_RegOpenKeyExW
0x18022331d  test    eax, eax
0x18022331f  jnz     short loc_18022336B
0x180223321  mov     rcx, [rbp+hKey]; hKey
0x180223325  lea     rax, [rbp+cbData]
0x180223329  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18022332e  lea     r9, [rbp+Type]; lpType
0x180223332  lea     rax, [rbp+Data]
0x180223336  xor     r8d, r8d; lpReserved
0x180223339  lea     rdx, aAmsidisablejs9; "AmsiDisableJS9"
0x180223340  mov     [rsp+50h+phkResult], rax; lpData
0x180223345  call    cs:__imp_RegQueryValueExW
0x18022334b  test    eax, eax
0x18022334d  jnz     short loc_180223361
0x18022334f  cmp     dword ptr [rbp+Data], 1
0x180223353  jnz     short loc_180223361
0x180223355  cmp     [rbp+Type], 4
0x180223359  jnz     short loc_180223361
0x18022335b  mov     cs:?g_AmsiEnabled@JAmsi@@0HA, eax; int JAmsi::g_AmsiEnabled
0x180223361  mov     rcx, [rbp+hKey]; hKey
0x180223365  call    cs:__imp_RegCloseKey
0x18022336b  cmp     cs:?g_AmsiEnabled@JAmsi@@0HA, 0; int JAmsi::g_AmsiEnabled
0x180223372  setnz   al
0x180223375  add     rsp, 50h
0x180223379  pop     rbp
0x18022337a  retn
```
