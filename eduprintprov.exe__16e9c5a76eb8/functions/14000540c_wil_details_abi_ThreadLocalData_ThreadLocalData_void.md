# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x14000540c`
- end: `0x140005488`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004cdc`

## callees

- `0x14000540c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005431`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005462`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005431`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005462`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000543f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005470`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000543f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005470`

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
0x14000540c  push    rbx
0x14000540e  push    rbp
0x14000540f  push    rsi
0x140005410  push    rdi
0x140005411  sub     rsp, 28h
0x140005415  movzx   eax, word ptr [rcx+20h]
0x140005419  mov     rsi, rcx
0x14000541c  mov     rdi, [rcx+18h]
0x140005420  lea     rbp, [rax+rax*4]
0x140005424  shl     rbp, 4
0x140005428  add     rbp, rdi
0x14000542b  jmp     short loc_140005459
0x14000542d  mov     rbx, [rdi+40h]
0x140005431  call    cs:__imp_GetProcessHeap
0x140005437  mov     r8, rbx; lpMem
0x14000543a  xor     edx, edx; dwFlags
0x14000543c  mov     rcx, rax; hHeap
0x14000543f  call    cs:__imp_HeapFree
0x140005445  mov     qword ptr [rdi+40h], 0
0x14000544d  mov     qword ptr [rdi+48h], 0
0x140005455  add     rdi, 50h ; 'P'
0x140005459  cmp     rdi, rbp
0x14000545c  jnz     short loc_14000542D
0x14000545e  mov     rbx, [rsi+18h]
0x140005462  call    cs:__imp_GetProcessHeap
0x140005468  mov     r8, rbx; lpMem
0x14000546b  xor     edx, edx; dwFlags
0x14000546d  mov     rcx, rax; hHeap
0x140005470  call    cs:__imp_HeapFree
0x140005476  xor     eax, eax
0x140005478  mov     [rsi+20h], eax
0x14000547b  mov     [rsi+18h], rax
0x14000547f  add     rsp, 28h
0x140005483  pop     rdi
0x140005484  pop     rsi
0x140005485  pop     rbp
0x140005486  pop     rbx
0x140005487  retn
```
