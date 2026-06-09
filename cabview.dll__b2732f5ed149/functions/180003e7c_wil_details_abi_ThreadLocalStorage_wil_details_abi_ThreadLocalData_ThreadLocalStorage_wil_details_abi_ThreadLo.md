# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180003e7c`
- end: `0x180003f56`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003dc4`

## callees

- `0x180003e7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ed7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ed7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ec9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003efa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ec9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003efa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f18`

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
0x180003e7c  push    rbx
0x180003e7e  push    rbp
0x180003e7f  push    rsi
0x180003e80  push    rdi
0x180003e81  push    r12
0x180003e83  push    r13
0x180003e85  push    r14
0x180003e87  push    r15
0x180003e89  sub     rsp, 28h
0x180003e8d  lea     r15, [rcx+50h]
0x180003e91  mov     rdi, rcx
0x180003e94  cmp     rcx, r15
0x180003e97  jz      loc_180003F45
0x180003e9d  mov     rsi, [rdi]
0x180003ea0  jmp     loc_180003F2C
0x180003ea5  mov     r13, rsi
0x180003ea8  mov     r12, rsi
0x180003eab  mov     rsi, [rsi+8]
0x180003eaf  movzx   eax, word ptr [r13+30h]
0x180003eb4  mov     rbp, [r13+28h]
0x180003eb8  lea     r14, [rax+rax*4]
0x180003ebc  shl     r14, 4
0x180003ec0  add     r14, rbp
0x180003ec3  jmp     short loc_180003EF1
0x180003ec5  mov     rbx, [rbp+40h]
0x180003ec9  call    cs:__imp_GetProcessHeap
0x180003ecf  mov     r8, rbx; lpMem
0x180003ed2  xor     edx, edx; dwFlags
0x180003ed4  mov     rcx, rax; hHeap
0x180003ed7  call    cs:__imp_HeapFree
0x180003edd  mov     qword ptr [rbp+40h], 0
0x180003ee5  mov     qword ptr [rbp+48h], 0
0x180003eed  add     rbp, 50h ; 'P'
0x180003ef1  cmp     rbp, r14
0x180003ef4  jnz     short loc_180003EC5
0x180003ef6  mov     rbx, [r13+28h]
0x180003efa  call    cs:__imp_GetProcessHeap
0x180003f00  mov     r8, rbx; lpMem
0x180003f03  xor     edx, edx; dwFlags
0x180003f05  mov     rcx, rax; hHeap
0x180003f08  call    cs:__imp_HeapFree
0x180003f0e  xor     eax, eax
0x180003f10  mov     [r13+30h], eax
0x180003f14  mov     [r13+28h], rax
0x180003f18  call    cs:__imp_GetProcessHeap
0x180003f1e  mov     r8, r12; lpMem
0x180003f21  xor     edx, edx; dwFlags
0x180003f23  mov     rcx, rax; hHeap
0x180003f26  call    cs:__imp_HeapFree
0x180003f2c  test    rsi, rsi
0x180003f2f  jnz     loc_180003EA5
0x180003f35  mov     [rdi], rsi
0x180003f38  add     rdi, 8
0x180003f3c  cmp     rdi, r15
0x180003f3f  jnz     loc_180003E9D
0x180003f45  add     rsp, 28h
0x180003f49  pop     r15
0x180003f4b  pop     r14
0x180003f4d  pop     r13
0x180003f4f  pop     r12
0x180003f51  pop     rdi
0x180003f52  pop     rsi
0x180003f53  pop     rbp
0x180003f54  pop     rbx
0x180003f55  retn
```
