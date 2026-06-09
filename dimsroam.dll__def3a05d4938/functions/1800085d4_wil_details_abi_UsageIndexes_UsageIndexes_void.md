# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800085d4`
- end: `0x180008661`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008284`
- `0x18000ae1c`
- `0x18000b8d0`

## callees

- `0x1800085d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008606`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000862b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008650`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008606`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000862b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008650`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000861d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008642`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000861d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008642`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(wil::details_abi::UsageIndexes *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax

  v1 = (void *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
  v4 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
}

```

## disassembly

```asm
0x1800085d4  mov     [rsp+arg_0], rbx
0x1800085d9  push    rdi
0x1800085da  sub     rsp, 20h
0x1800085de  mov     rdi, [rcx+0B0h]
0x1800085e5  mov     rbx, rcx
0x1800085e8  mov     qword ptr [rcx+0B0h], 0
0x1800085f3  test    rdi, rdi
0x1800085f6  jz      short loc_18000860C
0x1800085f8  call    cs:__imp_GetProcessHeap
0x1800085fe  mov     r8, rdi; lpMem
0x180008601  xor     edx, edx; dwFlags
0x180008603  mov     rcx, rax; hHeap
0x180008606  call    cs:__imp_HeapFree
0x18000860c  mov     rdi, [rbx+70h]
0x180008610  mov     qword ptr [rbx+70h], 0
0x180008618  test    rdi, rdi
0x18000861b  jz      short loc_180008631
0x18000861d  call    cs:__imp_GetProcessHeap
0x180008623  mov     r8, rdi; lpMem
0x180008626  xor     edx, edx; dwFlags
0x180008628  mov     rcx, rax; hHeap
0x18000862b  call    cs:__imp_HeapFree
0x180008631  mov     rdi, [rbx+30h]
0x180008635  mov     qword ptr [rbx+30h], 0
0x18000863d  test    rdi, rdi
0x180008640  jz      short loc_180008656
0x180008642  call    cs:__imp_GetProcessHeap
0x180008648  mov     r8, rdi; lpMem
0x18000864b  xor     edx, edx; dwFlags
0x18000864d  mov     rcx, rax; hHeap
0x180008650  call    cs:__imp_HeapFree
0x180008656  mov     rbx, [rsp+28h+arg_0]
0x18000865b  add     rsp, 20h
0x18000865f  pop     rdi
0x180008660  retn
```
