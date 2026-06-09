# ScHelperInitializeEventLogHandle(void)

- ea: `0x18007d08c`
- end: `0x18007d19f`
- name: `?ScHelperInitializeEventLogHandle@@YAJXZ`
- size: `275`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003f9c0`

## callees

- `0x18007d08c`
- `0x18007eef8`
- `0x18007ef6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d16c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d16c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007d0eb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007d0eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007d12f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007d161`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007d12f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007d161`

## string_xrefs

- `0x18007d0b2`: `System\CurrentControlSet\Services\EventLog\Application\Smart Card Logon`
- `0x18007d10b`: `%SystemRoot%\System32\kerberos.dll`

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
  v1 = (struct _RTL_CRITICAL_SECTION *)NetpEventlogOpen();
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
0x18007d08c  mov     r11, rsp
0x18007d08f  sub     rsp, 58h
0x18007d093  mov     rax, cs:?ScHelperGlobalEventLogHandle@@3REAXEA; void * ScHelperGlobalEventLogHandle
0x18007d09a  test    rax, rax
0x18007d09d  jnz     loc_18007D191
0x18007d0a3  mov     [r11+10h], rax
0x18007d0a7  lea     r9, Class; lpClass
0x18007d0ae  mov     [rsp+58h+Data], eax
0x18007d0b2  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ev"...
0x18007d0b9  lea     rax, [r11+8]
0x18007d0bd  xor     r8d, r8d; Reserved
0x18007d0c0  mov     [r11-18h], rax
0x18007d0c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007d0cb  lea     rax, [r11+10h]
0x18007d0cf  mov     [r11-20h], rax
0x18007d0d3  mov     qword ptr [r11-28h], 0
0x18007d0db  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18007d0e3  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18007d0eb  call    cs:__imp_RegCreateKeyExW
0x18007d0f1  test    eax, eax
0x18007d0f3  jz      short loc_18007D0FF
0x18007d0f5  mov     eax, 0C0000001h
0x18007d0fa  jmp     loc_18007D193
0x18007d0ff  cmp     [rsp+58h+Data], 1
0x18007d104  jnz     short loc_18007D167
0x18007d106  mov     rcx, [rsp+58h+hKey]; hKey
0x18007d10b  lea     rax, Data; "%SystemRoot%\\System32\\kerberos.dll"
0x18007d112  mov     [rsp+58h+samDesired], 46h ; 'F'; cbData
0x18007d11a  lea     rdx, aEventmessagefi; "EventMessageFile"
0x18007d121  mov     r9d, 2; dwType
0x18007d127  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18007d12c  xor     r8d, r8d; Reserved
0x18007d12f  call    cs:__imp_RegSetValueExW
0x18007d135  mov     rcx, [rsp+58h+hKey]; hKey
0x18007d13a  lea     rax, [rsp+58h+Data]
0x18007d13f  mov     r9d, 4; dwType
0x18007d145  mov     [rsp+58h+Data], 7
0x18007d14d  mov     [rsp+58h+samDesired], r9d; cbData
0x18007d152  lea     rdx, aTypessupported; "TypesSupported"
0x18007d159  xor     r8d, r8d; Reserved
0x18007d15c  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18007d161  call    cs:__imp_RegSetValueExW
0x18007d167  mov     rcx, [rsp+58h+hKey]; hKey
0x18007d16c  call    cs:__imp_RegCloseKey
0x18007d172  call    NetpEventlogOpen
0x18007d177  mov     rcx, rax; lpCriticalSection
0x18007d17a  test    rax, rax
0x18007d17d  jz      short loc_18007D198
0x18007d17f  xor     eax, eax
0x18007d181  lock cmpxchg cs:?ScHelperGlobalEventLogHandle@@3REAXEA, rcx; void * ScHelperGlobalEventLogHandle
0x18007d18a  jz      short loc_18007D191
0x18007d18c  call    NetpEventlogClose
0x18007d191  xor     eax, eax
0x18007d193  add     rsp, 58h
0x18007d197  retn
0x18007d198  mov     eax, 0C000018Fh
0x18007d19d  jmp     short loc_18007D193
```
