# DcSvcStopStart::GetTimerCountToRegistry(ulong *)

- ea: `0x18000bc40`
- end: `0x18000bce8`
- name: `?GetTimerCountToRegistry@DcSvcStopStart@@YAJPEAK@Z`
- size: `168`
- prototype: `__int64 __fastcall(PVOID pvData, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000c200`

## callees

- `0x18000bc40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bcc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bcc8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc76`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000bcbb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000bcbb`

## string_xrefs

- `0x18000bc6f`: `SYSTEM\CurrentControlSet\Services\dcsvc\Parameters`
- `0x18000bca4`: `SYSTEM\CurrentControlSet\Services\dcsvc\Parameters`

## pseudocode

```c
__int64 __fastcall DcSvcStopStart::GetTimerCountToRegistry(PVOID pvData, unsigned int *a2)
{
  LSTATUS ValueW; // ebx
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  hKey = 0;
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\dcsvc\\Parameters",
             0,
             0x20019u,
             &hKey);
  if ( !ValueW )
  {
    pcbData = 4;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Services\\dcsvc\\Parameters",
               L"IdleTimerCount",
               0x10u,
               0,
               pvData,
               &pcbData);
  }
  RegCloseKey(hKey);
  if ( ValueW > 0 )
    return (unsigned __int16)ValueW | 0x80070000;
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x18000bc40  mov     r11, rsp
0x18000bc43  mov     [r11+8], rbx
0x18000bc47  push    rdi
0x18000bc48  sub     rsp, 40h
0x18000bc4c  mov     rdi, rcx
0x18000bc4f  mov     qword ptr [r11+18h], 0
0x18000bc57  lea     rax, [r11+18h]
0x18000bc5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bc62  mov     r9d, 20019h; samDesired
0x18000bc68  mov     [r11-28h], rax
0x18000bc6c  xor     r8d, r8d; ulOptions
0x18000bc6f  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\dc"...
0x18000bc76  call    cs:__imp_RegOpenKeyExW
0x18000bc7c  mov     ebx, eax
0x18000bc7e  test    eax, eax
0x18000bc80  jnz     short loc_18000BCC3
0x18000bc82  lea     rax, [rsp+48h+arg_8]
0x18000bc87  mov     [rsp+48h+arg_8], 4
0x18000bc8f  mov     [rsp+48h+pcbData], rax; pcbData
0x18000bc94  lea     r9d, [rbx+10h]; dwFlags
0x18000bc98  mov     [rsp+48h+pvData], rdi; pvData
0x18000bc9d  lea     r8, ValueName; "IdleTimerCount"
0x18000bca4  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\dc"...
0x18000bcab  mov     [rsp+48h+pdwType], 0; pdwType
0x18000bcb4  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000bcbb  call    cs:__imp_RegGetValueW
0x18000bcc1  mov     ebx, eax
0x18000bcc3  mov     rcx, [rsp+48h+hKey]; hKey
0x18000bcc8  call    cs:__imp_RegCloseKey
0x18000bcce  test    ebx, ebx
0x18000bcd0  jle     short loc_18000BCDB
0x18000bcd2  movzx   ebx, bx
0x18000bcd5  or      ebx, 80070000h
0x18000bcdb  mov     eax, ebx
0x18000bcdd  mov     rbx, [rsp+48h+arg_0]
0x18000bce2  add     rsp, 40h
0x18000bce6  pop     rdi
0x18000bce7  retn
```
