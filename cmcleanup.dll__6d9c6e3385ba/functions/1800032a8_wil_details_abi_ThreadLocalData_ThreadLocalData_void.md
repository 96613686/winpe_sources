# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800032a8`
- end: `0x180003324`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003088`

## callees

- `0x1800032a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000330c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000330c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032fe`

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
0x1800032a8  push    rbx
0x1800032aa  push    rbp
0x1800032ab  push    rsi
0x1800032ac  push    rdi
0x1800032ad  sub     rsp, 28h
0x1800032b1  movzx   eax, word ptr [rcx+20h]
0x1800032b5  mov     rsi, rcx
0x1800032b8  mov     rdi, [rcx+18h]
0x1800032bc  lea     rbp, [rax+rax*4]
0x1800032c0  shl     rbp, 4
0x1800032c4  add     rbp, rdi
0x1800032c7  jmp     short loc_1800032F5
0x1800032c9  mov     rbx, [rdi+40h]
0x1800032cd  call    cs:__imp_GetProcessHeap
0x1800032d3  mov     r8, rbx; lpMem
0x1800032d6  xor     edx, edx; dwFlags
0x1800032d8  mov     rcx, rax; hHeap
0x1800032db  call    cs:__imp_HeapFree
0x1800032e1  mov     qword ptr [rdi+40h], 0
0x1800032e9  mov     qword ptr [rdi+48h], 0
0x1800032f1  add     rdi, 50h ; 'P'
0x1800032f5  cmp     rdi, rbp
0x1800032f8  jnz     short loc_1800032C9
0x1800032fa  mov     rbx, [rsi+18h]
0x1800032fe  call    cs:__imp_GetProcessHeap
0x180003304  mov     r8, rbx; lpMem
0x180003307  xor     edx, edx; dwFlags
0x180003309  mov     rcx, rax; hHeap
0x18000330c  call    cs:__imp_HeapFree
0x180003312  xor     eax, eax
0x180003314  mov     [rsi+20h], eax
0x180003317  mov     [rsi+18h], rax
0x18000331b  add     rsp, 28h
0x18000331f  pop     rdi
0x180003320  pop     rsi
0x180003321  pop     rbp
0x180003322  pop     rbx
0x180003323  retn
```
