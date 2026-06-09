# Debugger::Telemetry::IsTelemetryOptInSet(bool)

- ea: `0x18000e0d4`
- end: `0x18000e19f`
- name: `?IsTelemetryOptInSet@Telemetry@Debugger@@YA_N_N@Z`
- size: `203`
- prototype: `bool __fastcall(Debugger::Telemetry *__hidden this, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dfdc`

## callees

- `0x18000e0d4`

## import_xrefs

- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x18000e174`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x18000e174`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x18000e10c`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x18000e138`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x18000e10c`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x18000e138`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x18000e191`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x18000e191`

## pseudocode

```c
bool __fastcall Debugger::Telemetry::IsTelemetryOptInSet(Debugger::Telemetry *this)
{
  bool v1; // bl
  LSTATUS v2; // eax
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  LOBYTE(cbData) = (_BYTE)this;
  hKey = 0;
  v1 = 1;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Kits\\Ceip", 0, 0x20019u, &hKey);
  if ( v2 == 2 )
    v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Wow6432Node\\Microsoft\\Windows Kits\\Ceip", 0, 0x20019u, &hKey);
  if ( !v2 )
  {
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"OptIn", 0, 0, (LPBYTE)&Data, &cbData) && cbData == 4 )
      v1 = Data == 1;
    RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x18000e0d4  mov     byte ptr [rsp+cbData], cl
0x18000e0d8  push    rbx
0x18000e0d9  sub     rsp, 30h
0x18000e0dd  lea     rax, [rsp+38h+hKey]
0x18000e0e2  mov     [rsp+38h+hKey], 0
0x18000e0eb  mov     r9d, 20019h; samDesired
0x18000e0f1  mov     [rsp+38h+phkResult], rax; phkResult
0x18000e0f6  xor     r8d, r8d; ulOptions
0x18000e0f9  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows Kits\\Ceip"
0x18000e100  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e107  mov     ebx, 1
0x18000e10c  call    cs:__imp_RegOpenKeyExW
0x18000e112  cmp     eax, 2
0x18000e115  jnz     short loc_18000E13E
0x18000e117  lea     rax, [rsp+38h+hKey]
0x18000e11c  mov     r9d, 20019h; samDesired
0x18000e122  xor     r8d, r8d; ulOptions
0x18000e125  mov     [rsp+38h+phkResult], rax; phkResult
0x18000e12a  lea     rdx, aSoftwareWow643; "SOFTWARE\\Wow6432Node\\Microsoft\\Windo"...
0x18000e131  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e138  call    cs:__imp_RegOpenKeyExW
0x18000e13e  test    eax, eax
0x18000e140  jnz     short loc_18000E197
0x18000e142  mov     rcx, [rsp+38h+hKey]; hKey
0x18000e147  lea     rdx, ValueName; "OptIn"
0x18000e14e  mov     [rsp+38h+Data], eax
0x18000e152  xor     r9d, r9d; lpType
0x18000e155  lea     rax, [rsp+38h+cbData]
0x18000e15a  mov     [rsp+38h+cbData], 4
0x18000e162  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000e167  xor     r8d, r8d; lpReserved
0x18000e16a  lea     rax, [rsp+38h+Data]
0x18000e16f  mov     [rsp+38h+phkResult], rax; lpData
0x18000e174  call    cs:__imp_RegQueryValueExW
0x18000e17a  test    eax, eax
0x18000e17c  jnz     short loc_18000E18C
0x18000e17e  cmp     [rsp+38h+cbData], 4
0x18000e183  jnz     short loc_18000E18C
0x18000e185  cmp     [rsp+38h+Data], ebx
0x18000e189  setz    bl
0x18000e18c  mov     rcx, [rsp+38h+hKey]; hKey
0x18000e191  call    cs:__imp_RegCloseKey
0x18000e197  mov     al, bl
0x18000e199  add     rsp, 30h
0x18000e19d  pop     rbx
0x18000e19e  retn
```
