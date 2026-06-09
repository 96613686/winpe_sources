# NoRun(void)

- ea: `0x18006a480`
- end: `0x18006a600`
- name: `?NoRun@@YAHXZ`
- size: `384`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001acc0`
- `0x18001bc88`
- `0x1800534a8`
- `0x18006eaf4`

## callees

- `0x180017ca0`
- `0x180065230`
- `0x18006a480`

## import_xrefs

- `ADVAPI32!DeregisterEventSource` at `0x18006a50a`
- `ADVAPI32!DeregisterEventSource` at `0x18006a50a`
- `ADVAPI32!ReportEventA` at `0x18006a501`
- `ADVAPI32!ReportEventA` at `0x18006a501`
- `ADVAPI32!RegCloseKey` at `0x18006a56f`
- `ADVAPI32!RegCloseKey` at `0x18006a5ed`
- `ADVAPI32!RegCloseKey` at `0x18006a56f`
- `ADVAPI32!RegCloseKey` at `0x18006a5ed`
- `ADVAPI32!RegQueryValueExA` at `0x18006a563`
- `ADVAPI32!RegQueryValueExA` at `0x18006a5e1`
- `ADVAPI32!RegQueryValueExA` at `0x18006a563`
- `ADVAPI32!RegQueryValueExA` at `0x18006a5e1`
- `ADVAPI32!RegOpenKeyExA` at `0x18006a535`
- `ADVAPI32!RegOpenKeyExA` at `0x18006a5b3`
- `ADVAPI32!RegOpenKeyExA` at `0x18006a535`
- `ADVAPI32!RegOpenKeyExA` at `0x18006a5b3`

## pseudocode

```c
_BOOL8 __fastcall NoRun(HHUrlSecurityManager::InternalSecurityManager *a1)
{
  HANDLE v1; // rbx
  LSTATUS v2; // ebx
  LSTATUS v4; // ebx
  LPCSTR Strings; // [rsp+50h] [rbp-29h] BYREF
  HANDLE hEventLog[14]; // [rsp+60h] [rbp-19h] BYREF
  int Data; // [rsp+E0h] [rbp+67h] BYREF
  DWORD cbData; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD Type; // [rsp+F0h] [rbp+77h] BYREF
  HKEY phkResult; // [rsp+F8h] [rbp+7Fh] BYREF

  cbData = 4;
  phkResult = 0;
  Data = 0;
  Type = 0;
  HHUrlSecurityManager::InternalSecurityManager::Init(a1);
  if ( *(_DWORD *)&dword_18008C2D8 == 1 )
  {
    HHEventManager::HHEventManager((HHEventManager *)hEventLog);
    v1 = hEventLog[0];
    Strings = (LPCSTR)hEventLog[8];
    if ( hEventLog[0] )
    {
      ReportEventA(hEventLog[0], 4u, 0, 0x773u, 0, 1u, 0, &Strings, 0);
      DeregisterEventSource(v1);
    }
    return 1;
  }
  if ( RegOpenKeyExA(
         HKEY_CURRENT_USER,
         "Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer",
         0,
         0x20019u,
         &phkResult)
    || (v2 = RegQueryValueExA(phkResult, "NoRun", 0, &Type, (LPBYTE)&Data, &cbData), RegCloseKey(phkResult), v2) )
  {
    cbData = 4;
    if ( !RegOpenKeyExA(
            HKEY_LOCAL_MACHINE,
            "Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer",
            0,
            0x20019u,
            &phkResult) )
    {
      v4 = RegQueryValueExA(phkResult, "NoRun", 0, &Type, (LPBYTE)&Data, &cbData);
      RegCloseKey(phkResult);
      if ( !v4 && Data == 1 )
        return 1;
    }
    return 0;
  }
  return Data == 1;
}

