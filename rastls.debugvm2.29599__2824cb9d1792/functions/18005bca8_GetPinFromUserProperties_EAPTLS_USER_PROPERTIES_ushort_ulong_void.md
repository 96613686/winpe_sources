# GetPinFromUserProperties(_EAPTLS_USER_PROPERTIES *,ushort * *,ulong *,void *)

- ea: `0x18005bca8`
- end: `0x18005bf98`
- name: `?GetPinFromUserProperties@@YAKPEAU_EAPTLS_USER_PROPERTIES@@PEAPEAGPEAKPEAX@Z`
- size: `752`
- prototype: `unsigned int(struct _EAPTLS_USER_PROPERTIES *, unsigned __int16 **, unsigned int *, void *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180052430`
- `0x180058e34`
- `0x18005905c`

## callees

- `0x180004bd0`
- `0x1800344dc`
- `0x18005b898`
- `0x18005bca8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005bef8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005bef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bd94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bd94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bed3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005be0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bec5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005be0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bec5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf54`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005bd8a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005bd8a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005be6c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005be6c`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18005bd47`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18005bd47`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18005bdca`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18005be4d`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18005bdca`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18005be4d`

## pseudocode

```c
__int64 __fastcall GetPinFromUserProperties(
        struct _EAPTLS_USER_PROPERTIES *a1,
        unsigned __int16 **a2,
        unsigned int *a3,
        void *a4)
{
  WCHAR *v5; // rsi
  unsigned int PinLengthInBytes; // eax
  __int64 v8; // r10
  unsigned __int8 v9; // r8
  unsigned int *v10; // r9
  DWORD InfoFromCredBuffer; // eax
  WCHAR *v12; // r14
  DWORD v13; // ebx
  __int64 v14; // r15
  struct _EAPTLS_CONTROL_BLOCK *v15; // rcx
  __int64 v16; // rdx
  WCHAR *v17; // rax
  WCHAR *v18; // rdx
  __int64 i; // rax
  WCHAR *v20; // rcx
  __int64 j; // rax
  unsigned __int16 **pcchMaxChars; // [rsp+20h] [rbp-40h]
  unsigned int *v24; // [rsp+28h] [rbp-38h]
  unsigned __int16 **v25; // [rsp+30h] [rbp-30h]
  CRED_PROTECTION_TYPE pProtectionType; // [rsp+50h] [rbp-10h] BYREF
  DWORD cchProtectedCredentials; // [rsp+54h] [rbp-Ch] BYREF
  LPWSTR pszProtectedCredentials; // [rsp+58h] [rbp-8h] BYREF
  DWORD v29; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int16 **v30; // [rsp+A8h] [rbp+48h]

  v30 = a2;
  pszProtectedCredentials = 0;
  v5 = 0;
  cchProtectedCredentials = 0;
  pProtectionType = CredUnprotected;
  v29 = 0;
  PinLengthInBytes = GetPinLengthInBytes(a1);
  InfoFromCredBuffer = GetInfoFromCredBuffer(
                         PinLengthInBytes,
                         *(unsigned __int8 **)(v8 + 56),
                         v9,
                         v10,
                         pcchMaxChars,
                         v24,
                         v25,
                         &cchProtectedCredentials,
                         &pszProtectedCredentials);
  v12 = pszProtectedCredentials;
  v13 = InfoFromCredBuffer;
  v14 = cchProtectedCredentials;
  if ( InfoFromCredBuffer )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_32;
    v16 = 22;
    goto LABEL_4;
  }
  if ( !CredIsProtectedW(pszProtectedCredentials, &pProtectionType) )
  {
    v29 = v14;
    v17 = (WCHAR *)LocalAlloc(0x40u, 2 * v14);
    v5 = v17;
    if ( !v17 )
    {
      InfoFromCredBuffer = GetLastError();
      v13 = InfoFromCredBuffer;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v16 = 29;
        goto LABEL_4;
      }
      goto LABEL_32;
    }
    _o_wcscpy_s(v17, v29, v12);
    goto LABEL_31;
  }
  cchProtectedCredentials = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids,
      (unsigned int)pProtectionType);
  if ( pProtectionType == CredTrustedProtection && !RevertToSelf() )
  {
    InfoFromCredBuffer = GetLastError();
    v13 = InfoFromCredBuffer;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v16 = 24;
LABEL_4:
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids, InfoFromCredBuffer);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  if ( CredUnprotectW(0, v12, v14, 0, &v29) || v29 )
  {
    cchProtectedCredentials = v29;
    v5 = (WCHAR *)LocalAlloc(0x40u, 2LL * v29);
    if ( !v5 )
    {
      InfoFromCredBuffer = GetLastError();
      v13 = InfoFromCredBuffer;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v16 = 26;
        goto LABEL_4;
      }
      goto LABEL_32;
    }
    if ( !CredUnprotectW(0, v12, v14, v5, &cchProtectedCredentials) || cchProtectedCredentials > v29 )
    {
      InfoFromCredBuffer = GetLastError();
      v13 = InfoFromCredBuffer;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v16 = 27;
        goto LABEL_4;
      }
      goto LABEL_32;
    }
    if ( pProtectionType == CredTrustedProtection && !ImpersonateLoggedOnUser(a4) )
    {
      InfoFromCredBuffer = GetLastError();
      v13 = InfoFromCredBuffer;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v16 = 28;
        goto LABEL_4;
      }
      goto LABEL_32;
    }
