# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180002d38`
- end: `0x180002db4`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b80`

## callees

- `0x180002d38`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d8e`

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
0x180002d38  push    rbx
0x180002d3a  push    rbp
0x180002d3b  push    rsi
0x180002d3c  push    rdi
0x180002d3d  sub     rsp, 28h
0x180002d41  movzx   eax, word ptr [rcx+20h]
0x180002d45  mov     rsi, rcx
0x180002d48  mov     rdi, [rcx+18h]
0x180002d4c  lea     rbp, [rax+rax*4]
0x180002d50  shl     rbp, 4
0x180002d54  add     rbp, rdi
0x180002d57  jmp     short loc_180002D85
0x180002d59  mov     rbx, [rdi+40h]
0x180002d5d  call    cs:__imp_GetProcessHeap
0x180002d63  mov     r8, rbx; lpMem
0x180002d66  xor     edx, edx; dwFlags
0x180002d68  mov     rcx, rax; hHeap
0x180002d6b  call    cs:__imp_HeapFree
0x180002d71  mov     qword ptr [rdi+40h], 0
0x180002d79  mov     qword ptr [rdi+48h], 0
0x180002d81  add     rdi, 50h ; 'P'
0x180002d85  cmp     rdi, rbp
0x180002d88  jnz     short loc_180002D59
0x180002d8a  mov     rbx, [rsi+18h]
0x180002d8e  call    cs:__imp_GetProcessHeap
0x180002d94  mov     r8, rbx; lpMem
0x180002d97  xor     edx, edx; dwFlags
0x180002d99  mov     rcx, rax; hHeap
0x180002d9c  call    cs:__imp_HeapFree
0x180002da2  xor     eax, eax
0x180002da4  mov     [rsi+20h], eax
0x180002da7  mov     [rsi+18h], rax
0x180002dab  add     rsp, 28h
0x180002daf  pop     rdi
0x180002db0  pop     rsi
0x180002db1  pop     rbp
0x180002db2  pop     rbx
0x180002db3  retn
```
