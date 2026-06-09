# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x18000305c`
- end: `0x1800030f1`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e84`

## callees

- `0x18000305c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003081`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800030be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003081`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800030be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003095`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800030d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003095`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800030d2`

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
0x18000305c  push    rbx
0x18000305e  push    rbp
0x18000305f  push    rsi
0x180003060  push    rdi
0x180003061  sub     rsp, 28h
0x180003065  movzx   eax, word ptr [rcx+20h]
0x180003069  mov     rsi, rcx
0x18000306c  mov     rdi, [rcx+18h]
0x180003070  lea     rbp, [rax+rax*4]
0x180003074  shl     rbp, 4
0x180003078  add     rbp, rdi
0x18000307b  jmp     short loc_1800030B5
0x18000307d  mov     rbx, [rdi+40h]
0x180003081  call    cs:__imp_GetProcessHeap
0x180003088  nop     dword ptr [rax+rax+00h]
0x18000308d  mov     r8, rbx; lpMem
0x180003090  xor     edx, edx; dwFlags
0x180003092  mov     rcx, rax; hHeap
0x180003095  call    cs:__imp_HeapFree
0x18000309c  nop     dword ptr [rax+rax+00h]
0x1800030a1  mov     qword ptr [rdi+40h], 0
0x1800030a9  mov     qword ptr [rdi+48h], 0
0x1800030b1  add     rdi, 50h ; 'P'
0x1800030b5  cmp     rdi, rbp
0x1800030b8  jnz     short loc_18000307D
0x1800030ba  mov     rbx, [rsi+18h]
0x1800030be  call    cs:__imp_GetProcessHeap
0x1800030c5  nop     dword ptr [rax+rax+00h]
0x1800030ca  mov     r8, rbx; lpMem
0x1800030cd  xor     edx, edx; dwFlags
0x1800030cf  mov     rcx, rax; hHeap
0x1800030d2  call    cs:__imp_HeapFree
0x1800030d9  nop     dword ptr [rax+rax+00h]
0x1800030de  xor     eax, eax
0x1800030e0  mov     [rsi+20h], eax
0x1800030e3  mov     [rsi+18h], rax
0x1800030e7  add     rsp, 28h
0x1800030eb  pop     rdi
0x1800030ec  pop     rsi
0x1800030ed  pop     rbp
0x1800030ee  pop     rbx
0x1800030ef  retn
```
