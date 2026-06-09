# NSecurityLibrary::TSidUserContext::Initialize(void *,_TOKEN_USER * *)

- ea: `0x1800358e4`
- end: `0x1800359a9`
- name: `?Initialize@TSidUserContext@NSecurityLibrary@@CAJPEAXPEAPEAU_TOKEN_USER@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _TOKEN_USER **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800356a8`

## callees

- `0x1800029b0`
- `0x18000b200`
- `0x1800358e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035925`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003591b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003597f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003591b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003597f`

## pseudocode

```c
__int64 __fastcall NSecurityLibrary::TSidUserContext::Initialize(HANDLE TokenHandle, LPVOID *a2)
{
  signed int LastError; // eax
  signed int v5; // ebx
  struct _TOKEN_USER *v6; // rax
  NCoreLibrary *v7; // rcx
  DWORD TokenInformationLength; // [rsp+50h] [rbp+18h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+20h] BYREF

  ReturnLength = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError == 122 )
    {
      v6 = (struct _TOKEN_USER *)operator new[](
                                   TokenInformationLength,
                                   (const struct std::nothrow_t *)&NCoreLibrary::nothrow);
      *a2 = v6;
      v5 = v6 == 0 ? 0x8007000E : 0;
    }
    else if ( LastError > 0 )
    {
      v5 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v5 >= 0 && !GetTokenInformation(TokenHandle, TokenUser, *a2, TokenInformationLength, &ReturnLength) )
      return (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v7);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800358e4  mov     rax, rsp
0x1800358e7  mov     [rax+8], rbx
0x1800358eb  mov     [rax+10h], rsi
0x1800358ef  push    rdi
0x1800358f0  sub     rsp, 30h
0x1800358f4  xor     r9d, r9d; TokenInformationLength
0x1800358f7  mov     dword ptr [rax+20h], 0
0x1800358fe  mov     dword ptr [rax+18h], 0
0x180035905  lea     rax, [rax+18h]
0x180035909  mov     rdi, rdx
0x18003590c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180035911  xor     r8d, r8d; TokenInformation
0x180035914  mov     rsi, rcx
0x180035917  lea     edx, [r9+1]; TokenInformationClass
0x18003591b  call    cs:__imp_GetTokenInformation
0x180035921  test    eax, eax
0x180035923  jnz     short loc_180035992
0x180035925  call    cs:__imp_GetLastError
0x18003592b  mov     ebx, eax
0x18003592d  cmp     eax, 7Ah ; 'z'
0x180035930  jnz     short loc_180035954
0x180035932  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180035936  lea     rdx, ?nothrow@NCoreLibrary@@3Unothrow_t@std@@B; struct std::nothrow_t *
0x18003593d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180035942  mov     [rdi], rax
0x180035945  neg     rax
0x180035948  sbb     ebx, ebx
0x18003594a  not     ebx
0x18003594c  and     ebx, 8007000Eh
0x180035952  jmp     short loc_180035961
0x180035954  test    eax, eax
0x180035956  jle     short loc_180035961
0x180035958  movzx   ebx, ax
0x18003595b  or      ebx, 80070000h
0x180035961  test    ebx, ebx
0x180035963  js      short loc_180035997
0x180035965  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18003596a  lea     rax, [rsp+38h+arg_18]
0x18003596f  mov     r8, [rdi]; TokenInformation
0x180035972  mov     edx, 1; TokenInformationClass
0x180035977  mov     rcx, rsi; TokenHandle
0x18003597a  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18003597f  call    cs:__imp_GetTokenInformation
0x180035985  test    eax, eax
0x180035987  jnz     short loc_180035997
0x180035989  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18003598e  mov     ebx, eax
0x180035990  jmp     short loc_180035997
0x180035992  mov     ebx, 80004005h
0x180035997  mov     rsi, [rsp+38h+arg_8]
0x18003599c  mov     eax, ebx
0x18003599e  mov     rbx, [rsp+38h+arg_0]
0x1800359a3  add     rsp, 30h
0x1800359a7  pop     rdi
0x1800359a8  retn
```
