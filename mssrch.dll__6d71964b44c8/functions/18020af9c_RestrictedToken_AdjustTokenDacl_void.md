# RestrictedToken::AdjustTokenDacl(void *)

- ea: `0x18020af9c`
- end: `0x18020b117`
- name: `?AdjustTokenDacl@RestrictedToken@@QEAA_NPEAX@Z`
- size: `379`
- prototype: `bool(RestrictedToken *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e7000`

## callees

- `0x180119258`
- `0x1801249ec`
- `0x18020af9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020b006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020b006`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18020b0f1`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18020b0f1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18020b0ac`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18020b0ac`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18020afc1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18020afc1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18020b0d8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18020b0d8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18020afd2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18020afd2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18020b000`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18020b06b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18020b000`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18020b06b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18020b097`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18020b097`

## pseudocode

```c
char __fastcall RestrictedToken::AdjustTokenDacl(RestrictedToken *this, void *a2)
{
  DWORD LengthSid; // eax
  void *v5; // rcx
  DWORD v6; // ebx
  DWORD v7; // r14d
  __int64 v8; // rsi
  PACL *v9; // rax
  PACL *v10; // rbx
  DWORD v11; // esi
  DWORD ReturnLength; // [rsp+68h] [rbp+38h] BYREF
  PACL *v14; // [rsp+70h] [rbp+40h] BYREF
  LPVOID pAce; // [rsp+78h] [rbp+48h] BYREF

  if ( a2 && IsValidSid(a2) )
  {
    LengthSid = GetLengthSid(a2);
    v5 = (void *)*((_QWORD *)this + 1);
    v6 = LengthSid;
    ReturnLength = 0;
    v14 = 0;
    GetTokenInformation(v5, TokenDefaultDacl, 0, 0, &ReturnLength);
    if ( GetLastError() == 122 )
    {
      v7 = v6 + ReturnLength + 8;
      v8 = v7;
      v9 = (PACL *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v9;
      v10 = v9;
      if ( v9 )
      {
        if ( v7 )
        {
          do
          {
            *(_BYTE *)v9 = 0;
            v9 = (PACL *)((char *)v9 + 1);
            --v8;
          }
          while ( v8 );
        }
        if ( GetTokenInformation(*((HANDLE *)this + 1), TokenDefaultDacl, v10, v7, &ReturnLength) )
        {
          v11 = 0;
          (*v10)->AclSize = v7 - 8;
          pAce = 0;
          while ( GetAce(*v10, v11, &pAce) )
          {
            if ( EqualSid(a2, (char *)pAce + 8) )
              goto LABEL_12;
            ++v11;
          }
          if ( AddAccessAllowedAce(*v10, 2u, 0x20018u, a2)
            && SetTokenInformation(*((HANDLE *)this + 1), TokenDefaultDacl, v10, v7) )
          {
LABEL_12:
            std::unique_ptr<SQLiteDatabaseIdentifierValidatorFactory>::~unique_ptr<SQLiteDatabaseIdentifierValidatorFactory>(&v14);
            return 1;
          }
        }
      }
    }
    std::unique_ptr<SQLiteDatabaseIdentifierValidatorFactory>::~unique_ptr<SQLiteDatabaseIdentifierValidatorFactory>(&v14);
  }
  return 0;
}

```

## disassembly

```asm
0x18020af9c  mov     [rsp-28h+arg_0], rbx
0x18020afa1  push    rbp
0x18020afa2  push    rsi
0x18020afa3  push    rdi
0x18020afa4  push    r14
0x18020afa6  push    r15
0x18020afa8  mov     rbp, rsp
0x18020afab  sub     rsp, 30h
0x18020afaf  mov     rdi, rdx
0x18020afb2  mov     r15, rcx
0x18020afb5  test    rdx, rdx
0x18020afb8  jz      loc_18020B104
0x18020afbe  mov     rcx, rdx; pSid
0x18020afc1  call    cs:__imp_IsValidSid
0x18020afc7  test    eax, eax
0x18020afc9  jz      loc_18020B104
0x18020afcf  mov     rcx, rdi; pSid
0x18020afd2  call    cs:__imp_GetLengthSid
0x18020afd8  mov     rcx, [r15+8]; TokenHandle
0x18020afdc  xor     r9d, r9d; TokenInformationLength
0x18020afdf  mov     ebx, eax
0x18020afe1  mov     [rbp+arg_8], 0
0x18020afe8  lea     rax, [rbp+arg_8]
0x18020afec  mov     [rbp+arg_10], 0
0x18020aff4  xor     r8d, r8d; TokenInformation
0x18020aff7  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18020affc  lea     edx, [r9+6]; TokenInformationClass
0x18020b000  call    cs:__imp_GetTokenInformation
0x18020b006  call    cs:__imp_GetLastError
0x18020b00c  cmp     eax, 7Ah ; 'z'
0x18020b00f  jnz     loc_18020B0FB
0x18020b015  mov     r14d, [rbp+arg_8]
0x18020b019  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18020b020  add     r14d, 8
0x18020b024  add     r14d, ebx
0x18020b027  mov     ecx, r14d; unsigned __int64
0x18020b02a  mov     esi, r14d
0x18020b02d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18020b032  mov     [rbp+arg_10], rax
0x18020b036  mov     rbx, rax
0x18020b039  test    rax, rax
0x18020b03c  jz      loc_18020B0FB
0x18020b042  test    r14d, r14d
0x18020b045  jz      short loc_18020B053
0x18020b047  mov     byte ptr [rax], 0
0x18020b04a  inc     rax
0x18020b04d  sub     rsi, 1
0x18020b051  jnz     short loc_18020B047
0x18020b053  mov     rcx, [r15+8]; TokenHandle
0x18020b057  lea     rax, [rbp+arg_8]
0x18020b05b  mov     r9d, r14d; TokenInformationLength
0x18020b05e  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18020b063  mov     r8, rbx; TokenInformation
0x18020b066  mov     edx, 6; TokenInformationClass
0x18020b06b  call    cs:__imp_GetTokenInformation
0x18020b071  test    eax, eax
0x18020b073  jz      loc_18020B0FB
0x18020b079  mov     rax, [rbx]
0x18020b07c  lea     ecx, [r14-8]
0x18020b080  xor     esi, esi
0x18020b082  mov     [rax+2], cx
0x18020b086  mov     [rbp+pAce], 0
0x18020b08e  mov     rcx, [rbx]; pAcl
0x18020b091  lea     r8, [rbp+pAce]; pAce
0x18020b095  mov     edx, esi; dwAceIndex
0x18020b097  call    cs:__imp_GetAce
0x18020b09d  test    eax, eax
0x18020b09f  jz      short loc_18020B0C7
0x18020b0a1  mov     rdx, [rbp+pAce]
0x18020b0a5  mov     rcx, rdi; pSid1
0x18020b0a8  add     rdx, 8; pSid2
0x18020b0ac  call    cs:__imp_EqualSid
0x18020b0b2  test    eax, eax
0x18020b0b4  jnz     short loc_18020B0BA
0x18020b0b6  inc     esi
0x18020b0b8  jmp     short loc_18020B08E
0x18020b0ba  lea     rcx, [rbp+arg_10]
0x18020b0be  call    ??1?$unique_ptr@USQLiteDatabaseIdentifierValidatorFactory@@U?$default_delete@USQLiteDatabaseIdentifierValidatorFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<SQLiteDatabaseIdentifierValidatorFactory>::~unique_ptr<SQLiteDatabaseIdentifierValidatorFactory>(void)
0x18020b0c3  mov     al, 1
0x18020b0c5  jmp     short loc_18020B106
0x18020b0c7  mov     rcx, [rbx]; pAcl
0x18020b0ca  mov     r9, rdi; pSid
0x18020b0cd  mov     edx, 2; dwAceRevision
0x18020b0d2  mov     r8d, 20018h; AccessMask
0x18020b0d8  call    cs:__imp_AddAccessAllowedAce
0x18020b0de  test    eax, eax
0x18020b0e0  jz      short loc_18020B0FB
0x18020b0e2  mov     rcx, [r15+8]; TokenHandle
0x18020b0e6  mov     r9d, r14d; TokenInformationLength
0x18020b0e9  mov     r8, rbx; TokenInformation
0x18020b0ec  mov     edx, 6; TokenInformationClass
0x18020b0f1  call    cs:__imp_SetTokenInformation
0x18020b0f7  test    eax, eax
0x18020b0f9  jnz     short loc_18020B0BA
0x18020b0fb  lea     rcx, [rbp+arg_10]
0x18020b0ff  call    ??1?$unique_ptr@USQLiteDatabaseIdentifierValidatorFactory@@U?$default_delete@USQLiteDatabaseIdentifierValidatorFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<SQLiteDatabaseIdentifierValidatorFactory>::~unique_ptr<SQLiteDatabaseIdentifierValidatorFactory>(void)
0x18020b104  xor     al, al
0x18020b106  mov     rbx, [rsp+30h+arg_0]
0x18020b10b  add     rsp, 30h
0x18020b10f  pop     r15
0x18020b111  pop     r14
0x18020b113  pop     rdi
0x18020b114  pop     rsi
0x18020b115  pop     rbp
0x18020b116  retn
```
