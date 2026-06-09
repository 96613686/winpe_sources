# GetTokenSID(void *,_TOKEN_OWNER * *)

- ea: `0x180024820`
- end: `0x180024918`
- name: `?GetTokenSID@@YAKPEAXPEAPEAU_TOKEN_OWNER@@@Z`
- size: `248`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _TOKEN_OWNER **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180019230`
- `0x1800245e0`
- `0x180024820`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002488a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002488a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024869`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800248cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024869`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800248cf`

## pseudocode

```c
__int64 __fastcall GetTokenSID(HANDLE TokenHandle, struct _TOKEN_OWNER **a2)
{
  DWORD LastError; // ebx
  struct _TOKEN_OWNER *v5; // rbx
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  struct _TOKEN_OWNER *v8; // [rsp+50h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( !TokenHandle || !a2 )
    return 87;
  *a2 = 0;
  if ( GetTokenInformation(TokenHandle, TokenOwner, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
  {
    v8 = (struct _TOKEN_OWNER *)operator new(TokenInformationLength);
    v5 = v8;
    if ( v8 )
    {
      if ( GetTokenInformation(TokenHandle, TokenOwner, v8, TokenInformationLength, &TokenInformationLength) )
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
0x180024820  mov     rax, rsp
0x180024823  mov     [rax+10h], rbx
0x180024827  mov     [rax+20h], rsi
0x18002482b  push    rdi
0x18002482c  sub     rsp, 30h
0x180024830  mov     dword ptr [rax+8], 0
0x180024837  mov     rdi, rdx
0x18002483a  mov     rsi, rcx
0x18002483d  test    rcx, rcx
0x180024840  jz      loc_180024902
0x180024846  test    rdx, rdx
0x180024849  jz      loc_180024902
0x18002484f  xor     r9d, r9d; TokenInformationLength
0x180024852  mov     qword ptr [rdx], 0
0x180024859  lea     rax, [rax+8]
0x18002485d  xor     r8d, r8d; TokenInformation
0x180024860  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180024865  lea     edx, [r9+4]; TokenInformationClass
0x180024869  call    cs:__imp_GetTokenInformation
0x180024870  nop     dword ptr [rax+rax+00h]
0x180024875  test    eax, eax
0x180024877  jnz     short loc_18002489A
0x180024879  call    cs:__imp_GetLastError
0x180024880  nop     dword ptr [rax+rax+00h]
0x180024885  cmp     eax, 7Ah ; 'z'
0x180024888  jz      short loc_18002489A
0x18002488a  call    cs:__imp_GetLastError
0x180024891  nop     dword ptr [rax+rax+00h]
0x180024896  mov     ebx, eax
0x180024898  jmp     short loc_1800248FE
0x18002489a  mov     ecx, [rsp+38h+TokenInformationLength]; Size
0x18002489e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800248a3  mov     [rsp+38h+arg_10], rax
0x1800248a8  mov     rbx, rax
0x1800248ab  test    rax, rax
0x1800248ae  jnz     short loc_1800248B5
0x1800248b0  lea     ebx, [rax+8]
0x1800248b3  jmp     short loc_1800248FE
0x1800248b5  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800248ba  lea     rax, [rsp+38h+TokenInformationLength]
0x1800248bf  mov     r8, rbx; TokenInformation
0x1800248c2  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800248c7  mov     edx, 4; TokenInformationClass
0x1800248cc  mov     rcx, rsi; TokenHandle
0x1800248cf  call    cs:__imp_GetTokenInformation
0x1800248d6  nop     dword ptr [rax+rax+00h]
0x1800248db  test    eax, eax
0x1800248dd  jnz     short loc_1800248F9
0x1800248df  call    cs:__imp_GetLastError
0x1800248e6  nop     dword ptr [rax+rax+00h]
0x1800248eb  lea     rcx, [rsp+38h+arg_10]; struct _TOKEN_OWNER **
0x1800248f0  mov     ebx, eax
0x1800248f2  call    ?FreeTokenSID@@YAXPEAPEAU_TOKEN_OWNER@@@Z; FreeTokenSID(_TOKEN_OWNER * *)
0x1800248f7  jmp     short loc_1800248FE
0x1800248f9  mov     [rdi], rbx
0x1800248fc  xor     ebx, ebx
0x1800248fe  mov     eax, ebx
0x180024900  jmp     short loc_180024907
0x180024902  mov     eax, 57h ; 'W'
0x180024907  mov     rbx, [rsp+38h+arg_8]
0x18002490c  mov     rsi, [rsp+38h+arg_18]
0x180024911  add     rsp, 30h
0x180024915  pop     rdi
0x180024916  retn
```
