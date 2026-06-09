# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180008ee4`
- end: `0x180008f60`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008e18`

## callees

- `0x180008ee4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f3a`

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
0x180008ee4  push    rbx
0x180008ee6  push    rbp
0x180008ee7  push    rsi
0x180008ee8  push    rdi
0x180008ee9  sub     rsp, 28h
0x180008eed  movzx   eax, word ptr [rcx+20h]
0x180008ef1  mov     rsi, rcx
0x180008ef4  mov     rdi, [rcx+18h]
0x180008ef8  lea     rbp, [rax+rax*4]
0x180008efc  shl     rbp, 4
0x180008f00  add     rbp, rdi
0x180008f03  jmp     short loc_180008F31
0x180008f05  mov     rbx, [rdi+40h]
0x180008f09  call    cs:__imp_GetProcessHeap
0x180008f0f  mov     r8, rbx; lpMem
0x180008f12  xor     edx, edx; dwFlags
0x180008f14  mov     rcx, rax; hHeap
0x180008f17  call    cs:__imp_HeapFree
0x180008f1d  mov     qword ptr [rdi+40h], 0
0x180008f25  mov     qword ptr [rdi+48h], 0
0x180008f2d  add     rdi, 50h ; 'P'
0x180008f31  cmp     rdi, rbp
0x180008f34  jnz     short loc_180008F05
0x180008f36  mov     rbx, [rsi+18h]
0x180008f3a  call    cs:__imp_GetProcessHeap
0x180008f40  mov     r8, rbx; lpMem
0x180008f43  xor     edx, edx; dwFlags
0x180008f45  mov     rcx, rax; hHeap
0x180008f48  call    cs:__imp_HeapFree
0x180008f4e  xor     eax, eax
0x180008f50  mov     [rsi+20h], eax
0x180008f53  mov     [rsi+18h], rax
0x180008f57  add     rsp, 28h
0x180008f5b  pop     rdi
0x180008f5c  pop     rsi
0x180008f5d  pop     rbp
0x180008f5e  pop     rbx
0x180008f5f  retn
```
