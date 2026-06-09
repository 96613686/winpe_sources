# ReplaceSubStr(ushort const *,ushort * *,ushort * *,ushort const *,ulong *,ulong *)

- ea: `0x18000f564`
- end: `0x18000f6ee`
- name: `?ReplaceSubStr@@YAJPEBGPEAPEAG10PEAK2@Z`
- size: `394`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 **, unsigned __int16 **, const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000eb2c`
- `0x18000f09c`
- `0x18000f4b4`

## callees

- `0x1800036a6`
- `0x1800036b2`
- `0x180007014`
- `0x18000f564`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000f66a`
- `KERNEL32!LocalFree` at `0x18000f66a`
- `KERNEL32!LocalAlloc` at `0x18000f60e`
- `KERNEL32!LocalAlloc` at `0x18000f60e`

## pseudocode

```c
__int64 __fastcall ReplaceSubStr(
        const unsigned __int16 *a1,
        const unsigned __int16 **a2,
        unsigned __int16 **a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  __int64 v6; // r14
  const unsigned __int16 *v7; // rsi
  __int64 v8; // rbx
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r12
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // r13
  int v16; // eax
  unsigned __int16 *v17; // rcx

  v6 = -1;
  v7 = a4;
  v8 = a4 - *a3;
  v10 = -1;
  do
    ++v10;
  while ( a1[v10] );
  if ( v10 > v8 + (unsigned __int64)*a6 )
  {
    if ( v10 - v8 > 0x7FFFFFFFFFFFFFFFLL )
      return 2147500037LL;
    v11 = *a5;
    if ( v11 > 2 * (v8 - v10) - 1 )
      return 2147500037LL;
    v12 = v11 + 2 * (v10 - v8);
    if ( v12 > 0x3FFFFFFF )
      return 2147500037LL;
    v13 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v12);
    v14 = v13;
    if ( !v13 )
      return 2147942414LL;
    *a3 = &v13[*a3 - *a2];
    v7 = &v13[v7 - *a2];
    StringCchCopyW(v13, v12, *a2);
    LocalFree((HLOCAL)*a2);
    *a2 = v14;
    v16 = 2 * (v10 - v8);
    *a5 += v16;
    *a6 += v16;
  }
  v17 = &(*a3)[v10];
  if ( v17 != v7 )
  {
    do
      ++v6;
    while ( v7[v6] );
    memmove_0(v17, v7, 2 * v6 + 2);
  }
  if ( v10 )
    memcpy_0(*a3, a1, 2 * v10);
  *a6 += v8 - v10;
  return 0;
}

```

## disassembly

