# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180010898`
- end: `0x180010972`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010838`

## callees

- `0x180010898`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800108f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010924`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010942`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800108f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010924`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010942`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800108e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010916`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010934`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800108e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010916`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010934`

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
0x180010898  push    rbx
0x18001089a  push    rbp
0x18001089b  push    rsi
0x18001089c  push    rdi
0x18001089d  push    r12
0x18001089f  push    r13
0x1800108a1  push    r14
0x1800108a3  push    r15
0x1800108a5  sub     rsp, 28h
0x1800108a9  lea     r15, [rcx+50h]
0x1800108ad  mov     rdi, rcx
0x1800108b0  cmp     rcx, r15
0x1800108b3  jz      loc_180010961
0x1800108b9  mov     rsi, [rdi]
0x1800108bc  jmp     loc_180010948
0x1800108c1  mov     r13, rsi
0x1800108c4  mov     r12, rsi
0x1800108c7  mov     rsi, [rsi+8]
0x1800108cb  movzx   eax, word ptr [r13+30h]
0x1800108d0  mov     rbp, [r13+28h]
0x1800108d4  lea     r14, [rax+rax*4]
0x1800108d8  shl     r14, 4
0x1800108dc  add     r14, rbp
0x1800108df  jmp     short loc_18001090D
0x1800108e1  mov     rbx, [rbp+40h]
0x1800108e5  call    cs:__imp_GetProcessHeap
0x1800108eb  mov     r8, rbx; lpMem
0x1800108ee  xor     edx, edx; dwFlags
0x1800108f0  mov     rcx, rax; hHeap
0x1800108f3  call    cs:__imp_HeapFree
0x1800108f9  mov     qword ptr [rbp+40h], 0
0x180010901  mov     qword ptr [rbp+48h], 0
0x180010909  add     rbp, 50h ; 'P'
0x18001090d  cmp     rbp, r14
0x180010910  jnz     short loc_1800108E1
0x180010912  mov     rbx, [r13+28h]
0x180010916  call    cs:__imp_GetProcessHeap
0x18001091c  mov     r8, rbx; lpMem
0x18001091f  xor     edx, edx; dwFlags
0x180010921  mov     rcx, rax; hHeap
0x180010924  call    cs:__imp_HeapFree
0x18001092a  xor     eax, eax
0x18001092c  mov     [r13+30h], eax
0x180010930  mov     [r13+28h], rax
0x180010934  call    cs:__imp_GetProcessHeap
0x18001093a  mov     r8, r12; lpMem
0x18001093d  xor     edx, edx; dwFlags
0x18001093f  mov     rcx, rax; hHeap
0x180010942  call    cs:__imp_HeapFree
0x180010948  test    rsi, rsi
0x18001094b  jnz     loc_1800108C1
0x180010951  mov     [rdi], rsi
0x180010954  add     rdi, 8
0x180010958  cmp     rdi, r15
0x18001095b  jnz     loc_1800108B9
0x180010961  add     rsp, 28h
0x180010965  pop     r15
0x180010967  pop     r14
0x180010969  pop     r13
0x18001096b  pop     r12
0x18001096d  pop     rdi
0x18001096e  pop     rsi
0x18001096f  pop     rbp
0x180010970  pop     rbx
0x180010971  retn
```
