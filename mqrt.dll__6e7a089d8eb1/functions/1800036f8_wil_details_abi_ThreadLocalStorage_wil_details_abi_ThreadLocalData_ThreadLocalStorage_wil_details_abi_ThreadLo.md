# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800036f8`
- end: `0x1800037d2`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003640`

## callees

- `0x1800036f8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003745`
- `KERNEL32!GetProcessHeap` at `0x180003776`
- `KERNEL32!GetProcessHeap` at `0x180003794`
- `KERNEL32!GetProcessHeap` at `0x180003745`
- `KERNEL32!GetProcessHeap` at `0x180003776`
- `KERNEL32!GetProcessHeap` at `0x180003794`
- `KERNEL32!HeapFree` at `0x180003753`
- `KERNEL32!HeapFree` at `0x180003784`
- `KERNEL32!HeapFree` at `0x1800037a2`
- `KERNEL32!HeapFree` at `0x180003753`
- `KERNEL32!HeapFree` at `0x180003784`
- `KERNEL32!HeapFree` at `0x1800037a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        _QWORD *a1)
{
  _QWORD *v1; // rdi
  _QWORD *v2; // r15
  _QWORD *v3; // rsi
  void *v4; // r12
  _QWORD *v5; // r13
  __int64 v6; // rbp
  __int64 v7; // r14
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v1 = a1;
  v2 = a1 + 10;
  do
  {
    v3 = (_QWORD *)*v1;
    while ( v3 )
    {
      v4 = v3;
      v5 = v3;
      v3 = (_QWORD *)v3[1];
      v6 = v5[5];
      v7 = v6 + 80LL * *((unsigned __int16 *)v5 + 24);
      while ( v6 != v7 )
      {
        v8 = *(void **)(v6 + 64);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
        *(_QWORD *)(v6 + 64) = 0;
        *(_QWORD *)(v6 + 72) = 0;
        v6 += 80;
      }
      v10 = (void *)v5[5];
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      *((_DWORD *)v5 + 12) = 0;
      v5[5] = 0;
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v4);
    }
    *v1++ = 0;
  }
  while ( v1 != v2 );
}

```

## disassembly

```asm
0x1800036f8  push    rbx
0x1800036fa  push    rbp
0x1800036fb  push    rsi
0x1800036fc  push    rdi
0x1800036fd  push    r12
0x1800036ff  push    r13
0x180003701  push    r14
0x180003703  push    r15
0x180003705  sub     rsp, 28h
0x180003709  mov     rdi, rcx
0x18000370c  lea     r15, [rcx+50h]
0x180003710  cmp     rcx, r15
0x180003713  jz      loc_1800037C1
0x180003719  mov     rsi, [rdi]
0x18000371c  jmp     loc_1800037A8
0x180003721  mov     r12, rsi
0x180003724  mov     r13, rsi
0x180003727  mov     rsi, [rsi+8]
0x18000372b  mov     rbp, [r13+28h]
0x18000372f  movzx   eax, word ptr [r13+30h]
0x180003734  lea     r14, [rax+rax*4]
0x180003738  shl     r14, 4
0x18000373c  add     r14, rbp
0x18000373f  jmp     short loc_18000376D
0x180003741  mov     rbx, [rbp+40h]
0x180003745  call    cs:__imp_GetProcessHeap
0x18000374b  mov     r8, rbx; lpMem
0x18000374e  xor     edx, edx; dwFlags
0x180003750  mov     rcx, rax; hHeap
0x180003753  call    cs:__imp_HeapFree
0x180003759  mov     qword ptr [rbp+40h], 0
0x180003761  mov     qword ptr [rbp+48h], 0
0x180003769  add     rbp, 50h ; 'P'
0x18000376d  cmp     rbp, r14
0x180003770  jnz     short loc_180003741
0x180003772  mov     rbx, [r13+28h]
0x180003776  call    cs:__imp_GetProcessHeap
0x18000377c  mov     r8, rbx; lpMem
0x18000377f  xor     edx, edx; dwFlags
0x180003781  mov     rcx, rax; hHeap
0x180003784  call    cs:__imp_HeapFree
0x18000378a  xor     eax, eax
0x18000378c  mov     [r13+30h], eax
0x180003790  mov     [r13+28h], rax
0x180003794  call    cs:__imp_GetProcessHeap
0x18000379a  mov     rcx, rax; hHeap
0x18000379d  mov     r8, r12; lpMem
0x1800037a0  xor     edx, edx; dwFlags
0x1800037a2  call    cs:__imp_HeapFree
0x1800037a8  test    rsi, rsi
0x1800037ab  jnz     loc_180003721
0x1800037b1  mov     [rdi], rsi
0x1800037b4  add     rdi, 8
0x1800037b8  cmp     rdi, r15
0x1800037bb  jnz     loc_180003719
0x1800037c1  add     rsp, 28h
0x1800037c5  pop     r15
0x1800037c7  pop     r14
0x1800037c9  pop     r13
0x1800037cb  pop     r12
0x1800037cd  pop     rdi
0x1800037ce  pop     rsi
0x1800037cf  pop     rbp
0x1800037d0  pop     rbx
0x1800037d1  retn
```