```asm
0x18000f564  mov     [rsp+arg_10], rbx
0x18000f569  mov     [rsp+arg_8], rdx
0x18000f56e  mov     [rsp+Src], rcx
0x18000f573  push    rbp
0x18000f574  push    rsi
0x18000f575  push    rdi
0x18000f576  push    r12
0x18000f578  push    r13
0x18000f57a  push    r14
0x18000f57c  push    r15
0x18000f57e  sub     rsp, 20h
0x18000f582  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000f586  mov     rbx, r9
0x18000f589  sub     rbx, [r8]
0x18000f58c  mov     rsi, r9
0x18000f58f  sar     rbx, 1
0x18000f592  mov     r15, r8
0x18000f595  xor     edx, edx
0x18000f597  mov     rdi, r14
0x18000f59a  inc     rdi
0x18000f59d  cmp     [rcx+rdi*2], dx
0x18000f5a1  jnz     short loc_18000F59A
0x18000f5a3  mov     rbp, [rsp+58h+arg_28]
0x18000f5ab  mov     eax, [rbp+0]
0x18000f5ae  add     rax, rbx
0x18000f5b1  cmp     rdi, rax
0x18000f5b4  jbe     loc_18000F689
0x18000f5ba  mov     rcx, rdi
0x18000f5bd  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000f5c7  sub     rcx, rbx
0x18000f5ca  cmp     rcx, rax
0x18000f5cd  ja      loc_18000F6E7
0x18000f5d3  mov     rax, [rsp+58h+arg_20]
0x18000f5db  mov     edx, [rax]
0x18000f5dd  mov     rax, rbx
0x18000f5e0  sub     rax, rdi
0x18000f5e3  lea     rax, ds:0FFFFFFFFFFFFFFFFh[rax*2]
0x18000f5eb  cmp     rdx, rax
0x18000f5ee  ja      loc_18000F6E7
0x18000f5f4  lea     r12, [rdx+rcx*2]
0x18000f5f8  cmp     r12, 3FFFFFFFh
0x18000f5ff  ja      loc_18000F6E7
0x18000f605  lea     rdx, [r12+r12]; uBytes
0x18000f609  mov     ecx, 40h ; '@'; uFlags
0x18000f60e  call    cs:__imp_LocalAlloc
0x18000f614  mov     r13, rax
0x18000f617  test    rax, rax
0x18000f61a  jnz     short loc_18000F626
0x18000f61c  mov     eax, 8007000Eh
0x18000f621  jmp     loc_18000F6D2
0x18000f626  mov     rcx, [rsp+58h+arg_8]
0x18000f62b  mov     rdx, r12; unsigned __int64
0x18000f62e  mov     rax, [r15]
0x18000f631  sub     rax, [rcx]
0x18000f634  sar     rax, 1
0x18000f637  lea     rax, ds:0[rax*2]
0x18000f63f  add     rax, r13
0x18000f642  mov     [r15], rax
0x18000f645  sub     rsi, [rcx]
0x18000f648  mov     r8, [rcx]; unsigned __int16 *
0x18000f64b  mov     rcx, r13; unsigned __int16 *
0x18000f64e  sar     rsi, 1
0x18000f651  lea     rsi, ds:0[rsi*2]
0x18000f659  add     rsi, r13
0x18000f65c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f661  mov     r12, [rsp+58h+arg_8]
0x18000f666  mov     rcx, [r12]; hMem
0x18000f66a  call    cs:__imp_LocalFree
0x18000f670  mov     rcx, [rsp+58h+arg_20]
0x18000f678  mov     eax, edi
0x18000f67a  sub     eax, ebx
0x18000f67c  mov     [r12], r13
0x18000f680  add     eax, eax
0x18000f682  add     [rcx], eax
0x18000f684  add     [rbp+0], eax
0x18000f687  xor     edx, edx
0x18000f689  mov     rcx, [r15]
0x18000f68c  lea     r12, [rdi+rdi]
0x18000f690  add     rcx, r12; void *
0x18000f693  mov     r13d, edi
0x18000f696  cmp     rcx, rsi
0x18000f699  jz      short loc_18000F6B5
0x18000f69b  inc     r14
0x18000f69e  cmp     [rsi+r14*2], dx
0x18000f6a3  jnz     short loc_18000F69B
0x18000f6a5  lea     r8, ds:2[r14*2]; Size
0x18000f6ad  mov     rdx, rsi; Src
0x18000f6b0  call    memmove_0
0x18000f6b5  test    rdi, rdi
0x18000f6b8  jz      short loc_18000F6CA
0x18000f6ba  mov     rdx, [rsp+58h+Src]; Src
0x18000f6bf  mov     r8, r12; Size
0x18000f6c2  mov     rcx, [r15]; void *
0x18000f6c5  call    memcpy_0
0x18000f6ca  sub     ebx, r13d
0x18000f6cd  add     [rbp+0], ebx
0x18000f6d0  xor     eax, eax
0x18000f6d2  mov     rbx, [rsp+58h+arg_10]
0x18000f6d7  add     rsp, 20h
0x18000f6db  pop     r15
0x18000f6dd  pop     r14
0x18000f6df  pop     r13
0x18000f6e1  pop     r12
0x18000f6e3  pop     rdi
0x18000f6e4  pop     rsi
0x18000f6e5  pop     rbp
0x18000f6e6  retn
0x18000f6e7  mov     eax, 80004005h
0x18000f6ec  jmp     short loc_18000F6D2
```
