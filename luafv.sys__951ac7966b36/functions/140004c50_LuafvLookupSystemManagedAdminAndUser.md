# LuafvLookupSystemManagedAdminAndUser

- ea: `0x140004c50`
- end: `0x140004e64`
- name: `LuafvLookupSystemManagedAdminAndUser`
- size: `532`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400258a0`

## callees

- `0x140001e98`
- `0x140004c50`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140004d37`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140004d37`
- `ntoskrnl!SeTokenObjectType` at `0x140004d1b`
- `ntoskrnl!SeTokenObjectType` at `0x140004d8b`
- `ntoskrnl!ZwQueryInformationToken` at `0x140004d69`
- `ntoskrnl!ZwQueryInformationToken` at `0x140004d69`
- `ntoskrnl!ZwClose` at `0x140004d7f`
- `ntoskrnl!ZwClose` at `0x140004e0f`
- `ntoskrnl!ZwClose` at `0x140004e24`
- `ntoskrnl!ZwClose` at `0x140004d7f`
- `ntoskrnl!ZwClose` at `0x140004e0f`
- `ntoskrnl!ZwClose` at `0x140004e24`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140004dfa`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140004dfa`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004ccf`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004ccf`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140004db8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140004db8`
- `ntoskrnl!ObfDereferenceObject` at `0x140004e39`
- `ntoskrnl!ObfDereferenceObject` at `0x140004e39`

## pseudocode

```c
__int64 __fastcall LuafvLookupSystemManagedAdminAndUser(__int64 a1, __int64 *a2, __int64 *a3)
{
  __int64 v3; // rax
  bool v6; // zf
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // rbx
  char v8; // si
  PACCESS_TOKEN ClientToken; // rdi
  __int64 v10; // r14
  int User; // ebx
  __int64 v12; // rax
  HANDLE TokenInformation; // [rsp+40h] [rbp-40h] BYREF
  PVOID Object; // [rsp+48h] [rbp-38h] BYREF
  __int64 v16; // [rsp+50h] [rbp-30h] BYREF
  __int64 v17; // [rsp+58h] [rbp-28h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+60h] [rbp-20h] BYREF
  ULONG ReturnLength; // [rsp+B0h] [rbp+30h] BYREF
  HANDLE TokenHandle; // [rsp+C8h] [rbp+48h] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  Object = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  TokenInformation = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  v6 = *(_BYTE *)(v3 + 4) == 0;
  v16 = 0;
  v17 = 0;
  if ( v6 )
  {
    p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(v3 + 24) + 8LL) + 32LL);
    v8 = 0;
  }
  else
  {
    p_SubjectContext = &SubjectContext;
    SeCaptureSubjectContext(&SubjectContext);
    v8 = 1;
  }
  ClientToken = p_SubjectContext->ClientToken;
  if ( !p_SubjectContext->ClientToken )
    ClientToken = p_SubjectContext->PrimaryToken;
  LuafvFindUser(ClientToken, &v16);
  v10 = v16;
  if ( !v16 )
    goto LABEL_7;
  User = ObOpenObjectByPointer(ClientToken, 0x200u, 0, 8u, (POBJECT_TYPE)SeTokenObjectType, 0, &TokenHandle);
  if ( User >= 0 )
  {
    User = ZwQueryInformationToken(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength);
    if ( User >= 0 )
    {
      ZwClose(TokenHandle);
      TokenHandle = 0;
      User = ObReferenceObjectByHandle(TokenInformation, 8u, (POBJECT_TYPE)SeTokenObjectType, 0, &Object, 0);
      if ( User >= 0 )
      {
        User = LuafvFindUser(Object, &v17);
        v12 = v17;
        if ( !v17 )
        {
LABEL_7:
          User = -1073741275;
          goto LABEL_14;
        }
        if ( User >= 0 )
        {
          *a2 = v10;
          *a3 = v12;
        }
      }
    }
  }
LABEL_14:
  if ( v8 )
    SeReleaseSubjectContext(&SubjectContext);
  if ( TokenHandle )
    ZwClose(TokenHandle);
  if ( TokenInformation )
    ZwClose(TokenInformation);
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)User;
}

```

## disassembly

