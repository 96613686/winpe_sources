# FreeAepEntry(_AEP_ENTRY *)

- ea: `0x180016f70`
- end: `0x180017169`
- name: `?FreeAepEntry@@YAXPEAU_AEP_ENTRY@@@Z`
- size: `505`
- prototype: `void __fastcall(struct _AEP_ENTRY *lpMem)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180009800`
- `0x1800154b4`
- `0x180016dc0`
- `0x1800359c0`
- `0x180035f14`

## callees

- `0x180016f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001712a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001712a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016f9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016fc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017015`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017032`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001705f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800170b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800170d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017106`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017130`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016f9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016fc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017015`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017032`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001705f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800170b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800170d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017106`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017130`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016fab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016fd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017023`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017040`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001706d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800170c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800170e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017114`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001713e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016fab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016fd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017023`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017040`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001706d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800170c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800170e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017114`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001713e`

## pseudocode

```c
void __fastcall FreeAepEntry(struct _AEP_ENTRY *lpMem)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  void *v4; // rbx
  HANDLE v5; // rax
  unsigned int *v6; // r15
  void **v7; // rbp
  unsigned int i; // edi
  __int64 v9; // rbx
  void *v10; // rsi
  HANDLE v11; // rax
  void *v12; // rsi
  HANDLE v13; // rax
  void *v14; // rbx
  HANDLE v15; // rax
  unsigned int *v16; // r15
  _QWORD *v17; // r12
  unsigned int j; // esi
  _QWORD *v19; // rbx
  __int64 v20; // rdi
  void *v21; // rbp
  HANDLE v22; // rax
  void *v23; // rbp
  HANDLE v24; // rax
  _QWORD *v25; // rbx
  HANDLE v26; // rax
  HANDLE v27; // rax

  if ( lpMem )
  {
    v2 = (void *)*((_QWORD *)lpMem + 2);
    if ( v2 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
      *((_QWORD *)lpMem + 2) = 0;
    }
    v4 = (void *)*((_QWORD *)lpMem + 5);
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
    v6 = (unsigned int *)((char *)lpMem + 24);
    if ( lpMem != (struct _AEP_ENTRY *)-24LL )
    {
      v7 = (void **)((char *)lpMem + 32);
      if ( lpMem != (struct _AEP_ENTRY *)-32LL )
      {
        for ( i = 0; i < *v6; *(_OWORD *)(v9 + 32) = 0 )
        {
          v9 = (__int64)*v7 + 48 * i;
          v10 = *(void **)(v9 + 24);
          if ( v10 )
          {
            v11 = GetProcessHeap();
            HeapFree(v11, 0, v10);
          }
          v12 = *(void **)(v9 + 40);
          if ( v12 )
          {
            v13 = GetProcessHeap();
            HeapFree(v13, 0, v12);
          }
          ++i;
          *(_OWORD *)v9 = 0;
          *(_OWORD *)(v9 + 16) = 0;
        }
        v14 = *v7;
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v14);
        *v6 = 0;
        *v7 = 0;
      }
    }
    v16 = (unsigned int *)((char *)lpMem + 48);
    if ( lpMem != (struct _AEP_ENTRY *)-48LL )
    {
      v17 = (_QWORD *)((char *)lpMem + 56);
      if ( lpMem != (struct _AEP_ENTRY *)-56LL )
      {
        for ( j = 0; j < *v16; *(_OWORD *)&v19[v20 + 4] = 0 )
        {
          v19 = (_QWORD *)*v17;
          v20 = 6LL * j;
          v21 = *(void **)(*v17 + 48LL * j + 24);
          if ( v21 )
          {
            v22 = GetProcessHeap();
            HeapFree(v22, 0, v21);
          }
          v23 = (void *)v19[6 * j + 5];
          if ( v23 )
          {
            v24 = GetProcessHeap();
            HeapFree(v24, 0, v23);
          }
          ++j;
          *(_OWORD *)&v19[v20] = 0;
          *(_OWORD *)&v19[v20 + 2] = 0;
        }
        v25 = (_QWORD *)*v17;
        v26 = GetProcessHeap();
        HeapFree(v26, 0, v25);
        *v16 = 0;
        *v17 = 0;
      }
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 72));
    v27 = GetProcessHeap();
    HeapFree(v27, 0, lpMem);
  }
}

```

## disassembly

