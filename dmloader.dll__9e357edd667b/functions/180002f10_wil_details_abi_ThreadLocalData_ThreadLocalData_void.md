# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180002f10`
- end: `0x180002f8c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a84`

## callees

- `0x180002f10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f66`

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
0x180002f10  push    rbx
0x180002f12  push    rbp
0x180002f13  push    rsi
0x180002f14  push    rdi
0x180002f15  sub     rsp, 28h
0x180002f19  movzx   eax, word ptr [rcx+20h]
0x180002f1d  mov     rsi, rcx
0x180002f20  mov     rdi, [rcx+18h]
0x180002f24  lea     rbp, [rax+rax*4]
0x180002f28  shl     rbp, 4
0x180002f2c  add     rbp, rdi
0x180002f2f  jmp     short loc_180002F5D
0x180002f31  mov     rbx, [rdi+40h]
0x180002f35  call    cs:__imp_GetProcessHeap
0x180002f3b  mov     r8, rbx; lpMem
0x180002f3e  xor     edx, edx; dwFlags
0x180002f40  mov     rcx, rax; hHeap
0x180002f43  call    cs:__imp_HeapFree
0x180002f49  mov     qword ptr [rdi+40h], 0
0x180002f51  mov     qword ptr [rdi+48h], 0
0x180002f59  add     rdi, 50h ; 'P'
0x180002f5d  cmp     rdi, rbp
0x180002f60  jnz     short loc_180002F31
0x180002f62  mov     rbx, [rsi+18h]
0x180002f66  call    cs:__imp_GetProcessHeap
0x180002f6c  mov     r8, rbx; lpMem
0x180002f6f  xor     edx, edx; dwFlags
0x180002f71  mov     rcx, rax; hHeap
0x180002f74  call    cs:__imp_HeapFree
0x180002f7a  xor     eax, eax
0x180002f7c  mov     [rsi+20h], eax
0x180002f7f  mov     [rsi+18h], rax
0x180002f83  add     rsp, 28h
0x180002f87  pop     rdi
0x180002f88  pop     rsi
0x180002f89  pop     rbp
0x180002f8a  pop     rbx
0x180002f8b  retn
```
