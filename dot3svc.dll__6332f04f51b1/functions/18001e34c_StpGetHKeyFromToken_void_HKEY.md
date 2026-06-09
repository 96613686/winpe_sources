# StpGetHKeyFromToken(void *,HKEY__ * *)

- ea: `0x18001e34c`
- end: `0x18001e486`
- name: `?StpGetHKeyFromToken@@YAKPEAXPEAPEAUHKEY__@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HKEY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001d168`
- `0x18001dd30`

## callees

- `0x18000a7ec`
- `0x18000a87c`
- `0x18001e34c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e442`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e419`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e391`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e3f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e391`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e3f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e46b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e46b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001e40f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001e40f`

## pseudocode

```c
__int64 __fastcall StpGetHKeyFromToken(HANDLE TokenHandle, HKEY *a2)
{
  DWORD v4; // ebx
  DWORD LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  PSID *v8; // rdi
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp+38h] BYREF

  TokenInformationLength = 0;
  StringSid = 0;
  phkResult = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v4 = 1008;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError == 122 || !LastError )
    {
      v8 = (PSID *)Dot3Alloc(TokenInformationLength, v6, v7);
      if ( v8 || (v4 = GetLastError()) == 0 )
      {
        if ( (GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength)
           || (v4 = GetLastError()) == 0)
          && (ConvertSidToStringSidW(*v8, &StringSid) || (v4 = GetLastError()) == 0) )
        {
          v4 = RegOpenKeyExW(HKEY_USERS, StringSid, 0, 0xF003Fu, &phkResult);
          if ( !v4 )
            *a2 = phkResult;
        }
        if ( v8 )
          Dot3Free(v8);
      }
    }
  }
  if ( StringSid )
    LocalFree(StringSid);
  return v4;
}

```

## disassembly

```asm
0x18001e34c  mov     [rsp-18h+arg_0], rbx
0x18001e351  mov     [rsp-18h+arg_8], rsi
0x18001e356  push    rbp
0x18001e357  push    rdi
0x18001e358  push    r14
0x18001e35a  mov     rbp, rsp
0x18001e35d  sub     rsp, 40h
0x18001e361  xor     r9d, r9d; TokenInformationLength
0x18001e364  mov     [rbp+TokenInformationLength], 0
0x18001e36b  mov     r14, rdx
0x18001e36e  mov     [rbp+StringSid], 0
0x18001e376  lea     rax, [rbp+TokenInformationLength]
0x18001e37a  mov     [rbp+phkResult], 0
0x18001e382  xor     r8d, r8d; TokenInformation
0x18001e385  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18001e38a  lea     edx, [r9+1]; TokenInformationClass
0x18001e38e  mov     rsi, rcx
0x18001e391  call    cs:__imp_GetTokenInformation
0x18001e397  test    eax, eax
0x18001e399  jz      short loc_18001E3A5
0x18001e39b  mov     ebx, 3F0h
0x18001e3a0  jmp     loc_18001E462
0x18001e3a5  call    cs:__imp_GetLastError
0x18001e3ab  mov     ebx, eax
0x18001e3ad  cmp     eax, 7Ah ; 'z'
0x18001e3b0  jz      short loc_18001E3BA
0x18001e3b2  test    eax, eax
0x18001e3b4  jnz     loc_18001E462
0x18001e3ba  mov     ecx, [rbp+TokenInformationLength]; dwBytes
0x18001e3bd  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x18001e3c2  mov     rdi, rax
0x18001e3c5  test    rax, rax
0x18001e3c8  jnz     short loc_18001E3DA
0x18001e3ca  call    cs:__imp_GetLastError
0x18001e3d0  mov     ebx, eax
0x18001e3d2  test    eax, eax
0x18001e3d4  jnz     loc_18001E462
0x18001e3da  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001e3de  lea     rax, [rbp+TokenInformationLength]
0x18001e3e2  mov     r8, rdi; TokenInformation
0x18001e3e5  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18001e3ea  mov     edx, 1; TokenInformationClass
0x18001e3ef  mov     rcx, rsi; TokenHandle
0x18001e3f2  call    cs:__imp_GetTokenInformation
0x18001e3f8  test    eax, eax
0x18001e3fa  jnz     short loc_18001E408
0x18001e3fc  call    cs:__imp_GetLastError
0x18001e402  mov     ebx, eax
0x18001e404  test    eax, eax
0x18001e406  jnz     short loc_18001E455
0x18001e408  mov     rcx, [rdi]; Sid
0x18001e40b  lea     rdx, [rbp+StringSid]; StringSid
0x18001e40f  call    cs:__imp_ConvertSidToStringSidW
0x18001e415  test    eax, eax
0x18001e417  jnz     short loc_18001E425
0x18001e419  call    cs:__imp_GetLastError
0x18001e41f  mov     ebx, eax
0x18001e421  test    eax, eax
0x18001e423  jnz     short loc_18001E455
0x18001e425  mov     rdx, [rbp+StringSid]; lpSubKey
0x18001e429  lea     rax, [rbp+phkResult]
0x18001e42d  mov     r9d, 0F003Fh; samDesired
0x18001e433  mov     [rsp+40h+ReturnLength], rax; phkResult
0x18001e438  xor     r8d, r8d; ulOptions
0x18001e43b  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001e442  call    cs:__imp_RegOpenKeyExW
0x18001e448  mov     ebx, eax
0x18001e44a  test    eax, eax
0x18001e44c  jnz     short loc_18001E455
0x18001e44e  mov     rax, [rbp+phkResult]
0x18001e452  mov     [r14], rax
0x18001e455  test    rdi, rdi
0x18001e458  jz      short loc_18001E462
0x18001e45a  mov     rcx, rdi; lpMem
0x18001e45d  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18001e462  mov     rcx, [rbp+StringSid]; hMem
0x18001e466  test    rcx, rcx
0x18001e469  jz      short loc_18001E471
0x18001e46b  call    cs:__imp_LocalFree
0x18001e471  mov     rsi, [rsp+40h+arg_8]
0x18001e476  mov     eax, ebx
0x18001e478  mov     rbx, [rsp+40h+arg_0]
0x18001e47d  add     rsp, 40h
0x18001e481  pop     r14
0x18001e483  pop     rdi
0x18001e484  pop     rbp
0x18001e485  retn
```
