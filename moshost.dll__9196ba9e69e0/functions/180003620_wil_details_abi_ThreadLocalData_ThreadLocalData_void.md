# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003620`
- end: `0x18000369c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003468`

## callees

- `0x180003620`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003645`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003676`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003645`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003676`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003653`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003684`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003653`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003684`

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
0x180003620  push    rbx
0x180003622  push    rbp
0x180003623  push    rsi
0x180003624  push    rdi
0x180003625  sub     rsp, 28h
0x180003629  movzx   eax, word ptr [rcx+20h]
0x18000362d  mov     rsi, rcx
0x180003630  mov     rdi, [rcx+18h]
0x180003634  lea     rbp, [rax+rax*4]
0x180003638  shl     rbp, 4
0x18000363c  add     rbp, rdi
0x18000363f  jmp     short loc_18000366D
0x180003641  mov     rbx, [rdi+40h]
0x180003645  call    cs:__imp_GetProcessHeap
0x18000364b  mov     r8, rbx; lpMem
0x18000364e  xor     edx, edx; dwFlags
0x180003650  mov     rcx, rax; hHeap
0x180003653  call    cs:__imp_HeapFree
0x180003659  mov     qword ptr [rdi+40h], 0
0x180003661  mov     qword ptr [rdi+48h], 0
0x180003669  add     rdi, 50h ; 'P'
0x18000366d  cmp     rdi, rbp
0x180003670  jnz     short loc_180003641
0x180003672  mov     rbx, [rsi+18h]
0x180003676  call    cs:__imp_GetProcessHeap
0x18000367c  mov     r8, rbx; lpMem
0x18000367f  xor     edx, edx; dwFlags
0x180003681  mov     rcx, rax; hHeap
0x180003684  call    cs:__imp_HeapFree
0x18000368a  xor     eax, eax
0x18000368c  mov     [rsi+20h], eax
0x18000368f  mov     [rsi+18h], rax
0x180003693  add     rsp, 28h
0x180003697  pop     rdi
0x180003698  pop     rsi
0x180003699  pop     rbp
0x18000369a  pop     rbx
0x18000369b  retn
```
