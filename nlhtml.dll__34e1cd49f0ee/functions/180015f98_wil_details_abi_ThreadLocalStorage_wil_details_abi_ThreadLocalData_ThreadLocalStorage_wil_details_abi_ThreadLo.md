# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180015f98`
- end: `0x180016072`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180015f38`

## callees

- `0x180015f98`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015ff3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016024`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016042`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015ff3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016024`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016042`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015fe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016016`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016034`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015fe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016016`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016034`

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
0x180015f98  push    rbx
0x180015f9a  push    rbp
0x180015f9b  push    rsi
0x180015f9c  push    rdi
0x180015f9d  push    r12
0x180015f9f  push    r13
0x180015fa1  push    r14
0x180015fa3  push    r15
0x180015fa5  sub     rsp, 28h
0x180015fa9  lea     r15, [rcx+50h]
0x180015fad  mov     rdi, rcx
0x180015fb0  cmp     rcx, r15
0x180015fb3  jz      loc_180016061
0x180015fb9  mov     rsi, [rdi]
0x180015fbc  jmp     loc_180016048
0x180015fc1  mov     r13, rsi
0x180015fc4  mov     r12, rsi
0x180015fc7  mov     rsi, [rsi+8]
0x180015fcb  movzx   eax, word ptr [r13+30h]
0x180015fd0  mov     rbp, [r13+28h]
0x180015fd4  lea     r14, [rax+rax*4]
0x180015fd8  shl     r14, 4
0x180015fdc  add     r14, rbp
0x180015fdf  jmp     short loc_18001600D
0x180015fe1  mov     rbx, [rbp+40h]
0x180015fe5  call    cs:__imp_GetProcessHeap
0x180015feb  mov     r8, rbx; lpMem
0x180015fee  xor     edx, edx; dwFlags
0x180015ff0  mov     rcx, rax; hHeap
0x180015ff3  call    cs:__imp_HeapFree
0x180015ff9  mov     qword ptr [rbp+40h], 0
0x180016001  mov     qword ptr [rbp+48h], 0
0x180016009  add     rbp, 50h ; 'P'
0x18001600d  cmp     rbp, r14
0x180016010  jnz     short loc_180015FE1
0x180016012  mov     rbx, [r13+28h]
0x180016016  call    cs:__imp_GetProcessHeap
0x18001601c  mov     r8, rbx; lpMem
0x18001601f  xor     edx, edx; dwFlags
0x180016021  mov     rcx, rax; hHeap
0x180016024  call    cs:__imp_HeapFree
0x18001602a  xor     eax, eax
0x18001602c  mov     [r13+30h], eax
0x180016030  mov     [r13+28h], rax
0x180016034  call    cs:__imp_GetProcessHeap
0x18001603a  mov     r8, r12; lpMem
0x18001603d  xor     edx, edx; dwFlags
0x18001603f  mov     rcx, rax; hHeap
0x180016042  call    cs:__imp_HeapFree
0x180016048  test    rsi, rsi
0x18001604b  jnz     loc_180015FC1
0x180016051  mov     [rdi], rsi
0x180016054  add     rdi, 8
0x180016058  cmp     rdi, r15
0x18001605b  jnz     loc_180015FB9
0x180016061  add     rsp, 28h
0x180016065  pop     r15
0x180016067  pop     r14
0x180016069  pop     r13
0x18001606b  pop     r12
0x18001606d  pop     rdi
0x18001606e  pop     rsi
0x18001606f  pop     rbp
0x180016070  pop     rbx
0x180016071  retn
```
