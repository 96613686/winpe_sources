# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180004610`
- end: `0x18000468c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e94`

## callees

- `0x180004610`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004643`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004674`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004643`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004674`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004635`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004666`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004635`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004666`

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
0x180004610  push    rbx
0x180004612  push    rbp
0x180004613  push    rsi
0x180004614  push    rdi
0x180004615  sub     rsp, 28h
0x180004619  movzx   eax, word ptr [rcx+20h]
0x18000461d  mov     rsi, rcx
0x180004620  mov     rdi, [rcx+18h]
0x180004624  lea     rbp, [rax+rax*4]
0x180004628  shl     rbp, 4
0x18000462c  add     rbp, rdi
0x18000462f  jmp     short loc_18000465D
0x180004631  mov     rbx, [rdi+40h]
0x180004635  call    cs:__imp_GetProcessHeap
0x18000463b  mov     r8, rbx; lpMem
0x18000463e  xor     edx, edx; dwFlags
0x180004640  mov     rcx, rax; hHeap
0x180004643  call    cs:__imp_HeapFree
0x180004649  mov     qword ptr [rdi+40h], 0
0x180004651  mov     qword ptr [rdi+48h], 0
0x180004659  add     rdi, 50h ; 'P'
0x18000465d  cmp     rdi, rbp
0x180004660  jnz     short loc_180004631
0x180004662  mov     rbx, [rsi+18h]
0x180004666  call    cs:__imp_GetProcessHeap
0x18000466c  mov     r8, rbx; lpMem
0x18000466f  xor     edx, edx; dwFlags
0x180004671  mov     rcx, rax; hHeap
0x180004674  call    cs:__imp_HeapFree
0x18000467a  xor     eax, eax
0x18000467c  mov     [rsi+20h], eax
0x18000467f  mov     [rsi+18h], rax
0x180004683  add     rsp, 28h
0x180004687  pop     rdi
0x180004688  pop     rsi
0x180004689  pop     rbp
0x18000468a  pop     rbx
0x18000468b  retn
```