```asm
0x180016f70  test    rcx, rcx
0x180016f73  jz      locret_180017168
0x180016f79  push    r14
0x180016f7b  sub     rsp, 40h
0x180016f7f  mov     [rsp+48h+arg_0], rbx
0x180016f84  mov     r14, rcx
0x180016f87  mov     rbx, [rcx+10h]
0x180016f8b  mov     [rsp+48h+var_20], r13
0x180016f90  xor     r13d, r13d
0x180016f93  mov     [rsp+48h+var_28], r15
0x180016f98  test    rbx, rbx
0x180016f9b  jz      short loc_180016FB5
0x180016f9d  call    cs:__imp_GetProcessHeap
0x180016fa3  mov     r8, rbx; lpMem
0x180016fa6  xor     edx, edx; dwFlags
0x180016fa8  mov     rcx, rax; hHeap
0x180016fab  call    cs:__imp_HeapFree
0x180016fb1  mov     [r14+10h], r13
0x180016fb5  mov     rbx, [r14+28h]
0x180016fb9  mov     [rsp+48h+arg_8], rbp
0x180016fbe  mov     [rsp+48h+arg_10], rsi
0x180016fc3  mov     [rsp+48h+var_10], rdi
0x180016fc8  call    cs:__imp_GetProcessHeap
0x180016fce  mov     r8, rbx; lpMem
0x180016fd1  xor     edx, edx; dwFlags
0x180016fd3  mov     rcx, rax; hHeap
0x180016fd6  call    cs:__imp_HeapFree
0x180016fdc  lea     r15, [r14+18h]
0x180016fe0  test    r15, r15
0x180016fe3  jz      loc_18001707A
0x180016fe9  lea     rbp, [r14+20h]
0x180016fed  test    rbp, rbp
0x180016ff0  jz      loc_18001707A
0x180016ff6  mov     edi, r13d
0x180016ff9  cmp     [r15], r13d
0x180016ffc  jbe     short loc_18001705B
0x180016ffe  mov     eax, edi
0x180017000  lea     rbx, [rax+rax*2]
0x180017004  shl     rbx, 4
0x180017008  add     rbx, [rbp+0]
0x18001700c  mov     rsi, [rbx+18h]
0x180017010  test    rsi, rsi
0x180017013  jz      short loc_180017029
0x180017015  call    cs:__imp_GetProcessHeap
0x18001701b  mov     r8, rsi; lpMem
0x18001701e  xor     edx, edx; dwFlags
0x180017020  mov     rcx, rax; hHeap
0x180017023  call    cs:__imp_HeapFree
0x180017029  mov     rsi, [rbx+28h]
0x18001702d  test    rsi, rsi
0x180017030  jz      short loc_180017046
0x180017032  call    cs:__imp_GetProcessHeap
0x180017038  mov     r8, rsi; lpMem
0x18001703b  xor     edx, edx; dwFlags
0x18001703d  mov     rcx, rax; hHeap
0x180017040  call    cs:__imp_HeapFree
0x180017046  xorps   xmm0, xmm0
0x180017049  inc     edi
0x18001704b  movups  xmmword ptr [rbx], xmm0
0x18001704e  movups  xmmword ptr [rbx+10h], xmm0
0x180017052  movups  xmmword ptr [rbx+20h], xmm0
0x180017056  cmp     edi, [r15]
0x180017059  jb      short loc_180016FFE
0x18001705b  mov     rbx, [rbp+0]
0x18001705f  call    cs:__imp_GetProcessHeap
0x180017065  mov     r8, rbx; lpMem
0x180017068  xor     edx, edx; dwFlags
0x18001706a  mov     rcx, rax; hHeap
0x18001706d  call    cs:__imp_HeapFree
0x180017073  mov     [r15], r13d
0x180017076  mov     [rbp+0], r13
0x18001707a  lea     r15, [r14+30h]
0x18001707e  test    r15, r15
0x180017081  jz      loc_180017126
0x180017087  mov     [rsp+48h+var_18], r12
0x18001708c  lea     r12, [r14+38h]
0x180017090  test    r12, r12
0x180017093  jz      loc_180017121
0x180017099  mov     esi, r13d
0x18001709c  cmp     [r15], r13d
0x18001709f  jbe     short loc_180017102
0x1800170a1  mov     rbx, [r12]
0x1800170a5  mov     eax, esi
0x1800170a7  lea     rdi, [rax+rax*2]
0x1800170ab  add     rdi, rdi
0x1800170ae  mov     rbp, [rbx+rdi*8+18h]
0x1800170b3  test    rbp, rbp
0x1800170b6  jz      short loc_1800170CC
0x1800170b8  call    cs:__imp_GetProcessHeap
0x1800170be  mov     r8, rbp; lpMem
0x1800170c1  xor     edx, edx; dwFlags
0x1800170c3  mov     rcx, rax; hHeap
0x1800170c6  call    cs:__imp_HeapFree
0x1800170cc  mov     rbp, [rbx+rdi*8+28h]
0x1800170d1  test    rbp, rbp
0x1800170d4  jz      short loc_1800170EA
0x1800170d6  call    cs:__imp_GetProcessHeap
0x1800170dc  mov     r8, rbp; lpMem
0x1800170df  xor     edx, edx; dwFlags
0x1800170e1  mov     rcx, rax; hHeap
0x1800170e4  call    cs:__imp_HeapFree
0x1800170ea  xorps   xmm0, xmm0
0x1800170ed  inc     esi
0x1800170ef  movups  xmmword ptr [rbx+rdi*8], xmm0
0x1800170f3  movups  xmmword ptr [rbx+rdi*8+10h], xmm0
0x1800170f8  movups  xmmword ptr [rbx+rdi*8+20h], xmm0
0x1800170fd  cmp     esi, [r15]
0x180017100  jb      short loc_1800170A1
0x180017102  mov     rbx, [r12]
0x180017106  call    cs:__imp_GetProcessHeap
0x18001710c  mov     r8, rbx; lpMem
0x18001710f  xor     edx, edx; dwFlags
0x180017111  mov     rcx, rax; hHeap
0x180017114  call    cs:__imp_HeapFree
0x18001711a  mov     [r15], r13d
0x18001711d  mov     [r12], r13
0x180017121  mov     r12, [rsp+48h+var_18]
0x180017126  lea     rcx, [r14+48h]; lpCriticalSection
0x18001712a  call    cs:__imp_DeleteCriticalSection
0x180017130  call    cs:__imp_GetProcessHeap
0x180017136  mov     r8, r14; lpMem
0x180017139  xor     edx, edx; dwFlags
0x18001713b  mov     rcx, rax; hHeap
0x18001713e  call    cs:__imp_HeapFree
0x180017144  mov     r15, [rsp+48h+var_28]
0x180017149  mov     r13, [rsp+48h+var_20]
0x18001714e  mov     rdi, [rsp+48h+var_10]
0x180017153  mov     rsi, [rsp+48h+arg_10]
0x180017158  mov     rbp, [rsp+48h+arg_8]
0x18001715d  mov     rbx, [rsp+48h+arg_0]
0x180017162  add     rsp, 40h
0x180017166  pop     r14
0x180017168  retn
```
