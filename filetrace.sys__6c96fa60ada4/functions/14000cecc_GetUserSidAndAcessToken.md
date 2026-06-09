# GetUserSidAndAcessToken

- ea: `0x14000cecc`
- end: `0x14000d02a`
- name: `GetUserSidAndAcessToken`
- size: `350`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400010b0`
- `0x140002110`

## callees

- `0x140003600`
- `0x14000cecc`

## import_xrefs

- `ntoskrnl!PsReferencePrimaryToken` at `0x14000cf4e`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14000cf4e`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14000cfe8`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14000cfe8`
- `ntoskrnl!SeQueryInformationToken` at `0x14000cf6d`
- `ntoskrnl!SeQueryInformationToken` at `0x14000cf6d`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000cff6`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000cff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d00e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d00e`
- `ntoskrnl!ExAllocatePool2` at `0x14000cfa4`
- `ntoskrnl!ExAllocatePool2` at `0x14000cfa4`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000cf23`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000cf23`
- `FLTMGR!FltGetRequestorProcess` at `0x14000cf3a`
- `FLTMGR!FltGetRequestorProcess` at `0x14000cf3a`

## pseudocode

```c
__int64 __fastcall GetUserSidAndAcessToken(PFLT_CALLBACK_DATA CallbackData, _DWORD *a2, _QWORD *a3, _QWORD *a4)
{
  struct _KTHREAD *Thread; // rcx
  char v10; // bp
  PACCESS_TOKEN v11; // rbx
  struct _KPROCESS *RequestorProcess; // rax
  NTSTATUS v13; // edi
  PVOID v14; // rcx
  void *Pool2; // rax
  unsigned __int8 CopyOnOpen[4]; // [rsp+20h] [rbp-48h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+24h] [rbp-44h] BYREF
  PVOID TokenInformation; // [rsp+28h] [rbp-40h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+70h] [rbp+8h] BYREF

  CopyOnOpen[0] = 0;
  Thread = CallbackData->Thread;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityAnonymous;
  TokenInformation = 0;
  if ( !Thread )
    return 3221225485LL;
  v10 = 1;
  v11 = PsReferenceImpersonationToken(Thread, CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  if ( !v11 )
  {
    RequestorProcess = FltGetRequestorProcess(CallbackData);
    if ( !RequestorProcess )
      return 3221225473LL;
    v11 = PsReferencePrimaryToken(RequestorProcess);
    v10 = 0;
  }
  v13 = SeQueryInformationToken(v11, TokenUser, &TokenInformation);
  if ( v13 >= 0 )
  {
    v14 = TokenInformation;
    *a4 = v11;
    LODWORD(v14) = 4 * *(unsigned __int8 *)(*(_QWORD *)v14 + 1LL) + 24;
    *a2 = (_DWORD)v14;
    Pool2 = (void *)ExAllocatePool2(66, (unsigned int)v14, 1920224326);
    *a3 = Pool2;
    if ( Pool2 )
    {
      memmove(Pool2, TokenInformation, (unsigned int)*a2);
    }
    else
    {
      *a2 = 0;
      v13 = -1073741670;
      *a4 = 0;
    }
  }
  if ( v11 )
  {
    if ( v10 )
      PsDereferenceImpersonationToken(v11);
    else
      PsDereferencePrimaryToken(v11);
  }
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000cecc  mov     rax, rsp
0x14000cecf  push    rbx
0x14000ced0  push    rbp
0x14000ced1  push    rsi
0x14000ced2  push    rdi
0x14000ced3  push    r14
0x14000ced5  push    r15
0x14000ced7  sub     rsp, 38h
0x14000cedb  mov     rdi, rcx
0x14000cede  mov     byte ptr [rax-48h], 0
0x14000cee2  mov     rcx, [rcx+8]; Thread
0x14000cee6  mov     r14, r9
0x14000cee9  mov     byte ptr [rax+8], 0
0x14000ceed  mov     r15, r8
0x14000cef0  mov     dword ptr [rax-44h], 0
0x14000cef7  mov     rsi, rdx
0x14000cefa  mov     qword ptr [rax-40h], 0
0x14000cf02  test    rcx, rcx
0x14000cf05  jnz     short loc_14000CF11
0x14000cf07  mov     eax, 0C000000Dh
0x14000cf0c  jmp     loc_14000D01C
0x14000cf11  lea     r9, [rsp+68h+ImpersonationLevel]; ImpersonationLevel
0x14000cf16  mov     bpl, 1
0x14000cf19  lea     r8, [rsp+68h+EffectiveOnly]; EffectiveOnly
0x14000cf1e  lea     rdx, [rsp+68h+CopyOnOpen]; CopyOnOpen
0x14000cf23  call    cs:__imp_PsReferenceImpersonationToken
0x14000cf2a  nop     dword ptr [rax+rax+00h]
0x14000cf2f  mov     rbx, rax
0x14000cf32  test    rax, rax
0x14000cf35  jnz     short loc_14000CF60
0x14000cf37  mov     rcx, rdi; CallbackData
0x14000cf3a  call    cs:__imp_FltGetRequestorProcess
0x14000cf41  nop     dword ptr [rax+rax+00h]
0x14000cf46  test    rax, rax
0x14000cf49  jz      short loc_14000CFC4
0x14000cf4b  mov     rcx, rax; Process
0x14000cf4e  call    cs:__imp_PsReferencePrimaryToken
0x14000cf55  nop     dword ptr [rax+rax+00h]
0x14000cf5a  mov     rbx, rax
0x14000cf5d  xor     bpl, bpl
0x14000cf60  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x14000cf65  mov     edx, 1; TokenInformationClass
0x14000cf6a  mov     rcx, rbx; Token
0x14000cf6d  call    cs:__imp_SeQueryInformationToken
0x14000cf74  nop     dword ptr [rax+rax+00h]
0x14000cf79  mov     edi, eax
0x14000cf7b  test    eax, eax
0x14000cf7d  js      short loc_14000CFDB
0x14000cf7f  mov     rcx, [rsp+68h+TokenInformation]
0x14000cf84  mov     r8d, 72744C46h
0x14000cf8a  mov     [r14], rbx
0x14000cf8d  mov     rdx, [rcx]
0x14000cf90  movzx   ecx, byte ptr [rdx+1]
0x14000cf94  lea     ecx, ds:18h[rcx*4]
0x14000cf9b  mov     [rsi], ecx
0x14000cf9d  mov     edx, ecx
0x14000cf9f  mov     ecx, 42h ; 'B'
0x14000cfa4  call    cs:__imp_ExAllocatePool2
0x14000cfab  nop     dword ptr [rax+rax+00h]
0x14000cfb0  mov     [r15], rax
0x14000cfb3  test    rax, rax
0x14000cfb6  jnz     short loc_14000CFCB
0x14000cfb8  mov     [rsi], eax
0x14000cfba  mov     edi, 0C000009Ah
0x14000cfbf  mov     [r14], rax
0x14000cfc2  jmp     short loc_14000CFDB
0x14000cfc4  mov     eax, 0C0000001h
0x14000cfc9  jmp     short loc_14000D01C
0x14000cfcb  mov     r8d, [rsi]; Size
0x14000cfce  mov     rcx, rax; void *
0x14000cfd1  mov     rdx, [rsp+68h+TokenInformation]; Src
0x14000cfd6  call    memmove
0x14000cfdb  test    rbx, rbx
0x14000cfde  jz      short loc_14000D002
0x14000cfe0  mov     rcx, rbx; PrimaryToken
0x14000cfe3  test    bpl, bpl
0x14000cfe6  jz      short loc_14000CFF6
0x14000cfe8  call    cs:__imp_PsDereferenceImpersonationToken
0x14000cfef  nop     dword ptr [rax+rax+00h]
0x14000cff4  jmp     short loc_14000D002
0x14000cff6  call    cs:__imp_PsDereferencePrimaryToken
0x14000cffd  nop     dword ptr [rax+rax+00h]
0x14000d002  mov     rcx, [rsp+68h+TokenInformation]; P
0x14000d007  test    rcx, rcx
0x14000d00a  jz      short loc_14000D01A
0x14000d00c  xor     edx, edx; Tag
0x14000d00e  call    cs:__imp_ExFreePoolWithTag
0x14000d015  nop     dword ptr [rax+rax+00h]
0x14000d01a  mov     eax, edi
0x14000d01c  add     rsp, 38h
0x14000d020  pop     r15
0x14000d022  pop     r14
0x14000d024  pop     rdi
0x14000d025  pop     rsi
0x14000d026  pop     rbp
0x14000d027  pop     rbx
0x14000d028  retn
```
