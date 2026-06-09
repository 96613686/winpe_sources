# CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK(CddBitmap *,CddBitmap *)

- ea: `0x14000c0b0`
- end: `0x14000c1c6`
- name: `??0CDDMULTIBITMAPLOCK@@QEAA@PEAVCddBitmap@@0@Z`
- size: `278`
- prototype: `CDDMULTIBITMAPLOCK *(CDDMULTIBITMAPLOCK *__hidden this, struct CddBitmap *, struct CddBitmap *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140002504`
- `0x140004904`
- `0x14000a254`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`

## callees

- `0x14000c0b0`
- `0x14000c1cc`
- `0x1400372d0`

## import_xrefs

- `WIN32K!EngAcquireSemaphore` at `0x14000c0f3`
- `WIN32K!EngAcquireSemaphore` at `0x14000c129`
- `WIN32K!EngAcquireSemaphore` at `0x14000c0f3`
- `WIN32K!EngAcquireSemaphore` at `0x14000c129`

## pseudocode

```c
CDDMULTIBITMAPLOCK *__fastcall CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK(
        CDDMULTIBITMAPLOCK *this,
        struct CddBitmap *a2,
        struct CddBitmap *a3)
{
  struct CddBitmap *v3; // rsi
  struct CddBitmap *v4; // rax
  HSEMAPHORE v8; // rcx
  __int64 v9; // rsi
  HSEMAPHORE v10; // rcx
  signed __int32 v12[18]; // [rsp+0h] [rbp-48h] BYREF

  v3 = a2;
  v4 = a3;
  if ( a2 >= a3 )
  {
    v3 = a3;
    v4 = a2;
  }
  *((_QWORD *)this + 1) = v3;
  *((_QWORD *)this + 2) = v4;
  *(_DWORD *)this = 1;
  if ( v3 )
  {
    v8 = (HSEMAPHORE)*((_QWORD *)v3 + 24);
    if ( v8 )
      EngAcquireSemaphore(v8);
    *((_QWORD *)v3 + 67) = KeGetCurrentThread();
  }
  _InterlockedOr(v12, 0);
  v9 = *((_QWORD *)this + 2);
  if ( v9 )
  {
    v10 = *(HSEMAPHORE *)(v9 + 192);
    if ( v10 )
      EngAcquireSemaphore(v10);
    *(_QWORD *)(v9 + 536) = KeGetCurrentThread();
  }
  if ( a2 )
  {
    if ( *((_BYTE *)a2 + 133) )
    {
      (*(void (__fastcall **)(struct CddBitmap *))(*(_QWORD *)a2 + 176LL))(a2);
      *((_BYTE *)a2 + 133) = 0;
      CddBitmap::LogGDIContentAfterDX(a2);
    }
    *((_BYTE *)a2 + 132) = 1;
    *((_BYTE *)a2 + 134) = 1;
  }
  if ( a3 )
  {
    *((_DWORD *)a3 + 32) |= 0x20u;
    if ( *((_BYTE *)a3 + 133) )
    {
      (*(void (__fastcall **)(struct CddBitmap *))(*(_QWORD *)a3 + 176LL))(a3);
      *((_BYTE *)a3 + 133) = 0;
    }
  }
  return this;
}

```

## disassembly

```asm
0x14000c0b0  push    rbx
0x14000c0b2  push    rsi
0x14000c0b3  push    rdi
0x14000c0b4  push    r14
0x14000c0b6  sub     rsp, 28h
0x14000c0ba  cmp     rdx, r8
0x14000c0bd  mov     rsi, rdx
0x14000c0c0  mov     rax, r8
0x14000c0c3  mov     rdi, r8
0x14000c0c6  cmovnb  rsi, r8
0x14000c0ca  cmovnb  rax, rdx
0x14000c0ce  mov     [rcx+8], rsi
0x14000c0d2  mov     rbx, rdx
0x14000c0d5  mov     [rcx+10h], rax
0x14000c0d9  mov     r14, rcx
0x14000c0dc  mov     dword ptr [rcx], 1
0x14000c0e2  test    rsi, rsi
0x14000c0e5  jz      short loc_14000C10F
0x14000c0e7  mov     rcx, [rsi+0C0h]; hsem
0x14000c0ee  test    rcx, rcx
0x14000c0f1  jz      short loc_14000C0FF
0x14000c0f3  call    cs:__imp_EngAcquireSemaphore
0x14000c0fa  nop     dword ptr [rax+rax+00h]
0x14000c0ff  mov     rax, gs:188h
0x14000c108  mov     [rsi+218h], rax
0x14000c10f  lock or [rsp+48h+var_48], 0
0x14000c114  mov     rsi, [r14+10h]
0x14000c118  test    rsi, rsi
0x14000c11b  jz      short loc_14000C145
0x14000c11d  mov     rcx, [rsi+0C0h]; hsem
0x14000c124  test    rcx, rcx
0x14000c127  jz      short loc_14000C135
0x14000c129  call    cs:__imp_EngAcquireSemaphore
0x14000c130  nop     dword ptr [rax+rax+00h]
0x14000c135  mov     rax, gs:188h
0x14000c13e  mov     [rsi+218h], rax
0x14000c145  test    rbx, rbx
0x14000c148  jz      short loc_14000C163
0x14000c14a  movzx   eax, byte ptr [rbx+85h]
0x14000c151  test    al, al
0x14000c153  jnz     short loc_14000C188
0x14000c155  mov     byte ptr [rbx+84h], 1
0x14000c15c  mov     byte ptr [rbx+86h], 1
0x14000c163  test    rdi, rdi
0x14000c166  jz      short loc_14000C17A
0x14000c168  or      dword ptr [rdi+80h], 20h
0x14000c16f  movzx   eax, byte ptr [rdi+85h]
0x14000c176  test    al, al
0x14000c178  jnz     short loc_14000C1AB
0x14000c17a  mov     rax, r14
0x14000c17d  add     rsp, 28h
0x14000c181  pop     r14
0x14000c183  pop     rdi
0x14000c184  pop     rsi
0x14000c185  pop     rbx
0x14000c186  retn
0x14000c188  mov     rax, [rbx]
0x14000c18b  mov     rcx, rbx
0x14000c18e  mov     rax, [rax+0B0h]
0x14000c195  call    _guard_dispatch_icall
0x14000c19a  mov     rcx, rbx; this
0x14000c19d  mov     byte ptr [rbx+85h], 0
0x14000c1a4  call    ?LogGDIContentAfterDX@CddBitmap@@QEAAXXZ; CddBitmap::LogGDIContentAfterDX(void)
0x14000c1a9  jmp     short loc_14000C155
0x14000c1ab  mov     rax, [rdi]
0x14000c1ae  mov     rcx, rdi
0x14000c1b1  mov     rax, [rax+0B0h]
0x14000c1b8  call    _guard_dispatch_icall
0x14000c1bd  mov     byte ptr [rdi+85h], 0
0x14000c1c4  jmp     short loc_14000C17A
```
