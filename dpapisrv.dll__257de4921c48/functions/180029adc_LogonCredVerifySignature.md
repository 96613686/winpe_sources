# LogonCredVerifySignature

- ea: `0x180029adc`
- end: `0x180029e74`
- name: `LogonCredVerifySignature`
- size: `920`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle, UCHAR *, ULONG, unsigned __int8 *, struct _CRED_SIGNATURE *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026dbc`
- `0x180037ba8`

## callees

- `0x180002310`
- `0x180004d80`
- `0x180007f10`
- `0x18001c9c0`
- `0x18001d810`
- `0x18002955c`
- `0x180029adc`
- `0x18003c620`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180029cd0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180029cd0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180029b8d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180029b8d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180029caa`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180029caa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180029cfd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180029cfd`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180029b6e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180029b6e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180029e28`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180029e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180029bd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180029bd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029e3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029e3e`

## string_xrefs

- `0x180029baf`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180029c02`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
__int64 __fastcall LogonCredVerifySignature(
        HANDLE ExistingTokenHandle,
        UCHAR *a2,
        ULONG a3,
        unsigned __int8 *a4,
        struct _CRED_SIGNATURE *a5,
        unsigned int a6)
{
  int v6; // r13d
  HANDLE v8; // rcx
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  unsigned int v11; // eax
  __int64 v12; // r9
  int v13; // ecx
  unsigned int v14; // eax
  int v15; // r8d
  __int64 v16; // rdx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdx
  unsigned int v19; // r15d
  unsigned int v20; // r14d
  int v21; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-A0h] BYREF
  void *DuplicateTokenHandle; // [rsp+68h] [rbp-98h] BYREF
  ULONG cbInput; // [rsp+70h] [rbp-90h]
  struct _LUID v26; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 *v27; // [rsp+80h] [rbp-80h]
  PUCHAR pbInput; // [rsp+88h] [rbp-78h]
  UCHAR pbSecret[64]; // [rsp+90h] [rbp-70h] BYREF
  UCHAR Buf1[64]; // [rsp+D0h] [rbp-30h] BYREF

  v26 = 0;
  v6 = 0;
  DuplicateTokenHandle = 0;
  IsMember = 0;
  v27 = a4;
  cbInput = a3;
  pbInput = a2;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 43, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids);
  if ( ExistingTokenHandle )
  {
    if ( DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
    {
      v8 = DuplicateTokenHandle;
    }
    else
    {
      v8 = ExistingTokenHandle;
      DuplicateTokenHandle = ExistingTokenHandle;
    }
    if ( !ImpersonateLoggedOnUser(v8) )
    {
      LastError = GetLastError();
      DebugTraceError(
        LastError,
        "dwLastError",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
        2639);
      goto LABEL_46;
    }
    v6 = 1;
  }
  CurrentThread = GetCurrentThread();
  if ( !(unsigned int)GetThreadAuthenticationId(CurrentThread, &v26) )
  {
    v11 = GetLastError();
    v12 = 2650;
LABEL_13:
    LastError = v11;
LABEL_14:
    DebugTraceError(v11, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v12);
    goto LABEL_44;
  }
  if ( a5
    && a6 >= 0x30
    && (v13 = *(_DWORD *)a5, (unsigned int)(*(_DWORD *)a5 - 1) <= 1)
    && (v14 = *((_DWORD *)a5 + 10), v15 = *((_DWORD *)a5 + 11), v16 = v15 + v14, (unsigned int)v16 >= v14)
    && (v17 = (unsigned int)v16, v18 = v16 + 48, v18 >= v17)
    && v18 <= a6 )
  {
    v19 = 32782;
    if ( v13 != 2 )
      v19 = 32777;
    v20 = 64;
    if ( v13 != 2 )
      v20 = 20;
    if ( v15 != v20 )
    {
      v11 = 13;
      v12 = 2685;
      goto LABEL_13;
    }
    if ( !IsValidSid((char *)a5 + 48) )
    {
      v11 = 13;
      v12 = 2692;
      goto LABEL_13;
    }
    v21 = *((_DWORD *)a5 + 10);
    if ( v21 != GetLengthSid((char *)a5 + 48) )
    {
      v11 = 13;
      v12 = 2699;
      goto LABEL_13;
    }
    if ( !CheckTokenMembership(DuplicateTokenHandle, (char *)a5 + 48, &IsMember) )
    {
      v11 = GetLastError();
      v12 = 2708;
      goto LABEL_13;
    }
    if ( !IsMember )
      goto LABEL_34;
    v11 = LogonCredGenerateSignatureKey(&v26, 1, v27, a5, v19, pbSecret, v20);
    LastError = v11;
    if ( v11 )
    {
      v12 = 2729;
      goto LABEL_14;
    }
    if ( !(unsigned int)ReusableHMAC(0, 0, v19, pbSecret, v20, pbInput, cbInput, 0, 0, Buf1, v20) )
    {
      v11 = 13;
      v12 = 2744;
      goto LABEL_13;
    }
    if ( memcmp_0(Buf1, (char *)a5 + *((unsigned int *)a5 + 10) + 48, *((unsigned int *)a5 + 11)) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 47, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids);
LABEL_34:
      LastError = 12;
    }
  }
  else
  {
    LastError = 13;
  }
