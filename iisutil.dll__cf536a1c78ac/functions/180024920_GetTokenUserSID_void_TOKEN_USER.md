# GetTokenUserSID(void *,_TOKEN_USER * *)

- ea: `0x180024920`
- end: `0x180024a18`
- name: `?GetTokenUserSID@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z`
- size: `248`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _TOKEN_OWNER **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180019230`
- `0x1800245e0`
- `0x180024920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002498a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002498a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024969`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800249cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024969`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800249cf`

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
0x180024920  mov     rax, rsp
0x180024923  mov     [rax+10h], rbx
0x180024927  mov     [rax+20h], rsi
0x18002492b  push    rdi
0x18002492c  sub     rsp, 30h
0x180024930  mov     dword ptr [rax+8], 0
0x180024937  mov     rdi, rdx
0x18002493a  mov     rsi, rcx
0x18002493d  test    rcx, rcx
0x180024940  jz      loc_180024A02
0x180024946  test    rdx, rdx
0x180024949  jz      loc_180024A02
0x18002494f  xor     r9d, r9d; TokenInformationLength
0x180024952  mov     qword ptr [rdx], 0
0x180024959  lea     rax, [rax+8]
0x18002495d  xor     r8d, r8d; TokenInformation
0x180024960  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180024965  lea     edx, [r9+1]; TokenInformationClass
0x180024969  call    cs:__imp_GetTokenInformation
0x180024970  nop     dword ptr [rax+rax+00h]
0x180024975  test    eax, eax
0x180024977  jnz     short loc_18002499A
0x180024979  call    cs:__imp_GetLastError
0x180024980  nop     dword ptr [rax+rax+00h]
0x180024985  cmp     eax, 7Ah ; 'z'
0x180024988  jz      short loc_18002499A
0x18002498a  call    cs:__imp_GetLastError
0x180024991  nop     dword ptr [rax+rax+00h]
0x180024996  mov     ebx, eax
0x180024998  jmp     short loc_1800249FE
0x18002499a  mov     ecx, [rsp+38h+TokenInformationLength]; Size
0x18002499e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800249a3  mov     [rsp+38h+arg_10], rax
0x1800249a8  mov     rbx, rax
0x1800249ab  test    rax, rax
0x1800249ae  jnz     short loc_1800249B5
0x1800249b0  lea     ebx, [rax+8]
0x1800249b3  jmp     short loc_1800249FE
0x1800249b5  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800249ba  lea     rax, [rsp+38h+TokenInformationLength]
0x1800249bf  mov     r8, rbx; TokenInformation
0x1800249c2  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800249c7  mov     edx, 1; TokenInformationClass
0x1800249cc  mov     rcx, rsi; TokenHandle
0x1800249cf  call    cs:__imp_GetTokenInformation
0x1800249d6  nop     dword ptr [rax+rax+00h]
0x1800249db  test    eax, eax
0x1800249dd  jnz     short loc_1800249F9
0x1800249df  call    cs:__imp_GetLastError
0x1800249e6  nop     dword ptr [rax+rax+00h]
0x1800249eb  lea     rcx, [rsp+38h+arg_10]; struct _TOKEN_OWNER **
0x1800249f0  mov     ebx, eax
0x1800249f2  call    ?FreeTokenSID@@YAXPEAPEAU_TOKEN_OWNER@@@Z; FreeTokenSID(_TOKEN_OWNER * *)
0x1800249f7  jmp     short loc_1800249FE
0x1800249f9  mov     [rdi], rbx
0x1800249fc  xor     ebx, ebx
0x1800249fe  mov     eax, ebx
0x180024a00  jmp     short loc_180024A07
0x180024a02  mov     eax, 57h ; 'W'
0x180024a07  mov     rbx, [rsp+38h+arg_8]
0x180024a0c  mov     rsi, [rsp+38h+arg_18]
0x180024a11  add     rsp, 30h
0x180024a15  pop     rdi
0x180024a16  retn
```
