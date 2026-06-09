# Pku2uGetContextToken

- ea: `0x140028fb0`
- end: `0x1400290a2`
- name: `Pku2uGetContextToken`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140007008`
- `0x140028fb0`
- `0x140029d94`
- `0x140029f3c`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x14002903e`
- `ntoskrnl!ExGetPreviousMode` at `0x14002903e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002906b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002906b`

## string_xrefs

- `0x140028ffa`: `Invalid handle supplied for GetContextToken(0x%x)\n`
- `0x140028fcc`: `Pku2uGetContextToken Called\n`

## pseudocode

```c
__int64 __fastcall Pku2uGetContextToken(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rax
  _QWORD *v7; // rbx
  NTSTATUS v8; // edi
  __int64 v9; // rax
  KPROCESSOR_MODE PreviousMode; // al
  void *v11; // rcx
  PVOID Object; // [rsp+78h] [rbp+20h] BYREF

  if ( KsecInfoLevel )
    KsecDebugOut(4, "Pku2uGetContextToken Called\n");
  v6 = Pku2uReferenceContext(a1, 0);
  v7 = (_QWORD *)v6;
  if ( v6 )
  {
    v9 = *(_QWORD *)(v6 + 56);
    if ( v9 )
    {
      if ( a2 )
        *a2 = v9;
      v8 = 0;
      if ( a3 )
      {
        if ( !v7[7]
          || v7[5]
          || (PreviousMode = ExGetPreviousMode(),
              v11 = (void *)v7[7],
              Object = 0,
              v8 = ObReferenceObjectByHandle(v11, 4u, 0, PreviousMode, &Object, 0),
              v7[5] = Object,
              v8 >= 0) )
        {
          *a3 = v7[5];
        }
      }
    }
    else
    {
      v8 = -2146893045;
    }
    Pku2uDereferenceContext(v7);
  }
  else
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "Invalid handle supplied for GetContextToken(0x%x)\n", a1);
    return (unsigned int)-1073741816;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140028fb0  push    rbx
0x140028fb2  push    rsi
0x140028fb3  push    rdi
0x140028fb4  push    r14
0x140028fb6  sub     rsp, 38h
0x140028fba  cmp     cs:KsecInfoLevel, 0
0x140028fc1  mov     r14, r8
0x140028fc4  mov     rsi, rdx
0x140028fc7  mov     rdi, rcx
0x140028fca  jz      short loc_140028FDD
0x140028fcc  lea     rdx, aPku2ugetcontex; "Pku2uGetContextToken Called\n"
0x140028fd3  mov     ecx, 4
0x140028fd8  call    KsecDebugOut
0x140028fdd  xor     edx, edx
0x140028fdf  mov     rcx, rdi
0x140028fe2  call    Pku2uReferenceContext
0x140028fe7  mov     rbx, rax
0x140028fea  test    rax, rax
0x140028fed  jnz     short loc_140029013
0x140028fef  cmp     cs:KsecInfoLevel, eax
0x140028ff5  jz      short loc_140029009
0x140028ff7  mov     r8, rdi
0x140028ffa  lea     rdx, aInvalidHandleS_0; "Invalid handle supplied for GetContextT"...
0x140029001  lea     ecx, [rax+1]
0x140029004  call    KsecDebugOut
0x140029009  mov     edi, 0C0000008h
0x14002900e  jmp     loc_140029095
0x140029013  mov     rax, [rax+38h]
0x140029017  test    rax, rax
0x14002901a  jnz     short loc_140029023
0x14002901c  mov     edi, 8009030Bh
0x140029021  jmp     short loc_14002908D
0x140029023  test    rsi, rsi
0x140029026  jz      short loc_14002902B
0x140029028  mov     [rsi], rax
0x14002902b  xor     edi, edi
0x14002902d  test    r14, r14
0x140029030  jz      short loc_14002908D
0x140029032  cmp     [rbx+38h], rdi
0x140029036  jz      short loc_140029086
0x140029038  cmp     [rbx+28h], rdi
0x14002903c  jnz     short loc_140029086
0x14002903e  call    cs:__imp_ExGetPreviousMode
0x140029045  nop     dword ptr [rax+rax+00h]
0x14002904a  lea     rcx, [rsp+58h+arg_18]
0x14002904f  mov     [rsp+58h+HandleInformation], rdi; HandleInformation
0x140029054  mov     [rsp+58h+Object], rcx; Object
0x140029059  lea     edx, [rdi+4]; DesiredAccess
0x14002905c  mov     rcx, [rbx+38h]; Handle
0x140029060  mov     r9b, al; AccessMode
0x140029063  xor     r8d, r8d; ObjectType
0x140029066  mov     [rsp+58h+arg_18], rdi
0x14002906b  call    cs:__imp_ObReferenceObjectByHandle
0x140029072  nop     dword ptr [rax+rax+00h]
0x140029077  mov     rcx, [rsp+58h+arg_18]
0x14002907c  mov     edi, eax
0x14002907e  mov     [rbx+28h], rcx
0x140029082  test    eax, eax
0x140029084  js      short loc_14002908D
0x140029086  mov     rcx, [rbx+28h]
0x14002908a  mov     [r14], rcx
0x14002908d  mov     rcx, rbx; P
0x140029090  call    Pku2uDereferenceContext
0x140029095  mov     eax, edi
0x140029097  add     rsp, 38h
0x14002909b  pop     r14
0x14002909d  pop     rdi
0x14002909e  pop     rsi
0x14002909f  pop     rbx
0x1400290a0  retn
```
