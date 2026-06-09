# PuLoadDebugFlagsFromRegStr

- ea: `0x180002994`
- end: `0x180002a48`
- name: `PuLoadDebugFlagsFromRegStr`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180001948`

## callees

- `0x180002994`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180002a16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180002a16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002a32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002a32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800029d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800029d0`

## string_xrefs

- `0x1800029c0`: `System\CurrentControlSet\Services\W3SVC\Parameters\HWEBCORE`

## pseudocode

```c
__int64 __fastcall PuLoadDebugFlagsFromRegStr(__int64 a1, DWORD a2)
{
  unsigned int v2; // ebx
  __int64 Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  Type = a2;
  Data = a1;
  hKey = 0;
  v2 = 0;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\HWEBCORE",
          0,
          0x20019u,
          &hKey) )
  {
    LODWORD(Data) = 0;
    cbData = 4;
    Type = 0;
    if ( hKey && !RegQueryValueExA(hKey, "DebugFlags", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v2 = Data;
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x180002994  mov     [rsp-10h+Type], edx
0x180002998  mov     [rsp-10h+Data], rcx
0x18000299d  push    rbp
0x18000299e  push    rbx
0x18000299f  mov     rbp, rsp
0x1800029a2  sub     rsp, 38h
0x1800029a6  lea     rax, [rbp+hKey]
0x1800029aa  mov     [rbp+hKey], 0
0x1800029b2  mov     r9d, 20019h; samDesired
0x1800029b8  mov     [rsp+38h+phkResult], rax; phkResult
0x1800029bd  xor     r8d, r8d; ulOptions
0x1800029c0  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\W3"...
0x1800029c7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800029ce  xor     ebx, ebx
0x1800029d0  call    cs:__imp_RegOpenKeyExA
0x1800029d7  nop     dword ptr [rax+rax+00h]
0x1800029dc  test    eax, eax
0x1800029de  jnz     short loc_180002A3E
0x1800029e0  mov     rcx, [rbp+hKey]; hKey
0x1800029e4  mov     dword ptr [rbp+Data], ebx
0x1800029e7  mov     [rbp+cbData], 4
0x1800029ee  mov     [rbp+Type], ebx
0x1800029f1  test    rcx, rcx
0x1800029f4  jz      short loc_180002A2E
0x1800029f6  lea     rax, [rbp+cbData]
0x1800029fa  xor     r8d, r8d; lpReserved
0x1800029fd  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180002a02  lea     r9, [rbp+Type]; lpType
0x180002a06  lea     rax, [rbp+Data]
0x180002a0a  lea     rdx, ValueName; "DebugFlags"
0x180002a11  mov     [rsp+38h+phkResult], rax; lpData
0x180002a16  call    cs:__imp_RegQueryValueExA
0x180002a1d  nop     dword ptr [rax+rax+00h]
0x180002a22  test    eax, eax
0x180002a24  jnz     short loc_180002A2E
0x180002a26  cmp     [rbp+Type], 4
0x180002a2a  cmovz   ebx, dword ptr [rbp+Data]
0x180002a2e  mov     rcx, [rbp+hKey]; hKey
0x180002a32  call    cs:__imp_RegCloseKey
0x180002a39  nop     dword ptr [rax+rax+00h]
0x180002a3e  mov     eax, ebx
0x180002a40  add     rsp, 38h
0x180002a44  pop     rbx
0x180002a45  pop     rbp
0x180002a46  retn
```
