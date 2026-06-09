# CreateShellSessionKey(ulong,HKEY__ * *)

- ea: `0x18009cb60`
- end: `0x18009cc2c`
- name: `?CreateShellSessionKey@@YAJKPEAPEAUHKEY__@@@Z`
- size: `204`
- prototype: `int(unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009cc34`

## callees

- `0x18002568c`
- `0x18006ed20`
- `0x18009cb60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18009cb9a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18009cb9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009cb8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009cb8d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009cc01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009cc01`

## pseudocode

```c
LSTATUS __fastcall CreateShellSessionKey(__int64 a1, HKEY *a2)
{
  DWORD CurrentProcessId; // eax
  LSTATUS result; // eax
  DWORD pSessionId; // [rsp+50h] [rbp-C8h] BYREF
  DWORD dwDisposition[3]; // [rsp+54h] [rbp-C4h] BYREF
  WCHAR SubKey[80]; // [rsp+60h] [rbp-B8h] BYREF

  *a2 = 0;
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, &pSessionId);
  result = StringCchPrintfW(
             SubKey,
             0x4Bu,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\SessionInfo\\%d",
             pSessionId);
  if ( result >= 0 )
  {
    dwDisposition[0] = 0;
    result = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 1u, 4u, 0, a2, dwDisposition);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18009cb60  push    rbx
0x18009cb62  sub     rsp, 110h
0x18009cb69  mov     rax, cs:__security_cookie
0x18009cb70  xor     rax, rsp
0x18009cb73  mov     [rsp+118h+var_18], rax
0x18009cb7b  mov     rbx, rdx
0x18009cb7e  mov     qword ptr [rdx], 0
0x18009cb85  mov     [rsp+118h+pSessionId], 0
0x18009cb8d  call    cs:__imp_GetCurrentProcessId
0x18009cb93  mov     ecx, eax; dwProcessId
0x18009cb95  lea     rdx, [rsp+118h+pSessionId]; pSessionId
0x18009cb9a  call    cs:__imp_ProcessIdToSessionId
0x18009cba0  mov     r9d, [rsp+118h+pSessionId]
0x18009cba5  lea     r8, ?shellSessionKeyFormat@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009cbac  mov     edx, 4Bh ; 'K'; unsigned __int64
0x18009cbb1  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x18009cbb6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009cbbb  test    eax, eax
0x18009cbbd  js      short loc_18009CC13
0x18009cbbf  lea     rax, [rsp+118h+dwDisposition]
0x18009cbc4  mov     [rsp+118h+dwDisposition], 0
0x18009cbcc  mov     [rsp+118h+lpdwDisposition], rax; lpdwDisposition
0x18009cbd1  lea     rdx, [rsp+118h+SubKey]; lpSubKey
0x18009cbd6  mov     [rsp+118h+phkResult], rbx; phkResult
0x18009cbdb  xor     r9d, r9d; lpClass
0x18009cbde  mov     [rsp+118h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009cbe7  xor     r8d, r8d; Reserved
0x18009cbea  mov     [rsp+118h+samDesired], 4; samDesired
0x18009cbf2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18009cbf9  mov     [rsp+118h+dwOptions], 1; dwOptions
0x18009cc01  call    cs:__imp_RegCreateKeyExW
0x18009cc07  test    eax, eax
0x18009cc09  jle     short loc_18009CC13
0x18009cc0b  movzx   eax, ax
0x18009cc0e  or      eax, 80070000h
0x18009cc13  mov     rcx, [rsp+118h+var_18]
0x18009cc1b  xor     rcx, rsp; StackCookie
0x18009cc1e  call    __security_check_cookie
0x18009cc23  add     rsp, 110h
0x18009cc2a  pop     rbx
0x18009cc2b  retn
```