LABEL_44:
  if ( v6 )
    RevertToSelf();
LABEL_46:
  if ( DuplicateTokenHandle != ExistingTokenHandle )
    CloseHandle(DuplicateTokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180029adc  mov     [rsp-8+arg_10], rbx
0x180029ae1  push    rbp
0x180029ae2  push    rsi
0x180029ae3  push    rdi
0x180029ae4  push    r12
0x180029ae6  push    r13
0x180029ae8  push    r14
0x180029aea  push    r15
0x180029aec  lea     rbp, [rsp-20h]
0x180029af1  sub     rsp, 120h
0x180029af8  mov     rax, cs:__security_cookie
0x180029aff  xor     rax, rsp
0x180029b02  mov     [rbp+50h+var_40], rax
0x180029b06  mov     rdi, [rbp+50h+arg_20]
0x180029b0d  xor     ebx, ebx
0x180029b0f  mov     qword ptr [rsp+150h+var_D8.LowPart], rbx
0x180029b14  mov     r13d, ebx
0x180029b17  mov     [rsp+150h+DuplicateTokenHandle], rbx
0x180029b1c  mov     r12, rcx
0x180029b1f  mov     [rsp+150h+IsMember], ebx
0x180029b23  mov     [rbp+50h+var_D0], r9
0x180029b27  mov     [rsp+150h+var_E0], r8d
0x180029b2c  mov     [rbp+50h+var_C8], rdx
0x180029b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b37  lea     rax, WPP_GLOBAL_Control
0x180029b3e  cmp     rcx, rax
0x180029b41  jz      short loc_180029B5C
0x180029b43  test    byte ptr [rcx+1Ch], 4
0x180029b47  jz      short loc_180029B5C
0x180029b49  mov     rcx, [rcx+10h]
0x180029b4d  lea     edx, [rbx+2Bh]
0x180029b50  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x180029b57  call    WPP_SF_
0x180029b5c  test    r12, r12
0x180029b5f  jz      short loc_180029BD1
0x180029b61  lea     r8, [rsp+150h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180029b66  mov     edx, 2; ImpersonationLevel
0x180029b6b  mov     rcx, r12; ExistingTokenHandle
0x180029b6e  call    cs:__imp_DuplicateToken
0x180029b75  nop     dword ptr [rax+rax+00h]
0x180029b7a  test    eax, eax
0x180029b7c  jnz     short loc_180029B88
0x180029b7e  mov     rcx, r12
0x180029b81  mov     [rsp+150h+DuplicateTokenHandle], rcx
0x180029b86  jmp     short loc_180029B8D
0x180029b88  mov     rcx, [rsp+150h+DuplicateTokenHandle]; hToken
0x180029b8d  call    cs:__imp_ImpersonateLoggedOnUser
0x180029b94  nop     dword ptr [rax+rax+00h]
0x180029b99  test    eax, eax
0x180029b9b  jnz     short loc_180029BCB
0x180029b9d  call    cs:__imp_GetLastError
0x180029ba4  nop     dword ptr [rax+rax+00h]
0x180029ba9  mov     r9d, 0A4Fh
0x180029baf  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180029bb6  mov     ecx, eax
0x180029bb8  lea     rdx, aDwlasterror; "dwLastError"
0x180029bbf  mov     ebx, eax
0x180029bc1  call    DebugTraceError
0x180029bc6  jmp     loc_180029E34
0x180029bcb  mov     r13d, 1
0x180029bd1  call    cs:__imp_GetCurrentThread
0x180029bd8  nop     dword ptr [rax+rax+00h]
0x180029bdd  mov     rcx, rax
0x180029be0  lea     rdx, [rsp+150h+var_D8]
0x180029be5  call    GetThreadAuthenticationId
0x180029bea  test    eax, eax
0x180029bec  jnz     short loc_180029C1C
0x180029bee  call    cs:__imp_GetLastError
0x180029bf5  nop     dword ptr [rax+rax+00h]
0x180029bfa  mov     r9d, 0A5Ah
0x180029c00  mov     ebx, eax
0x180029c02  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180029c09  mov     ecx, eax
0x180029c0b  lea     rdx, aDwlasterror; "dwLastError"
0x180029c12  call    DebugTraceError
0x180029c17  jmp     loc_180029E23
0x180029c1c  test    rdi, rdi
0x180029c1f  jz      loc_180029E1E
0x180029c25  cmp     [rbp+50h+arg_28], 30h ; '0'
0x180029c2c  jb      loc_180029E1E
0x180029c32  mov     ecx, [rdi]
0x180029c34  lea     eax, [rcx-1]
0x180029c37  cmp     eax, 1
0x180029c3a  ja      loc_180029E1E
0x180029c40  mov     eax, [rdi+28h]
0x180029c43  mov     r8d, [rdi+2Ch]
0x180029c47  lea     edx, [r8+rax]
0x180029c4b  cmp     edx, eax
0x180029c4d  jb      loc_180029E1E
0x180029c53  mov     eax, edx
0x180029c55  add     rdx, 30h ; '0'
0x180029c59  cmp     rdx, rax
0x180029c5c  jb      loc_180029E1E
0x180029c62  mov     eax, [rbp+50h+arg_28]
0x180029c68  cmp     rdx, rax
0x180029c6b  ja      loc_180029E1E
0x180029c71  mov     eax, 8009h
0x180029c76  cmp     ecx, 2
0x180029c79  lea     r15d, [rax+5]
0x180029c7d  cmovnz  r15d, eax
0x180029c81  mov     eax, 14h
0x180029c86  lea     r14d, [rax+2Ch]
0x180029c8a  cmovnz  r14d, eax
0x180029c8e  cmp     r8d, r14d
0x180029c91  jz      short loc_180029CA3
0x180029c93  mov     eax, 0Dh
0x180029c98  mov     r9d, 0A7Dh
0x180029c9e  jmp     loc_180029C00
0x180029ca3  lea     rsi, [rdi+30h]
0x180029ca7  mov     rcx, rsi; pSid
0x180029caa  call    cs:__imp_IsValidSid
0x180029cb1  nop     dword ptr [rax+rax+00h]
0x180029cb6  test    eax, eax
0x180029cb8  jnz     short loc_180029CCA
0x180029cba  mov     eax, 0Dh
0x180029cbf  mov     r9d, 0A84h
0x180029cc5  jmp     loc_180029C00
0x180029cca  mov     ebx, [rdi+28h]
0x180029ccd  mov     rcx, rsi; pSid
0x180029cd0  call    cs:__imp_GetLengthSid
0x180029cd7  nop     dword ptr [rax+rax+00h]
0x180029cdc  cmp     ebx, eax
0x180029cde  jz      short loc_180029CF0
0x180029ce0  mov     eax, 0Dh
0x180029ce5  mov     r9d, 0A8Bh
0x180029ceb  jmp     loc_180029C00
0x180029cf0  mov     rcx, [rsp+150h+DuplicateTokenHandle]; TokenHandle
0x180029cf5  lea     r8, [rsp+150h+IsMember]; IsMember
0x180029cfa  mov     rdx, rsi; SidToCheck
0x180029cfd  call    cs:__imp_CheckTokenMembership
0x180029d04  nop     dword ptr [rax+rax+00h]
0x180029d09  test    eax, eax
0x180029d0b  jnz     short loc_180029D24
0x180029d0d  call    cs:__imp_GetLastError
0x180029d14  nop     dword ptr [rax+rax+00h]
0x180029d19  mov     r9d, 0A94h
0x180029d1f  jmp     loc_180029C00
0x180029d24  cmp     [rsp+150h+IsMember], 0
0x180029d29  jnz     short loc_180029D35
0x180029d2b  mov     ebx, 0Ch
0x180029d30  jmp     loc_180029E23
0x180029d35  mov     r8, [rbp+50h+var_D0]; unsigned __int8 *
0x180029d39  lea     rax, [rbp+50h+pbSecret]
0x180029d3d  mov     [rsp+150h+cbInput], r14d; unsigned int
0x180029d42  lea     rcx, [rsp+150h+var_D8]; struct _LUID *
0x180029d47  mov     [rsp+150h+pbInput], rax; unsigned __int8 *
0x180029d4c  mov     r9, rdi; struct _CRED_SIGNATURE *
0x180029d4f  mov     edx, 1; unsigned int
0x180029d54  mov     [rsp+150h+var_130], r15d; unsigned int
0x180029d59  call    ?LogonCredGenerateSignatureKey@@YAKPEAU_LUID@@KPEAEPEAU_CRED_SIGNATURE@@I1K@Z; LogonCredGenerateSignatureKey(_LUID *,ulong,uchar *,_CRED_SIGNATURE *,uint,uchar *,ulong)
0x180029d5e  mov     ebx, eax
0x180029d60  test    eax, eax
0x180029d62  jz      short loc_180029D6F
0x180029d64  mov     r9d, 0AA9h
0x180029d6a  jmp     loc_180029C02
0x180029d6f  mov     [rsp+150h+var_100], r14d; unsigned int
0x180029d74  lea     rax, [rbp+50h+Buf1]
0x180029d78  mov     [rsp+150h+pbOutput], rax; pbOutput
0x180029d7d  lea     r9, [rbp+50h+pbSecret]; pbSecret
0x180029d81  mov     eax, [rsp+150h+var_E0]
0x180029d85  mov     r8d, r15d; unsigned int
0x180029d88  mov     [rsp+150h+cbHashObject], 0; cbHashObject
0x180029d90  xor     edx, edx; hHash
0x180029d92  mov     [rsp+150h+pbHashObject], 0; pbHashObject
0x180029d9b  xor     ecx, ecx; hAlgorithm
0x180029d9d  mov     [rsp+150h+cbInput], eax; cbInput
0x180029da1  mov     rax, [rbp+50h+var_C8]
0x180029da5  mov     [rsp+150h+pbInput], rax; pbInput
0x180029daa  mov     [rsp+150h+var_130], r14d; ULONG
0x180029daf  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x180029db4  test    eax, eax
0x180029db6  jnz     short loc_180029DC8
0x180029db8  mov     eax, 0Dh
0x180029dbd  mov     r9d, 0AB8h
0x180029dc3  jmp     loc_180029C00
0x180029dc8  mov     edx, [rdi+28h]
0x180029dcb  lea     rcx, [rbp+50h+Buf1]; Buf1
0x180029dcf  mov     r8d, [rdi+2Ch]; Size
0x180029dd3  add     rdx, 30h ; '0'
0x180029dd7  add     rdx, rdi; Buf2
0x180029dda  call    memcmp_0
0x180029ddf  test    eax, eax
0x180029de1  jz      short loc_180029E23
0x180029de3  mov     rcx, cs:WPP_GLOBAL_Control
0x180029dea  lea     rax, WPP_GLOBAL_Control
0x180029df1  cmp     rcx, rax
0x180029df4  jz      loc_180029D2B
0x180029dfa  test    byte ptr [rcx+1Ch], 1
0x180029dfe  jz      loc_180029D2B
0x180029e04  mov     rcx, [rcx+10h]
0x180029e08  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x180029e0f  mov     edx, 2Fh ; '/'
0x180029e14  call    WPP_SF_
0x180029e19  jmp     loc_180029D2B
0x180029e1e  mov     ebx, 0Dh
0x180029e23  test    r13d, r13d
0x180029e26  jz      short loc_180029E34
0x180029e28  call    cs:__imp_RevertToSelf
0x180029e2f  nop     dword ptr [rax+rax+00h]
0x180029e34  mov     rcx, [rsp+150h+DuplicateTokenHandle]; hObject
0x180029e39  cmp     rcx, r12
0x180029e3c  jz      short loc_180029E4A
0x180029e3e  call    cs:__imp_CloseHandle
0x180029e45  nop     dword ptr [rax+rax+00h]
0x180029e4a  mov     eax, ebx
0x180029e4c  mov     rcx, [rbp+50h+var_40]
0x180029e50  xor     rcx, rsp; StackCookie
0x180029e53  call    __security_check_cookie
0x180029e58  mov     rbx, [rsp+150h+arg_10]
0x180029e60  add     rsp, 120h
0x180029e67  pop     r15
0x180029e69  pop     r14
0x180029e6b  pop     r13
0x180029e6d  pop     r12
0x180029e6f  pop     rdi
0x180029e70  pop     rsi
0x180029e71  pop     rbp
0x180029e72  retn
```
