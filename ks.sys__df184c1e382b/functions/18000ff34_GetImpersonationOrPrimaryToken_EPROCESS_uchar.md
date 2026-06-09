# GetImpersonationOrPrimaryToken(_EPROCESS *,uchar *)

- ea: `0x18000ff34`
- end: `0x18000ff9c`
- name: `?GetImpersonationOrPrimaryToken@@YAPEAXPEAU_EPROCESS@@PEAE@Z`
- size: `104`
- prototype: `PACCESS_TOKEN __fastcall(PEPROCESS Process, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f454`

## callees

- `0x18000ff34`

## import_xrefs

- `ntoskrnl!PsReferencePrimaryToken` at `0x18000ff81`
- `ntoskrnl!PsReferencePrimaryToken` at `0x18000ff81`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x18000ff6d`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x18000ff6d`

## pseudocode

```c
PACCESS_TOKEN __fastcall GetImpersonationOrPrimaryToken(PEPROCESS Process, unsigned __int8 *a2)
{
  struct _KTHREAD *CurrentThread; // rcx
  PACCESS_TOKEN result; // rax
  unsigned __int8 v6; // [rsp+38h] [rbp+10h] BYREF
  unsigned __int8 v7; // [rsp+40h] [rbp+18h] BYREF
  int v8; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v6 = 0;
  v8 = 0;
  CurrentThread = KeGetCurrentThread();
  *a2 = 1;
  result = PsReferenceImpersonationToken(CurrentThread, &v7, &v6, (PSECURITY_IMPERSONATION_LEVEL)&v8);
  if ( !result )
  {
    result = PsReferencePrimaryToken(Process);
    *a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ff34  mov     rax, rsp
0x18000ff37  mov     [rax+8], rbx
0x18000ff3b  push    rdi
0x18000ff3c  sub     rsp, 20h
0x18000ff40  mov     rbx, rdx
0x18000ff43  mov     byte ptr [rax+18h], 0
0x18000ff47  mov     rdi, rcx
0x18000ff4a  mov     byte ptr [rax+10h], 0
0x18000ff4e  mov     dword ptr [rax+20h], 0
0x18000ff55  lea     r9, [rax+20h]; ImpersonationLevel
0x18000ff59  mov     rcx, gs:188h; Thread
0x18000ff62  lea     r8, [rax+10h]; EffectiveOnly
0x18000ff66  mov     byte ptr [rdx], 1
0x18000ff69  lea     rdx, [rax+18h]; CopyOnOpen
0x18000ff6d  call    cs:__imp_PsReferenceImpersonationToken
0x18000ff74  nop     dword ptr [rax+rax+00h]
0x18000ff79  test    rax, rax
0x18000ff7c  jnz     short loc_18000FF90
0x18000ff7e  mov     rcx, rdi; Process
0x18000ff81  call    cs:__imp_PsReferencePrimaryToken
0x18000ff88  nop     dword ptr [rax+rax+00h]
0x18000ff8d  mov     byte ptr [rbx], 0
0x18000ff90  mov     rbx, [rsp+28h+arg_0]
0x18000ff95  add     rsp, 20h
0x18000ff99  pop     rdi
0x18000ff9a  retn
```
