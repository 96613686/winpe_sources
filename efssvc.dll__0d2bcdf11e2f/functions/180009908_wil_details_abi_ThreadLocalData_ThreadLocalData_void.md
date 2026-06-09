# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180009908`
- end: `0x18000999d`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009834`

## callees

- `0x180009908`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009941`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000997e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009941`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000997e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000992d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000996a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000992d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000996a`

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
0x180009908  push    rbx
0x18000990a  push    rbp
0x18000990b  push    rsi
0x18000990c  push    rdi
0x18000990d  sub     rsp, 28h
0x180009911  movzx   eax, word ptr [rcx+20h]
0x180009915  mov     rsi, rcx
0x180009918  mov     rdi, [rcx+18h]
0x18000991c  lea     rbp, [rax+rax*4]
0x180009920  shl     rbp, 4
0x180009924  add     rbp, rdi
0x180009927  jmp     short loc_180009961
0x180009929  mov     rbx, [rdi+40h]
0x18000992d  call    cs:__imp_GetProcessHeap
0x180009934  nop     dword ptr [rax+rax+00h]
0x180009939  mov     r8, rbx; lpMem
0x18000993c  xor     edx, edx; dwFlags
0x18000993e  mov     rcx, rax; hHeap
0x180009941  call    cs:__imp_HeapFree
0x180009948  nop     dword ptr [rax+rax+00h]
0x18000994d  mov     qword ptr [rdi+40h], 0
0x180009955  mov     qword ptr [rdi+48h], 0
0x18000995d  add     rdi, 50h ; 'P'
0x180009961  cmp     rdi, rbp
0x180009964  jnz     short loc_180009929
0x180009966  mov     rbx, [rsi+18h]
0x18000996a  call    cs:__imp_GetProcessHeap
0x180009971  nop     dword ptr [rax+rax+00h]
0x180009976  mov     r8, rbx; lpMem
0x180009979  xor     edx, edx; dwFlags
0x18000997b  mov     rcx, rax; hHeap
0x18000997e  call    cs:__imp_HeapFree
0x180009985  nop     dword ptr [rax+rax+00h]
0x18000998a  xor     eax, eax
0x18000998c  mov     [rsi+20h], eax
0x18000998f  mov     [rsi+18h], rax
0x180009993  add     rsp, 28h
0x180009997  pop     rdi
0x180009998  pop     rsi
0x180009999  pop     rbp
0x18000999a  pop     rbx
0x18000999b  retn
```
