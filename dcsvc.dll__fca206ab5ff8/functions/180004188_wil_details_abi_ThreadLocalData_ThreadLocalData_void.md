# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180004188`
- end: `0x180004204`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a54`

## callees

- `0x180004188`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041ec`

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
0x180004188  push    rbx
0x18000418a  push    rbp
0x18000418b  push    rsi
0x18000418c  push    rdi
0x18000418d  sub     rsp, 28h
0x180004191  movzx   eax, word ptr [rcx+20h]
0x180004195  mov     rsi, rcx
0x180004198  mov     rdi, [rcx+18h]
0x18000419c  lea     rbp, [rax+rax*4]
0x1800041a0  shl     rbp, 4
0x1800041a4  add     rbp, rdi
0x1800041a7  jmp     short loc_1800041D5
0x1800041a9  mov     rbx, [rdi+40h]
0x1800041ad  call    cs:__imp_GetProcessHeap
0x1800041b3  mov     r8, rbx; lpMem
0x1800041b6  xor     edx, edx; dwFlags
0x1800041b8  mov     rcx, rax; hHeap
0x1800041bb  call    cs:__imp_HeapFree
0x1800041c1  mov     qword ptr [rdi+40h], 0
0x1800041c9  mov     qword ptr [rdi+48h], 0
0x1800041d1  add     rdi, 50h ; 'P'
0x1800041d5  cmp     rdi, rbp
0x1800041d8  jnz     short loc_1800041A9
0x1800041da  mov     rbx, [rsi+18h]
0x1800041de  call    cs:__imp_GetProcessHeap
0x1800041e4  mov     r8, rbx; lpMem
0x1800041e7  xor     edx, edx; dwFlags
0x1800041e9  mov     rcx, rax; hHeap
0x1800041ec  call    cs:__imp_HeapFree
0x1800041f2  xor     eax, eax
0x1800041f4  mov     [rsi+20h], eax
0x1800041f7  mov     [rsi+18h], rax
0x1800041fb  add     rsp, 28h
0x1800041ff  pop     rdi
0x180004200  pop     rsi
0x180004201  pop     rbp
0x180004202  pop     rbx
0x180004203  retn
```
