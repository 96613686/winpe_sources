# ndisCmGetThreadState

- ea: `0x140048750`
- end: `0x1400489a0`
- name: `ndisCmGetThreadState`
- size: `592`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400481b0`
- `0x1400d07f8`

## callees

- `0x140048750`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400487ae`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004881f`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400487ae`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004881f`
- `ntoskrnl!ObfDereferenceObject` at `0x14004898f`
- `ntoskrnl!ObfDereferenceObject` at `0x14004898f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140048940`
- `ntoskrnl!KeReleaseSpinLock` at `0x140048940`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140048911`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140048911`
- `ntoskrnl!SeQueryInformationToken` at `0x14004889e`
- `ntoskrnl!SeQueryInformationToken` at `0x1400488d9`
- `ntoskrnl!SeQueryInformationToken` at `0x14004889e`
- `ntoskrnl!SeQueryInformationToken` at `0x1400488d9`
- `ntoskrnl!PsGetThreadProperty` at `0x14004876e`
- `ntoskrnl!PsGetThreadProperty` at `0x14004876e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004895d`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004896e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004895d`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004896e`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400487d4`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140048845`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400487d4`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140048845`
- `ntoskrnl!PsGetThreadSessionId` at `0x1400487ef`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004885c`
- `ntoskrnl!PsGetThreadSessionId` at `0x1400487ef`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004885c`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400488af`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400488ea`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400488af`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400488ea`

## pseudocode

```c
__int64 __fastcall ndisCmGetThreadState(PETHREAD Thread, _DWORD *a2, _DWORD *a3)
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
  unsigned __int8 EffectiveOnly; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+68h] [rbp+20h] BYREF

  result = (__int64)PsGetThreadProperty(Thread, 0x6D43644Eu, 0);
  if ( result )
  {
    *a2 = *(_DWORD *)result;
    *a3 = *(_DWORD *)(result + 4);
    result = ObfDereferenceObject((PVOID)result);
  }
  else
  {
    *a2 = 0;
    *a3 = 0;
  }
  if ( *a2 )
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
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x140048750  mov     [rsp+arg_10], rbx
0x140048755  push    rbp
0x140048756  push    rdi
0x140048757  push    r14
0x140048759  sub     rsp, 30h
0x14004875d  mov     rbx, r8
0x140048760  mov     rdi, rdx
0x140048763  xor     r8d, r8d; Flags
0x140048766  mov     edx, 6D43644Eh; Key
0x14004876b  mov     rbp, rcx
0x14004876e  call    cs:__imp_PsGetThreadProperty
0x140048775  nop     dword ptr [rax+rax+00h]
0x14004877a  xor     r14d, r14d
0x14004877d  test    rax, rax
0x140048780  jnz     loc_14004897F
0x140048786  mov     [rdi], r14d
0x140048789  mov     [rbx], r14d
0x14004878c  cmp     [rdi], r14d
0x14004878f  jnz     loc_140048882
0x140048795  mov     [rsp+48h+arg_0], rsi
0x14004879a  mov     [rsp+48h+CopyOnOpen], r14b
0x14004879f  mov     [rsp+48h+EffectiveOnly], r14b
0x1400487a4  mov     [rsp+48h+ImpersonationLevel], r14d
0x1400487a9  mov     [rsp+48h+TokenInformation], r14
0x1400487ae  call    cs:__imp_KeGetCurrentIrql
0x1400487b5  nop     dword ptr [rax+rax+00h]
0x1400487ba  cmp     al, 2
0x1400487bc  jnb     loc_14004895D
0x1400487c2  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x1400487c7  mov     rcx, rbp; Thread
0x1400487ca  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x1400487cf  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x1400487d4  call    cs:__imp_PsReferenceImpersonationToken
0x1400487db  nop     dword ptr [rax+rax+00h]
0x1400487e0  mov     rsi, rax
0x1400487e3  test    rax, rax
0x1400487e6  jnz     loc_140048891
0x1400487ec  mov     rcx, rbp
0x1400487ef  call    cs:__imp_PsGetThreadSessionId
0x1400487f6  nop     dword ptr [rax+rax+00h]
0x1400487fb  mov     ebx, eax
0x1400487fd  cmp     ebx, 0FFFFFFFFh
0x140048800  jnz     short loc_14004886A
0x140048802  mov     rsi, gs:188h
0x14004880b  mov     [rsp+48h+CopyOnOpen], r14b
0x140048810  mov     [rsp+48h+EffectiveOnly], r14b
0x140048815  mov     [rsp+48h+ImpersonationLevel], r14d
0x14004881a  mov     [rsp+48h+TokenInformation], r14
0x14004881f  call    cs:__imp_KeGetCurrentIrql
0x140048826  nop     dword ptr [rax+rax+00h]
0x14004882b  cmp     al, 2
0x14004882d  jnb     loc_14004896E
0x140048833  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x140048838  mov     rcx, rsi; Thread
0x14004883b  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140048840  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x140048845  call    cs:__imp_PsReferenceImpersonationToken
0x14004884c  nop     dword ptr [rax+rax+00h]
0x140048851  mov     rbp, rax
0x140048854  test    rax, rax
0x140048857  jnz     short loc_1400488CC
0x140048859  mov     rcx, rsi
0x14004885c  call    cs:__imp_PsGetThreadSessionId
0x140048863  nop     dword ptr [rax+rax+00h]
0x140048868  mov     ebx, eax
0x14004886a  cmp     ebx, cs:dword_140122898
0x140048870  jb      loc_140048907
0x140048876  mov     eax, 1
0x14004887b  mov     rsi, [rsp+48h+arg_0]
0x140048880  mov     [rdi], eax
0x140048882  mov     rbx, [rsp+48h+arg_10]
0x140048887  add     rsp, 30h
0x14004888b  pop     r14
0x14004888d  pop     rdi
0x14004888e  pop     rbp
0x14004888f  retn
0x140048891  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140048896  mov     edx, 0Ch; TokenInformationClass
0x14004889b  mov     rcx, rsi; Token
0x14004889e  call    cs:__imp_SeQueryInformationToken
0x1400488a5  nop     dword ptr [rax+rax+00h]
0x1400488aa  mov     rcx, rsi; ImpersonationToken
0x1400488ad  mov     ebx, eax
0x1400488af  call    cs:__imp_PsDereferenceImpersonationToken
0x1400488b6  nop     dword ptr [rax+rax+00h]
0x1400488bb  test    ebx, ebx
0x1400488bd  js      loc_1400487EC
0x1400488c3  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x1400488c7  jmp     loc_1400487FD
0x1400488cc  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x1400488d1  mov     edx, 0Ch; TokenInformationClass
0x1400488d6  mov     rcx, rbp; Token
0x1400488d9  call    cs:__imp_SeQueryInformationToken
0x1400488e0  nop     dword ptr [rax+rax+00h]
0x1400488e5  mov     rcx, rbp; ImpersonationToken
0x1400488e8  mov     ebx, eax
0x1400488ea  call    cs:__imp_PsDereferenceImpersonationToken
0x1400488f1  nop     dword ptr [rax+rax+00h]
0x1400488f6  test    ebx, ebx
0x1400488f8  js      loc_140048859
0x1400488fe  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x140048902  jmp     loc_14004886A
0x140048907  lea     rcx, qword_1401228E0; SpinLock
0x14004890e  mov     esi, r14d
0x140048911  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140048918  nop     dword ptr [rax+rax+00h]
0x14004891d  cmp     ebx, cs:dword_140122898
0x140048923  jnb     short loc_140048936
0x140048925  mov     edx, ebx
0x140048927  lea     r8, [rdx+rdx*2]
0x14004892b  mov     rdx, cs:qword_1401228E8
0x140048932  mov     esi, [rdx+r8*8]
0x140048936  movzx   edx, al; NewIrql
0x140048939  lea     rcx, qword_1401228E0; SpinLock
0x140048940  call    cs:__imp_KeReleaseSpinLock
0x140048947  nop     dword ptr [rax+rax+00h]
0x14004894c  mov     eax, 1
0x140048951  test    esi, esi
0x140048953  cmovz   esi, eax
0x140048956  mov     eax, esi
0x140048958  jmp     loc_14004887B
0x14004895d  call    cs:__imp_PsGetCurrentProcessSessionId
0x140048964  nop     dword ptr [rax+rax+00h]
0x140048969  jmp     loc_1400487FB
0x14004896e  call    cs:__imp_PsGetCurrentProcessSessionId
0x140048975  nop     dword ptr [rax+rax+00h]
0x14004897a  jmp     loc_140048868
0x14004897f  mov     r9d, [rax]
0x140048982  mov     rcx, rax; Object
0x140048985  mov     [rdi], r9d
0x140048988  mov     r8d, [rax+4]
0x14004898c  mov     [rbx], r8d
0x14004898f  call    cs:__imp_ObfDereferenceObject
0x140048996  nop     dword ptr [rax+rax+00h]
0x14004899b  jmp     loc_14004878C
```
