# SetMountOptions

- ea: `0x140016b14`
- end: `0x140016cb2`
- name: `SetMountOptions`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140022c5c`

## callees

- `0x1400159fc`
- `0x140016634`
- `0x140016aa8`
- `0x140016b14`
- `0x1400173f8`
- `0x140017590`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140016b76`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140016b76`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140016b9b`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140016b9b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140016bac`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140016bac`

## pseudocode

```c
__int64 __fastcall SetMountOptions(__int64 a1, unsigned int a2)
{
  __int64 v2; // rdi
  PACCESS_TOKEN PrimaryToken; // rcx
  unsigned int updated; // ebx
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+40h] [rbp-28h] BYREF
  struct _LUID AuthenticationId; // [rsp+80h] [rbp+18h] BYREF
  size_t pcchLength; // [rsp+88h] [rbp+20h] BYREF

  v2 = a2;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  AuthenticationId = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids);
  SeCaptureSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  SeQueryAuthenticationIdToken(PrimaryToken, &AuthenticationId);
  SeReleaseSubjectContext(&SubjectContext);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_dd(
      WPP_GLOBAL_Control->AttachedDevice,
      38,
      WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids,
      AuthenticationId.LowPart,
      AuthenticationId.HighPart);
  if ( (unsigned int)v2 < 0x40 || !a1 )
    return 3221225485LL;
  *(_QWORD *)a1 = a1 + 64;
  if ( RtlStringCchLengthW((STRSAFE_PCNZWCH)(a1 + 64), (unsigned int)((unsigned __int64)(v2 - 64) >> 1), &pcchLength) )
    return 3221225485LL;
  updated = NuiUpdateDefault((unsigned int)&AuthenticationId, 0, 0, 0, 0, 32, 0, a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids);
  return updated;
}

```

## disassembly

```asm
0x140016b14  mov     rax, rsp
0x140016b17  mov     [rax+8], rbx
0x140016b1b  mov     [rax+10h], rdi
0x140016b1f  push    r14
0x140016b21  sub     rsp, 60h
0x140016b25  mov     edi, edx
0x140016b27  mov     rbx, rcx
0x140016b2a  xorps   xmm0, xmm0
0x140016b2d  movups  xmmword ptr [rax-28h], xmm0
0x140016b31  movups  xmmword ptr [rax-18h], xmm0
0x140016b35  mov     qword ptr [rax+18h], 0
0x140016b3d  lea     r14, WPP_GLOBAL_Control
0x140016b44  mov     rcx, cs:WPP_GLOBAL_Control
0x140016b4b  cmp     rcx, r14
0x140016b4e  jz      short loc_140016B71
0x140016b50  test    dword ptr [rcx+2Ch], 20000h
0x140016b57  jz      short loc_140016B71
0x140016b59  mov     edx, 25h ; '%'
0x140016b5e  mov     r9, rbx
0x140016b61  lea     r8, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids
0x140016b68  mov     rcx, [rcx+18h]
0x140016b6c  call    WPP_SF_q
0x140016b71  lea     rcx, [rsp+68h+SubjectContext]; SubjectContext
0x140016b76  call    cs:__imp_SeCaptureSubjectContext
0x140016b7d  nop     dword ptr [rax+rax+00h]
0x140016b82  mov     rcx, [rsp+68h+SubjectContext.PrimaryToken]
0x140016b87  mov     rax, [rsp+68h+SubjectContext.ClientToken]
0x140016b8c  test    rax, rax
0x140016b8f  cmovnz  rcx, rax; Token
0x140016b93  lea     rdx, [rsp+68h+AuthenticationId]; AuthenticationId
0x140016b9b  call    cs:__imp_SeQueryAuthenticationIdToken
0x140016ba2  nop     dword ptr [rax+rax+00h]
0x140016ba7  lea     rcx, [rsp+68h+SubjectContext]; SubjectContext
0x140016bac  call    cs:__imp_SeReleaseSubjectContext
0x140016bb3  nop     dword ptr [rax+rax+00h]
0x140016bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140016bbf  cmp     rcx, r14
0x140016bc2  jz      short loc_140016BF5
0x140016bc4  test    dword ptr [rcx+2Ch], 20000h
0x140016bcb  jz      short loc_140016BF5
0x140016bcd  mov     edx, 26h ; '&'
0x140016bd2  mov     eax, [rsp+68h+AuthenticationId.HighPart]
0x140016bd9  mov     [rsp+68h+var_48], eax
0x140016bdd  mov     r9d, [rsp+68h+AuthenticationId.LowPart]
0x140016be5  lea     r8, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids
0x140016bec  mov     rcx, [rcx+18h]
0x140016bf0  call    WPP_SF_dd
0x140016bf5  cmp     edi, 40h ; '@'
0x140016bf8  jb      loc_140016C9B
0x140016bfe  test    rbx, rbx
0x140016c01  jz      loc_140016C9B
0x140016c07  lea     rcx, [rbx+40h]; psz
0x140016c0b  mov     [rbx], rcx
0x140016c0e  lea     rdx, [rdi-40h]
0x140016c12  shr     rdx, 1
0x140016c15  mov     edx, edx; cchMax
0x140016c17  lea     r8, [rsp+68h+pcchLength]; pcchLength
0x140016c1f  call    RtlStringCchLengthW
0x140016c24  test    eax, eax
0x140016c26  jz      short loc_140016C2F
0x140016c28  mov     eax, 0C000000Dh
0x140016c2d  jmp     short loc_140016CA0
0x140016c2f  mov     [rsp+68h+var_30], rbx
0x140016c34  mov     [rsp+68h+var_38], 0
0x140016c3d  mov     [rsp+68h+var_40], 20h ; ' '
0x140016c45  mov     [rsp+68h+var_48], 0
0x140016c4d  xor     r9d, r9d
0x140016c50  xor     r8d, r8d
0x140016c53  xor     edx, edx
0x140016c55  lea     rcx, [rsp+68h+AuthenticationId]
0x140016c5d  call    NuiUpdateDefault
0x140016c62  mov     ebx, eax
0x140016c64  mov     rcx, cs:WPP_GLOBAL_Control
0x140016c6b  cmp     rcx, r14
0x140016c6e  jz      short loc_140016C90
0x140016c70  mov     edx, [rcx+2Ch]
0x140016c73  test    dl, 4
0x140016c76  jz      short loc_140016C90
0x140016c78  mov     edx, 27h ; '''
0x140016c7d  mov     r9d, eax
0x140016c80  lea     r8, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids
0x140016c87  mov     rcx, [rcx+18h]
0x140016c8b  call    WPP_SF_d
0x140016c90  mov     eax, ebx
0x140016c92  jmp     short loc_140016CA0
0x140016c94  mov     eax, 0C000000Dh
0x140016c99  jmp     short loc_140016CA0
0x140016c9b  mov     eax, 0C000000Dh
0x140016ca0  mov     rbx, [rsp+68h+arg_0]
0x140016ca5  mov     rdi, [rsp+68h+arg_8]
0x140016caa  add     rsp, 60h
0x140016cae  pop     r14
0x140016cb0  retn
```
