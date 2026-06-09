# UtilGetTokenUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x18003b078`
- end: `0x18003b2e1`
- name: `?UtilGetTokenUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003ab24`

## callees

- `0x1800028b4`
- `0x1800028ec`
- `0x180002e90`
- `0x180009ed8`
- `0x180009f00`
- `0x180039c1c`
- `0x18003b078`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b0e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b0e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b189`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003b0da`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003b17f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003b0da`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003b17f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilGetTokenUserSid(HANDLE TokenHandle, const struct std::nothrow_t *a2)
{
  PSID *v4; // rsi
  PSID v5; // r15
  void *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  signed int LastError; // eax
  int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  signed int v15; // eax
  void *v16; // rcx
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  PSID v19; // [rsp+70h] [rbp+40h] BYREF
  __int64 v20; // [rsp+78h] [rbp+48h]

  v4 = 0;
  v20 = 0;
  TokenInformationLength = 0;
  v5 = 0;
  v19 = 0;
  if ( !a2 || !TokenHandle )
  {
    v12 = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    goto LABEL_39;
  }
  v6 = *(void **)a2;
  *(_QWORD *)a2 = 0;
  if ( v6 )
    operator delete(v6, a2);
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v12 = -2147418113;
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7, v9, v10);
    goto LABEL_39;
  }
  LastError = GetLastError();
  v12 = LastError;
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
  if ( v12 >= 0 )
  {
    v12 = -2147467259;
LABEL_11:
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 11;
LABEL_14:
      WPP_SF_d(v13[2], v14, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, (unsigned int)v12);
      goto LABEL_39;
    }
    goto LABEL_39;
  }
  if ( (_WORD)v12 != 122 )
    goto LABEL_11;
  v4 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
    {
      v12 = UtilDuplicateSid(*v4, &v19);
      if ( v12 >= 0 )
      {
        v5 = 0;
        v16 = *(void **)a2;
        *(_QWORD *)a2 = v19;
        if ( v16 )
          operator delete(v16, a2);
        v12 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
            (unsigned int)v12);
        v5 = v19;
      }
    }
    else
    {
      v15 = GetLastError();
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      if ( v15 >= 0 )
        v15 = -2147467259;
      v12 = v15;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 13;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v4 = 0;
    v12 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
        TokenInformationLength);
  }
LABEL_39:
  if ( v5 )
    operator delete(v5, a2);
  if ( v4 )
    operator delete(v4);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003b078  mov     [rsp-28h+arg_0], rbx
0x18003b07d  push    rbp
0x18003b07e  push    rsi
0x18003b07f  push    r12
0x18003b081  push    r14
0x18003b083  push    r15
0x18003b085  mov     rbp, rsp
0x18003b088  sub     rsp, 30h
0x18003b08c  mov     r14, rdx
0x18003b08f  mov     r12, rcx
0x18003b092  xor     esi, esi
0x18003b094  mov     [rbp+arg_18], rsi
0x18003b098  mov     [rbp+TokenInformationLength], esi
0x18003b09b  xor     r15d, r15d
0x18003b09e  mov     [rbp+arg_10], r15
0x18003b0a2  test    rdx, rdx
0x18003b0a5  jz      loc_18003B27E
0x18003b0ab  test    rcx, rcx
0x18003b0ae  jz      loc_18003B27E
0x18003b0b4  mov     rcx, [rdx]; void *
0x18003b0b7  mov     [rdx], r15
0x18003b0ba  test    rcx, rcx
0x18003b0bd  jz      short loc_18003B0C4
0x18003b0bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003b0c4  lea     rax, [rbp+TokenInformationLength]
0x18003b0c8  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18003b0cd  xor     r9d, r9d; TokenInformationLength
0x18003b0d0  xor     r8d, r8d; TokenInformation
0x18003b0d3  lea     edx, [r9+1]; TokenInformationClass
0x18003b0d7  mov     rcx, r12; TokenHandle
0x18003b0da  call    cs:__imp_GetTokenInformation
0x18003b0e0  test    eax, eax
0x18003b0e2  jnz     loc_18003B272
0x18003b0e8  call    cs:__imp_GetLastError
0x18003b0ee  mov     ebx, eax
0x18003b0f0  test    eax, eax
0x18003b0f2  jle     short loc_18003B0FD
0x18003b0f4  movzx   ebx, ax
0x18003b0f7  or      ebx, 80070000h
0x18003b0fd  test    ebx, ebx
0x18003b0ff  js      short loc_18003B108
0x18003b101  mov     ebx, 80004005h
0x18003b106  jmp     short loc_18003B10E
0x18003b108  cmp     bx, 7Ah ; 'z'
0x18003b10c  jz      short loc_18003B14C
0x18003b10e  lea     rax, WPP_GLOBAL_Control
0x18003b115  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b11c  cmp     rcx, rax
0x18003b11f  jz      loc_18003B2B2
0x18003b125  test    byte ptr [rcx+1Ch], 1
0x18003b129  jz      loc_18003B2B2
0x18003b12f  mov     edx, 0Bh
0x18003b134  mov     r9d, ebx
0x18003b137  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003b13e  mov     rcx, [rcx+10h]
0x18003b142  call    WPP_SF_d
0x18003b147  jmp     loc_18003B2B2
0x18003b14c  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x18003b14f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003b156  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003b15b  mov     rsi, rax
0x18003b15e  test    rax, rax
0x18003b161  jz      loc_18003B239
0x18003b167  lea     rax, [rbp+TokenInformationLength]
0x18003b16b  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18003b170  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18003b174  mov     r8, rsi; TokenInformation
0x18003b177  mov     edx, 1; TokenInformationClass
0x18003b17c  mov     rcx, r12; TokenHandle
0x18003b17f  call    cs:__imp_GetTokenInformation
0x18003b185  test    eax, eax
0x18003b187  jnz     short loc_18003B1D2
0x18003b189  call    cs:__imp_GetLastError
0x18003b18f  test    eax, eax
0x18003b191  jle     short loc_18003B19B
0x18003b193  movzx   eax, ax
0x18003b196  or      eax, 80070000h
0x18003b19b  mov     ebx, 80004005h
0x18003b1a0  test    eax, eax
0x18003b1a2  cmovns  eax, ebx
0x18003b1a5  mov     ebx, eax
0x18003b1a7  lea     rax, WPP_GLOBAL_Control
0x18003b1ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b1b5  cmp     rcx, rax
0x18003b1b8  jz      loc_18003B2B2
0x18003b1be  test    byte ptr [rcx+1Ch], 1
0x18003b1c2  jz      loc_18003B2B2
0x18003b1c8  mov     edx, 0Dh
0x18003b1cd  jmp     loc_18003B134
0x18003b1d2  lea     rdx, [rbp+arg_10]
0x18003b1d6  mov     rcx, [rsi]; pSourceSid
0x18003b1d9  call    ?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x18003b1de  mov     ebx, eax
0x18003b1e0  test    eax, eax
0x18003b1e2  jns     short loc_18003B21E
0x18003b1e4  lea     rax, WPP_GLOBAL_Control
0x18003b1eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b1f2  cmp     rcx, rax
0x18003b1f5  jz      short loc_18003B215
0x18003b1f7  test    byte ptr [rcx+1Ch], 1
0x18003b1fb  jz      short loc_18003B215
0x18003b1fd  mov     edx, 0Eh
0x18003b202  mov     r9d, ebx
0x18003b205  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003b20c  mov     rcx, [rcx+10h]
0x18003b210  call    WPP_SF_d
0x18003b215  mov     r15, [rbp+arg_10]
0x18003b219  jmp     loc_18003B2B2
0x18003b21e  mov     rax, [rbp+arg_10]
0x18003b222  xor     r15d, r15d
0x18003b225  mov     rcx, [r14]; void *
0x18003b228  mov     [r14], rax
0x18003b22b  test    rcx, rcx
0x18003b22e  jz      short loc_18003B235
0x18003b230  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003b235  xor     ebx, ebx
0x18003b237  jmp     short loc_18003B2B2
0x18003b239  xor     esi, esi
0x18003b23b  mov     ebx, 8007000Eh
0x18003b240  lea     rax, WPP_GLOBAL_Control
0x18003b247  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b24e  cmp     rcx, rax
0x18003b251  jz      short loc_18003B2B2
0x18003b253  test    byte ptr [rcx+1Ch], 1
0x18003b257  jz      short loc_18003B2B2
0x18003b259  lea     edx, [rsi+0Ch]
0x18003b25c  mov     r9d, [rbp+TokenInformationLength]
0x18003b260  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003b267  mov     rcx, [rcx+10h]
0x18003b26b  call    WPP_SF_d
0x18003b270  jmp     short loc_18003B2B2
0x18003b272  mov     ebx, 8000FFFFh
0x18003b277  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003b27c  jmp     short loc_18003B2B2
0x18003b27e  mov     ebx, 80070057h
0x18003b283  lea     rax, WPP_GLOBAL_Control
0x18003b28a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b291  cmp     rcx, rax
0x18003b294  jz      short loc_18003B2B2
0x18003b296  test    byte ptr [rcx+1Ch], 1
0x18003b29a  jz      short loc_18003B2B2
0x18003b29c  mov     edx, 0Ah
0x18003b2a1  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003b2a8  mov     rcx, [rcx+10h]
0x18003b2ac  call    WPP_SF_
0x18003b2b1  nop
0x18003b2b2  test    r15, r15
0x18003b2b5  jz      short loc_18003B2C0
0x18003b2b7  mov     rcx, r15; void *
0x18003b2ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003b2bf  nop
0x18003b2c0  test    rsi, rsi
0x18003b2c3  jz      short loc_18003B2CD
0x18003b2c5  mov     rcx, rsi; Block
0x18003b2c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003b2cd  mov     eax, ebx
0x18003b2cf  mov     rbx, [rsp+30h+arg_0]
0x18003b2d4  add     rsp, 30h
0x18003b2d8  pop     r15
0x18003b2da  pop     r14
0x18003b2dc  pop     r12
0x18003b2de  pop     rsi
0x18003b2df  pop     rbp
0x18003b2e0  retn
```
