# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1400037c4`
- end: `0x140003851`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003350`
- `0x140005eb0`
- `0x1400069c0`
- `0x14001aa6d`

## callees

- `0x1400037c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400037f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000381b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003840`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400037f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000381b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003840`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400037e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000380d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003832`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400037e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000380d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003832`

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
0x1400037c4  mov     [rsp+arg_0], rbx
0x1400037c9  push    rdi
0x1400037ca  sub     rsp, 20h
0x1400037ce  mov     rdi, [rcx+0B0h]
0x1400037d5  mov     rbx, rcx
0x1400037d8  mov     qword ptr [rcx+0B0h], 0
0x1400037e3  test    rdi, rdi
0x1400037e6  jz      short loc_1400037FC
0x1400037e8  call    cs:__imp_GetProcessHeap
0x1400037ee  mov     r8, rdi; lpMem
0x1400037f1  xor     edx, edx; dwFlags
0x1400037f3  mov     rcx, rax; hHeap
0x1400037f6  call    cs:__imp_HeapFree
0x1400037fc  mov     rdi, [rbx+70h]
0x140003800  mov     qword ptr [rbx+70h], 0
0x140003808  test    rdi, rdi
0x14000380b  jz      short loc_140003821
0x14000380d  call    cs:__imp_GetProcessHeap
0x140003813  mov     r8, rdi; lpMem
0x140003816  xor     edx, edx; dwFlags
0x140003818  mov     rcx, rax; hHeap
0x14000381b  call    cs:__imp_HeapFree
0x140003821  mov     rdi, [rbx+30h]
0x140003825  mov     qword ptr [rbx+30h], 0
0x14000382d  test    rdi, rdi
0x140003830  jz      short loc_140003846
0x140003832  call    cs:__imp_GetProcessHeap
0x140003838  mov     r8, rdi; lpMem
0x14000383b  xor     edx, edx; dwFlags
0x14000383d  mov     rcx, rax; hHeap
0x140003840  call    cs:__imp_HeapFree
0x140003846  mov     rbx, [rsp+28h+arg_0]
0x14000384b  add     rsp, 20h
0x14000384f  pop     rdi
0x140003850  retn
```
