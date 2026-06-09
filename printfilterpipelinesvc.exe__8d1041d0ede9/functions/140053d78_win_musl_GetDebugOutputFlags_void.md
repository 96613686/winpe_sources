# win_musl::GetDebugOutputFlags(void)

- ea: `0x140053d78`
- end: `0x140053e34`
- name: `?GetDebugOutputFlags@win_musl@@YAKXZ`
- size: `188`
- prototype: `unsigned int __fastcall(win_musl *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140053ac4`

## callees

- `0x140053d78`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140053e22`
- `ADVAPI32!RegCloseKey` at `0x140053e22`
- `ADVAPI32!RegOpenKeyExW` at `0x140053dcd`
- `ADVAPI32!RegOpenKeyExW` at `0x140053dcd`
- `ADVAPI32!RegQueryValueExW` at `0x140053dfb`
- `ADVAPI32!RegQueryValueExW` at `0x140053dfb`

## string_xrefs

- `0x140053db1`: `Software\Microsoft\Windows\CurrentVersion\DocumentServices`

## pseudocode

```c
__int64 __fastcall win_musl::GetDebugOutputFlags(win_musl *this)
{
  DWORD Type; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  int Data; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  if ( !_interlockedbittestandset(&dword_1400811F0, 0x1Eu) )
  {
    hKey = 0;
    Data = 0;
    cbData = 4;
    Type = 0;
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\DocumentServices",
            0,
            1u,
            &hKey) )
    {
      if ( !RegQueryValueExW(hKey, L"DebugOutputFlags", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
        dword_1400811F0 = Data | 0x40000000;
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)dword_1400811F0;
}

```

## disassembly

```asm
0x140053d78  push    rbp
0x140053d7a  mov     rbp, rsp
0x140053d7d  sub     rsp, 30h
0x140053d81  lock bts cs:dword_1400811F0, 1Eh
0x140053d8a  jb      loc_140053E28
0x140053d90  lea     rax, [rbp+hKey]
0x140053d94  mov     [rbp+hKey], 0
0x140053d9c  mov     r9d, 1; samDesired
0x140053da2  mov     [rsp+30h+phkResult], rax; phkResult
0x140053da7  xor     r8d, r8d; ulOptions
0x140053daa  mov     [rbp+Data], 0
0x140053db1  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140053db8  mov     [rbp+cbData], 4
0x140053dbf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140053dc6  mov     [rbp+Type], 0
0x140053dcd  call    cs:__imp_RegOpenKeyExW
0x140053dd3  test    eax, eax
0x140053dd5  jnz     short loc_140053E28
0x140053dd7  mov     rcx, [rbp+hKey]; hKey
0x140053ddb  lea     rax, [rbp+cbData]
0x140053ddf  mov     [rsp+30h+lpcbData], rax; lpcbData
0x140053de4  lea     r9, [rbp+Type]; lpType
0x140053de8  lea     rax, [rbp+Data]
0x140053dec  xor     r8d, r8d; lpReserved
0x140053def  lea     rdx, aDebugoutputfla; "DebugOutputFlags"
0x140053df6  mov     [rsp+30h+phkResult], rax; lpData
0x140053dfb  call    cs:__imp_RegQueryValueExW
0x140053e01  test    eax, eax
0x140053e03  jnz     short loc_140053E1E
0x140053e05  cmp     [rbp+Type], 4
0x140053e09  jnz     short loc_140053E1E
0x140053e0b  cmp     [rbp+cbData], 4
0x140053e0f  jnz     short loc_140053E1E
0x140053e11  mov     eax, [rbp+Data]
0x140053e14  bts     eax, 1Eh
0x140053e18  mov     cs:dword_1400811F0, eax
0x140053e1e  mov     rcx, [rbp+hKey]; hKey
0x140053e22  call    cs:__imp_RegCloseKey
0x140053e28  mov     eax, cs:dword_1400811F0
0x140053e2e  add     rsp, 30h
0x140053e32  pop     rbp
0x140053e33  retn
```
