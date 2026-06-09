# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003838`
- end: `0x1800038b4`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003104`

## callees

- `0x180003838`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000386b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000389c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000386b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000389c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000385d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000388e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000385d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000388e`

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
0x180003838  push    rbx
0x18000383a  push    rbp
0x18000383b  push    rsi
0x18000383c  push    rdi
0x18000383d  sub     rsp, 28h
0x180003841  movzx   eax, word ptr [rcx+20h]
0x180003845  mov     rsi, rcx
0x180003848  mov     rdi, [rcx+18h]
0x18000384c  lea     rbp, [rax+rax*4]
0x180003850  shl     rbp, 4
0x180003854  add     rbp, rdi
0x180003857  jmp     short loc_180003885
0x180003859  mov     rbx, [rdi+40h]
0x18000385d  call    cs:__imp_GetProcessHeap
0x180003863  mov     r8, rbx; lpMem
0x180003866  xor     edx, edx; dwFlags
0x180003868  mov     rcx, rax; hHeap
0x18000386b  call    cs:__imp_HeapFree
0x180003871  mov     qword ptr [rdi+40h], 0
0x180003879  mov     qword ptr [rdi+48h], 0
0x180003881  add     rdi, 50h ; 'P'
0x180003885  cmp     rdi, rbp
0x180003888  jnz     short loc_180003859
0x18000388a  mov     rbx, [rsi+18h]
0x18000388e  call    cs:__imp_GetProcessHeap
0x180003894  mov     r8, rbx; lpMem
0x180003897  xor     edx, edx; dwFlags
0x180003899  mov     rcx, rax; hHeap
0x18000389c  call    cs:__imp_HeapFree
0x1800038a2  xor     eax, eax
0x1800038a4  mov     [rsi+20h], eax
0x1800038a7  mov     [rsi+18h], rax
0x1800038ab  add     rsp, 28h
0x1800038af  pop     rdi
0x1800038b0  pop     rsi
0x1800038b1  pop     rbp
0x1800038b2  pop     rbx
0x1800038b3  retn
```
