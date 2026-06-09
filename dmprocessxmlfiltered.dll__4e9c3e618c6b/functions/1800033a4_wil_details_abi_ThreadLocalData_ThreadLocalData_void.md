# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800033a4`
- end: `0x180003420`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000315c`

## callees

- `0x1800033a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003408`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003408`

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
0x1800033a4  push    rbx
0x1800033a6  push    rbp
0x1800033a7  push    rsi
0x1800033a8  push    rdi
0x1800033a9  sub     rsp, 28h
0x1800033ad  movzx   eax, word ptr [rcx+20h]
0x1800033b1  mov     rsi, rcx
0x1800033b4  mov     rdi, [rcx+18h]
0x1800033b8  lea     rbp, [rax+rax*4]
0x1800033bc  shl     rbp, 4
0x1800033c0  add     rbp, rdi
0x1800033c3  jmp     short loc_1800033F1
0x1800033c5  mov     rbx, [rdi+40h]
0x1800033c9  call    cs:__imp_GetProcessHeap
0x1800033cf  mov     r8, rbx; lpMem
0x1800033d2  xor     edx, edx; dwFlags
0x1800033d4  mov     rcx, rax; hHeap
0x1800033d7  call    cs:__imp_HeapFree
0x1800033dd  mov     qword ptr [rdi+40h], 0
0x1800033e5  mov     qword ptr [rdi+48h], 0
0x1800033ed  add     rdi, 50h ; 'P'
0x1800033f1  cmp     rdi, rbp
0x1800033f4  jnz     short loc_1800033C5
0x1800033f6  mov     rbx, [rsi+18h]
0x1800033fa  call    cs:__imp_GetProcessHeap
0x180003400  mov     r8, rbx; lpMem
0x180003403  xor     edx, edx; dwFlags
0x180003405  mov     rcx, rax; hHeap
0x180003408  call    cs:__imp_HeapFree
0x18000340e  xor     eax, eax
0x180003410  mov     [rsi+20h], eax
0x180003413  mov     [rsi+18h], rax
0x180003417  add     rsp, 28h
0x18000341b  pop     rdi
0x18000341c  pop     rsi
0x18000341d  pop     rbp
0x18000341e  pop     rbx
0x18000341f  retn
```
