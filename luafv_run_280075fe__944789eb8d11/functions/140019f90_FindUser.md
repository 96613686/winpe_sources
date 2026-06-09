# FindUser

- ea: `0x140019f90`
- end: `0x14001a30c`
- name: `FindUser`
- size: `892`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140019b10`

## callees

- `0x14000160c`
- `0x140001adc`
- `0x1400051a8`
- `0x140006080`
- `0x140006380`
- `0x140019f90`
- `0x14001b6a0`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x14001a082`
- `ntoskrnl!RtlEqualSid` at `0x14001a082`
- `ntoskrnl!SeQueryServerSiloToken` at `0x14001a04b`
- `ntoskrnl!SeQueryServerSiloToken` at `0x14001a04b`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14001a2cb`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14001a2cb`
- `ntoskrnl!RtlCopySid` at `0x14001a180`
- `ntoskrnl!RtlCopySid` at `0x14001a180`
- `ntoskrnl!SeMarkLogonSessionForTerminationNotificationEx` at `0x14001a1f1`
- `ntoskrnl!SeMarkLogonSessionForTerminationNotificationEx` at `0x14001a1f1`
- `ntoskrnl!RtlLengthSid` at `0x14001a23a`
- `ntoskrnl!RtlLengthSid` at `0x14001a23a`
- `ntoskrnl!SeQueryInformationToken` at `0x14001a015`
- `ntoskrnl!SeQueryInformationToken` at `0x14001a015`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001a2e8`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001a2e8`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14001a032`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14001a032`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14001a10c`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14001a15b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14001a10c`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14001a15b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a0f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a2fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a0f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a2fb`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14001a221`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14001a221`

## pseudocode

```c
__int64 __fastcall FindUser(__int64 a1, char a2, __int64 *a3)
{
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v7; // rcx
  char v8; // si
  struct _SECURITY_SUBJECT_CONTEXT *v9; // rbx
  PACCESS_TOKEN PrimaryToken; // rdi
  int UserWithToken; // ebx
  __int64 v12; // rbx
  void *v13; // r15
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // rbx
  PACCESS_TOKEN ClientToken; // rcx
  __int16 v17; // ax
  void *v18; // rcx
  __int64 v19; // rax
  PVOID v20; // rdx
  ULONG v21; // eax
  __int64 v22; // r8
  ULONG v23; // r13d
  ULONG v24; // r12d
  unsigned int v25; // ebx
  void *Pool; // rax
  __int64 v27; // rdi
  PVOID TokenInformation; // [rsp+20h] [rbp-48h] BYREF
  struct _LUID AuthenticationId; // [rsp+28h] [rbp-40h] BYREF
  void *Src[2]; // [rsp+30h] [rbp-38h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+40h] [rbp-28h] BYREF
  PVOID Object; // [rsp+C8h] [rbp+60h] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  TokenInformation = 0;
  AuthenticationId = 0;
  *(_OWORD *)Src = 0;
  Object = 0;
  IsEnabledDeviceUsageNoInline = Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline();
  v7 = *(_QWORD *)(a1 + 16);
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( *(_BYTE *)(v7 + 4) )
    {
      p_SubjectContext = &SubjectContext;
      SeCaptureSubjectContext(&SubjectContext);
      v8 = 1;
    }
    else
    {
      v8 = 0;
      p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL) + 32LL);
    }
    ClientToken = p_SubjectContext->ClientToken;
    if ( !p_SubjectContext->ClientToken )
      ClientToken = p_SubjectContext->PrimaryToken;
    UserWithToken = FindUserWithToken(ClientToken, a2, a3);
  }
  else
  {
    TokenInformation = 0;
    Src[1] = 0;
    if ( *(_BYTE *)(v7 + 4) )
    {
      v9 = &SubjectContext;
      SeCaptureSubjectContext(&SubjectContext);
      v8 = 1;
    }
    else
    {
      v8 = 0;
      v9 = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL) + 32LL);
    }
    PrimaryToken = v9->ClientToken;
    if ( !v9->ClientToken )
      PrimaryToken = v9->PrimaryToken;
    UserWithToken = SeQueryInformationToken(PrimaryToken, TokenUser, &TokenInformation);
    if ( UserWithToken >= 0 )
    {
      UserWithToken = SeQueryAuthenticationIdToken(PrimaryToken, &AuthenticationId);
      if ( UserWithToken >= 0 )
      {
        UserWithToken = SeQueryServerSiloToken(PrimaryToken, &Object);
        if ( UserWithToken >= 0 )
        {
          v12 = UserList;
          v13 = *(void **)TokenInformation;
          while ( (__int64 *)v12 != &UserList )
          {
            if ( RtlEqualSid(*(PSID *)(v12 + 80), v13) && *(PVOID *)(v12 + 56) == Object )
            {
              _InterlockedExchange64((volatile __int64 *)(v12 + 16), MEMORY[0xFFFFF78000000014]);
              *a3 = v12;
LABEL_15:
              UserWithToken = 0;
              goto LABEL_16;
            }
            v12 = *(_QWORD *)v12;
          }
          if ( !a2 )
          {
            *a3 = 0;
            goto LABEL_15;
          }
          UserWithToken = RtlConvertSidToUnicodeString((PUNICODE_STRING)Src, v13, 1u);
          if ( UserWithToken >= 0 )
          {
            v21 = RtlLengthSid(v13);
            LOBYTE(v22) = 15;
            v23 = v21;
            v24 = v21 + 1;
            v25 = ((v21 + 1) & 0xFFFFFFFE) + LOWORD(Src[0]) + 192;
            Pool = (void *)LuafvAllocatePool(1, v25, v22);
            v27 = (__int64)Pool;
            if ( Pool )
            {
              memset(Pool, 0, v25);
              *(_DWORD *)(v27 + 24) = 1;
              *(_QWORD *)(v27 + 16) = MEMORY[0xFFFFF78000000014];
              *(_QWORD *)(v27 + 40) = v27 + 32;
              *(_QWORD *)(v27 + 32) = v27 + 32;
              *(struct _LUID *)(v27 + 48) = AuthenticationId;
              if ( Object )
              {
                ObfReferenceObjectWithTag(Object, 0x6661754Cu);
                *(_QWORD *)(v27 + 56) = Object;
              }
              *(_QWORD *)(v27 + 80) = v27 + 192;
              RtlCopySid(v23, (PSID)(v27 + 192), v13);
              *(_WORD *)(v27 + 90) = Src[0];
              v17 = (__int16)Src[0];
              v18 = (void *)(v27 + 192 + (v24 & 0xFFFFFFFE));
              *(_QWORD *)(v27 + 96) = v18;
              *(_WORD *)(v27 + 88) = v17;
              memmove(v18, Src[1], LOWORD(Src[0]));
              v19 = UserList;
              if ( *(__int64 **)(UserList + 8) != &UserList )
                __fastfail(3u);
              *(_QWORD *)(v27 + 8) = &UserList;
              *(_QWORD *)v27 = v19;
              *(_QWORD *)(v19 + 8) = v27;
              v20 = Object;
              UserList = v27;
              *a3 = v27;
              SeMarkLogonSessionForTerminationNotificationEx(&AuthenticationId, v20);
              LuafvRunScavenger();
              goto LABEL_15;
            }
            UserWithToken = -1073741670;
          }
        }
      }
    }
  }
