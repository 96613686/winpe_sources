# NdisGetThreadObjectCompartmentId

- ea: `0x140050630`
- end: `0x140050864`
- name: `NdisGetThreadObjectCompartmentId`
- size: `564`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140050630`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140050676`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400506e6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140050676`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400506e6`
- `ntoskrnl!ObfDereferenceObject` at `0x140050846`
- `ntoskrnl!ObfDereferenceObject` at `0x140050846`
- `ntoskrnl!KeReleaseSpinLock` at `0x140050802`
- `ntoskrnl!KeReleaseSpinLock` at `0x140050802`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400507d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400507d3`
- `ntoskrnl!SeQueryInformationToken` at `0x140050761`
- `ntoskrnl!SeQueryInformationToken` at `0x14005079c`
- `ntoskrnl!SeQueryInformationToken` at `0x140050761`
- `ntoskrnl!SeQueryInformationToken` at `0x14005079c`
- `ntoskrnl!PsGetThreadProperty` at `0x140050642`
- `ntoskrnl!PsGetThreadProperty` at `0x140050642`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14005081f`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140050830`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14005081f`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140050830`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14005069c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14005070c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14005069c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14005070c`
- `ntoskrnl!PsGetThreadSessionId` at `0x1400506b7`
- `ntoskrnl!PsGetThreadSessionId` at `0x140050723`
- `ntoskrnl!PsGetThreadSessionId` at `0x1400506b7`
- `ntoskrnl!PsGetThreadSessionId` at `0x140050723`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140050772`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400507ad`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140050772`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400507ad`

## pseudocode

```c
__int64 __fastcall NdisGetThreadObjectCompartmentId(PETHREAD Thread)
{
  unsigned int *ThreadProperty; // rax
  __int64 v3; // rcx
  PACCESS_TOKEN v4; // rax
  void *v5; // rsi
  unsigned int CurrentProcessSessionId; // eax
  unsigned int v7; // ebx
  struct _KTHREAD *CurrentThread; // rdi
  __int64 v9; // rcx
  PACCESS_TOKEN v10; // rax
  void *v11; // rsi
  unsigned int ThreadSessionId; // eax
  NTSTATUS InformationToken; // ebx
  NTSTATUS v15; // ebx
  unsigned int v16; // edi
  KIRQL v17; // al
  unsigned int v18; // ebx
  PVOID TokenInformation[2]; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+60h] [rbp+18h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+68h] [rbp+20h] BYREF

  ThreadProperty = (unsigned int *)PsGetThreadProperty(Thread, 0x6D43644Eu, 0);
  if ( ThreadProperty )
  {
    v18 = *ThreadProperty;
    ObfDereferenceObject(ThreadProperty);
    if ( v18 )
      return v18;
  }
  ImpersonationLevel = SecurityAnonymous;
  TokenInformation[0] = 0;
  CopyOnOpen = 0;
  EffectiveOnly = 0;
  if ( KeGetCurrentIrql() >= 2u )
  {
    CurrentProcessSessionId = PsGetCurrentProcessSessionId(v3);
    goto LABEL_5;
  }
  v4 = PsReferenceImpersonationToken(Thread, &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  v5 = v4;
  if ( !v4
    || (InformationToken = SeQueryInformationToken(v4, TokenSessionId, TokenInformation),
        PsDereferenceImpersonationToken(v5),
        InformationToken < 0) )
  {
    CurrentProcessSessionId = PsGetThreadSessionId(Thread);
LABEL_5:
    v7 = CurrentProcessSessionId;
    goto LABEL_6;
  }
  v7 = (unsigned int)TokenInformation[0];
LABEL_6:
  if ( v7 != -1 )
    goto LABEL_11;
  CurrentThread = KeGetCurrentThread();
  CopyOnOpen = 0;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityAnonymous;
  TokenInformation[0] = 0;
  if ( KeGetCurrentIrql() >= 2u )
  {
    ThreadSessionId = PsGetCurrentProcessSessionId(v9);
    goto LABEL_10;
  }
  v10 = PsReferenceImpersonationToken(CurrentThread, &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  v11 = v10;
  if ( !v10
    || (v15 = SeQueryInformationToken(v10, TokenSessionId, TokenInformation),
        PsDereferenceImpersonationToken(v11),
        v15 < 0) )
  {
    ThreadSessionId = PsGetThreadSessionId(CurrentThread);
LABEL_10:
    v7 = ThreadSessionId;
    goto LABEL_11;
  }
  v7 = (unsigned int)TokenInformation[0];
LABEL_11:
  if ( v7 >= dword_140122898 )
    return 1;
  v16 = 0;
  v17 = KeAcquireSpinLockRaiseToDpc(&qword_1401228E0);
  if ( v7 < dword_140122898 )
    v16 = *((_DWORD *)qword_1401228E8 + 6 * v7);
  KeReleaseSpinLock(&qword_1401228E0, v17);
  if ( !v16 )
    return 1;
  return v16;
}

```

