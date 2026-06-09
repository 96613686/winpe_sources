# GetTokenSID(void *,_TOKEN_OWNER * *)

- ea: `0x180022f90`
- end: `0x180023069`
- name: `?GetTokenSID@@YAKPEAXPEAPEAU_TOKEN_OWNER@@@Z`
- size: `217`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, struct _TOKEN_OWNER **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800183f8`
- `0x180022d70`
- `0x180022f90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022fe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022fe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023037`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022fd9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002302d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022fd9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002302d`

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
0x180022f90  mov     rax, rsp
0x180022f93  mov     [rax+10h], rbx
0x180022f97  mov     [rax+20h], rsi
0x180022f9b  push    rdi
0x180022f9c  sub     rsp, 30h
0x180022fa0  mov     dword ptr [rax+8], 0
0x180022fa7  mov     rdi, rdx
0x180022faa  mov     rsi, rcx
0x180022fad  test    rcx, rcx
0x180022fb0  jz      loc_180023054
0x180022fb6  test    rdx, rdx
0x180022fb9  jz      loc_180023054
0x180022fbf  xor     r9d, r9d; TokenInformationLength
0x180022fc2  mov     qword ptr [rdx], 0
0x180022fc9  lea     rax, [rax+8]
0x180022fcd  xor     r8d, r8d; TokenInformation
0x180022fd0  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180022fd5  lea     edx, [r9+4]; TokenInformationClass
0x180022fd9  call    cs:__imp_GetTokenInformation
0x180022fdf  test    eax, eax
0x180022fe1  jnz     short loc_180022FF8
0x180022fe3  call    cs:__imp_GetLastError
0x180022fe9  cmp     eax, 7Ah ; 'z'
0x180022fec  jz      short loc_180022FF8
0x180022fee  call    cs:__imp_GetLastError
0x180022ff4  mov     ebx, eax
0x180022ff6  jmp     short loc_180023050
0x180022ff8  mov     ecx, [rsp+38h+TokenInformationLength]; Size
0x180022ffc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023001  mov     [rsp+38h+arg_10], rax
0x180023006  mov     rbx, rax
0x180023009  test    rax, rax
0x18002300c  jnz     short loc_180023013
0x18002300e  lea     ebx, [rax+8]
0x180023011  jmp     short loc_180023050
0x180023013  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180023018  lea     rax, [rsp+38h+TokenInformationLength]
0x18002301d  mov     r8, rbx; TokenInformation
0x180023020  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180023025  mov     edx, 4; TokenInformationClass
0x18002302a  mov     rcx, rsi; TokenHandle
0x18002302d  call    cs:__imp_GetTokenInformation
0x180023033  test    eax, eax
0x180023035  jnz     short loc_18002304B
0x180023037  call    cs:__imp_GetLastError
0x18002303d  lea     rcx, [rsp+38h+arg_10]; struct _TOKEN_OWNER **
0x180023042  mov     ebx, eax
0x180023044  call    ?FreeTokenSID@@YAXPEAPEAU_TOKEN_OWNER@@@Z; FreeTokenSID(_TOKEN_OWNER * *)
0x180023049  jmp     short loc_180023050
0x18002304b  mov     [rdi], rbx
0x18002304e  xor     ebx, ebx
0x180023050  mov     eax, ebx
0x180023052  jmp     short loc_180023059
0x180023054  mov     eax, 57h ; 'W'
0x180023059  mov     rbx, [rsp+38h+arg_8]
0x18002305e  mov     rsi, [rsp+38h+arg_18]
0x180023063  add     rsp, 30h
0x180023067  pop     rdi
0x180023068  retn
```