LABEL_31:
    *v30 = v5;
    *a3 = v29;
    goto LABEL_32;
  }
  InfoFromCredBuffer = GetLastError();
  v13 = InfoFromCredBuffer;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v16 = 25;
    goto LABEL_4;
  }
LABEL_32:
  if ( v12 )
  {
    v18 = v12;
    for ( i = 2 * v14; i; --i )
    {
      *(_BYTE *)v18 = 0;
      v18 = (WCHAR *)((char *)v18 + 1);
    }
    LocalFree(v12);
  }
  if ( v13 && v5 )
  {
    v20 = v5;
    for ( j = 2LL * v29; j; --j )
    {
      *(_BYTE *)v20 = 0;
      v20 = (WCHAR *)((char *)v20 + 1);
    }
    LocalFree(v5);
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x18005bca8  mov     [rsp-38h+arg_10], rbx
0x18005bcad  mov     [rsp-38h+arg_8], rdx
0x18005bcb2  push    rbp
0x18005bcb3  push    rsi
0x18005bcb4  push    rdi
0x18005bcb5  push    r12
0x18005bcb7  push    r13
0x18005bcb9  push    r14
0x18005bcbb  push    r15
0x18005bcbd  mov     rbp, rsp
0x18005bcc0  sub     rsp, 60h
0x18005bcc4  xor     edi, edi
0x18005bcc6  mov     r12, r9
0x18005bcc9  mov     [rbp+pszProtectedCredentials], rdi
0x18005bccd  mov     esi, edi
0x18005bccf  mov     [rbp+cchProtectedCredentials], edi
0x18005bcd2  mov     r13, r8
0x18005bcd5  mov     [rbp+pProtectionType], edi
0x18005bcd8  mov     r10, rcx
0x18005bcdb  mov     [rbp+arg_0], edi
0x18005bcde  call    ?GetPinLengthInBytes@@YAKPEBU_EAPTLS_USER_PROPERTIES@@@Z; GetPinLengthInBytes(_EAPTLS_USER_PROPERTIES const *)
0x18005bce3  mov     rdx, [r10+38h]; unsigned __int8 *
0x18005bce7  mov     ecx, eax; unsigned int
0x18005bce9  lea     rax, [rbp+pszProtectedCredentials]
0x18005bced  mov     [rsp+60h+var_20], rax; unsigned __int16 **
0x18005bcf2  lea     rax, [rbp+cchProtectedCredentials]
0x18005bcf6  mov     [rsp+60h+var_28], rax; unsigned int *
0x18005bcfb  call    ?GetInfoFromCredBuffer@@YAKKPEAEEPEAKPEAPEAG1212@Z; GetInfoFromCredBuffer(ulong,uchar *,uchar,ulong *,ushort * *,ulong *,ushort * *,ulong *,ushort * *)
0x18005bd00  mov     r14, [rbp+pszProtectedCredentials]
0x18005bd04  mov     ebx, eax
0x18005bd06  mov     r15d, [rbp+cchProtectedCredentials]
0x18005bd0a  test    eax, eax
0x18005bd0c  jz      short loc_18005BD40
0x18005bd0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bd15  lea     rdi, WPP_GLOBAL_Control
0x18005bd1c  cmp     rcx, rdi
0x18005bd1f  jz      loc_18005BF0C
0x18005bd25  lea     edx, [rsi+16h]
0x18005bd28  mov     rcx, [rcx+10h]
0x18005bd2c  lea     r8, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x18005bd33  mov     r9d, eax
0x18005bd36  call    WPP_SF_d
0x18005bd3b  jmp     loc_18005BF0C
0x18005bd40  lea     rdx, [rbp+pProtectionType]; pProtectionType
0x18005bd44  mov     rcx, r14; pszProtectedCredentials
0x18005bd47  call    cs:__imp_CredIsProtectedW
0x18005bd4d  lea     rdi, WPP_GLOBAL_Control
0x18005bd54  test    eax, eax
0x18005bd56  jz      loc_18005BEB6
0x18005bd5c  mov     [rbp+cchProtectedCredentials], esi
0x18005bd5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bd66  cmp     rcx, rdi
0x18005bd69  jz      short loc_18005BD84
0x18005bd6b  mov     r9d, [rbp+pProtectionType]
0x18005bd6f  lea     r8, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x18005bd76  mov     rcx, [rcx+10h]
0x18005bd7a  mov     edx, 17h
0x18005bd7f  call    WPP_SF_d
0x18005bd84  cmp     [rbp+pProtectionType], 2
0x18005bd88  jnz     short loc_18005BDB6
0x18005bd8a  call    cs:__imp_RevertToSelf
0x18005bd90  test    eax, eax
0x18005bd92  jnz     short loc_18005BDB6
0x18005bd94  call    cs:__imp_GetLastError
0x18005bd9a  mov     ebx, eax
0x18005bd9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bda3  cmp     rcx, rdi
0x18005bda6  jz      loc_18005BF0C
0x18005bdac  mov     edx, 18h
0x18005bdb1  jmp     loc_18005BD28
0x18005bdb6  lea     rax, [rbp+arg_0]
0x18005bdba  xor     r9d, r9d; pszCredentials
0x18005bdbd  mov     r8d, r15d; cchProtectedCredentials
0x18005bdc0  mov     [rsp+60h+pcchMaxChars], rax; pcchMaxChars
0x18005bdc5  mov     rdx, r14; pszProtectedCredentials
0x18005bdc8  xor     ecx, ecx; fAsSelf
0x18005bdca  call    cs:__imp_CredUnprotectW
0x18005bdd0  mov     ecx, [rbp+arg_0]
0x18005bdd3  test    eax, eax
0x18005bdd5  jnz     short loc_18005BDFD
0x18005bdd7  test    ecx, ecx
0x18005bdd9  jnz     short loc_18005BDFD
0x18005bddb  call    cs:__imp_GetLastError
0x18005bde1  mov     ebx, eax
0x18005bde3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bdea  cmp     rcx, rdi
0x18005bded  jz      loc_18005BF0C
0x18005bdf3  mov     edx, 19h
0x18005bdf8  jmp     loc_18005BD28
0x18005bdfd  mov     rdx, rcx
0x18005be00  mov     [rbp+cchProtectedCredentials], ecx
0x18005be03  add     rdx, rdx; uBytes
0x18005be06  mov     ecx, 40h ; '@'; uFlags
0x18005be0b  call    cs:__imp_LocalAlloc
0x18005be11  mov     rsi, rax
0x18005be14  test    rax, rax
0x18005be17  jnz     short loc_18005BE39
0x18005be19  call    cs:__imp_GetLastError
0x18005be1f  mov     ebx, eax
0x18005be21  mov     rcx, cs:WPP_GLOBAL_Control
0x18005be28  cmp     rcx, rdi
0x18005be2b  jz      loc_18005BF0C
0x18005be31  lea     edx, [rsi+1Ah]
0x18005be34  jmp     loc_18005BD28
0x18005be39  lea     rax, [rbp+cchProtectedCredentials]
0x18005be3d  mov     r9, rsi; pszCredentials
0x18005be40  mov     r8d, r15d; cchProtectedCredentials
0x18005be43  mov     [rsp+60h+pcchMaxChars], rax; pcchMaxChars
0x18005be48  mov     rdx, r14; pszProtectedCredentials
0x18005be4b  xor     ecx, ecx; fAsSelf
0x18005be4d  call    cs:__imp_CredUnprotectW
0x18005be53  test    eax, eax
0x18005be55  jz      short loc_18005BE98
0x18005be57  mov     eax, [rbp+arg_0]
0x18005be5a  cmp     [rbp+cchProtectedCredentials], eax
0x18005be5d  ja      short loc_18005BE98
0x18005be5f  cmp     [rbp+pProtectionType], 2
0x18005be63  jnz     loc_18005BEFE
0x18005be69  mov     rcx, r12; hToken
0x18005be6c  call    cs:__imp_ImpersonateLoggedOnUser
0x18005be72  test    eax, eax
0x18005be74  jnz     loc_18005BEFE
0x18005be7a  call    cs:__imp_GetLastError
0x18005be80  mov     ebx, eax
0x18005be82  mov     rcx, cs:WPP_GLOBAL_Control
0x18005be89  cmp     rcx, rdi
0x18005be8c  jz      short loc_18005BF0C
0x18005be8e  mov     edx, 1Ch
0x18005be93  jmp     loc_18005BD28
0x18005be98  call    cs:__imp_GetLastError
0x18005be9e  mov     ebx, eax
0x18005bea0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bea7  cmp     rcx, rdi
0x18005beaa  jz      short loc_18005BF0C
0x18005beac  mov     edx, 1Bh
0x18005beb1  jmp     loc_18005BD28
0x18005beb6  mov     rdx, r15
0x18005beb9  mov     [rbp+arg_0], r15d
0x18005bebd  add     rdx, rdx; uBytes
0x18005bec0  mov     ecx, 40h ; '@'; uFlags
0x18005bec5  call    cs:__imp_LocalAlloc
0x18005becb  mov     rsi, rax
0x18005bece  test    rax, rax
0x18005bed1  jnz     short loc_18005BEEF
0x18005bed3  call    cs:__imp_GetLastError
0x18005bed9  mov     ebx, eax
0x18005bedb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bee2  cmp     rcx, rdi
0x18005bee5  jz      short loc_18005BF0C
0x18005bee7  lea     edx, [rsi+1Dh]
0x18005beea  jmp     loc_18005BD28
0x18005beef  mov     edx, [rbp+arg_0]
0x18005bef2  mov     r8, r14
0x18005bef5  mov     rcx, rax
0x18005bef8  call    cs:__imp__o_wcscpy_s
0x18005befe  mov     rax, [rbp+arg_8]
0x18005bf02  mov     [rax], rsi
0x18005bf05  mov     eax, [rbp+arg_0]
0x18005bf08  mov     [r13+0], eax
0x18005bf0c  test    r14, r14
0x18005bf0f  jz      short loc_18005BF31
0x18005bf11  mov     rax, r15
0x18005bf14  mov     rdx, r14
0x18005bf17  add     rax, rax
0x18005bf1a  jz      short loc_18005BF28
0x18005bf1c  mov     byte ptr [rdx], 0
0x18005bf1f  inc     rdx
0x18005bf22  sub     rax, 1
0x18005bf26  jnz     short loc_18005BF1C
0x18005bf28  mov     rcx, r14; hMem
0x18005bf2b  call    cs:__imp_LocalFree
0x18005bf31  test    ebx, ebx
0x18005bf33  jz      short loc_18005BF5A
0x18005bf35  test    rsi, rsi
0x18005bf38  jz      short loc_18005BF5A
0x18005bf3a  mov     eax, [rbp+arg_0]
0x18005bf3d  mov     rcx, rsi
0x18005bf40  add     rax, rax
0x18005bf43  jz      short loc_18005BF51
0x18005bf45  mov     byte ptr [rcx], 0
0x18005bf48  inc     rcx
0x18005bf4b  sub     rax, 1
0x18005bf4f  jnz     short loc_18005BF45
0x18005bf51  mov     rcx, rsi; hMem
0x18005bf54  call    cs:__imp_LocalFree
0x18005bf5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bf61  cmp     rcx, rdi
0x18005bf64  jz      short loc_18005BF7E
0x18005bf66  mov     rcx, [rcx+10h]
0x18005bf6a  lea     r8, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x18005bf71  mov     edx, 1Eh
0x18005bf76  mov     r9d, ebx
0x18005bf79  call    WPP_SF_d
0x18005bf7e  mov     eax, ebx
0x18005bf80  mov     rbx, [rsp+60h+arg_10]
0x18005bf88  add     rsp, 60h
0x18005bf8c  pop     r15
0x18005bf8e  pop     r14
0x18005bf90  pop     r13
0x18005bf92  pop     r12
0x18005bf94  pop     rdi
0x18005bf95  pop     rsi
0x18005bf96  pop     rbp
0x18005bf97  retn
```
