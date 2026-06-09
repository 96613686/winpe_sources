# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180004394`
- end: `0x18000446e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004254`

## callees

- `0x180004394`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004430`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004430`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004420`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000443e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004420`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000443e`

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
0x180004394  push    rbx
0x180004396  push    rbp
0x180004397  push    rsi
0x180004398  push    rdi
0x180004399  push    r12
0x18000439b  push    r13
0x18000439d  push    r14
0x18000439f  push    r15
0x1800043a1  sub     rsp, 28h
0x1800043a5  lea     r15, [rcx+50h]
0x1800043a9  mov     rdi, rcx
0x1800043ac  cmp     rcx, r15
0x1800043af  jz      loc_18000445D
0x1800043b5  mov     rsi, [rdi]
0x1800043b8  jmp     loc_180004444
0x1800043bd  mov     r13, rsi
0x1800043c0  mov     r12, rsi
0x1800043c3  mov     rsi, [rsi+8]
0x1800043c7  movzx   eax, word ptr [r13+30h]
0x1800043cc  mov     rbp, [r13+28h]
0x1800043d0  lea     r14, [rax+rax*4]
0x1800043d4  shl     r14, 4
0x1800043d8  add     r14, rbp
0x1800043db  jmp     short loc_180004409
0x1800043dd  mov     rbx, [rbp+40h]
0x1800043e1  call    cs:__imp_GetProcessHeap
0x1800043e7  mov     r8, rbx; lpMem
0x1800043ea  xor     edx, edx; dwFlags
0x1800043ec  mov     rcx, rax; hHeap
0x1800043ef  call    cs:__imp_HeapFree
0x1800043f5  mov     qword ptr [rbp+40h], 0
0x1800043fd  mov     qword ptr [rbp+48h], 0
0x180004405  add     rbp, 50h ; 'P'
0x180004409  cmp     rbp, r14
0x18000440c  jnz     short loc_1800043DD
0x18000440e  mov     rbx, [r13+28h]
0x180004412  call    cs:__imp_GetProcessHeap
0x180004418  mov     r8, rbx; lpMem
0x18000441b  xor     edx, edx; dwFlags
0x18000441d  mov     rcx, rax; hHeap
0x180004420  call    cs:__imp_HeapFree
0x180004426  xor     eax, eax
0x180004428  mov     [r13+30h], eax
0x18000442c  mov     [r13+28h], rax
0x180004430  call    cs:__imp_GetProcessHeap
0x180004436  mov     r8, r12; lpMem
0x180004439  xor     edx, edx; dwFlags
0x18000443b  mov     rcx, rax; hHeap
0x18000443e  call    cs:__imp_HeapFree
0x180004444  test    rsi, rsi
0x180004447  jnz     loc_1800043BD
0x18000444d  mov     [rdi], rsi
0x180004450  add     rdi, 8
0x180004454  cmp     rdi, r15
0x180004457  jnz     loc_1800043B5
0x18000445d  add     rsp, 28h
0x180004461  pop     r15
0x180004463  pop     r14
0x180004465  pop     r13
0x180004467  pop     r12
0x180004469  pop     rdi
0x18000446a  pop     rsi
0x18000446b  pop     rbp
0x18000446c  pop     rbx
0x18000446d  retn
```
