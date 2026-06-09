# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800033d4`
- end: `0x180003464`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800032f4`

## callees

- `0x1800032bc`
- `0x1800033d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003404`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003437`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003404`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003437`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003412`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003445`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003412`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003445`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 i; // rdi
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  void *v5; // rbx
  HANDLE v6; // rax
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF

  wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(v7, *((_QWORD *)this + 3));
  for ( i = v7[0]; i != v7[1]; i += 80 )
  {
    v3 = *(void **)(i + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *(_QWORD *)(i + 64) = 0;
    *(_QWORD *)(i + 72) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 3);
  v6 = GetProcessHeap();
  HeapFree(v6, 0, v5);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x1800033d4  mov     [rsp+arg_0], rbx
0x1800033d9  mov     [rsp+arg_8], rsi
0x1800033de  push    rdi
0x1800033df  sub     rsp, 30h
0x1800033e3  movzx   r8d, word ptr [rcx+20h]
0x1800033e8  mov     rsi, rcx
0x1800033eb  mov     rdx, [rcx+18h]
0x1800033ef  lea     rcx, [rsp+38h+var_18]
0x1800033f4  call    ??$make_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@wil@@YA?AV?$pointer_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@details@0@PEAUThreadLocalFailureInfo@details_abi@0@_K@Z; wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(wil::details_abi::ThreadLocalFailureInfo *,unsigned __int64)
0x1800033f9  mov     rdi, [rsp+38h+var_18]
0x1800033fe  jmp     short loc_18000342C
0x180003400  mov     rbx, [rdi+40h]
0x180003404  call    cs:__imp_GetProcessHeap
0x18000340a  mov     r8, rbx; lpMem
0x18000340d  xor     edx, edx; dwFlags
0x18000340f  mov     rcx, rax; hHeap
0x180003412  call    cs:__imp_HeapFree
0x180003418  mov     qword ptr [rdi+40h], 0
0x180003420  mov     qword ptr [rdi+48h], 0
0x180003428  add     rdi, 50h ; 'P'
0x18000342c  cmp     rdi, [rsp+38h+var_10]
0x180003431  jnz     short loc_180003400
0x180003433  mov     rbx, [rsi+18h]
0x180003437  call    cs:__imp_GetProcessHeap
0x18000343d  mov     r8, rbx; lpMem
0x180003440  xor     edx, edx; dwFlags
0x180003442  mov     rcx, rax; hHeap
0x180003445  call    cs:__imp_HeapFree
0x18000344b  mov     rbx, [rsp+38h+arg_0]
0x180003450  xor     eax, eax
0x180003452  mov     [rsi+20h], eax
0x180003455  mov     [rsi+18h], rax
0x180003459  mov     rsi, [rsp+38h+arg_8]
0x18000345e  add     rsp, 30h
0x180003462  pop     rdi
0x180003463  retn
```
