# DmWapPushSvcStopStart::GetDmWapIdleWaitTime(void)

- ea: `0x180004f74`
- end: `0x180005019`
- name: `?GetDmWapIdleWaitTime@DmWapPushSvcStopStart@@YAKXZ`
- size: `165`
- prototype: `__int64 __fastcall(DmWapPushSvcStopStart *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180004ab4`

## callees

- `0x180004f74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004ff3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004ff3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000500a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000500a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004fb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004fb1`

## string_xrefs

- `0x180004f9e`: `SYSTEM\CurrentControlSet\Services\dmwappushservice\Parameters`
- `0x180004fe3`: `SYSTEM\CurrentControlSet\Services\dmwappushservice\Parameters`

## pseudocode

```c
__int64 __fastcall DmWapPushSvcStopStart::GetDmWapIdleWaitTime(DmWapPushSvcStopStart *this)
{
  unsigned int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  pvData = 120;
  hKey = 0;
  pcbData = 4;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\dmwappushservice\\Parameters",
          0,
          0x20019u,
          &hKey)
    && RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\dmwappushservice\\Parameters",
         L"IdleTimeout(sec)",
         0x10u,
         0,
         &pvData,
         &pcbData) )
  {
    pvData = 120;
  }
  RegCloseKey(hKey);
  return pvData;
}

```

## disassembly

```asm
0x180004f74  mov     rax, rsp
0x180004f77  sub     rsp, 48h
0x180004f7b  mov     dword ptr [rax+8], 78h ; 'x'
0x180004f82  mov     r9d, 20019h; samDesired
0x180004f88  mov     qword ptr [rax+18h], 0
0x180004f90  xor     r8d, r8d; ulOptions
0x180004f93  mov     dword ptr [rax+10h], 4
0x180004f9a  lea     rax, [rax+18h]
0x180004f9e  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\dm"...
0x180004fa5  mov     [rsp+48h+phkResult], rax; phkResult
0x180004faa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004fb1  call    cs:__imp_RegOpenKeyExW
0x180004fb7  test    eax, eax
0x180004fb9  jnz     short loc_180005005
0x180004fbb  lea     rax, [rsp+48h+arg_8]
0x180004fc0  mov     r9d, 10h; dwFlags
0x180004fc6  mov     [rsp+48h+pcbData], rax; pcbData
0x180004fcb  lea     r8, Value; "IdleTimeout(sec)"
0x180004fd2  lea     rax, [rsp+48h+arg_0]
0x180004fd7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180004fde  mov     [rsp+48h+pvData], rax; pvData
0x180004fe3  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\dm"...
0x180004fea  mov     [rsp+48h+phkResult], 0; pdwType
0x180004ff3  call    cs:__imp_RegGetValueW
0x180004ff9  test    eax, eax
0x180004ffb  jz      short loc_180005005
0x180004ffd  mov     [rsp+48h+arg_0], 78h ; 'x'
0x180005005  mov     rcx, [rsp+48h+hKey]; hKey
0x18000500a  call    cs:__imp_RegCloseKey
0x180005010  mov     eax, [rsp+48h+arg_0]
0x180005014  add     rsp, 48h
0x180005018  retn
```