## disassembly

```asm
0x140050630  push    rbx
0x140050632  push    rdi
0x140050633  sub     rsp, 38h
0x140050637  xor     r8d, r8d; Flags
0x14005063a  mov     edx, 6D43644Eh; Key
0x14005063f  mov     rdi, rcx
0x140050642  call    cs:__imp_PsGetThreadProperty
0x140050649  nop     dword ptr [rax+rax+00h]
0x14005064e  test    rax, rax
0x140050651  jnz     loc_140050841
0x140050657  mov     [rsp+48h+arg_0], rbp
0x14005065c  xor     ebp, ebp
0x14005065e  mov     [rsp+48h+ImpersonationLevel], ebp
0x140050662  mov     [rsp+48h+TokenInformation], rbp
0x140050667  mov     [rsp+48h+var_18], rsi
0x14005066c  mov     [rsp+48h+CopyOnOpen], 0
0x140050671  mov     [rsp+48h+EffectiveOnly], 0
0x140050676  call    cs:__imp_KeGetCurrentIrql
0x14005067d  nop     dword ptr [rax+rax+00h]
0x140050682  cmp     al, 2
0x140050684  jnb     loc_14005081F
0x14005068a  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x14005068f  mov     rcx, rdi; Thread
0x140050692  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140050697  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x14005069c  call    cs:__imp_PsReferenceImpersonationToken
0x1400506a3  nop     dword ptr [rax+rax+00h]
0x1400506a8  mov     rsi, rax
0x1400506ab  test    rax, rax
0x1400506ae  jnz     loc_140050754
0x1400506b4  mov     rcx, rdi
0x1400506b7  call    cs:__imp_PsGetThreadSessionId
0x1400506be  nop     dword ptr [rax+rax+00h]
0x1400506c3  mov     ebx, eax
0x1400506c5  cmp     ebx, 0FFFFFFFFh
0x1400506c8  jnz     short loc_140050731
0x1400506ca  mov     rdi, gs:188h
0x1400506d3  mov     [rsp+48h+CopyOnOpen], bpl
0x1400506d8  mov     [rsp+48h+EffectiveOnly], bpl
0x1400506dd  mov     [rsp+48h+ImpersonationLevel], ebp
0x1400506e1  mov     [rsp+48h+TokenInformation], rbp
0x1400506e6  call    cs:__imp_KeGetCurrentIrql
0x1400506ed  nop     dword ptr [rax+rax+00h]
0x1400506f2  cmp     al, 2
0x1400506f4  jnb     loc_140050830
0x1400506fa  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x1400506ff  mov     rcx, rdi; Thread
0x140050702  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140050707  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x14005070c  call    cs:__imp_PsReferenceImpersonationToken
0x140050713  nop     dword ptr [rax+rax+00h]
0x140050718  mov     rsi, rax
0x14005071b  test    rax, rax
0x14005071e  jnz     short loc_14005078F
0x140050720  mov     rcx, rdi
0x140050723  call    cs:__imp_PsGetThreadSessionId
0x14005072a  nop     dword ptr [rax+rax+00h]
0x14005072f  mov     ebx, eax
0x140050731  cmp     ebx, cs:dword_140122898
0x140050737  mov     rsi, [rsp+48h+var_18]
0x14005073c  jb      loc_1400507CA
0x140050742  mov     eax, 1
0x140050747  mov     rbp, [rsp+48h+arg_0]
0x14005074c  add     rsp, 38h
0x140050750  pop     rdi
0x140050751  pop     rbx
0x140050752  retn
0x140050754  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140050759  mov     edx, 0Ch; TokenInformationClass
0x14005075e  mov     rcx, rsi; Token
0x140050761  call    cs:__imp_SeQueryInformationToken
0x140050768  nop     dword ptr [rax+rax+00h]
0x14005076d  mov     rcx, rsi; ImpersonationToken
0x140050770  mov     ebx, eax
0x140050772  call    cs:__imp_PsDereferenceImpersonationToken
0x140050779  nop     dword ptr [rax+rax+00h]
0x14005077e  test    ebx, ebx
0x140050780  js      loc_1400506B4
0x140050786  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x14005078a  jmp     loc_1400506C5
0x14005078f  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140050794  mov     edx, 0Ch; TokenInformationClass
0x140050799  mov     rcx, rsi; Token
0x14005079c  call    cs:__imp_SeQueryInformationToken
0x1400507a3  nop     dword ptr [rax+rax+00h]
0x1400507a8  mov     rcx, rsi; ImpersonationToken
0x1400507ab  mov     ebx, eax
0x1400507ad  call    cs:__imp_PsDereferenceImpersonationToken
0x1400507b4  nop     dword ptr [rax+rax+00h]
0x1400507b9  test    ebx, ebx
0x1400507bb  js      loc_140050720
0x1400507c1  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x1400507c5  jmp     loc_140050731
0x1400507ca  lea     rcx, qword_1401228E0; SpinLock
0x1400507d1  mov     edi, ebp
0x1400507d3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400507da  nop     dword ptr [rax+rax+00h]
0x1400507df  cmp     ebx, cs:dword_140122898
0x1400507e5  jnb     short loc_1400507F8
0x1400507e7  mov     edx, ebx
0x1400507e9  lea     r8, [rdx+rdx*2]
0x1400507ed  mov     rdx, cs:qword_1401228E8
0x1400507f4  mov     edi, [rdx+r8*8]
0x1400507f8  movzx   edx, al; NewIrql
0x1400507fb  lea     rcx, qword_1401228E0; SpinLock
0x140050802  call    cs:__imp_KeReleaseSpinLock
0x140050809  nop     dword ptr [rax+rax+00h]
0x14005080e  mov     eax, 1
0x140050813  test    edi, edi
0x140050815  cmovz   edi, eax
0x140050818  mov     eax, edi
0x14005081a  jmp     loc_140050747
0x14005081f  call    cs:__imp_PsGetCurrentProcessSessionId
0x140050826  nop     dword ptr [rax+rax+00h]
0x14005082b  jmp     loc_1400506C3
0x140050830  call    cs:__imp_PsGetCurrentProcessSessionId
0x140050837  nop     dword ptr [rax+rax+00h]
0x14005083c  jmp     loc_14005072F
0x140050841  mov     ebx, [rax]
0x140050843  mov     rcx, rax; Object
0x140050846  call    cs:__imp_ObfDereferenceObject
0x14005084d  nop     dword ptr [rax+rax+00h]
0x140050852  test    ebx, ebx
0x140050854  jz      loc_140050657
0x14005085a  mov     eax, ebx
0x14005085c  add     rsp, 38h
0x140050860  pop     rdi
0x140050861  pop     rbx
0x140050862  retn
```
