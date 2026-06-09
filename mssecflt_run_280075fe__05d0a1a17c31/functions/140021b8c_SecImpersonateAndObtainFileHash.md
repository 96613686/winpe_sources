# SecImpersonateAndObtainFileHash

- ea: `0x140021b8c`
- end: `0x140021c94`
- name: `SecImpersonateAndObtainFileHash`
- size: `264`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400222d0`
- `0x140022300`

## callees

- `0x140011650`
- `0x140021b8c`
- `0x140031c88`

## import_xrefs

- `ntoskrnl!PsRevertToSelf` at `0x140021c29`
- `ntoskrnl!PsRevertToSelf` at `0x140021c29`
- `ntoskrnl!PsImpersonateClient` at `0x140021c02`
- `ntoskrnl!PsImpersonateClient` at `0x140021c55`
- `ntoskrnl!PsImpersonateClient` at `0x140021c02`
- `ntoskrnl!PsImpersonateClient` at `0x140021c55`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140021bd9`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140021bd9`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140021c6b`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140021c6b`

## pseudocode

```c
__int64 __fastcall SecImpersonateAndObtainFileHash(__int64 a1, void *a2, __int64 a3)
{
  PACCESS_TOKEN v6; // rbp
  unsigned int v7; // edi
  BOOLEAN EffectiveOnly; // [rsp+30h] [rbp-28h] BYREF
  BOOLEAN CopyOnOpen[3]; // [rsp+31h] [rbp-27h] BYREF
  SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+34h] [rbp-24h] BYREF

  CopyOnOpen[0] = 0;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityAnonymous;
  v6 = PsReferenceImpersonationToken(KeGetCurrentThread(), CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  LODWORD(a2) = PsImpersonateClient(KeGetCurrentThread(), a2, 0, 0, SecurityImpersonation);
  v7 = SecNotifyObtainFileHash(a1, a3);
  if ( (int)a2 < 0 )
  {
    if ( !v6 )
      return v7;
LABEL_6:
    PsDereferenceImpersonationToken(v6);
    return v7;
  }
  if ( v6 )
  {
    PsImpersonateClient(KeGetCurrentThread(), v6, CopyOnOpen[0], EffectiveOnly, ImpersonationLevel);
    goto LABEL_6;
  }
  PsRevertToSelf();
  return v7;
}

```

## disassembly

```asm
0x140021b8c  mov     r11, rsp
0x140021b8f  mov     [r11+20h], rbx
0x140021b93  push    rbp
0x140021b94  push    rsi
0x140021b95  push    rdi
0x140021b96  sub     rsp, 40h
0x140021b9a  mov     rax, cs:__security_cookie
0x140021ba1  xor     rax, rsp
0x140021ba4  mov     [rsp+58h+var_20], rax
0x140021ba9  mov     rsi, r8
0x140021bac  mov     [rsp+58h+CopyOnOpen], 0
0x140021bb1  mov     rbx, rdx
0x140021bb4  mov     [rsp+58h+EffectiveOnly], 0
0x140021bb9  mov     rdi, rcx
0x140021bbc  mov     [rsp+58h+var_24], 0
0x140021bc4  mov     rcx, gs:188h; Thread
0x140021bcd  lea     r8, [r11-28h]; EffectiveOnly
0x140021bd1  lea     rdx, [r11-27h]; CopyOnOpen
0x140021bd5  lea     r9, [r11-24h]; ImpersonationLevel
0x140021bd9  call    cs:__imp_PsReferenceImpersonationToken
0x140021be0  nop     dword ptr [rax+rax+00h]
0x140021be5  mov     rcx, gs:188h; Thread
0x140021bee  xor     r9d, r9d; EffectiveOnly
0x140021bf1  xor     r8d, r8d; CopyOnOpen
0x140021bf4  mov     [rsp+58h+ImpersonationLevel], 2; ImpersonationLevel
0x140021bfc  mov     rdx, rbx; Token
0x140021bff  mov     rbp, rax
0x140021c02  call    cs:__imp_PsImpersonateClient
0x140021c09  nop     dword ptr [rax+rax+00h]
0x140021c0e  mov     rdx, rsi
0x140021c11  mov     rcx, rdi
0x140021c14  mov     ebx, eax
0x140021c16  call    SecNotifyObtainFileHash
0x140021c1b  shr     ebx, 1Fh
0x140021c1e  mov     edi, eax
0x140021c20  test    bl, bl
0x140021c22  jnz     short loc_140021C63
0x140021c24  test    rbp, rbp
0x140021c27  jnz     short loc_140021C37
0x140021c29  call    cs:__imp_PsRevertToSelf
0x140021c30  nop     dword ptr [rax+rax+00h]
0x140021c35  jmp     short loc_140021C77
0x140021c37  mov     rcx, gs:188h; Thread
0x140021c40  mov     rdx, rbp; Token
0x140021c43  mov     eax, [rsp+58h+var_24]
0x140021c47  mov     r9b, [rsp+58h+EffectiveOnly]; EffectiveOnly
0x140021c4c  mov     r8b, [rsp+58h+CopyOnOpen]; CopyOnOpen
0x140021c51  mov     [rsp+58h+ImpersonationLevel], eax; ImpersonationLevel
0x140021c55  call    cs:__imp_PsImpersonateClient
0x140021c5c  nop     dword ptr [rax+rax+00h]
0x140021c61  jmp     short loc_140021C68
0x140021c63  test    rbp, rbp
0x140021c66  jz      short loc_140021C77
0x140021c68  mov     rcx, rbp; ImpersonationToken
0x140021c6b  call    cs:__imp_PsDereferenceImpersonationToken
0x140021c72  nop     dword ptr [rax+rax+00h]
0x140021c77  mov     eax, edi
0x140021c79  mov     rcx, [rsp+58h+var_20]
0x140021c7e  xor     rcx, rsp; StackCookie
0x140021c81  call    __security_check_cookie
0x140021c86  mov     rbx, [rsp+58h+arg_18]
0x140021c8b  add     rsp, 40h
0x140021c8f  pop     rdi
0x140021c90  pop     rsi
0x140021c91  pop     rbp
0x140021c92  retn
```
