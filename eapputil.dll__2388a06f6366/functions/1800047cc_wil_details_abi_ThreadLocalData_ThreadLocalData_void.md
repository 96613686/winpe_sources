# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800047cc`
- end: `0x180004848`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004538`

## callees

- `0x1800047cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004822`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004822`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004830`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004830`

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
0x1800047cc  push    rbx
0x1800047ce  push    rbp
0x1800047cf  push    rsi
0x1800047d0  push    rdi
0x1800047d1  sub     rsp, 28h
0x1800047d5  movzx   eax, word ptr [rcx+20h]
0x1800047d9  mov     rsi, rcx
0x1800047dc  mov     rdi, [rcx+18h]
0x1800047e0  lea     rbp, [rax+rax*4]
0x1800047e4  shl     rbp, 4
0x1800047e8  add     rbp, rdi
0x1800047eb  jmp     short loc_180004819
0x1800047ed  mov     rbx, [rdi+40h]
0x1800047f1  call    cs:__imp_GetProcessHeap
0x1800047f7  mov     r8, rbx; lpMem
0x1800047fa  xor     edx, edx; dwFlags
0x1800047fc  mov     rcx, rax; hHeap
0x1800047ff  call    cs:__imp_HeapFree
0x180004805  mov     qword ptr [rdi+40h], 0
0x18000480d  mov     qword ptr [rdi+48h], 0
0x180004815  add     rdi, 50h ; 'P'
0x180004819  cmp     rdi, rbp
0x18000481c  jnz     short loc_1800047ED
0x18000481e  mov     rbx, [rsi+18h]
0x180004822  call    cs:__imp_GetProcessHeap
0x180004828  mov     r8, rbx; lpMem
0x18000482b  xor     edx, edx; dwFlags
0x18000482d  mov     rcx, rax; hHeap
0x180004830  call    cs:__imp_HeapFree
0x180004836  xor     eax, eax
0x180004838  mov     [rsi+20h], eax
0x18000483b  mov     [rsi+18h], rax
0x18000483f  add     rsp, 28h
0x180004843  pop     rdi
0x180004844  pop     rsi
0x180004845  pop     rbp
0x180004846  pop     rbx
0x180004847  retn
```
