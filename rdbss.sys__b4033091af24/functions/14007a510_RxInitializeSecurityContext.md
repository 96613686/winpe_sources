# RxInitializeSecurityContext

- ea: `0x14007a510`
- end: `0x14007abfa`
- name: `RxInitializeSecurityContext`
- size: `1770`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140078fe0`

## callees

- `0x14000f500`
- `0x14001c544`
- `0x140022044`
- `0x1400220a4`
- `0x140022110`
- `0x14002266c`
- `0x1400226fc`
- `0x140022770`
- `0x140025be6`
- `0x14006de60`
- `0x14006e150`
- `0x14006e180`
- `0x14006f0e0`
- `0x14007a510`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14007a7e1`
- `ntoskrnl!ZwClose` at `0x14007a7e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a617`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a617`
- `ntoskrnl!SeQueryInformationToken` at `0x14007a5f9`
- `ntoskrnl!SeQueryInformationToken` at `0x14007a759`
- `ntoskrnl!SeQueryInformationToken` at `0x14007a771`
- `ntoskrnl!SeQueryInformationToken` at `0x14007a7fd`
- `ntoskrnl!SeQueryInformationToken` at `0x14007a837`
- `ntoskrnl!SeQueryInformationToken` at `0x14007a5f9`
- `ntoskrnl!SeQueryInformationToken` at `0x14007a759`
- `ntoskrnl!SeQueryInformationToken` at `0x14007a771`
- `ntoskrnl!SeQueryInformationToken` at `0x14007a7fd`
- `ntoskrnl!SeQueryInformationToken` at `0x14007a837`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14007a72e`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14007a72e`
- `ntoskrnl!SeLockSubjectContext` at `0x14007a5c2`
- `ntoskrnl!SeLockSubjectContext` at `0x14007a5c2`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14007a63e`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14007a812`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14007a930`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14007a63e`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14007a812`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14007a930`
- `ntoskrnl!SeTokenIsRestricted` at `0x14007a6fb`
- `ntoskrnl!SeTokenIsRestricted` at `0x14007a6fb`
- `ntoskrnl!SeQuerySessionIdToken` at `0x14007a741`
- `ntoskrnl!SeQuerySessionIdToken` at `0x14007a741`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14007a7b0`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14007a7b0`

## string_xrefs

- `0x14007a8ff`: `impersonation`

## pseudocode

```c
__int64 __fastcall RxInitializeSecurityContext(__int64 a1, __int128 *a2, __int64 a3)
{
  char v4; // r13
  NTSTATUS v5; // esi
  int v6; // ebx
  PSECURITY_SUBJECT_CONTEXT v7; // rdi
  PACCESS_TOKEN ClientToken; // r15
  PACCESS_TOKEN PrimaryToken; // r12
  NTSTATUS v10; // eax
  int v11; // ebx
  PACCESS_TOKEN v13; // rcx
  int v14; // edx
  __int64 v15; // r8
  int MostRestrictiveBlockNtlmTokenInformation; // eax
  unsigned __int8 v17; // bl
  char v18; // cl
  const char *v19; // rbx
  __int16 v20; // ax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdi
  __int64 v24; // rax
  __int64 v25; // rax
  char v26; // bl
  __int64 v27; // rdx
  __int128 *v28; // r9
  __int128 *v29; // rcx
  PSECURITY_SUBJECT_CONTEXT v30; // rcx
  PSECURITY_SUBJECT_CONTEXT v31; // rax
  PVOID v32; // [rsp+68h] [rbp-59h] BYREF
  struct _LUID AuthenticationId; // [rsp+70h] [rbp-51h] BYREF
  struct _LUID v34; // [rsp+78h] [rbp-49h] BYREF
  PVOID v35; // [rsp+80h] [rbp-41h] BYREF
  PVOID v36; // [rsp+88h] [rbp-39h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp-31h] BYREF
  PVOID TokenInformation; // [rsp+98h] [rbp-29h] BYREF
  const char *v39; // [rsp+A0h] [rbp-21h]
  __int128 v40; // [rsp+A8h] [rbp-19h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT *v41; // [rsp+B8h] [rbp-9h]
  __int128 v42; // [rsp+C0h] [rbp-1h] BYREF
  PSECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+128h] [rbp+67h] BYREF
  char v44; // [rsp+130h] [rbp+6Fh]
  int v45; // [rsp+138h] [rbp+77h]
  PVOID v46; // [rsp+140h] [rbp+7Fh] BYREF

  v4 = 0;
  SubjectContext = 0;
  TokenInformation = 0;
  v35 = 0;
  LODWORD(v46) = 0;
  Handle = 0;
  AuthenticationId = 0;
  v34 = 0;
  LODWORD(v36) = 0;
  LODWORD(v32) = 1;
  v41 = 0;
  if ( *(char *)(a1 + 749) >= 0 )
  {
    v40 = 0;
    v42 = 0;
    v5 = RxSubjectContextFromRxContext(a1, &SubjectContext);
    if ( v5 < 0 )
    {
      v6 = 368;
      goto LABEL_14;
    }
    v7 = SubjectContext;
    SeLockSubjectContext(SubjectContext);
    ClientToken = v7->ClientToken;
    if ( v7->ClientToken )
    {
      if ( v7->ImpersonationLevel >= SecurityImpersonation )
      {
LABEL_7:
        PrimaryToken = v7->PrimaryToken;
        v6 = 0;
        v45 = 0;
        if ( !PrimaryToken )
          __int2c();
        v10 = SeQueryInformationToken(ClientToken, TokenImpersonationLevel, &TokenInformation);
        v5 = v10;
        if ( v10 >= 0 )
        {
          v11 = *(_DWORD *)TokenInformation;
          ExFreePoolWithTag(TokenInformation, 0);
LABEL_21:
          if ( (*(_DWORD *)(*(_QWORD *)(a1 + 80) + 336LL) & 0x8000) == 0
            && (SeTokenIsRestricted(ClientToken) || v11 < 2) )
          {
            v5 = -1073741790;
            v6 = 417;
            goto LABEL_13;
          }
          LOBYTE(SubjectContext) = 0;
          v44 = 0;
          SeQueryAuthenticationIdToken(ClientToken, &AuthenticationId);
          SeQuerySessionIdToken(ClientToken, (PULONG)&v35 + 1);
          SeQueryInformationToken(ClientToken, TokenIntegrityLevel, &v36);
          SeQueryInformationToken(ClientToken, TokenIsAppContainer, &v32);
          if ( (_DWORD)v32 )
          {
            v13 = v7->ClientToken;
            if ( !v7->ClientToken )
              v13 = v7->PrimaryToken;
            if ( ObOpenObjectByPointer(v13, 0x200u, 0, 8u, 0, 0, &Handle) >= 0 )
            {
              LOBYTE(SubjectContext) = RxCheckIsDevelopmentModeProcess(Handle);
              v44 = RxCheckIsRemoteFileAccessAllowedProcess(Handle);
            }
            if ( Handle )
            {
              ZwClose(Handle);
              Handle = 0;
            }
          }
          v5 = SeQueryInformationToken(ClientToken, TokenRestrictedDeviceClaimAttributes|TokenAuditPolicy, &v46);
          if ( v5 < 0 )
          {
LABEL_33:
            SeUnlockSubjectContext(v7);
            v6 = 0;
            goto LABEL_14;
          }
          if ( ClientToken == PrimaryToken )
          {
            MostRestrictiveBlockNtlmTokenInformation = (int)v46;
          }
          else
          {
            v5 = SeQueryInformationToken(PrimaryToken, TokenRestrictedDeviceClaimAttributes|TokenAuditPolicy, &v35);
            if ( v5 < 0 )
              goto LABEL_33;
            MostRestrictiveBlockNtlmTokenInformation = GetMostRestrictiveBlockNtlmTokenInformation(
                                                         (unsigned int)v46,
                                                         (unsigned int)v35);
          }
          v39 = 0;
          HIDWORD(v36) = 0;
          if ( (MostRestrictiveBlockNtlmTokenInformation & 0x20000000) != 0 )
          {
            v17 = 1;
          }
          else
          {
            v17 = 0;
            if ( (MostRestrictiveBlockNtlmTokenInformation & 0x40000000) == 0 )
              goto LABEL_44;
            v17 = 2;
          }
          if ( MostRestrictiveBlockNtlmTokenInformation < 0 )
            v17 |= 4u;
LABEL_44:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_dddq(WPP_GLOBAL_Control->AttachedDevice, v17 >> 2, v15, v17 & 1, (v17 >> 1) & 1, v17 >> 2, a1);
          }
          if ( ((v17 & 3) != 0 || v17 >= 4u)
            && ClientToken != PrimaryToken
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_Sq(WPP_GLOBAL_Control->AttachedDevice, v14, v15, (unsigned int)L"impersonation", a1);
          }
          v34 = AuthenticationId;
          if ( RxEnableLinkedConnections )
            RxpGetLinkedLuid(ClientToken, &v34);
          SeUnlockSubjectContext(v7);
          v18 = *(_BYTE *)(a1 + 749);
          if ( (v18 & 0x28) == 8 && (*(_DWORD *)(a1 + 528) & 4) != 0 )
          {
            AuthenticationId = (struct _LUID)-1LL;
            v34 = (struct _LUID)-1LL;
          }
          *(struct _LUID *)(a1 + 760) = AuthenticationId;
          *(struct _LUID *)(a1 + 768) = v34;
          *(_DWORD *)(a1 + 776) = HIDWORD(v35);
          *(_DWORD *)(a1 + 780) = (_DWORD)v36;
          *(_BYTE *)(a1 + 784) = (_BYTE)v32;
          *(_BYTE *)(a1 + 785) = (_BYTE)SubjectContext;
          *(_BYTE *)(a1 + 786) = v44;
          *(_BYTE *)(a1 + 787) = v17;
          if ( (v18 & 8) != 0 )
          {
            if ( *(_DWORD *)(a1 + 712) )
            {
              v19 = *(const char **)(a1 + 696);
              if ( v19 )
              {
                while ( 1 )
                {
                  if ( !strcmp_0(v19 + 8, "AuthIdentity") )
                  {
                    v4 = 1;
                    HIDWORD(v36) = *((unsigned __int16 *)v19 + 3);
                    v39 = &v19[*((unsigned __int8 *)v19 + 5) + 9];
                  }
                  else
                  {
                    if ( !strcmp_0(v19 + 8, "Transport") )
                    {
                      a2 = &v42;
                    }
                    else
                    {
                      if ( strcmp_0(v19 + 8, "Principal") )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                        {
                          WPP_SF_s(
                            WPP_GLOBAL_Control->AttachedDevice,
                            12,
                            WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids,
                            v19 + 8);
                        }
                        goto LABEL_75;
                      }
                      a2 = &v40;
                    }
                    v20 = *((_WORD *)v19 + 3);
                    v4 = 1;
                    if ( (v20 & 1) != 0 )
                    {
                      v5 = -1073741811;
                      v6 = 687;
                      goto LABEL_14;
                    }
                    v21 = *((unsigned __int8 *)v19 + 5) + 9LL;
                    *(_WORD *)a2 = v20;
                    *((_WORD *)a2 + 1) = v20;
                    *((_QWORD *)a2 + 1) = &v19[v21];
                  }
LABEL_75:
                  v22 = *(unsigned int *)v19;
                  if ( (_DWORD)v22 )
                  {
                    v19 += v22;
                    if ( v19 )
                      continue;
                  }
                  break;
                }
              }
            }
          }
          v23 = *((_QWORD *)&v40 + 1);
          if ( !*((_QWORD *)&v40 + 1) )
          {
            v24 = *(_QWORD *)(a1 + 560);
            if ( v24 == 4282664531LL || v24 == 289687123 )
            {
              v25 = *(_QWORD *)(a1 + 568);
              if ( *(_QWORD *)(v25 + 72) )
              {
                v23 = *(_QWORD *)(v25 + 72);
                v4 = 1;
                v40 = *(_OWORD *)(v25 + 64);
              }
            }
          }
          if ( (*(_BYTE *)(a1 + 749) & 0x28) == 8 && *(_DWORD *)(a1 + 716) )
          {
            v26 = 1;
          }
          else
          {
            v26 = 0;
            if ( !v4 )
            {
              v31 = v41;
              goto LABEL_102;
            }
          }
          SubjectContext = *(PSECURITY_SUBJECT_CONTEXT *)(a1 + 792);
          if ( SubjectContext )
          {
            RxDereferenceCredential();
            SubjectContext = 0;
            *(_QWORD *)(a1 + 792) = 0;
          }
          if ( v26 )
            v27 = *(_QWORD *)(a1 + 704);
          else
            v27 = 0;
          v28 = &v42;
          v29 = &v40;
          if ( !*((_QWORD *)&v42 + 1) )
            v28 = 0;
          if ( !v23 )
            v29 = 0;
          v5 = RxCreateCredential(&SubjectContext, v39, HIDWORD(v36), 0, 0, 0, v29, v28, v27);
          if ( v5 < 0 )
          {
            v30 = SubjectContext;
            if ( SubjectContext
              && _InterlockedExchangeAdd((volatile signed __int32 *)&SubjectContext->ClientToken + 1, 0xFFFFFFFF) == 1 )
            {
              RxpFreeCredential(v30);
              v6 = v45;
              goto LABEL_14;
            }
LABEL_103:
            v6 = v45;
            goto LABEL_14;
          }
          v31 = SubjectContext;
LABEL_102:
          *(_BYTE *)(a1 + 749) |= 0x80u;
          *(_QWORD *)(a1 + 792) = v31;
          goto LABEL_103;
        }
        if ( v10 == -1073741821 )
        {
          v11 = 2;
          goto LABEL_21;
        }
LABEL_13:
        SeUnlockSubjectContext(v7);
        goto LABEL_14;
      }
    }
    else
    {
      ClientToken = v7->PrimaryToken;
      if ( ClientToken )
        goto LABEL_7;
    }
    v5 = -1073741790;
    v6 = 380;
    goto LABEL_13;
  }
  v5 = 0;
  v6 = 353;
