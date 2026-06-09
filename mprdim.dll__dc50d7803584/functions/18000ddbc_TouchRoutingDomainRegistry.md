# TouchRoutingDomainRegistry

- ea: `0x18000ddbc`
- end: `0x18000de45`
- name: `TouchRoutingDomainRegistry`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180010cd0`

## callees

- `0x18000ddbc`

## import_xrefs

- `msvcrt!_time64` at `0x18000ddcd`
- `msvcrt!_time64` at `0x18000ddcd`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ddf9`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ddf9`
- `ADVAPI32!RegSetValueExW` at `0x18000de25`
- `ADVAPI32!RegSetValueExW` at `0x18000de25`
- `ADVAPI32!RegCloseKey` at `0x18000de37`
- `ADVAPI32!RegCloseKey` at `0x18000de37`

## string_xrefs

- `0x18000dde1`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`

## pseudocode

```c
__int64 TouchRoutingDomainRegistry()
{
  unsigned int v0; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  __time64_t Data; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  Data = _time64(0);
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
         0,
         0xF003Fu,
         &hKey);
  if ( !v0 )
  {
    v0 = RegSetValueExW(hKey, 0, 0, 0xBu, (const BYTE *)&Data, 8u);
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x18000ddbc  push    rbx
0x18000ddbe  sub     rsp, 30h
0x18000ddc2  xor     ecx, ecx; Time
0x18000ddc4  mov     [rsp+38h+hKey], 0
0x18000ddcd  call    cs:__imp__time64
0x18000ddd3  mov     [rsp+38h+Data], rax
0x18000ddd8  mov     r9d, 0F003Fh; samDesired
0x18000ddde  xor     r8d, r8d; ulOptions
0x18000dde1  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x18000dde8  lea     rax, [rsp+38h+hKey]
0x18000dded  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ddf4  mov     [rsp+38h+phkResult], rax; phkResult
0x18000ddf9  call    cs:__imp_RegOpenKeyExW
0x18000ddff  mov     ebx, eax
0x18000de01  test    eax, eax
0x18000de03  jnz     short loc_18000DE3D
0x18000de05  mov     rcx, [rsp+38h+hKey]; hKey
0x18000de0a  lea     rax, [rsp+38h+Data]
0x18000de0f  mov     [rsp+38h+cbData], 8; cbData
0x18000de17  lea     r9d, [rbx+0Bh]; dwType
0x18000de1b  xor     r8d, r8d; Reserved
0x18000de1e  mov     [rsp+38h+phkResult], rax; lpData
0x18000de23  xor     edx, edx; lpValueName
0x18000de25  call    cs:__imp_RegSetValueExW
0x18000de2b  mov     ebx, eax
0x18000de2d  mov     rcx, [rsp+38h+hKey]; hKey
0x18000de32  test    rcx, rcx
0x18000de35  jz      short loc_18000DE3D
0x18000de37  call    cs:__imp_RegCloseKey
0x18000de3d  mov     eax, ebx
0x18000de3f  add     rsp, 30h
0x18000de43  pop     rbx
0x18000de44  retn
```
