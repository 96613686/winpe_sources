# LUASetUIAToken2

- ea: `0x18000a9cc`
- end: `0x18000ad1c`
- name: `LUASetUIAToken2`
- size: `848`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006cb4`

## callees

- `0x18000a9cc`
- `0x18000c5f4`
- `0x18000cd10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ace6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000acef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ace6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000acef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aaf9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000abb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aaf9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000abb8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000ac1b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000ac1b`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18000aba8`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18000ac0a`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18000aba8`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18000ac0a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000aae0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000ab1b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000aae0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000ab1b`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18000abdc`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18000abdc`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000ab4e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000ab4e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000ab35`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000ab35`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aa45`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aa83`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aab1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000ab7c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000abfa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aa45`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aa83`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aab1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000ab7c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000abfa`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18000ac59`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18000ac83`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18000ac59`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18000ac83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acd9`

## pseudocode

```c
__int64 __fastcall LUASetUIAToken2(HANDLE *a1)
{
  HANDLE v1; // rdi
  PSID *v3; // rsi
  void *v4; // r14
  DWORD LastError; // ebx
  HANDLE v6; // rbx
  HLOCAL v7; // rax
  PSID *v8; // rax
  PDWORD SidSubAuthority; // rcx
  int v10; // eax
  unsigned int v11; // eax
  DWORD cbSid; // [rsp+30h] [rbp-40h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-3Ch] BYREF
  WINBOOL IsMember; // [rsp+38h] [rbp-38h] BYREF
  int v16; // [rsp+3Ch] [rbp-34h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-30h] BYREF
  void *DuplicateTokenHandle; // [rsp+48h] [rbp-28h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+50h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+58h] [rbp-18h] BYREF

  v1 = *a1;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  ExistingTokenHandle = 0;
  v16 = 0;
  v3 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  DuplicateTokenHandle = 0;
  cbSid = 4;
  hObject = 0;
  IsMember = 0;
  v4 = 0;
  TokenInformation = 1;
  if ( !GetTokenInformation(v1, TokenUIAccess, &TokenInformation, 4u, &cbSid) )
    goto LABEL_2;
  LastError = 0;
  if ( TokenInformation != 1 )
  {
    if ( !GetTokenInformation(v1, TokenElevationType, &v16, 4u, &cbSid) )
      goto LABEL_2;
    if ( v16 == 3 )
    {
      if ( GetTokenInformation(v1, TokenLinkedToken, &ExistingTokenHandle, 8u, &cbSid) )
      {
        v6 = ExistingTokenHandle;
        if ( (unsigned int)LUAIsShadowAdminEnabled() )
        {
          cbSid = 0;
          if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, 0, &cbSid) )
          {
            LastError = 122;
            goto LABEL_32;
          }
          v7 = LocalAlloc(0, cbSid);
          v4 = v7;
          if ( !v7 )
          {
            LastError = 14;
            goto LABEL_32;
          }
          if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v7, &cbSid)
            || !DuplicateToken(v6, SecurityIdentification, &DuplicateTokenHandle)
            || !CheckTokenMembership(DuplicateTokenHandle, v4, &IsMember) )
          {
            goto LABEL_2;
          }
          if ( IsMember )
          {
            if ( !GetTokenInformation(v6, (TOKEN_INFORMATION_CLASS)-2, &hObject, 8u, &cbSid) )
              goto LABEL_2;
            v1 = hObject;
          }
        }
LABEL_20:
        cbSid = GetSidLengthRequired(1u) + 16;
        v8 = (PSID *)LocalAlloc(0, cbSid);
        v3 = v8;
        if ( !v8 )
        {
          LastError = 8;
          goto LABEL_32;
        }
        *v8 = v8 + 2;
        InitializeSid(v8 + 2, &pIdentifierAuthority, 1u);
        if ( !GetTokenInformation(v6, TokenIntegrityLevel, v3, cbSid, &cbSid) )
          goto LABEL_2;
        cbSid = GetSidLengthRequired(1u) + 16;
        SidSubAuthority = GetSidSubAuthority(*v3, 0);
        v10 = 0x2000;
        if ( *SidSubAuthority >= 0x2000 )
        {
          if ( *SidSubAuthority >= 0x3000 )
            goto LABEL_28;
          v10 = *SidSubAuthority;
        }
        v11 = v10 + 16;
        *SidSubAuthority = v11;
        if ( v11 > 0x3000 )
          *SidSubAuthority = 12288;
LABEL_28:
        *((_DWORD *)v3 + 2) = 96;
        if ( SetTokenInformation(v1, TokenIntegrityLevel, v3, cbSid) )
        {
          TokenInformation = 1;
          cbSid = 4;
          if ( SetTokenInformation(v1, TokenUIAccess, &TokenInformation, 4u) )
          {
            LastError = 0;
            if ( IsMember )
            {
              CloseHandle(*a1);
              *a1 = v1;
              hObject = 0;
            }
            goto LABEL_32;
          }
        }
LABEL_2:
        LastError = GetLastError();
        goto LABEL_32;
      }
      LastError = GetLastError();
      if ( LastError != 1312 )
        goto LABEL_32;
    }
    v6 = v1;
    goto LABEL_20;
  }
LABEL_32:
  if ( DuplicateTokenHandle )
  {
    CloseHandle(DuplicateTokenHandle);
    DuplicateTokenHandle = 0;
  }
  if ( ExistingTokenHandle )
  {
    CloseHandle(ExistingTokenHandle);
    ExistingTokenHandle = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  LocalFree(v4);
  LocalFree(v3);
  return LastError;
}

```

