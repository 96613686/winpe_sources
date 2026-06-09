# GetImpersonationOrPrimaryToken(_EPROCESS *,uchar *)

- ea: `0x18000ff20`
- end: `0x18000ff88`
- name: `?GetImpersonationOrPrimaryToken@@YAPEAXPEAU_EPROCESS@@PEAE@Z`
- size: `104`
- prototype: `void *__fastcall(PEPROCESS Process, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ed64`

## callees

- `0x18000ff20`

## import_xrefs

- `ntoskrnl!PsReferencePrimaryToken` at `0x18000ff6d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x18000ff6d`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x18000ff59`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x18000ff59`

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
0x18000ff20  mov     rax, rsp
0x18000ff23  mov     [rax+8], rbx
0x18000ff27  push    rdi
0x18000ff28  sub     rsp, 20h
0x18000ff2c  mov     rbx, rdx
0x18000ff2f  mov     byte ptr [rax+18h], 0
0x18000ff33  mov     rdi, rcx
0x18000ff36  mov     byte ptr [rax+10h], 0
0x18000ff3a  mov     dword ptr [rax+20h], 0
0x18000ff41  lea     r9, [rax+20h]; ImpersonationLevel
0x18000ff45  mov     rcx, gs:188h; Thread
0x18000ff4e  lea     r8, [rax+10h]; EffectiveOnly
0x18000ff52  mov     byte ptr [rdx], 1
0x18000ff55  lea     rdx, [rax+18h]; CopyOnOpen
0x18000ff59  call    cs:__imp_PsReferenceImpersonationToken
0x18000ff60  nop     dword ptr [rax+rax+00h]
0x18000ff65  test    rax, rax
0x18000ff68  jnz     short loc_18000FF7C
0x18000ff6a  mov     rcx, rdi; Process
0x18000ff6d  call    cs:__imp_PsReferencePrimaryToken
0x18000ff74  nop     dword ptr [rax+rax+00h]
0x18000ff79  mov     byte ptr [rbx], 0
0x18000ff7c  mov     rbx, [rsp+28h+arg_0]
0x18000ff81  add     rsp, 20h
0x18000ff85  pop     rdi
0x18000ff86  retn
```
