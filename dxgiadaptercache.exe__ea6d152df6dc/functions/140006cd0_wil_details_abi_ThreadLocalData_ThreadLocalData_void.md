# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140006cd0`
- end: `0x140006d4c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140006044`

## callees

- `0x140006cd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006cf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006d26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006cf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006d26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d34`

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
0x140006cd0  push    rbx
0x140006cd2  push    rbp
0x140006cd3  push    rsi
0x140006cd4  push    rdi
0x140006cd5  sub     rsp, 28h
0x140006cd9  movzx   eax, word ptr [rcx+20h]
0x140006cdd  mov     rsi, rcx
0x140006ce0  mov     rdi, [rcx+18h]
0x140006ce4  lea     rbp, [rax+rax*4]
0x140006ce8  shl     rbp, 4
0x140006cec  add     rbp, rdi
0x140006cef  jmp     short loc_140006D1D
0x140006cf1  mov     rbx, [rdi+40h]
0x140006cf5  call    cs:__imp_GetProcessHeap
0x140006cfb  mov     r8, rbx; lpMem
0x140006cfe  xor     edx, edx; dwFlags
0x140006d00  mov     rcx, rax; hHeap
0x140006d03  call    cs:__imp_HeapFree
0x140006d09  mov     qword ptr [rdi+40h], 0
0x140006d11  mov     qword ptr [rdi+48h], 0
0x140006d19  add     rdi, 50h ; 'P'
0x140006d1d  cmp     rdi, rbp
0x140006d20  jnz     short loc_140006CF1
0x140006d22  mov     rbx, [rsi+18h]
0x140006d26  call    cs:__imp_GetProcessHeap
0x140006d2c  mov     r8, rbx; lpMem
0x140006d2f  xor     edx, edx; dwFlags
0x140006d31  mov     rcx, rax; hHeap
0x140006d34  call    cs:__imp_HeapFree
0x140006d3a  xor     eax, eax
0x140006d3c  mov     [rsi+20h], eax
0x140006d3f  mov     [rsi+18h], rax
0x140006d43  add     rsp, 28h
0x140006d47  pop     rdi
0x140006d48  pop     rsi
0x140006d49  pop     rbp
0x140006d4a  pop     rbx
0x140006d4b  retn
```
