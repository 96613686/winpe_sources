# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800043e0`
- end: `0x18000445c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000403c`

## callees

- `0x1800043e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004413`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004444`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004413`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004444`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004405`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004436`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004405`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004436`

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
0x1800043e0  push    rbx
0x1800043e2  push    rbp
0x1800043e3  push    rsi
0x1800043e4  push    rdi
0x1800043e5  sub     rsp, 28h
0x1800043e9  movzx   eax, word ptr [rcx+20h]
0x1800043ed  mov     rsi, rcx
0x1800043f0  mov     rdi, [rcx+18h]
0x1800043f4  lea     rbp, [rax+rax*4]
0x1800043f8  shl     rbp, 4
0x1800043fc  add     rbp, rdi
0x1800043ff  jmp     short loc_18000442D
0x180004401  mov     rbx, [rdi+40h]
0x180004405  call    cs:__imp_GetProcessHeap
0x18000440b  mov     r8, rbx; lpMem
0x18000440e  xor     edx, edx; dwFlags
0x180004410  mov     rcx, rax; hHeap
0x180004413  call    cs:__imp_HeapFree
0x180004419  mov     qword ptr [rdi+40h], 0
0x180004421  mov     qword ptr [rdi+48h], 0
0x180004429  add     rdi, 50h ; 'P'
0x18000442d  cmp     rdi, rbp
0x180004430  jnz     short loc_180004401
0x180004432  mov     rbx, [rsi+18h]
0x180004436  call    cs:__imp_GetProcessHeap
0x18000443c  mov     r8, rbx; lpMem
0x18000443f  xor     edx, edx; dwFlags
0x180004441  mov     rcx, rax; hHeap
0x180004444  call    cs:__imp_HeapFree
0x18000444a  xor     eax, eax
0x18000444c  mov     [rsi+20h], eax
0x18000444f  mov     [rsi+18h], rax
0x180004453  add     rsp, 28h
0x180004457  pop     rdi
0x180004458  pop     rsi
0x180004459  pop     rbp
0x18000445a  pop     rbx
0x18000445b  retn
```
