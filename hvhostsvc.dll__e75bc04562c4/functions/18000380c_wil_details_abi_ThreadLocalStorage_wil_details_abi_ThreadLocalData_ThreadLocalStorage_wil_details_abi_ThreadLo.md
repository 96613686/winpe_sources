# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000380c`
- end: `0x1800038e6`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003784`

## callees

- `0x18000380c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003867`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003898`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003867`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003898`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003859`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000388a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003859`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000388a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038a8`

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
0x18000380c  push    rbx
0x18000380e  push    rbp
0x18000380f  push    rsi
0x180003810  push    rdi
0x180003811  push    r12
0x180003813  push    r13
0x180003815  push    r14
0x180003817  push    r15
0x180003819  sub     rsp, 28h
0x18000381d  lea     r15, [rcx+50h]
0x180003821  mov     rdi, rcx
0x180003824  cmp     rcx, r15
0x180003827  jz      loc_1800038D5
0x18000382d  mov     rsi, [rdi]
0x180003830  jmp     loc_1800038BC
0x180003835  mov     r13, rsi
0x180003838  mov     r12, rsi
0x18000383b  mov     rsi, [rsi+8]
0x18000383f  movzx   eax, word ptr [r13+30h]
0x180003844  mov     rbp, [r13+28h]
0x180003848  lea     r14, [rax+rax*4]
0x18000384c  shl     r14, 4
0x180003850  add     r14, rbp
0x180003853  jmp     short loc_180003881
0x180003855  mov     rbx, [rbp+40h]
0x180003859  call    cs:__imp_GetProcessHeap
0x18000385f  mov     r8, rbx; lpMem
0x180003862  xor     edx, edx; dwFlags
0x180003864  mov     rcx, rax; hHeap
0x180003867  call    cs:__imp_HeapFree
0x18000386d  mov     qword ptr [rbp+40h], 0
0x180003875  mov     qword ptr [rbp+48h], 0
0x18000387d  add     rbp, 50h ; 'P'
0x180003881  cmp     rbp, r14
0x180003884  jnz     short loc_180003855
0x180003886  mov     rbx, [r13+28h]
0x18000388a  call    cs:__imp_GetProcessHeap
0x180003890  mov     r8, rbx; lpMem
0x180003893  xor     edx, edx; dwFlags
0x180003895  mov     rcx, rax; hHeap
0x180003898  call    cs:__imp_HeapFree
0x18000389e  xor     eax, eax
0x1800038a0  mov     [r13+30h], eax
0x1800038a4  mov     [r13+28h], rax
0x1800038a8  call    cs:__imp_GetProcessHeap
0x1800038ae  mov     r8, r12; lpMem
0x1800038b1  xor     edx, edx; dwFlags
0x1800038b3  mov     rcx, rax; hHeap
0x1800038b6  call    cs:__imp_HeapFree
0x1800038bc  test    rsi, rsi
0x1800038bf  jnz     loc_180003835
0x1800038c5  mov     [rdi], rsi
0x1800038c8  add     rdi, 8
0x1800038cc  cmp     rdi, r15
0x1800038cf  jnz     loc_18000382D
0x1800038d5  add     rsp, 28h
0x1800038d9  pop     r15
0x1800038db  pop     r14
0x1800038dd  pop     r13
0x1800038df  pop     r12
0x1800038e1  pop     rdi
0x1800038e2  pop     rsi
0x1800038e3  pop     rbp
0x1800038e4  pop     rbx
0x1800038e5  retn
```
