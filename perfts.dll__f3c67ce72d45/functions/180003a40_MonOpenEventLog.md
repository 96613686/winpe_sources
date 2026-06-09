# MonOpenEventLog

- ea: `0x180003a40`
- end: `0x180003ba3`
- name: `MonOpenEventLog`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800034c8`

## callees

- `0x180003a40`
- `0x180009930`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180003b4f`
- `ADVAPI32!RegCloseKey` at `0x180003b4f`
- `ADVAPI32!RegOpenKeyExW` at `0x180003b02`
- `ADVAPI32!RegOpenKeyExW` at `0x180003b02`
- `ADVAPI32!RegisterEventSourceW` at `0x180003b76`
- `ADVAPI32!RegisterEventSourceW` at `0x180003b76`
- `ADVAPI32!RegQueryValueExW` at `0x180003b34`
- `ADVAPI32!RegQueryValueExW` at `0x180003b34`

## pseudocode

```c
HANDLE MonOpenEventLog()
{
  LSTATUS v0; // eax
  int v1; // ecx
  HANDLE result; // rax
  DWORD cbData; // [rsp+30h] [rbp-69h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-65h] BYREF
  DWORD Type; // [rsp+38h] [rbp-61h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-59h] BYREF
  WCHAR ValueName[20]; // [rsp+48h] [rbp-51h] BYREF
  WCHAR SubKey[56]; // [rsp+70h] [rbp-29h] BYREF

  wcscpy(SubKey, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersiPerflib");
  hKey = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  wcscpy(ValueName, L"EvenogLevel");
  if ( !MESSAGE_LEVEL )
  {
    cbData = 4;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
    {
      MESSAGE_LEVEL = 1;
    }
    else
    {
      v0 = RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData);
      v1 = 1;
      if ( !v0 )
        v1 = *(_DWORD *)Data;
      MESSAGE_LEVEL = v1;
      RegCloseKey(hKey);
    }
  }
  result = hEventLog;
  if ( hEventLog || (result = RegisterEventSourceW(0, L"PerfTS"), (hEventLog = result) != 0) )
    ++dwLogUsers;
  return result;
}

```

## disassembly

```asm
0x180003a40  push    rbp
0x180003a42  lea     rbp, [rsp-57h]
0x180003a47  sub     rsp, 0F0h
0x180003a4e  mov     rax, cs:__security_cookie
0x180003a55  xor     rax, rsp
0x180003a58  mov     [rbp+57h+var_10], rax
0x180003a5c  cmp     cs:MESSAGE_LEVEL, 0
0x180003a63  movaps  xmm0, xmmword ptr cs:aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180003a6a  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+10h; "\\Microsoft\\Windows NT\\CurrentVersion"...
0x180003a71  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x180003a75  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+20h; "ft\\Windows NT\\CurrentVersion\\Perflib"
0x180003a7c  movaps  [rbp+57h+var_60], xmm0
0x180003a80  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+40h; "rrentVersion\\Perflib"
0x180003a87  movaps  [rbp+57h+var_70], xmm1
0x180003a8b  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+30h; "ws NT\\CurrentVersion\\Perflib"
0x180003a92  movaps  [rbp+57h+var_40], xmm0
0x180003a96  movups  xmm0, xmmword ptr cs:aSoftwareMicros+5Ah; "Perflib"
0x180003a9d  mov     [rbp+57h+hKey], 0
0x180003aa5  movaps  [rbp+57h+var_50], xmm1
0x180003aa9  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+50h; "sion\\Perflib"
0x180003ab0  movaps  [rbp+57h+var_30], xmm1
0x180003ab4  movups  xmm1, xmmword ptr cs:aEventloglevel; "EventLogLevel"
0x180003abb  mov     dword ptr [rbp+57h+Data], 0
0x180003ac2  movups  [rbp+57h+var_30+0Ah], xmm0
0x180003ac6  mov     [rbp+57h+Type], 0
0x180003acd  movups  xmm0, xmmword ptr cs:aEventloglevel+0Ch; "ogLevel"
0x180003ad4  mov     [rbp+57h+cbData], 0
0x180003adb  movups  xmmword ptr [rbp+57h+ValueName], xmm1
0x180003adf  movups  xmmword ptr [rbp+57h+ValueName+0Ch], xmm0
0x180003ae3  jnz     short loc_180003B61
0x180003ae5  lea     rax, [rbp+57h+hKey]
0x180003ae9  mov     r9d, 20019h; samDesired
0x180003aef  xor     r8d, r8d; ulOptions
0x180003af2  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180003af7  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180003afb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003b02  call    cs:__imp_RegOpenKeyExW
0x180003b08  mov     [rbp+57h+cbData], 4
0x180003b0f  test    eax, eax
0x180003b11  jnz     short loc_180003B57
0x180003b13  mov     rcx, [rbp+57h+hKey]; hKey
0x180003b17  lea     rax, [rbp+57h+cbData]
0x180003b1b  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x180003b20  lea     r9, [rbp+57h+Type]; lpType
0x180003b24  lea     rax, [rbp+57h+Data]
0x180003b28  xor     r8d, r8d; lpReserved
0x180003b2b  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x180003b2f  mov     [rsp+0F0h+phkResult], rax; lpData
0x180003b34  call    cs:__imp_RegQueryValueExW
0x180003b3a  test    eax, eax
0x180003b3c  mov     ecx, 1
0x180003b41  cmovz   ecx, dword ptr [rbp+57h+Data]
0x180003b45  mov     cs:MESSAGE_LEVEL, ecx
0x180003b4b  mov     rcx, [rbp+57h+hKey]; hKey
0x180003b4f  call    cs:__imp_RegCloseKey
0x180003b55  jmp     short loc_180003B61
0x180003b57  mov     cs:MESSAGE_LEVEL, 1
0x180003b61  mov     rax, cs:hEventLog
0x180003b68  test    rax, rax
0x180003b6b  jnz     short loc_180003B88
0x180003b6d  lea     rdx, SourceName; "PerfTS"
0x180003b74  xor     ecx, ecx; lpUNCServerName
0x180003b76  call    cs:__imp_RegisterEventSourceW
0x180003b7c  mov     cs:hEventLog, rax
0x180003b83  test    rax, rax
0x180003b86  jz      short loc_180003B8E
0x180003b88  inc     cs:dwLogUsers
0x180003b8e  mov     rcx, [rbp+57h+var_10]
0x180003b92  xor     rcx, rsp; StackCookie
0x180003b95  call    __security_check_cookie
0x180003b9a  add     rsp, 0F0h
0x180003ba1  pop     rbp
0x180003ba2  retn
```
