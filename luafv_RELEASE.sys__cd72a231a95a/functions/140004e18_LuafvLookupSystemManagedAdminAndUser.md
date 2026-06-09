# LuafvLookupSystemManagedAdminAndUser

- ea: `0x140004e18`
- end: `0x14000502c`
- name: `LuafvLookupSystemManagedAdminAndUser`
- size: `532`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140025820`

## callees

- `0x140001e98`
- `0x140004e18`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140004eff`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140004eff`
- `ntoskrnl!SeTokenObjectType` at `0x140004ee3`
- `ntoskrnl!SeTokenObjectType` at `0x140004f53`
- `ntoskrnl!ZwQueryInformationToken` at `0x140004f31`
- `ntoskrnl!ZwQueryInformationToken` at `0x140004f31`
- `ntoskrnl!ZwClose` at `0x140004f47`
- `ntoskrnl!ZwClose` at `0x140004fd7`
- `ntoskrnl!ZwClose` at `0x140004fec`
- `ntoskrnl!ZwClose` at `0x140004f47`
- `ntoskrnl!ZwClose` at `0x140004fd7`
- `ntoskrnl!ZwClose` at `0x140004fec`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140004fc2`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140004fc2`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004e97`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004e97`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140004f80`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140004f80`
- `ntoskrnl!ObfDereferenceObject` at `0x140005001`
- `ntoskrnl!ObfDereferenceObject` at `0x140005001`

## pseudocode

```c
__int64 __fastcall LuafvLookupSystemManagedAdminAndUser(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x140004e18  mov     [rsp-28h+arg_8], rbx
0x140004e1d  mov     [rsp-28h+arg_10], rsi
0x140004e22  push    rbp
0x140004e23  push    rdi
0x140004e24  push    r12
0x140004e26  push    r14
0x140004e28  push    r15
0x140004e2a  mov     rbp, rsp
0x140004e2d  sub     rsp, 80h
0x140004e34  mov     rax, [rcx+10h]
0x140004e38  xorps   xmm0, xmm0
0x140004e3b  mov     [rbp+Object], 0
0x140004e43  mov     r15, r8
0x140004e46  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x140004e4a  mov     [rbp+TokenInformation], 0
0x140004e52  mov     r12, rdx
0x140004e55  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x140004e59  mov     [rbp+TokenHandle], 0
0x140004e61  mov     [rbp+ReturnLength], 0
0x140004e68  cmp     byte ptr [rax+4], 0
0x140004e6c  mov     [rbp+var_30], 0
0x140004e74  mov     [rbp+var_28], 0
0x140004e7c  jnz     short loc_140004E8F
0x140004e7e  mov     rax, [rax+18h]
0x140004e82  mov     rbx, [rax+8]
0x140004e86  add     rbx, 20h ; ' '
0x140004e8a  xor     sil, sil
0x140004e8d  jmp     short loc_140004EA6
0x140004e8f  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140004e93  lea     rbx, [rbp+SubjectContext]
0x140004e97  call    cs:__imp_SeCaptureSubjectContext
0x140004e9e  nop     dword ptr [rax+rax+00h]
0x140004ea3  mov     sil, 1
0x140004ea6  mov     rdi, [rbx]
0x140004ea9  test    rdi, rdi
0x140004eac  jnz     short loc_140004EB2
0x140004eae  mov     rdi, [rbx+10h]
0x140004eb2  lea     rdx, [rbp+var_30]
0x140004eb6  mov     rcx, rdi; Token
0x140004eb9  call    LuafvFindUser
0x140004ebe  mov     r14, [rbp+var_30]
0x140004ec2  test    r14, r14
0x140004ec5  jnz     short loc_140004ED1
0x140004ec7  mov     ebx, 0C0000225h
0x140004ecc  jmp     loc_140004FB9
0x140004ed1  lea     rax, [rbp+TokenHandle]
0x140004ed5  mov     r9d, 8; DesiredAccess
0x140004edb  mov     [rsp+80h+Handle], rax; Handle
0x140004ee0  xor     r8d, r8d; PassedAccessState
0x140004ee3  mov     rax, cs:__imp_SeTokenObjectType
0x140004eea  mov     rcx, rdi; Object
0x140004eed  mov     [rsp+80h+AccessMode], 0; AccessMode
0x140004ef2  mov     rdx, [rax]
0x140004ef5  mov     [rsp+80h+ObjectType], rdx; ObjectType
0x140004efa  mov     edx, 200h; HandleAttributes
0x140004eff  call    cs:__imp_ObOpenObjectByPointer
0x140004f06  nop     dword ptr [rax+rax+00h]
0x140004f0b  mov     ebx, eax
0x140004f0d  test    eax, eax
0x140004f0f  js      loc_140004FB9
0x140004f15  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140004f19  lea     rax, [rbp+ReturnLength]
0x140004f1d  mov     edi, 8
0x140004f22  mov     [rsp+80h+ObjectType], rax; ReturnLength
0x140004f27  mov     r9d, edi; TokenInformationLength
0x140004f2a  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140004f2e  lea     edx, [rdi+0Bh]; TokenInformationClass
0x140004f31  call    cs:__imp_ZwQueryInformationToken
0x140004f38  nop     dword ptr [rax+rax+00h]
0x140004f3d  mov     ebx, eax
0x140004f3f  test    eax, eax
0x140004f41  js      short loc_140004FB9
0x140004f43  mov     rcx, [rbp+TokenHandle]; Handle
0x140004f47  call    cs:__imp_ZwClose
0x140004f4e  nop     dword ptr [rax+rax+00h]
0x140004f53  mov     r8, cs:__imp_SeTokenObjectType
0x140004f5a  lea     rax, [rbp+Object]
0x140004f5e  mov     rcx, [rbp+TokenInformation]; Handle
0x140004f62  xor     r9d, r9d; AccessMode
0x140004f65  mov     [rbp+TokenHandle], 0
0x140004f6d  mov     edx, edi; DesiredAccess
0x140004f6f  mov     qword ptr [rsp+80h+AccessMode], 0; HandleInformation
0x140004f78  mov     r8, [r8]; ObjectType
0x140004f7b  mov     [rsp+80h+ObjectType], rax; Object
0x140004f80  call    cs:__imp_ObReferenceObjectByHandle
0x140004f87  nop     dword ptr [rax+rax+00h]
0x140004f8c  mov     ebx, eax
0x140004f8e  test    eax, eax
0x140004f90  js      short loc_140004FB9
0x140004f92  mov     rcx, [rbp+Object]; Token
0x140004f96  lea     rdx, [rbp+var_28]
0x140004f9a  call    LuafvFindUser
0x140004f9f  mov     ebx, eax
0x140004fa1  mov     rax, [rbp+var_28]
0x140004fa5  test    rax, rax
0x140004fa8  jz      loc_140004EC7
0x140004fae  test    ebx, ebx
0x140004fb0  js      short loc_140004FB9
0x140004fb2  mov     [r12], r14
0x140004fb6  mov     [r15], rax
0x140004fb9  test    sil, sil
0x140004fbc  jz      short loc_140004FCE
0x140004fbe  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140004fc2  call    cs:__imp_SeReleaseSubjectContext
0x140004fc9  nop     dword ptr [rax+rax+00h]
0x140004fce  mov     rcx, [rbp+TokenHandle]; Handle
0x140004fd2  test    rcx, rcx
0x140004fd5  jz      short loc_140004FE3
0x140004fd7  call    cs:__imp_ZwClose
0x140004fde  nop     dword ptr [rax+rax+00h]
0x140004fe3  mov     rcx, [rbp+TokenInformation]; Handle
0x140004fe7  test    rcx, rcx
0x140004fea  jz      short loc_140004FF8
0x140004fec  call    cs:__imp_ZwClose
0x140004ff3  nop     dword ptr [rax+rax+00h]
0x140004ff8  mov     rcx, [rbp+Object]; Object
0x140004ffc  test    rcx, rcx
0x140004fff  jz      short loc_14000500D
0x140005001  call    cs:__imp_ObfDereferenceObject
0x140005008  nop     dword ptr [rax+rax+00h]
0x14000500d  lea     r11, [rsp+80h+var_s0]
0x140005015  mov     eax, ebx
0x140005017  mov     rbx, [r11+38h]
0x14000501b  mov     rsi, [r11+40h]
0x14000501f  mov     rsp, r11
0x140005022  pop     r15
0x140005024  pop     r14
0x140005026  pop     r12
0x140005028  pop     rdi
0x140005029  pop     rbp
0x14000502a  retn
```
