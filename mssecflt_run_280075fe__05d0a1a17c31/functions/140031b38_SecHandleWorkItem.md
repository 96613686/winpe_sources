# SecHandleWorkItem

- ea: `0x140031b38`
- end: `0x140031c88`
- name: `SecHandleWorkItem`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002f5e0`

## callees

- `0x140011650`
- `0x1400119c0`
- `0x140031b38`
- `0x140031c88`

## import_xrefs

- `ntoskrnl!PsRevertToSelf` at `0x140031c10`
- `ntoskrnl!PsRevertToSelf` at `0x140031c10`
- `ntoskrnl!PsImpersonateClient` at `0x140031be9`
- `ntoskrnl!PsImpersonateClient` at `0x140031c3c`
- `ntoskrnl!PsImpersonateClient` at `0x140031be9`
- `ntoskrnl!PsImpersonateClient` at `0x140031c3c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140031bbe`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140031bbe`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140031c52`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140031c52`

## pseudocode

```c
void __fastcall SecHandleWorkItem(__int64 a1)
{
  PACCESS_TOKEN v2; // rdi
  NTSTATUS v3; // eax
  __int64 v4; // rcx
  int v5; // ebx
  unsigned __int8 EffectiveOnly; // [rsp+30h] [rbp-C8h] BYREF
  unsigned __int8 CopyOnOpen[3]; // [rsp+31h] [rbp-C7h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel[3]; // [rsp+34h] [rbp-C4h] BYREF
  _BYTE v9[160]; // [rsp+40h] [rbp-B8h] BYREF

  memset(v9, 0, 0x94u);
  CopyOnOpen[0] = 0;
  EffectiveOnly = 0;
  ImpersonationLevel[0] = SecurityAnonymous;
  if ( a1 && *(_WORD *)(a1 + 24) && *(_QWORD *)(a1 + 40) )
  {
    v2 = PsReferenceImpersonationToken(KeGetCurrentThread(), CopyOnOpen, &EffectiveOnly, ImpersonationLevel);
    v3 = PsImpersonateClient(
           KeGetCurrentThread(),
           *(PACCESS_TOKEN *)(a1 + 40),
           *(_BYTE *)(a1 + 49),
           *(_BYTE *)(a1 + 50),
           *(SECURITY_IMPERSONATION_LEVEL *)(a1 + 52));
    v4 = a1 + 24;
    v5 = v3;
    SecNotifyObtainFileHash(v4, v9);
    if ( v5 < 0 )
    {
      if ( !v2 )
        return;
    }
    else
    {
      if ( !v2 )
      {
        PsRevertToSelf();
        return;
      }
      PsImpersonateClient(KeGetCurrentThread(), v2, CopyOnOpen[0], EffectiveOnly, ImpersonationLevel[0]);
    }
    PsDereferenceImpersonationToken(v2);
  }
}

```

## disassembly

```asm
0x140031b38  mov     [rsp+arg_8], rbx
0x140031b3d  mov     [rsp+arg_10], rbp
0x140031b42  mov     [rsp+arg_18], rsi
0x140031b47  push    rdi
0x140031b48  sub     rsp, 0F0h
0x140031b4f  mov     rax, cs:__security_cookie
0x140031b56  xor     rax, rsp
0x140031b59  mov     [rsp+0F8h+var_18], rax
0x140031b61  mov     rbx, rcx
0x140031b64  xor     edx, edx; Val
0x140031b66  lea     rcx, [rsp+0F8h+var_B8]; void *
0x140031b6b  mov     r8d, 94h; Size
0x140031b71  call    memset
0x140031b76  xor     ebp, ebp
0x140031b78  mov     [rsp+0F8h+CopyOnOpen], bpl
0x140031b7d  mov     [rsp+0F8h+EffectiveOnly], bpl
0x140031b82  mov     [rsp+0F8h+ImpersonationLevel], ebp
0x140031b86  test    rbx, rbx
0x140031b89  jz      loc_140031C5E
0x140031b8f  lea     rsi, [rbx+18h]
0x140031b93  cmp     [rsi], bp
0x140031b96  jz      loc_140031C5E
0x140031b9c  cmp     [rbx+28h], rbp
0x140031ba0  jz      loc_140031C5E
0x140031ba6  mov     rcx, gs:188h; Thread
0x140031baf  lea     r9, [rsp+0F8h+ImpersonationLevel]; ImpersonationLevel
0x140031bb4  lea     r8, [rsp+0F8h+EffectiveOnly]; EffectiveOnly
0x140031bb9  lea     rdx, [rsp+0F8h+CopyOnOpen]; CopyOnOpen
0x140031bbe  call    cs:__imp_PsReferenceImpersonationToken
0x140031bc5  nop     dword ptr [rax+rax+00h]
0x140031bca  mov     rcx, gs:188h; Thread
0x140031bd3  mov     rdi, rax
0x140031bd6  mov     edx, [rbx+34h]
0x140031bd9  mov     r9b, [rbx+32h]; EffectiveOnly
0x140031bdd  mov     r8b, [rbx+31h]; CopyOnOpen
0x140031be1  mov     [rsp+0F8h+var_D8], edx; ImpersonationLevel
0x140031be5  mov     rdx, [rbx+28h]; Token
0x140031be9  call    cs:__imp_PsImpersonateClient
0x140031bf0  nop     dword ptr [rax+rax+00h]
0x140031bf5  lea     rdx, [rsp+0F8h+var_B8]
0x140031bfa  mov     rcx, rsi
0x140031bfd  mov     ebx, eax
0x140031bff  call    SecNotifyObtainFileHash
0x140031c04  shr     ebx, 1Fh
0x140031c07  test    bl, bl
0x140031c09  jnz     short loc_140031C4A
0x140031c0b  test    rdi, rdi
0x140031c0e  jnz     short loc_140031C1E
0x140031c10  call    cs:__imp_PsRevertToSelf
0x140031c17  nop     dword ptr [rax+rax+00h]
0x140031c1c  jmp     short loc_140031C5E
0x140031c1e  mov     rcx, gs:188h; Thread
0x140031c27  mov     rdx, rdi; Token
0x140031c2a  mov     eax, [rsp+0F8h+ImpersonationLevel]
0x140031c2e  mov     r9b, [rsp+0F8h+EffectiveOnly]; EffectiveOnly
0x140031c33  mov     r8b, [rsp+0F8h+CopyOnOpen]; CopyOnOpen
0x140031c38  mov     [rsp+0F8h+var_D8], eax; ImpersonationLevel
0x140031c3c  call    cs:__imp_PsImpersonateClient
0x140031c43  nop     dword ptr [rax+rax+00h]
0x140031c48  jmp     short loc_140031C4F
0x140031c4a  test    rdi, rdi
0x140031c4d  jz      short loc_140031C5E
0x140031c4f  mov     rcx, rdi; ImpersonationToken
0x140031c52  call    cs:__imp_PsDereferenceImpersonationToken
0x140031c59  nop     dword ptr [rax+rax+00h]
0x140031c5e  mov     rcx, [rsp+0F8h+var_18]
0x140031c66  xor     rcx, rsp; StackCookie
0x140031c69  call    __security_check_cookie
0x140031c6e  lea     r11, [rsp+0F8h+var_8]
0x140031c76  mov     rbx, [r11+18h]
0x140031c7a  mov     rbp, [r11+20h]
0x140031c7e  mov     rsi, [r11+28h]
0x140031c82  mov     rsp, r11
0x140031c85  pop     rdi
0x140031c86  retn
```
