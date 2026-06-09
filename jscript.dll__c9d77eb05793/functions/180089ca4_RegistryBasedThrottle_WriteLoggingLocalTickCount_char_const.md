# RegistryBasedThrottle::WriteLoggingLocalTickCount(char const *)

- ea: `0x180089ca4`
- end: `0x180089dab`
- name: `?WriteLoggingLocalTickCount@RegistryBasedThrottle@@QEAAJPEBD@Z`
- size: `263`
- prototype: `__int64 __fastcall(RegistryBasedThrottle *__hidden this, LPCSTR lpValueName)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18007b250`
- `0x18007b384`
- `0x18007b4b8`
- `0x18007b6f0`

## callees

- `0x180088fc0`
- `0x180089ca4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180089d85`
- `ADVAPI32!RegCloseKey` at `0x180089d93`
- `ADVAPI32!RegCloseKey` at `0x180089d85`
- `ADVAPI32!RegCloseKey` at `0x180089d93`
- `ADVAPI32!RegSetValueExA` at `0x180089d6d`
- `ADVAPI32!RegSetValueExA` at `0x180089d6d`
- `ADVAPI32!RegCreateKeyExA` at `0x180089d3d`
- `ADVAPI32!RegCreateKeyExA` at `0x180089d3d`
- `ADVAPI32!RegOpenCurrentUser` at `0x180089ce7`
- `ADVAPI32!RegOpenCurrentUser` at `0x180089ce7`
- `KERNEL32!GetTickCount64` at `0x180089cca`
- `KERNEL32!GetTickCount64` at `0x180089cca`

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
0x180089ca4  mov     rax, rsp
0x180089ca7  mov     [rax+8], rbx
0x180089cab  mov     [rax+10h], rsi
0x180089caf  push    rdi
0x180089cb0  sub     rsp, 60h
0x180089cb4  mov     rsi, rdx
0x180089cb7  mov     qword ptr [rax+20h], 0
0x180089cbf  mov     rdi, rcx
0x180089cc2  mov     qword ptr [rax+18h], 0
0x180089cca  call    cs:__imp_GetTickCount64
0x180089cd0  lea     rdx, [rsp+68h+phkResult]; phkResult
0x180089cd8  mov     ecx, 20106h; samDesired
0x180089cdd  mov     qword ptr [rsp+68h+Data], rax
0x180089ce2  mov     ebx, 80004005h
0x180089ce7  call    cs:__imp_RegOpenCurrentUser
0x180089ced  test    eax, eax
0x180089cef  jnz     loc_180089D99
0x180089cf5  mov     rcx, rdi; this
0x180089cf8  call    ?GetCurrentProcessTickCountRegistryKey@RegistryBasedThrottle@@AEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessTickCountRegistryKey(void)
0x180089cfd  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180089d06  lea     rcx, [rsp+68h+hKey]
0x180089d0e  mov     [rsp+68h+var_30], rcx; phkResult
0x180089d13  xor     r9d, r9d; lpClass
0x180089d16  mov     rcx, [rsp+68h+phkResult]; hKey
0x180089d1e  xor     r8d, r8d; Reserved
0x180089d21  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180089d2a  mov     rdx, rax; lpSubKey
0x180089d2d  mov     [rsp+68h+samDesired], 2000000h; samDesired
0x180089d35  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180089d3d  call    cs:__imp_RegCreateKeyExA
0x180089d43  test    eax, eax
0x180089d45  jnz     short loc_180089D8B
0x180089d47  mov     rcx, [rsp+68h+hKey]; hKey
0x180089d4f  lea     rax, [rsp+68h+Data]
0x180089d54  mov     [rsp+68h+samDesired], 8; cbData
0x180089d5c  mov     r9d, 0Bh; dwType
0x180089d62  xor     r8d, r8d; Reserved
0x180089d65  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180089d6a  mov     rdx, rsi; lpValueName
0x180089d6d  call    cs:__imp_RegSetValueExA
0x180089d73  xor     ecx, ecx
0x180089d75  sub     ecx, eax
0x180089d77  neg     ecx
0x180089d79  mov     rcx, [rsp+68h+hKey]; hKey
0x180089d81  sbb     eax, eax
0x180089d83  and     ebx, eax
0x180089d85  call    cs:__imp_RegCloseKey
0x180089d8b  mov     rcx, [rsp+68h+phkResult]; hKey
0x180089d93  call    cs:__imp_RegCloseKey
0x180089d99  mov     rsi, [rsp+68h+arg_8]
0x180089d9e  mov     eax, ebx
0x180089da0  mov     rbx, [rsp+68h+arg_0]
0x180089da5  add     rsp, 60h
0x180089da9  pop     rdi
0x180089daa  retn
```
