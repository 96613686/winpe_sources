# CReservedBlockManager::LoadRegSettings(void)

- ea: `0x18013eb84`
- end: `0x18013ec7d`
- name: `?LoadRegSettings@CReservedBlockManager@@IEAAXXZ`
- size: `249`
- prototype: `void __fastcall(CReservedBlockManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18013e9ec`

## callees

- `0x180003d80`
- `0x18013eb84`

## import_xrefs

- `ADVAPI32!RegOpenKeyW` at `0x18013ebb9`
- `ADVAPI32!RegOpenKeyW` at `0x18013ebb9`
- `ADVAPI32!RegQueryValueExW` at `0x18013ebf8`
- `ADVAPI32!RegQueryValueExW` at `0x18013ec46`
- `ADVAPI32!RegQueryValueExW` at `0x18013ebf8`
- `ADVAPI32!RegQueryValueExW` at `0x18013ec46`
- `ADVAPI32!RegCloseKey` at `0x18013ec60`
- `ADVAPI32!RegCloseKey` at `0x18013ec60`

## string_xrefs

- `0x18013ebab`: `SOFTWARE\Microsoft\DataAccess\MSOLEDBSQL`

## pseudocode

```c
void __fastcall CReservedBlockManager::LoadRegSettings(CReservedBlockManager *this)
{
  HKEY phkResult; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+38h] [rbp-18h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-14h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-10h] BYREF

  phkResult = 0;
  if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\DataAccess\\MSOLEDBSQL", &phkResult) )
  {
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(phkResult, L"ReservedMemorySize", 0, &Type, Data, &cbData) && Type == 4 )
      *(_DWORD *)this = -g_SystemInfo.dwPageSize & (g_SystemInfo.dwPageSize + *(_DWORD *)Data - 1);
    cbData = 4;
    if ( !RegQueryValueExW(phkResult, L"MaxReservedBlocks", 0, &Type, Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 1) = *(_DWORD *)Data;
    RegCloseKey(phkResult);
  }
}

```

## disassembly

```asm
0x18013eb84  mov     [rsp-8+arg_8], rbx
0x18013eb89  push    rbp
0x18013eb8a  mov     rbp, rsp
0x18013eb8d  sub     rsp, 50h
0x18013eb91  mov     rax, cs:__security_cookie
0x18013eb98  xor     rax, rsp
0x18013eb9b  mov     [rbp+var_8], rax
0x18013eb9f  and     [rbp+phkResult], 0
0x18013eba4  lea     r8, [rbp+phkResult]; phkResult
0x18013eba8  mov     rbx, rcx
0x18013ebab  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\DataAccess\\MSOLED"...
0x18013ebb2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18013ebb9  call    cs:__imp_RegOpenKeyW
0x18013ebbf  test    eax, eax
0x18013ebc1  jnz     loc_18013EC66
0x18013ebc7  and     [rbp+Type], eax
0x18013ebca  lea     r9, [rbp+Type]; lpType
0x18013ebce  and     dword ptr [rbp+Data], eax
0x18013ebd1  lea     rdx, aReservedmemory; "ReservedMemorySize"
0x18013ebd8  mov     rcx, [rbp+phkResult]; hKey
0x18013ebdc  lea     rax, [rbp+cbData]
0x18013ebe0  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18013ebe5  xor     r8d, r8d; lpReserved
0x18013ebe8  lea     rax, [rbp+Data]
0x18013ebec  mov     [rbp+cbData], 4
0x18013ebf3  mov     [rsp+50h+lpData], rax; lpData
0x18013ebf8  call    cs:__imp_RegQueryValueExW
0x18013ebfe  test    eax, eax
0x18013ec00  jnz     short loc_18013EC1B
0x18013ec02  cmp     [rbp+Type], 4
0x18013ec06  jnz     short loc_18013EC1B
0x18013ec08  mov     edx, cs:?g_SystemInfo@@3U_SYSTEM_INFO@@A.dwPageSize; _SYSTEM_INFO g_SystemInfo ...
0x18013ec0e  mov     ecx, dword ptr [rbp+Data]
0x18013ec11  dec     ecx
0x18013ec13  add     ecx, edx
0x18013ec15  neg     edx
0x18013ec17  and     ecx, edx
0x18013ec19  mov     [rbx], ecx
0x18013ec1b  mov     rcx, [rbp+phkResult]; hKey
0x18013ec1f  lea     rax, [rbp+cbData]
0x18013ec23  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18013ec28  lea     r9, [rbp+Type]; lpType
0x18013ec2c  lea     rax, [rbp+Data]
0x18013ec30  mov     [rbp+cbData], 4
0x18013ec37  xor     r8d, r8d; lpReserved
0x18013ec3a  mov     [rsp+50h+lpData], rax; lpData
0x18013ec3f  lea     rdx, aMaxreservedblo; "MaxReservedBlocks"
0x18013ec46  call    cs:__imp_RegQueryValueExW
0x18013ec4c  test    eax, eax
0x18013ec4e  jnz     short loc_18013EC5C
0x18013ec50  cmp     [rbp+Type], 4
0x18013ec54  jnz     short loc_18013EC5C
0x18013ec56  mov     eax, dword ptr [rbp+Data]
0x18013ec59  mov     [rbx+4], eax
0x18013ec5c  mov     rcx, [rbp+phkResult]; hKey
0x18013ec60  call    cs:__imp_RegCloseKey
0x18013ec66  mov     rcx, [rbp+var_8]
0x18013ec6a  xor     rcx, rsp; StackCookie
0x18013ec6d  call    __security_check_cookie
0x18013ec72  mov     rbx, [rsp+50h+arg_8]
0x18013ec77  add     rsp, 50h
0x18013ec7b  pop     rbp
0x18013ec7c  retn
```
