# DfscNetUseGetSearchKey

- ea: `0x140025aa0`
- end: `0x140025d46`
- name: `DfscNetUseGetSearchKey`
- size: `678`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140003a94`
- `0x14001134c`
- `0x140013db8`
- `0x14002545c`

## callees

- `0x1400027f8`
- `0x1400042c8`
- `0x140025aa0`
- `0x140025d4c`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140025b79`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140025c0d`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140025b79`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140025c0d`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140025c2c`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140025c2c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140025be7`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140025c3f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140025be7`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140025c3f`
- `ntoskrnl!towupper` at `0x140025afb`
- `ntoskrnl!towupper` at `0x140025afb`
- `ntoskrnl!SeQuerySessionIdToken` at `0x140025b9a`
- `ntoskrnl!SeQuerySessionIdToken` at `0x140025b9a`

## pseudocode

```c
__int64 __fastcall DfscNetUseGetSearchKey(__int64 a1, __int128 *a2, __int64 a3, PRTL_AVL_TABLE *a4, __int64 a5)
{
  wint_t *v5; // rax
  wint_t v9; // cx
  int v10; // r15d
  int v11; // r12d
  __int64 v12; // rdx
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // rbx
  PACCESS_TOKEN ClientToken; // rcx
  __int64 v15; // rdx
  NTSTATUS SessionIdToken; // esi
  __int64 v17; // r8
  PACCESS_TOKEN PrimaryToken; // rcx
  unsigned int AuthenticationIdToken; // ebx
  PRTL_AVL_TABLE DevicelessNetUseTable; // rax
  __int128 v21; // xmm0
  __int64 v23; // rbx
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+20h] [rbp-68h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT Token; // [rsp+40h] [rbp-48h] BYREF

  v5 = (wint_t *)*((_QWORD *)a2 + 1);
  if ( !v5 )
    return 3221225485LL;
  v9 = *v5;
  if ( !*v5 )
    return 3221225485LL;
  v10 = 1;
  if ( v9 == 92 || v5[1] != 58 )
  {
    v11 = 0;
    goto LABEL_7;
  }
  if ( (unsigned __int16)(towupper(v9) - 65) > 0x19u )
    return 3221225485LL;
  v11 = 1;
LABEL_7:
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  *(_OWORD *)a5 = 0;
  *(_OWORD *)(a5 + 16) = 0;
  *(_OWORD *)(a5 + 32) = 0;
  v12 = *(_QWORD *)(a3 + 184);
  if ( (!*(_BYTE *)v12 || *(_BYTE *)v12 == 1 || *(_BYTE *)v12 == 19) && (v23 = *(_QWORD *)(v12 + 8)) != 0 )
  {
    p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(v23 + 8) + 32LL);
  }
  else
  {
    SeCaptureSubjectContext(&SubjectContext);
    p_SubjectContext = &SubjectContext;
  }
  ClientToken = p_SubjectContext->ClientToken;
  if ( !p_SubjectContext->ClientToken )
    ClientToken = p_SubjectContext->PrimaryToken;
  SessionIdToken = SeQuerySessionIdToken(ClientToken, (PULONG)(a5 + 16));
  if ( SessionIdToken < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        35,
        WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids,
        (unsigned int)SessionIdToken);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
  {
    WPP_SF_l(WPP_GLOBAL_Control->AttachedDevice, v15, v17, *(unsigned int *)(a5 + 16));
  }
  if ( p_SubjectContext == &SubjectContext )
    SeReleaseSubjectContext(&SubjectContext);
  if ( SessionIdToken )
    return (unsigned int)SessionIdToken;
  memset(&Token, 0, sizeof(Token));
  SeCaptureSubjectContext(&Token);
  PrimaryToken = Token.ClientToken;
  if ( !Token.ClientToken )
    PrimaryToken = Token.PrimaryToken;
  AuthenticationIdToken = SeQueryAuthenticationIdToken(PrimaryToken, (PLUID)(a5 + 20));
  SeReleaseSubjectContext(&Token);
  if ( !AuthenticationIdToken )
  {
    if ( v11 )
    {
      if ( a1 )
        DevicelessNetUseTable = *(PRTL_AVL_TABLE *)(a1 + 256);
      else
        DevicelessNetUseTable = Table;
    }
    else
    {
      DevicelessNetUseTable = (PRTL_AVL_TABLE)DfscGetDevicelessNetUseTable(a1);
      v10 = 0;
    }
    *(_DWORD *)(a5 + 40) = v10;
    v21 = *a2;
    *a4 = DevicelessNetUseTable;
    *(_OWORD *)a5 = v21;
  }
  return AuthenticationIdToken;
}

