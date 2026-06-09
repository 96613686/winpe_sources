# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18002640c`
- end: `0x1800264e6`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026354`

## callees

- `0x18002640c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026459`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002648a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800264a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026459`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002648a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800264a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026467`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026498`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800264b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026467`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026498`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800264b6`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        _QWORD *a1)
{
  _QWORD *v1; // r15
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  _QWORD *v4; // r13
  void *v5; // r12
  __int64 v6; // rbp
  __int64 v7; // r14
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v5 = v3;
      v3 = (_QWORD *)v3[1];
      v6 = v4[5];
      v7 = v6 + 80LL * *((unsigned __int16 *)v4 + 24);
      while ( v6 != v7 )
      {
        v8 = *(void **)(v6 + 64);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
        *(_QWORD *)(v6 + 64) = 0;
        *(_QWORD *)(v6 + 72) = 0;
        v6 += 80;
      }
      v10 = (void *)v4[5];
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      *((_DWORD *)v4 + 12) = 0;
      v4[5] = 0;
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v5);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x18002640c  push    rbx
0x18002640e  push    rbp
0x18002640f  push    rsi
0x180026410  push    rdi
0x180026411  push    r12
0x180026413  push    r13
0x180026415  push    r14
0x180026417  push    r15
0x180026419  sub     rsp, 28h
0x18002641d  lea     r15, [rcx+50h]
0x180026421  mov     rdi, rcx
0x180026424  cmp     rcx, r15
0x180026427  jz      loc_1800264D5
0x18002642d  mov     rsi, [rdi]
0x180026430  jmp     loc_1800264BC
0x180026435  mov     r13, rsi
0x180026438  mov     r12, rsi
0x18002643b  mov     rsi, [rsi+8]
0x18002643f  movzx   eax, word ptr [r13+30h]
0x180026444  mov     rbp, [r13+28h]
0x180026448  lea     r14, [rax+rax*4]
0x18002644c  shl     r14, 4
0x180026450  add     r14, rbp
0x180026453  jmp     short loc_180026481
0x180026455  mov     rbx, [rbp+40h]
0x180026459  call    cs:__imp_GetProcessHeap
0x18002645f  mov     r8, rbx; lpMem
0x180026462  xor     edx, edx; dwFlags
0x180026464  mov     rcx, rax; hHeap
0x180026467  call    cs:__imp_HeapFree
0x18002646d  mov     qword ptr [rbp+40h], 0
0x180026475  mov     qword ptr [rbp+48h], 0
0x18002647d  add     rbp, 50h ; 'P'
0x180026481  cmp     rbp, r14
0x180026484  jnz     short loc_180026455
0x180026486  mov     rbx, [r13+28h]
0x18002648a  call    cs:__imp_GetProcessHeap
0x180026490  mov     r8, rbx; lpMem
0x180026493  xor     edx, edx; dwFlags
0x180026495  mov     rcx, rax; hHeap
0x180026498  call    cs:__imp_HeapFree
0x18002649e  xor     eax, eax
0x1800264a0  mov     [r13+30h], eax
0x1800264a4  mov     [r13+28h], rax
0x1800264a8  call    cs:__imp_GetProcessHeap
0x1800264ae  mov     r8, r12; lpMem
0x1800264b1  xor     edx, edx; dwFlags
0x1800264b3  mov     rcx, rax; hHeap
0x1800264b6  call    cs:__imp_HeapFree
0x1800264bc  test    rsi, rsi
0x1800264bf  jnz     loc_180026435
0x1800264c5  mov     [rdi], rsi
0x1800264c8  add     rdi, 8
0x1800264cc  cmp     rdi, r15
0x1800264cf  jnz     loc_18002642D
0x1800264d5  add     rsp, 28h
0x1800264d9  pop     r15
0x1800264db  pop     r14
0x1800264dd  pop     r13
0x1800264df  pop     r12
0x1800264e1  pop     rdi
0x1800264e2  pop     rsi
0x1800264e3  pop     rbp
0x1800264e4  pop     rbx
0x1800264e5  retn
```
