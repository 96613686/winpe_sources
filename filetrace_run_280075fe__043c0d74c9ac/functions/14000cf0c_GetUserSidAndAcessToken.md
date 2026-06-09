# GetUserSidAndAcessToken

- ea: `0x14000cf0c`
- end: `0x14000d067`
- name: `GetUserSidAndAcessToken`
- size: `347`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400010b0`
- `0x140002110`

## callees

- `0x140003600`
- `0x14000cf0c`

## import_xrefs

- `ntoskrnl!PsReferencePrimaryToken` at `0x14000cf8e`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14000cf8e`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14000d025`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14000d025`
- `ntoskrnl!SeQueryInformationToken` at `0x14000cfad`
- `ntoskrnl!SeQueryInformationToken` at `0x14000cfad`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000d033`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000d033`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d04b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d04b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cfe5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cfe5`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000cf63`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000cf63`
- `FLTMGR!FltGetRequestorProcess` at `0x14000cf7a`
- `FLTMGR!FltGetRequestorProcess` at `0x14000cf7a`

## pseudocode

```c
__int64 __fastcall GetUserSidAndAcessToken(PFLT_CALLBACK_DATA CallbackData, _DWORD *a2, _QWORD *a3, _QWORD *a4)
{
  struct _KTHREAD *Thread; // rcx
  char v10; // si
  PACCESS_TOKEN v11; // rbx
  struct _KPROCESS *RequestorProcess; // rax
  NTSTATUS v13; // edi
  PVOID v14; // rcx
  PVOID PoolWithTag; // rax
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
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, (unsigned int)v14, 0x72744C46u);
    *a3 = PoolWithTag;
    if ( PoolWithTag )
      memmove(PoolWithTag, TokenInformation, (unsigned int)*a2);
    else
      v13 = -1073741670;
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
0x14000cf0c  mov     rax, rsp
0x14000cf0f  push    rbx
0x14000cf10  push    rbp
0x14000cf11  push    rsi
0x14000cf12  push    rdi
0x14000cf13  push    r14
0x14000cf15  push    r15
0x14000cf17  sub     rsp, 38h
0x14000cf1b  mov     rdi, rcx
0x14000cf1e  mov     byte ptr [rax-48h], 0
0x14000cf22  mov     rcx, [rcx+8]; Thread
0x14000cf26  mov     r15, r9
0x14000cf29  mov     byte ptr [rax+8], 0
0x14000cf2d  mov     rbp, r8
0x14000cf30  mov     dword ptr [rax-44h], 0
0x14000cf37  mov     r14, rdx
0x14000cf3a  mov     qword ptr [rax-40h], 0
0x14000cf42  test    rcx, rcx
0x14000cf45  jnz     short loc_14000CF51
0x14000cf47  mov     eax, 0C000000Dh
0x14000cf4c  jmp     loc_14000D059
0x14000cf51  lea     r9, [rsp+68h+ImpersonationLevel]; ImpersonationLevel
0x14000cf56  mov     sil, 1
0x14000cf59  lea     r8, [rsp+68h+EffectiveOnly]; EffectiveOnly
0x14000cf5e  lea     rdx, [rsp+68h+CopyOnOpen]; CopyOnOpen
0x14000cf63  call    cs:__imp_PsReferenceImpersonationToken
0x14000cf6a  nop     dword ptr [rax+rax+00h]
0x14000cf6f  mov     rbx, rax
0x14000cf72  test    rax, rax
0x14000cf75  jnz     short loc_14000CFA0
0x14000cf77  mov     rcx, rdi; CallbackData
0x14000cf7a  call    cs:__imp_FltGetRequestorProcess
0x14000cf81  nop     dword ptr [rax+rax+00h]
0x14000cf86  test    rax, rax
0x14000cf89  jz      short loc_14000D001
0x14000cf8b  mov     rcx, rax; Process
0x14000cf8e  call    cs:__imp_PsReferencePrimaryToken
0x14000cf95  nop     dword ptr [rax+rax+00h]
0x14000cf9a  mov     rbx, rax
0x14000cf9d  xor     sil, sil
0x14000cfa0  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x14000cfa5  mov     edx, 1; TokenInformationClass
0x14000cfaa  mov     rcx, rbx; Token
0x14000cfad  call    cs:__imp_SeQueryInformationToken
0x14000cfb4  nop     dword ptr [rax+rax+00h]
0x14000cfb9  mov     edi, eax
0x14000cfbb  test    eax, eax
0x14000cfbd  js      short loc_14000D018
0x14000cfbf  mov     rcx, [rsp+68h+TokenInformation]
0x14000cfc4  mov     r8d, 72744C46h; Tag
0x14000cfca  mov     [r15], rbx
0x14000cfcd  mov     rdx, [rcx]
0x14000cfd0  movzx   ecx, byte ptr [rdx+1]
0x14000cfd4  lea     ecx, ds:18h[rcx*4]
0x14000cfdb  mov     [r14], ecx
0x14000cfde  mov     edx, ecx; NumberOfBytes
0x14000cfe0  mov     ecx, 200h; PoolType
0x14000cfe5  call    cs:__imp_ExAllocatePoolWithTag
0x14000cfec  nop     dword ptr [rax+rax+00h]
0x14000cff1  mov     [rbp+0], rax
0x14000cff5  test    rax, rax
0x14000cff8  jnz     short loc_14000D008
0x14000cffa  mov     edi, 0C000009Ah
0x14000cfff  jmp     short loc_14000D018
0x14000d001  mov     eax, 0C0000001h
0x14000d006  jmp     short loc_14000D059
0x14000d008  mov     r8d, [r14]; Size
0x14000d00b  mov     rcx, rax; void *
0x14000d00e  mov     rdx, [rsp+68h+TokenInformation]; Src
0x14000d013  call    memmove
0x14000d018  test    rbx, rbx
0x14000d01b  jz      short loc_14000D03F
0x14000d01d  mov     rcx, rbx; PrimaryToken
0x14000d020  test    sil, sil
0x14000d023  jz      short loc_14000D033
0x14000d025  call    cs:__imp_PsDereferenceImpersonationToken
0x14000d02c  nop     dword ptr [rax+rax+00h]
0x14000d031  jmp     short loc_14000D03F
0x14000d033  call    cs:__imp_PsDereferencePrimaryToken
0x14000d03a  nop     dword ptr [rax+rax+00h]
0x14000d03f  mov     rcx, [rsp+68h+TokenInformation]; P
0x14000d044  test    rcx, rcx
0x14000d047  jz      short loc_14000D057
0x14000d049  xor     edx, edx; Tag
0x14000d04b  call    cs:__imp_ExFreePoolWithTag
0x14000d052  nop     dword ptr [rax+rax+00h]
0x14000d057  mov     eax, edi
0x14000d059  add     rsp, 38h
0x14000d05d  pop     r15
0x14000d05f  pop     r14
0x14000d061  pop     rdi
0x14000d062  pop     rsi
0x14000d063  pop     rbp
0x14000d064  pop     rbx
0x14000d065  retn
```
