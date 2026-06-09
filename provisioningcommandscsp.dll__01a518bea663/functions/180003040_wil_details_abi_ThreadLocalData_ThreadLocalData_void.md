# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003040`
- end: `0x1800030bc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e90`

## callees

- `0x180003040`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003073`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800030a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003073`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800030a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003065`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003096`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003065`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003096`

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
0x180003040  push    rbx
0x180003042  push    rbp
0x180003043  push    rsi
0x180003044  push    rdi
0x180003045  sub     rsp, 28h
0x180003049  movzx   eax, word ptr [rcx+20h]
0x18000304d  mov     rsi, rcx
0x180003050  mov     rdi, [rcx+18h]
0x180003054  lea     rbp, [rax+rax*4]
0x180003058  shl     rbp, 4
0x18000305c  add     rbp, rdi
0x18000305f  jmp     short loc_18000308D
0x180003061  mov     rbx, [rdi+40h]
0x180003065  call    cs:__imp_GetProcessHeap
0x18000306b  mov     r8, rbx; lpMem
0x18000306e  xor     edx, edx; dwFlags
0x180003070  mov     rcx, rax; hHeap
0x180003073  call    cs:__imp_HeapFree
0x180003079  mov     qword ptr [rdi+40h], 0
0x180003081  mov     qword ptr [rdi+48h], 0
0x180003089  add     rdi, 50h ; 'P'
0x18000308d  cmp     rdi, rbp
0x180003090  jnz     short loc_180003061
0x180003092  mov     rbx, [rsi+18h]
0x180003096  call    cs:__imp_GetProcessHeap
0x18000309c  mov     r8, rbx; lpMem
0x18000309f  xor     edx, edx; dwFlags
0x1800030a1  mov     rcx, rax; hHeap
0x1800030a4  call    cs:__imp_HeapFree
0x1800030aa  xor     eax, eax
0x1800030ac  mov     [rsi+20h], eax
0x1800030af  mov     [rsi+18h], rax
0x1800030b3  add     rsp, 28h
0x1800030b7  pop     rdi
0x1800030b8  pop     rsi
0x1800030b9  pop     rbp
0x1800030ba  pop     rbx
0x1800030bb  retn
```
