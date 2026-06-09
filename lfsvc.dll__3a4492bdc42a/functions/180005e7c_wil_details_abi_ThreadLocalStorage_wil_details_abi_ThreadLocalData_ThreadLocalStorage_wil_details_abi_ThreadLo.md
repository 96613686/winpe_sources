# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180005e7c`
- end: `0x180005f56`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e1c`

## callees

- `0x180005e7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ec9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005efa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ec9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005efa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005ed7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005ed7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f26`

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
0x180005e7c  push    rbx
0x180005e7e  push    rbp
0x180005e7f  push    rsi
0x180005e80  push    rdi
0x180005e81  push    r12
0x180005e83  push    r13
0x180005e85  push    r14
0x180005e87  push    r15
0x180005e89  sub     rsp, 28h
0x180005e8d  lea     r15, [rcx+50h]
0x180005e91  mov     rdi, rcx
0x180005e94  cmp     rcx, r15
0x180005e97  jz      loc_180005F45
0x180005e9d  mov     rsi, [rdi]
0x180005ea0  jmp     loc_180005F2C
0x180005ea5  mov     r13, rsi
0x180005ea8  mov     r12, rsi
0x180005eab  mov     rsi, [rsi+8]
0x180005eaf  movzx   eax, word ptr [r13+30h]
0x180005eb4  mov     rbp, [r13+28h]
0x180005eb8  lea     r14, [rax+rax*4]
0x180005ebc  shl     r14, 4
0x180005ec0  add     r14, rbp
0x180005ec3  jmp     short loc_180005EF1
0x180005ec5  mov     rbx, [rbp+40h]
0x180005ec9  call    cs:__imp_GetProcessHeap
0x180005ecf  mov     r8, rbx; lpMem
0x180005ed2  xor     edx, edx; dwFlags
0x180005ed4  mov     rcx, rax; hHeap
0x180005ed7  call    cs:__imp_HeapFree
0x180005edd  mov     qword ptr [rbp+40h], 0
0x180005ee5  mov     qword ptr [rbp+48h], 0
0x180005eed  add     rbp, 50h ; 'P'
0x180005ef1  cmp     rbp, r14
0x180005ef4  jnz     short loc_180005EC5
0x180005ef6  mov     rbx, [r13+28h]
0x180005efa  call    cs:__imp_GetProcessHeap
0x180005f00  mov     r8, rbx; lpMem
0x180005f03  xor     edx, edx; dwFlags
0x180005f05  mov     rcx, rax; hHeap
0x180005f08  call    cs:__imp_HeapFree
0x180005f0e  xor     eax, eax
0x180005f10  mov     [r13+30h], eax
0x180005f14  mov     [r13+28h], rax
0x180005f18  call    cs:__imp_GetProcessHeap
0x180005f1e  mov     r8, r12; lpMem
0x180005f21  xor     edx, edx; dwFlags
0x180005f23  mov     rcx, rax; hHeap
0x180005f26  call    cs:__imp_HeapFree
0x180005f2c  test    rsi, rsi
0x180005f2f  jnz     loc_180005EA5
0x180005f35  mov     [rdi], rsi
0x180005f38  add     rdi, 8
0x180005f3c  cmp     rdi, r15
0x180005f3f  jnz     loc_180005E9D
0x180005f45  add     rsp, 28h
0x180005f49  pop     r15
0x180005f4b  pop     r14
0x180005f4d  pop     r13
0x180005f4f  pop     r12
0x180005f51  pop     rdi
0x180005f52  pop     rsi
0x180005f53  pop     rbp
0x180005f54  pop     rbx
0x180005f55  retn
```
