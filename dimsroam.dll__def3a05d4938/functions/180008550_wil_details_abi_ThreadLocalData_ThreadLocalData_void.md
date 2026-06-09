# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180008550`
- end: `0x1800085cc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800080c4`

## callees

- `0x180008550`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008583`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800085b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008583`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800085b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008575`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008575`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085a6`

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
0x180008550  push    rbx
0x180008552  push    rbp
0x180008553  push    rsi
0x180008554  push    rdi
0x180008555  sub     rsp, 28h
0x180008559  movzx   eax, word ptr [rcx+20h]
0x18000855d  mov     rsi, rcx
0x180008560  mov     rdi, [rcx+18h]
0x180008564  lea     rbp, [rax+rax*4]
0x180008568  shl     rbp, 4
0x18000856c  add     rbp, rdi
0x18000856f  jmp     short loc_18000859D
0x180008571  mov     rbx, [rdi+40h]
0x180008575  call    cs:__imp_GetProcessHeap
0x18000857b  mov     r8, rbx; lpMem
0x18000857e  xor     edx, edx; dwFlags
0x180008580  mov     rcx, rax; hHeap
0x180008583  call    cs:__imp_HeapFree
0x180008589  mov     qword ptr [rdi+40h], 0
0x180008591  mov     qword ptr [rdi+48h], 0
0x180008599  add     rdi, 50h ; 'P'
0x18000859d  cmp     rdi, rbp
0x1800085a0  jnz     short loc_180008571
0x1800085a2  mov     rbx, [rsi+18h]
0x1800085a6  call    cs:__imp_GetProcessHeap
0x1800085ac  mov     r8, rbx; lpMem
0x1800085af  xor     edx, edx; dwFlags
0x1800085b1  mov     rcx, rax; hHeap
0x1800085b4  call    cs:__imp_HeapFree
0x1800085ba  xor     eax, eax
0x1800085bc  mov     [rsi+20h], eax
0x1800085bf  mov     [rsi+18h], rax
0x1800085c3  add     rsp, 28h
0x1800085c7  pop     rdi
0x1800085c8  pop     rsi
0x1800085c9  pop     rbp
0x1800085ca  pop     rbx
0x1800085cb  retn
```
