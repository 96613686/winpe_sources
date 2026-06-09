# pUtilGetSystemLastShutdownTime

- ea: `0x1800088d8`
- end: `0x180008988`
- name: `pUtilGetSystemLastShutdownTime`
- size: `176`
- prototype: `__int64 __fastcall(LPBYTE lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004e74`

## callees

- `0x1800088d8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000891d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000891d`
- `ADVAPI32!RegCloseKey` at `0x180008975`
- `ADVAPI32!RegCloseKey` at `0x180008975`
- `ADVAPI32!RegQueryValueExW` at `0x180008954`
- `ADVAPI32!RegQueryValueExW` at `0x180008954`

## pseudocode

```c
__int64 __fastcall pUtilGetSystemLastShutdownTime(LPBYTE lpData)
{
  unsigned int v2; // ebx
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Windows", 0, 1u, &hKey);
  if ( !v2 )
  {
    cbData = 8;
    v2 = RegQueryValueExW(hKey, L"ShutdownTime", 0, &Type, lpData, &cbData);
    if ( !v2 && Type != 3 )
      v2 = 13;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x1800088d8  mov     rax, rsp
0x1800088db  mov     [rax+8], rbx
0x1800088df  push    rdi
0x1800088e0  sub     rsp, 30h
0x1800088e4  mov     qword ptr [rax+20h], 0
0x1800088ec  mov     rdi, rcx
0x1800088ef  mov     dword ptr [rax+10h], 0
0x1800088f6  mov     r9d, 1; samDesired
0x1800088fc  mov     dword ptr [rax+18h], 0
0x180008903  lea     rax, [rax+20h]
0x180008907  xor     r8d, r8d; ulOptions
0x18000890a  mov     [rsp+38h+phkResult], rax; phkResult
0x18000890f  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Win"...
0x180008916  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000891d  call    cs:__imp_RegOpenKeyExW
0x180008923  mov     ebx, eax
0x180008925  test    eax, eax
0x180008927  jnz     short loc_18000896B
0x180008929  mov     rcx, [rsp+38h+hKey]; hKey
0x18000892e  lea     rax, [rsp+38h+cbData]
0x180008933  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180008938  lea     r9, [rsp+38h+Type]; lpType
0x18000893d  xor     r8d, r8d; lpReserved
0x180008940  mov     [rsp+38h+phkResult], rdi; lpData
0x180008945  lea     rdx, aShutdowntime; "ShutdownTime"
0x18000894c  mov     [rsp+38h+cbData], 8
0x180008954  call    cs:__imp_RegQueryValueExW
0x18000895a  mov     ebx, eax
0x18000895c  test    eax, eax
0x18000895e  jnz     short loc_18000896B
0x180008960  cmp     [rsp+38h+Type], 3
0x180008965  lea     eax, [rbx+0Dh]
0x180008968  cmovnz  ebx, eax
0x18000896b  mov     rcx, [rsp+38h+hKey]; hKey
0x180008970  test    rcx, rcx
0x180008973  jz      short loc_18000897B
0x180008975  call    cs:__imp_RegCloseKey
0x18000897b  mov     eax, ebx
0x18000897d  mov     rbx, [rsp+38h+arg_0]
0x180008982  add     rsp, 30h
0x180008986  pop     rdi
0x180008987  retn
```
