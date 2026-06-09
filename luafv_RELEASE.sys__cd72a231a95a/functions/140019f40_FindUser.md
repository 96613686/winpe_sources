# FindUser

- ea: `0x140019f40`
- end: `0x14001a2bf`
- name: `FindUser`
- size: `895`
- prototype: `__int64 __fastcall(__int64, char, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140019ac0`

## callees

- `0x14000160c`
- `0x140001adc`
- `0x140001f7c`
- `0x140005d00`
- `0x140006000`
- `0x140019f40`
- `0x14001b650`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x14001a032`
- `ntoskrnl!RtlEqualSid` at `0x14001a032`
- `ntoskrnl!SeQueryServerSiloToken` at `0x140019ffb`
- `ntoskrnl!SeQueryServerSiloToken` at `0x140019ffb`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14001a27e`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14001a27e`
- `ntoskrnl!RtlCopySid` at `0x14001a133`
- `ntoskrnl!RtlCopySid` at `0x14001a133`
- `ntoskrnl!SeMarkLogonSessionForTerminationNotificationEx` at `0x14001a1a4`
- `ntoskrnl!SeMarkLogonSessionForTerminationNotificationEx` at `0x14001a1a4`
- `ntoskrnl!RtlLengthSid` at `0x14001a1ed`
- `ntoskrnl!RtlLengthSid` at `0x14001a1ed`
- `ntoskrnl!SeQueryInformationToken` at `0x140019fc5`
- `ntoskrnl!SeQueryInformationToken` at `0x140019fc5`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001a29b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001a29b`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140019fe2`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140019fe2`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14001a0bc`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14001a10e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14001a0bc`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14001a10e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a0a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a2ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a0a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a2ae`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14001a1d4`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14001a1d4`

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
    UserWithToken = FindUserWithToken(ClientToken, a2, 0, a3);
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
0x140019f40  push    rbp
0x140019f42  push    rbx
0x140019f43  push    rsi
0x140019f44  push    rdi
0x140019f45  push    r12
0x140019f47  push    r13
0x140019f49  push    r14
0x140019f4b  push    r15
0x140019f4d  mov     rbp, rsp
0x140019f50  sub     rsp, 68h
0x140019f54  xorps   xmm0, xmm0
0x140019f57  xor     r13d, r13d
0x140019f5a  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x140019f5e  mov     [rbp+TokenInformation], r13
0x140019f62  mov     r14, r8
0x140019f65  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x140019f69  mov     qword ptr [rbp+AuthenticationId.LowPart], r13
0x140019f6d  mov     r12b, dl
0x140019f70  movups  xmmword ptr [rbp+Src], xmm0
0x140019f74  mov     [rbp+Object], r13
0x140019f78  mov     rbx, rcx
0x140019f7b  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x140019f80  mov     rcx, [rbx+10h]
0x140019f84  test    eax, eax
0x140019f86  jnz     loc_14001A0D0
0x140019f8c  mov     [rbp+TokenInformation], r13
0x140019f90  mov     [rbp+Src+8], r13
0x140019f94  cmp     [rcx+4], r13b
0x140019f98  jnz     loc_14001A0B4
0x140019f9e  mov     rax, [rcx+18h]
0x140019fa2  mov     sil, r13b
0x140019fa5  mov     rbx, [rax+8]
0x140019fa9  add     rbx, 20h ; ' '
0x140019fad  mov     rdi, [rbx]
0x140019fb0  test    rdi, rdi
0x140019fb3  jnz     short loc_140019FB9
0x140019fb5  mov     rdi, [rbx+10h]
0x140019fb9  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140019fbd  mov     edx, 1; TokenInformationClass
0x140019fc2  mov     rcx, rdi; Token
0x140019fc5  call    cs:__imp_SeQueryInformationToken
0x140019fcc  nop     dword ptr [rax+rax+00h]
0x140019fd1  mov     ebx, eax
0x140019fd3  test    eax, eax
0x140019fd5  js      loc_14001A068
0x140019fdb  lea     rdx, [rbp+AuthenticationId]; AuthenticationId
0x140019fdf  mov     rcx, rdi; Token
0x140019fe2  call    cs:__imp_SeQueryAuthenticationIdToken
0x140019fe9  nop     dword ptr [rax+rax+00h]
0x140019fee  mov     ebx, eax
0x140019ff0  test    eax, eax
0x140019ff2  js      short loc_14001A068
0x140019ff4  lea     rdx, [rbp+Object]
0x140019ff8  mov     rcx, rdi
0x140019ffb  call    cs:__imp_SeQueryServerSiloToken
0x14001a002  nop     dword ptr [rax+rax+00h]
0x14001a007  mov     ebx, eax
0x14001a009  test    eax, eax
0x14001a00b  js      short loc_14001A068
0x14001a00d  mov     rax, [rbp+TokenInformation]
0x14001a011  mov     rbx, cs:UserList
0x14001a018  mov     r15, [rax]
0x14001a01b  lea     rax, UserList
0x14001a022  cmp     rbx, rax
0x14001a025  jz      loc_14001A1BD
0x14001a02b  mov     rcx, [rbx+50h]; Sid1
0x14001a02f  mov     rdx, r15; Sid2
0x14001a032  call    cs:__imp_RtlEqualSid
0x14001a039  nop     dword ptr [rax+rax+00h]
0x14001a03e  test    al, al
0x14001a040  jnz     short loc_14001A047
0x14001a042  mov     rbx, [rbx]
0x14001a045  jmp     short loc_14001A01B
0x14001a047  mov     rax, [rbp+Object]
0x14001a04b  cmp     [rbx+38h], rax
0x14001a04f  jnz     short loc_14001A042
0x14001a051  mov     rax, 0FFFFF78000000014h
0x14001a05b  mov     rax, [rax]
0x14001a05e  xchg    rax, [rbx+10h]
0x14001a062  mov     [r14], rbx
0x14001a065  mov     ebx, r13d
0x14001a068  test    sil, sil
0x14001a06b  jnz     loc_14001A297
0x14001a071  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x14001a076  test    eax, eax
0x14001a078  jz      short loc_14001A08E
0x14001a07a  mov     eax, ebx
0x14001a07c  add     rsp, 68h
0x14001a080  pop     r15
0x14001a082  pop     r14
0x14001a084  pop     r13
0x14001a086  pop     r12
0x14001a088  pop     rdi
0x14001a089  pop     rsi
0x14001a08a  pop     rbx
0x14001a08b  pop     rbp
0x14001a08c  retn
0x14001a08e  mov     rcx, [rbp+Src+8]; P
0x14001a092  test    rcx, rcx
0x14001a095  jnz     loc_14001A2AC
0x14001a09b  mov     rcx, [rbp+TokenInformation]; P
0x14001a09f  test    rcx, rcx
0x14001a0a2  jz      short loc_14001A07A
0x14001a0a4  xor     edx, edx; Tag
0x14001a0a6  call    cs:__imp_ExFreePoolWithTag
0x14001a0ad  nop     dword ptr [rax+rax+00h]
0x14001a0b2  jmp     short loc_14001A07A
0x14001a0b4  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14001a0b8  lea     rbx, [rbp+SubjectContext]
0x14001a0bc  call    cs:__imp_SeCaptureSubjectContext
0x14001a0c3  nop     dword ptr [rax+rax+00h]
0x14001a0c8  mov     sil, 1
0x14001a0cb  jmp     loc_140019FAD
0x14001a0d0  cmp     [rcx+4], r13b
0x14001a0d4  jnz     short loc_14001A106
0x14001a0d6  mov     rax, [rcx+18h]
0x14001a0da  mov     sil, r13b
0x14001a0dd  mov     rbx, [rax+8]
0x14001a0e1  add     rbx, 20h ; ' '
0x14001a0e5  mov     rcx, [rbx]
0x14001a0e8  test    rcx, rcx
0x14001a0eb  jnz     short loc_14001A0F1
0x14001a0ed  mov     rcx, [rbx+10h]; Token
0x14001a0f1  mov     r9, r14
0x14001a0f4  xor     r8d, r8d
0x14001a0f7  mov     dl, r12b
0x14001a0fa  call    FindUserWithToken
0x14001a0ff  mov     ebx, eax
0x14001a101  jmp     loc_14001A068
0x14001a106  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14001a10a  lea     rbx, [rbp+SubjectContext]
0x14001a10e  call    cs:__imp_SeCaptureSubjectContext
0x14001a115  nop     dword ptr [rax+rax+00h]
0x14001a11a  mov     sil, 1
0x14001a11d  jmp     short loc_14001A0E5
0x14001a11f  lea     rbx, [rdi+0C0h]
0x14001a126  mov     r8, r15; SourceSid
0x14001a129  mov     rdx, rbx; DestinationSid
0x14001a12c  mov     [rdi+50h], rbx
0x14001a130  mov     ecx, r13d; DestinationSidLength
0x14001a133  call    cs:__imp_RtlCopySid
0x14001a13a  nop     dword ptr [rax+rax+00h]
0x14001a13f  movzx   eax, word ptr [rbp+Src]
0x14001a143  mov     ecx, 0FFFFFFFEh
0x14001a148  mov     [rdi+5Ah], ax
0x14001a14c  and     rcx, r12
0x14001a14f  movzx   eax, word ptr [rbp+Src]
0x14001a153  add     rcx, rbx; void *
0x14001a156  mov     [rdi+60h], rcx
0x14001a15a  mov     [rdi+58h], ax
0x14001a15e  movzx   r8d, word ptr [rbp+Src]; Size
0x14001a163  mov     rdx, [rbp+Src+8]; Src
0x14001a167  call    memmove
0x14001a16c  mov     rax, cs:UserList
0x14001a173  lea     rcx, UserList
0x14001a17a  cmp     [rax+8], rcx
0x14001a17e  jz      short loc_14001A187
0x14001a180  mov     ecx, 3
0x14001a185  int     29h; Win8: RtlFailFast(ecx)
0x14001a187  mov     [rdi+8], rcx
0x14001a18b  lea     rcx, [rbp+AuthenticationId]
0x14001a18f  mov     [rdi], rax
0x14001a192  mov     [rax+8], rdi
0x14001a196  mov     rdx, [rbp+Object]
0x14001a19a  mov     cs:UserList, rdi
0x14001a1a1  mov     [r14], rdi
0x14001a1a4  call    cs:__imp_SeMarkLogonSessionForTerminationNotificationEx
0x14001a1ab  nop     dword ptr [rax+rax+00h]
0x14001a1b0  call    LuafvRunScavenger
0x14001a1b5  xor     r13d, r13d
0x14001a1b8  jmp     loc_14001A065
0x14001a1bd  test    r12b, r12b
0x14001a1c0  jnz     short loc_14001A1CA
0x14001a1c2  mov     [r14], r13
0x14001a1c5  jmp     loc_14001A065
0x14001a1ca  mov     r8b, 1; AllocateDestinationString
0x14001a1cd  lea     rcx, [rbp+Src]; UnicodeString
0x14001a1d1  mov     rdx, r15; Sid
0x14001a1d4  call    cs:__imp_RtlConvertSidToUnicodeString
0x14001a1db  nop     dword ptr [rax+rax+00h]
0x14001a1e0  mov     ebx, eax
0x14001a1e2  test    eax, eax
0x14001a1e4  js      loc_14001A068
0x14001a1ea  mov     rcx, r15; Sid
0x14001a1ed  call    cs:__imp_RtlLengthSid
0x14001a1f4  nop     dword ptr [rax+rax+00h]
0x14001a1f9  movzx   ebx, word ptr [rbp+Src]
0x14001a1fd  mov     r8b, 0Fh
0x14001a200  mov     r13d, eax
0x14001a203  add     ebx, 0C0h
0x14001a209  mov     ecx, 1
0x14001a20e  lea     r12d, [rax+1]
0x14001a212  mov     eax, 0FFFFFFFEh
0x14001a217  mov     edx, r12d
0x14001a21a  and     edx, eax
0x14001a21c  add     ebx, edx
0x14001a21e  mov     edx, ebx
0x14001a220  call    LuafvAllocatePool
0x14001a225  mov     rdi, rax
0x14001a228  test    rax, rax
0x14001a22b  jnz     short loc_14001A237
0x14001a22d  mov     ebx, 0C000009Ah
0x14001a232  jmp     loc_14001A068
0x14001a237  mov     r8d, ebx; Size
0x14001a23a  xor     edx, edx; Val
0x14001a23c  mov     rcx, rdi; void *
0x14001a23f  call    memset
0x14001a244  mov     dword ptr [rdi+18h], 1
0x14001a24b  mov     rax, ds:0FFFFF78000000014h
0x14001a255  mov     [rdi+10h], rax
0x14001a259  lea     rax, [rdi+20h]
0x14001a25d  mov     [rax+8], rax
0x14001a261  mov     [rax], rax
0x14001a264  mov     rax, qword ptr [rbp+AuthenticationId.LowPart]
0x14001a268  mov     [rdi+30h], rax
0x14001a26c  mov     rcx, [rbp+Object]; Object
0x14001a270  test    rcx, rcx
0x14001a273  jz      loc_14001A11F
0x14001a279  mov     edx, 6661754Ch; Tag
0x14001a27e  call    cs:__imp_ObfReferenceObjectWithTag
0x14001a285  nop     dword ptr [rax+rax+00h]
0x14001a28a  mov     rax, [rbp+Object]
0x14001a28e  mov     [rdi+38h], rax
0x14001a292  jmp     loc_14001A11F
0x14001a297  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14001a29b  call    cs:__imp_SeReleaseSubjectContext
0x14001a2a2  nop     dword ptr [rax+rax+00h]
0x14001a2a7  jmp     loc_14001A071
0x14001a2ac  xor     edx, edx; Tag
0x14001a2ae  call    cs:__imp_ExFreePoolWithTag
0x14001a2b5  nop     dword ptr [rax+rax+00h]
0x14001a2ba  jmp     loc_14001A09B
```
