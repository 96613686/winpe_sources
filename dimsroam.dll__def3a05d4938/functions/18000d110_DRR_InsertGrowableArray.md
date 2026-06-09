# DRR_InsertGrowableArray

- ea: `0x18000d110`
- end: `0x18000d1ea`
- name: `DRR_InsertGrowableArray`
- size: `218`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f4c`
- `0x1800050d4`
- `0x18000cde8`

## callees

- `0x18000d110`
- `0x18000d892`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d16d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d16d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1c4`

## pseudocode

```c
__int64 __fastcall DRR_InsertGrowableArray(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v3; // r14d
  __int64 v6; // rsi
  _QWORD *v7; // rdx
  _QWORD *i; // rcx
  unsigned int v9; // r14d
  _QWORD *v10; // rax
  _QWORD *v11; // rdi
  __int64 v12; // rbp
  unsigned int v13; // eax
  __int64 result; // rax

  v3 = *(_DWORD *)(a1 + 12);
  v6 = a2;
  if ( *(_DWORD *)(a1 + 8) < v3 )
  {
    v7 = (_QWORD *)(*(_QWORD *)a1 + 8LL * a2);
    for ( i = (_QWORD *)(*(_QWORD *)a1 + 8 * (*(unsigned int *)(a1 + 8) - 1LL)); i >= v7; --i )
      i[1] = *i;
    *v7 = a3;
LABEL_14:
    result = 0;
    ++*(_DWORD *)(a1 + 8);
    return result;
  }
  v9 = v3 + 64;
  if ( v9 <= 0x1FFFFFFF )
  {
    v10 = LocalAlloc(0, 8LL * v9);
    v11 = v10;
    if ( v10 )
    {
      if ( (_DWORD)v6 )
      {
        v12 = v6;
        memcpy_0(v10, *(const void **)a1, 8 * v6);
      }
      else
      {
        v12 = 0;
      }
      v11[v12] = a3;
      v13 = *(_DWORD *)(a1 + 8);
      if ( (unsigned int)v6 < v13 )
        memcpy_0(&v11[v12 + 1], (const void *)(*(_QWORD *)a1 + 8 * v12), 8LL * (v13 - (unsigned int)v6));
      LocalFree(*(HLOCAL *)a1);
      *(_QWORD *)a1 = v11;
      *(_DWORD *)(a1 + 12) = v9;
      goto LABEL_14;
    }
  }
  return 14;
}

```

## disassembly

```asm
0x18000d110  push    rbx
0x18000d112  push    rbp
0x18000d113  push    rsi
0x18000d114  push    rdi
0x18000d115  push    r14
0x18000d117  push    r15
0x18000d119  sub     rsp, 28h
0x18000d11d  mov     r14d, [rcx+0Ch]
0x18000d121  mov     r15, r8
0x18000d124  mov     rbx, rcx
0x18000d127  mov     esi, edx
0x18000d129  cmp     [rcx+8], r14d
0x18000d12d  jnb     short loc_18000D157
0x18000d12f  mov     r9, [rcx]
0x18000d132  mov     ecx, [rcx+8]
0x18000d135  dec     rcx
0x18000d138  lea     rdx, [r9+rsi*8]
0x18000d13c  lea     rcx, [r9+rcx*8]
0x18000d140  jmp     short loc_18000D14D
0x18000d142  mov     rax, [rcx]
0x18000d145  mov     [rcx+8], rax
0x18000d149  sub     rcx, 8
0x18000d14d  cmp     rcx, rdx
0x18000d150  jnb     short loc_18000D142
0x18000d152  mov     [rdx], r15
0x18000d155  jmp     short loc_18000D1D1
0x18000d157  add     r14d, 40h ; '@'
0x18000d15b  cmp     r14d, 1FFFFFFFh
0x18000d162  ja      short loc_18000D1D8
0x18000d164  mov     edx, r14d
0x18000d167  xor     ecx, ecx; uFlags
0x18000d169  shl     rdx, 3; uBytes
0x18000d16d  call    cs:__imp_LocalAlloc
0x18000d173  mov     rdi, rax
0x18000d176  test    rax, rax
0x18000d179  jz      short loc_18000D1D8
0x18000d17b  test    esi, esi
0x18000d17d  jz      short loc_18000D197
0x18000d17f  mov     rdx, [rbx]; Src
0x18000d182  lea     r8, ds:0[rsi*8]; Size
0x18000d18a  mov     rcx, rax; void *
0x18000d18d  mov     rbp, rsi
0x18000d190  call    memcpy_0
0x18000d195  jmp     short loc_18000D199
0x18000d197  xor     ebp, ebp
0x18000d199  mov     [rdi+rbp*8], r15
0x18000d19d  mov     eax, [rbx+8]
0x18000d1a0  cmp     esi, eax
0x18000d1a2  jnb     short loc_18000D1C1
0x18000d1a4  sub     eax, esi
0x18000d1a6  lea     rcx, [rdi+8]
0x18000d1aa  mov     r8d, eax
0x18000d1ad  lea     rcx, [rcx+rbp*8]; void *
0x18000d1b1  mov     rax, [rbx]
0x18000d1b4  shl     r8, 3; Size
0x18000d1b8  lea     rdx, [rax+rbp*8]; Src
0x18000d1bc  call    memcpy_0
0x18000d1c1  mov     rcx, [rbx]; hMem
0x18000d1c4  call    cs:__imp_LocalFree
0x18000d1ca  mov     [rbx], rdi
0x18000d1cd  mov     [rbx+0Ch], r14d
0x18000d1d1  xor     eax, eax
0x18000d1d3  inc     dword ptr [rbx+8]
0x18000d1d6  jmp     short loc_18000D1DD
0x18000d1d8  mov     eax, 0Eh
0x18000d1dd  add     rsp, 28h
0x18000d1e1  pop     r15
0x18000d1e3  pop     r14
0x18000d1e5  pop     rdi
0x18000d1e6  pop     rsi
0x18000d1e7  pop     rbp
0x18000d1e8  pop     rbx
0x18000d1e9  retn
```
