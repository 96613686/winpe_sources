# ndisCmGetThreadState

- ea: `0x140043c50`
- end: `0x140043ea0`
- name: `ndisCmGetThreadState`
- size: `592`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400436b0`
- `0x1400cb648`

## callees

- `0x140043c50`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140043cae`
- `ntoskrnl!KeGetCurrentIrql` at `0x140043d1f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140043cae`
- `ntoskrnl!KeGetCurrentIrql` at `0x140043d1f`
- `ntoskrnl!ObfDereferenceObject` at `0x140043e8f`
- `ntoskrnl!ObfDereferenceObject` at `0x140043e8f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140043e40`
- `ntoskrnl!KeReleaseSpinLock` at `0x140043e40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140043e11`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140043e11`
- `ntoskrnl!SeQueryInformationToken` at `0x140043d9e`
- `ntoskrnl!SeQueryInformationToken` at `0x140043dd9`
- `ntoskrnl!SeQueryInformationToken` at `0x140043d9e`
- `ntoskrnl!SeQueryInformationToken` at `0x140043dd9`
- `ntoskrnl!PsGetThreadProperty` at `0x140043c6e`
- `ntoskrnl!PsGetThreadProperty` at `0x140043c6e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140043e5d`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140043e6e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140043e5d`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140043e6e`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140043cd4`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140043d45`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140043cd4`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140043d45`
- `ntoskrnl!PsGetThreadSessionId` at `0x140043cef`
- `ntoskrnl!PsGetThreadSessionId` at `0x140043d5c`
- `ntoskrnl!PsGetThreadSessionId` at `0x140043cef`
- `ntoskrnl!PsGetThreadSessionId` at `0x140043d5c`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140043daf`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140043dea`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140043daf`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140043dea`

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
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x140043c50  mov     [rsp+arg_10], rbx
0x140043c55  push    rbp
0x140043c56  push    rdi
0x140043c57  push    r14
0x140043c59  sub     rsp, 30h
0x140043c5d  mov     rbx, r8
0x140043c60  mov     rdi, rdx
0x140043c63  xor     r8d, r8d; Flags
0x140043c66  mov     edx, 6D43644Eh; Key
0x140043c6b  mov     rbp, rcx
0x140043c6e  call    cs:__imp_PsGetThreadProperty
0x140043c75  nop     dword ptr [rax+rax+00h]
0x140043c7a  xor     r14d, r14d
0x140043c7d  test    rax, rax
0x140043c80  jnz     loc_140043E7F
0x140043c86  mov     [rdi], r14d
0x140043c89  mov     [rbx], r14d
0x140043c8c  cmp     [rdi], r14d
0x140043c8f  jnz     loc_140043D82
0x140043c95  mov     [rsp+48h+arg_0], rsi
0x140043c9a  mov     [rsp+48h+CopyOnOpen], r14b
0x140043c9f  mov     [rsp+48h+EffectiveOnly], r14b
0x140043ca4  mov     [rsp+48h+ImpersonationLevel], r14d
0x140043ca9  mov     [rsp+48h+TokenInformation], r14
0x140043cae  call    cs:__imp_KeGetCurrentIrql
0x140043cb5  nop     dword ptr [rax+rax+00h]
0x140043cba  cmp     al, 2
0x140043cbc  jnb     loc_140043E5D
0x140043cc2  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x140043cc7  mov     rcx, rbp; Thread
0x140043cca  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140043ccf  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x140043cd4  call    cs:__imp_PsReferenceImpersonationToken
0x140043cdb  nop     dword ptr [rax+rax+00h]
0x140043ce0  mov     rsi, rax
0x140043ce3  test    rax, rax
0x140043ce6  jnz     loc_140043D91
0x140043cec  mov     rcx, rbp
0x140043cef  call    cs:__imp_PsGetThreadSessionId
0x140043cf6  nop     dword ptr [rax+rax+00h]
0x140043cfb  mov     ebx, eax
0x140043cfd  cmp     ebx, 0FFFFFFFFh
0x140043d00  jnz     short loc_140043D6A
0x140043d02  mov     rsi, gs:188h
0x140043d0b  mov     [rsp+48h+CopyOnOpen], r14b
0x140043d10  mov     [rsp+48h+EffectiveOnly], r14b
0x140043d15  mov     [rsp+48h+ImpersonationLevel], r14d
0x140043d1a  mov     [rsp+48h+TokenInformation], r14
0x140043d1f  call    cs:__imp_KeGetCurrentIrql
0x140043d26  nop     dword ptr [rax+rax+00h]
0x140043d2b  cmp     al, 2
0x140043d2d  jnb     loc_140043E6E
0x140043d33  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x140043d38  mov     rcx, rsi; Thread
0x140043d3b  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140043d40  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x140043d45  call    cs:__imp_PsReferenceImpersonationToken
0x140043d4c  nop     dword ptr [rax+rax+00h]
0x140043d51  mov     rbp, rax
0x140043d54  test    rax, rax
0x140043d57  jnz     short loc_140043DCC
0x140043d59  mov     rcx, rsi
0x140043d5c  call    cs:__imp_PsGetThreadSessionId
0x140043d63  nop     dword ptr [rax+rax+00h]
0x140043d68  mov     ebx, eax
0x140043d6a  cmp     ebx, cs:dword_14011C898
0x140043d70  jb      loc_140043E07
0x140043d76  mov     eax, 1
0x140043d7b  mov     rsi, [rsp+48h+arg_0]
0x140043d80  mov     [rdi], eax
0x140043d82  mov     rbx, [rsp+48h+arg_10]
0x140043d87  add     rsp, 30h
0x140043d8b  pop     r14
0x140043d8d  pop     rdi
0x140043d8e  pop     rbp
0x140043d8f  retn
0x140043d91  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140043d96  mov     edx, 0Ch; TokenInformationClass
0x140043d9b  mov     rcx, rsi; Token
0x140043d9e  call    cs:__imp_SeQueryInformationToken
0x140043da5  nop     dword ptr [rax+rax+00h]
0x140043daa  mov     rcx, rsi; ImpersonationToken
0x140043dad  mov     ebx, eax
0x140043daf  call    cs:__imp_PsDereferenceImpersonationToken
0x140043db6  nop     dword ptr [rax+rax+00h]
0x140043dbb  test    ebx, ebx
0x140043dbd  js      loc_140043CEC
0x140043dc3  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x140043dc7  jmp     loc_140043CFD
0x140043dcc  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140043dd1  mov     edx, 0Ch; TokenInformationClass
0x140043dd6  mov     rcx, rbp; Token
0x140043dd9  call    cs:__imp_SeQueryInformationToken
0x140043de0  nop     dword ptr [rax+rax+00h]
0x140043de5  mov     rcx, rbp; ImpersonationToken
0x140043de8  mov     ebx, eax
0x140043dea  call    cs:__imp_PsDereferenceImpersonationToken
0x140043df1  nop     dword ptr [rax+rax+00h]
0x140043df6  test    ebx, ebx
0x140043df8  js      loc_140043D59
0x140043dfe  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x140043e02  jmp     loc_140043D6A
0x140043e07  lea     rcx, qword_14011C8E0; SpinLock
0x140043e0e  mov     esi, r14d
0x140043e11  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140043e18  nop     dword ptr [rax+rax+00h]
0x140043e1d  cmp     ebx, cs:dword_14011C898
0x140043e23  jnb     short loc_140043E36
0x140043e25  mov     edx, ebx
0x140043e27  lea     r8, [rdx+rdx*2]
0x140043e2b  mov     rdx, cs:qword_14011C8E8
0x140043e32  mov     esi, [rdx+r8*8]
0x140043e36  movzx   edx, al; NewIrql
0x140043e39  lea     rcx, qword_14011C8E0; SpinLock
0x140043e40  call    cs:__imp_KeReleaseSpinLock
0x140043e47  nop     dword ptr [rax+rax+00h]
0x140043e4c  mov     eax, 1
0x140043e51  test    esi, esi
0x140043e53  cmovz   esi, eax
0x140043e56  mov     eax, esi
0x140043e58  jmp     loc_140043D7B
0x140043e5d  call    cs:__imp_PsGetCurrentProcessSessionId
0x140043e64  nop     dword ptr [rax+rax+00h]
0x140043e69  jmp     loc_140043CFB
0x140043e6e  call    cs:__imp_PsGetCurrentProcessSessionId
0x140043e75  nop     dword ptr [rax+rax+00h]
0x140043e7a  jmp     loc_140043D68
0x140043e7f  mov     r9d, [rax]
0x140043e82  mov     rcx, rax; Object
0x140043e85  mov     [rdi], r9d
0x140043e88  mov     r8d, [rax+4]
0x140043e8c  mov     [rbx], r8d
0x140043e8f  call    cs:__imp_ObfDereferenceObject
0x140043e96  nop     dword ptr [rax+rax+00h]
0x140043e9b  jmp     loc_140043C8C
```
