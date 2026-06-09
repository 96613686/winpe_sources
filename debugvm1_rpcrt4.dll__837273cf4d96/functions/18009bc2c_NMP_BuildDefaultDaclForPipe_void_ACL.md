# NMP_BuildDefaultDaclForPipe(void *,_ACL * *)

- ea: `0x18009bc2c`
- end: `0x18009bffd`
- name: `?NMP_BuildDefaultDaclForPipe@@YAJPEAXPEAPEAU_ACL@@@Z`
- size: `977`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _ACL **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180084d8c`

## callees

- `0x180021e70`
- `0x180022870`
- `0x1800283bc`
- `0x18009bc2c`
- `0x1800ca049`
- `0x1800ca140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bcfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bf21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bf4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bf7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bcfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bf21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bf4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bf7a`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18009bd8c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18009bda5`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18009bdb6`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18009bd8c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18009bda5`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18009bdb6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18009bd7e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18009be92`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18009bd7e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18009be92`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18009bd69`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18009be80`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18009bd69`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18009be80`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18009bd47`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18009be5e`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18009bd47`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18009be5e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18009bd38`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18009be4f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18009bd38`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18009be4f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009bc94`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009bcf4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009bf17`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009bc94`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009bcf4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009bf17`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009be09`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009be2c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009beb2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009bf41`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009bf70`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009be09`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009be2c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009beb2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009bf41`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009bf70`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009bdee`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009bdee`

## pseudocode

```c
__int64 __fastcall NMP_BuildDefaultDaclForPipe(HANDLE TokenHandle, struct _ACL **a2)
{
  int v2; // r13d
  HANDLE v4; // r15
  unsigned int v5; // ebx
  DWORD LastError; // eax
  unsigned int *v7; // rdi
  DWORD v8; // eax
  int v9; // r12d
  unsigned int v10; // esi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v12; // ecx
  UCHAR *SidSubAuthorityCount; // r15
  DWORD SidLengthRequired; // eax
  DWORD v15; // edx
  DWORD v16; // ebx
  struct _ACL *v17; // rax
  __int64 *v18; // rbx
  unsigned int i; // ebx
  PSID_IDENTIFIER_AUTHORITY v20; // rax
  int v21; // ecx
  DWORD v22; // eax
  PSID *v23; // rcx
  DWORD v24; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v27; // [rsp+34h] [rbp-CCh]
  DWORD TokenInformationLength; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30; // [rsp+48h] [rbp-B8h]
  HANDLE v31; // [rsp+58h] [rbp-A8h]
  PSID TokenInformation[76]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 0;
  v31 = TokenHandle;
  *a2 = 0;
  TokenInformationLength = 0;
  ReturnLength = 0;
  v27 = 1280;
  v4 = TokenHandle;
  if ( GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength) )
    goto LABEL_2;
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v7 = (unsigned int *)AllocWrapper(TokenInformationLength);
    if ( !v7 )
      goto LABEL_2;
    if ( !GetTokenInformation(v4, TokenGroups, v7, TokenInformationLength, &TokenInformationLength) )
    {
      v8 = GetLastError();
      RpcpErrorAddRecord(2u, v8, 0xFDDu, 0, 0);
LABEL_8:
      v5 = 14;
LABEL_45:
      FreeWrapper(v7);
      goto LABEL_46;
    }
    v9 = 0;
    v10 = 0;
    if ( *v7 )
    {
      do
      {
        if ( IsValidSid(*(PSID *)&v7[4 * v10 + 2]) )
        {
          SidIdentifierAuthority = GetSidIdentifierAuthority(*(PSID *)&v7[4 * v10 + 2]);
          v12 = *(_DWORD *)SidIdentifierAuthority->Value - ReturnLength;
          if ( *(_DWORD *)SidIdentifierAuthority->Value == ReturnLength )
            v12 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - v27;
          if ( !v12 )
          {
            SidSubAuthorityCount = GetSidSubAuthorityCount(*(PSID *)&v7[4 * v10 + 2]);
            if ( *SidSubAuthorityCount )
            {
              if ( *GetSidSubAuthority(*(PSID *)&v7[4 * v10 + 2], 0) == 80 )
              {
                v2 += GetSidLengthRequired(*SidSubAuthorityCount);
                ++v9;
              }
            }
          }
        }
        ++v10;
      }
      while ( v10 < *v7 );
      v4 = v31;
    }
    SidLengthRequired = GetSidLengthRequired(0xFu);
    v15 = 12;
    if ( SidLengthRequired >= 0xC )
      v15 = GetSidLengthRequired(0xFu);
    v16 = v2 + 68 + v15 + 12 * v9;
    v17 = (struct _ACL *)AllocWrapper(v16);
    *a2 = v17;
    if ( !v17 )
      goto LABEL_8;
    InitializeAcl(v17, v16, 2u);
    v18 = qword_1800E3300;
    if ( AddAccessAllowedAce(*a2, 2u, 0x12019Bu, qword_1800E3300) )
    {
      v18 = qword_1800E32F0;
      if ( AddAccessAllowedAce(*a2, 2u, 0x12019Bu, qword_1800E32F0) )
      {
        for ( i = 0; i < *v7; ++i )
        {
          if ( IsValidSid(*(PSID *)&v7[4 * i + 2]) )
          {
            v20 = GetSidIdentifierAuthority(*(PSID *)&v7[4 * i + 2]);
            v21 = *(_DWORD *)v20->Value - ReturnLength;
            if ( *(_DWORD *)v20->Value == ReturnLength )
              v21 = *(unsigned __int16 *)&v20->Value[4] - v27;
            if ( !v21
              && *GetSidSubAuthorityCount(*(PSID *)&v7[4 * i + 2])
              && *GetSidSubAuthority(*(PSID *)&v7[4 * i + 2], 0) == 80
              && !AddAccessAllowedAce(*a2, 2u, 0x1F01FFu, *(PSID *)&v7[4 * i + 2]) )
            {
              v22 = GetLastError();
              LODWORD(v23) = 16 * i + (_DWORD)v7 + 8;
LABEL_34:
              v30 = (int)v23;
              goto LABEL_43;
            }
          }
        }
        if ( !v9 )
        {
          ReturnLength = 76;
          memset_0(TokenInformation, 0, sizeof(TokenInformation));
          if ( !GetTokenInformation(v4, TokenOwner, TokenInformation, 0x4Cu, &ReturnLength) )
          {
            v24 = GetLastError();
            RpcpErrorAddRecord(2u, v24, 0xFE9u, 0, 0);
LABEL_44:
            v5 = 1721;
            goto LABEL_45;
          }
          if ( !AddAccessAllowedAce(*a2, 2u, 0x1F01FFu, TokenInformation[0]) )
          {
            v22 = GetLastError();
            v23 = TokenInformation;
            goto LABEL_34;
          }
LABEL_49:
          FreeWrapper(v7);
          return 0;
        }
        v18 = qword_1800E3310;
        if ( AddAccessAllowedAce(*a2, 2u, 0x20000u, qword_1800E3310) )
          goto LABEL_49;
      }
    }
    v22 = GetLastError();
    v30 = (int)v18;
