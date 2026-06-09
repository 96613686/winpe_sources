# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000c740`
- end: `0x18000c81a`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c6e0`

## callees

- `0x18000c740`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c79b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c79b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c78d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c78d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7dc`

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
0x18000c740  push    rbx
0x18000c742  push    rbp
0x18000c743  push    rsi
0x18000c744  push    rdi
0x18000c745  push    r12
0x18000c747  push    r13
0x18000c749  push    r14
0x18000c74b  push    r15
0x18000c74d  sub     rsp, 28h
0x18000c751  lea     r15, [rcx+50h]
0x18000c755  mov     rdi, rcx
0x18000c758  cmp     rcx, r15
0x18000c75b  jz      loc_18000C809
0x18000c761  mov     rsi, [rdi]
0x18000c764  jmp     loc_18000C7F0
0x18000c769  mov     r13, rsi
0x18000c76c  mov     r12, rsi
0x18000c76f  mov     rsi, [rsi+8]
0x18000c773  movzx   eax, word ptr [r13+30h]
0x18000c778  mov     rbp, [r13+28h]
0x18000c77c  lea     r14, [rax+rax*4]
0x18000c780  shl     r14, 4
0x18000c784  add     r14, rbp
0x18000c787  jmp     short loc_18000C7B5
0x18000c789  mov     rbx, [rbp+40h]
0x18000c78d  call    cs:__imp_GetProcessHeap
0x18000c793  mov     r8, rbx; lpMem
0x18000c796  xor     edx, edx; dwFlags
0x18000c798  mov     rcx, rax; hHeap
0x18000c79b  call    cs:__imp_HeapFree
0x18000c7a1  mov     qword ptr [rbp+40h], 0
0x18000c7a9  mov     qword ptr [rbp+48h], 0
0x18000c7b1  add     rbp, 50h ; 'P'
0x18000c7b5  cmp     rbp, r14
0x18000c7b8  jnz     short loc_18000C789
0x18000c7ba  mov     rbx, [r13+28h]
0x18000c7be  call    cs:__imp_GetProcessHeap
0x18000c7c4  mov     r8, rbx; lpMem
0x18000c7c7  xor     edx, edx; dwFlags
0x18000c7c9  mov     rcx, rax; hHeap
0x18000c7cc  call    cs:__imp_HeapFree
0x18000c7d2  xor     eax, eax
0x18000c7d4  mov     [r13+30h], eax
0x18000c7d8  mov     [r13+28h], rax
0x18000c7dc  call    cs:__imp_GetProcessHeap
0x18000c7e2  mov     r8, r12; lpMem
0x18000c7e5  xor     edx, edx; dwFlags
0x18000c7e7  mov     rcx, rax; hHeap
0x18000c7ea  call    cs:__imp_HeapFree
0x18000c7f0  test    rsi, rsi
0x18000c7f3  jnz     loc_18000C769
0x18000c7f9  mov     [rdi], rsi
0x18000c7fc  add     rdi, 8
0x18000c800  cmp     rdi, r15
0x18000c803  jnz     loc_18000C761
0x18000c809  add     rsp, 28h
0x18000c80d  pop     r15
0x18000c80f  pop     r14
0x18000c811  pop     r13
0x18000c813  pop     r12
0x18000c815  pop     rdi
0x18000c816  pop     rsi
0x18000c817  pop     rbp
0x18000c818  pop     rbx
0x18000c819  retn
```
