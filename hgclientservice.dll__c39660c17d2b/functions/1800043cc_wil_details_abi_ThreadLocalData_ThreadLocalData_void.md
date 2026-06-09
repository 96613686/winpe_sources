# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800043cc`
- end: `0x180004448`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800041a8`

## callees

- `0x1800043cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004430`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004430`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004422`

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
0x1800043cc  push    rbx
0x1800043ce  push    rbp
0x1800043cf  push    rsi
0x1800043d0  push    rdi
0x1800043d1  sub     rsp, 28h
0x1800043d5  movzx   eax, word ptr [rcx+20h]
0x1800043d9  mov     rsi, rcx
0x1800043dc  mov     rdi, [rcx+18h]
0x1800043e0  lea     rbp, [rax+rax*4]
0x1800043e4  shl     rbp, 4
0x1800043e8  add     rbp, rdi
0x1800043eb  jmp     short loc_180004419
0x1800043ed  mov     rbx, [rdi+40h]
0x1800043f1  call    cs:__imp_GetProcessHeap
0x1800043f7  mov     r8, rbx; lpMem
0x1800043fa  xor     edx, edx; dwFlags
0x1800043fc  mov     rcx, rax; hHeap
0x1800043ff  call    cs:__imp_HeapFree
0x180004405  mov     qword ptr [rdi+40h], 0
0x18000440d  mov     qword ptr [rdi+48h], 0
0x180004415  add     rdi, 50h ; 'P'
0x180004419  cmp     rdi, rbp
0x18000441c  jnz     short loc_1800043ED
0x18000441e  mov     rbx, [rsi+18h]
0x180004422  call    cs:__imp_GetProcessHeap
0x180004428  mov     r8, rbx; lpMem
0x18000442b  xor     edx, edx; dwFlags
0x18000442d  mov     rcx, rax; hHeap
0x180004430  call    cs:__imp_HeapFree
0x180004436  xor     eax, eax
0x180004438  mov     [rsi+20h], eax
0x18000443b  mov     [rsi+18h], rax
0x18000443f  add     rsp, 28h
0x180004443  pop     rdi
0x180004444  pop     rsi
0x180004445  pop     rbp
0x180004446  pop     rbx
0x180004447  retn
```
