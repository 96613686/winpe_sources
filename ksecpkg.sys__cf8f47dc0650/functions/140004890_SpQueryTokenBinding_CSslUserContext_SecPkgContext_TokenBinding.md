# SpQueryTokenBinding(CSslUserContext *,_SecPkgContext_TokenBinding *)

- ea: `0x140004890`
- end: `0x140004935`
- name: `?SpQueryTokenBinding@@YAJPEAUCSslUserContext@@PEAU_SecPkgContext_TokenBinding@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(struct CSslUserContext *, struct _SecPkgContext_TokenBinding *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002f880`

## callees

- `0x140004890`
- `0x1400102c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400048ec`
- `ntoskrnl!ExAllocatePool2` at `0x1400048ec`

## pseudocode

```c
__int64 __fastcall SpQueryTokenBinding(struct CSslUserContext *a1, struct _SecPkgContext_TokenBinding *a2)
{
  __int64 v2; // rdi
  __int64 result; // rax
  const void *v5; // rbp
  void *v6; // rsi
  size_t v7; // r14
  void *Pool2; // rax

  v2 = *((_QWORD *)a1 + 56);
  if ( !v2 )
  {
    result = 0;
    *(_OWORD *)a2 = 0;
    return result;
  }
  v5 = *(const void **)(v2 + 8);
  v6 = 0;
  if ( v5 )
  {
    v7 = *(unsigned __int16 *)(v2 + 2);
    Pool2 = (void *)ExAllocatePool2(SslPoolType, v7, 1131180883);
    v6 = Pool2;
    if ( !Pool2 )
      return 2148074240LL;
    memmove(Pool2, v5, v7);
  }
  result = 0;
  *(_OWORD *)a2 = *(_OWORD *)v2;
  *((_QWORD *)a2 + 1) = v6;
  return result;
}

```

## disassembly

```asm
0x140004890  mov     [rsp+arg_18], rbx
0x140004895  push    rdi
0x140004896  sub     rsp, 20h
0x14000489a  mov     rdi, [rcx+1C0h]
0x1400048a1  mov     rbx, rdx
0x1400048a4  test    rdi, rdi
0x1400048a7  jnz     short loc_1400048BD
0x1400048a9  xorps   xmm0, xmm0
0x1400048ac  xor     eax, eax
0x1400048ae  movups  xmmword ptr [rdx], xmm0
0x1400048b1  mov     rbx, [rsp+28h+arg_18]
0x1400048b6  add     rsp, 20h
0x1400048ba  pop     rdi
0x1400048bb  retn
0x1400048bd  mov     [rsp+28h+arg_0], rbp
0x1400048c2  mov     rbp, [rdi+8]
0x1400048c6  mov     [rsp+28h+arg_8], rsi
0x1400048cb  xor     esi, esi
0x1400048cd  mov     [rsp+28h+arg_10], r14
0x1400048d2  test    rbp, rbp
0x1400048d5  jz      short loc_140004915
0x1400048d7  movzx   r14d, word ptr [rdi+2]
0x1400048dc  mov     r8d, 436C7353h
0x1400048e2  mov     rcx, cs:?SslPoolType@@3_KA; unsigned __int64 SslPoolType
0x1400048e9  mov     edx, r14d
0x1400048ec  call    cs:__imp_ExAllocatePool2
0x1400048f3  nop     dword ptr [rax+rax+00h]
0x1400048f8  mov     rsi, rax
0x1400048fb  test    rax, rax
0x1400048fe  jnz     short loc_140004907
0x140004900  mov     eax, 80090300h
0x140004905  jmp     short loc_140004921
0x140004907  mov     r8, r14; Size
0x14000490a  mov     rdx, rbp; Src
0x14000490d  mov     rcx, rax; void *
0x140004910  call    memmove
0x140004915  movups  xmm0, xmmword ptr [rdi]
0x140004918  xor     eax, eax
0x14000491a  movups  xmmword ptr [rbx], xmm0
0x14000491d  mov     [rbx+8], rsi
0x140004921  mov     rsi, [rsp+28h+arg_8]
0x140004926  mov     rbp, [rsp+28h+arg_0]
0x14000492b  mov     r14, [rsp+28h+arg_10]
0x140004930  jmp     loc_1400048B1
```
