# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140002d14`
- end: `0x140002d90`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002b08`

## callees

- `0x140002d14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002d47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002d78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002d47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002d78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002d39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002d6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002d39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002d6a`

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
0x140002d14  push    rbx
0x140002d16  push    rbp
0x140002d17  push    rsi
0x140002d18  push    rdi
0x140002d19  sub     rsp, 28h
0x140002d1d  movzx   eax, word ptr [rcx+20h]
0x140002d21  mov     rsi, rcx
0x140002d24  mov     rdi, [rcx+18h]
0x140002d28  lea     rbp, [rax+rax*4]
0x140002d2c  shl     rbp, 4
0x140002d30  add     rbp, rdi
0x140002d33  jmp     short loc_140002D61
0x140002d35  mov     rbx, [rdi+40h]
0x140002d39  call    cs:__imp_GetProcessHeap
0x140002d3f  mov     r8, rbx; lpMem
0x140002d42  xor     edx, edx; dwFlags
0x140002d44  mov     rcx, rax; hHeap
0x140002d47  call    cs:__imp_HeapFree
0x140002d4d  mov     qword ptr [rdi+40h], 0
0x140002d55  mov     qword ptr [rdi+48h], 0
0x140002d5d  add     rdi, 50h ; 'P'
0x140002d61  cmp     rdi, rbp
0x140002d64  jnz     short loc_140002D35
0x140002d66  mov     rbx, [rsi+18h]
0x140002d6a  call    cs:__imp_GetProcessHeap
0x140002d70  mov     r8, rbx; lpMem
0x140002d73  xor     edx, edx; dwFlags
0x140002d75  mov     rcx, rax; hHeap
0x140002d78  call    cs:__imp_HeapFree
0x140002d7e  xor     eax, eax
0x140002d80  mov     [rsi+20h], eax
0x140002d83  mov     [rsi+18h], rax
0x140002d87  add     rsp, 28h
0x140002d8b  pop     rdi
0x140002d8c  pop     rsi
0x140002d8d  pop     rbp
0x140002d8e  pop     rbx
0x140002d8f  retn
```
