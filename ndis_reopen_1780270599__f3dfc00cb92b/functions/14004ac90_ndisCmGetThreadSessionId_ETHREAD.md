# ndisCmGetThreadSessionId(_ETHREAD *)

- ea: `0x14004ac90`
- end: `0x14004ad63`
- name: `?ndisCmGetThreadSessionId@@YAKPEAU_ETHREAD@@@Z`
- size: `211`
- prototype: `unsigned int __fastcall(PETHREAD Thread)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400cebe0`

## callees

- `0x14004ac90`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14004acae`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004acae`
- `ntoskrnl!SeQueryInformationToken` at `0x14004ad1a`
- `ntoskrnl!SeQueryInformationToken` at `0x14004ad1a`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004ad50`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004ad50`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004acd9`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004acd9`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004acf0`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004acf0`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004ad2b`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004ad2b`

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
0x14004ac90  push    rbx
0x14004ac92  sub     rsp, 40h
0x14004ac96  xor     eax, eax
0x14004ac98  mov     [rsp+48h+CopyOnOpen], 0
0x14004ac9d  mov     [rsp+48h+ImpersonationLevel], eax
0x14004aca1  mov     rbx, rcx
0x14004aca4  mov     [rsp+48h+TokenInformation], rax
0x14004aca9  mov     [rsp+48h+EffectiveOnly], 0
0x14004acae  call    cs:__imp_KeGetCurrentIrql
0x14004acb5  nop     dword ptr [rax+rax+00h]
0x14004acba  cmp     al, 2
0x14004acbc  jnb     loc_14004AD50
0x14004acc2  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x14004acc7  mov     [rsp+48h+var_10], rsi
0x14004accc  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x14004acd1  mov     rcx, rbx; Thread
0x14004acd4  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x14004acd9  call    cs:__imp_PsReferenceImpersonationToken
0x14004ace0  nop     dword ptr [rax+rax+00h]
0x14004ace5  mov     rsi, rax
0x14004ace8  test    rax, rax
0x14004aceb  jnz     short loc_14004AD08
0x14004aced  mov     rcx, rbx
0x14004acf0  call    cs:__imp_PsGetThreadSessionId
0x14004acf7  nop     dword ptr [rax+rax+00h]
0x14004acfc  mov     rsi, [rsp+48h+var_10]
0x14004ad01  add     rsp, 40h
0x14004ad05  pop     rbx
0x14004ad06  retn
0x14004ad08  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14004ad0d  mov     [rsp+48h+var_18], rdi
0x14004ad12  mov     edx, 0Ch; TokenInformationClass
0x14004ad17  mov     rcx, rsi; Token
0x14004ad1a  call    cs:__imp_SeQueryInformationToken
0x14004ad21  nop     dword ptr [rax+rax+00h]
0x14004ad26  mov     rcx, rsi; ImpersonationToken
0x14004ad29  mov     edi, eax
0x14004ad2b  call    cs:__imp_PsDereferenceImpersonationToken
0x14004ad32  nop     dword ptr [rax+rax+00h]
0x14004ad37  test    edi, edi
0x14004ad39  mov     rdi, [rsp+48h+var_18]
0x14004ad3e  js      short loc_14004ACED
0x14004ad40  mov     eax, dword ptr [rsp+48h+TokenInformation]
0x14004ad44  mov     rsi, [rsp+48h+var_10]
0x14004ad49  add     rsp, 40h
0x14004ad4d  pop     rbx
0x14004ad4e  retn
0x14004ad50  call    cs:__imp_PsGetCurrentProcessSessionId
0x14004ad57  nop     dword ptr [rax+rax+00h]
0x14004ad5c  add     rsp, 40h
0x14004ad60  pop     rbx
0x14004ad61  retn
```
