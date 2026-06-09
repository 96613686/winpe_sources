# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180020d78`
- end: `0x180020e52`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180020d18`

## callees

- `0x180020d78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020dc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020df6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020e14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020dc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020df6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020e14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020dd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020e04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020e22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020dd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020e04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020e22`

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
0x180020d78  push    rbx
0x180020d7a  push    rbp
0x180020d7b  push    rsi
0x180020d7c  push    rdi
0x180020d7d  push    r12
0x180020d7f  push    r13
0x180020d81  push    r14
0x180020d83  push    r15
0x180020d85  sub     rsp, 28h
0x180020d89  lea     r15, [rcx+50h]
0x180020d8d  mov     rdi, rcx
0x180020d90  cmp     rcx, r15
0x180020d93  jz      loc_180020E41
0x180020d99  mov     rsi, [rdi]
0x180020d9c  jmp     loc_180020E28
0x180020da1  mov     r13, rsi
0x180020da4  mov     r12, rsi
0x180020da7  mov     rsi, [rsi+8]
0x180020dab  movzx   eax, word ptr [r13+30h]
0x180020db0  mov     rbp, [r13+28h]
0x180020db4  lea     r14, [rax+rax*4]
0x180020db8  shl     r14, 4
0x180020dbc  add     r14, rbp
0x180020dbf  jmp     short loc_180020DED
0x180020dc1  mov     rbx, [rbp+40h]
0x180020dc5  call    cs:__imp_GetProcessHeap
0x180020dcb  mov     r8, rbx; lpMem
0x180020dce  xor     edx, edx; dwFlags
0x180020dd0  mov     rcx, rax; hHeap
0x180020dd3  call    cs:__imp_HeapFree
0x180020dd9  mov     qword ptr [rbp+40h], 0
0x180020de1  mov     qword ptr [rbp+48h], 0
0x180020de9  add     rbp, 50h ; 'P'
0x180020ded  cmp     rbp, r14
0x180020df0  jnz     short loc_180020DC1
0x180020df2  mov     rbx, [r13+28h]
0x180020df6  call    cs:__imp_GetProcessHeap
0x180020dfc  mov     r8, rbx; lpMem
0x180020dff  xor     edx, edx; dwFlags
0x180020e01  mov     rcx, rax; hHeap
0x180020e04  call    cs:__imp_HeapFree
0x180020e0a  xor     eax, eax
0x180020e0c  mov     [r13+30h], eax
0x180020e10  mov     [r13+28h], rax
0x180020e14  call    cs:__imp_GetProcessHeap
0x180020e1a  mov     r8, r12; lpMem
0x180020e1d  xor     edx, edx; dwFlags
0x180020e1f  mov     rcx, rax; hHeap
0x180020e22  call    cs:__imp_HeapFree
0x180020e28  test    rsi, rsi
0x180020e2b  jnz     loc_180020DA1
0x180020e31  mov     [rdi], rsi
0x180020e34  add     rdi, 8
0x180020e38  cmp     rdi, r15
0x180020e3b  jnz     loc_180020D99
0x180020e41  add     rsp, 28h
0x180020e45  pop     r15
0x180020e47  pop     r14
0x180020e49  pop     r13
0x180020e4b  pop     r12
0x180020e4d  pop     rdi
0x180020e4e  pop     rsi
0x180020e4f  pop     rbp
0x180020e50  pop     rbx
0x180020e51  retn
```
