# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180006624`
- end: `0x1800066fe`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800065f4`

## callees

- `0x180006624`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000667f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000667f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006671`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006671`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066c0`

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
0x180006624  push    rbx
0x180006626  push    rbp
0x180006627  push    rsi
0x180006628  push    rdi
0x180006629  push    r12
0x18000662b  push    r13
0x18000662d  push    r14
0x18000662f  push    r15
0x180006631  sub     rsp, 28h
0x180006635  lea     r15, [rcx+50h]
0x180006639  mov     rdi, rcx
0x18000663c  cmp     rcx, r15
0x18000663f  jz      loc_1800066ED
0x180006645  mov     rsi, [rdi]
0x180006648  jmp     loc_1800066D4
0x18000664d  mov     r13, rsi
0x180006650  mov     r12, rsi
0x180006653  mov     rsi, [rsi+8]
0x180006657  movzx   eax, word ptr [r13+30h]
0x18000665c  mov     rbp, [r13+28h]
0x180006660  lea     r14, [rax+rax*4]
0x180006664  shl     r14, 4
0x180006668  add     r14, rbp
0x18000666b  jmp     short loc_180006699
0x18000666d  mov     rbx, [rbp+40h]
0x180006671  call    cs:__imp_GetProcessHeap
0x180006677  mov     r8, rbx; lpMem
0x18000667a  xor     edx, edx; dwFlags
0x18000667c  mov     rcx, rax; hHeap
0x18000667f  call    cs:__imp_HeapFree
0x180006685  mov     qword ptr [rbp+40h], 0
0x18000668d  mov     qword ptr [rbp+48h], 0
0x180006695  add     rbp, 50h ; 'P'
0x180006699  cmp     rbp, r14
0x18000669c  jnz     short loc_18000666D
0x18000669e  mov     rbx, [r13+28h]
0x1800066a2  call    cs:__imp_GetProcessHeap
0x1800066a8  mov     r8, rbx; lpMem
0x1800066ab  xor     edx, edx; dwFlags
0x1800066ad  mov     rcx, rax; hHeap
0x1800066b0  call    cs:__imp_HeapFree
0x1800066b6  xor     eax, eax
0x1800066b8  mov     [r13+30h], eax
0x1800066bc  mov     [r13+28h], rax
0x1800066c0  call    cs:__imp_GetProcessHeap
0x1800066c6  mov     r8, r12; lpMem
0x1800066c9  xor     edx, edx; dwFlags
0x1800066cb  mov     rcx, rax; hHeap
0x1800066ce  call    cs:__imp_HeapFree
0x1800066d4  test    rsi, rsi
0x1800066d7  jnz     loc_18000664D
0x1800066dd  mov     [rdi], rsi
0x1800066e0  add     rdi, 8
0x1800066e4  cmp     rdi, r15
0x1800066e7  jnz     loc_180006645
0x1800066ed  add     rsp, 28h
0x1800066f1  pop     r15
0x1800066f3  pop     r14
0x1800066f5  pop     r13
0x1800066f7  pop     r12
0x1800066f9  pop     rdi
0x1800066fa  pop     rsi
0x1800066fb  pop     rbp
0x1800066fc  pop     rbx
0x1800066fd  retn
```
