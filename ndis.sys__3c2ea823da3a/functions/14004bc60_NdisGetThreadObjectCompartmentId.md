# NdisGetThreadObjectCompartmentId

- ea: `0x14004bc60`
- end: `0x14004be94`
- name: `NdisGetThreadObjectCompartmentId`
- size: `564`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14004bc60`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14004bca6`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004bd16`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004bca6`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004bd16`
- `ntoskrnl!ObfDereferenceObject` at `0x14004be76`
- `ntoskrnl!ObfDereferenceObject` at `0x14004be76`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004be32`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004be32`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004be03`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004be03`
- `ntoskrnl!SeQueryInformationToken` at `0x14004bd91`
- `ntoskrnl!SeQueryInformationToken` at `0x14004bdcc`
- `ntoskrnl!SeQueryInformationToken` at `0x14004bd91`
- `ntoskrnl!SeQueryInformationToken` at `0x14004bdcc`
- `ntoskrnl!PsGetThreadProperty` at `0x14004bc72`
- `ntoskrnl!PsGetThreadProperty` at `0x14004bc72`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004be4f`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004be60`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004be4f`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004be60`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004bccc`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004bd3c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004bccc`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004bd3c`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004bce7`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004bd53`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004bce7`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004bd53`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004bda2`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004bddd`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004bda2`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004bddd`

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
  if ( v7 >= dword_14011C898 )
    return 1;
  v16 = 0;
  v17 = KeAcquireSpinLockRaiseToDpc(&qword_14011C8E0);
  if ( v7 < dword_14011C898 )
    v16 = *((_DWORD *)qword_14011C8E8 + 6 * v7);
  KeReleaseSpinLock(&qword_14011C8E0, v17);
  if ( !v16 )
    return 1;
  return v16;
}

