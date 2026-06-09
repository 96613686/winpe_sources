# HIDA_Create(_ITEMIDLIST const *,uint,_ITEMIDLIST const * *)

- ea: `0x18000bec8`
- end: `0x18000bf9e`
- name: `?HIDA_Create@@YAPEAXPEFBU_ITEMIDLIST@@IPEAPEFBU1@@Z`
- size: `214`
- prototype: `void *__fastcall(const struct _ITEMIDLIST *Src, unsigned int, const struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ba40`

## callees

- `0x18000bec8`
- `0x180012a80`

## import_xrefs

- `SHELL32!__imp_ILGetSize` at `0x18000bef4`
- `SHELL32!__imp_ILGetSize` at `0x18000bf09`
- `SHELL32!__imp_ILGetSize` at `0x18000bf38`
- `SHELL32!__imp_ILGetSize` at `0x18000bf64`
- `SHELL32!__imp_ILGetSize` at `0x18000bef4`
- `SHELL32!__imp_ILGetSize` at `0x18000bf09`
- `SHELL32!__imp_ILGetSize` at `0x18000bf38`
- `SHELL32!__imp_ILGetSize` at `0x18000bf64`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000bf1e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000bf1e`

## pseudocode

```c
_DWORD *__fastcall HIDA_Create(const struct _ITEMIDLIST *Src, unsigned int a2, const struct _ITEMIDLIST **a3)
{
  _DWORD *v3; // rsi
  unsigned int v7; // r15d
  __int64 v8; // rdi
  unsigned int i; // ebx
  _DWORD *v10; // rax
  __int64 v11; // r12
  UINT v12; // ebx
  unsigned int v13; // r14d
  const ITEMIDLIST *v14; // rdi
  UINT v15; // ebx

  v3 = 0;
  if ( Src )
  {
    v7 = 4 * a2 + 8;
    v8 = 0;
    for ( i = v7 + ILGetSize(Src); (unsigned int)v8 < a2; v8 = (unsigned int)(v8 + 1) )
      i += ILGetSize(a3[v8]);
    v10 = GlobalAlloc(0x40u, i);
    v3 = v10;
    if ( v10 )
    {
      *v10 = a2;
      if ( a2 )
      {
        v11 = 0;
        v12 = ILGetSize(Src);
        v3[1] = v7;
        memcpy_0((char *)v3 + v7, Src, v12);
        v13 = v7 + v12;
        do
        {
          v14 = a3[v11];
          v11 = (unsigned int)(v11 + 1);
          v15 = ILGetSize(v14);
          v3[(unsigned int)v11 + 1] = v13;
          memcpy_0((char *)v3 + v13, v14, v15);
          v13 += v15;
        }
        while ( (_DWORD)v11 != a2 );
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000bec8  push    rbx
0x18000beca  push    rbp
0x18000becb  push    rsi
0x18000becc  push    rdi
0x18000becd  push    r12
0x18000becf  push    r13
0x18000bed1  push    r14
0x18000bed3  push    r15
0x18000bed5  sub     rsp, 28h
0x18000bed9  xor     esi, esi
0x18000bedb  mov     r13, r8
0x18000bede  mov     ebp, edx
0x18000bee0  mov     r14, rcx
0x18000bee3  test    rcx, rcx
0x18000bee6  jz      loc_18000BF8A
0x18000beec  lea     r15d, ds:8[rdx*4]
0x18000bef4  call    cs:__imp_ILGetSize
0x18000befa  xor     edi, edi
0x18000befc  lea     ebx, [r15+rax]
0x18000bf00  test    ebp, ebp
0x18000bf02  jz      short loc_18000BF17
0x18000bf04  mov     rcx, [r13+rdi*8+0]; pidl
0x18000bf09  call    cs:__imp_ILGetSize
0x18000bf0f  add     ebx, eax
0x18000bf11  inc     edi
0x18000bf13  cmp     edi, ebp
0x18000bf15  jb      short loc_18000BF04
0x18000bf17  mov     edx, ebx; dwBytes
0x18000bf19  mov     ecx, 40h ; '@'; uFlags
0x18000bf1e  call    cs:__imp_GlobalAlloc
0x18000bf24  mov     rsi, rax
0x18000bf27  test    rax, rax
0x18000bf2a  jz      short loc_18000BF8A
0x18000bf2c  mov     [rax], ebp
0x18000bf2e  test    ebp, ebp
0x18000bf30  jz      short loc_18000BF8A
0x18000bf32  mov     rcx, r14; pidl
0x18000bf35  xor     r12d, r12d
0x18000bf38  call    cs:__imp_ILGetSize
0x18000bf3e  mov     ecx, r15d
0x18000bf41  mov     rdx, r14; Src
0x18000bf44  add     rcx, rsi; void *
0x18000bf47  mov     r8d, eax; Size
0x18000bf4a  mov     ebx, eax
0x18000bf4c  mov     [rsi+4], r15d
0x18000bf50  call    memcpy_0
0x18000bf55  lea     r14d, [r15+rbx]
0x18000bf59  mov     rdi, [r13+r12*8+0]
0x18000bf5e  inc     r12d
0x18000bf61  mov     rcx, rdi; pidl
0x18000bf64  call    cs:__imp_ILGetSize
0x18000bf6a  mov     ecx, r14d
0x18000bf6d  mov     rdx, rdi; Src
0x18000bf70  add     rcx, rsi; void *
0x18000bf73  mov     r8d, eax; Size
0x18000bf76  mov     ebx, eax
0x18000bf78  mov     [rsi+r12*4+4], r14d
0x18000bf7d  call    memcpy_0
0x18000bf82  add     r14d, ebx
0x18000bf85  cmp     r12d, ebp
0x18000bf88  jnz     short loc_18000BF59
0x18000bf8a  mov     rax, rsi
0x18000bf8d  add     rsp, 28h
0x18000bf91  pop     r15
0x18000bf93  pop     r14
0x18000bf95  pop     r13
0x18000bf97  pop     r12
0x18000bf99  pop     rdi
0x18000bf9a  pop     rsi
0x18000bf9b  pop     rbp
0x18000bf9c  pop     rbx
0x18000bf9d  retn
```
