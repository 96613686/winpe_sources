# DbgTelemetryCheckTelemetryOptinAndSetGlobal

- ea: `0x180023c74`
- end: `0x180023d50`
- name: `DbgTelemetryCheckTelemetryOptinAndSetGlobal`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018bac`

## callees

- `0x180023c74`

## import_xrefs

- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x180023d19`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x180023d19`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x180023cba`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x180023cde`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x180023cba`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x180023cde`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180023d3a`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180023d3a`

## pseudocode

```c
_BOOL8 DbgTelemetryCheckTelemetryOptinAndSetGlobal()
{
  LSTATUS v0; // eax
  BOOL v1; // ebx
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  int Data; // [rsp+58h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Kits\\Ceip", 0, 0x20019u, &hKey);
  if ( v0 == 2 )
    v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Wow6432Node\\Microsoft\\Windows Kits\\Ceip", 0, 0x20019u, &hKey);
  v1 = 1;
  if ( !v0 )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"OptIn", 0, 0, (LPBYTE)&Data, &cbData) && cbData == 4 )
      v1 = Data == 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  `GlobalTelemetryState'::`2'::s_isTelemetryEnabled = v1;
  return v1;
}

```

## disassembly

```asm
0x180023c74  push    rbp
0x180023c76  push    rbx
0x180023c77  push    rsi
0x180023c78  mov     rbp, rsp
0x180023c7b  sub     rsp, 30h
0x180023c7f  lea     rax, [rbp+hKey]
0x180023c83  mov     [rbp+hKey], 0
0x180023c8b  mov     ebx, 20019h
0x180023c90  mov     [rbp+Data], 0
0x180023c97  mov     rsi, 0FFFFFFFF80000002h
0x180023c9e  mov     [rbp+cbData], 0
0x180023ca5  mov     r9d, ebx; samDesired
0x180023ca8  mov     [rsp+30h+phkResult], rax; phkResult
0x180023cad  mov     rcx, rsi; hKey
0x180023cb0  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows Kits\\Ceip"
0x180023cb7  xor     r8d, r8d; ulOptions
0x180023cba  call    cs:__imp_RegOpenKeyExW
0x180023cc0  cmp     eax, 2
0x180023cc3  jnz     short loc_180023CE4
0x180023cc5  lea     rax, [rbp+hKey]
0x180023cc9  mov     r9d, ebx; samDesired
0x180023ccc  xor     r8d, r8d; ulOptions
0x180023ccf  mov     [rsp+30h+phkResult], rax; phkResult
0x180023cd4  lea     rdx, aSoftwareWow643; "SOFTWARE\\Wow6432Node\\Microsoft\\Windo"...
0x180023cdb  mov     rcx, rsi; hKey
0x180023cde  call    cs:__imp_RegOpenKeyExW
0x180023ce4  mov     esi, 1
0x180023ce9  mov     ebx, esi
0x180023ceb  test    eax, eax
0x180023ced  jnz     short loc_180023D31
0x180023cef  mov     rcx, [rbp+hKey]; hKey
0x180023cf3  lea     rax, [rbp+cbData]
0x180023cf7  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180023cfc  lea     rdx, ValueName; "OptIn"
0x180023d03  lea     rax, [rbp+Data]
0x180023d07  mov     [rbp+cbData], 4
0x180023d0e  xor     r9d, r9d; lpType
0x180023d11  mov     [rsp+30h+phkResult], rax; lpData
0x180023d16  xor     r8d, r8d; lpReserved
0x180023d19  call    cs:__imp_RegQueryValueExW
0x180023d1f  test    eax, eax
0x180023d21  jnz     short loc_180023D31
0x180023d23  cmp     [rbp+cbData], 4
0x180023d27  jnz     short loc_180023D31
0x180023d29  xor     ebx, ebx
0x180023d2b  cmp     [rbp+Data], esi
0x180023d2e  setz    bl
0x180023d31  mov     rcx, [rbp+hKey]; hKey
0x180023d35  test    rcx, rcx
0x180023d38  jz      short loc_180023D40
0x180023d3a  call    cs:__imp_RegCloseKey
0x180023d40  mov     cs:?s_isTelemetryEnabled@?1??GlobalTelemetryState@@YAPEAHXZ@4HA, ebx; int `GlobalTelemetryState(void)'::`2'::s_isTelemetryEnabled
0x180023d46  mov     eax, ebx
0x180023d48  add     rsp, 30h
0x180023d4c  pop     rsi
0x180023d4d  pop     rbx
0x180023d4e  pop     rbp
0x180023d4f  retn
```
