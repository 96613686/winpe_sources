# UtilGetTokenIntegrityRid(void *,ulong *)

- ea: `0x18003af6c`
- end: `0x18003b071`
- name: `?UtilGetTokenIntegrityRid@@YAJPEAXPEAK@Z`
- size: `261`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003a9e8`

## callees

- `0x1800028ec`
- `0x180002e90`
- `0x18003af6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003afba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b04a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003afba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b04a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003afac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003b002`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003afac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003b002`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003b026`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003b026`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003b034`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003b034`

## pseudocode

```c
__int64 __fastcall UtilGetTokenIntegrityRid(HANDLE TokenHandle, unsigned int *a2)
{
  unsigned int v4; // ebx
  PSID *v5; // rdi
  signed int v6; // eax
  PUCHAR SidSubAuthorityCount; // rax
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      if ( v5 )
      {
        if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v5, TokenInformationLength, &TokenInformationLength) )
        {
          SidSubAuthorityCount = GetSidSubAuthorityCount(*v5);
          *a2 = *GetSidSubAuthority(*v5, (unsigned int)*SidSubAuthorityCount - 1);
          v4 = 0;
        }
        else
        {
          v6 = GetLastError();
          v4 = v6;
          if ( v6 > 0 )
            v4 = (unsigned __int16)v6 | 0x80070000;
        }
        operator delete(v5);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18003af6c  mov     [rsp+arg_0], rbx
0x18003af71  mov     [rsp+arg_10], rsi
0x18003af76  push    rdi
0x18003af77  sub     rsp, 30h
0x18003af7b  mov     rbx, rdx
0x18003af7e  mov     rsi, rcx
0x18003af81  test    rdx, rdx
0x18003af84  jnz     short loc_18003AF90
0x18003af86  mov     ebx, 80070057h
0x18003af8b  jmp     loc_18003B05F
0x18003af90  xor     r9d, r9d; TokenInformationLength
0x18003af93  mov     [rsp+38h+TokenInformationLength], 0
0x18003af9b  lea     rax, [rsp+38h+TokenInformationLength]
0x18003afa0  xor     r8d, r8d; TokenInformation
0x18003afa3  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18003afa8  lea     edx, [r9+19h]; TokenInformationClass
0x18003afac  call    cs:__imp_GetTokenInformation
0x18003afb2  test    eax, eax
0x18003afb4  jnz     loc_18003B04A
0x18003afba  call    cs:__imp_GetLastError
0x18003afc0  cmp     eax, 7Ah ; 'z'
0x18003afc3  jnz     loc_18003B04A
0x18003afc9  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18003afcd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003afd4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003afd9  mov     rdi, rax
0x18003afdc  test    rax, rax
0x18003afdf  jnz     short loc_18003AFE8
0x18003afe1  mov     ebx, 8007000Eh
0x18003afe6  jmp     short loc_18003B05F
0x18003afe8  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18003afed  lea     rax, [rsp+38h+TokenInformationLength]
0x18003aff2  mov     r8, rdi; TokenInformation
0x18003aff5  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18003affa  mov     edx, 19h; TokenInformationClass
0x18003afff  mov     rcx, rsi; TokenHandle
0x18003b002  call    cs:__imp_GetTokenInformation
0x18003b008  test    eax, eax
0x18003b00a  jnz     short loc_18003B023
0x18003b00c  call    cs:__imp_GetLastError
0x18003b012  mov     ebx, eax
0x18003b014  test    eax, eax
0x18003b016  jle     short loc_18003B040
0x18003b018  movzx   ebx, ax
0x18003b01b  or      ebx, 80070000h
0x18003b021  jmp     short loc_18003B040
0x18003b023  mov     rcx, [rdi]; pSid
0x18003b026  call    cs:__imp_GetSidSubAuthorityCount
0x18003b02c  mov     rcx, [rdi]; pSid
0x18003b02f  movzx   edx, byte ptr [rax]
0x18003b032  dec     edx; nSubAuthority
0x18003b034  call    cs:__imp_GetSidSubAuthority
0x18003b03a  mov     edx, [rax]
0x18003b03c  mov     [rbx], edx
0x18003b03e  xor     ebx, ebx
0x18003b040  mov     rcx, rdi; Block
0x18003b043  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003b048  jmp     short loc_18003B05F
0x18003b04a  call    cs:__imp_GetLastError
0x18003b050  mov     ebx, eax
0x18003b052  test    eax, eax
0x18003b054  jle     short loc_18003B05F
0x18003b056  movzx   ebx, ax
0x18003b059  or      ebx, 80070000h
0x18003b05f  mov     rsi, [rsp+38h+arg_10]
0x18003b064  mov     eax, ebx
0x18003b066  mov     rbx, [rsp+38h+arg_0]
0x18003b06b  add     rsp, 30h
0x18003b06f  pop     rdi
0x18003b070  retn
```
