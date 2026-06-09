# LuafvGetUserAndLinkedSystemManagedAdmin

- ea: `0x140001c0c`
- end: `0x140001e90`
- name: `LuafvGetUserAndLinkedSystemManagedAdmin`
- size: `644`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400258a0`

## callees

- `0x140001c0c`
- `0x140001e98`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x140001de7`
- `ntoskrnl!RtlEqualSid` at `0x140001de7`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140001d1c`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140001d1c`
- `ntoskrnl!SeTokenObjectType` at `0x140001d00`
- `ntoskrnl!SeTokenObjectType` at `0x140001d6c`
- `ntoskrnl!ZwQueryInformationToken` at `0x140001d4e`
- `ntoskrnl!ZwQueryInformationToken` at `0x140001d4e`
- `ntoskrnl!SeQueryInformationToken` at `0x140001db0`
- `ntoskrnl!SeQueryInformationToken` at `0x140001db0`
- `ntoskrnl!ZwClose` at `0x140001e43`
- `ntoskrnl!ZwClose` at `0x140001e58`
- `ntoskrnl!ZwClose` at `0x140001e43`
- `ntoskrnl!ZwClose` at `0x140001e58`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140001e6d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140001e6d`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140001c7e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140001c7e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140001d8d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140001d8d`
- `ntoskrnl!ObfDereferenceObject` at `0x140001e2e`
- `ntoskrnl!ObfDereferenceObject` at `0x140001e2e`

## pseudocode

```c
__int64 __fastcall LuafvGetUserAndLinkedSystemManagedAdmin(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v3; // rax
  char v6; // r12
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // rbx
  PACCESS_TOKEN ClientToken; // rsi
  NTSTATUS User; // ebx
  __int64 v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rsi
  signed __int32 v14[8]; // [rsp+0h] [rbp-69h] BYREF
  HANDLE TokenInformation; // [rsp+40h] [rbp-29h] BYREF
  __int64 v16; // [rsp+48h] [rbp-21h]
  __int64 v17; // [rsp+50h] [rbp-19h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+58h] [rbp-11h] BYREF
  PVOID v19; // [rsp+D0h] [rbp+67h] BYREF
  ULONG ReturnLength; // [rsp+D8h] [rbp+6Fh] BYREF
  PVOID Object; // [rsp+E0h] [rbp+77h] BYREF
  HANDLE TokenHandle; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  LODWORD(v19) = 0;
  TokenInformation = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  ReturnLength = 0;
  TokenHandle = 0;
  Object = 0;
  v16 = 0;
  v17 = 0;
  *a3 = 0;
  *a2 = 0;
  if ( *(_BYTE *)(v3 + 4) )
  {
    p_SubjectContext = &SubjectContext;
    SeCaptureSubjectContext(&SubjectContext);
    v6 = 1;
  }
  else
  {
    v6 = 0;
    p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(v3 + 24) + 8LL) + 32LL);
  }
  ClientToken = p_SubjectContext->ClientToken;
  if ( !p_SubjectContext->ClientToken )
    ClientToken = p_SubjectContext->PrimaryToken;
  User = LuafvFindUser(ClientToken);
  if ( User >= 0 )
  {
    v10 = v16;
    if ( (*(_BYTE *)(v16 + 168) & 1) != 0 )
    {
      v11 = *(_QWORD *)(v16 + 176);
      if ( v11 )
      {
        _InterlockedExchange64((volatile __int64 *)(v11 + 16), MEMORY[0xFFFFF78000000014]);
        *a3 = *(_QWORD *)(v16 + 176);
        *a2 = v10;
      }
      User = 0;
    }
    else
    {
      User = ObOpenObjectByPointer(ClientToken, 0x200u, 0, 8u, (POBJECT_TYPE)SeTokenObjectType, 0, &TokenHandle);
      if ( User >= 0 )
      {
        User = ZwQueryInformationToken(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength);
        if ( User >= 0 )
        {
          User = ObReferenceObjectByHandle(TokenInformation, 8u, (POBJECT_TYPE)SeTokenObjectType, 0, &Object, 0);
          if ( User >= 0 )
          {
            User = SeQueryInformationToken(Object, TokenRestrictedUserClaimAttributes|TokenAuditPolicy, &v19);
            if ( User >= 0 )
            {
              if ( (_DWORD)v19 )
              {
                User = LuafvFindUser(Object);
                if ( User >= 0 )
                {
                  v12 = v17;
                  if ( !RtlEqualSid(*(PSID *)(v10 + 80), *(PSID *)(v17 + 80)) )
                  {
                    _InterlockedOr(v14, 0);
                    *(_QWORD *)(v10 + 176) = v12;
                    *(_BYTE *)(v10 + 168) |= 1u;
                    _InterlockedIncrement((volatile signed __int32 *)(v12 + 24));
                    _InterlockedExchange64((volatile __int64 *)(v12 + 16), MEMORY[0xFFFFF78000000014]);
                    *a2 = v10;
                    *a3 = v12;
                  }
                }
              }
            }
          }
        }
        else
        {
          *(_BYTE *)(v10 + 168) |= 1u;
        }
      }
    }
  }
  if ( Object )
    ObfDereferenceObject(Object);
  if ( TokenHandle )
    ZwClose(TokenHandle);
  if ( TokenInformation )
    ZwClose(TokenInformation);
  if ( v6 )
    SeReleaseSubjectContext(&SubjectContext);
  return (unsigned int)User;
}

```

