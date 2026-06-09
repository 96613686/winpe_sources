# GetTokenUserSID(void *,_TOKEN_USER * *)

- ea: `0x180023070`
- end: `0x180023149`
- name: `?GetTokenUserSID@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z`
- size: `217`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, struct _TOKEN_USER **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800183f8`
- `0x180022d70`
- `0x180023070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023117`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800230b9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002310d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800230b9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002310d`

## pseudocode

```c
__int64 __fastcall GetTokenUserSID(HANDLE TokenHandle, struct _TOKEN_OWNER **a2)
{
  DWORD LastError; // ebx
  struct _TOKEN_OWNER *v5; // rbx
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  struct _TOKEN_OWNER *v8; // [rsp+50h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( !TokenHandle || !a2 )
    return 87;
  *a2 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
  {
    v8 = (struct _TOKEN_OWNER *)operator new(TokenInformationLength);
    v5 = v8;
    if ( v8 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
      {
        *a2 = v5;
        return 0;
      }
      else
      {
        LastError = GetLastError();
        FreeTokenSID(&v8);
      }
    }
    else
    {
      return 8;
    }
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x180023070  mov     rax, rsp
0x180023073  mov     [rax+10h], rbx
0x180023077  mov     [rax+20h], rsi
0x18002307b  push    rdi
0x18002307c  sub     rsp, 30h
0x180023080  mov     dword ptr [rax+8], 0
0x180023087  mov     rdi, rdx
0x18002308a  mov     rsi, rcx
0x18002308d  test    rcx, rcx
0x180023090  jz      loc_180023134
0x180023096  test    rdx, rdx
0x180023099  jz      loc_180023134
0x18002309f  xor     r9d, r9d; TokenInformationLength
0x1800230a2  mov     qword ptr [rdx], 0
0x1800230a9  lea     rax, [rax+8]
0x1800230ad  xor     r8d, r8d; TokenInformation
0x1800230b0  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800230b5  lea     edx, [r9+1]; TokenInformationClass
0x1800230b9  call    cs:__imp_GetTokenInformation
0x1800230bf  test    eax, eax
0x1800230c1  jnz     short loc_1800230D8
0x1800230c3  call    cs:__imp_GetLastError
0x1800230c9  cmp     eax, 7Ah ; 'z'
0x1800230cc  jz      short loc_1800230D8
0x1800230ce  call    cs:__imp_GetLastError
0x1800230d4  mov     ebx, eax
0x1800230d6  jmp     short loc_180023130
0x1800230d8  mov     ecx, [rsp+38h+TokenInformationLength]; Size
0x1800230dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800230e1  mov     [rsp+38h+arg_10], rax
0x1800230e6  mov     rbx, rax
0x1800230e9  test    rax, rax
0x1800230ec  jnz     short loc_1800230F3
0x1800230ee  lea     ebx, [rax+8]
0x1800230f1  jmp     short loc_180023130
0x1800230f3  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800230f8  lea     rax, [rsp+38h+TokenInformationLength]
0x1800230fd  mov     r8, rbx; TokenInformation
0x180023100  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180023105  mov     edx, 1; TokenInformationClass
0x18002310a  mov     rcx, rsi; TokenHandle
0x18002310d  call    cs:__imp_GetTokenInformation
0x180023113  test    eax, eax
0x180023115  jnz     short loc_18002312B
0x180023117  call    cs:__imp_GetLastError
0x18002311d  lea     rcx, [rsp+38h+arg_10]; struct _TOKEN_OWNER **
0x180023122  mov     ebx, eax
0x180023124  call    ?FreeTokenSID@@YAXPEAPEAU_TOKEN_OWNER@@@Z; FreeTokenSID(_TOKEN_OWNER * *)
0x180023129  jmp     short loc_180023130
0x18002312b  mov     [rdi], rbx
0x18002312e  xor     ebx, ebx
0x180023130  mov     eax, ebx
0x180023132  jmp     short loc_180023139
0x180023134  mov     eax, 57h ; 'W'
0x180023139  mov     rbx, [rsp+38h+arg_8]
0x18002313e  mov     rsi, [rsp+38h+arg_18]
0x180023143  add     rsp, 30h
0x180023147  pop     rdi
0x180023148  retn
```
