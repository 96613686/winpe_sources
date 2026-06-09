# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180004858`
- end: `0x180004932`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800047d0`

## callees

- `0x180004858`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004902`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004902`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048f4`

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
0x180004858  push    rbx
0x18000485a  push    rbp
0x18000485b  push    rsi
0x18000485c  push    rdi
0x18000485d  push    r12
0x18000485f  push    r13
0x180004861  push    r14
0x180004863  push    r15
0x180004865  sub     rsp, 28h
0x180004869  lea     r15, [rcx+50h]
0x18000486d  mov     rdi, rcx
0x180004870  cmp     rcx, r15
0x180004873  jz      loc_180004921
0x180004879  mov     rsi, [rdi]
0x18000487c  jmp     loc_180004908
0x180004881  mov     r13, rsi
0x180004884  mov     r12, rsi
0x180004887  mov     rsi, [rsi+8]
0x18000488b  movzx   eax, word ptr [r13+30h]
0x180004890  mov     rbp, [r13+28h]
0x180004894  lea     r14, [rax+rax*4]
0x180004898  shl     r14, 4
0x18000489c  add     r14, rbp
0x18000489f  jmp     short loc_1800048CD
0x1800048a1  mov     rbx, [rbp+40h]
0x1800048a5  call    cs:__imp_GetProcessHeap
0x1800048ab  mov     r8, rbx; lpMem
0x1800048ae  xor     edx, edx; dwFlags
0x1800048b0  mov     rcx, rax; hHeap
0x1800048b3  call    cs:__imp_HeapFree
0x1800048b9  mov     qword ptr [rbp+40h], 0
0x1800048c1  mov     qword ptr [rbp+48h], 0
0x1800048c9  add     rbp, 50h ; 'P'
0x1800048cd  cmp     rbp, r14
0x1800048d0  jnz     short loc_1800048A1
0x1800048d2  mov     rbx, [r13+28h]
0x1800048d6  call    cs:__imp_GetProcessHeap
0x1800048dc  mov     r8, rbx; lpMem
0x1800048df  xor     edx, edx; dwFlags
0x1800048e1  mov     rcx, rax; hHeap
0x1800048e4  call    cs:__imp_HeapFree
0x1800048ea  xor     eax, eax
0x1800048ec  mov     [r13+30h], eax
0x1800048f0  mov     [r13+28h], rax
0x1800048f4  call    cs:__imp_GetProcessHeap
0x1800048fa  mov     r8, r12; lpMem
0x1800048fd  xor     edx, edx; dwFlags
0x1800048ff  mov     rcx, rax; hHeap
0x180004902  call    cs:__imp_HeapFree
0x180004908  test    rsi, rsi
0x18000490b  jnz     loc_180004881
0x180004911  mov     [rdi], rsi
0x180004914  add     rdi, 8
0x180004918  cmp     rdi, r15
0x18000491b  jnz     loc_180004879
0x180004921  add     rsp, 28h
0x180004925  pop     r15
0x180004927  pop     r14
0x180004929  pop     r13
0x18000492b  pop     r12
0x18000492d  pop     rdi
0x18000492e  pop     rsi
0x18000492f  pop     rbp
0x180004930  pop     rbx
0x180004931  retn
```
