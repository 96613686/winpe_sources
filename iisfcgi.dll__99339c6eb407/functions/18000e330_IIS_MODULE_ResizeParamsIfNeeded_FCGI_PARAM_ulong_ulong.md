# IIS_MODULE::ResizeParamsIfNeeded(_FCGI_PARAM * *,ulong *,ulong)

- ea: `0x18000e330`
- end: `0x18000e3a4`
- name: `?ResizeParamsIfNeeded@IIS_MODULE@@AEAAHPEAPEAU_FCGI_PARAM@@PEAKK@Z`
- size: `116`
- prototype: `__int64 __fastcall(IIS_MODULE *__hidden this, struct _FCGI_PARAM **, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18000b564`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000e330`
- `0x18000edc6`

## pseudocode

```c
__int64 __fastcall IIS_MODULE::ResizeParamsIfNeeded(
        IIS_MODULE *this,
        struct _FCGI_PARAM **a2,
        unsigned int *a3,
        unsigned int a4)
{
  int v4; // eax
  unsigned __int64 v7; // rbp
  __int64 result; // rax
  struct _FCGI_PARAM *v9; // rsi

  v4 = *a3;
  if ( a4 < *a3 )
    return 1;
  v7 = a4 + v4;
  if ( 2 * v4 >= a4 )
    v7 = (unsigned int)(2 * v4);
  result = (__int64)operator new(saturated_mul(v7, 0x20u));
  v9 = (struct _FCGI_PARAM *)result;
  if ( result )
  {
    memcpy_0((void *)result, *a2, 32LL * *a3);
    operator delete(*a2);
    *a2 = v9;
    *a3 = v7;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000e330  push    rbx
0x18000e332  push    rbp
0x18000e333  push    rsi
0x18000e334  push    rdi
0x18000e335  sub     rsp, 28h
0x18000e339  mov     eax, [r8]
0x18000e33c  mov     rbx, r8
0x18000e33f  mov     rdi, rdx
0x18000e342  cmp     r9d, eax
0x18000e345  jb      short loc_18000E396
0x18000e347  lea     ecx, [rax+rax]
0x18000e34a  cmp     ecx, r9d
0x18000e34d  lea     ebp, [r9+rax]
0x18000e351  mov     eax, 20h ; ' '
0x18000e356  cmovnb  ebp, ecx
0x18000e359  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e360  mul     rbp
0x18000e363  cmovb   rax, rcx
0x18000e367  mov     rcx, rax; Size
0x18000e36a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e36f  mov     rsi, rax
0x18000e372  test    rax, rax
0x18000e375  jz      short loc_18000E39B
0x18000e377  mov     r8d, [rbx]
0x18000e37a  mov     rcx, rsi; void *
0x18000e37d  mov     rdx, [rdi]; Src
0x18000e380  shl     r8, 5; Size
0x18000e384  call    memcpy_0
0x18000e389  mov     rcx, [rdi]; Block
0x18000e38c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e391  mov     [rdi], rsi
0x18000e394  mov     [rbx], ebp
0x18000e396  mov     eax, 1
0x18000e39b  add     rsp, 28h
0x18000e39f  pop     rdi
0x18000e3a0  pop     rsi
0x18000e3a1  pop     rbp
0x18000e3a2  pop     rbx
0x18000e3a3  retn
```
