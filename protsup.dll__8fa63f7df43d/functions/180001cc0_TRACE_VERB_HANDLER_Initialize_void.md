# TRACE_VERB_HANDLER::Initialize(void)

- ea: `0x180001cc0`
- end: `0x180001d55`
- name: `?Initialize@TRACE_VERB_HANDLER@@SAJXZ`
- size: `149`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180001c10`

## callees

- `0x180001cc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001d34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001d34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001cfa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001cfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001d47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001d47`

## string_xrefs

- `0x180001cdf`: `System\CurrentControlSet\Services\w3svc\Parameters`

## pseudocode

```c
__int64 TRACE_VERB_HANDLER::Initialize(void)
{
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  DWORD Type; // [rsp+48h] [rbp+10h] BYREF
  int Data; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\w3svc\\Parameters", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnableTraceMethod", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      TRACE_VERB_HANDLER::s_fTraceEnabled = Data != 0;
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180001cc0  push    rbx
0x180001cc2  sub     rsp, 30h
0x180001cc6  xor     ebx, ebx
0x180001cc8  lea     rax, [rsp+38h+hKey]
0x180001ccd  mov     r9d, 20019h; samDesired
0x180001cd3  mov     [rsp+38h+hKey], rbx
0x180001cd8  xor     r8d, r8d; ulOptions
0x180001cdb  mov     [rsp+38h+Type], ebx
0x180001cdf  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\w3"...
0x180001ce6  mov     [rsp+38h+cbData], ebx
0x180001cea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001cf1  mov     [rsp+38h+Data], ebx
0x180001cf5  mov     [rsp+38h+phkResult], rax; phkResult
0x180001cfa  call    cs:__imp_RegOpenKeyExW
0x180001d00  test    eax, eax
0x180001d02  jnz     short loc_180001D4D
0x180001d04  mov     rcx, [rsp+38h+hKey]; hKey
0x180001d09  lea     rax, [rsp+38h+cbData]
0x180001d0e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180001d13  lea     r9, [rsp+38h+Type]; lpType
0x180001d18  lea     rax, [rsp+38h+Data]
0x180001d1d  mov     [rsp+38h+cbData], 4
0x180001d25  xor     r8d, r8d; lpReserved
0x180001d28  mov     [rsp+38h+phkResult], rax; lpData
0x180001d2d  lea     rdx, ValueName; "EnableTraceMethod"
0x180001d34  call    cs:__imp_RegQueryValueExW
0x180001d3a  test    eax, eax
0x180001d3c  jz      loc_1800031FA
0x180001d42  mov     rcx, [rsp+38h+hKey]; hKey
0x180001d47  call    cs:__imp_RegCloseKey
0x180001d4d  xor     eax, eax
0x180001d4f  add     rsp, 30h
0x180001d53  pop     rbx
0x180001d54  retn
0x1800031fa  cmp     [rsp+38h+Type], 4
0x1800031ff  jnz     loc_180001D42
0x180003205  cmp     [rsp+38h+Data], ebx
0x180003209  mov     eax, ebx
0x18000320b  setnz   al
0x18000320e  mov     cs:?s_fTraceEnabled@TRACE_VERB_HANDLER@@0HA, eax; int TRACE_VERB_HANDLER::s_fTraceEnabled
0x180003214  jmp     loc_180001D42
```