```asm
0x140004c50  mov     [rsp-28h+arg_8], rbx
0x140004c55  mov     [rsp-28h+arg_10], rsi
0x140004c5a  push    rbp
0x140004c5b  push    rdi
0x140004c5c  push    r12
0x140004c5e  push    r14
0x140004c60  push    r15
0x140004c62  mov     rbp, rsp
0x140004c65  sub     rsp, 80h
0x140004c6c  mov     rax, [rcx+10h]
0x140004c70  xorps   xmm0, xmm0
0x140004c73  mov     [rbp+Object], 0
0x140004c7b  mov     r15, r8
0x140004c7e  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x140004c82  mov     [rbp+TokenInformation], 0
0x140004c8a  mov     r12, rdx
0x140004c8d  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x140004c91  mov     [rbp+TokenHandle], 0
0x140004c99  mov     [rbp+ReturnLength], 0
0x140004ca0  cmp     byte ptr [rax+4], 0
0x140004ca4  mov     [rbp+var_30], 0
0x140004cac  mov     [rbp+var_28], 0
0x140004cb4  jnz     short loc_140004CC7
0x140004cb6  mov     rax, [rax+18h]
0x140004cba  mov     rbx, [rax+8]
0x140004cbe  add     rbx, 20h ; ' '
0x140004cc2  xor     sil, sil
0x140004cc5  jmp     short loc_140004CDE
0x140004cc7  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140004ccb  lea     rbx, [rbp+SubjectContext]
0x140004ccf  call    cs:__imp_SeCaptureSubjectContext
0x140004cd6  nop     dword ptr [rax+rax+00h]
0x140004cdb  mov     sil, 1
0x140004cde  mov     rdi, [rbx]
0x140004ce1  test    rdi, rdi
0x140004ce4  jnz     short loc_140004CEA
0x140004ce6  mov     rdi, [rbx+10h]
0x140004cea  lea     rdx, [rbp+var_30]
0x140004cee  mov     rcx, rdi; Token
0x140004cf1  call    LuafvFindUser
0x140004cf6  mov     r14, [rbp+var_30]
0x140004cfa  test    r14, r14
0x140004cfd  jnz     short loc_140004D09
0x140004cff  mov     ebx, 0C0000225h
0x140004d04  jmp     loc_140004DF1
0x140004d09  lea     rax, [rbp+TokenHandle]
0x140004d0d  mov     r9d, 8; DesiredAccess
0x140004d13  mov     [rsp+80h+Handle], rax; Handle
0x140004d18  xor     r8d, r8d; PassedAccessState
0x140004d1b  mov     rax, cs:__imp_SeTokenObjectType
0x140004d22  mov     rcx, rdi; Object
0x140004d25  mov     [rsp+80h+AccessMode], 0; AccessMode
0x140004d2a  mov     rdx, [rax]
0x140004d2d  mov     [rsp+80h+ObjectType], rdx; ObjectType
0x140004d32  mov     edx, 200h; HandleAttributes
0x140004d37  call    cs:__imp_ObOpenObjectByPointer
0x140004d3e  nop     dword ptr [rax+rax+00h]
0x140004d43  mov     ebx, eax
0x140004d45  test    eax, eax
0x140004d47  js      loc_140004DF1
0x140004d4d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140004d51  lea     rax, [rbp+ReturnLength]
0x140004d55  mov     edi, 8
0x140004d5a  mov     [rsp+80h+ObjectType], rax; ReturnLength
0x140004d5f  mov     r9d, edi; TokenInformationLength
0x140004d62  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140004d66  lea     edx, [rdi+0Bh]; TokenInformationClass
0x140004d69  call    cs:__imp_ZwQueryInformationToken
0x140004d70  nop     dword ptr [rax+rax+00h]
0x140004d75  mov     ebx, eax
0x140004d77  test    eax, eax
0x140004d79  js      short loc_140004DF1
0x140004d7b  mov     rcx, [rbp+TokenHandle]; Handle
0x140004d7f  call    cs:__imp_ZwClose
0x140004d86  nop     dword ptr [rax+rax+00h]
0x140004d8b  mov     r8, cs:__imp_SeTokenObjectType
0x140004d92  lea     rax, [rbp+Object]
0x140004d96  mov     rcx, [rbp+TokenInformation]; Handle
0x140004d9a  xor     r9d, r9d; AccessMode
0x140004d9d  mov     [rbp+TokenHandle], 0
0x140004da5  mov     edx, edi; DesiredAccess
0x140004da7  mov     qword ptr [rsp+80h+AccessMode], 0; HandleInformation
0x140004db0  mov     r8, [r8]; ObjectType
0x140004db3  mov     [rsp+80h+ObjectType], rax; Object
0x140004db8  call    cs:__imp_ObReferenceObjectByHandle
0x140004dbf  nop     dword ptr [rax+rax+00h]
0x140004dc4  mov     ebx, eax
0x140004dc6  test    eax, eax
0x140004dc8  js      short loc_140004DF1
0x140004dca  mov     rcx, [rbp+Object]; Token
0x140004dce  lea     rdx, [rbp+var_28]
0x140004dd2  call    LuafvFindUser
0x140004dd7  mov     ebx, eax
0x140004dd9  mov     rax, [rbp+var_28]
0x140004ddd  test    rax, rax
0x140004de0  jz      loc_140004CFF
0x140004de6  test    ebx, ebx
0x140004de8  js      short loc_140004DF1
0x140004dea  mov     [r12], r14
0x140004dee  mov     [r15], rax
0x140004df1  test    sil, sil
0x140004df4  jz      short loc_140004E06
0x140004df6  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140004dfa  call    cs:__imp_SeReleaseSubjectContext
0x140004e01  nop     dword ptr [rax+rax+00h]
0x140004e06  mov     rcx, [rbp+TokenHandle]; Handle
0x140004e0a  test    rcx, rcx
0x140004e0d  jz      short loc_140004E1B
0x140004e0f  call    cs:__imp_ZwClose
0x140004e16  nop     dword ptr [rax+rax+00h]
0x140004e1b  mov     rcx, [rbp+TokenInformation]; Handle
0x140004e1f  test    rcx, rcx
0x140004e22  jz      short loc_140004E30
0x140004e24  call    cs:__imp_ZwClose
0x140004e2b  nop     dword ptr [rax+rax+00h]
0x140004e30  mov     rcx, [rbp+Object]; Object
0x140004e34  test    rcx, rcx
0x140004e37  jz      short loc_140004E45
0x140004e39  call    cs:__imp_ObfDereferenceObject
0x140004e40  nop     dword ptr [rax+rax+00h]
0x140004e45  lea     r11, [rsp+80h+var_s0]
0x140004e4d  mov     eax, ebx
0x140004e4f  mov     rbx, [r11+38h]
0x140004e53  mov     rsi, [r11+40h]
0x140004e57  mov     rsp, r11
0x140004e5a  pop     r15
0x140004e5c  pop     r14
0x140004e5e  pop     r12
0x140004e60  pop     rdi
0x140004e61  pop     rbp
0x140004e62  retn
```
