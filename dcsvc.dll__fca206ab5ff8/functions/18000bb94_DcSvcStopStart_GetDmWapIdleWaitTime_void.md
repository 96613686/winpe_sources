# DcSvcStopStart::GetDmWapIdleWaitTime(void)

- ea: `0x18000bb94`
- end: `0x18000bc39`
- name: `?GetDmWapIdleWaitTime@DcSvcStopStart@@YAKXZ`
- size: `165`
- prototype: `__int64 __fastcall(DcSvcStopStart *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800060b0`

## callees

- `0x18000bb94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bbd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bbd1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000bc13`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000bc13`

## string_xrefs

- `0x18000bbbe`: `SYSTEM\CurrentControlSet\Services\dcsvc\Parameters`
- `0x18000bc03`: `SYSTEM\CurrentControlSet\Services\dcsvc\Parameters`

## pseudocode

```c
__int64 __fastcall DcSvcStopStart::GetDmWapIdleWaitTime(DcSvcStopStart *this)
{
  unsigned int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  pvData = 120;
  hKey = 0;
  pcbData = 4;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\dcsvc\\Parameters", 0, 0x20019u, &hKey)
    && RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\dcsvc\\Parameters",
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
0x18000bb94  mov     rax, rsp
0x18000bb97  sub     rsp, 48h
0x18000bb9b  mov     dword ptr [rax+8], 78h ; 'x'
0x18000bba2  mov     r9d, 20019h; samDesired
0x18000bba8  mov     qword ptr [rax+18h], 0
0x18000bbb0  xor     r8d, r8d; ulOptions
0x18000bbb3  mov     dword ptr [rax+10h], 4
0x18000bbba  lea     rax, [rax+18h]
0x18000bbbe  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\dc"...
0x18000bbc5  mov     [rsp+48h+phkResult], rax; phkResult
0x18000bbca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bbd1  call    cs:__imp_RegOpenKeyExW
0x18000bbd7  test    eax, eax
0x18000bbd9  jnz     short loc_18000BC25
0x18000bbdb  lea     rax, [rsp+48h+arg_8]
0x18000bbe0  mov     r9d, 10h; dwFlags
0x18000bbe6  mov     [rsp+48h+pcbData], rax; pcbData
0x18000bbeb  lea     r8, aIdletimeoutSec_0; "IdleTimeout(sec)"
0x18000bbf2  lea     rax, [rsp+48h+arg_0]
0x18000bbf7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000bbfe  mov     [rsp+48h+pvData], rax; pvData
0x18000bc03  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\dc"...
0x18000bc0a  mov     [rsp+48h+phkResult], 0; pdwType
0x18000bc13  call    cs:__imp_RegGetValueW
0x18000bc19  test    eax, eax
0x18000bc1b  jz      short loc_18000BC25
0x18000bc1d  mov     [rsp+48h+arg_0], 78h ; 'x'
0x18000bc25  mov     rcx, [rsp+48h+hKey]; hKey
0x18000bc2a  call    cs:__imp_RegCloseKey
0x18000bc30  mov     eax, [rsp+48h+arg_0]
0x18000bc34  add     rsp, 48h
0x18000bc38  retn
```