## disassembly

```asm
0x18000a9cc  mov     [rsp-28h+arg_8], rbx
0x18000a9d1  mov     [rsp-28h+arg_10], rsi
0x18000a9d6  push    rbp
0x18000a9d7  push    rdi
0x18000a9d8  push    r12
0x18000a9da  push    r14
0x18000a9dc  push    r15
0x18000a9de  mov     rbp, rsp
0x18000a9e1  sub     rsp, 70h
0x18000a9e5  mov     rax, cs:__security_cookie
0x18000a9ec  xor     rax, rsp
0x18000a9ef  mov     [rbp+var_10], rax
0x18000a9f3  mov     rdi, [rcx]
0x18000a9f6  lea     rax, [rbp+cbSid]
0x18000a9fa  xor     r12d, r12d
0x18000a9fd  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 1000h
0x18000aa03  mov     r15, rcx
0x18000aa06  mov     [rbp+ExistingTokenHandle], r12
0x18000aa0a  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000aa0e  mov     [rbp+var_34], r12d
0x18000aa12  mov     esi, r12d
0x18000aa15  mov     dword ptr [rbp+pIdentifierAuthority.Value], r12d
0x18000aa19  lea     ecx, [r12+4]
0x18000aa1e  mov     [rbp+DuplicateTokenHandle], r12
0x18000aa22  mov     [rbp+cbSid], ecx
0x18000aa25  lea     edx, [rcx+16h]; TokenInformationClass
0x18000aa28  mov     r9d, ecx; TokenInformationLength
0x18000aa2b  mov     [rbp+hObject], r12
0x18000aa2f  mov     rcx, rdi; TokenHandle
0x18000aa32  mov     [rbp+IsMember], r12d
0x18000aa36  mov     r14d, r12d
0x18000aa39  mov     [rbp+TokenInformation], 1
0x18000aa40  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18000aa45  call    cs:__imp_GetTokenInformation
0x18000aa4b  test    eax, eax
0x18000aa4d  jnz     short loc_18000AA5C
0x18000aa4f  call    cs:__imp_GetLastError
0x18000aa55  mov     ebx, eax
0x18000aa57  jmp     loc_18000ACAA
0x18000aa5c  cmp     [rbp+TokenInformation], 1
0x18000aa60  mov     ebx, r12d
0x18000aa63  jz      loc_18000ACAA
0x18000aa69  mov     r9d, 4; TokenInformationLength
0x18000aa6f  lea     rax, [rbp+cbSid]
0x18000aa73  lea     r8, [rbp+var_34]; TokenInformation
0x18000aa77  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18000aa7c  mov     rcx, rdi; TokenHandle
0x18000aa7f  lea     edx, [r9+0Eh]; TokenInformationClass
0x18000aa83  call    cs:__imp_GetTokenInformation
0x18000aa89  test    eax, eax
0x18000aa8b  jz      short loc_18000AA4F
0x18000aa8d  cmp     [rbp+var_34], 3
0x18000aa91  jnz     loc_18000ABA3
0x18000aa97  mov     r9d, 8; TokenInformationLength
0x18000aa9d  lea     rax, [rbp+cbSid]
0x18000aaa1  lea     r8, [rbp+ExistingTokenHandle]; TokenInformation
0x18000aaa5  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18000aaaa  mov     rcx, rdi; TokenHandle
0x18000aaad  lea     edx, [r9+0Bh]; TokenInformationClass
0x18000aab1  call    cs:__imp_GetTokenInformation
0x18000aab7  test    eax, eax
0x18000aab9  jz      loc_18000AB90
0x18000aabf  mov     rbx, [rbp+ExistingTokenHandle]
0x18000aac3  call    LUAIsShadowAdminEnabled
0x18000aac8  test    eax, eax
0x18000aaca  jz      loc_18000ABA6
0x18000aad0  xor     edx, edx; DomainSid
0x18000aad2  mov     [rbp+cbSid], r12d
0x18000aad6  lea     r9, [rbp+cbSid]; cbSid
0x18000aada  xor     r8d, r8d; pSid
0x18000aadd  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18000aae0  call    cs:__imp_CreateWellKnownSid
0x18000aae6  test    eax, eax
0x18000aae8  jz      short loc_18000AAF4
0x18000aaea  mov     ebx, 7Ah ; 'z'
0x18000aaef  jmp     loc_18000ACAA
0x18000aaf4  mov     edx, [rbp+cbSid]; uBytes
0x18000aaf7  xor     ecx, ecx; uFlags
0x18000aaf9  call    cs:__imp_LocalAlloc
0x18000aaff  mov     r14, rax
0x18000ab02  test    rax, rax
0x18000ab05  jnz     short loc_18000AB0F
0x18000ab07  lea     ebx, [rax+0Eh]
0x18000ab0a  jmp     loc_18000ACAA
0x18000ab0f  xor     edx, edx; DomainSid
0x18000ab11  lea     r9, [rbp+cbSid]; cbSid
0x18000ab15  mov     r8, r14; pSid
0x18000ab18  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18000ab1b  call    cs:__imp_CreateWellKnownSid
0x18000ab21  test    eax, eax
0x18000ab23  jz      loc_18000AA4F
0x18000ab29  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x18000ab2d  mov     edx, 1; ImpersonationLevel
0x18000ab32  mov     rcx, rbx; ExistingTokenHandle
0x18000ab35  call    cs:__imp_DuplicateToken
0x18000ab3b  test    eax, eax
0x18000ab3d  jz      loc_18000AA4F
0x18000ab43  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x18000ab47  lea     r8, [rbp+IsMember]; IsMember
0x18000ab4b  mov     rdx, r14; SidToCheck
0x18000ab4e  call    cs:__imp_CheckTokenMembership
0x18000ab54  test    eax, eax
0x18000ab56  jz      loc_18000AA4F
0x18000ab5c  cmp     [rbp+IsMember], r12d
0x18000ab60  jz      short loc_18000ABA6
0x18000ab62  mov     r9d, 8; TokenInformationLength
0x18000ab68  lea     rax, [rbp+cbSid]
0x18000ab6c  lea     r8, [rbp+hObject]; TokenInformation
0x18000ab70  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18000ab75  mov     rcx, rbx; TokenHandle
0x18000ab78  lea     edx, [r9-0Ah]; TokenInformationClass
0x18000ab7c  call    cs:__imp_GetTokenInformation
0x18000ab82  test    eax, eax
0x18000ab84  jz      loc_18000AA4F
0x18000ab8a  mov     rdi, [rbp+hObject]
0x18000ab8e  jmp     short loc_18000ABA6
0x18000ab90  call    cs:__imp_GetLastError
0x18000ab96  mov     ebx, eax
0x18000ab98  cmp     eax, 520h
0x18000ab9d  jnz     loc_18000ACAA
0x18000aba3  mov     rbx, rdi
0x18000aba6  mov     cl, 1; nSubAuthorityCount
0x18000aba8  call    cs:__imp_GetSidLengthRequired
0x18000abae  add     eax, 10h
0x18000abb1  xor     ecx, ecx; uFlags
0x18000abb3  mov     edx, eax; uBytes
0x18000abb5  mov     [rbp+cbSid], eax
0x18000abb8  call    cs:__imp_LocalAlloc
0x18000abbe  mov     rsi, rax
0x18000abc1  test    rax, rax
0x18000abc4  jnz     short loc_18000ABCE
0x18000abc6  lea     ebx, [rax+8]
0x18000abc9  jmp     loc_18000ACAA
0x18000abce  lea     rcx, [rax+10h]; Sid
0x18000abd2  mov     r8b, 1; nSubAuthorityCount
0x18000abd5  lea     rdx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18000abd9  mov     [rax], rcx
0x18000abdc  call    cs:__imp_InitializeSid
0x18000abe2  mov     r9d, [rbp+cbSid]; TokenInformationLength
0x18000abe6  lea     rax, [rbp+cbSid]
0x18000abea  mov     r8, rsi; TokenInformation
0x18000abed  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18000abf2  mov     edx, 19h; TokenInformationClass
0x18000abf7  mov     rcx, rbx; TokenHandle
0x18000abfa  call    cs:__imp_GetTokenInformation
0x18000ac00  test    eax, eax
0x18000ac02  jz      loc_18000AA4F
0x18000ac08  mov     cl, 1; nSubAuthorityCount
0x18000ac0a  call    cs:__imp_GetSidLengthRequired
0x18000ac10  add     eax, 10h
0x18000ac13  xor     edx, edx; nSubAuthority
0x18000ac15  mov     [rbp+cbSid], eax
0x18000ac18  mov     rcx, [rsi]; pSid
0x18000ac1b  call    cs:__imp_GetSidSubAuthority
0x18000ac21  mov     rcx, rax
0x18000ac24  mov     edx, 3000h
0x18000ac29  mov     eax, 2000h
0x18000ac2e  cmp     [rcx], eax
0x18000ac30  jb      short loc_18000AC38
0x18000ac32  cmp     [rcx], edx
0x18000ac34  jnb     short loc_18000AC43
0x18000ac36  mov     eax, [rcx]
0x18000ac38  add     eax, 10h
0x18000ac3b  mov     [rcx], eax
0x18000ac3d  cmp     eax, edx
0x18000ac3f  jbe     short loc_18000AC43
0x18000ac41  mov     [rcx], edx
0x18000ac43  mov     dword ptr [rsi+8], 60h ; '`'
0x18000ac4a  mov     r8, rsi; TokenInformation
0x18000ac4d  mov     r9d, [rbp+cbSid]; TokenInformationLength
0x18000ac51  mov     edx, 19h; TokenInformationClass
0x18000ac56  mov     rcx, rdi; TokenHandle
0x18000ac59  call    cs:__imp_SetTokenInformation
0x18000ac5f  test    eax, eax
0x18000ac61  jz      loc_18000AA4F
0x18000ac67  mov     eax, 4
0x18000ac6c  mov     [rbp+TokenInformation], 1
0x18000ac73  mov     r9d, eax; TokenInformationLength
0x18000ac76  mov     [rbp+cbSid], eax
0x18000ac79  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000ac7d  mov     rcx, rdi; TokenHandle
0x18000ac80  lea     edx, [rax+16h]; TokenInformationClass
0x18000ac83  call    cs:__imp_SetTokenInformation
0x18000ac89  test    eax, eax
0x18000ac8b  jz      loc_18000AA4F
0x18000ac91  mov     ebx, r12d
0x18000ac94  cmp     [rbp+IsMember], r12d
0x18000ac98  jz      short loc_18000ACAA
0x18000ac9a  mov     rcx, [r15]; hObject
0x18000ac9d  call    cs:__imp_CloseHandle
0x18000aca3  mov     [r15], rdi
0x18000aca6  mov     [rbp+hObject], r12
0x18000acaa  mov     rcx, [rbp+DuplicateTokenHandle]; hObject
0x18000acae  test    rcx, rcx
0x18000acb1  jz      short loc_18000ACBD
0x18000acb3  call    cs:__imp_CloseHandle
0x18000acb9  mov     [rbp+DuplicateTokenHandle], r12
0x18000acbd  mov     rcx, [rbp+ExistingTokenHandle]; hObject
0x18000acc1  test    rcx, rcx
0x18000acc4  jz      short loc_18000ACD0
0x18000acc6  call    cs:__imp_CloseHandle
0x18000accc  mov     [rbp+ExistingTokenHandle], r12
0x18000acd0  mov     rcx, [rbp+hObject]; hObject
0x18000acd4  test    rcx, rcx
0x18000acd7  jz      short loc_18000ACE3
0x18000acd9  call    cs:__imp_CloseHandle
0x18000acdf  mov     [rbp+hObject], r12
0x18000ace3  mov     rcx, r14; hMem
0x18000ace6  call    cs:__imp_LocalFree
0x18000acec  mov     rcx, rsi; hMem
0x18000acef  call    cs:__imp_LocalFree
0x18000acf5  mov     eax, ebx
0x18000acf7  mov     rcx, [rbp+var_10]
0x18000acfb  xor     rcx, rsp; StackCookie
0x18000acfe  call    __security_check_cookie
0x18000ad03  lea     r11, [rsp+70h+var_s0]
0x18000ad08  mov     rbx, [r11+38h]
0x18000ad0c  mov     rsi, [r11+40h]
0x18000ad10  mov     rsp, r11
0x18000ad13  pop     r15
0x18000ad15  pop     r14
0x18000ad17  pop     r12
0x18000ad19  pop     rdi
0x18000ad1a  pop     rbp
0x18000ad1b  retn
```
