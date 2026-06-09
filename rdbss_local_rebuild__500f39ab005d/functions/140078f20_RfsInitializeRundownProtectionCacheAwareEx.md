# RfsInitializeRundownProtectionCacheAwareEx

- ea: `0x140078f20`
- end: `0x140078fd0`
- name: `RfsInitializeRundownProtectionCacheAwareEx`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140047ea0`

## callees

- `0x140078f20`

## import_xrefs

- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140078f59`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140078f59`

## pseudocode

```c
__int64 __fastcall RfsInitializeRundownProtectionCacheAwareEx(__int64 *a1, __int64 a2)
{
  unsigned __int64 v2; // rdi
  __int64 *v4; // rsi
  unsigned int v5; // r9d
  unsigned int v6; // r8d
  ULONG RecommendedSharedDataAlignment; // eax
  __int64 v8; // rcx
  __int64 result; // rax
  int v10; // edx

  v2 = a2 - 32;
  v4 = a1 + 4;
  if ( a2 == 40 )
  {
    v5 = 1;
    *a1 = (__int64)v4;
    v6 = 0;
    *((_DWORD *)a1 + 6) = 1;
    a1[1] = 0;
    *((_DWORD *)a1 + 5) = v2;
  }
  else
  {
    RecommendedSharedDataAlignment = KeGetRecommendedSharedDataAlignment();
    *((_DWORD *)a1 + 5) = RecommendedSharedDataAlignment;
    v8 = (__int64)v4 + RecommendedSharedDataAlignment - 1;
    v5 = v2 / RecommendedSharedDataAlignment - 1;
    *((_DWORD *)a1 + 6) = v5;
    v6 = 0;
    result = -RecommendedSharedDataAlignment;
    a1[1] = 0;
    *a1 = result & v8;
    if ( !v5 )
      return result;
  }
  do
  {
    v10 = v6 % v5;
    result = *a1;
    ++v6;
    *(_QWORD *)((unsigned int)(*((_DWORD *)a1 + 5) * v10) + *a1) = 1;
    v5 = *((_DWORD *)a1 + 6);
  }
  while ( v6 < v5 );
  return result;
}

```

## disassembly

```asm
0x140078f20  mov     [rsp+arg_0], rbx
0x140078f25  mov     [rsp+arg_8], rsi
0x140078f2a  push    rdi
0x140078f2b  sub     rsp, 20h
0x140078f2f  lea     rdi, [rdx-20h]
0x140078f33  mov     rbx, rcx
0x140078f36  lea     rsi, [rcx+20h]
0x140078f3a  cmp     rdi, 8
0x140078f3e  jnz     short loc_140078F59
0x140078f40  mov     r9d, 1
0x140078f46  mov     [rcx], rsi
0x140078f49  xor     r8d, r8d
0x140078f4c  mov     [rcx+18h], r9d
0x140078f50  mov     [rcx+8], r8
0x140078f54  mov     [rcx+14h], edi
0x140078f57  jmp     short loc_140078F9C
0x140078f59  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x140078f60  nop     dword ptr [rax+rax+00h]
0x140078f65  mov     r8d, eax
0x140078f68  xor     edx, edx
0x140078f6a  lea     rcx, [rsi-1]
0x140078f6e  mov     [rbx+14h], r8d
0x140078f72  mov     rax, rdi
0x140078f75  add     rcx, r8
0x140078f78  div     r8
0x140078f7b  lea     r9d, [rax-1]
0x140078f7f  mov     eax, r8d
0x140078f82  neg     eax
0x140078f84  mov     [rbx+18h], r9d
0x140078f88  xor     r8d, r8d
0x140078f8b  cdqe
0x140078f8d  and     rcx, rax
0x140078f90  mov     [rbx+8], r8
0x140078f94  mov     [rbx], rcx
0x140078f97  test    r9d, r9d
0x140078f9a  jz      short loc_140078FBF
0x140078f9c  xor     edx, edx
0x140078f9e  mov     eax, r8d
0x140078fa1  div     r9d
0x140078fa4  mov     rax, [rbx]
0x140078fa7  inc     r8d
0x140078faa  imul    edx, [rbx+14h]
0x140078fae  mov     qword ptr [rdx+rax], 1
0x140078fb6  mov     r9d, [rbx+18h]
0x140078fba  cmp     r8d, r9d
0x140078fbd  jb      short loc_140078F9C
0x140078fbf  mov     rbx, [rsp+28h+arg_0]
0x140078fc4  mov     rsi, [rsp+28h+arg_8]
0x140078fc9  add     rsp, 20h
0x140078fcd  pop     rdi
0x140078fce  retn
```