```

## disassembly

```asm
0x18006a480  push    rbp
0x18006a482  push    rbx
0x18006a483  push    rsi
0x18006a484  push    rdi
0x18006a485  lea     rbp, [rsp-3Fh]
0x18006a48a  sub     rsp, 0B8h
0x18006a491  xor     edi, edi
0x18006a493  mov     [rbp+57h+cbData], 4
0x18006a49a  mov     [rbp+57h+phkResult], rdi
0x18006a49e  mov     [rbp+57h+Data], edi
0x18006a4a1  mov     [rbp+57h+Type], edi
0x18006a4a4  call    ?Init@InternalSecurityManager@HHUrlSecurityManager@@QEAAXXZ; HHUrlSecurityManager::InternalSecurityManager::Init(void)
0x18006a4a9  mov     esi, 1
0x18006a4ae  cmp     cs:dword_18008C2D8, esi
0x18006a4b4  jnz     short loc_18006A515
0x18006a4b6  lea     rcx, [rbp+57h+hEventLog]; this
0x18006a4ba  call    ??0HHEventManager@@QEAA@XZ; HHEventManager::HHEventManager(void)
0x18006a4bf  mov     rbx, [rbp+57h+hEventLog]
0x18006a4c3  mov     rax, [rbp+57h+var_30]
0x18006a4c7  mov     [rbp+57h+Strings], rax
0x18006a4cb  test    rbx, rbx
0x18006a4ce  jz      loc_18006A5FC
0x18006a4d4  mov     [rsp+0D0h+lpRawData], rdi; lpRawData
0x18006a4d9  lea     rax, [rbp+57h+Strings]
0x18006a4dd  mov     [rsp+0D0h+lpStrings], rax; lpStrings
0x18006a4e2  xor     r8d, r8d; wCategory
0x18006a4e5  mov     [rsp+0D0h+dwDataSize], edi; dwDataSize
0x18006a4e9  mov     edx, 4; wType
0x18006a4ee  mov     [rsp+0D0h+wNumStrings], si; wNumStrings
0x18006a4f3  mov     r9d, 773h; dwEventID
0x18006a4f9  mov     rcx, rbx; hEventLog
0x18006a4fc  mov     [rsp+0D0h+lpUserSid], rdi; lpUserSid
0x18006a501  call    cs:__imp_ReportEventA
0x18006a507  mov     rcx, rbx; hEventLog
0x18006a50a  call    cs:__imp_DeregisterEventSource
0x18006a510  jmp     loc_18006A5FC
0x18006a515  lea     rax, [rbp+57h+phkResult]
0x18006a519  mov     r9d, 20019h; samDesired
0x18006a51f  xor     r8d, r8d; ulOptions
0x18006a522  mov     [rsp+0D0h+lpUserSid], rax; phkResult
0x18006a527  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006a52e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18006a535  call    cs:__imp_RegOpenKeyExA
0x18006a53b  test    eax, eax
0x18006a53d  jnz     short loc_18006A58C
0x18006a53f  mov     rcx, [rbp+57h+phkResult]; hKey
0x18006a543  lea     rax, [rbp+57h+cbData]
0x18006a547  mov     qword ptr [rsp+0D0h+wNumStrings], rax; lpcbData
0x18006a54c  lea     r9, [rbp+57h+Type]; lpType
0x18006a550  lea     rax, [rbp+57h+Data]
0x18006a554  xor     r8d, r8d; lpReserved
0x18006a557  lea     rdx, aNorun; "NoRun"
0x18006a55e  mov     [rsp+0D0h+lpUserSid], rax; lpData
0x18006a563  call    cs:__imp_RegQueryValueExA
0x18006a569  mov     rcx, [rbp+57h+phkResult]; hKey
0x18006a56d  mov     ebx, eax
0x18006a56f  call    cs:__imp_RegCloseKey
0x18006a575  test    ebx, ebx
0x18006a577  jnz     short loc_18006A58C
0x18006a579  cmp     [rbp+57h+Data], esi
0x18006a57c  jz      short loc_18006A5FC
0x18006a57e  xor     eax, eax
0x18006a580  add     rsp, 0B8h
0x18006a587  pop     rdi
0x18006a588  pop     rsi
0x18006a589  pop     rbx
0x18006a58a  pop     rbp
0x18006a58b  retn
0x18006a58c  lea     rax, [rbp+57h+phkResult]
0x18006a590  mov     [rbp+57h+cbData], 4
0x18006a597  mov     r9d, 20019h; samDesired
0x18006a59d  mov     [rsp+0D0h+lpUserSid], rax; phkResult
0x18006a5a2  xor     r8d, r8d; ulOptions
0x18006a5a5  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006a5ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006a5b3  call    cs:__imp_RegOpenKeyExA
0x18006a5b9  test    eax, eax
0x18006a5bb  jnz     short loc_18006A57E
0x18006a5bd  mov     rcx, [rbp+57h+phkResult]; hKey
0x18006a5c1  lea     rax, [rbp+57h+cbData]
0x18006a5c5  mov     qword ptr [rsp+0D0h+wNumStrings], rax; lpcbData
0x18006a5ca  lea     r9, [rbp+57h+Type]; lpType
0x18006a5ce  lea     rax, [rbp+57h+Data]
0x18006a5d2  xor     r8d, r8d; lpReserved
0x18006a5d5  lea     rdx, aNorun; "NoRun"
0x18006a5dc  mov     [rsp+0D0h+lpUserSid], rax; lpData
0x18006a5e1  call    cs:__imp_RegQueryValueExA
0x18006a5e7  mov     rcx, [rbp+57h+phkResult]; hKey
0x18006a5eb  mov     ebx, eax
0x18006a5ed  call    cs:__imp_RegCloseKey
0x18006a5f3  test    ebx, ebx
0x18006a5f5  jnz     short loc_18006A57E
0x18006a5f7  cmp     [rbp+57h+Data], esi
0x18006a5fa  jnz     short loc_18006A57E
0x18006a5fc  mov     eax, esi
0x18006a5fe  jmp     short loc_18006A580
```
