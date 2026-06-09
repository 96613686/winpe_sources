# ndisCmGetThreadSessionId(_ETHREAD *)

- ea: `0x140046190`
- end: `0x140046263`
- name: `?ndisCmGetThreadSessionId@@YAKPEAU_ETHREAD@@@Z`
- size: `211`
- prototype: `unsigned int __fastcall(PETHREAD Thread)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400c9a30`

## callees

- `0x140046190`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400461ae`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400461ae`
- `ntoskrnl!SeQueryInformationToken` at `0x14004621a`
- `ntoskrnl!SeQueryInformationToken` at `0x14004621a`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140046250`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140046250`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400461d9`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400461d9`
- `ntoskrnl!PsGetThreadSessionId` at `0x1400461f0`
- `ntoskrnl!PsGetThreadSessionId` at `0x1400461f0`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004622b`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004622b`

## pseudocode

```c
__int64 __fastcall ndisCmGetThreadSessionId(PETHREAD Thread)
{
  __int64 v2; // rcx
  PACCESS_TOKEN v3; // rax
  void *v4; // rsi
  NTSTATUS v6; // edi
  PVOID TokenInformation; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+60h] [rbp+18h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+68h] [rbp+20h] BYREF

  CopyOnOpen = 0;
  ImpersonationLevel = SecurityAnonymous;
  TokenInformation = 0;
  EffectiveOnly = 0;
  if ( KeGetCurrentIrql() >= 2u )
    return PsGetCurrentProcessSessionId(v2);
  v3 = PsReferenceImpersonationToken(Thread, &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  v4 = v3;
  if ( v3
    && (v6 = SeQueryInformationToken(v3, TokenSessionId, &TokenInformation), PsDereferenceImpersonationToken(v4),
                                                                             v6 >= 0) )
  {
    return (unsigned int)TokenInformation;
  }
  else
  {
    return PsGetThreadSessionId(Thread);
  }
}

```

## disassembly

```asm
0x140046190  push    rbx
0x140046192  sub     rsp, 40h
0x140046196  xor     eax, eax
0x140046198  mov     [rsp+48h+CopyOnOpen], 0
0x14004619d  mov     [rsp+48h+ImpersonationLevel], eax
0x1400461a1  mov     rbx, rcx
0x1400461a4  mov     [rsp+48h+TokenInformation], rax
0x1400461a9  mov     [rsp+48h+EffectiveOnly], 0
0x1400461ae  call    cs:__imp_KeGetCurrentIrql
0x1400461b5  nop     dword ptr [rax+rax+00h]
0x1400461ba  cmp     al, 2
0x1400461bc  jnb     loc_140046250
0x1400461c2  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x1400461c7  mov     [rsp+48h+var_10], rsi
0x1400461cc  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x1400461d1  mov     rcx, rbx; Thread
0x1400461d4  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x1400461d9  call    cs:__imp_PsReferenceImpersonationToken
0x1400461e0  nop     dword ptr [rax+rax+00h]
0x1400461e5  mov     rsi, rax
0x1400461e8  test    rax, rax
0x1400461eb  jnz     short loc_140046208
0x1400461ed  mov     rcx, rbx
0x1400461f0  call    cs:__imp_PsGetThreadSessionId
0x1400461f7  nop     dword ptr [rax+rax+00h]
0x1400461fc  mov     rsi, [rsp+48h+var_10]
0x140046201  add     rsp, 40h
0x140046205  pop     rbx
0x140046206  retn
0x140046208  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14004620d  mov     [rsp+48h+var_18], rdi
0x140046212  mov     edx, 0Ch; TokenInformationClass
0x140046217  mov     rcx, rsi; Token
0x14004621a  call    cs:__imp_SeQueryInformationToken
0x140046221  nop     dword ptr [rax+rax+00h]
0x140046226  mov     rcx, rsi; ImpersonationToken
0x140046229  mov     edi, eax
0x14004622b  call    cs:__imp_PsDereferenceImpersonationToken
0x140046232  nop     dword ptr [rax+rax+00h]
0x140046237  test    edi, edi
0x140046239  mov     rdi, [rsp+48h+var_18]
0x14004623e  js      short loc_1400461ED
0x140046240  mov     eax, dword ptr [rsp+48h+TokenInformation]
0x140046244  mov     rsi, [rsp+48h+var_10]
0x140046249  add     rsp, 40h
0x14004624d  pop     rbx
0x14004624e  retn
0x140046250  call    cs:__imp_PsGetCurrentProcessSessionId
0x140046257  nop     dword ptr [rax+rax+00h]
0x14004625c  add     rsp, 40h
0x140046260  pop     rbx
0x140046261  retn
```