## disassembly

```asm
0x140001c0c  push    rbp
0x140001c0e  push    rbx
0x140001c0f  push    rsi
0x140001c10  push    rdi
0x140001c11  push    r12
0x140001c13  push    r13
0x140001c15  push    r14
0x140001c17  push    r15
0x140001c19  lea     rbp, [rsp-1Fh]
0x140001c1e  sub     rsp, 88h
0x140001c25  mov     rax, [rcx+10h]
0x140001c29  xor     r13d, r13d
0x140001c2c  xorps   xmm0, xmm0
0x140001c2f  mov     dword ptr [rbp+57h+arg_0], r13d
0x140001c33  mov     [rbp+57h+TokenInformation], r13
0x140001c37  mov     r14, r8
0x140001c3a  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x140001c3e  mov     [rbp+57h+ReturnLength], r13d
0x140001c42  mov     r15, rdx
0x140001c45  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x140001c49  mov     [rbp+57h+TokenHandle], r13
0x140001c4d  mov     [rbp+57h+Object], r13
0x140001c51  mov     [rbp+57h+var_78], r13
0x140001c55  mov     [rbp+57h+var_70], r13
0x140001c59  mov     [r8], r13
0x140001c5c  mov     [rdx], r13
0x140001c5f  cmp     [rax+4], r13b
0x140001c63  jnz     short loc_140001C76
0x140001c65  mov     rax, [rax+18h]
0x140001c69  mov     r12b, r13b
0x140001c6c  mov     rbx, [rax+8]
0x140001c70  add     rbx, 20h ; ' '
0x140001c74  jmp     short loc_140001C8D
0x140001c76  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140001c7a  lea     rbx, [rbp+57h+SubjectContext]
0x140001c7e  call    cs:__imp_SeCaptureSubjectContext
0x140001c85  nop     dword ptr [rax+rax+00h]
0x140001c8a  mov     r12b, 1
0x140001c8d  mov     rsi, [rbx]
0x140001c90  test    rsi, rsi
0x140001c93  jnz     short loc_140001C99
0x140001c95  mov     rsi, [rbx+10h]
0x140001c99  lea     rdx, [rbp+57h+var_78]
0x140001c9d  mov     rcx, rsi; Token
0x140001ca0  call    LuafvFindUser
0x140001ca5  mov     ebx, eax
0x140001ca7  test    eax, eax
0x140001ca9  js      loc_140001E25
0x140001caf  mov     rdi, [rbp+57h+var_78]
0x140001cb3  test    byte ptr [rdi+0A8h], 1
0x140001cba  jz      short loc_140001CEE
0x140001cbc  mov     rcx, [rdi+0B0h]
0x140001cc3  test    rcx, rcx
0x140001cc6  jz      short loc_140001CE6
0x140001cc8  mov     rax, 0FFFFF78000000014h
0x140001cd2  mov     rax, [rax]
0x140001cd5  xchg    rax, [rcx+10h]
0x140001cd9  mov     rax, [rdi+0B0h]
0x140001ce0  mov     [r14], rax
0x140001ce3  mov     [r15], rdi
0x140001ce6  mov     ebx, r13d
0x140001ce9  jmp     loc_140001E25
0x140001cee  lea     rax, [rbp+57h+TokenHandle]
0x140001cf2  mov     r9d, 8; DesiredAccess
0x140001cf8  mov     [rsp+0C0h+Handle], rax; Handle
0x140001cfd  xor     r8d, r8d; PassedAccessState
0x140001d00  mov     rax, cs:__imp_SeTokenObjectType
0x140001d07  mov     rcx, rsi; Object
0x140001d0a  mov     [rsp+0C0h+AccessMode], r13b; AccessMode
0x140001d0f  mov     rdx, [rax]
0x140001d12  mov     [rsp+0C0h+ObjectType], rdx; ObjectType
0x140001d17  mov     edx, 200h; HandleAttributes
0x140001d1c  call    cs:__imp_ObOpenObjectByPointer
0x140001d23  nop     dword ptr [rax+rax+00h]
0x140001d28  mov     ebx, eax
0x140001d2a  test    eax, eax
0x140001d2c  js      loc_140001E25
0x140001d32  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x140001d36  lea     rax, [rbp+57h+ReturnLength]
0x140001d3a  mov     esi, 8
0x140001d3f  mov     [rsp+0C0h+ObjectType], rax; ReturnLength
0x140001d44  mov     r9d, esi; TokenInformationLength
0x140001d47  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140001d4b  lea     edx, [rsi+0Bh]; TokenInformationClass
0x140001d4e  call    cs:__imp_ZwQueryInformationToken
0x140001d55  nop     dword ptr [rax+rax+00h]
0x140001d5a  mov     ebx, eax
0x140001d5c  test    eax, eax
0x140001d5e  jns     short loc_140001D6C
0x140001d60  or      byte ptr [rdi+0A8h], 1
0x140001d67  jmp     loc_140001E25
0x140001d6c  mov     r8, cs:__imp_SeTokenObjectType
0x140001d73  lea     rax, [rbp+57h+Object]
0x140001d77  mov     rcx, [rbp+57h+TokenInformation]; Handle
0x140001d7b  xor     r9d, r9d; AccessMode
0x140001d7e  mov     qword ptr [rsp+0C0h+AccessMode], r13; HandleInformation
0x140001d83  mov     edx, esi; DesiredAccess
0x140001d85  mov     [rsp+0C0h+ObjectType], rax; Object
0x140001d8a  mov     r8, [r8]; ObjectType
0x140001d8d  call    cs:__imp_ObReferenceObjectByHandle
0x140001d94  nop     dword ptr [rax+rax+00h]
0x140001d99  mov     ebx, eax
0x140001d9b  test    eax, eax
0x140001d9d  js      loc_140001E25
0x140001da3  mov     rcx, [rbp+57h+Object]; Token
0x140001da7  lea     r8, [rbp+57h+arg_0]; TokenInformation
0x140001dab  mov     edx, 33h ; '3'; TokenInformationClass
0x140001db0  call    cs:__imp_SeQueryInformationToken
0x140001db7  nop     dword ptr [rax+rax+00h]
0x140001dbc  mov     ebx, eax
0x140001dbe  test    eax, eax
0x140001dc0  js      short loc_140001E25
0x140001dc2  cmp     dword ptr [rbp+57h+arg_0], r13d
0x140001dc6  jz      short loc_140001E25
0x140001dc8  mov     rcx, [rbp+57h+Object]; Token
0x140001dcc  lea     rdx, [rbp+57h+var_70]
0x140001dd0  call    LuafvFindUser
0x140001dd5  mov     ebx, eax
0x140001dd7  test    eax, eax
0x140001dd9  js      short loc_140001E25
0x140001ddb  mov     rsi, [rbp+57h+var_70]
0x140001ddf  mov     rcx, [rdi+50h]; Sid1
0x140001de3  mov     rdx, [rsi+50h]; Sid2
0x140001de7  call    cs:__imp_RtlEqualSid
0x140001dee  nop     dword ptr [rax+rax+00h]
0x140001df3  test    al, al
0x140001df5  jnz     short loc_140001E25
0x140001df7  lock or [rsp+0C0h+var_C0], r13d
0x140001dfc  mov     [rdi+0B0h], rsi
0x140001e03  or      byte ptr [rdi+0A8h], 1
0x140001e0a  lock inc dword ptr [rsi+18h]
0x140001e0e  mov     rax, 0FFFFF78000000014h
0x140001e18  mov     rax, [rax]
0x140001e1b  xchg    rax, [rsi+10h]
0x140001e1f  mov     [r15], rdi
0x140001e22  mov     [r14], rsi
0x140001e25  mov     rcx, [rbp+57h+Object]; Object
0x140001e29  test    rcx, rcx
0x140001e2c  jz      short loc_140001E3A
0x140001e2e  call    cs:__imp_ObfDereferenceObject
0x140001e35  nop     dword ptr [rax+rax+00h]
0x140001e3a  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x140001e3e  test    rcx, rcx
0x140001e41  jz      short loc_140001E4F
0x140001e43  call    cs:__imp_ZwClose
0x140001e4a  nop     dword ptr [rax+rax+00h]
0x140001e4f  mov     rcx, [rbp+57h+TokenInformation]; Handle
0x140001e53  test    rcx, rcx
0x140001e56  jz      short loc_140001E64
0x140001e58  call    cs:__imp_ZwClose
0x140001e5f  nop     dword ptr [rax+rax+00h]
0x140001e64  test    r12b, r12b
0x140001e67  jz      short loc_140001E79
0x140001e69  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140001e6d  call    cs:__imp_SeReleaseSubjectContext
0x140001e74  nop     dword ptr [rax+rax+00h]
0x140001e79  mov     eax, ebx
0x140001e7b  add     rsp, 88h
0x140001e82  pop     r15
0x140001e84  pop     r14
0x140001e86  pop     r13
0x140001e88  pop     r12
0x140001e8a  pop     rdi
0x140001e8b  pop     rsi
0x140001e8c  pop     rbx
0x140001e8d  pop     rbp
0x140001e8e  retn
```
