# DetectCallerLogonTypeSid(void *,void * *)

- ea: `0x1800f0a2c`
- end: `0x1800f0c6c`
- name: `?DetectCallerLogonTypeSid@@YAJPEAXPEAPEAX@Z`
- size: `576`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005a4a0`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x1800ada18`
- `0x1800bd1ac`
- `0x1800bd218`
- `0x1800f0a2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0a6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0b7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0b8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0a6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0b7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0b8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0b9e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800f0bd2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800f0bd2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f0a5b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f0b6e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f0a5b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f0b6e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800f0c01`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800f0c01`

## pseudocode

```c
signed int __fastcall DetectCallerLogonTypeSid(HANDLE TokenHandle, void **a2)
{
  signed int result; // eax
  struct _RTL_BALANCED_NODE *v5; // rbx
  void *v6; // rdx
  void *v7; // rdx
  unsigned int LastError; // edi
  unsigned int i; // edi
  PSID *j; // rsi
  PSID v11; // r14
  DWORD TokenInformationLength; // [rsp+80h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength)
    || (result = GetLastError(), result == 122) )
  {
    v5 = (struct _RTL_BALANCED_NODE *)LsapAllocate(TokenInformationLength);
    if ( v5 )
    {
      if ( dword_1801A1530 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 4LL) )
      {
        Init_thread_header(&dword_1801A1530);
        if ( dword_1801A1530 == -1 )
        {
          qword_1801A0C78 = *((_QWORD *)WellKnownSids + 66);
          qword_1801A0C80 = *((_QWORD *)WellKnownSids + 174);
          qword_1801A0C88 = *((_QWORD *)WellKnownSids + 54);
          qword_1801A0C90 = *((_QWORD *)WellKnownSids + 60);
          qword_1801A0C98 = *((_QWORD *)WellKnownSids + 72);
          qword_1801A0CA0 = *((_QWORD *)WellKnownSids + 474);
          Init_thread_footer(&dword_1801A1530);
        }
      }
      if ( GetTokenInformation(TokenHandle, TokenGroups, v5, TokenInformationLength, &TokenInformationLength) )
      {
        for ( i = 0; i < LODWORD(v5->Children[0]); ++i )
        {
          if ( *GetSidSubAuthorityCount(v5->Children[2 * i + 1]) <= 1u )
          {
            for ( j = (PSID *)&qword_1801A0C78; j != (PSID *)&g_LocalKdcRunning; ++j )
            {
              v11 = *j;
              if ( EqualSid(v5->Children[2 * i + 1], *j) )
              {
                *a2 = v11;
                break;
              }
            }
          }
        }
        if ( !*a2
          && WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_fac8e1c640d53114d3306e5e667a867e_Traceguids);
        }
        LsapSubProv_FreeRoutine(v5, v6);
        return 0;
      }
      else
      {
        if ( (int)GetLastError() > 0 )
          LastError = (unsigned __int16)GetLastError() | 0xC0070000;
        else
          LastError = GetLastError();
        LsapSubProv_FreeRoutine(v5, v7);
        return LastError;
      }
    }
    else
    {
      return -1073741801;
    }
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0xC0070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800f0a2c  mov     rax, rsp
0x1800f0a2f  push    rbx
0x1800f0a30  push    rbp
0x1800f0a31  push    rsi
0x1800f0a32  push    rdi
0x1800f0a33  push    r14
0x1800f0a35  push    r15
0x1800f0a37  sub     rsp, 38h
0x1800f0a3b  xor     r9d, r9d; TokenInformationLength
0x1800f0a3e  mov     dword ptr [rax+18h], 0
0x1800f0a45  mov     r15, rdx
0x1800f0a48  lea     rax, [rax+18h]
0x1800f0a4c  xor     r8d, r8d; TokenInformation
0x1800f0a4f  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800f0a54  mov     rdi, rcx
0x1800f0a57  lea     edx, [r9+2]; TokenInformationClass
0x1800f0a5b  call    cs:__imp_GetTokenInformation
0x1800f0a62  nop     dword ptr [rax+rax+00h]
0x1800f0a67  test    eax, eax
0x1800f0a69  jnz     short loc_1800F0A91
0x1800f0a6b  call    cs:__imp_GetLastError
0x1800f0a72  nop     dword ptr [rax+rax+00h]
0x1800f0a77  cmp     eax, 7Ah ; 'z'
0x1800f0a7a  jz      short loc_1800F0A91
0x1800f0a7c  test    eax, eax
0x1800f0a7e  jle     loc_1800F0C5E
0x1800f0a84  movzx   eax, ax
0x1800f0a87  or      eax, 0C0070000h
0x1800f0a8c  jmp     loc_1800F0C5E
0x1800f0a91  mov     ecx, [rsp+68h+TokenInformationLength]
0x1800f0a98  call    LsapAllocate
0x1800f0a9d  mov     rbx, rax
0x1800f0aa0  test    rax, rax
0x1800f0aa3  jnz     short loc_1800F0AAF
0x1800f0aa5  mov     eax, 0C0000017h
0x1800f0aaa  jmp     loc_1800F0C5E
0x1800f0aaf  mov     ecx, cs:_tls_index
0x1800f0ab5  mov     rax, gs:58h
0x1800f0abe  mov     edx, 4
0x1800f0ac3  mov     rax, [rax+rcx*8]
0x1800f0ac7  mov     eax, [rdx+rax]
0x1800f0aca  cmp     cs:dword_1801A1530, eax
0x1800f0ad0  jle     short loc_1800F0B4E
0x1800f0ad2  lea     rcx, dword_1801A1530
0x1800f0ad9  call    _Init_thread_header
0x1800f0ade  cmp     cs:dword_1801A1530, 0FFFFFFFFh
0x1800f0ae5  jnz     short loc_1800F0B4E
0x1800f0ae7  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800f0aee  lea     rcx, dword_1801A1530
0x1800f0af5  mov     rax, [rdx+210h]
0x1800f0afc  mov     cs:qword_1801A0C78, rax
0x1800f0b03  mov     rax, [rdx+570h]
0x1800f0b0a  mov     cs:qword_1801A0C80, rax
0x1800f0b11  mov     rax, [rdx+1B0h]
0x1800f0b18  mov     cs:qword_1801A0C88, rax
0x1800f0b1f  mov     rax, [rdx+1E0h]
0x1800f0b26  mov     cs:qword_1801A0C90, rax
0x1800f0b2d  mov     rax, [rdx+240h]
0x1800f0b34  mov     cs:qword_1801A0C98, rax
0x1800f0b3b  mov     rax, [rdx+0ED0h]
0x1800f0b42  mov     cs:qword_1801A0CA0, rax
0x1800f0b49  call    _Init_thread_footer
0x1800f0b4e  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x1800f0b56  lea     rax, [rsp+68h+TokenInformationLength]
0x1800f0b5e  mov     r8, rbx; TokenInformation
0x1800f0b61  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800f0b66  mov     edx, 2; TokenInformationClass
0x1800f0b6b  mov     rcx, rdi; TokenHandle
0x1800f0b6e  call    cs:__imp_GetTokenInformation
0x1800f0b75  nop     dword ptr [rax+rax+00h]
0x1800f0b7a  test    eax, eax
0x1800f0b7c  jnz     short loc_1800F0BC2
0x1800f0b7e  call    cs:__imp_GetLastError
0x1800f0b85  nop     dword ptr [rax+rax+00h]
0x1800f0b8a  test    eax, eax
0x1800f0b8c  jg      short loc_1800F0B9E
0x1800f0b8e  call    cs:__imp_GetLastError
0x1800f0b95  nop     dword ptr [rax+rax+00h]
0x1800f0b9a  mov     edi, eax
0x1800f0b9c  jmp     short loc_1800F0BB3
0x1800f0b9e  call    cs:__imp_GetLastError
0x1800f0ba5  nop     dword ptr [rax+rax+00h]
0x1800f0baa  movzx   edi, ax
0x1800f0bad  or      edi, 0C0070000h
0x1800f0bb3  mov     rcx, rbx; struct _RTL_BALANCED_NODE *
0x1800f0bb6  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800f0bbb  mov     eax, edi
0x1800f0bbd  jmp     loc_1800F0C5E
0x1800f0bc2  xor     edi, edi
0x1800f0bc4  cmp     [rbx], edi
0x1800f0bc6  jbe     short loc_1800F0C20
0x1800f0bc8  mov     ebp, edi
0x1800f0bca  add     rbp, rbp
0x1800f0bcd  mov     rcx, [rbx+rbp*8+8]; pSid
0x1800f0bd2  call    cs:__imp_GetSidSubAuthorityCount
0x1800f0bd9  nop     dword ptr [rax+rax+00h]
0x1800f0bde  cmp     byte ptr [rax], 1
0x1800f0be1  ja      short loc_1800F0C1A
0x1800f0be3  lea     rsi, qword_1801A0C78
0x1800f0bea  lea     rax, ?g_LocalKdcRunning@@3_NA; bool g_LocalKdcRunning
0x1800f0bf1  cmp     rsi, rax
0x1800f0bf4  jz      short loc_1800F0C1A
0x1800f0bf6  mov     r14, [rsi]
0x1800f0bf9  mov     rcx, [rbx+rbp*8+8]; pSid1
0x1800f0bfe  mov     rdx, r14; pSid2
0x1800f0c01  call    cs:__imp_EqualSid
0x1800f0c08  nop     dword ptr [rax+rax+00h]
0x1800f0c0d  test    eax, eax
0x1800f0c0f  jnz     short loc_1800F0C17
0x1800f0c11  add     rsi, 8
0x1800f0c15  jmp     short loc_1800F0BEA
0x1800f0c17  mov     [r15], r14
0x1800f0c1a  inc     edi
0x1800f0c1c  cmp     edi, [rbx]
0x1800f0c1e  jb      short loc_1800F0BC8
0x1800f0c20  cmp     qword ptr [r15], 0
0x1800f0c24  jnz     short loc_1800F0C54
0x1800f0c26  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0c2d  lea     rax, WPP_GLOBAL_Control
0x1800f0c34  cmp     rcx, rax
0x1800f0c37  jz      short loc_1800F0C54
0x1800f0c39  test    byte ptr [rcx+1Ch], 2
0x1800f0c3d  jz      short loc_1800F0C54
0x1800f0c3f  mov     rcx, [rcx+10h]
0x1800f0c43  lea     r8, WPP_fac8e1c640d53114d3306e5e667a867e_Traceguids
0x1800f0c4a  mov     edx, 10h
0x1800f0c4f  call    WPP_SF_
0x1800f0c54  mov     rcx, rbx; struct _RTL_BALANCED_NODE *
0x1800f0c57  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800f0c5c  xor     eax, eax
0x1800f0c5e  add     rsp, 38h
0x1800f0c62  pop     r15
0x1800f0c64  pop     r14
0x1800f0c66  pop     rdi
0x1800f0c67  pop     rsi
0x1800f0c68  pop     rbp
0x1800f0c69  pop     rbx
0x1800f0c6a  retn
```