LABEL_16:
  if ( v8 )
    SeReleaseSubjectContext(&SubjectContext);
  if ( !(unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( Src[1] )
      ExFreePoolWithTag(Src[1], 0);
    if ( TokenInformation )
      ExFreePoolWithTag(TokenInformation, 0);
  }
  return (unsigned int)UserWithToken;
}

```

## disassembly

```asm
0x140019f90  push    rbp
0x140019f92  push    rbx
0x140019f93  push    rsi
0x140019f94  push    rdi
0x140019f95  push    r12
0x140019f97  push    r13
0x140019f99  push    r14
0x140019f9b  push    r15
0x140019f9d  mov     rbp, rsp
0x140019fa0  sub     rsp, 68h
0x140019fa4  xorps   xmm0, xmm0
0x140019fa7  xor     r13d, r13d
0x140019faa  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x140019fae  mov     [rbp+TokenInformation], r13
0x140019fb2  mov     r14, r8
0x140019fb5  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x140019fb9  mov     qword ptr [rbp+AuthenticationId.LowPart], r13
0x140019fbd  mov     r12b, dl
0x140019fc0  movups  xmmword ptr [rbp+Src], xmm0
0x140019fc4  mov     [rbp+Object], r13
0x140019fc8  mov     rbx, rcx
0x140019fcb  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x140019fd0  mov     rcx, [rbx+10h]
0x140019fd4  test    eax, eax
0x140019fd6  jnz     loc_14001A120
0x140019fdc  mov     [rbp+TokenInformation], r13
0x140019fe0  mov     [rbp+Src+8], r13
0x140019fe4  cmp     [rcx+4], r13b
0x140019fe8  jnz     loc_14001A104
0x140019fee  mov     rax, [rcx+18h]
0x140019ff2  mov     sil, r13b
0x140019ff5  mov     rbx, [rax+8]
0x140019ff9  add     rbx, 20h ; ' '
0x140019ffd  mov     rdi, [rbx]
0x14001a000  test    rdi, rdi
0x14001a003  jnz     short loc_14001A009
0x14001a005  mov     rdi, [rbx+10h]
0x14001a009  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14001a00d  mov     edx, 1; TokenInformationClass
0x14001a012  mov     rcx, rdi; Token
0x14001a015  call    cs:__imp_SeQueryInformationToken
0x14001a01c  nop     dword ptr [rax+rax+00h]
0x14001a021  mov     ebx, eax
0x14001a023  test    eax, eax
0x14001a025  js      loc_14001A0B8
0x14001a02b  lea     rdx, [rbp+AuthenticationId]; AuthenticationId
0x14001a02f  mov     rcx, rdi; Token
0x14001a032  call    cs:__imp_SeQueryAuthenticationIdToken
0x14001a039  nop     dword ptr [rax+rax+00h]
0x14001a03e  mov     ebx, eax
0x14001a040  test    eax, eax
0x14001a042  js      short loc_14001A0B8
0x14001a044  lea     rdx, [rbp+Object]
0x14001a048  mov     rcx, rdi
0x14001a04b  call    cs:__imp_SeQueryServerSiloToken
0x14001a052  nop     dword ptr [rax+rax+00h]
0x14001a057  mov     ebx, eax
0x14001a059  test    eax, eax
0x14001a05b  js      short loc_14001A0B8
0x14001a05d  mov     rax, [rbp+TokenInformation]
0x14001a061  mov     rbx, cs:UserList
0x14001a068  mov     r15, [rax]
0x14001a06b  lea     rax, UserList
0x14001a072  cmp     rbx, rax
0x14001a075  jz      loc_14001A20A
0x14001a07b  mov     rcx, [rbx+50h]; Sid1
0x14001a07f  mov     rdx, r15; Sid2
0x14001a082  call    cs:__imp_RtlEqualSid
0x14001a089  nop     dword ptr [rax+rax+00h]
0x14001a08e  test    al, al
0x14001a090  jnz     short loc_14001A097
0x14001a092  mov     rbx, [rbx]
0x14001a095  jmp     short loc_14001A06B
0x14001a097  mov     rax, [rbp+Object]
0x14001a09b  cmp     [rbx+38h], rax
0x14001a09f  jnz     short loc_14001A092
0x14001a0a1  mov     rax, 0FFFFF78000000014h
0x14001a0ab  mov     rax, [rax]
0x14001a0ae  xchg    rax, [rbx+10h]
0x14001a0b2  mov     [r14], rbx
0x14001a0b5  mov     ebx, r13d
0x14001a0b8  test    sil, sil
0x14001a0bb  jnz     loc_14001A2E4
0x14001a0c1  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x14001a0c6  test    eax, eax
0x14001a0c8  jz      short loc_14001A0DE
0x14001a0ca  mov     eax, ebx
0x14001a0cc  add     rsp, 68h
0x14001a0d0  pop     r15
0x14001a0d2  pop     r14
0x14001a0d4  pop     r13
0x14001a0d6  pop     r12
0x14001a0d8  pop     rdi
0x14001a0d9  pop     rsi
0x14001a0da  pop     rbx
0x14001a0db  pop     rbp
0x14001a0dc  retn
0x14001a0de  mov     rcx, [rbp+Src+8]; P
0x14001a0e2  test    rcx, rcx
0x14001a0e5  jnz     loc_14001A2F9
0x14001a0eb  mov     rcx, [rbp+TokenInformation]; P
0x14001a0ef  test    rcx, rcx
0x14001a0f2  jz      short loc_14001A0CA
0x14001a0f4  xor     edx, edx; Tag
0x14001a0f6  call    cs:__imp_ExFreePoolWithTag
0x14001a0fd  nop     dword ptr [rax+rax+00h]
0x14001a102  jmp     short loc_14001A0CA
0x14001a104  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14001a108  lea     rbx, [rbp+SubjectContext]
0x14001a10c  call    cs:__imp_SeCaptureSubjectContext
0x14001a113  nop     dword ptr [rax+rax+00h]
0x14001a118  mov     sil, 1
0x14001a11b  jmp     loc_140019FFD
0x14001a120  cmp     [rcx+4], r13b
0x14001a124  jnz     short loc_14001A153
0x14001a126  mov     rax, [rcx+18h]
0x14001a12a  mov     sil, r13b
0x14001a12d  mov     rbx, [rax+8]
0x14001a131  add     rbx, 20h ; ' '
0x14001a135  mov     rcx, [rbx]
0x14001a138  test    rcx, rcx
0x14001a13b  jnz     short loc_14001A141
0x14001a13d  mov     rcx, [rbx+10h]; Token
0x14001a141  mov     r8, r14
0x14001a144  mov     dl, r12b
0x14001a147  call    FindUserWithToken
0x14001a14c  mov     ebx, eax
0x14001a14e  jmp     loc_14001A0B8
0x14001a153  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14001a157  lea     rbx, [rbp+SubjectContext]
0x14001a15b  call    cs:__imp_SeCaptureSubjectContext
0x14001a162  nop     dword ptr [rax+rax+00h]
0x14001a167  mov     sil, 1
0x14001a16a  jmp     short loc_14001A135
0x14001a16c  lea     rbx, [rdi+0C0h]
0x14001a173  mov     r8, r15; SourceSid
0x14001a176  mov     rdx, rbx; DestinationSid
0x14001a179  mov     [rdi+50h], rbx
0x14001a17d  mov     ecx, r13d; DestinationSidLength
0x14001a180  call    cs:__imp_RtlCopySid
0x14001a187  nop     dword ptr [rax+rax+00h]
0x14001a18c  movzx   eax, word ptr [rbp+Src]
0x14001a190  mov     ecx, 0FFFFFFFEh
0x14001a195  mov     [rdi+5Ah], ax
0x14001a199  and     rcx, r12
0x14001a19c  movzx   eax, word ptr [rbp+Src]
0x14001a1a0  add     rcx, rbx; void *
0x14001a1a3  mov     [rdi+60h], rcx
0x14001a1a7  mov     [rdi+58h], ax
0x14001a1ab  movzx   r8d, word ptr [rbp+Src]; Size
0x14001a1b0  mov     rdx, [rbp+Src+8]; Src
0x14001a1b4  call    memmove
0x14001a1b9  mov     rax, cs:UserList
0x14001a1c0  lea     rcx, UserList
0x14001a1c7  cmp     [rax+8], rcx
0x14001a1cb  jz      short loc_14001A1D4
0x14001a1cd  mov     ecx, 3
0x14001a1d2  int     29h; Win8: RtlFailFast(ecx)
0x14001a1d4  mov     [rdi+8], rcx
0x14001a1d8  lea     rcx, [rbp+AuthenticationId]
0x14001a1dc  mov     [rdi], rax
0x14001a1df  mov     [rax+8], rdi
0x14001a1e3  mov     rdx, [rbp+Object]
0x14001a1e7  mov     cs:UserList, rdi
0x14001a1ee  mov     [r14], rdi
0x14001a1f1  call    cs:__imp_SeMarkLogonSessionForTerminationNotificationEx
0x14001a1f8  nop     dword ptr [rax+rax+00h]
0x14001a1fd  call    LuafvRunScavenger
0x14001a202  xor     r13d, r13d
0x14001a205  jmp     loc_14001A0B5
0x14001a20a  test    r12b, r12b
0x14001a20d  jnz     short loc_14001A217
0x14001a20f  mov     [r14], r13
0x14001a212  jmp     loc_14001A0B5
0x14001a217  mov     r8b, 1; AllocateDestinationString
0x14001a21a  lea     rcx, [rbp+Src]; UnicodeString
0x14001a21e  mov     rdx, r15; Sid
0x14001a221  call    cs:__imp_RtlConvertSidToUnicodeString
0x14001a228  nop     dword ptr [rax+rax+00h]
0x14001a22d  mov     ebx, eax
0x14001a22f  test    eax, eax
0x14001a231  js      loc_14001A0B8
0x14001a237  mov     rcx, r15; Sid
0x14001a23a  call    cs:__imp_RtlLengthSid
0x14001a241  nop     dword ptr [rax+rax+00h]
0x14001a246  movzx   ebx, word ptr [rbp+Src]
0x14001a24a  mov     r8b, 0Fh
0x14001a24d  mov     r13d, eax
0x14001a250  add     ebx, 0C0h
0x14001a256  mov     ecx, 1
0x14001a25b  lea     r12d, [rax+1]
0x14001a25f  mov     eax, 0FFFFFFFEh
0x14001a264  mov     edx, r12d
0x14001a267  and     edx, eax
0x14001a269  add     ebx, edx
0x14001a26b  mov     edx, ebx
0x14001a26d  call    LuafvAllocatePool
0x14001a272  mov     rdi, rax
0x14001a275  test    rax, rax
0x14001a278  jnz     short loc_14001A284
0x14001a27a  mov     ebx, 0C000009Ah
0x14001a27f  jmp     loc_14001A0B8
0x14001a284  mov     r8d, ebx; Size
0x14001a287  xor     edx, edx; Val
0x14001a289  mov     rcx, rdi; void *
0x14001a28c  call    memset
0x14001a291  mov     dword ptr [rdi+18h], 1
0x14001a298  mov     rax, ds:0FFFFF78000000014h
0x14001a2a2  mov     [rdi+10h], rax
0x14001a2a6  lea     rax, [rdi+20h]
0x14001a2aa  mov     [rax+8], rax
0x14001a2ae  mov     [rax], rax
0x14001a2b1  mov     rax, qword ptr [rbp+AuthenticationId.LowPart]
0x14001a2b5  mov     [rdi+30h], rax
0x14001a2b9  mov     rcx, [rbp+Object]; Object
0x14001a2bd  test    rcx, rcx
0x14001a2c0  jz      loc_14001A16C
0x14001a2c6  mov     edx, 6661754Ch; Tag
0x14001a2cb  call    cs:__imp_ObfReferenceObjectWithTag
0x14001a2d2  nop     dword ptr [rax+rax+00h]
0x14001a2d7  mov     rax, [rbp+Object]
0x14001a2db  mov     [rdi+38h], rax
0x14001a2df  jmp     loc_14001A16C
0x14001a2e4  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14001a2e8  call    cs:__imp_SeReleaseSubjectContext
0x14001a2ef  nop     dword ptr [rax+rax+00h]
0x14001a2f4  jmp     loc_14001A0C1
0x14001a2f9  xor     edx, edx; Tag
0x14001a2fb  call    cs:__imp_ExFreePoolWithTag
0x14001a302  nop     dword ptr [rax+rax+00h]
0x14001a307  jmp     loc_14001A0EB
```