LABEL_43:
    v29 = 3;
    RpcpErrorAddRecord(2u, v22, 0xFE9u, 1, (struct tagParam *)&v29);
    goto LABEL_44;
  }
  RpcpErrorAddRecord(2u, LastError, 0xFDCu, 0, 0);
LABEL_2:
  v5 = 14;
LABEL_46:
  if ( *a2 )
    FreeWrapper(*a2);
  return v5;
}

```

## disassembly

```asm
0x18009bc2c  mov     [rsp-8+arg_10], rbx
0x18009bc31  push    rbp
0x18009bc32  push    rsi
0x18009bc33  push    rdi
0x18009bc34  push    r12
0x18009bc36  push    r13
0x18009bc38  push    r14
0x18009bc3a  push    r15
0x18009bc3c  lea     rbp, [rsp-1D0h]
0x18009bc44  sub     rsp, 2D0h
0x18009bc4b  mov     rax, cs:__security_cookie
0x18009bc52  xor     rax, rsp
0x18009bc55  mov     [rbp+200h+var_40], rax
0x18009bc5c  xor     r13d, r13d
0x18009bc5f  mov     [rsp+300h+var_2A8], rcx
0x18009bc64  mov     r14, rdx
0x18009bc67  mov     [rdx], r13
0x18009bc6a  lea     rax, [rsp+300h+TokenInformationLength]
0x18009bc6f  mov     [rsp+300h+TokenInformationLength], r13d
0x18009bc74  xor     r9d, r9d; TokenInformationLength
0x18009bc77  mov     [rsp+300h+var_2D0], r13d
0x18009bc7c  lea     ebx, [r13+2]
0x18009bc80  mov     [rsp+300h+var_2CC], 500h
0x18009bc87  mov     edx, ebx; TokenInformationClass
0x18009bc89  mov     [rsp+300h+ReturnLength], rax; ReturnLength
0x18009bc8e  xor     r8d, r8d; TokenInformation
0x18009bc91  mov     r15, rcx
0x18009bc94  call    cs:__imp_GetTokenInformation
0x18009bc9a  test    eax, eax
0x18009bc9c  jz      short loc_18009BCA8
0x18009bc9e  mov     ebx, 0Eh
0x18009bca3  jmp     loc_18009BFB8
0x18009bca8  call    cs:__imp_GetLastError
0x18009bcae  cmp     eax, 7Ah ; 'z'
0x18009bcb1  jz      short loc_18009BCCC
0x18009bcb3  mov     r8d, 0FDCh; unsigned __int16
0x18009bcb9  mov     [rsp+300h+ReturnLength], r13; struct tagParam *
0x18009bcbe  xor     r9d, r9d; int
0x18009bcc1  mov     edx, eax; int
0x18009bcc3  mov     ecx, ebx; unsigned int
0x18009bcc5  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18009bcca  jmp     short loc_18009BC9E
0x18009bccc  mov     ecx, [rsp+300h+TokenInformationLength]; dwBytes
0x18009bcd0  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18009bcd5  mov     rdi, rax
0x18009bcd8  test    rax, rax
0x18009bcdb  jz      short loc_18009BC9E
0x18009bcdd  mov     r9d, [rsp+300h+TokenInformationLength]; TokenInformationLength
0x18009bce2  lea     rax, [rsp+300h+TokenInformationLength]
0x18009bce7  mov     r8, rdi; TokenInformation
0x18009bcea  mov     [rsp+300h+ReturnLength], rax; ReturnLength
0x18009bcef  mov     edx, ebx; TokenInformationClass
0x18009bcf1  mov     rcx, r15; TokenHandle
0x18009bcf4  call    cs:__imp_GetTokenInformation
0x18009bcfa  test    eax, eax
0x18009bcfc  jnz     short loc_18009BD25
0x18009bcfe  call    cs:__imp_GetLastError
0x18009bd04  mov     r8d, 0FDDh; unsigned __int16
0x18009bd0a  mov     [rsp+300h+ReturnLength], r13; struct tagParam *
0x18009bd0f  mov     edx, eax; int
0x18009bd11  xor     r9d, r9d; int
0x18009bd14  mov     ecx, ebx; unsigned int
0x18009bd16  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18009bd1b  mov     ebx, 0Eh
0x18009bd20  jmp     loc_18009BFB0
0x18009bd25  xor     r12d, r12d
0x18009bd28  xor     esi, esi
0x18009bd2a  cmp     [rdi], esi
0x18009bd2c  jbe     short loc_18009BDA3
0x18009bd2e  mov     ebx, esi
0x18009bd30  add     rbx, rbx
0x18009bd33  mov     rcx, [rdi+rbx*8+8]; pSid
0x18009bd38  call    cs:__imp_IsValidSid
0x18009bd3e  test    eax, eax
0x18009bd40  jz      short loc_18009BD98
0x18009bd42  mov     rcx, [rdi+rbx*8+8]; pSid
0x18009bd47  call    cs:__imp_GetSidIdentifierAuthority
0x18009bd4d  mov     ecx, [rax]
0x18009bd4f  sub     ecx, [rsp+300h+var_2D0]
0x18009bd53  jnz     short loc_18009BD60
0x18009bd55  movzx   ecx, word ptr [rax+4]
0x18009bd59  movzx   eax, [rsp+300h+var_2CC]
0x18009bd5e  sub     ecx, eax
0x18009bd60  test    ecx, ecx
0x18009bd62  jnz     short loc_18009BD98
0x18009bd64  mov     rcx, [rdi+rbx*8+8]; pSid
0x18009bd69  call    cs:__imp_GetSidSubAuthorityCount
0x18009bd6f  mov     r15, rax
0x18009bd72  cmp     byte ptr [rax], 1
0x18009bd75  jb      short loc_18009BD98
0x18009bd77  mov     rcx, [rdi+rbx*8+8]; pSid
0x18009bd7c  xor     edx, edx; nSubAuthority
0x18009bd7e  call    cs:__imp_GetSidSubAuthority
0x18009bd84  cmp     dword ptr [rax], 50h ; 'P'
0x18009bd87  jnz     short loc_18009BD98
0x18009bd89  mov     cl, [r15]; nSubAuthorityCount
0x18009bd8c  call    cs:__imp_GetSidLengthRequired
0x18009bd92  add     r13d, eax
0x18009bd95  inc     r12d
0x18009bd98  inc     esi
0x18009bd9a  cmp     esi, [rdi]
0x18009bd9c  jb      short loc_18009BD2E
0x18009bd9e  mov     r15, [rsp+300h+var_2A8]
0x18009bda3  mov     cl, 0Fh; nSubAuthorityCount
0x18009bda5  call    cs:__imp_GetSidLengthRequired
0x18009bdab  mov     edx, 0Ch
0x18009bdb0  cmp     eax, edx
0x18009bdb2  jb      short loc_18009BDBE
0x18009bdb4  mov     cl, 0Fh; nSubAuthorityCount
0x18009bdb6  call    cs:__imp_GetSidLengthRequired
0x18009bdbc  mov     edx, eax
0x18009bdbe  lea     ecx, [r12+r12*2]
0x18009bdc2  add     r13d, 44h ; 'D'
0x18009bdc6  lea     ebx, [rdx+rcx*4]
0x18009bdc9  add     ebx, r13d
0x18009bdcc  mov     ecx, ebx; dwBytes
0x18009bdce  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18009bdd3  xor     r13d, r13d
0x18009bdd6  mov     [r14], rax
0x18009bdd9  test    rax, rax
0x18009bddc  jz      loc_18009BD1B
0x18009bde2  lea     esi, [r13+2]
0x18009bde6  mov     edx, ebx; nAclLength
0x18009bde8  mov     r8d, esi; dwAclRevision
0x18009bdeb  mov     rcx, rax; pAcl
0x18009bdee  call    cs:__imp_InitializeAcl
0x18009bdf4  mov     rcx, [r14]; pAcl
0x18009bdf7  lea     rbx, qword_1800E3300
0x18009bdfe  mov     r9, rbx; pSid
0x18009be01  mov     r8d, 12019Bh; AccessMask
0x18009be07  mov     edx, esi; dwAceRevision
0x18009be09  call    cs:__imp_AddAccessAllowedAce
0x18009be0f  test    eax, eax
0x18009be11  jz      loc_18009BF7A
0x18009be17  mov     rcx, [r14]; pAcl
0x18009be1a  lea     rbx, qword_1800E32F0
0x18009be21  mov     r9, rbx; pSid
0x18009be24  mov     r8d, 12019Bh; AccessMask
0x18009be2a  mov     edx, esi; dwAceRevision
0x18009be2c  call    cs:__imp_AddAccessAllowedAce
0x18009be32  test    eax, eax
0x18009be34  jz      loc_18009BF7A
0x18009be3a  mov     ebx, r13d
0x18009be3d  cmp     ebx, [rdi]
0x18009be3f  jnb     loc_18009BEDF
0x18009be45  mov     esi, ebx
0x18009be47  add     rsi, rsi
0x18009be4a  mov     rcx, [rdi+rsi*8+8]; pSid
0x18009be4f  call    cs:__imp_IsValidSid
0x18009be55  test    eax, eax
0x18009be57  jz      short loc_18009BED3
0x18009be59  mov     rcx, [rdi+rsi*8+8]; pSid
0x18009be5e  call    cs:__imp_GetSidIdentifierAuthority
0x18009be64  mov     ecx, [rax]
0x18009be66  sub     ecx, [rsp+300h+var_2D0]
0x18009be6a  jnz     short loc_18009BE77
0x18009be6c  movzx   ecx, word ptr [rax+4]
0x18009be70  movzx   eax, [rsp+300h+var_2CC]
0x18009be75  sub     ecx, eax
0x18009be77  test    ecx, ecx
0x18009be79  jnz     short loc_18009BED3
0x18009be7b  mov     rcx, [rdi+rsi*8+8]; pSid
0x18009be80  call    cs:__imp_GetSidSubAuthorityCount
0x18009be86  cmp     byte ptr [rax], 1
0x18009be89  jb      short loc_18009BED3
0x18009be8b  mov     rcx, [rdi+rsi*8+8]; pSid
0x18009be90  xor     edx, edx; nSubAuthority
0x18009be92  call    cs:__imp_GetSidSubAuthority
0x18009be98  cmp     dword ptr [rax], 50h ; 'P'
0x18009be9b  jnz     short loc_18009BED3
0x18009be9d  mov     r9, [rdi+rsi*8+8]; pSid
0x18009bea2  mov     r8d, 1F01FFh; AccessMask
0x18009bea8  mov     rcx, [r14]; pAcl
0x18009beab  mov     esi, 2
0x18009beb0  mov     edx, esi; dwAceRevision
0x18009beb2  call    cs:__imp_AddAccessAllowedAce
0x18009beb8  test    eax, eax
0x18009beba  jnz     short loc_18009BED8
0x18009bebc  call    cs:__imp_GetLastError
0x18009bec2  lea     ecx, [rdi+8]
0x18009bec5  shl     ebx, 4
0x18009bec8  add     ecx, ebx
0x18009beca  mov     [rsp+300h+var_2B8], ecx
0x18009bece  jmp     loc_18009BF84
0x18009bed3  mov     esi, 2
0x18009bed8  inc     ebx
0x18009beda  jmp     loc_18009BE3D
0x18009bedf  test    r12d, r12d
0x18009bee2  jnz     short loc_18009BF5B
0x18009bee4  lea     ebx, [r12+4Ch]
0x18009bee9  xor     edx, edx; Val
0x18009beeb  mov     r8d, 260h; Size
0x18009bef1  mov     [rsp+300h+var_2D0], ebx
0x18009bef5  lea     rcx, [rsp+300h+TokenInformation]; void *
0x18009befa  call    memset_0
0x18009beff  lea     rax, [rsp+300h+var_2D0]
0x18009bf04  mov     r9d, ebx; TokenInformationLength
0x18009bf07  lea     r8, [rsp+300h+TokenInformation]; TokenInformation
0x18009bf0c  mov     [rsp+300h+ReturnLength], rax; ReturnLength
0x18009bf11  lea     edx, [rbx-48h]; TokenInformationClass
0x18009bf14  mov     rcx, r15; TokenHandle
0x18009bf17  call    cs:__imp_GetTokenInformation
0x18009bf1d  test    eax, eax
0x18009bf1f  jnz     short loc_18009BF31
0x18009bf21  call    cs:__imp_GetLastError
0x18009bf27  xor     r9d, r9d
0x18009bf2a  mov     [rsp+300h+ReturnLength], r13
0x18009bf2f  jmp     short loc_18009BF9C
0x18009bf31  mov     r9, [rsp+300h+TokenInformation]; pSid
0x18009bf36  mov     r8d, 1F01FFh; AccessMask
0x18009bf3c  mov     rcx, [r14]; pAcl
0x18009bf3f  mov     edx, esi; dwAceRevision
0x18009bf41  call    cs:__imp_AddAccessAllowedAce
0x18009bf47  test    eax, eax
0x18009bf49  jnz     short loc_18009BFC9
0x18009bf4b  call    cs:__imp_GetLastError
0x18009bf51  lea     rcx, [rsp+300h+TokenInformation]
0x18009bf56  jmp     loc_18009BECA
0x18009bf5b  mov     rcx, [r14]; pAcl
0x18009bf5e  lea     rbx, qword_1800E3310
0x18009bf65  mov     r9, rbx; pSid
0x18009bf68  mov     r8d, 20000h; AccessMask
0x18009bf6e  mov     edx, esi; dwAceRevision
0x18009bf70  call    cs:__imp_AddAccessAllowedAce
0x18009bf76  test    eax, eax
0x18009bf78  jnz     short loc_18009BFC9
0x18009bf7a  call    cs:__imp_GetLastError
0x18009bf80  mov     [rsp+300h+var_2B8], ebx
0x18009bf84  lea     rcx, [rsp+300h+var_2C0]
0x18009bf89  mov     [rsp+300h+var_2C0], 3
0x18009bf91  mov     [rsp+300h+ReturnLength], rcx; struct tagParam *
0x18009bf96  mov     r9d, 1; int
0x18009bf9c  mov     r8d, 0FE9h; unsigned __int16
0x18009bfa2  mov     edx, eax; int
0x18009bfa4  mov     ecx, esi; unsigned int
0x18009bfa6  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18009bfab  mov     ebx, 6B9h
0x18009bfb0  mov     rcx, rdi; lpMem
0x18009bfb3  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009bfb8  mov     rcx, [r14]; lpMem
0x18009bfbb  test    rcx, rcx
0x18009bfbe  jz      short loc_18009BFC5
0x18009bfc0  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009bfc5  mov     eax, ebx
0x18009bfc7  jmp     short loc_18009BFD3
0x18009bfc9  mov     rcx, rdi; lpMem
0x18009bfcc  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009bfd1  xor     eax, eax
0x18009bfd3  mov     rcx, [rbp+200h+var_40]
0x18009bfda  xor     rcx, rsp; StackCookie
0x18009bfdd  call    __security_check_cookie
0x18009bfe2  mov     rbx, [rsp+300h+arg_10]
0x18009bfea  add     rsp, 2D0h
0x18009bff1  pop     r15
0x18009bff3  pop     r14
0x18009bff5  pop     r13
0x18009bff7  pop     r12
0x18009bff9  pop     rdi
0x18009bffa  pop     rsi
0x18009bffb  pop     rbp
0x18009bffc  retn
```
