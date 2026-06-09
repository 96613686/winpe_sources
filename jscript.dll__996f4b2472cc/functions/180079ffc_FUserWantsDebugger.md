# FUserWantsDebugger

- ea: `0x180079ffc`
- end: `0x18007a0e8`
- name: `FUserWantsDebugger`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032410`

## callees

- `0x180079ffc`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18007a0d2`
- `ADVAPI32!RegCloseKey` at `0x18007a0d2`
- `ADVAPI32!RegQueryValueExA` at `0x18007a080`
- `ADVAPI32!RegQueryValueExA` at `0x18007a080`
- `ADVAPI32!RegSetValueExA` at `0x18007a0bd`
- `ADVAPI32!RegSetValueExA` at `0x18007a0bd`
- `ADVAPI32!RegCreateKeyExA` at `0x18007a04c`
- `ADVAPI32!RegCreateKeyExA` at `0x18007a04c`

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
0x180079ffc  push    rbp
0x180079ffe  push    rbx
0x180079fff  mov     rbp, rsp
0x18007a002  sub     rsp, 58h
0x18007a006  xor     ebx, ebx
0x18007a008  mov     [rbp+cbData], 4
0x18007a00f  mov     [rsp+58h+lpdwDisposition], rbx; lpdwDisposition
0x18007a014  lea     rax, [rbp+hKey]
0x18007a018  mov     [rsp+58h+phkResult], rax; phkResult
0x18007a01d  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows Script\\Se"...
0x18007a024  mov     [rsp+58h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18007a029  xor     r9d, r9d; lpClass
0x18007a02c  mov     [rsp+58h+samDesired], 2000000h; samDesired
0x18007a034  xor     r8d, r8d; Reserved
0x18007a037  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18007a03e  mov     [rsp+58h+dwOptions], ebx; dwOptions
0x18007a042  mov     [rbp+hKey], rbx
0x18007a046  mov     [rbp+Type], ebx
0x18007a049  mov     [rbp+Data], ebx
0x18007a04c  call    cs:__imp_RegCreateKeyExA
0x18007a053  nop     dword ptr [rax+rax+00h]
0x18007a058  test    eax, eax
0x18007a05a  jnz     short loc_18007A0C9
0x18007a05c  mov     rcx, [rbp+hKey]; hKey
0x18007a060  lea     rax, [rbp+cbData]
0x18007a064  mov     qword ptr [rsp+58h+samDesired], rax; lpcbData
0x18007a069  lea     r9, [rbp+Type]; lpType
0x18007a06d  lea     rax, [rbp+Data]
0x18007a071  xor     r8d, r8d; lpReserved
0x18007a074  lea     rdx, aJitdebug; "JITDebug"
0x18007a07b  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18007a080  call    cs:__imp_RegQueryValueExA
0x18007a087  nop     dword ptr [rax+rax+00h]
0x18007a08c  test    eax, eax
0x18007a08e  jnz     short loc_18007A098
0x18007a090  cmp     [rbp+Data], ebx
0x18007a093  setnz   bl
0x18007a096  jmp     short loc_18007A0C9
0x18007a098  mov     rcx, [rbp+hKey]; hKey
0x18007a09c  lea     rax, [rbp+Data]
0x18007a0a0  mov     [rsp+58h+samDesired], 4; cbData
0x18007a0a8  lea     rdx, aJitdebug; "JITDebug"
0x18007a0af  mov     r9d, 4; dwType
0x18007a0b5  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18007a0ba  xor     r8d, r8d; Reserved
0x18007a0bd  call    cs:__imp_RegSetValueExA
0x18007a0c4  nop     dword ptr [rax+rax+00h]
0x18007a0c9  mov     rcx, [rbp+hKey]; hKey
0x18007a0cd  test    rcx, rcx
0x18007a0d0  jz      short loc_18007A0DE
0x18007a0d2  call    cs:__imp_RegCloseKey
0x18007a0d9  nop     dword ptr [rax+rax+00h]
0x18007a0de  mov     eax, ebx
0x18007a0e0  add     rsp, 58h
0x18007a0e4  pop     rbx
0x18007a0e5  pop     rbp
0x18007a0e6  retn
```
