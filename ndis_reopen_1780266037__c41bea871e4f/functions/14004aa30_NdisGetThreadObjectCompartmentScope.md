# NdisGetThreadObjectCompartmentScope

- ea: `0x14004aa30`
- end: `0x14004ac80`
- name: `NdisGetThreadObjectCompartmentScope`
- size: `592`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14004aa30`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14004aa8e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004aaff`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004aa8e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004aaff`
- `ntoskrnl!ObfDereferenceObject` at `0x14004ac6f`
- `ntoskrnl!ObfDereferenceObject` at `0x14004ac6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004ac20`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004ac20`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004abf1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004abf1`
- `ntoskrnl!SeQueryInformationToken` at `0x14004ab7e`
- `ntoskrnl!SeQueryInformationToken` at `0x14004abb9`
- `ntoskrnl!SeQueryInformationToken` at `0x14004ab7e`
- `ntoskrnl!SeQueryInformationToken` at `0x14004abb9`
- `ntoskrnl!PsGetThreadProperty` at `0x14004aa4e`
- `ntoskrnl!PsGetThreadProperty` at `0x14004aa4e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004ac3d`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004ac4e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004ac3d`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004ac4e`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004aab4`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004ab25`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004aab4`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004ab25`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004aacf`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004ab3c`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004aacf`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004ab3c`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004ab8f`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004abca`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004ab8f`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004abca`

## pseudocode

```c
__int64 __fastcall NdisGetThreadObjectCompartmentScope(PETHREAD Thread, _DWORD *a2, _DWORD *a3)
{
  __int64 result; // rax
  __int64 v7; // rcx
  PACCESS_TOKEN v8; // rax
  void *v9; // rsi
  unsigned int CurrentProcessSessionId; // eax
  unsigned int v11; // ebx
  struct _KTHREAD *CurrentThread; // rsi
  __int64 v13; // rcx
  PACCESS_TOKEN v14; // rax
  void *v15; // rbp
  unsigned int ThreadSessionId; // eax
  NTSTATUS InformationToken; // ebx
  NTSTATUS v18; // ebx
  unsigned int v19; // esi
  KIRQL v20; // al
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+20h] [rbp-28h] BYREF
  PVOID TokenInformation[4]; // [rsp+28h] [rbp-20h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+68h] [rbp+20h] BYREF

  result = (__int64)PsGetThreadProperty(Thread, 0x6D43644Eu, 0);
  if ( result )
  {
    *a3 = *(_DWORD *)result;
    *a2 = *(_DWORD *)(result + 4);
    result = ObfDereferenceObject((PVOID)result);
  }
  else
  {
    *a3 = 0;
    *a2 = 0;
  }
  if ( *a3 )
    return result;
  CopyOnOpen = 0;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityAnonymous;
  TokenInformation[0] = 0;
  if ( KeGetCurrentIrql() >= 2u )
  {
    CurrentProcessSessionId = PsGetCurrentProcessSessionId(v7);
    goto LABEL_7;
  }
  v8 = PsReferenceImpersonationToken(Thread, &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  v9 = v8;
  if ( !v8
    || (InformationToken = SeQueryInformationToken(v8, TokenSessionId, TokenInformation),
        PsDereferenceImpersonationToken(v9),
        InformationToken < 0) )
  {
    CurrentProcessSessionId = PsGetThreadSessionId(Thread);
LABEL_7:
    v11 = CurrentProcessSessionId;
    goto LABEL_8;
  }
  v11 = (unsigned int)TokenInformation[0];
LABEL_8:
  if ( v11 == -1 )
  {
    CurrentThread = KeGetCurrentThread();
    CopyOnOpen = 0;
    EffectiveOnly = 0;
    ImpersonationLevel = SecurityAnonymous;
    TokenInformation[0] = 0;
    if ( KeGetCurrentIrql() >= 2u )
    {
      ThreadSessionId = PsGetCurrentProcessSessionId(v13);
    }
    else
    {
      v14 = PsReferenceImpersonationToken(CurrentThread, &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
      v15 = v14;
      if ( v14 )
      {
        v18 = SeQueryInformationToken(v14, TokenSessionId, TokenInformation);
        PsDereferenceImpersonationToken(v15);
        if ( v18 >= 0 )
        {
          v11 = (unsigned int)TokenInformation[0];
          goto LABEL_13;
        }
      }
      ThreadSessionId = PsGetThreadSessionId(CurrentThread);
    }
    v11 = ThreadSessionId;
  }
LABEL_13:
  if ( v11 < dword_140122898 )
  {
    v19 = 0;
    v20 = KeAcquireSpinLockRaiseToDpc(&qword_1401228E0);
    if ( v11 < dword_140122898 )
      v19 = *((_DWORD *)qword_1401228E8 + 6 * v11);
    KeReleaseSpinLock(&qword_1401228E0, v20);
    if ( !v19 )
      v19 = 1;
    result = v19;
  }
  else
  {
    result = 1;
  }
  *a3 = result;
  return result;
}

```

## disassembly

```asm
0x14004aa30  mov     [rsp+arg_8], rbx
0x14004aa35  push    rbp
0x14004aa36  push    rdi
0x14004aa37  push    r14
0x14004aa39  sub     rsp, 30h
0x14004aa3d  mov     rdi, r8
0x14004aa40  mov     rbx, rdx
0x14004aa43  xor     r8d, r8d; Flags
0x14004aa46  mov     edx, 6D43644Eh; Key
0x14004aa4b  mov     rbp, rcx
0x14004aa4e  call    cs:__imp_PsGetThreadProperty
0x14004aa55  nop     dword ptr [rax+rax+00h]
0x14004aa5a  xor     r14d, r14d
0x14004aa5d  test    rax, rax
0x14004aa60  jnz     loc_14004AC5F
0x14004aa66  mov     [rdi], r14d
0x14004aa69  mov     [rbx], r14d
0x14004aa6c  cmp     [rdi], r14d
0x14004aa6f  jnz     loc_14004AB62
0x14004aa75  mov     [rsp+48h+arg_0], rsi
0x14004aa7a  mov     [rsp+48h+CopyOnOpen], r14b
0x14004aa7f  mov     [rsp+48h+EffectiveOnly], r14b
0x14004aa84  mov     [rsp+48h+ImpersonationLevel], r14d
0x14004aa89  mov     [rsp+48h+TokenInformation], r14
0x14004aa8e  call    cs:__imp_KeGetCurrentIrql
0x14004aa95  nop     dword ptr [rax+rax+00h]
0x14004aa9a  cmp     al, 2
0x14004aa9c  jnb     loc_14004AC3D
0x14004aaa2  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x14004aaa7  mov     rcx, rbp; Thread
0x14004aaaa  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x14004aaaf  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x14004aab4  call    cs:__imp_PsReferenceImpersonationToken
0x14004aabb  nop     dword ptr [rax+rax+00h]
0x14004aac0  mov     rsi, rax
0x14004aac3  test    rax, rax
0x14004aac6  jnz     loc_14004AB71
0x14004aacc  mov     rcx, rbp
0x14004aacf  call    cs:__imp_PsGetThreadSessionId
0x14004aad6  nop     dword ptr [rax+rax+00h]
0x14004aadb  mov     ebx, eax
0x14004aadd  cmp     ebx, 0FFFFFFFFh
0x14004aae0  jnz     short loc_14004AB4A
0x14004aae2  mov     rsi, gs:188h
0x14004aaeb  mov     [rsp+48h+CopyOnOpen], r14b
0x14004aaf0  mov     [rsp+48h+EffectiveOnly], r14b
0x14004aaf5  mov     [rsp+48h+ImpersonationLevel], r14d
0x14004aafa  mov     [rsp+48h+TokenInformation], r14
0x14004aaff  call    cs:__imp_KeGetCurrentIrql
0x14004ab06  nop     dword ptr [rax+rax+00h]
0x14004ab0b  cmp     al, 2
0x14004ab0d  jnb     loc_14004AC4E
0x14004ab13  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x14004ab18  mov     rcx, rsi; Thread
0x14004ab1b  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x14004ab20  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x14004ab25  call    cs:__imp_PsReferenceImpersonationToken
0x14004ab2c  nop     dword ptr [rax+rax+00h]
0x14004ab31  mov     rbp, rax
0x14004ab34  test    rax, rax
0x14004ab37  jnz     short loc_14004ABAC
0x14004ab39  mov     rcx, rsi
0x14004ab3c  call    cs:__imp_PsGetThreadSessionId
0x14004ab43  nop     dword ptr [rax+rax+00h]
0x14004ab48  mov     ebx, eax
0x14004ab4a  cmp     ebx, cs:dword_140122898
0x14004ab50  jb      loc_14004ABE7
0x14004ab56  mov     eax, 1
0x14004ab5b  mov     rsi, [rsp+48h+arg_0]
0x14004ab60  mov     [rdi], eax
0x14004ab62  mov     rbx, [rsp+48h+arg_8]
0x14004ab67  add     rsp, 30h
0x14004ab6b  pop     r14
0x14004ab6d  pop     rdi
0x14004ab6e  pop     rbp
0x14004ab6f  retn
0x14004ab71  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14004ab76  mov     edx, 0Ch; TokenInformationClass
0x14004ab7b  mov     rcx, rsi; Token
0x14004ab7e  call    cs:__imp_SeQueryInformationToken
0x14004ab85  nop     dword ptr [rax+rax+00h]
0x14004ab8a  mov     rcx, rsi; ImpersonationToken
0x14004ab8d  mov     ebx, eax
0x14004ab8f  call    cs:__imp_PsDereferenceImpersonationToken
0x14004ab96  nop     dword ptr [rax+rax+00h]
0x14004ab9b  test    ebx, ebx
0x14004ab9d  js      loc_14004AACC
0x14004aba3  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x14004aba7  jmp     loc_14004AADD
0x14004abac  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14004abb1  mov     edx, 0Ch; TokenInformationClass
0x14004abb6  mov     rcx, rbp; Token
0x14004abb9  call    cs:__imp_SeQueryInformationToken
0x14004abc0  nop     dword ptr [rax+rax+00h]
0x14004abc5  mov     rcx, rbp; ImpersonationToken
0x14004abc8  mov     ebx, eax
0x14004abca  call    cs:__imp_PsDereferenceImpersonationToken
0x14004abd1  nop     dword ptr [rax+rax+00h]
0x14004abd6  test    ebx, ebx
0x14004abd8  js      loc_14004AB39
0x14004abde  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x14004abe2  jmp     loc_14004AB4A
0x14004abe7  lea     rcx, qword_1401228E0; SpinLock
0x14004abee  mov     esi, r14d
0x14004abf1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004abf8  nop     dword ptr [rax+rax+00h]
0x14004abfd  cmp     ebx, cs:dword_140122898
0x14004ac03  jnb     short loc_14004AC16
0x14004ac05  mov     edx, ebx
0x14004ac07  lea     r8, [rdx+rdx*2]
0x14004ac0b  mov     rdx, cs:qword_1401228E8
0x14004ac12  mov     esi, [rdx+r8*8]
0x14004ac16  movzx   edx, al; NewIrql
0x14004ac19  lea     rcx, qword_1401228E0; SpinLock
0x14004ac20  call    cs:__imp_KeReleaseSpinLock
0x14004ac27  nop     dword ptr [rax+rax+00h]
0x14004ac2c  mov     eax, 1
0x14004ac31  test    esi, esi
0x14004ac33  cmovz   esi, eax
0x14004ac36  mov     eax, esi
0x14004ac38  jmp     loc_14004AB5B
0x14004ac3d  call    cs:__imp_PsGetCurrentProcessSessionId
0x14004ac44  nop     dword ptr [rax+rax+00h]
0x14004ac49  jmp     loc_14004AADB
0x14004ac4e  call    cs:__imp_PsGetCurrentProcessSessionId
0x14004ac55  nop     dword ptr [rax+rax+00h]
0x14004ac5a  jmp     loc_14004AB48
0x14004ac5f  mov     r9d, [rax]
0x14004ac62  mov     rcx, rax; Object
0x14004ac65  mov     [rdi], r9d
0x14004ac68  mov     r8d, [rax+4]
0x14004ac6c  mov     [rbx], r8d
0x14004ac6f  call    cs:__imp_ObfDereferenceObject
0x14004ac76  nop     dword ptr [rax+rax+00h]
0x14004ac7b  jmp     loc_14004AA6C
```
