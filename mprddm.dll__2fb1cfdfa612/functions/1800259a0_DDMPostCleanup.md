# DDMPostCleanup

- ea: `0x1800259a0`
- end: `0x180025a95`
- name: `DDMPostCleanup`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18001b570`

## callees

- `0x1800259a0`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180025a5c`
- `KERNEL32!DeleteCriticalSection` at `0x180025a5c`
- `KERNEL32!FreeLibrary` at `0x180025a44`
- `KERNEL32!FreeLibrary` at `0x180025a7f`
- `KERNEL32!FreeLibrary` at `0x180025a44`
- `KERNEL32!FreeLibrary` at `0x180025a7f`
- `ADVAPI32!RegSetValueExW` at `0x180025a2c`
- `ADVAPI32!RegSetValueExW` at `0x180025a2c`
- `ADVAPI32!RegOpenKeyExW` at `0x1800259fe`
- `ADVAPI32!RegOpenKeyExW` at `0x1800259fe`
- `ADVAPI32!RegCloseKey` at `0x180025a37`
- `ADVAPI32!RegCloseKey` at `0x180025a37`
- `rasman!RasReferenceRasman` at `0x1800259af`
- `rasman!RasReferenceRasman` at `0x1800259af`

## string_xrefs

- `0x1800259f0`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Accounting`

## pseudocode

```c
int DDMPostCleanup()
{
  int result; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( dword_1800C8648 )
    RasReferenceRasman(0);
  if ( qword_1800C8588 )
    qword_1800C8588();
  if ( qword_1800C8590 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Accounting",
            0,
            0x2001Fu,
            &hKey) )
    {
      RegSetValueExW(hKey, L"AccountSessionIdStart", 0, 4u, &Data, 4u);
      RegCloseKey(hKey);
    }
    FreeLibrary(qword_1800C8590);
    qword_1800C8590 = 0;
  }
  DeleteCriticalSection(&stru_1800C85A8);
  result = (int)qword_1800C8578;
  if ( qword_1800C8578 )
    result = qword_1800C8578();
  if ( qword_1800C8580 )
  {
    result = FreeLibrary(qword_1800C8580);
    qword_1800C8580 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800259a0  sub     rsp, 38h
0x1800259a4  cmp     cs:dword_1800C8648, 0
0x1800259ab  jz      short loc_1800259B5
0x1800259ad  xor     ecx, ecx
0x1800259af  call    cs:__imp_RasReferenceRasman
0x1800259b5  mov     rax, cs:qword_1800C8588
0x1800259bc  test    rax, rax
0x1800259bf  jz      short loc_1800259C6
0x1800259c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259c6  cmp     cs:qword_1800C8590, 0
0x1800259ce  jz      loc_180025A55
0x1800259d4  lea     rax, [rsp+38h+hKey]
0x1800259d9  mov     [rsp+38h+hKey], 0
0x1800259e2  mov     r9d, 2001Fh; samDesired
0x1800259e8  mov     [rsp+38h+phkResult], rax; phkResult
0x1800259ed  xor     r8d, r8d; ulOptions
0x1800259f0  lea     rdx, aSystemCurrentc_9; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x1800259f7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800259fe  call    cs:__imp_RegOpenKeyExW
0x180025a04  test    eax, eax
0x180025a06  jnz     short loc_180025A3D
0x180025a08  mov     rcx, [rsp+38h+hKey]; hKey
0x180025a0d  lea     r9d, [rax+4]; dwType
0x180025a11  lea     rax, Data
0x180025a18  mov     [rsp+38h+cbData], r9d; cbData
0x180025a1d  xor     r8d, r8d; Reserved
0x180025a20  mov     [rsp+38h+phkResult], rax; lpData
0x180025a25  lea     rdx, aAccountsession; "AccountSessionIdStart"
0x180025a2c  call    cs:__imp_RegSetValueExW
0x180025a32  mov     rcx, [rsp+38h+hKey]; hKey
0x180025a37  call    cs:__imp_RegCloseKey
0x180025a3d  mov     rcx, cs:qword_1800C8590; hLibModule
0x180025a44  call    cs:__imp_FreeLibrary
0x180025a4a  mov     cs:qword_1800C8590, 0
0x180025a55  lea     rcx, stru_1800C85A8; lpCriticalSection
0x180025a5c  call    cs:__imp_DeleteCriticalSection
0x180025a62  mov     rax, cs:qword_1800C8578
0x180025a69  test    rax, rax
0x180025a6c  jz      short loc_180025A73
0x180025a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a73  mov     rcx, cs:qword_1800C8580; hLibModule
0x180025a7a  test    rcx, rcx
0x180025a7d  jz      short loc_180025A90
0x180025a7f  call    cs:__imp_FreeLibrary
0x180025a85  mov     cs:qword_1800C8580, 0
0x180025a90  add     rsp, 38h
0x180025a94  retn
```
