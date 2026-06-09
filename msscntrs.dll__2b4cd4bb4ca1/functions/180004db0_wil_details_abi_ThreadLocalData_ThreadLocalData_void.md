# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180004db0`
- end: `0x180004e2c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800045a8`

## callees

- `0x180004db0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004de3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004de3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e14`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  while ( v2 != v3 )
  {
    v4 = *(void **)(v2 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    v2 += 80;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180004db0  push    rbx
0x180004db2  push    rbp
0x180004db3  push    rsi
0x180004db4  push    rdi
0x180004db5  sub     rsp, 28h
0x180004db9  movzx   eax, word ptr [rcx+20h]
0x180004dbd  mov     rsi, rcx
0x180004dc0  mov     rdi, [rcx+18h]
0x180004dc4  lea     rbp, [rax+rax*4]
0x180004dc8  shl     rbp, 4
0x180004dcc  add     rbp, rdi
0x180004dcf  jmp     short loc_180004DFD
0x180004dd1  mov     rbx, [rdi+40h]
0x180004dd5  call    cs:__imp_GetProcessHeap
0x180004ddb  mov     r8, rbx; lpMem
0x180004dde  xor     edx, edx; dwFlags
0x180004de0  mov     rcx, rax; hHeap
0x180004de3  call    cs:__imp_HeapFree
0x180004de9  mov     qword ptr [rdi+40h], 0
0x180004df1  mov     qword ptr [rdi+48h], 0
0x180004df9  add     rdi, 50h ; 'P'
0x180004dfd  cmp     rdi, rbp
0x180004e00  jnz     short loc_180004DD1
0x180004e02  mov     rbx, [rsi+18h]
0x180004e06  call    cs:__imp_GetProcessHeap
0x180004e0c  mov     r8, rbx; lpMem
0x180004e0f  xor     edx, edx; dwFlags
0x180004e11  mov     rcx, rax; hHeap
0x180004e14  call    cs:__imp_HeapFree
0x180004e1a  xor     eax, eax
0x180004e1c  mov     [rsi+20h], eax
0x180004e1f  mov     [rsi+18h], rax
0x180004e23  add     rsp, 28h
0x180004e27  pop     rdi
0x180004e28  pop     rsi
0x180004e29  pop     rbp
0x180004e2a  pop     rbx
0x180004e2b  retn
```
