# SpQueryTokenBindingEKM(CSslUserContext *,_SecPkgContext_KeyingMaterial *)

- ea: `0x14000bcb4`
- end: `0x14000bd2e`
- name: `?SpQueryTokenBindingEKM@@YAJPEAUCSslUserContext@@PEAU_SecPkgContext_KeyingMaterial@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(struct CSslUserContext *, struct _SecPkgContext_KeyingMaterial *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002f880`

## callees

- `0x14000bcb4`
- `0x1400102c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000bce7`
- `ntoskrnl!ExAllocatePool2` at `0x14000bce7`

## pseudocode

```c
__int64 __fastcall SpQueryTokenBindingEKM(struct CSslUserContext *a1, struct _SecPkgContext_KeyingMaterial *a2)
{
  void *Pool2; // rax
  void *v5; // rsi
  unsigned int v7; // ebx

  *(_OWORD *)a2 = 0;
  if ( *((_QWORD *)a1 + 58) )
  {
    Pool2 = (void *)ExAllocatePool2(SslPoolType, *((unsigned int *)a1 + 114), 1131180883);
    v5 = Pool2;
    if ( !Pool2 )
      return 2148074240LL;
    v7 = *((_DWORD *)a1 + 114);
    memmove(Pool2, *((const void **)a1 + 58), v7);
    *(_DWORD *)a2 = v7;
    *((_QWORD *)a2 + 1) = v5;
  }
  return 0;
}

```

## disassembly

```asm
0x14000bcb4  push    rbx
0x14000bcb6  push    rsi
0x14000bcb7  push    rdi
0x14000bcb8  push    r14
0x14000bcba  sub     rsp, 28h
0x14000bcbe  xorps   xmm0, xmm0
0x14000bcc1  mov     r14, rdx
0x14000bcc4  movups  xmmword ptr [rdx], xmm0
0x14000bcc7  cmp     qword ptr [rcx+1D0h], 0
0x14000bccf  mov     rdi, rcx
0x14000bcd2  jz      short loc_14000BD21
0x14000bcd4  mov     edx, [rcx+1C8h]
0x14000bcda  mov     r8d, 436C7353h
0x14000bce0  mov     rcx, cs:?SslPoolType@@3_KA; unsigned __int64 SslPoolType
0x14000bce7  call    cs:__imp_ExAllocatePool2
0x14000bcee  nop     dword ptr [rax+rax+00h]
0x14000bcf3  mov     rsi, rax
0x14000bcf6  test    rax, rax
0x14000bcf9  jnz     short loc_14000BD02
0x14000bcfb  mov     eax, 80090300h
0x14000bd00  jmp     short loc_14000BD23
0x14000bd02  mov     ebx, [rdi+1C8h]
0x14000bd08  mov     rcx, rsi; void *
0x14000bd0b  mov     rdx, [rdi+1D0h]; Src
0x14000bd12  mov     r8d, ebx; Size
0x14000bd15  call    memmove
0x14000bd1a  mov     [r14], ebx
0x14000bd1d  mov     [r14+8], rsi
0x14000bd21  xor     eax, eax
0x14000bd23  add     rsp, 28h
0x14000bd27  pop     r14
0x14000bd29  pop     rdi
0x14000bd2a  pop     rsi
0x14000bd2b  pop     rbx
0x14000bd2c  retn
```
