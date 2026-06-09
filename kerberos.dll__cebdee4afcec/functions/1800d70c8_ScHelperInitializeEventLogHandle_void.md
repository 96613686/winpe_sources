# ScHelperInitializeEventLogHandle(void)

- ea: `0x1800d70c8`
- end: `0x1800d71e2`
- name: `?ScHelperInitializeEventLogHandle@@YAJXZ`
- size: `282`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d637c`

## callees

- `0x1800d70c8`
- `0x1800f0890`
- `0x1800f0904`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d7127`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d7127`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d71a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d71a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d716b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d719d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d716b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d719d`

## string_xrefs

- `0x1800d70ee`: `System\CurrentControlSet\Services\EventLog\Application\Smart Card Logon`
- `0x1800d7147`: `%SystemRoot%\System32\kerberos.dll`

## pseudocode

```c
__int64 ScHelperInitializeEventLogHandle(void)
{
  struct _RTL_CRITICAL_SECTION *v1; // rax
  DWORD Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  if ( ScHelperGlobalEventLogHandle )
    return 0;
  hKey = 0;
  Data = 0;
  if ( RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\EventLog\\Application\\Smart Card Logon",
         0,
         (LPWSTR)&Class,
         0,
         0x20006u,
         0,
         &hKey,
         &Data) )
  {
    return 3221225473LL;
  }
  if ( Data == 1 )
  {
    RegSetValueExW(hKey, L"EventMessageFile", 0, 2u, L"%SystemRoot%\\System32\\kerberos.dll", 0x46u);
    Data = 7;
    RegSetValueExW(hKey, L"TypesSupported", 0, 4u, (const BYTE *)&Data, 4u);
  }
  RegCloseKey(hKey);
  v1 = (struct _RTL_CRITICAL_SECTION *)NetpEventlogOpen((wchar_t *)L"Smart Card Logon");
  if ( v1 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&ScHelperGlobalEventLogHandle, (signed __int64)v1, 0) )
      NetpEventlogClose(v1);
    return 0;
  }
  return 3221225871LL;
}

```

## disassembly

```asm
0x1800d70c8  mov     r11, rsp
0x1800d70cb  sub     rsp, 58h
0x1800d70cf  mov     rax, cs:?ScHelperGlobalEventLogHandle@@3REAXEA; void * ScHelperGlobalEventLogHandle
0x1800d70d6  test    rax, rax
0x1800d70d9  jnz     loc_1800D71D4
0x1800d70df  mov     [r11+10h], rax
0x1800d70e3  lea     r9, Class; lpClass
0x1800d70ea  mov     [rsp+58h+Data], eax
0x1800d70ee  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ev"...
0x1800d70f5  lea     rax, [r11+8]
0x1800d70f9  xor     r8d, r8d; Reserved
0x1800d70fc  mov     [r11-18h], rax
0x1800d7100  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d7107  lea     rax, [r11+10h]
0x1800d710b  mov     [r11-20h], rax
0x1800d710f  mov     qword ptr [r11-28h], 0
0x1800d7117  mov     [rsp+58h+samDesired], 20006h; samDesired
0x1800d711f  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800d7127  call    cs:__imp_RegCreateKeyExW
0x1800d712d  test    eax, eax
0x1800d712f  jz      short loc_1800D713B
0x1800d7131  mov     eax, 0C0000001h
0x1800d7136  jmp     loc_1800D71D6
0x1800d713b  cmp     [rsp+58h+Data], 1
0x1800d7140  jnz     short loc_1800D71A3
0x1800d7142  mov     rcx, [rsp+58h+hKey]; hKey
0x1800d7147  lea     rax, Data; "%SystemRoot%\\System32\\kerberos.dll"
0x1800d714e  mov     [rsp+58h+samDesired], 46h ; 'F'; cbData
0x1800d7156  lea     rdx, aEventmessagefi; "EventMessageFile"
0x1800d715d  mov     r9d, 2; dwType
0x1800d7163  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800d7168  xor     r8d, r8d; Reserved
0x1800d716b  call    cs:__imp_RegSetValueExW
0x1800d7171  mov     rcx, [rsp+58h+hKey]; hKey
0x1800d7176  lea     rax, [rsp+58h+Data]
0x1800d717b  mov     r9d, 4; dwType
0x1800d7181  mov     [rsp+58h+Data], 7
0x1800d7189  mov     [rsp+58h+samDesired], r9d; cbData
0x1800d718e  lea     rdx, aTypessupported; "TypesSupported"
0x1800d7195  xor     r8d, r8d; Reserved
0x1800d7198  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800d719d  call    cs:__imp_RegSetValueExW
0x1800d71a3  mov     rcx, [rsp+58h+hKey]; hKey
0x1800d71a8  call    cs:__imp_RegCloseKey
0x1800d71ae  lea     rcx, aSmartCardLogon; "Smart Card Logon"
0x1800d71b5  call    NetpEventlogOpen
0x1800d71ba  mov     rcx, rax; lpCriticalSection
0x1800d71bd  test    rax, rax
0x1800d71c0  jz      short loc_1800D71DB
0x1800d71c2  xor     eax, eax
0x1800d71c4  lock cmpxchg cs:?ScHelperGlobalEventLogHandle@@3REAXEA, rcx; void * ScHelperGlobalEventLogHandle
0x1800d71cd  jz      short loc_1800D71D4
0x1800d71cf  call    NetpEventlogClose
0x1800d71d4  xor     eax, eax
0x1800d71d6  add     rsp, 58h
0x1800d71da  retn
0x1800d71db  mov     eax, 0C000018Fh
0x1800d71e0  jmp     short loc_1800D71D6
```
