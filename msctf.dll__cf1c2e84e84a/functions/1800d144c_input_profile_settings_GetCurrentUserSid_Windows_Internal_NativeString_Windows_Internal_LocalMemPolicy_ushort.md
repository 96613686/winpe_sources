# input_profile_settings::GetCurrentUserSid(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> &)

- ea: `0x1800d144c`
- end: `0x1800d1567`
- name: `?GetCurrentUserSid@input_profile_settings@@YA_NAEAV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008426c`

## callees

- `0x1800139a4`
- `0x180084768`
- `0x1800d144c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d14b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d14b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d146e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d146e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800d147f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800d147f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d153c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d153c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d14cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d14cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d151b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d151b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d14ab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d14f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d14ab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d14f0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800d1505`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800d1505`

## pseudocode

```c
char __fastcall input_profile_settings::GetCurrentUserSid(__int64 a1)
{
  HANDLE CurrentProcess; // rax
  char v3; // di
  void **v4; // rsi
  void *v5; // rcx
  LPWSTR v6; // r14
  DWORD TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp+40h] BYREF

  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free();
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  v3 = 1;
  if ( TokenHandle )
  {
    TokenInformationLength = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( GetLastError() == 122 )
    {
      if ( TokenInformationLength )
      {
        v4 = (void **)LocalAlloc(0x40u, TokenInformationLength);
        if ( v4 )
        {
          if ( GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
          {
            v5 = *v4;
            StringSid = 0;
            if ( ConvertSidToStringSidW(v5, &StringSid) )
            {
              v6 = StringSid;
              if ( *(_QWORD *)a1 )
                LocalFree(*(HLOCAL *)a1);
              *(_QWORD *)a1 = v6;
              *(_QWORD *)(a1 + 16) = -1;
              *(_QWORD *)(a1 + 8) = -1;
            }
          }
          cicMemFree(v4);
        }
        CloseHandle(TokenHandle);
      }
    }
  }
  if ( !*(_QWORD *)a1 || !**(_WORD **)a1 )
    return 0;
  return v3;
}

```

## disassembly

```asm
0x1800d144c  mov     [rsp-28h+arg_18], rbx
0x1800d1451  push    rbp
0x1800d1452  push    rsi
0x1800d1453  push    rdi
0x1800d1454  push    r14
0x1800d1456  push    r15
0x1800d1458  mov     rbp, rsp
0x1800d145b  sub     rsp, 30h
0x1800d145f  mov     rbx, rcx
0x1800d1462  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1800d1467  xor     r15d, r15d
0x1800d146a  mov     [rbp+TokenHandle], r15
0x1800d146e  call    cs:__imp_GetCurrentProcess
0x1800d1474  mov     rcx, rax; ProcessHandle
0x1800d1477  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800d147b  lea     edx, [r15+8]; DesiredAccess
0x1800d147f  call    cs:__imp_OpenProcessToken
0x1800d1485  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800d1489  lea     edi, [r15+1]
0x1800d148d  test    rcx, rcx
0x1800d1490  jz      loc_1800D1542
0x1800d1496  lea     rax, [rbp+TokenInformationLength]
0x1800d149a  mov     [rbp+TokenInformationLength], r15d
0x1800d149e  xor     r9d, r9d; TokenInformationLength
0x1800d14a1  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800d14a6  xor     r8d, r8d; TokenInformation
0x1800d14a9  mov     edx, edi; TokenInformationClass
0x1800d14ab  call    cs:__imp_GetTokenInformation
0x1800d14b1  call    cs:__imp_GetLastError
0x1800d14b7  cmp     eax, 7Ah ; 'z'
0x1800d14ba  jnz     loc_1800D1542
0x1800d14c0  mov     eax, [rbp+TokenInformationLength]
0x1800d14c3  test    eax, eax
0x1800d14c5  jz      short loc_1800D1542
0x1800d14c7  mov     edx, eax; uBytes
0x1800d14c9  lea     ecx, [rdi+3Fh]; uFlags
0x1800d14cc  call    cs:__imp_LocalAlloc
0x1800d14d2  mov     rsi, rax
0x1800d14d5  test    rax, rax
0x1800d14d8  jz      short loc_1800D1538
0x1800d14da  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800d14de  lea     rax, [rbp+TokenInformationLength]
0x1800d14e2  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800d14e6  mov     r8, rsi; TokenInformation
0x1800d14e9  mov     edx, edi; TokenInformationClass
0x1800d14eb  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800d14f0  call    cs:__imp_GetTokenInformation
0x1800d14f6  test    eax, eax
0x1800d14f8  jz      short loc_1800D1530
0x1800d14fa  mov     rcx, [rsi]; Sid
0x1800d14fd  lea     rdx, [rbp+StringSid]; StringSid
0x1800d1501  mov     [rbp+StringSid], r15
0x1800d1505  call    cs:__imp_ConvertSidToStringSidW
0x1800d150b  test    eax, eax
0x1800d150d  jz      short loc_1800D1530
0x1800d150f  mov     rcx, [rbx]; hMem
0x1800d1512  mov     r14, [rbp+StringSid]
0x1800d1516  test    rcx, rcx
0x1800d1519  jz      short loc_1800D1521
0x1800d151b  call    cs:__imp_LocalFree
0x1800d1521  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d1525  mov     [rbx], r14
0x1800d1528  mov     [rbx+10h], rax
0x1800d152c  mov     [rbx+8], rax
0x1800d1530  mov     rcx, rsi
0x1800d1533  call    cicMemFree
0x1800d1538  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d153c  call    cs:__imp_CloseHandle
0x1800d1542  mov     rax, [rbx]
0x1800d1545  test    rax, rax
0x1800d1548  jz      short loc_1800D1550
0x1800d154a  cmp     [rax], r15w
0x1800d154e  jnz     short loc_1800D1553
0x1800d1550  mov     dil, r15b
0x1800d1553  mov     rbx, [rsp+30h+arg_18]
0x1800d1558  mov     al, dil
0x1800d155b  add     rsp, 30h
0x1800d155f  pop     r15
0x1800d1561  pop     r14
0x1800d1563  pop     rdi
0x1800d1564  pop     rsi
0x1800d1565  pop     rbp
0x1800d1566  retn
```
