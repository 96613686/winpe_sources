# IsSystemInAuditMode(int *)

- ea: `0x14000f23c`
- end: `0x14000f350`
- name: `?IsSystemInAuditMode@@YAJPEAH@Z`
- size: `276`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x14000d8b8`

## callees

- `0x14000f23c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000f2e4`
- `ADVAPI32!RegCloseKey` at `0x14000f330`
- `ADVAPI32!RegCloseKey` at `0x14000f33f`
- `ADVAPI32!RegCloseKey` at `0x14000f2e4`
- `ADVAPI32!RegCloseKey` at `0x14000f330`
- `ADVAPI32!RegCloseKey` at `0x14000f33f`
- `ADVAPI32!RegOpenKeyExW` at `0x14000f279`
- `ADVAPI32!RegOpenKeyExW` at `0x14000f317`
- `ADVAPI32!RegOpenKeyExW` at `0x14000f279`
- `ADVAPI32!RegOpenKeyExW` at `0x14000f317`
- `ADVAPI32!RegQueryValueExW` at `0x14000f2c1`
- `ADVAPI32!RegQueryValueExW` at `0x14000f2c1`
- `KERNEL32!SetLastError` at `0x14000f2ec`
- `KERNEL32!SetLastError` at `0x14000f2ec`
- `KERNEL32!GetLastError` at `0x14000f2d9`
- `KERNEL32!GetLastError` at `0x14000f2d9`

## pseudocode

```c
__int64 __fastcall IsSystemInAuditMode(int *a1)
{
  HKEY v2; // rdi
  DWORD LastError; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  int Data; // [rsp+70h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+30h] BYREF
  DWORD Type; // [rsp+80h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+40h] BYREF

  *a1 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup\\Status", 0, 0x20019u, &hKey) )
  {
    Data = 0;
    phkResult = 0;
    Type = 4;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"AuditBoot", 0, &Type, (LPBYTE)&Data, &cbData) && Data )
      goto LABEL_7;
    v2 = phkResult;
    if ( phkResult )
    {
      LastError = GetLastError();
      RegCloseKey(v2);
      SetLastError(LastError);
    }
    phkResult = 0;
    if ( !RegOpenKeyExW(hKey, L"AuditBootVolatile", 0, 0x20019u, &phkResult) )
LABEL_7:
      *a1 = 1;
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x14000f23c  push    rbp
0x14000f23e  push    rbx
0x14000f23f  push    rsi
0x14000f240  push    rdi
0x14000f241  mov     rbp, rsp
0x14000f244  sub     rsp, 48h
0x14000f248  mov     rsi, rcx
0x14000f24b  mov     dword ptr [rcx], 0
0x14000f251  lea     rax, [rbp+hKey]
0x14000f255  mov     [rbp+hKey], 0
0x14000f25d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000f264  mov     [rsp+48h+phkResult], rax; phkResult
0x14000f269  mov     r9d, 20019h; samDesired
0x14000f26f  lea     rdx, aSystemSetupSta; "System\\Setup\\Status"
0x14000f276  xor     r8d, r8d; ulOptions
0x14000f279  call    cs:__imp_RegOpenKeyExW
0x14000f27f  test    eax, eax
0x14000f281  jnz     loc_14000F336
0x14000f287  mov     rcx, [rbp+hKey]; hKey
0x14000f28b  lea     r9, [rbp+Type]; lpType
0x14000f28f  mov     [rbp+Data], eax
0x14000f292  lea     rdx, aAuditboot; "AuditBoot"
0x14000f299  mov     eax, 4
0x14000f29e  mov     [rbp+arg_18], 0
0x14000f2a6  mov     [rbp+Type], eax
0x14000f2a9  xor     r8d, r8d; lpReserved
0x14000f2ac  mov     [rbp+cbData], eax
0x14000f2af  lea     rax, [rbp+cbData]
0x14000f2b3  mov     [rsp+48h+lpcbData], rax; lpcbData
0x14000f2b8  lea     rax, [rbp+Data]
0x14000f2bc  mov     [rsp+48h+phkResult], rax; lpData
0x14000f2c1  call    cs:__imp_RegQueryValueExW
0x14000f2c7  test    eax, eax
0x14000f2c9  jnz     short loc_14000F2D0
0x14000f2cb  cmp     [rbp+Data], eax
0x14000f2ce  jnz     short loc_14000F321
0x14000f2d0  mov     rdi, [rbp+arg_18]
0x14000f2d4  test    rdi, rdi
0x14000f2d7  jz      short loc_14000F2F2
0x14000f2d9  call    cs:__imp_GetLastError
0x14000f2df  mov     rcx, rdi; hKey
0x14000f2e2  mov     ebx, eax
0x14000f2e4  call    cs:__imp_RegCloseKey
0x14000f2ea  mov     ecx, ebx; dwErrCode
0x14000f2ec  call    cs:__imp_SetLastError
0x14000f2f2  mov     rcx, [rbp+hKey]; hKey
0x14000f2f6  lea     rax, [rbp+arg_18]
0x14000f2fa  mov     r9d, 20019h; samDesired
0x14000f300  mov     [rsp+48h+phkResult], rax; phkResult
0x14000f305  xor     r8d, r8d; ulOptions
0x14000f308  mov     [rbp+arg_18], 0
0x14000f310  lea     rdx, aAuditbootvolat; "AuditBootVolatile"
0x14000f317  call    cs:__imp_RegOpenKeyExW
0x14000f31d  test    eax, eax
0x14000f31f  jnz     short loc_14000F327
0x14000f321  mov     dword ptr [rsi], 1
0x14000f327  mov     rcx, [rbp+arg_18]; hKey
0x14000f32b  test    rcx, rcx
0x14000f32e  jz      short loc_14000F336
0x14000f330  call    cs:__imp_RegCloseKey
0x14000f336  mov     rcx, [rbp+hKey]; hKey
0x14000f33a  test    rcx, rcx
0x14000f33d  jz      short loc_14000F345
0x14000f33f  call    cs:__imp_RegCloseKey
0x14000f345  xor     eax, eax
0x14000f347  add     rsp, 48h
0x14000f34b  pop     rdi
0x14000f34c  pop     rsi
0x14000f34d  pop     rbx
0x14000f34e  pop     rbp
0x14000f34f  retn
```
