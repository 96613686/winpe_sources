# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x18000c768`
- end: `0x18000c7e4`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c2fc`

## callees

- `0x18000c768`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c79b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c79b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c78d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c78d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7be`

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
0x18000c768  push    rbx
0x18000c76a  push    rbp
0x18000c76b  push    rsi
0x18000c76c  push    rdi
0x18000c76d  sub     rsp, 28h
0x18000c771  mov     rsi, rcx
0x18000c774  mov     rdi, [rcx+18h]
0x18000c778  movzx   eax, word ptr [rcx+20h]
0x18000c77c  lea     rbp, [rax+rax*4]
0x18000c780  shl     rbp, 4
0x18000c784  add     rbp, rdi
0x18000c787  jmp     short loc_18000C7B5
0x18000c789  mov     rbx, [rdi+40h]
0x18000c78d  call    cs:__imp_GetProcessHeap
0x18000c793  mov     r8, rbx; lpMem
0x18000c796  xor     edx, edx; dwFlags
0x18000c798  mov     rcx, rax; hHeap
0x18000c79b  call    cs:__imp_HeapFree
0x18000c7a1  mov     qword ptr [rdi+40h], 0
0x18000c7a9  mov     qword ptr [rdi+48h], 0
0x18000c7b1  add     rdi, 50h ; 'P'
0x18000c7b5  cmp     rdi, rbp
0x18000c7b8  jnz     short loc_18000C789
0x18000c7ba  mov     rbx, [rsi+18h]
0x18000c7be  call    cs:__imp_GetProcessHeap
0x18000c7c4  mov     r8, rbx; lpMem
0x18000c7c7  xor     edx, edx; dwFlags
0x18000c7c9  mov     rcx, rax; hHeap
0x18000c7cc  call    cs:__imp_HeapFree
0x18000c7d2  xor     eax, eax
0x18000c7d4  mov     [rsi+20h], eax
0x18000c7d7  mov     [rsi+18h], rax
0x18000c7db  add     rsp, 28h
0x18000c7df  pop     rdi
0x18000c7e0  pop     rsi
0x18000c7e1  pop     rbp
0x18000c7e2  pop     rbx
0x18000c7e3  retn
```
