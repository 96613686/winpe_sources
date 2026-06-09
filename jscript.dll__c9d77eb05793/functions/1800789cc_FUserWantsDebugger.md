# FUserWantsDebugger

- ea: `0x1800789cc`
- end: `0x180078a9f`
- name: `FUserWantsDebugger`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003ff0`

## callees

- `0x1800789cc`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180078a90`
- `ADVAPI32!RegCloseKey` at `0x180078a90`
- `ADVAPI32!RegQueryValueExA` at `0x180078a4a`
- `ADVAPI32!RegQueryValueExA` at `0x180078a4a`
- `ADVAPI32!RegSetValueExA` at `0x180078a81`
- `ADVAPI32!RegSetValueExA` at `0x180078a81`
- `ADVAPI32!RegCreateKeyExA` at `0x180078a1c`
- `ADVAPI32!RegCreateKeyExA` at `0x180078a1c`

## pseudocode

```c
__int64 FUserWantsDebugger()
{
  unsigned int v0; // ebx
  int Data; // [rsp+70h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+20h] BYREF
  DWORD Type; // [rsp+80h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+30h] BYREF

  v0 = 0;
  cbData = 4;
  hKey = 0;
  Type = 0;
  Data = 0;
  if ( !RegCreateKeyExA(
          HKEY_CURRENT_USER,
          "Software\\Microsoft\\Windows Script\\Settings",
          0,
          0,
          0,
          0x2000000u,
          0,
          &hKey,
          0) )
  {
    if ( RegQueryValueExA(hKey, "JITDebug", 0, &Type, (LPBYTE)&Data, &cbData) )
      RegSetValueExA(hKey, "JITDebug", 0, 4u, (const BYTE *)&Data, 4u);
    else
      LOBYTE(v0) = Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x1800789cc  push    rbp
0x1800789ce  push    rbx
0x1800789cf  mov     rbp, rsp
0x1800789d2  sub     rsp, 58h
0x1800789d6  xor     ebx, ebx
0x1800789d8  mov     [rbp+cbData], 4
0x1800789df  mov     [rsp+58h+lpdwDisposition], rbx; lpdwDisposition
0x1800789e4  lea     rax, [rbp+hKey]
0x1800789e8  mov     [rsp+58h+phkResult], rax; phkResult
0x1800789ed  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows Script\\Se"...
0x1800789f4  mov     [rsp+58h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800789f9  xor     r9d, r9d; lpClass
0x1800789fc  mov     [rsp+58h+samDesired], 2000000h; samDesired
0x180078a04  xor     r8d, r8d; Reserved
0x180078a07  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180078a0e  mov     [rsp+58h+dwOptions], ebx; dwOptions
0x180078a12  mov     [rbp+hKey], rbx
0x180078a16  mov     [rbp+Type], ebx
0x180078a19  mov     [rbp+Data], ebx
0x180078a1c  call    cs:__imp_RegCreateKeyExA
0x180078a22  test    eax, eax
0x180078a24  jnz     short loc_180078A87
0x180078a26  mov     rcx, [rbp+hKey]; hKey
0x180078a2a  lea     rax, [rbp+cbData]
0x180078a2e  mov     qword ptr [rsp+58h+samDesired], rax; lpcbData
0x180078a33  lea     r9, [rbp+Type]; lpType
0x180078a37  lea     rax, [rbp+Data]
0x180078a3b  xor     r8d, r8d; lpReserved
0x180078a3e  lea     rdx, aJitdebug; "JITDebug"
0x180078a45  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180078a4a  call    cs:__imp_RegQueryValueExA
0x180078a50  test    eax, eax
0x180078a52  jnz     short loc_180078A5C
0x180078a54  cmp     [rbp+Data], ebx
0x180078a57  setnz   bl
0x180078a5a  jmp     short loc_180078A87
0x180078a5c  mov     rcx, [rbp+hKey]; hKey
0x180078a60  lea     rax, [rbp+Data]
0x180078a64  mov     [rsp+58h+samDesired], 4; cbData
0x180078a6c  lea     rdx, aJitdebug; "JITDebug"
0x180078a73  mov     r9d, 4; dwType
0x180078a79  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180078a7e  xor     r8d, r8d; Reserved
0x180078a81  call    cs:__imp_RegSetValueExA
0x180078a87  mov     rcx, [rbp+hKey]; hKey
0x180078a8b  test    rcx, rcx
0x180078a8e  jz      short loc_180078A96
0x180078a90  call    cs:__imp_RegCloseKey
0x180078a96  mov     eax, ebx
0x180078a98  add     rsp, 58h
0x180078a9c  pop     rbx
0x180078a9d  pop     rbp
0x180078a9e  retn
```
