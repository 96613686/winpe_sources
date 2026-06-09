# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x18000a5b0`
- end: `0x18000a645`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009dec`

## callees

- `0x18000a5b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a626`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a626`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a612`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a612`

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
0x18000a5b0  push    rbx
0x18000a5b2  push    rbp
0x18000a5b3  push    rsi
0x18000a5b4  push    rdi
0x18000a5b5  sub     rsp, 28h
0x18000a5b9  movzx   eax, word ptr [rcx+20h]
0x18000a5bd  mov     rsi, rcx
0x18000a5c0  mov     rdi, [rcx+18h]
0x18000a5c4  lea     rbp, [rax+rax*4]
0x18000a5c8  shl     rbp, 4
0x18000a5cc  add     rbp, rdi
0x18000a5cf  jmp     short loc_18000A609
0x18000a5d1  mov     rbx, [rdi+40h]
0x18000a5d5  call    cs:__imp_GetProcessHeap
0x18000a5dc  nop     dword ptr [rax+rax+00h]
0x18000a5e1  mov     r8, rbx; lpMem
0x18000a5e4  xor     edx, edx; dwFlags
0x18000a5e6  mov     rcx, rax; hHeap
0x18000a5e9  call    cs:__imp_HeapFree
0x18000a5f0  nop     dword ptr [rax+rax+00h]
0x18000a5f5  mov     qword ptr [rdi+40h], 0
0x18000a5fd  mov     qword ptr [rdi+48h], 0
0x18000a605  add     rdi, 50h ; 'P'
0x18000a609  cmp     rdi, rbp
0x18000a60c  jnz     short loc_18000A5D1
0x18000a60e  mov     rbx, [rsi+18h]
0x18000a612  call    cs:__imp_GetProcessHeap
0x18000a619  nop     dword ptr [rax+rax+00h]
0x18000a61e  mov     r8, rbx; lpMem
0x18000a621  xor     edx, edx; dwFlags
0x18000a623  mov     rcx, rax; hHeap
0x18000a626  call    cs:__imp_HeapFree
0x18000a62d  nop     dword ptr [rax+rax+00h]
0x18000a632  xor     eax, eax
0x18000a634  mov     [rsi+20h], eax
0x18000a637  mov     [rsi+18h], rax
0x18000a63b  add     rsp, 28h
0x18000a63f  pop     rdi
0x18000a640  pop     rsi
0x18000a641  pop     rbp
0x18000a642  pop     rbx
0x18000a643  retn
```
