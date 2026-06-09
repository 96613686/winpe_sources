# RegistryBasedThrottle::WriteLoggingLocalTickCount(char const *)

- ea: `0x18008bcd0`
- end: `0x18008bdfc`
- name: `?WriteLoggingLocalTickCount@RegistryBasedThrottle@@QEAAJPEBD@Z`
- size: `300`
- prototype: `__int64 __fastcall(RegistryBasedThrottle *__hidden this, LPCSTR lpValueName)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18007ca60`
- `0x18007cba0`
- `0x18007cce0`
- `0x18007cf28`

## callees

- `0x18008ae94`
- `0x18008bcd0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18008bdc9`
- `ADVAPI32!RegCloseKey` at `0x18008bddd`
- `ADVAPI32!RegCloseKey` at `0x18008bdc9`
- `ADVAPI32!RegCloseKey` at `0x18008bddd`
- `ADVAPI32!RegSetValueExA` at `0x18008bdab`
- `ADVAPI32!RegSetValueExA` at `0x18008bdab`
- `ADVAPI32!RegCreateKeyExA` at `0x18008bd75`
- `ADVAPI32!RegCreateKeyExA` at `0x18008bd75`
- `ADVAPI32!RegOpenCurrentUser` at `0x18008bd19`
- `ADVAPI32!RegOpenCurrentUser` at `0x18008bd19`
- `KERNEL32!GetTickCount64` at `0x18008bcf6`
- `KERNEL32!GetTickCount64` at `0x18008bcf6`

## pseudocode

```c
__int64 __fastcall RegistryBasedThrottle::WriteLoggingLocalTickCount(RegistryBasedThrottle *this, LPCSTR lpValueName)
{
  unsigned int v4; // ebx
  const CHAR *CurrentProcessTickCountRegistryKey; // rax
  BYTE Data[24]; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+20h] BYREF

  phkResult = 0;
  hKey = 0;
  *(_QWORD *)Data = GetTickCount64();
  v4 = -2147467259;
  if ( !RegOpenCurrentUser(0x20106u, &phkResult) )
  {
    CurrentProcessTickCountRegistryKey = RegistryBasedThrottle::GetCurrentProcessTickCountRegistryKey(this);
    if ( !RegCreateKeyExA(phkResult, CurrentProcessTickCountRegistryKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0) )
    {
      v4 = RegSetValueExA(hKey, lpValueName, 0, 0xBu, Data, 8u) != 0 ? 0x80004005 : 0;
      RegCloseKey(hKey);
    }
    RegCloseKey(phkResult);
  }
  return v4;
}

```

## disassembly

```asm
0x18008bcd0  mov     rax, rsp
0x18008bcd3  mov     [rax+8], rbx
0x18008bcd7  mov     [rax+10h], rsi
0x18008bcdb  push    rdi
0x18008bcdc  sub     rsp, 60h
0x18008bce0  mov     rsi, rdx
0x18008bce3  mov     qword ptr [rax+20h], 0
0x18008bceb  mov     rdi, rcx
0x18008bcee  mov     qword ptr [rax+18h], 0
0x18008bcf6  call    cs:__imp_GetTickCount64
0x18008bcfd  nop     dword ptr [rax+rax+00h]
0x18008bd02  lea     rdx, [rsp+68h+phkResult]; phkResult
0x18008bd0a  mov     ecx, 20106h; samDesired
0x18008bd0f  mov     qword ptr [rsp+68h+Data], rax
0x18008bd14  mov     ebx, 80004005h
0x18008bd19  call    cs:__imp_RegOpenCurrentUser
0x18008bd20  nop     dword ptr [rax+rax+00h]
0x18008bd25  test    eax, eax
0x18008bd27  jnz     loc_18008BDE9
0x18008bd2d  mov     rcx, rdi; this
0x18008bd30  call    ?GetCurrentProcessTickCountRegistryKey@RegistryBasedThrottle@@AEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessTickCountRegistryKey(void)
0x18008bd35  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18008bd3e  lea     rcx, [rsp+68h+hKey]
0x18008bd46  mov     [rsp+68h+var_30], rcx; phkResult
0x18008bd4b  xor     r9d, r9d; lpClass
0x18008bd4e  mov     rcx, [rsp+68h+phkResult]; hKey
0x18008bd56  xor     r8d, r8d; Reserved
0x18008bd59  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18008bd62  mov     rdx, rax; lpSubKey
0x18008bd65  mov     [rsp+68h+samDesired], 2000000h; samDesired
0x18008bd6d  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18008bd75  call    cs:__imp_RegCreateKeyExA
0x18008bd7c  nop     dword ptr [rax+rax+00h]
0x18008bd81  test    eax, eax
0x18008bd83  jnz     short loc_18008BDD5
0x18008bd85  mov     rcx, [rsp+68h+hKey]; hKey
0x18008bd8d  lea     rax, [rsp+68h+Data]
0x18008bd92  mov     [rsp+68h+samDesired], 8; cbData
0x18008bd9a  mov     r9d, 0Bh; dwType
0x18008bda0  xor     r8d, r8d; Reserved
0x18008bda3  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18008bda8  mov     rdx, rsi; lpValueName
0x18008bdab  call    cs:__imp_RegSetValueExA
0x18008bdb2  nop     dword ptr [rax+rax+00h]
0x18008bdb7  xor     ecx, ecx
0x18008bdb9  sub     ecx, eax
0x18008bdbb  neg     ecx
0x18008bdbd  mov     rcx, [rsp+68h+hKey]; hKey
0x18008bdc5  sbb     eax, eax
0x18008bdc7  and     ebx, eax
0x18008bdc9  call    cs:__imp_RegCloseKey
0x18008bdd0  nop     dword ptr [rax+rax+00h]
0x18008bdd5  mov     rcx, [rsp+68h+phkResult]; hKey
0x18008bddd  call    cs:__imp_RegCloseKey
0x18008bde4  nop     dword ptr [rax+rax+00h]
0x18008bde9  mov     rsi, [rsp+68h+arg_8]
0x18008bdee  mov     eax, ebx
0x18008bdf0  mov     rbx, [rsp+68h+arg_0]
0x18008bdf5  add     rsp, 60h
0x18008bdf9  pop     rdi
0x18008bdfa  retn
```