LABEL_14:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qDDDDqDd(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      a1,
      AuthenticationId.HighPart,
      AuthenticationId.LowPart,
      v34.HighPart,
      v34.LowPart,
      *(_QWORD *)(a1 + 792),
      v5,
      v6);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14007a510  mov     rax, rsp
0x14007a513  push    rbp
0x14007a514  push    rbx
0x14007a515  push    rsi
0x14007a516  push    r14
0x14007a518  lea     rbp, [rax-5Fh]
0x14007a51c  sub     rsp, 0F8h
0x14007a523  mov     [rax-30h], r12
0x14007a527  mov     r14, rcx
0x14007a52a  mov     [rax-38h], r13
0x14007a52e  xor     r13d, r13d
0x14007a531  mov     [rbp+57h+SubjectContext], r13
0x14007a535  mov     [rbp+57h+TokenInformation], r13
0x14007a539  mov     dword ptr [rbp+57h+var_98], r13d
0x14007a53d  mov     dword ptr [rbp+57h+arg_18], r13d
0x14007a541  mov     [rbp+57h+var_88], r13
0x14007a545  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], r13
0x14007a549  mov     [rbp+57h+var_A0], r13
0x14007a54d  mov     dword ptr [rbp+57h+var_98+4], r13d
0x14007a551  mov     dword ptr [rbp+57h+var_90], r13d
0x14007a555  mov     dword ptr [rbp+57h+var_B0], 1
0x14007a55c  mov     [rbp+57h+var_60], r13
0x14007a560  cmp     [rcx+2EDh], r13b
0x14007a567  jge     short loc_14007A57D
0x14007a569  mov     esi, r13d
0x14007a56c  lea     r12, WPP_GLOBAL_Control
0x14007a573  mov     ebx, 161h
0x14007a578  jmp     loc_14007A661
0x14007a57d  xorps   xmm0, xmm0
0x14007a580  lea     rdx, [rbp+57h+SubjectContext]
0x14007a584  xorps   xmm1, xmm1
0x14007a587  movups  [rbp+57h+var_70], xmm0
0x14007a58b  movups  [rbp+57h+var_58], xmm1
0x14007a58f  call    RxSubjectContextFromRxContext
0x14007a594  mov     esi, eax
0x14007a596  test    eax, eax
0x14007a598  jns     short loc_14007A5AB
0x14007a59a  mov     ebx, 170h
0x14007a59f  lea     r12, WPP_GLOBAL_Control
0x14007a5a6  jmp     loc_14007A661
0x14007a5ab  mov     [rsp+0F0h], rdi
0x14007a5b3  mov     rdi, [rbp+57h+SubjectContext]
0x14007a5b7  mov     rcx, rdi; SubjectContext
0x14007a5ba  mov     [rsp+110h+var_38], r15
0x14007a5c2  call    cs:__imp_SeLockSubjectContext
0x14007a5c9  nop     dword ptr [rax+rax+00h]
0x14007a5ce  mov     r15, [rdi]
0x14007a5d1  test    r15, r15
0x14007a5d4  jz      short loc_14007A628
0x14007a5d6  cmp     dword ptr [rdi+8], 2
0x14007a5da  jl      short loc_14007A631
0x14007a5dc  mov     r12, [rdi+10h]
0x14007a5e0  mov     ebx, r13d
0x14007a5e3  mov     [rbp+57h+arg_10], ebx
0x14007a5e6  test    r12, r12
0x14007a5e9  jnz     short loc_14007A5ED
0x14007a5eb  int     2Ch; Windows NT - assertion failure
0x14007a5ed  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14007a5f1  mov     edx, 9; TokenInformationClass
0x14007a5f6  mov     rcx, r15; Token
0x14007a5f9  call    cs:__imp_SeQueryInformationToken
0x14007a600  nop     dword ptr [rax+rax+00h]
0x14007a605  mov     esi, eax
0x14007a607  test    eax, eax
0x14007a609  js      loc_14007A6D8
0x14007a60f  mov     rcx, [rbp+57h+TokenInformation]; P
0x14007a613  xor     edx, edx; Tag
0x14007a615  mov     ebx, [rcx]
0x14007a617  call    cs:__imp_ExFreePoolWithTag
0x14007a61e  nop     dword ptr [rax+rax+00h]
0x14007a623  jmp     loc_14007A6E8
0x14007a628  mov     r15, [rdi+10h]
0x14007a62c  test    r15, r15
0x14007a62f  jnz     short loc_14007A5DC
0x14007a631  mov     esi, 0C0000022h
0x14007a636  mov     ebx, 17Ch
0x14007a63b  mov     rcx, rdi; SubjectContext
0x14007a63e  call    cs:__imp_SeUnlockSubjectContext
0x14007a645  nop     dword ptr [rax+rax+00h]
0x14007a64a  lea     r12, WPP_GLOBAL_Control
0x14007a651  mov     rdi, [rsp+0F0h]
0x14007a659  mov     r15, [rsp+110h+var_38]
0x14007a661  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a668  mov     r13, [rsp+110h+var_30]
0x14007a670  cmp     rcx, r12
0x14007a673  mov     r12, [rsp+110h+var_28]
0x14007a67b  jz      short loc_14007A6C8
0x14007a67d  test    dword ptr [rcx+2Ch], 1000h
0x14007a684  jz      short loc_14007A6C8
0x14007a686  cmp     byte ptr [rcx+29h], 2
0x14007a68a  jb      short loc_14007A6C8
0x14007a68c  mov     rax, [r14+318h]
0x14007a693  mov     r9, r14
0x14007a696  mov     rcx, [rcx+18h]
0x14007a69a  mov     [rsp+50h], ebx
0x14007a69e  mov     [rsp+110h+var_C8], esi
0x14007a6a2  mov     qword ptr [rsp+110h+var_D0], rax
0x14007a6a7  mov     eax, dword ptr [rbp+57h+var_A0]
0x14007a6aa  mov     dword ptr [rsp+110h+var_D8], eax
0x14007a6ae  mov     eax, dword ptr [rbp+57h+var_A0+4]
0x14007a6b1  mov     dword ptr [rsp+110h+Handle], eax
0x14007a6b5  mov     eax, [rbp+57h+AuthenticationId.LowPart]
0x14007a6b8  mov     dword ptr [rsp+110h+AccessMode], eax
0x14007a6bc  mov     eax, [rbp+57h+AuthenticationId.HighPart]
0x14007a6bf  mov     dword ptr [rsp+110h+ObjectType], eax
0x14007a6c3  call    WPP_SF_qDDDDqDd
0x14007a6c8  mov     eax, esi
0x14007a6ca  add     rsp, 0F8h
0x14007a6d1  pop     r14
0x14007a6d3  pop     rsi
0x14007a6d4  pop     rbx
0x14007a6d5  pop     rbp
0x14007a6d6  retn
0x14007a6d8  cmp     eax, 0C0000003h
0x14007a6dd  jnz     loc_14007A63B
0x14007a6e3  mov     ebx, 2
0x14007a6e8  mov     rax, [r14+50h]
0x14007a6ec  test    dword ptr [rax+150h], 8000h
0x14007a6f6  jnz     short loc_14007A71F
0x14007a6f8  mov     rcx, r15; Token
0x14007a6fb  call    cs:__imp_SeTokenIsRestricted
0x14007a702  nop     dword ptr [rax+rax+00h]
0x14007a707  test    al, al
0x14007a709  jnz     short loc_14007A710
0x14007a70b  cmp     ebx, 2
0x14007a70e  jge     short loc_14007A71F
0x14007a710  mov     esi, 0C0000022h
0x14007a715  mov     ebx, 1A1h
0x14007a71a  jmp     loc_14007A63B
0x14007a71f  lea     rdx, [rbp+57h+AuthenticationId]; AuthenticationId
0x14007a723  mov     byte ptr [rbp+57h+SubjectContext], r13b
0x14007a727  mov     rcx, r15; Token
0x14007a72a  mov     [rbp+57h+arg_8], r13b
0x14007a72e  call    cs:__imp_SeQueryAuthenticationIdToken
0x14007a735  nop     dword ptr [rax+rax+00h]
0x14007a73a  lea     rdx, [rbp+57h+var_98+4]; SessionId
0x14007a73e  mov     rcx, r15; Token
0x14007a741  call    cs:__imp_SeQuerySessionIdToken
0x14007a748  nop     dword ptr [rax+rax+00h]
0x14007a74d  lea     r8, [rbp+57h+var_90]; TokenInformation
0x14007a751  mov     edx, 19h; TokenInformationClass
0x14007a756  mov     rcx, r15; Token
0x14007a759  call    cs:__imp_SeQueryInformationToken
0x14007a760  nop     dword ptr [rax+rax+00h]
0x14007a765  lea     r8, [rbp+57h+var_B0]; TokenInformation
0x14007a769  mov     edx, 1Dh; TokenInformationClass
0x14007a76e  mov     rcx, r15; Token
0x14007a771  call    cs:__imp_SeQueryInformationToken
0x14007a778  nop     dword ptr [rax+rax+00h]
0x14007a77d  cmp     dword ptr [rbp+57h+var_B0], r13d
0x14007a781  jz      short loc_14007A7F1
0x14007a783  mov     rcx, [rdi]
0x14007a786  test    rcx, rcx
0x14007a789  jnz     short loc_14007A78F
0x14007a78b  mov     rcx, [rdi+10h]; Object
0x14007a78f  lea     rax, [rbp+57h+var_88]
0x14007a793  mov     r9d, 8; DesiredAccess
0x14007a799  mov     [rsp+110h+Handle], rax; Handle
0x14007a79e  xor     r8d, r8d; PassedAccessState
0x14007a7a1  mov     [rsp+110h+AccessMode], r13b; AccessMode
0x14007a7a6  mov     edx, 200h; HandleAttributes
0x14007a7ab  mov     [rsp+110h+ObjectType], r13; ObjectType
0x14007a7b0  call    cs:__imp_ObOpenObjectByPointer
0x14007a7b7  nop     dword ptr [rax+rax+00h]
0x14007a7bc  test    eax, eax
0x14007a7be  js      short loc_14007A7D8
0x14007a7c0  mov     rcx, [rbp+57h+var_88]
0x14007a7c4  call    RxCheckIsDevelopmentModeProcess
0x14007a7c9  mov     rcx, [rbp+57h+var_88]
0x14007a7cd  mov     byte ptr [rbp+57h+SubjectContext], al
0x14007a7d0  call    RxCheckIsRemoteFileAccessAllowedProcess
0x14007a7d5  mov     [rbp+57h+arg_8], al
0x14007a7d8  mov     rcx, [rbp+57h+var_88]; Handle
0x14007a7dc  test    rcx, rcx
0x14007a7df  jz      short loc_14007A7F1
0x14007a7e1  call    cs:__imp_ZwClose
0x14007a7e8  nop     dword ptr [rax+rax+00h]
0x14007a7ed  mov     [rbp+57h+var_88], r13
0x14007a7f1  lea     r8, [rbp+57h+arg_18]; TokenInformation
0x14007a7f5  mov     edx, 34h ; '4'; TokenInformationClass
0x14007a7fa  mov     rcx, r15; Token
0x14007a7fd  call    cs:__imp_SeQueryInformationToken
0x14007a804  nop     dword ptr [rax+rax+00h]
0x14007a809  mov     esi, eax
0x14007a80b  test    eax, eax
0x14007a80d  jns     short loc_14007A826
0x14007a80f  mov     rcx, rdi; SubjectContext
0x14007a812  call    cs:__imp_SeUnlockSubjectContext
0x14007a819  nop     dword ptr [rax+rax+00h]
0x14007a81e  mov     ebx, r13d
0x14007a821  jmp     loc_14007A64A
0x14007a826  cmp     r15, r12
0x14007a829  jz      short loc_14007A856
0x14007a82b  lea     r8, [rbp+57h+var_98]; TokenInformation
0x14007a82f  mov     edx, 34h ; '4'; TokenInformationClass
0x14007a834  mov     rcx, r12; Token
0x14007a837  call    cs:__imp_SeQueryInformationToken
0x14007a83e  nop     dword ptr [rax+rax+00h]
0x14007a843  mov     esi, eax
0x14007a845  test    eax, eax
0x14007a847  js      short loc_14007A80F
0x14007a849  mov     ecx, dword ptr [rbp+57h+arg_18]
0x14007a84c  mov     edx, dword ptr [rbp+57h+var_98]
0x14007a84f  call    GetMostRestrictiveBlockNtlmTokenInformation
0x14007a854  jmp     short loc_14007A859
0x14007a856  mov     eax, dword ptr [rbp+57h+arg_18]
0x14007a859  mov     [rbp+57h+var_78], r13
0x14007a85d  mov     dword ptr [rbp+57h+var_90+4], r13d
0x14007a861  bt      eax, 1Dh
0x14007a865  jnb     short loc_14007A86B
0x14007a867  mov     bl, 1
0x14007a869  jmp     short loc_14007A875
0x14007a86b  xor     bl, bl
0x14007a86d  bt      eax, 1Eh
0x14007a871  jnb     short loc_14007A87C
0x14007a873  mov     bl, 2
0x14007a875  test    eax, eax
0x14007a877  jns     short loc_14007A87C
0x14007a879  or      bl, 4
0x14007a87c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a883  lea     rax, WPP_GLOBAL_Control
0x14007a88a  cmp     rcx, rax
0x14007a88d  jz      short loc_14007A8D1
0x14007a88f  test    dword ptr [rcx+2Ch], 1000h
0x14007a896  jz      short loc_14007A8CA
0x14007a898  cmp     byte ptr [rcx+29h], 4
0x14007a89c  jb      short loc_14007A8CA
0x14007a89e  mov     rcx, [rcx+18h]
0x14007a8a2  movzx   r9d, bl
0x14007a8a6  mov     eax, r9d
0x14007a8a9  mov     [rsp+110h+Handle], r14
0x14007a8ae  mov     edx, r9d
0x14007a8b1  shr     eax, 1
0x14007a8b3  shr     edx, 2
0x14007a8b6  and     eax, 1
0x14007a8b9  mov     dword ptr [rsp+110h+AccessMode], edx
0x14007a8bd  and     r9d, 1
0x14007a8c1  mov     dword ptr [rsp+110h+ObjectType], eax
0x14007a8c5  call    WPP_SF_dddq
0x14007a8ca  lea     rax, WPP_GLOBAL_Control
0x14007a8d1  test    bl, 3
0x14007a8d4  jnz     short loc_14007A8DB
0x14007a8d6  cmp     bl, 4
0x14007a8d9  jb      short loc_14007A910
0x14007a8db  cmp     r15, r12
0x14007a8de  jz      short loc_14007A910
0x14007a8e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a8e7  cmp     rcx, rax
0x14007a8ea  jz      short loc_14007A910
0x14007a8ec  test    dword ptr [rcx+2Ch], 1000h
0x14007a8f3  jz      short loc_14007A910
0x14007a8f5  cmp     byte ptr [rcx+29h], 4
0x14007a8f9  jb      short loc_14007A910
0x14007a8fb  mov     rcx, [rcx+18h]
0x14007a8ff  lea     r9, aImpersonation; "impersonation"
0x14007a906  mov     [rsp+110h+ObjectType], r14
0x14007a90b  call    WPP_SF_Sq
0x14007a910  cmp     cs:RxEnableLinkedConnections, r13b
0x14007a917  mov     rax, qword ptr [rbp+57h+AuthenticationId.LowPart]
0x14007a91b  mov     [rbp+57h+var_A0], rax
0x14007a91f  jz      short loc_14007A92D
0x14007a921  lea     rdx, [rbp+57h+var_A0]
0x14007a925  mov     rcx, r15
0x14007a928  call    RxpGetLinkedLuid
0x14007a92d  mov     rcx, rdi; SubjectContext
0x14007a930  call    cs:__imp_SeUnlockSubjectContext
0x14007a937  nop     dword ptr [rax+rax+00h]
0x14007a93c  movzx   ecx, byte ptr [r14+2EDh]
0x14007a944  mov     r15, 0FFFFFFFFFFFFFFFFh
0x14007a94b  movzx   eax, cl
0x14007a94e  and     al, 28h
0x14007a950  cmp     al, 8
0x14007a952  jnz     short loc_14007A967
0x14007a954  mov     eax, [r14+210h]
0x14007a95b  test    al, 4
0x14007a95d  jz      short loc_14007A967
0x14007a95f  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], r15
0x14007a963  mov     [rbp+57h+var_A0], r15
0x14007a967  mov     rax, qword ptr [rbp+57h+AuthenticationId.LowPart]
0x14007a96b  lea     r12, WPP_GLOBAL_Control
0x14007a972  mov     [r14+2F8h], rax
0x14007a979  mov     rax, [rbp+57h+var_A0]
0x14007a97d  mov     [r14+300h], rax
0x14007a984  mov     eax, dword ptr [rbp+57h+var_98+4]
0x14007a987  mov     [r14+308h], eax
0x14007a98e  mov     eax, dword ptr [rbp+57h+var_90]
0x14007a991  mov     [r14+30Ch], eax
0x14007a998  movzx   eax, byte ptr [rbp+57h+var_B0]
0x14007a99c  mov     [r14+310h], al
0x14007a9a3  movzx   eax, byte ptr [rbp+57h+SubjectContext]
0x14007a9a7  mov     [r14+311h], al
0x14007a9ae  movzx   eax, [rbp+57h+arg_8]
0x14007a9b2  mov     [r14+312h], al
0x14007a9b9  mov     [r14+313h], bl
0x14007a9c0  test    cl, 8
0x14007a9c3  jz      loc_14007AABF
0x14007a9c9  cmp     dword ptr [r14+2C8h], 0
0x14007a9d1  jbe     loc_14007AABF
0x14007a9d7  mov     rbx, [r14+2B8h]
0x14007a9de  test    rbx, rbx
  ... truncated ...
```
