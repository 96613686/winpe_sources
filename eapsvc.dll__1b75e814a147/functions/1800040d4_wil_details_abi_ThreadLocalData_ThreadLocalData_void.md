# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800040d4`
- end: `0x180004150`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800038c4`

## callees

- `0x1800040d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004107`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004138`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004107`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004138`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000412a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000412a`

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
0x1800040d4  push    rbx
0x1800040d6  push    rbp
0x1800040d7  push    rsi
0x1800040d8  push    rdi
0x1800040d9  sub     rsp, 28h
0x1800040dd  movzx   eax, word ptr [rcx+20h]
0x1800040e1  mov     rsi, rcx
0x1800040e4  mov     rdi, [rcx+18h]
0x1800040e8  lea     rbp, [rax+rax*4]
0x1800040ec  shl     rbp, 4
0x1800040f0  add     rbp, rdi
0x1800040f3  jmp     short loc_180004121
0x1800040f5  mov     rbx, [rdi+40h]
0x1800040f9  call    cs:__imp_GetProcessHeap
0x1800040ff  mov     r8, rbx; lpMem
0x180004102  xor     edx, edx; dwFlags
0x180004104  mov     rcx, rax; hHeap
0x180004107  call    cs:__imp_HeapFree
0x18000410d  mov     qword ptr [rdi+40h], 0
0x180004115  mov     qword ptr [rdi+48h], 0
0x18000411d  add     rdi, 50h ; 'P'
0x180004121  cmp     rdi, rbp
0x180004124  jnz     short loc_1800040F5
0x180004126  mov     rbx, [rsi+18h]
0x18000412a  call    cs:__imp_GetProcessHeap
0x180004130  mov     r8, rbx; lpMem
0x180004133  xor     edx, edx; dwFlags
0x180004135  mov     rcx, rax; hHeap
0x180004138  call    cs:__imp_HeapFree
0x18000413e  xor     eax, eax
0x180004140  mov     [rsi+20h], eax
0x180004143  mov     [rsi+18h], rax
0x180004147  add     rsp, 28h
0x18000414b  pop     rdi
0x18000414c  pop     rsi
0x18000414d  pop     rbp
0x18000414e  pop     rbx
0x18000414f  retn
```
