# RootInfoCreateNew

- ea: `0x18002139c`
- end: `0x1800214a1`
- name: `RootInfoCreateNew`
- size: `261`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, _QWORD *, int, const void **, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180021674`

## callees

- `0x18002139c`
- `0x1800243f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021444`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021444`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021486`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021486`

## pseudocode

```c
__int64 __fastcall RootInfoCreateNew(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        int a5,
        const void **a6,
        _DWORD *a7)
{
  __int64 v9; // r8
  unsigned int v10; // edi
  __int64 i; // rcx
  _QWORD *v12; // r10
  __int64 v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rbx

  v9 = (unsigned int)*a7;
  if ( !(_DWORD)v9 || v9 == 24 * ((unsigned int)*a7 / 0x18uLL) )
  {
    v10 = 0;
    for ( i = 0; (unsigned int)i < (unsigned int)*a7 / 0x18uLL; i = (unsigned int)(i + 1) )
    {
      v12 = *a6;
      v13 = *((_QWORD *)*a6 + 3 * i) - *a4;
      if ( !v13 )
        v13 = v12[3 * i + 1] - a4[1];
      if ( !v13 )
      {
        v12[3 * i + 2] = *a3;
        return v10;
      }
    }
    v14 = HeapAlloc(g_hHeap, 8u, v9 + 24);
    v15 = v14;
    if ( v14 )
    {
      *(_OWORD *)v14 = *(_OWORD *)a4;
      v14[2] = *a3;
      if ( *a6 )
      {
        memcpy_0(v14 + 3, *a6, (unsigned int)*a7);
        HeapFree(g_hHeap, 0, (LPVOID)*a6);
      }
      *a7 += 24;
      *a6 = v15;
    }
    else
    {
      return 8;
    }
  }
  else
  {
    return (unsigned int)-2146885631;
  }
  return v10;
}

```

## disassembly

```asm
0x18002139c  push    rbx
0x18002139e  push    rbp
0x18002139f  push    rsi
0x1800213a0  push    rdi
0x1800213a1  push    r14
0x1800213a3  push    r15
0x1800213a5  sub     rsp, 28h
0x1800213a9  mov     rsi, [rsp+58h+arg_30]
0x1800213b1  mov     r15, r8
0x1800213b4  mov     rbp, r9
0x1800213b7  mov     r9, 0AAAAAAAAAAAAAAABh
0x1800213c1  mov     r8d, [rsi]
0x1800213c4  test    r8d, r8d
0x1800213c7  jz      short loc_1800213EA
0x1800213c9  mov     rax, r9
0x1800213cc  mul     r8
0x1800213cf  shr     rdx, 4
0x1800213d3  lea     rcx, [rdx+rdx*2]
0x1800213d7  shl     rcx, 3
0x1800213db  cmp     r8, rcx
0x1800213de  jz      short loc_1800213EA
0x1800213e0  mov     edi, 80092001h
0x1800213e5  jmp     loc_180021492
0x1800213ea  mov     r14, [rsp+58h+arg_28]
0x1800213f2  mov     rax, r9
0x1800213f5  mul     r8
0x1800213f8  xor     edi, edi
0x1800213fa  xor     ecx, ecx
0x1800213fc  shr     rdx, 4
0x180021400  mov     eax, ecx
0x180021402  cmp     rax, rdx
0x180021405  jnb     short loc_180021434
0x180021407  mov     r10, [r14]
0x18002140a  lea     r9, [rcx+rcx*2]
0x18002140e  mov     rax, [r10+r9*8]
0x180021412  sub     rax, [rbp+0]
0x180021416  jnz     short loc_180021421
0x180021418  mov     rax, [r10+r9*8+8]
0x18002141d  sub     rax, [rbp+8]
0x180021421  test    rax, rax
0x180021424  jz      short loc_18002142A
0x180021426  inc     ecx
0x180021428  jmp     short loc_180021400
0x18002142a  mov     rax, [r15]
0x18002142d  mov     [r10+r9*8+10h], rax
0x180021432  jmp     short loc_180021492
0x180021434  mov     rcx, cs:g_hHeap; hHeap
0x18002143b  add     r8, 18h; dwBytes
0x18002143f  mov     edx, 8; dwFlags
0x180021444  call    cs:__imp_HeapAlloc
0x18002144a  mov     rbx, rax
0x18002144d  test    rax, rax
0x180021450  jnz     short loc_180021457
0x180021452  lea     edi, [rax+8]
0x180021455  jmp     short loc_180021492
0x180021457  movups  xmm0, xmmword ptr [rbp+0]
0x18002145b  movdqu  xmmword ptr [rax], xmm0
0x18002145f  mov     rax, [r15]
0x180021462  mov     [rbx+10h], rax
0x180021466  cmp     [r14], rdi
0x180021469  jz      short loc_18002148C
0x18002146b  mov     r8d, [rsi]; Size
0x18002146e  lea     rcx, [rbx+18h]; void *
0x180021472  mov     rdx, [r14]; Src
0x180021475  call    memcpy_0
0x18002147a  mov     r8, [r14]; lpMem
0x18002147d  xor     edx, edx; dwFlags
0x18002147f  mov     rcx, cs:g_hHeap; hHeap
0x180021486  call    cs:__imp_HeapFree
0x18002148c  add     dword ptr [rsi], 18h
0x18002148f  mov     [r14], rbx
0x180021492  mov     eax, edi
0x180021494  add     rsp, 28h
0x180021498  pop     r15
0x18002149a  pop     r14
0x18002149c  pop     rdi
0x18002149d  pop     rsi
0x18002149e  pop     rbp
0x18002149f  pop     rbx
0x1800214a0  retn
```
