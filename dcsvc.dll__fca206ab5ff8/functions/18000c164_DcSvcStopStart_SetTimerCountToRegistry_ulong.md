# DcSvcStopStart::SetTimerCountToRegistry(ulong)

- ea: `0x18000c164`
- end: `0x18000c1ed`
- name: `?SetTimerCountToRegistry@DcSvcStopStart@@YAJK@Z`
- size: `137`
- prototype: `__int64 __fastcall(DcSvcStopStart *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800060b0`
- `0x18000c200`

## callees

- `0x18000c164`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c1c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c1c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c1d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c1d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c197`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c197`

## string_xrefs

- `0x18000c189`: `SYSTEM\CurrentControlSet\Services\dcsvc\Parameters`

## pseudocode

```c
__int64 __fastcall DcSvcStopStart::SetTimerCountToRegistry(DcSvcStopStart *this)
{
  LSTATUS v1; // ebx
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  Data = (int)this;
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\dcsvc\\Parameters", 0, 0x20006u, &hKey);
  if ( !v1 )
    v1 = RegSetValueExW(hKey, L"IdleTimerCount", 0, 4u, (const BYTE *)&Data, 4u);
  RegCloseKey(hKey);
  if ( v1 > 0 )
    return (unsigned __int16)v1 | 0x80070000;
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000c164  mov     [rsp+Data], ecx
0x18000c168  push    rbx
0x18000c169  sub     rsp, 30h
0x18000c16d  lea     rax, [rsp+38h+hKey]
0x18000c172  mov     [rsp+38h+hKey], 0
0x18000c17b  mov     r9d, 20006h; samDesired
0x18000c181  mov     [rsp+38h+phkResult], rax; phkResult
0x18000c186  xor     r8d, r8d; ulOptions
0x18000c189  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\dc"...
0x18000c190  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c197  call    cs:__imp_RegOpenKeyExW
0x18000c19d  mov     ebx, eax
0x18000c19f  test    eax, eax
0x18000c1a1  jnz     short loc_18000C1CD
0x18000c1a3  mov     rcx, [rsp+38h+hKey]; hKey
0x18000c1a8  lea     r9d, [rax+4]; dwType
0x18000c1ac  lea     rax, [rsp+38h+Data]
0x18000c1b1  mov     [rsp+38h+cbData], r9d; cbData
0x18000c1b6  xor     r8d, r8d; Reserved
0x18000c1b9  mov     [rsp+38h+phkResult], rax; lpData
0x18000c1be  lea     rdx, ValueName; "IdleTimerCount"
0x18000c1c5  call    cs:__imp_RegSetValueExW
0x18000c1cb  mov     ebx, eax
0x18000c1cd  mov     rcx, [rsp+38h+hKey]; hKey
0x18000c1d2  call    cs:__imp_RegCloseKey
0x18000c1d8  test    ebx, ebx
0x18000c1da  jle     short loc_18000C1E5
0x18000c1dc  movzx   ebx, bx
0x18000c1df  or      ebx, 80070000h
0x18000c1e5  mov     eax, ebx
0x18000c1e7  add     rsp, 30h
0x18000c1eb  pop     rbx
0x18000c1ec  retn
```
