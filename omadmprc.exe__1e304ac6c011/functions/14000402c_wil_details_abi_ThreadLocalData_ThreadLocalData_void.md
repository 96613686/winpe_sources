# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x14000402c`
- end: `0x1400040c1`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400039c8`

## callees

- `0x14000402c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000408e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000408e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004065`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400040a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004065`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400040a2`

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
0x14000402c  push    rbx
0x14000402e  push    rbp
0x14000402f  push    rsi
0x140004030  push    rdi
0x140004031  sub     rsp, 28h
0x140004035  movzx   eax, word ptr [rcx+20h]
0x140004039  mov     rsi, rcx
0x14000403c  mov     rdi, [rcx+18h]
0x140004040  lea     rbp, [rax+rax*4]
0x140004044  shl     rbp, 4
0x140004048  add     rbp, rdi
0x14000404b  jmp     short loc_140004085
0x14000404d  mov     rbx, [rdi+40h]
0x140004051  call    cs:__imp_GetProcessHeap
0x140004058  nop     dword ptr [rax+rax+00h]
0x14000405d  mov     r8, rbx; lpMem
0x140004060  xor     edx, edx; dwFlags
0x140004062  mov     rcx, rax; hHeap
0x140004065  call    cs:__imp_HeapFree
0x14000406c  nop     dword ptr [rax+rax+00h]
0x140004071  mov     qword ptr [rdi+40h], 0
0x140004079  mov     qword ptr [rdi+48h], 0
0x140004081  add     rdi, 50h ; 'P'
0x140004085  cmp     rdi, rbp
0x140004088  jnz     short loc_14000404D
0x14000408a  mov     rbx, [rsi+18h]
0x14000408e  call    cs:__imp_GetProcessHeap
0x140004095  nop     dword ptr [rax+rax+00h]
0x14000409a  mov     r8, rbx; lpMem
0x14000409d  xor     edx, edx; dwFlags
0x14000409f  mov     rcx, rax; hHeap
0x1400040a2  call    cs:__imp_HeapFree
0x1400040a9  nop     dword ptr [rax+rax+00h]
0x1400040ae  xor     eax, eax
0x1400040b0  mov     [rsi+20h], eax
0x1400040b3  mov     [rsi+18h], rax
0x1400040b7  add     rsp, 28h
0x1400040bb  pop     rdi
0x1400040bc  pop     rsi
0x1400040bd  pop     rbp
0x1400040be  pop     rbx
0x1400040bf  retn
```
