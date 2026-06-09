# CryptNetDebugFlagsInitOnceCallback

- ea: `0x180018890`
- end: `0x18001894d`
- name: `CryptNetDebugFlagsInitOnceCallback`
- size: `189`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180018890`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001891c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001891c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180018909`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180018909`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800188db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800188db`

## string_xrefs

- `0x1800188cd`: `SYSTEM\CurrentControlSet\Services\crypt32`

## pseudocode

```c
__int64 __fastcall CryptNetDebugFlagsInitOnceCallback(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  BYTE Data[8]; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  if ( Context )
    *Context = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\CurrentControlSet\\Services\\crypt32", 0, 0x20019u, &hKey)
    && !RegQueryValueExA(hKey, "DebugFlags", 0, &Type, Data, &cbData)
    && Type == 4
    && cbData == 4 )
  {
    dword_180032904 = *(_DWORD *)Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x180018890  push    rbp
0x180018892  mov     rbp, rsp
0x180018895  sub     rsp, 40h
0x180018899  mov     [rbp+hKey], 0
0x1800188a1  mov     [rbp+Type], 0
0x1800188a8  mov     dword ptr [rbp+Data], 0
0x1800188af  mov     [rbp+cbData], 4
0x1800188b6  test    r8, r8
0x1800188b9  jnz     short loc_18001892D
0x1800188bb  lea     rax, [rbp+hKey]
0x1800188bf  mov     r9d, 20019h; samDesired
0x1800188c5  xor     r8d, r8d; ulOptions
0x1800188c8  mov     [rsp+40h+phkResult], rax; phkResult
0x1800188cd  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\cr"...
0x1800188d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800188db  call    cs:__imp_RegOpenKeyExA
0x1800188e1  test    eax, eax
0x1800188e3  jnz     short loc_180018913
0x1800188e5  mov     rcx, [rbp+hKey]; hKey
0x1800188e9  lea     rax, [rbp+cbData]
0x1800188ed  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800188f2  lea     r9, [rbp+Type]; lpType
0x1800188f6  lea     rax, [rbp+Data]
0x1800188fa  xor     r8d, r8d; lpReserved
0x1800188fd  lea     rdx, aDebugflags; "DebugFlags"
0x180018904  mov     [rsp+40h+phkResult], rax; lpData
0x180018909  call    cs:__imp_RegQueryValueExA
0x18001890f  test    eax, eax
0x180018911  jz      short loc_180018936
0x180018913  mov     rcx, [rbp+hKey]; hKey
0x180018917  test    rcx, rcx
0x18001891a  jz      short loc_180018922
0x18001891c  call    cs:__imp_RegCloseKey
0x180018922  mov     eax, 1
0x180018927  add     rsp, 40h
0x18001892b  pop     rbp
0x18001892c  retn
0x18001892d  mov     qword ptr [r8], 0
0x180018934  jmp     short loc_1800188BB
0x180018936  cmp     [rbp+Type], 4
0x18001893a  jnz     short loc_180018913
0x18001893c  cmp     [rbp+cbData], 4
0x180018940  jnz     short loc_180018913
0x180018942  mov     eax, dword ptr [rbp+Data]
0x180018945  mov     cs:dword_180032904, eax
0x18001894b  jmp     short loc_180018913
```
