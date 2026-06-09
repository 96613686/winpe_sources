# NdisGetThreadObjectCompartmentScope

- ea: `0x140045f30`
- end: `0x140046180`
- name: `NdisGetThreadObjectCompartmentScope`
- size: `592`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140045f30`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140045f8e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140045fff`
- `ntoskrnl!KeGetCurrentIrql` at `0x140045f8e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140045fff`
- `ntoskrnl!ObfDereferenceObject` at `0x14004616f`
- `ntoskrnl!ObfDereferenceObject` at `0x14004616f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140046120`
- `ntoskrnl!KeReleaseSpinLock` at `0x140046120`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400460f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400460f1`
- `ntoskrnl!SeQueryInformationToken` at `0x14004607e`
- `ntoskrnl!SeQueryInformationToken` at `0x1400460b9`
- `ntoskrnl!SeQueryInformationToken` at `0x14004607e`
- `ntoskrnl!SeQueryInformationToken` at `0x1400460b9`
- `ntoskrnl!PsGetThreadProperty` at `0x140045f4e`
- `ntoskrnl!PsGetThreadProperty` at `0x140045f4e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004613d`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004614e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004613d`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004614e`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140045fb4`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140046025`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140045fb4`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140046025`
- `ntoskrnl!PsGetThreadSessionId` at `0x140045fcf`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004603c`
- `ntoskrnl!PsGetThreadSessionId` at `0x140045fcf`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004603c`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004608f`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400460ca`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004608f`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400460ca`

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
  if ( v11 < dword_14011C898 )
  {
    v19 = 0;
    v20 = KeAcquireSpinLockRaiseToDpc(&qword_14011C8E0);
    if ( v11 < dword_14011C898 )
      v19 = *((_DWORD *)qword_14011C8E8 + 6 * v11);
    KeReleaseSpinLock(&qword_14011C8E0, v20);
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
0x140045f30  mov     [rsp+arg_8], rbx
0x140045f35  push    rbp
0x140045f36  push    rdi
0x140045f37  push    r14
0x140045f39  sub     rsp, 30h
0x140045f3d  mov     rdi, r8
0x140045f40  mov     rbx, rdx
0x140045f43  xor     r8d, r8d; Flags
0x140045f46  mov     edx, 6D43644Eh; Key
0x140045f4b  mov     rbp, rcx
0x140045f4e  call    cs:__imp_PsGetThreadProperty
0x140045f55  nop     dword ptr [rax+rax+00h]
0x140045f5a  xor     r14d, r14d
0x140045f5d  test    rax, rax
0x140045f60  jnz     loc_14004615F
0x140045f66  mov     [rdi], r14d
0x140045f69  mov     [rbx], r14d
0x140045f6c  cmp     [rdi], r14d
0x140045f6f  jnz     loc_140046062
0x140045f75  mov     [rsp+48h+arg_0], rsi
0x140045f7a  mov     [rsp+48h+CopyOnOpen], r14b
0x140045f7f  mov     [rsp+48h+EffectiveOnly], r14b
0x140045f84  mov     [rsp+48h+ImpersonationLevel], r14d
0x140045f89  mov     [rsp+48h+TokenInformation], r14
0x140045f8e  call    cs:__imp_KeGetCurrentIrql
0x140045f95  nop     dword ptr [rax+rax+00h]
0x140045f9a  cmp     al, 2
0x140045f9c  jnb     loc_14004613D
0x140045fa2  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x140045fa7  mov     rcx, rbp; Thread
0x140045faa  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140045faf  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x140045fb4  call    cs:__imp_PsReferenceImpersonationToken
0x140045fbb  nop     dword ptr [rax+rax+00h]
0x140045fc0  mov     rsi, rax
0x140045fc3  test    rax, rax
0x140045fc6  jnz     loc_140046071
0x140045fcc  mov     rcx, rbp
0x140045fcf  call    cs:__imp_PsGetThreadSessionId
0x140045fd6  nop     dword ptr [rax+rax+00h]
0x140045fdb  mov     ebx, eax
0x140045fdd  cmp     ebx, 0FFFFFFFFh
0x140045fe0  jnz     short loc_14004604A
0x140045fe2  mov     rsi, gs:188h
0x140045feb  mov     [rsp+48h+CopyOnOpen], r14b
0x140045ff0  mov     [rsp+48h+EffectiveOnly], r14b
0x140045ff5  mov     [rsp+48h+ImpersonationLevel], r14d
0x140045ffa  mov     [rsp+48h+TokenInformation], r14
0x140045fff  call    cs:__imp_KeGetCurrentIrql
0x140046006  nop     dword ptr [rax+rax+00h]
0x14004600b  cmp     al, 2
0x14004600d  jnb     loc_14004614E
0x140046013  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x140046018  mov     rcx, rsi; Thread
0x14004601b  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140046020  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x140046025  call    cs:__imp_PsReferenceImpersonationToken
0x14004602c  nop     dword ptr [rax+rax+00h]
0x140046031  mov     rbp, rax
0x140046034  test    rax, rax
0x140046037  jnz     short loc_1400460AC
0x140046039  mov     rcx, rsi
0x14004603c  call    cs:__imp_PsGetThreadSessionId
0x140046043  nop     dword ptr [rax+rax+00h]
0x140046048  mov     ebx, eax
0x14004604a  cmp     ebx, cs:dword_14011C898
0x140046050  jb      loc_1400460E7
0x140046056  mov     eax, 1
0x14004605b  mov     rsi, [rsp+48h+arg_0]
0x140046060  mov     [rdi], eax
0x140046062  mov     rbx, [rsp+48h+arg_8]
0x140046067  add     rsp, 30h
0x14004606b  pop     r14
0x14004606d  pop     rdi
0x14004606e  pop     rbp
0x14004606f  retn
0x140046071  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140046076  mov     edx, 0Ch; TokenInformationClass
0x14004607b  mov     rcx, rsi; Token
0x14004607e  call    cs:__imp_SeQueryInformationToken
0x140046085  nop     dword ptr [rax+rax+00h]
0x14004608a  mov     rcx, rsi; ImpersonationToken
0x14004608d  mov     ebx, eax
0x14004608f  call    cs:__imp_PsDereferenceImpersonationToken
0x140046096  nop     dword ptr [rax+rax+00h]
0x14004609b  test    ebx, ebx
0x14004609d  js      loc_140045FCC
0x1400460a3  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x1400460a7  jmp     loc_140045FDD
0x1400460ac  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x1400460b1  mov     edx, 0Ch; TokenInformationClass
0x1400460b6  mov     rcx, rbp; Token
0x1400460b9  call    cs:__imp_SeQueryInformationToken
0x1400460c0  nop     dword ptr [rax+rax+00h]
0x1400460c5  mov     rcx, rbp; ImpersonationToken
0x1400460c8  mov     ebx, eax
0x1400460ca  call    cs:__imp_PsDereferenceImpersonationToken
0x1400460d1  nop     dword ptr [rax+rax+00h]
0x1400460d6  test    ebx, ebx
0x1400460d8  js      loc_140046039
0x1400460de  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x1400460e2  jmp     loc_14004604A
0x1400460e7  lea     rcx, qword_14011C8E0; SpinLock
0x1400460ee  mov     esi, r14d
0x1400460f1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400460f8  nop     dword ptr [rax+rax+00h]
0x1400460fd  cmp     ebx, cs:dword_14011C898
0x140046103  jnb     short loc_140046116
0x140046105  mov     edx, ebx
0x140046107  lea     r8, [rdx+rdx*2]
0x14004610b  mov     rdx, cs:qword_14011C8E8
0x140046112  mov     esi, [rdx+r8*8]
0x140046116  movzx   edx, al; NewIrql
0x140046119  lea     rcx, qword_14011C8E0; SpinLock
0x140046120  call    cs:__imp_KeReleaseSpinLock
0x140046127  nop     dword ptr [rax+rax+00h]
0x14004612c  mov     eax, 1
0x140046131  test    esi, esi
0x140046133  cmovz   esi, eax
0x140046136  mov     eax, esi
0x140046138  jmp     loc_14004605B
0x14004613d  call    cs:__imp_PsGetCurrentProcessSessionId
0x140046144  nop     dword ptr [rax+rax+00h]
0x140046149  jmp     loc_140045FDB
0x14004614e  call    cs:__imp_PsGetCurrentProcessSessionId
0x140046155  nop     dword ptr [rax+rax+00h]
0x14004615a  jmp     loc_140046048
0x14004615f  mov     r9d, [rax]
0x140046162  mov     rcx, rax; Object
0x140046165  mov     [rdi], r9d
0x140046168  mov     r8d, [rax+4]
0x14004616c  mov     [rbx], r8d
0x14004616f  call    cs:__imp_ObfDereferenceObject
0x140046176  nop     dword ptr [rax+rax+00h]
0x14004617b  jmp     loc_140045F6C
```
