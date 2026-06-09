# LockoutKey::initialize(void)

- ea: `0x180011f48`
- end: `0x180012038`
- name: `?initialize@LockoutKey@@QEAAXXZ`
- size: `240`
- prototype: `void __fastcall(LockoutKey *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000ea2c`

## callees

- `0x180011f48`
- `0x18001215c`

## import_xrefs

- `iassvcs!IASGlobalLock` at `0x180011f51`
- `iassvcs!IASGlobalLock` at `0x180011f51`
- `iassvcs!IASGlobalUnlock` at `0x180012031`
- `KERNEL32!CreateEventW` at `0x180011fb6`
- `KERNEL32!CreateEventW` at `0x180011fb6`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180012019`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180012019`
- `ADVAPI32!RegCreateKeyExW` at `0x180011fa6`
- `ADVAPI32!RegCreateKeyExW` at `0x180011fa6`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x180011fdb`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x180011fdb`

## string_xrefs

- `0x180011f75`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters\AccountLockout`

## pseudocode

```c
void __fastcall LockoutKey::initialize(LockoutKey *this)
{
  int v1; // eax
  __int64 v2; // rcx
  LockoutKey *dwDisposition; // [rsp+60h] [rbp+8h] BYREF

  dwDisposition = this;
  IASGlobalLock();
  v1 = dword_18003FAD4;
  v2 = 0;
  if ( !dword_18003FAD4 )
  {
    LODWORD(dwDisposition) = 0;
    RegCreateKeyExW(
      HKEY_LOCAL_MACHINE,
      L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\AccountLockout",
      0,
      0,
      0,
      0x2001Fu,
      0,
      &hKey,
      (LPDWORD)&dwDisposition);
    hObject = CreateEventW(0, 0, 0, 0);
    RegNotifyChangeKeyValue(hKey, 0, 4u, hObject, 1);
    LockoutKey::readValues((LockoutKey *)&AccountInfo::root);
    RegisterWaitForSingleObject(&phNewWaitObject, hObject, LockoutKey::onChange, &AccountInfo::root, 0xFFFFFFFF, 0x80u);
    v1 = dword_18003FAD4;
  }
  dword_18003FAD4 = v1 + 1;
  IASGlobalUnlock(v2);
}

```

## disassembly

```asm
0x180011f48  mov     [rsp+dwDisposition], rcx
0x180011f4d  sub     rsp, 58h
0x180011f51  call    cs:__imp_IASGlobalLock
0x180011f57  mov     eax, cs:dword_18003FAD4
0x180011f5d  xor     ecx, ecx
0x180011f5f  test    eax, eax
0x180011f61  jnz     loc_180012025
0x180011f67  lea     rax, [rsp+58h+dwDisposition]
0x180011f6c  mov     dword ptr [rsp+58h+dwDisposition], ecx
0x180011f70  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180011f75  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180011f7c  lea     rax, hKey
0x180011f83  xor     r9d, r9d; lpClass
0x180011f86  mov     [rsp+58h+phkResult], rax; phkResult
0x180011f8b  xor     r8d, r8d; Reserved
0x180011f8e  mov     [rsp+58h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180011f93  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180011f9b  mov     [rsp+58h+dwOptions], ecx; dwOptions
0x180011f9f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011fa6  call    cs:__imp_RegCreateKeyExW
0x180011fac  xor     r9d, r9d; lpName
0x180011faf  xor     r8d, r8d; bInitialState
0x180011fb2  xor     edx, edx; bManualReset
0x180011fb4  xor     ecx, ecx; lpEventAttributes
0x180011fb6  call    cs:__imp_CreateEventW
0x180011fbc  mov     rcx, cs:hKey; hKey
0x180011fc3  xor     edx, edx; bWatchSubtree
0x180011fc5  mov     r9, rax; hEvent
0x180011fc8  mov     cs:hObject, rax
0x180011fcf  mov     [rsp+58h+dwOptions], 1; fAsynchronous
0x180011fd7  lea     r8d, [rdx+4]; dwNotifyFilter
0x180011fdb  call    cs:__imp_RegNotifyChangeKeyValue
0x180011fe1  lea     rcx, ?root@AccountInfo@@0VLockoutKey@@A; this
0x180011fe8  call    ?readValues@LockoutKey@@IEAAXXZ; LockoutKey::readValues(void)
0x180011fed  mov     rdx, cs:hObject; hObject
0x180011ff4  lea     r9, ?root@AccountInfo@@0VLockoutKey@@A; Context
0x180011ffb  lea     r8, ?onChange@LockoutKey@@CAXPEAXE@Z; Callback
0x180012002  mov     [rsp+58h+samDesired], 80h; dwFlags
0x18001200a  lea     rcx, phNewWaitObject; phNewWaitObject
0x180012011  mov     [rsp+58h+dwOptions], 0FFFFFFFFh; dwMilliseconds
0x180012019  call    cs:__imp_RegisterWaitForSingleObject
0x18001201f  mov     eax, cs:dword_18003FAD4
0x180012025  inc     eax
0x180012027  mov     cs:dword_18003FAD4, eax
0x18001202d  add     rsp, 58h
0x180012031  jmp     cs:__imp_IASGlobalUnlock
```
