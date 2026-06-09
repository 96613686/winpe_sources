# DDMPostCleanup

- ea: `0x180027b70`
- end: `0x180027c87`
- name: `DDMPostCleanup`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18001bf40`

## callees

- `0x180027b70`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180027c44`
- `KERNEL32!DeleteCriticalSection` at `0x180027c44`
- `KERNEL32!FreeLibrary` at `0x180027c29`
- `KERNEL32!FreeLibrary` at `0x180027c6d`
- `KERNEL32!FreeLibrary` at `0x180027c29`
- `KERNEL32!FreeLibrary` at `0x180027c6d`
- `ADVAPI32!RegSetValueExW` at `0x180027c05`
- `ADVAPI32!RegSetValueExW` at `0x180027c05`
- `ADVAPI32!RegOpenKeyExW` at `0x180027bd1`
- `ADVAPI32!RegOpenKeyExW` at `0x180027bd1`
- `ADVAPI32!RegCloseKey` at `0x180027c16`
- `ADVAPI32!RegCloseKey` at `0x180027c16`
- `rasman!RasReferenceRasman` at `0x180027b7f`
- `rasman!RasReferenceRasman` at `0x180027b7f`

## string_xrefs

- `0x180027bc3`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Accounting`

## pseudocode

```c
int DDMPostCleanup()
{
  int result; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( dword_1800CF648 )
    RasReferenceRasman(0);
  if ( qword_1800CF588 )
    qword_1800CF588();
  if ( qword_1800CF590 )
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
    FreeLibrary(qword_1800CF590);
    qword_1800CF590 = 0;
  }
  DeleteCriticalSection(&stru_1800CF5A8);
  result = (int)qword_1800CF578;
  if ( qword_1800CF578 )
    result = qword_1800CF578();
  if ( qword_1800CF580 )
  {
    result = FreeLibrary(qword_1800CF580);
    qword_1800CF580 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180027b70  sub     rsp, 38h
0x180027b74  cmp     cs:dword_1800CF648, 0
0x180027b7b  jz      short loc_180027B8B
0x180027b7d  xor     ecx, ecx
0x180027b7f  call    cs:__imp_RasReferenceRasman
0x180027b86  nop     dword ptr [rax+rax+00h]
0x180027b8b  mov     rax, cs:qword_1800CF588
0x180027b92  test    rax, rax
0x180027b95  jz      short loc_180027B9C
0x180027b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b9c  cmp     cs:qword_1800CF590, 0
0x180027ba4  jz      loc_180027C3D
0x180027baa  and     [rsp+38h+hKey], 0
0x180027bb0  lea     rax, [rsp+38h+hKey]
0x180027bb5  mov     r9d, 2001Fh; samDesired
0x180027bbb  mov     [rsp+38h+phkResult], rax; phkResult
0x180027bc0  xor     r8d, r8d; ulOptions
0x180027bc3  lea     rdx, aSystemCurrentc_9; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180027bca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027bd1  call    cs:__imp_RegOpenKeyExW
0x180027bd8  nop     dword ptr [rax+rax+00h]
0x180027bdd  test    eax, eax
0x180027bdf  jnz     short loc_180027C22
0x180027be1  mov     rcx, [rsp+38h+hKey]; hKey
0x180027be6  lea     r9d, [rax+4]; dwType
0x180027bea  lea     rax, Data
0x180027bf1  mov     [rsp+38h+cbData], r9d; cbData
0x180027bf6  xor     r8d, r8d; Reserved
0x180027bf9  mov     [rsp+38h+phkResult], rax; lpData
0x180027bfe  lea     rdx, aAccountsession; "AccountSessionIdStart"
0x180027c05  call    cs:__imp_RegSetValueExW
0x180027c0c  nop     dword ptr [rax+rax+00h]
0x180027c11  mov     rcx, [rsp+38h+hKey]; hKey
0x180027c16  call    cs:__imp_RegCloseKey
0x180027c1d  nop     dword ptr [rax+rax+00h]
0x180027c22  mov     rcx, cs:qword_1800CF590; hLibModule
0x180027c29  call    cs:__imp_FreeLibrary
0x180027c30  nop     dword ptr [rax+rax+00h]
0x180027c35  and     cs:qword_1800CF590, 0
0x180027c3d  lea     rcx, stru_1800CF5A8; lpCriticalSection
0x180027c44  call    cs:__imp_DeleteCriticalSection
0x180027c4b  nop     dword ptr [rax+rax+00h]
0x180027c50  mov     rax, cs:qword_1800CF578
0x180027c57  test    rax, rax
0x180027c5a  jz      short loc_180027C61
0x180027c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c61  mov     rcx, cs:qword_1800CF580; hLibModule
0x180027c68  test    rcx, rcx
0x180027c6b  jz      short loc_180027C81
0x180027c6d  call    cs:__imp_FreeLibrary
0x180027c74  nop     dword ptr [rax+rax+00h]
0x180027c79  and     cs:qword_1800CF580, 0
0x180027c81  add     rsp, 38h
0x180027c85  retn
```
