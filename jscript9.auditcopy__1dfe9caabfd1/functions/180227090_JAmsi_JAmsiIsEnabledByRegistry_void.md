# JAmsi::JAmsiIsEnabledByRegistry(void)

- ea: `0x180227090`
- end: `0x180227172`
- name: `?JAmsiIsEnabledByRegistry@JAmsi@@QEAA_NXZ`
- size: `226`
- prototype: `char __fastcall(JAmsi *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180219414`

## callees

- `0x180227090`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180227155`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180227155`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1802270fb`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1802270fb`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18022712f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18022712f`

## string_xrefs

- `0x180227123`: `AmsiDisableJS9`

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
0x180227090  mov     [rsp-8+arg_0], rcx
0x180227095  push    rbp
0x180227096  mov     rbp, rsp
0x180227099  sub     rsp, 50h
0x18022709d  mov     eax, cs:?g_AmsiEnabled@JAmsi@@0HA; int JAmsi::g_AmsiEnabled
0x1802270a3  mov     [rbp+hKey], 0
0x1802270ab  mov     dword ptr [rbp+Data], 0
0x1802270b2  mov     [rbp+cbData], 4
0x1802270b9  mov     [rbp+Type], 0
0x1802270c0  test    eax, eax
0x1802270c2  jz      loc_18022716B
0x1802270c8  jle     short loc_1802270D1
0x1802270ca  mov     al, 1
0x1802270cc  jmp     loc_18022716B
0x1802270d1  lea     rax, [rbp+hKey]
0x1802270d5  mov     cs:?g_AmsiEnabled@JAmsi@@0HA, 1; int JAmsi::g_AmsiEnabled
0x1802270df  mov     r9d, 20019h; samDesired
0x1802270e5  mov     [rsp+50h+phkResult], rax; phkResult
0x1802270ea  xor     r8d, r8d; ulOptions
0x1802270ed  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows Script\\Se"...
0x1802270f4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802270fb  call    cs:__imp_RegOpenKeyExW
0x180227102  nop     dword ptr [rax+rax+00h]
0x180227107  test    eax, eax
0x180227109  jnz     short loc_180227161
0x18022710b  mov     rcx, [rbp+hKey]; hKey
0x18022710f  lea     rax, [rbp+cbData]
0x180227113  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180227118  lea     r9, [rbp+Type]; lpType
0x18022711c  lea     rax, [rbp+Data]
0x180227120  xor     r8d, r8d; lpReserved
0x180227123  lea     rdx, aAmsidisablejs9; "AmsiDisableJS9"
0x18022712a  mov     [rsp+50h+phkResult], rax; lpData
0x18022712f  call    cs:__imp_RegQueryValueExW
0x180227136  nop     dword ptr [rax+rax+00h]
0x18022713b  test    eax, eax
0x18022713d  jnz     short loc_180227151
0x18022713f  cmp     dword ptr [rbp+Data], 1
0x180227143  jnz     short loc_180227151
0x180227145  cmp     [rbp+Type], 4
0x180227149  jnz     short loc_180227151
0x18022714b  mov     cs:?g_AmsiEnabled@JAmsi@@0HA, eax; int JAmsi::g_AmsiEnabled
0x180227151  mov     rcx, [rbp+hKey]; hKey
0x180227155  call    cs:__imp_RegCloseKey
0x18022715c  nop     dword ptr [rax+rax+00h]
0x180227161  cmp     cs:?g_AmsiEnabled@JAmsi@@0HA, 0; int JAmsi::g_AmsiEnabled
0x180227168  setnz   al
0x18022716b  add     rsp, 50h
0x18022716f  pop     rbp
0x180227170  retn
```