```

## disassembly

```asm
0x140025aa0  mov     [rsp+arg_18], r9
0x140025aa5  push    rbx
0x140025aa6  push    rbp
0x140025aa7  push    r12
0x140025aa9  push    r13
0x140025aab  push    r15
0x140025aad  sub     rsp, 60h
0x140025ab1  mov     rax, [rdx+8]
0x140025ab5  mov     rbx, r8
0x140025ab8  mov     rbp, rdx
0x140025abb  mov     r13, rcx
0x140025abe  test    rax, rax
0x140025ac1  jz      loc_140025C9E
0x140025ac7  movzx   ecx, word ptr [rax]; C
0x140025aca  test    cx, cx
0x140025acd  jz      loc_140025C9E
0x140025ad3  mov     r15d, 1
0x140025ad9  cmp     cx, 5Ch ; '\'
0x140025add  jz      loc_140025CB1
0x140025ae3  movzx   edx, word ptr [rax+2]
0x140025ae7  cmp     dx, 5Ch ; '\'
0x140025aeb  jz      loc_140025CB1
0x140025af1  cmp     dx, 3Ah ; ':'
0x140025af5  jnz     loc_140025CB1
0x140025afb  call    cs:__imp_towupper
0x140025b02  nop     dword ptr [rax+rax+00h]
0x140025b07  sub     ax, 41h ; 'A'
0x140025b0b  cmp     ax, 19h
0x140025b0f  ja      loc_140025C9E
0x140025b15  mov     r12d, r15d
0x140025b18  xorps   xmm0, xmm0
0x140025b1b  mov     [rsp+88h+arg_0], rsi
0x140025b23  mov     [rsp+88h+arg_8], rdi
0x140025b2b  mov     rdi, [rsp+88h+arg_20]
0x140025b33  movups  xmmword ptr [rsp+88h+SubjectContext.ClientToken], xmm0
0x140025b38  mov     [rsp+88h+arg_10], r14
0x140025b40  movups  xmmword ptr [rsp+88h+SubjectContext.PrimaryToken], xmm0
0x140025b45  movups  xmmword ptr [rdi], xmm0
0x140025b48  movups  xmmword ptr [rdi+10h], xmm0
0x140025b4c  movups  xmmword ptr [rdi+20h], xmm0
0x140025b50  mov     rdx, [rbx+0B8h]
0x140025b57  movzx   eax, byte ptr [rdx]
0x140025b5a  test    eax, eax
0x140025b5c  jz      loc_140025CB9
0x140025b62  sub     eax, r15d
0x140025b65  jz      loc_140025CB9
0x140025b6b  cmp     eax, 12h
0x140025b6e  jz      loc_140025CB9
0x140025b74  lea     rcx, [rsp+88h+SubjectContext]; SubjectContext
0x140025b79  call    cs:__imp_SeCaptureSubjectContext
0x140025b80  nop     dword ptr [rax+rax+00h]
0x140025b85  lea     rbx, [rsp+88h+SubjectContext]
0x140025b8a  mov     rcx, [rbx]
0x140025b8d  test    rcx, rcx
0x140025b90  jnz     short loc_140025B96
0x140025b92  mov     rcx, [rbx+10h]; Token
0x140025b96  lea     rdx, [rdi+10h]; SessionId
0x140025b9a  call    cs:__imp_SeQuerySessionIdToken
0x140025ba1  nop     dword ptr [rax+rax+00h]
0x140025ba6  mov     esi, eax
0x140025ba8  test    eax, eax
0x140025baa  js      loc_140025CD7
0x140025bb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140025bb7  lea     rax, WPP_GLOBAL_Control
0x140025bbe  cmp     rcx, rax
0x140025bc1  jz      short loc_140025BD0
0x140025bc3  test    dword ptr [rcx+2Ch], 400000h
0x140025bca  jnz     loc_140025D18
0x140025bd0  mov     r14, [rsp+88h+arg_10]
0x140025bd8  lea     rax, [rsp+88h+SubjectContext]
0x140025bdd  cmp     rbx, rax
0x140025be0  jnz     short loc_140025BF3
0x140025be2  lea     rcx, [rsp+88h+SubjectContext]; SubjectContext
0x140025be7  call    cs:__imp_SeReleaseSubjectContext
0x140025bee  nop     dword ptr [rax+rax+00h]
0x140025bf3  test    esi, esi
0x140025bf5  jnz     loc_140025CD3
0x140025bfb  xorps   xmm0, xmm0
0x140025bfe  lea     rcx, [rsp+88h+Token]; SubjectContext
0x140025c03  movups  xmmword ptr [rsp+88h+Token.ClientToken], xmm0
0x140025c08  movups  xmmword ptr [rsp+88h+Token.PrimaryToken], xmm0
0x140025c0d  call    cs:__imp_SeCaptureSubjectContext
0x140025c14  nop     dword ptr [rax+rax+00h]
0x140025c19  mov     rcx, [rsp+88h+Token.ClientToken]
0x140025c1e  lea     rdx, [rdi+14h]; AuthenticationId
0x140025c22  test    rcx, rcx
0x140025c25  jnz     short loc_140025C2C
0x140025c27  mov     rcx, [rsp+88h+Token.PrimaryToken]; Token
0x140025c2c  call    cs:__imp_SeQueryAuthenticationIdToken
0x140025c33  nop     dword ptr [rax+rax+00h]
0x140025c38  lea     rcx, [rsp+88h+Token]; SubjectContext
0x140025c3d  mov     ebx, eax
0x140025c3f  call    cs:__imp_SeReleaseSubjectContext
0x140025c46  nop     dword ptr [rax+rax+00h]
0x140025c4b  test    ebx, ebx
0x140025c4d  jnz     short loc_140025C7E
0x140025c4f  test    r12d, r12d
0x140025c52  jz      loc_140025D36
0x140025c58  test    r13, r13
0x140025c5b  jnz     loc_140025D2A
0x140025c61  mov     rax, cs:Table
0x140025c68  mov     [rdi+28h], r15d
0x140025c6c  mov     rcx, [rsp+88h+arg_18]
0x140025c74  movups  xmm0, xmmword ptr [rbp+0]
0x140025c78  mov     [rcx], rax
0x140025c7b  movups  xmmword ptr [rdi], xmm0
0x140025c7e  mov     eax, ebx
0x140025c80  mov     rsi, [rsp+88h+arg_0]
0x140025c88  mov     rdi, [rsp+88h+arg_8]
0x140025c90  add     rsp, 60h
0x140025c94  pop     r15
0x140025c96  pop     r13
0x140025c98  pop     r12
0x140025c9a  pop     rbp
0x140025c9b  pop     rbx
0x140025c9c  retn
0x140025c9e  mov     eax, 0C000000Dh
0x140025ca3  add     rsp, 60h
0x140025ca7  pop     r15
0x140025ca9  pop     r13
0x140025cab  pop     r12
0x140025cad  pop     rbp
0x140025cae  pop     rbx
0x140025caf  retn
0x140025cb1  xor     r12d, r12d
0x140025cb4  jmp     loc_140025B18
0x140025cb9  mov     rbx, [rdx+8]
0x140025cbd  test    rbx, rbx
0x140025cc0  jz      loc_140025B74
0x140025cc6  mov     rbx, [rbx+8]
0x140025cca  add     rbx, 20h ; ' '
0x140025cce  jmp     loc_140025B8A
0x140025cd3  mov     eax, esi
0x140025cd5  jmp     short loc_140025C80
0x140025cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140025cde  lea     rax, WPP_GLOBAL_Control
0x140025ce5  cmp     rcx, rax
0x140025ce8  jz      loc_140025BD0
0x140025cee  test    dword ptr [rcx+2Ch], 100000h
0x140025cf5  jz      loc_140025BD0
0x140025cfb  mov     rcx, [rcx+18h]
0x140025cff  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x140025d06  mov     edx, 23h ; '#'
0x140025d0b  mov     r9d, esi
0x140025d0e  call    WPP_SF_D
0x140025d13  jmp     loc_140025BD0
0x140025d18  mov     r9d, [rdi+10h]
0x140025d1c  mov     rcx, [rcx+18h]
0x140025d20  call    WPP_SF_l
0x140025d25  jmp     loc_140025BD0
0x140025d2a  mov     rax, [r13+100h]
0x140025d31  jmp     loc_140025C68
0x140025d36  mov     rcx, r13
0x140025d39  call    DfscGetDevicelessNetUseTable
0x140025d3e  xor     r15d, r15d
0x140025d41  jmp     loc_140025C68
```
