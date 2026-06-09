# ClientToken::CreateFromCurrentToken(void)

- ea: `0x14004e544`
- end: `0x14004e630`
- name: `?CreateFromCurrentToken@ClientToken@@SAPEAV1@XZ`
- size: `236`
- prototype: `struct ClientToken *(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14004e6ec`
- `0x140087730`

## callees

- `0x14004e544`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x14004e588`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004e588`
- `ntoskrnl!ExAllocatePool2` at `0x14004e5c7`
- `ntoskrnl!ExAllocatePool2` at `0x14004e5c7`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14004e604`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14004e604`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14004e597`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14004e597`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004e574`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004e574`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004e612`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004e612`

## pseudocode

```c
struct ClientToken *ClientToken::CreateFromCurrentToken(void)
{
  PACCESS_TOKEN v0; // rbx
  struct _KPROCESS *CurrentProcess; // rax
  bool v2; // di
  __int64 Pool2; // r8
  BOOLEAN v4; // cl
  int v5; // edx
  BOOLEAN v7; // [rsp+30h] [rbp+8h] BYREF
  BOOLEAN v8; // [rsp+38h] [rbp+10h] BYREF
  int v9; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  v7 = 0;
  v9 = 3;
  v0 = PsReferenceImpersonationToken(KeGetCurrentThread(), &v8, &v7, (PSECURITY_IMPERSONATION_LEVEL)&v9);
  if ( v0 )
  {
    v2 = 0;
  }
  else
  {
    CurrentProcess = IoGetCurrentProcess();
    v0 = PsReferencePrimaryToken(CurrentProcess);
    v2 = v0 != 0;
    if ( !v0 )
      return 0;
  }
  Pool2 = ExAllocatePool2(256, 16, 1094929747);
  if ( !Pool2 )
  {
    if ( v2 )
      PsDereferencePrimaryToken(v0);
    else
      PsDereferenceImpersonationToken(v0);
    return 0;
  }
  v4 = v7;
  v5 = v9;
  *(_BYTE *)(Pool2 + 9) = v8;
  *(_BYTE *)(Pool2 + 10) = v4;
  *(_QWORD *)Pool2 = v0;
  *(_BYTE *)(Pool2 + 8) = v2;
  *(_DWORD *)(Pool2 + 12) = v5;
  return (struct ClientToken *)Pool2;
}

```

## disassembly

```asm
0x14004e544  mov     rax, rsp
0x14004e547  mov     [rax+20h], rbx
0x14004e54b  push    rdi
0x14004e54c  sub     rsp, 20h
0x14004e550  mov     byte ptr [rax+10h], 0
0x14004e554  lea     r9, [rax+18h]; ImpersonationLevel
0x14004e558  mov     byte ptr [rax+8], 0
0x14004e55c  lea     r8, [rax+8]; EffectiveOnly
0x14004e560  mov     dword ptr [rax+18h], 3
0x14004e567  lea     rdx, [rax+10h]; CopyOnOpen
0x14004e56b  mov     rcx, gs:188h; Thread
0x14004e574  call    cs:__imp_PsReferenceImpersonationToken
0x14004e57b  nop     dword ptr [rax+rax+00h]
0x14004e580  mov     rbx, rax
0x14004e583  test    rax, rax
0x14004e586  jnz     short loc_14004E5B4
0x14004e588  call    cs:__imp_IoGetCurrentProcess
0x14004e58f  nop     dword ptr [rax+rax+00h]
0x14004e594  mov     rcx, rax; Process
0x14004e597  call    cs:__imp_PsReferencePrimaryToken
0x14004e59e  nop     dword ptr [rax+rax+00h]
0x14004e5a3  test    rax, rax
0x14004e5a6  mov     rbx, rax
0x14004e5a9  setnz   dil
0x14004e5ad  test    rax, rax
0x14004e5b0  jnz     short loc_14004E5B7
0x14004e5b2  jmp     short loc_14004E61E
0x14004e5b4  xor     dil, dil
0x14004e5b7  mov     edx, 10h
0x14004e5bc  mov     ecx, 100h
0x14004e5c1  mov     r8d, 41434D53h
0x14004e5c7  call    cs:__imp_ExAllocatePool2
0x14004e5ce  nop     dword ptr [rax+rax+00h]
0x14004e5d3  mov     r8, rax
0x14004e5d6  test    rax, rax
0x14004e5d9  jz      short loc_14004E5FC
0x14004e5db  mov     cl, [rsp+28h+arg_0]
0x14004e5df  mov     al, [rsp+28h+arg_8]
0x14004e5e3  mov     edx, [rsp+28h+arg_10]
0x14004e5e7  mov     [r8+9], al
0x14004e5eb  mov     [r8+0Ah], cl
0x14004e5ef  mov     [r8], rbx
0x14004e5f2  mov     [r8+8], dil
0x14004e5f6  mov     [r8+0Ch], edx
0x14004e5fa  jmp     short loc_14004E621
0x14004e5fc  mov     rcx, rbx; ImpersonationToken
0x14004e5ff  test    dil, dil
0x14004e602  jz      short loc_14004E612
0x14004e604  call    cs:__imp_PsDereferencePrimaryToken
0x14004e60b  nop     dword ptr [rax+rax+00h]
0x14004e610  jmp     short loc_14004E61E
0x14004e612  call    cs:__imp_PsDereferenceImpersonationToken
0x14004e619  nop     dword ptr [rax+rax+00h]
0x14004e61e  xor     r8d, r8d
0x14004e621  mov     rbx, [rsp+28h+arg_18]
0x14004e626  mov     rax, r8
0x14004e629  add     rsp, 20h
0x14004e62d  pop     rdi
0x14004e62e  retn
```
