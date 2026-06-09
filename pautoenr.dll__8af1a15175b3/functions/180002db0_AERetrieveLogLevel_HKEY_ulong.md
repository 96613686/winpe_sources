# AERetrieveLogLevel(HKEY__ *,ulong *)

- ea: `0x180002db0`
- end: `0x180002f3d`
- name: `?AERetrieveLogLevel@@YAHPEAUHKEY__@@PEAK@Z`
- size: `397`
- prototype: `__int64 __fastcall(HKEY, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001d90`
- `0x180002db0`

## callees

- `0x180002db0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002ed5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002f1b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002ed5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002f1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002e00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002e5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002e00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002e5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e77`

## pseudocode

```c
__int64 __fastcall AERetrieveLogLevel(HKEY a1, unsigned int *a2)
{
  int v3; // edi
  int v5; // edi
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+38h] BYREF

  Data = 2;
  Type = 0;
  hKey = 0;
  cbData = 4;
  v3 = 0;
  if ( RegOpenKeyExW(a1, L"SOFTWARE\\Microsoft\\Cryptography\\AutoEnrollment", 0, 0x20019u, &hKey) )
    goto LABEL_2;
  if ( !RegQueryValueExW(hKey, L"LogLevel", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
  {
    v3 = 1;
LABEL_2:
    *a2 = Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v3 )
  {
    Data = 2;
    cbData = 4;
    Type = 0;
    hKey = 0;
    v5 = 0;
    if ( !RegOpenKeyExW(a1, L"SOFTWARE\\Microsoft\\Cryptography\\AutoEnrollment", 0, 0x20019u, &hKey) )
    {
      if ( RegQueryValueExW(hKey, L"AEEventLogLevel", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
        goto LABEL_8;
      v5 = 1;
    }
    *a2 = Data;
LABEL_8:
    if ( hKey )
      RegCloseKey(hKey);
    if ( !v5 && a1 != HKEY_LOCAL_MACHINE )
      AERetrieveLogLevel(HKEY_LOCAL_MACHINE, a2);
  }
  return 1;
}

```

## disassembly

```asm
0x180002db0  mov     [rsp-18h+arg_0], rbx
0x180002db5  mov     [rsp-18h+arg_8], rsi
0x180002dba  push    rbp
0x180002dbb  push    rdi
0x180002dbc  push    r14
0x180002dbe  mov     rbp, rsp
0x180002dc1  sub     rsp, 40h
0x180002dc5  xor     r14d, r14d
0x180002dc8  mov     [rbp+Data], 2
0x180002dcf  mov     rsi, rdx
0x180002dd2  mov     [rbp+Type], r14d
0x180002dd6  lea     rax, [rbp+hKey]
0x180002dda  mov     [rbp+hKey], r14
0x180002dde  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Cryptography\\Auto"...
0x180002de5  mov     [rsp+40h+phkResult], rax; phkResult
0x180002dea  mov     r9d, 20019h; samDesired
0x180002df0  mov     [rbp+cbData], 4
0x180002df7  xor     r8d, r8d; ulOptions
0x180002dfa  mov     edi, r14d
0x180002dfd  mov     rbx, rcx
0x180002e00  call    cs:__imp_RegOpenKeyExW
0x180002e06  test    eax, eax
0x180002e08  jz      loc_180002EB1
0x180002e0e  mov     eax, [rbp+Data]
0x180002e11  mov     [rsi], eax
0x180002e13  mov     rcx, [rbp+hKey]; hKey
0x180002e17  test    rcx, rcx
0x180002e1a  jz      short loc_180002E22
0x180002e1c  call    cs:__imp_RegCloseKey
0x180002e22  test    edi, edi
0x180002e24  jnz     short loc_180002E99
0x180002e26  lea     rax, [rbp+hKey]
0x180002e2a  mov     [rbp+Data], 2
0x180002e31  mov     r9d, 20019h; samDesired
0x180002e37  mov     [rsp+40h+phkResult], rax; phkResult
0x180002e3c  xor     r8d, r8d; ulOptions
0x180002e3f  mov     [rbp+cbData], 4
0x180002e46  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Cryptography\\Auto"...
0x180002e4d  mov     [rbp+Type], r14d
0x180002e51  mov     rcx, rbx; hKey
0x180002e54  mov     [rbp+hKey], r14
0x180002e58  mov     edi, r14d
0x180002e5b  call    cs:__imp_RegOpenKeyExW
0x180002e61  test    eax, eax
0x180002e63  jz      loc_180002EF7
0x180002e69  mov     eax, [rbp+Data]
0x180002e6c  mov     [rsi], eax
0x180002e6e  mov     rcx, [rbp+hKey]; hKey
0x180002e72  test    rcx, rcx
0x180002e75  jz      short loc_180002E7D
0x180002e77  call    cs:__imp_RegCloseKey
0x180002e7d  test    edi, edi
0x180002e7f  jnz     short loc_180002E99
0x180002e81  cmp     rbx, 0FFFFFFFF80000002h
0x180002e88  jz      short loc_180002E99
0x180002e8a  mov     rdx, rsi; unsigned int *
0x180002e8d  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180002e94  call    ?AERetrieveLogLevel@@YAHPEAUHKEY__@@PEAK@Z; AERetrieveLogLevel(HKEY__ *,ulong *)
0x180002e99  mov     rbx, [rsp+40h+arg_0]
0x180002e9e  mov     eax, 1
0x180002ea3  mov     rsi, [rsp+40h+arg_8]
0x180002ea8  add     rsp, 40h
0x180002eac  pop     r14
0x180002eae  pop     rdi
0x180002eaf  pop     rbp
0x180002eb0  retn
0x180002eb1  mov     rcx, [rbp+hKey]; hKey
0x180002eb5  lea     rax, [rbp+cbData]
0x180002eb9  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180002ebe  lea     r9, [rbp+Type]; lpType
0x180002ec2  lea     rax, [rbp+Data]
0x180002ec6  xor     r8d, r8d; lpReserved
0x180002ec9  lea     rdx, aLoglevel; "LogLevel"
0x180002ed0  mov     [rsp+40h+phkResult], rax; lpData
0x180002ed5  call    cs:__imp_RegQueryValueExW
0x180002edb  test    eax, eax
0x180002edd  jnz     loc_180002E13
0x180002ee3  cmp     [rbp+Type], 4
0x180002ee7  jnz     loc_180002E13
0x180002eed  mov     edi, 1
0x180002ef2  jmp     loc_180002E0E
0x180002ef7  mov     rcx, [rbp+hKey]; hKey
0x180002efb  lea     rax, [rbp+cbData]
0x180002eff  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180002f04  lea     r9, [rbp+Type]; lpType
0x180002f08  lea     rax, [rbp+Data]
0x180002f0c  xor     r8d, r8d; lpReserved
0x180002f0f  lea     rdx, aAeeventlogleve; "AEEventLogLevel"
0x180002f16  mov     [rsp+40h+phkResult], rax; lpData
0x180002f1b  call    cs:__imp_RegQueryValueExW
0x180002f21  test    eax, eax
0x180002f23  jnz     loc_180002E6E
0x180002f29  cmp     [rbp+Type], 4
0x180002f2d  jnz     loc_180002E6E
0x180002f33  mov     edi, 1
0x180002f38  jmp     loc_180002E69
```