```

## disassembly

```asm
0x14004bc60  push    rbx
0x14004bc62  push    rdi
0x14004bc63  sub     rsp, 38h
0x14004bc67  xor     r8d, r8d; Flags
0x14004bc6a  mov     edx, 6D43644Eh; Key
0x14004bc6f  mov     rdi, rcx
0x14004bc72  call    cs:__imp_PsGetThreadProperty
0x14004bc79  nop     dword ptr [rax+rax+00h]
0x14004bc7e  test    rax, rax
0x14004bc81  jnz     loc_14004BE71
0x14004bc87  mov     [rsp+48h+arg_0], rbp
0x14004bc8c  xor     ebp, ebp
0x14004bc8e  mov     [rsp+48h+ImpersonationLevel], ebp
0x14004bc92  mov     [rsp+48h+TokenInformation], rbp
0x14004bc97  mov     [rsp+48h+var_18], rsi
0x14004bc9c  mov     [rsp+48h+CopyOnOpen], 0
0x14004bca1  mov     [rsp+48h+EffectiveOnly], 0
0x14004bca6  call    cs:__imp_KeGetCurrentIrql
0x14004bcad  nop     dword ptr [rax+rax+00h]
0x14004bcb2  cmp     al, 2
0x14004bcb4  jnb     loc_14004BE4F
0x14004bcba  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x14004bcbf  mov     rcx, rdi; Thread
0x14004bcc2  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x14004bcc7  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x14004bccc  call    cs:__imp_PsReferenceImpersonationToken
0x14004bcd3  nop     dword ptr [rax+rax+00h]
0x14004bcd8  mov     rsi, rax
0x14004bcdb  test    rax, rax
0x14004bcde  jnz     loc_14004BD84
0x14004bce4  mov     rcx, rdi
0x14004bce7  call    cs:__imp_PsGetThreadSessionId
0x14004bcee  nop     dword ptr [rax+rax+00h]
0x14004bcf3  mov     ebx, eax
0x14004bcf5  cmp     ebx, 0FFFFFFFFh
0x14004bcf8  jnz     short loc_14004BD61
0x14004bcfa  mov     rdi, gs:188h
0x14004bd03  mov     [rsp+48h+CopyOnOpen], bpl
0x14004bd08  mov     [rsp+48h+EffectiveOnly], bpl
0x14004bd0d  mov     [rsp+48h+ImpersonationLevel], ebp
0x14004bd11  mov     [rsp+48h+TokenInformation], rbp
0x14004bd16  call    cs:__imp_KeGetCurrentIrql
0x14004bd1d  nop     dword ptr [rax+rax+00h]
0x14004bd22  cmp     al, 2
0x14004bd24  jnb     loc_14004BE60
0x14004bd2a  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x14004bd2f  mov     rcx, rdi; Thread
0x14004bd32  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x14004bd37  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x14004bd3c  call    cs:__imp_PsReferenceImpersonationToken
0x14004bd43  nop     dword ptr [rax+rax+00h]
0x14004bd48  mov     rsi, rax
0x14004bd4b  test    rax, rax
0x14004bd4e  jnz     short loc_14004BDBF
0x14004bd50  mov     rcx, rdi
0x14004bd53  call    cs:__imp_PsGetThreadSessionId
0x14004bd5a  nop     dword ptr [rax+rax+00h]
0x14004bd5f  mov     ebx, eax
0x14004bd61  cmp     ebx, cs:dword_14011C898
0x14004bd67  mov     rsi, [rsp+48h+var_18]
0x14004bd6c  jb      loc_14004BDFA
0x14004bd72  mov     eax, 1
0x14004bd77  mov     rbp, [rsp+48h+arg_0]
0x14004bd7c  add     rsp, 38h
0x14004bd80  pop     rdi
0x14004bd81  pop     rbx
0x14004bd82  retn
0x14004bd84  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14004bd89  mov     edx, 0Ch; TokenInformationClass
0x14004bd8e  mov     rcx, rsi; Token
0x14004bd91  call    cs:__imp_SeQueryInformationToken
0x14004bd98  nop     dword ptr [rax+rax+00h]
0x14004bd9d  mov     rcx, rsi; ImpersonationToken
0x14004bda0  mov     ebx, eax
0x14004bda2  call    cs:__imp_PsDereferenceImpersonationToken
0x14004bda9  nop     dword ptr [rax+rax+00h]
0x14004bdae  test    ebx, ebx
0x14004bdb0  js      loc_14004BCE4
0x14004bdb6  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x14004bdba  jmp     loc_14004BCF5
0x14004bdbf  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14004bdc4  mov     edx, 0Ch; TokenInformationClass
0x14004bdc9  mov     rcx, rsi; Token
0x14004bdcc  call    cs:__imp_SeQueryInformationToken
0x14004bdd3  nop     dword ptr [rax+rax+00h]
0x14004bdd8  mov     rcx, rsi; ImpersonationToken
0x14004bddb  mov     ebx, eax
0x14004bddd  call    cs:__imp_PsDereferenceImpersonationToken
0x14004bde4  nop     dword ptr [rax+rax+00h]
0x14004bde9  test    ebx, ebx
0x14004bdeb  js      loc_14004BD50
0x14004bdf1  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x14004bdf5  jmp     loc_14004BD61
0x14004bdfa  lea     rcx, qword_14011C8E0; SpinLock
0x14004be01  mov     edi, ebp
0x14004be03  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004be0a  nop     dword ptr [rax+rax+00h]
0x14004be0f  cmp     ebx, cs:dword_14011C898
0x14004be15  jnb     short loc_14004BE28
0x14004be17  mov     edx, ebx
0x14004be19  lea     r8, [rdx+rdx*2]
0x14004be1d  mov     rdx, cs:qword_14011C8E8
0x14004be24  mov     edi, [rdx+r8*8]
0x14004be28  movzx   edx, al; NewIrql
0x14004be2b  lea     rcx, qword_14011C8E0; SpinLock
0x14004be32  call    cs:__imp_KeReleaseSpinLock
0x14004be39  nop     dword ptr [rax+rax+00h]
0x14004be3e  mov     eax, 1
0x14004be43  test    edi, edi
0x14004be45  cmovz   edi, eax
0x14004be48  mov     eax, edi
0x14004be4a  jmp     loc_14004BD77
0x14004be4f  call    cs:__imp_PsGetCurrentProcessSessionId
0x14004be56  nop     dword ptr [rax+rax+00h]
0x14004be5b  jmp     loc_14004BCF3
0x14004be60  call    cs:__imp_PsGetCurrentProcessSessionId
0x14004be67  nop     dword ptr [rax+rax+00h]
0x14004be6c  jmp     loc_14004BD5F
0x14004be71  mov     ebx, [rax]
0x14004be73  mov     rcx, rax; Object
0x14004be76  call    cs:__imp_ObfDereferenceObject
0x14004be7d  nop     dword ptr [rax+rax+00h]
0x14004be82  test    ebx, ebx
0x14004be84  jz      loc_14004BC87
0x14004be8a  mov     eax, ebx
0x14004be8c  add     rsp, 38h
0x14004be90  pop     rdi
0x14004be91  pop     rbx
0x14004be92  retn
```
