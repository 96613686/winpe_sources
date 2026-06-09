# _RetrieveLogLevel

- ea: `0x180001770`
- end: `0x1800018df`
- name: `_RetrieveLogLevel`
- size: `367`
- prototype: `__int64 __fastcall(HKEY, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001410`
- `0x180001770`

## callees

- `0x180001770`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800017ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001882`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800017ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001882`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001811`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800018a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001811`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800018a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800017c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001854`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800017c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001854`

## pseudocode

```c
__int64 __fastcall RetrieveLogLevel(HKEY a1, int *a2)
{
  int v3; // edi
  int v5; // edi
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF

  Data = 2;
  Type = 0;
  hKey = 0;
  cbData = 4;
  v3 = 0;
  if ( RegOpenKeyExW(a1, L"SOFTWARE\\Microsoft\\Cryptography\\AutoEnrollment", 0, 0x20019u, &hKey) )
    goto LABEL_5;
  if ( !RegQueryValueExW(hKey, L"LogLevel", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
  {
    v3 = 1;
LABEL_5:
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
        goto LABEL_14;
      v5 = 1;
    }
    *a2 = Data;
LABEL_14:
    if ( hKey )
      RegCloseKey(hKey);
    if ( !v5 && a1 != HKEY_LOCAL_MACHINE )
      RetrieveLogLevel(-2147483646, a2);
  }
  return 1;
}

```

## disassembly

```asm
0x180001770  mov     [rsp-18h+arg_0], rbx
0x180001775  mov     [rsp-18h+arg_8], rsi
0x18000177a  push    rbp
0x18000177b  push    rdi
0x18000177c  push    r14
0x18000177e  mov     rbp, rsp
0x180001781  sub     rsp, 40h
0x180001785  xor     r14d, r14d
0x180001788  mov     [rbp+Data], 2
0x18000178f  mov     rsi, rdx
0x180001792  mov     [rbp+Type], r14d
0x180001796  lea     rax, [rbp+hKey]
0x18000179a  mov     [rbp+hKey], r14
0x18000179e  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Cryptography\\Auto"...
0x1800017a5  mov     [rsp+40h+phkResult], rax; phkResult
0x1800017aa  mov     r9d, 20019h; samDesired
0x1800017b0  mov     [rbp+cbData], 4
0x1800017b7  xor     r8d, r8d; ulOptions
0x1800017ba  mov     edi, r14d
0x1800017bd  mov     rbx, rcx
0x1800017c0  call    cs:__imp_RegOpenKeyExW
0x1800017c6  test    eax, eax
0x1800017c8  jnz     short loc_180001803
0x1800017ca  mov     rcx, [rbp+hKey]; hKey
0x1800017ce  lea     rax, [rbp+cbData]
0x1800017d2  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800017d7  lea     r9, [rbp+Type]; lpType
0x1800017db  lea     rax, [rbp+Data]
0x1800017df  xor     r8d, r8d; lpReserved
0x1800017e2  lea     rdx, ValueName; "LogLevel"
0x1800017e9  mov     [rsp+40h+phkResult], rax; lpData
0x1800017ee  call    cs:__imp_RegQueryValueExW
0x1800017f4  test    eax, eax
0x1800017f6  jnz     short loc_180001808
0x1800017f8  cmp     [rbp+Type], 4
0x1800017fc  jnz     short loc_180001808
0x1800017fe  mov     edi, 1
0x180001803  mov     eax, [rbp+Data]
0x180001806  mov     [rsi], eax
0x180001808  mov     rcx, [rbp+hKey]; hKey
0x18000180c  test    rcx, rcx
0x18000180f  jz      short loc_180001817
0x180001811  call    cs:__imp_RegCloseKey
0x180001817  test    edi, edi
0x180001819  jnz     loc_1800018C7
0x18000181f  lea     rax, [rbp+hKey]
0x180001823  mov     [rbp+Data], 2
0x18000182a  mov     r9d, 20019h; samDesired
0x180001830  mov     [rsp+40h+phkResult], rax; phkResult
0x180001835  xor     r8d, r8d; ulOptions
0x180001838  mov     [rbp+cbData], 4
0x18000183f  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Cryptography\\Auto"...
0x180001846  mov     [rbp+Type], r14d
0x18000184a  mov     rcx, rbx; hKey
0x18000184d  mov     [rbp+hKey], r14
0x180001851  mov     edi, r14d
0x180001854  call    cs:__imp_RegOpenKeyExW
0x18000185a  test    eax, eax
0x18000185c  jnz     short loc_180001897
0x18000185e  mov     rcx, [rbp+hKey]; hKey
0x180001862  lea     rax, [rbp+cbData]
0x180001866  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000186b  lea     r9, [rbp+Type]; lpType
0x18000186f  lea     rax, [rbp+Data]
0x180001873  xor     r8d, r8d; lpReserved
0x180001876  lea     rdx, aAeeventlogleve; "AEEventLogLevel"
0x18000187d  mov     [rsp+40h+phkResult], rax; lpData
0x180001882  call    cs:__imp_RegQueryValueExW
0x180001888  test    eax, eax
0x18000188a  jnz     short loc_18000189C
0x18000188c  cmp     [rbp+Type], 4
0x180001890  jnz     short loc_18000189C
0x180001892  mov     edi, 1
0x180001897  mov     eax, [rbp+Data]
0x18000189a  mov     [rsi], eax
0x18000189c  mov     rcx, [rbp+hKey]; hKey
0x1800018a0  test    rcx, rcx
0x1800018a3  jz      short loc_1800018AB
0x1800018a5  call    cs:__imp_RegCloseKey
0x1800018ab  test    edi, edi
0x1800018ad  jnz     short loc_1800018C7
0x1800018af  cmp     rbx, 0FFFFFFFF80000002h
0x1800018b6  jz      short loc_1800018C7
0x1800018b8  mov     rdx, rsi
0x1800018bb  mov     rcx, 0FFFFFFFF80000002h
0x1800018c2  call    _RetrieveLogLevel
0x1800018c7  mov     rbx, [rsp+40h+arg_0]
0x1800018cc  mov     eax, 1
0x1800018d1  mov     rsi, [rsp+40h+arg_8]
0x1800018d6  add     rsp, 40h
0x1800018da  pop     r14
0x1800018dc  pop     rdi
0x1800018dd  pop     rbp
0x1800018de  retn
```
